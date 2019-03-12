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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できる状態で、80の機密情報の種類が含まれています。 このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。
ms.openlocfilehash: e9811b285e98a791570dc91e275cb5cead4f8bc9
ms.sourcegitcommit: 6e8e2b43a4bea31c1e835c5b050824651c6a0094
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30537644"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="6657e-104">機密情報の種類の検索基準：</span><span class="sxs-lookup"><span data-stu-id="6657e-104">What the sensitive information types look for</span></span>

<span data-ttu-id="6657e-105">Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6657e-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="6657e-106">このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="6657e-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="6657e-107">機密情報の種類はパターンで定義され、正規表現または関数で識別できます。</span><span class="sxs-lookup"><span data-stu-id="6657e-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="6657e-108">機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="6657e-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="6657e-109">信頼レベルと近接も、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="6657e-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="6657e-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="6657e-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-111">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-111">Format</span></span>

<span data-ttu-id="6657e-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-113">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-113">Pattern</span></span>

<span data-ttu-id="6657e-114">さ</span><span class="sxs-lookup"><span data-stu-id="6657e-114">Formatted:</span></span>
- <span data-ttu-id="6657e-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="6657e-116">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-116">A hyphen</span></span>
- <span data-ttu-id="6657e-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-117">Four digits</span></span>
- <span data-ttu-id="6657e-118">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-118">A hyphen</span></span>
- <span data-ttu-id="6657e-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-119">A digit</span></span>

<span data-ttu-id="6657e-120">書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字</span><span class="sxs-lookup"><span data-stu-id="6657e-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="6657e-121">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-121">Checksum</span></span>

<span data-ttu-id="6657e-122">無</span><span class="sxs-lookup"><span data-stu-id="6657e-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-123">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-123">Definition</span></span>

<span data-ttu-id="6657e-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="6657e-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="6657e-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="6657e-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="6657e-129">aba</span><span class="sxs-lookup"><span data-stu-id="6657e-129">aba</span></span>
- <span data-ttu-id="6657e-130">aba #</span><span class="sxs-lookup"><span data-stu-id="6657e-130">aba #</span></span>
- <span data-ttu-id="6657e-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="6657e-131">aba routing #</span></span>
- <span data-ttu-id="6657e-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="6657e-132">aba routing number</span></span>
- <span data-ttu-id="6657e-133">aba</span><span class="sxs-lookup"><span data-stu-id="6657e-133">aba#</span></span>
- <span data-ttu-id="6657e-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="6657e-134">abarouting#</span></span>
- <span data-ttu-id="6657e-135">aba number</span><span class="sxs-lookup"><span data-stu-id="6657e-135">aba number</span></span>
- <span data-ttu-id="6657e-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-136">abaroutingnumber</span></span>
- <span data-ttu-id="6657e-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="6657e-137">american bank association routing #</span></span>
- <span data-ttu-id="6657e-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="6657e-138">american bank association routing number</span></span>
- <span data-ttu-id="6657e-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="6657e-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="6657e-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="6657e-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="6657e-141">bank routing number</span></span>
- <span data-ttu-id="6657e-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="6657e-142">bankrouting#</span></span>
- <span data-ttu-id="6657e-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-143">bankroutingnumber</span></span>
- <span data-ttu-id="6657e-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="6657e-144">routing transit number</span></span>
- <span data-ttu-id="6657e-145">rtn</span><span class="sxs-lookup"><span data-stu-id="6657e-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="6657e-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-147">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-147">Format</span></span>

<span data-ttu-id="6657e-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-149">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-149">Pattern</span></span>

<span data-ttu-id="6657e-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-150">Eight digits:</span></span>
- <span data-ttu-id="6657e-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-151">Two digits</span></span>
- <span data-ttu-id="6657e-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-152">A period</span></span>
- <span data-ttu-id="6657e-153">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-153">Three digits</span></span>
- <span data-ttu-id="6657e-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-154">A period</span></span>
- <span data-ttu-id="6657e-155">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-156">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-156">Checksum</span></span>

<span data-ttu-id="6657e-157">無</span><span class="sxs-lookup"><span data-stu-id="6657e-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-158">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-158">Definition</span></span>

<span data-ttu-id="6657e-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-160">正規表現 Regex_argentina_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-161">Keyword_argentina_national_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="6657e-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="6657e-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="6657e-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="6657e-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="6657e-165">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-165">Identity</span></span> 
- <span data-ttu-id="6657e-166">識別国の id カード</span><span class="sxs-lookup"><span data-stu-id="6657e-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="6657e-167">DNI</span><span class="sxs-lookup"><span data-stu-id="6657e-167">DNI</span></span> 
- <span data-ttu-id="6657e-168">個人の NIC National レジストリ</span><span class="sxs-lookup"><span data-stu-id="6657e-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="6657e-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="6657e-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="6657e-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="6657e-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="6657e-171">dad の識別子</span><span class="sxs-lookup"><span data-stu-id="6657e-171">Identidad</span></span> 
- <span data-ttu-id="6657e-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="6657e-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="6657e-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-174">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-174">Format</span></span>

<span data-ttu-id="6657e-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-176">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-176">Pattern</span></span>

<span data-ttu-id="6657e-177">口座番号は 6 ～ 10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="6657e-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="6657e-178">オーストラリアの銀行の州支店番号:</span><span class="sxs-lookup"><span data-stu-id="6657e-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="6657e-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-179">Three digits</span></span> 
- <span data-ttu-id="6657e-180">ハイフン</span><span class="sxs-lookup"><span data-stu-id="6657e-180">A hyphen</span></span> 
- <span data-ttu-id="6657e-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-182">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-182">Checksum</span></span>

<span data-ttu-id="6657e-183">無</span><span class="sxs-lookup"><span data-stu-id="6657e-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-184">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-184">Definition</span></span>

<span data-ttu-id="6657e-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="6657e-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="6657e-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="6657e-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="6657e-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="6657e-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="6657e-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="6657e-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="6657e-194">swift bank code</span></span>
- <span data-ttu-id="6657e-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="6657e-195">correspondent bank</span></span>
- <span data-ttu-id="6657e-196">base currency</span><span class="sxs-lookup"><span data-stu-id="6657e-196">base currency</span></span>
- <span data-ttu-id="6657e-197">usa account</span><span class="sxs-lookup"><span data-stu-id="6657e-197">usa account</span></span>
- <span data-ttu-id="6657e-198">holder address</span><span class="sxs-lookup"><span data-stu-id="6657e-198">holder address</span></span>
- <span data-ttu-id="6657e-199">bank address</span><span class="sxs-lookup"><span data-stu-id="6657e-199">bank address</span></span>
- <span data-ttu-id="6657e-200">information account</span><span class="sxs-lookup"><span data-stu-id="6657e-200">information account</span></span>
- <span data-ttu-id="6657e-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="6657e-201">fund transfers</span></span>
- <span data-ttu-id="6657e-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="6657e-202">bank charges</span></span>
- <span data-ttu-id="6657e-203">bank details</span><span class="sxs-lookup"><span data-stu-id="6657e-203">bank details</span></span>
- <span data-ttu-id="6657e-204">banking information</span><span class="sxs-lookup"><span data-stu-id="6657e-204">banking information</span></span>
- <span data-ttu-id="6657e-205">full names</span><span class="sxs-lookup"><span data-stu-id="6657e-205">full names</span></span>
- <span data-ttu-id="6657e-206">iaea</span><span class="sxs-lookup"><span data-stu-id="6657e-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="6657e-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-208">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-208">Format</span></span>

<span data-ttu-id="6657e-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="6657e-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-210">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-210">Pattern</span></span>

<span data-ttu-id="6657e-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="6657e-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-213">Two digits</span></span> 
- <span data-ttu-id="6657e-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="6657e-215">または</span><span class="sxs-lookup"><span data-stu-id="6657e-215">OR</span></span>

- <span data-ttu-id="6657e-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-217">4-9 digits</span></span>

<span data-ttu-id="6657e-218">または</span><span class="sxs-lookup"><span data-stu-id="6657e-218">OR</span></span>

- <span data-ttu-id="6657e-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="6657e-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-220">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-220">Checksum</span></span>

<span data-ttu-id="6657e-221">無</span><span class="sxs-lookup"><span data-stu-id="6657e-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-222">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-222">Definition</span></span>

<span data-ttu-id="6657e-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="6657e-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="6657e-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6657e-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="6657e-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="6657e-229">international driving permits</span></span>
- <span data-ttu-id="6657e-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="6657e-230">australian automobile association</span></span>
- <span data-ttu-id="6657e-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="6657e-231">international driving permit</span></span>
- <span data-ttu-id="6657e-232">driverlicence</span><span class="sxs-lookup"><span data-stu-id="6657e-232">DriverLicence</span></span>
- <span data-ttu-id="6657e-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="6657e-233">DriverLicences</span></span>
- <span data-ttu-id="6657e-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-234">Driver Lic</span></span>
- <span data-ttu-id="6657e-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-235">Driver Licence</span></span>
- <span data-ttu-id="6657e-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-236">Driver Licences</span></span>
- <span data-ttu-id="6657e-237">driverslic</span><span class="sxs-lookup"><span data-stu-id="6657e-237">DriversLic</span></span>
- <span data-ttu-id="6657e-238">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-238">DriversLicence</span></span>
- <span data-ttu-id="6657e-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="6657e-239">DriversLicences</span></span>
- <span data-ttu-id="6657e-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-240">Drivers Lic</span></span>
- <span data-ttu-id="6657e-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-241">Drivers Lics</span></span>
- <span data-ttu-id="6657e-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-242">Drivers Licence</span></span>
- <span data-ttu-id="6657e-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-243">Drivers Licences</span></span>
- <span data-ttu-id="6657e-244">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-244">Driver'Lic</span></span>
- <span data-ttu-id="6657e-245">driver' lics</span><span class="sxs-lookup"><span data-stu-id="6657e-245">Driver'Lics</span></span>
- <span data-ttu-id="6657e-246">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-246">Driver'Licence</span></span>
- <span data-ttu-id="6657e-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-247">Driver'Licences</span></span>
- <span data-ttu-id="6657e-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-248">Driver' Lic</span></span>
- <span data-ttu-id="6657e-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-249">Driver' Lics</span></span>
- <span data-ttu-id="6657e-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-250">Driver' Licence</span></span>
- <span data-ttu-id="6657e-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-251">Driver' Licences</span></span>
- <span data-ttu-id="6657e-252">driver' slic</span><span class="sxs-lookup"><span data-stu-id="6657e-252">Driver'sLic</span></span>
- <span data-ttu-id="6657e-253">driver' slics</span><span class="sxs-lookup"><span data-stu-id="6657e-253">Driver'sLics</span></span>
- <span data-ttu-id="6657e-254">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="6657e-254">Driver'sLicence</span></span>
- <span data-ttu-id="6657e-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="6657e-255">Driver'sLicences</span></span>
- <span data-ttu-id="6657e-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-256">Driver's Lic</span></span>
- <span data-ttu-id="6657e-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-257">Driver's Lics</span></span>
- <span data-ttu-id="6657e-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-258">Driver's Licence</span></span>
- <span data-ttu-id="6657e-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-259">Driver's Licences</span></span>
- <span data-ttu-id="6657e-260">driverlic #</span><span class="sxs-lookup"><span data-stu-id="6657e-260">DriverLic#</span></span>
- <span data-ttu-id="6657e-261">driverlics #</span><span class="sxs-lookup"><span data-stu-id="6657e-261">DriverLics#</span></span>
- <span data-ttu-id="6657e-262">driverlicence #</span><span class="sxs-lookup"><span data-stu-id="6657e-262">DriverLicence#</span></span>
- <span data-ttu-id="6657e-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="6657e-263">DriverLicences#</span></span>
- <span data-ttu-id="6657e-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-264">Driver Lic#</span></span>
- <span data-ttu-id="6657e-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-265">Driver Lics#</span></span>
- <span data-ttu-id="6657e-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-266">Driver Licence#</span></span>
- <span data-ttu-id="6657e-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-267">Driver Licences#</span></span>
- <span data-ttu-id="6657e-268">driverslic #</span><span class="sxs-lookup"><span data-stu-id="6657e-268">DriversLic#</span></span>
- <span data-ttu-id="6657e-269">driverslics #</span><span class="sxs-lookup"><span data-stu-id="6657e-269">DriversLics#</span></span>
- <span data-ttu-id="6657e-270">のデモライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-270">DriversLicence#</span></span>
- <span data-ttu-id="6657e-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="6657e-271">DriversLicences#</span></span>
- <span data-ttu-id="6657e-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-272">Drivers Lic#</span></span>
- <span data-ttu-id="6657e-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-273">Drivers Lics#</span></span>
- <span data-ttu-id="6657e-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-274">Drivers Licence#</span></span>
- <span data-ttu-id="6657e-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-275">Drivers Licences#</span></span>
- <span data-ttu-id="6657e-276">driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="6657e-276">Driver'Lic#</span></span>
- <span data-ttu-id="6657e-277">driver' lics #</span><span class="sxs-lookup"><span data-stu-id="6657e-277">Driver'Lics#</span></span>
- <span data-ttu-id="6657e-278">driver' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-278">Driver'Licence#</span></span>
- <span data-ttu-id="6657e-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="6657e-279">Driver'Licences#</span></span>
- <span data-ttu-id="6657e-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-280">Driver' Lic#</span></span>
- <span data-ttu-id="6657e-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-281">Driver' Lics#</span></span>
- <span data-ttu-id="6657e-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-282">Driver' Licence#</span></span>
- <span data-ttu-id="6657e-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-283">Driver' Licences#</span></span>
- <span data-ttu-id="6657e-284">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="6657e-284">Driver'sLic#</span></span>
- <span data-ttu-id="6657e-285">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="6657e-285">Driver'sLics#</span></span>
- <span data-ttu-id="6657e-286">ドライバ ' スライスの持続性 #</span><span class="sxs-lookup"><span data-stu-id="6657e-286">Driver'sLicence#</span></span>
- <span data-ttu-id="6657e-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="6657e-287">Driver'sLicences#</span></span>
- <span data-ttu-id="6657e-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-288">Driver's Lic#</span></span>
- <span data-ttu-id="6657e-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-289">Driver's Lics#</span></span>
- <span data-ttu-id="6657e-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-290">Driver's Licence#</span></span>
- <span data-ttu-id="6657e-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="6657e-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="6657e-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="6657e-293">aaa</span><span class="sxs-lookup"><span data-stu-id="6657e-293">aaa</span></span>
- <span data-ttu-id="6657e-294">driverlicense</span><span class="sxs-lookup"><span data-stu-id="6657e-294">DriverLicense</span></span>
- <span data-ttu-id="6657e-295">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="6657e-295">DriverLicenses</span></span>
- <span data-ttu-id="6657e-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="6657e-296">Driver License</span></span>
- <span data-ttu-id="6657e-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-297">Driver Licenses</span></span>
- <span data-ttu-id="6657e-298">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="6657e-298">DriversLicense</span></span>
- <span data-ttu-id="6657e-299">このライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-299">DriversLicenses</span></span>
- <span data-ttu-id="6657e-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="6657e-300">Drivers License</span></span>
- <span data-ttu-id="6657e-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-301">Drivers Licenses</span></span>
- <span data-ttu-id="6657e-302">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-302">Driver'License</span></span>
- <span data-ttu-id="6657e-303">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-303">Driver'Licenses</span></span>
- <span data-ttu-id="6657e-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="6657e-304">Driver' License</span></span>
- <span data-ttu-id="6657e-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-305">Driver' Licenses</span></span>
- <span data-ttu-id="6657e-306">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-306">Driver'sLicense</span></span>
- <span data-ttu-id="6657e-307">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-307">Driver'sLicenses</span></span>
- <span data-ttu-id="6657e-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="6657e-308">Driver's License</span></span>
- <span data-ttu-id="6657e-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-309">Driver's Licenses</span></span>
- <span data-ttu-id="6657e-310">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="6657e-310">DriverLicense#</span></span>
- <span data-ttu-id="6657e-311">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="6657e-311">DriverLicenses#</span></span>
- <span data-ttu-id="6657e-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="6657e-312">Driver License#</span></span>
- <span data-ttu-id="6657e-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-313">Driver Licenses#</span></span>
- <span data-ttu-id="6657e-314">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-314">DriversLicense#</span></span>
- <span data-ttu-id="6657e-315">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-315">DriversLicenses#</span></span>
- <span data-ttu-id="6657e-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="6657e-316">Drivers License#</span></span>
- <span data-ttu-id="6657e-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-317">Drivers Licenses#</span></span>
- <span data-ttu-id="6657e-318">driver' License #</span><span class="sxs-lookup"><span data-stu-id="6657e-318">Driver'License#</span></span>
- <span data-ttu-id="6657e-319">driver' Licenses #</span><span class="sxs-lookup"><span data-stu-id="6657e-319">Driver'Licenses#</span></span>
- <span data-ttu-id="6657e-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="6657e-320">Driver' License#</span></span>
- <span data-ttu-id="6657e-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-321">Driver' Licenses#</span></span>
- <span data-ttu-id="6657e-322">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="6657e-322">Driver'sLicense#</span></span>
- <span data-ttu-id="6657e-323">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="6657e-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="6657e-324">Driver's License#</span></span>
- <span data-ttu-id="6657e-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="6657e-326">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-327">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-327">Format</span></span>

<span data-ttu-id="6657e-328">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-329">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-329">Pattern</span></span>

<span data-ttu-id="6657e-330">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-330">10-11 digits:</span></span>
- <span data-ttu-id="6657e-331">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="6657e-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="6657e-332">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="6657e-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="6657e-333">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="6657e-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="6657e-334">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="6657e-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-335">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-335">Checksum</span></span>

<span data-ttu-id="6657e-336">有</span><span class="sxs-lookup"><span data-stu-id="6657e-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-337">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-337">Definition</span></span>

<span data-ttu-id="6657e-338">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-339">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-340">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="6657e-341">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-341">The checksum passes.</span></span>

<span data-ttu-id="6657e-342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-343">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-344">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-345">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="6657e-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="6657e-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="6657e-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="6657e-347">bank account details</span></span>
- <span data-ttu-id="6657e-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="6657e-348">medicare payments</span></span>
- <span data-ttu-id="6657e-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="6657e-349">mortgage account</span></span>
- <span data-ttu-id="6657e-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="6657e-350">bank payments</span></span>
- <span data-ttu-id="6657e-351">information branch</span><span class="sxs-lookup"><span data-stu-id="6657e-351">information branch</span></span>
- <span data-ttu-id="6657e-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="6657e-352">credit card loan</span></span>
- <span data-ttu-id="6657e-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="6657e-353">department of human services</span></span>
- <span data-ttu-id="6657e-354">local service</span><span class="sxs-lookup"><span data-stu-id="6657e-354">local service</span></span>
- <span data-ttu-id="6657e-355">medicare</span><span class="sxs-lookup"><span data-stu-id="6657e-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="6657e-356">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-357">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-357">Format</span></span>

<span data-ttu-id="6657e-358">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-359">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-359">Pattern</span></span>

<span data-ttu-id="6657e-360">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-361">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-361">Checksum</span></span>

<span data-ttu-id="6657e-362">無</span><span class="sxs-lookup"><span data-stu-id="6657e-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-363">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-363">Definition</span></span>

<span data-ttu-id="6657e-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-365">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-366">Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-367">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6657e-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-368">Keyword_passport</span></span>

- <span data-ttu-id="6657e-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6657e-369">Passport Number</span></span>
- <span data-ttu-id="6657e-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="6657e-370">Passport No</span></span>
- <span data-ttu-id="6657e-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="6657e-371">Passport #</span></span>
- <span data-ttu-id="6657e-372">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-372">Passport#</span></span>
- <span data-ttu-id="6657e-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="6657e-373">PassportID</span></span>
- <span data-ttu-id="6657e-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="6657e-374">Passportno</span></span>
- <span data-ttu-id="6657e-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-375">passportnumber</span></span>
- <span data-ttu-id="6657e-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-376">パスポート</span></span>
- <span data-ttu-id="6657e-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-377">パスポート番号</span></span>
- <span data-ttu-id="6657e-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="6657e-378">パスポートのNum</span></span>
- <span data-ttu-id="6657e-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="6657e-379">パスポート ＃</span></span> 
- <span data-ttu-id="6657e-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6657e-380">Numéro de passeport</span></span>
- <span data-ttu-id="6657e-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6657e-381">Passeport n °</span></span>
- <span data-ttu-id="6657e-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="6657e-382">Passeport Non</span></span>
- <span data-ttu-id="6657e-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-383">Passeport #</span></span>
- <span data-ttu-id="6657e-384">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-384">Passeport#</span></span>
- <span data-ttu-id="6657e-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6657e-385">PasseportNon</span></span>
- <span data-ttu-id="6657e-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6657e-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="6657e-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="6657e-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="6657e-388">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-388">passport</span></span>
- <span data-ttu-id="6657e-389">passport details</span><span class="sxs-lookup"><span data-stu-id="6657e-389">passport details</span></span>
- <span data-ttu-id="6657e-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="6657e-390">immigration and citizenship</span></span>
- <span data-ttu-id="6657e-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="6657e-391">commonwealth of australia</span></span>
- <span data-ttu-id="6657e-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="6657e-392">department of immigration</span></span>
- <span data-ttu-id="6657e-393">residential address</span><span class="sxs-lookup"><span data-stu-id="6657e-393">residential address</span></span>
- <span data-ttu-id="6657e-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="6657e-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="6657e-395">visa</span><span class="sxs-lookup"><span data-stu-id="6657e-395">visa</span></span>
- <span data-ttu-id="6657e-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="6657e-396">national identity card</span></span>
- <span data-ttu-id="6657e-397">passport number</span><span class="sxs-lookup"><span data-stu-id="6657e-397">passport number</span></span>
- <span data-ttu-id="6657e-398">travel document</span><span class="sxs-lookup"><span data-stu-id="6657e-398">travel document</span></span>
- <span data-ttu-id="6657e-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="6657e-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="6657e-400">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="6657e-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-401">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-401">Format</span></span>

<span data-ttu-id="6657e-402">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-403">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-403">Pattern</span></span>

<span data-ttu-id="6657e-404">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6657e-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="6657e-405">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-405">Three digits</span></span> 
- <span data-ttu-id="6657e-406">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-406">An optional space</span></span> 
- <span data-ttu-id="6657e-407">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-407">Three digits</span></span> 
- <span data-ttu-id="6657e-408">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-408">An optional space</span></span> 
- <span data-ttu-id="6657e-409">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="6657e-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-410">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-410">Checksum</span></span>

<span data-ttu-id="6657e-411">有</span><span class="sxs-lookup"><span data-stu-id="6657e-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-412">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-412">Definition</span></span>

<span data-ttu-id="6657e-413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-414">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-415">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="6657e-416">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="6657e-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="6657e-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="6657e-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="6657e-419">australian business number</span></span>
- <span data-ttu-id="6657e-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="6657e-420">marginal tax rate</span></span>
- <span data-ttu-id="6657e-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="6657e-421">medicare levy</span></span>
- <span data-ttu-id="6657e-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="6657e-422">portfolio number</span></span>
- <span data-ttu-id="6657e-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="6657e-423">service veterans</span></span>
- <span data-ttu-id="6657e-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="6657e-424">withholding tax</span></span>
- <span data-ttu-id="6657e-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="6657e-425">individual tax return</span></span>
- <span data-ttu-id="6657e-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="6657e-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="6657e-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="6657e-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="6657e-428">00000000</span><span class="sxs-lookup"><span data-stu-id="6657e-428">00000000</span></span>
- <span data-ttu-id="6657e-429">11111111</span><span class="sxs-lookup"><span data-stu-id="6657e-429">11111111</span></span>
- <span data-ttu-id="6657e-430">22222222</span><span class="sxs-lookup"><span data-stu-id="6657e-430">22222222</span></span>
- <span data-ttu-id="6657e-431">33333333</span><span class="sxs-lookup"><span data-stu-id="6657e-431">33333333</span></span>
- <span data-ttu-id="6657e-432">44444444</span><span class="sxs-lookup"><span data-stu-id="6657e-432">44444444</span></span>
- <span data-ttu-id="6657e-433">55555555</span><span class="sxs-lookup"><span data-stu-id="6657e-433">55555555</span></span>
- <span data-ttu-id="6657e-434">66666666</span><span class="sxs-lookup"><span data-stu-id="6657e-434">66666666</span></span>
- <span data-ttu-id="6657e-435">77777777</span><span class="sxs-lookup"><span data-stu-id="6657e-435">77777777</span></span>
- <span data-ttu-id="6657e-436">88888888</span><span class="sxs-lookup"><span data-stu-id="6657e-436">88888888</span></span>
- <span data-ttu-id="6657e-437">99999999</span><span class="sxs-lookup"><span data-stu-id="6657e-437">99999999</span></span>
- <span data-ttu-id="6657e-438">000000000</span><span class="sxs-lookup"><span data-stu-id="6657e-438">000000000</span></span>
- <span data-ttu-id="6657e-439">111111111</span><span class="sxs-lookup"><span data-stu-id="6657e-439">111111111</span></span>
- <span data-ttu-id="6657e-440">222222222</span><span class="sxs-lookup"><span data-stu-id="6657e-440">222222222</span></span>
- <span data-ttu-id="6657e-441">333333333</span><span class="sxs-lookup"><span data-stu-id="6657e-441">333333333</span></span>
- <span data-ttu-id="6657e-442">444444444</span><span class="sxs-lookup"><span data-stu-id="6657e-442">444444444</span></span>
- <span data-ttu-id="6657e-443">555555555</span><span class="sxs-lookup"><span data-stu-id="6657e-443">555555555</span></span>
- <span data-ttu-id="6657e-444">666666666</span><span class="sxs-lookup"><span data-stu-id="6657e-444">666666666</span></span>
- <span data-ttu-id="6657e-445">777777777</span><span class="sxs-lookup"><span data-stu-id="6657e-445">777777777</span></span>
- <span data-ttu-id="6657e-446">888888888</span><span class="sxs-lookup"><span data-stu-id="6657e-446">888888888</span></span>
- <span data-ttu-id="6657e-447">999999999</span><span class="sxs-lookup"><span data-stu-id="6657e-447">999999999</span></span>
- <span data-ttu-id="6657e-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="6657e-448">0000000000</span></span>
- <span data-ttu-id="6657e-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="6657e-449">1111111111</span></span>
- <span data-ttu-id="6657e-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="6657e-450">2222222222</span></span>
- <span data-ttu-id="6657e-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="6657e-451">3333333333</span></span>
- <span data-ttu-id="6657e-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="6657e-452">4444444444</span></span>
- <span data-ttu-id="6657e-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="6657e-453">5555555555</span></span>
- <span data-ttu-id="6657e-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="6657e-454">6666666666</span></span>
- <span data-ttu-id="6657e-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="6657e-455">7777777777</span></span>
- <span data-ttu-id="6657e-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="6657e-456">8888888888</span></span>
- <span data-ttu-id="6657e-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="6657e-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="6657e-458">Azure DocumentDB 認証キー</span><span class="sxs-lookup"><span data-stu-id="6657e-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="6657e-459">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-459">Format</span></span>

<span data-ttu-id="6657e-460">文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="6657e-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-461">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-461">Pattern</span></span>

- <span data-ttu-id="6657e-462">文字列 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="6657e-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="6657e-463">3-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-464">より大きい記号 (>)、等号 (=)、二重引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="6657e-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="6657e-465">86の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="6657e-466">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-467">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-467">Checksum</span></span>

<span data-ttu-id="6657e-468">無</span><span class="sxs-lookup"><span data-stu-id="6657e-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-469">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-469">Definition</span></span>

<span data-ttu-id="6657e-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-471">正規表現 CEP_Regex_AzureDocumentDBAuthKey は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-472">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-473">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-473">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-475">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-476">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-476">contoso</span></span>
- <span data-ttu-id="6657e-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-477">fabrikam</span></span>
- <span data-ttu-id="6657e-478">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-478">northwind</span></span>
- <span data-ttu-id="6657e-479">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-479">sandbox</span></span>
- <span data-ttu-id="6657e-480">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-480">onebox</span></span>
- <span data-ttu-id="6657e-481">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-481">localhost</span></span>
- <span data-ttu-id="6657e-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-482">127.0.0.1</span></span>
- <span data-ttu-id="6657e-483">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-483">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-484">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-484">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="6657e-485">azure IAAS データベースの接続文字列と azure SQL 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6657e-485">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="6657e-486">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-486">Format</span></span>

<span data-ttu-id="6657e-487">文字列 "server"、"server"、または "data source" の後に、次のパターンで概説されている文字と文字列を指定します (文字列 "cloudapp" を含む)。<!--no-hyperlink-->com または "cloudapp azure。<!--no-hyperlink-->net "または" database "です。<!--no-hyperlink-->net "、および" password "または" pwd "という文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-487">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.<!--no-hyperlink-->com" or "cloudapp.azure.<!--no-hyperlink-->net" or "database.windows.<!--no-hyperlink-->net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-488">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-488">Pattern</span></span>

