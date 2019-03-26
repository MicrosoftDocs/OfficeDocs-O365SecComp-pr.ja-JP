---
title: 機密情報の種類の検索基準：
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できる状態で、80の機密情報の種類が含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。
ms.openlocfilehash: d161435c75149183289cfbfd6abe79d55e371e31
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30639194"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="56c6f-104">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="56c6f-104">What the sensitive information types look for</span></span>

<span data-ttu-id="56c6f-105">Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="56c6f-106">このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="56c6f-107">機密情報の種類はパターンで定義され、正規表現または関数で識別できます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="56c6f-108">機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="56c6f-109">信頼レベルと近接も、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="56c6f-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-111">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-111">Format</span></span>

<span data-ttu-id="56c6f-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-113">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-113">Pattern</span></span>

<span data-ttu-id="56c6f-114">さ</span><span class="sxs-lookup"><span data-stu-id="56c6f-114">Formatted:</span></span>
- <span data-ttu-id="56c6f-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="56c6f-116">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-116">A hyphen</span></span>
- <span data-ttu-id="56c6f-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-117">Four digits</span></span>
- <span data-ttu-id="56c6f-118">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-118">A hyphen</span></span>
- <span data-ttu-id="56c6f-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-119">A digit</span></span>

<span data-ttu-id="56c6f-120">書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="56c6f-121">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-121">Checksum</span></span>

<span data-ttu-id="56c6f-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-123">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-123">Definition</span></span>

<span data-ttu-id="56c6f-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="56c6f-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="56c6f-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="56c6f-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="56c6f-129">aba</span><span class="sxs-lookup"><span data-stu-id="56c6f-129">aba</span></span>
- <span data-ttu-id="56c6f-130">aba #</span><span class="sxs-lookup"><span data-stu-id="56c6f-130">aba #</span></span>
- <span data-ttu-id="56c6f-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="56c6f-131">aba routing #</span></span>
- <span data-ttu-id="56c6f-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="56c6f-132">aba routing number</span></span>
- <span data-ttu-id="56c6f-133">aba</span><span class="sxs-lookup"><span data-stu-id="56c6f-133">aba#</span></span>
- <span data-ttu-id="56c6f-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="56c6f-134">abarouting#</span></span>
- <span data-ttu-id="56c6f-135">aba number</span><span class="sxs-lookup"><span data-stu-id="56c6f-135">aba number</span></span>
- <span data-ttu-id="56c6f-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-136">abaroutingnumber</span></span>
- <span data-ttu-id="56c6f-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="56c6f-137">american bank association routing #</span></span>
- <span data-ttu-id="56c6f-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="56c6f-138">american bank association routing number</span></span>
- <span data-ttu-id="56c6f-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="56c6f-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="56c6f-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="56c6f-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="56c6f-141">bank routing number</span></span>
- <span data-ttu-id="56c6f-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="56c6f-142">bankrouting#</span></span>
- <span data-ttu-id="56c6f-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-143">bankroutingnumber</span></span>
- <span data-ttu-id="56c6f-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="56c6f-144">routing transit number</span></span>
- <span data-ttu-id="56c6f-145">rtn</span><span class="sxs-lookup"><span data-stu-id="56c6f-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="56c6f-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-147">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-147">Format</span></span>

<span data-ttu-id="56c6f-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-149">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-149">Pattern</span></span>

<span data-ttu-id="56c6f-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-150">Eight digits:</span></span>
- <span data-ttu-id="56c6f-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-151">Two digits</span></span>
- <span data-ttu-id="56c6f-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-152">A period</span></span>
- <span data-ttu-id="56c6f-153">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-153">Three digits</span></span>
- <span data-ttu-id="56c6f-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-154">A period</span></span>
- <span data-ttu-id="56c6f-155">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-156">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-156">Checksum</span></span>

<span data-ttu-id="56c6f-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-158">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-158">Definition</span></span>

<span data-ttu-id="56c6f-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-160">正規表現 Regex_argentina_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-161">Keyword_argentina_national_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="56c6f-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="56c6f-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="56c6f-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="56c6f-165">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-165">Identity</span></span> 
- <span data-ttu-id="56c6f-166">識別国の id カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="56c6f-167">DNI</span><span class="sxs-lookup"><span data-stu-id="56c6f-167">DNI</span></span> 
- <span data-ttu-id="56c6f-168">個人の NIC National レジストリ</span><span class="sxs-lookup"><span data-stu-id="56c6f-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="56c6f-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="56c6f-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="56c6f-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="56c6f-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="56c6f-171">dad の識別子</span><span class="sxs-lookup"><span data-stu-id="56c6f-171">Identidad</span></span> 
- <span data-ttu-id="56c6f-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="56c6f-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="56c6f-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-174">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-174">Format</span></span>

<span data-ttu-id="56c6f-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-176">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-176">Pattern</span></span>

<span data-ttu-id="56c6f-177">口座番号は 6 ～ 10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="56c6f-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="56c6f-178">オーストラリアの銀行の州支店番号:</span><span class="sxs-lookup"><span data-stu-id="56c6f-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="56c6f-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-179">Three digits</span></span> 
- <span data-ttu-id="56c6f-180">ハイフン</span><span class="sxs-lookup"><span data-stu-id="56c6f-180">A hyphen</span></span> 
- <span data-ttu-id="56c6f-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-182">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-182">Checksum</span></span>

<span data-ttu-id="56c6f-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-184">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-184">Definition</span></span>

<span data-ttu-id="56c6f-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="56c6f-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="56c6f-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="56c6f-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="56c6f-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="56c6f-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="56c6f-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="56c6f-194">swift bank code</span></span>
- <span data-ttu-id="56c6f-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="56c6f-195">correspondent bank</span></span>
- <span data-ttu-id="56c6f-196">base currency</span><span class="sxs-lookup"><span data-stu-id="56c6f-196">base currency</span></span>
- <span data-ttu-id="56c6f-197">usa account</span><span class="sxs-lookup"><span data-stu-id="56c6f-197">usa account</span></span>
- <span data-ttu-id="56c6f-198">holder address</span><span class="sxs-lookup"><span data-stu-id="56c6f-198">holder address</span></span>
- <span data-ttu-id="56c6f-199">bank address</span><span class="sxs-lookup"><span data-stu-id="56c6f-199">bank address</span></span>
- <span data-ttu-id="56c6f-200">information account</span><span class="sxs-lookup"><span data-stu-id="56c6f-200">information account</span></span>
- <span data-ttu-id="56c6f-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="56c6f-201">fund transfers</span></span>
- <span data-ttu-id="56c6f-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="56c6f-202">bank charges</span></span>
- <span data-ttu-id="56c6f-203">bank details</span><span class="sxs-lookup"><span data-stu-id="56c6f-203">bank details</span></span>
- <span data-ttu-id="56c6f-204">banking information</span><span class="sxs-lookup"><span data-stu-id="56c6f-204">banking information</span></span>
- <span data-ttu-id="56c6f-205">full names</span><span class="sxs-lookup"><span data-stu-id="56c6f-205">full names</span></span>
- <span data-ttu-id="56c6f-206">iaea</span><span class="sxs-lookup"><span data-stu-id="56c6f-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="56c6f-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-208">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-208">Format</span></span>

<span data-ttu-id="56c6f-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-210">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-210">Pattern</span></span>

<span data-ttu-id="56c6f-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="56c6f-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-213">Two digits</span></span> 
- <span data-ttu-id="56c6f-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="56c6f-215">OR</span><span class="sxs-lookup"><span data-stu-id="56c6f-215">OR</span></span>

- <span data-ttu-id="56c6f-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-217">4-9 digits</span></span>

<span data-ttu-id="56c6f-218">OR</span><span class="sxs-lookup"><span data-stu-id="56c6f-218">OR</span></span>

- <span data-ttu-id="56c6f-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="56c6f-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-220">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-220">Checksum</span></span>

<span data-ttu-id="56c6f-221">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-222">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-222">Definition</span></span>

<span data-ttu-id="56c6f-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="56c6f-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="56c6f-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="56c6f-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="56c6f-229">international driving permits</span></span>
- <span data-ttu-id="56c6f-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="56c6f-230">australian automobile association</span></span>
- <span data-ttu-id="56c6f-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="56c6f-231">international driving permit</span></span>
- <span data-ttu-id="56c6f-232">driverlicence</span><span class="sxs-lookup"><span data-stu-id="56c6f-232">DriverLicence</span></span>
- <span data-ttu-id="56c6f-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="56c6f-233">DriverLicences</span></span>
- <span data-ttu-id="56c6f-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-234">Driver Lic</span></span>
- <span data-ttu-id="56c6f-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-235">Driver Licence</span></span>
- <span data-ttu-id="56c6f-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-236">Driver Licences</span></span>
- <span data-ttu-id="56c6f-237">driverslic</span><span class="sxs-lookup"><span data-stu-id="56c6f-237">DriversLic</span></span>
- <span data-ttu-id="56c6f-238">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-238">DriversLicence</span></span>
- <span data-ttu-id="56c6f-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="56c6f-239">DriversLicences</span></span>
- <span data-ttu-id="56c6f-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-240">Drivers Lic</span></span>
- <span data-ttu-id="56c6f-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-241">Drivers Lics</span></span>
- <span data-ttu-id="56c6f-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-242">Drivers Licence</span></span>
- <span data-ttu-id="56c6f-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-243">Drivers Licences</span></span>
- <span data-ttu-id="56c6f-244">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-244">Driver'Lic</span></span>
- <span data-ttu-id="56c6f-245">driver' lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-245">Driver'Lics</span></span>
- <span data-ttu-id="56c6f-246">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-246">Driver'Licence</span></span>
- <span data-ttu-id="56c6f-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-247">Driver'Licences</span></span>
- <span data-ttu-id="56c6f-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-248">Driver' Lic</span></span>
- <span data-ttu-id="56c6f-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-249">Driver' Lics</span></span>
- <span data-ttu-id="56c6f-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-250">Driver' Licence</span></span>
- <span data-ttu-id="56c6f-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-251">Driver' Licences</span></span>
- <span data-ttu-id="56c6f-252">driver' slic</span><span class="sxs-lookup"><span data-stu-id="56c6f-252">Driver'sLic</span></span>
- <span data-ttu-id="56c6f-253">driver' slics</span><span class="sxs-lookup"><span data-stu-id="56c6f-253">Driver'sLics</span></span>
- <span data-ttu-id="56c6f-254">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="56c6f-254">Driver'sLicence</span></span>
- <span data-ttu-id="56c6f-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="56c6f-255">Driver'sLicences</span></span>
- <span data-ttu-id="56c6f-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-256">Driver's Lic</span></span>
- <span data-ttu-id="56c6f-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-257">Driver's Lics</span></span>
- <span data-ttu-id="56c6f-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-258">Driver's Licence</span></span>
- <span data-ttu-id="56c6f-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-259">Driver's Licences</span></span>
- <span data-ttu-id="56c6f-260">driverlic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-260">DriverLic#</span></span>
- <span data-ttu-id="56c6f-261">driverlics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-261">DriverLics#</span></span>
- <span data-ttu-id="56c6f-262">driverlicence #</span><span class="sxs-lookup"><span data-stu-id="56c6f-262">DriverLicence#</span></span>
- <span data-ttu-id="56c6f-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-263">DriverLicences#</span></span>
- <span data-ttu-id="56c6f-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-264">Driver Lic#</span></span>
- <span data-ttu-id="56c6f-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-265">Driver Lics#</span></span>
- <span data-ttu-id="56c6f-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-266">Driver Licence#</span></span>
- <span data-ttu-id="56c6f-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-267">Driver Licences#</span></span>
- <span data-ttu-id="56c6f-268">driverslic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-268">DriversLic#</span></span>
- <span data-ttu-id="56c6f-269">driverslics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-269">DriversLics#</span></span>
- <span data-ttu-id="56c6f-270">のデモライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-270">DriversLicence#</span></span>
- <span data-ttu-id="56c6f-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-271">DriversLicences#</span></span>
- <span data-ttu-id="56c6f-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-272">Drivers Lic#</span></span>
- <span data-ttu-id="56c6f-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-273">Drivers Lics#</span></span>
- <span data-ttu-id="56c6f-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-274">Drivers Licence#</span></span>
- <span data-ttu-id="56c6f-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-275">Drivers Licences#</span></span>
- <span data-ttu-id="56c6f-276">driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-276">Driver'Lic#</span></span>
- <span data-ttu-id="56c6f-277">driver' lics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-277">Driver'Lics#</span></span>
- <span data-ttu-id="56c6f-278">driver' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-278">Driver'Licence#</span></span>
- <span data-ttu-id="56c6f-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-279">Driver'Licences#</span></span>
- <span data-ttu-id="56c6f-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-280">Driver' Lic#</span></span>
- <span data-ttu-id="56c6f-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-281">Driver' Lics#</span></span>
- <span data-ttu-id="56c6f-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-282">Driver' Licence#</span></span>
- <span data-ttu-id="56c6f-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-283">Driver' Licences#</span></span>
- <span data-ttu-id="56c6f-284">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-284">Driver'sLic#</span></span>
- <span data-ttu-id="56c6f-285">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-285">Driver'sLics#</span></span>
- <span data-ttu-id="56c6f-286">ドライバ ' スライスの持続性 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-286">Driver'sLicence#</span></span>
- <span data-ttu-id="56c6f-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-287">Driver'sLicences#</span></span>
- <span data-ttu-id="56c6f-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-288">Driver's Lic#</span></span>
- <span data-ttu-id="56c6f-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-289">Driver's Lics#</span></span>
- <span data-ttu-id="56c6f-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-290">Driver's Licence#</span></span>
- <span data-ttu-id="56c6f-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="56c6f-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="56c6f-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="56c6f-293">aaa</span><span class="sxs-lookup"><span data-stu-id="56c6f-293">aaa</span></span>
- <span data-ttu-id="56c6f-294">driverlicense</span><span class="sxs-lookup"><span data-stu-id="56c6f-294">DriverLicense</span></span>
- <span data-ttu-id="56c6f-295">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-295">DriverLicenses</span></span>
- <span data-ttu-id="56c6f-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="56c6f-296">Driver License</span></span>
- <span data-ttu-id="56c6f-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-297">Driver Licenses</span></span>
- <span data-ttu-id="56c6f-298">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="56c6f-298">DriversLicense</span></span>
- <span data-ttu-id="56c6f-299">このライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-299">DriversLicenses</span></span>
- <span data-ttu-id="56c6f-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="56c6f-300">Drivers License</span></span>
- <span data-ttu-id="56c6f-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-301">Drivers Licenses</span></span>
- <span data-ttu-id="56c6f-302">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-302">Driver'License</span></span>
- <span data-ttu-id="56c6f-303">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-303">Driver'Licenses</span></span>
- <span data-ttu-id="56c6f-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="56c6f-304">Driver' License</span></span>
- <span data-ttu-id="56c6f-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-305">Driver' Licenses</span></span>
- <span data-ttu-id="56c6f-306">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-306">Driver'sLicense</span></span>
- <span data-ttu-id="56c6f-307">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-307">Driver'sLicenses</span></span>
- <span data-ttu-id="56c6f-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="56c6f-308">Driver's License</span></span>
- <span data-ttu-id="56c6f-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-309">Driver's Licenses</span></span>
- <span data-ttu-id="56c6f-310">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="56c6f-310">DriverLicense#</span></span>
- <span data-ttu-id="56c6f-311">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="56c6f-311">DriverLicenses#</span></span>
- <span data-ttu-id="56c6f-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-312">Driver License#</span></span>
- <span data-ttu-id="56c6f-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-313">Driver Licenses#</span></span>
- <span data-ttu-id="56c6f-314">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-314">DriversLicense#</span></span>
- <span data-ttu-id="56c6f-315">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-315">DriversLicenses#</span></span>
- <span data-ttu-id="56c6f-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-316">Drivers License#</span></span>
- <span data-ttu-id="56c6f-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-317">Drivers Licenses#</span></span>
- <span data-ttu-id="56c6f-318">driver' License #</span><span class="sxs-lookup"><span data-stu-id="56c6f-318">Driver'License#</span></span>
- <span data-ttu-id="56c6f-319">driver' Licenses #</span><span class="sxs-lookup"><span data-stu-id="56c6f-319">Driver'Licenses#</span></span>
- <span data-ttu-id="56c6f-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-320">Driver' License#</span></span>
- <span data-ttu-id="56c6f-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-321">Driver' Licenses#</span></span>
- <span data-ttu-id="56c6f-322">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-322">Driver'sLicense#</span></span>
- <span data-ttu-id="56c6f-323">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="56c6f-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-324">Driver's License#</span></span>
- <span data-ttu-id="56c6f-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="56c6f-326">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-327">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-327">Format</span></span>

<span data-ttu-id="56c6f-328">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-329">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-329">Pattern</span></span>

<span data-ttu-id="56c6f-330">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-330">10-11 digits:</span></span>
- <span data-ttu-id="56c6f-331">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="56c6f-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="56c6f-332">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="56c6f-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="56c6f-333">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="56c6f-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="56c6f-334">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-335">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-335">Checksum</span></span>

<span data-ttu-id="56c6f-336">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-337">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-337">Definition</span></span>

<span data-ttu-id="56c6f-338">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-339">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-340">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="56c6f-341">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-341">The checksum passes.</span></span>

<span data-ttu-id="56c6f-342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-343">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-344">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-345">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="56c6f-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="56c6f-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="56c6f-347">bank account details</span></span>
- <span data-ttu-id="56c6f-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="56c6f-348">medicare payments</span></span>
- <span data-ttu-id="56c6f-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="56c6f-349">mortgage account</span></span>
- <span data-ttu-id="56c6f-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="56c6f-350">bank payments</span></span>
- <span data-ttu-id="56c6f-351">information branch</span><span class="sxs-lookup"><span data-stu-id="56c6f-351">information branch</span></span>
- <span data-ttu-id="56c6f-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="56c6f-352">credit card loan</span></span>
- <span data-ttu-id="56c6f-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="56c6f-353">department of human services</span></span>
- <span data-ttu-id="56c6f-354">local service</span><span class="sxs-lookup"><span data-stu-id="56c6f-354">local service</span></span>
- <span data-ttu-id="56c6f-355">medicare</span><span class="sxs-lookup"><span data-stu-id="56c6f-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="56c6f-356">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-357">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-357">Format</span></span>

<span data-ttu-id="56c6f-358">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-359">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-359">Pattern</span></span>

<span data-ttu-id="56c6f-360">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-361">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-361">Checksum</span></span>

<span data-ttu-id="56c6f-362">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-363">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-363">Definition</span></span>

<span data-ttu-id="56c6f-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-365">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-366">Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-367">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="56c6f-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-368">Keyword_passport</span></span>

- <span data-ttu-id="56c6f-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-369">Passport Number</span></span>
- <span data-ttu-id="56c6f-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="56c6f-370">Passport No</span></span>
- <span data-ttu-id="56c6f-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-371">Passport #</span></span>
- <span data-ttu-id="56c6f-372">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-372">Passport#</span></span>
- <span data-ttu-id="56c6f-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="56c6f-373">PassportID</span></span>
- <span data-ttu-id="56c6f-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="56c6f-374">Passportno</span></span>
- <span data-ttu-id="56c6f-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-375">passportnumber</span></span>
- <span data-ttu-id="56c6f-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-376">パスポート</span></span>
- <span data-ttu-id="56c6f-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-377">パスポート番号</span></span>
- <span data-ttu-id="56c6f-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="56c6f-378">パスポートのNum</span></span>
- <span data-ttu-id="56c6f-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="56c6f-379">パスポート ＃</span></span> 
- <span data-ttu-id="56c6f-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="56c6f-380">Numéro de passeport</span></span>
- <span data-ttu-id="56c6f-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-381">Passeport n °</span></span>
- <span data-ttu-id="56c6f-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="56c6f-382">Passeport Non</span></span>
- <span data-ttu-id="56c6f-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-383">Passeport #</span></span>
- <span data-ttu-id="56c6f-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-384">Passeport#</span></span>
- <span data-ttu-id="56c6f-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="56c6f-385">PasseportNon</span></span>
- <span data-ttu-id="56c6f-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="56c6f-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="56c6f-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="56c6f-388">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-388">passport</span></span>
- <span data-ttu-id="56c6f-389">passport details</span><span class="sxs-lookup"><span data-stu-id="56c6f-389">passport details</span></span>
- <span data-ttu-id="56c6f-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="56c6f-390">immigration and citizenship</span></span>
- <span data-ttu-id="56c6f-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="56c6f-391">commonwealth of australia</span></span>
- <span data-ttu-id="56c6f-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="56c6f-392">department of immigration</span></span>
- <span data-ttu-id="56c6f-393">residential address</span><span class="sxs-lookup"><span data-stu-id="56c6f-393">residential address</span></span>
- <span data-ttu-id="56c6f-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="56c6f-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="56c6f-395">visa</span><span class="sxs-lookup"><span data-stu-id="56c6f-395">visa</span></span>
- <span data-ttu-id="56c6f-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="56c6f-396">national identity card</span></span>
- <span data-ttu-id="56c6f-397">passport number</span><span class="sxs-lookup"><span data-stu-id="56c6f-397">passport number</span></span>
- <span data-ttu-id="56c6f-398">travel document</span><span class="sxs-lookup"><span data-stu-id="56c6f-398">travel document</span></span>
- <span data-ttu-id="56c6f-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="56c6f-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="56c6f-400">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-401">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-401">Format</span></span>

<span data-ttu-id="56c6f-402">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-403">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-403">Pattern</span></span>

<span data-ttu-id="56c6f-404">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="56c6f-405">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-405">Three digits</span></span> 
- <span data-ttu-id="56c6f-406">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-406">An optional space</span></span> 
- <span data-ttu-id="56c6f-407">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-407">Three digits</span></span> 
- <span data-ttu-id="56c6f-408">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-408">An optional space</span></span> 
- <span data-ttu-id="56c6f-409">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="56c6f-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-410">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-410">Checksum</span></span>

<span data-ttu-id="56c6f-411">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-412">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-412">Definition</span></span>

<span data-ttu-id="56c6f-413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-414">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-415">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="56c6f-416">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="56c6f-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="56c6f-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="56c6f-419">australian business number</span></span>
- <span data-ttu-id="56c6f-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="56c6f-420">marginal tax rate</span></span>
- <span data-ttu-id="56c6f-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="56c6f-421">medicare levy</span></span>
- <span data-ttu-id="56c6f-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="56c6f-422">portfolio number</span></span>
- <span data-ttu-id="56c6f-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="56c6f-423">service veterans</span></span>
- <span data-ttu-id="56c6f-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="56c6f-424">withholding tax</span></span>
- <span data-ttu-id="56c6f-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="56c6f-425">individual tax return</span></span>
- <span data-ttu-id="56c6f-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="56c6f-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="56c6f-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="56c6f-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="56c6f-428">00000000</span><span class="sxs-lookup"><span data-stu-id="56c6f-428">00000000</span></span>
- <span data-ttu-id="56c6f-429">11111111</span><span class="sxs-lookup"><span data-stu-id="56c6f-429">11111111</span></span>
- <span data-ttu-id="56c6f-430">22222222</span><span class="sxs-lookup"><span data-stu-id="56c6f-430">22222222</span></span>
- <span data-ttu-id="56c6f-431">33333333</span><span class="sxs-lookup"><span data-stu-id="56c6f-431">33333333</span></span>
- <span data-ttu-id="56c6f-432">44444444</span><span class="sxs-lookup"><span data-stu-id="56c6f-432">44444444</span></span>
- <span data-ttu-id="56c6f-433">55555555</span><span class="sxs-lookup"><span data-stu-id="56c6f-433">55555555</span></span>
- <span data-ttu-id="56c6f-434">66666666</span><span class="sxs-lookup"><span data-stu-id="56c6f-434">66666666</span></span>
- <span data-ttu-id="56c6f-435">77777777</span><span class="sxs-lookup"><span data-stu-id="56c6f-435">77777777</span></span>
- <span data-ttu-id="56c6f-436">88888888</span><span class="sxs-lookup"><span data-stu-id="56c6f-436">88888888</span></span>
- <span data-ttu-id="56c6f-437">99999999</span><span class="sxs-lookup"><span data-stu-id="56c6f-437">99999999</span></span>
- <span data-ttu-id="56c6f-438">000000000</span><span class="sxs-lookup"><span data-stu-id="56c6f-438">000000000</span></span>
- <span data-ttu-id="56c6f-439">111111111</span><span class="sxs-lookup"><span data-stu-id="56c6f-439">111111111</span></span>
- <span data-ttu-id="56c6f-440">222222222</span><span class="sxs-lookup"><span data-stu-id="56c6f-440">222222222</span></span>
- <span data-ttu-id="56c6f-441">333333333</span><span class="sxs-lookup"><span data-stu-id="56c6f-441">333333333</span></span>
- <span data-ttu-id="56c6f-442">444444444</span><span class="sxs-lookup"><span data-stu-id="56c6f-442">444444444</span></span>
- <span data-ttu-id="56c6f-443">555555555</span><span class="sxs-lookup"><span data-stu-id="56c6f-443">555555555</span></span>
- <span data-ttu-id="56c6f-444">666666666</span><span class="sxs-lookup"><span data-stu-id="56c6f-444">666666666</span></span>
- <span data-ttu-id="56c6f-445">777777777</span><span class="sxs-lookup"><span data-stu-id="56c6f-445">777777777</span></span>
- <span data-ttu-id="56c6f-446">888888888</span><span class="sxs-lookup"><span data-stu-id="56c6f-446">888888888</span></span>
- <span data-ttu-id="56c6f-447">999999999</span><span class="sxs-lookup"><span data-stu-id="56c6f-447">999999999</span></span>
- <span data-ttu-id="56c6f-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="56c6f-448">0000000000</span></span>
- <span data-ttu-id="56c6f-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="56c6f-449">1111111111</span></span>
- <span data-ttu-id="56c6f-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="56c6f-450">2222222222</span></span>
- <span data-ttu-id="56c6f-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="56c6f-451">3333333333</span></span>
- <span data-ttu-id="56c6f-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="56c6f-452">4444444444</span></span>
- <span data-ttu-id="56c6f-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="56c6f-453">5555555555</span></span>
- <span data-ttu-id="56c6f-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="56c6f-454">6666666666</span></span>
- <span data-ttu-id="56c6f-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="56c6f-455">7777777777</span></span>
- <span data-ttu-id="56c6f-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="56c6f-456">8888888888</span></span>
- <span data-ttu-id="56c6f-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="56c6f-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="56c6f-458">Azure DocumentDB 認証キー</span><span class="sxs-lookup"><span data-stu-id="56c6f-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-459">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-459">Format</span></span>

<span data-ttu-id="56c6f-460">文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-461">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-461">Pattern</span></span>

- <span data-ttu-id="56c6f-462">文字列 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="56c6f-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="56c6f-463">3-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-464">より大きい記号 (>)、等号 (=)、二重引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="56c6f-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="56c6f-465">86の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="56c6f-466">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-467">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-467">Checksum</span></span>

<span data-ttu-id="56c6f-468">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-469">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-469">Definition</span></span>

<span data-ttu-id="56c6f-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-471">正規表現 CEP_Regex_AzureDocumentDBAuthKey は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-472">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-473">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-475">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-476">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-476">contoso</span></span>
- <span data-ttu-id="56c6f-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-477">fabrikam</span></span>
- <span data-ttu-id="56c6f-478">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-478">northwind</span></span>
- <span data-ttu-id="56c6f-479">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-479">sandbox</span></span>
- <span data-ttu-id="56c6f-480">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-480">onebox</span></span>
- <span data-ttu-id="56c6f-481">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-481">localhost</span></span>
- <span data-ttu-id="56c6f-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-482">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-483">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-484">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-484">com</span></span>
- <span data-ttu-id="56c6f-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-486">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="56c6f-487">azure IAAS データベースの接続文字列と azure SQL 接続文字列</span><span class="sxs-lookup"><span data-stu-id="56c6f-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-488">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-488">Format</span></span>

<span data-ttu-id="56c6f-489">文字列 "server"、"server"、または "data source" の後に、次のパターンで概説されている文字と文字列を指定します (文字列 "cloudapp" を含む)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-490">com または "cloudapp azure。</span><span class="sxs-lookup"><span data-stu-id="56c6f-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-491">net "または" database "です。</span><span class="sxs-lookup"><span data-stu-id="56c6f-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-492">net "、および" password "または" pwd "という文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-493">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-493">Pattern</span></span>

- <span data-ttu-id="56c6f-494">文字列 "server"、"server"、または "data source"</span><span class="sxs-lookup"><span data-stu-id="56c6f-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="56c6f-495">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-496">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-496">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-497">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-498">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-499">文字列 "cloudapp。</span><span class="sxs-lookup"><span data-stu-id="56c6f-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="56c6f-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-501">net "、または" database "です。</span><span class="sxs-lookup"><span data-stu-id="56c6f-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-502">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-502">net"</span></span>
- <span data-ttu-id="56c6f-503">1-300 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-504">文字列 "password"、"password"、または "pwd"</span><span class="sxs-lookup"><span data-stu-id="56c6f-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="56c6f-505">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-506">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-506">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-507">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-508">セミコロンではない1つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="56c6f-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="56c6f-509">セミコロン (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="56c6f-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-510">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-510">Checksum</span></span>

<span data-ttu-id="56c6f-511">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-512">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-512">Definition</span></span>

<span data-ttu-id="56c6f-513">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-514">正規表現 CEP_Regex_AzureConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-515">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-516">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-516">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-518">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-519">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-519">contoso</span></span>
- <span data-ttu-id="56c6f-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-520">fabrikam</span></span>
- <span data-ttu-id="56c6f-521">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-521">northwind</span></span>
- <span data-ttu-id="56c6f-522">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-522">sandbox</span></span>
- <span data-ttu-id="56c6f-523">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-523">onebox</span></span>
- <span data-ttu-id="56c6f-524">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-524">localhost</span></span>
- <span data-ttu-id="56c6f-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-525">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-526">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-527">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-527">com</span></span>
- <span data-ttu-id="56c6f-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-529">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="56c6f-530">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="56c6f-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-531">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-531">Format</span></span>

<span data-ttu-id="56c6f-532">文字列 "HostName" の後に、次のパターンで概説されている文字と文字列 ("azure デバイス" を含む)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-533">net "および" sharedaccesskey "。</span><span class="sxs-lookup"><span data-stu-id="56c6f-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-534">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-534">Pattern</span></span>

- <span data-ttu-id="56c6f-535">文字列 "HostName"</span><span class="sxs-lookup"><span data-stu-id="56c6f-535">The string "HostName"</span></span>
- <span data-ttu-id="56c6f-536">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-537">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-537">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-538">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-539">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-540">文字列 "azure デバイス。</span><span class="sxs-lookup"><span data-stu-id="56c6f-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-541">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-541">net"</span></span>
- <span data-ttu-id="56c6f-542">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-543">文字列 "sharedaccesskey"</span><span class="sxs-lookup"><span data-stu-id="56c6f-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="56c6f-544">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-545">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-545">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-546">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-547">43の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="56c6f-548">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-549">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-549">Checksum</span></span>

<span data-ttu-id="56c6f-550">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-551">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-551">Definition</span></span>

<span data-ttu-id="56c6f-552">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-553">正規表現 CEP_Regex_AzureIoTConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-554">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-555">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-555">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-557">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-558">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-558">contoso</span></span>
- <span data-ttu-id="56c6f-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-559">fabrikam</span></span>
- <span data-ttu-id="56c6f-560">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-560">northwind</span></span>
- <span data-ttu-id="56c6f-561">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-561">sandbox</span></span>
- <span data-ttu-id="56c6f-562">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-562">onebox</span></span>
- <span data-ttu-id="56c6f-563">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-563">localhost</span></span>
- <span data-ttu-id="56c6f-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-564">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-565">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-566">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-566">com</span></span>
- <span data-ttu-id="56c6f-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-568">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="56c6f-569">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-570">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-570">Format</span></span>