- <span data-ttu-id="6657e-489">文字列 "server"、"server"、または "data source"</span><span class="sxs-lookup"><span data-stu-id="6657e-489">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="6657e-490">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-490">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-491">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-491">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-492">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-492">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-493">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-493">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-494">文字列 "cloudapp。<!--no-hyperlink-->com "," cloudapp。<!--no-hyperlink-->net "、または" database "です。<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="6657e-494">The string "cloudapp.azure.<!--no-hyperlink-->com", "cloudapp.azure.<!--no-hyperlink-->net", or "database.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="6657e-495">1-300 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-495">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-496">文字列 "password"、"password"、または "pwd"</span><span class="sxs-lookup"><span data-stu-id="6657e-496">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="6657e-497">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-498">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-498">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-499">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-499">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-500">セミコロンではない1つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="6657e-500">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="6657e-501">セミコロン (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="6657e-501">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-502">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-502">Checksum</span></span>

<span data-ttu-id="6657e-503">無</span><span class="sxs-lookup"><span data-stu-id="6657e-503">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-504">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-504">Definition</span></span>

<span data-ttu-id="6657e-505">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-505">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-506">正規表現 CEP_Regex_AzureConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-506">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-507">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-507">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-508">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-508">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-509">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-509">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-510">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-510">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-511">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-511">contoso</span></span>
- <span data-ttu-id="6657e-512">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-512">fabrikam</span></span>
- <span data-ttu-id="6657e-513">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-513">northwind</span></span>
- <span data-ttu-id="6657e-514">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-514">sandbox</span></span>
- <span data-ttu-id="6657e-515">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-515">onebox</span></span>
- <span data-ttu-id="6657e-516">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-516">localhost</span></span>
- <span data-ttu-id="6657e-517">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-517">127.0.0.1</span></span>
- <span data-ttu-id="6657e-518">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-518">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-519">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-519">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="6657e-520">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6657e-520">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="6657e-521">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-521">Format</span></span>

<span data-ttu-id="6657e-522">文字列 "HostName" の後に、次のパターンで概説されている文字と文字列 ("azure デバイス" を含む)。<!--no-hyperlink-->net "および" sharedaccesskey "。</span><span class="sxs-lookup"><span data-stu-id="6657e-522">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.<!--no-hyperlink-->net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-523">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-523">Pattern</span></span>

- <span data-ttu-id="6657e-524">文字列 "HostName"</span><span class="sxs-lookup"><span data-stu-id="6657e-524">The string "HostName"</span></span>
- <span data-ttu-id="6657e-525">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-525">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-526">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-526">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-527">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-527">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-528">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-528">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-529">文字列 "azure デバイス。<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="6657e-529">The string "azure-devices.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="6657e-530">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-530">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-531">文字列 "sharedaccesskey"</span><span class="sxs-lookup"><span data-stu-id="6657e-531">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="6657e-532">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-532">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-533">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-533">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-534">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-534">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-535">43の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-535">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="6657e-536">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-536">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-537">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-537">Checksum</span></span>

<span data-ttu-id="6657e-538">無</span><span class="sxs-lookup"><span data-stu-id="6657e-538">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-539">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-539">Definition</span></span>

<span data-ttu-id="6657e-540">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-540">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-541">正規表現 CEP_Regex_AzureIoTConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-541">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-542">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-542">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-543">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-543">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-544">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-544">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-545">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-545">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-546">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-546">contoso</span></span>
- <span data-ttu-id="6657e-547">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-547">fabrikam</span></span>
- <span data-ttu-id="6657e-548">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-548">northwind</span></span>
- <span data-ttu-id="6657e-549">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-549">sandbox</span></span>
- <span data-ttu-id="6657e-550">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-550">onebox</span></span>
- <span data-ttu-id="6657e-551">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-551">localhost</span></span>
- <span data-ttu-id="6657e-552">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-552">127.0.0.1</span></span>
- <span data-ttu-id="6657e-553">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-553">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-554">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-554">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="6657e-555">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="6657e-555">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="6657e-556">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-556">Format</span></span>

<span data-ttu-id="6657e-557">文字列 "userpwd =" に続けて英数字の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-557">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-558">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-558">Pattern</span></span>

- <span data-ttu-id="6657e-559">文字列 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="6657e-559">The string "userpwd="</span></span>
- <span data-ttu-id="6657e-560">60小文字または数字の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-560">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="6657e-561">二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="6657e-561">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-562">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-562">Checksum</span></span>

<span data-ttu-id="6657e-563">無</span><span class="sxs-lookup"><span data-stu-id="6657e-563">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-564">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-564">Definition</span></span>

<span data-ttu-id="6657e-565">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-565">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-566">正規表現 CEP_Regex_AzurePublishSettingPasswords は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-566">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-567">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-567">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


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

### <a name="keywords"></a><span data-ttu-id="6657e-568">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-568">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-569">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-569">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-570">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-570">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-571">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-571">contoso</span></span>
- <span data-ttu-id="6657e-572">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-572">fabrikam</span></span>
- <span data-ttu-id="6657e-573">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-573">northwind</span></span>
- <span data-ttu-id="6657e-574">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-574">sandbox</span></span>
- <span data-ttu-id="6657e-575">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-575">onebox</span></span>
- <span data-ttu-id="6657e-576">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-576">localhost</span></span>
- <span data-ttu-id="6657e-577">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-577">127.0.0.1</span></span>
- <span data-ttu-id="6657e-578">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-578">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-579">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-579">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="6657e-580">Azure Redis cache 接続文字列</span><span class="sxs-lookup"><span data-stu-id="6657e-580">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="6657e-581">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-581">Format</span></span>

<span data-ttu-id="6657e-582">文字列 "redis...<!--no-hyperlink-->net "の後に、次のパターンで概説されている文字と文字列を指定します。文字列" password "または" pwd "が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6657e-582">The string "redis.cache.windows.<!--no-hyperlink-->net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-583">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-583">Pattern</span></span>

- <span data-ttu-id="6657e-584">文字列 "redis...<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="6657e-584">The string "redis.cache.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="6657e-585">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-585">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-586">文字列 "password" または "pwd"</span><span class="sxs-lookup"><span data-stu-id="6657e-586">The string "password" or "pwd"</span></span>
- <span data-ttu-id="6657e-587">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-587">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-588">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-588">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-589">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-589">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-590">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="6657e-590">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="6657e-591">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-591">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-592">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-592">Checksum</span></span>

<span data-ttu-id="6657e-593">無</span><span class="sxs-lookup"><span data-stu-id="6657e-593">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-594">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-594">Definition</span></span>

<span data-ttu-id="6657e-595">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-596">正規表現 CEP_Regex_AzureRedisCacheConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-596">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="6657e-597">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-597">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-598">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-598">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-599">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-599">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-600">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-600">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-601">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-601">contoso</span></span>
- <span data-ttu-id="6657e-602">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-602">fabrikam</span></span>
- <span data-ttu-id="6657e-603">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-603">northwind</span></span>
- <span data-ttu-id="6657e-604">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-604">sandbox</span></span>
- <span data-ttu-id="6657e-605">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-605">onebox</span></span>
- <span data-ttu-id="6657e-606">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-606">localhost</span></span>
- <span data-ttu-id="6657e-607">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-607">127.0.0.1</span></span>
- <span data-ttu-id="6657e-608">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-608">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-609">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-609">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="6657e-610">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="6657e-610">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="6657e-611">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-611">Format</span></span>

<span data-ttu-id="6657e-612">文字列 "sig" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="6657e-612">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-613">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-613">Pattern</span></span>

- <span data-ttu-id="6657e-614">文字列 "sig"</span><span class="sxs-lookup"><span data-stu-id="6657e-614">The string "sig"</span></span>
- <span data-ttu-id="6657e-615">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-615">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-616">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-616">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-617">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-617">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-618">43-53 文字のうち、下位または大文字の文字、数字、またはパーセント記号 (%) の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="6657e-618">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="6657e-619">文字列 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="6657e-619">The string "%3d"</span></span>
- <span data-ttu-id="6657e-620">小文字または大文字、数字、パーセント記号 (%) 以外の文字</span><span class="sxs-lookup"><span data-stu-id="6657e-620">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-621">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-621">Checksum</span></span>

<span data-ttu-id="6657e-622">無</span><span class="sxs-lookup"><span data-stu-id="6657e-622">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-623">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-623">Definition</span></span>

<span data-ttu-id="6657e-624">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-624">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-625">正規表現 CEP_Regex_AzureSAS は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-625">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="6657e-626">Azure Service Bus の接続文字列</span><span class="sxs-lookup"><span data-stu-id="6657e-626">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="6657e-627">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-627">Format</span></span>

<span data-ttu-id="6657e-628">文字列 "EndPoint" の後に、次のパターンで概説されている文字と文字列が続きます。<!--no-hyperlink-->net "および" shared' キー "。</span><span class="sxs-lookup"><span data-stu-id="6657e-628">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.<!--no-hyperlink-->net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-629">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-629">Pattern</span></span>

- <span data-ttu-id="6657e-630">文字列 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="6657e-630">The string "EndPoint"</span></span>
- <span data-ttu-id="6657e-631">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-631">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-632">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-632">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-633">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-633">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-634">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-634">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-635">文字列 "windows.<!--no-hyperlink-->net "</span><span class="sxs-lookup"><span data-stu-id="6657e-635">The string "servicebus.windows.<!--no-hyperlink-->net"</span></span>
- <span data-ttu-id="6657e-636">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-636">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-637">文字列 "sharedaccesskey"</span><span class="sxs-lookup"><span data-stu-id="6657e-637">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="6657e-638">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-638">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-639">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-639">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-640">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-640">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-641">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="6657e-641">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="6657e-642">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-642">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-643">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-643">Checksum</span></span>

<span data-ttu-id="6657e-644">無</span><span class="sxs-lookup"><span data-stu-id="6657e-644">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-645">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-645">Definition</span></span>

<span data-ttu-id="6657e-646">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-646">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-647">正規表現 CEP_Regex_AzureServiceBusConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-647">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="6657e-648">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-648">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-649">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-649">Keywords</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-650">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-650">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-651">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-651">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-652">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-652">contoso</span></span>
- <span data-ttu-id="6657e-653">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-653">fabrikam</span></span>
- <span data-ttu-id="6657e-654">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-654">northwind</span></span>
- <span data-ttu-id="6657e-655">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-655">sandbox</span></span>
- <span data-ttu-id="6657e-656">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-656">onebox</span></span>
- <span data-ttu-id="6657e-657">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-657">localhost</span></span>
- <span data-ttu-id="6657e-658">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-658">127.0.0.1</span></span>
- <span data-ttu-id="6657e-659">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-659">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-660">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-660">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="6657e-661">Azure ストレージアカウントキー</span><span class="sxs-lookup"><span data-stu-id="6657e-661">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="6657e-662">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-662">Format</span></span>

<span data-ttu-id="6657e-663">文字列 "defaultendpointsprotocol" の後に、文字列 "AccountKey" を含む、次のパターンで概説されている文字および文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="6657e-663">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-664">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-664">Pattern</span></span>

- <span data-ttu-id="6657e-665">文字列 "defaultendpointsprotocol"</span><span class="sxs-lookup"><span data-stu-id="6657e-665">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="6657e-666">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-666">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-667">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-667">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-668">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-668">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-669">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-669">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-670">文字列 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="6657e-670">The string "AccountKey"</span></span>
- <span data-ttu-id="6657e-671">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-671">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-672">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-672">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-673">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="6657e-673">0-2 whitespace characters</span></span>
- <span data-ttu-id="6657e-674">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="6657e-674">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="6657e-675">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-675">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-676">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-676">Checksum</span></span>

<span data-ttu-id="6657e-677">無</span><span class="sxs-lookup"><span data-stu-id="6657e-677">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-678">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-678">Definition</span></span>

<span data-ttu-id="6657e-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-679">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-680">正規表現 CEP_Regex_AzureStorageAccountKey は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-680">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-681">正規表現 CEP_AzureEmulatorStorageAccountFilter は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-681">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-682">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-682">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-683">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-683">Keywords</span></span>

#### <a name="cepazureemulatorstorageaccountfilter"></a><span data-ttu-id="6657e-684">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="6657e-684">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="6657e-685">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-685">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/kbhbeksogmgw = =</span><span class="sxs-lookup"><span data-stu-id="6657e-686">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-687">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-687">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-688">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-688">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-689">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-689">contoso</span></span>
- <span data-ttu-id="6657e-690">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-690">fabrikam</span></span>
- <span data-ttu-id="6657e-691">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-691">northwind</span></span>
- <span data-ttu-id="6657e-692">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-692">sandbox</span></span>
- <span data-ttu-id="6657e-693">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-693">onebox</span></span>
- <span data-ttu-id="6657e-694">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-694">localhost</span></span>
- <span data-ttu-id="6657e-695">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-695">127.0.0.1</span></span>
- <span data-ttu-id="6657e-696">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-696">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-697">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-697">s-int.<!--no-hyperlink-->net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="6657e-698">Azure ストレージアカウントキー (汎用)</span><span class="sxs-lookup"><span data-stu-id="6657e-698">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-699">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-699">Format</span></span>

<span data-ttu-id="6657e-700">86の下または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、下のパターンで説明されている文字が前または後にある。</span><span class="sxs-lookup"><span data-stu-id="6657e-700">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-701">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-701">Pattern</span></span>

- <span data-ttu-id="6657e-702">0-1 より大きい記号 (>)、アポストロフィ (')、等号 (=)、二重引用符 (")、または番号記号 (#) を指定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-702">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="6657e-703">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="6657e-703">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="6657e-704">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-704">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="6657e-705">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-705">Checksum</span></span>

<span data-ttu-id="6657e-706">無</span><span class="sxs-lookup"><span data-stu-id="6657e-706">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-707">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-707">Definition</span></span>

<span data-ttu-id="6657e-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-708">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-709">正規表現 CEP_Regex_AzureStorageAccountKeyGeneric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-709">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="6657e-710">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="6657e-710">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-711">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-711">Format</span></span>

<span data-ttu-id="6657e-712">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="6657e-712">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-713">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-713">Pattern</span></span>

<span data-ttu-id="6657e-714">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="6657e-714">11 digits plus delimiters:</span></span>
- <span data-ttu-id="6657e-715">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="6657e-715">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="6657e-716">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-716">A hyphen</span></span> 
- <span data-ttu-id="6657e-717">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="6657e-717">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="6657e-718">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="6657e-718">A period</span></span> 
- <span data-ttu-id="6657e-719">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-719">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-720">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-720">Checksum</span></span>

<span data-ttu-id="6657e-721">有</span><span class="sxs-lookup"><span data-stu-id="6657e-721">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-722">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-722">Definition</span></span>

<span data-ttu-id="6657e-723">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-723">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-724">関数 Func_belgium_national_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-724">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-725">Keyword_belgium_national_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-725">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="6657e-726">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-726">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-727">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-727">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="6657e-728">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="6657e-728">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="6657e-729">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-729">Identity</span></span>
- <span data-ttu-id="6657e-730">レジスタ</span><span class="sxs-lookup"><span data-stu-id="6657e-730">Registration</span></span>
- <span data-ttu-id="6657e-731">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-731">Identification</span></span> 
- <span data-ttu-id="6657e-732">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-732">ID</span></span> 
- <span data-ttu-id="6657e-733">「識別子」</span><span class="sxs-lookup"><span data-stu-id="6657e-733">Identiteitskaart</span></span>
- <span data-ttu-id="6657e-734">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="6657e-734">Registratie nummer</span></span> 
- <span data-ttu-id="6657e-735">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="6657e-735">Identificatie nummer</span></span> 
- <span data-ttu-id="6657e-736">識別子</span><span class="sxs-lookup"><span data-stu-id="6657e-736">Identiteit</span></span>
- <span data-ttu-id="6657e-737">Registratie</span><span class="sxs-lookup"><span data-stu-id="6657e-737">Registratie</span></span>
- <span data-ttu-id="6657e-738">識別子</span><span class="sxs-lookup"><span data-stu-id="6657e-738">Identificatie</span></span> 
- <span data-ttu-id="6657e-739">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="6657e-739">Carte d’identité</span></span> 
- <span data-ttu-id="6657e-740">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="6657e-740">numéro d'immatriculation</span></span>
- <span data-ttu-id="6657e-741">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="6657e-741">numéro d'identification</span></span>
- <span data-ttu-id="6657e-742">識別子</span><span class="sxs-lookup"><span data-stu-id="6657e-742">identité</span></span> 
- <span data-ttu-id="6657e-743">inscription</span><span class="sxs-lookup"><span data-stu-id="6657e-743">inscription</span></span> 
- <span data-ttu-id="6657e-744">Identifikation</span><span class="sxs-lookup"><span data-stu-id="6657e-744">Identifikation</span></span>
- <span data-ttu-id="6657e-745">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="6657e-745">Identifizierung</span></span>
- <span data-ttu-id="6657e-746">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-746">Identifikationsnummer</span></span>
- <span data-ttu-id="6657e-747">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="6657e-747">Personalausweis</span></span>
- <span data-ttu-id="6657e-748">Registrierung</span><span class="sxs-lookup"><span data-stu-id="6657e-748">Registrierung</span></span>
- <span data-ttu-id="6657e-749">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-749">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="6657e-750">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-750">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-751">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-751">Format</span></span>

<span data-ttu-id="6657e-752">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-752">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-753">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-753">Pattern</span></span>

<span data-ttu-id="6657e-754">さ</span><span class="sxs-lookup"><span data-stu-id="6657e-754">Formatted:</span></span>
- <span data-ttu-id="6657e-755">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-755">Three digits</span></span> 
- <span data-ttu-id="6657e-756">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-756">A period</span></span> 
- <span data-ttu-id="6657e-757">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-757">Three digits</span></span> 
- <span data-ttu-id="6657e-758">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-758">A period</span></span> 
- <span data-ttu-id="6657e-759">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-759">Three digits</span></span> 
- <span data-ttu-id="6657e-760">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-760">A hyphen</span></span> 
- <span data-ttu-id="6657e-761">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-761">Two digits which are check digits</span></span>

<span data-ttu-id="6657e-762">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-762">Unformatted:</span></span>
- <span data-ttu-id="6657e-763">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="6657e-763">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-764">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-764">Checksum</span></span>

<span data-ttu-id="6657e-765">有</span><span class="sxs-lookup"><span data-stu-id="6657e-765">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-766">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-766">Definition</span></span>

<span data-ttu-id="6657e-767">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-767">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-768">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-768">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-769">Keyword_brazil_cpf からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-769">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="6657e-770">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-770">The checksum passes.</span></span>

<span data-ttu-id="6657e-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-772">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-772">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-773">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-773">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-774">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="6657e-775">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="6657e-775">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="6657e-776">CPF</span><span class="sxs-lookup"><span data-stu-id="6657e-776">CPF</span></span>
- <span data-ttu-id="6657e-777">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-777">Identification</span></span>
- <span data-ttu-id="6657e-778">レジスタ</span><span class="sxs-lookup"><span data-stu-id="6657e-778">Registration</span></span>
- <span data-ttu-id="6657e-779">増大</span><span class="sxs-lookup"><span data-stu-id="6657e-779">Revenue</span></span>
- <span data-ttu-id="6657e-780">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="6657e-780">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="6657e-781">imposto</span><span class="sxs-lookup"><span data-stu-id="6657e-781">Imposto</span></span> 
- <span data-ttu-id="6657e-782">Identificação</span><span class="sxs-lookup"><span data-stu-id="6657e-782">Identificação</span></span> 
- <span data-ttu-id="6657e-783">Inscrição</span><span class="sxs-lookup"><span data-stu-id="6657e-783">Inscrição</span></span> 
- <span data-ttu-id="6657e-784">Receita</span><span class="sxs-lookup"><span data-stu-id="6657e-784">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="6657e-785">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="6657e-785">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-786">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-786">Format</span></span>

<span data-ttu-id="6657e-787">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-787">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-788">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-788">Pattern</span></span>
<span data-ttu-id="6657e-789">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="6657e-789">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="6657e-790">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-790">Two digits</span></span> 
- <span data-ttu-id="6657e-791">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-791">A period</span></span> 
- <span data-ttu-id="6657e-792">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-792">Three digits</span></span> 
- <span data-ttu-id="6657e-793">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-793">A period</span></span> 
- <span data-ttu-id="6657e-794">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="6657e-794">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="6657e-795">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-795">A forward slash</span></span> 
- <span data-ttu-id="6657e-796">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="6657e-796">Four-digit branch number</span></span> 
- <span data-ttu-id="6657e-797">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-797">A hyphen</span></span> 
- <span data-ttu-id="6657e-798">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-798">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-799">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-799">Checksum</span></span>

<span data-ttu-id="6657e-800">有</span><span class="sxs-lookup"><span data-stu-id="6657e-800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-801">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-801">Definition</span></span>

<span data-ttu-id="6657e-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-803">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-803">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-804">Keyword_brazil_cnpj からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-804">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="6657e-805">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-805">The checksum passes.</span></span>

<span data-ttu-id="6657e-806">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-806">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-807">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-807">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-808">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-808">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-809">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-809">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="6657e-810">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="6657e-810">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="6657e-811">CNPJ</span><span class="sxs-lookup"><span data-stu-id="6657e-811">CNPJ</span></span> 
- <span data-ttu-id="6657e-812">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="6657e-812">CNPJ/MF</span></span> 
- <span data-ttu-id="6657e-813">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="6657e-813">CNPJ-MF</span></span> 
- <span data-ttu-id="6657e-814">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="6657e-814">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="6657e-815">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="6657e-815">Taxpayers Registry</span></span> 
- <span data-ttu-id="6657e-816">Legal entity</span><span class="sxs-lookup"><span data-stu-id="6657e-816">Legal entity</span></span> 
- <span data-ttu-id="6657e-817">Legal entities</span><span class="sxs-lookup"><span data-stu-id="6657e-817">Legal entities</span></span> 
- <span data-ttu-id="6657e-818">Registration Status</span><span class="sxs-lookup"><span data-stu-id="6657e-818">Registration Status</span></span> 
- <span data-ttu-id="6657e-819">Business</span><span class="sxs-lookup"><span data-stu-id="6657e-819">Business</span></span> 
- <span data-ttu-id="6657e-820">Company</span><span class="sxs-lookup"><span data-stu-id="6657e-820">Company</span></span>
- <span data-ttu-id="6657e-821">CNPJ</span><span class="sxs-lookup"><span data-stu-id="6657e-821">CNPJ</span></span> 
- <span data-ttu-id="6657e-822">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="6657e-822">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="6657e-823">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="6657e-823">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="6657e-824">cgc</span><span class="sxs-lookup"><span data-stu-id="6657e-824">CGC</span></span> 
- <span data-ttu-id="6657e-825">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="6657e-825">Pessoa jurídica</span></span> 
- <span data-ttu-id="6657e-826">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="6657e-826">Pessoas jurídicas</span></span> 
- <span data-ttu-id="6657e-827">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="6657e-827">Situação cadastral</span></span> 
- <span data-ttu-id="6657e-828">Inscrição</span><span class="sxs-lookup"><span data-stu-id="6657e-828">Inscrição</span></span> 
- <span data-ttu-id="6657e-829">サイト</span><span class="sxs-lookup"><span data-stu-id="6657e-829">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="6657e-830">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="6657e-830">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-831">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-831">Format</span></span>

<span data-ttu-id="6657e-832">Registro geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-832">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="6657e-833">Registro de 識別子 dade (ric) (新しい形式):11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-833">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-834">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-834">Pattern</span></span>

<span data-ttu-id="6657e-835">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="6657e-835">Registro Geral (old format):</span></span>
- <span data-ttu-id="6657e-836">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-836">Two digits</span></span> 
- <span data-ttu-id="6657e-837">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-837">A period</span></span> 
- <span data-ttu-id="6657e-838">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-838">Three digits</span></span> 
- <span data-ttu-id="6657e-839">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-839">A period</span></span> 
- <span data-ttu-id="6657e-840">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-840">Three digits</span></span> 
- <span data-ttu-id="6657e-841">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-841">A hyphen</span></span> 
- <span data-ttu-id="6657e-842">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-842">One digit which is a check digit</span></span>

<span data-ttu-id="6657e-843">Registro de 識別子 dade (ric) (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="6657e-843">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="6657e-844">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-844">10 digits</span></span> 
- <span data-ttu-id="6657e-845">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-845">A hyphen</span></span> 
- <span data-ttu-id="6657e-846">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-846">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-847">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-847">Checksum</span></span>

<span data-ttu-id="6657e-848">有</span><span class="sxs-lookup"><span data-stu-id="6657e-848">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-849">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-849">Definition</span></span>

<span data-ttu-id="6657e-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-850">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-851">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-851">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-852">Keyword_brazil_rg からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-852">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="6657e-853">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-853">The checksum passes.</span></span>

<span data-ttu-id="6657e-854">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-854">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-855">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-855">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-856">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-856">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-857">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-857">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="6657e-858">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="6657e-858">Keyword_brazil_rg</span></span>

<span data-ttu-id="6657e-859">Cédula de 識別子 dade id カード national id número de rregistro registro de i識別子 dade registro geral このキーワードは大文字と小文字を区別します) ric (このキーワードは大文字と小文字を区別します)</span><span class="sxs-lookup"><span data-stu-id="6657e-859">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="6657e-860">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-860">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-861">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-861">Format</span></span>

<span data-ttu-id="6657e-862">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-862">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-863">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-863">Pattern</span></span>

<span data-ttu-id="6657e-864">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="6657e-864">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="6657e-865">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6657e-865">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="6657e-866">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-866">Five digits</span></span> 
- <span data-ttu-id="6657e-867">ハイフン</span><span class="sxs-lookup"><span data-stu-id="6657e-867">A hyphen</span></span> 
- <span data-ttu-id="6657e-868">3桁の数字または</span><span class="sxs-lookup"><span data-stu-id="6657e-868">Three digits OR</span></span>
- <span data-ttu-id="6657e-869">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="6657e-869">A zero "0"</span></span> 
- <span data-ttu-id="6657e-870">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-870">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-871">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-871">Checksum</span></span>

<span data-ttu-id="6657e-872">無</span><span class="sxs-lookup"><span data-stu-id="6657e-872">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-873">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-873">Definition</span></span>

<span data-ttu-id="6657e-874">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-874">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-875">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-875">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-876">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-876">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="6657e-877">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-877">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="6657e-878">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-878">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-879">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-879">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-880">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-880">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-881">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-881">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="6657e-882">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="6657e-882">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="6657e-883">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="6657e-883">canada savings bonds</span></span>
- <span data-ttu-id="6657e-884">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="6657e-884">canada revenue agency</span></span>
- <span data-ttu-id="6657e-885">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="6657e-885">canadian financial institution</span></span>
- <span data-ttu-id="6657e-886">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="6657e-886">direct deposit form</span></span>
- <span data-ttu-id="6657e-887">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="6657e-887">canadian citizen</span></span>
- <span data-ttu-id="6657e-888">legal representative</span><span class="sxs-lookup"><span data-stu-id="6657e-888">legal representative</span></span>
- <span data-ttu-id="6657e-889">notary public</span><span class="sxs-lookup"><span data-stu-id="6657e-889">notary public</span></span>
- <span data-ttu-id="6657e-890">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="6657e-890">commissioner for oaths</span></span>
- <span data-ttu-id="6657e-891">child care benefit</span><span class="sxs-lookup"><span data-stu-id="6657e-891">child care benefit</span></span>
- <span data-ttu-id="6657e-892">universal child care</span><span class="sxs-lookup"><span data-stu-id="6657e-892">universal child care</span></span>
- <span data-ttu-id="6657e-893">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="6657e-893">canada child tax benefit</span></span>
- <span data-ttu-id="6657e-894">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="6657e-894">income tax benefit</span></span>
- <span data-ttu-id="6657e-895">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="6657e-895">harmonized sales tax</span></span>
- <span data-ttu-id="6657e-896">social insurance number</span><span class="sxs-lookup"><span data-stu-id="6657e-896">social insurance number</span></span>
- <span data-ttu-id="6657e-897">income tax refund</span><span class="sxs-lookup"><span data-stu-id="6657e-897">income tax refund</span></span>
- <span data-ttu-id="6657e-898">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="6657e-898">child tax benefit</span></span>
- <span data-ttu-id="6657e-899">territorial payments</span><span class="sxs-lookup"><span data-stu-id="6657e-899">territorial payments</span></span>
- <span data-ttu-id="6657e-900">institution number</span><span class="sxs-lookup"><span data-stu-id="6657e-900">institution number</span></span>
- <span data-ttu-id="6657e-901">deposit request</span><span class="sxs-lookup"><span data-stu-id="6657e-901">deposit request</span></span>
- <span data-ttu-id="6657e-902">banking information</span><span class="sxs-lookup"><span data-stu-id="6657e-902">banking information</span></span>
- <span data-ttu-id="6657e-903">direct deposit</span><span class="sxs-lookup"><span data-stu-id="6657e-903">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="6657e-904">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-904">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-905">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-905">Format</span></span>

<span data-ttu-id="6657e-906">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="6657e-906">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-907">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-907">Pattern</span></span>

<span data-ttu-id="6657e-908">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-908">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-909">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-909">Checksum</span></span>

<span data-ttu-id="6657e-910">無</span><span class="sxs-lookup"><span data-stu-id="6657e-910">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-911">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-911">Definition</span></span>

<span data-ttu-id="6657e-912">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-913">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-913">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-914">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-914">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="6657e-915">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-915">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-916">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-916">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="6657e-917">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="6657e-917">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="6657e-918">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="6657e-918">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="6657e-919">州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="6657e-919">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="6657e-920">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6657e-920">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="6657e-921">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-921">DL</span></span>
- <span data-ttu-id="6657e-922">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-922">DLS</span></span>
- <span data-ttu-id="6657e-923">CDL</span><span class="sxs-lookup"><span data-stu-id="6657e-923">CDL</span></span>
- <span data-ttu-id="6657e-924">cdls</span><span class="sxs-lookup"><span data-stu-id="6657e-924">CDLS</span></span>
- <span data-ttu-id="6657e-925">driverlic</span><span class="sxs-lookup"><span data-stu-id="6657e-925">DriverLic</span></span>
- <span data-ttu-id="6657e-926">driverlics</span><span class="sxs-lookup"><span data-stu-id="6657e-926">DriverLics</span></span>
- <span data-ttu-id="6657e-927">driverlicense</span><span class="sxs-lookup"><span data-stu-id="6657e-927">DriverLicense</span></span>
- <span data-ttu-id="6657e-928">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="6657e-928">DriverLicenses</span></span>
- <span data-ttu-id="6657e-929">driverlicence</span><span class="sxs-lookup"><span data-stu-id="6657e-929">DriverLicence</span></span>
- <span data-ttu-id="6657e-930">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="6657e-930">DriverLicences</span></span>
- <span data-ttu-id="6657e-931">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-931">Driver Lic</span></span>
- <span data-ttu-id="6657e-932">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-932">Driver Lics</span></span>
- <span data-ttu-id="6657e-933">Driver License</span><span class="sxs-lookup"><span data-stu-id="6657e-933">Driver License</span></span>
- <span data-ttu-id="6657e-934">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-934">Driver Licenses</span></span>
- <span data-ttu-id="6657e-935">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-935">Driver Licence</span></span>
- <span data-ttu-id="6657e-936">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-936">Driver Licences</span></span>
- <span data-ttu-id="6657e-937">driverslic</span><span class="sxs-lookup"><span data-stu-id="6657e-937">DriversLic</span></span>
- <span data-ttu-id="6657e-938">driverslics</span><span class="sxs-lookup"><span data-stu-id="6657e-938">DriversLics</span></span>
- <span data-ttu-id="6657e-939">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-939">DriversLicence</span></span>
- <span data-ttu-id="6657e-940">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="6657e-940">DriversLicences</span></span>
- <span data-ttu-id="6657e-941">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="6657e-941">DriversLicense</span></span>
- <span data-ttu-id="6657e-942">このライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-942">DriversLicenses</span></span>
- <span data-ttu-id="6657e-943">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-943">Drivers Lic</span></span>
- <span data-ttu-id="6657e-944">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-944">Drivers Lics</span></span>
- <span data-ttu-id="6657e-945">Drivers License</span><span class="sxs-lookup"><span data-stu-id="6657e-945">Drivers License</span></span>
- <span data-ttu-id="6657e-946">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-946">Drivers Licenses</span></span>
- <span data-ttu-id="6657e-947">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-947">Drivers Licence</span></span>
- <span data-ttu-id="6657e-948">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-948">Drivers Licences</span></span>
- <span data-ttu-id="6657e-949">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-949">Driver'Lic</span></span>
- <span data-ttu-id="6657e-950">driver' lics</span><span class="sxs-lookup"><span data-stu-id="6657e-950">Driver'Lics</span></span>
- <span data-ttu-id="6657e-951">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-951">Driver'License</span></span>
- <span data-ttu-id="6657e-952">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-952">Driver'Licenses</span></span>
- <span data-ttu-id="6657e-953">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-953">Driver'Licence</span></span>
- <span data-ttu-id="6657e-954">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-954">Driver'Licences</span></span>
- <span data-ttu-id="6657e-955">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-955">Driver' Lic</span></span>
- <span data-ttu-id="6657e-956">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-956">Driver' Lics</span></span>
- <span data-ttu-id="6657e-957">Driver' License</span><span class="sxs-lookup"><span data-stu-id="6657e-957">Driver' License</span></span>
- <span data-ttu-id="6657e-958">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-958">Driver' Licenses</span></span>
- <span data-ttu-id="6657e-959">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-959">Driver' Licence</span></span>
- <span data-ttu-id="6657e-960">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-960">Driver' Licences</span></span>
- <span data-ttu-id="6657e-961">driver' slic</span><span class="sxs-lookup"><span data-stu-id="6657e-961">Driver'sLic</span></span>
- <span data-ttu-id="6657e-962">driver' slics</span><span class="sxs-lookup"><span data-stu-id="6657e-962">Driver'sLics</span></span>
- <span data-ttu-id="6657e-963">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-963">Driver'sLicense</span></span>
- <span data-ttu-id="6657e-964">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-964">Driver'sLicenses</span></span>
- <span data-ttu-id="6657e-965">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="6657e-965">Driver'sLicence</span></span>
- <span data-ttu-id="6657e-966">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="6657e-966">Driver'sLicences</span></span>
- <span data-ttu-id="6657e-967">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-967">Driver's Lic</span></span>
- <span data-ttu-id="6657e-968">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-968">Driver's Lics</span></span>
- <span data-ttu-id="6657e-969">Driver's License</span><span class="sxs-lookup"><span data-stu-id="6657e-969">Driver's License</span></span>
- <span data-ttu-id="6657e-970">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-970">Driver's Licenses</span></span>
- <span data-ttu-id="6657e-971">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-971">Driver's Licence</span></span>
- <span data-ttu-id="6657e-972">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-972">Driver's Licences</span></span>
- <span data-ttu-id="6657e-973">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="6657e-973">Permis de Conduire</span></span>
- <span data-ttu-id="6657e-974">id</span><span class="sxs-lookup"><span data-stu-id="6657e-974">id</span></span>
- <span data-ttu-id="6657e-975">ids</span><span class="sxs-lookup"><span data-stu-id="6657e-975">ids</span></span>
- <span data-ttu-id="6657e-976">idcard number</span><span class="sxs-lookup"><span data-stu-id="6657e-976">idcard number</span></span>
- <span data-ttu-id="6657e-977">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-977">idcard numbers</span></span>
- <span data-ttu-id="6657e-978">idcard #</span><span class="sxs-lookup"><span data-stu-id="6657e-978">idcard #</span></span>
- <span data-ttu-id="6657e-979">idcard #s</span><span class="sxs-lookup"><span data-stu-id="6657e-979">idcard #s</span></span>
- <span data-ttu-id="6657e-980">idcard card</span><span class="sxs-lookup"><span data-stu-id="6657e-980">idcard card</span></span>
- <span data-ttu-id="6657e-981">idcard cards</span><span class="sxs-lookup"><span data-stu-id="6657e-981">idcard cards</span></span>
- <span data-ttu-id="6657e-982">idcard</span><span class="sxs-lookup"><span data-stu-id="6657e-982">idcard</span></span>
- <span data-ttu-id="6657e-983">identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-983">identification number</span></span>
- <span data-ttu-id="6657e-984">identification numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-984">identification numbers</span></span>
- <span data-ttu-id="6657e-985">identification #</span><span class="sxs-lookup"><span data-stu-id="6657e-985">identification #</span></span>
- <span data-ttu-id="6657e-986">identification #s</span><span class="sxs-lookup"><span data-stu-id="6657e-986">identification #s</span></span>
- <span data-ttu-id="6657e-987">identification card</span><span class="sxs-lookup"><span data-stu-id="6657e-987">identification card</span></span>
- <span data-ttu-id="6657e-988">identification cards</span><span class="sxs-lookup"><span data-stu-id="6657e-988">identification cards</span></span>
- <span data-ttu-id="6657e-989">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-989">identification</span></span> 
- <span data-ttu-id="6657e-990">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-990">DL#</span></span>
- <span data-ttu-id="6657e-991">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-991">DLS#</span></span> 
- <span data-ttu-id="6657e-992">CDL</span><span class="sxs-lookup"><span data-stu-id="6657e-992">CDL#</span></span> 
- <span data-ttu-id="6657e-993">cdls #</span><span class="sxs-lookup"><span data-stu-id="6657e-993">CDLS#</span></span> 
- <span data-ttu-id="6657e-994">driverlic #</span><span class="sxs-lookup"><span data-stu-id="6657e-994">DriverLic#</span></span> 
- <span data-ttu-id="6657e-995">driverlics #</span><span class="sxs-lookup"><span data-stu-id="6657e-995">DriverLics#</span></span> 
- <span data-ttu-id="6657e-996">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="6657e-996">DriverLicense#</span></span> 
- <span data-ttu-id="6657e-997">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="6657e-997">DriverLicenses#</span></span> 
- <span data-ttu-id="6657e-998">driverlicence #</span><span class="sxs-lookup"><span data-stu-id="6657e-998">DriverLicence#</span></span> 
- <span data-ttu-id="6657e-999">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="6657e-999">DriverLicences#</span></span> 
- <span data-ttu-id="6657e-1000">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-1000">Driver Lic#</span></span>
- <span data-ttu-id="6657e-1001">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-1001">Driver Lics#</span></span> 
- <span data-ttu-id="6657e-1002">Driver License#</span><span class="sxs-lookup"><span data-stu-id="6657e-1002">Driver License#</span></span> 
- <span data-ttu-id="6657e-1003">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-1003">Driver Licenses#</span></span> 
- <span data-ttu-id="6657e-1004">Driver License#</span><span class="sxs-lookup"><span data-stu-id="6657e-1004">Driver License#</span></span> 
- <span data-ttu-id="6657e-1005">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-1005">Driver Licences#</span></span> 
- <span data-ttu-id="6657e-1006">driverslic #</span><span class="sxs-lookup"><span data-stu-id="6657e-1006">DriversLic#</span></span> 
- <span data-ttu-id="6657e-1007">driverslics #</span><span class="sxs-lookup"><span data-stu-id="6657e-1007">DriversLics#</span></span> 
- <span data-ttu-id="6657e-1008">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-1008">DriversLicense#</span></span> 
- <span data-ttu-id="6657e-1009">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-1009">DriversLicenses#</span></span> 
- <span data-ttu-id="6657e-1010">のデモライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-1010">DriversLicence#</span></span> 
- <span data-ttu-id="6657e-1011">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="6657e-1011">DriversLicences#</span></span> 
- <span data-ttu-id="6657e-1012">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-1012">Drivers Lic#</span></span> 
- <span data-ttu-id="6657e-1013">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-1013">Drivers Lics#</span></span> 
- <span data-ttu-id="6657e-1014">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="6657e-1014">Drivers License#</span></span> 
- <span data-ttu-id="6657e-1015">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-1015">Drivers Licenses#</span></span> 
- <span data-ttu-id="6657e-1016">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-1016">Drivers Licence#</span></span> 
- <span data-ttu-id="6657e-1017">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-1017">Drivers Licences#</span></span> 
- <span data-ttu-id="6657e-1018">driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="6657e-1018">Driver'Lic#</span></span> 
- <span data-ttu-id="6657e-1019">driver' lics #</span><span class="sxs-lookup"><span data-stu-id="6657e-1019">Driver'Lics#</span></span> 
- <span data-ttu-id="6657e-1020">driver' License #</span><span class="sxs-lookup"><span data-stu-id="6657e-1020">Driver'License#</span></span> 
- <span data-ttu-id="6657e-1021">driver' Licenses #</span><span class="sxs-lookup"><span data-stu-id="6657e-1021">Driver'Licenses#</span></span> 
- <span data-ttu-id="6657e-1022">driver' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-1022">Driver'Licence#</span></span> 
- <span data-ttu-id="6657e-1023">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="6657e-1023">Driver'Licences#</span></span> 
- <span data-ttu-id="6657e-1024">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-1024">Driver' Lic#</span></span> 
- <span data-ttu-id="6657e-1025">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-1025">Driver' Lics#</span></span> 
- <span data-ttu-id="6657e-1026">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="6657e-1026">Driver' License#</span></span> 
- <span data-ttu-id="6657e-1027">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-1027">Driver' Licenses#</span></span> 
- <span data-ttu-id="6657e-1028">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-1028">Driver' Licence#</span></span> 
- <span data-ttu-id="6657e-1029">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-1029">Driver' Licences#</span></span> 
- <span data-ttu-id="6657e-1030">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="6657e-1030">Driver'sLic#</span></span> 
- <span data-ttu-id="6657e-1031">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="6657e-1031">Driver'sLics#</span></span> 
- <span data-ttu-id="6657e-1032">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1032">Driver'sLicense#</span></span> 
- <span data-ttu-id="6657e-1033">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-1033">Driver'sLicenses#</span></span> 
- <span data-ttu-id="6657e-1034">ドライバ ' スライスの持続性 #</span><span class="sxs-lookup"><span data-stu-id="6657e-1034">Driver'sLicence#</span></span> 
- <span data-ttu-id="6657e-1035">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="6657e-1035">Driver'sLicences#</span></span> 
- <span data-ttu-id="6657e-1036">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-1036">Driver's Lic#</span></span> 
- <span data-ttu-id="6657e-1037">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-1037">Driver's Lics#</span></span> 
- <span data-ttu-id="6657e-1038">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="6657e-1038">Driver's License#</span></span> 
- <span data-ttu-id="6657e-1039">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-1039">Driver's Licenses#</span></span> 
- <span data-ttu-id="6657e-1040">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="6657e-1040">Driver's Licence#</span></span> 
- <span data-ttu-id="6657e-1041">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="6657e-1041">Driver's Licences#</span></span> 
- <span data-ttu-id="6657e-1042">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="6657e-1042">Permis de Conduire#</span></span> 
- <span data-ttu-id="6657e-1043">rid</span><span class="sxs-lookup"><span data-stu-id="6657e-1043">id#</span></span> 
- <span data-ttu-id="6657e-1044">rid</span><span class="sxs-lookup"><span data-stu-id="6657e-1044">ids#</span></span> 
- <span data-ttu-id="6657e-1045">idcard card#</span><span class="sxs-lookup"><span data-stu-id="6657e-1045">idcard card#</span></span> 
- <span data-ttu-id="6657e-1046">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="6657e-1046">idcard cards#</span></span> 
- <span data-ttu-id="6657e-1047">idcard #</span><span class="sxs-lookup"><span data-stu-id="6657e-1047">idcard#</span></span> 
- <span data-ttu-id="6657e-1048">identification card#</span><span class="sxs-lookup"><span data-stu-id="6657e-1048">identification card#</span></span> 
- <span data-ttu-id="6657e-1049">identification cards#</span><span class="sxs-lookup"><span data-stu-id="6657e-1049">identification cards#</span></span> 
- <span data-ttu-id="6657e-1050">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-1050">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="6657e-1051">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1051">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1052">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1052">Format</span></span>

<span data-ttu-id="6657e-1053">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1053">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1054">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1054">Pattern</span></span>

<span data-ttu-id="6657e-1055">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1055">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1056">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1056">Checksum</span></span>

<span data-ttu-id="6657e-1057">無</span><span class="sxs-lookup"><span data-stu-id="6657e-1057">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1058">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1058">Definition</span></span>

<span data-ttu-id="6657e-1059">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1059">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1060">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1060">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1061">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1061">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1062">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1062">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="6657e-1063">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="6657e-1063">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="6657e-1064">personal health number</span><span class="sxs-lookup"><span data-stu-id="6657e-1064">personal health number</span></span>
- <span data-ttu-id="6657e-1065">patient information</span><span class="sxs-lookup"><span data-stu-id="6657e-1065">patient information</span></span>
- <span data-ttu-id="6657e-1066">health services</span><span class="sxs-lookup"><span data-stu-id="6657e-1066">health services</span></span>
- <span data-ttu-id="6657e-1067">speciality services</span><span class="sxs-lookup"><span data-stu-id="6657e-1067">speciality services</span></span>
- <span data-ttu-id="6657e-1068">automobile accident</span><span class="sxs-lookup"><span data-stu-id="6657e-1068">automobile accident</span></span>
- <span data-ttu-id="6657e-1069">patient hospital</span><span class="sxs-lookup"><span data-stu-id="6657e-1069">patient hospital</span></span>
- <span data-ttu-id="6657e-1070">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="6657e-1070">psychiatrist</span></span>
- <span data-ttu-id="6657e-1071">workers compensation</span><span class="sxs-lookup"><span data-stu-id="6657e-1071">workers compensation</span></span>
- <span data-ttu-id="6657e-1072">身体</span><span class="sxs-lookup"><span data-stu-id="6657e-1072">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="6657e-1073">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1073">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1074">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1074">Format</span></span>

<span data-ttu-id="6657e-1075">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1075">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1076">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1076">Pattern</span></span>

<span data-ttu-id="6657e-1077">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1077">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1078">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1078">Checksum</span></span>

<span data-ttu-id="6657e-1079">無</span><span class="sxs-lookup"><span data-stu-id="6657e-1079">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1080">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1080">Definition</span></span>

<span data-ttu-id="6657e-1081">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1081">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1082">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1082">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1083">Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1083">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1084">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1084">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="6657e-1085">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="6657e-1085">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="6657e-1086">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="6657e-1086">canadian citizenship</span></span>
- <span data-ttu-id="6657e-1087">canadian passport</span><span class="sxs-lookup"><span data-stu-id="6657e-1087">canadian passport</span></span>
- <span data-ttu-id="6657e-1088">passport application</span><span class="sxs-lookup"><span data-stu-id="6657e-1088">passport application</span></span>
- <span data-ttu-id="6657e-1089">passport photos</span><span class="sxs-lookup"><span data-stu-id="6657e-1089">passport photos</span></span>
- <span data-ttu-id="6657e-1090">certified translator</span><span class="sxs-lookup"><span data-stu-id="6657e-1090">certified translator</span></span>
- <span data-ttu-id="6657e-1091">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="6657e-1091">canadian citizens</span></span>
- <span data-ttu-id="6657e-1092">processing times</span><span class="sxs-lookup"><span data-stu-id="6657e-1092">processing times</span></span>
- <span data-ttu-id="6657e-1093">renewal application</span><span class="sxs-lookup"><span data-stu-id="6657e-1093">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6657e-1094">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-1094">Keyword_passport</span></span>

- <span data-ttu-id="6657e-1095">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6657e-1095">Passport Number</span></span>
- <span data-ttu-id="6657e-1096">Passport No</span><span class="sxs-lookup"><span data-stu-id="6657e-1096">Passport No</span></span>
- <span data-ttu-id="6657e-1097">Passport #</span><span class="sxs-lookup"><span data-stu-id="6657e-1097">Passport #</span></span>
- <span data-ttu-id="6657e-1098">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-1098">Passport#</span></span>
- <span data-ttu-id="6657e-1099">PassportID</span><span class="sxs-lookup"><span data-stu-id="6657e-1099">PassportID</span></span>
- <span data-ttu-id="6657e-1100">Passportno</span><span class="sxs-lookup"><span data-stu-id="6657e-1100">Passportno</span></span>
- <span data-ttu-id="6657e-1101">passportnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-1101">passportnumber</span></span>
- <span data-ttu-id="6657e-1102">パスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-1102">パスポート</span></span>
- <span data-ttu-id="6657e-1103">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1103">パスポート番号</span></span>
- <span data-ttu-id="6657e-1104">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="6657e-1104">パスポートのNum</span></span>
- <span data-ttu-id="6657e-1105">パスポート #</span><span class="sxs-lookup"><span data-stu-id="6657e-1105">パスポート＃</span></span>
- <span data-ttu-id="6657e-1106">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6657e-1106">Numéro de passeport</span></span>
- <span data-ttu-id="6657e-1107">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6657e-1107">Passeport n °</span></span>
- <span data-ttu-id="6657e-1108">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="6657e-1108">Passeport Non</span></span>
- <span data-ttu-id="6657e-1109">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-1109">Passeport #</span></span>
- <span data-ttu-id="6657e-1110">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-1110">Passeport#</span></span>
- <span data-ttu-id="6657e-1111">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6657e-1111">PasseportNon</span></span>
- <span data-ttu-id="6657e-1112">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6657e-1112">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="6657e-1113">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="6657e-1113">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1114">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1114">Format</span></span>

<span data-ttu-id="6657e-1115">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1115">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1116">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1116">Pattern</span></span>

<span data-ttu-id="6657e-1117">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1117">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1118">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1118">Checksum</span></span>

<span data-ttu-id="6657e-1119">無</span><span class="sxs-lookup"><span data-stu-id="6657e-1119">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1120">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1120">Definition</span></span>

<span data-ttu-id="6657e-1121">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-1122">Keyword_canada_phin または Keyword_canada_provinces から、少なくとも2つのキーワードが見つかります。</span><span class="sxs-lookup"><span data-stu-id="6657e-1122">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1123">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1123">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="6657e-1124">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="6657e-1124">Keyword_canada_phin</span></span>

- <span data-ttu-id="6657e-1125">social insurance number</span><span class="sxs-lookup"><span data-stu-id="6657e-1125">social insurance number</span></span>
- <span data-ttu-id="6657e-1126">health information act</span><span class="sxs-lookup"><span data-stu-id="6657e-1126">health information act</span></span>
- <span data-ttu-id="6657e-1127">income tax information</span><span class="sxs-lookup"><span data-stu-id="6657e-1127">income tax information</span></span>
- <span data-ttu-id="6657e-1128">manitoba health</span><span class="sxs-lookup"><span data-stu-id="6657e-1128">manitoba health</span></span>
- <span data-ttu-id="6657e-1129">health registration</span><span class="sxs-lookup"><span data-stu-id="6657e-1129">health registration</span></span>
- <span data-ttu-id="6657e-1130">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="6657e-1130">prescription purchases</span></span>
- <span data-ttu-id="6657e-1131">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="6657e-1131">benefit eligibility</span></span>
- <span data-ttu-id="6657e-1132">personal health</span><span class="sxs-lookup"><span data-stu-id="6657e-1132">personal health</span></span>
- <span data-ttu-id="6657e-1133">power of attorney</span><span class="sxs-lookup"><span data-stu-id="6657e-1133">power of attorney</span></span>
- <span data-ttu-id="6657e-1134">registration number</span><span class="sxs-lookup"><span data-stu-id="6657e-1134">registration number</span></span>
- <span data-ttu-id="6657e-1135">personal health number</span><span class="sxs-lookup"><span data-stu-id="6657e-1135">personal health number</span></span>
- <span data-ttu-id="6657e-1136">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="6657e-1136">practitioner referral</span></span>
- <span data-ttu-id="6657e-1137">wellness professional</span><span class="sxs-lookup"><span data-stu-id="6657e-1137">wellness professional</span></span>
- <span data-ttu-id="6657e-1138">patient referral</span><span class="sxs-lookup"><span data-stu-id="6657e-1138">patient referral</span></span>
- <span data-ttu-id="6657e-1139">health and wellness</span><span class="sxs-lookup"><span data-stu-id="6657e-1139">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="6657e-1140">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="6657e-1140">Keyword_canada_provinces</span></span>

- <span data-ttu-id="6657e-1141">Nunavut</span><span class="sxs-lookup"><span data-stu-id="6657e-1141">Nunavut</span></span>
- <span data-ttu-id="6657e-1142">州</span><span class="sxs-lookup"><span data-stu-id="6657e-1142">Quebec</span></span>
- <span data-ttu-id="6657e-1143">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="6657e-1143">Northwest Territories</span></span>
- <span data-ttu-id="6657e-1144">オンタリオ州</span><span class="sxs-lookup"><span data-stu-id="6657e-1144">Ontario</span></span>
- <span data-ttu-id="6657e-1145">British Columbia</span><span class="sxs-lookup"><span data-stu-id="6657e-1145">British Columbia</span></span>
- <span data-ttu-id="6657e-1146">州</span><span class="sxs-lookup"><span data-stu-id="6657e-1146">Alberta</span></span>
- <span data-ttu-id="6657e-1147">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="6657e-1147">Saskatchewan</span></span>
- <span data-ttu-id="6657e-1148">マニトバ州</span><span class="sxs-lookup"><span data-stu-id="6657e-1148">Manitoba</span></span>
- <span data-ttu-id="6657e-1149">州</span><span class="sxs-lookup"><span data-stu-id="6657e-1149">Yukon</span></span>
- <span data-ttu-id="6657e-1150">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="6657e-1150">Newfoundland and Labrador</span></span>
- <span data-ttu-id="6657e-1151">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="6657e-1151">New Brunswick</span></span>
- <span data-ttu-id="6657e-1152">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="6657e-1152">Nova Scotia</span></span>
- <span data-ttu-id="6657e-1153">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="6657e-1153">Prince Edward Island</span></span>
- <span data-ttu-id="6657e-1154">カナダ</span><span class="sxs-lookup"><span data-stu-id="6657e-1154">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="6657e-1155">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1155">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1156">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1156">Format</span></span>

<span data-ttu-id="6657e-1157">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-1157">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1158">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1158">Pattern</span></span>

<span data-ttu-id="6657e-1159">さ</span><span class="sxs-lookup"><span data-stu-id="6657e-1159">Formatted:</span></span>
- <span data-ttu-id="6657e-1160">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1160">Three digits</span></span> 
- <span data-ttu-id="6657e-1161">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-1161">A hyphen or space</span></span> 
- <span data-ttu-id="6657e-1162">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1162">Three digits</span></span> 
- <span data-ttu-id="6657e-1163">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-1163">A hyphen or space</span></span> 
- <span data-ttu-id="6657e-1164">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1164">Three digits</span></span>

<span data-ttu-id="6657e-1165">書式なし: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1165">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1166">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1166">Checksum</span></span>

<span data-ttu-id="6657e-1167">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1167">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1168">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1168">Definition</span></span>

<span data-ttu-id="6657e-1169">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1169">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1170">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1170">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1171">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-1171">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="6657e-1172">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1172">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="6657e-1173">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1173">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="6657e-1174">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1174">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6657e-1175">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1175">The checksum passes.</span></span>

<span data-ttu-id="6657e-1176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1177">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1177">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1178">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1178">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="6657e-1179">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1179">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1180">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1180">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="6657e-1181">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="6657e-1181">Keyword_sin</span></span>

- <span data-ttu-id="6657e-1182">sin</span><span class="sxs-lookup"><span data-stu-id="6657e-1182">sin</span></span> 
- <span data-ttu-id="6657e-1183">social insurance</span><span class="sxs-lookup"><span data-stu-id="6657e-1183">social insurance</span></span> 
- <span data-ttu-id="6657e-1184">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="6657e-1184">numero d'assurance sociale</span></span> 
- <span data-ttu-id="6657e-1185">大罪</span><span class="sxs-lookup"><span data-stu-id="6657e-1185">sins</span></span> 
- <span data-ttu-id="6657e-1186">ssn</span><span class="sxs-lookup"><span data-stu-id="6657e-1186">ssn</span></span> 
- <span data-ttu-id="6657e-1187">ssn</span><span class="sxs-lookup"><span data-stu-id="6657e-1187">ssns</span></span> 
- <span data-ttu-id="6657e-1188">social security</span><span class="sxs-lookup"><span data-stu-id="6657e-1188">social security</span></span> 
- <span data-ttu-id="6657e-1189">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="6657e-1189">numero d'assurance social</span></span> 
- <span data-ttu-id="6657e-1190">national identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-1190">national identification number</span></span> 
- <span data-ttu-id="6657e-1191">national id</span><span class="sxs-lookup"><span data-stu-id="6657e-1191">national id</span></span> 
- <span data-ttu-id="6657e-1192">sin</span><span class="sxs-lookup"><span data-stu-id="6657e-1192">sin#</span></span> 
- <span data-ttu-id="6657e-1193">soc ins</span><span class="sxs-lookup"><span data-stu-id="6657e-1193">soc ins</span></span> 
- <span data-ttu-id="6657e-1194">social ins</span><span class="sxs-lookup"><span data-stu-id="6657e-1194">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="6657e-1195">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="6657e-1195">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="6657e-1196">driver's license</span><span class="sxs-lookup"><span data-stu-id="6657e-1196">driver's license</span></span> 
- <span data-ttu-id="6657e-1197">drivers license</span><span class="sxs-lookup"><span data-stu-id="6657e-1197">drivers license</span></span> 
- <span data-ttu-id="6657e-1198">driver's licence</span><span class="sxs-lookup"><span data-stu-id="6657e-1198">driver's licence</span></span> 
- <span data-ttu-id="6657e-1199">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6657e-1199">drivers licence</span></span> 
- <span data-ttu-id="6657e-1200">dob</span><span class="sxs-lookup"><span data-stu-id="6657e-1200">DOB</span></span> 
- <span data-ttu-id="6657e-1201">誕生日</span><span class="sxs-lookup"><span data-stu-id="6657e-1201">Birthdate</span></span> 
- <span data-ttu-id="6657e-1202">Birthday</span><span class="sxs-lookup"><span data-stu-id="6657e-1202">Birthday</span></span> 
- <span data-ttu-id="6657e-1203">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="6657e-1203">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="6657e-1204">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1204">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1205">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1205">Format</span></span>

<span data-ttu-id="6657e-1206">7-8 桁の数字と区切り文字のチェックディジットまたは文字</span><span class="sxs-lookup"><span data-stu-id="6657e-1206">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1207">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1207">Pattern</span></span>

<span data-ttu-id="6657e-1208">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="6657e-1208">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="6657e-1209">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-1209">1-2 digits</span></span> 
- <span data-ttu-id="6657e-1210">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-1210">A period</span></span> 
- <span data-ttu-id="6657e-1211">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1211">Three digits</span></span> 
- <span data-ttu-id="6657e-1212">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-1212">A period</span></span> 
- <span data-ttu-id="6657e-1213">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1213">Three digits</span></span> 
- <span data-ttu-id="6657e-1214">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-1214">A dash</span></span> 
- <span data-ttu-id="6657e-1215">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="6657e-1215">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1216">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1216">Checksum</span></span>

<span data-ttu-id="6657e-1217">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1217">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1218">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1218">Definition</span></span>

<span data-ttu-id="6657e-1219">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1219">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1220">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1220">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1221">Keyword_chile_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1221">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="6657e-1222">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1222">The checksum passes.</span></span>

<span data-ttu-id="6657e-1223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1224">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1224">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1225">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1225">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1226">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1226">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="6657e-1227">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="6657e-1227">Keyword_chile_id_card</span></span>

- <span data-ttu-id="6657e-1228">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="6657e-1228">National Identification Number</span></span> 
- <span data-ttu-id="6657e-1229">Identity card</span><span class="sxs-lookup"><span data-stu-id="6657e-1229">Identity card</span></span> 
- <span data-ttu-id="6657e-1230">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-1230">ID</span></span> 
- <span data-ttu-id="6657e-1231">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-1231">Identification</span></span> 
- <span data-ttu-id="6657e-1232">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="6657e-1232">Rol Único Nacional</span></span> 
- <span data-ttu-id="6657e-1233">実行</span><span class="sxs-lookup"><span data-stu-id="6657e-1233">RUN</span></span> 
- <span data-ttu-id="6657e-1234">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="6657e-1234">Rol Único Tributario</span></span> 
- <span data-ttu-id="6657e-1235">類型</span><span class="sxs-lookup"><span data-stu-id="6657e-1235">RUT</span></span> 
- <span data-ttu-id="6657e-1236">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="6657e-1236">Cédula de Identidad</span></span> 
- <span data-ttu-id="6657e-1237">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="6657e-1237">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="6657e-1238">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="6657e-1238">Tarjeta de identificación</span></span> 
- <span data-ttu-id="6657e-1239">Identificación</span><span class="sxs-lookup"><span data-stu-id="6657e-1239">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="6657e-1240">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1240">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1241">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1241">Format</span></span>

<span data-ttu-id="6657e-1242">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1242">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1243">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1243">Pattern</span></span>

<span data-ttu-id="6657e-1244">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-1244">18 digits:</span></span>
- <span data-ttu-id="6657e-1245">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-1245">Six digits which are an address code</span></span> 
- <span data-ttu-id="6657e-1246">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-1246">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6657e-1247">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-1247">Three digits which are an order code</span></span> 
- <span data-ttu-id="6657e-1248">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1248">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1249">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1249">Checksum</span></span>

<span data-ttu-id="6657e-1250">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1250">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1251">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1251">Definition</span></span>

<span data-ttu-id="6657e-1252">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1252">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1253">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1253">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1254">Keyword_china_resident_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1254">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="6657e-1255">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1255">The checksum passes.</span></span>

<span data-ttu-id="6657e-1256">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1256">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1257">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1257">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1258">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1258">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1259">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1259">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="6657e-1260">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="6657e-1260">Keyword_china_resident_id</span></span>

- <span data-ttu-id="6657e-1261">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="6657e-1261">Resident Identity Card</span></span> 
- <span data-ttu-id="6657e-1262">PRC</span><span class="sxs-lookup"><span data-stu-id="6657e-1262">PRC</span></span> 
- <span data-ttu-id="6657e-1263">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="6657e-1263">National Identification Card</span></span> 
- <span data-ttu-id="6657e-1264">身份证</span><span class="sxs-lookup"><span data-stu-id="6657e-1264">身份证</span></span> 
- <span data-ttu-id="6657e-1265">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="6657e-1265">居民 身份证</span></span> 
- <span data-ttu-id="6657e-1266">居民身份证</span><span class="sxs-lookup"><span data-stu-id="6657e-1266">居民身份证</span></span> 
- <span data-ttu-id="6657e-1267">鉴定</span><span class="sxs-lookup"><span data-stu-id="6657e-1267">鉴定</span></span> 
- <span data-ttu-id="6657e-1268">身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-1268">身分證</span></span> 
- <span data-ttu-id="6657e-1269">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-1269">居民 身份證</span></span>
- <span data-ttu-id="6657e-1270">鑑定</span><span class="sxs-lookup"><span data-stu-id="6657e-1270">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="6657e-1271">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1271">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1272">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1272">Format</span></span>

<span data-ttu-id="6657e-1273">書式設定または書式設定ができない16桁の数字 (dddddddddddddddd)。 luhn テストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-1273">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1274">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1274">Pattern</span></span>

<span data-ttu-id="6657e-1275">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="6657e-1275">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1276">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1276">Checksum</span></span>

<span data-ttu-id="6657e-1277">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="6657e-1277">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1278">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1278">Definition</span></span>

<span data-ttu-id="6657e-1279">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1279">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1280">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1280">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1281">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-1281">One of the following is true:</span></span>
    - <span data-ttu-id="6657e-1282">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1282">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="6657e-1283">Keyword_cc_name からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1283">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="6657e-1284">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1284">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6657e-1285">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1285">The checksum passes.</span></span>

<span data-ttu-id="6657e-1286">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1286">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1287">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1287">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1288">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1288">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1289">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1289">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="6657e-1290">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="6657e-1290">Keyword_cc_verification</span></span>

- <span data-ttu-id="6657e-1291">card verification</span><span class="sxs-lookup"><span data-stu-id="6657e-1291">card verification</span></span>
- <span data-ttu-id="6657e-1292">card identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-1292">card identification number</span></span>
- <span data-ttu-id="6657e-1293">cvn</span><span class="sxs-lookup"><span data-stu-id="6657e-1293">cvn</span></span>
- <span data-ttu-id="6657e-1294">cid</span><span class="sxs-lookup"><span data-stu-id="6657e-1294">cid</span></span>
- <span data-ttu-id="6657e-1295">cvc2</span><span class="sxs-lookup"><span data-stu-id="6657e-1295">cvc2</span></span>
- <span data-ttu-id="6657e-1296">cvv2</span><span class="sxs-lookup"><span data-stu-id="6657e-1296">cvv2</span></span>
- <span data-ttu-id="6657e-1297">pin block</span><span class="sxs-lookup"><span data-stu-id="6657e-1297">pin block</span></span>
- <span data-ttu-id="6657e-1298">security code</span><span class="sxs-lookup"><span data-stu-id="6657e-1298">security code</span></span>
- <span data-ttu-id="6657e-1299">security number</span><span class="sxs-lookup"><span data-stu-id="6657e-1299">security number</span></span>
- <span data-ttu-id="6657e-1300">security no</span><span class="sxs-lookup"><span data-stu-id="6657e-1300">security no</span></span>
- <span data-ttu-id="6657e-1301">issue number</span><span class="sxs-lookup"><span data-stu-id="6657e-1301">issue number</span></span>
- <span data-ttu-id="6657e-1302">issue no</span><span class="sxs-lookup"><span data-stu-id="6657e-1302">issue no</span></span>
- <span data-ttu-id="6657e-1303">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="6657e-1303">cryptogramme</span></span>
- <span data-ttu-id="6657e-1304">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="6657e-1304">numéro de sécurité</span></span>
- <span data-ttu-id="6657e-1305">numero de securite</span><span class="sxs-lookup"><span data-stu-id="6657e-1305">numero de securite</span></span>
- <span data-ttu-id="6657e-1306">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1306">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="6657e-1307">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1307">kreditkartenprufnummer</span></span>
- <span data-ttu-id="6657e-1308">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="6657e-1308">prüfziffer</span></span>
- <span data-ttu-id="6657e-1309">prufziffer</span><span class="sxs-lookup"><span data-stu-id="6657e-1309">prufziffer</span></span>
- <span data-ttu-id="6657e-1310">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="6657e-1310">sicherheits Kode</span></span>
- <span data-ttu-id="6657e-1311">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="6657e-1311">sicherheitscode</span></span>
- <span data-ttu-id="6657e-1312">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1312">sicherheitsnummer</span></span>
- <span data-ttu-id="6657e-1313">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1313">verfalldatum</span></span>
- <span data-ttu-id="6657e-1314">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="6657e-1314">codice di verifica</span></span>
- <span data-ttu-id="6657e-1315">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1315">cod.</span></span> <span data-ttu-id="6657e-1316">sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1316">sicurezza</span></span>
- <span data-ttu-id="6657e-1317">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1317">cod sicurezza</span></span>
- <span data-ttu-id="6657e-1318">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6657e-1318">n autorizzazione</span></span>
- <span data-ttu-id="6657e-1319">código</span><span class="sxs-lookup"><span data-stu-id="6657e-1319">código</span></span>
- <span data-ttu-id="6657e-1320">codigo</span><span class="sxs-lookup"><span data-stu-id="6657e-1320">codigo</span></span>
- <span data-ttu-id="6657e-1321">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1321">cod.</span></span> <span data-ttu-id="6657e-1322">seg</span><span class="sxs-lookup"><span data-stu-id="6657e-1322">seg</span></span>
- <span data-ttu-id="6657e-1323">cod seg</span><span class="sxs-lookup"><span data-stu-id="6657e-1323">cod seg</span></span>
- <span data-ttu-id="6657e-1324">código de segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1324">código de segurança</span></span>
- <span data-ttu-id="6657e-1325">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1325">codigo de seguranca</span></span>
- <span data-ttu-id="6657e-1326">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1326">codigo de segurança</span></span>
- <span data-ttu-id="6657e-1327">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1327">código de seguranca</span></span>
- <span data-ttu-id="6657e-1328">cód。</span><span class="sxs-lookup"><span data-stu-id="6657e-1328">cód.</span></span> <span data-ttu-id="6657e-1329">segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1329">segurança</span></span>
- <span data-ttu-id="6657e-1330">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1330">cod.</span></span> <span data-ttu-id="6657e-1331">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="6657e-1331">seguranca cod.</span></span> <span data-ttu-id="6657e-1332">segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1332">segurança</span></span>
- <span data-ttu-id="6657e-1333">cód。</span><span class="sxs-lookup"><span data-stu-id="6657e-1333">cód.</span></span> <span data-ttu-id="6657e-1334">seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1334">seguranca</span></span>
- <span data-ttu-id="6657e-1335">cód segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1335">cód segurança</span></span>
- <span data-ttu-id="6657e-1336">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1336">cod seguranca cod segurança</span></span>
- <span data-ttu-id="6657e-1337">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1337">cód seguranca</span></span>
- <span data-ttu-id="6657e-1338">número de verificação</span><span class="sxs-lookup"><span data-stu-id="6657e-1338">número de verificação</span></span>
- <span data-ttu-id="6657e-1339">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="6657e-1339">numero de verificacao</span></span>
- <span data-ttu-id="6657e-1340">ablん f</span><span class="sxs-lookup"><span data-stu-id="6657e-1340">ablauf</span></span>
- <span data-ttu-id="6657e-1341">gültig bis</span><span class="sxs-lookup"><span data-stu-id="6657e-1341">gültig bis</span></span>
- <span data-ttu-id="6657e-1342">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1342">gültigkeitsdatum</span></span>
- <span data-ttu-id="6657e-1343">gultig bis</span><span class="sxs-lookup"><span data-stu-id="6657e-1343">gultig bis</span></span>
- <span data-ttu-id="6657e-1344">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1344">gultigkeitsdatum</span></span>
- <span data-ttu-id="6657e-1345">scadenza</span><span class="sxs-lookup"><span data-stu-id="6657e-1345">scadenza</span></span>
- <span data-ttu-id="6657e-1346">data scad</span><span class="sxs-lookup"><span data-stu-id="6657e-1346">data scad</span></span>
- <span data-ttu-id="6657e-1347">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="6657e-1347">fecha de expiracion</span></span>
- <span data-ttu-id="6657e-1348">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="6657e-1348">fecha de venc</span></span>
- <span data-ttu-id="6657e-1349">vencimiento</span><span class="sxs-lookup"><span data-stu-id="6657e-1349">vencimiento</span></span>
- <span data-ttu-id="6657e-1350">válido hasta</span><span class="sxs-lookup"><span data-stu-id="6657e-1350">válido hasta</span></span>
- <span data-ttu-id="6657e-1351">valido hasta</span><span class="sxs-lookup"><span data-stu-id="6657e-1351">valido hasta</span></span>
- <span data-ttu-id="6657e-1352">vto</span><span class="sxs-lookup"><span data-stu-id="6657e-1352">vto</span></span>
- <span data-ttu-id="6657e-1353">data de expiração</span><span class="sxs-lookup"><span data-stu-id="6657e-1353">data de expiração</span></span>
- <span data-ttu-id="6657e-1354">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="6657e-1354">data de expiracao</span></span>
- <span data-ttu-id="6657e-1355">data em que expira</span><span class="sxs-lookup"><span data-stu-id="6657e-1355">data em que expira</span></span>
- <span data-ttu-id="6657e-1356">validade</span><span class="sxs-lookup"><span data-stu-id="6657e-1356">validade</span></span>
- <span data-ttu-id="6657e-1357">valor は</span><span class="sxs-lookup"><span data-stu-id="6657e-1357">valor</span></span>
- <span data-ttu-id="6657e-1358">vencimento</span><span class="sxs-lookup"><span data-stu-id="6657e-1358">vencimento</span></span>
- <span data-ttu-id="6657e-1359">venc</span><span class="sxs-lookup"><span data-stu-id="6657e-1359">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="6657e-1360">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="6657e-1360">Keyword_cc_name</span></span>

- <span data-ttu-id="6657e-1361">amex</span><span class="sxs-lookup"><span data-stu-id="6657e-1361">amex</span></span>
- <span data-ttu-id="6657e-1362">american express</span><span class="sxs-lookup"><span data-stu-id="6657e-1362">american express</span></span>
- <span data-ttu-id="6657e-1363">americanexpress</span><span class="sxs-lookup"><span data-stu-id="6657e-1363">americanexpress</span></span>
- <span data-ttu-id="6657e-1364">Visa</span><span class="sxs-lookup"><span data-stu-id="6657e-1364">Visa</span></span>
- <span data-ttu-id="6657e-1365">mastercard</span><span class="sxs-lookup"><span data-stu-id="6657e-1365">mastercard</span></span>
- <span data-ttu-id="6657e-1366">master card</span><span class="sxs-lookup"><span data-stu-id="6657e-1366">master card</span></span>
- <span data-ttu-id="6657e-1367">mc</span><span class="sxs-lookup"><span data-stu-id="6657e-1367">mc</span></span> 
- <span data-ttu-id="6657e-1368">mastercards</span><span class="sxs-lookup"><span data-stu-id="6657e-1368">mastercards</span></span>
- <span data-ttu-id="6657e-1369">master cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1369">master cards</span></span>
- <span data-ttu-id="6657e-1370">diner's Club</span><span class="sxs-lookup"><span data-stu-id="6657e-1370">diner's Club</span></span>
- <span data-ttu-id="6657e-1371">diners club</span><span class="sxs-lookup"><span data-stu-id="6657e-1371">diners club</span></span>
- <span data-ttu-id="6657e-1372">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="6657e-1372">dinersclub</span></span>
- <span data-ttu-id="6657e-1373">discover card</span><span class="sxs-lookup"><span data-stu-id="6657e-1373">discover card</span></span>
- <span data-ttu-id="6657e-1374">discovercard</span><span class="sxs-lookup"><span data-stu-id="6657e-1374">discovercard</span></span>
- <span data-ttu-id="6657e-1375">discover cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1375">discover cards</span></span>
- <span data-ttu-id="6657e-1376">JCB</span><span class="sxs-lookup"><span data-stu-id="6657e-1376">JCB</span></span>
- <span data-ttu-id="6657e-1377">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="6657e-1377">japanese card bureau</span></span>
- <span data-ttu-id="6657e-1378">carte blanche</span><span class="sxs-lookup"><span data-stu-id="6657e-1378">carte blanche</span></span>
- <span data-ttu-id="6657e-1379">carteblanche</span><span class="sxs-lookup"><span data-stu-id="6657e-1379">carteblanche</span></span>
- <span data-ttu-id="6657e-1380">credit card</span><span class="sxs-lookup"><span data-stu-id="6657e-1380">credit card</span></span>
- <span data-ttu-id="6657e-1381">]</span><span class="sxs-lookup"><span data-stu-id="6657e-1381">cc#</span></span>
- <span data-ttu-id="6657e-1382">cc #:</span><span class="sxs-lookup"><span data-stu-id="6657e-1382">cc#:</span></span>
- <span data-ttu-id="6657e-1383">expiration date</span><span class="sxs-lookup"><span data-stu-id="6657e-1383">expiration date</span></span>
- <span data-ttu-id="6657e-1384">exp date</span><span class="sxs-lookup"><span data-stu-id="6657e-1384">exp date</span></span>
- <span data-ttu-id="6657e-1385">expiry date</span><span class="sxs-lookup"><span data-stu-id="6657e-1385">expiry date</span></span>
- <span data-ttu-id="6657e-1386">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="6657e-1386">date d’expiration</span></span>
- <span data-ttu-id="6657e-1387">date d'exp</span><span class="sxs-lookup"><span data-stu-id="6657e-1387">date d'exp</span></span>
- <span data-ttu-id="6657e-1388">date expiration</span><span class="sxs-lookup"><span data-stu-id="6657e-1388">date expiration</span></span>
- <span data-ttu-id="6657e-1389">bank card</span><span class="sxs-lookup"><span data-stu-id="6657e-1389">bank card</span></span>
- <span data-ttu-id="6657e-1390">bankcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1390">bankcard</span></span>
- <span data-ttu-id="6657e-1391">card number</span><span class="sxs-lookup"><span data-stu-id="6657e-1391">card number</span></span>
- <span data-ttu-id="6657e-1392">card num</span><span class="sxs-lookup"><span data-stu-id="6657e-1392">card num</span></span>
- <span data-ttu-id="6657e-1393">カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1393">cardnumber</span></span>
- <span data-ttu-id="6657e-1394">カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1394">cardnumbers</span></span>
- <span data-ttu-id="6657e-1395">card numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-1395">card numbers</span></span>
- <span data-ttu-id="6657e-1396">creditcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1396">creditcard</span></span>
- <span data-ttu-id="6657e-1397">credit cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1397">credit cards</span></span>
- <span data-ttu-id="6657e-1398">creditcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1398">creditcards</span></span>
- <span data-ttu-id="6657e-1399">ccn</span><span class="sxs-lookup"><span data-stu-id="6657e-1399">ccn</span></span>
- <span data-ttu-id="6657e-1400">card holder</span><span class="sxs-lookup"><span data-stu-id="6657e-1400">card holder</span></span>
- <span data-ttu-id="6657e-1401">所有者</span><span class="sxs-lookup"><span data-stu-id="6657e-1401">cardholder</span></span>
- <span data-ttu-id="6657e-1402">card holders</span><span class="sxs-lookup"><span data-stu-id="6657e-1402">card holders</span></span>
- <span data-ttu-id="6657e-1403">cardholders</span><span class="sxs-lookup"><span data-stu-id="6657e-1403">cardholders</span></span>
- <span data-ttu-id="6657e-1404">check card</span><span class="sxs-lookup"><span data-stu-id="6657e-1404">check card</span></span>
- <span data-ttu-id="6657e-1405">checkcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1405">checkcard</span></span>
- <span data-ttu-id="6657e-1406">check cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1406">check cards</span></span>
- <span data-ttu-id="6657e-1407">checkcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1407">checkcards</span></span>
- <span data-ttu-id="6657e-1408">debit card</span><span class="sxs-lookup"><span data-stu-id="6657e-1408">debit card</span></span>
- <span data-ttu-id="6657e-1409">debitcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1409">debitcard</span></span>
- <span data-ttu-id="6657e-1410">debit cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1410">debit cards</span></span>
- <span data-ttu-id="6657e-1411">debitcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1411">debitcards</span></span>
- <span data-ttu-id="6657e-1412">atm card</span><span class="sxs-lookup"><span data-stu-id="6657e-1412">atm card</span></span>
- <span data-ttu-id="6657e-1413">atmcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1413">atmcard</span></span>
- <span data-ttu-id="6657e-1414">atm cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1414">atm cards</span></span>
- <span data-ttu-id="6657e-1415">atmcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1415">atmcards</span></span>
- <span data-ttu-id="6657e-1416">enroute</span><span class="sxs-lookup"><span data-stu-id="6657e-1416">enroute</span></span>
- <span data-ttu-id="6657e-1417">en route</span><span class="sxs-lookup"><span data-stu-id="6657e-1417">en route</span></span>
- <span data-ttu-id="6657e-1418">card type</span><span class="sxs-lookup"><span data-stu-id="6657e-1418">card type</span></span>
- <span data-ttu-id="6657e-1419">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="6657e-1419">carte bancaire</span></span>
- <span data-ttu-id="6657e-1420">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="6657e-1420">carte de crédit</span></span>
- <span data-ttu-id="6657e-1421">carte de credit</span><span class="sxs-lookup"><span data-stu-id="6657e-1421">carte de credit</span></span>
- <span data-ttu-id="6657e-1422">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1422">numéro de carte</span></span>
- <span data-ttu-id="6657e-1423">numero de carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1423">numero de carte</span></span>
- <span data-ttu-id="6657e-1424">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1424">nº de la carte</span></span>
- <span data-ttu-id="6657e-1425">nº de carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1425">nº de carte</span></span>
- <span data-ttu-id="6657e-1426">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="6657e-1426">kreditkarte</span></span>
- <span data-ttu-id="6657e-1427">karte</span><span class="sxs-lookup"><span data-stu-id="6657e-1427">karte</span></span>
- <span data-ttu-id="6657e-1428">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="6657e-1428">karteninhaber</span></span>
- <span data-ttu-id="6657e-1429">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="6657e-1429">karteninhabers</span></span>
- <span data-ttu-id="6657e-1430">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="6657e-1430">kreditkarteninhaber</span></span>
- <span data-ttu-id="6657e-1431">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="6657e-1431">kreditkarteninstitut</span></span>
- <span data-ttu-id="6657e-1432">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="6657e-1432">kreditkartentyp</span></span>
- <span data-ttu-id="6657e-1433">eigentümername</span><span class="sxs-lookup"><span data-stu-id="6657e-1433">eigentümername</span></span>
- <span data-ttu-id="6657e-1434">kartennr</span><span class="sxs-lookup"><span data-stu-id="6657e-1434">kartennr</span></span> 
- <span data-ttu-id="6657e-1435">kartennummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1435">kartennummer</span></span>
- <span data-ttu-id="6657e-1436">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1436">kreditkartennummer</span></span>
- <span data-ttu-id="6657e-1437">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1437">kreditkarten-nummer</span></span>
- <span data-ttu-id="6657e-1438">carta di credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1438">carta di credito</span></span>
- <span data-ttu-id="6657e-1439">carta credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1439">carta credito</span></span>
- <span data-ttu-id="6657e-1440">carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1440">carta</span></span>
- <span data-ttu-id="6657e-1441">n carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1441">n carta</span></span>
- <span data-ttu-id="6657e-1442">nr.</span><span class="sxs-lookup"><span data-stu-id="6657e-1442">nr.</span></span> <span data-ttu-id="6657e-1443">carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1443">carta</span></span>
- <span data-ttu-id="6657e-1444">nr carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1444">nr carta</span></span>
- <span data-ttu-id="6657e-1445">numero carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1445">numero carta</span></span>
- <span data-ttu-id="6657e-1446">numero della carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1446">numero della carta</span></span>
- <span data-ttu-id="6657e-1447">numero di carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1447">numero di carta</span></span>
- <span data-ttu-id="6657e-1448">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1448">tarjeta credito</span></span>
- <span data-ttu-id="6657e-1449">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1449">tarjeta de credito</span></span>
- <span data-ttu-id="6657e-1450">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="6657e-1450">tarjeta crédito</span></span>
- <span data-ttu-id="6657e-1451">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="6657e-1451">tarjeta de crédito</span></span>
- <span data-ttu-id="6657e-1452">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="6657e-1452">tarjeta de atm</span></span>
- <span data-ttu-id="6657e-1453">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="6657e-1453">tarjeta atm</span></span>
- <span data-ttu-id="6657e-1454">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1454">tarjeta debito</span></span>
- <span data-ttu-id="6657e-1455">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1455">tarjeta de debito</span></span>
- <span data-ttu-id="6657e-1456">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="6657e-1456">tarjeta débito</span></span>
- <span data-ttu-id="6657e-1457">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="6657e-1457">tarjeta de débito</span></span>
- <span data-ttu-id="6657e-1458">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1458">nº de tarjeta</span></span>
- <span data-ttu-id="6657e-1459">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1459">no.</span></span> <span data-ttu-id="6657e-1460">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1460">de tarjeta</span></span>
- <span data-ttu-id="6657e-1461">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1461">no de tarjeta</span></span>
- <span data-ttu-id="6657e-1462">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1462">numero de tarjeta</span></span>
- <span data-ttu-id="6657e-1463">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1463">número de tarjeta</span></span>
- <span data-ttu-id="6657e-1464">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="6657e-1464">tarjeta no</span></span>
- <span data-ttu-id="6657e-1465">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="6657e-1465">tarjetahabiente</span></span>
- <span data-ttu-id="6657e-1466">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="6657e-1466">cartão de crédito</span></span>
- <span data-ttu-id="6657e-1467">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1467">cartão de credito</span></span>
- <span data-ttu-id="6657e-1468">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="6657e-1468">cartao de crédito</span></span>
- <span data-ttu-id="6657e-1469">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1469">cartao de credito</span></span>
- <span data-ttu-id="6657e-1470">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="6657e-1470">cartão de débito</span></span>
- <span data-ttu-id="6657e-1471">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="6657e-1471">cartao de débito</span></span>
- <span data-ttu-id="6657e-1472">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1472">cartão de debito</span></span>
- <span data-ttu-id="6657e-1473">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1473">cartao de debito</span></span>
- <span data-ttu-id="6657e-1474">débito automático</span><span class="sxs-lookup"><span data-stu-id="6657e-1474">débito automático</span></span>
- <span data-ttu-id="6657e-1475">debito automatico</span><span class="sxs-lookup"><span data-stu-id="6657e-1475">debito automatico</span></span>
- <span data-ttu-id="6657e-1476">número do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1476">número do cartão</span></span>
- <span data-ttu-id="6657e-1477">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1477">numero do cartão</span></span> 
- <span data-ttu-id="6657e-1478">número do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1478">número do cartao</span></span>
- <span data-ttu-id="6657e-1479">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1479">numero do cartao</span></span>
- <span data-ttu-id="6657e-1480">número de cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1480">número de cartão</span></span>
- <span data-ttu-id="6657e-1481">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1481">numero de cartão</span></span>
- <span data-ttu-id="6657e-1482">número de cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1482">número de cartao</span></span>
- <span data-ttu-id="6657e-1483">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1483">numero de cartao</span></span>
- <span data-ttu-id="6657e-1484">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1484">nº do cartão</span></span>
- <span data-ttu-id="6657e-1485">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1485">nº do cartao</span></span>
- <span data-ttu-id="6657e-1486">n °</span><span class="sxs-lookup"><span data-stu-id="6657e-1486">nº.</span></span> <span data-ttu-id="6657e-1487">do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1487">do cartão</span></span>
- <span data-ttu-id="6657e-1488">no do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1488">no do cartão</span></span>
- <span data-ttu-id="6657e-1489">no do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1489">no do cartao</span></span>
- <span data-ttu-id="6657e-1490">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1490">no.</span></span> <span data-ttu-id="6657e-1491">do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1491">do cartão</span></span>
- <span data-ttu-id="6657e-1492">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1492">no.</span></span> <span data-ttu-id="6657e-1493">do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1493">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="6657e-1494">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1494">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1495">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1495">Format</span></span>

<span data-ttu-id="6657e-1496">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1496">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1497">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1497">Pattern</span></span>

<span data-ttu-id="6657e-1498">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1498">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1499">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1499">Checksum</span></span>

<span data-ttu-id="6657e-1500">無</span><span class="sxs-lookup"><span data-stu-id="6657e-1500">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1501">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1501">Definition</span></span>

<span data-ttu-id="6657e-1502">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1502">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1503">関数 Func_croatia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1503">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1504">Keyword_croatia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1504">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-1505">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1505">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="6657e-1506">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="6657e-1506">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="6657e-1507">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="6657e-1507">Croatian identity card</span></span>
- <span data-ttu-id="6657e-1508">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="6657e-1508">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="6657e-1509">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="6657e-1509">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1510">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1510">Format</span></span>

<span data-ttu-id="6657e-1511">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1511">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1512">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1512">Pattern</span></span>

<span data-ttu-id="6657e-1513">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-1513">11 digits:</span></span>
- <span data-ttu-id="6657e-1514">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1514">10 digits</span></span> 
- <span data-ttu-id="6657e-1515">最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="6657e-1515">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1516">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1516">Checksum</span></span>

<span data-ttu-id="6657e-1517">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1518">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1518">Definition</span></span>

<span data-ttu-id="6657e-1519">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1520">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1520">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1521">Keyword_croatia_oib_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1521">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="6657e-1522">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1522">The checksum passes.</span></span>

<span data-ttu-id="6657e-1523">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1523">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1524">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1524">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1525">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1525">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1526">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1526">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="6657e-1527">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="6657e-1527">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="6657e-1528">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="6657e-1528">Personal Identification Number</span></span>
- <span data-ttu-id="6657e-1529">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="6657e-1529">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="6657e-1530">oib</span><span class="sxs-lookup"><span data-stu-id="6657e-1530">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="6657e-1531">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1531">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1532">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1532">Format</span></span>

<span data-ttu-id="6657e-1533">省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)</span><span class="sxs-lookup"><span data-stu-id="6657e-1533">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1534">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1534">Pattern</span></span>

<span data-ttu-id="6657e-1535">9桁の数字 (古い形式):</span><span class="sxs-lookup"><span data-stu-id="6657e-1535">Nine digits (old format):</span></span>
- <span data-ttu-id="6657e-1536">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1536">Nine digits</span></span>

<span data-ttu-id="6657e-1537">または</span><span class="sxs-lookup"><span data-stu-id="6657e-1537">OR</span></span>

- <span data-ttu-id="6657e-1538">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1538">Six digits that represent date of birth</span></span>
- <span data-ttu-id="6657e-1539">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-1539">A forward slash</span></span>
- <span data-ttu-id="6657e-1540">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1540">Three digits</span></span>

<span data-ttu-id="6657e-1541">10桁の数字 (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="6657e-1541">10 digits (new format):</span></span>
- <span data-ttu-id="6657e-1542">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1542">10 digits</span></span>

<span data-ttu-id="6657e-1543">または</span><span class="sxs-lookup"><span data-stu-id="6657e-1543">OR</span></span>

- <span data-ttu-id="6657e-1544">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1544">Six digits that represent date of birth</span></span>
- <span data-ttu-id="6657e-1545">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-1545">A forward slash</span></span> 
- <span data-ttu-id="6657e-1546">4桁の数字 (最後の桁はチェックディジット)</span><span class="sxs-lookup"><span data-stu-id="6657e-1546">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1547">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1547">Checksum</span></span>

<span data-ttu-id="6657e-1548">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1549">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1549">Definition</span></span>

<span data-ttu-id="6657e-1550">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-1551">Keyword_czech_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1551">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="6657e-1552">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1552">The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="6657e-1553">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1553">Keywords</span></span>

- <span data-ttu-id="6657e-1554">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1554">czech personal identity number</span></span>
- <span data-ttu-id="6657e-1555">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="6657e-1555">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="6657e-1556">	Denmark Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="6657e-1556">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1557">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1557">Format</span></span>

<span data-ttu-id="6657e-1558">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1558">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1559">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1559">Pattern</span></span>

<span data-ttu-id="6657e-1560">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-1560">10 digits:</span></span>
- <span data-ttu-id="6657e-1561">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-1561">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6657e-1562">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-1562">A hyphen</span></span> 
- <span data-ttu-id="6657e-1563">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="6657e-1563">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1564">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1564">Checksum</span></span>

<span data-ttu-id="6657e-1565">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1565">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1566">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1566">Definition</span></span>

<span data-ttu-id="6657e-1567">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1567">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-1568">Keyword_denmark_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1568">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="6657e-1569">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1569">The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-1570">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1570">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="6657e-1571">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="6657e-1571">Keyword_denmark_id</span></span>

- <span data-ttu-id="6657e-1572">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="6657e-1572">Personal Identification Number</span></span>
- <span data-ttu-id="6657e-1573">CPR</span><span class="sxs-lookup"><span data-stu-id="6657e-1573">CPR</span></span>
- <span data-ttu-id="6657e-1574">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="6657e-1574">Det Centrale Personregister</span></span>
- <span data-ttu-id="6657e-1575">Personnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1575">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="6657e-1576">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1576">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1577">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1577">Format</span></span>

<span data-ttu-id="6657e-1578">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1578">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1579">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1579">Pattern</span></span>

<span data-ttu-id="6657e-1580">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-1580">Pattern must include all of the following:</span></span>
- <span data-ttu-id="6657e-1581">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="6657e-1581">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="6657e-1582">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="6657e-1582">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="6657e-1583">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="6657e-1583">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1584">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1584">Checksum</span></span>

<span data-ttu-id="6657e-1585">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1586">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1586">Definition</span></span>

<span data-ttu-id="6657e-1587">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1587">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1588">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1588">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1589">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1589">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-1590">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1590">Keywords</span></span>

<span data-ttu-id="6657e-1591">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-1591">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="6657e-1592">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1592">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1593">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1593">Format</span></span>

<span data-ttu-id="6657e-1594">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1594">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1595">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1595">Pattern</span></span>

<span data-ttu-id="6657e-1596">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1596">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1597">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1597">Checksum</span></span>

<span data-ttu-id="6657e-1598">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1598">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1599">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1599">Definition</span></span>

<span data-ttu-id="6657e-1600">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1600">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1601">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1601">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1602">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-1602">At least one of the following is true:</span></span>
    - <span data-ttu-id="6657e-1603">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1603">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="6657e-1604">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1604">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="6657e-1605">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1605">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="6657e-1606">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1606">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="6657e-1607">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1607">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6657e-1608">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1608">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1609">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1609">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="6657e-1610">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="6657e-1610">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="6657e-1611">account number</span><span class="sxs-lookup"><span data-stu-id="6657e-1611">account number</span></span> 
- <span data-ttu-id="6657e-1612">card number</span><span class="sxs-lookup"><span data-stu-id="6657e-1612">card number</span></span> 
- <span data-ttu-id="6657e-1613">card no.</span><span class="sxs-lookup"><span data-stu-id="6657e-1613">card no.</span></span> 
- <span data-ttu-id="6657e-1614">security number</span><span class="sxs-lookup"><span data-stu-id="6657e-1614">security number</span></span> 
- <span data-ttu-id="6657e-1615">]</span><span class="sxs-lookup"><span data-stu-id="6657e-1615">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="6657e-1616">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="6657e-1616">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="6657e-1617">acct nbr</span><span class="sxs-lookup"><span data-stu-id="6657e-1617">acct nbr</span></span> 
- <span data-ttu-id="6657e-1618">acct num</span><span class="sxs-lookup"><span data-stu-id="6657e-1618">acct num</span></span> 
- <span data-ttu-id="6657e-1619">acct no</span><span class="sxs-lookup"><span data-stu-id="6657e-1619">acct no</span></span> 
- <span data-ttu-id="6657e-1620">american express</span><span class="sxs-lookup"><span data-stu-id="6657e-1620">american express</span></span> 
- <span data-ttu-id="6657e-1621">americanexpress</span><span class="sxs-lookup"><span data-stu-id="6657e-1621">americanexpress</span></span> 
- <span data-ttu-id="6657e-1622">americano espresso</span><span class="sxs-lookup"><span data-stu-id="6657e-1622">americano espresso</span></span> 
- <span data-ttu-id="6657e-1623">amex</span><span class="sxs-lookup"><span data-stu-id="6657e-1623">amex</span></span> 
- <span data-ttu-id="6657e-1624">atm card</span><span class="sxs-lookup"><span data-stu-id="6657e-1624">atm card</span></span> 
- <span data-ttu-id="6657e-1625">atm cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1625">atm cards</span></span> 
- <span data-ttu-id="6657e-1626">atm kaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1626">atm kaart</span></span> 
- <span data-ttu-id="6657e-1627">atmcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1627">atmcard</span></span> 
- <span data-ttu-id="6657e-1628">atmcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1628">atmcards</span></span> 
- <span data-ttu-id="6657e-1629">atmkaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1629">atmkaart</span></span> 
- <span data-ttu-id="6657e-1630">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="6657e-1630">atmkaarten</span></span> 
- <span data-ttu-id="6657e-1631"># # の連絡先</span><span class="sxs-lookup"><span data-stu-id="6657e-1631">bancontact</span></span> 
- <span data-ttu-id="6657e-1632">bank card</span><span class="sxs-lookup"><span data-stu-id="6657e-1632">bank card</span></span> 
- <span data-ttu-id="6657e-1633">bankkaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1633">bankkaart</span></span> 
- <span data-ttu-id="6657e-1634">card holder</span><span class="sxs-lookup"><span data-stu-id="6657e-1634">card holder</span></span> 
- <span data-ttu-id="6657e-1635">card holders</span><span class="sxs-lookup"><span data-stu-id="6657e-1635">card holders</span></span> 
- <span data-ttu-id="6657e-1636">card num</span><span class="sxs-lookup"><span data-stu-id="6657e-1636">card num</span></span> 
- <span data-ttu-id="6657e-1637">card number</span><span class="sxs-lookup"><span data-stu-id="6657e-1637">card number</span></span> 
- <span data-ttu-id="6657e-1638">card numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-1638">card numbers</span></span> 
- <span data-ttu-id="6657e-1639">card type</span><span class="sxs-lookup"><span data-stu-id="6657e-1639">card type</span></span> 
- <span data-ttu-id="6657e-1640">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="6657e-1640">cardano numerico</span></span> 
- <span data-ttu-id="6657e-1641">所有者</span><span class="sxs-lookup"><span data-stu-id="6657e-1641">cardholder</span></span> 
- <span data-ttu-id="6657e-1642">cardholders</span><span class="sxs-lookup"><span data-stu-id="6657e-1642">cardholders</span></span> 
- <span data-ttu-id="6657e-1643">カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1643">cardnumber</span></span> 
- <span data-ttu-id="6657e-1644">カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1644">cardnumbers</span></span> 
- <span data-ttu-id="6657e-1645">carta bianca</span><span class="sxs-lookup"><span data-stu-id="6657e-1645">carta bianca</span></span> 
- <span data-ttu-id="6657e-1646">carta credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1646">carta credito</span></span> 
- <span data-ttu-id="6657e-1647">carta di credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1647">carta di credito</span></span> 
- <span data-ttu-id="6657e-1648">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1648">cartao de credito</span></span> 
- <span data-ttu-id="6657e-1649">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="6657e-1649">cartao de crédito</span></span> 
- <span data-ttu-id="6657e-1650">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1650">cartao de debito</span></span> 
- <span data-ttu-id="6657e-1651">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="6657e-1651">cartao de débito</span></span> 
- <span data-ttu-id="6657e-1652">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="6657e-1652">carte bancaire</span></span> 
- <span data-ttu-id="6657e-1653">carte blanche</span><span class="sxs-lookup"><span data-stu-id="6657e-1653">carte blanche</span></span> 
- <span data-ttu-id="6657e-1654">carte bleue</span><span class="sxs-lookup"><span data-stu-id="6657e-1654">carte bleue</span></span> 
- <span data-ttu-id="6657e-1655">carte de credit</span><span class="sxs-lookup"><span data-stu-id="6657e-1655">carte de credit</span></span> 
- <span data-ttu-id="6657e-1656">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="6657e-1656">carte de crédit</span></span> 
- <span data-ttu-id="6657e-1657">carte di credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1657">carte di credito</span></span> 
- <span data-ttu-id="6657e-1658">carteblanche</span><span class="sxs-lookup"><span data-stu-id="6657e-1658">carteblanche</span></span> 
- <span data-ttu-id="6657e-1659">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1659">cartão de credito</span></span> 
- <span data-ttu-id="6657e-1660">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="6657e-1660">cartão de crédito</span></span> 
- <span data-ttu-id="6657e-1661">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1661">cartão de debito</span></span> 
- <span data-ttu-id="6657e-1662">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="6657e-1662">cartão de débito</span></span> 
- <span data-ttu-id="6657e-1663">cb</span><span class="sxs-lookup"><span data-stu-id="6657e-1663">cb</span></span> 
- <span data-ttu-id="6657e-1664">ccn</span><span class="sxs-lookup"><span data-stu-id="6657e-1664">ccn</span></span> 
- <span data-ttu-id="6657e-1665">check card</span><span class="sxs-lookup"><span data-stu-id="6657e-1665">check card</span></span> 
- <span data-ttu-id="6657e-1666">check cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1666">check cards</span></span> 
- <span data-ttu-id="6657e-1667">checkcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1667">checkcard</span></span>
- <span data-ttu-id="6657e-1668">checkcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1668">checkcards</span></span> 
- <span data-ttu-id="6657e-1669">chequekaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1669">chequekaart</span></span> 
- <span data-ttu-id="6657e-1670">cirrus</span><span class="sxs-lookup"><span data-stu-id="6657e-1670">cirrus</span></span> 
- <span data-ttu-id="6657e-1671">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="6657e-1671">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="6657e-1672">lekaart の方法</span><span class="sxs-lookup"><span data-stu-id="6657e-1672">controlekaart</span></span> 
- <span data-ttu-id="6657e-1673">lekaar10 の場合</span><span class="sxs-lookup"><span data-stu-id="6657e-1673">controlekaarten</span></span> 
- <span data-ttu-id="6657e-1674">credit card</span><span class="sxs-lookup"><span data-stu-id="6657e-1674">credit card</span></span> 
- <span data-ttu-id="6657e-1675">credit cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1675">credit cards</span></span> 
- <span data-ttu-id="6657e-1676">creditcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1676">creditcard</span></span> 
- <span data-ttu-id="6657e-1677">creditcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1677">creditcards</span></span> 
- <span data-ttu-id="6657e-1678">debetkaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1678">debetkaart</span></span> 
- <span data-ttu-id="6657e-1679">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="6657e-1679">debetkaarten</span></span> 
- <span data-ttu-id="6657e-1680">debit card</span><span class="sxs-lookup"><span data-stu-id="6657e-1680">debit card</span></span> 
- <span data-ttu-id="6657e-1681">debit cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1681">debit cards</span></span> 
- <span data-ttu-id="6657e-1682">debitcard</span><span class="sxs-lookup"><span data-stu-id="6657e-1682">debitcard</span></span> 
- <span data-ttu-id="6657e-1683">debitcards</span><span class="sxs-lookup"><span data-stu-id="6657e-1683">debitcards</span></span> 
- <span data-ttu-id="6657e-1684">debito automatico</span><span class="sxs-lookup"><span data-stu-id="6657e-1684">debito automatico</span></span> 
- <span data-ttu-id="6657e-1685">diners club</span><span class="sxs-lookup"><span data-stu-id="6657e-1685">diners club</span></span> 
- <span data-ttu-id="6657e-1686">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="6657e-1686">dinersclub</span></span> 
- <span data-ttu-id="6657e-1687">開示</span><span class="sxs-lookup"><span data-stu-id="6657e-1687">discover</span></span> 
- <span data-ttu-id="6657e-1688">discover card</span><span class="sxs-lookup"><span data-stu-id="6657e-1688">discover card</span></span> 
- <span data-ttu-id="6657e-1689">discover cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1689">discover cards</span></span> 
- <span data-ttu-id="6657e-1690">discovercard</span><span class="sxs-lookup"><span data-stu-id="6657e-1690">discovercard</span></span> 
- <span data-ttu-id="6657e-1691">discovercards</span><span class="sxs-lookup"><span data-stu-id="6657e-1691">discovercards</span></span> 
- <span data-ttu-id="6657e-1692">débito automático</span><span class="sxs-lookup"><span data-stu-id="6657e-1692">débito automático</span></span>
- <span data-ttu-id="6657e-1693">edc</span><span class="sxs-lookup"><span data-stu-id="6657e-1693">edc</span></span> 
- <span data-ttu-id="6657e-1694">eigentümername</span><span class="sxs-lookup"><span data-stu-id="6657e-1694">eigentümername</span></span> 
- <span data-ttu-id="6657e-1695">european debit card</span><span class="sxs-lookup"><span data-stu-id="6657e-1695">european debit card</span></span> 
- <span data-ttu-id="6657e-1696">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1696">hoofdkaart</span></span> 
- <span data-ttu-id="6657e-1697">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="6657e-1697">hoofdkaarten</span></span> 
- <span data-ttu-id="6657e-1698">in viaggio</span><span class="sxs-lookup"><span data-stu-id="6657e-1698">in viaggio</span></span> 
- <span data-ttu-id="6657e-1699">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="6657e-1699">japanese card bureau</span></span> 
- <span data-ttu-id="6657e-1700">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="6657e-1700">japanse kaartdienst</span></span> 
- <span data-ttu-id="6657e-1701">jcb</span><span class="sxs-lookup"><span data-stu-id="6657e-1701">jcb</span></span> 
- <span data-ttu-id="6657e-1702">kaart</span><span class="sxs-lookup"><span data-stu-id="6657e-1702">kaart</span></span> 
- <span data-ttu-id="6657e-1703">kaart num</span><span class="sxs-lookup"><span data-stu-id="6657e-1703">kaart num</span></span> 
- <span data-ttu-id="6657e-1704">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="6657e-1704">kaartaantal</span></span> 
- <span data-ttu-id="6657e-1705">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="6657e-1705">kaartaantallen</span></span> 
- <span data-ttu-id="6657e-1706">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="6657e-1706">kaarthouder</span></span> 
- <span data-ttu-id="6657e-1707">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="6657e-1707">kaarthouders</span></span> 
- <span data-ttu-id="6657e-1708">karte</span><span class="sxs-lookup"><span data-stu-id="6657e-1708">karte</span></span>  
- <span data-ttu-id="6657e-1709">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="6657e-1709">karteninhaber</span></span> 
- <span data-ttu-id="6657e-1710">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="6657e-1710">karteninhabers</span></span>
- <span data-ttu-id="6657e-1711">kartennr</span><span class="sxs-lookup"><span data-stu-id="6657e-1711">kartennr</span></span> 
- <span data-ttu-id="6657e-1712">kartennummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1712">kartennummer</span></span> 
- <span data-ttu-id="6657e-1713">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="6657e-1713">kreditkarte</span></span> 
- <span data-ttu-id="6657e-1714">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1714">kreditkarten-nummer</span></span> 
- <span data-ttu-id="6657e-1715">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="6657e-1715">kreditkarteninhaber</span></span> 
- <span data-ttu-id="6657e-1716">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="6657e-1716">kreditkarteninstitut</span></span> 
- <span data-ttu-id="6657e-1717">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1717">kreditkartennummer</span></span> 
- <span data-ttu-id="6657e-1718">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="6657e-1718">kreditkartentyp</span></span> 
- <span data-ttu-id="6657e-1719">maestro</span><span class="sxs-lookup"><span data-stu-id="6657e-1719">maestro</span></span> 
- <span data-ttu-id="6657e-1720">master card</span><span class="sxs-lookup"><span data-stu-id="6657e-1720">master card</span></span> 
- <span data-ttu-id="6657e-1721">master cards</span><span class="sxs-lookup"><span data-stu-id="6657e-1721">master cards</span></span> 
- <span data-ttu-id="6657e-1722">mastercard</span><span class="sxs-lookup"><span data-stu-id="6657e-1722">mastercard</span></span> 
- <span data-ttu-id="6657e-1723">mastercards</span><span class="sxs-lookup"><span data-stu-id="6657e-1723">mastercards</span></span> 
- <span data-ttu-id="6657e-1724">mc</span><span class="sxs-lookup"><span data-stu-id="6657e-1724">mc</span></span> 
- <span data-ttu-id="6657e-1725">mister cash</span><span class="sxs-lookup"><span data-stu-id="6657e-1725">mister cash</span></span> 
- <span data-ttu-id="6657e-1726">n carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1726">n carta</span></span> 
- <span data-ttu-id="6657e-1727">carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1727">carta</span></span> 
- <span data-ttu-id="6657e-1728">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1728">no de tarjeta</span></span> 
- <span data-ttu-id="6657e-1729">no do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1729">no do cartao</span></span> 
- <span data-ttu-id="6657e-1730">no do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1730">no do cartão</span></span> 
- <span data-ttu-id="6657e-1731">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1731">no.</span></span> <span data-ttu-id="6657e-1732">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1732">de tarjeta</span></span> 
- <span data-ttu-id="6657e-1733">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1733">no.</span></span> <span data-ttu-id="6657e-1734">do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1734">do cartao</span></span> 
- <span data-ttu-id="6657e-1735">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1735">no.</span></span> <span data-ttu-id="6657e-1736">do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1736">do cartão</span></span> 
- <span data-ttu-id="6657e-1737">nr carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1737">nr carta</span></span> 
- <span data-ttu-id="6657e-1738">nr.</span><span class="sxs-lookup"><span data-stu-id="6657e-1738">nr.</span></span> <span data-ttu-id="6657e-1739">carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1739">carta</span></span> 
- <span data-ttu-id="6657e-1740">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1740">numeri di scheda</span></span> 
- <span data-ttu-id="6657e-1741">numero carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1741">numero carta</span></span> 
- <span data-ttu-id="6657e-1742">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1742">numero de cartao</span></span> 
- <span data-ttu-id="6657e-1743">numero de carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1743">numero de carte</span></span> 
- <span data-ttu-id="6657e-1744">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1744">numero de cartão</span></span> 
- <span data-ttu-id="6657e-1745">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1745">numero de tarjeta</span></span>
- <span data-ttu-id="6657e-1746">numero della carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1746">numero della carta</span></span> 
- <span data-ttu-id="6657e-1747">numero di carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1747">numero di carta</span></span> 
- <span data-ttu-id="6657e-1748">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1748">numero di scheda</span></span> 
- <span data-ttu-id="6657e-1749">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1749">numero do cartao</span></span> 
- <span data-ttu-id="6657e-1750">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1750">numero do cartão</span></span> 
- <span data-ttu-id="6657e-1751">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1751">numéro de carte</span></span> 
- <span data-ttu-id="6657e-1752">nº carta</span><span class="sxs-lookup"><span data-stu-id="6657e-1752">nº carta</span></span> 
- <span data-ttu-id="6657e-1753">nº de carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1753">nº de carte</span></span> 
- <span data-ttu-id="6657e-1754">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="6657e-1754">nº de la carte</span></span> 
- <span data-ttu-id="6657e-1755">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1755">nº de tarjeta</span></span> 
- <span data-ttu-id="6657e-1756">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1756">nº do cartao</span></span> 
- <span data-ttu-id="6657e-1757">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1757">nº do cartão</span></span> 
- <span data-ttu-id="6657e-1758">n °</span><span class="sxs-lookup"><span data-stu-id="6657e-1758">nº.</span></span> <span data-ttu-id="6657e-1759">do cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1759">do cartão</span></span> 
- <span data-ttu-id="6657e-1760">número de cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1760">número de cartao</span></span> 
- <span data-ttu-id="6657e-1761">número de cartão</span><span class="sxs-lookup"><span data-stu-id="6657e-1761">número de cartão</span></span> 
- <span data-ttu-id="6657e-1762">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="6657e-1762">número de tarjeta</span></span> 
- <span data-ttu-id="6657e-1763">número do cartao</span><span class="sxs-lookup"><span data-stu-id="6657e-1763">número do cartao</span></span> 
- <span data-ttu-id="6657e-1764">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="6657e-1764">scheda dell'assegno</span></span> 
- <span data-ttu-id="6657e-1765">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="6657e-1765">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="6657e-1766">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="6657e-1766">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="6657e-1767">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="6657e-1767">scheda della banca</span></span> 
- <span data-ttu-id="6657e-1768">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="6657e-1768">scheda di controllo</span></span> 
- <span data-ttu-id="6657e-1769">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1769">scheda di debito</span></span> 
- <span data-ttu-id="6657e-1770">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="6657e-1770">scheda matrice</span></span> 
- <span data-ttu-id="6657e-1771">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="6657e-1771">schede dell'atmosfera</span></span> 
- <span data-ttu-id="6657e-1772">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="6657e-1772">schede di controllo</span></span> 
- <span data-ttu-id="6657e-1773">schede di debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1773">schede di debito</span></span> 
- <span data-ttu-id="6657e-1774">schede matrici</span><span class="sxs-lookup"><span data-stu-id="6657e-1774">schede matrici</span></span> 
- <span data-ttu-id="6657e-1775">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1775">scoprono la scheda</span></span> 
- <span data-ttu-id="6657e-1776">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="6657e-1776">scoprono le schede</span></span> 
- <span data-ttu-id="6657e-1777">単独</span><span class="sxs-lookup"><span data-stu-id="6657e-1777">solo</span></span> 
- <span data-ttu-id="6657e-1778">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1778">supporti di scheda</span></span> 
- <span data-ttu-id="6657e-1779">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1779">supporto di scheda</span></span> 
- <span data-ttu-id="6657e-1780">switch</span><span class="sxs-lookup"><span data-stu-id="6657e-1780">switch</span></span> 
- <span data-ttu-id="6657e-1781">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="6657e-1781">tarjeta atm</span></span> 
- <span data-ttu-id="6657e-1782">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1782">tarjeta credito</span></span> 
- <span data-ttu-id="6657e-1783">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="6657e-1783">tarjeta de atm</span></span> 
- <span data-ttu-id="6657e-1784">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="6657e-1784">tarjeta de credito</span></span> 
- <span data-ttu-id="6657e-1785">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1785">tarjeta de debito</span></span> 
- <span data-ttu-id="6657e-1786">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="6657e-1786">tarjeta debito</span></span> 
- <span data-ttu-id="6657e-1787">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="6657e-1787">tarjeta no</span></span>
- <span data-ttu-id="6657e-1788">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="6657e-1788">tarjetahabiente</span></span> 
- <span data-ttu-id="6657e-1789">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1789">tipo della scheda</span></span> 
- <span data-ttu-id="6657e-1790">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="6657e-1790">ufficio giapponese della</span></span> 
- <span data-ttu-id="6657e-1791">scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1791">scheda</span></span> 
- <span data-ttu-id="6657e-1792">v pay</span><span class="sxs-lookup"><span data-stu-id="6657e-1792">v pay</span></span> 
- <span data-ttu-id="6657e-1793">v-支払い</span><span class="sxs-lookup"><span data-stu-id="6657e-1793">v-pay</span></span> 
- <span data-ttu-id="6657e-1794">visa</span><span class="sxs-lookup"><span data-stu-id="6657e-1794">visa</span></span> 
- <span data-ttu-id="6657e-1795">visa plus</span><span class="sxs-lookup"><span data-stu-id="6657e-1795">visa plus</span></span> 
- <span data-ttu-id="6657e-1796">visa electron</span><span class="sxs-lookup"><span data-stu-id="6657e-1796">visa electron</span></span> 
- <span data-ttu-id="6657e-1797">visto</span><span class="sxs-lookup"><span data-stu-id="6657e-1797">visto</span></span> 
- <span data-ttu-id="6657e-1798">visum</span><span class="sxs-lookup"><span data-stu-id="6657e-1798">visum</span></span> 
- <span data-ttu-id="6657e-1799">vpay</span><span class="sxs-lookup"><span data-stu-id="6657e-1799">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="6657e-1800">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="6657e-1800">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="6657e-1801">card identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-1801">card identification number</span></span>
- <span data-ttu-id="6657e-1802">card verification</span><span class="sxs-lookup"><span data-stu-id="6657e-1802">card verification</span></span> 
- <span data-ttu-id="6657e-1803">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="6657e-1803">cardi la verifica</span></span> 
- <span data-ttu-id="6657e-1804">cid</span><span class="sxs-lookup"><span data-stu-id="6657e-1804">cid</span></span> 
- <span data-ttu-id="6657e-1805">cod seg</span><span class="sxs-lookup"><span data-stu-id="6657e-1805">cod seg</span></span> 
- <span data-ttu-id="6657e-1806">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1806">cod seguranca</span></span> 
- <span data-ttu-id="6657e-1807">cod segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1807">cod segurança</span></span> 
- <span data-ttu-id="6657e-1808">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1808">cod sicurezza</span></span> 
- <span data-ttu-id="6657e-1809">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1809">cod.</span></span> <span data-ttu-id="6657e-1810">seg</span><span class="sxs-lookup"><span data-stu-id="6657e-1810">seg</span></span> 
- <span data-ttu-id="6657e-1811">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1811">cod.</span></span> <span data-ttu-id="6657e-1812">seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1812">seguranca</span></span> 
- <span data-ttu-id="6657e-1813">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1813">cod.</span></span> <span data-ttu-id="6657e-1814">segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1814">segurança</span></span> 
- <span data-ttu-id="6657e-1815">cod.</span><span class="sxs-lookup"><span data-stu-id="6657e-1815">cod.</span></span> <span data-ttu-id="6657e-1816">sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1816">sicurezza</span></span> 
- <span data-ttu-id="6657e-1817">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1817">codice di sicurezza</span></span> 
- <span data-ttu-id="6657e-1818">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="6657e-1818">codice di verifica</span></span> 
- <span data-ttu-id="6657e-1819">codigo</span><span class="sxs-lookup"><span data-stu-id="6657e-1819">codigo</span></span> 
- <span data-ttu-id="6657e-1820">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1820">codigo de seguranca</span></span> 
- <span data-ttu-id="6657e-1821">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1821">codigo de segurança</span></span> 
- <span data-ttu-id="6657e-1822">crittogramma</span><span class="sxs-lookup"><span data-stu-id="6657e-1822">crittogramma</span></span> 
- <span data-ttu-id="6657e-1823">cryptogram</span><span class="sxs-lookup"><span data-stu-id="6657e-1823">cryptogram</span></span> 
- <span data-ttu-id="6657e-1824">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="6657e-1824">cryptogramme</span></span> 
- <span data-ttu-id="6657e-1825">cv2</span><span class="sxs-lookup"><span data-stu-id="6657e-1825">cv2</span></span> 
- <span data-ttu-id="6657e-1826">cvc</span><span class="sxs-lookup"><span data-stu-id="6657e-1826">cvc</span></span> 
- <span data-ttu-id="6657e-1827">cvc2</span><span class="sxs-lookup"><span data-stu-id="6657e-1827">cvc2</span></span> 
- <span data-ttu-id="6657e-1828">cvn</span><span class="sxs-lookup"><span data-stu-id="6657e-1828">cvn</span></span> 
- <span data-ttu-id="6657e-1829">cvv</span><span class="sxs-lookup"><span data-stu-id="6657e-1829">cvv</span></span> 
- <span data-ttu-id="6657e-1830">cvv2</span><span class="sxs-lookup"><span data-stu-id="6657e-1830">cvv2</span></span> 
- <span data-ttu-id="6657e-1831">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1831">cód seguranca</span></span> 
- <span data-ttu-id="6657e-1832">cód segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1832">cód segurança</span></span> 
- <span data-ttu-id="6657e-1833">cód。</span><span class="sxs-lookup"><span data-stu-id="6657e-1833">cód.</span></span> <span data-ttu-id="6657e-1834">seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1834">seguranca</span></span> 
- <span data-ttu-id="6657e-1835">cód。</span><span class="sxs-lookup"><span data-stu-id="6657e-1835">cód.</span></span> <span data-ttu-id="6657e-1836">segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1836">segurança</span></span> 
- <span data-ttu-id="6657e-1837">código</span><span class="sxs-lookup"><span data-stu-id="6657e-1837">código</span></span> 
- <span data-ttu-id="6657e-1838">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="6657e-1838">código de seguranca</span></span> 
- <span data-ttu-id="6657e-1839">código de segurança</span><span class="sxs-lookup"><span data-stu-id="6657e-1839">código de segurança</span></span> 
- <span data-ttu-id="6657e-1840">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="6657e-1840">de kaart controle</span></span> 
- <span data-ttu-id="6657e-1841">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="6657e-1841">geeft nr uit</span></span> 
- <span data-ttu-id="6657e-1842">issue no</span><span class="sxs-lookup"><span data-stu-id="6657e-1842">issue no</span></span> 
- <span data-ttu-id="6657e-1843">issue number</span><span class="sxs-lookup"><span data-stu-id="6657e-1843">issue number</span></span> 
- <span data-ttu-id="6657e-1844">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1844">kaartidentificatienummer</span></span> 
- <span data-ttu-id="6657e-1845">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1845">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="6657e-1846">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1846">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="6657e-1847">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="6657e-1847">kwestieaantal</span></span> 
- <span data-ttu-id="6657e-1848">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1848">no.</span></span> <span data-ttu-id="6657e-1849">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="6657e-1849">dell'edizione</span></span> 
- <span data-ttu-id="6657e-1850">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-1850">no.</span></span> <span data-ttu-id="6657e-1851">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1851">di sicurezza</span></span> 
- <span data-ttu-id="6657e-1852">numero de securite</span><span class="sxs-lookup"><span data-stu-id="6657e-1852">numero de securite</span></span> 
- <span data-ttu-id="6657e-1853">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="6657e-1853">numero de verificacao</span></span> 
- <span data-ttu-id="6657e-1854">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="6657e-1854">numero dell'edizione</span></span> 
- <span data-ttu-id="6657e-1855">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="6657e-1855">numero di identificazione della</span></span> 
- <span data-ttu-id="6657e-1856">scheda</span><span class="sxs-lookup"><span data-stu-id="6657e-1856">scheda</span></span> 
- <span data-ttu-id="6657e-1857">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="6657e-1857">numero di sicurezza</span></span> 
- <span data-ttu-id="6657e-1858">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="6657e-1858">numero van veiligheid</span></span> 
- <span data-ttu-id="6657e-1859">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="6657e-1859">numéro de sécurité</span></span> 
- <span data-ttu-id="6657e-1860">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="6657e-1860">nº autorizzazione</span></span> 
- <span data-ttu-id="6657e-1861">número de verificação</span><span class="sxs-lookup"><span data-stu-id="6657e-1861">número de verificação</span></span> 
- <span data-ttu-id="6657e-1862">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="6657e-1862">perno il blocco</span></span> 
- <span data-ttu-id="6657e-1863">pin block</span><span class="sxs-lookup"><span data-stu-id="6657e-1863">pin block</span></span> 
- <span data-ttu-id="6657e-1864">prufziffer</span><span class="sxs-lookup"><span data-stu-id="6657e-1864">prufziffer</span></span> 
- <span data-ttu-id="6657e-1865">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="6657e-1865">prüfziffer</span></span> 
- <span data-ttu-id="6657e-1866">security code</span><span class="sxs-lookup"><span data-stu-id="6657e-1866">security code</span></span> 
- <span data-ttu-id="6657e-1867">security no</span><span class="sxs-lookup"><span data-stu-id="6657e-1867">security no</span></span> 
- <span data-ttu-id="6657e-1868">security number</span><span class="sxs-lookup"><span data-stu-id="6657e-1868">security number</span></span> 
- <span data-ttu-id="6657e-1869">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="6657e-1869">sicherheits kode</span></span> 
- <span data-ttu-id="6657e-1870">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="6657e-1870">sicherheitscode</span></span> 
- <span data-ttu-id="6657e-1871">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1871">sicherheitsnummer</span></span> 
- <span data-ttu-id="6657e-1872">speldblok</span><span class="sxs-lookup"><span data-stu-id="6657e-1872">speldblok</span></span> 
- <span data-ttu-id="6657e-1873">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="6657e-1873">veiligheid nr</span></span> 
- <span data-ttu-id="6657e-1874">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="6657e-1874">veiligheidsaantal</span></span> 
- <span data-ttu-id="6657e-1875">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="6657e-1875">veiligheidscode</span></span> 
- <span data-ttu-id="6657e-1876">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1876">veiligheidsnummer</span></span> 
- <span data-ttu-id="6657e-1877">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1877">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="6657e-1878">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="6657e-1878">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="6657e-1879">ablん f</span><span class="sxs-lookup"><span data-stu-id="6657e-1879">ablauf</span></span> 
- <span data-ttu-id="6657e-1880">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="6657e-1880">data de expiracao</span></span> 
- <span data-ttu-id="6657e-1881">data de expiração</span><span class="sxs-lookup"><span data-stu-id="6657e-1881">data de expiração</span></span> 
- <span data-ttu-id="6657e-1882">data del exp</span><span class="sxs-lookup"><span data-stu-id="6657e-1882">data del exp</span></span> 
- <span data-ttu-id="6657e-1883">data di exp</span><span class="sxs-lookup"><span data-stu-id="6657e-1883">data di exp</span></span> 
- <span data-ttu-id="6657e-1884">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="6657e-1884">data di scadenza</span></span> 
- <span data-ttu-id="6657e-1885">data em que expira</span><span class="sxs-lookup"><span data-stu-id="6657e-1885">data em que expira</span></span> 
- <span data-ttu-id="6657e-1886">data scad</span><span class="sxs-lookup"><span data-stu-id="6657e-1886">data scad</span></span> 
- <span data-ttu-id="6657e-1887">data scadenza</span><span class="sxs-lookup"><span data-stu-id="6657e-1887">data scadenza</span></span> 
- <span data-ttu-id="6657e-1888">date de validité</span><span class="sxs-lookup"><span data-stu-id="6657e-1888">date de validité</span></span> 
- <span data-ttu-id="6657e-1889">datum afloop</span><span class="sxs-lookup"><span data-stu-id="6657e-1889">datum afloop</span></span> 
- <span data-ttu-id="6657e-1890">datum van exp</span><span class="sxs-lookup"><span data-stu-id="6657e-1890">datum van exp</span></span> 
- <span data-ttu-id="6657e-1891">de afloop</span><span class="sxs-lookup"><span data-stu-id="6657e-1891">de afloop</span></span> 
- <span data-ttu-id="6657e-1892">espira</span><span class="sxs-lookup"><span data-stu-id="6657e-1892">espira</span></span> 
- <span data-ttu-id="6657e-1893">espira</span><span class="sxs-lookup"><span data-stu-id="6657e-1893">espira</span></span> 
- <span data-ttu-id="6657e-1894">exp date</span><span class="sxs-lookup"><span data-stu-id="6657e-1894">exp date</span></span> 
- <span data-ttu-id="6657e-1895">exp datum</span><span class="sxs-lookup"><span data-stu-id="6657e-1895">exp datum</span></span> 
- <span data-ttu-id="6657e-1896">nntp</span><span class="sxs-lookup"><span data-stu-id="6657e-1896">expiration</span></span> 
- <span data-ttu-id="6657e-1897">無効</span><span class="sxs-lookup"><span data-stu-id="6657e-1897">expire</span></span> 
- <span data-ttu-id="6657e-1898">期限</span><span class="sxs-lookup"><span data-stu-id="6657e-1898">expires</span></span> 
- <span data-ttu-id="6657e-1899">期限</span><span class="sxs-lookup"><span data-stu-id="6657e-1899">expiry</span></span> 
- <span data-ttu-id="6657e-1900">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="6657e-1900">fecha de expiracion</span></span> 
- <span data-ttu-id="6657e-1901">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="6657e-1901">fecha de venc</span></span> 
- <span data-ttu-id="6657e-1902">gultig bis</span><span class="sxs-lookup"><span data-stu-id="6657e-1902">gultig bis</span></span> 
- <span data-ttu-id="6657e-1903">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1903">gultigkeitsdatum</span></span> 
- <span data-ttu-id="6657e-1904">gültig bis</span><span class="sxs-lookup"><span data-stu-id="6657e-1904">gültig bis</span></span> 
- <span data-ttu-id="6657e-1905">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1905">gültigkeitsdatum</span></span> 
- <span data-ttu-id="6657e-1906">la scadenza</span><span class="sxs-lookup"><span data-stu-id="6657e-1906">la scadenza</span></span> 
- <span data-ttu-id="6657e-1907">scadenza</span><span class="sxs-lookup"><span data-stu-id="6657e-1907">scadenza</span></span> 
- <span data-ttu-id="6657e-1908">valable</span><span class="sxs-lookup"><span data-stu-id="6657e-1908">valable</span></span> 
- <span data-ttu-id="6657e-1909">validade</span><span class="sxs-lookup"><span data-stu-id="6657e-1909">validade</span></span> 
- <span data-ttu-id="6657e-1910">valido hasta</span><span class="sxs-lookup"><span data-stu-id="6657e-1910">valido hasta</span></span> 
- <span data-ttu-id="6657e-1911">valor は</span><span class="sxs-lookup"><span data-stu-id="6657e-1911">valor</span></span> 
- <span data-ttu-id="6657e-1912">venc</span><span class="sxs-lookup"><span data-stu-id="6657e-1912">venc</span></span> 
- <span data-ttu-id="6657e-1913">vencimento</span><span class="sxs-lookup"><span data-stu-id="6657e-1913">vencimento</span></span> 
- <span data-ttu-id="6657e-1914">vencimiento</span><span class="sxs-lookup"><span data-stu-id="6657e-1914">vencimiento</span></span> 
- <span data-ttu-id="6657e-1915">verloopt</span><span class="sxs-lookup"><span data-stu-id="6657e-1915">verloopt</span></span> 
- <span data-ttu-id="6657e-1916">vervaldag</span><span class="sxs-lookup"><span data-stu-id="6657e-1916">vervaldag</span></span> 
- <span data-ttu-id="6657e-1917">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="6657e-1917">vervaldatum</span></span> 
- <span data-ttu-id="6657e-1918">vto</span><span class="sxs-lookup"><span data-stu-id="6657e-1918">vto</span></span> 
- <span data-ttu-id="6657e-1919">válido hasta</span><span class="sxs-lookup"><span data-stu-id="6657e-1919">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="6657e-1920">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1920">EU Driver's License Number</span></span>