<span data-ttu-id="56c6f-571">文字列 "userpwd =" に続けて英数字の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-572">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-572">Pattern</span></span>

- <span data-ttu-id="56c6f-573">文字列 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="56c6f-573">The string "userpwd="</span></span>
- <span data-ttu-id="56c6f-574">60小文字または数字の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="56c6f-575">二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="56c6f-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-576">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-576">Checksum</span></span>

<span data-ttu-id="56c6f-577">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-578">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-578">Definition</span></span>

<span data-ttu-id="56c6f-579">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-580">正規表現 CEP_Regex_AzurePublishSettingPasswords は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-581">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="56c6f-582">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-582">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-584">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-585">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-585">contoso</span></span>
- <span data-ttu-id="56c6f-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-586">fabrikam</span></span>
- <span data-ttu-id="56c6f-587">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-587">northwind</span></span>
- <span data-ttu-id="56c6f-588">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-588">sandbox</span></span>
- <span data-ttu-id="56c6f-589">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-589">onebox</span></span>
- <span data-ttu-id="56c6f-590">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-590">localhost</span></span>
- <span data-ttu-id="56c6f-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-591">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-592">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-593">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-593">com</span></span>
- <span data-ttu-id="56c6f-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-595">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="56c6f-596">Azure Redis cache 接続文字列</span><span class="sxs-lookup"><span data-stu-id="56c6f-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-597">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-597">Format</span></span>

<span data-ttu-id="56c6f-598">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="56c6f-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-599">net "の後に、次のパターンで概説されている文字と文字列を指定します。文字列" password "または" pwd "が含まれます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-600">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-600">Pattern</span></span>

- <span data-ttu-id="56c6f-601">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="56c6f-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-602">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-602">net"</span></span>
- <span data-ttu-id="56c6f-603">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-604">文字列 "password" または "pwd"</span><span class="sxs-lookup"><span data-stu-id="56c6f-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="56c6f-605">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-606">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-606">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-607">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-608">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="56c6f-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="56c6f-609">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-610">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-610">Checksum</span></span>

<span data-ttu-id="56c6f-611">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-612">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-612">Definition</span></span>

<span data-ttu-id="56c6f-613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-614">正規表現 CEP_Regex_AzureRedisCacheConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="56c6f-615">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-616">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-616">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-618">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-619">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-619">contoso</span></span>
- <span data-ttu-id="56c6f-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-620">fabrikam</span></span>
- <span data-ttu-id="56c6f-621">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-621">northwind</span></span>
- <span data-ttu-id="56c6f-622">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-622">sandbox</span></span>
- <span data-ttu-id="56c6f-623">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-623">onebox</span></span>
- <span data-ttu-id="56c6f-624">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-624">localhost</span></span>
- <span data-ttu-id="56c6f-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-625">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-626">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-627">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-627">com</span></span>
- <span data-ttu-id="56c6f-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-629">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="56c6f-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="56c6f-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-631">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-631">Format</span></span>

<span data-ttu-id="56c6f-632">文字列 "sig" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-633">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-633">Pattern</span></span>

- <span data-ttu-id="56c6f-634">文字列 "sig"</span><span class="sxs-lookup"><span data-stu-id="56c6f-634">The string "sig"</span></span>
- <span data-ttu-id="56c6f-635">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-636">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-636">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-637">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-638">43-53 文字のうち、下位または大文字の文字、数字、またはパーセント記号 (%) の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="56c6f-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="56c6f-639">文字列 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="56c6f-639">The string "%3d"</span></span>
- <span data-ttu-id="56c6f-640">小文字または大文字、数字、パーセント記号 (%) 以外の文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-641">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-641">Checksum</span></span>

<span data-ttu-id="56c6f-642">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-643">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-643">Definition</span></span>

<span data-ttu-id="56c6f-644">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-645">正規表現 CEP_Regex_AzureSAS は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="56c6f-646">Azure Service Bus の接続文字列</span><span class="sxs-lookup"><span data-stu-id="56c6f-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-647">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-647">Format</span></span>

<span data-ttu-id="56c6f-648">文字列 "EndPoint" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-649">net "および" shared' キー "。</span><span class="sxs-lookup"><span data-stu-id="56c6f-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-650">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-650">Pattern</span></span>

- <span data-ttu-id="56c6f-651">文字列 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="56c6f-651">The string "EndPoint"</span></span>
- <span data-ttu-id="56c6f-652">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-653">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-653">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-654">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-655">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-656">文字列 "windows.</span><span class="sxs-lookup"><span data-stu-id="56c6f-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-657">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-657">net"</span></span>
- <span data-ttu-id="56c6f-658">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-659">文字列 "sharedaccesskey"</span><span class="sxs-lookup"><span data-stu-id="56c6f-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="56c6f-660">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-661">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-661">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-662">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-663">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="56c6f-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="56c6f-664">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-665">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-665">Checksum</span></span>

<span data-ttu-id="56c6f-666">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-667">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-667">Definition</span></span>

<span data-ttu-id="56c6f-668">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-669">正規表現 CEP_Regex_AzureServiceBusConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="56c6f-670">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-671">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-671">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-673">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-674">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-674">contoso</span></span>
- <span data-ttu-id="56c6f-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-675">fabrikam</span></span>
- <span data-ttu-id="56c6f-676">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-676">northwind</span></span>
- <span data-ttu-id="56c6f-677">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-677">sandbox</span></span>
- <span data-ttu-id="56c6f-678">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-678">onebox</span></span>
- <span data-ttu-id="56c6f-679">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-679">localhost</span></span>
- <span data-ttu-id="56c6f-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-680">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-681">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-682">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-682">com</span></span>
- <span data-ttu-id="56c6f-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-684">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="56c6f-685">Azure ストレージアカウントキー</span><span class="sxs-lookup"><span data-stu-id="56c6f-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-686">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-686">Format</span></span>

<span data-ttu-id="56c6f-687">文字列 "defaultendpointsprotocol" の後に、文字列 "AccountKey" を含む、次のパターンで概説されている文字および文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-688">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-688">Pattern</span></span>

- <span data-ttu-id="56c6f-689">文字列 "defaultendpointsprotocol"</span><span class="sxs-lookup"><span data-stu-id="56c6f-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="56c6f-690">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-691">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-691">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-692">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-693">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-694">文字列 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="56c6f-694">The string "AccountKey"</span></span>
- <span data-ttu-id="56c6f-695">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-696">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-696">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-697">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="56c6f-698">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="56c6f-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="56c6f-699">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-700">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-700">Checksum</span></span>

<span data-ttu-id="56c6f-701">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-702">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-702">Definition</span></span>

<span data-ttu-id="56c6f-703">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-704">正規表現 CEP_Regex_AzureStorageAccountKey は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-705">正規表現 CEP_AzureEmulatorStorageAccountFilter は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-706">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-707">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-707">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="56c6f-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="56c6f-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="56c6f-709">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/kbhbeksogmgw = =</span><span class="sxs-lookup"><span data-stu-id="56c6f-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-712">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-713">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-713">contoso</span></span>
- <span data-ttu-id="56c6f-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-714">fabrikam</span></span>
- <span data-ttu-id="56c6f-715">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-715">northwind</span></span>
- <span data-ttu-id="56c6f-716">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-716">sandbox</span></span>
- <span data-ttu-id="56c6f-717">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-717">onebox</span></span>
- <span data-ttu-id="56c6f-718">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-718">localhost</span></span>
- <span data-ttu-id="56c6f-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-719">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-720">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-721">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-721">com</span></span>
- <span data-ttu-id="56c6f-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-723">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="56c6f-724">Azure ストレージアカウントキー (汎用)</span><span class="sxs-lookup"><span data-stu-id="56c6f-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-725">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-725">Format</span></span>

<span data-ttu-id="56c6f-726">86の下または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、下のパターンで説明されている文字が前または後にある。</span><span class="sxs-lookup"><span data-stu-id="56c6f-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-727">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-727">Pattern</span></span>