<span data-ttu-id="6657e-1921">詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6657e-1921">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="6657e-1922">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1922">EU National Identification Number</span></span>

<span data-ttu-id="6657e-1923">詳細については、「 [EU 国立 id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6657e-1923">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="6657e-1924">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1924">EU Passport Number</span></span>

<span data-ttu-id="6657e-1925">詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6657e-1925">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="6657e-1926">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="6657e-1926">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="6657e-1927">詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6657e-1927">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="6657e-1928">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1928">EU Tax Identification Number</span></span>

<span data-ttu-id="6657e-1929">詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6657e-1929">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="6657e-1930">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="6657e-1930">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1931">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1931">Format</span></span>

<span data-ttu-id="6657e-1932">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="6657e-1932">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1933">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1933">Pattern</span></span>

<span data-ttu-id="6657e-1934">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-1934">Pattern must include all of the following:</span></span>
- <span data-ttu-id="6657e-1935">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1935">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="6657e-1936">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="6657e-1936">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="6657e-1937">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1937">Three-digit personal identification number</span></span> 
- <span data-ttu-id="6657e-1938">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="6657e-1938">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1939">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1939">Checksum</span></span>

<span data-ttu-id="6657e-1940">有</span><span class="sxs-lookup"><span data-stu-id="6657e-1940">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1941">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1941">Definition</span></span>

<span data-ttu-id="6657e-1942">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1942">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1943">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1943">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1944">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1944">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="6657e-1945">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-1945">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-1946">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1946">Keywords</span></span>

- <span data-ttu-id="6657e-1947">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="6657e-1947">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="6657e-1948">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="6657e-1948">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="6657e-1949">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="6657e-1949">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="6657e-1950">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="6657e-1950">Personbeteckning</span></span>
- <span data-ttu-id="6657e-1951">Personnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-1951">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="6657e-1952">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1952">Finland Passport Number</span></span>

<span data-ttu-id="6657e-1953">次の9つの文字と数字のパターンの組み合わせを書式設定します。9桁の文字 (大文字小文字を区別しない)、7桁のチェックサムを定義しません。 DLP ポリシーは 75% で、この種類の機密情報がある場合に、300文字の近接性: 正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1953">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-1954">Keyword_finland_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-1954">A keyword from Keyword_finland_passport_number is found.</span></span>
<span data-ttu-id="6657e-1955"><!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="6657e-1955"></span></span>
<span data-ttu-id="6657e-1956">キーワード Keyword_finland_passport_number passport Passi</span><span class="sxs-lookup"><span data-stu-id="6657e-1956">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="6657e-1957">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1957">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1958">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1958">Format</span></span>

<span data-ttu-id="6657e-1959">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1959">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1960">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1960">Pattern</span></span>

<span data-ttu-id="6657e-1961">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1961">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1962">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1962">Checksum</span></span>

<span data-ttu-id="6657e-1963">無</span><span class="sxs-lookup"><span data-stu-id="6657e-1963">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1964">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1964">Definition</span></span>

<span data-ttu-id="6657e-1965">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1965">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1966">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1966">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-1967">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-1967">At least one of the following is true:</span></span>
- <span data-ttu-id="6657e-1968">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1968">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="6657e-1969">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1969">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-1970">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1970">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="6657e-1971">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6657e-1971">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="6657e-1972">drivers licence</span><span class="sxs-lookup"><span data-stu-id="6657e-1972">drivers licence</span></span>
- <span data-ttu-id="6657e-1973">drivers license</span><span class="sxs-lookup"><span data-stu-id="6657e-1973">drivers license</span></span>
- <span data-ttu-id="6657e-1974">driving licence</span><span class="sxs-lookup"><span data-stu-id="6657e-1974">driving licence</span></span>
- <span data-ttu-id="6657e-1975">driving license</span><span class="sxs-lookup"><span data-stu-id="6657e-1975">driving license</span></span>
- <span data-ttu-id="6657e-1976">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="6657e-1976">permis de conduire</span></span>
- <span data-ttu-id="6657e-1977">licence number</span><span class="sxs-lookup"><span data-stu-id="6657e-1977">licence number</span></span>
- <span data-ttu-id="6657e-1978">license number</span><span class="sxs-lookup"><span data-stu-id="6657e-1978">license number</span></span>
- <span data-ttu-id="6657e-1979">licence numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-1979">licence numbers</span></span>
- <span data-ttu-id="6657e-1980">license numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-1980">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="6657e-1981">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="6657e-1981">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1982">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1982">Format</span></span>

<span data-ttu-id="6657e-1983">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1983">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1984">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1984">Pattern</span></span>

<span data-ttu-id="6657e-1985">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1985">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-1986">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-1986">Checksum</span></span>

<span data-ttu-id="6657e-1987">無</span><span class="sxs-lookup"><span data-stu-id="6657e-1987">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-1988">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-1988">Definition</span></span>

<span data-ttu-id="6657e-1989">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-1989">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-1990">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-1990">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-1991">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-1991">Keywords</span></span>

<span data-ttu-id="6657e-1992">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-1992">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="6657e-1993">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-1993">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-1994">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-1994">Format</span></span>

<span data-ttu-id="6657e-1995">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="6657e-1995">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-1996">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-1996">Pattern</span></span>

<span data-ttu-id="6657e-1997">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="6657e-1997">Nine digits and letters:</span></span>
- <span data-ttu-id="6657e-1998">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-1998">Two digits</span></span> 
- <span data-ttu-id="6657e-1999">2 つの文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-1999">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-2000">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2000">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2001">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2001">Checksum</span></span>

<span data-ttu-id="6657e-2002">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2002">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2003">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2003">Definition</span></span>

<span data-ttu-id="6657e-2004">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2005">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2005">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2006">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2006">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2007">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2007">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6657e-2008">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-2008">Keyword_passport</span></span>

- <span data-ttu-id="6657e-2009">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2009">Passport Number</span></span>
- <span data-ttu-id="6657e-2010">Passport No</span><span class="sxs-lookup"><span data-stu-id="6657e-2010">Passport No</span></span>
- <span data-ttu-id="6657e-2011">Passport #</span><span class="sxs-lookup"><span data-stu-id="6657e-2011">Passport #</span></span>
- <span data-ttu-id="6657e-2012">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-2012">Passport#</span></span>
- <span data-ttu-id="6657e-2013">PassportID</span><span class="sxs-lookup"><span data-stu-id="6657e-2013">PassportID</span></span>
- <span data-ttu-id="6657e-2014">Passportno</span><span class="sxs-lookup"><span data-stu-id="6657e-2014">Passportno</span></span>
- <span data-ttu-id="6657e-2015">passportnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-2015">passportnumber</span></span>
- <span data-ttu-id="6657e-2016">パスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-2016">パスポート</span></span>
- <span data-ttu-id="6657e-2017">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2017">パスポート番号</span></span>
- <span data-ttu-id="6657e-2018">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="6657e-2018">パスポートのNum</span></span>
- <span data-ttu-id="6657e-2019">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="6657e-2019">パスポート ＃</span></span> 
- <span data-ttu-id="6657e-2020">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6657e-2020">Numéro de passeport</span></span>
- <span data-ttu-id="6657e-2021">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6657e-2021">Passeport n °</span></span>
- <span data-ttu-id="6657e-2022">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="6657e-2022">Passeport Non</span></span>
- <span data-ttu-id="6657e-2023">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-2023">Passeport #</span></span>
- <span data-ttu-id="6657e-2024">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-2024">Passeport#</span></span>
- <span data-ttu-id="6657e-2025">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6657e-2025">PasseportNon</span></span>
- <span data-ttu-id="6657e-2026">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6657e-2026">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="6657e-2027">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="6657e-2027">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2028">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2028">Format</span></span>

<span data-ttu-id="6657e-2029">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2029">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2030">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2030">Pattern</span></span>

<span data-ttu-id="6657e-2031">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="6657e-2031">Must match one of two patterns:</span></span>
- <span data-ttu-id="6657e-2032">13桁の数字の後にスペースを続け、2桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2032">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="6657e-2033">または</span><span class="sxs-lookup"><span data-stu-id="6657e-2033">or</span></span>
- <span data-ttu-id="6657e-2034">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2034">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2035">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2035">Checksum</span></span>

<span data-ttu-id="6657e-2036">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2036">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2037">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2037">Definition</span></span>

<span data-ttu-id="6657e-2038">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2038">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2039">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2039">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2040">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2040">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="6657e-2041">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2041">The checksum passes.</span></span>

<span data-ttu-id="6657e-2042">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2042">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2043">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2043">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2044">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-2044">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="6657e-2045">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2045">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2046">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2046">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="6657e-2047">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="6657e-2047">Keyword_fr_insee</span></span>

- <span data-ttu-id="6657e-2048">insee</span><span class="sxs-lookup"><span data-stu-id="6657e-2048">insee</span></span>
- <span data-ttu-id="6657e-2049">securité sociale</span><span class="sxs-lookup"><span data-stu-id="6657e-2049">securité sociale</span></span>
- <span data-ttu-id="6657e-2050">securite sociale</span><span class="sxs-lookup"><span data-stu-id="6657e-2050">securite sociale</span></span>
- <span data-ttu-id="6657e-2051">national id</span><span class="sxs-lookup"><span data-stu-id="6657e-2051">national id</span></span>
- <span data-ttu-id="6657e-2052">national identification</span><span class="sxs-lookup"><span data-stu-id="6657e-2052">national identification</span></span>
- <span data-ttu-id="6657e-2053">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="6657e-2053">numéro d'identité</span></span>
- <span data-ttu-id="6657e-2054">no d'identité</span><span class="sxs-lookup"><span data-stu-id="6657e-2054">no d'identité</span></span>
- <span data-ttu-id="6657e-2055">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-2055">no.</span></span> <span data-ttu-id="6657e-2056">d'identité</span><span class="sxs-lookup"><span data-stu-id="6657e-2056">d'identité</span></span>
- <span data-ttu-id="6657e-2057">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="6657e-2057">numero d'identite</span></span>
- <span data-ttu-id="6657e-2058">no d'identite</span><span class="sxs-lookup"><span data-stu-id="6657e-2058">no d'identite</span></span>
- <span data-ttu-id="6657e-2059">違います。</span><span class="sxs-lookup"><span data-stu-id="6657e-2059">no.</span></span> <span data-ttu-id="6657e-2060">d'identite</span><span class="sxs-lookup"><span data-stu-id="6657e-2060">d'identite</span></span>
- <span data-ttu-id="6657e-2061">social security number</span><span class="sxs-lookup"><span data-stu-id="6657e-2061">social security number</span></span>
- <span data-ttu-id="6657e-2062">social security code</span><span class="sxs-lookup"><span data-stu-id="6657e-2062">social security code</span></span>
- <span data-ttu-id="6657e-2063">social insurance number</span><span class="sxs-lookup"><span data-stu-id="6657e-2063">social insurance number</span></span>
- <span data-ttu-id="6657e-2064">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="6657e-2064">le numéro d'identification nationale</span></span>
- <span data-ttu-id="6657e-2065">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="6657e-2065">d'identité nationale</span></span>
- <span data-ttu-id="6657e-2066">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="6657e-2066">numéro de sécurité sociale</span></span>
- <span data-ttu-id="6657e-2067">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="6657e-2067">le code de la sécurité sociale</span></span>
- <span data-ttu-id="6657e-2068">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="6657e-2068">numéro d'assurance sociale</span></span>
- <span data-ttu-id="6657e-2069">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="6657e-2069">numéro de sécu</span></span>
- <span data-ttu-id="6657e-2070">code sécu</span><span class="sxs-lookup"><span data-stu-id="6657e-2070">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="6657e-2071">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2071">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2072">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2072">Format</span></span>

<span data-ttu-id="6657e-2073">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-2073">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2074">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2074">Pattern</span></span>

<span data-ttu-id="6657e-2075">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="6657e-2075">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="6657e-2076">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2076">A digit or letter</span></span> 
- <span data-ttu-id="6657e-2077">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2077">Two digits</span></span> 
- <span data-ttu-id="6657e-2078">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2078">Six digits or letters</span></span> 
- <span data-ttu-id="6657e-2079">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2079">A digit</span></span> 
- <span data-ttu-id="6657e-2080">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2080">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2081">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2081">Checksum</span></span>

<span data-ttu-id="6657e-2082">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2083">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2083">Definition</span></span>

<span data-ttu-id="6657e-2084">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2084">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2085">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2085">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2086">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-2086">At least one of the following is true:</span></span>
    - <span data-ttu-id="6657e-2087">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2087">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="6657e-2088">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2088">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="6657e-2089">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2089">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="6657e-2090">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2090">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2091">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2091">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="6657e-2092">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2092">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="6657e-2093">Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2093">Führerschein</span></span>
- <span data-ttu-id="6657e-2094">futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2094">Fuhrerschein</span></span>
- <span data-ttu-id="6657e-2095">futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="6657e-2095">Fuehrerschein</span></span>
- <span data-ttu-id="6657e-2096">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2096">Führerscheinnummer</span></span>
- <span data-ttu-id="6657e-2097">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2097">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="6657e-2098">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2098">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="6657e-2099">Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2099">Führerschein-</span></span> 
- <span data-ttu-id="6657e-2100">futex (中)</span><span class="sxs-lookup"><span data-stu-id="6657e-2100">Fuhrerschein-</span></span> 
- <span data-ttu-id="6657e-2101">futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="6657e-2101">Fuehrerschein-</span></span> 
- <span data-ttu-id="6657e-2102">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6657e-2102">FührerscheinnummerNr</span></span>
- <span data-ttu-id="6657e-2103">futex がある hていません einnumnr</span><span class="sxs-lookup"><span data-stu-id="6657e-2103">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="6657e-2104">futex の ehの再リリース/einnumnr</span><span class="sxs-lookup"><span data-stu-id="6657e-2104">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="6657e-2105">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2105">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="6657e-2106">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2106">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="6657e-2107">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2107">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="6657e-2108">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2108">Führerschein- Nr</span></span>
- <span data-ttu-id="6657e-2109">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2109">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="6657e-2110">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2110">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="6657e-2111">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2111">Führerschein- Klasse</span></span> 
- <span data-ttu-id="6657e-2112">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2112">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="6657e-2113">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2113">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="6657e-2114">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="6657e-2114">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="6657e-2115">futex がある hていません einnumnr</span><span class="sxs-lookup"><span data-stu-id="6657e-2115">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="6657e-2116">futex の ehの再リリース/einnumnr</span><span class="sxs-lookup"><span data-stu-id="6657e-2116">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="6657e-2117">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2117">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="6657e-2118">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2118">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="6657e-2119">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2119">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="6657e-2120">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2120">Führerschein- Nr</span></span> 
- <span data-ttu-id="6657e-2121">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2121">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="6657e-2122">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2122">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="6657e-2123">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2123">Führerschein- Klasse</span></span> 
- <span data-ttu-id="6657e-2124">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2124">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="6657e-2125">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2125">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="6657e-2126">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-2126">DL</span></span> 
- <span data-ttu-id="6657e-2127">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-2127">DLS</span></span>
- <span data-ttu-id="6657e-2128">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-2128">Driv Lic</span></span> 
- <span data-ttu-id="6657e-2129">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="6657e-2129">Driv Licen</span></span> 
- <span data-ttu-id="6657e-2130">Driv License</span><span class="sxs-lookup"><span data-stu-id="6657e-2130">Driv License</span></span>
- <span data-ttu-id="6657e-2131">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2131">Driv Licenses</span></span> 
- <span data-ttu-id="6657e-2132">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-2132">Driv Licence</span></span> 
- <span data-ttu-id="6657e-2133">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-2133">Driv Licences</span></span> 
- <span data-ttu-id="6657e-2134">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-2134">Driv Lic</span></span> 
- <span data-ttu-id="6657e-2135">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="6657e-2135">Driver Licen</span></span> 
- <span data-ttu-id="6657e-2136">Driver License</span><span class="sxs-lookup"><span data-stu-id="6657e-2136">Driver License</span></span> 
- <span data-ttu-id="6657e-2137">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2137">Driver Licenses</span></span> 
- <span data-ttu-id="6657e-2138">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-2138">Driver Licence</span></span> 
- <span data-ttu-id="6657e-2139">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-2139">Driver Licences</span></span> 
- <span data-ttu-id="6657e-2140">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-2140">Drivers Lic</span></span> 
- <span data-ttu-id="6657e-2141">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="6657e-2141">Drivers Licen</span></span> 
- <span data-ttu-id="6657e-2142">Drivers License</span><span class="sxs-lookup"><span data-stu-id="6657e-2142">Drivers License</span></span> 
- <span data-ttu-id="6657e-2143">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2143">Drivers Licenses</span></span> 
- <span data-ttu-id="6657e-2144">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-2144">Drivers Licence</span></span> 
- <span data-ttu-id="6657e-2145">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-2145">Drivers Licences</span></span> 
- <span data-ttu-id="6657e-2146">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-2146">Driver's Lic</span></span> 
- <span data-ttu-id="6657e-2147">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="6657e-2147">Driver's Licen</span></span> 
- <span data-ttu-id="6657e-2148">Driver's License</span><span class="sxs-lookup"><span data-stu-id="6657e-2148">Driver's License</span></span> 
- <span data-ttu-id="6657e-2149">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2149">Driver's Licenses</span></span> 
- <span data-ttu-id="6657e-2150">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-2150">Driver's Licence</span></span> 
- <span data-ttu-id="6657e-2151">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-2151">Driver's Licences</span></span> 
- <span data-ttu-id="6657e-2152">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-2152">Driving Lic</span></span> 
- <span data-ttu-id="6657e-2153">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="6657e-2153">Driving Licen</span></span> 
- <span data-ttu-id="6657e-2154">Driving License</span><span class="sxs-lookup"><span data-stu-id="6657e-2154">Driving License</span></span> 
- <span data-ttu-id="6657e-2155">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2155">Driving Licenses</span></span> 
- <span data-ttu-id="6657e-2156">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="6657e-2156">Driving Licence</span></span> 
- <span data-ttu-id="6657e-2157">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="6657e-2157">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="6657e-2158">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="6657e-2158">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="6657e-2159">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2159">Nr-Führerschein</span></span> 
- <span data-ttu-id="6657e-2160">Nr-futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2160">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="6657e-2161">"Nr" という futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2161">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="6657e-2162">Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2162">No-Führerschein</span></span> 
- <span data-ttu-id="6657e-2163">(futex なし)</span><span class="sxs-lookup"><span data-stu-id="6657e-2163">No-Fuhrerschein</span></span> 
- <span data-ttu-id="6657e-2164">その他の ehの場合</span><span class="sxs-lookup"><span data-stu-id="6657e-2164">No-Fuehrerschein</span></span> 
- <span data-ttu-id="6657e-2165">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2165">N-Führerschein</span></span> 
- <span data-ttu-id="6657e-2166">N の futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2166">N-Fuhrerschein</span></span> 
- <span data-ttu-id="6657e-2167">N 桁の ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="6657e-2167">N-Fuehrerschein</span></span>
- <span data-ttu-id="6657e-2168">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2168">Nr-Führerschein</span></span> 
- <span data-ttu-id="6657e-2169">Nr-futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2169">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="6657e-2170">"Nr" という futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2170">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="6657e-2171">Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2171">No-Führerschein</span></span> 
- <span data-ttu-id="6657e-2172">(futex なし)</span><span class="sxs-lookup"><span data-stu-id="6657e-2172">No-Fuhrerschein</span></span> 
- <span data-ttu-id="6657e-2173">その他の ehの場合</span><span class="sxs-lookup"><span data-stu-id="6657e-2173">No-Fuehrerschein</span></span> 
- <span data-ttu-id="6657e-2174">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="6657e-2174">N-Führerschein</span></span> 
- <span data-ttu-id="6657e-2175">N の futex</span><span class="sxs-lookup"><span data-stu-id="6657e-2175">N-Fuhrerschein</span></span> 
- <span data-ttu-id="6657e-2176">N 桁の ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="6657e-2176">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="6657e-2177">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6657e-2177">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="6657e-2178">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-2178">ausstellungsdatum</span></span>
- <span data-ttu-id="6657e-2179">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="6657e-2179">ausstellungsort</span></span>
- <span data-ttu-id="6657e-2180">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="6657e-2180">ausstellende behöde</span></span>
- <span data-ttu-id="6657e-2181">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="6657e-2181">ausstellende behorde</span></span>
- <span data-ttu-id="6657e-2182">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="6657e-2182">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="6657e-2183">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2183">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2184">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2184">Format</span></span>

<span data-ttu-id="6657e-2185">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2185">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2186">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2186">Pattern</span></span>

<span data-ttu-id="6657e-2187">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-2187">Pattern must include all of the following:</span></span>
- <span data-ttu-id="6657e-2188">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2188">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="6657e-2189">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2189">Three digits</span></span> 
- <span data-ttu-id="6657e-2190">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="6657e-2190">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="6657e-2191">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2191">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2192">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2192">Checksum</span></span>

<span data-ttu-id="6657e-2193">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2194">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2194">Definition</span></span>

<span data-ttu-id="6657e-2195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2196">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2196">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2197">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2197">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="6657e-2198">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2198">The checksum passes.</span></span>

<span data-ttu-id="6657e-2199">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2199">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2200">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2200">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2201">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2201">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="6657e-2202">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2202">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2203">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2203">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="6657e-2204">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-2204">Keyword_german_passport</span></span>

- <span data-ttu-id="6657e-2205">reisepass</span><span class="sxs-lookup"><span data-stu-id="6657e-2205">reisepass</span></span>
- <span data-ttu-id="6657e-2206">reisepasse</span><span class="sxs-lookup"><span data-stu-id="6657e-2206">reisepasse</span></span>
- <span data-ttu-id="6657e-2207">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2207">reisepassnummer</span></span>
- <span data-ttu-id="6657e-2208">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-2208">passport</span></span>
- <span data-ttu-id="6657e-2209">passport</span><span class="sxs-lookup"><span data-stu-id="6657e-2209">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="6657e-2210">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="6657e-2210">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="6657e-2211">ge気流 tsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-2211">geburtsdatum</span></span>
- <span data-ttu-id="6657e-2212">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="6657e-2212">ausstellungsdatum</span></span>
- <span data-ttu-id="6657e-2213">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="6657e-2213">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="6657e-2214">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2214">Keyword_german_passport_number</span></span>

<span data-ttu-id="6657e-2215">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="6657e-2215">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="6657e-2216">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="6657e-2216">Keyword_german_passport1</span></span>

<span data-ttu-id="6657e-2217">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="6657e-2217">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="6657e-2218">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="6657e-2218">Keyword_german_passport2</span></span>

<span data-ttu-id="6657e-2219">bnationalit</span><span class="sxs-lookup"><span data-stu-id="6657e-2219">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="6657e-2220">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2220">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2221">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2221">Format</span></span>

<span data-ttu-id="6657e-2222">2010年11月1日以降: 9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2222">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="6657e-2223">1987年4月1日から2010年10月31日まで:10 桁</span><span class="sxs-lookup"><span data-stu-id="6657e-2223">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2224">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2224">Pattern</span></span>

<span data-ttu-id="6657e-2225">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="6657e-2225">Since 1 November 2010:</span></span>
- <span data-ttu-id="6657e-2226">1 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2226">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-2227">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2227">Eight digits</span></span>

<span data-ttu-id="6657e-2228">1987年4月1日から2010年10月31日まで。</span><span class="sxs-lookup"><span data-stu-id="6657e-2228">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="6657e-2229">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2229">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2230">Checksum</span></span>

<span data-ttu-id="6657e-2231">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2232">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2232">Definition</span></span>

<span data-ttu-id="6657e-2233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2233">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2234">正規表現 Regex_germany_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2234">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2235">Keyword_germany_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2235">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2236">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2236">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="6657e-2237">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="6657e-2237">Keyword_germany_id_card</span></span>

- <span data-ttu-id="6657e-2238">Identity Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2238">Identity Card</span></span>
- <span data-ttu-id="6657e-2239">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2239">ID</span></span>
- <span data-ttu-id="6657e-2240">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-2240">Identification</span></span>
- <span data-ttu-id="6657e-2241">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="6657e-2241">Personalausweis</span></span>
- <span data-ttu-id="6657e-2242">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2242">Identifizierungsnummer</span></span>
- <span data-ttu-id="6657e-2243">Ausweis</span><span class="sxs-lookup"><span data-stu-id="6657e-2243">Ausweis</span></span>
- <span data-ttu-id="6657e-2244">Identifikation</span><span class="sxs-lookup"><span data-stu-id="6657e-2244">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="6657e-2245">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2245">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2246">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2246">Format</span></span>

<span data-ttu-id="6657e-2247">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="6657e-2247">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2248">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2248">Pattern</span></span>

<span data-ttu-id="6657e-2249">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="6657e-2249">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="6657e-2250">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="6657e-2250">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="6657e-2251">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-2251">A dash</span></span> 
- <span data-ttu-id="6657e-2252">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2252">Six digits</span></span>

<span data-ttu-id="6657e-2253">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="6657e-2253">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="6657e-2254">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2254">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="6657e-2255">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-2255">A dash</span></span> 
- <span data-ttu-id="6657e-2256">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2256">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2257">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2257">Checksum</span></span>

<span data-ttu-id="6657e-2258">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2258">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2259">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2259">Definition</span></span>

<span data-ttu-id="6657e-2260">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2261">正規表現 Regex_greece_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2261">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2262">Keyword_greece_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2262">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2263">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2263">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="6657e-2264">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="6657e-2264">Keyword_greece_id_card</span></span>

- <span data-ttu-id="6657e-2265">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2265">Greek identity Card</span></span>
- <span data-ttu-id="6657e-2266">tautotita</span><span class="sxs-lookup"><span data-stu-id="6657e-2266">Tautotita</span></span>
- <span data-ttu-id="6657e-2267">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="6657e-2267">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="6657e-2268">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="6657e-2268">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="6657e-2269">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2269">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2270">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2270">Format</span></span>

<span data-ttu-id="6657e-2271">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="6657e-2271">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2272">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2272">Pattern</span></span>

<span data-ttu-id="6657e-2273">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="6657e-2273">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="6657e-2274">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2274">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-2275">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2275">Six digits</span></span> 
- <span data-ttu-id="6657e-2276">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="6657e-2276">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2277">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2277">Checksum</span></span>

<span data-ttu-id="6657e-2278">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2278">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2279">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2279">Definition</span></span>

<span data-ttu-id="6657e-2280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2281">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2281">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2282">Keyword_hong_kong_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2282">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="6657e-2283">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2283">The checksum passes.</span></span>

<span data-ttu-id="6657e-2284">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2284">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2285">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2285">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2286">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2286">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2287">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2287">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="6657e-2288">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="6657e-2288">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="6657e-2289">香港の id カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2289">hong kong identity card</span></span>
- <span data-ttu-id="6657e-2290">hkidc</span><span class="sxs-lookup"><span data-stu-id="6657e-2290">HKIDC</span></span>
- <span data-ttu-id="6657e-2291">id card</span><span class="sxs-lookup"><span data-stu-id="6657e-2291">id card</span></span>
- <span data-ttu-id="6657e-2292">Identity card</span><span class="sxs-lookup"><span data-stu-id="6657e-2292">identity card</span></span>
- <span data-ttu-id="6657e-2293">hk の id カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2293">hk identity card</span></span>
- <span data-ttu-id="6657e-2294">香港特別行政 id</span><span class="sxs-lookup"><span data-stu-id="6657e-2294">hong kong id</span></span>
- <span data-ttu-id="6657e-2295">香港身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2295">香港身份證</span></span>
- <span data-ttu-id="6657e-2296">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2296">香港永久性居民身份證</span></span>
- <span data-ttu-id="6657e-2297">身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2297">身份證</span></span>
- <span data-ttu-id="6657e-2298">身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2298">身份証</span></span>
- <span data-ttu-id="6657e-2299">身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2299">身分證</span></span>
- <span data-ttu-id="6657e-2300">身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2300">身分証</span></span>
- <span data-ttu-id="6657e-2301">香港身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2301">香港身份証</span></span>
- <span data-ttu-id="6657e-2302">香港身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2302">香港身分證</span></span>
- <span data-ttu-id="6657e-2303">香港身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2303">香港身分証</span></span>
- <span data-ttu-id="6657e-2304">香港身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2304">香港身份證</span></span>
- <span data-ttu-id="6657e-2305">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2305">香港居民身份證</span></span>
- <span data-ttu-id="6657e-2306">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2306">香港居民身份証</span></span>
- <span data-ttu-id="6657e-2307">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2307">香港居民身分證</span></span>
- <span data-ttu-id="6657e-2308">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2308">香港居民身分証</span></span>
- <span data-ttu-id="6657e-2309">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2309">香港永久性居民身份証</span></span>
- <span data-ttu-id="6657e-2310">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2310">香港永久性居民身分證</span></span>
- <span data-ttu-id="6657e-2311">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2311">香港永久性居民身分証</span></span>
- <span data-ttu-id="6657e-2312">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2312">香港永久性居民身份證</span></span>
- <span data-ttu-id="6657e-2313">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2313">香港非永久性居民身份證</span></span>
- <span data-ttu-id="6657e-2314">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2314">香港非永久性居民身份証</span></span>
- <span data-ttu-id="6657e-2315">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2315">香港非永久性居民身分證</span></span>
- <span data-ttu-id="6657e-2316">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2316">香港非永久性居民身分証</span></span>
- <span data-ttu-id="6657e-2317">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2317">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="6657e-2318">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2318">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="6657e-2319">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2319">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="6657e-2320">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2320">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="6657e-2321">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-2321">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="6657e-2322">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="6657e-2322">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="6657e-2323">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-2323">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="6657e-2324">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="6657e-2324">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="6657e-2325">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="6657e-2325">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2326">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2326">Format</span></span>

<span data-ttu-id="6657e-2327">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2327">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2328">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2328">Pattern</span></span>

<span data-ttu-id="6657e-2329">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2329">10 letters or digits:</span></span>
- <span data-ttu-id="6657e-2330">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2330">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-2331">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2331">Four digits</span></span> 
- <span data-ttu-id="6657e-2332">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2332">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2333">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2333">Checksum</span></span>

<span data-ttu-id="6657e-2334">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2335">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2335">Definition</span></span>

<span data-ttu-id="6657e-2336">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2337">正規表現 Regex_india_permanent_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2337">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2338">Keyword_india_permanent_account_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2338">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="6657e-2339">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2339">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2340">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2340">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="6657e-2341">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2341">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="6657e-2342">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2342">Permanent Account Number</span></span> 
- <span data-ttu-id="6657e-2343">ペン</span><span class="sxs-lookup"><span data-stu-id="6657e-2343">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="6657e-2344">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2344">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2345">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2345">Format</span></span>

<span data-ttu-id="6657e-2346">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2346">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2347">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2347">Pattern</span></span>

<span data-ttu-id="6657e-2348">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2348">12 digits:</span></span>
- <span data-ttu-id="6657e-2349">4 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2349">Four digits</span></span> 
- <span data-ttu-id="6657e-2350">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2350">An optional space or dash</span></span> 
- <span data-ttu-id="6657e-2351">4 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2351">Four digits</span></span> 
- <span data-ttu-id="6657e-2352">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2352">An optional space or dash</span></span> 
- <span data-ttu-id="6657e-2353">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="6657e-2353">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2354">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2354">Checksum</span></span>

<span data-ttu-id="6657e-2355">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2355">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2356">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2356">Definition</span></span>

<span data-ttu-id="6657e-2357">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2357">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-2358">Keyword_india_aadhar からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2358">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="6657e-2359">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2359">The checksum passes.</span></span>
<span data-ttu-id="6657e-2360">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-2361">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2361">The checksum passes.</span></span>
<span data-ttu-id="6657e-2362"><!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="6657e-2362"></span></span>

### <a name="keywords"></a><span data-ttu-id="6657e-2363">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2363">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="6657e-2364">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="6657e-2364">Keyword_india_aadhar</span></span>
- <span data-ttu-id="6657e-2365">Aadhar</span><span class="sxs-lookup"><span data-stu-id="6657e-2365">Aadhar</span></span>
- <span data-ttu-id="6657e-2366">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="6657e-2366">Aadhaar</span></span>
- <span data-ttu-id="6657e-2367">UID</span><span class="sxs-lookup"><span data-stu-id="6657e-2367">UID</span></span>
- <span data-ttu-id="6657e-2368">आधार</span><span class="sxs-lookup"><span data-stu-id="6657e-2368">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="6657e-2369">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2369">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2370">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2370">Format</span></span>

<span data-ttu-id="6657e-2371">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2371">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2372">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2372">Pattern</span></span>

<span data-ttu-id="6657e-2373">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2373">16 digits:</span></span>
- <span data-ttu-id="6657e-2374">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="6657e-2374">Two-digit province code</span></span> 
- <span data-ttu-id="6657e-2375">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2375">A period (optional)</span></span> 
- <span data-ttu-id="6657e-2376">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="6657e-2376">Two-digit regency or city code</span></span> 
- <span data-ttu-id="6657e-2377">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="6657e-2377">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="6657e-2378">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2378">A period (optional)</span></span> 
- <span data-ttu-id="6657e-2379">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2379">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6657e-2380">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2380">A period (optional)</span></span> 
- <span data-ttu-id="6657e-2381">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2381">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2382">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2382">Checksum</span></span>

<span data-ttu-id="6657e-2383">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2383">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2384">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2384">Definition</span></span>

<span data-ttu-id="6657e-2385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2386">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2386">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2387">Keyword_indonesia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2387">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="6657e-2388">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2388">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2389">正規表現 Regex_indonesia_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2389">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2390">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2390">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="6657e-2391">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="6657e-2391">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="6657e-2392">KTP</span><span class="sxs-lookup"><span data-stu-id="6657e-2392">KTP</span></span>
- <span data-ttu-id="6657e-2393">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="6657e-2393">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="6657e-2394">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="6657e-2394">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="6657e-2395">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="6657e-2395">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2396">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2396">Format</span></span>

<span data-ttu-id="6657e-2397">国コード (2 文字)、チェックディジット (2 桁)、および番号を bban 最大30文字)</span><span class="sxs-lookup"><span data-stu-id="6657e-2397">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2398">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2398">Pattern</span></span>