- <span data-ttu-id="56c6f-728">0-1 より大きい記号 (>)、アポストロフィ (')、等号 (=)、二重引用符 (")、または番号記号 (#) を指定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="56c6f-729">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="56c6f-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="56c6f-730">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="56c6f-731">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-731">Checksum</span></span>

<span data-ttu-id="56c6f-732">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-733">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-733">Definition</span></span>

<span data-ttu-id="56c6f-734">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-735">正規表現 CEP_Regex_AzureStorageAccountKeyGeneric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="56c6f-736">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-737">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-737">Format</span></span>

<span data-ttu-id="56c6f-738">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-739">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-739">Pattern</span></span>

<span data-ttu-id="56c6f-740">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="56c6f-741">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="56c6f-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="56c6f-742">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-742">A hyphen</span></span> 
- <span data-ttu-id="56c6f-743">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="56c6f-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="56c6f-744">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="56c6f-744">A period</span></span> 
- <span data-ttu-id="56c6f-745">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-746">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-746">Checksum</span></span>

<span data-ttu-id="56c6f-747">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-748">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-748">Definition</span></span>

<span data-ttu-id="56c6f-749">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-750">関数 Func_belgium_national_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-751">Keyword_belgium_national_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="56c6f-752">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-752">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-753">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-753">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="56c6f-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="56c6f-755">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-755">Identity</span></span>
- <span data-ttu-id="56c6f-756">レジスタ</span><span class="sxs-lookup"><span data-stu-id="56c6f-756">Registration</span></span>
- <span data-ttu-id="56c6f-757">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-757">Identification</span></span> 
- <span data-ttu-id="56c6f-758">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-758">ID</span></span> 
- <span data-ttu-id="56c6f-759">「識別子」</span><span class="sxs-lookup"><span data-stu-id="56c6f-759">Identiteitskaart</span></span>
- <span data-ttu-id="56c6f-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-760">Registratie nummer</span></span> 
- <span data-ttu-id="56c6f-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-761">Identificatie nummer</span></span> 
- <span data-ttu-id="56c6f-762">識別子</span><span class="sxs-lookup"><span data-stu-id="56c6f-762">Identiteit</span></span>
- <span data-ttu-id="56c6f-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="56c6f-763">Registratie</span></span>
- <span data-ttu-id="56c6f-764">識別子</span><span class="sxs-lookup"><span data-stu-id="56c6f-764">Identificatie</span></span> 
- <span data-ttu-id="56c6f-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="56c6f-765">Carte d’identité</span></span> 
- <span data-ttu-id="56c6f-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="56c6f-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="56c6f-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="56c6f-767">numéro d'identification</span></span>
- <span data-ttu-id="56c6f-768">識別子</span><span class="sxs-lookup"><span data-stu-id="56c6f-768">identité</span></span> 
- <span data-ttu-id="56c6f-769">inscription</span><span class="sxs-lookup"><span data-stu-id="56c6f-769">inscription</span></span> 
- <span data-ttu-id="56c6f-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="56c6f-770">Identifikation</span></span>
- <span data-ttu-id="56c6f-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="56c6f-771">Identifizierung</span></span>
- <span data-ttu-id="56c6f-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-772">Identifikationsnummer</span></span>
- <span data-ttu-id="56c6f-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="56c6f-773">Personalausweis</span></span>
- <span data-ttu-id="56c6f-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="56c6f-774">Registrierung</span></span>
- <span data-ttu-id="56c6f-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="56c6f-776">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-777">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-777">Format</span></span>

<span data-ttu-id="56c6f-778">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-779">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-779">Pattern</span></span>

<span data-ttu-id="56c6f-780">さ</span><span class="sxs-lookup"><span data-stu-id="56c6f-780">Formatted:</span></span>
- <span data-ttu-id="56c6f-781">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-781">Three digits</span></span> 
- <span data-ttu-id="56c6f-782">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-782">A period</span></span> 
- <span data-ttu-id="56c6f-783">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-783">Three digits</span></span> 
- <span data-ttu-id="56c6f-784">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-784">A period</span></span> 
- <span data-ttu-id="56c6f-785">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-785">Three digits</span></span> 
- <span data-ttu-id="56c6f-786">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-786">A hyphen</span></span> 
- <span data-ttu-id="56c6f-787">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-787">Two digits which are check digits</span></span>

<span data-ttu-id="56c6f-788">なし</span><span class="sxs-lookup"><span data-stu-id="56c6f-788">Unformatted:</span></span>
- <span data-ttu-id="56c6f-789">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="56c6f-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-790">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-790">Checksum</span></span>

<span data-ttu-id="56c6f-791">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-792">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-792">Definition</span></span>

<span data-ttu-id="56c6f-793">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-794">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-795">Keyword_brazil_cpf からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="56c6f-796">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-796">The checksum passes.</span></span>

<span data-ttu-id="56c6f-797">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-798">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-799">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-799">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-800">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-800">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="56c6f-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="56c6f-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="56c6f-802">CPF</span><span class="sxs-lookup"><span data-stu-id="56c6f-802">CPF</span></span>
- <span data-ttu-id="56c6f-803">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-803">Identification</span></span>
- <span data-ttu-id="56c6f-804">レジスタ</span><span class="sxs-lookup"><span data-stu-id="56c6f-804">Registration</span></span>
- <span data-ttu-id="56c6f-805">増大</span><span class="sxs-lookup"><span data-stu-id="56c6f-805">Revenue</span></span>
- <span data-ttu-id="56c6f-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="56c6f-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="56c6f-807">imposto</span><span class="sxs-lookup"><span data-stu-id="56c6f-807">Imposto</span></span> 
- <span data-ttu-id="56c6f-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="56c6f-808">Identificação</span></span> 
- <span data-ttu-id="56c6f-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="56c6f-809">Inscrição</span></span> 
- <span data-ttu-id="56c6f-810">Receita</span><span class="sxs-lookup"><span data-stu-id="56c6f-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="56c6f-811">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="56c6f-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-812">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-812">Format</span></span>

<span data-ttu-id="56c6f-813">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-814">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-814">Pattern</span></span>
<span data-ttu-id="56c6f-815">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="56c6f-816">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-816">Two digits</span></span> 
- <span data-ttu-id="56c6f-817">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-817">A period</span></span> 
- <span data-ttu-id="56c6f-818">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-818">Three digits</span></span> 
- <span data-ttu-id="56c6f-819">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-819">A period</span></span> 
- <span data-ttu-id="56c6f-820">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="56c6f-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="56c6f-821">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-821">A forward slash</span></span> 
- <span data-ttu-id="56c6f-822">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="56c6f-822">Four-digit branch number</span></span> 
- <span data-ttu-id="56c6f-823">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-823">A hyphen</span></span> 
- <span data-ttu-id="56c6f-824">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-825">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-825">Checksum</span></span>

<span data-ttu-id="56c6f-826">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-827">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-827">Definition</span></span>

<span data-ttu-id="56c6f-828">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-829">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-830">Keyword_brazil_cnpj からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="56c6f-831">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-831">The checksum passes.</span></span>

<span data-ttu-id="56c6f-832">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-833">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-834">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-834">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-835">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-835">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="56c6f-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="56c6f-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="56c6f-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="56c6f-837">CNPJ</span></span> 
- <span data-ttu-id="56c6f-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="56c6f-838">CNPJ/MF</span></span> 
- <span data-ttu-id="56c6f-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="56c6f-839">CNPJ-MF</span></span> 
- <span data-ttu-id="56c6f-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="56c6f-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="56c6f-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="56c6f-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="56c6f-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="56c6f-842">Legal entity</span></span> 
- <span data-ttu-id="56c6f-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="56c6f-843">Legal entities</span></span> 
- <span data-ttu-id="56c6f-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="56c6f-844">Registration Status</span></span> 
- <span data-ttu-id="56c6f-845">Business</span><span class="sxs-lookup"><span data-stu-id="56c6f-845">Business</span></span> 
- <span data-ttu-id="56c6f-846">Company</span><span class="sxs-lookup"><span data-stu-id="56c6f-846">Company</span></span>
- <span data-ttu-id="56c6f-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="56c6f-847">CNPJ</span></span> 
- <span data-ttu-id="56c6f-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="56c6f-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="56c6f-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="56c6f-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="56c6f-850">cgc</span><span class="sxs-lookup"><span data-stu-id="56c6f-850">CGC</span></span> 
- <span data-ttu-id="56c6f-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="56c6f-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="56c6f-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="56c6f-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="56c6f-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="56c6f-853">Situação cadastral</span></span> 
- <span data-ttu-id="56c6f-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="56c6f-854">Inscrição</span></span> 
- <span data-ttu-id="56c6f-855">サイト</span><span class="sxs-lookup"><span data-stu-id="56c6f-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="56c6f-856">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="56c6f-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-857">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-857">Format</span></span>

<span data-ttu-id="56c6f-858">Registro geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="56c6f-859">Registro de 識別子 dade (ric) (新しい形式):11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-860">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-860">Pattern</span></span>

<span data-ttu-id="56c6f-861">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="56c6f-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="56c6f-862">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-862">Two digits</span></span> 
- <span data-ttu-id="56c6f-863">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-863">A period</span></span> 
- <span data-ttu-id="56c6f-864">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-864">Three digits</span></span> 
- <span data-ttu-id="56c6f-865">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-865">A period</span></span> 
- <span data-ttu-id="56c6f-866">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-866">Three digits</span></span> 
- <span data-ttu-id="56c6f-867">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-867">A hyphen</span></span> 
- <span data-ttu-id="56c6f-868">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-868">One digit which is a check digit</span></span>

<span data-ttu-id="56c6f-869">Registro de 識別子 dade (ric) (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="56c6f-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="56c6f-870">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-870">10 digits</span></span> 
- <span data-ttu-id="56c6f-871">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-871">A hyphen</span></span> 
- <span data-ttu-id="56c6f-872">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-873">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-873">Checksum</span></span>

<span data-ttu-id="56c6f-874">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-875">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-875">Definition</span></span>

<span data-ttu-id="56c6f-876">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-877">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-878">Keyword_brazil_rg からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="56c6f-879">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-879">The checksum passes.</span></span>

<span data-ttu-id="56c6f-880">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-881">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-882">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-882">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-883">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-883">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="56c6f-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="56c6f-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="56c6f-885">Cédula de 識別子 dade id カード national id número de rregistro registro de i識別子 dade registro geral このキーワードは大文字と小文字を区別します) ric (このキーワードは大文字と小文字を区別します)</span><span class="sxs-lookup"><span data-stu-id="56c6f-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="56c6f-886">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-887">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-887">Format</span></span>

<span data-ttu-id="56c6f-888">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-889">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-889">Pattern</span></span>

<span data-ttu-id="56c6f-890">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="56c6f-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="56c6f-891">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="56c6f-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="56c6f-892">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-892">Five digits</span></span> 
- <span data-ttu-id="56c6f-893">ハイフン</span><span class="sxs-lookup"><span data-stu-id="56c6f-893">A hyphen</span></span> 
- <span data-ttu-id="56c6f-894">3桁の数字または</span><span class="sxs-lookup"><span data-stu-id="56c6f-894">Three digits OR</span></span>
- <span data-ttu-id="56c6f-895">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="56c6f-895">A zero "0"</span></span> 
- <span data-ttu-id="56c6f-896">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-897">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-897">Checksum</span></span>

<span data-ttu-id="56c6f-898">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-899">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-899">Definition</span></span>

<span data-ttu-id="56c6f-900">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-901">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-902">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="56c6f-903">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="56c6f-904">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-905">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-906">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-907">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-907">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="56c6f-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="56c6f-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="56c6f-909">canada savings bonds</span></span>
- <span data-ttu-id="56c6f-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="56c6f-910">canada revenue agency</span></span>
- <span data-ttu-id="56c6f-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="56c6f-911">canadian financial institution</span></span>
- <span data-ttu-id="56c6f-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="56c6f-912">direct deposit form</span></span>
- <span data-ttu-id="56c6f-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="56c6f-913">canadian citizen</span></span>
- <span data-ttu-id="56c6f-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="56c6f-914">legal representative</span></span>
- <span data-ttu-id="56c6f-915">notary public</span><span class="sxs-lookup"><span data-stu-id="56c6f-915">notary public</span></span>
- <span data-ttu-id="56c6f-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="56c6f-916">commissioner for oaths</span></span>
- <span data-ttu-id="56c6f-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="56c6f-917">child care benefit</span></span>
- <span data-ttu-id="56c6f-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="56c6f-918">universal child care</span></span>
- <span data-ttu-id="56c6f-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="56c6f-919">canada child tax benefit</span></span>
- <span data-ttu-id="56c6f-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="56c6f-920">income tax benefit</span></span>
- <span data-ttu-id="56c6f-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="56c6f-921">harmonized sales tax</span></span>
- <span data-ttu-id="56c6f-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="56c6f-922">social insurance number</span></span>
- <span data-ttu-id="56c6f-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="56c6f-923">income tax refund</span></span>
- <span data-ttu-id="56c6f-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="56c6f-924">child tax benefit</span></span>
- <span data-ttu-id="56c6f-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="56c6f-925">territorial payments</span></span>
- <span data-ttu-id="56c6f-926">institution number</span><span class="sxs-lookup"><span data-stu-id="56c6f-926">institution number</span></span>
- <span data-ttu-id="56c6f-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="56c6f-927">deposit request</span></span>
- <span data-ttu-id="56c6f-928">banking information</span><span class="sxs-lookup"><span data-stu-id="56c6f-928">banking information</span></span>
- <span data-ttu-id="56c6f-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="56c6f-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="56c6f-930">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-931">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-931">Format</span></span>

<span data-ttu-id="56c6f-932">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="56c6f-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-933">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-933">Pattern</span></span>

<span data-ttu-id="56c6f-934">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-935">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-935">Checksum</span></span>

<span data-ttu-id="56c6f-936">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-937">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-937">Definition</span></span>

<span data-ttu-id="56c6f-938">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-939">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-940">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="56c6f-941">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-942">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-942">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="56c6f-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="56c6f-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="56c6f-944">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="56c6f-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="56c6f-945">州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="56c6f-945">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="56c6f-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="56c6f-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="56c6f-947">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-947">DL</span></span>
- <span data-ttu-id="56c6f-948">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-948">DLS</span></span>
- <span data-ttu-id="56c6f-949">CDL</span><span class="sxs-lookup"><span data-stu-id="56c6f-949">CDL</span></span>
- <span data-ttu-id="56c6f-950">cdls</span><span class="sxs-lookup"><span data-stu-id="56c6f-950">CDLS</span></span>
- <span data-ttu-id="56c6f-951">driverlic</span><span class="sxs-lookup"><span data-stu-id="56c6f-951">DriverLic</span></span>
- <span data-ttu-id="56c6f-952">driverlics</span><span class="sxs-lookup"><span data-stu-id="56c6f-952">DriverLics</span></span>
- <span data-ttu-id="56c6f-953">driverlicense</span><span class="sxs-lookup"><span data-stu-id="56c6f-953">DriverLicense</span></span>
- <span data-ttu-id="56c6f-954">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-954">DriverLicenses</span></span>
- <span data-ttu-id="56c6f-955">driverlicence</span><span class="sxs-lookup"><span data-stu-id="56c6f-955">DriverLicence</span></span>
- <span data-ttu-id="56c6f-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="56c6f-956">DriverLicences</span></span>
- <span data-ttu-id="56c6f-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-957">Driver Lic</span></span>
- <span data-ttu-id="56c6f-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-958">Driver Lics</span></span>
- <span data-ttu-id="56c6f-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="56c6f-959">Driver License</span></span>
- <span data-ttu-id="56c6f-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-960">Driver Licenses</span></span>
- <span data-ttu-id="56c6f-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-961">Driver Licence</span></span>
- <span data-ttu-id="56c6f-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-962">Driver Licences</span></span>
- <span data-ttu-id="56c6f-963">driverslic</span><span class="sxs-lookup"><span data-stu-id="56c6f-963">DriversLic</span></span>
- <span data-ttu-id="56c6f-964">driverslics</span><span class="sxs-lookup"><span data-stu-id="56c6f-964">DriversLics</span></span>
- <span data-ttu-id="56c6f-965">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-965">DriversLicence</span></span>
- <span data-ttu-id="56c6f-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="56c6f-966">DriversLicences</span></span>
- <span data-ttu-id="56c6f-967">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="56c6f-967">DriversLicense</span></span>
- <span data-ttu-id="56c6f-968">このライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-968">DriversLicenses</span></span>
- <span data-ttu-id="56c6f-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-969">Drivers Lic</span></span>
- <span data-ttu-id="56c6f-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-970">Drivers Lics</span></span>
- <span data-ttu-id="56c6f-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="56c6f-971">Drivers License</span></span>
- <span data-ttu-id="56c6f-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-972">Drivers Licenses</span></span>
- <span data-ttu-id="56c6f-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-973">Drivers Licence</span></span>
- <span data-ttu-id="56c6f-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-974">Drivers Licences</span></span>
- <span data-ttu-id="56c6f-975">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-975">Driver'Lic</span></span>
- <span data-ttu-id="56c6f-976">driver' lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-976">Driver'Lics</span></span>
- <span data-ttu-id="56c6f-977">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-977">Driver'License</span></span>
- <span data-ttu-id="56c6f-978">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-978">Driver'Licenses</span></span>
- <span data-ttu-id="56c6f-979">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-979">Driver'Licence</span></span>
- <span data-ttu-id="56c6f-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-980">Driver'Licences</span></span>
- <span data-ttu-id="56c6f-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-981">Driver' Lic</span></span>
- <span data-ttu-id="56c6f-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-982">Driver' Lics</span></span>
- <span data-ttu-id="56c6f-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="56c6f-983">Driver' License</span></span>
- <span data-ttu-id="56c6f-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-984">Driver' Licenses</span></span>
- <span data-ttu-id="56c6f-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-985">Driver' Licence</span></span>
- <span data-ttu-id="56c6f-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-986">Driver' Licences</span></span>
- <span data-ttu-id="56c6f-987">driver' slic</span><span class="sxs-lookup"><span data-stu-id="56c6f-987">Driver'sLic</span></span>
- <span data-ttu-id="56c6f-988">driver' slics</span><span class="sxs-lookup"><span data-stu-id="56c6f-988">Driver'sLics</span></span>
- <span data-ttu-id="56c6f-989">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-989">Driver'sLicense</span></span>
- <span data-ttu-id="56c6f-990">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-990">Driver'sLicenses</span></span>
- <span data-ttu-id="56c6f-991">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="56c6f-991">Driver'sLicence</span></span>
- <span data-ttu-id="56c6f-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="56c6f-992">Driver'sLicences</span></span>
- <span data-ttu-id="56c6f-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-993">Driver's Lic</span></span>
- <span data-ttu-id="56c6f-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-994">Driver's Lics</span></span>
- <span data-ttu-id="56c6f-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="56c6f-995">Driver's License</span></span>
- <span data-ttu-id="56c6f-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-996">Driver's Licenses</span></span>
- <span data-ttu-id="56c6f-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-997">Driver's Licence</span></span>
- <span data-ttu-id="56c6f-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-998">Driver's Licences</span></span>
- <span data-ttu-id="56c6f-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="56c6f-999">Permis de Conduire</span></span>
- <span data-ttu-id="56c6f-1000">id</span><span class="sxs-lookup"><span data-stu-id="56c6f-1000">id</span></span>
- <span data-ttu-id="56c6f-1001">ids</span><span class="sxs-lookup"><span data-stu-id="56c6f-1001">ids</span></span>
- <span data-ttu-id="56c6f-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1002">idcard number</span></span>
- <span data-ttu-id="56c6f-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-1003">idcard numbers</span></span>
- <span data-ttu-id="56c6f-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1004">idcard #</span></span>
- <span data-ttu-id="56c6f-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="56c6f-1005">idcard #s</span></span>
- <span data-ttu-id="56c6f-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1006">idcard card</span></span>
- <span data-ttu-id="56c6f-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1007">idcard cards</span></span>
- <span data-ttu-id="56c6f-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1008">idcard</span></span>
- <span data-ttu-id="56c6f-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1009">identification number</span></span>
- <span data-ttu-id="56c6f-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-1010">identification numbers</span></span>
- <span data-ttu-id="56c6f-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1011">identification #</span></span>
- <span data-ttu-id="56c6f-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="56c6f-1012">identification #s</span></span>
- <span data-ttu-id="56c6f-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1013">identification card</span></span>
- <span data-ttu-id="56c6f-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1014">identification cards</span></span>
- <span data-ttu-id="56c6f-1015">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-1015">identification</span></span> 
- <span data-ttu-id="56c6f-1016">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-1016">DL#</span></span>
- <span data-ttu-id="56c6f-1017">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-1017">DLS#</span></span> 
- <span data-ttu-id="56c6f-1018">CDL</span><span class="sxs-lookup"><span data-stu-id="56c6f-1018">CDL#</span></span> 
- <span data-ttu-id="56c6f-1019">cdls #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1019">CDLS#</span></span> 
- <span data-ttu-id="56c6f-1020">driverlic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1020">DriverLic#</span></span> 
- <span data-ttu-id="56c6f-1021">driverlics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1021">DriverLics#</span></span> 
- <span data-ttu-id="56c6f-1022">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1022">DriverLicense#</span></span> 
- <span data-ttu-id="56c6f-1023">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="56c6f-1024">driverlicence #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1024">DriverLicence#</span></span> 
- <span data-ttu-id="56c6f-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1025">DriverLicences#</span></span> 
- <span data-ttu-id="56c6f-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1026">Driver Lic#</span></span>
- <span data-ttu-id="56c6f-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1027">Driver Lics#</span></span> 
- <span data-ttu-id="56c6f-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1028">Driver License#</span></span> 
- <span data-ttu-id="56c6f-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="56c6f-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1030">Driver License#</span></span> 
- <span data-ttu-id="56c6f-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1031">Driver Licences#</span></span> 
- <span data-ttu-id="56c6f-1032">driverslic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1032">DriversLic#</span></span> 
- <span data-ttu-id="56c6f-1033">driverslics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1033">DriversLics#</span></span> 
- <span data-ttu-id="56c6f-1034">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1034">DriversLicense#</span></span> 
- <span data-ttu-id="56c6f-1035">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="56c6f-1036">のデモライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1036">DriversLicence#</span></span> 
- <span data-ttu-id="56c6f-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1037">DriversLicences#</span></span> 
- <span data-ttu-id="56c6f-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="56c6f-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="56c6f-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1040">Drivers License#</span></span> 
- <span data-ttu-id="56c6f-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="56c6f-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="56c6f-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="56c6f-1044">driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="56c6f-1045">driver' lics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="56c6f-1046">driver' License #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1046">Driver'License#</span></span> 
- <span data-ttu-id="56c6f-1047">driver' Licenses #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="56c6f-1048">driver' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="56c6f-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="56c6f-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="56c6f-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="56c6f-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1052">Driver' License#</span></span> 
- <span data-ttu-id="56c6f-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="56c6f-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="56c6f-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="56c6f-1056">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="56c6f-1057">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="56c6f-1058">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="56c6f-1059">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="56c6f-1060">ドライバ ' スライスの持続性 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="56c6f-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="56c6f-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="56c6f-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="56c6f-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1064">Driver's License#</span></span> 
- <span data-ttu-id="56c6f-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="56c6f-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="56c6f-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="56c6f-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="56c6f-1069">rid</span><span class="sxs-lookup"><span data-stu-id="56c6f-1069">id#</span></span> 
- <span data-ttu-id="56c6f-1070">rid</span><span class="sxs-lookup"><span data-stu-id="56c6f-1070">ids#</span></span> 
- <span data-ttu-id="56c6f-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1071">idcard card#</span></span> 
- <span data-ttu-id="56c6f-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1072">idcard cards#</span></span> 
- <span data-ttu-id="56c6f-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1073">idcard#</span></span> 
- <span data-ttu-id="56c6f-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1074">identification card#</span></span> 
- <span data-ttu-id="56c6f-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="56c6f-1075">identification cards#</span></span> 
- <span data-ttu-id="56c6f-1076">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="56c6f-1077">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1078">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1078">Format</span></span>

<span data-ttu-id="56c6f-1079">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1080">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1080">Pattern</span></span>

<span data-ttu-id="56c6f-1081">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1082">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1082">Checksum</span></span>

<span data-ttu-id="56c6f-1083">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1084">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1084">Definition</span></span>

<span data-ttu-id="56c6f-1085">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1086">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1087">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1088">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1088">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="56c6f-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="56c6f-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1090">personal health number</span></span>
- <span data-ttu-id="56c6f-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="56c6f-1091">patient information</span></span>
- <span data-ttu-id="56c6f-1092">health services</span><span class="sxs-lookup"><span data-stu-id="56c6f-1092">health services</span></span>
- <span data-ttu-id="56c6f-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="56c6f-1093">speciality services</span></span>
- <span data-ttu-id="56c6f-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="56c6f-1094">automobile accident</span></span>
- <span data-ttu-id="56c6f-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="56c6f-1095">patient hospital</span></span>
- <span data-ttu-id="56c6f-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="56c6f-1096">psychiatrist</span></span>
- <span data-ttu-id="56c6f-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="56c6f-1097">workers compensation</span></span>
- <span data-ttu-id="56c6f-1098">身体</span><span class="sxs-lookup"><span data-stu-id="56c6f-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="56c6f-1099">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1100">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1100">Format</span></span>

<span data-ttu-id="56c6f-1101">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1102">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1102">Pattern</span></span>

<span data-ttu-id="56c6f-1103">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1104">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1104">Checksum</span></span>

<span data-ttu-id="56c6f-1105">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1106">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1106">Definition</span></span>

<span data-ttu-id="56c6f-1107">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1108">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1109">Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1110">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1110">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="56c6f-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="56c6f-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="56c6f-1112">canadian citizenship</span></span>
- <span data-ttu-id="56c6f-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-1113">canadian passport</span></span>
- <span data-ttu-id="56c6f-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="56c6f-1114">passport application</span></span>
- <span data-ttu-id="56c6f-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="56c6f-1115">passport photos</span></span>
- <span data-ttu-id="56c6f-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="56c6f-1116">certified translator</span></span>
- <span data-ttu-id="56c6f-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="56c6f-1117">canadian citizens</span></span>
- <span data-ttu-id="56c6f-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="56c6f-1118">processing times</span></span>
- <span data-ttu-id="56c6f-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="56c6f-1119">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="56c6f-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-1120">Keyword_passport</span></span>

- <span data-ttu-id="56c6f-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1121">Passport Number</span></span>
- <span data-ttu-id="56c6f-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="56c6f-1122">Passport No</span></span>
- <span data-ttu-id="56c6f-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1123">Passport #</span></span>
- <span data-ttu-id="56c6f-1124">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-1124">Passport#</span></span>
- <span data-ttu-id="56c6f-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="56c6f-1125">PassportID</span></span>
- <span data-ttu-id="56c6f-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="56c6f-1126">Passportno</span></span>
- <span data-ttu-id="56c6f-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-1127">passportnumber</span></span>
- <span data-ttu-id="56c6f-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-1128">パスポート</span></span>
- <span data-ttu-id="56c6f-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1129">パスポート番号</span></span>
- <span data-ttu-id="56c6f-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1130">パスポートのNum</span></span>
- <span data-ttu-id="56c6f-1131">パスポート #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1131">パスポート＃</span></span>
- <span data-ttu-id="56c6f-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="56c6f-1132">Numéro de passeport</span></span>
- <span data-ttu-id="56c6f-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-1133">Passeport n °</span></span>
- <span data-ttu-id="56c6f-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="56c6f-1134">Passeport Non</span></span>
- <span data-ttu-id="56c6f-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1135">Passeport #</span></span>
- <span data-ttu-id="56c6f-1136">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-1136">Passeport#</span></span>
- <span data-ttu-id="56c6f-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="56c6f-1137">PasseportNon</span></span>
- <span data-ttu-id="56c6f-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="56c6f-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="56c6f-1139">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1140">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1140">Format</span></span>

<span data-ttu-id="56c6f-1141">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1142">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1142">Pattern</span></span>

<span data-ttu-id="56c6f-1143">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1144">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1144">Checksum</span></span>

<span data-ttu-id="56c6f-1145">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1146">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1146">Definition</span></span>

<span data-ttu-id="56c6f-1147">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-1148">Keyword_canada_phin または Keyword_canada_provinces から、少なくとも2つのキーワードが見つかります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1149">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1149">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="56c6f-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="56c6f-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="56c6f-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1151">social insurance number</span></span>
- <span data-ttu-id="56c6f-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="56c6f-1152">health information act</span></span>
- <span data-ttu-id="56c6f-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="56c6f-1153">income tax information</span></span>
- <span data-ttu-id="56c6f-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="56c6f-1154">manitoba health</span></span>
- <span data-ttu-id="56c6f-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="56c6f-1155">health registration</span></span>
- <span data-ttu-id="56c6f-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="56c6f-1156">prescription purchases</span></span>
- <span data-ttu-id="56c6f-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="56c6f-1157">benefit eligibility</span></span>
- <span data-ttu-id="56c6f-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="56c6f-1158">personal health</span></span>
- <span data-ttu-id="56c6f-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="56c6f-1159">power of attorney</span></span>
- <span data-ttu-id="56c6f-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1160">registration number</span></span>
- <span data-ttu-id="56c6f-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1161">personal health number</span></span>
- <span data-ttu-id="56c6f-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="56c6f-1162">practitioner referral</span></span>
- <span data-ttu-id="56c6f-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="56c6f-1163">wellness professional</span></span>
- <span data-ttu-id="56c6f-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="56c6f-1164">patient referral</span></span>
- <span data-ttu-id="56c6f-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="56c6f-1165">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="56c6f-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="56c6f-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="56c6f-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="56c6f-1167">Nunavut</span></span>
- <span data-ttu-id="56c6f-1168">州</span><span class="sxs-lookup"><span data-stu-id="56c6f-1168">Quebec</span></span>
- <span data-ttu-id="56c6f-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="56c6f-1169">Northwest Territories</span></span>
- <span data-ttu-id="56c6f-1170">オンタリオ州</span><span class="sxs-lookup"><span data-stu-id="56c6f-1170">Ontario</span></span>
- <span data-ttu-id="56c6f-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="56c6f-1171">British Columbia</span></span>
- <span data-ttu-id="56c6f-1172">州</span><span class="sxs-lookup"><span data-stu-id="56c6f-1172">Alberta</span></span>
- <span data-ttu-id="56c6f-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="56c6f-1173">Saskatchewan</span></span>
- <span data-ttu-id="56c6f-1174">マニトバ州</span><span class="sxs-lookup"><span data-stu-id="56c6f-1174">Manitoba</span></span>
- <span data-ttu-id="56c6f-1175">州</span><span class="sxs-lookup"><span data-stu-id="56c6f-1175">Yukon</span></span>
- <span data-ttu-id="56c6f-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="56c6f-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="56c6f-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="56c6f-1177">New Brunswick</span></span>
- <span data-ttu-id="56c6f-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="56c6f-1178">Nova Scotia</span></span>
- <span data-ttu-id="56c6f-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="56c6f-1179">Prince Edward Island</span></span>
- <span data-ttu-id="56c6f-1180">カナダ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="56c6f-1181">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1182">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1182">Format</span></span>

<span data-ttu-id="56c6f-1183">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1184">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1184">Pattern</span></span>

<span data-ttu-id="56c6f-1185">さ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1185">Formatted:</span></span>
- <span data-ttu-id="56c6f-1186">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1186">Three digits</span></span> 
- <span data-ttu-id="56c6f-1187">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-1187">A hyphen or space</span></span> 
- <span data-ttu-id="56c6f-1188">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1188">Three digits</span></span> 
- <span data-ttu-id="56c6f-1189">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-1189">A hyphen or space</span></span> 
- <span data-ttu-id="56c6f-1190">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1190">Three digits</span></span>

<span data-ttu-id="56c6f-1191">書式なし: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1192">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1192">Checksum</span></span>

<span data-ttu-id="56c6f-1193">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1194">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1194">Definition</span></span>

<span data-ttu-id="56c6f-1195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1196">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1197">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="56c6f-1198">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="56c6f-1199">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="56c6f-1200">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="56c6f-1201">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1201">The checksum passes.</span></span>

<span data-ttu-id="56c6f-1202">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1203">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1204">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="56c6f-1205">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1205">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1206">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1206">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="56c6f-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="56c6f-1207">Keyword_sin</span></span>

- <span data-ttu-id="56c6f-1208">sin</span><span class="sxs-lookup"><span data-stu-id="56c6f-1208">sin</span></span> 
- <span data-ttu-id="56c6f-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="56c6f-1209">social insurance</span></span> 
- <span data-ttu-id="56c6f-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="56c6f-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="56c6f-1211">大罪</span><span class="sxs-lookup"><span data-stu-id="56c6f-1211">sins</span></span> 
- <span data-ttu-id="56c6f-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="56c6f-1212">ssn</span></span> 
- <span data-ttu-id="56c6f-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="56c6f-1213">ssns</span></span> 
- <span data-ttu-id="56c6f-1214">social security</span><span class="sxs-lookup"><span data-stu-id="56c6f-1214">social security</span></span> 
- <span data-ttu-id="56c6f-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="56c6f-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="56c6f-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1216">national identification number</span></span> 
- <span data-ttu-id="56c6f-1217">national id</span><span class="sxs-lookup"><span data-stu-id="56c6f-1217">national id</span></span> 
- <span data-ttu-id="56c6f-1218">sin</span><span class="sxs-lookup"><span data-stu-id="56c6f-1218">sin#</span></span> 
- <span data-ttu-id="56c6f-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="56c6f-1219">soc ins</span></span> 
- <span data-ttu-id="56c6f-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="56c6f-1220">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="56c6f-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="56c6f-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="56c6f-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="56c6f-1222">driver's license</span></span> 
- <span data-ttu-id="56c6f-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="56c6f-1223">drivers license</span></span> 
- <span data-ttu-id="56c6f-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-1224">driver's licence</span></span> 
- <span data-ttu-id="56c6f-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-1225">drivers licence</span></span> 
- <span data-ttu-id="56c6f-1226">dob</span><span class="sxs-lookup"><span data-stu-id="56c6f-1226">DOB</span></span> 
- <span data-ttu-id="56c6f-1227">誕生日</span><span class="sxs-lookup"><span data-stu-id="56c6f-1227">Birthdate</span></span> 
- <span data-ttu-id="56c6f-1228">Birthday</span><span class="sxs-lookup"><span data-stu-id="56c6f-1228">Birthday</span></span> 
- <span data-ttu-id="56c6f-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="56c6f-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="56c6f-1230">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1231">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1231">Format</span></span>

<span data-ttu-id="56c6f-1232">7-8 桁の数字と区切り文字のチェックディジットまたは文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1233">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1233">Pattern</span></span>

<span data-ttu-id="56c6f-1234">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="56c6f-1235">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-1235">1-2 digits</span></span> 
- <span data-ttu-id="56c6f-1236">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-1236">A period</span></span> 
- <span data-ttu-id="56c6f-1237">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1237">Three digits</span></span> 
- <span data-ttu-id="56c6f-1238">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-1238">A period</span></span> 
- <span data-ttu-id="56c6f-1239">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1239">Three digits</span></span> 
- <span data-ttu-id="56c6f-1240">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-1240">A dash</span></span> 
- <span data-ttu-id="56c6f-1241">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1242">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1242">Checksum</span></span>

<span data-ttu-id="56c6f-1243">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1244">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1244">Definition</span></span>

<span data-ttu-id="56c6f-1245">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1246">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1247">Keyword_chile_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="56c6f-1248">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1248">The checksum passes.</span></span>

<span data-ttu-id="56c6f-1249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1250">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1251">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1251">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1252">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1252">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="56c6f-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="56c6f-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1254">National Identification Number</span></span> 
- <span data-ttu-id="56c6f-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1255">Identity card</span></span> 
- <span data-ttu-id="56c6f-1256">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-1256">ID</span></span> 
- <span data-ttu-id="56c6f-1257">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-1257">Identification</span></span> 
- <span data-ttu-id="56c6f-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="56c6f-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="56c6f-1259">実行</span><span class="sxs-lookup"><span data-stu-id="56c6f-1259">RUN</span></span> 
- <span data-ttu-id="56c6f-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="56c6f-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="56c6f-1261">類型</span><span class="sxs-lookup"><span data-stu-id="56c6f-1261">RUT</span></span> 
- <span data-ttu-id="56c6f-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="56c6f-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="56c6f-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="56c6f-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="56c6f-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="56c6f-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="56c6f-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="56c6f-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="56c6f-1266">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1267">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1267">Format</span></span>

<span data-ttu-id="56c6f-1268">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1269">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1269">Pattern</span></span>

<span data-ttu-id="56c6f-1270">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1270">18 digits:</span></span>
- <span data-ttu-id="56c6f-1271">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="56c6f-1272">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-1273">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="56c6f-1274">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1275">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1275">Checksum</span></span>

<span data-ttu-id="56c6f-1276">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1277">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1277">Definition</span></span>

<span data-ttu-id="56c6f-1278">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1279">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1280">Keyword_china_resident_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="56c6f-1281">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1281">The checksum passes.</span></span>

<span data-ttu-id="56c6f-1282">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1283">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1284">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1284">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1285">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1285">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="56c6f-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="56c6f-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="56c6f-1288">PRC</span><span class="sxs-lookup"><span data-stu-id="56c6f-1288">PRC</span></span> 
- <span data-ttu-id="56c6f-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1289">National Identification Card</span></span> 
- <span data-ttu-id="56c6f-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="56c6f-1290">身份证</span></span> 
- <span data-ttu-id="56c6f-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="56c6f-1291">居民 身份证</span></span> 
- <span data-ttu-id="56c6f-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="56c6f-1292">居民身份证</span></span> 
- <span data-ttu-id="56c6f-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="56c6f-1293">鉴定</span></span> 
- <span data-ttu-id="56c6f-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-1294">身分證</span></span> 
- <span data-ttu-id="56c6f-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-1295">居民 身份證</span></span>
- <span data-ttu-id="56c6f-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="56c6f-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="56c6f-1297">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1298">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1298">Format</span></span>

<span data-ttu-id="56c6f-1299">書式設定または書式設定ができない16桁の数字 (dddddddddddddddd)。 luhn テストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1300">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1300">Pattern</span></span>

<span data-ttu-id="56c6f-1301">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1302">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1302">Checksum</span></span>

<span data-ttu-id="56c6f-1303">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1304">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1304">Definition</span></span>

<span data-ttu-id="56c6f-1305">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1306">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1307">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1307">One of the following is true:</span></span>
    - <span data-ttu-id="56c6f-1308">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="56c6f-1309">Keyword_cc_name からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="56c6f-1310">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="56c6f-1311">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1311">The checksum passes.</span></span>

<span data-ttu-id="56c6f-1312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1313">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1314">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1314">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1315">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1315">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="56c6f-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="56c6f-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="56c6f-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="56c6f-1317">card verification</span></span>
- <span data-ttu-id="56c6f-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1318">card identification number</span></span>
- <span data-ttu-id="56c6f-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="56c6f-1319">cvn</span></span>
- <span data-ttu-id="56c6f-1320">cid</span><span class="sxs-lookup"><span data-stu-id="56c6f-1320">cid</span></span>
- <span data-ttu-id="56c6f-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="56c6f-1321">cvc2</span></span>
- <span data-ttu-id="56c6f-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="56c6f-1322">cvv2</span></span>
- <span data-ttu-id="56c6f-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="56c6f-1323">pin block</span></span>
- <span data-ttu-id="56c6f-1324">security code</span><span class="sxs-lookup"><span data-stu-id="56c6f-1324">security code</span></span>
- <span data-ttu-id="56c6f-1325">security number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1325">security number</span></span>
- <span data-ttu-id="56c6f-1326">security no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1326">security no</span></span>
- <span data-ttu-id="56c6f-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1327">issue number</span></span>
- <span data-ttu-id="56c6f-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1328">issue no</span></span>
- <span data-ttu-id="56c6f-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="56c6f-1329">cryptogramme</span></span>
- <span data-ttu-id="56c6f-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="56c6f-1330">numéro de sécurité</span></span>
- <span data-ttu-id="56c6f-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="56c6f-1331">numero de securite</span></span>
- <span data-ttu-id="56c6f-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="56c6f-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="56c6f-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1334">prüfziffer</span></span>
- <span data-ttu-id="56c6f-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1335">prufziffer</span></span>
- <span data-ttu-id="56c6f-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="56c6f-1336">sicherheits Kode</span></span>
- <span data-ttu-id="56c6f-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="56c6f-1337">sicherheitscode</span></span>
- <span data-ttu-id="56c6f-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="56c6f-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1339">verfalldatum</span></span>
- <span data-ttu-id="56c6f-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="56c6f-1340">codice di verifica</span></span>
- <span data-ttu-id="56c6f-1341">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1341">cod.</span></span> <span data-ttu-id="56c6f-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1342">sicurezza</span></span>
- <span data-ttu-id="56c6f-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1343">cod sicurezza</span></span>
- <span data-ttu-id="56c6f-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="56c6f-1344">n autorizzazione</span></span>
- <span data-ttu-id="56c6f-1345">código</span><span class="sxs-lookup"><span data-stu-id="56c6f-1345">código</span></span>
- <span data-ttu-id="56c6f-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="56c6f-1346">codigo</span></span>
- <span data-ttu-id="56c6f-1347">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1347">cod.</span></span> <span data-ttu-id="56c6f-1348">seg</span><span class="sxs-lookup"><span data-stu-id="56c6f-1348">seg</span></span>
- <span data-ttu-id="56c6f-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="56c6f-1349">cod seg</span></span>
- <span data-ttu-id="56c6f-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1350">código de segurança</span></span>
- <span data-ttu-id="56c6f-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1351">codigo de seguranca</span></span>
- <span data-ttu-id="56c6f-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1352">codigo de segurança</span></span>
- <span data-ttu-id="56c6f-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1353">código de seguranca</span></span>
- <span data-ttu-id="56c6f-1354">cód。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1354">cód.</span></span> <span data-ttu-id="56c6f-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1355">segurança</span></span>
- <span data-ttu-id="56c6f-1356">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1356">cod.</span></span> <span data-ttu-id="56c6f-1357">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1357">seguranca cod.</span></span> <span data-ttu-id="56c6f-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1358">segurança</span></span>
- <span data-ttu-id="56c6f-1359">cód。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1359">cód.</span></span> <span data-ttu-id="56c6f-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1360">seguranca</span></span>
- <span data-ttu-id="56c6f-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1361">cód segurança</span></span>
- <span data-ttu-id="56c6f-1362">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="56c6f-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1363">cód seguranca</span></span>
- <span data-ttu-id="56c6f-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="56c6f-1364">número de verificação</span></span>
- <span data-ttu-id="56c6f-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1365">numero de verificacao</span></span>
- <span data-ttu-id="56c6f-1366">ablん f</span><span class="sxs-lookup"><span data-stu-id="56c6f-1366">ablauf</span></span>
- <span data-ttu-id="56c6f-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="56c6f-1367">gültig bis</span></span>
- <span data-ttu-id="56c6f-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="56c6f-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="56c6f-1369">gultig bis</span></span>
- <span data-ttu-id="56c6f-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="56c6f-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1371">scadenza</span></span>
- <span data-ttu-id="56c6f-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="56c6f-1372">data scad</span></span>
- <span data-ttu-id="56c6f-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="56c6f-1373">fecha de expiracion</span></span>
- <span data-ttu-id="56c6f-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1374">fecha de venc</span></span>
- <span data-ttu-id="56c6f-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="56c6f-1375">vencimiento</span></span>
- <span data-ttu-id="56c6f-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1376">válido hasta</span></span>
- <span data-ttu-id="56c6f-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1377">valido hasta</span></span>
- <span data-ttu-id="56c6f-1378">vto</span><span class="sxs-lookup"><span data-stu-id="56c6f-1378">vto</span></span>
- <span data-ttu-id="56c6f-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="56c6f-1379">data de expiração</span></span>
- <span data-ttu-id="56c6f-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1380">data de expiracao</span></span>
- <span data-ttu-id="56c6f-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="56c6f-1381">data em que expira</span></span>
- <span data-ttu-id="56c6f-1382">validade</span><span class="sxs-lookup"><span data-stu-id="56c6f-1382">validade</span></span>
- <span data-ttu-id="56c6f-1383">valor は</span><span class="sxs-lookup"><span data-stu-id="56c6f-1383">valor</span></span>
- <span data-ttu-id="56c6f-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="56c6f-1384">vencimento</span></span>
- <span data-ttu-id="56c6f-1385">venc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1385">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="56c6f-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="56c6f-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="56c6f-1387">amex</span><span class="sxs-lookup"><span data-stu-id="56c6f-1387">amex</span></span>
- <span data-ttu-id="56c6f-1388">american express</span><span class="sxs-lookup"><span data-stu-id="56c6f-1388">american express</span></span>
- <span data-ttu-id="56c6f-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="56c6f-1389">americanexpress</span></span>
- <span data-ttu-id="56c6f-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="56c6f-1390">Visa</span></span>
- <span data-ttu-id="56c6f-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1391">mastercard</span></span>
- <span data-ttu-id="56c6f-1392">master card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1392">master card</span></span>
- <span data-ttu-id="56c6f-1393">mc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1393">mc</span></span> 
- <span data-ttu-id="56c6f-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1394">mastercards</span></span>
- <span data-ttu-id="56c6f-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1395">master cards</span></span>
- <span data-ttu-id="56c6f-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="56c6f-1396">diner's Club</span></span>
- <span data-ttu-id="56c6f-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="56c6f-1397">diners club</span></span>
- <span data-ttu-id="56c6f-1398">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1398">dinersclub</span></span>
- <span data-ttu-id="56c6f-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1399">discover card</span></span>
- <span data-ttu-id="56c6f-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1400">discovercard</span></span>
- <span data-ttu-id="56c6f-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1401">discover cards</span></span>
- <span data-ttu-id="56c6f-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="56c6f-1402">JCB</span></span>
- <span data-ttu-id="56c6f-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="56c6f-1403">japanese card bureau</span></span>
- <span data-ttu-id="56c6f-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="56c6f-1404">carte blanche</span></span>
- <span data-ttu-id="56c6f-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="56c6f-1405">carteblanche</span></span>
- <span data-ttu-id="56c6f-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1406">credit card</span></span>
- <span data-ttu-id="56c6f-1407">]</span><span class="sxs-lookup"><span data-stu-id="56c6f-1407">cc#</span></span>
- <span data-ttu-id="56c6f-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1408">cc#:</span></span>
- <span data-ttu-id="56c6f-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="56c6f-1409">expiration date</span></span>
- <span data-ttu-id="56c6f-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="56c6f-1410">exp date</span></span>
- <span data-ttu-id="56c6f-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="56c6f-1411">expiry date</span></span>
- <span data-ttu-id="56c6f-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="56c6f-1412">date d’expiration</span></span>
- <span data-ttu-id="56c6f-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1413">date d'exp</span></span>
- <span data-ttu-id="56c6f-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="56c6f-1414">date expiration</span></span>
- <span data-ttu-id="56c6f-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1415">bank card</span></span>
- <span data-ttu-id="56c6f-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1416">bankcard</span></span>
- <span data-ttu-id="56c6f-1417">card number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1417">card number</span></span>
- <span data-ttu-id="56c6f-1418">card num</span><span class="sxs-lookup"><span data-stu-id="56c6f-1418">card num</span></span>
- <span data-ttu-id="56c6f-1419">カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1419">cardnumber</span></span>
- <span data-ttu-id="56c6f-1420">カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1420">cardnumbers</span></span>
- <span data-ttu-id="56c6f-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-1421">card numbers</span></span>
- <span data-ttu-id="56c6f-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1422">creditcard</span></span>
- <span data-ttu-id="56c6f-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1423">credit cards</span></span>
- <span data-ttu-id="56c6f-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1424">creditcards</span></span>
- <span data-ttu-id="56c6f-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="56c6f-1425">ccn</span></span>
- <span data-ttu-id="56c6f-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="56c6f-1426">card holder</span></span>
- <span data-ttu-id="56c6f-1427">所有者</span><span class="sxs-lookup"><span data-stu-id="56c6f-1427">cardholder</span></span>
- <span data-ttu-id="56c6f-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="56c6f-1428">card holders</span></span>
- <span data-ttu-id="56c6f-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="56c6f-1429">cardholders</span></span>
- <span data-ttu-id="56c6f-1430">check card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1430">check card</span></span>
- <span data-ttu-id="56c6f-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1431">checkcard</span></span>
- <span data-ttu-id="56c6f-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1432">check cards</span></span>
- <span data-ttu-id="56c6f-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1433">checkcards</span></span>
- <span data-ttu-id="56c6f-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1434">debit card</span></span>
- <span data-ttu-id="56c6f-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1435">debitcard</span></span>
- <span data-ttu-id="56c6f-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1436">debit cards</span></span>
- <span data-ttu-id="56c6f-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1437">debitcards</span></span>
- <span data-ttu-id="56c6f-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1438">atm card</span></span>
- <span data-ttu-id="56c6f-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1439">atmcard</span></span>
- <span data-ttu-id="56c6f-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1440">atm cards</span></span>
- <span data-ttu-id="56c6f-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1441">atmcards</span></span>
- <span data-ttu-id="56c6f-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="56c6f-1442">enroute</span></span>
- <span data-ttu-id="56c6f-1443">en route</span><span class="sxs-lookup"><span data-stu-id="56c6f-1443">en route</span></span>
- <span data-ttu-id="56c6f-1444">card type</span><span class="sxs-lookup"><span data-stu-id="56c6f-1444">card type</span></span>
- <span data-ttu-id="56c6f-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="56c6f-1445">carte bancaire</span></span>
- <span data-ttu-id="56c6f-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="56c6f-1446">carte de crédit</span></span>
- <span data-ttu-id="56c6f-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="56c6f-1447">carte de credit</span></span>
- <span data-ttu-id="56c6f-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1448">numéro de carte</span></span>
- <span data-ttu-id="56c6f-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1449">numero de carte</span></span>
- <span data-ttu-id="56c6f-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1450">nº de la carte</span></span>
- <span data-ttu-id="56c6f-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1451">nº de carte</span></span>
- <span data-ttu-id="56c6f-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1452">kreditkarte</span></span>
- <span data-ttu-id="56c6f-1453">karte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1453">karte</span></span>
- <span data-ttu-id="56c6f-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="56c6f-1454">karteninhaber</span></span>
- <span data-ttu-id="56c6f-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="56c6f-1455">karteninhabers</span></span>
- <span data-ttu-id="56c6f-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="56c6f-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="56c6f-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="56c6f-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="56c6f-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1458">kreditkartentyp</span></span>
- <span data-ttu-id="56c6f-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="56c6f-1459">eigentümername</span></span>
- <span data-ttu-id="56c6f-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="56c6f-1460">kartennr</span></span> 
- <span data-ttu-id="56c6f-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1461">kartennummer</span></span>
- <span data-ttu-id="56c6f-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1462">kreditkartennummer</span></span>
- <span data-ttu-id="56c6f-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="56c6f-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1464">carta di credito</span></span>
- <span data-ttu-id="56c6f-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1465">carta credito</span></span>
- <span data-ttu-id="56c6f-1466">carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1466">carta</span></span>
- <span data-ttu-id="56c6f-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1467">n carta</span></span>
- <span data-ttu-id="56c6f-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1468">nr.</span></span> <span data-ttu-id="56c6f-1469">carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1469">carta</span></span>
- <span data-ttu-id="56c6f-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1470">nr carta</span></span>
- <span data-ttu-id="56c6f-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1471">numero carta</span></span>
- <span data-ttu-id="56c6f-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1472">numero della carta</span></span>
- <span data-ttu-id="56c6f-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1473">numero di carta</span></span>
- <span data-ttu-id="56c6f-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1474">tarjeta credito</span></span>
- <span data-ttu-id="56c6f-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1475">tarjeta de credito</span></span>
- <span data-ttu-id="56c6f-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1476">tarjeta crédito</span></span>
- <span data-ttu-id="56c6f-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="56c6f-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="56c6f-1478">tarjeta de atm</span></span>
- <span data-ttu-id="56c6f-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="56c6f-1479">tarjeta atm</span></span>
- <span data-ttu-id="56c6f-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1480">tarjeta debito</span></span>
- <span data-ttu-id="56c6f-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1481">tarjeta de debito</span></span>
- <span data-ttu-id="56c6f-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1482">tarjeta débito</span></span>
- <span data-ttu-id="56c6f-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1483">tarjeta de débito</span></span>
- <span data-ttu-id="56c6f-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1484">nº de tarjeta</span></span>
- <span data-ttu-id="56c6f-1485">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1485">no.</span></span> <span data-ttu-id="56c6f-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1486">de tarjeta</span></span>
- <span data-ttu-id="56c6f-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1487">no de tarjeta</span></span>
- <span data-ttu-id="56c6f-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1488">numero de tarjeta</span></span>
- <span data-ttu-id="56c6f-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1489">número de tarjeta</span></span>
- <span data-ttu-id="56c6f-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1490">tarjeta no</span></span>
- <span data-ttu-id="56c6f-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="56c6f-1491">tarjetahabiente</span></span>
- <span data-ttu-id="56c6f-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1492">cartão de crédito</span></span>
- <span data-ttu-id="56c6f-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1493">cartão de credito</span></span>
- <span data-ttu-id="56c6f-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1494">cartao de crédito</span></span>
- <span data-ttu-id="56c6f-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1495">cartao de credito</span></span>
- <span data-ttu-id="56c6f-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1496">cartão de débito</span></span>
- <span data-ttu-id="56c6f-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1497">cartao de débito</span></span>
- <span data-ttu-id="56c6f-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1498">cartão de debito</span></span>
- <span data-ttu-id="56c6f-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1499">cartao de debito</span></span>
- <span data-ttu-id="56c6f-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="56c6f-1500">débito automático</span></span>
- <span data-ttu-id="56c6f-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="56c6f-1501">debito automatico</span></span>
- <span data-ttu-id="56c6f-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1502">número do cartão</span></span>
- <span data-ttu-id="56c6f-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1503">numero do cartão</span></span> 
- <span data-ttu-id="56c6f-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1504">número do cartao</span></span>
- <span data-ttu-id="56c6f-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1505">numero do cartao</span></span>
- <span data-ttu-id="56c6f-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1506">número de cartão</span></span>
- <span data-ttu-id="56c6f-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1507">numero de cartão</span></span>
- <span data-ttu-id="56c6f-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1508">número de cartao</span></span>
- <span data-ttu-id="56c6f-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1509">numero de cartao</span></span>
- <span data-ttu-id="56c6f-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1510">nº do cartão</span></span>
- <span data-ttu-id="56c6f-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1511">nº do cartao</span></span>
- <span data-ttu-id="56c6f-1512">n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-1512">nº.</span></span> <span data-ttu-id="56c6f-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1513">do cartão</span></span>
- <span data-ttu-id="56c6f-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1514">no do cartão</span></span>
- <span data-ttu-id="56c6f-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1515">no do cartao</span></span>
- <span data-ttu-id="56c6f-1516">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1516">no.</span></span> <span data-ttu-id="56c6f-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1517">do cartão</span></span>
- <span data-ttu-id="56c6f-1518">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1518">no.</span></span> <span data-ttu-id="56c6f-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="56c6f-1520">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1521">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1521">Format</span></span>

<span data-ttu-id="56c6f-1522">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1523">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1523">Pattern</span></span>

<span data-ttu-id="56c6f-1524">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1525">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1525">Checksum</span></span>

<span data-ttu-id="56c6f-1526">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1527">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1527">Definition</span></span>

<span data-ttu-id="56c6f-1528">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1529">関数 Func_croatia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1530">Keyword_croatia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-1531">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1531">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="56c6f-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="56c6f-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1533">Croatian identity card</span></span>
- <span data-ttu-id="56c6f-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="56c6f-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="56c6f-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1536">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1536">Format</span></span>

<span data-ttu-id="56c6f-1537">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1538">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1538">Pattern</span></span>

<span data-ttu-id="56c6f-1539">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1539">11 digits:</span></span>
- <span data-ttu-id="56c6f-1540">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1540">10 digits</span></span> 
- <span data-ttu-id="56c6f-1541">最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1542">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1542">Checksum</span></span>

<span data-ttu-id="56c6f-1543">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1544">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1544">Definition</span></span>

<span data-ttu-id="56c6f-1545">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1546">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1547">Keyword_croatia_oib_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="56c6f-1548">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1548">The checksum passes.</span></span>

<span data-ttu-id="56c6f-1549">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1550">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1551">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1551">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1552">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1552">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="56c6f-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="56c6f-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1554">Personal Identification Number</span></span>
- <span data-ttu-id="56c6f-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="56c6f-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="56c6f-1556">oib</span><span class="sxs-lookup"><span data-stu-id="56c6f-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="56c6f-1557">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1558">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1558">Format</span></span>

<span data-ttu-id="56c6f-1559">省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1560">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1560">Pattern</span></span>

<span data-ttu-id="56c6f-1561">9桁の数字 (古い形式):</span><span class="sxs-lookup"><span data-stu-id="56c6f-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="56c6f-1562">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1562">Nine digits</span></span>

<span data-ttu-id="56c6f-1563">OR</span><span class="sxs-lookup"><span data-stu-id="56c6f-1563">OR</span></span>

- <span data-ttu-id="56c6f-1564">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="56c6f-1565">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-1565">A forward slash</span></span>
- <span data-ttu-id="56c6f-1566">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1566">Three digits</span></span>

<span data-ttu-id="56c6f-1567">10桁の数字 (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="56c6f-1567">10 digits (new format):</span></span>
- <span data-ttu-id="56c6f-1568">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1568">10 digits</span></span>

<span data-ttu-id="56c6f-1569">OR</span><span class="sxs-lookup"><span data-stu-id="56c6f-1569">OR</span></span>

- <span data-ttu-id="56c6f-1570">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="56c6f-1571">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-1571">A forward slash</span></span> 
- <span data-ttu-id="56c6f-1572">4桁の数字 (最後の桁はチェックディジット)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1573">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1573">Checksum</span></span>

<span data-ttu-id="56c6f-1574">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1575">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1575">Definition</span></span>

<span data-ttu-id="56c6f-1576">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-1577">Keyword_czech_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="56c6f-1578">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1578">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="56c6f-1579">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1579">Keywords</span></span>

- <span data-ttu-id="56c6f-1580">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1580">czech personal identity number</span></span>
- <span data-ttu-id="56c6f-1581">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="56c6f-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="56c6f-1582">	Denmark Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1583">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1583">Format</span></span>

<span data-ttu-id="56c6f-1584">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1585">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1585">Pattern</span></span>

<span data-ttu-id="56c6f-1586">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1586">10 digits:</span></span>
- <span data-ttu-id="56c6f-1587">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-1588">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-1588">A hyphen</span></span> 
- <span data-ttu-id="56c6f-1589">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1590">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1590">Checksum</span></span>

<span data-ttu-id="56c6f-1591">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1592">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1592">Definition</span></span>

<span data-ttu-id="56c6f-1593">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-1594">Keyword_denmark_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="56c6f-1595">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1595">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-1596">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1596">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="56c6f-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="56c6f-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1598">Personal Identification Number</span></span>
- <span data-ttu-id="56c6f-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="56c6f-1599">CPR</span></span>
- <span data-ttu-id="56c6f-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="56c6f-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="56c6f-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="56c6f-1602">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1603">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1603">Format</span></span>

<span data-ttu-id="56c6f-1604">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1605">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1605">Pattern</span></span>

<span data-ttu-id="56c6f-1606">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="56c6f-1607">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="56c6f-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="56c6f-1608">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="56c6f-1609">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="56c6f-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1610">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1610">Checksum</span></span>

<span data-ttu-id="56c6f-1611">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1612">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1612">Definition</span></span>

<span data-ttu-id="56c6f-1613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1614">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1615">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1615">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-1616">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1616">Keywords</span></span>

<span data-ttu-id="56c6f-1617">None</span><span class="sxs-lookup"><span data-stu-id="56c6f-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="56c6f-1618">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1619">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1619">Format</span></span>

<span data-ttu-id="56c6f-1620">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1621">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1621">Pattern</span></span>

<span data-ttu-id="56c6f-1622">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1623">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1623">Checksum</span></span>

<span data-ttu-id="56c6f-1624">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1625">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1625">Definition</span></span>

<span data-ttu-id="56c6f-1626">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1627">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1628">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="56c6f-1629">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="56c6f-1630">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="56c6f-1631">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="56c6f-1632">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="56c6f-1633">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="56c6f-1634">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1634">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1635">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1635">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="56c6f-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="56c6f-1637">account number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1637">account number</span></span> 
- <span data-ttu-id="56c6f-1638">card number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1638">card number</span></span> 
- <span data-ttu-id="56c6f-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1639">card no.</span></span> 
- <span data-ttu-id="56c6f-1640">security number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1640">security number</span></span> 
- <span data-ttu-id="56c6f-1641">]</span><span class="sxs-lookup"><span data-stu-id="56c6f-1641">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="56c6f-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="56c6f-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="56c6f-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="56c6f-1643">acct nbr</span></span> 
- <span data-ttu-id="56c6f-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="56c6f-1644">acct num</span></span> 
- <span data-ttu-id="56c6f-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1645">acct no</span></span> 
- <span data-ttu-id="56c6f-1646">american express</span><span class="sxs-lookup"><span data-stu-id="56c6f-1646">american express</span></span> 
- <span data-ttu-id="56c6f-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="56c6f-1647">americanexpress</span></span> 
- <span data-ttu-id="56c6f-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="56c6f-1648">americano espresso</span></span> 
- <span data-ttu-id="56c6f-1649">amex</span><span class="sxs-lookup"><span data-stu-id="56c6f-1649">amex</span></span> 
- <span data-ttu-id="56c6f-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1650">atm card</span></span> 
- <span data-ttu-id="56c6f-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1651">atm cards</span></span> 
- <span data-ttu-id="56c6f-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1652">atm kaart</span></span> 
- <span data-ttu-id="56c6f-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1653">atmcard</span></span> 
- <span data-ttu-id="56c6f-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1654">atmcards</span></span> 
- <span data-ttu-id="56c6f-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1655">atmkaart</span></span> 
- <span data-ttu-id="56c6f-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="56c6f-1656">atmkaarten</span></span> 
- <span data-ttu-id="56c6f-1657"># # の連絡先</span><span class="sxs-lookup"><span data-stu-id="56c6f-1657">bancontact</span></span> 
- <span data-ttu-id="56c6f-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1658">bank card</span></span> 
- <span data-ttu-id="56c6f-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1659">bankkaart</span></span> 
- <span data-ttu-id="56c6f-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="56c6f-1660">card holder</span></span> 
- <span data-ttu-id="56c6f-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="56c6f-1661">card holders</span></span> 
- <span data-ttu-id="56c6f-1662">card num</span><span class="sxs-lookup"><span data-stu-id="56c6f-1662">card num</span></span> 
- <span data-ttu-id="56c6f-1663">card number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1663">card number</span></span> 
- <span data-ttu-id="56c6f-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-1664">card numbers</span></span> 
- <span data-ttu-id="56c6f-1665">card type</span><span class="sxs-lookup"><span data-stu-id="56c6f-1665">card type</span></span> 
- <span data-ttu-id="56c6f-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="56c6f-1666">cardano numerico</span></span> 
- <span data-ttu-id="56c6f-1667">所有者</span><span class="sxs-lookup"><span data-stu-id="56c6f-1667">cardholder</span></span> 
- <span data-ttu-id="56c6f-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="56c6f-1668">cardholders</span></span> 
- <span data-ttu-id="56c6f-1669">カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1669">cardnumber</span></span> 
- <span data-ttu-id="56c6f-1670">カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1670">cardnumbers</span></span> 
- <span data-ttu-id="56c6f-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1671">carta bianca</span></span> 
- <span data-ttu-id="56c6f-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1672">carta credito</span></span> 
- <span data-ttu-id="56c6f-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1673">carta di credito</span></span> 
- <span data-ttu-id="56c6f-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1674">cartao de credito</span></span> 
- <span data-ttu-id="56c6f-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1675">cartao de crédito</span></span> 
- <span data-ttu-id="56c6f-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1676">cartao de debito</span></span> 
- <span data-ttu-id="56c6f-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1677">cartao de débito</span></span> 
- <span data-ttu-id="56c6f-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="56c6f-1678">carte bancaire</span></span> 
- <span data-ttu-id="56c6f-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="56c6f-1679">carte blanche</span></span> 
- <span data-ttu-id="56c6f-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="56c6f-1680">carte bleue</span></span> 
- <span data-ttu-id="56c6f-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="56c6f-1681">carte de credit</span></span> 
- <span data-ttu-id="56c6f-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="56c6f-1682">carte de crédit</span></span> 
- <span data-ttu-id="56c6f-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1683">carte di credito</span></span> 
- <span data-ttu-id="56c6f-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="56c6f-1684">carteblanche</span></span> 
- <span data-ttu-id="56c6f-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1685">cartão de credito</span></span> 
- <span data-ttu-id="56c6f-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1686">cartão de crédito</span></span> 
- <span data-ttu-id="56c6f-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1687">cartão de debito</span></span> 
- <span data-ttu-id="56c6f-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1688">cartão de débito</span></span> 
- <span data-ttu-id="56c6f-1689">cb</span><span class="sxs-lookup"><span data-stu-id="56c6f-1689">cb</span></span> 
- <span data-ttu-id="56c6f-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="56c6f-1690">ccn</span></span> 
- <span data-ttu-id="56c6f-1691">check card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1691">check card</span></span> 
- <span data-ttu-id="56c6f-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1692">check cards</span></span> 
- <span data-ttu-id="56c6f-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1693">checkcard</span></span>
- <span data-ttu-id="56c6f-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1694">checkcards</span></span> 
- <span data-ttu-id="56c6f-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1695">chequekaart</span></span> 
- <span data-ttu-id="56c6f-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="56c6f-1696">cirrus</span></span> 
- <span data-ttu-id="56c6f-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="56c6f-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="56c6f-1698">lekaart の方法</span><span class="sxs-lookup"><span data-stu-id="56c6f-1698">controlekaart</span></span> 
- <span data-ttu-id="56c6f-1699">lekaar10 の場合</span><span class="sxs-lookup"><span data-stu-id="56c6f-1699">controlekaarten</span></span> 
- <span data-ttu-id="56c6f-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1700">credit card</span></span> 
- <span data-ttu-id="56c6f-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1701">credit cards</span></span> 
- <span data-ttu-id="56c6f-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1702">creditcard</span></span> 
- <span data-ttu-id="56c6f-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1703">creditcards</span></span> 
- <span data-ttu-id="56c6f-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1704">debetkaart</span></span> 
- <span data-ttu-id="56c6f-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="56c6f-1705">debetkaarten</span></span> 
- <span data-ttu-id="56c6f-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1706">debit card</span></span> 
- <span data-ttu-id="56c6f-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1707">debit cards</span></span> 
- <span data-ttu-id="56c6f-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1708">debitcard</span></span> 
- <span data-ttu-id="56c6f-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1709">debitcards</span></span> 
- <span data-ttu-id="56c6f-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="56c6f-1710">debito automatico</span></span> 
- <span data-ttu-id="56c6f-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="56c6f-1711">diners club</span></span> 
- <span data-ttu-id="56c6f-1712">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1712">dinersclub</span></span> 
- <span data-ttu-id="56c6f-1713">開示</span><span class="sxs-lookup"><span data-stu-id="56c6f-1713">discover</span></span> 
- <span data-ttu-id="56c6f-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1714">discover card</span></span> 
- <span data-ttu-id="56c6f-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1715">discover cards</span></span> 
- <span data-ttu-id="56c6f-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1716">discovercard</span></span> 
- <span data-ttu-id="56c6f-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1717">discovercards</span></span> 
- <span data-ttu-id="56c6f-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="56c6f-1718">débito automático</span></span>
- <span data-ttu-id="56c6f-1719">edc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1719">edc</span></span> 
- <span data-ttu-id="56c6f-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="56c6f-1720">eigentümername</span></span> 
- <span data-ttu-id="56c6f-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1721">european debit card</span></span> 
- <span data-ttu-id="56c6f-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1722">hoofdkaart</span></span> 
- <span data-ttu-id="56c6f-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="56c6f-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="56c6f-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="56c6f-1724">in viaggio</span></span> 
- <span data-ttu-id="56c6f-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="56c6f-1725">japanese card bureau</span></span> 
- <span data-ttu-id="56c6f-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="56c6f-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="56c6f-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="56c6f-1727">jcb</span></span> 
- <span data-ttu-id="56c6f-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="56c6f-1728">kaart</span></span> 
- <span data-ttu-id="56c6f-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="56c6f-1729">kaart num</span></span> 
- <span data-ttu-id="56c6f-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="56c6f-1730">kaartaantal</span></span> 
- <span data-ttu-id="56c6f-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="56c6f-1731">kaartaantallen</span></span> 
- <span data-ttu-id="56c6f-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="56c6f-1732">kaarthouder</span></span> 
- <span data-ttu-id="56c6f-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="56c6f-1733">kaarthouders</span></span> 
- <span data-ttu-id="56c6f-1734">karte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1734">karte</span></span>  
- <span data-ttu-id="56c6f-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="56c6f-1735">karteninhaber</span></span> 
- <span data-ttu-id="56c6f-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="56c6f-1736">karteninhabers</span></span>
- <span data-ttu-id="56c6f-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="56c6f-1737">kartennr</span></span> 
- <span data-ttu-id="56c6f-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1738">kartennummer</span></span> 
- <span data-ttu-id="56c6f-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1739">kreditkarte</span></span> 
- <span data-ttu-id="56c6f-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="56c6f-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="56c6f-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="56c6f-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="56c6f-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="56c6f-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="56c6f-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="56c6f-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="56c6f-1745">maestro</span></span> 
- <span data-ttu-id="56c6f-1746">master card</span><span class="sxs-lookup"><span data-stu-id="56c6f-1746">master card</span></span> 
- <span data-ttu-id="56c6f-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1747">master cards</span></span> 
- <span data-ttu-id="56c6f-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="56c6f-1748">mastercard</span></span> 
- <span data-ttu-id="56c6f-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="56c6f-1749">mastercards</span></span> 
- <span data-ttu-id="56c6f-1750">mc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1750">mc</span></span> 
- <span data-ttu-id="56c6f-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="56c6f-1751">mister cash</span></span> 
- <span data-ttu-id="56c6f-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1752">n carta</span></span> 
- <span data-ttu-id="56c6f-1753">carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1753">carta</span></span> 
- <span data-ttu-id="56c6f-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1754">no de tarjeta</span></span> 
- <span data-ttu-id="56c6f-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1755">no do cartao</span></span> 
- <span data-ttu-id="56c6f-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1756">no do cartão</span></span> 
- <span data-ttu-id="56c6f-1757">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1757">no.</span></span> <span data-ttu-id="56c6f-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1758">de tarjeta</span></span> 
- <span data-ttu-id="56c6f-1759">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1759">no.</span></span> <span data-ttu-id="56c6f-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1760">do cartao</span></span> 
- <span data-ttu-id="56c6f-1761">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1761">no.</span></span> <span data-ttu-id="56c6f-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1762">do cartão</span></span> 
- <span data-ttu-id="56c6f-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1763">nr carta</span></span> 
- <span data-ttu-id="56c6f-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1764">nr.</span></span> <span data-ttu-id="56c6f-1765">carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1765">carta</span></span> 
- <span data-ttu-id="56c6f-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1766">numeri di scheda</span></span> 
- <span data-ttu-id="56c6f-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1767">numero carta</span></span> 
- <span data-ttu-id="56c6f-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1768">numero de cartao</span></span> 
- <span data-ttu-id="56c6f-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1769">numero de carte</span></span> 
- <span data-ttu-id="56c6f-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1770">numero de cartão</span></span> 
- <span data-ttu-id="56c6f-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1771">numero de tarjeta</span></span>
- <span data-ttu-id="56c6f-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1772">numero della carta</span></span> 
- <span data-ttu-id="56c6f-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1773">numero di carta</span></span> 
- <span data-ttu-id="56c6f-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1774">numero di scheda</span></span> 
- <span data-ttu-id="56c6f-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1775">numero do cartao</span></span> 
- <span data-ttu-id="56c6f-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1776">numero do cartão</span></span> 
- <span data-ttu-id="56c6f-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1777">numéro de carte</span></span> 
- <span data-ttu-id="56c6f-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1778">nº carta</span></span> 
- <span data-ttu-id="56c6f-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1779">nº de carte</span></span> 
- <span data-ttu-id="56c6f-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="56c6f-1780">nº de la carte</span></span> 
- <span data-ttu-id="56c6f-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="56c6f-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1782">nº do cartao</span></span> 
- <span data-ttu-id="56c6f-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1783">nº do cartão</span></span> 
- <span data-ttu-id="56c6f-1784">n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-1784">nº.</span></span> <span data-ttu-id="56c6f-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1785">do cartão</span></span> 
- <span data-ttu-id="56c6f-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1786">número de cartao</span></span> 
- <span data-ttu-id="56c6f-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="56c6f-1787">número de cartão</span></span> 
- <span data-ttu-id="56c6f-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1788">número de tarjeta</span></span> 
- <span data-ttu-id="56c6f-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1789">número do cartao</span></span> 
- <span data-ttu-id="56c6f-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="56c6f-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="56c6f-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="56c6f-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="56c6f-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="56c6f-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="56c6f-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1793">scheda della banca</span></span> 
- <span data-ttu-id="56c6f-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="56c6f-1794">scheda di controllo</span></span> 
- <span data-ttu-id="56c6f-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1795">scheda di debito</span></span> 
- <span data-ttu-id="56c6f-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="56c6f-1796">scheda matrice</span></span> 
- <span data-ttu-id="56c6f-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="56c6f-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="56c6f-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="56c6f-1798">schede di controllo</span></span> 
- <span data-ttu-id="56c6f-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1799">schede di debito</span></span> 
- <span data-ttu-id="56c6f-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="56c6f-1800">schede matrici</span></span> 
- <span data-ttu-id="56c6f-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="56c6f-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="56c6f-1802">scoprono le schede</span></span> 
- <span data-ttu-id="56c6f-1803">単独</span><span class="sxs-lookup"><span data-stu-id="56c6f-1803">solo</span></span> 
- <span data-ttu-id="56c6f-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1804">supporti di scheda</span></span> 
- <span data-ttu-id="56c6f-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1805">supporto di scheda</span></span> 
- <span data-ttu-id="56c6f-1806">switch</span><span class="sxs-lookup"><span data-stu-id="56c6f-1806">switch</span></span> 
- <span data-ttu-id="56c6f-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="56c6f-1807">tarjeta atm</span></span> 
- <span data-ttu-id="56c6f-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1808">tarjeta credito</span></span> 
- <span data-ttu-id="56c6f-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="56c6f-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="56c6f-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="56c6f-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="56c6f-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="56c6f-1812">tarjeta debito</span></span> 
- <span data-ttu-id="56c6f-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1813">tarjeta no</span></span>
- <span data-ttu-id="56c6f-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="56c6f-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="56c6f-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1815">tipo della scheda</span></span> 
- <span data-ttu-id="56c6f-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="56c6f-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="56c6f-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1817">scheda</span></span> 
- <span data-ttu-id="56c6f-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="56c6f-1818">v pay</span></span> 
- <span data-ttu-id="56c6f-1819">v-支払い</span><span class="sxs-lookup"><span data-stu-id="56c6f-1819">v-pay</span></span> 
- <span data-ttu-id="56c6f-1820">visa</span><span class="sxs-lookup"><span data-stu-id="56c6f-1820">visa</span></span> 
- <span data-ttu-id="56c6f-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="56c6f-1821">visa plus</span></span> 
- <span data-ttu-id="56c6f-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="56c6f-1822">visa electron</span></span> 
- <span data-ttu-id="56c6f-1823">visto</span><span class="sxs-lookup"><span data-stu-id="56c6f-1823">visto</span></span> 
- <span data-ttu-id="56c6f-1824">visum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1824">visum</span></span> 
- <span data-ttu-id="56c6f-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="56c6f-1825">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="56c6f-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="56c6f-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="56c6f-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1827">card identification number</span></span>
- <span data-ttu-id="56c6f-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="56c6f-1828">card verification</span></span> 
- <span data-ttu-id="56c6f-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="56c6f-1829">cardi la verifica</span></span> 
- <span data-ttu-id="56c6f-1830">cid</span><span class="sxs-lookup"><span data-stu-id="56c6f-1830">cid</span></span> 
- <span data-ttu-id="56c6f-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="56c6f-1831">cod seg</span></span> 
- <span data-ttu-id="56c6f-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1832">cod seguranca</span></span> 
- <span data-ttu-id="56c6f-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1833">cod segurança</span></span> 
- <span data-ttu-id="56c6f-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1834">cod sicurezza</span></span> 
- <span data-ttu-id="56c6f-1835">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1835">cod.</span></span> <span data-ttu-id="56c6f-1836">seg</span><span class="sxs-lookup"><span data-stu-id="56c6f-1836">seg</span></span> 
- <span data-ttu-id="56c6f-1837">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1837">cod.</span></span> <span data-ttu-id="56c6f-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1838">seguranca</span></span> 
- <span data-ttu-id="56c6f-1839">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1839">cod.</span></span> <span data-ttu-id="56c6f-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1840">segurança</span></span> 
- <span data-ttu-id="56c6f-1841">cod.</span><span class="sxs-lookup"><span data-stu-id="56c6f-1841">cod.</span></span> <span data-ttu-id="56c6f-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1842">sicurezza</span></span> 
- <span data-ttu-id="56c6f-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="56c6f-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="56c6f-1844">codice di verifica</span></span> 
- <span data-ttu-id="56c6f-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="56c6f-1845">codigo</span></span> 
- <span data-ttu-id="56c6f-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="56c6f-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1847">codigo de segurança</span></span> 
- <span data-ttu-id="56c6f-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="56c6f-1848">crittogramma</span></span> 
- <span data-ttu-id="56c6f-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="56c6f-1849">cryptogram</span></span> 
- <span data-ttu-id="56c6f-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="56c6f-1850">cryptogramme</span></span> 
- <span data-ttu-id="56c6f-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="56c6f-1851">cv2</span></span> 
- <span data-ttu-id="56c6f-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1852">cvc</span></span> 
- <span data-ttu-id="56c6f-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="56c6f-1853">cvc2</span></span> 
- <span data-ttu-id="56c6f-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="56c6f-1854">cvn</span></span> 
- <span data-ttu-id="56c6f-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="56c6f-1855">cvv</span></span> 
- <span data-ttu-id="56c6f-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="56c6f-1856">cvv2</span></span> 
- <span data-ttu-id="56c6f-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1857">cód seguranca</span></span> 
- <span data-ttu-id="56c6f-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1858">cód segurança</span></span> 
- <span data-ttu-id="56c6f-1859">cód。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1859">cód.</span></span> <span data-ttu-id="56c6f-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1860">seguranca</span></span> 
- <span data-ttu-id="56c6f-1861">cód。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1861">cód.</span></span> <span data-ttu-id="56c6f-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1862">segurança</span></span> 
- <span data-ttu-id="56c6f-1863">código</span><span class="sxs-lookup"><span data-stu-id="56c6f-1863">código</span></span> 
- <span data-ttu-id="56c6f-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="56c6f-1864">código de seguranca</span></span> 
- <span data-ttu-id="56c6f-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="56c6f-1865">código de segurança</span></span> 
- <span data-ttu-id="56c6f-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="56c6f-1866">de kaart controle</span></span> 
- <span data-ttu-id="56c6f-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="56c6f-1867">geeft nr uit</span></span> 
- <span data-ttu-id="56c6f-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1868">issue no</span></span> 
- <span data-ttu-id="56c6f-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1869">issue number</span></span> 
- <span data-ttu-id="56c6f-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="56c6f-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="56c6f-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="56c6f-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="56c6f-1873">kwestieaantal</span></span> 
- <span data-ttu-id="56c6f-1874">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1874">no.</span></span> <span data-ttu-id="56c6f-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="56c6f-1875">dell'edizione</span></span> 
- <span data-ttu-id="56c6f-1876">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1876">no.</span></span> <span data-ttu-id="56c6f-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1877">di sicurezza</span></span> 
- <span data-ttu-id="56c6f-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="56c6f-1878">numero de securite</span></span> 
- <span data-ttu-id="56c6f-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1879">numero de verificacao</span></span> 
- <span data-ttu-id="56c6f-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="56c6f-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="56c6f-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="56c6f-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="56c6f-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="56c6f-1882">scheda</span></span> 
- <span data-ttu-id="56c6f-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="56c6f-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="56c6f-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="56c6f-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="56c6f-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="56c6f-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="56c6f-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="56c6f-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="56c6f-1887">número de verificação</span></span> 
- <span data-ttu-id="56c6f-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="56c6f-1888">perno il blocco</span></span> 
- <span data-ttu-id="56c6f-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="56c6f-1889">pin block</span></span> 
- <span data-ttu-id="56c6f-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1890">prufziffer</span></span> 
- <span data-ttu-id="56c6f-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1891">prüfziffer</span></span> 
- <span data-ttu-id="56c6f-1892">security code</span><span class="sxs-lookup"><span data-stu-id="56c6f-1892">security code</span></span> 
- <span data-ttu-id="56c6f-1893">security no</span><span class="sxs-lookup"><span data-stu-id="56c6f-1893">security no</span></span> 
- <span data-ttu-id="56c6f-1894">security number</span><span class="sxs-lookup"><span data-stu-id="56c6f-1894">security number</span></span> 
- <span data-ttu-id="56c6f-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="56c6f-1895">sicherheits kode</span></span> 
- <span data-ttu-id="56c6f-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="56c6f-1896">sicherheitscode</span></span> 
- <span data-ttu-id="56c6f-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="56c6f-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="56c6f-1898">speldblok</span></span> 
- <span data-ttu-id="56c6f-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-1899">veiligheid nr</span></span> 
- <span data-ttu-id="56c6f-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="56c6f-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="56c6f-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="56c6f-1901">veiligheidscode</span></span> 
- <span data-ttu-id="56c6f-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="56c6f-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1903">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="56c6f-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="56c6f-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="56c6f-1905">ablん f</span><span class="sxs-lookup"><span data-stu-id="56c6f-1905">ablauf</span></span> 
- <span data-ttu-id="56c6f-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="56c6f-1906">data de expiracao</span></span> 
- <span data-ttu-id="56c6f-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="56c6f-1907">data de expiração</span></span> 
- <span data-ttu-id="56c6f-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1908">data del exp</span></span> 
- <span data-ttu-id="56c6f-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1909">data di exp</span></span> 
- <span data-ttu-id="56c6f-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1910">data di scadenza</span></span> 
- <span data-ttu-id="56c6f-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="56c6f-1911">data em que expira</span></span> 
- <span data-ttu-id="56c6f-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="56c6f-1912">data scad</span></span> 
- <span data-ttu-id="56c6f-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1913">data scadenza</span></span> 
- <span data-ttu-id="56c6f-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="56c6f-1914">date de validité</span></span> 
- <span data-ttu-id="56c6f-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="56c6f-1915">datum afloop</span></span> 
- <span data-ttu-id="56c6f-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1916">datum van exp</span></span> 
- <span data-ttu-id="56c6f-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="56c6f-1917">de afloop</span></span> 
- <span data-ttu-id="56c6f-1918">espira</span><span class="sxs-lookup"><span data-stu-id="56c6f-1918">espira</span></span> 
- <span data-ttu-id="56c6f-1919">espira</span><span class="sxs-lookup"><span data-stu-id="56c6f-1919">espira</span></span> 
- <span data-ttu-id="56c6f-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="56c6f-1920">exp date</span></span> 
- <span data-ttu-id="56c6f-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1921">exp datum</span></span> 
- <span data-ttu-id="56c6f-1922">nntp</span><span class="sxs-lookup"><span data-stu-id="56c6f-1922">expiration</span></span> 
- <span data-ttu-id="56c6f-1923">無効</span><span class="sxs-lookup"><span data-stu-id="56c6f-1923">expire</span></span> 
- <span data-ttu-id="56c6f-1924">期限</span><span class="sxs-lookup"><span data-stu-id="56c6f-1924">expires</span></span> 
- <span data-ttu-id="56c6f-1925">期限</span><span class="sxs-lookup"><span data-stu-id="56c6f-1925">expiry</span></span> 
- <span data-ttu-id="56c6f-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="56c6f-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="56c6f-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1927">fecha de venc</span></span> 
- <span data-ttu-id="56c6f-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="56c6f-1928">gultig bis</span></span> 
- <span data-ttu-id="56c6f-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="56c6f-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="56c6f-1930">gültig bis</span></span> 
- <span data-ttu-id="56c6f-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="56c6f-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1932">la scadenza</span></span> 
- <span data-ttu-id="56c6f-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="56c6f-1933">scadenza</span></span> 
- <span data-ttu-id="56c6f-1934">valable</span><span class="sxs-lookup"><span data-stu-id="56c6f-1934">valable</span></span> 
- <span data-ttu-id="56c6f-1935">validade</span><span class="sxs-lookup"><span data-stu-id="56c6f-1935">validade</span></span> 
- <span data-ttu-id="56c6f-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1936">valido hasta</span></span> 
- <span data-ttu-id="56c6f-1937">valor は</span><span class="sxs-lookup"><span data-stu-id="56c6f-1937">valor</span></span> 
- <span data-ttu-id="56c6f-1938">venc</span><span class="sxs-lookup"><span data-stu-id="56c6f-1938">venc</span></span> 
- <span data-ttu-id="56c6f-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="56c6f-1939">vencimento</span></span> 
- <span data-ttu-id="56c6f-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="56c6f-1940">vencimiento</span></span> 
- <span data-ttu-id="56c6f-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="56c6f-1941">verloopt</span></span> 
- <span data-ttu-id="56c6f-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="56c6f-1942">vervaldag</span></span> 
- <span data-ttu-id="56c6f-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-1943">vervaldatum</span></span> 
- <span data-ttu-id="56c6f-1944">vto</span><span class="sxs-lookup"><span data-stu-id="56c6f-1944">vto</span></span> 
- <span data-ttu-id="56c6f-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="56c6f-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="56c6f-1946">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1946">EU Driver's License Number</span></span>

<span data-ttu-id="56c6f-1947">詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="56c6f-1948">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1948">EU National Identification Number</span></span>

<span data-ttu-id="56c6f-1949">詳細については、「 [EU 国立 id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="56c6f-1950">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1950">EU Passport Number</span></span>

<span data-ttu-id="56c6f-1951">詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="56c6f-1952">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="56c6f-1953">詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="56c6f-1954">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="56c6f-1955">詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="56c6f-1956">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1957">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1957">Format</span></span>

<span data-ttu-id="56c6f-1958">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="56c6f-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1959">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1959">Pattern</span></span>

<span data-ttu-id="56c6f-1960">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="56c6f-1961">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="56c6f-1962">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="56c6f-1963">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="56c6f-1964">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="56c6f-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1965">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1965">Checksum</span></span>

<span data-ttu-id="56c6f-1966">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1967">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1967">Definition</span></span>

<span data-ttu-id="56c6f-1968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1969">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1970">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="56c6f-1971">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1971">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-1972">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1972">Keywords</span></span>

- <span data-ttu-id="56c6f-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="56c6f-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="56c6f-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="56c6f-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="56c6f-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="56c6f-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="56c6f-1976">Personbeteckning</span></span>
- <span data-ttu-id="56c6f-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="56c6f-1978">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1978">Finland Passport Number</span></span>

<span data-ttu-id="56c6f-1979">次の9つの文字と数字のパターンの組み合わせを書式設定します。9桁の文字 (大文字小文字を区別しない)、7桁のチェックサムを定義しません。 DLP ポリシーは 75% で、この種類の機密情報がある場合に、300文字の近接性: 正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-1980">Keyword_finland_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="56c6f-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="56c6f-1981"></span></span>
<span data-ttu-id="56c6f-1982">キーワード Keyword_finland_passport_number passport Passi</span><span class="sxs-lookup"><span data-stu-id="56c6f-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="56c6f-1983">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-1984">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-1984">Format</span></span>

<span data-ttu-id="56c6f-1985">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-1986">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-1986">Pattern</span></span>

<span data-ttu-id="56c6f-1987">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-1988">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-1988">Checksum</span></span>

<span data-ttu-id="56c6f-1989">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-1990">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-1990">Definition</span></span>

<span data-ttu-id="56c6f-1991">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-1992">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-1993">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="56c6f-1994">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="56c6f-1995">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-1995">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-1996">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-1996">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="56c6f-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="56c6f-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="56c6f-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-1998">drivers licence</span></span>
- <span data-ttu-id="56c6f-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="56c6f-1999">drivers license</span></span>
- <span data-ttu-id="56c6f-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2000">driving licence</span></span>
- <span data-ttu-id="56c6f-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="56c6f-2001">driving license</span></span>
- <span data-ttu-id="56c6f-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="56c6f-2002">permis de conduire</span></span>
- <span data-ttu-id="56c6f-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2003">licence number</span></span>
- <span data-ttu-id="56c6f-2004">license number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2004">license number</span></span>
- <span data-ttu-id="56c6f-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-2005">licence numbers</span></span>
- <span data-ttu-id="56c6f-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="56c6f-2007">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2008">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2008">Format</span></span>

<span data-ttu-id="56c6f-2009">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2010">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2010">Pattern</span></span>

<span data-ttu-id="56c6f-2011">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2012">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2012">Checksum</span></span>

<span data-ttu-id="56c6f-2013">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2014">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2014">Definition</span></span>

<span data-ttu-id="56c6f-2015">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2016">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2017">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2017">Keywords</span></span>

<span data-ttu-id="56c6f-2018">None</span><span class="sxs-lookup"><span data-stu-id="56c6f-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="56c6f-2019">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2020">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2020">Format</span></span>

<span data-ttu-id="56c6f-2021">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2022">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2022">Pattern</span></span>

<span data-ttu-id="56c6f-2023">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="56c6f-2024">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2024">Two digits</span></span> 
- <span data-ttu-id="56c6f-2025">2 つの文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-2026">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2027">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2027">Checksum</span></span>

<span data-ttu-id="56c6f-2028">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2029">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2029">Definition</span></span>

<span data-ttu-id="56c6f-2030">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2031">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2032">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2032">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2033">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2033">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="56c6f-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-2034">Keyword_passport</span></span>

- <span data-ttu-id="56c6f-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2035">Passport Number</span></span>
- <span data-ttu-id="56c6f-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="56c6f-2036">Passport No</span></span>
- <span data-ttu-id="56c6f-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2037">Passport #</span></span>
- <span data-ttu-id="56c6f-2038">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-2038">Passport#</span></span>
- <span data-ttu-id="56c6f-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2039">PassportID</span></span>
- <span data-ttu-id="56c6f-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="56c6f-2040">Passportno</span></span>
- <span data-ttu-id="56c6f-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-2041">passportnumber</span></span>
- <span data-ttu-id="56c6f-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-2042">パスポート</span></span>
- <span data-ttu-id="56c6f-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2043">パスポート番号</span></span>
- <span data-ttu-id="56c6f-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="56c6f-2044">パスポートのNum</span></span>
- <span data-ttu-id="56c6f-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="56c6f-2045">パスポート ＃</span></span> 
- <span data-ttu-id="56c6f-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="56c6f-2046">Numéro de passeport</span></span>
- <span data-ttu-id="56c6f-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-2047">Passeport n °</span></span>
- <span data-ttu-id="56c6f-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="56c6f-2048">Passeport Non</span></span>
- <span data-ttu-id="56c6f-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2049">Passeport #</span></span>
- <span data-ttu-id="56c6f-2050">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2050">Passeport#</span></span>
- <span data-ttu-id="56c6f-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="56c6f-2051">PasseportNon</span></span>
- <span data-ttu-id="56c6f-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="56c6f-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="56c6f-2053">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2054">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2054">Format</span></span>

<span data-ttu-id="56c6f-2055">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2056">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2056">Pattern</span></span>

<span data-ttu-id="56c6f-2057">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="56c6f-2058">13桁の数字の後にスペースを続け、2桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="56c6f-2059">または</span><span class="sxs-lookup"><span data-stu-id="56c6f-2059">or</span></span>
- <span data-ttu-id="56c6f-2060">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2061">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2061">Checksum</span></span>

<span data-ttu-id="56c6f-2062">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2063">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2063">Definition</span></span>

<span data-ttu-id="56c6f-2064">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2065">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2066">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="56c6f-2067">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2067">The checksum passes.</span></span>

<span data-ttu-id="56c6f-2068">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2069">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2070">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="56c6f-2071">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2071">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2072">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2072">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="56c6f-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="56c6f-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="56c6f-2074">insee</span><span class="sxs-lookup"><span data-stu-id="56c6f-2074">insee</span></span>
- <span data-ttu-id="56c6f-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2075">securité sociale</span></span>
- <span data-ttu-id="56c6f-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2076">securite sociale</span></span>
- <span data-ttu-id="56c6f-2077">national id</span><span class="sxs-lookup"><span data-stu-id="56c6f-2077">national id</span></span>
- <span data-ttu-id="56c6f-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="56c6f-2078">national identification</span></span>
- <span data-ttu-id="56c6f-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="56c6f-2079">numéro d'identité</span></span>
- <span data-ttu-id="56c6f-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="56c6f-2080">no d'identité</span></span>
- <span data-ttu-id="56c6f-2081">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2081">no.</span></span> <span data-ttu-id="56c6f-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="56c6f-2082">d'identité</span></span>
- <span data-ttu-id="56c6f-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="56c6f-2083">numero d'identite</span></span>
- <span data-ttu-id="56c6f-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="56c6f-2084">no d'identite</span></span>
- <span data-ttu-id="56c6f-2085">違います。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2085">no.</span></span> <span data-ttu-id="56c6f-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="56c6f-2086">d'identite</span></span>
- <span data-ttu-id="56c6f-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2087">social security number</span></span>
- <span data-ttu-id="56c6f-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="56c6f-2088">social security code</span></span>
- <span data-ttu-id="56c6f-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2089">social insurance number</span></span>
- <span data-ttu-id="56c6f-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="56c6f-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2091">d'identité nationale</span></span>
- <span data-ttu-id="56c6f-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="56c6f-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="56c6f-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="56c6f-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="56c6f-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="56c6f-2095">numéro de sécu</span></span>
- <span data-ttu-id="56c6f-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="56c6f-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="56c6f-2097">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2098">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2098">Format</span></span>

<span data-ttu-id="56c6f-2099">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2100">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2100">Pattern</span></span>

<span data-ttu-id="56c6f-2101">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="56c6f-2102">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2102">A digit or letter</span></span> 
- <span data-ttu-id="56c6f-2103">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2103">Two digits</span></span> 
- <span data-ttu-id="56c6f-2104">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2104">Six digits or letters</span></span> 
- <span data-ttu-id="56c6f-2105">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2105">A digit</span></span> 
- <span data-ttu-id="56c6f-2106">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2107">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2107">Checksum</span></span>

<span data-ttu-id="56c6f-2108">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2109">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2109">Definition</span></span>

<span data-ttu-id="56c6f-2110">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2111">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2112">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="56c6f-2113">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="56c6f-2114">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="56c6f-2115">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="56c6f-2116">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2116">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2117">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2117">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="56c6f-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="56c6f-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2119">Führerschein</span></span>
- <span data-ttu-id="56c6f-2120">futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2120">Fuhrerschein</span></span>
- <span data-ttu-id="56c6f-2121">futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="56c6f-2121">Fuehrerschein</span></span>
- <span data-ttu-id="56c6f-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="56c6f-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="56c6f-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="56c6f-2125">Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2125">Führerschein-</span></span> 
- <span data-ttu-id="56c6f-2126">futex (中)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="56c6f-2127">futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="56c6f-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="56c6f-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="56c6f-2129">futex がある hていません einnumnr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="56c6f-2130">futex の ehの再リリース/einnumnr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="56c6f-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="56c6f-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="56c6f-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="56c6f-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="56c6f-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="56c6f-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="56c6f-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="56c6f-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="56c6f-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="56c6f-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="56c6f-2141">futex がある hていません einnumnr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="56c6f-2142">futex の ehの再リリース/einnumnr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="56c6f-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="56c6f-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="56c6f-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="56c6f-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="56c6f-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="56c6f-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="56c6f-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="56c6f-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="56c6f-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="56c6f-2152">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-2152">DL</span></span> 
- <span data-ttu-id="56c6f-2153">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-2153">DLS</span></span>
- <span data-ttu-id="56c6f-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-2154">Driv Lic</span></span> 
- <span data-ttu-id="56c6f-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="56c6f-2155">Driv Licen</span></span> 
- <span data-ttu-id="56c6f-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="56c6f-2156">Driv License</span></span>
- <span data-ttu-id="56c6f-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2157">Driv Licenses</span></span> 
- <span data-ttu-id="56c6f-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2158">Driv Licence</span></span> 
- <span data-ttu-id="56c6f-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-2159">Driv Licences</span></span> 
- <span data-ttu-id="56c6f-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-2160">Driv Lic</span></span> 
- <span data-ttu-id="56c6f-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="56c6f-2161">Driver Licen</span></span> 
- <span data-ttu-id="56c6f-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="56c6f-2162">Driver License</span></span> 
- <span data-ttu-id="56c6f-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2163">Driver Licenses</span></span> 
- <span data-ttu-id="56c6f-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2164">Driver Licence</span></span> 
- <span data-ttu-id="56c6f-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-2165">Driver Licences</span></span> 
- <span data-ttu-id="56c6f-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-2166">Drivers Lic</span></span> 
- <span data-ttu-id="56c6f-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="56c6f-2167">Drivers Licen</span></span> 
- <span data-ttu-id="56c6f-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="56c6f-2168">Drivers License</span></span> 
- <span data-ttu-id="56c6f-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="56c6f-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2170">Drivers Licence</span></span> 
- <span data-ttu-id="56c6f-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-2171">Drivers Licences</span></span> 
- <span data-ttu-id="56c6f-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-2172">Driver's Lic</span></span> 
- <span data-ttu-id="56c6f-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="56c6f-2173">Driver's Licen</span></span> 
- <span data-ttu-id="56c6f-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="56c6f-2174">Driver's License</span></span> 
- <span data-ttu-id="56c6f-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="56c6f-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2176">Driver's Licence</span></span> 
- <span data-ttu-id="56c6f-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-2177">Driver's Licences</span></span> 
- <span data-ttu-id="56c6f-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-2178">Driving Lic</span></span> 
- <span data-ttu-id="56c6f-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="56c6f-2179">Driving Licen</span></span> 
- <span data-ttu-id="56c6f-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="56c6f-2180">Driving License</span></span> 
- <span data-ttu-id="56c6f-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2181">Driving Licenses</span></span> 
- <span data-ttu-id="56c6f-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2182">Driving Licence</span></span> 
- <span data-ttu-id="56c6f-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-2183">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="56c6f-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="56c6f-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="56c6f-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="56c6f-2186">Nr-futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="56c6f-2187">"Nr" という futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="56c6f-2188">Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2188">No-Führerschein</span></span> 
- <span data-ttu-id="56c6f-2189">(futex なし)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="56c6f-2190">その他の ehの場合</span><span class="sxs-lookup"><span data-stu-id="56c6f-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="56c6f-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2191">N-Führerschein</span></span> 
- <span data-ttu-id="56c6f-2192">N の futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="56c6f-2193">N 桁の ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="56c6f-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="56c6f-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="56c6f-2195">Nr-futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="56c6f-2196">"Nr" という futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="56c6f-2197">Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2197">No-Führerschein</span></span> 
- <span data-ttu-id="56c6f-2198">(futex なし)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="56c6f-2199">その他の ehの場合</span><span class="sxs-lookup"><span data-stu-id="56c6f-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="56c6f-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="56c6f-2200">N-Führerschein</span></span> 
- <span data-ttu-id="56c6f-2201">N の futex</span><span class="sxs-lookup"><span data-stu-id="56c6f-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="56c6f-2202">N 桁の ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="56c6f-2202">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="56c6f-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="56c6f-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="56c6f-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="56c6f-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="56c6f-2205">ausstellungsort</span></span>
- <span data-ttu-id="56c6f-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="56c6f-2206">ausstellende behöde</span></span>
- <span data-ttu-id="56c6f-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="56c6f-2207">ausstellende behorde</span></span>
- <span data-ttu-id="56c6f-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="56c6f-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="56c6f-2209">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2210">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2210">Format</span></span>

<span data-ttu-id="56c6f-2211">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2212">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2212">Pattern</span></span>

<span data-ttu-id="56c6f-2213">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="56c6f-2214">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="56c6f-2215">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2215">Three digits</span></span> 
- <span data-ttu-id="56c6f-2216">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="56c6f-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="56c6f-2217">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2218">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2218">Checksum</span></span>

<span data-ttu-id="56c6f-2219">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2220">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2220">Definition</span></span>

<span data-ttu-id="56c6f-2221">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2222">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2223">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="56c6f-2224">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2224">The checksum passes.</span></span>

<span data-ttu-id="56c6f-2225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2226">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2227">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="56c6f-2228">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2228">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2229">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2229">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="56c6f-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="56c6f-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="56c6f-2231">reisepass</span></span>
- <span data-ttu-id="56c6f-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="56c6f-2232">reisepasse</span></span>
- <span data-ttu-id="56c6f-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2233">reisepassnummer</span></span>
- <span data-ttu-id="56c6f-2234">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-2234">passport</span></span>
- <span data-ttu-id="56c6f-2235">passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-2235">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="56c6f-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="56c6f-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="56c6f-2237">ge気流 tsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-2237">geburtsdatum</span></span>
- <span data-ttu-id="56c6f-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="56c6f-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="56c6f-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="56c6f-2239">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="56c6f-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="56c6f-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="56c6f-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="56c6f-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="56c6f-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="56c6f-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2243">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="56c6f-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="56c6f-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="56c6f-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="56c6f-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="56c6f-2246">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2247">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2247">Format</span></span>

<span data-ttu-id="56c6f-2248">2010年11月1日以降: 9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="56c6f-2249">1987年4月1日から2010年10月31日まで:10 桁</span><span class="sxs-lookup"><span data-stu-id="56c6f-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2250">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2250">Pattern</span></span>

<span data-ttu-id="56c6f-2251">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="56c6f-2252">1 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-2253">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2253">Eight digits</span></span>

<span data-ttu-id="56c6f-2254">1987年4月1日から2010年10月31日まで。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="56c6f-2255">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2256">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2256">Checksum</span></span>

<span data-ttu-id="56c6f-2257">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2258">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2258">Definition</span></span>

<span data-ttu-id="56c6f-2259">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2260">正規表現 Regex_germany_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2261">Keyword_germany_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2262">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2262">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="56c6f-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="56c6f-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2264">Identity Card</span></span>
- <span data-ttu-id="56c6f-2265">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2265">ID</span></span>
- <span data-ttu-id="56c6f-2266">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-2266">Identification</span></span>
- <span data-ttu-id="56c6f-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="56c6f-2267">Personalausweis</span></span>
- <span data-ttu-id="56c6f-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="56c6f-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="56c6f-2269">Ausweis</span></span>
- <span data-ttu-id="56c6f-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="56c6f-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="56c6f-2271">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2272">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2272">Format</span></span>

<span data-ttu-id="56c6f-2273">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2274">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2274">Pattern</span></span>

<span data-ttu-id="56c6f-2275">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="56c6f-2276">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="56c6f-2277">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-2277">A dash</span></span> 
- <span data-ttu-id="56c6f-2278">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2278">Six digits</span></span>

<span data-ttu-id="56c6f-2279">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="56c6f-2280">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="56c6f-2281">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-2281">A dash</span></span> 
- <span data-ttu-id="56c6f-2282">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2283">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2283">Checksum</span></span>

<span data-ttu-id="56c6f-2284">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2285">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2285">Definition</span></span>

<span data-ttu-id="56c6f-2286">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2287">正規表現 Regex_greece_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2288">Keyword_greece_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2289">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2289">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="56c6f-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="56c6f-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2291">Greek identity Card</span></span>
- <span data-ttu-id="56c6f-2292">tautotita</span><span class="sxs-lookup"><span data-stu-id="56c6f-2292">Tautotita</span></span>
- <span data-ttu-id="56c6f-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="56c6f-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="56c6f-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="56c6f-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="56c6f-2295">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2296">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2296">Format</span></span>

<span data-ttu-id="56c6f-2297">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="56c6f-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2298">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2298">Pattern</span></span>

<span data-ttu-id="56c6f-2299">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="56c6f-2300">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-2301">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2301">Six digits</span></span> 
- <span data-ttu-id="56c6f-2302">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2303">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2303">Checksum</span></span>

<span data-ttu-id="56c6f-2304">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2305">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2305">Definition</span></span>

<span data-ttu-id="56c6f-2306">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2307">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2308">Keyword_hong_kong_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="56c6f-2309">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2309">The checksum passes.</span></span>

<span data-ttu-id="56c6f-2310">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2311">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2312">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2312">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2313">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2313">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="56c6f-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="56c6f-2315">香港の id カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2315">hong kong identity card</span></span>
- <span data-ttu-id="56c6f-2316">hkidc</span><span class="sxs-lookup"><span data-stu-id="56c6f-2316">HKIDC</span></span>
- <span data-ttu-id="56c6f-2317">id card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2317">id card</span></span>
- <span data-ttu-id="56c6f-2318">Identity card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2318">identity card</span></span>
- <span data-ttu-id="56c6f-2319">hk の id カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2319">hk identity card</span></span>
- <span data-ttu-id="56c6f-2320">香港特別行政 id</span><span class="sxs-lookup"><span data-stu-id="56c6f-2320">hong kong id</span></span>
- <span data-ttu-id="56c6f-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2321">香港身份證</span></span>
- <span data-ttu-id="56c6f-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="56c6f-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2323">身份證</span></span>
- <span data-ttu-id="56c6f-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2324">身份証</span></span>
- <span data-ttu-id="56c6f-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2325">身分證</span></span>
- <span data-ttu-id="56c6f-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2326">身分証</span></span>
- <span data-ttu-id="56c6f-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2327">香港身份証</span></span>
- <span data-ttu-id="56c6f-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2328">香港身分證</span></span>
- <span data-ttu-id="56c6f-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2329">香港身分証</span></span>
- <span data-ttu-id="56c6f-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2330">香港身份證</span></span>
- <span data-ttu-id="56c6f-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2331">香港居民身份證</span></span>
- <span data-ttu-id="56c6f-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2332">香港居民身份証</span></span>
- <span data-ttu-id="56c6f-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2333">香港居民身分證</span></span>
- <span data-ttu-id="56c6f-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2334">香港居民身分証</span></span>
- <span data-ttu-id="56c6f-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="56c6f-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="56c6f-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="56c6f-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="56c6f-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="56c6f-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="56c6f-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="56c6f-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="56c6f-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="56c6f-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="56c6f-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="56c6f-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="56c6f-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="56c6f-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="56c6f-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="56c6f-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="56c6f-2351">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2352">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2352">Format</span></span>

<span data-ttu-id="56c6f-2353">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2354">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2354">Pattern</span></span>

<span data-ttu-id="56c6f-2355">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2355">10 letters or digits:</span></span>
- <span data-ttu-id="56c6f-2356">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-2357">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2357">Four digits</span></span> 
- <span data-ttu-id="56c6f-2358">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2359">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2359">Checksum</span></span>

<span data-ttu-id="56c6f-2360">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2361">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2361">Definition</span></span>

<span data-ttu-id="56c6f-2362">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2363">正規表現 Regex_india_permanent_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2364">Keyword_india_permanent_account_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="56c6f-2365">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2365">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2366">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2366">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="56c6f-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="56c6f-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="56c6f-2369">ペン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="56c6f-2370">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2371">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2371">Format</span></span>

<span data-ttu-id="56c6f-2372">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2373">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2373">Pattern</span></span>

<span data-ttu-id="56c6f-2374">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2374">12 digits:</span></span>
- <span data-ttu-id="56c6f-2375">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2375">Four digits</span></span> 
- <span data-ttu-id="56c6f-2376">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2376">An optional space or dash</span></span> 
- <span data-ttu-id="56c6f-2377">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2377">Four digits</span></span> 
- <span data-ttu-id="56c6f-2378">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2378">An optional space or dash</span></span> 
- <span data-ttu-id="56c6f-2379">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="56c6f-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2380">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2380">Checksum</span></span>

<span data-ttu-id="56c6f-2381">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2382">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2382">Definition</span></span>

<span data-ttu-id="56c6f-2383">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-2384">Keyword_india_aadhar からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="56c6f-2385">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2385">The checksum passes.</span></span>
<span data-ttu-id="56c6f-2386">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-2387">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2387">The checksum passes.</span></span>
<!-- India Unique Identification (Aadhaar) number -->
<span data-ttu-id="56c6f-2388"><Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="56c6f-2388"></span></span>

### <a name="keywords"></a><span data-ttu-id="56c6f-2389">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2389">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="56c6f-2390">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="56c6f-2390">Keyword_india_aadhar</span></span>
- <span data-ttu-id="56c6f-2391">Aadhar</span><span class="sxs-lookup"><span data-stu-id="56c6f-2391">Aadhar</span></span>
- <span data-ttu-id="56c6f-2392">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="56c6f-2392">Aadhaar</span></span>
- <span data-ttu-id="56c6f-2393">UID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2393">UID</span></span>
- <span data-ttu-id="56c6f-2394">आधार</span><span class="sxs-lookup"><span data-stu-id="56c6f-2394">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="56c6f-2395">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2395">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2396">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2396">Format</span></span>

<span data-ttu-id="56c6f-2397">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2397">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2398">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2398">Pattern</span></span>

<span data-ttu-id="56c6f-2399">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2399">16 digits:</span></span>
- <span data-ttu-id="56c6f-2400">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="56c6f-2400">Two-digit province code</span></span> 
- <span data-ttu-id="56c6f-2401">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2401">A period (optional)</span></span> 
- <span data-ttu-id="56c6f-2402">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="56c6f-2402">Two-digit regency or city code</span></span> 
- <span data-ttu-id="56c6f-2403">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="56c6f-2403">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="56c6f-2404">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2404">A period (optional)</span></span> 
- <span data-ttu-id="56c6f-2405">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2405">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-2406">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2406">A period (optional)</span></span> 
- <span data-ttu-id="56c6f-2407">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2407">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2408">Checksum</span></span>

<span data-ttu-id="56c6f-2409">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2409">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2410">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2410">Definition</span></span>

<span data-ttu-id="56c6f-2411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2412">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2412">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2413">Keyword_indonesia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2413">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="56c6f-2414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2415">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2415">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2416">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2416">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="56c6f-2417">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2417">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="56c6f-2418">KTP</span><span class="sxs-lookup"><span data-stu-id="56c6f-2418">KTP</span></span>
- <span data-ttu-id="56c6f-2419">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="56c6f-2419">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="56c6f-2420">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="56c6f-2420">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="56c6f-2421">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2421">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2422">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2422">Format</span></span>

<span data-ttu-id="56c6f-2423">国コード (2 文字)、チェックディジット (2 桁)、および番号を bban 最大30文字)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2423">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2424">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2424">Pattern</span></span>

<span data-ttu-id="56c6f-2425">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2425">Pattern must include all of the following:</span></span>

- <span data-ttu-id="56c6f-2426">2文字の国コード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2426">Two-letter country code</span></span>
- <span data-ttu-id="56c6f-2427">2つのチェックディジット (オプションのスペースが続く)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2427">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="56c6f-2428">1-7 4 つの文字または数字のグループ (スペースで区切ることができます)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2428">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="56c6f-2429">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2429">1-3 letters or digits</span></span>

<span data-ttu-id="56c6f-2430">各国の形式は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2430">The format for each country is slightly different.</span></span> <span data-ttu-id="56c6f-2431">IBAN 機密情報の種類には、次の60国が含まれています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2431">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="56c6f-2432">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、hu、gl、gr、hr、、ie、il、、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="56c6f-2432">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2433">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2433">Checksum</span></span>

<span data-ttu-id="56c6f-2434">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2435">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2435">Definition</span></span>

<span data-ttu-id="56c6f-2436">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2437">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2437">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2438">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2438">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2439">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2439">Keywords</span></span>

<span data-ttu-id="56c6f-2440">None</span><span class="sxs-lookup"><span data-stu-id="56c6f-2440">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="56c6f-2441">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="56c6f-2441">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2442">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2442">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="56c6f-2443">IPv4</span><span class="sxs-lookup"><span data-stu-id="56c6f-2443">IPv4:</span></span>
<span data-ttu-id="56c6f-2444">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2444">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="56c6f-2445">IPv6</span><span class="sxs-lookup"><span data-stu-id="56c6f-2445">IPv6:</span></span>
<span data-ttu-id="56c6f-2446"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2446">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2447">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2447">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2448">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2448">Checksum</span></span>

<span data-ttu-id="56c6f-2449">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2449">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2450">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2450">Definition</span></span>

<span data-ttu-id="56c6f-2451">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2451">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2452">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2452">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2453">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2453">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="56c6f-2454">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2454">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2455">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2455">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2456">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2456">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="56c6f-2457">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2457">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2458">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2458">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2459">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2459">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2460">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2460">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="56c6f-2461">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="56c6f-2461">Keyword_ipaddress</span></span>

- <span data-ttu-id="56c6f-2462">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2462">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="56c6f-2463">ip address</span><span class="sxs-lookup"><span data-stu-id="56c6f-2463">ip address</span></span> 
- <span data-ttu-id="56c6f-2464">ip addresses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2464">ip addresses</span></span>
- <span data-ttu-id="56c6f-2465">internet protocol</span><span class="sxs-lookup"><span data-stu-id="56c6f-2465">internet protocol</span></span>
- <span data-ttu-id="56c6f-2466">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="56c6f-2466">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="56c6f-2467">Diseases の国際分類 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2467">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2468">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2468">Format</span></span>

<span data-ttu-id="56c6f-2469">Dictionary</span><span class="sxs-lookup"><span data-stu-id="56c6f-2469">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2470">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2470">Pattern</span></span>

<span data-ttu-id="56c6f-2471">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2471">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2472">Checksum</span></span>

<span data-ttu-id="56c6f-2473">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2474">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2474">Definition</span></span>

<span data-ttu-id="56c6f-2475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2476">Dictionary_icd_10_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2476">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="56c6f-2477">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2477">Keywords</span></span>

<span data-ttu-id="56c6f-2478">Dictionary_icd_10_cm キーワードディクショナリの用語。 [Diseases、10リビジョン、臨床修正 (icd-10-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2478">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="56c6f-2479">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2479">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="56c6f-2480">Diseases の国際分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2480">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2481">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2481">Format</span></span>

<span data-ttu-id="56c6f-2482">Dictionary</span><span class="sxs-lookup"><span data-stu-id="56c6f-2482">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2483">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2483">Pattern</span></span>

<span data-ttu-id="56c6f-2484">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2484">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2485">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2485">Checksum</span></span>

<span data-ttu-id="56c6f-2486">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2486">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2487">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2487">Definition</span></span>

<span data-ttu-id="56c6f-2488">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2488">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2489">Dictionary_icd_9_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2489">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2490">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2490">Keywords</span></span>

<span data-ttu-id="56c6f-2491">Dictionary_icd_9_cm キーワードディクショナリの用語。 [Diseases、9リビジョン、臨床修正 (icd-9-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2491">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="56c6f-2492">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2492">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="56c6f-2493">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2493">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2494">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2494">Format</span></span>

<span data-ttu-id="56c6f-2495">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2495">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="56c6f-2496">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2496">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="56c6f-2497">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2497">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="56c6f-2498">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2498">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2499">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2499">Pattern</span></span>

<span data-ttu-id="56c6f-2500">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2500">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="56c6f-2501">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2501">Seven digits</span></span> 
- <span data-ttu-id="56c6f-2502">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2502">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="56c6f-2503">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="56c6f-2503">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="56c6f-2504">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2504">Seven digits</span></span> 
- <span data-ttu-id="56c6f-2505">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2505">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="56c6f-2506">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2506">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2507">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2507">Checksum</span></span>

<span data-ttu-id="56c6f-2508">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2508">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2509">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2509">Definition</span></span>

<span data-ttu-id="56c6f-2510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2511">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2511">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2512">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2512">One of the following is true:</span></span>
    - <span data-ttu-id="56c6f-2513">Keyword_ireland_pps からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2513">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="56c6f-2514">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2514">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="56c6f-2515">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2515">The checksum passes.</span></span>

<span data-ttu-id="56c6f-2516">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2516">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2517">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2517">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2518">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2518">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2519">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2519">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="56c6f-2520">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="56c6f-2520">Keyword_ireland_pps</span></span>

- <span data-ttu-id="56c6f-2521">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2521">Personal Public Service Number</span></span> 
- <span data-ttu-id="56c6f-2522">PPS Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2522">PPS Number</span></span> 
- <span data-ttu-id="56c6f-2523">PPS Num</span><span class="sxs-lookup"><span data-stu-id="56c6f-2523">PPS Num</span></span> 
- <span data-ttu-id="56c6f-2524">PPS No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2524">PPS No.</span></span> 
- <span data-ttu-id="56c6f-2525">PPS #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2525">PPS #</span></span> 
- <span data-ttu-id="56c6f-2526">PPS</span><span class="sxs-lookup"><span data-stu-id="56c6f-2526">PPS#</span></span> 
- <span data-ttu-id="56c6f-2527">ppsn</span><span class="sxs-lookup"><span data-stu-id="56c6f-2527">PPSN</span></span> 
- <span data-ttu-id="56c6f-2528">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2528">Public Services Card</span></span> 
- <span data-ttu-id="56c6f-2529">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="56c6f-2529">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="56c6f-2530">Uimh。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2530">Uimh.</span></span> <span data-ttu-id="56c6f-2531">PSP</span><span class="sxs-lookup"><span data-stu-id="56c6f-2531">PSP</span></span> 
- <span data-ttu-id="56c6f-2532">PSP</span><span class="sxs-lookup"><span data-stu-id="56c6f-2532">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="56c6f-2533">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2533">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2534">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2534">Format</span></span>

<span data-ttu-id="56c6f-2535">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2535">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2536">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2536">Pattern</span></span>

<span data-ttu-id="56c6f-2537">さ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2537">Formatted:</span></span>
- <span data-ttu-id="56c6f-2538">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2538">Two digits</span></span> 
- <span data-ttu-id="56c6f-2539">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2539">A dash</span></span> 
- <span data-ttu-id="56c6f-2540">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2540">Three digits</span></span> 
- <span data-ttu-id="56c6f-2541">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2541">A dash</span></span> 
- <span data-ttu-id="56c6f-2542">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2542">Eight digits</span></span>

<span data-ttu-id="56c6f-2543">なし</span><span class="sxs-lookup"><span data-stu-id="56c6f-2543">Unformatted:</span></span>
- <span data-ttu-id="56c6f-2544">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2544">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2545">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2545">Checksum</span></span>

<span data-ttu-id="56c6f-2546">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2546">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2547">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2547">Definition</span></span>

<span data-ttu-id="56c6f-2548">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2549">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2549">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2550">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2550">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2551">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2551">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="56c6f-2552">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2552">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="56c6f-2553">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2553">Bank Account Number</span></span> 
- <span data-ttu-id="56c6f-2554">Bank Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-2554">Bank Account</span></span> 
- <span data-ttu-id="56c6f-2555">Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2555">Account Number</span></span> 
- <span data-ttu-id="56c6f-2556">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="56c6f-2556">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="56c6f-2557">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2557">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2558">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2558">Format</span></span>

<span data-ttu-id="56c6f-2559">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2559">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2560">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2560">Pattern</span></span>

<span data-ttu-id="56c6f-2561">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2561">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2562">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2562">Checksum</span></span>

<span data-ttu-id="56c6f-2563">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2563">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2564">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2564">Definition</span></span>

<span data-ttu-id="56c6f-2565">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2565">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2566">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2566">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2567">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2567">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="56c6f-2568">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2568">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2569">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2569">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="56c6f-2570">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2570">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="56c6f-2571">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="56c6f-2571">מספר זהות</span></span> 
- <span data-ttu-id="56c6f-2572">National ID Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2572">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="56c6f-2573">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2573">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2574">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2574">Format</span></span>

<span data-ttu-id="56c6f-2575">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2575">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2576">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2576">Pattern</span></span>

- <span data-ttu-id="56c6f-2577">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2577">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="56c6f-2578">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2578">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-2579">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2579">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-2580">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2580">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="56c6f-2581">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2581">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2582">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2582">Checksum</span></span>

<span data-ttu-id="56c6f-2583">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2583">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2584">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2584">Definition</span></span>

<span data-ttu-id="56c6f-2585">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2586">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2586">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2587">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2587">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2588">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2588">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="56c6f-2589">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2589">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="56c6f-2590">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="56c6f-2590">numero di patente di guida</span></span> 
- <span data-ttu-id="56c6f-2591">patente di guida</span><span class="sxs-lookup"><span data-stu-id="56c6f-2591">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="56c6f-2592">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2592">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2593">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2593">Format</span></span>

<span data-ttu-id="56c6f-2594">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2594">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2595">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2595">Pattern</span></span>

<span data-ttu-id="56c6f-2596">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2596">Bank account number:</span></span>
- <span data-ttu-id="56c6f-2597">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2597">Seven or eight digits</span></span>
- <span data-ttu-id="56c6f-2598">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2598">Bank account branch code:</span></span>
- <span data-ttu-id="56c6f-2599">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2599">Four digits</span></span> 
- <span data-ttu-id="56c6f-2600">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2600">A space or dash (optional)</span></span> 
- <span data-ttu-id="56c6f-2601">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2601">Three digits</span></span>

<span data-ttu-id="56c6f-2602">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2602">Checksum</span></span>

<span data-ttu-id="56c6f-2603">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2603">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2604">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2604">Definition</span></span>

<span data-ttu-id="56c6f-2605">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2605">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2606">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2606">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2607">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2607">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="56c6f-2608">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2608">One of the following is true:</span></span>
- <span data-ttu-id="56c6f-2609">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2609">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2610">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2610">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="56c6f-2611">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2611">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2612">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2612">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2613">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2613">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2614">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2614">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="56c6f-2615">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="56c6f-2615">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="56c6f-2616">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2616">Checking Account Number</span></span> 
- <span data-ttu-id="56c6f-2617">Checking Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-2617">Checking Account</span></span> 
- <span data-ttu-id="56c6f-2618">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2618">Checking Account #</span></span> 
- <span data-ttu-id="56c6f-2619">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2619">Checking Acct Number</span></span> 
- <span data-ttu-id="56c6f-2620">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2620">Checking Acct #</span></span> 
- <span data-ttu-id="56c6f-2621">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2621">Checking Acct No.</span></span> 
- <span data-ttu-id="56c6f-2622">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2622">Checking Account No.</span></span> 
- <span data-ttu-id="56c6f-2623">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2623">Bank Account Number</span></span> 
- <span data-ttu-id="56c6f-2624">Bank Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-2624">Bank Account</span></span> 
- <span data-ttu-id="56c6f-2625">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2625">Bank Account #</span></span> 
- <span data-ttu-id="56c6f-2626">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2626">Bank Acct Number</span></span> 
- <span data-ttu-id="56c6f-2627">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2627">Bank Acct #</span></span> 
- <span data-ttu-id="56c6f-2628">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2628">Bank Acct No.</span></span> 
- <span data-ttu-id="56c6f-2629">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2629">Bank Account No.</span></span> 
- <span data-ttu-id="56c6f-2630">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2630">Savings Account Number</span></span> 
- <span data-ttu-id="56c6f-2631">Savings Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-2631">Savings Account</span></span> 
- <span data-ttu-id="56c6f-2632">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2632">Savings Account #</span></span> 
- <span data-ttu-id="56c6f-2633">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2633">Savings Acct Number</span></span> 
- <span data-ttu-id="56c6f-2634">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2634">Savings Acct #</span></span> 
- <span data-ttu-id="56c6f-2635">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2635">Savings Acct No.</span></span> 
- <span data-ttu-id="56c6f-2636">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2636">Savings Account No.</span></span> 
- <span data-ttu-id="56c6f-2637">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2637">Debit Account Number</span></span> 
- <span data-ttu-id="56c6f-2638">Debit Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-2638">Debit Account</span></span> 
- <span data-ttu-id="56c6f-2639">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2639">Debit Account #</span></span> 
- <span data-ttu-id="56c6f-2640">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2640">Debit Acct Number</span></span> 
- <span data-ttu-id="56c6f-2641">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2641">Debit Acct #</span></span> 
- <span data-ttu-id="56c6f-2642">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2642">Debit Acct No.</span></span> 
- <span data-ttu-id="56c6f-2643">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2643">Debit Account No.</span></span> 
- <span data-ttu-id="56c6f-2644">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="56c6f-2644">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="56c6f-2645">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="56c6f-2645">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="56c6f-2646">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="56c6f-2646">＃勘定の確認</span></span> 
- <span data-ttu-id="56c6f-2647">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="56c6f-2647">勘定番号の確認</span></span> 
- <span data-ttu-id="56c6f-2648">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="56c6f-2648">口座番号の確認</span></span> 
- <span data-ttu-id="56c6f-2649">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2649">銀行口座番号</span></span> 
- <span data-ttu-id="56c6f-2650">銀行口座</span><span class="sxs-lookup"><span data-stu-id="56c6f-2650">銀行口座</span></span> 
- <span data-ttu-id="56c6f-2651">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2651">銀行口座＃</span></span> 
- <span data-ttu-id="56c6f-2652">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2652">銀行の勘定番号</span></span> 
- <span data-ttu-id="56c6f-2653">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2653">銀行のacct＃</span></span> 
- <span data-ttu-id="56c6f-2654">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2654">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="56c6f-2655">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2655">銀行口座番号</span></span>
- <span data-ttu-id="56c6f-2656">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2656">普通預金口座番号</span></span> 
- <span data-ttu-id="56c6f-2657">預金口座</span><span class="sxs-lookup"><span data-stu-id="56c6f-2657">預金口座</span></span> 
- <span data-ttu-id="56c6f-2658">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2658">貯蓄口座＃</span></span> 
- <span data-ttu-id="56c6f-2659">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="56c6f-2659">貯蓄勘定の数</span></span> 
- <span data-ttu-id="56c6f-2660">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2660">貯蓄勘定＃</span></span> 
- <span data-ttu-id="56c6f-2661">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2661">貯蓄勘定番号</span></span> 
- <span data-ttu-id="56c6f-2662">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2662">普通預金口座番号</span></span> 
- <span data-ttu-id="56c6f-2663">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2663">引き落とし口座番号</span></span> 
- <span data-ttu-id="56c6f-2664">口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2664">口座番号</span></span> 
- <span data-ttu-id="56c6f-2665">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2665">口座番号＃</span></span> 
- <span data-ttu-id="56c6f-2666">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2666">デビットのacct番号</span></span> 
- <span data-ttu-id="56c6f-2667">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2667">デビット勘定＃</span></span> 
- <span data-ttu-id="56c6f-2668">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2668">デビットACCTの番号</span></span> 
- <span data-ttu-id="56c6f-2669">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2669">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="56c6f-2670">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="56c6f-2670">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="56c6f-2671">Otemachi</span><span class="sxs-lookup"><span data-stu-id="56c6f-2671">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="56c6f-2672">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2672">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2673">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2673">Format</span></span>

<span data-ttu-id="56c6f-2674">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2674">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2675">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2675">Pattern</span></span>

<span data-ttu-id="56c6f-2676">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2676">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2677">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2677">Checksum</span></span>

<span data-ttu-id="56c6f-2678">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2678">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2679">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2679">Definition</span></span>

<span data-ttu-id="56c6f-2680">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2681">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2681">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2682">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2682">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2683">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2683">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="56c6f-2684">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2684">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="56c6f-2685">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-2685">dl#</span></span> 
- <span data-ttu-id="56c6f-2686">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-2686">DL＃</span></span> 
- <span data-ttu-id="56c6f-2687">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-2687">dls#</span></span> 
- <span data-ttu-id="56c6f-2688">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-2688">DLS＃</span></span> 
- <span data-ttu-id="56c6f-2689">driver license</span><span class="sxs-lookup"><span data-stu-id="56c6f-2689">driver license</span></span> 
- <span data-ttu-id="56c6f-2690">driver licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2690">driver licenses</span></span> 
- <span data-ttu-id="56c6f-2691">drivers license</span><span class="sxs-lookup"><span data-stu-id="56c6f-2691">drivers license</span></span> 
- <span data-ttu-id="56c6f-2692">driver's license</span><span class="sxs-lookup"><span data-stu-id="56c6f-2692">driver's license</span></span> 
- <span data-ttu-id="56c6f-2693">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2693">drivers licenses</span></span> 
- <span data-ttu-id="56c6f-2694">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-2694">driver's licenses</span></span> 
- <span data-ttu-id="56c6f-2695">driving licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-2695">driving licence</span></span> 
- <span data-ttu-id="56c6f-2696">そして</span><span class="sxs-lookup"><span data-stu-id="56c6f-2696">lic#</span></span> 
- <span data-ttu-id="56c6f-2697">そして</span><span class="sxs-lookup"><span data-stu-id="56c6f-2697">LIC＃</span></span> 
- <span data-ttu-id="56c6f-2698">lics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2698">lics#</span></span> 
- <span data-ttu-id="56c6f-2699">state id</span><span class="sxs-lookup"><span data-stu-id="56c6f-2699">state id</span></span> 
- <span data-ttu-id="56c6f-2700">state identification</span><span class="sxs-lookup"><span data-stu-id="56c6f-2700">state identification</span></span> 
- <span data-ttu-id="56c6f-2701">state identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2701">state identification number</span></span> 
- <span data-ttu-id="56c6f-2702">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2702">低所得国＃</span></span> 
- <span data-ttu-id="56c6f-2703">免許証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2703">免許証</span></span> 
- <span data-ttu-id="56c6f-2704">状態ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2704">状態ID</span></span>
- <span data-ttu-id="56c6f-2705">状態の識別</span><span class="sxs-lookup"><span data-stu-id="56c6f-2705">状態の識別</span></span> 
- <span data-ttu-id="56c6f-2706">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2706">状態の識別番号</span></span> 
- <span data-ttu-id="56c6f-2707">運転免許</span><span class="sxs-lookup"><span data-stu-id="56c6f-2707">運転免許</span></span> 
- <span data-ttu-id="56c6f-2708">運転免許証</span><span class="sxs-lookup"><span data-stu-id="56c6f-2708">運転免許証</span></span> 
- <span data-ttu-id="56c6f-2709">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2709">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="56c6f-2710">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2710">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2711">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2711">Format</span></span>

<span data-ttu-id="56c6f-2712">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2712">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2713">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2713">Pattern</span></span>

<span data-ttu-id="56c6f-2714">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2714">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2715">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2715">Checksum</span></span>

<span data-ttu-id="56c6f-2716">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2716">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2717">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2717">Definition</span></span>

<span data-ttu-id="56c6f-2718">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2718">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2719">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2719">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2720">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2720">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2721">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2721">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="56c6f-2722">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-2722">Keyword_jp_passport</span></span>

- <span data-ttu-id="56c6f-2723">パスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-2723">パスポート</span></span> 
- <span data-ttu-id="56c6f-2724">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2724">パスポート番号</span></span> 
- <span data-ttu-id="56c6f-2725">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="56c6f-2725">パスポートのNum</span></span> 
- <span data-ttu-id="56c6f-2726">パスポート #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2726">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="56c6f-2727">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2727">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2728">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2728">Format</span></span>

<span data-ttu-id="56c6f-2729">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2729">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2730">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2730">Pattern</span></span>

<span data-ttu-id="56c6f-2731">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2731">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2732">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2732">Checksum</span></span>

<span data-ttu-id="56c6f-2733">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2733">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2734">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2734">Definition</span></span>

<span data-ttu-id="56c6f-2735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2736">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2736">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2737">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2737">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2738">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2738">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="56c6f-2739">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2739">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="56c6f-2740">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2740">Resident Registration Number</span></span>
- <span data-ttu-id="56c6f-2741">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2741">Resident Register Number</span></span> 
- <span data-ttu-id="56c6f-2742">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2742">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="56c6f-2743">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2743">Resident Registration No.</span></span> 
- <span data-ttu-id="56c6f-2744">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2744">Resident Register No.</span></span> 
- <span data-ttu-id="56c6f-2745">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2745">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="56c6f-2746">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2746">Basic Resident Register No.</span></span> 
- <span data-ttu-id="56c6f-2747">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="56c6f-2747">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="56c6f-2748">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2748">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="56c6f-2749">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="56c6f-2749">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="56c6f-2750">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2750">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="56c6f-2751">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2751">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2752">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2752">Format</span></span>

<span data-ttu-id="56c6f-2753">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2753">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2754">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2754">Pattern</span></span>

<span data-ttu-id="56c6f-2755">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2755">7-12 digits:</span></span>
- <span data-ttu-id="56c6f-2756">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2756">Four digits</span></span> 
- <span data-ttu-id="56c6f-2757">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2757">A hyphen (optional)</span></span> 
- <span data-ttu-id="56c6f-2758">6桁の数字または</span><span class="sxs-lookup"><span data-stu-id="56c6f-2758">Six digits OR</span></span>
- <span data-ttu-id="56c6f-2759">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2759">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2760">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2760">Checksum</span></span>

<span data-ttu-id="56c6f-2761">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2761">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2762">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2762">Definition</span></span>

<span data-ttu-id="56c6f-2763">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2763">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2764">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2764">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2765">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2765">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="56c6f-2766">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2766">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2767">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2767">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2768">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2768">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2769">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2769">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="56c6f-2770">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="56c6f-2770">Keyword_jp_sin</span></span>

- <span data-ttu-id="56c6f-2771">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2771">Social Insurance No.</span></span> 
- <span data-ttu-id="56c6f-2772">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="56c6f-2772">Social Insurance Num</span></span> 
- <span data-ttu-id="56c6f-2773">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2773">Social Insurance Number</span></span> 
- <span data-ttu-id="56c6f-2774">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="56c6f-2774">社会保険のテンキー</span></span> 
- <span data-ttu-id="56c6f-2775">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2775">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="56c6f-2776">日本の居住カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2776">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2777">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2777">Format</span></span>

<span data-ttu-id="56c6f-2778">12桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2778">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2779">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2779">Pattern</span></span>

<span data-ttu-id="56c6f-2780">12桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2780">12 letters and digits:</span></span>
- <span data-ttu-id="56c6f-2781">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2781">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="56c6f-2782">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2782">Eight digits</span></span> 
- <span data-ttu-id="56c6f-2783">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2783">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2784">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2784">Checksum</span></span>

<span data-ttu-id="56c6f-2785">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2785">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2786">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2786">Definition</span></span>

<span data-ttu-id="56c6f-2787">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2788">正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2788">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2789">Keyword_jp_residence_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2789">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2790">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2790">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="56c6f-2791">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2791">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="56c6f-2792">居住カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2792">Residence card number</span></span>
- <span data-ttu-id="56c6f-2793">住居カードなし</span><span class="sxs-lookup"><span data-stu-id="56c6f-2793">Residence card no</span></span>
- <span data-ttu-id="56c6f-2794">住居カード #</span><span class="sxs-lookup"><span data-stu-id="56c6f-2794">Residence card #</span></span>
- <span data-ttu-id="56c6f-2795">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2795">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="56c6f-2796">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2796">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2797">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2797">Format</span></span>

<span data-ttu-id="56c6f-2798">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2798">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2799">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2799">Pattern</span></span>

<span data-ttu-id="56c6f-2800">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2800">12 digits:</span></span>
- <span data-ttu-id="56c6f-2801">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2801">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-2802">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2802">A dash (optional)</span></span> 
- <span data-ttu-id="56c6f-2803">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2803">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="56c6f-2804">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2804">A dash (optional)</span></span> 
- <span data-ttu-id="56c6f-2805">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2805">Three random digits</span></span> 
- <span data-ttu-id="56c6f-2806">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2806">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2807">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2807">Checksum</span></span>

<span data-ttu-id="56c6f-2808">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2808">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2809">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2809">Definition</span></span>

<span data-ttu-id="56c6f-2810">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2810">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2811">正規表現 Regex_malaysia_id_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2811">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2812">Keyword_malaysia_id_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2812">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2813">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2813">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="56c6f-2814">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2814">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="56c6f-2815">デジタルアプリケーションカード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2815">digital application card</span></span>
- <span data-ttu-id="56c6f-2816">i/c</span><span class="sxs-lookup"><span data-stu-id="56c6f-2816">i/c</span></span>
- <span data-ttu-id="56c6f-2817">i/c いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2817">i/c no</span></span>
- <span data-ttu-id="56c6f-2818">ic</span><span class="sxs-lookup"><span data-stu-id="56c6f-2818">ic</span></span>
- <span data-ttu-id="56c6f-2819">ic no</span><span class="sxs-lookup"><span data-stu-id="56c6f-2819">ic no</span></span>
- <span data-ttu-id="56c6f-2820">id card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2820">id card</span></span>
- <span data-ttu-id="56c6f-2821">識別カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2821">identification Card</span></span>
- <span data-ttu-id="56c6f-2822">Identity card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2822">identity card</span></span>
- <span data-ttu-id="56c6f-2823">k/p</span><span class="sxs-lookup"><span data-stu-id="56c6f-2823">k/p</span></span>
- <span data-ttu-id="56c6f-2824">k/p no</span><span class="sxs-lookup"><span data-stu-id="56c6f-2824">k/p no</span></span>
- <span data-ttu-id="56c6f-2825">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="56c6f-2825">kad akuan diri</span></span>
- <span data-ttu-id="56c6f-2826">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="56c6f-2826">kad aplikasi digital</span></span>
- <span data-ttu-id="56c6f-2827">kad の genalan マレーシア</span><span class="sxs-lookup"><span data-stu-id="56c6f-2827">kad pengenalan malaysia</span></span>
- <span data-ttu-id="56c6f-2828">kp</span><span class="sxs-lookup"><span data-stu-id="56c6f-2828">kp</span></span>
- <span data-ttu-id="56c6f-2829">kp no</span><span class="sxs-lookup"><span data-stu-id="56c6f-2829">kp no</span></span>
- <span data-ttu-id="56c6f-2830">mykad</span><span class="sxs-lookup"><span data-stu-id="56c6f-2830">mykad</span></span>
- <span data-ttu-id="56c6f-2831">mykas</span><span class="sxs-lookup"><span data-stu-id="56c6f-2831">mykas</span></span>
- <span data-ttu-id="56c6f-2832">mykid</span><span class="sxs-lookup"><span data-stu-id="56c6f-2832">mykid</span></span>
- <span data-ttu-id="56c6f-2833">mypr</span><span class="sxs-lookup"><span data-stu-id="56c6f-2833">mypr</span></span>
- <span data-ttu-id="56c6f-2834">mytentera</span><span class="sxs-lookup"><span data-stu-id="56c6f-2834">mytentera</span></span>
- <span data-ttu-id="56c6f-2835">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2835">malaysia identity card</span></span>
- <span data-ttu-id="56c6f-2836">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2836">malaysian identity card</span></span>
- <span data-ttu-id="56c6f-2837">nric</span><span class="sxs-lookup"><span data-stu-id="56c6f-2837">nric</span></span>
- <span data-ttu-id="56c6f-2838">個人識別カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2838">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="56c6f-2839">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2839">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2840">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2840">Format</span></span>

<span data-ttu-id="56c6f-2841">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2841">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2842">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2842">Pattern</span></span>

<span data-ttu-id="56c6f-2843">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2843">8-9 digits:</span></span>
- <span data-ttu-id="56c6f-2844">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2844">Three digits</span></span> 
- <span data-ttu-id="56c6f-2845">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2845">A space (optional)</span></span> 
- <span data-ttu-id="56c6f-2846">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2846">Three digits</span></span> 
- <span data-ttu-id="56c6f-2847">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="56c6f-2847">A space (optional)</span></span> 
- <span data-ttu-id="56c6f-2848">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2848">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2849">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2849">Checksum</span></span>

<span data-ttu-id="56c6f-2850">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2850">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2851">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2851">Definition</span></span>

<span data-ttu-id="56c6f-2852">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2852">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2853">関数 Func_netherlands_bsn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2853">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2854">Keyword_netherlands_bsn からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2854">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="56c6f-2855">関数 Func_eu_date2 は、日付を正しい日付形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2855">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="56c6f-2856">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2857">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2857">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="56c6f-2858">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="56c6f-2858">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="56c6f-2859">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2859">Citizen service number</span></span> 
- <span data-ttu-id="56c6f-2860">BSN</span><span class="sxs-lookup"><span data-stu-id="56c6f-2860">BSN</span></span> 
- <span data-ttu-id="56c6f-2861">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2861">Burgerservicenummer</span></span> 
- <span data-ttu-id="56c6f-2862">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2862">Sofinummer</span></span> 
- <span data-ttu-id="56c6f-2863">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2863">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="56c6f-2864">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2864">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="56c6f-2865">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2865">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2866">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2866">Format</span></span>

<span data-ttu-id="56c6f-2867">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2867">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2868">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2868">Pattern</span></span>

<span data-ttu-id="56c6f-2869">3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2869">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2870">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2870">Checksum</span></span>

<span data-ttu-id="56c6f-2871">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2871">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2872">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2872">Definition</span></span>

<span data-ttu-id="56c6f-2873">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2873">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2874">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2874">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2875">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2875">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="56c6f-2876">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2876">The checksum passes.</span></span>

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

<span data-ttu-id="56c6f-2877">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2877">Keywords</span></span>

<span data-ttu-id="56c6f-2878">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="56c6f-2878">Keyword_nz_terms</span></span>

- <span data-ttu-id="56c6f-2879">nhi</span><span class="sxs-lookup"><span data-stu-id="56c6f-2879">NHI</span></span> 
- <span data-ttu-id="56c6f-2880">New Zealand</span><span class="sxs-lookup"><span data-stu-id="56c6f-2880">New Zealand</span></span> 
- <span data-ttu-id="56c6f-2881">タスクの状況</span><span class="sxs-lookup"><span data-stu-id="56c6f-2881">Health</span></span> 
- <span data-ttu-id="56c6f-2882">処理</span><span class="sxs-lookup"><span data-stu-id="56c6f-2882">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="56c6f-2883">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2883">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2884">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2884">Format</span></span>

<span data-ttu-id="56c6f-2885">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2885">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2886">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2886">Pattern</span></span>

<span data-ttu-id="56c6f-2887">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2887">11 digits:</span></span>
- <span data-ttu-id="56c6f-2888">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2888">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-2889">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2889">Three-digit individual number</span></span> 
- <span data-ttu-id="56c6f-2890">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="56c6f-2890">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2891">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2891">Checksum</span></span>

<span data-ttu-id="56c6f-2892">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2892">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2893">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2893">Definition</span></span>

<span data-ttu-id="56c6f-2894">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2894">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2895">関数 Func_norway_id_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2895">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2896">Keyword_norway_id_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2896">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="56c6f-2897">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2897">The checksum passes.</span></span>
- <span data-ttu-id="56c6f-2898">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2898">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2899">関数 Func_norway_id_numbe は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2899">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2900">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2900">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2901">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2901">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="56c6f-2902">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2902">Keyword_norway_id_number</span></span>

- <span data-ttu-id="56c6f-2903">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2903">Personal identification number</span></span>
- <span data-ttu-id="56c6f-2904">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2904">Norwegian ID Number</span></span>
- <span data-ttu-id="56c6f-2905">ID Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2905">ID Number</span></span>
- <span data-ttu-id="56c6f-2906">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-2906">Identification</span></span>
- <span data-ttu-id="56c6f-2907">Personnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2907">Personnummer</span></span>
- <span data-ttu-id="56c6f-2908">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="56c6f-2908">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="56c6f-2909">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2909">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2910">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2910">Format</span></span>

<span data-ttu-id="56c6f-2911">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2911">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2912">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2912">Pattern</span></span>

<span data-ttu-id="56c6f-2913">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-2913">12 digits:</span></span>
- <span data-ttu-id="56c6f-2914">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2914">Four digits</span></span> 
- <span data-ttu-id="56c6f-2915">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-2915">A hyphen</span></span> 
- <span data-ttu-id="56c6f-2916">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-2916">Seven digits</span></span> 
- <span data-ttu-id="56c6f-2917">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-2917">A hyphen</span></span> 
- <span data-ttu-id="56c6f-2918">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2918">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2919">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2919">Checksum</span></span>

<span data-ttu-id="56c6f-2920">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2920">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2921">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2921">Definition</span></span>

<span data-ttu-id="56c6f-2922">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2922">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2923">正規表現 Regex_philippines_unified_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2923">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2924">Keyword_philippines_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2924">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2925">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2925">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="56c6f-2926">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-2926">Keyword_philippines_id</span></span>

- <span data-ttu-id="56c6f-2927">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2927">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="56c6f-2928">umid</span><span class="sxs-lookup"><span data-stu-id="56c6f-2928">UMID</span></span> 
- <span data-ttu-id="56c6f-2929">Identity Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2929">Identity Card</span></span> 
- <span data-ttu-id="56c6f-2930">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-2930">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="56c6f-2931">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2931">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2932">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2932">Format</span></span>

<span data-ttu-id="56c6f-2933">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2933">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2934">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2934">Pattern</span></span>

<span data-ttu-id="56c6f-2935">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2935">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2936">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2936">Checksum</span></span>

<span data-ttu-id="56c6f-2937">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2937">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2938">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2938">Definition</span></span>

<span data-ttu-id="56c6f-2939">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2939">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="56c6f-2940">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2940">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="56c6f-2941">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2941">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2942">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2942">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="56c6f-2943">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2943">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="56c6f-2944">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="56c6f-2944">Dowód osobisty</span></span>
- <span data-ttu-id="56c6f-2945">特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="56c6f-2945">Numer dowodu osobistego</span></span>
- <span data-ttu-id="56c6f-2946">nazwa i 特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="56c6f-2946">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="56c6f-2947">nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="56c6f-2947">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="56c6f-2948">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="56c6f-2948">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="56c6f-2949">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="56c6f-2949">Dowód Tożsamości</span></span>
- <span data-ttu-id="56c6f-2950">dow.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2950">dow.</span></span> <span data-ttu-id="56c6f-2951">hp-ux.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2951">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="56c6f-2952">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="56c6f-2952">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2953">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2953">Format</span></span>

<span data-ttu-id="56c6f-2954">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2954">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2955">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2955">Pattern</span></span>

<span data-ttu-id="56c6f-2956">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2956">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2957">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2957">Checksum</span></span>

<span data-ttu-id="56c6f-2958">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2958">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2959">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2959">Definition</span></span>

<span data-ttu-id="56c6f-2960">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2960">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2961">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2961">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2962">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2962">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="56c6f-2963">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2963">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2964">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2964">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="56c6f-2965">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2965">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="56c6f-2966">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="56c6f-2966">Nr PESEL</span></span>
- <span data-ttu-id="56c6f-2967">PESEL</span><span class="sxs-lookup"><span data-stu-id="56c6f-2967">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="56c6f-2968">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-2968">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2969">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2969">Format</span></span>

<span data-ttu-id="56c6f-2970">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2970">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2971">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2971">Pattern</span></span>

<span data-ttu-id="56c6f-2972">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2972">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2973">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2973">Checksum</span></span>

<span data-ttu-id="56c6f-2974">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-2974">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2975">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2975">Definition</span></span>

<span data-ttu-id="56c6f-2976">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2976">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2977">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2977">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2978">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2978">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="56c6f-2979">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2979">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-2980">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2980">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="56c6f-2981">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-2981">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="56c6f-2982">特定の引数</span><span class="sxs-lookup"><span data-stu-id="56c6f-2982">Numer paszportu</span></span>
- <span data-ttu-id="56c6f-2983">Nr.</span><span class="sxs-lookup"><span data-stu-id="56c6f-2983">Nr.</span></span> <span data-ttu-id="56c6f-2984">大き zportu</span><span class="sxs-lookup"><span data-stu-id="56c6f-2984">Paszportu</span></span>
- <span data-ttu-id="56c6f-2985">があります</span><span class="sxs-lookup"><span data-stu-id="56c6f-2985">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="56c6f-2986">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-2986">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-2987">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-2987">Format</span></span>

<span data-ttu-id="56c6f-2988">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2988">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-2989">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-2989">Pattern</span></span>

<span data-ttu-id="56c6f-2990">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-2990">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-2991">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-2991">Checksum</span></span>

<span data-ttu-id="56c6f-2992">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-2992">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-2993">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-2993">Definition</span></span>

<span data-ttu-id="56c6f-2994">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2994">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-2995">正規表現 Regex_portugal_citizen_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2995">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-2996">Keyword_portugal_citizen_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-2996">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-2997">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-2997">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="56c6f-2998">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2998">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="56c6f-2999">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-2999">Citizen Card</span></span>
- <span data-ttu-id="56c6f-3000">National ID Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3000">National ID Card</span></span>
- <span data-ttu-id="56c6f-3001">CC</span><span class="sxs-lookup"><span data-stu-id="56c6f-3001">CC</span></span>
- <span data-ttu-id="56c6f-3002">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="56c6f-3002">Cartão de Cidadão</span></span>
- <span data-ttu-id="56c6f-3003">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="56c6f-3003">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="56c6f-3004">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3004">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3005">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3005">Format</span></span>

<span data-ttu-id="56c6f-3006">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3006">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3007">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3007">Pattern</span></span>

<span data-ttu-id="56c6f-3008">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3008">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3009">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3009">Checksum</span></span>

<span data-ttu-id="56c6f-3010">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3010">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3011">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3011">Definition</span></span>

<span data-ttu-id="56c6f-3012">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3012">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3013">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3013">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3014">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3014">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3015">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3015">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="56c6f-3016">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-3016">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="56c6f-3017">Identification Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3017">Identification Card</span></span> 
- <span data-ttu-id="56c6f-3018">I card number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3018">I card number</span></span> 
- <span data-ttu-id="56c6f-3019">ID number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3019">ID number</span></span> 
- <span data-ttu-id="56c6f-3020">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="56c6f-3020">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="56c6f-3021">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3021">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3022">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3022">Format</span></span>

<span data-ttu-id="56c6f-3023">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3023">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3024">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3024">Pattern</span></span>

- <span data-ttu-id="56c6f-3025">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3025">Nine letters and digits:</span></span>
- <span data-ttu-id="56c6f-3026">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-3026">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-3027">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3027">Seven digits</span></span> 
- <span data-ttu-id="56c6f-3028">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="56c6f-3028">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3029">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3029">Checksum</span></span>

<span data-ttu-id="56c6f-3030">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3030">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3031">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3031">Definition</span></span>

<span data-ttu-id="56c6f-3032">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3032">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3033">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3033">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3034">Keyword_singapore_nric からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3034">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="56c6f-3035">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3035">The checksum passes.</span></span>

<span data-ttu-id="56c6f-3036">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3036">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3037">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3037">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3038">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3038">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3039">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3039">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="56c6f-3040">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="56c6f-3040">Keyword_singapore_nric</span></span>

- <span data-ttu-id="56c6f-3041">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3041">National Registration Identity Card</span></span> 
- <span data-ttu-id="56c6f-3042">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3042">Identity Card Number</span></span> 
- <span data-ttu-id="56c6f-3043">NRIC</span><span class="sxs-lookup"><span data-stu-id="56c6f-3043">NRIC</span></span> 
- <span data-ttu-id="56c6f-3044">IC</span><span class="sxs-lookup"><span data-stu-id="56c6f-3044">IC</span></span> 
- <span data-ttu-id="56c6f-3045">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3045">Foreign Identification Number</span></span> 
- <span data-ttu-id="56c6f-3046">FIN</span><span class="sxs-lookup"><span data-stu-id="56c6f-3046">FIN</span></span> 
- <span data-ttu-id="56c6f-3047">身份证</span><span class="sxs-lookup"><span data-stu-id="56c6f-3047">身份证</span></span> 
- <span data-ttu-id="56c6f-3048">身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-3048">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="56c6f-3049">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3049">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3050">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3050">Format</span></span>

<span data-ttu-id="56c6f-3051">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3051">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3052">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3052">Pattern</span></span>

<span data-ttu-id="56c6f-3053">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3053">13 digits:</span></span>
- <span data-ttu-id="56c6f-3054">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3054">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-3055">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3055">Four digits</span></span> 
- <span data-ttu-id="56c6f-3056">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3056">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="56c6f-3057">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3057">The digit "8" or "9"</span></span> 
- <span data-ttu-id="56c6f-3058">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3058">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3059">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3059">Checksum</span></span>

<span data-ttu-id="56c6f-3060">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3061">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3061">Definition</span></span>

<span data-ttu-id="56c6f-3062">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3063">関数 Func_south_africa_identification_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3063">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3064">Keyword_south_africa_identification_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3064">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="56c6f-3065">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3065">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3066">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3066">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="56c6f-3067">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3067">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="56c6f-3068">Identity card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3068">Identity card</span></span>
- <span data-ttu-id="56c6f-3069">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3069">ID</span></span>
- <span data-ttu-id="56c6f-3070">fim</span><span class="sxs-lookup"><span data-stu-id="56c6f-3070">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="56c6f-3071">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3071">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3072">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3072">Format</span></span>

<span data-ttu-id="56c6f-3073">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3073">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3074">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3074">Pattern</span></span>

<span data-ttu-id="56c6f-3075">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3075">13 digits:</span></span>
- <span data-ttu-id="56c6f-3076">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3076">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="56c6f-3077">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="56c6f-3077">A hyphen</span></span> 
- <span data-ttu-id="56c6f-3078">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3078">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="56c6f-3079">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="56c6f-3079">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="56c6f-3080">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3080">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="56c6f-3081">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="56c6f-3081">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3082">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3082">Checksum</span></span>

<span data-ttu-id="56c6f-3083">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3083">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3084">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3084">Definition</span></span>

<span data-ttu-id="56c6f-3085">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3085">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3086">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3086">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3087">Keyword_south_korea_resident_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3087">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="56c6f-3088">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3088">The checksum passes.</span></span>

<span data-ttu-id="56c6f-3089">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3089">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3090">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3090">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3091">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3091">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3092">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3092">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="56c6f-3093">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3093">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="56c6f-3094">National ID card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3094">National ID card</span></span> 
- <span data-ttu-id="56c6f-3095">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3095">Citizen's Registration Number</span></span> 
- <span data-ttu-id="56c6f-3096">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="56c6f-3096">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="56c6f-3097">rrn</span><span class="sxs-lookup"><span data-stu-id="56c6f-3097">RRN</span></span> 
- <span data-ttu-id="56c6f-3098">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="56c6f-3098">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="56c6f-3099">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3099">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3100">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3100">Format</span></span>

<span data-ttu-id="56c6f-3101">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3101">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3102">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3102">Pattern</span></span>

<span data-ttu-id="56c6f-3103">11-12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3103">11-12 digits:</span></span>
- <span data-ttu-id="56c6f-3104">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3104">Two digits</span></span> 
- <span data-ttu-id="56c6f-3105">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3105">A forward slash (optional)</span></span> 
- <span data-ttu-id="56c6f-3106">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3106">7-8 digits</span></span> 
- <span data-ttu-id="56c6f-3107">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3107">A forward slash (optional)</span></span> 
- <span data-ttu-id="56c6f-3108">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3108">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3109">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3109">Checksum</span></span>

<span data-ttu-id="56c6f-3110">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3110">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3111">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3111">Definition</span></span>

<span data-ttu-id="56c6f-3112">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3112">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3113">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3113">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3114">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3114">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3115">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3115">Keywords</span></span>

<span data-ttu-id="56c6f-3116">None</span><span class="sxs-lookup"><span data-stu-id="56c6f-3116">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="56c6f-3117">SQL Server の接続文字列</span><span class="sxs-lookup"><span data-stu-id="56c6f-3117">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3118">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3118">Format</span></span>

<span data-ttu-id="56c6f-3119">文字列 "user id"、"user id"、"uid"、または "UserId" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3119">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3120">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3120">Pattern</span></span>

- <span data-ttu-id="56c6f-3121">文字列 "user id"、"user id"、"uid"、または "UserId"</span><span class="sxs-lookup"><span data-stu-id="56c6f-3121">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="56c6f-3122">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3122">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="56c6f-3123">文字列 "Password" または "pwd" ("pwd" の前に小文字が含まれていません)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3123">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="56c6f-3124">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3124">An equal sign (=)</span></span>
- <span data-ttu-id="56c6f-3125">ドル記号 ($)、パーセント記号 (%)、不等号 (>)、記号 (@)、二重引用符 (")、セミコロン (;)、左中かっこ ([)、左大かっこ ({) のいずれでもない文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3125">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="56c6f-3126">セミコロンではない7-128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")</span><span class="sxs-lookup"><span data-stu-id="56c6f-3126">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="56c6f-3127">セミコロン (;)または二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="56c6f-3127">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3128">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3128">Checksum</span></span>

<span data-ttu-id="56c6f-3129">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3129">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3130">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3130">Definition</span></span>

<span data-ttu-id="56c6f-3131">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3131">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3132">正規表現 CEP_Regex_SQLServerConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3132">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3133">CEP_GlobalFilter からのキーワードが見つかり**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3133">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="56c6f-3134">正規表現 CEP_PasswordPlaceHolder は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3134">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3135">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3135">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3136">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3136">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="56c6f-3137">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="56c6f-3137">CEP_GlobalFilter</span></span>

- <span data-ttu-id="56c6f-3138">パスワードの一部</span><span class="sxs-lookup"><span data-stu-id="56c6f-3138">some-password</span></span>
- <span data-ttu-id="56c6f-3139">パスワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3139">somepassword</span></span>
- <span data-ttu-id="56c6f-3140">secretPassword</span><span class="sxs-lookup"><span data-stu-id="56c6f-3140">secretPassword</span></span>
- <span data-ttu-id="56c6f-3141">示す</span><span class="sxs-lookup"><span data-stu-id="56c6f-3141">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="56c6f-3142">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="56c6f-3142">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="56c6f-3143">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3143">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-3144">Password または pwd の後に、0-2 スペース、等号 (=)、0-2 スペース、アスタリスク (\*)、または--</span><span class="sxs-lookup"><span data-stu-id="56c6f-3144">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="56c6f-3145">Password または pwd の後に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3145">Password or pwd followed by:</span></span>
    - <span data-ttu-id="56c6f-3146">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3146">Equal sign (=)</span></span>
    - <span data-ttu-id="56c6f-3147">小なり記号 (<)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3147">Less than symbol (<)</span></span>
    - <span data-ttu-id="56c6f-3148">1-200 文字の大文字と小文字、数字、アスタリスク (\*)、ハイフン (-)、下線 (_)、または空白文字の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3148">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="56c6f-3149">より大きい記号 (>)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3149">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="56c6f-3150">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="56c6f-3150">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="56c6f-3151">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3151">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="56c6f-3152">拠点</span><span class="sxs-lookup"><span data-stu-id="56c6f-3152">contoso</span></span>
- <span data-ttu-id="56c6f-3153">fabrikam</span><span class="sxs-lookup"><span data-stu-id="56c6f-3153">fabrikam</span></span>
- <span data-ttu-id="56c6f-3154">ノース</span><span class="sxs-lookup"><span data-stu-id="56c6f-3154">northwind</span></span>
- <span data-ttu-id="56c6f-3155">サンド</span><span class="sxs-lookup"><span data-stu-id="56c6f-3155">sandbox</span></span>
- <span data-ttu-id="56c6f-3156">onebox</span><span class="sxs-lookup"><span data-stu-id="56c6f-3156">onebox</span></span>
- <span data-ttu-id="56c6f-3157">localhost</span><span class="sxs-lookup"><span data-stu-id="56c6f-3157">localhost</span></span>
- <span data-ttu-id="56c6f-3158">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="56c6f-3158">127.0.0.1</span></span>
- <span data-ttu-id="56c6f-3159">testacs。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3159">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-3160">com</span><span class="sxs-lookup"><span data-stu-id="56c6f-3160">com</span></span>
- <span data-ttu-id="56c6f-3161">s-int。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3161">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="56c6f-3162">ネット</span><span class="sxs-lookup"><span data-stu-id="56c6f-3162">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="56c6f-3163">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3163">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3164">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3164">Format</span></span>

<span data-ttu-id="56c6f-3165">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3165">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3166">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3166">Pattern</span></span>

<span data-ttu-id="56c6f-3167">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3167">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="56c6f-3168">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3168">2-4 digits (optional)</span></span> 
- <span data-ttu-id="56c6f-3169">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3169">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="56c6f-3170">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="56c6f-3170">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="56c6f-3171">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3171">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3172">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3172">Checksum</span></span>

<span data-ttu-id="56c6f-3173">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3173">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3174">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3174">Definition</span></span>

<span data-ttu-id="56c6f-3175">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3175">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3176">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3176">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3177">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3177">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3178">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3178">Keywords</span></span>

<span data-ttu-id="56c6f-3179">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3179">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="56c6f-3180">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3180">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3181">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3181">Format</span></span>

<span data-ttu-id="56c6f-3182">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3182">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3183">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3183">Pattern</span></span>

<span data-ttu-id="56c6f-3184">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3184">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3185">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3185">Checksum</span></span>

<span data-ttu-id="56c6f-3186">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3186">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3187">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3187">Definition</span></span>

<span data-ttu-id="56c6f-3188">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3188">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3189">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3189">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3190">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3190">One of the following is true:</span></span>
    - <span data-ttu-id="56c6f-3191">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3191">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="56c6f-3192">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3192">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3193">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3193">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="56c6f-3194">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-3194">Keyword_sweden_passport</span></span>

- <span data-ttu-id="56c6f-3195">visa requirements</span><span class="sxs-lookup"><span data-stu-id="56c6f-3195">visa requirements</span></span> 
- <span data-ttu-id="56c6f-3196">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3196">Alien Registration Card</span></span> 
- <span data-ttu-id="56c6f-3197">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="56c6f-3197">Schengen visas</span></span> 
- <span data-ttu-id="56c6f-3198">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="56c6f-3198">Schengen visa</span></span> 
- <span data-ttu-id="56c6f-3199">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="56c6f-3199">Visa Processing</span></span> 
- <span data-ttu-id="56c6f-3200">Visa Type</span><span class="sxs-lookup"><span data-stu-id="56c6f-3200">Visa Type</span></span> 
- <span data-ttu-id="56c6f-3201">Single Entry</span><span class="sxs-lookup"><span data-stu-id="56c6f-3201">Single Entry</span></span> 
- <span data-ttu-id="56c6f-3202">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="56c6f-3202">Multiple Entry</span></span> 
- <span data-ttu-id="56c6f-3203">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="56c6f-3203">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="56c6f-3204">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-3204">Keyword_passport</span></span>

- <span data-ttu-id="56c6f-3205">Passport Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3205">Passport Number</span></span> 
- <span data-ttu-id="56c6f-3206">Passport No</span><span class="sxs-lookup"><span data-stu-id="56c6f-3206">Passport No</span></span> 
- <span data-ttu-id="56c6f-3207">Passport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3207">Passport #</span></span> 
- <span data-ttu-id="56c6f-3208">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-3208">Passport#</span></span> 
- <span data-ttu-id="56c6f-3209">PassportID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3209">PassportID</span></span> 
- <span data-ttu-id="56c6f-3210">Passportno</span><span class="sxs-lookup"><span data-stu-id="56c6f-3210">Passportno</span></span> 
- <span data-ttu-id="56c6f-3211">passportnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-3211">passportnumber</span></span> 
- <span data-ttu-id="56c6f-3212">パスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-3212">パスポート</span></span> 
- <span data-ttu-id="56c6f-3213">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3213">パスポート番号</span></span> 
- <span data-ttu-id="56c6f-3214">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="56c6f-3214">パスポートのNum</span></span> 
- <span data-ttu-id="56c6f-3215">パスポート #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3215">パスポート＃</span></span> 
- <span data-ttu-id="56c6f-3216">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="56c6f-3216">Numéro de passeport</span></span> 
- <span data-ttu-id="56c6f-3217">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-3217">Passeport n °</span></span> 
- <span data-ttu-id="56c6f-3218">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="56c6f-3218">Passeport Non</span></span> 
- <span data-ttu-id="56c6f-3219">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3219">Passeport #</span></span> 
- <span data-ttu-id="56c6f-3220">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3220">Passeport#</span></span> 
- <span data-ttu-id="56c6f-3221">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="56c6f-3221">PasseportNon</span></span> 
- <span data-ttu-id="56c6f-3222">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="56c6f-3222">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="56c6f-3223">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3223">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3224">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3224">Format</span></span>

<span data-ttu-id="56c6f-3225">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3225">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3226">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3226">Pattern</span></span>

<span data-ttu-id="56c6f-3227">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3227">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="56c6f-3228">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3228">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-3229">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-3229">An optional space</span></span> 
- <span data-ttu-id="56c6f-3230">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="56c6f-3230">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="56c6f-3231">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-3231">An optional space</span></span> 
- <span data-ttu-id="56c6f-3232">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3232">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3233">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3233">Checksum</span></span>

<span data-ttu-id="56c6f-3234">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3234">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3235">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3235">Definition</span></span>

<span data-ttu-id="56c6f-3236">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3236">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3237">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3237">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3238">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3238">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3239">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3239">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="56c6f-3240">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="56c6f-3240">Keyword_swift</span></span>

- <span data-ttu-id="56c6f-3241">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="56c6f-3241">international organization for standardization 9362</span></span> 
- <span data-ttu-id="56c6f-3242">iso 9362</span><span class="sxs-lookup"><span data-stu-id="56c6f-3242">iso 9362</span></span> 
- <span data-ttu-id="56c6f-3243">iso9362</span><span class="sxs-lookup"><span data-stu-id="56c6f-3243">iso9362</span></span> 
- <span data-ttu-id="56c6f-3244">実現\#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3244">swift\#</span></span> 
- <span data-ttu-id="56c6f-3245">swiftcode</span><span class="sxs-lookup"><span data-stu-id="56c6f-3245">swiftcode</span></span> 
- <span data-ttu-id="56c6f-3246">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-3246">swiftnumber</span></span> 
- <span data-ttu-id="56c6f-3247">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-3247">swiftroutingnumber</span></span> 
- <span data-ttu-id="56c6f-3248">swift code</span><span class="sxs-lookup"><span data-stu-id="56c6f-3248">swift code</span></span> 
- <span data-ttu-id="56c6f-3249">swift number #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3249">swift number #</span></span> 
- <span data-ttu-id="56c6f-3250">swift routing number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3250">swift routing number</span></span> 
- <span data-ttu-id="56c6f-3251">bic number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3251">bic number</span></span> 
- <span data-ttu-id="56c6f-3252">bic code</span><span class="sxs-lookup"><span data-stu-id="56c6f-3252">bic code</span></span> 
- <span data-ttu-id="56c6f-3253">bic\#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3253">bic \#</span></span> 
- <span data-ttu-id="56c6f-3254">bic\#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3254">bic\#</span></span> 
- <span data-ttu-id="56c6f-3255">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="56c6f-3255">bank identifier code</span></span> 
- <span data-ttu-id="56c6f-3256">標準化9362</span><span class="sxs-lookup"><span data-stu-id="56c6f-3256">標準化9362</span></span> 
- <span data-ttu-id="56c6f-3257">迅速 #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3257">迅速＃</span></span> 
- <span data-ttu-id="56c6f-3258">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3258">SWIFTコード</span></span> 
- <span data-ttu-id="56c6f-3259">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3259">SWIFT番号</span></span> 
- <span data-ttu-id="56c6f-3260">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3260">迅速なルーティング番号</span></span> 
- <span data-ttu-id="56c6f-3261">BIC番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3261">BIC番号</span></span> 
- <span data-ttu-id="56c6f-3262">BICコード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3262">BICコード</span></span> 
- <span data-ttu-id="56c6f-3263">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="56c6f-3263">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="56c6f-3264">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="56c6f-3264">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="56c6f-3265">rapide\#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3265">rapide \#</span></span> 
- <span data-ttu-id="56c6f-3266">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="56c6f-3266">code SWIFT</span></span> 
- <span data-ttu-id="56c6f-3267">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="56c6f-3267">le numéro de swift</span></span> 
- <span data-ttu-id="56c6f-3268">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="56c6f-3268">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="56c6f-3269">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="56c6f-3269">le numéro BIC</span></span> 
- <span data-ttu-id="56c6f-3270">\#bic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3270">\# BIC</span></span> 
- <span data-ttu-id="56c6f-3271">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="56c6f-3271">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="56c6f-3272">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3272">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3273">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3273">Format</span></span>

<span data-ttu-id="56c6f-3274">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3274">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3275">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3275">Pattern</span></span>

<span data-ttu-id="56c6f-3276">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3276">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="56c6f-3277">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3277">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-3278">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="56c6f-3278">The digit "1" or "2"</span></span> 
- <span data-ttu-id="56c6f-3279">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3279">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3280">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3280">Checksum</span></span>

<span data-ttu-id="56c6f-3281">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3281">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3282">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3282">Definition</span></span>

<span data-ttu-id="56c6f-3283">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3283">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3284">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3284">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3285">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3285">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="56c6f-3286">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3286">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3287">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3287">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="56c6f-3288">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="56c6f-3288">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="56c6f-3289">身份證字號</span><span class="sxs-lookup"><span data-stu-id="56c6f-3289">身份證字號</span></span> 
- <span data-ttu-id="56c6f-3290">身份證</span><span class="sxs-lookup"><span data-stu-id="56c6f-3290">身份證</span></span> 
- <span data-ttu-id="56c6f-3291">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="56c6f-3291">身份證號碼</span></span> 
- <span data-ttu-id="56c6f-3292">身份證號</span><span class="sxs-lookup"><span data-stu-id="56c6f-3292">身份證號</span></span> 
- <span data-ttu-id="56c6f-3293">身分證字號</span><span class="sxs-lookup"><span data-stu-id="56c6f-3293">身分證字號</span></span> 
- <span data-ttu-id="56c6f-3294">身分證</span><span class="sxs-lookup"><span data-stu-id="56c6f-3294">身分證</span></span> 
- <span data-ttu-id="56c6f-3295">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="56c6f-3295">身分證號碼</span></span> 
- <span data-ttu-id="56c6f-3296">身份證號</span><span class="sxs-lookup"><span data-stu-id="56c6f-3296">身份證號</span></span> 
- <span data-ttu-id="56c6f-3297">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="56c6f-3297">身分證統一編號</span></span> 
- <span data-ttu-id="56c6f-3298">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="56c6f-3298">國民身分證統一編號</span></span> 
- <span data-ttu-id="56c6f-3299">簽名</span><span class="sxs-lookup"><span data-stu-id="56c6f-3299">簽名</span></span> 
- <span data-ttu-id="56c6f-3300">蓋章</span><span class="sxs-lookup"><span data-stu-id="56c6f-3300">蓋章</span></span> 
- <span data-ttu-id="56c6f-3301">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="56c6f-3301">簽名或蓋章</span></span> 
- <span data-ttu-id="56c6f-3302">簽章</span><span class="sxs-lookup"><span data-stu-id="56c6f-3302">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="56c6f-3303">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3303">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3304">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3304">Format</span></span>

- <span data-ttu-id="56c6f-3305">バイオメトリックパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3305">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="56c6f-3306">バイオメトリクスでないパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3306">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3307">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3307">Pattern</span></span>
<span data-ttu-id="56c6f-3308">バイオメトリックパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3308">Biometric passport number:</span></span>
- <span data-ttu-id="56c6f-3309">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="56c6f-3309">The digit "3"</span></span> 
- <span data-ttu-id="56c6f-3310">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3310">Eight digits</span></span>

<span data-ttu-id="56c6f-3311">バイオメトリクスではないパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3311">Non-biometric passport number:</span></span>
- <span data-ttu-id="56c6f-3312">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3312">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3313">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3313">Checksum</span></span>

<span data-ttu-id="56c6f-3314">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3314">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3315">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3315">Definition</span></span>

<span data-ttu-id="56c6f-3316">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3316">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3317">正規表現 Regex_taiwan_passport は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3317">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3318">Keyword_taiwan_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3318">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3319">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3319">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="56c6f-3320">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-3320">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="56c6f-3321">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3321">ROC passport number</span></span> 
- <span data-ttu-id="56c6f-3322">Passport number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3322">Passport number</span></span> 
- <span data-ttu-id="56c6f-3323">Passport no</span><span class="sxs-lookup"><span data-stu-id="56c6f-3323">Passport no</span></span> 
- <span data-ttu-id="56c6f-3324">Passport Num</span><span class="sxs-lookup"><span data-stu-id="56c6f-3324">Passport Num</span></span> 
- <span data-ttu-id="56c6f-3325">Passport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3325">Passport #</span></span> 
- <span data-ttu-id="56c6f-3326">护照</span><span class="sxs-lookup"><span data-stu-id="56c6f-3326">护照</span></span> 
- <span data-ttu-id="56c6f-3327">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="56c6f-3327">中華民國護照</span></span> 
- <span data-ttu-id="56c6f-3328">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="56c6f-3328">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="56c6f-3329">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3329">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3330">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3330">Format</span></span>

<span data-ttu-id="56c6f-3331">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3331">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3332">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3332">Pattern</span></span>

<span data-ttu-id="56c6f-3333">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3333">10 letters and digits:</span></span>
- <span data-ttu-id="56c6f-3334">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="56c6f-3334">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="56c6f-3335">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3335">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3336">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3336">Checksum</span></span>

<span data-ttu-id="56c6f-3337">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3337">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3338">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3338">Definition</span></span>

<span data-ttu-id="56c6f-3339">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3340">正規表現 Regex_taiwan_resident_certificate は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3340">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3341">Keyword_taiwan_resident_certificate からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3341">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3342">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3342">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="56c6f-3343">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="56c6f-3343">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="56c6f-3344">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="56c6f-3344">Resident Certificate</span></span> 
- <span data-ttu-id="56c6f-3345">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="56c6f-3345">Resident Cert</span></span> 
- <span data-ttu-id="56c6f-3346">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3346">Resident Cert.</span></span> 
- <span data-ttu-id="56c6f-3347">Identification card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3347">Identification card</span></span> 
- <span data-ttu-id="56c6f-3348">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="56c6f-3348">Alien Resident Certificate</span></span> 
- <span data-ttu-id="56c6f-3349">円弧</span><span class="sxs-lookup"><span data-stu-id="56c6f-3349">ARC</span></span> 
- <span data-ttu-id="56c6f-3350">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="56c6f-3350">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="56c6f-3351">tarc</span><span class="sxs-lookup"><span data-stu-id="56c6f-3351">TARC</span></span> 
- <span data-ttu-id="56c6f-3352">居留證</span><span class="sxs-lookup"><span data-stu-id="56c6f-3352">居留證</span></span> 
- <span data-ttu-id="56c6f-3353">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="56c6f-3353">外僑居留證</span></span> 
- <span data-ttu-id="56c6f-3354">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="56c6f-3354">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="56c6f-3355">タイ語の母集団識別コード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3355">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3356">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3356">Format</span></span>

<span data-ttu-id="56c6f-3357">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3357">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3358">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3358">Pattern</span></span>

<span data-ttu-id="56c6f-3359">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3359">13 digits:</span></span>
- <span data-ttu-id="56c6f-3360">最初の桁が0または9ではない</span><span class="sxs-lookup"><span data-stu-id="56c6f-3360">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="56c6f-3361">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3361">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3362">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3362">Checksum</span></span>

<span data-ttu-id="56c6f-3363">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3363">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3364">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3364">Definition</span></span>

<span data-ttu-id="56c6f-3365">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3365">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3366">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3366">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3367">Keyword_Thai_Citizen_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3367">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="56c6f-3368">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3368">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3369">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3369">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3370">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3370">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="56c6f-3371">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="56c6f-3371">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="56c6f-3372">ID Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3372">ID Number</span></span>
- <span data-ttu-id="56c6f-3373">識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3373">Identification Number</span></span>
- <span data-ttu-id="56c6f-3374">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="56c6f-3374">บัตรประชาชน</span></span>
- <span data-ttu-id="56c6f-3375">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="56c6f-3375">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="56c6f-3376">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="56c6f-3376">บัตรประชาชน</span></span>
- <span data-ttu-id="56c6f-3377">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="56c6f-3377">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="56c6f-3378">トルコの国の識別番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3378">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3379">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3379">Format</span></span>

<span data-ttu-id="56c6f-3380">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3380">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3381">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3381">Pattern</span></span>

<span data-ttu-id="56c6f-3382">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3382">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3383">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3383">Checksum</span></span>

<span data-ttu-id="56c6f-3384">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3384">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3385">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3385">Definition</span></span>

<span data-ttu-id="56c6f-3386">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3386">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3387">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3387">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3388">Keyword_Turkish_National_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3388">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="56c6f-3389">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3390">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3390">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3391">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3391">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="56c6f-3392">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="56c6f-3392">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="56c6f-3393">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="56c6f-3393">TC Kimlik No</span></span>
- <span data-ttu-id="56c6f-3394">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="56c6f-3394">TC Kimlik numarası</span></span>
- <span data-ttu-id="56c6f-3395">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="56c6f-3395">Vatandaşlık numarası</span></span>
- <span data-ttu-id="56c6f-3396">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="56c6f-3396">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="56c6f-p142">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-p142">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3399">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3399">Format</span></span>

<span data-ttu-id="56c6f-3400">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3400">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3401">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3401">Pattern</span></span>

<span data-ttu-id="56c6f-3402">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3402">18 letters and digits:</span></span>
- <span data-ttu-id="56c6f-3403">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3403">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="56c6f-3404">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3404">One digit</span></span> 
- <span data-ttu-id="56c6f-3405">誕生日を示す DDMMY という日付形式の 5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3405">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="56c6f-3406">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3406">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="56c6f-3407">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3407">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3408">Checksum</span></span>

<span data-ttu-id="56c6f-3409">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3409">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3410">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3410">Definition</span></span>

<span data-ttu-id="56c6f-3411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3412">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3412">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3413">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3413">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="56c6f-3414">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3414">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3415">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3415">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="56c6f-3416">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="56c6f-3416">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="56c6f-3417">dvla</span><span class="sxs-lookup"><span data-stu-id="56c6f-3417">DVLA</span></span> 
- <span data-ttu-id="56c6f-3418">light vans</span><span class="sxs-lookup"><span data-stu-id="56c6f-3418">light vans</span></span> 
- <span data-ttu-id="56c6f-3419">quadbikes</span><span class="sxs-lookup"><span data-stu-id="56c6f-3419">quadbikes</span></span> 
- <span data-ttu-id="56c6f-3420">motor cars</span><span class="sxs-lookup"><span data-stu-id="56c6f-3420">motor cars</span></span> 
- <span data-ttu-id="56c6f-3421">125cc</span><span class="sxs-lookup"><span data-stu-id="56c6f-3421">125cc</span></span> 
- <span data-ttu-id="56c6f-3422">sidecar</span><span class="sxs-lookup"><span data-stu-id="56c6f-3422">sidecar</span></span> 
- <span data-ttu-id="56c6f-3423">tricycles</span><span class="sxs-lookup"><span data-stu-id="56c6f-3423">tricycles</span></span> 
- <span data-ttu-id="56c6f-3424">motorcycles</span><span class="sxs-lookup"><span data-stu-id="56c6f-3424">motorcycles</span></span> 
- <span data-ttu-id="56c6f-3425">photocard licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-3425">photocard licence</span></span> 
- <span data-ttu-id="56c6f-3426">learner drivers</span><span class="sxs-lookup"><span data-stu-id="56c6f-3426">learner drivers</span></span> 
- <span data-ttu-id="56c6f-3427">licence holder</span><span class="sxs-lookup"><span data-stu-id="56c6f-3427">licence holder</span></span> 
- <span data-ttu-id="56c6f-3428">licence holders</span><span class="sxs-lookup"><span data-stu-id="56c6f-3428">licence holders</span></span> 
- <span data-ttu-id="56c6f-3429">driving licences</span><span class="sxs-lookup"><span data-stu-id="56c6f-3429">driving licences</span></span> 
- <span data-ttu-id="56c6f-3430">driving licence</span><span class="sxs-lookup"><span data-stu-id="56c6f-3430">driving licence</span></span> 
- <span data-ttu-id="56c6f-3431">dual control car</span><span class="sxs-lookup"><span data-stu-id="56c6f-3431">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="56c6f-p143">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-p143">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3434">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3434">Format</span></span>

<span data-ttu-id="56c6f-3435">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3435">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3436">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3436">Pattern</span></span>

<span data-ttu-id="56c6f-3437">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3437">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3438">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3438">Checksum</span></span>

<span data-ttu-id="56c6f-3439">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3439">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3440">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3440">Definition</span></span>

<span data-ttu-id="56c6f-3441">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3441">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3442">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3442">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3443">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3443">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3444">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3444">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="56c6f-3445">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="56c6f-3445">Keyword_uk_electoral</span></span>

- <span data-ttu-id="56c6f-3446">council nomination</span><span class="sxs-lookup"><span data-stu-id="56c6f-3446">council nomination</span></span> 
- <span data-ttu-id="56c6f-3447">nomination form</span><span class="sxs-lookup"><span data-stu-id="56c6f-3447">nomination form</span></span> 
- <span data-ttu-id="56c6f-3448">electoral register</span><span class="sxs-lookup"><span data-stu-id="56c6f-3448">electoral register</span></span> 
- <span data-ttu-id="56c6f-3449">electoral roll</span><span class="sxs-lookup"><span data-stu-id="56c6f-3449">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="56c6f-p144">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-p144">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3452">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3452">Format</span></span>

<span data-ttu-id="56c6f-3453">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3453">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3454">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3454">Pattern</span></span>

<span data-ttu-id="56c6f-3455">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3455">10-17 digits:</span></span>
- <span data-ttu-id="56c6f-3456">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3456">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="56c6f-3457">スペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-3457">A space</span></span> 
- <span data-ttu-id="56c6f-3458">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3458">Three digits</span></span> 
- <span data-ttu-id="56c6f-3459">スペース</span><span class="sxs-lookup"><span data-stu-id="56c6f-3459">A space</span></span> 
- <span data-ttu-id="56c6f-3460">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3460">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3461">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3461">Checksum</span></span>

<span data-ttu-id="56c6f-3462">はい</span><span class="sxs-lookup"><span data-stu-id="56c6f-3462">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3463">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3463">Definition</span></span>

<span data-ttu-id="56c6f-3464">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3464">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3465">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3465">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3466">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3466">One of the following is true:</span></span>
    - <span data-ttu-id="56c6f-3467">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3467">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="56c6f-3468">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3468">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="56c6f-3469">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3469">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="56c6f-3470">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3470">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3471">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3471">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="56c6f-3472">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3472">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="56c6f-3473">national health service</span><span class="sxs-lookup"><span data-stu-id="56c6f-3473">national health service</span></span> 
- <span data-ttu-id="56c6f-3474">nhs</span><span class="sxs-lookup"><span data-stu-id="56c6f-3474">nhs</span></span> 
- <span data-ttu-id="56c6f-3475">health services authority</span><span class="sxs-lookup"><span data-stu-id="56c6f-3475">health services authority</span></span> 
- <span data-ttu-id="56c6f-3476">health authority</span><span class="sxs-lookup"><span data-stu-id="56c6f-3476">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="56c6f-3477">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="56c6f-3477">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="56c6f-3478">patient id</span><span class="sxs-lookup"><span data-stu-id="56c6f-3478">patient id</span></span> 
- <span data-ttu-id="56c6f-3479">patient identification</span><span class="sxs-lookup"><span data-stu-id="56c6f-3479">patient identification</span></span> 
- <span data-ttu-id="56c6f-3480">patient no</span><span class="sxs-lookup"><span data-stu-id="56c6f-3480">patient no</span></span> 
- <span data-ttu-id="56c6f-3481">patient number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3481">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="56c6f-3482">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="56c6f-3482">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="56c6f-3483">GP</span><span class="sxs-lookup"><span data-stu-id="56c6f-3483">GP</span></span> 
- <span data-ttu-id="56c6f-3484">dob</span><span class="sxs-lookup"><span data-stu-id="56c6f-3484">DOB</span></span> 
- <span data-ttu-id="56c6f-3485">D.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3485">D.O.B</span></span> 
- <span data-ttu-id="56c6f-3486">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="56c6f-3486">Date of Birth</span></span> 
- <span data-ttu-id="56c6f-3487">Birth Date</span><span class="sxs-lookup"><span data-stu-id="56c6f-3487">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="56c6f-p145">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="56c6f-p145">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3490">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3490">Format</span></span>

<span data-ttu-id="56c6f-3491">スペースまたはダッシュで区切られた7文字または9文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3491">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3492">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3492">Pattern</span></span>

<span data-ttu-id="56c6f-3493">次の2つのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3493">Two possible patterns:</span></span>

- <span data-ttu-id="56c6f-3494">2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3494">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="56c6f-3495">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3495">Six digits</span></span>
- <span data-ttu-id="56c6f-3496">「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3496">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="56c6f-3497">OR</span><span class="sxs-lookup"><span data-stu-id="56c6f-3497">OR</span></span>

- <span data-ttu-id="56c6f-3498">2文字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3498">Two letters</span></span>
- <span data-ttu-id="56c6f-3499">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3499">A space or dash</span></span>
- <span data-ttu-id="56c6f-3500">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3500">Two digits</span></span>
- <span data-ttu-id="56c6f-3501">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3501">A space or dash</span></span>
- <span data-ttu-id="56c6f-3502">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3502">Two digits</span></span>
- <span data-ttu-id="56c6f-3503">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3503">A space or dash</span></span>
- <span data-ttu-id="56c6f-3504">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3504">Two digits</span></span>
- <span data-ttu-id="56c6f-3505">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3505">A space or dash</span></span>
- <span data-ttu-id="56c6f-3506">' A '、' B '、' C '、または ' d ' のどちらか</span><span class="sxs-lookup"><span data-stu-id="56c6f-3506">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3507">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3507">Checksum</span></span>

<span data-ttu-id="56c6f-3508">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3508">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3509">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3509">Definition</span></span>

<span data-ttu-id="56c6f-3510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3510">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3511">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3511">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3512">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3512">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="56c6f-3513">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3513">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3514">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3514">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3515">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3515">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3516">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3516">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="56c6f-3517">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="56c6f-3517">Keyword_uk_nino</span></span>

- <span data-ttu-id="56c6f-3518">national insurance number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3518">national insurance number</span></span> 
- <span data-ttu-id="56c6f-3519">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="56c6f-3519">national insurance contributions</span></span> 
- <span data-ttu-id="56c6f-3520">protection act</span><span class="sxs-lookup"><span data-stu-id="56c6f-3520">protection act</span></span> 
- <span data-ttu-id="56c6f-3521">金</span><span class="sxs-lookup"><span data-stu-id="56c6f-3521">insurance</span></span> 
- <span data-ttu-id="56c6f-3522">social security number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3522">social security number</span></span> 
- <span data-ttu-id="56c6f-3523">insurance application</span><span class="sxs-lookup"><span data-stu-id="56c6f-3523">insurance application</span></span> 
- <span data-ttu-id="56c6f-3524">medical application</span><span class="sxs-lookup"><span data-stu-id="56c6f-3524">medical application</span></span> 
- <span data-ttu-id="56c6f-3525">social insurance</span><span class="sxs-lookup"><span data-stu-id="56c6f-3525">social insurance</span></span> 
- <span data-ttu-id="56c6f-3526">medical attention</span><span class="sxs-lookup"><span data-stu-id="56c6f-3526">medical attention</span></span> 
- <span data-ttu-id="56c6f-3527">social security</span><span class="sxs-lookup"><span data-stu-id="56c6f-3527">social security</span></span> 
- <span data-ttu-id="56c6f-3528">great britain</span><span class="sxs-lookup"><span data-stu-id="56c6f-3528">great britain</span></span> 
- <span data-ttu-id="56c6f-3529">金</span><span class="sxs-lookup"><span data-stu-id="56c6f-3529">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="56c6f-p146">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-p146">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3532">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3532">Format</span></span>

<span data-ttu-id="56c6f-3533">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3534">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3534">Pattern</span></span>

<span data-ttu-id="56c6f-3535">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3536">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3536">Checksum</span></span>

<span data-ttu-id="56c6f-3537">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3537">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3538">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3538">Definition</span></span>

<span data-ttu-id="56c6f-3539">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3540">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3540">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3541">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3541">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3542">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3542">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="56c6f-3543">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="56c6f-3543">Keyword_passport</span></span>

- <span data-ttu-id="56c6f-3544">Passport Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3544">Passport Number</span></span> 
- <span data-ttu-id="56c6f-3545">Passport No</span><span class="sxs-lookup"><span data-stu-id="56c6f-3545">Passport No</span></span> 
- <span data-ttu-id="56c6f-3546">Passport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3546">Passport #</span></span> 
- <span data-ttu-id="56c6f-3547">サインアウト</span><span class="sxs-lookup"><span data-stu-id="56c6f-3547">Passport#</span></span> 
- <span data-ttu-id="56c6f-3548">PassportID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3548">PassportID</span></span> 
- <span data-ttu-id="56c6f-3549">Passportno</span><span class="sxs-lookup"><span data-stu-id="56c6f-3549">Passportno</span></span> 
- <span data-ttu-id="56c6f-3550">passportnumber</span><span class="sxs-lookup"><span data-stu-id="56c6f-3550">passportnumber</span></span> 
- <span data-ttu-id="56c6f-3551">パスポート</span><span class="sxs-lookup"><span data-stu-id="56c6f-3551">パスポート</span></span> 
- <span data-ttu-id="56c6f-3552">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3552">パスポート番号</span></span> 
- <span data-ttu-id="56c6f-3553">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="56c6f-3553">パスポートのNum</span></span> 
- <span data-ttu-id="56c6f-3554">パスポート #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3554">パスポート＃</span></span> 
- <span data-ttu-id="56c6f-3555">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="56c6f-3555">Numéro de passeport</span></span> 
- <span data-ttu-id="56c6f-3556">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="56c6f-3556">Passeport n °</span></span> 
- <span data-ttu-id="56c6f-3557">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="56c6f-3557">Passeport Non</span></span> 
- <span data-ttu-id="56c6f-3558">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3558">Passeport #</span></span> 
- <span data-ttu-id="56c6f-3559">Passeport #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3559">Passeport#</span></span> 
- <span data-ttu-id="56c6f-3560">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="56c6f-3560">PasseportNon</span></span> 
- <span data-ttu-id="56c6f-3561">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="56c6f-3561">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="56c6f-3562">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3562">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3563">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3563">Format</span></span>

<span data-ttu-id="56c6f-3564">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3564">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3565">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3565">Pattern</span></span>

<span data-ttu-id="56c6f-3566">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3566">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3567">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3567">Checksum</span></span>

<span data-ttu-id="56c6f-3568">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3568">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3569">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3569">Definition</span></span>

<span data-ttu-id="56c6f-3570">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3571">正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3571">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3572">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3572">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="56c6f-3573">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3573">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="56c6f-3574">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-3574">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="56c6f-3575">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3575">Checking Account Number</span></span> 
- <span data-ttu-id="56c6f-3576">Checking Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-3576">Checking Account</span></span> 
- <span data-ttu-id="56c6f-3577">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3577">Checking Account #</span></span> 
- <span data-ttu-id="56c6f-3578">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3578">Checking Acct Number</span></span> 
- <span data-ttu-id="56c6f-3579">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3579">Checking Acct #</span></span> 
- <span data-ttu-id="56c6f-3580">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3580">Checking Acct No.</span></span> 
- <span data-ttu-id="56c6f-3581">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3581">Checking Account No.</span></span> 
- <span data-ttu-id="56c6f-3582">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3582">Bank Account Number</span></span> 
- <span data-ttu-id="56c6f-3583">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3583">Bank Account #</span></span> 
- <span data-ttu-id="56c6f-3584">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3584">Bank Acct Number</span></span> 
- <span data-ttu-id="56c6f-3585">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3585">Bank Acct #</span></span> 
- <span data-ttu-id="56c6f-3586">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3586">Bank Acct No.</span></span> 
- <span data-ttu-id="56c6f-3587">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3587">Bank Account No.</span></span> 
- <span data-ttu-id="56c6f-3588">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3588">Savings Account Number</span></span> 
- <span data-ttu-id="56c6f-3589">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3589">Savings Account.</span></span> 
- <span data-ttu-id="56c6f-3590">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3590">Savings Account #</span></span> 
- <span data-ttu-id="56c6f-3591">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3591">Savings Acct Number</span></span> 
- <span data-ttu-id="56c6f-3592">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3592">Savings Acct #</span></span> 
- <span data-ttu-id="56c6f-3593">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3593">Savings Acct No.</span></span> 
- <span data-ttu-id="56c6f-3594">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3594">Savings Account No.</span></span> 
- <span data-ttu-id="56c6f-3595">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3595">Debit Account Number</span></span> 
- <span data-ttu-id="56c6f-3596">Debit Account</span><span class="sxs-lookup"><span data-stu-id="56c6f-3596">Debit Account</span></span> 
- <span data-ttu-id="56c6f-3597">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3597">Debit Account #</span></span> 
- <span data-ttu-id="56c6f-3598">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3598">Debit Acct Number</span></span> 
- <span data-ttu-id="56c6f-3599">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3599">Debit Acct #</span></span> 
- <span data-ttu-id="56c6f-3600">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3600">Debit Acct No.</span></span> 
- <span data-ttu-id="56c6f-3601">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="56c6f-3601">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="56c6f-3602">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3602">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3603">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3603">Format</span></span>

<span data-ttu-id="56c6f-3604">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="56c6f-3604">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3605">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3605">Pattern</span></span>

<span data-ttu-id="56c6f-3606">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3606">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="56c6f-3607">ddd ddd ddd のような形式の9桁の数字は一致します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3607">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="56c6f-3608">ddddddddd のように9桁の数字は一致しません。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3608">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3609">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3609">Checksum</span></span>

<span data-ttu-id="56c6f-3610">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3610">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3611">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3611">Definition</span></span>

<span data-ttu-id="56c6f-3612">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3612">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3613">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3613">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3614">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3614">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="56c6f-3615">Keyword_us_drivers_license からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3615">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="56c6f-3616">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3616">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3617">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3617">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3618">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3618">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="56c6f-3619">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3619">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="56c6f-3620">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3620">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3621">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3621">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="56c6f-3622">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="56c6f-3622">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="56c6f-3623">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-3623">DL</span></span> 
- <span data-ttu-id="56c6f-3624">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-3624">DLS</span></span> 
- <span data-ttu-id="56c6f-3625">CDL</span><span class="sxs-lookup"><span data-stu-id="56c6f-3625">CDL</span></span> 
- <span data-ttu-id="56c6f-3626">cdls</span><span class="sxs-lookup"><span data-stu-id="56c6f-3626">CDLS</span></span> 
- <span data-ttu-id="56c6f-3627">ID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3627">ID</span></span> 
- <span data-ttu-id="56c6f-3628">rid</span><span class="sxs-lookup"><span data-stu-id="56c6f-3628">IDs</span></span> 
- <span data-ttu-id="56c6f-3629">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-3629">DL#</span></span> 
- <span data-ttu-id="56c6f-3630">dl</span><span class="sxs-lookup"><span data-stu-id="56c6f-3630">DLS#</span></span> 
- <span data-ttu-id="56c6f-3631">CDL</span><span class="sxs-lookup"><span data-stu-id="56c6f-3631">CDL#</span></span> 
- <span data-ttu-id="56c6f-3632">cdls #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3632">CDLS#</span></span> 
- <span data-ttu-id="56c6f-3633">rid</span><span class="sxs-lookup"><span data-stu-id="56c6f-3633">ID#</span></span>
- <span data-ttu-id="56c6f-3634">rid</span><span class="sxs-lookup"><span data-stu-id="56c6f-3634">IDs#</span></span> 
- <span data-ttu-id="56c6f-3635">ID number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3635">ID number</span></span> 
- <span data-ttu-id="56c6f-3636">ID numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-3636">ID numbers</span></span> 
- <span data-ttu-id="56c6f-3637">そして</span><span class="sxs-lookup"><span data-stu-id="56c6f-3637">LIC</span></span> 
- <span data-ttu-id="56c6f-3638">そして</span><span class="sxs-lookup"><span data-stu-id="56c6f-3638">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="56c6f-3639">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="56c6f-3639">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="56c6f-3640">driverlic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3640">DriverLic</span></span> 
- <span data-ttu-id="56c6f-3641">driverlics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3641">DriverLics</span></span> 
- <span data-ttu-id="56c6f-3642">driverlicense</span><span class="sxs-lookup"><span data-stu-id="56c6f-3642">DriverLicense</span></span> 
- <span data-ttu-id="56c6f-3643">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-3643">DriverLicenses</span></span> 
- <span data-ttu-id="56c6f-3644">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3644">Driver Lic</span></span> 
- <span data-ttu-id="56c6f-3645">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3645">Driver Lics</span></span> 
- <span data-ttu-id="56c6f-3646">Driver License</span><span class="sxs-lookup"><span data-stu-id="56c6f-3646">Driver License</span></span> 
- <span data-ttu-id="56c6f-3647">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-3647">Driver Licenses</span></span> 
- <span data-ttu-id="56c6f-3648">driverslic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3648">DriversLic</span></span> 
- <span data-ttu-id="56c6f-3649">driverslics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3649">DriversLics</span></span> 
- <span data-ttu-id="56c6f-3650">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="56c6f-3650">DriversLicense</span></span> 
- <span data-ttu-id="56c6f-3651">このライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-3651">DriversLicenses</span></span> 
- <span data-ttu-id="56c6f-3652">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3652">Drivers Lic</span></span> 
- <span data-ttu-id="56c6f-3653">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3653">Drivers Lics</span></span> 
- <span data-ttu-id="56c6f-3654">Drivers License</span><span class="sxs-lookup"><span data-stu-id="56c6f-3654">Drivers License</span></span> 
- <span data-ttu-id="56c6f-3655">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-3655">Drivers Licenses</span></span> 
- <span data-ttu-id="56c6f-3656">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3656">Driver'Lic</span></span> 
- <span data-ttu-id="56c6f-3657">driver' lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3657">Driver'Lics</span></span> 
- <span data-ttu-id="56c6f-3658">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-3658">Driver'License</span></span> 
- <span data-ttu-id="56c6f-3659">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-3659">Driver'Licenses</span></span> 
- <span data-ttu-id="56c6f-3660">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3660">Driver' Lic</span></span> 
- <span data-ttu-id="56c6f-3661">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3661">Driver' Lics</span></span> 
- <span data-ttu-id="56c6f-3662">Driver' License</span><span class="sxs-lookup"><span data-stu-id="56c6f-3662">Driver' License</span></span> 
- <span data-ttu-id="56c6f-3663">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-3663">Driver' Licenses</span></span>
- <span data-ttu-id="56c6f-3664">driver' slic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3664">Driver'sLic</span></span> 
- <span data-ttu-id="56c6f-3665">driver' slics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3665">Driver'sLics</span></span> 
- <span data-ttu-id="56c6f-3666">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-3666">Driver'sLicense</span></span> 
- <span data-ttu-id="56c6f-3667">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="56c6f-3667">Driver'sLicenses</span></span> 
- <span data-ttu-id="56c6f-3668">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="56c6f-3668">Driver's Lic</span></span> 
- <span data-ttu-id="56c6f-3669">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="56c6f-3669">Driver's Lics</span></span> 
- <span data-ttu-id="56c6f-3670">Driver's License</span><span class="sxs-lookup"><span data-stu-id="56c6f-3670">Driver's License</span></span> 
- <span data-ttu-id="56c6f-3671">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="56c6f-3671">Driver's Licenses</span></span> 
- <span data-ttu-id="56c6f-3672">identification number</span><span class="sxs-lookup"><span data-stu-id="56c6f-3672">identification number</span></span> 
- <span data-ttu-id="56c6f-3673">identification numbers</span><span class="sxs-lookup"><span data-stu-id="56c6f-3673">identification numbers</span></span> 
- <span data-ttu-id="56c6f-3674">identification #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3674">identification #</span></span> 
- <span data-ttu-id="56c6f-3675">id card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3675">id card</span></span> 
- <span data-ttu-id="56c6f-3676">id cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-3676">id cards</span></span> 
- <span data-ttu-id="56c6f-3677">identification card</span><span class="sxs-lookup"><span data-stu-id="56c6f-3677">identification card</span></span> 
- <span data-ttu-id="56c6f-3678">identification cards</span><span class="sxs-lookup"><span data-stu-id="56c6f-3678">identification cards</span></span> 
- <span data-ttu-id="56c6f-3679">driverlic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3679">DriverLic#</span></span> 
- <span data-ttu-id="56c6f-3680">driverlics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3680">DriverLics#</span></span> 
- <span data-ttu-id="56c6f-3681">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3681">DriverLicense#</span></span> 
- <span data-ttu-id="56c6f-3682">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3682">DriverLicenses#</span></span> 
- <span data-ttu-id="56c6f-3683">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3683">Driver Lic#</span></span> 
- <span data-ttu-id="56c6f-3684">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3684">Driver Lics#</span></span> 
- <span data-ttu-id="56c6f-3685">Driver License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3685">Driver License#</span></span> 
- <span data-ttu-id="56c6f-3686">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3686">Driver Licenses#</span></span> 
- <span data-ttu-id="56c6f-3687">driverslic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3687">DriversLic#</span></span> 
- <span data-ttu-id="56c6f-3688">driverslics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3688">DriversLics#</span></span> 
- <span data-ttu-id="56c6f-3689">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3689">DriversLicense#</span></span> 
- <span data-ttu-id="56c6f-3690">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3690">DriversLicenses#</span></span> 
- <span data-ttu-id="56c6f-3691">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3691">Drivers Lic#</span></span> 
- <span data-ttu-id="56c6f-3692">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3692">Drivers Lics#</span></span> 
- <span data-ttu-id="56c6f-3693">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3693">Drivers License#</span></span> 
- <span data-ttu-id="56c6f-3694">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3694">Drivers Licenses#</span></span> 
- <span data-ttu-id="56c6f-3695">driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3695">Driver'Lic#</span></span> 
- <span data-ttu-id="56c6f-3696">driver' lics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3696">Driver'Lics#</span></span> 
- <span data-ttu-id="56c6f-3697">driver' License #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3697">Driver'License#</span></span> 
- <span data-ttu-id="56c6f-3698">driver' Licenses #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3698">Driver'Licenses#</span></span> 
- <span data-ttu-id="56c6f-3699">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3699">Driver' Lic#</span></span> 
- <span data-ttu-id="56c6f-3700">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3700">Driver' Lics#</span></span> 
- <span data-ttu-id="56c6f-3701">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3701">Driver' License#</span></span> 
- <span data-ttu-id="56c6f-3702">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3702">Driver' Licenses#</span></span> 
- <span data-ttu-id="56c6f-3703">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3703">Driver'sLic#</span></span> 
- <span data-ttu-id="56c6f-3704">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3704">Driver'sLics#</span></span> 
- <span data-ttu-id="56c6f-3705">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="56c6f-3705">Driver'sLicense#</span></span> 
- <span data-ttu-id="56c6f-3706">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="56c6f-3706">Driver'sLicenses#</span></span> 
- <span data-ttu-id="56c6f-3707">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3707">Driver's Lic#</span></span> 
- <span data-ttu-id="56c6f-3708">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3708">Driver's Lics#</span></span> 
- <span data-ttu-id="56c6f-3709">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3709">Driver's License#</span></span> 
- <span data-ttu-id="56c6f-3710">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3710">Driver's Licenses#</span></span> 
- <span data-ttu-id="56c6f-3711">id card#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3711">id card#</span></span> 
- <span data-ttu-id="56c6f-3712">id cards#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3712">id cards#</span></span> 
- <span data-ttu-id="56c6f-3713">identification card#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3713">identification card#</span></span> 
- <span data-ttu-id="56c6f-3714">identification cards#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3714">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="56c6f-3715">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="56c6f-3715">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="56c6f-3716">州の略号 (たとえば、"NY")</span><span class="sxs-lookup"><span data-stu-id="56c6f-3716">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="56c6f-3717">州の名前 (たとえば、"New York")</span><span class="sxs-lookup"><span data-stu-id="56c6f-3717">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="56c6f-3718">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3718">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3719">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3719">Format</span></span>

<span data-ttu-id="56c6f-3720">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="56c6f-3720">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3721">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3721">Pattern</span></span>

<span data-ttu-id="56c6f-3722">さ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3722">Formatted:</span></span>
- <span data-ttu-id="56c6f-3723">数字「9」</span><span class="sxs-lookup"><span data-stu-id="56c6f-3723">The digit "9"</span></span> 
- <span data-ttu-id="56c6f-3724">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3724">Two digits</span></span> 
- <span data-ttu-id="56c6f-3725">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3725">A space or dash</span></span> 
- <span data-ttu-id="56c6f-3726">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="56c6f-3726">A "7" or "8"</span></span> 
- <span data-ttu-id="56c6f-3727">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3727">A digit</span></span> 
- <span data-ttu-id="56c6f-3728">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3728">A space, or dash</span></span> 
- <span data-ttu-id="56c6f-3729">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3729">Four digits</span></span>

<span data-ttu-id="56c6f-3730">なし</span><span class="sxs-lookup"><span data-stu-id="56c6f-3730">Unformatted:</span></span>
- <span data-ttu-id="56c6f-3731">数字「9」</span><span class="sxs-lookup"><span data-stu-id="56c6f-3731">The digit "9"</span></span> 
- <span data-ttu-id="56c6f-3732">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3732">Two digits</span></span> 
- <span data-ttu-id="56c6f-3733">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="56c6f-3733">A "7" or "8"</span></span> 
- <span data-ttu-id="56c6f-3734">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3734">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3735">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3735">Checksum</span></span>

<span data-ttu-id="56c6f-3736">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3736">No</span></span>

### <a name="definition"></a><span data-ttu-id="56c6f-3737">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3737">Definition</span></span>

<span data-ttu-id="56c6f-3738">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3738">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3739">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3739">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3740">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3740">At least one of the following is true:</span></span>
    - <span data-ttu-id="56c6f-3741">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3741">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="56c6f-3742">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3742">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="56c6f-3743">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3743">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="56c6f-3744">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3744">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="56c6f-3745">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3745">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3746">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3746">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3747">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="56c6f-3747">At least one of the following is true:</span></span>
    - <span data-ttu-id="56c6f-3748">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3748">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="56c6f-3749">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3749">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="56c6f-3750">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3750">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3751">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3751">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="56c6f-3752">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="56c6f-3752">Keyword_itin</span></span>

- <span data-ttu-id="56c6f-3753">納税</span><span class="sxs-lookup"><span data-stu-id="56c6f-3753">taxpayer</span></span> 
- <span data-ttu-id="56c6f-3754">tax id</span><span class="sxs-lookup"><span data-stu-id="56c6f-3754">tax id</span></span> 
- <span data-ttu-id="56c6f-3755">tax identification</span><span class="sxs-lookup"><span data-stu-id="56c6f-3755">tax identification</span></span> 
- <span data-ttu-id="56c6f-3756">itin</span><span class="sxs-lookup"><span data-stu-id="56c6f-3756">itin</span></span> 
- <span data-ttu-id="56c6f-3757">ssn</span><span class="sxs-lookup"><span data-stu-id="56c6f-3757">ssn</span></span> 
- <span data-ttu-id="56c6f-3758">は</span><span class="sxs-lookup"><span data-stu-id="56c6f-3758">tin</span></span> 
- <span data-ttu-id="56c6f-3759">social security</span><span class="sxs-lookup"><span data-stu-id="56c6f-3759">social security</span></span> 
- <span data-ttu-id="56c6f-3760">tax payer</span><span class="sxs-lookup"><span data-stu-id="56c6f-3760">tax payer</span></span> 
- <span data-ttu-id="56c6f-3761">itins</span><span class="sxs-lookup"><span data-stu-id="56c6f-3761">itins</span></span> 
- <span data-ttu-id="56c6f-3762">taxid</span><span class="sxs-lookup"><span data-stu-id="56c6f-3762">taxid</span></span> 
- <span data-ttu-id="56c6f-3763">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="56c6f-3763">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="56c6f-3764">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="56c6f-3764">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="56c6f-3765">License</span><span class="sxs-lookup"><span data-stu-id="56c6f-3765">License</span></span> 
- <span data-ttu-id="56c6f-3766">DL</span><span class="sxs-lookup"><span data-stu-id="56c6f-3766">DL</span></span> 
- <span data-ttu-id="56c6f-3767">dob</span><span class="sxs-lookup"><span data-stu-id="56c6f-3767">DOB</span></span> 
- <span data-ttu-id="56c6f-3768">誕生日</span><span class="sxs-lookup"><span data-stu-id="56c6f-3768">Birthdate</span></span> 
- <span data-ttu-id="56c6f-3769">Birthday</span><span class="sxs-lookup"><span data-stu-id="56c6f-3769">Birthday</span></span> 
- <span data-ttu-id="56c6f-3770">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="56c6f-3770">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="56c6f-3771">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="56c6f-3771">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="56c6f-3772">Format</span><span class="sxs-lookup"><span data-stu-id="56c6f-3772">Format</span></span>

<span data-ttu-id="56c6f-3773">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="56c6f-3773">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="56c6f-3774">2011より前に発行された場合、SSN の書式には、特定の範囲内にある特定の範囲内にある必要があり、チェックサムがないという厳密な形式があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3774">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="56c6f-3775">パターン</span><span class="sxs-lookup"><span data-stu-id="56c6f-3775">Pattern</span></span>

<span data-ttu-id="56c6f-3776">次の4つの異なるパターンで ssns を検索する4つの関数があります。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3776">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="56c6f-3777">Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3777">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="56c6f-3778">Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3778">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="56c6f-3779">Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3779">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="56c6f-3780">Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3780">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="56c6f-3781">チェックサム</span><span class="sxs-lookup"><span data-stu-id="56c6f-3781">Checksum</span></span>

<span data-ttu-id="56c6f-3782">いいえ</span><span class="sxs-lookup"><span data-stu-id="56c6f-3782">No</span></span>


### <a name="definition"></a><span data-ttu-id="56c6f-3783">定義</span><span class="sxs-lookup"><span data-stu-id="56c6f-3783">Definition</span></span>

<span data-ttu-id="56c6f-3784">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3785">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3785">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3786">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3786">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="56c6f-3787">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3787">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3788">関数 Func_unformatted_ssn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3788">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3789">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3789">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="56c6f-3790">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3790">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3791">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3791">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3792">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3792">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="56c6f-3793">関数 Func_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3793">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="56c6f-3794">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3794">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="56c6f-3795">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3795">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="56c6f-3796">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3796">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="56c6f-3797">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="56c6f-3797">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="56c6f-3798">キーワード</span><span class="sxs-lookup"><span data-stu-id="56c6f-3798">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="56c6f-3799">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="56c6f-3799">Keyword_ssn</span></span>

- <span data-ttu-id="56c6f-3800">Social Security</span><span class="sxs-lookup"><span data-stu-id="56c6f-3800">Social Security</span></span> 
- <span data-ttu-id="56c6f-3801">Social Security#</span><span class="sxs-lookup"><span data-stu-id="56c6f-3801">Social Security#</span></span> 
- <span data-ttu-id="56c6f-3802">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="56c6f-3802">Soc Sec</span></span> 
- <span data-ttu-id="56c6f-3803">SSN</span><span class="sxs-lookup"><span data-stu-id="56c6f-3803">SSN</span></span> 
- <span data-ttu-id="56c6f-3804">ssn</span><span class="sxs-lookup"><span data-stu-id="56c6f-3804">SSNS</span></span> 
- <span data-ttu-id="56c6f-3805">SSN</span><span class="sxs-lookup"><span data-stu-id="56c6f-3805">SSN#</span></span> 
- <span data-ttu-id="56c6f-3806">秒</span><span class="sxs-lookup"><span data-stu-id="56c6f-3806">SS#</span></span> 
- <span data-ttu-id="56c6f-3807">SSID</span><span class="sxs-lookup"><span data-stu-id="56c6f-3807">SSID</span></span> 
   