<span data-ttu-id="6657e-2399">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-2399">Pattern must include all of the following:</span></span>

- <span data-ttu-id="6657e-2400">2文字の国コード</span><span class="sxs-lookup"><span data-stu-id="6657e-2400">Two-letter country code</span></span>
- <span data-ttu-id="6657e-2401">2つのチェックディジット (オプションのスペースが続く)</span><span class="sxs-lookup"><span data-stu-id="6657e-2401">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="6657e-2402">1-7 4 つの文字または数字のグループ (スペースで区切ることができます)</span><span class="sxs-lookup"><span data-stu-id="6657e-2402">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="6657e-2403">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2403">1-3 letters or digits</span></span>

<span data-ttu-id="6657e-2404">各国の形式は少し異なります。</span><span class="sxs-lookup"><span data-stu-id="6657e-2404">The format for each country is slightly different.</span></span> <span data-ttu-id="6657e-2405">IBAN 機密情報の種類には、次の60国が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6657e-2405">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="6657e-2406">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、hu、gl、gr、hr、、ie、il、、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="6657e-2406">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2407">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2407">Checksum</span></span>

<span data-ttu-id="6657e-2408">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2408">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2409">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2409">Definition</span></span>

<span data-ttu-id="6657e-2410">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2410">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2411">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2411">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2412">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2412">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2413">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2413">Keywords</span></span>

<span data-ttu-id="6657e-2414">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-2414">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="6657e-2415">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="6657e-2415">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2416">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2416">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="6657e-2417">IPv4</span><span class="sxs-lookup"><span data-stu-id="6657e-2417">IPv4:</span></span>
<span data-ttu-id="6657e-2418">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2418">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="6657e-2419">IPv6</span><span class="sxs-lookup"><span data-stu-id="6657e-2419">IPv6:</span></span>
<span data-ttu-id="6657e-2420"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2420">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2421">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2421">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2422">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2422">Checksum</span></span>

<span data-ttu-id="6657e-2423">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2424">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2424">Definition</span></span>

<span data-ttu-id="6657e-2425">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2425">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2426">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2426">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2427">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-2427">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="6657e-2428">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2428">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2429">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2429">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2430">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2430">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="6657e-2431">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2431">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2432">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2432">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2433">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-2433">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2434">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2434">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="6657e-2435">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="6657e-2435">Keyword_ipaddress</span></span>

- <span data-ttu-id="6657e-2436">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="6657e-2436">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="6657e-2437">ip address</span><span class="sxs-lookup"><span data-stu-id="6657e-2437">ip address</span></span> 
- <span data-ttu-id="6657e-2438">ip addresses</span><span class="sxs-lookup"><span data-stu-id="6657e-2438">ip addresses</span></span>
- <span data-ttu-id="6657e-2439">internet protocol</span><span class="sxs-lookup"><span data-stu-id="6657e-2439">internet protocol</span></span>
- <span data-ttu-id="6657e-2440">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="6657e-2440">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="6657e-2441">Diseases の国際分類 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="6657e-2441">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2442">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2442">Format</span></span>

<span data-ttu-id="6657e-2443">Dictionary</span><span class="sxs-lookup"><span data-stu-id="6657e-2443">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2444">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2444">Pattern</span></span>

<span data-ttu-id="6657e-2445">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2445">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2446">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2446">Checksum</span></span>

<span data-ttu-id="6657e-2447">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2447">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2448">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2448">Definition</span></span>

<span data-ttu-id="6657e-2449">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2449">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2450">Dictionary_icd_10_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2450">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="6657e-2451">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2451">Keywords</span></span>

<span data-ttu-id="6657e-2452">Dictionary_icd_10_cm キーワードディクショナリの用語。 [Diseases、10リビジョン、臨床修正 (icd-10-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6657e-2452">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="6657e-2453">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6657e-2453">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="6657e-2454">Diseases の国際分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="6657e-2454">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2455">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2455">Format</span></span>

<span data-ttu-id="6657e-2456">Dictionary</span><span class="sxs-lookup"><span data-stu-id="6657e-2456">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2457">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2457">Pattern</span></span>

<span data-ttu-id="6657e-2458">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2458">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2459">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2459">Checksum</span></span>

<span data-ttu-id="6657e-2460">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2460">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2461">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2461">Definition</span></span>

<span data-ttu-id="6657e-2462">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2462">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2463">Dictionary_icd_9_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2463">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2464">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2464">Keywords</span></span>

<span data-ttu-id="6657e-2465">Dictionary_icd_9_cm キーワードディクショナリの用語。 [Diseases、9リビジョン、臨床修正 (icd-9-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="6657e-2465">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="6657e-2466">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6657e-2466">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="6657e-2467">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2467">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2468">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2468">Format</span></span>

<span data-ttu-id="6657e-2469">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="6657e-2469">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="6657e-2470">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2470">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="6657e-2471">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="6657e-2471">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="6657e-2472">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2472">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2473">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2473">Pattern</span></span>

<span data-ttu-id="6657e-2474">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="6657e-2474">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="6657e-2475">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2475">Seven digits</span></span> 
- <span data-ttu-id="6657e-2476">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2476">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="6657e-2477">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="6657e-2477">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="6657e-2478">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2478">Seven digits</span></span> 
- <span data-ttu-id="6657e-2479">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2479">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="6657e-2480">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="6657e-2480">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2481">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2481">Checksum</span></span>

<span data-ttu-id="6657e-2482">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2482">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2483">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2483">Definition</span></span>

<span data-ttu-id="6657e-2484">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2484">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2485">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2485">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2486">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-2486">One of the following is true:</span></span>
    - <span data-ttu-id="6657e-2487">Keyword_ireland_pps からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2487">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="6657e-2488">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2488">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="6657e-2489">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2489">The checksum passes.</span></span>

<span data-ttu-id="6657e-2490">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2490">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2491">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2491">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2492">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2492">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2493">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2493">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="6657e-2494">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="6657e-2494">Keyword_ireland_pps</span></span>

- <span data-ttu-id="6657e-2495">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2495">Personal Public Service Number</span></span> 
- <span data-ttu-id="6657e-2496">PPS Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2496">PPS Number</span></span> 
- <span data-ttu-id="6657e-2497">PPS Num</span><span class="sxs-lookup"><span data-stu-id="6657e-2497">PPS Num</span></span> 
- <span data-ttu-id="6657e-2498">PPS No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2498">PPS No.</span></span> 
- <span data-ttu-id="6657e-2499">PPS #</span><span class="sxs-lookup"><span data-stu-id="6657e-2499">PPS #</span></span> 
- <span data-ttu-id="6657e-2500">PPS</span><span class="sxs-lookup"><span data-stu-id="6657e-2500">PPS#</span></span> 
- <span data-ttu-id="6657e-2501">ppsn</span><span class="sxs-lookup"><span data-stu-id="6657e-2501">PPSN</span></span> 
- <span data-ttu-id="6657e-2502">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2502">Public Services Card</span></span> 
- <span data-ttu-id="6657e-2503">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="6657e-2503">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="6657e-2504">Uimh。</span><span class="sxs-lookup"><span data-stu-id="6657e-2504">Uimh.</span></span> <span data-ttu-id="6657e-2505">PSP</span><span class="sxs-lookup"><span data-stu-id="6657e-2505">PSP</span></span> 
- <span data-ttu-id="6657e-2506">PSP</span><span class="sxs-lookup"><span data-stu-id="6657e-2506">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="6657e-2507">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2507">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2508">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2508">Format</span></span>

<span data-ttu-id="6657e-2509">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2509">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2510">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2510">Pattern</span></span>

<span data-ttu-id="6657e-2511">さ</span><span class="sxs-lookup"><span data-stu-id="6657e-2511">Formatted:</span></span>
- <span data-ttu-id="6657e-2512">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2512">Two digits</span></span> 
- <span data-ttu-id="6657e-2513">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-2513">A dash</span></span> 
- <span data-ttu-id="6657e-2514">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2514">Three digits</span></span> 
- <span data-ttu-id="6657e-2515">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-2515">A dash</span></span> 
- <span data-ttu-id="6657e-2516">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2516">Eight digits</span></span>

<span data-ttu-id="6657e-2517">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-2517">Unformatted:</span></span>
- <span data-ttu-id="6657e-2518">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2518">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2519">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2519">Checksum</span></span>

<span data-ttu-id="6657e-2520">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2520">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2521">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2521">Definition</span></span>

<span data-ttu-id="6657e-2522">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2523">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2523">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2524">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2524">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2525">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2525">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="6657e-2526">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2526">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="6657e-2527">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2527">Bank Account Number</span></span> 
- <span data-ttu-id="6657e-2528">Bank Account</span><span class="sxs-lookup"><span data-stu-id="6657e-2528">Bank Account</span></span> 
- <span data-ttu-id="6657e-2529">Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2529">Account Number</span></span> 
- <span data-ttu-id="6657e-2530">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="6657e-2530">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="6657e-2531">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2531">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2532">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2532">Format</span></span>

<span data-ttu-id="6657e-2533">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2533">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2534">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2534">Pattern</span></span>

<span data-ttu-id="6657e-2535">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2535">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2536">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2536">Checksum</span></span>

<span data-ttu-id="6657e-2537">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2537">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2538">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2538">Definition</span></span>

<span data-ttu-id="6657e-2539">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2540">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2540">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2541">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2541">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="6657e-2542">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2542">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2543">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2543">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="6657e-2544">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2544">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="6657e-2545">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="6657e-2545">מספר זהות</span></span> 
- <span data-ttu-id="6657e-2546">National ID Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2546">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="6657e-2547">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2547">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2548">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2548">Format</span></span>

<span data-ttu-id="6657e-2549">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-2549">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2550">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2550">Pattern</span></span>

- <span data-ttu-id="6657e-2551">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="6657e-2551">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="6657e-2552">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-2552">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-2553">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-2553">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-2554">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="6657e-2554">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="6657e-2555">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-2555">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2556">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2556">Checksum</span></span>

<span data-ttu-id="6657e-2557">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2557">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2558">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2558">Definition</span></span>

<span data-ttu-id="6657e-2559">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2559">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2560">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2560">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2561">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2561">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2562">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2562">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="6657e-2563">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2563">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="6657e-2564">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="6657e-2564">numero di patente di guida</span></span> 
- <span data-ttu-id="6657e-2565">patente di guida</span><span class="sxs-lookup"><span data-stu-id="6657e-2565">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="6657e-2566">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2566">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2567">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2567">Format</span></span>

<span data-ttu-id="6657e-2568">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2568">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2569">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2569">Pattern</span></span>

<span data-ttu-id="6657e-2570">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="6657e-2570">Bank account number:</span></span>
- <span data-ttu-id="6657e-2571">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2571">Seven or eight digits</span></span>
- <span data-ttu-id="6657e-2572">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="6657e-2572">Bank account branch code:</span></span>
- <span data-ttu-id="6657e-2573">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2573">Four digits</span></span> 
- <span data-ttu-id="6657e-2574">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="6657e-2574">A space or dash (optional)</span></span> 
- <span data-ttu-id="6657e-2575">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2575">Three digits</span></span>

<span data-ttu-id="6657e-2576">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2576">Checksum</span></span>

<span data-ttu-id="6657e-2577">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2577">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2578">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2578">Definition</span></span>

<span data-ttu-id="6657e-2579">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2580">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2580">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2581">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2581">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="6657e-2582">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-2582">One of the following is true:</span></span>
- <span data-ttu-id="6657e-2583">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2583">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2584">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2584">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="6657e-2585">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2585">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2586">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2586">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2587">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2587">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2588">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2588">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="6657e-2589">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="6657e-2589">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="6657e-2590">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2590">Checking Account Number</span></span> 
- <span data-ttu-id="6657e-2591">Checking Account</span><span class="sxs-lookup"><span data-stu-id="6657e-2591">Checking Account</span></span> 
- <span data-ttu-id="6657e-2592">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-2592">Checking Account #</span></span> 
- <span data-ttu-id="6657e-2593">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2593">Checking Acct Number</span></span> 
- <span data-ttu-id="6657e-2594">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-2594">Checking Acct #</span></span> 
- <span data-ttu-id="6657e-2595">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2595">Checking Acct No.</span></span> 
- <span data-ttu-id="6657e-2596">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2596">Checking Account No.</span></span> 
- <span data-ttu-id="6657e-2597">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2597">Bank Account Number</span></span> 
- <span data-ttu-id="6657e-2598">Bank Account</span><span class="sxs-lookup"><span data-stu-id="6657e-2598">Bank Account</span></span> 
- <span data-ttu-id="6657e-2599">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-2599">Bank Account #</span></span> 
- <span data-ttu-id="6657e-2600">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2600">Bank Acct Number</span></span> 
- <span data-ttu-id="6657e-2601">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-2601">Bank Acct #</span></span> 
- <span data-ttu-id="6657e-2602">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2602">Bank Acct No.</span></span> 
- <span data-ttu-id="6657e-2603">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2603">Bank Account No.</span></span> 
- <span data-ttu-id="6657e-2604">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2604">Savings Account Number</span></span> 
- <span data-ttu-id="6657e-2605">Savings Account</span><span class="sxs-lookup"><span data-stu-id="6657e-2605">Savings Account</span></span> 
- <span data-ttu-id="6657e-2606">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-2606">Savings Account #</span></span> 
- <span data-ttu-id="6657e-2607">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2607">Savings Acct Number</span></span> 
- <span data-ttu-id="6657e-2608">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-2608">Savings Acct #</span></span> 
- <span data-ttu-id="6657e-2609">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2609">Savings Acct No.</span></span> 
- <span data-ttu-id="6657e-2610">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2610">Savings Account No.</span></span> 
- <span data-ttu-id="6657e-2611">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2611">Debit Account Number</span></span> 
- <span data-ttu-id="6657e-2612">Debit Account</span><span class="sxs-lookup"><span data-stu-id="6657e-2612">Debit Account</span></span> 
- <span data-ttu-id="6657e-2613">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-2613">Debit Account #</span></span> 
- <span data-ttu-id="6657e-2614">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2614">Debit Acct Number</span></span> 
- <span data-ttu-id="6657e-2615">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-2615">Debit Acct #</span></span> 
- <span data-ttu-id="6657e-2616">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2616">Debit Acct No.</span></span> 
- <span data-ttu-id="6657e-2617">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2617">Debit Account No.</span></span> 
- <span data-ttu-id="6657e-2618">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="6657e-2618">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="6657e-2619">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="6657e-2619">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="6657e-2620">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="6657e-2620">＃勘定の確認</span></span> 
- <span data-ttu-id="6657e-2621">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="6657e-2621">勘定番号の確認</span></span> 
- <span data-ttu-id="6657e-2622">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="6657e-2622">口座番号の確認</span></span> 
- <span data-ttu-id="6657e-2623">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2623">銀行口座番号</span></span> 
- <span data-ttu-id="6657e-2624">銀行口座</span><span class="sxs-lookup"><span data-stu-id="6657e-2624">銀行口座</span></span> 
- <span data-ttu-id="6657e-2625">銀行口座 #</span><span class="sxs-lookup"><span data-stu-id="6657e-2625">銀行口座＃</span></span> 
- <span data-ttu-id="6657e-2626">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2626">銀行の勘定番号</span></span> 
- <span data-ttu-id="6657e-2627">銀行のacct #</span><span class="sxs-lookup"><span data-stu-id="6657e-2627">銀行のacct＃</span></span> 
- <span data-ttu-id="6657e-2628">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="6657e-2628">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="6657e-2629">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2629">銀行口座番号</span></span>
- <span data-ttu-id="6657e-2630">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2630">普通預金口座番号</span></span> 
- <span data-ttu-id="6657e-2631">預金口座</span><span class="sxs-lookup"><span data-stu-id="6657e-2631">預金口座</span></span> 
- <span data-ttu-id="6657e-2632">貯蓄口座 #</span><span class="sxs-lookup"><span data-stu-id="6657e-2632">貯蓄口座＃</span></span> 
- <span data-ttu-id="6657e-2633">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="6657e-2633">貯蓄勘定の数</span></span> 
- <span data-ttu-id="6657e-2634">貯蓄勘定 #</span><span class="sxs-lookup"><span data-stu-id="6657e-2634">貯蓄勘定＃</span></span> 
- <span data-ttu-id="6657e-2635">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2635">貯蓄勘定番号</span></span> 
- <span data-ttu-id="6657e-2636">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2636">普通預金口座番号</span></span> 
- <span data-ttu-id="6657e-2637">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2637">引き落とし口座番号</span></span> 
- <span data-ttu-id="6657e-2638">口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2638">口座番号</span></span> 
- <span data-ttu-id="6657e-2639">口座番号 #</span><span class="sxs-lookup"><span data-stu-id="6657e-2639">口座番号＃</span></span> 
- <span data-ttu-id="6657e-2640">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2640">デビットのacct番号</span></span> 
- <span data-ttu-id="6657e-2641">デビット勘定 #</span><span class="sxs-lookup"><span data-stu-id="6657e-2641">デビット勘定＃</span></span> 
- <span data-ttu-id="6657e-2642">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2642">デビットACCTの番号</span></span> 
- <span data-ttu-id="6657e-2643">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2643">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="6657e-2644">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="6657e-2644">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="6657e-2645">Otemachi</span><span class="sxs-lookup"><span data-stu-id="6657e-2645">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="6657e-2646">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2646">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2647">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2647">Format</span></span>

<span data-ttu-id="6657e-2648">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2648">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2649">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2649">Pattern</span></span>

<span data-ttu-id="6657e-2650">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2650">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2651">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2651">Checksum</span></span>

<span data-ttu-id="6657e-2652">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2652">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2653">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2653">Definition</span></span>

<span data-ttu-id="6657e-2654">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2654">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2655">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2655">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2656">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2656">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2657">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2657">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="6657e-2658">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2658">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="6657e-2659">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-2659">dl#</span></span> 
- <span data-ttu-id="6657e-2660">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-2660">DL＃</span></span> 
- <span data-ttu-id="6657e-2661">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-2661">dls#</span></span> 
- <span data-ttu-id="6657e-2662">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-2662">DLS＃</span></span> 
- <span data-ttu-id="6657e-2663">driver license</span><span class="sxs-lookup"><span data-stu-id="6657e-2663">driver license</span></span> 
- <span data-ttu-id="6657e-2664">driver licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2664">driver licenses</span></span> 
- <span data-ttu-id="6657e-2665">drivers license</span><span class="sxs-lookup"><span data-stu-id="6657e-2665">drivers license</span></span> 
- <span data-ttu-id="6657e-2666">driver's license</span><span class="sxs-lookup"><span data-stu-id="6657e-2666">driver's license</span></span> 
- <span data-ttu-id="6657e-2667">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2667">drivers licenses</span></span> 
- <span data-ttu-id="6657e-2668">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-2668">driver's licenses</span></span> 
- <span data-ttu-id="6657e-2669">driving licence</span><span class="sxs-lookup"><span data-stu-id="6657e-2669">driving licence</span></span> 
- <span data-ttu-id="6657e-2670">そして</span><span class="sxs-lookup"><span data-stu-id="6657e-2670">lic#</span></span> 
- <span data-ttu-id="6657e-2671">そして</span><span class="sxs-lookup"><span data-stu-id="6657e-2671">LIC＃</span></span> 
- <span data-ttu-id="6657e-2672">lics #</span><span class="sxs-lookup"><span data-stu-id="6657e-2672">lics#</span></span> 
- <span data-ttu-id="6657e-2673">state id</span><span class="sxs-lookup"><span data-stu-id="6657e-2673">state id</span></span> 
- <span data-ttu-id="6657e-2674">state identification</span><span class="sxs-lookup"><span data-stu-id="6657e-2674">state identification</span></span> 
- <span data-ttu-id="6657e-2675">state identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-2675">state identification number</span></span> 
- <span data-ttu-id="6657e-2676">低所得国 #</span><span class="sxs-lookup"><span data-stu-id="6657e-2676">低所得国＃</span></span> 
- <span data-ttu-id="6657e-2677">免許証</span><span class="sxs-lookup"><span data-stu-id="6657e-2677">免許証</span></span> 
- <span data-ttu-id="6657e-2678">状態ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2678">状態ID</span></span>
- <span data-ttu-id="6657e-2679">状態の識別</span><span class="sxs-lookup"><span data-stu-id="6657e-2679">状態の識別</span></span> 
- <span data-ttu-id="6657e-2680">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2680">状態の識別番号</span></span> 
- <span data-ttu-id="6657e-2681">運転免許</span><span class="sxs-lookup"><span data-stu-id="6657e-2681">運転免許</span></span> 
- <span data-ttu-id="6657e-2682">運転免許証</span><span class="sxs-lookup"><span data-stu-id="6657e-2682">運転免許証</span></span> 
- <span data-ttu-id="6657e-2683">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2683">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="6657e-2684">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2684">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2685">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2685">Format</span></span>

<span data-ttu-id="6657e-2686">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2686">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2687">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2687">Pattern</span></span>

<span data-ttu-id="6657e-2688">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2688">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2689">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2689">Checksum</span></span>

<span data-ttu-id="6657e-2690">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2690">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2691">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2691">Definition</span></span>

<span data-ttu-id="6657e-2692">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2692">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2693">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2693">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2694">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2694">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2695">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2695">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="6657e-2696">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-2696">Keyword_jp_passport</span></span>

- <span data-ttu-id="6657e-2697">パスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-2697">パスポート</span></span> 
- <span data-ttu-id="6657e-2698">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2698">パスポート番号</span></span> 
- <span data-ttu-id="6657e-2699">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="6657e-2699">パスポートのNum</span></span> 
- <span data-ttu-id="6657e-2700">パスポート #</span><span class="sxs-lookup"><span data-stu-id="6657e-2700">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="6657e-2701">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2701">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2702">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2702">Format</span></span>

<span data-ttu-id="6657e-2703">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2703">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2704">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2704">Pattern</span></span>

<span data-ttu-id="6657e-2705">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2705">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2706">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2706">Checksum</span></span>

<span data-ttu-id="6657e-2707">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2707">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2708">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2708">Definition</span></span>

<span data-ttu-id="6657e-2709">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2709">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2710">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2710">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2711">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2711">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2712">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2712">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="6657e-2713">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2713">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="6657e-2714">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2714">Resident Registration Number</span></span>
- <span data-ttu-id="6657e-2715">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2715">Resident Register Number</span></span> 
- <span data-ttu-id="6657e-2716">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2716">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="6657e-2717">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2717">Resident Registration No.</span></span> 
- <span data-ttu-id="6657e-2718">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2718">Resident Register No.</span></span> 
- <span data-ttu-id="6657e-2719">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2719">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="6657e-2720">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2720">Basic Resident Register No.</span></span> 
- <span data-ttu-id="6657e-2721">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="6657e-2721">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="6657e-2722">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2722">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="6657e-2723">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="6657e-2723">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="6657e-2724">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2724">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="6657e-2725">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="6657e-2725">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2726">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2726">Format</span></span>

<span data-ttu-id="6657e-2727">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2727">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2728">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2728">Pattern</span></span>

<span data-ttu-id="6657e-2729">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2729">7-12 digits:</span></span>
- <span data-ttu-id="6657e-2730">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2730">Four digits</span></span> 
- <span data-ttu-id="6657e-2731">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="6657e-2731">A hyphen (optional)</span></span> 
- <span data-ttu-id="6657e-2732">6桁の数字または</span><span class="sxs-lookup"><span data-stu-id="6657e-2732">Six digits OR</span></span>
- <span data-ttu-id="6657e-2733">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2733">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2734">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2734">Checksum</span></span>

<span data-ttu-id="6657e-2735">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2736">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2736">Definition</span></span>

<span data-ttu-id="6657e-2737">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2737">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2738">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2738">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2739">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2739">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="6657e-2740">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2740">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2741">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2741">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2742">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2742">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2743">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2743">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="6657e-2744">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="6657e-2744">Keyword_jp_sin</span></span>

- <span data-ttu-id="6657e-2745">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="6657e-2745">Social Insurance No.</span></span> 
- <span data-ttu-id="6657e-2746">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="6657e-2746">Social Insurance Num</span></span> 
- <span data-ttu-id="6657e-2747">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2747">Social Insurance Number</span></span> 
- <span data-ttu-id="6657e-2748">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="6657e-2748">社会保険のテンキー</span></span> 
- <span data-ttu-id="6657e-2749">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2749">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="6657e-2750">日本の居住カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2750">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2751">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2751">Format</span></span>

<span data-ttu-id="6657e-2752">12桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2752">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2753">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2753">Pattern</span></span>

<span data-ttu-id="6657e-2754">12桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2754">12 letters and digits:</span></span>
- <span data-ttu-id="6657e-2755">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2755">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="6657e-2756">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2756">Eight digits</span></span> 
- <span data-ttu-id="6657e-2757">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-2757">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2758">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2758">Checksum</span></span>

<span data-ttu-id="6657e-2759">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2759">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2760">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2760">Definition</span></span>

<span data-ttu-id="6657e-2761">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2761">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2762">正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2762">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2763">Keyword_jp_residence_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2763">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2764">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2764">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="6657e-2765">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2765">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="6657e-2766">居住カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2766">Residence card number</span></span>
- <span data-ttu-id="6657e-2767">住居カードなし</span><span class="sxs-lookup"><span data-stu-id="6657e-2767">Residence card no</span></span>
- <span data-ttu-id="6657e-2768">住居カード #</span><span class="sxs-lookup"><span data-stu-id="6657e-2768">Residence card #</span></span>
- <span data-ttu-id="6657e-2769">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2769">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="6657e-2770">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2770">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2771">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2771">Format</span></span>

<span data-ttu-id="6657e-2772">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2772">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2773">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2773">Pattern</span></span>

<span data-ttu-id="6657e-2774">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2774">12 digits:</span></span>
- <span data-ttu-id="6657e-2775">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2775">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6657e-2776">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2776">A dash (optional)</span></span> 
- <span data-ttu-id="6657e-2777">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2777">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="6657e-2778">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2778">A dash (optional)</span></span> 
- <span data-ttu-id="6657e-2779">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2779">Three random digits</span></span> 
- <span data-ttu-id="6657e-2780">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="6657e-2780">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2781">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2781">Checksum</span></span>

<span data-ttu-id="6657e-2782">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2782">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2783">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2783">Definition</span></span>

<span data-ttu-id="6657e-2784">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2785">正規表現 Regex_malaysia_id_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2785">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2786">Keyword_malaysia_id_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2786">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2787">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2787">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="6657e-2788">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2788">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="6657e-2789">デジタルアプリケーションカード</span><span class="sxs-lookup"><span data-stu-id="6657e-2789">digital application card</span></span>
- <span data-ttu-id="6657e-2790">i/c</span><span class="sxs-lookup"><span data-stu-id="6657e-2790">i/c</span></span>
- <span data-ttu-id="6657e-2791">i/c いいえ</span><span class="sxs-lookup"><span data-stu-id="6657e-2791">i/c no</span></span>
- <span data-ttu-id="6657e-2792">ic</span><span class="sxs-lookup"><span data-stu-id="6657e-2792">ic</span></span>
- <span data-ttu-id="6657e-2793">ic no</span><span class="sxs-lookup"><span data-stu-id="6657e-2793">ic no</span></span>
- <span data-ttu-id="6657e-2794">id card</span><span class="sxs-lookup"><span data-stu-id="6657e-2794">id card</span></span>
- <span data-ttu-id="6657e-2795">識別カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2795">identification Card</span></span>
- <span data-ttu-id="6657e-2796">Identity card</span><span class="sxs-lookup"><span data-stu-id="6657e-2796">identity card</span></span>
- <span data-ttu-id="6657e-2797">k/p</span><span class="sxs-lookup"><span data-stu-id="6657e-2797">k/p</span></span>
- <span data-ttu-id="6657e-2798">k/p no</span><span class="sxs-lookup"><span data-stu-id="6657e-2798">k/p no</span></span>
- <span data-ttu-id="6657e-2799">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="6657e-2799">kad akuan diri</span></span>
- <span data-ttu-id="6657e-2800">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="6657e-2800">kad aplikasi digital</span></span>
- <span data-ttu-id="6657e-2801">kad の genalan マレーシア</span><span class="sxs-lookup"><span data-stu-id="6657e-2801">kad pengenalan malaysia</span></span>
- <span data-ttu-id="6657e-2802">kp</span><span class="sxs-lookup"><span data-stu-id="6657e-2802">kp</span></span>
- <span data-ttu-id="6657e-2803">kp no</span><span class="sxs-lookup"><span data-stu-id="6657e-2803">kp no</span></span>
- <span data-ttu-id="6657e-2804">mykad</span><span class="sxs-lookup"><span data-stu-id="6657e-2804">mykad</span></span>
- <span data-ttu-id="6657e-2805">mykas</span><span class="sxs-lookup"><span data-stu-id="6657e-2805">mykas</span></span>
- <span data-ttu-id="6657e-2806">mykid</span><span class="sxs-lookup"><span data-stu-id="6657e-2806">mykid</span></span>
- <span data-ttu-id="6657e-2807">mypr</span><span class="sxs-lookup"><span data-stu-id="6657e-2807">mypr</span></span>
- <span data-ttu-id="6657e-2808">mytentera</span><span class="sxs-lookup"><span data-stu-id="6657e-2808">mytentera</span></span>
- <span data-ttu-id="6657e-2809">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2809">malaysia identity card</span></span>
- <span data-ttu-id="6657e-2810">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2810">malaysian identity card</span></span>
- <span data-ttu-id="6657e-2811">nric</span><span class="sxs-lookup"><span data-stu-id="6657e-2811">nric</span></span>
- <span data-ttu-id="6657e-2812">個人識別カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2812">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="6657e-2813">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2813">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2814">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2814">Format</span></span>

<span data-ttu-id="6657e-2815">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2815">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2816">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2816">Pattern</span></span>

<span data-ttu-id="6657e-2817">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2817">8-9 digits:</span></span>
- <span data-ttu-id="6657e-2818">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2818">Three digits</span></span> 
- <span data-ttu-id="6657e-2819">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2819">A space (optional)</span></span> 
- <span data-ttu-id="6657e-2820">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2820">Three digits</span></span> 
- <span data-ttu-id="6657e-2821">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="6657e-2821">A space (optional)</span></span> 
- <span data-ttu-id="6657e-2822">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2822">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2823">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2823">Checksum</span></span>

<span data-ttu-id="6657e-2824">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2825">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2825">Definition</span></span>

<span data-ttu-id="6657e-2826">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2826">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2827">関数 Func_netherlands_bsn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2827">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2828">Keyword_netherlands_bsn からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2828">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="6657e-2829">関数 Func_eu_date2 は、日付を正しい日付形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2829">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="6657e-2830">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2830">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2831">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2831">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="6657e-2832">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="6657e-2832">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="6657e-2833">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="6657e-2833">Citizen service number</span></span> 
- <span data-ttu-id="6657e-2834">BSN</span><span class="sxs-lookup"><span data-stu-id="6657e-2834">BSN</span></span> 
- <span data-ttu-id="6657e-2835">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2835">Burgerservicenummer</span></span> 
- <span data-ttu-id="6657e-2836">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2836">Sofinummer</span></span> 
- <span data-ttu-id="6657e-2837">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2837">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="6657e-2838">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2838">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="6657e-2839">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2839">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2840">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2840">Format</span></span>

<span data-ttu-id="6657e-2841">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2841">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2842">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2842">Pattern</span></span>

<span data-ttu-id="6657e-2843">3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2843">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2844">Checksum</span></span>

<span data-ttu-id="6657e-2845">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2845">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2846">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2846">Definition</span></span>

<span data-ttu-id="6657e-2847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2848">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2848">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2849">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2849">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="6657e-2850">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2850">The checksum passes.</span></span>

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

<span data-ttu-id="6657e-2851">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2851">Keywords</span></span>

<span data-ttu-id="6657e-2852">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="6657e-2852">Keyword_nz_terms</span></span>

- <span data-ttu-id="6657e-2853">nhi</span><span class="sxs-lookup"><span data-stu-id="6657e-2853">NHI</span></span> 
- <span data-ttu-id="6657e-2854">New Zealand</span><span class="sxs-lookup"><span data-stu-id="6657e-2854">New Zealand</span></span> 
- <span data-ttu-id="6657e-2855">タスクの状況</span><span class="sxs-lookup"><span data-stu-id="6657e-2855">Health</span></span> 
- <span data-ttu-id="6657e-2856">処理</span><span class="sxs-lookup"><span data-stu-id="6657e-2856">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="6657e-2857">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2857">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2858">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2858">Format</span></span>

<span data-ttu-id="6657e-2859">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2859">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2860">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2860">Pattern</span></span>

<span data-ttu-id="6657e-2861">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2861">11 digits:</span></span>
- <span data-ttu-id="6657e-2862">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2862">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="6657e-2863">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="6657e-2863">Three-digit individual number</span></span> 
- <span data-ttu-id="6657e-2864">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="6657e-2864">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2865">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2865">Checksum</span></span>

<span data-ttu-id="6657e-2866">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2866">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2867">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2867">Definition</span></span>

<span data-ttu-id="6657e-2868">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2868">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2869">関数 Func_norway_id_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2869">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2870">Keyword_norway_id_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2870">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="6657e-2871">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2871">The checksum passes.</span></span>
- <span data-ttu-id="6657e-2872">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2873">関数 Func_norway_id_numbe は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2873">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2874">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2874">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2875">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2875">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="6657e-2876">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2876">Keyword_norway_id_number</span></span>

- <span data-ttu-id="6657e-2877">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-2877">Personal identification number</span></span>
- <span data-ttu-id="6657e-2878">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2878">Norwegian ID Number</span></span>
- <span data-ttu-id="6657e-2879">ID Number</span><span class="sxs-lookup"><span data-stu-id="6657e-2879">ID Number</span></span>
- <span data-ttu-id="6657e-2880">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-2880">Identification</span></span>
- <span data-ttu-id="6657e-2881">Personnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2881">Personnummer</span></span>
- <span data-ttu-id="6657e-2882">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="6657e-2882">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="6657e-2883">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2883">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2884">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2884">Format</span></span>

<span data-ttu-id="6657e-2885">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2885">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2886">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2886">Pattern</span></span>

<span data-ttu-id="6657e-2887">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2887">12 digits:</span></span>
- <span data-ttu-id="6657e-2888">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2888">Four digits</span></span> 
- <span data-ttu-id="6657e-2889">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-2889">A hyphen</span></span> 
- <span data-ttu-id="6657e-2890">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-2890">Seven digits</span></span> 
- <span data-ttu-id="6657e-2891">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-2891">A hyphen</span></span> 
- <span data-ttu-id="6657e-2892">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2892">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2893">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2893">Checksum</span></span>

<span data-ttu-id="6657e-2894">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2894">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2895">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2895">Definition</span></span>

<span data-ttu-id="6657e-2896">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2896">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2897">正規表現 Regex_philippines_unified_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2897">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2898">Keyword_philippines_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2898">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2899">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2899">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="6657e-2900">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="6657e-2900">Keyword_philippines_id</span></span>

- <span data-ttu-id="6657e-2901">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2901">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="6657e-2902">umid</span><span class="sxs-lookup"><span data-stu-id="6657e-2902">UMID</span></span> 
- <span data-ttu-id="6657e-2903">Identity Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2903">Identity Card</span></span> 
- <span data-ttu-id="6657e-2904">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2904">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="6657e-2905">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="6657e-2905">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2906">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2906">Format</span></span>

<span data-ttu-id="6657e-2907">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2907">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2908">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2908">Pattern</span></span>

<span data-ttu-id="6657e-2909">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2909">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2910">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2910">Checksum</span></span>

<span data-ttu-id="6657e-2911">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2911">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2912">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2912">Definition</span></span>

<span data-ttu-id="6657e-2913">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2913">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="6657e-2914">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2914">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="6657e-2915">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2915">The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2916">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2916">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="6657e-2917">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2917">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="6657e-2918">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="6657e-2918">Dowód osobisty</span></span>
- <span data-ttu-id="6657e-2919">特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="6657e-2919">Numer dowodu osobistego</span></span>
- <span data-ttu-id="6657e-2920">nazwa i 特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="6657e-2920">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="6657e-2921">nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="6657e-2921">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="6657e-2922">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="6657e-2922">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="6657e-2923">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="6657e-2923">Dowód Tożsamości</span></span>
- <span data-ttu-id="6657e-2924">dow.</span><span class="sxs-lookup"><span data-stu-id="6657e-2924">dow.</span></span> <span data-ttu-id="6657e-2925">hp-ux.</span><span class="sxs-lookup"><span data-stu-id="6657e-2925">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="6657e-2926">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="6657e-2926">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2927">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2927">Format</span></span>

<span data-ttu-id="6657e-2928">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2928">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2929">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2929">Pattern</span></span>

<span data-ttu-id="6657e-2930">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2930">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2931">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2931">Checksum</span></span>

<span data-ttu-id="6657e-2932">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2932">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2933">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2933">Definition</span></span>

<span data-ttu-id="6657e-2934">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2934">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2935">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2935">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2936">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2936">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="6657e-2937">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2937">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2938">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2938">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="6657e-2939">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2939">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="6657e-2940">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="6657e-2940">Nr PESEL</span></span>
- <span data-ttu-id="6657e-2941">PESEL</span><span class="sxs-lookup"><span data-stu-id="6657e-2941">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="6657e-2942">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-2942">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2943">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2943">Format</span></span>

<span data-ttu-id="6657e-2944">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2944">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2945">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2945">Pattern</span></span>

<span data-ttu-id="6657e-2946">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2946">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2947">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2947">Checksum</span></span>

<span data-ttu-id="6657e-2948">有</span><span class="sxs-lookup"><span data-stu-id="6657e-2948">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2949">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2949">Definition</span></span>

<span data-ttu-id="6657e-2950">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2950">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2951">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2951">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2952">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2952">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="6657e-2953">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-2953">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2954">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2954">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="6657e-2955">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="6657e-2955">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="6657e-2956">特定の引数</span><span class="sxs-lookup"><span data-stu-id="6657e-2956">Numer paszportu</span></span>
- <span data-ttu-id="6657e-2957">Nr.</span><span class="sxs-lookup"><span data-stu-id="6657e-2957">Nr.</span></span> <span data-ttu-id="6657e-2958">大き zportu</span><span class="sxs-lookup"><span data-stu-id="6657e-2958">Paszportu</span></span>
- <span data-ttu-id="6657e-2959">があります</span><span class="sxs-lookup"><span data-stu-id="6657e-2959">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="6657e-2960">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2960">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2961">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2961">Format</span></span>

<span data-ttu-id="6657e-2962">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2962">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2963">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2963">Pattern</span></span>

<span data-ttu-id="6657e-2964">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2964">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2965">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2965">Checksum</span></span>

<span data-ttu-id="6657e-2966">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2966">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2967">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2967">Definition</span></span>

<span data-ttu-id="6657e-2968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2969">正規表現 Regex_portugal_citizen_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2969">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2970">Keyword_portugal_citizen_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-2970">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-2971">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2971">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="6657e-2972">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="6657e-2972">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="6657e-2973">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2973">Citizen Card</span></span>
- <span data-ttu-id="6657e-2974">National ID Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2974">National ID Card</span></span>
- <span data-ttu-id="6657e-2975">CC</span><span class="sxs-lookup"><span data-stu-id="6657e-2975">CC</span></span>
- <span data-ttu-id="6657e-2976">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="6657e-2976">Cartão de Cidadão</span></span>
- <span data-ttu-id="6657e-2977">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="6657e-2977">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="6657e-2978">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="6657e-2978">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2979">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2979">Format</span></span>

<span data-ttu-id="6657e-2980">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2980">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2981">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2981">Pattern</span></span>

<span data-ttu-id="6657e-2982">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2982">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-2983">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-2983">Checksum</span></span>

<span data-ttu-id="6657e-2984">無</span><span class="sxs-lookup"><span data-stu-id="6657e-2984">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-2985">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-2985">Definition</span></span>

<span data-ttu-id="6657e-2986">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-2987">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2987">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-2988">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-2988">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-2989">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-2989">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="6657e-2990">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="6657e-2990">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="6657e-2991">Identification Card</span><span class="sxs-lookup"><span data-stu-id="6657e-2991">Identification Card</span></span> 
- <span data-ttu-id="6657e-2992">I card number</span><span class="sxs-lookup"><span data-stu-id="6657e-2992">I card number</span></span> 
- <span data-ttu-id="6657e-2993">ID number</span><span class="sxs-lookup"><span data-stu-id="6657e-2993">ID number</span></span> 
- <span data-ttu-id="6657e-2994">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="6657e-2994">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="6657e-2995">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-2995">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-2996">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-2996">Format</span></span>

<span data-ttu-id="6657e-2997">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="6657e-2997">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-2998">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-2998">Pattern</span></span>

- <span data-ttu-id="6657e-2999">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-2999">Nine letters and digits:</span></span>
- <span data-ttu-id="6657e-3000">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-3000">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-3001">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-3001">Seven digits</span></span> 
- <span data-ttu-id="6657e-3002">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="6657e-3002">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3003">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3003">Checksum</span></span>

<span data-ttu-id="6657e-3004">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3004">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3005">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3005">Definition</span></span>

<span data-ttu-id="6657e-3006">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3006">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3007">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3007">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3008">Keyword_singapore_nric からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3008">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="6657e-3009">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3009">The checksum passes.</span></span>

<span data-ttu-id="6657e-3010">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3010">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3011">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3011">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3012">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3012">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3013">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3013">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="6657e-3014">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="6657e-3014">Keyword_singapore_nric</span></span>

- <span data-ttu-id="6657e-3015">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="6657e-3015">National Registration Identity Card</span></span> 
- <span data-ttu-id="6657e-3016">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3016">Identity Card Number</span></span> 
- <span data-ttu-id="6657e-3017">NRIC</span><span class="sxs-lookup"><span data-stu-id="6657e-3017">NRIC</span></span> 
- <span data-ttu-id="6657e-3018">IC</span><span class="sxs-lookup"><span data-stu-id="6657e-3018">IC</span></span> 
- <span data-ttu-id="6657e-3019">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3019">Foreign Identification Number</span></span> 
- <span data-ttu-id="6657e-3020">FIN</span><span class="sxs-lookup"><span data-stu-id="6657e-3020">FIN</span></span> 
- <span data-ttu-id="6657e-3021">身份证</span><span class="sxs-lookup"><span data-stu-id="6657e-3021">身份证</span></span> 
- <span data-ttu-id="6657e-3022">身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-3022">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="6657e-3023">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3023">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3024">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3024">Format</span></span>

<span data-ttu-id="6657e-3025">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3025">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3026">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3026">Pattern</span></span>

<span data-ttu-id="6657e-3027">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3027">13 digits:</span></span>
- <span data-ttu-id="6657e-3028">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-3028">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6657e-3029">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3029">Four digits</span></span> 
- <span data-ttu-id="6657e-3030">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="6657e-3030">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="6657e-3031">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="6657e-3031">The digit "8" or "9"</span></span> 
- <span data-ttu-id="6657e-3032">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3032">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3033">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3033">Checksum</span></span>

<span data-ttu-id="6657e-3034">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3034">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3035">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3035">Definition</span></span>

<span data-ttu-id="6657e-3036">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3036">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3037">関数 Func_south_africa_identification_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3037">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3038">Keyword_south_africa_identification_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3038">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="6657e-3039">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3039">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3040">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3040">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="6657e-3041">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="6657e-3041">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="6657e-3042">Identity card</span><span class="sxs-lookup"><span data-stu-id="6657e-3042">Identity card</span></span>
- <span data-ttu-id="6657e-3043">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-3043">ID</span></span>
- <span data-ttu-id="6657e-3044">fim</span><span class="sxs-lookup"><span data-stu-id="6657e-3044">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="6657e-3045">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3045">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3046">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3046">Format</span></span>

<span data-ttu-id="6657e-3047">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3047">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3048">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3048">Pattern</span></span>

<span data-ttu-id="6657e-3049">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3049">13 digits:</span></span>
- <span data-ttu-id="6657e-3050">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-3050">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="6657e-3051">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="6657e-3051">A hyphen</span></span> 
- <span data-ttu-id="6657e-3052">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-3052">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="6657e-3053">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="6657e-3053">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="6657e-3054">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="6657e-3054">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="6657e-3055">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="6657e-3055">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3056">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3056">Checksum</span></span>

<span data-ttu-id="6657e-3057">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3057">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3058">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3058">Definition</span></span>

<span data-ttu-id="6657e-3059">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3059">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3060">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3060">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3061">Keyword_south_korea_resident_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3061">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="6657e-3062">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3062">The checksum passes.</span></span>

<span data-ttu-id="6657e-3063">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3063">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3064">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3064">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3065">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3065">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3066">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3066">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="6657e-3067">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="6657e-3067">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="6657e-3068">National ID card</span><span class="sxs-lookup"><span data-stu-id="6657e-3068">National ID card</span></span> 
- <span data-ttu-id="6657e-3069">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3069">Citizen's Registration Number</span></span> 
- <span data-ttu-id="6657e-3070">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="6657e-3070">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="6657e-3071">rrn</span><span class="sxs-lookup"><span data-stu-id="6657e-3071">RRN</span></span> 
- <span data-ttu-id="6657e-3072">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="6657e-3072">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="6657e-3073">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="6657e-3073">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3074">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3074">Format</span></span>

<span data-ttu-id="6657e-3075">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3075">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3076">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3076">Pattern</span></span>

<span data-ttu-id="6657e-3077">11-12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3077">11-12 digits:</span></span>
- <span data-ttu-id="6657e-3078">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3078">Two digits</span></span> 
- <span data-ttu-id="6657e-3079">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="6657e-3079">A forward slash (optional)</span></span> 
- <span data-ttu-id="6657e-3080">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3080">7-8 digits</span></span> 
- <span data-ttu-id="6657e-3081">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="6657e-3081">A forward slash (optional)</span></span> 
- <span data-ttu-id="6657e-3082">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3082">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3083">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3083">Checksum</span></span>

<span data-ttu-id="6657e-3084">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3084">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3085">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3085">Definition</span></span>

<span data-ttu-id="6657e-3086">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3086">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3087">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3087">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3088">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3088">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3089">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3089">Keywords</span></span>

<span data-ttu-id="6657e-3090">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-3090">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="6657e-3091">SQL Server の接続文字列</span><span class="sxs-lookup"><span data-stu-id="6657e-3091">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3092">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3092">Format</span></span>

<span data-ttu-id="6657e-3093">文字列 "user id"、"user id"、"uid"、または "UserId" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="6657e-3093">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3094">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3094">Pattern</span></span>

- <span data-ttu-id="6657e-3095">文字列 "user id"、"user id"、"uid"、または "UserId"</span><span class="sxs-lookup"><span data-stu-id="6657e-3095">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="6657e-3096">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="6657e-3096">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="6657e-3097">文字列 "Password" または "pwd" ("pwd" の前に小文字が含まれていません)</span><span class="sxs-lookup"><span data-stu-id="6657e-3097">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="6657e-3098">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-3098">An equal sign (=)</span></span>
- <span data-ttu-id="6657e-3099">ドル記号 ($)、パーセント記号 (%)、不等号 (>)、記号 (@)、二重引用符 (")、セミコロン (;)、左中かっこ ([)、左大かっこ ({) のいずれでもない文字</span><span class="sxs-lookup"><span data-stu-id="6657e-3099">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="6657e-3100">セミコロンではない7-128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")</span><span class="sxs-lookup"><span data-stu-id="6657e-3100">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="6657e-3101">セミコロン (;)または二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="6657e-3101">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3102">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3102">Checksum</span></span>

<span data-ttu-id="6657e-3103">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3103">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3104">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3104">Definition</span></span>

<span data-ttu-id="6657e-3105">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3105">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3106">正規表現 CEP_Regex_SQLServerConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3106">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3107">CEP_GlobalFilter からのキーワードが見つかり**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-3107">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="6657e-3108">正規表現 CEP_PasswordPlaceHolder は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-3108">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3109">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="6657e-3109">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3110">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3110">Keywords</span></span>

#### <a name="cepglobalfilter"></a><span data-ttu-id="6657e-3111">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="6657e-3111">CEP_GlobalFilter</span></span>

- <span data-ttu-id="6657e-3112">パスワードの一部</span><span class="sxs-lookup"><span data-stu-id="6657e-3112">some-password</span></span>
- <span data-ttu-id="6657e-3113">パスワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3113">somepassword</span></span>
- <span data-ttu-id="6657e-3114">secretPassword</span><span class="sxs-lookup"><span data-stu-id="6657e-3114">secretPassword</span></span>
- <span data-ttu-id="6657e-3115">示す</span><span class="sxs-lookup"><span data-stu-id="6657e-3115">sample</span></span>

#### <a name="ceppasswordplaceholder"></a><span data-ttu-id="6657e-3116">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="6657e-3116">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="6657e-3117">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-3117">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-3118">Password または pwd の後に、0-2 スペース、等号 (=)、0-2 スペース、アスタリスク (\*)、または--</span><span class="sxs-lookup"><span data-stu-id="6657e-3118">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="6657e-3119">Password または pwd の後に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3119">Password or pwd followed by:</span></span>
    - <span data-ttu-id="6657e-3120">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="6657e-3120">Equal sign (=)</span></span>
    - <span data-ttu-id="6657e-3121">小なり記号 (<)</span><span class="sxs-lookup"><span data-stu-id="6657e-3121">Less than symbol (<)</span></span>
    - <span data-ttu-id="6657e-3122">1-200 文字の大文字と小文字、数字、アスタリスク (\*)、ハイフン (-)、下線 (_)、または空白文字の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="6657e-3122">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="6657e-3123">より大きい記号 (>)</span><span class="sxs-lookup"><span data-stu-id="6657e-3123">Greater than symbol (>)</span></span>

#### <a name="cepcommonexamplekeywords"></a><span data-ttu-id="6657e-3124">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="6657e-3124">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="6657e-3125">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="6657e-3125">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="6657e-3126">拠点</span><span class="sxs-lookup"><span data-stu-id="6657e-3126">contoso</span></span>
- <span data-ttu-id="6657e-3127">fabrikam</span><span class="sxs-lookup"><span data-stu-id="6657e-3127">fabrikam</span></span>
- <span data-ttu-id="6657e-3128">ノース</span><span class="sxs-lookup"><span data-stu-id="6657e-3128">northwind</span></span>
- <span data-ttu-id="6657e-3129">サンド</span><span class="sxs-lookup"><span data-stu-id="6657e-3129">sandbox</span></span>
- <span data-ttu-id="6657e-3130">onebox</span><span class="sxs-lookup"><span data-stu-id="6657e-3130">onebox</span></span>
- <span data-ttu-id="6657e-3131">localhost</span><span class="sxs-lookup"><span data-stu-id="6657e-3131">localhost</span></span>
- <span data-ttu-id="6657e-3132">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="6657e-3132">127.0.0.1</span></span>
- <span data-ttu-id="6657e-3133">testacs。<!--no-hyperlink-->com</span><span class="sxs-lookup"><span data-stu-id="6657e-3133">testacs.<!--no-hyperlink-->com</span></span>
- <span data-ttu-id="6657e-3134">s-int<!--no-hyperlink--></span><span class="sxs-lookup"><span data-stu-id="6657e-3134">s-int.<!--no-hyperlink-->net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="6657e-3135">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="6657e-3135">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3136">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3136">Format</span></span>

<span data-ttu-id="6657e-3137">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="6657e-3137">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3138">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3138">Pattern</span></span>

<span data-ttu-id="6657e-3139">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="6657e-3139">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="6657e-3140">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="6657e-3140">2-4 digits (optional)</span></span> 
- <span data-ttu-id="6657e-3141">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3141">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="6657e-3142">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="6657e-3142">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="6657e-3143">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3143">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3144">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3144">Checksum</span></span>

<span data-ttu-id="6657e-3145">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3145">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3146">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3146">Definition</span></span>

<span data-ttu-id="6657e-3147">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3147">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3148">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3148">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3149">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3149">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3150">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3150">Keywords</span></span>

<span data-ttu-id="6657e-3151">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3151">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="6657e-3152">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3152">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3153">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3153">Format</span></span>

<span data-ttu-id="6657e-3154">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3154">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3155">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3155">Pattern</span></span>

<span data-ttu-id="6657e-3156">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3156">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3157">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3157">Checksum</span></span>

<span data-ttu-id="6657e-3158">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3158">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3159">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3159">Definition</span></span>

<span data-ttu-id="6657e-3160">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3160">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3161">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3161">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3162">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-3162">One of the following is true:</span></span>
    - <span data-ttu-id="6657e-3163">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3163">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="6657e-3164">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3164">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3165">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3165">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="6657e-3166">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-3166">Keyword_sweden_passport</span></span>

- <span data-ttu-id="6657e-3167">visa requirements</span><span class="sxs-lookup"><span data-stu-id="6657e-3167">visa requirements</span></span> 
- <span data-ttu-id="6657e-3168">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="6657e-3168">Alien Registration Card</span></span> 
- <span data-ttu-id="6657e-3169">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="6657e-3169">Schengen visas</span></span> 
- <span data-ttu-id="6657e-3170">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="6657e-3170">Schengen visa</span></span> 
- <span data-ttu-id="6657e-3171">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="6657e-3171">Visa Processing</span></span> 
- <span data-ttu-id="6657e-3172">Visa Type</span><span class="sxs-lookup"><span data-stu-id="6657e-3172">Visa Type</span></span> 
- <span data-ttu-id="6657e-3173">Single Entry</span><span class="sxs-lookup"><span data-stu-id="6657e-3173">Single Entry</span></span> 
- <span data-ttu-id="6657e-3174">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="6657e-3174">Multiple Entry</span></span> 
- <span data-ttu-id="6657e-3175">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="6657e-3175">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="6657e-3176">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-3176">Keyword_passport</span></span>

- <span data-ttu-id="6657e-3177">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3177">Passport Number</span></span> 
- <span data-ttu-id="6657e-3178">Passport No</span><span class="sxs-lookup"><span data-stu-id="6657e-3178">Passport No</span></span> 
- <span data-ttu-id="6657e-3179">Passport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3179">Passport #</span></span> 
- <span data-ttu-id="6657e-3180">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-3180">Passport#</span></span> 
- <span data-ttu-id="6657e-3181">PassportID</span><span class="sxs-lookup"><span data-stu-id="6657e-3181">PassportID</span></span> 
- <span data-ttu-id="6657e-3182">Passportno</span><span class="sxs-lookup"><span data-stu-id="6657e-3182">Passportno</span></span> 
- <span data-ttu-id="6657e-3183">passportnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-3183">passportnumber</span></span> 
- <span data-ttu-id="6657e-3184">パスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-3184">パスポート</span></span> 
- <span data-ttu-id="6657e-3185">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3185">パスポート番号</span></span> 
- <span data-ttu-id="6657e-3186">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="6657e-3186">パスポートのNum</span></span> 
- <span data-ttu-id="6657e-3187">パスポート #</span><span class="sxs-lookup"><span data-stu-id="6657e-3187">パスポート＃</span></span> 
- <span data-ttu-id="6657e-3188">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6657e-3188">Numéro de passeport</span></span> 
- <span data-ttu-id="6657e-3189">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6657e-3189">Passeport n °</span></span> 
- <span data-ttu-id="6657e-3190">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="6657e-3190">Passeport Non</span></span> 
- <span data-ttu-id="6657e-3191">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3191">Passeport #</span></span> 
- <span data-ttu-id="6657e-3192">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3192">Passeport#</span></span> 
- <span data-ttu-id="6657e-3193">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6657e-3193">PasseportNon</span></span> 
- <span data-ttu-id="6657e-3194">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6657e-3194">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="6657e-3195">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="6657e-3195">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3196">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3196">Format</span></span>

<span data-ttu-id="6657e-3197">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3197">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3198">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3198">Pattern</span></span>

<span data-ttu-id="6657e-3199">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3199">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="6657e-3200">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="6657e-3200">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-3201">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-3201">An optional space</span></span> 
- <span data-ttu-id="6657e-3202">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="6657e-3202">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="6657e-3203">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="6657e-3203">An optional space</span></span> 
- <span data-ttu-id="6657e-3204">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="6657e-3204">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3205">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3205">Checksum</span></span>

<span data-ttu-id="6657e-3206">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3206">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3207">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3207">Definition</span></span>

<span data-ttu-id="6657e-3208">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3208">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3209">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3209">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3210">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3210">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3211">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3211">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="6657e-3212">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="6657e-3212">Keyword_swift</span></span>

- <span data-ttu-id="6657e-3213">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="6657e-3213">international organization for standardization 9362</span></span> 
- <span data-ttu-id="6657e-3214">iso 9362</span><span class="sxs-lookup"><span data-stu-id="6657e-3214">iso 9362</span></span> 
- <span data-ttu-id="6657e-3215">iso9362</span><span class="sxs-lookup"><span data-stu-id="6657e-3215">iso9362</span></span> 
- <span data-ttu-id="6657e-3216">実現\#</span><span class="sxs-lookup"><span data-stu-id="6657e-3216">swift\#</span></span> 
- <span data-ttu-id="6657e-3217">swiftcode</span><span class="sxs-lookup"><span data-stu-id="6657e-3217">swiftcode</span></span> 
- <span data-ttu-id="6657e-3218">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-3218">swiftnumber</span></span> 
- <span data-ttu-id="6657e-3219">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-3219">swiftroutingnumber</span></span> 
- <span data-ttu-id="6657e-3220">swift code</span><span class="sxs-lookup"><span data-stu-id="6657e-3220">swift code</span></span> 
- <span data-ttu-id="6657e-3221">swift number #</span><span class="sxs-lookup"><span data-stu-id="6657e-3221">swift number #</span></span> 
- <span data-ttu-id="6657e-3222">swift routing number</span><span class="sxs-lookup"><span data-stu-id="6657e-3222">swift routing number</span></span> 
- <span data-ttu-id="6657e-3223">bic number</span><span class="sxs-lookup"><span data-stu-id="6657e-3223">bic number</span></span> 
- <span data-ttu-id="6657e-3224">bic code</span><span class="sxs-lookup"><span data-stu-id="6657e-3224">bic code</span></span> 
- <span data-ttu-id="6657e-3225">bic\#</span><span class="sxs-lookup"><span data-stu-id="6657e-3225">bic \#</span></span> 
- <span data-ttu-id="6657e-3226">bic\#</span><span class="sxs-lookup"><span data-stu-id="6657e-3226">bic\#</span></span> 
- <span data-ttu-id="6657e-3227">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="6657e-3227">bank identifier code</span></span> 
- <span data-ttu-id="6657e-3228">標準化9362</span><span class="sxs-lookup"><span data-stu-id="6657e-3228">標準化9362</span></span> 
- <span data-ttu-id="6657e-3229">迅速 #</span><span class="sxs-lookup"><span data-stu-id="6657e-3229">迅速＃</span></span> 
- <span data-ttu-id="6657e-3230">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="6657e-3230">SWIFTコード</span></span> 
- <span data-ttu-id="6657e-3231">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3231">SWIFT番号</span></span> 
- <span data-ttu-id="6657e-3232">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3232">迅速なルーティング番号</span></span> 
- <span data-ttu-id="6657e-3233">BIC番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3233">BIC番号</span></span> 
- <span data-ttu-id="6657e-3234">BICコード</span><span class="sxs-lookup"><span data-stu-id="6657e-3234">BICコード</span></span> 
- <span data-ttu-id="6657e-3235">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="6657e-3235">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="6657e-3236">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="6657e-3236">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="6657e-3237">rapide\#</span><span class="sxs-lookup"><span data-stu-id="6657e-3237">rapide \#</span></span> 
- <span data-ttu-id="6657e-3238">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="6657e-3238">code SWIFT</span></span> 
- <span data-ttu-id="6657e-3239">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="6657e-3239">le numéro de swift</span></span> 
- <span data-ttu-id="6657e-3240">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="6657e-3240">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="6657e-3241">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="6657e-3241">le numéro BIC</span></span> 
- <span data-ttu-id="6657e-3242">\#bic</span><span class="sxs-lookup"><span data-stu-id="6657e-3242">\# BIC</span></span> 
- <span data-ttu-id="6657e-3243">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="6657e-3243">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="6657e-3244">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="6657e-3244">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3245">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3245">Format</span></span>

<span data-ttu-id="6657e-3246">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3246">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3247">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3247">Pattern</span></span>

<span data-ttu-id="6657e-3248">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3248">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="6657e-3249">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="6657e-3249">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="6657e-3250">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="6657e-3250">The digit "1" or "2"</span></span> 
- <span data-ttu-id="6657e-3251">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3251">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3252">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3252">Checksum</span></span>

<span data-ttu-id="6657e-3253">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3253">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3254">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3254">Definition</span></span>

<span data-ttu-id="6657e-3255">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3255">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3256">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3256">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3257">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3257">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="6657e-3258">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3258">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3259">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3259">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="6657e-3260">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="6657e-3260">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="6657e-3261">身份證字號</span><span class="sxs-lookup"><span data-stu-id="6657e-3261">身份證字號</span></span> 
- <span data-ttu-id="6657e-3262">身份證</span><span class="sxs-lookup"><span data-stu-id="6657e-3262">身份證</span></span> 
- <span data-ttu-id="6657e-3263">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="6657e-3263">身份證號碼</span></span> 
- <span data-ttu-id="6657e-3264">身份證號</span><span class="sxs-lookup"><span data-stu-id="6657e-3264">身份證號</span></span> 
- <span data-ttu-id="6657e-3265">身分證字號</span><span class="sxs-lookup"><span data-stu-id="6657e-3265">身分證字號</span></span> 
- <span data-ttu-id="6657e-3266">身分證</span><span class="sxs-lookup"><span data-stu-id="6657e-3266">身分證</span></span> 
- <span data-ttu-id="6657e-3267">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="6657e-3267">身分證號碼</span></span> 
- <span data-ttu-id="6657e-3268">身份證號</span><span class="sxs-lookup"><span data-stu-id="6657e-3268">身份證號</span></span> 
- <span data-ttu-id="6657e-3269">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="6657e-3269">身分證統一編號</span></span> 
- <span data-ttu-id="6657e-3270">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="6657e-3270">國民身分證統一編號</span></span> 
- <span data-ttu-id="6657e-3271">簽名</span><span class="sxs-lookup"><span data-stu-id="6657e-3271">簽名</span></span> 
- <span data-ttu-id="6657e-3272">蓋章</span><span class="sxs-lookup"><span data-stu-id="6657e-3272">蓋章</span></span> 
- <span data-ttu-id="6657e-3273">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="6657e-3273">簽名或蓋章</span></span> 
- <span data-ttu-id="6657e-3274">簽章</span><span class="sxs-lookup"><span data-stu-id="6657e-3274">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="6657e-3275">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3275">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3276">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3276">Format</span></span>

- <span data-ttu-id="6657e-3277">バイオメトリックパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3277">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="6657e-3278">バイオメトリクスでないパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3278">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3279">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3279">Pattern</span></span>
<span data-ttu-id="6657e-3280">バイオメトリックパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="6657e-3280">Biometric passport number:</span></span>
- <span data-ttu-id="6657e-3281">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="6657e-3281">The digit "3"</span></span> 
- <span data-ttu-id="6657e-3282">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3282">Eight digits</span></span>

<span data-ttu-id="6657e-3283">バイオメトリクスではないパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="6657e-3283">Non-biometric passport number:</span></span>
- <span data-ttu-id="6657e-3284">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3284">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3285">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3285">Checksum</span></span>

<span data-ttu-id="6657e-3286">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3287">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3287">Definition</span></span>

<span data-ttu-id="6657e-3288">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3289">正規表現 Regex_taiwan_passport は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3289">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3290">Keyword_taiwan_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3290">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3291">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3291">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="6657e-3292">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-3292">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="6657e-3293">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="6657e-3293">ROC passport number</span></span> 
- <span data-ttu-id="6657e-3294">Passport number</span><span class="sxs-lookup"><span data-stu-id="6657e-3294">Passport number</span></span> 
- <span data-ttu-id="6657e-3295">Passport no</span><span class="sxs-lookup"><span data-stu-id="6657e-3295">Passport no</span></span> 
- <span data-ttu-id="6657e-3296">Passport Num</span><span class="sxs-lookup"><span data-stu-id="6657e-3296">Passport Num</span></span> 
- <span data-ttu-id="6657e-3297">Passport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3297">Passport #</span></span> 
- <span data-ttu-id="6657e-3298">护照</span><span class="sxs-lookup"><span data-stu-id="6657e-3298">护照</span></span> 
- <span data-ttu-id="6657e-3299">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="6657e-3299">中華民國護照</span></span> 
- <span data-ttu-id="6657e-3300">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="6657e-3300">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="6657e-3301">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3301">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3302">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3302">Format</span></span>

<span data-ttu-id="6657e-3303">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3303">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3304">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3304">Pattern</span></span>

<span data-ttu-id="6657e-3305">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3305">10 letters and digits:</span></span>
- <span data-ttu-id="6657e-3306">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="6657e-3306">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="6657e-3307">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3307">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3308">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3308">Checksum</span></span>

<span data-ttu-id="6657e-3309">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3309">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3310">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3310">Definition</span></span>

<span data-ttu-id="6657e-3311">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3311">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3312">正規表現 Regex_taiwan_resident_certificate は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3312">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3313">Keyword_taiwan_resident_certificate からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3313">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3314">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3314">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="6657e-3315">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="6657e-3315">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="6657e-3316">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="6657e-3316">Resident Certificate</span></span> 
- <span data-ttu-id="6657e-3317">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="6657e-3317">Resident Cert</span></span> 
- <span data-ttu-id="6657e-3318">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="6657e-3318">Resident Cert.</span></span> 
- <span data-ttu-id="6657e-3319">Identification card</span><span class="sxs-lookup"><span data-stu-id="6657e-3319">Identification card</span></span> 
- <span data-ttu-id="6657e-3320">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="6657e-3320">Alien Resident Certificate</span></span> 
- <span data-ttu-id="6657e-3321">円弧</span><span class="sxs-lookup"><span data-stu-id="6657e-3321">ARC</span></span> 
- <span data-ttu-id="6657e-3322">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="6657e-3322">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="6657e-3323">tarc</span><span class="sxs-lookup"><span data-stu-id="6657e-3323">TARC</span></span> 
- <span data-ttu-id="6657e-3324">居留證</span><span class="sxs-lookup"><span data-stu-id="6657e-3324">居留證</span></span> 
- <span data-ttu-id="6657e-3325">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="6657e-3325">外僑居留證</span></span> 
- <span data-ttu-id="6657e-3326">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="6657e-3326">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="6657e-3327">タイ語の母集団識別コード</span><span class="sxs-lookup"><span data-stu-id="6657e-3327">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3328">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3328">Format</span></span>

<span data-ttu-id="6657e-3329">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3329">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3330">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3330">Pattern</span></span>

<span data-ttu-id="6657e-3331">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3331">13 digits:</span></span>
- <span data-ttu-id="6657e-3332">最初の桁が0または9ではない</span><span class="sxs-lookup"><span data-stu-id="6657e-3332">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="6657e-3333">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3333">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3334">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3334">Checksum</span></span>

<span data-ttu-id="6657e-3335">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3335">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3336">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3336">Definition</span></span>

<span data-ttu-id="6657e-3337">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3337">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3338">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3338">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3339">Keyword_Thai_Citizen_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3339">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="6657e-3340">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3340">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3341">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3341">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3342">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3342">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="6657e-3343">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="6657e-3343">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="6657e-3344">ID Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3344">ID Number</span></span>
- <span data-ttu-id="6657e-3345">識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3345">Identification Number</span></span>
- <span data-ttu-id="6657e-3346">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="6657e-3346">บัตรประชาชน</span></span>
- <span data-ttu-id="6657e-3347">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="6657e-3347">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="6657e-3348">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="6657e-3348">บัตรประชาชน</span></span>
- <span data-ttu-id="6657e-3349">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="6657e-3349">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="6657e-3350">トルコの国の識別番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3350">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3351">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3351">Format</span></span>

<span data-ttu-id="6657e-3352">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3352">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3353">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3353">Pattern</span></span>

<span data-ttu-id="6657e-3354">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3354">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3355">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3355">Checksum</span></span>

<span data-ttu-id="6657e-3356">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3356">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3357">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3357">Definition</span></span>

<span data-ttu-id="6657e-3358">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3358">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3359">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3359">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3360">Keyword_Turkish_National_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3360">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="6657e-3361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3362">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3362">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3363">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3363">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="6657e-3364">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="6657e-3364">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="6657e-3365">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="6657e-3365">TC Kimlik No</span></span>
- <span data-ttu-id="6657e-3366">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="6657e-3366">TC Kimlik numarası</span></span>
- <span data-ttu-id="6657e-3367">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="6657e-3367">Vatandaşlık numarası</span></span>
- <span data-ttu-id="6657e-3368">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="6657e-3368">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="6657e-p141">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3371">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3371">Format</span></span>

<span data-ttu-id="6657e-3372">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3372">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3373">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3373">Pattern</span></span>

<span data-ttu-id="6657e-3374">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3374">18 letters and digits:</span></span>
- <span data-ttu-id="6657e-3375">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="6657e-3375">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="6657e-3376">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3376">One digit</span></span> 
- <span data-ttu-id="6657e-3377">誕生日を示す DDMMY という日付形式の 5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3377">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="6657e-3378">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="6657e-3378">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="6657e-3379">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3379">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3380">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3380">Checksum</span></span>

<span data-ttu-id="6657e-3381">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3382">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3382">Definition</span></span>

<span data-ttu-id="6657e-3383">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3383">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3384">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3384">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3385">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3385">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="6657e-3386">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3386">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3387">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3387">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="6657e-3388">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6657e-3388">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="6657e-3389">dvla</span><span class="sxs-lookup"><span data-stu-id="6657e-3389">DVLA</span></span> 
- <span data-ttu-id="6657e-3390">light vans</span><span class="sxs-lookup"><span data-stu-id="6657e-3390">light vans</span></span> 
- <span data-ttu-id="6657e-3391">quadbikes</span><span class="sxs-lookup"><span data-stu-id="6657e-3391">quadbikes</span></span> 
- <span data-ttu-id="6657e-3392">motor cars</span><span class="sxs-lookup"><span data-stu-id="6657e-3392">motor cars</span></span> 
- <span data-ttu-id="6657e-3393">125cc</span><span class="sxs-lookup"><span data-stu-id="6657e-3393">125cc</span></span> 
- <span data-ttu-id="6657e-3394">sidecar</span><span class="sxs-lookup"><span data-stu-id="6657e-3394">sidecar</span></span> 
- <span data-ttu-id="6657e-3395">tricycles</span><span class="sxs-lookup"><span data-stu-id="6657e-3395">tricycles</span></span> 
- <span data-ttu-id="6657e-3396">motorcycles</span><span class="sxs-lookup"><span data-stu-id="6657e-3396">motorcycles</span></span> 
- <span data-ttu-id="6657e-3397">photocard licence</span><span class="sxs-lookup"><span data-stu-id="6657e-3397">photocard licence</span></span> 
- <span data-ttu-id="6657e-3398">learner drivers</span><span class="sxs-lookup"><span data-stu-id="6657e-3398">learner drivers</span></span> 
- <span data-ttu-id="6657e-3399">licence holder</span><span class="sxs-lookup"><span data-stu-id="6657e-3399">licence holder</span></span> 
- <span data-ttu-id="6657e-3400">licence holders</span><span class="sxs-lookup"><span data-stu-id="6657e-3400">licence holders</span></span> 
- <span data-ttu-id="6657e-3401">driving licences</span><span class="sxs-lookup"><span data-stu-id="6657e-3401">driving licences</span></span> 
- <span data-ttu-id="6657e-3402">driving licence</span><span class="sxs-lookup"><span data-stu-id="6657e-3402">driving licence</span></span> 
- <span data-ttu-id="6657e-3403">dual control car</span><span class="sxs-lookup"><span data-stu-id="6657e-3403">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="6657e-p142">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="6657e-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3406">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3406">Format</span></span>

<span data-ttu-id="6657e-3407">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3407">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3408">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3408">Pattern</span></span>

<span data-ttu-id="6657e-3409">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3409">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3410">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3410">Checksum</span></span>

<span data-ttu-id="6657e-3411">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3411">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3412">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3412">Definition</span></span>

<span data-ttu-id="6657e-3413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3414">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3414">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3415">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3415">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3416">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3416">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="6657e-3417">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="6657e-3417">Keyword_uk_electoral</span></span>

- <span data-ttu-id="6657e-3418">council nomination</span><span class="sxs-lookup"><span data-stu-id="6657e-3418">council nomination</span></span> 
- <span data-ttu-id="6657e-3419">nomination form</span><span class="sxs-lookup"><span data-stu-id="6657e-3419">nomination form</span></span> 
- <span data-ttu-id="6657e-3420">electoral register</span><span class="sxs-lookup"><span data-stu-id="6657e-3420">electoral register</span></span> 
- <span data-ttu-id="6657e-3421">electoral roll</span><span class="sxs-lookup"><span data-stu-id="6657e-3421">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="6657e-p143">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="6657e-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3424">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3424">Format</span></span>

<span data-ttu-id="6657e-3425">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3425">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3426">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3426">Pattern</span></span>

<span data-ttu-id="6657e-3427">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="6657e-3427">10-17 digits:</span></span>
- <span data-ttu-id="6657e-3428">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3428">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="6657e-3429">スペース</span><span class="sxs-lookup"><span data-stu-id="6657e-3429">A space</span></span> 
- <span data-ttu-id="6657e-3430">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3430">Three digits</span></span> 
- <span data-ttu-id="6657e-3431">スペース</span><span class="sxs-lookup"><span data-stu-id="6657e-3431">A space</span></span> 
- <span data-ttu-id="6657e-3432">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3432">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3433">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3433">Checksum</span></span>

<span data-ttu-id="6657e-3434">有</span><span class="sxs-lookup"><span data-stu-id="6657e-3434">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3435">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3435">Definition</span></span>

<span data-ttu-id="6657e-3436">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3436">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3437">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3437">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3438">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-3438">One of the following is true:</span></span>
    - <span data-ttu-id="6657e-3439">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3439">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="6657e-3440">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3440">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="6657e-3441">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3441">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="6657e-3442">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="6657e-3442">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3443">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3443">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="6657e-3444">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="6657e-3444">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="6657e-3445">national health service</span><span class="sxs-lookup"><span data-stu-id="6657e-3445">national health service</span></span> 
- <span data-ttu-id="6657e-3446">nhs</span><span class="sxs-lookup"><span data-stu-id="6657e-3446">nhs</span></span> 
- <span data-ttu-id="6657e-3447">health services authority</span><span class="sxs-lookup"><span data-stu-id="6657e-3447">health services authority</span></span> 
- <span data-ttu-id="6657e-3448">health authority</span><span class="sxs-lookup"><span data-stu-id="6657e-3448">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="6657e-3449">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="6657e-3449">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="6657e-3450">patient id</span><span class="sxs-lookup"><span data-stu-id="6657e-3450">patient id</span></span> 
- <span data-ttu-id="6657e-3451">patient identification</span><span class="sxs-lookup"><span data-stu-id="6657e-3451">patient identification</span></span> 
- <span data-ttu-id="6657e-3452">patient no</span><span class="sxs-lookup"><span data-stu-id="6657e-3452">patient no</span></span> 
- <span data-ttu-id="6657e-3453">patient number</span><span class="sxs-lookup"><span data-stu-id="6657e-3453">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="6657e-3454">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="6657e-3454">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="6657e-3455">GP</span><span class="sxs-lookup"><span data-stu-id="6657e-3455">GP</span></span> 
- <span data-ttu-id="6657e-3456">dob</span><span class="sxs-lookup"><span data-stu-id="6657e-3456">DOB</span></span> 
- <span data-ttu-id="6657e-3457">D.</span><span class="sxs-lookup"><span data-stu-id="6657e-3457">D.O.B</span></span> 
- <span data-ttu-id="6657e-3458">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="6657e-3458">Date of Birth</span></span> 
- <span data-ttu-id="6657e-3459">Birth Date</span><span class="sxs-lookup"><span data-stu-id="6657e-3459">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="6657e-p144">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="6657e-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3462">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3462">Format</span></span>

<span data-ttu-id="6657e-3463">スペースまたはダッシュで区切られた7文字または9文字</span><span class="sxs-lookup"><span data-stu-id="6657e-3463">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3464">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3464">Pattern</span></span>

<span data-ttu-id="6657e-3465">次の2つのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6657e-3465">Two possible patterns:</span></span>

- <span data-ttu-id="6657e-3466">2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。</span><span class="sxs-lookup"><span data-stu-id="6657e-3466">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="6657e-3467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3467">Six digits</span></span>
- <span data-ttu-id="6657e-3468">「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)</span><span class="sxs-lookup"><span data-stu-id="6657e-3468">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="6657e-3469">または</span><span class="sxs-lookup"><span data-stu-id="6657e-3469">OR</span></span>

- <span data-ttu-id="6657e-3470">2文字</span><span class="sxs-lookup"><span data-stu-id="6657e-3470">Two letters</span></span>
- <span data-ttu-id="6657e-3471">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-3471">A space or dash</span></span>
- <span data-ttu-id="6657e-3472">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3472">Two digits</span></span>
- <span data-ttu-id="6657e-3473">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-3473">A space or dash</span></span>
- <span data-ttu-id="6657e-3474">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3474">Two digits</span></span>
- <span data-ttu-id="6657e-3475">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-3475">A space or dash</span></span>
- <span data-ttu-id="6657e-3476">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3476">Two digits</span></span>
- <span data-ttu-id="6657e-3477">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-3477">A space or dash</span></span>
- <span data-ttu-id="6657e-3478">' A '、' B '、' C '、または ' d ' のどちらか</span><span class="sxs-lookup"><span data-stu-id="6657e-3478">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3479">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3479">Checksum</span></span>

<span data-ttu-id="6657e-3480">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3480">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3481">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3481">Definition</span></span>

<span data-ttu-id="6657e-3482">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3482">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3483">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3483">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3484">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3484">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="6657e-3485">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3485">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3486">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3486">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3487">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-3487">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3488">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3488">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="6657e-3489">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="6657e-3489">Keyword_uk_nino</span></span>

- <span data-ttu-id="6657e-3490">national insurance number</span><span class="sxs-lookup"><span data-stu-id="6657e-3490">national insurance number</span></span> 
- <span data-ttu-id="6657e-3491">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="6657e-3491">national insurance contributions</span></span> 
- <span data-ttu-id="6657e-3492">protection act</span><span class="sxs-lookup"><span data-stu-id="6657e-3492">protection act</span></span> 
- <span data-ttu-id="6657e-3493">金</span><span class="sxs-lookup"><span data-stu-id="6657e-3493">insurance</span></span> 
- <span data-ttu-id="6657e-3494">social security number</span><span class="sxs-lookup"><span data-stu-id="6657e-3494">social security number</span></span> 
- <span data-ttu-id="6657e-3495">insurance application</span><span class="sxs-lookup"><span data-stu-id="6657e-3495">insurance application</span></span> 
- <span data-ttu-id="6657e-3496">medical application</span><span class="sxs-lookup"><span data-stu-id="6657e-3496">medical application</span></span> 
- <span data-ttu-id="6657e-3497">social insurance</span><span class="sxs-lookup"><span data-stu-id="6657e-3497">social insurance</span></span> 
- <span data-ttu-id="6657e-3498">medical attention</span><span class="sxs-lookup"><span data-stu-id="6657e-3498">medical attention</span></span> 
- <span data-ttu-id="6657e-3499">social security</span><span class="sxs-lookup"><span data-stu-id="6657e-3499">social security</span></span> 
- <span data-ttu-id="6657e-3500">great britain</span><span class="sxs-lookup"><span data-stu-id="6657e-3500">great britain</span></span> 
- <span data-ttu-id="6657e-3501">金</span><span class="sxs-lookup"><span data-stu-id="6657e-3501">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="6657e-p145">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3504">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3504">Format</span></span>

<span data-ttu-id="6657e-3505">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3505">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3506">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3506">Pattern</span></span>

<span data-ttu-id="6657e-3507">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3507">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3508">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3508">Checksum</span></span>

<span data-ttu-id="6657e-3509">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3509">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3510">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3510">Definition</span></span>

<span data-ttu-id="6657e-3511">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3511">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3512">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3512">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3513">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3513">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3514">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3514">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="6657e-3515">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="6657e-3515">Keyword_passport</span></span>

- <span data-ttu-id="6657e-3516">Passport Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3516">Passport Number</span></span> 
- <span data-ttu-id="6657e-3517">Passport No</span><span class="sxs-lookup"><span data-stu-id="6657e-3517">Passport No</span></span> 
- <span data-ttu-id="6657e-3518">Passport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3518">Passport #</span></span> 
- <span data-ttu-id="6657e-3519">サインアウト</span><span class="sxs-lookup"><span data-stu-id="6657e-3519">Passport#</span></span> 
- <span data-ttu-id="6657e-3520">PassportID</span><span class="sxs-lookup"><span data-stu-id="6657e-3520">PassportID</span></span> 
- <span data-ttu-id="6657e-3521">Passportno</span><span class="sxs-lookup"><span data-stu-id="6657e-3521">Passportno</span></span> 
- <span data-ttu-id="6657e-3522">passportnumber</span><span class="sxs-lookup"><span data-stu-id="6657e-3522">passportnumber</span></span> 
- <span data-ttu-id="6657e-3523">パスポート</span><span class="sxs-lookup"><span data-stu-id="6657e-3523">パスポート</span></span> 
- <span data-ttu-id="6657e-3524">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3524">パスポート番号</span></span> 
- <span data-ttu-id="6657e-3525">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="6657e-3525">パスポートのNum</span></span> 
- <span data-ttu-id="6657e-3526">パスポート #</span><span class="sxs-lookup"><span data-stu-id="6657e-3526">パスポート＃</span></span> 
- <span data-ttu-id="6657e-3527">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="6657e-3527">Numéro de passeport</span></span> 
- <span data-ttu-id="6657e-3528">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="6657e-3528">Passeport n °</span></span> 
- <span data-ttu-id="6657e-3529">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="6657e-3529">Passeport Non</span></span> 
- <span data-ttu-id="6657e-3530">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3530">Passeport #</span></span> 
- <span data-ttu-id="6657e-3531">Passeport #</span><span class="sxs-lookup"><span data-stu-id="6657e-3531">Passeport#</span></span> 
- <span data-ttu-id="6657e-3532">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="6657e-3532">PasseportNon</span></span> 
- <span data-ttu-id="6657e-3533">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="6657e-3533">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="6657e-3534">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3534">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3535">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3535">Format</span></span>

<span data-ttu-id="6657e-3536">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3536">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3537">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3537">Pattern</span></span>

<span data-ttu-id="6657e-3538">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3538">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3539">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3539">Checksum</span></span>

<span data-ttu-id="6657e-3540">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3540">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3541">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3541">Definition</span></span>

<span data-ttu-id="6657e-3542">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3542">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3543">正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3543">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3544">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3544">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="6657e-3545">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3545">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="6657e-3546">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="6657e-3546">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="6657e-3547">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3547">Checking Account Number</span></span> 
- <span data-ttu-id="6657e-3548">Checking Account</span><span class="sxs-lookup"><span data-stu-id="6657e-3548">Checking Account</span></span> 
- <span data-ttu-id="6657e-3549">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-3549">Checking Account #</span></span> 
- <span data-ttu-id="6657e-3550">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3550">Checking Acct Number</span></span> 
- <span data-ttu-id="6657e-3551">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-3551">Checking Acct #</span></span> 
- <span data-ttu-id="6657e-3552">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3552">Checking Acct No.</span></span> 
- <span data-ttu-id="6657e-3553">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3553">Checking Account No.</span></span> 
- <span data-ttu-id="6657e-3554">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3554">Bank Account Number</span></span> 
- <span data-ttu-id="6657e-3555">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-3555">Bank Account #</span></span> 
- <span data-ttu-id="6657e-3556">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3556">Bank Acct Number</span></span> 
- <span data-ttu-id="6657e-3557">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-3557">Bank Acct #</span></span> 
- <span data-ttu-id="6657e-3558">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3558">Bank Acct No.</span></span> 
- <span data-ttu-id="6657e-3559">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3559">Bank Account No.</span></span> 
- <span data-ttu-id="6657e-3560">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3560">Savings Account Number</span></span> 
- <span data-ttu-id="6657e-3561">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="6657e-3561">Savings Account.</span></span> 
- <span data-ttu-id="6657e-3562">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-3562">Savings Account #</span></span> 
- <span data-ttu-id="6657e-3563">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3563">Savings Acct Number</span></span> 
- <span data-ttu-id="6657e-3564">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-3564">Savings Acct #</span></span> 
- <span data-ttu-id="6657e-3565">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3565">Savings Acct No.</span></span> 
- <span data-ttu-id="6657e-3566">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3566">Savings Account No.</span></span> 
- <span data-ttu-id="6657e-3567">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3567">Debit Account Number</span></span> 
- <span data-ttu-id="6657e-3568">Debit Account</span><span class="sxs-lookup"><span data-stu-id="6657e-3568">Debit Account</span></span> 
- <span data-ttu-id="6657e-3569">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="6657e-3569">Debit Account #</span></span> 
- <span data-ttu-id="6657e-3570">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="6657e-3570">Debit Acct Number</span></span> 
- <span data-ttu-id="6657e-3571">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="6657e-3571">Debit Acct #</span></span> 
- <span data-ttu-id="6657e-3572">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3572">Debit Acct No.</span></span> 
- <span data-ttu-id="6657e-3573">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="6657e-3573">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="6657e-3574">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3574">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3575">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3575">Format</span></span>

<span data-ttu-id="6657e-3576">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="6657e-3576">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3577">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3577">Pattern</span></span>

<span data-ttu-id="6657e-3578">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="6657e-3578">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="6657e-3579">ddd ddd ddd のような形式の9桁の数字は一致します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3579">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="6657e-3580">ddddddddd のように9桁の数字は一致しません。</span><span class="sxs-lookup"><span data-stu-id="6657e-3580">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3581">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3581">Checksum</span></span>

<span data-ttu-id="6657e-3582">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3582">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3583">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3583">Definition</span></span>

<span data-ttu-id="6657e-3584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3585">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3585">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3586">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3586">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="6657e-3587">Keyword_us_drivers_license からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="6657e-3587">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="6657e-3588">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3588">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3589">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3589">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3590">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3590">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="6657e-3591">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3591">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="6657e-3592">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-3592">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3593">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3593">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="6657e-3594">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="6657e-3594">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="6657e-3595">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-3595">DL</span></span> 
- <span data-ttu-id="6657e-3596">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-3596">DLS</span></span> 
- <span data-ttu-id="6657e-3597">CDL</span><span class="sxs-lookup"><span data-stu-id="6657e-3597">CDL</span></span> 
- <span data-ttu-id="6657e-3598">cdls</span><span class="sxs-lookup"><span data-stu-id="6657e-3598">CDLS</span></span> 
- <span data-ttu-id="6657e-3599">ID</span><span class="sxs-lookup"><span data-stu-id="6657e-3599">ID</span></span> 
- <span data-ttu-id="6657e-3600">rid</span><span class="sxs-lookup"><span data-stu-id="6657e-3600">IDs</span></span> 
- <span data-ttu-id="6657e-3601">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-3601">DL#</span></span> 
- <span data-ttu-id="6657e-3602">dl</span><span class="sxs-lookup"><span data-stu-id="6657e-3602">DLS#</span></span> 
- <span data-ttu-id="6657e-3603">CDL</span><span class="sxs-lookup"><span data-stu-id="6657e-3603">CDL#</span></span> 
- <span data-ttu-id="6657e-3604">cdls #</span><span class="sxs-lookup"><span data-stu-id="6657e-3604">CDLS#</span></span> 
- <span data-ttu-id="6657e-3605">rid</span><span class="sxs-lookup"><span data-stu-id="6657e-3605">ID#</span></span>
- <span data-ttu-id="6657e-3606">rid</span><span class="sxs-lookup"><span data-stu-id="6657e-3606">IDs#</span></span> 
- <span data-ttu-id="6657e-3607">ID number</span><span class="sxs-lookup"><span data-stu-id="6657e-3607">ID number</span></span> 
- <span data-ttu-id="6657e-3608">ID numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-3608">ID numbers</span></span> 
- <span data-ttu-id="6657e-3609">そして</span><span class="sxs-lookup"><span data-stu-id="6657e-3609">LIC</span></span> 
- <span data-ttu-id="6657e-3610">そして</span><span class="sxs-lookup"><span data-stu-id="6657e-3610">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="6657e-3611">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="6657e-3611">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="6657e-3612">driverlic</span><span class="sxs-lookup"><span data-stu-id="6657e-3612">DriverLic</span></span> 
- <span data-ttu-id="6657e-3613">driverlics</span><span class="sxs-lookup"><span data-stu-id="6657e-3613">DriverLics</span></span> 
- <span data-ttu-id="6657e-3614">driverlicense</span><span class="sxs-lookup"><span data-stu-id="6657e-3614">DriverLicense</span></span> 
- <span data-ttu-id="6657e-3615">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="6657e-3615">DriverLicenses</span></span> 
- <span data-ttu-id="6657e-3616">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-3616">Driver Lic</span></span> 
- <span data-ttu-id="6657e-3617">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-3617">Driver Lics</span></span> 
- <span data-ttu-id="6657e-3618">Driver License</span><span class="sxs-lookup"><span data-stu-id="6657e-3618">Driver License</span></span> 
- <span data-ttu-id="6657e-3619">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-3619">Driver Licenses</span></span> 
- <span data-ttu-id="6657e-3620">driverslic</span><span class="sxs-lookup"><span data-stu-id="6657e-3620">DriversLic</span></span> 
- <span data-ttu-id="6657e-3621">driverslics</span><span class="sxs-lookup"><span data-stu-id="6657e-3621">DriversLics</span></span> 
- <span data-ttu-id="6657e-3622">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="6657e-3622">DriversLicense</span></span> 
- <span data-ttu-id="6657e-3623">このライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-3623">DriversLicenses</span></span> 
- <span data-ttu-id="6657e-3624">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-3624">Drivers Lic</span></span> 
- <span data-ttu-id="6657e-3625">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-3625">Drivers Lics</span></span> 
- <span data-ttu-id="6657e-3626">Drivers License</span><span class="sxs-lookup"><span data-stu-id="6657e-3626">Drivers License</span></span> 
- <span data-ttu-id="6657e-3627">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-3627">Drivers Licenses</span></span> 
- <span data-ttu-id="6657e-3628">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-3628">Driver'Lic</span></span> 
- <span data-ttu-id="6657e-3629">driver' lics</span><span class="sxs-lookup"><span data-stu-id="6657e-3629">Driver'Lics</span></span> 
- <span data-ttu-id="6657e-3630">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-3630">Driver'License</span></span> 
- <span data-ttu-id="6657e-3631">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-3631">Driver'Licenses</span></span> 
- <span data-ttu-id="6657e-3632">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-3632">Driver' Lic</span></span> 
- <span data-ttu-id="6657e-3633">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-3633">Driver' Lics</span></span> 
- <span data-ttu-id="6657e-3634">Driver' License</span><span class="sxs-lookup"><span data-stu-id="6657e-3634">Driver' License</span></span> 
- <span data-ttu-id="6657e-3635">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-3635">Driver' Licenses</span></span>
- <span data-ttu-id="6657e-3636">driver' slic</span><span class="sxs-lookup"><span data-stu-id="6657e-3636">Driver'sLic</span></span> 
- <span data-ttu-id="6657e-3637">driver' slics</span><span class="sxs-lookup"><span data-stu-id="6657e-3637">Driver'sLics</span></span> 
- <span data-ttu-id="6657e-3638">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-3638">Driver'sLicense</span></span> 
- <span data-ttu-id="6657e-3639">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="6657e-3639">Driver'sLicenses</span></span> 
- <span data-ttu-id="6657e-3640">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="6657e-3640">Driver's Lic</span></span> 
- <span data-ttu-id="6657e-3641">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="6657e-3641">Driver's Lics</span></span> 
- <span data-ttu-id="6657e-3642">Driver's License</span><span class="sxs-lookup"><span data-stu-id="6657e-3642">Driver's License</span></span> 
- <span data-ttu-id="6657e-3643">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="6657e-3643">Driver's Licenses</span></span> 
- <span data-ttu-id="6657e-3644">identification number</span><span class="sxs-lookup"><span data-stu-id="6657e-3644">identification number</span></span> 
- <span data-ttu-id="6657e-3645">identification numbers</span><span class="sxs-lookup"><span data-stu-id="6657e-3645">identification numbers</span></span> 
- <span data-ttu-id="6657e-3646">identification #</span><span class="sxs-lookup"><span data-stu-id="6657e-3646">identification #</span></span> 
- <span data-ttu-id="6657e-3647">id card</span><span class="sxs-lookup"><span data-stu-id="6657e-3647">id card</span></span> 
- <span data-ttu-id="6657e-3648">id cards</span><span class="sxs-lookup"><span data-stu-id="6657e-3648">id cards</span></span> 
- <span data-ttu-id="6657e-3649">identification card</span><span class="sxs-lookup"><span data-stu-id="6657e-3649">identification card</span></span> 
- <span data-ttu-id="6657e-3650">identification cards</span><span class="sxs-lookup"><span data-stu-id="6657e-3650">identification cards</span></span> 
- <span data-ttu-id="6657e-3651">driverlic #</span><span class="sxs-lookup"><span data-stu-id="6657e-3651">DriverLic#</span></span> 
- <span data-ttu-id="6657e-3652">driverlics #</span><span class="sxs-lookup"><span data-stu-id="6657e-3652">DriverLics#</span></span> 
- <span data-ttu-id="6657e-3653">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="6657e-3653">DriverLicense#</span></span> 
- <span data-ttu-id="6657e-3654">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="6657e-3654">DriverLicenses#</span></span> 
- <span data-ttu-id="6657e-3655">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-3655">Driver Lic#</span></span> 
- <span data-ttu-id="6657e-3656">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-3656">Driver Lics#</span></span> 
- <span data-ttu-id="6657e-3657">Driver License#</span><span class="sxs-lookup"><span data-stu-id="6657e-3657">Driver License#</span></span> 
- <span data-ttu-id="6657e-3658">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-3658">Driver Licenses#</span></span> 
- <span data-ttu-id="6657e-3659">driverslic #</span><span class="sxs-lookup"><span data-stu-id="6657e-3659">DriversLic#</span></span> 
- <span data-ttu-id="6657e-3660">driverslics #</span><span class="sxs-lookup"><span data-stu-id="6657e-3660">DriversLics#</span></span> 
- <span data-ttu-id="6657e-3661">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-3661">DriversLicense#</span></span> 
- <span data-ttu-id="6657e-3662">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-3662">DriversLicenses#</span></span> 
- <span data-ttu-id="6657e-3663">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-3663">Drivers Lic#</span></span> 
- <span data-ttu-id="6657e-3664">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-3664">Drivers Lics#</span></span> 
- <span data-ttu-id="6657e-3665">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="6657e-3665">Drivers License#</span></span> 
- <span data-ttu-id="6657e-3666">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-3666">Drivers Licenses#</span></span> 
- <span data-ttu-id="6657e-3667">driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="6657e-3667">Driver'Lic#</span></span> 
- <span data-ttu-id="6657e-3668">driver' lics #</span><span class="sxs-lookup"><span data-stu-id="6657e-3668">Driver'Lics#</span></span> 
- <span data-ttu-id="6657e-3669">driver' License #</span><span class="sxs-lookup"><span data-stu-id="6657e-3669">Driver'License#</span></span> 
- <span data-ttu-id="6657e-3670">driver' Licenses #</span><span class="sxs-lookup"><span data-stu-id="6657e-3670">Driver'Licenses#</span></span> 
- <span data-ttu-id="6657e-3671">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-3671">Driver' Lic#</span></span> 
- <span data-ttu-id="6657e-3672">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-3672">Driver' Lics#</span></span> 
- <span data-ttu-id="6657e-3673">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="6657e-3673">Driver' License#</span></span> 
- <span data-ttu-id="6657e-3674">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-3674">Driver' Licenses#</span></span> 
- <span data-ttu-id="6657e-3675">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="6657e-3675">Driver'sLic#</span></span> 
- <span data-ttu-id="6657e-3676">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="6657e-3676">Driver'sLics#</span></span> 
- <span data-ttu-id="6657e-3677">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="6657e-3677">Driver'sLicense#</span></span> 
- <span data-ttu-id="6657e-3678">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="6657e-3678">Driver'sLicenses#</span></span> 
- <span data-ttu-id="6657e-3679">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="6657e-3679">Driver's Lic#</span></span> 
- <span data-ttu-id="6657e-3680">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="6657e-3680">Driver's Lics#</span></span> 
- <span data-ttu-id="6657e-3681">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="6657e-3681">Driver's License#</span></span> 
- <span data-ttu-id="6657e-3682">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="6657e-3682">Driver's Licenses#</span></span> 
- <span data-ttu-id="6657e-3683">id card#</span><span class="sxs-lookup"><span data-stu-id="6657e-3683">id card#</span></span> 
- <span data-ttu-id="6657e-3684">id cards#</span><span class="sxs-lookup"><span data-stu-id="6657e-3684">id cards#</span></span> 
- <span data-ttu-id="6657e-3685">identification card#</span><span class="sxs-lookup"><span data-stu-id="6657e-3685">identification card#</span></span> 
- <span data-ttu-id="6657e-3686">identification cards#</span><span class="sxs-lookup"><span data-stu-id="6657e-3686">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="6657e-3687">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="6657e-3687">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="6657e-3688">州の略号 (たとえば、"NY")</span><span class="sxs-lookup"><span data-stu-id="6657e-3688">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="6657e-3689">州の名前 (たとえば、"New York")</span><span class="sxs-lookup"><span data-stu-id="6657e-3689">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="6657e-3690">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="6657e-3690">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3691">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3691">Format</span></span>

<span data-ttu-id="6657e-3692">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="6657e-3692">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3693">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3693">Pattern</span></span>

<span data-ttu-id="6657e-3694">さ</span><span class="sxs-lookup"><span data-stu-id="6657e-3694">Formatted:</span></span>
- <span data-ttu-id="6657e-3695">数字「9」</span><span class="sxs-lookup"><span data-stu-id="6657e-3695">The digit "9"</span></span> 
- <span data-ttu-id="6657e-3696">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3696">Two digits</span></span> 
- <span data-ttu-id="6657e-3697">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-3697">A space or dash</span></span> 
- <span data-ttu-id="6657e-3698">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="6657e-3698">A "7" or "8"</span></span> 
- <span data-ttu-id="6657e-3699">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3699">A digit</span></span> 
- <span data-ttu-id="6657e-3700">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="6657e-3700">A space, or dash</span></span> 
- <span data-ttu-id="6657e-3701">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3701">Four digits</span></span>

<span data-ttu-id="6657e-3702">なし</span><span class="sxs-lookup"><span data-stu-id="6657e-3702">Unformatted:</span></span>
- <span data-ttu-id="6657e-3703">数字「9」</span><span class="sxs-lookup"><span data-stu-id="6657e-3703">The digit "9"</span></span> 
- <span data-ttu-id="6657e-3704">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3704">Two digits</span></span> 
- <span data-ttu-id="6657e-3705">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="6657e-3705">A "7" or "8"</span></span> 
- <span data-ttu-id="6657e-3706">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3706">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3707">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3707">Checksum</span></span>

<span data-ttu-id="6657e-3708">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3708">No</span></span>

### <a name="definition"></a><span data-ttu-id="6657e-3709">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3709">Definition</span></span>

<span data-ttu-id="6657e-3710">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3710">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3711">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3711">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3712">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-3712">At least one of the following is true:</span></span>
    - <span data-ttu-id="6657e-3713">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3713">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="6657e-3714">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3714">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="6657e-3715">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3715">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="6657e-3716">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3716">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="6657e-3717">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3717">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3718">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3718">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3719">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="6657e-3719">At least one of the following is true:</span></span>
    - <span data-ttu-id="6657e-3720">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3720">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="6657e-3721">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3721">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="6657e-3722">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3722">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3723">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3723">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="6657e-3724">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="6657e-3724">Keyword_itin</span></span>

- <span data-ttu-id="6657e-3725">納税</span><span class="sxs-lookup"><span data-stu-id="6657e-3725">taxpayer</span></span> 
- <span data-ttu-id="6657e-3726">tax id</span><span class="sxs-lookup"><span data-stu-id="6657e-3726">tax id</span></span> 
- <span data-ttu-id="6657e-3727">tax identification</span><span class="sxs-lookup"><span data-stu-id="6657e-3727">tax identification</span></span> 
- <span data-ttu-id="6657e-3728">itin</span><span class="sxs-lookup"><span data-stu-id="6657e-3728">itin</span></span> 
- <span data-ttu-id="6657e-3729">ssn</span><span class="sxs-lookup"><span data-stu-id="6657e-3729">ssn</span></span> 
- <span data-ttu-id="6657e-3730">は</span><span class="sxs-lookup"><span data-stu-id="6657e-3730">tin</span></span> 
- <span data-ttu-id="6657e-3731">social security</span><span class="sxs-lookup"><span data-stu-id="6657e-3731">social security</span></span> 
- <span data-ttu-id="6657e-3732">tax payer</span><span class="sxs-lookup"><span data-stu-id="6657e-3732">tax payer</span></span> 
- <span data-ttu-id="6657e-3733">itins</span><span class="sxs-lookup"><span data-stu-id="6657e-3733">itins</span></span> 
- <span data-ttu-id="6657e-3734">taxid</span><span class="sxs-lookup"><span data-stu-id="6657e-3734">taxid</span></span> 
- <span data-ttu-id="6657e-3735">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="6657e-3735">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="6657e-3736">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="6657e-3736">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="6657e-3737">License</span><span class="sxs-lookup"><span data-stu-id="6657e-3737">License</span></span> 
- <span data-ttu-id="6657e-3738">DL</span><span class="sxs-lookup"><span data-stu-id="6657e-3738">DL</span></span> 
- <span data-ttu-id="6657e-3739">dob</span><span class="sxs-lookup"><span data-stu-id="6657e-3739">DOB</span></span> 
- <span data-ttu-id="6657e-3740">誕生日</span><span class="sxs-lookup"><span data-stu-id="6657e-3740">Birthdate</span></span> 
- <span data-ttu-id="6657e-3741">Birthday</span><span class="sxs-lookup"><span data-stu-id="6657e-3741">Birthday</span></span> 
- <span data-ttu-id="6657e-3742">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="6657e-3742">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="6657e-3743">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="6657e-3743">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="6657e-3744">Format</span><span class="sxs-lookup"><span data-stu-id="6657e-3744">Format</span></span>

<span data-ttu-id="6657e-3745">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="6657e-3745">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="6657e-3746">2011より前に発行された場合、SSN の書式には、特定の範囲内にある特定の範囲内にある必要があり、チェックサムがないという厳密な形式があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-3746">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="6657e-3747">パターン</span><span class="sxs-lookup"><span data-stu-id="6657e-3747">Pattern</span></span>

<span data-ttu-id="6657e-3748">次の4つの異なるパターンで ssns を検索する4つの関数があります。</span><span class="sxs-lookup"><span data-stu-id="6657e-3748">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="6657e-3749">Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="6657e-3749">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="6657e-3750">Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="6657e-3750">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="6657e-3751">Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="6657e-3751">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="6657e-3752">Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="6657e-3752">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="6657e-3753">チェックサム</span><span class="sxs-lookup"><span data-stu-id="6657e-3753">Checksum</span></span>

<span data-ttu-id="6657e-3754">無</span><span class="sxs-lookup"><span data-stu-id="6657e-3754">No</span></span>


### <a name="definition"></a><span data-ttu-id="6657e-3755">定義</span><span class="sxs-lookup"><span data-stu-id="6657e-3755">Definition</span></span>

<span data-ttu-id="6657e-3756">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3757">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3757">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3758">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3758">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="6657e-3759">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3759">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3760">関数 Func_unformatted_ssn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3760">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3761">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3761">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="6657e-3762">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3762">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3763">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3763">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3764">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3764">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="6657e-3765">関数 Func_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-3765">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="6657e-3766">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="6657e-3766">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="6657e-3767">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3767">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="6657e-3768">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="6657e-3768">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="6657e-3769">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="6657e-3769">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="6657e-3770">キーワード</span><span class="sxs-lookup"><span data-stu-id="6657e-3770">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="6657e-3771">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="6657e-3771">Keyword_ssn</span></span>

- <span data-ttu-id="6657e-3772">Social Security</span><span class="sxs-lookup"><span data-stu-id="6657e-3772">Social Security</span></span> 
- <span data-ttu-id="6657e-3773">Social Security#</span><span class="sxs-lookup"><span data-stu-id="6657e-3773">Social Security#</span></span> 
- <span data-ttu-id="6657e-3774">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="6657e-3774">Soc Sec</span></span> 
- <span data-ttu-id="6657e-3775">SSN</span><span class="sxs-lookup"><span data-stu-id="6657e-3775">SSN</span></span> 
- <span data-ttu-id="6657e-3776">ssn</span><span class="sxs-lookup"><span data-stu-id="6657e-3776">SSNS</span></span> 
- <span data-ttu-id="6657e-3777">SSN</span><span class="sxs-lookup"><span data-stu-id="6657e-3777">SSN#</span></span> 
- <span data-ttu-id="6657e-3778">秒</span><span class="sxs-lookup"><span data-stu-id="6657e-3778">SS#</span></span> 
- <span data-ttu-id="6657e-3779">SSID</span><span class="sxs-lookup"><span data-stu-id="6657e-3779">SSID</span></span> 
   

