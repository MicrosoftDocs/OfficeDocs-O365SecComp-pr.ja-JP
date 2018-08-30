---
title: 機密情報の種類の検索基準：
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;準拠のセンターには、DLP ポリシーを使用する準備ができている 80 の機密性の高い情報の種類が含まれています。このトピックでは、機密性の高い情報の種類のすべてを一覧表示しを示しています DLP ポリシーそれぞれの種類を検出したとき。
ms.openlocfilehash: 064606085363ba9de972511642993277451c8ce3
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532523"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="518c1-104">機密情報の種類の検索基準：</span><span class="sxs-lookup"><span data-stu-id="518c1-104">What the sensitive information types look for</span></span>

<span data-ttu-id="518c1-p102">Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、機密性の高い情報の種類のすべてを一覧表示しを示しています DLP ポリシーそれぞれの種類を検出したとき。機密性の高い情報の種類は、正規表現、または関数を識別可能なパターンによって定義されます。さらに、機密性の高い情報の種類を識別するキーワードやチェックサムなどの corroborative の証拠を使用できます。信頼レベルと近接は、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="518c1-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="518c1-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="518c1-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-111">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-111">Format</span></span>

<span data-ttu-id="518c1-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-113">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-113">Pattern</span></span>

<span data-ttu-id="518c1-114">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-114">Formatted:</span></span>
- <span data-ttu-id="518c1-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="518c1-116">ハイフン</span><span class="sxs-lookup"><span data-stu-id="518c1-116">A hyphen</span></span>
- <span data-ttu-id="518c1-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-117">Four digits</span></span>
- <span data-ttu-id="518c1-118">ハイフン</span><span class="sxs-lookup"><span data-stu-id="518c1-118">A hyphen</span></span>
- <span data-ttu-id="518c1-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-119">A digit</span></span>

<span data-ttu-id="518c1-120">以降では 0、1、2、3、6、7、8 または 9 連続した数字をフォーマットします。</span><span class="sxs-lookup"><span data-stu-id="518c1-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="518c1-121">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-121">Checksum</span></span>

<span data-ttu-id="518c1-122">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-123">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-123">Definition</span></span>

<span data-ttu-id="518c1-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="518c1-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="518c1-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="518c1-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="518c1-129">aba</span><span class="sxs-lookup"><span data-stu-id="518c1-129">aba</span></span>
- <span data-ttu-id="518c1-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="518c1-130">aba #</span></span>
- <span data-ttu-id="518c1-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="518c1-131">aba routing #</span></span>
- <span data-ttu-id="518c1-132">aba ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="518c1-132">aba routing number</span></span>
- <span data-ttu-id="518c1-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="518c1-133">aba#</span></span>
- <span data-ttu-id="518c1-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="518c1-134">abarouting#</span></span>
- <span data-ttu-id="518c1-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="518c1-135">aba number</span></span>
- <span data-ttu-id="518c1-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="518c1-136">abaroutingnumber</span></span>
- <span data-ttu-id="518c1-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="518c1-137">american bank association routing #</span></span>
- <span data-ttu-id="518c1-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="518c1-138">american bank association routing number</span></span>
- <span data-ttu-id="518c1-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="518c1-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="518c1-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="518c1-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="518c1-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="518c1-141">bank routing number</span></span>
- <span data-ttu-id="518c1-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="518c1-142">bankrouting#</span></span>
- <span data-ttu-id="518c1-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="518c1-143">bankroutingnumber</span></span>
- <span data-ttu-id="518c1-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="518c1-144">routing transit number</span></span>
- <span data-ttu-id="518c1-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="518c1-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="518c1-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-147">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-147">Format</span></span>

<span data-ttu-id="518c1-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-149">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-149">Pattern</span></span>

<span data-ttu-id="518c1-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-150">Eight digits:</span></span>
- <span data-ttu-id="518c1-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-151">Two digits</span></span>
- <span data-ttu-id="518c1-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-152">A period</span></span>
- <span data-ttu-id="518c1-153">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-153">Three digits</span></span>
- <span data-ttu-id="518c1-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-154">A period</span></span>
- <span data-ttu-id="518c1-155">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-156">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-156">Checksum</span></span>

<span data-ttu-id="518c1-157">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-158">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-158">Definition</span></span>

<span data-ttu-id="518c1-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-160">正規表現 Regex_argentina_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-161">Keyword_argentina_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="518c1-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="518c1-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="518c1-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="518c1-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="518c1-165">ID</span><span class="sxs-lookup"><span data-stu-id="518c1-165">Identity</span></span> 
- <span data-ttu-id="518c1-166">国家身分証明書の識別</span><span class="sxs-lookup"><span data-stu-id="518c1-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="518c1-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="518c1-167">DNI</span></span> 
- <span data-ttu-id="518c1-168">担当者の NIC の国別レジストリ</span><span class="sxs-lookup"><span data-stu-id="518c1-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="518c1-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="518c1-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="518c1-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="518c1-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="518c1-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="518c1-171">Identidad</span></span> 
- <span data-ttu-id="518c1-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="518c1-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="518c1-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-174">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-174">Format</span></span>

<span data-ttu-id="518c1-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-176">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-176">Pattern</span></span>

<span data-ttu-id="518c1-p103">勘定番号は、6-10 桁の数字です。オーストラリアの銀行の状態の枝番号。</span><span class="sxs-lookup"><span data-stu-id="518c1-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="518c1-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-179">Three digits</span></span> 
- <span data-ttu-id="518c1-180">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-180">A hyphen</span></span> 
- <span data-ttu-id="518c1-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-182">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-182">Checksum</span></span>

<span data-ttu-id="518c1-183">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-184">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-184">Definition</span></span>

<span data-ttu-id="518c1-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="518c1-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="518c1-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="518c1-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="518c1-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="518c1-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="518c1-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="518c1-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="518c1-194">swift bank code</span></span>
- <span data-ttu-id="518c1-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="518c1-195">correspondent bank</span></span>
- <span data-ttu-id="518c1-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="518c1-196">base currency</span></span>
- <span data-ttu-id="518c1-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="518c1-197">usa account</span></span>
- <span data-ttu-id="518c1-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="518c1-198">holder address</span></span>
- <span data-ttu-id="518c1-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="518c1-199">bank address</span></span>
- <span data-ttu-id="518c1-200">
information account</span><span class="sxs-lookup"><span data-stu-id="518c1-200">information account</span></span>
- <span data-ttu-id="518c1-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="518c1-201">fund transfers</span></span>
- <span data-ttu-id="518c1-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="518c1-202">bank charges</span></span>
- <span data-ttu-id="518c1-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="518c1-203">bank details</span></span>
- <span data-ttu-id="518c1-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="518c1-204">banking information</span></span>
- <span data-ttu-id="518c1-205">
full names</span><span class="sxs-lookup"><span data-stu-id="518c1-205">full names</span></span>
- <span data-ttu-id="518c1-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="518c1-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="518c1-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-208">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-208">Format</span></span>

<span data-ttu-id="518c1-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="518c1-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-210">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-210">Pattern</span></span>

<span data-ttu-id="518c1-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="518c1-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-213">Two digits</span></span> 
- <span data-ttu-id="518c1-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="518c1-215">または</span><span class="sxs-lookup"><span data-stu-id="518c1-215">OR</span></span>

- <span data-ttu-id="518c1-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-217">4-9 digits</span></span>

<span data-ttu-id="518c1-218">または</span><span class="sxs-lookup"><span data-stu-id="518c1-218">OR</span></span>

- <span data-ttu-id="518c1-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="518c1-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-220">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-220">Checksum</span></span>

<span data-ttu-id="518c1-221">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-222">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-222">Definition</span></span>

<span data-ttu-id="518c1-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="518c1-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="518c1-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="518c1-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="518c1-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="518c1-229">international driving permits</span></span>
- <span data-ttu-id="518c1-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="518c1-230">australian automobile association</span></span>
- <span data-ttu-id="518c1-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="518c1-231">sydney nsw</span></span>
- <span data-ttu-id="518c1-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="518c1-232">international driving permit</span></span>
- <span data-ttu-id="518c1-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="518c1-233">DriverLicence</span></span>
- <span data-ttu-id="518c1-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="518c1-234">DriverLicences</span></span>
- <span data-ttu-id="518c1-235">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-235">Driver Lic</span></span>
- <span data-ttu-id="518c1-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-236">Driver Licence</span></span>
- <span data-ttu-id="518c1-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-237">Driver Licences</span></span>
- <span data-ttu-id="518c1-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="518c1-238">DriversLic</span></span>
- <span data-ttu-id="518c1-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="518c1-239">DriversLicence</span></span>
- <span data-ttu-id="518c1-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="518c1-240">DriversLicences</span></span>
- <span data-ttu-id="518c1-241">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-241">Drivers Lic</span></span>
- <span data-ttu-id="518c1-242">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-242">Drivers Lics</span></span>
- <span data-ttu-id="518c1-243">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-243">Drivers Licence</span></span>
- <span data-ttu-id="518c1-244">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-244">Drivers Licences</span></span>
- <span data-ttu-id="518c1-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-245">Driver'Lic</span></span>
- <span data-ttu-id="518c1-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-246">Driver'Lics</span></span>
- <span data-ttu-id="518c1-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="518c1-247">Driver'Licence</span></span>
- <span data-ttu-id="518c1-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="518c1-248">Driver'Licences</span></span>
- <span data-ttu-id="518c1-249">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-249">Driver' Lic</span></span>
- <span data-ttu-id="518c1-250">ドライバー ' Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-250">Driver' Lics</span></span>
- <span data-ttu-id="518c1-251">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-251">Driver' Licence</span></span>
- <span data-ttu-id="518c1-252">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-252">Driver' Licences</span></span>
- <span data-ttu-id="518c1-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="518c1-253">Driver'sLic</span></span>
- <span data-ttu-id="518c1-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="518c1-254">Driver'sLics</span></span>
- <span data-ttu-id="518c1-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="518c1-255">Driver'sLicence</span></span>
- <span data-ttu-id="518c1-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="518c1-256">Driver'sLicences</span></span>
- <span data-ttu-id="518c1-257">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-257">Driver's Lic</span></span>
- <span data-ttu-id="518c1-258">ドライバーの Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-258">Driver's Lics</span></span>
- <span data-ttu-id="518c1-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-259">Driver's Licence</span></span>
- <span data-ttu-id="518c1-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-260">Driver's Licences</span></span>
- <span data-ttu-id="518c1-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-261">DriverLic#</span></span>
- <span data-ttu-id="518c1-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-262">DriverLics#</span></span>
- <span data-ttu-id="518c1-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="518c1-263">DriverLicence#</span></span>
- <span data-ttu-id="518c1-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="518c1-264">DriverLicences#</span></span>
- <span data-ttu-id="518c1-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="518c1-265">Driver Lic#</span></span>
- <span data-ttu-id="518c1-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-266">Driver Lics#</span></span>
- <span data-ttu-id="518c1-267">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-267">Driver Licence#</span></span>
- <span data-ttu-id="518c1-268">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-268">Driver Licences#</span></span>
- <span data-ttu-id="518c1-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-269">DriversLic#</span></span>
- <span data-ttu-id="518c1-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-270">DriversLics#</span></span>
- <span data-ttu-id="518c1-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="518c1-271">DriversLicence#</span></span>
- <span data-ttu-id="518c1-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="518c1-272">DriversLicences#</span></span>
- <span data-ttu-id="518c1-273">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="518c1-273">Drivers Lic#</span></span>
- <span data-ttu-id="518c1-274">ドライバー Lics #</span><span class="sxs-lookup"><span data-stu-id="518c1-274">Drivers Lics#</span></span>
- <span data-ttu-id="518c1-275">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-275">Drivers Licence#</span></span>
- <span data-ttu-id="518c1-276">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-276">Drivers Licences#</span></span>
- <span data-ttu-id="518c1-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-277">Driver'Lic#</span></span>
- <span data-ttu-id="518c1-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-278">Driver'Lics#</span></span>
- <span data-ttu-id="518c1-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="518c1-279">Driver'Licence#</span></span>
- <span data-ttu-id="518c1-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="518c1-280">Driver'Licences#</span></span>
- <span data-ttu-id="518c1-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-281">Driver' Lic#</span></span>
- <span data-ttu-id="518c1-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-282">Driver' Lics#</span></span>
- <span data-ttu-id="518c1-283">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-283">Driver' Licence#</span></span>
- <span data-ttu-id="518c1-284">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-284">Driver' Licences#</span></span>
- <span data-ttu-id="518c1-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-285">Driver'sLic#</span></span>
- <span data-ttu-id="518c1-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-286">Driver'sLics#</span></span>
- <span data-ttu-id="518c1-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="518c1-287">Driver'sLicence#</span></span>
- <span data-ttu-id="518c1-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="518c1-288">Driver'sLicences#</span></span>
- <span data-ttu-id="518c1-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-289">Driver's Lic#</span></span>
- <span data-ttu-id="518c1-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-290">Driver's Lics#</span></span>
- <span data-ttu-id="518c1-291">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-291">Driver's Licence#</span></span>
- <span data-ttu-id="518c1-292">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="518c1-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="518c1-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="518c1-294">aaa</span><span class="sxs-lookup"><span data-stu-id="518c1-294">aaa</span></span>
- <span data-ttu-id="518c1-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="518c1-295">DriverLicense</span></span>
- <span data-ttu-id="518c1-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-296">DriverLicenses</span></span>
- <span data-ttu-id="518c1-297">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-297">Driver License</span></span>
- <span data-ttu-id="518c1-298">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-298">Driver Licenses</span></span>
- <span data-ttu-id="518c1-299">証</span><span class="sxs-lookup"><span data-stu-id="518c1-299">DriversLicense</span></span>
- <span data-ttu-id="518c1-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-300">DriversLicenses</span></span>
- <span data-ttu-id="518c1-301">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-301">Drivers License</span></span>
- <span data-ttu-id="518c1-302">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-302">Drivers Licenses</span></span>
- <span data-ttu-id="518c1-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="518c1-303">Driver'License</span></span>
- <span data-ttu-id="518c1-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="518c1-304">Driver'Licenses</span></span>
- <span data-ttu-id="518c1-305">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-305">Driver' License</span></span>
- <span data-ttu-id="518c1-306">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-306">Driver' Licenses</span></span>
- <span data-ttu-id="518c1-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="518c1-307">Driver'sLicense</span></span>
- <span data-ttu-id="518c1-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-308">Driver'sLicenses</span></span>
- <span data-ttu-id="518c1-309">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-309">Driver's License</span></span>
- <span data-ttu-id="518c1-310">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-310">Driver's Licenses</span></span>
- <span data-ttu-id="518c1-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="518c1-311">DriverLicense#</span></span>
- <span data-ttu-id="518c1-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-312">DriverLicenses#</span></span>
- <span data-ttu-id="518c1-313">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-313">Driver License#</span></span>
- <span data-ttu-id="518c1-314">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-314">Driver Licenses#</span></span>
- <span data-ttu-id="518c1-315">証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-315">DriversLicense#</span></span>
- <span data-ttu-id="518c1-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-316">DriversLicenses#</span></span>
- <span data-ttu-id="518c1-317">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-317">Drivers License#</span></span>
- <span data-ttu-id="518c1-318">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-318">Drivers Licenses#</span></span>
- <span data-ttu-id="518c1-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-319">Driver'License#</span></span>
- <span data-ttu-id="518c1-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-320">Driver'Licenses#</span></span>
- <span data-ttu-id="518c1-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-321">Driver' License#</span></span>
- <span data-ttu-id="518c1-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-322">Driver' Licenses#</span></span>
- <span data-ttu-id="518c1-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="518c1-323">Driver'sLicense#</span></span>
- <span data-ttu-id="518c1-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="518c1-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-325">Driver's License#</span></span>
- <span data-ttu-id="518c1-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="518c1-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="518c1-327">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-328">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-328">Format</span></span>

<span data-ttu-id="518c1-329">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-330">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-330">Pattern</span></span>

<span data-ttu-id="518c1-331">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-331">10-11 digits:</span></span>
- <span data-ttu-id="518c1-332">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="518c1-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="518c1-333">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="518c1-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="518c1-334">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="518c1-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="518c1-335">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="518c1-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-336">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-336">Checksum</span></span>

<span data-ttu-id="518c1-337">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-338">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-338">Definition</span></span>

<span data-ttu-id="518c1-339">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-340">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-341">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="518c1-342">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-342">The checksum passes.</span></span>

<span data-ttu-id="518c1-343">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-344">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-345">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-346">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="518c1-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="518c1-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="518c1-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="518c1-348">bank account details</span></span>
- <span data-ttu-id="518c1-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="518c1-349">medicare payments</span></span>
- <span data-ttu-id="518c1-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="518c1-350">mortgage account</span></span>
- <span data-ttu-id="518c1-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="518c1-351">bank payments</span></span>
- <span data-ttu-id="518c1-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="518c1-352">information branch</span></span>
- <span data-ttu-id="518c1-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="518c1-353">credit card loan</span></span>
- <span data-ttu-id="518c1-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="518c1-354">department of human services</span></span>
- <span data-ttu-id="518c1-355">ローカル サービス</span><span class="sxs-lookup"><span data-stu-id="518c1-355">local service</span></span>
- <span data-ttu-id="518c1-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="518c1-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="518c1-357">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-358">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-358">Format</span></span>

<span data-ttu-id="518c1-359">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-360">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-360">Pattern</span></span>

<span data-ttu-id="518c1-361">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-362">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-362">Checksum</span></span>

<span data-ttu-id="518c1-363">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-364">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-364">Definition</span></span>

<span data-ttu-id="518c1-365">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-366">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-367">Keyword_passport または Keyword_australia_passport_number からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="518c1-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-368">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="518c1-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-369">Keyword_passport</span></span>

- <span data-ttu-id="518c1-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="518c1-370">Passport Number</span></span>
- <span data-ttu-id="518c1-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="518c1-371">Passport No</span></span>
- <span data-ttu-id="518c1-372">Passport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-372">Passport #</span></span>
- <span data-ttu-id="518c1-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-373">Passport#</span></span>
- <span data-ttu-id="518c1-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="518c1-374">PassportID</span></span>
- <span data-ttu-id="518c1-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="518c1-375">Passportno</span></span>
- <span data-ttu-id="518c1-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-376">passportnumber</span></span>
- <span data-ttu-id="518c1-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="518c1-377">パスポート</span></span>
- <span data-ttu-id="518c1-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-378">パスポート番号</span></span>
- <span data-ttu-id="518c1-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="518c1-379">パスポートのNum</span></span>
- <span data-ttu-id="518c1-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-380">パスポート ＃</span></span> 
- <span data-ttu-id="518c1-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="518c1-381">Numéro de passeport</span></span>
- <span data-ttu-id="518c1-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="518c1-382">Passeport n °</span></span>
- <span data-ttu-id="518c1-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="518c1-383">Passeport Non</span></span>
- <span data-ttu-id="518c1-384">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-384">Passeport #</span></span>
- <span data-ttu-id="518c1-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-385">Passeport#</span></span>
- <span data-ttu-id="518c1-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="518c1-386">PasseportNon</span></span>
- <span data-ttu-id="518c1-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="518c1-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="518c1-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="518c1-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="518c1-389">passport</span><span class="sxs-lookup"><span data-stu-id="518c1-389">passport</span></span>
- <span data-ttu-id="518c1-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="518c1-390">passport details</span></span>
- <span data-ttu-id="518c1-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="518c1-391">immigration and citizenship</span></span>
- <span data-ttu-id="518c1-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="518c1-392">commonwealth of australia</span></span>
- <span data-ttu-id="518c1-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="518c1-393">department of immigration</span></span>
- <span data-ttu-id="518c1-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="518c1-394">residential address</span></span>
- <span data-ttu-id="518c1-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="518c1-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="518c1-396">visa
</span><span class="sxs-lookup"><span data-stu-id="518c1-396">visa</span></span>
- <span data-ttu-id="518c1-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="518c1-397">national identity card</span></span>
- <span data-ttu-id="518c1-398">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-398">passport number</span></span>
- <span data-ttu-id="518c1-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="518c1-399">travel document</span></span>
- <span data-ttu-id="518c1-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="518c1-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="518c1-401">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="518c1-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-402">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-402">Format</span></span>

<span data-ttu-id="518c1-403">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-404">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-404">Pattern</span></span>

<span data-ttu-id="518c1-405">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="518c1-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="518c1-406">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-406">Three digits</span></span> 
- <span data-ttu-id="518c1-407">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="518c1-407">An optional space</span></span> 
- <span data-ttu-id="518c1-408">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-408">Three digits</span></span> 
- <span data-ttu-id="518c1-409">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="518c1-409">An optional space</span></span> 
- <span data-ttu-id="518c1-410">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="518c1-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-411">Checksum</span></span>

<span data-ttu-id="518c1-412">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-413">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-413">Definition</span></span>

<span data-ttu-id="518c1-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-415">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-416">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="518c1-417">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-418">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="518c1-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="518c1-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="518c1-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="518c1-420">australian business number</span></span>
- <span data-ttu-id="518c1-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="518c1-421">marginal tax rate</span></span>
- <span data-ttu-id="518c1-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="518c1-422">medicare levy</span></span>
- <span data-ttu-id="518c1-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="518c1-423">portfolio number</span></span>
- <span data-ttu-id="518c1-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="518c1-424">service veterans</span></span>
- <span data-ttu-id="518c1-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="518c1-425">withholding tax</span></span>
- <span data-ttu-id="518c1-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="518c1-426">individual tax return</span></span>
- <span data-ttu-id="518c1-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="518c1-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="518c1-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="518c1-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="518c1-429">00000000</span><span class="sxs-lookup"><span data-stu-id="518c1-429">00000000</span></span>
- <span data-ttu-id="518c1-430">11111111</span><span class="sxs-lookup"><span data-stu-id="518c1-430">11111111</span></span>
- <span data-ttu-id="518c1-431">22222222</span><span class="sxs-lookup"><span data-stu-id="518c1-431">22222222</span></span>
- <span data-ttu-id="518c1-432">33333333</span><span class="sxs-lookup"><span data-stu-id="518c1-432">33333333</span></span>
- <span data-ttu-id="518c1-433">44444444</span><span class="sxs-lookup"><span data-stu-id="518c1-433">44444444</span></span>
- <span data-ttu-id="518c1-434">55555555</span><span class="sxs-lookup"><span data-stu-id="518c1-434">55555555</span></span>
- <span data-ttu-id="518c1-435">66666666</span><span class="sxs-lookup"><span data-stu-id="518c1-435">66666666</span></span>
- <span data-ttu-id="518c1-436">77777777</span><span class="sxs-lookup"><span data-stu-id="518c1-436">77777777</span></span>
- <span data-ttu-id="518c1-437">88888888</span><span class="sxs-lookup"><span data-stu-id="518c1-437">88888888</span></span>
- <span data-ttu-id="518c1-438">99999999</span><span class="sxs-lookup"><span data-stu-id="518c1-438">99999999</span></span>
- <span data-ttu-id="518c1-439">000000000</span><span class="sxs-lookup"><span data-stu-id="518c1-439">000000000</span></span>
- <span data-ttu-id="518c1-440">111111111</span><span class="sxs-lookup"><span data-stu-id="518c1-440">111111111</span></span>
- <span data-ttu-id="518c1-441">222222222</span><span class="sxs-lookup"><span data-stu-id="518c1-441">222222222</span></span>
- <span data-ttu-id="518c1-442">333333333</span><span class="sxs-lookup"><span data-stu-id="518c1-442">333333333</span></span>
- <span data-ttu-id="518c1-443">444444444</span><span class="sxs-lookup"><span data-stu-id="518c1-443">444444444</span></span>
- <span data-ttu-id="518c1-444">555555555</span><span class="sxs-lookup"><span data-stu-id="518c1-444">555555555</span></span>
- <span data-ttu-id="518c1-445">666666666</span><span class="sxs-lookup"><span data-stu-id="518c1-445">666666666</span></span>
- <span data-ttu-id="518c1-446">777777777</span><span class="sxs-lookup"><span data-stu-id="518c1-446">777777777</span></span>
- <span data-ttu-id="518c1-447">888888888</span><span class="sxs-lookup"><span data-stu-id="518c1-447">888888888</span></span>
- <span data-ttu-id="518c1-448">999999999</span><span class="sxs-lookup"><span data-stu-id="518c1-448">999999999</span></span>
- <span data-ttu-id="518c1-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="518c1-449">0000000000</span></span>
- <span data-ttu-id="518c1-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="518c1-450">1111111111</span></span>
- <span data-ttu-id="518c1-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="518c1-451">2222222222</span></span>
- <span data-ttu-id="518c1-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="518c1-452">3333333333</span></span>
- <span data-ttu-id="518c1-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="518c1-453">4444444444</span></span>
- <span data-ttu-id="518c1-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="518c1-454">5555555555</span></span>
- <span data-ttu-id="518c1-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="518c1-455">6666666666</span></span>
- <span data-ttu-id="518c1-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="518c1-456">7777777777</span></span>
- <span data-ttu-id="518c1-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="518c1-457">8888888888</span></span>
- <span data-ttu-id="518c1-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="518c1-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="518c1-459">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="518c1-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-460">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-460">Format</span></span>

<span data-ttu-id="518c1-461">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="518c1-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-462">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-462">Pattern</span></span>

<span data-ttu-id="518c1-463">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="518c1-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="518c1-464">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="518c1-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="518c1-465">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-465">A hyphen</span></span> 
- <span data-ttu-id="518c1-466">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="518c1-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="518c1-467">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-467">A period</span></span> 
- <span data-ttu-id="518c1-468">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-469">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-469">Checksum</span></span>

<span data-ttu-id="518c1-470">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-471">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-471">Definition</span></span>

<span data-ttu-id="518c1-472">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-473">関数 Func_belgium_national_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-474">Keyword_belgium_national_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="518c1-475">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-476">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="518c1-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="518c1-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="518c1-478">Identity</span><span class="sxs-lookup"><span data-stu-id="518c1-478">Identity</span></span>
- <span data-ttu-id="518c1-479">Registration</span><span class="sxs-lookup"><span data-stu-id="518c1-479">Registration</span></span>
- <span data-ttu-id="518c1-480">Identification</span><span class="sxs-lookup"><span data-stu-id="518c1-480">Identification</span></span> 
- <span data-ttu-id="518c1-481">ID</span><span class="sxs-lookup"><span data-stu-id="518c1-481">ID</span></span> 
- <span data-ttu-id="518c1-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="518c1-482">Identiteitskaart</span></span>
- <span data-ttu-id="518c1-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="518c1-483">Registratie nummer</span></span> 
- <span data-ttu-id="518c1-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-484">Identificatie nummer</span></span> 
- <span data-ttu-id="518c1-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="518c1-485">Identiteit</span></span>
- <span data-ttu-id="518c1-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="518c1-486">Registratie</span></span>
- <span data-ttu-id="518c1-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="518c1-487">Identificatie</span></span> 
- <span data-ttu-id="518c1-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="518c1-488">Carte d’identité</span></span> 
- <span data-ttu-id="518c1-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="518c1-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="518c1-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="518c1-490">numéro d'identification</span></span>
- <span data-ttu-id="518c1-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="518c1-491">identité</span></span> 
- <span data-ttu-id="518c1-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="518c1-492">inscription</span></span> 
- <span data-ttu-id="518c1-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="518c1-493">Identifikation</span></span>
- <span data-ttu-id="518c1-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="518c1-494">Identifizierung</span></span>
- <span data-ttu-id="518c1-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-495">Identifikationsnummer</span></span>
- <span data-ttu-id="518c1-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="518c1-496">Personalausweis</span></span>
- <span data-ttu-id="518c1-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="518c1-497">Registrierung</span></span>
- <span data-ttu-id="518c1-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="518c1-499">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-500">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-500">Format</span></span>

<span data-ttu-id="518c1-501">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-502">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-502">Pattern</span></span>

<span data-ttu-id="518c1-503">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-503">Formatted:</span></span>
- <span data-ttu-id="518c1-504">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-504">Three digits</span></span> 
- <span data-ttu-id="518c1-505">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-505">A period</span></span> 
- <span data-ttu-id="518c1-506">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-506">Three digits</span></span> 
- <span data-ttu-id="518c1-507">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-507">A period</span></span> 
- <span data-ttu-id="518c1-508">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-508">Three digits</span></span> 
- <span data-ttu-id="518c1-509">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-509">A hyphen</span></span> 
- <span data-ttu-id="518c1-510">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-510">Two digits which are check digits</span></span>

<span data-ttu-id="518c1-511">書式設定なし:</span><span class="sxs-lookup"><span data-stu-id="518c1-511">Unformatted:</span></span>
- <span data-ttu-id="518c1-512">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="518c1-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-513">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-513">Checksum</span></span>

<span data-ttu-id="518c1-514">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-515">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-515">Definition</span></span>

<span data-ttu-id="518c1-516">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-517">関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-518">Keyword_brazil_cpf のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="518c1-519">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-519">The checksum passes.</span></span>

<span data-ttu-id="518c1-520">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-521">関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-522">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-523">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="518c1-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="518c1-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="518c1-525">CPF</span><span class="sxs-lookup"><span data-stu-id="518c1-525">CPF</span></span>
- <span data-ttu-id="518c1-526">Identification</span><span class="sxs-lookup"><span data-stu-id="518c1-526">Identification</span></span>
- <span data-ttu-id="518c1-527">Registration</span><span class="sxs-lookup"><span data-stu-id="518c1-527">Registration</span></span>
- <span data-ttu-id="518c1-528">Revenue</span><span class="sxs-lookup"><span data-stu-id="518c1-528">Revenue</span></span>
- <span data-ttu-id="518c1-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="518c1-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="518c1-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="518c1-530">Imposto</span></span> 
- <span data-ttu-id="518c1-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="518c1-531">Identificação</span></span> 
- <span data-ttu-id="518c1-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="518c1-532">Inscrição</span></span> 
- <span data-ttu-id="518c1-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="518c1-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="518c1-534">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="518c1-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-535">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-535">Format</span></span>

<span data-ttu-id="518c1-536">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-537">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-537">Pattern</span></span>
<span data-ttu-id="518c1-538">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="518c1-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="518c1-539">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-539">Two digits</span></span> 
- <span data-ttu-id="518c1-540">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-540">A period</span></span> 
- <span data-ttu-id="518c1-541">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-541">Three digits</span></span> 
- <span data-ttu-id="518c1-542">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-542">A period</span></span> 
- <span data-ttu-id="518c1-543">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="518c1-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="518c1-544">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-544">A forward slash</span></span> 
- <span data-ttu-id="518c1-545">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="518c1-545">Four-digit branch number</span></span> 
- <span data-ttu-id="518c1-546">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-546">A hyphen</span></span> 
- <span data-ttu-id="518c1-547">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-548">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-548">Checksum</span></span>

<span data-ttu-id="518c1-549">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-550">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-550">Definition</span></span>

<span data-ttu-id="518c1-551">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-552">関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-553">Keyword_brazil_cnpj のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="518c1-554">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-554">The checksum passes.</span></span>

<span data-ttu-id="518c1-555">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-556">関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-557">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-558">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="518c1-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="518c1-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="518c1-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="518c1-560">CNPJ</span></span> 
- <span data-ttu-id="518c1-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="518c1-561">CNPJ/MF</span></span> 
- <span data-ttu-id="518c1-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="518c1-562">CNPJ-MF</span></span> 
- <span data-ttu-id="518c1-563">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="518c1-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="518c1-564">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="518c1-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="518c1-565">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="518c1-565">Legal entity</span></span> 
- <span data-ttu-id="518c1-566">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="518c1-566">Legal entities</span></span> 
- <span data-ttu-id="518c1-567">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="518c1-567">Registration Status</span></span> 
- <span data-ttu-id="518c1-568">Business
</span><span class="sxs-lookup"><span data-stu-id="518c1-568">Business</span></span> 
- <span data-ttu-id="518c1-569">Company</span><span class="sxs-lookup"><span data-stu-id="518c1-569">Company</span></span>
- <span data-ttu-id="518c1-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="518c1-570">CNPJ</span></span> 
- <span data-ttu-id="518c1-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="518c1-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="518c1-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="518c1-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="518c1-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="518c1-573">CGC</span></span> 
- <span data-ttu-id="518c1-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="518c1-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="518c1-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="518c1-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="518c1-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="518c1-576">Situação cadastral</span></span> 
- <span data-ttu-id="518c1-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="518c1-577">Inscrição</span></span> 
- <span data-ttu-id="518c1-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="518c1-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="518c1-579">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="518c1-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-580">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-580">Format</span></span>

<span data-ttu-id="518c1-581">Registro Geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="518c1-582">Registro de Identidade (RIC) (新しい形式): 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-583">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-583">Pattern</span></span>

<span data-ttu-id="518c1-584">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="518c1-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="518c1-585">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-585">Two digits</span></span> 
- <span data-ttu-id="518c1-586">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-586">A period</span></span> 
- <span data-ttu-id="518c1-587">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-587">Three digits</span></span> 
- <span data-ttu-id="518c1-588">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-588">A period</span></span> 
- <span data-ttu-id="518c1-589">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-589">Three digits</span></span> 
- <span data-ttu-id="518c1-590">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-590">A hyphen</span></span> 
- <span data-ttu-id="518c1-591">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-591">One digit which is a check digit</span></span>

<span data-ttu-id="518c1-592">Registro de Identidade (RIC) (新しい形式)。</span><span class="sxs-lookup"><span data-stu-id="518c1-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="518c1-593">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-593">10 digits</span></span> 
- <span data-ttu-id="518c1-594">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-594">A hyphen</span></span> 
- <span data-ttu-id="518c1-595">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-596">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-596">Checksum</span></span>

<span data-ttu-id="518c1-597">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-598">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-598">Definition</span></span>

<span data-ttu-id="518c1-599">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-600">関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-601">Keyword_brazil_rg のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="518c1-602">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-602">The checksum passes.</span></span>

<span data-ttu-id="518c1-603">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-604">関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-605">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-606">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="518c1-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="518c1-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="518c1-608">Cédula de identidade 身分証明書国民 id número de rregistro registro de Iidentidade registro geral (このキーワードでは大文字小文字を区別) RG (このキーワードでは大文字小文字を区別) RIC</span><span class="sxs-lookup"><span data-stu-id="518c1-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="518c1-609">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-610">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-610">Format</span></span>

<span data-ttu-id="518c1-611">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-612">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-612">Pattern</span></span>

<span data-ttu-id="518c1-613">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="518c1-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="518c1-614">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="518c1-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="518c1-615">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-615">Five digits</span></span> 
- <span data-ttu-id="518c1-616">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-616">A hyphen</span></span> 
- <span data-ttu-id="518c1-617">3 桁の数字または</span><span class="sxs-lookup"><span data-stu-id="518c1-617">Three digits OR</span></span>
- <span data-ttu-id="518c1-618">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="518c1-618">A zero "0"</span></span> 
- <span data-ttu-id="518c1-619">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-620">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-620">Checksum</span></span>

<span data-ttu-id="518c1-621">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-622">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-622">Definition</span></span>

<span data-ttu-id="518c1-623">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-624">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-625">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="518c1-626">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="518c1-627">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-628">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-629">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-630">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="518c1-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="518c1-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="518c1-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="518c1-632">canada savings bonds</span></span>
- <span data-ttu-id="518c1-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="518c1-633">canada revenue agency</span></span>
- <span data-ttu-id="518c1-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="518c1-634">canadian financial institution</span></span>
- <span data-ttu-id="518c1-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="518c1-635">direct deposit form</span></span>
- <span data-ttu-id="518c1-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="518c1-636">canadian citizen</span></span>
- <span data-ttu-id="518c1-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="518c1-637">legal representative</span></span>
- <span data-ttu-id="518c1-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="518c1-638">notary public</span></span>
- <span data-ttu-id="518c1-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="518c1-639">commissioner for oaths</span></span>
- <span data-ttu-id="518c1-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="518c1-640">child care benefit</span></span>
- <span data-ttu-id="518c1-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="518c1-641">universal child care</span></span>
- <span data-ttu-id="518c1-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="518c1-642">canada child tax benefit</span></span>
- <span data-ttu-id="518c1-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="518c1-643">income tax benefit</span></span>
- <span data-ttu-id="518c1-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="518c1-644">harmonized sales tax</span></span>
- <span data-ttu-id="518c1-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="518c1-645">social insurance number</span></span>
- <span data-ttu-id="518c1-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="518c1-646">income tax refund</span></span>
- <span data-ttu-id="518c1-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="518c1-647">child tax benefit</span></span>
- <span data-ttu-id="518c1-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="518c1-648">territorial payments</span></span>
- <span data-ttu-id="518c1-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="518c1-649">institution number</span></span>
- <span data-ttu-id="518c1-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="518c1-650">deposit request</span></span>
- <span data-ttu-id="518c1-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="518c1-651">banking information</span></span>
- <span data-ttu-id="518c1-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="518c1-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="518c1-653">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-654">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-654">Format</span></span>

<span data-ttu-id="518c1-655">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="518c1-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-656">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-656">Pattern</span></span>

<span data-ttu-id="518c1-657">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-658">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-658">Checksum</span></span>

<span data-ttu-id="518c1-659">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-660">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-660">Definition</span></span>

<span data-ttu-id="518c1-661">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-662">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-663">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="518c1-664">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-665">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="518c1-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="518c1-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="518c1-667">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="518c1-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="518c1-668">
州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="518c1-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="518c1-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="518c1-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="518c1-670">DL</span><span class="sxs-lookup"><span data-stu-id="518c1-670">DL</span></span>
- <span data-ttu-id="518c1-671">DLS</span><span class="sxs-lookup"><span data-stu-id="518c1-671">DLS</span></span>
- <span data-ttu-id="518c1-672">CDL</span><span class="sxs-lookup"><span data-stu-id="518c1-672">CDL</span></span>
- <span data-ttu-id="518c1-673">CDL</span><span class="sxs-lookup"><span data-stu-id="518c1-673">CDLS</span></span>
- <span data-ttu-id="518c1-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="518c1-674">DriverLic</span></span>
- <span data-ttu-id="518c1-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="518c1-675">DriverLics</span></span>
- <span data-ttu-id="518c1-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="518c1-676">DriverLicense</span></span>
- <span data-ttu-id="518c1-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-677">DriverLicenses</span></span>
- <span data-ttu-id="518c1-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="518c1-678">DriverLicence</span></span>
- <span data-ttu-id="518c1-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="518c1-679">DriverLicences</span></span>
- <span data-ttu-id="518c1-680">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-680">Driver Lic</span></span>
- <span data-ttu-id="518c1-681">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-681">Driver Lics</span></span>
- <span data-ttu-id="518c1-682">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-682">Driver License</span></span>
- <span data-ttu-id="518c1-683">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-683">Driver Licenses</span></span>
- <span data-ttu-id="518c1-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-684">Driver Licence</span></span>
- <span data-ttu-id="518c1-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-685">Driver Licences</span></span>
- <span data-ttu-id="518c1-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="518c1-686">DriversLic</span></span>
- <span data-ttu-id="518c1-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="518c1-687">DriversLics</span></span>
- <span data-ttu-id="518c1-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="518c1-688">DriversLicence</span></span>
- <span data-ttu-id="518c1-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="518c1-689">DriversLicences</span></span>
- <span data-ttu-id="518c1-690">証</span><span class="sxs-lookup"><span data-stu-id="518c1-690">DriversLicense</span></span>
- <span data-ttu-id="518c1-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-691">DriversLicenses</span></span>
- <span data-ttu-id="518c1-692">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-692">Drivers Lic</span></span>
- <span data-ttu-id="518c1-693">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-693">Drivers Lics</span></span>
- <span data-ttu-id="518c1-694">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-694">Drivers License</span></span>
- <span data-ttu-id="518c1-695">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-695">Drivers Licenses</span></span>
- <span data-ttu-id="518c1-696">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-696">Drivers Licence</span></span>
- <span data-ttu-id="518c1-697">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-697">Drivers Licences</span></span>
- <span data-ttu-id="518c1-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-698">Driver'Lic</span></span>
- <span data-ttu-id="518c1-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-699">Driver'Lics</span></span>
- <span data-ttu-id="518c1-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="518c1-700">Driver'License</span></span>
- <span data-ttu-id="518c1-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="518c1-701">Driver'Licenses</span></span>
- <span data-ttu-id="518c1-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="518c1-702">Driver'Licence</span></span>
- <span data-ttu-id="518c1-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="518c1-703">Driver'Licences</span></span>
- <span data-ttu-id="518c1-704">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-704">Driver' Lic</span></span>
- <span data-ttu-id="518c1-705">ドライバー ' Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-705">Driver' Lics</span></span>
- <span data-ttu-id="518c1-706">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-706">Driver' License</span></span>
- <span data-ttu-id="518c1-707">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-707">Driver' Licenses</span></span>
- <span data-ttu-id="518c1-708">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-708">Driver' Licence</span></span>
- <span data-ttu-id="518c1-709">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-709">Driver' Licences</span></span>
- <span data-ttu-id="518c1-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="518c1-710">Driver'sLic</span></span>
- <span data-ttu-id="518c1-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="518c1-711">Driver'sLics</span></span>
- <span data-ttu-id="518c1-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="518c1-712">Driver'sLicense</span></span>
- <span data-ttu-id="518c1-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-713">Driver'sLicenses</span></span>
- <span data-ttu-id="518c1-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="518c1-714">Driver'sLicence</span></span>
- <span data-ttu-id="518c1-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="518c1-715">Driver'sLicences</span></span>
- <span data-ttu-id="518c1-716">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-716">Driver's Lic</span></span>
- <span data-ttu-id="518c1-717">ドライバーの Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-717">Driver's Lics</span></span>
- <span data-ttu-id="518c1-718">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-718">Driver's License</span></span>
- <span data-ttu-id="518c1-719">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-719">Driver's Licenses</span></span>
- <span data-ttu-id="518c1-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-720">Driver's Licence</span></span>
- <span data-ttu-id="518c1-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-721">Driver's Licences</span></span>
- <span data-ttu-id="518c1-722">Permis デ Conduire</span><span class="sxs-lookup"><span data-stu-id="518c1-722">Permis de Conduire</span></span>
- <span data-ttu-id="518c1-723">id</span><span class="sxs-lookup"><span data-stu-id="518c1-723">id</span></span>
- <span data-ttu-id="518c1-724">id</span><span class="sxs-lookup"><span data-stu-id="518c1-724">ids</span></span>
- <span data-ttu-id="518c1-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="518c1-725">idcard number</span></span>
- <span data-ttu-id="518c1-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="518c1-726">idcard numbers</span></span>
- <span data-ttu-id="518c1-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="518c1-727">idcard #</span></span>
- <span data-ttu-id="518c1-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="518c1-728">idcard #s</span></span>
- <span data-ttu-id="518c1-729">idcard カード</span><span class="sxs-lookup"><span data-stu-id="518c1-729">idcard card</span></span>
- <span data-ttu-id="518c1-730">idcard カード</span><span class="sxs-lookup"><span data-stu-id="518c1-730">idcard cards</span></span>
- <span data-ttu-id="518c1-731">idcard</span><span class="sxs-lookup"><span data-stu-id="518c1-731">idcard</span></span>
- <span data-ttu-id="518c1-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="518c1-732">identification number</span></span>
- <span data-ttu-id="518c1-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-733">identification numbers</span></span>
- <span data-ttu-id="518c1-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="518c1-734">identification #</span></span>
- <span data-ttu-id="518c1-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="518c1-735">identification #s</span></span>
- <span data-ttu-id="518c1-736">id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-736">identification card</span></span>
- <span data-ttu-id="518c1-737">id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-737">identification cards</span></span>
- <span data-ttu-id="518c1-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="518c1-738">identification</span></span> 
- <span data-ttu-id="518c1-739">DL#</span><span class="sxs-lookup"><span data-stu-id="518c1-739">DL#</span></span>
- <span data-ttu-id="518c1-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="518c1-740">DLS#</span></span> 
- <span data-ttu-id="518c1-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="518c1-741">CDL#</span></span> 
- <span data-ttu-id="518c1-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="518c1-742">CDLS#</span></span> 
- <span data-ttu-id="518c1-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-743">DriverLic#</span></span> 
- <span data-ttu-id="518c1-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-744">DriverLics#</span></span> 
- <span data-ttu-id="518c1-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="518c1-745">DriverLicense#</span></span> 
- <span data-ttu-id="518c1-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-746">DriverLicenses#</span></span> 
- <span data-ttu-id="518c1-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="518c1-747">DriverLicence#</span></span> 
- <span data-ttu-id="518c1-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="518c1-748">DriverLicences#</span></span> 
- <span data-ttu-id="518c1-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="518c1-749">Driver Lic#</span></span>
- <span data-ttu-id="518c1-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-750">Driver Lics#</span></span> 
- <span data-ttu-id="518c1-751">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-751">Driver License#</span></span> 
- <span data-ttu-id="518c1-752">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-752">Driver Licenses#</span></span> 
- <span data-ttu-id="518c1-753">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-753">Driver License#</span></span> 
- <span data-ttu-id="518c1-754">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-754">Driver Licences#</span></span> 
- <span data-ttu-id="518c1-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-755">DriversLic#</span></span> 
- <span data-ttu-id="518c1-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-756">DriversLics#</span></span> 
- <span data-ttu-id="518c1-757">証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-757">DriversLicense#</span></span> 
- <span data-ttu-id="518c1-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-758">DriversLicenses#</span></span> 
- <span data-ttu-id="518c1-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="518c1-759">DriversLicence#</span></span> 
- <span data-ttu-id="518c1-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="518c1-760">DriversLicences#</span></span> 
- <span data-ttu-id="518c1-761">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="518c1-761">Drivers Lic#</span></span> 
- <span data-ttu-id="518c1-762">ドライバー Lics #</span><span class="sxs-lookup"><span data-stu-id="518c1-762">Drivers Lics#</span></span> 
- <span data-ttu-id="518c1-763">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-763">Drivers License#</span></span> 
- <span data-ttu-id="518c1-764">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="518c1-765">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-765">Drivers Licence#</span></span> 
- <span data-ttu-id="518c1-766">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-766">Drivers Licences#</span></span> 
- <span data-ttu-id="518c1-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-767">Driver'Lic#</span></span> 
- <span data-ttu-id="518c1-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-768">Driver'Lics#</span></span> 
- <span data-ttu-id="518c1-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-769">Driver'License#</span></span> 
- <span data-ttu-id="518c1-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="518c1-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="518c1-771">Driver'Licence#</span></span> 
- <span data-ttu-id="518c1-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="518c1-772">Driver'Licences#</span></span> 
- <span data-ttu-id="518c1-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-773">Driver' Lic#</span></span> 
- <span data-ttu-id="518c1-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-774">Driver' Lics#</span></span> 
- <span data-ttu-id="518c1-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-775">Driver' License#</span></span> 
- <span data-ttu-id="518c1-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="518c1-777">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-777">Driver' Licence#</span></span> 
- <span data-ttu-id="518c1-778">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-778">Driver' Licences#</span></span> 
- <span data-ttu-id="518c1-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-779">Driver'sLic#</span></span> 
- <span data-ttu-id="518c1-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-780">Driver'sLics#</span></span> 
- <span data-ttu-id="518c1-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="518c1-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="518c1-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="518c1-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="518c1-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="518c1-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="518c1-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="518c1-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-785">Driver's Lic#</span></span> 
- <span data-ttu-id="518c1-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-786">Driver's Lics#</span></span> 
- <span data-ttu-id="518c1-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-787">Driver's License#</span></span> 
- <span data-ttu-id="518c1-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="518c1-789">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-789">Driver's Licence#</span></span> 
- <span data-ttu-id="518c1-790">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-790">Driver's Licences#</span></span> 
- <span data-ttu-id="518c1-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="518c1-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="518c1-792">id 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-792">id#</span></span> 
- <span data-ttu-id="518c1-793">id #</span><span class="sxs-lookup"><span data-stu-id="518c1-793">ids#</span></span> 
- <span data-ttu-id="518c1-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="518c1-794">idcard card#</span></span> 
- <span data-ttu-id="518c1-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="518c1-795">idcard cards#</span></span> 
- <span data-ttu-id="518c1-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="518c1-796">idcard#</span></span> 
- <span data-ttu-id="518c1-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="518c1-797">identification card#</span></span> 
- <span data-ttu-id="518c1-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="518c1-798">identification cards#</span></span> 
- <span data-ttu-id="518c1-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="518c1-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="518c1-800">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="518c1-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-801">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-801">Format</span></span>

<span data-ttu-id="518c1-802">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-803">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-803">Pattern</span></span>

<span data-ttu-id="518c1-804">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-805">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-805">Checksum</span></span>

<span data-ttu-id="518c1-806">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-807">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-807">Definition</span></span>

<span data-ttu-id="518c1-808">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-809">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-810">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-811">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="518c1-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="518c1-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="518c1-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="518c1-813">personal health number</span></span>
- <span data-ttu-id="518c1-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="518c1-814">patient information</span></span>
- <span data-ttu-id="518c1-815">正常性サービス</span><span class="sxs-lookup"><span data-stu-id="518c1-815">health services</span></span>
- <span data-ttu-id="518c1-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="518c1-816">speciality services</span></span>
- <span data-ttu-id="518c1-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="518c1-817">automobile accident</span></span>
- <span data-ttu-id="518c1-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="518c1-818">patient hospital</span></span>
- <span data-ttu-id="518c1-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="518c1-819">psychiatrist</span></span>
- <span data-ttu-id="518c1-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="518c1-820">workers compensation</span></span>
- <span data-ttu-id="518c1-821">
disability</span><span class="sxs-lookup"><span data-stu-id="518c1-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="518c1-822">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-823">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-823">Format</span></span>

<span data-ttu-id="518c1-824">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-825">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-825">Pattern</span></span>

<span data-ttu-id="518c1-826">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-827">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-827">Checksum</span></span>

<span data-ttu-id="518c1-828">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-829">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-829">Definition</span></span>

<span data-ttu-id="518c1-830">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-831">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-832">Keyword_canada_passport_number または Keyword_passport からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="518c1-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-833">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="518c1-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="518c1-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="518c1-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="518c1-835">canadian citizenship</span></span>
- <span data-ttu-id="518c1-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="518c1-836">canadian passport</span></span>
- <span data-ttu-id="518c1-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="518c1-837">passport application</span></span>
- <span data-ttu-id="518c1-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="518c1-838">passport photos</span></span>
- <span data-ttu-id="518c1-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="518c1-839">certified translator</span></span>
- <span data-ttu-id="518c1-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="518c1-840">canadian citizens</span></span>
- <span data-ttu-id="518c1-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="518c1-841">processing times</span></span>
- <span data-ttu-id="518c1-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="518c1-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="518c1-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-843">Keyword_passport</span></span>

- <span data-ttu-id="518c1-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="518c1-844">Passport Number</span></span>
- <span data-ttu-id="518c1-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="518c1-845">Passport No</span></span>
- <span data-ttu-id="518c1-846">Passport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-846">Passport #</span></span>
- <span data-ttu-id="518c1-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-847">Passport#</span></span>
- <span data-ttu-id="518c1-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="518c1-848">PassportID</span></span>
- <span data-ttu-id="518c1-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="518c1-849">Passportno</span></span>
- <span data-ttu-id="518c1-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-850">passportnumber</span></span>
- <span data-ttu-id="518c1-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="518c1-851">パスポート</span></span>
- <span data-ttu-id="518c1-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-852">パスポート番号</span></span>
- <span data-ttu-id="518c1-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="518c1-853">パスポートのNum</span></span>
- <span data-ttu-id="518c1-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-854">パスポート＃</span></span>
- <span data-ttu-id="518c1-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="518c1-855">Numéro de passeport</span></span>
- <span data-ttu-id="518c1-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="518c1-856">Passeport n °</span></span>
- <span data-ttu-id="518c1-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="518c1-857">Passeport Non</span></span>
- <span data-ttu-id="518c1-858">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-858">Passeport #</span></span>
- <span data-ttu-id="518c1-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-859">Passeport#</span></span>
- <span data-ttu-id="518c1-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="518c1-860">PasseportNon</span></span>
- <span data-ttu-id="518c1-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="518c1-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="518c1-862">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="518c1-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-863">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-863">Format</span></span>

<span data-ttu-id="518c1-864">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-865">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-865">Pattern</span></span>

<span data-ttu-id="518c1-866">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-867">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-867">Checksum</span></span>

<span data-ttu-id="518c1-868">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-869">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-869">Definition</span></span>

<span data-ttu-id="518c1-p104">DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Regex_canada_phin の正規表現パターンに一致するコンテンツを検索します。Keyword_canada_phin または Keyword_canada_provinces からの 2 つ以上のキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="518c1-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-872">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="518c1-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="518c1-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="518c1-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="518c1-874">social insurance number</span></span>
- <span data-ttu-id="518c1-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="518c1-875">health information act</span></span>
- <span data-ttu-id="518c1-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="518c1-876">income tax information</span></span>
- <span data-ttu-id="518c1-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="518c1-877">manitoba health</span></span>
- <span data-ttu-id="518c1-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="518c1-878">health registration</span></span>
- <span data-ttu-id="518c1-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="518c1-879">prescription purchases</span></span>
- <span data-ttu-id="518c1-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="518c1-880">benefit eligibility</span></span>
- <span data-ttu-id="518c1-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="518c1-881">personal health</span></span>
- <span data-ttu-id="518c1-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="518c1-882">power of attorney</span></span>
- <span data-ttu-id="518c1-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="518c1-883">registration number</span></span>
- <span data-ttu-id="518c1-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="518c1-884">personal health number</span></span>
- <span data-ttu-id="518c1-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="518c1-885">practitioner referral</span></span>
- <span data-ttu-id="518c1-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="518c1-886">wellness professional</span></span>
- <span data-ttu-id="518c1-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="518c1-887">patient referral</span></span>
- <span data-ttu-id="518c1-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="518c1-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="518c1-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="518c1-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="518c1-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="518c1-890">Nunavut</span></span>
- <span data-ttu-id="518c1-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="518c1-891">Quebec</span></span>
- <span data-ttu-id="518c1-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="518c1-892">Northwest Territories</span></span>
- <span data-ttu-id="518c1-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="518c1-893">Ontario</span></span>
- <span data-ttu-id="518c1-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="518c1-894">British Columbia</span></span>
- <span data-ttu-id="518c1-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="518c1-895">Alberta</span></span>
- <span data-ttu-id="518c1-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="518c1-896">Saskatchewan</span></span>
- <span data-ttu-id="518c1-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="518c1-897">Manitoba</span></span>
- <span data-ttu-id="518c1-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="518c1-898">Yukon</span></span>
- <span data-ttu-id="518c1-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="518c1-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="518c1-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="518c1-900">New Brunswick</span></span>
- <span data-ttu-id="518c1-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="518c1-901">Nova Scotia</span></span>
- <span data-ttu-id="518c1-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="518c1-902">Prince Edward Island</span></span>
- <span data-ttu-id="518c1-903">カナダ</span><span class="sxs-lookup"><span data-stu-id="518c1-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="518c1-904">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="518c1-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-905">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-905">Format</span></span>

<span data-ttu-id="518c1-906">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="518c1-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-907">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-907">Pattern</span></span>

<span data-ttu-id="518c1-908">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-908">Formatted:</span></span>
- <span data-ttu-id="518c1-909">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-909">Three digits</span></span> 
- <span data-ttu-id="518c1-910">ハイフンまたはスペース 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-910">A hyphen or space</span></span> 
- <span data-ttu-id="518c1-911">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-911">Three digits</span></span> 
- <span data-ttu-id="518c1-912">ハイフンまたはスペース 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-912">A hyphen or space</span></span> 
- <span data-ttu-id="518c1-913">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-913">Three digits</span></span>

<span data-ttu-id="518c1-914">9 桁のフォーマットされていません。</span><span class="sxs-lookup"><span data-stu-id="518c1-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-915">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-915">Checksum</span></span>

<span data-ttu-id="518c1-916">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-917">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-917">Definition</span></span>

<span data-ttu-id="518c1-918">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-919">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-920">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="518c1-921">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="518c1-922">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="518c1-923">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="518c1-924">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-924">The checksum passes.</span></span>

<span data-ttu-id="518c1-925">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-926">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-927">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="518c1-928">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-929">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="518c1-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="518c1-930">Keyword_sin</span></span>

- <span data-ttu-id="518c1-931">sin</span><span class="sxs-lookup"><span data-stu-id="518c1-931">sin</span></span> 
- <span data-ttu-id="518c1-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="518c1-932">social insurance</span></span> 
- <span data-ttu-id="518c1-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="518c1-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="518c1-934">sins
</span><span class="sxs-lookup"><span data-stu-id="518c1-934">sins</span></span> 
- <span data-ttu-id="518c1-935">ssn</span><span class="sxs-lookup"><span data-stu-id="518c1-935">ssn</span></span> 
- <span data-ttu-id="518c1-936">ssn</span><span class="sxs-lookup"><span data-stu-id="518c1-936">ssns</span></span> 
- <span data-ttu-id="518c1-937">社会保障</span><span class="sxs-lookup"><span data-stu-id="518c1-937">social security</span></span> 
- <span data-ttu-id="518c1-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="518c1-938">numero d'assurance social</span></span> 
- <span data-ttu-id="518c1-939">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="518c1-939">national identification number</span></span> 
- <span data-ttu-id="518c1-940">
national id</span><span class="sxs-lookup"><span data-stu-id="518c1-940">national id</span></span> 
- <span data-ttu-id="518c1-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="518c1-941">sin#</span></span> 
- <span data-ttu-id="518c1-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="518c1-942">soc ins</span></span> 
- <span data-ttu-id="518c1-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="518c1-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="518c1-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="518c1-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="518c1-945">driver's license</span><span class="sxs-lookup"><span data-stu-id="518c1-945">driver's license</span></span> 
- <span data-ttu-id="518c1-946">drivers license</span><span class="sxs-lookup"><span data-stu-id="518c1-946">drivers license</span></span> 
- <span data-ttu-id="518c1-947">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-947">driver's licence</span></span> 
- <span data-ttu-id="518c1-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="518c1-948">drivers licence</span></span> 
- <span data-ttu-id="518c1-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="518c1-949">DOB</span></span> 
- <span data-ttu-id="518c1-950">誕生日</span><span class="sxs-lookup"><span data-stu-id="518c1-950">Birthdate</span></span> 
- <span data-ttu-id="518c1-951">誕生日 </span><span class="sxs-lookup"><span data-stu-id="518c1-951">Birthday</span></span> 
- <span data-ttu-id="518c1-952">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="518c1-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="518c1-953">チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="518c1-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-954">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-954">Format</span></span>

<span data-ttu-id="518c1-955">7-8 桁の数字と区切り文字チェックの数字または文字</span><span class="sxs-lookup"><span data-stu-id="518c1-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-956">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-956">Pattern</span></span>

<span data-ttu-id="518c1-957">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="518c1-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="518c1-958">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-958">1-2 digits</span></span> 
- <span data-ttu-id="518c1-959">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-959">A period</span></span> 
- <span data-ttu-id="518c1-960">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-960">Three digits</span></span> 
- <span data-ttu-id="518c1-961">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-961">A period</span></span> 
- <span data-ttu-id="518c1-962">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-962">Three digits</span></span> 
- <span data-ttu-id="518c1-963">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-963">A dash</span></span> 
- <span data-ttu-id="518c1-964">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="518c1-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-965">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-965">Checksum</span></span>

<span data-ttu-id="518c1-966">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-967">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-967">Definition</span></span>

<span data-ttu-id="518c1-968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-969">関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-970">Keyword_chile_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="518c1-971">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-971">The checksum passes.</span></span>

<span data-ttu-id="518c1-972">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-973">関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-974">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-975">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="518c1-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="518c1-977">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-977">National Identification Number</span></span> 
- <span data-ttu-id="518c1-978">Identity card</span><span class="sxs-lookup"><span data-stu-id="518c1-978">Identity card</span></span> 
- <span data-ttu-id="518c1-979">ID</span><span class="sxs-lookup"><span data-stu-id="518c1-979">ID</span></span> 
- <span data-ttu-id="518c1-980">Identification</span><span class="sxs-lookup"><span data-stu-id="518c1-980">Identification</span></span> 
- <span data-ttu-id="518c1-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="518c1-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="518c1-982">実行</span><span class="sxs-lookup"><span data-stu-id="518c1-982">RUN</span></span> 
- <span data-ttu-id="518c1-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="518c1-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="518c1-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="518c1-984">RUT</span></span> 
- <span data-ttu-id="518c1-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="518c1-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="518c1-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="518c1-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="518c1-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="518c1-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="518c1-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="518c1-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="518c1-989">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-990">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-990">Format</span></span>

<span data-ttu-id="518c1-991">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-992">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-992">Pattern</span></span>

<span data-ttu-id="518c1-993">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-993">18 digits:</span></span>
- <span data-ttu-id="518c1-994">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="518c1-995">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="518c1-996">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="518c1-997">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-998">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-998">Checksum</span></span>

<span data-ttu-id="518c1-999">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1000">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1000">Definition</span></span>

<span data-ttu-id="518c1-1001">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1002">関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1003">Keyword_china_resident_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="518c1-1004">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1004">The checksum passes.</span></span>

<span data-ttu-id="518c1-1005">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1006">関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1007">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1008">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="518c1-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="518c1-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="518c1-1010">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="518c1-1011">PRC
</span><span class="sxs-lookup"><span data-stu-id="518c1-1011">PRC</span></span> 
- <span data-ttu-id="518c1-1012">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1012">National Identification Card</span></span> 
- <span data-ttu-id="518c1-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="518c1-1013">身份证</span></span> 
- <span data-ttu-id="518c1-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="518c1-1014">居民 身份证</span></span> 
- <span data-ttu-id="518c1-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="518c1-1015">居民身份证</span></span> 
- <span data-ttu-id="518c1-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="518c1-1016">鉴定</span></span> 
- <span data-ttu-id="518c1-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="518c1-1017">身分證</span></span> 
- <span data-ttu-id="518c1-1018">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="518c1-1018">居民 身份證</span></span>
- <span data-ttu-id="518c1-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="518c1-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="518c1-1020">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1021">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1021">Format</span></span>

<span data-ttu-id="518c1-1022">16 桁の数字書式を設定することができますが、または書式設定されていない (dddddddddddddddd) と、Luhn のテストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="518c1-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1023">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1023">Pattern</span></span>

<span data-ttu-id="518c1-1024">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="518c1-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1025">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1025">Checksum</span></span>

<span data-ttu-id="518c1-1026">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="518c1-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1027">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1027">Definition</span></span>

<span data-ttu-id="518c1-1028">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1029">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1030">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-1030">One of the following is true:</span></span>
    - <span data-ttu-id="518c1-1031">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="518c1-1032">Keyword_cc_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="518c1-1033">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="518c1-1034">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1034">The checksum passes.</span></span>

<span data-ttu-id="518c1-1035">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1036">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1037">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1038">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="518c1-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="518c1-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="518c1-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="518c1-1040">card verification</span></span>
- <span data-ttu-id="518c1-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="518c1-1041">card identification number</span></span>
- <span data-ttu-id="518c1-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="518c1-1042">cvn</span></span>
- <span data-ttu-id="518c1-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="518c1-1043">cid</span></span>
- <span data-ttu-id="518c1-1044">cvc2</span><span class="sxs-lookup"><span data-stu-id="518c1-1044">cvc2</span></span>
- <span data-ttu-id="518c1-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="518c1-1045">cvv2</span></span>
- <span data-ttu-id="518c1-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="518c1-1046">pin block</span></span>
- <span data-ttu-id="518c1-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="518c1-1047">security code</span></span>
- <span data-ttu-id="518c1-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1048">security number</span></span>
- <span data-ttu-id="518c1-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1049">security no</span></span>
- <span data-ttu-id="518c1-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1050">issue number</span></span>
- <span data-ttu-id="518c1-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1051">issue no</span></span>
- <span data-ttu-id="518c1-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="518c1-1052">cryptogramme</span></span>
- <span data-ttu-id="518c1-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="518c1-1053">numéro de sécurité</span></span>
- <span data-ttu-id="518c1-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="518c1-1054">numero de securite</span></span>
- <span data-ttu-id="518c1-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="518c1-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="518c1-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1057">prüfziffer</span></span>
- <span data-ttu-id="518c1-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1058">prufziffer</span></span>
- <span data-ttu-id="518c1-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="518c1-1059">sicherheits Kode</span></span>
- <span data-ttu-id="518c1-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="518c1-1060">sicherheitscode</span></span>
- <span data-ttu-id="518c1-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="518c1-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1062">verfalldatum</span></span>
- <span data-ttu-id="518c1-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="518c1-1063">codice di verifica</span></span>
- <span data-ttu-id="518c1-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="518c1-p105">cod. sicurezza</span></span>
- <span data-ttu-id="518c1-1066">代金引換払いの sicurezza</span><span class="sxs-lookup"><span data-stu-id="518c1-1066">cod sicurezza</span></span>
- <span data-ttu-id="518c1-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="518c1-1067">n autorizzazione</span></span>
- <span data-ttu-id="518c1-1068">código
</span><span class="sxs-lookup"><span data-stu-id="518c1-1068">código</span></span>
- <span data-ttu-id="518c1-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="518c1-1069">codigo</span></span>
- <span data-ttu-id="518c1-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="518c1-p106">cod. seg</span></span>
- <span data-ttu-id="518c1-1072">代金引換払い seg</span><span class="sxs-lookup"><span data-stu-id="518c1-1072">cod seg</span></span>
- <span data-ttu-id="518c1-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-1073">código de segurança</span></span>
- <span data-ttu-id="518c1-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-1074">codigo de seguranca</span></span>
- <span data-ttu-id="518c1-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-1075">codigo de segurança</span></span>
- <span data-ttu-id="518c1-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-1076">código de seguranca</span></span>
- <span data-ttu-id="518c1-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-p107">cód. segurança</span></span>
- <span data-ttu-id="518c1-p108">代金引換払いです。seguranca 代金引換払いです。segurança</span><span class="sxs-lookup"><span data-stu-id="518c1-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="518c1-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-p109">cód. seguranca</span></span>
- <span data-ttu-id="518c1-1084">cód segurança</span><span class="sxs-lookup"><span data-stu-id="518c1-1084">cód segurança</span></span>
- <span data-ttu-id="518c1-1085">代金引換払いの代金引換払い segurança の seguranca</span><span class="sxs-lookup"><span data-stu-id="518c1-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="518c1-1086">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="518c1-1086">cód seguranca</span></span>
- <span data-ttu-id="518c1-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="518c1-1087">número de verificação</span></span>
- <span data-ttu-id="518c1-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1088">numero de verificacao</span></span>
- <span data-ttu-id="518c1-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="518c1-1089">ablauf</span></span>
- <span data-ttu-id="518c1-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="518c1-1090">gültig bis</span></span>
- <span data-ttu-id="518c1-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="518c1-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="518c1-1092">gultig bis</span></span>
- <span data-ttu-id="518c1-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="518c1-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1094">scadenza</span></span>
- <span data-ttu-id="518c1-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="518c1-1095">data scad</span></span>
- <span data-ttu-id="518c1-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="518c1-1096">fecha de expiracion</span></span>
- <span data-ttu-id="518c1-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="518c1-1097">fecha de venc</span></span>
- <span data-ttu-id="518c1-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="518c1-1098">vencimiento</span></span>
- <span data-ttu-id="518c1-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1099">válido hasta</span></span>
- <span data-ttu-id="518c1-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1100">valido hasta</span></span>
- <span data-ttu-id="518c1-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="518c1-1101">vto</span></span>
- <span data-ttu-id="518c1-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="518c1-1102">data de expiração</span></span>
- <span data-ttu-id="518c1-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1103">data de expiracao</span></span>
- <span data-ttu-id="518c1-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="518c1-1104">data em que expira</span></span>
- <span data-ttu-id="518c1-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="518c1-1105">validade</span></span>
- <span data-ttu-id="518c1-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="518c1-1106">valor</span></span>
- <span data-ttu-id="518c1-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="518c1-1107">vencimento</span></span>
- <span data-ttu-id="518c1-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="518c1-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="518c1-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="518c1-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="518c1-1110">amex</span><span class="sxs-lookup"><span data-stu-id="518c1-1110">amex</span></span>
- <span data-ttu-id="518c1-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="518c1-1111">american express</span></span>
- <span data-ttu-id="518c1-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="518c1-1112">americanexpress</span></span>
- <span data-ttu-id="518c1-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="518c1-1113">Visa</span></span>
- <span data-ttu-id="518c1-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1114">mastercard</span></span>
- <span data-ttu-id="518c1-1115">master card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1115">master card</span></span>
- <span data-ttu-id="518c1-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="518c1-1116">mc</span></span> 
- <span data-ttu-id="518c1-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="518c1-1117">mastercards</span></span>
- <span data-ttu-id="518c1-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="518c1-1118">master cards</span></span>
- <span data-ttu-id="518c1-1119">給仕のクラブ</span><span class="sxs-lookup"><span data-stu-id="518c1-1119">diner's Club</span></span>
- <span data-ttu-id="518c1-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="518c1-1120">diners club</span></span>
- <span data-ttu-id="518c1-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="518c1-1121">dinersclub</span></span>
- <span data-ttu-id="518c1-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1122">discover card</span></span>
- <span data-ttu-id="518c1-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1123">discovercard</span></span>
- <span data-ttu-id="518c1-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1124">discover cards</span></span>
- <span data-ttu-id="518c1-1125">安全</span><span class="sxs-lookup"><span data-stu-id="518c1-1125">JCB</span></span>
- <span data-ttu-id="518c1-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="518c1-1126">japanese card bureau</span></span>
- <span data-ttu-id="518c1-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="518c1-1127">carte blanche</span></span>
- <span data-ttu-id="518c1-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="518c1-1128">carteblanche</span></span>
- <span data-ttu-id="518c1-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1129">credit card</span></span>
- <span data-ttu-id="518c1-1130">cc #</span><span class="sxs-lookup"><span data-stu-id="518c1-1130">cc#</span></span>
- <span data-ttu-id="518c1-1131">cc # します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1131">cc#:</span></span>
- <span data-ttu-id="518c1-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="518c1-1132">expiration date</span></span>
- <span data-ttu-id="518c1-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="518c1-1133">exp date</span></span>
- <span data-ttu-id="518c1-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="518c1-1134">expiry date</span></span>
- <span data-ttu-id="518c1-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="518c1-1135">date d’expiration</span></span>
- <span data-ttu-id="518c1-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="518c1-1136">date d'exp</span></span>
- <span data-ttu-id="518c1-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="518c1-1137">date expiration</span></span>
- <span data-ttu-id="518c1-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1138">bank card</span></span>
- <span data-ttu-id="518c1-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="518c1-1139">bankcard</span></span>
- <span data-ttu-id="518c1-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1140">card number</span></span>
- <span data-ttu-id="518c1-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="518c1-1141">card num</span></span>
- <span data-ttu-id="518c1-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1142">cardnumber</span></span>
- <span data-ttu-id="518c1-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-1143">cardnumbers</span></span>
- <span data-ttu-id="518c1-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-1144">card numbers</span></span>
- <span data-ttu-id="518c1-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1145">creditcard</span></span>
- <span data-ttu-id="518c1-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1146">credit cards</span></span>
- <span data-ttu-id="518c1-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1147">creditcards</span></span>
- <span data-ttu-id="518c1-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="518c1-1148">ccn</span></span>
- <span data-ttu-id="518c1-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="518c1-1149">card holder</span></span>
- <span data-ttu-id="518c1-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="518c1-1150">cardholder</span></span>
- <span data-ttu-id="518c1-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="518c1-1151">card holders</span></span>
- <span data-ttu-id="518c1-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="518c1-1152">cardholders</span></span>
- <span data-ttu-id="518c1-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1153">check card</span></span>
- <span data-ttu-id="518c1-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1154">checkcard</span></span>
- <span data-ttu-id="518c1-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1155">check cards</span></span>
- <span data-ttu-id="518c1-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1156">checkcards</span></span>
- <span data-ttu-id="518c1-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1157">debit card</span></span>
- <span data-ttu-id="518c1-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1158">debitcard</span></span>
- <span data-ttu-id="518c1-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1159">debit cards</span></span>
- <span data-ttu-id="518c1-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1160">debitcards</span></span>
- <span data-ttu-id="518c1-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1161">atm card</span></span>
- <span data-ttu-id="518c1-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1162">atmcard</span></span>
- <span data-ttu-id="518c1-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1163">atm cards</span></span>
- <span data-ttu-id="518c1-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1164">atmcards</span></span>
- <span data-ttu-id="518c1-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="518c1-1165">enroute</span></span>
- <span data-ttu-id="518c1-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="518c1-1166">en route</span></span>
- <span data-ttu-id="518c1-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="518c1-1167">card type</span></span>
- <span data-ttu-id="518c1-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="518c1-1168">carte bancaire</span></span>
- <span data-ttu-id="518c1-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="518c1-1169">carte de crédit</span></span>
- <span data-ttu-id="518c1-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="518c1-1170">carte de credit</span></span>
- <span data-ttu-id="518c1-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1171">numéro de carte</span></span>
- <span data-ttu-id="518c1-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1172">numero de carte</span></span>
- <span data-ttu-id="518c1-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1173">nº de la carte</span></span>
- <span data-ttu-id="518c1-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1174">nº de carte</span></span>
- <span data-ttu-id="518c1-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1175">kreditkarte</span></span>
- <span data-ttu-id="518c1-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1176">karte</span></span>
- <span data-ttu-id="518c1-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1177">karteninhaber</span></span>
- <span data-ttu-id="518c1-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="518c1-1178">karteninhabers</span></span>
- <span data-ttu-id="518c1-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="518c1-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="518c1-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="518c1-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="518c1-1181">kreditkartentyp</span></span>
- <span data-ttu-id="518c1-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="518c1-1182">eigentümername</span></span>
- <span data-ttu-id="518c1-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1183">kartennr</span></span> 
- <span data-ttu-id="518c1-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1184">kartennummer</span></span>
- <span data-ttu-id="518c1-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1185">kreditkartennummer</span></span>
- <span data-ttu-id="518c1-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="518c1-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1187">carta di credito</span></span>
- <span data-ttu-id="518c1-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1188">carta credito</span></span>
- <span data-ttu-id="518c1-1189">carta</span><span class="sxs-lookup"><span data-stu-id="518c1-1189">carta</span></span>
- <span data-ttu-id="518c1-1190">n carta</span><span class="sxs-lookup"><span data-stu-id="518c1-1190">n carta</span></span>
- <span data-ttu-id="518c1-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-p110">nr. carta</span></span>
- <span data-ttu-id="518c1-1193">nr carta</span><span class="sxs-lookup"><span data-stu-id="518c1-1193">nr carta</span></span>
- <span data-ttu-id="518c1-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1194">numero carta</span></span>
- <span data-ttu-id="518c1-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1195">numero della carta</span></span>
- <span data-ttu-id="518c1-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1196">numero di carta</span></span>
- <span data-ttu-id="518c1-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1197">tarjeta credito</span></span>
- <span data-ttu-id="518c1-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1198">tarjeta de credito</span></span>
- <span data-ttu-id="518c1-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="518c1-1199">tarjeta crédito</span></span>
- <span data-ttu-id="518c1-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="518c1-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="518c1-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="518c1-1201">tarjeta de atm</span></span>
- <span data-ttu-id="518c1-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="518c1-1202">tarjeta atm</span></span>
- <span data-ttu-id="518c1-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1203">tarjeta debito</span></span>
- <span data-ttu-id="518c1-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1204">tarjeta de debito</span></span>
- <span data-ttu-id="518c1-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="518c1-1205">tarjeta débito</span></span>
- <span data-ttu-id="518c1-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="518c1-1206">tarjeta de débito</span></span>
- <span data-ttu-id="518c1-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1207">nº de tarjeta</span></span>
- <span data-ttu-id="518c1-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-p111">no. de tarjeta</span></span>
- <span data-ttu-id="518c1-1210">なし de tarjeta</span><span class="sxs-lookup"><span data-stu-id="518c1-1210">no de tarjeta</span></span>
- <span data-ttu-id="518c1-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1211">numero de tarjeta</span></span>
- <span data-ttu-id="518c1-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1212">número de tarjeta</span></span>
- <span data-ttu-id="518c1-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1213">tarjeta no</span></span>
- <span data-ttu-id="518c1-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="518c1-1214">tarjetahabiente</span></span>
- <span data-ttu-id="518c1-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1215">cartão de crédito</span></span>
- <span data-ttu-id="518c1-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1216">cartão de credito</span></span>
- <span data-ttu-id="518c1-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1217">cartao de crédito</span></span>
- <span data-ttu-id="518c1-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1218">cartao de credito</span></span>
- <span data-ttu-id="518c1-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1219">cartão de débito</span></span>
- <span data-ttu-id="518c1-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1220">cartao de débito</span></span>
- <span data-ttu-id="518c1-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1221">cartão de debito</span></span>
- <span data-ttu-id="518c1-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1222">cartao de debito</span></span>
- <span data-ttu-id="518c1-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="518c1-1223">débito automático</span></span>
- <span data-ttu-id="518c1-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="518c1-1224">debito automatico</span></span>
- <span data-ttu-id="518c1-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="518c1-1225">número do cartão</span></span>
- <span data-ttu-id="518c1-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-1226">numero do cartão</span></span> 
- <span data-ttu-id="518c1-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="518c1-1227">número do cartao</span></span>
- <span data-ttu-id="518c1-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="518c1-1228">numero do cartao</span></span>
- <span data-ttu-id="518c1-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-1229">número de cartão</span></span>
- <span data-ttu-id="518c1-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-1230">numero de cartão</span></span>
- <span data-ttu-id="518c1-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1231">número de cartao</span></span>
- <span data-ttu-id="518c1-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1232">numero de cartao</span></span>
- <span data-ttu-id="518c1-1233">nº は cartão</span><span class="sxs-lookup"><span data-stu-id="518c1-1233">nº do cartão</span></span>
- <span data-ttu-id="518c1-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1234">nº do cartao</span></span>
- <span data-ttu-id="518c1-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-p112">nº. do cartão</span></span>
- <span data-ttu-id="518c1-1237">なしは cartão</span><span class="sxs-lookup"><span data-stu-id="518c1-1237">no do cartão</span></span>
- <span data-ttu-id="518c1-1238">なしは cartao</span><span class="sxs-lookup"><span data-stu-id="518c1-1238">no do cartao</span></span>
- <span data-ttu-id="518c1-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-p113">no. do cartão</span></span>
- <span data-ttu-id="518c1-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="518c1-1243">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1244">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1244">Format</span></span>

<span data-ttu-id="518c1-1245">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1246">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1246">Pattern</span></span>

<span data-ttu-id="518c1-1247">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1248">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1248">Checksum</span></span>

<span data-ttu-id="518c1-1249">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1250">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1250">Definition</span></span>

<span data-ttu-id="518c1-1251">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1252">関数 Func_croatia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1253">Keyword_croatia_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1254">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="518c1-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="518c1-1256">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="518c1-1256">Croatian identity card</span></span>
- <span data-ttu-id="518c1-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="518c1-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="518c1-1258">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1259">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1259">Format</span></span>

<span data-ttu-id="518c1-1260">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1261">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1261">Pattern</span></span>

<span data-ttu-id="518c1-1262">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-1262">10 digits:</span></span>
- <span data-ttu-id="518c1-1263">DDMMYY の形式で生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="518c1-1264">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="518c1-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1265">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1265">Checksum</span></span>

<span data-ttu-id="518c1-1266">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1267">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1267">Definition</span></span>

<span data-ttu-id="518c1-1268">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1269">関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1270">Keyword_croatia_oib_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="518c1-1271">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1271">The checksum passes.</span></span>

<span data-ttu-id="518c1-1272">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1273">関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1274">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1275">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="518c1-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="518c1-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="518c1-1277">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="518c1-1277">Personal Identification Number</span></span>
- <span data-ttu-id="518c1-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="518c1-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="518c1-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="518c1-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="518c1-1280">チェコの国民身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1281">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1281">Format</span></span>

<span data-ttu-id="518c1-1282">スラッシュを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1283">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1283">Pattern</span></span>

<span data-ttu-id="518c1-1284">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-1284">10 digits:</span></span>
- <span data-ttu-id="518c1-1285">生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="518c1-1286">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-1286">A forward slash</span></span> 
- <span data-ttu-id="518c1-1287">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="518c1-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1288">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1288">Checksum</span></span>

<span data-ttu-id="518c1-1289">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1290">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1290">Definition</span></span>

<span data-ttu-id="518c1-p115">DLP ポリシーとは、85% をこの種類の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_czech_id_card 関数は、パターンに一致するコンテンツを検索します。。Keyword_czech_id_card からキーワードを検出するとします。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="518c1-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="518c1-1294">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1294">Keywords</span></span>

- <span data-ttu-id="518c1-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="518c1-1296">Czech national identity card</span><span class="sxs-lookup"><span data-stu-id="518c1-1296">Czech national identity card</span></span>
- <span data-ttu-id="518c1-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="518c1-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="518c1-1298">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1299">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1299">Format</span></span>

<span data-ttu-id="518c1-1300">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1301">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1301">Pattern</span></span>

<span data-ttu-id="518c1-1302">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-1302">10 digits:</span></span>
- <span data-ttu-id="518c1-1303">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="518c1-1304">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-1304">A hyphen</span></span> 
- <span data-ttu-id="518c1-1305">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="518c1-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1306">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1306">Checksum</span></span>

<span data-ttu-id="518c1-1307">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1308">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1308">Definition</span></span>

<span data-ttu-id="518c1-p116">DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Regex_denmark_id の正規表現パターンに一致するコンテンツを検索します。Keyword_denmark_id からキーワードを検出するとします。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="518c1-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1312">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="518c1-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="518c1-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="518c1-1314">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="518c1-1314">Personal Identification Number</span></span>
- <span data-ttu-id="518c1-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="518c1-1315">CPR</span></span>
- <span data-ttu-id="518c1-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="518c1-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="518c1-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="518c1-1318">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1319">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1319">Format</span></span>

<span data-ttu-id="518c1-1320">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1321">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1321">Pattern</span></span>

<span data-ttu-id="518c1-1322">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="518c1-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="518c1-1323">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="518c1-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="518c1-1324">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="518c1-1325">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="518c1-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1326">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1326">Checksum</span></span>

<span data-ttu-id="518c1-1327">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1328">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1328">Definition</span></span>

<span data-ttu-id="518c1-1329">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1330">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1331">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1332">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1332">Keywords</span></span>

<span data-ttu-id="518c1-1333">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="518c1-1334">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1335">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1335">Format</span></span>

<span data-ttu-id="518c1-1336">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1337">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1337">Pattern</span></span>

<span data-ttu-id="518c1-1338">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1339">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1339">Checksum</span></span>

<span data-ttu-id="518c1-1340">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1341">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1341">Definition</span></span>

<span data-ttu-id="518c1-1342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1343">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1344">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="518c1-1345">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="518c1-1346">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="518c1-1347">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="518c1-1348">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="518c1-1349">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="518c1-1350">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1351">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="518c1-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="518c1-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="518c1-1353">アカウント番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1353">account number</span></span> 
- <span data-ttu-id="518c1-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1354">card number</span></span> 
- <span data-ttu-id="518c1-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="518c1-1355">card no.</span></span> 
- <span data-ttu-id="518c1-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1356">security number</span></span> 
- <span data-ttu-id="518c1-1357">cc #</span><span class="sxs-lookup"><span data-stu-id="518c1-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="518c1-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="518c1-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="518c1-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1359">acct nbr</span></span> 
- <span data-ttu-id="518c1-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="518c1-1360">acct num</span></span> 
- <span data-ttu-id="518c1-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1361">acct no</span></span> 
- <span data-ttu-id="518c1-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="518c1-1362">american express</span></span> 
- <span data-ttu-id="518c1-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="518c1-1363">americanexpress</span></span> 
- <span data-ttu-id="518c1-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="518c1-1364">americano espresso</span></span> 
- <span data-ttu-id="518c1-1365">amex</span><span class="sxs-lookup"><span data-stu-id="518c1-1365">amex</span></span> 
- <span data-ttu-id="518c1-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1366">atm card</span></span> 
- <span data-ttu-id="518c1-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1367">atm cards</span></span> 
- <span data-ttu-id="518c1-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1368">atm kaart</span></span> 
- <span data-ttu-id="518c1-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1369">atmcard</span></span> 
- <span data-ttu-id="518c1-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1370">atmcards</span></span> 
- <span data-ttu-id="518c1-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1371">atmkaart</span></span> 
- <span data-ttu-id="518c1-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="518c1-1372">atmkaarten</span></span> 
- <span data-ttu-id="518c1-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="518c1-1373">bancontact</span></span> 
- <span data-ttu-id="518c1-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1374">bank card</span></span> 
- <span data-ttu-id="518c1-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1375">bankkaart</span></span> 
- <span data-ttu-id="518c1-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="518c1-1376">card holder</span></span> 
- <span data-ttu-id="518c1-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="518c1-1377">card holders</span></span> 
- <span data-ttu-id="518c1-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="518c1-1378">card num</span></span> 
- <span data-ttu-id="518c1-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1379">card number</span></span> 
- <span data-ttu-id="518c1-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-1380">card numbers</span></span> 
- <span data-ttu-id="518c1-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="518c1-1381">card type</span></span> 
- <span data-ttu-id="518c1-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="518c1-1382">cardano numerico</span></span> 
- <span data-ttu-id="518c1-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="518c1-1383">cardholder</span></span> 
- <span data-ttu-id="518c1-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="518c1-1384">cardholders</span></span> 
- <span data-ttu-id="518c1-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1385">cardnumber</span></span> 
- <span data-ttu-id="518c1-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-1386">cardnumbers</span></span> 
- <span data-ttu-id="518c1-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="518c1-1387">carta bianca</span></span> 
- <span data-ttu-id="518c1-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1388">carta credito</span></span> 
- <span data-ttu-id="518c1-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1389">carta di credito</span></span> 
- <span data-ttu-id="518c1-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1390">cartao de credito</span></span> 
- <span data-ttu-id="518c1-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1391">cartao de crédito</span></span> 
- <span data-ttu-id="518c1-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1392">cartao de debito</span></span> 
- <span data-ttu-id="518c1-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1393">cartao de débito</span></span> 
- <span data-ttu-id="518c1-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="518c1-1394">carte bancaire</span></span> 
- <span data-ttu-id="518c1-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="518c1-1395">carte blanche</span></span> 
- <span data-ttu-id="518c1-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="518c1-1396">carte bleue</span></span> 
- <span data-ttu-id="518c1-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="518c1-1397">carte de credit</span></span> 
- <span data-ttu-id="518c1-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="518c1-1398">carte de crédit</span></span> 
- <span data-ttu-id="518c1-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1399">carte di credito</span></span> 
- <span data-ttu-id="518c1-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="518c1-1400">carteblanche</span></span> 
- <span data-ttu-id="518c1-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1401">cartão de credito</span></span> 
- <span data-ttu-id="518c1-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1402">cartão de crédito</span></span> 
- <span data-ttu-id="518c1-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1403">cartão de debito</span></span> 
- <span data-ttu-id="518c1-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1404">cartão de débito</span></span> 
- <span data-ttu-id="518c1-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="518c1-1405">cb</span></span> 
- <span data-ttu-id="518c1-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="518c1-1406">ccn</span></span> 
- <span data-ttu-id="518c1-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1407">check card</span></span> 
- <span data-ttu-id="518c1-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1408">check cards</span></span> 
- <span data-ttu-id="518c1-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1409">checkcard</span></span>
- <span data-ttu-id="518c1-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1410">checkcards</span></span> 
- <span data-ttu-id="518c1-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1411">chequekaart</span></span> 
- <span data-ttu-id="518c1-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="518c1-1412">cirrus</span></span> 
- <span data-ttu-id="518c1-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="518c1-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="518c1-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1414">controlekaart</span></span> 
- <span data-ttu-id="518c1-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="518c1-1415">controlekaarten</span></span> 
- <span data-ttu-id="518c1-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1416">credit card</span></span> 
- <span data-ttu-id="518c1-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1417">credit cards</span></span> 
- <span data-ttu-id="518c1-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1418">creditcard</span></span> 
- <span data-ttu-id="518c1-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1419">creditcards</span></span> 
- <span data-ttu-id="518c1-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1420">debetkaart</span></span> 
- <span data-ttu-id="518c1-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="518c1-1421">debetkaarten</span></span> 
- <span data-ttu-id="518c1-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1422">debit card</span></span> 
- <span data-ttu-id="518c1-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1423">debit cards</span></span> 
- <span data-ttu-id="518c1-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1424">debitcard</span></span> 
- <span data-ttu-id="518c1-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1425">debitcards</span></span> 
- <span data-ttu-id="518c1-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="518c1-1426">debito automatico</span></span> 
- <span data-ttu-id="518c1-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="518c1-1427">diners club</span></span> 
- <span data-ttu-id="518c1-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="518c1-1428">dinersclub</span></span> 
- <span data-ttu-id="518c1-1429">検出</span><span class="sxs-lookup"><span data-stu-id="518c1-1429">discover</span></span> 
- <span data-ttu-id="518c1-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1430">discover card</span></span> 
- <span data-ttu-id="518c1-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1431">discover cards</span></span> 
- <span data-ttu-id="518c1-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1432">discovercard</span></span> 
- <span data-ttu-id="518c1-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1433">discovercards</span></span> 
- <span data-ttu-id="518c1-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="518c1-1434">débito automático</span></span>
- <span data-ttu-id="518c1-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="518c1-1435">edc</span></span> 
- <span data-ttu-id="518c1-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="518c1-1436">eigentümername</span></span> 
- <span data-ttu-id="518c1-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1437">european debit card</span></span> 
- <span data-ttu-id="518c1-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1438">hoofdkaart</span></span> 
- <span data-ttu-id="518c1-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="518c1-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="518c1-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="518c1-1440">in viaggio</span></span> 
- <span data-ttu-id="518c1-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="518c1-1441">japanese card bureau</span></span> 
- <span data-ttu-id="518c1-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="518c1-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="518c1-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="518c1-1443">jcb</span></span> 
- <span data-ttu-id="518c1-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="518c1-1444">kaart</span></span> 
- <span data-ttu-id="518c1-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="518c1-1445">kaart num</span></span> 
- <span data-ttu-id="518c1-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="518c1-1446">kaartaantal</span></span> 
- <span data-ttu-id="518c1-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="518c1-1447">kaartaantallen</span></span> 
- <span data-ttu-id="518c1-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="518c1-1448">kaarthouder</span></span> 
- <span data-ttu-id="518c1-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="518c1-1449">kaarthouders</span></span> 
- <span data-ttu-id="518c1-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1450">karte</span></span>  
- <span data-ttu-id="518c1-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1451">karteninhaber</span></span> 
- <span data-ttu-id="518c1-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="518c1-1452">karteninhabers</span></span>
- <span data-ttu-id="518c1-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1453">kartennr</span></span> 
- <span data-ttu-id="518c1-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1454">kartennummer</span></span> 
- <span data-ttu-id="518c1-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1455">kreditkarte</span></span> 
- <span data-ttu-id="518c1-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="518c1-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="518c1-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="518c1-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="518c1-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="518c1-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="518c1-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="518c1-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="518c1-1461">maestro</span></span> 
- <span data-ttu-id="518c1-1462">master card
</span><span class="sxs-lookup"><span data-stu-id="518c1-1462">master card</span></span> 
- <span data-ttu-id="518c1-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="518c1-1463">master cards</span></span> 
- <span data-ttu-id="518c1-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="518c1-1464">mastercard</span></span> 
- <span data-ttu-id="518c1-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="518c1-1465">mastercards</span></span> 
- <span data-ttu-id="518c1-1466">mc</span><span class="sxs-lookup"><span data-stu-id="518c1-1466">mc</span></span> 
- <span data-ttu-id="518c1-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="518c1-1467">mister cash</span></span> 
- <span data-ttu-id="518c1-1468">n carta</span><span class="sxs-lookup"><span data-stu-id="518c1-1468">n carta</span></span> 
- <span data-ttu-id="518c1-1469">carta</span><span class="sxs-lookup"><span data-stu-id="518c1-1469">carta</span></span> 
- <span data-ttu-id="518c1-1470">なし de tarjeta</span><span class="sxs-lookup"><span data-stu-id="518c1-1470">no de tarjeta</span></span> 
- <span data-ttu-id="518c1-1471">なしは cartao</span><span class="sxs-lookup"><span data-stu-id="518c1-1471">no do cartao</span></span> 
- <span data-ttu-id="518c1-1472">なしは cartão</span><span class="sxs-lookup"><span data-stu-id="518c1-1472">no do cartão</span></span> 
- <span data-ttu-id="518c1-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="518c1-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-p118">no. do cartao</span></span> 
- <span data-ttu-id="518c1-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-p119">no. do cartão</span></span> 
- <span data-ttu-id="518c1-1479">nr carta</span><span class="sxs-lookup"><span data-stu-id="518c1-1479">nr carta</span></span> 
- <span data-ttu-id="518c1-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-p120">nr. carta</span></span> 
- <span data-ttu-id="518c1-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1482">numeri di scheda</span></span> 
- <span data-ttu-id="518c1-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1483">numero carta</span></span> 
- <span data-ttu-id="518c1-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1484">numero de cartao</span></span> 
- <span data-ttu-id="518c1-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1485">numero de carte</span></span> 
- <span data-ttu-id="518c1-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-1486">numero de cartão</span></span> 
- <span data-ttu-id="518c1-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1487">numero de tarjeta</span></span>
- <span data-ttu-id="518c1-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1488">numero della carta</span></span> 
- <span data-ttu-id="518c1-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1489">numero di carta</span></span> 
- <span data-ttu-id="518c1-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1490">numero di scheda</span></span> 
- <span data-ttu-id="518c1-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1491">numero do cartao</span></span> 
- <span data-ttu-id="518c1-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-1492">numero do cartão</span></span> 
- <span data-ttu-id="518c1-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1493">numéro de carte</span></span> 
- <span data-ttu-id="518c1-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1494">nº carta</span></span> 
- <span data-ttu-id="518c1-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1495">nº de carte</span></span> 
- <span data-ttu-id="518c1-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="518c1-1496">nº de la carte</span></span> 
- <span data-ttu-id="518c1-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="518c1-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1498">nº do cartao</span></span> 
- <span data-ttu-id="518c1-1499">nº は cartão</span><span class="sxs-lookup"><span data-stu-id="518c1-1499">nº do cartão</span></span> 
- <span data-ttu-id="518c1-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-p121">nº. do cartão</span></span> 
- <span data-ttu-id="518c1-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1502">número de cartao</span></span> 
- <span data-ttu-id="518c1-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="518c1-1503">número de cartão</span></span> 
- <span data-ttu-id="518c1-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1504">número de tarjeta</span></span> 
- <span data-ttu-id="518c1-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="518c1-1505">número do cartao</span></span> 
- <span data-ttu-id="518c1-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="518c1-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="518c1-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="518c1-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="518c1-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="518c1-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="518c1-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="518c1-1509">scheda della banca</span></span> 
- <span data-ttu-id="518c1-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="518c1-1510">scheda di controllo</span></span> 
- <span data-ttu-id="518c1-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1511">scheda di debito</span></span> 
- <span data-ttu-id="518c1-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="518c1-1512">scheda matrice</span></span> 
- <span data-ttu-id="518c1-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="518c1-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="518c1-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="518c1-1514">schede di controllo</span></span> 
- <span data-ttu-id="518c1-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1515">schede di debito</span></span> 
- <span data-ttu-id="518c1-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="518c1-1516">schede matrici</span></span> 
- <span data-ttu-id="518c1-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="518c1-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="518c1-1518">scoprono le schede</span></span> 
- <span data-ttu-id="518c1-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="518c1-1519">solo</span></span> 
- <span data-ttu-id="518c1-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1520">supporti di scheda</span></span> 
- <span data-ttu-id="518c1-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1521">supporto di scheda</span></span> 
- <span data-ttu-id="518c1-1522">switch
</span><span class="sxs-lookup"><span data-stu-id="518c1-1522">switch</span></span> 
- <span data-ttu-id="518c1-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="518c1-1523">tarjeta atm</span></span> 
- <span data-ttu-id="518c1-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1524">tarjeta credito</span></span> 
- <span data-ttu-id="518c1-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="518c1-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="518c1-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="518c1-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="518c1-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="518c1-1528">tarjeta debito</span></span> 
- <span data-ttu-id="518c1-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1529">tarjeta no</span></span>
- <span data-ttu-id="518c1-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="518c1-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="518c1-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1531">tipo della scheda</span></span> 
- <span data-ttu-id="518c1-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="518c1-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="518c1-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1533">scheda</span></span> 
- <span data-ttu-id="518c1-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="518c1-1534">v pay</span></span> 
- <span data-ttu-id="518c1-1535">v 支払</span><span class="sxs-lookup"><span data-stu-id="518c1-1535">v-pay</span></span> 
- <span data-ttu-id="518c1-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="518c1-1536">visa</span></span> 
- <span data-ttu-id="518c1-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="518c1-1537">visa plus</span></span> 
- <span data-ttu-id="518c1-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="518c1-1538">visa electron</span></span> 
- <span data-ttu-id="518c1-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="518c1-1539">visto</span></span> 
- <span data-ttu-id="518c1-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1540">visum</span></span> 
- <span data-ttu-id="518c1-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="518c1-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="518c1-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="518c1-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="518c1-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="518c1-1543">card identification number</span></span>
- <span data-ttu-id="518c1-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="518c1-1544">card verification</span></span> 
- <span data-ttu-id="518c1-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="518c1-1545">cardi la verifica</span></span> 
- <span data-ttu-id="518c1-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="518c1-1546">cid</span></span> 
- <span data-ttu-id="518c1-1547">代金引換払い seg</span><span class="sxs-lookup"><span data-stu-id="518c1-1547">cod seg</span></span> 
- <span data-ttu-id="518c1-1548">代金引換払い seguranca</span><span class="sxs-lookup"><span data-stu-id="518c1-1548">cod seguranca</span></span> 
- <span data-ttu-id="518c1-1549">代金引換払い segurança</span><span class="sxs-lookup"><span data-stu-id="518c1-1549">cod segurança</span></span> 
- <span data-ttu-id="518c1-1550">代金引換払いの sicurezza</span><span class="sxs-lookup"><span data-stu-id="518c1-1550">cod sicurezza</span></span> 
- <span data-ttu-id="518c1-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="518c1-p122">cod. seg</span></span> 
- <span data-ttu-id="518c1-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-p123">cod. seguranca</span></span> 
- <span data-ttu-id="518c1-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-p124">cod. segurança</span></span> 
- <span data-ttu-id="518c1-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="518c1-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="518c1-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="518c1-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="518c1-1560">codice di verifica</span></span> 
- <span data-ttu-id="518c1-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="518c1-1561">codigo</span></span> 
- <span data-ttu-id="518c1-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="518c1-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-1563">codigo de segurança</span></span> 
- <span data-ttu-id="518c1-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="518c1-1564">crittogramma</span></span> 
- <span data-ttu-id="518c1-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="518c1-1565">cryptogram</span></span> 
- <span data-ttu-id="518c1-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="518c1-1566">cryptogramme</span></span> 
- <span data-ttu-id="518c1-1567">cv2</span><span class="sxs-lookup"><span data-stu-id="518c1-1567">cv2</span></span> 
- <span data-ttu-id="518c1-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="518c1-1568">cvc</span></span> 
- <span data-ttu-id="518c1-1569">cvc2</span><span class="sxs-lookup"><span data-stu-id="518c1-1569">cvc2</span></span> 
- <span data-ttu-id="518c1-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="518c1-1570">cvn</span></span> 
- <span data-ttu-id="518c1-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="518c1-1571">cvv</span></span> 
- <span data-ttu-id="518c1-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="518c1-1572">cvv2</span></span> 
- <span data-ttu-id="518c1-1573">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="518c1-1573">cód seguranca</span></span> 
- <span data-ttu-id="518c1-1574">cód segurança</span><span class="sxs-lookup"><span data-stu-id="518c1-1574">cód segurança</span></span> 
- <span data-ttu-id="518c1-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-p126">cód. seguranca</span></span> 
- <span data-ttu-id="518c1-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-p127">cód. segurança</span></span> 
- <span data-ttu-id="518c1-1579">código
</span><span class="sxs-lookup"><span data-stu-id="518c1-1579">código</span></span> 
- <span data-ttu-id="518c1-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="518c1-1580">código de seguranca</span></span> 
- <span data-ttu-id="518c1-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="518c1-1581">código de segurança</span></span> 
- <span data-ttu-id="518c1-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="518c1-1582">de kaart controle</span></span> 
- <span data-ttu-id="518c1-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="518c1-1583">geeft nr uit</span></span> 
- <span data-ttu-id="518c1-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1584">issue no</span></span> 
- <span data-ttu-id="518c1-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1585">issue number</span></span> 
- <span data-ttu-id="518c1-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="518c1-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="518c1-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="518c1-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="518c1-1589">kwestieaantal</span></span> 
- <span data-ttu-id="518c1-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="518c1-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="518c1-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="518c1-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="518c1-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="518c1-1594">numero de securite</span></span> 
- <span data-ttu-id="518c1-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1595">numero de verificacao</span></span> 
- <span data-ttu-id="518c1-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="518c1-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="518c1-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="518c1-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="518c1-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="518c1-1598">scheda</span></span> 
- <span data-ttu-id="518c1-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="518c1-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="518c1-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="518c1-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="518c1-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="518c1-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="518c1-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="518c1-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="518c1-1603">número de verificação</span></span> 
- <span data-ttu-id="518c1-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="518c1-1604">perno il blocco</span></span> 
- <span data-ttu-id="518c1-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="518c1-1605">pin block</span></span> 
- <span data-ttu-id="518c1-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1606">prufziffer</span></span> 
- <span data-ttu-id="518c1-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1607">prüfziffer</span></span> 
- <span data-ttu-id="518c1-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="518c1-1608">security code</span></span> 
- <span data-ttu-id="518c1-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="518c1-1609">security no</span></span> 
- <span data-ttu-id="518c1-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1610">security number</span></span> 
- <span data-ttu-id="518c1-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="518c1-1611">sicherheits kode</span></span> 
- <span data-ttu-id="518c1-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="518c1-1612">sicherheitscode</span></span> 
- <span data-ttu-id="518c1-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="518c1-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="518c1-1614">speldblok</span></span> 
- <span data-ttu-id="518c1-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1615">veiligheid nr</span></span> 
- <span data-ttu-id="518c1-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="518c1-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="518c1-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="518c1-1617">veiligheidscode</span></span> 
- <span data-ttu-id="518c1-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="518c1-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="518c1-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="518c1-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="518c1-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="518c1-1621">ablauf</span></span> 
- <span data-ttu-id="518c1-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="518c1-1622">data de expiracao</span></span> 
- <span data-ttu-id="518c1-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="518c1-1623">data de expiração</span></span> 
- <span data-ttu-id="518c1-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="518c1-1624">data del exp</span></span> 
- <span data-ttu-id="518c1-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="518c1-1625">data di exp</span></span> 
- <span data-ttu-id="518c1-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1626">data di scadenza</span></span> 
- <span data-ttu-id="518c1-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="518c1-1627">data em que expira</span></span> 
- <span data-ttu-id="518c1-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="518c1-1628">data scad</span></span> 
- <span data-ttu-id="518c1-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1629">data scadenza</span></span> 
- <span data-ttu-id="518c1-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="518c1-1630">date de validité</span></span> 
- <span data-ttu-id="518c1-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="518c1-1631">datum afloop</span></span> 
- <span data-ttu-id="518c1-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="518c1-1632">datum van exp</span></span> 
- <span data-ttu-id="518c1-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="518c1-1633">de afloop</span></span> 
- <span data-ttu-id="518c1-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="518c1-1634">espira</span></span> 
- <span data-ttu-id="518c1-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="518c1-1635">espira</span></span> 
- <span data-ttu-id="518c1-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="518c1-1636">exp date</span></span> 
- <span data-ttu-id="518c1-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1637">exp datum</span></span> 
- <span data-ttu-id="518c1-1638">有効期限</span><span class="sxs-lookup"><span data-stu-id="518c1-1638">expiration</span></span> 
- <span data-ttu-id="518c1-1639">expire
</span><span class="sxs-lookup"><span data-stu-id="518c1-1639">expire</span></span> 
- <span data-ttu-id="518c1-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="518c1-1640">expires</span></span> 
- <span data-ttu-id="518c1-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="518c1-1641">expiry</span></span> 
- <span data-ttu-id="518c1-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="518c1-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="518c1-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="518c1-1643">fecha de venc</span></span> 
- <span data-ttu-id="518c1-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="518c1-1644">gultig bis</span></span> 
- <span data-ttu-id="518c1-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="518c1-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="518c1-1646">gültig bis</span></span> 
- <span data-ttu-id="518c1-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="518c1-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1648">la scadenza</span></span> 
- <span data-ttu-id="518c1-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="518c1-1649">scadenza</span></span> 
- <span data-ttu-id="518c1-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="518c1-1650">valable</span></span> 
- <span data-ttu-id="518c1-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="518c1-1651">validade</span></span> 
- <span data-ttu-id="518c1-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1652">valido hasta</span></span> 
- <span data-ttu-id="518c1-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="518c1-1653">valor</span></span> 
- <span data-ttu-id="518c1-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="518c1-1654">venc</span></span> 
- <span data-ttu-id="518c1-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="518c1-1655">vencimento</span></span> 
- <span data-ttu-id="518c1-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="518c1-1656">vencimiento</span></span> 
- <span data-ttu-id="518c1-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="518c1-1657">verloopt</span></span> 
- <span data-ttu-id="518c1-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="518c1-1658">vervaldag</span></span> 
- <span data-ttu-id="518c1-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1659">vervaldatum</span></span> 
- <span data-ttu-id="518c1-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="518c1-1660">vto</span></span> 
- <span data-ttu-id="518c1-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="518c1-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="518c1-1662">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1662">EU Driver's License Number</span></span>

<span data-ttu-id="518c1-1663">詳細については、 [EU ドライバーのライセンス番号の機密性の高い情報の種類](eu-driver-s-license-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518c1-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="518c1-1664">EU 国民 Id 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1664">EU National Identification Number</span></span>

<span data-ttu-id="518c1-1665">詳細については、 [EU 各国の識別番号の機密性の高い情報の種類](eu-national-identification-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518c1-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="518c1-1666">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1666">EU Passport Number</span></span>

<span data-ttu-id="518c1-1667">詳細については、 [EU のパスポート番号の機密性の高い情報の種類](eu-passport-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518c1-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="518c1-1668">EU の社会保障番号またはそれと同等の ID</span><span class="sxs-lookup"><span data-stu-id="518c1-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="518c1-1669">詳細については、 [EU の社会保障番号、または機密性の高い情報の種類のと同じ ID](eu-social-security-number-or-equivalent-id.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518c1-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="518c1-1670">EU 税 Id 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="518c1-1671">詳細については、 [EU の税 Id 番号の機密性の高い情報の種類](eu-tax-identification-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518c1-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="518c1-1672">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="518c1-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1673">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1673">Format</span></span>

<span data-ttu-id="518c1-1674">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="518c1-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1675">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1675">Pattern</span></span>

<span data-ttu-id="518c1-1676">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="518c1-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="518c1-1677">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="518c1-1678">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="518c1-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="518c1-1679">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="518c1-1680">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="518c1-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1681">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1681">Checksum</span></span>

<span data-ttu-id="518c1-1682">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1683">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1683">Definition</span></span>

<span data-ttu-id="518c1-1684">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1685">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1686">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="518c1-1687">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1688">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1688">Keywords</span></span>

- <span data-ttu-id="518c1-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="518c1-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="518c1-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="518c1-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="518c1-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="518c1-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="518c1-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="518c1-1692">Personbeteckning</span></span>
- <span data-ttu-id="518c1-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="518c1-1694">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1694">Finland Passport Number</span></span>

<span data-ttu-id="518c1-p130">9 つの文字と数字の 9 つの文字と数字の組み合わせのパターンの組み合わせを書式設定: 2 つの文字 (いない大文字小文字を区別) の 7 桁のチェックサムなしの定義 A DLP ポリシーは、75% の場合はこの種の機密情報を検出したことを確信で、300 文字の長さ: Regex_finland_passport_number の正規表現パターンに一致するコンテンツを検索します。Keyword_finland_passport_number からキーワードを検出するとします。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Keyword_finland_passport_number Passport Passi のキーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="518c1-1699">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1700">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1700">Format</span></span>

<span data-ttu-id="518c1-1701">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1702">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1702">Pattern</span></span>

<span data-ttu-id="518c1-1703">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1704">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1704">Checksum</span></span>

<span data-ttu-id="518c1-1705">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1706">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1706">Definition</span></span>

<span data-ttu-id="518c1-1707">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1708">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1709">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="518c1-1710">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="518c1-1711">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1712">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="518c1-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="518c1-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="518c1-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="518c1-1714">drivers licence</span></span>
- <span data-ttu-id="518c1-1715">drivers license</span><span class="sxs-lookup"><span data-stu-id="518c1-1715">drivers license</span></span>
- <span data-ttu-id="518c1-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-1716">driving licence</span></span>
- <span data-ttu-id="518c1-1717">ライセンスを推進</span><span class="sxs-lookup"><span data-stu-id="518c1-1717">driving license</span></span>
- <span data-ttu-id="518c1-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="518c1-1718">permis de conduire</span></span>
- <span data-ttu-id="518c1-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="518c1-1719">licence number</span></span>
- <span data-ttu-id="518c1-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="518c1-1720">license number</span></span>
- <span data-ttu-id="518c1-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="518c1-1721">licence numbers</span></span>
- <span data-ttu-id="518c1-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="518c1-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="518c1-1723">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="518c1-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1724">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1724">Format</span></span>

<span data-ttu-id="518c1-1725">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1726">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1726">Pattern</span></span>

<span data-ttu-id="518c1-1727">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1728">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1728">Checksum</span></span>

<span data-ttu-id="518c1-1729">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1730">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1730">Definition</span></span>

<span data-ttu-id="518c1-1731">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1732">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1733">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1733">Keywords</span></span>

<span data-ttu-id="518c1-1734">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="518c1-1735">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1736">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1736">Format</span></span>

<span data-ttu-id="518c1-1737">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1738">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1738">Pattern</span></span>

<span data-ttu-id="518c1-1739">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="518c1-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="518c1-1740">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1740">Two digits</span></span> 
- <span data-ttu-id="518c1-1741">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-1742">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1743">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1743">Checksum</span></span>

<span data-ttu-id="518c1-1744">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1745">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1745">Definition</span></span>

<span data-ttu-id="518c1-1746">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1747">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1748">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1749">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="518c1-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-1750">Keyword_passport</span></span>

- <span data-ttu-id="518c1-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="518c1-1751">Passport Number</span></span>
- <span data-ttu-id="518c1-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="518c1-1752">Passport No</span></span>
- <span data-ttu-id="518c1-1753">Passport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-1753">Passport #</span></span>
- <span data-ttu-id="518c1-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-1754">Passport#</span></span>
- <span data-ttu-id="518c1-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="518c1-1755">PassportID</span></span>
- <span data-ttu-id="518c1-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="518c1-1756">Passportno</span></span>
- <span data-ttu-id="518c1-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-1757">passportnumber</span></span>
- <span data-ttu-id="518c1-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="518c1-1758">パスポート</span></span>
- <span data-ttu-id="518c1-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-1759">パスポート番号</span></span>
- <span data-ttu-id="518c1-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="518c1-1760">パスポートのNum</span></span>
- <span data-ttu-id="518c1-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-1761">パスポート ＃</span></span> 
- <span data-ttu-id="518c1-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="518c1-1762">Numéro de passeport</span></span>
- <span data-ttu-id="518c1-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="518c1-1763">Passeport n °</span></span>
- <span data-ttu-id="518c1-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="518c1-1764">Passeport Non</span></span>
- <span data-ttu-id="518c1-1765">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-1765">Passeport #</span></span>
- <span data-ttu-id="518c1-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-1766">Passeport#</span></span>
- <span data-ttu-id="518c1-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="518c1-1767">PasseportNon</span></span>
- <span data-ttu-id="518c1-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="518c1-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="518c1-1769">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="518c1-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1770">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1770">Format</span></span>

<span data-ttu-id="518c1-1771">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1772">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1772">Pattern</span></span>

<span data-ttu-id="518c1-1773">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="518c1-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="518c1-1774">13 桁の数字が 2 桁の後にスペースの後に</span><span class="sxs-lookup"><span data-stu-id="518c1-1774">13 digits followed by a space followed by two digits</span></span></br>
<span data-ttu-id="518c1-1775">または</span><span class="sxs-lookup"><span data-stu-id="518c1-1775">or</span></span>
- <span data-ttu-id="518c1-1776">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1777">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1777">Checksum</span></span>

<span data-ttu-id="518c1-1778">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1779">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1779">Definition</span></span>

<span data-ttu-id="518c1-1780">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1781">Func_french_insee または Func_fr_insee 関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1782">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="518c1-1783">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1783">The checksum passes.</span></span>

<span data-ttu-id="518c1-1784">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1785">Func_french_insee または Func_fr_insee 関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1786">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="518c1-1787">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1788">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="518c1-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="518c1-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="518c1-1790">insee</span><span class="sxs-lookup"><span data-stu-id="518c1-1790">insee</span></span>
- <span data-ttu-id="518c1-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="518c1-1791">securité sociale</span></span>
- <span data-ttu-id="518c1-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="518c1-1792">securite sociale</span></span>
- <span data-ttu-id="518c1-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="518c1-1793">national id</span></span>
- <span data-ttu-id="518c1-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="518c1-1794">national identification</span></span>
- <span data-ttu-id="518c1-1795">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="518c1-1795">numéro d'identité</span></span>
- <span data-ttu-id="518c1-1796">なし d'identité</span><span class="sxs-lookup"><span data-stu-id="518c1-1796">no d'identité</span></span>
- <span data-ttu-id="518c1-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="518c1-p131">no. d'identité</span></span>
- <span data-ttu-id="518c1-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="518c1-1799">numero d'identite</span></span>
- <span data-ttu-id="518c1-1800">なし d'identite</span><span class="sxs-lookup"><span data-stu-id="518c1-1800">no d'identite</span></span>
- <span data-ttu-id="518c1-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="518c1-p132">no. d'identite</span></span>
- <span data-ttu-id="518c1-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="518c1-1803">social security number</span></span>
- <span data-ttu-id="518c1-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="518c1-1804">social security code</span></span>
- <span data-ttu-id="518c1-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="518c1-1805">social insurance number</span></span>
- <span data-ttu-id="518c1-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="518c1-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="518c1-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="518c1-1807">d'identité nationale</span></span>
- <span data-ttu-id="518c1-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="518c1-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="518c1-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="518c1-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="518c1-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="518c1-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="518c1-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="518c1-1811">numéro de sécu</span></span>
- <span data-ttu-id="518c1-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="518c1-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="518c1-1813">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1814">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1814">Format</span></span>

<span data-ttu-id="518c1-1815">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="518c1-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1816">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1816">Pattern</span></span>

<span data-ttu-id="518c1-1817">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="518c1-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="518c1-1818">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1818">A digit or letter</span></span> 
- <span data-ttu-id="518c1-1819">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1819">Two digits</span></span> 
- <span data-ttu-id="518c1-1820">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1820">Six digits or letters</span></span> 
- <span data-ttu-id="518c1-1821">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1821">A digit</span></span> 
- <span data-ttu-id="518c1-1822">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1823">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1823">Checksum</span></span>

<span data-ttu-id="518c1-1824">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1825">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1825">Definition</span></span>

<span data-ttu-id="518c1-1826">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1827">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1828">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="518c1-1829">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="518c1-1830">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="518c1-1831">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="518c1-1832">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1833">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="518c1-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="518c1-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="518c1-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="518c1-1835">Führerschein</span></span>
- <span data-ttu-id="518c1-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="518c1-1836">Fuhrerschein</span></span>
- <span data-ttu-id="518c1-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="518c1-1837">Fuehrerschein</span></span>
- <span data-ttu-id="518c1-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="518c1-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="518c1-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="518c1-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="518c1-1841">Führerschein-</span></span> 
- <span data-ttu-id="518c1-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="518c1-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="518c1-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="518c1-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="518c1-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="518c1-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="518c1-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="518c1-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="518c1-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="518c1-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="518c1-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="518c1-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="518c1-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="518c1-1850">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="518c1-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="518c1-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="518c1-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="518c1-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="518c1-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="518c1-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="518c1-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="518c1-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="518c1-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="518c1-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="518c1-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="518c1-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="518c1-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="518c1-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="518c1-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="518c1-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="518c1-1862">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="518c1-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="518c1-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="518c1-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="518c1-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="518c1-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="518c1-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="518c1-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="518c1-1868">DL</span><span class="sxs-lookup"><span data-stu-id="518c1-1868">DL</span></span> 
- <span data-ttu-id="518c1-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="518c1-1869">DLS</span></span>
- <span data-ttu-id="518c1-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="518c1-1870">Driv Lic</span></span> 
- <span data-ttu-id="518c1-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="518c1-1871">Driv Licen</span></span> 
- <span data-ttu-id="518c1-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="518c1-1872">Driv License</span></span>
- <span data-ttu-id="518c1-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="518c1-1873">Driv Licenses</span></span> 
- <span data-ttu-id="518c1-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-1874">Driv Licence</span></span> 
- <span data-ttu-id="518c1-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-1875">Driv Licences</span></span> 
- <span data-ttu-id="518c1-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="518c1-1876">Driv Lic</span></span> 
- <span data-ttu-id="518c1-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="518c1-1877">Driver Licen</span></span> 
- <span data-ttu-id="518c1-1878">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-1878">Driver License</span></span> 
- <span data-ttu-id="518c1-1879">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-1879">Driver Licenses</span></span> 
- <span data-ttu-id="518c1-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-1880">Driver Licence</span></span> 
- <span data-ttu-id="518c1-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-1881">Driver Licences</span></span> 
- <span data-ttu-id="518c1-1882">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-1882">Drivers Lic</span></span> 
- <span data-ttu-id="518c1-1883">ドライバー Licen</span><span class="sxs-lookup"><span data-stu-id="518c1-1883">Drivers Licen</span></span> 
- <span data-ttu-id="518c1-1884">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1884">Drivers License</span></span> 
- <span data-ttu-id="518c1-1885">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="518c1-1886">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-1886">Drivers Licence</span></span> 
- <span data-ttu-id="518c1-1887">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-1887">Drivers Licences</span></span> 
- <span data-ttu-id="518c1-1888">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-1888">Driver's Lic</span></span> 
- <span data-ttu-id="518c1-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="518c1-1889">Driver's Licen</span></span> 
- <span data-ttu-id="518c1-1890">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-1890">Driver's License</span></span> 
- <span data-ttu-id="518c1-1891">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="518c1-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-1892">Driver's Licence</span></span> 
- <span data-ttu-id="518c1-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-1893">Driver's Licences</span></span> 
- <span data-ttu-id="518c1-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="518c1-1894">Driving Lic</span></span> 
- <span data-ttu-id="518c1-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="518c1-1895">Driving Licen</span></span> 
- <span data-ttu-id="518c1-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="518c1-1896">Driving License</span></span> 
- <span data-ttu-id="518c1-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="518c1-1897">Driving Licenses</span></span> 
- <span data-ttu-id="518c1-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="518c1-1898">Driving Licence</span></span> 
- <span data-ttu-id="518c1-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="518c1-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="518c1-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="518c1-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="518c1-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="518c1-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="518c1-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="518c1-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1904">No-Führerschein</span></span> 
- <span data-ttu-id="518c1-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="518c1-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="518c1-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1907">N-Führerschein</span></span> 
- <span data-ttu-id="518c1-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="518c1-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="518c1-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="518c1-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="518c1-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="518c1-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="518c1-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1913">No-Führerschein</span></span> 
- <span data-ttu-id="518c1-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="518c1-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="518c1-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1916">N-Führerschein</span></span> 
- <span data-ttu-id="518c1-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="518c1-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="518c1-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="518c1-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="518c1-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="518c1-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="518c1-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="518c1-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="518c1-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="518c1-1921">ausstellungsort</span></span>
- <span data-ttu-id="518c1-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="518c1-1922">ausstellende behöde</span></span>
- <span data-ttu-id="518c1-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="518c1-1923">ausstellende behorde</span></span>
- <span data-ttu-id="518c1-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="518c1-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="518c1-1925">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1926">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1926">Format</span></span>

<span data-ttu-id="518c1-1927">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1928">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1928">Pattern</span></span>

<span data-ttu-id="518c1-1929">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="518c1-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="518c1-1930">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="518c1-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="518c1-1931">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1931">Three digits</span></span> 
- <span data-ttu-id="518c1-1932">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="518c1-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="518c1-1933">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1934">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1934">Checksum</span></span>

<span data-ttu-id="518c1-1935">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1936">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1936">Definition</span></span>

<span data-ttu-id="518c1-1937">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1938">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1939">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="518c1-1940">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1940">The checksum passes.</span></span>

<span data-ttu-id="518c1-1941">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1942">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1943">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="518c1-1944">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-1945">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="518c1-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="518c1-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="518c1-1947">reisepass</span></span>
- <span data-ttu-id="518c1-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="518c1-1948">reisepasse</span></span>
- <span data-ttu-id="518c1-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1949">reisepassnummer</span></span>
- <span data-ttu-id="518c1-1950">passport</span><span class="sxs-lookup"><span data-stu-id="518c1-1950">passport</span></span>
- <span data-ttu-id="518c1-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="518c1-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="518c1-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="518c1-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="518c1-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="518c1-1953">geburtsdatum</span></span>
- <span data-ttu-id="518c1-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="518c1-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="518c1-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="518c1-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="518c1-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="518c1-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="518c1-1957">いいえ-Reisepass-Reisepass Nr</span><span class="sxs-lookup"><span data-stu-id="518c1-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="518c1-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="518c1-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="518c1-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="518c1-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="518c1-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="518c1-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="518c1-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="518c1-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="518c1-1962">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="518c1-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1963">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1963">Format</span></span>

<span data-ttu-id="518c1-1964">1 2010 年 11 月以降: 9 つの文字と数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="518c1-1965">31 10 月 2010: 10 桁までの 1 年 1987年 4 月から</span><span class="sxs-lookup"><span data-stu-id="518c1-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1966">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1966">Pattern</span></span>

<span data-ttu-id="518c1-1967">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="518c1-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="518c1-1968">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-1969">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1969">Eight digits</span></span>

<span data-ttu-id="518c1-1970">31 2010 年 10 月までの 1 年 1987年 4 月: から</span><span class="sxs-lookup"><span data-stu-id="518c1-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="518c1-1971">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1972">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1972">Checksum</span></span>

<span data-ttu-id="518c1-1973">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-1974">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-1974">Definition</span></span>

<span data-ttu-id="518c1-1975">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-1976">正規表現 Regex_germany_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-1977">Keyword_germany_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-1978">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="518c1-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="518c1-1980">Identity Card</span><span class="sxs-lookup"><span data-stu-id="518c1-1980">Identity Card</span></span>
- <span data-ttu-id="518c1-1981">ID</span><span class="sxs-lookup"><span data-stu-id="518c1-1981">ID</span></span>
- <span data-ttu-id="518c1-1982">Identification</span><span class="sxs-lookup"><span data-stu-id="518c1-1982">Identification</span></span>
- <span data-ttu-id="518c1-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="518c1-1983">Personalausweis</span></span>
- <span data-ttu-id="518c1-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="518c1-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="518c1-1985">Ausweis</span></span>
- <span data-ttu-id="518c1-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="518c1-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="518c1-1987">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="518c1-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="518c1-1988">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-1988">Format</span></span>

<span data-ttu-id="518c1-1989">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="518c1-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-1990">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-1990">Pattern</span></span>

<span data-ttu-id="518c1-1991">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="518c1-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="518c1-1992">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="518c1-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="518c1-1993">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-1993">A dash</span></span> 
- <span data-ttu-id="518c1-1994">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1994">Six digits</span></span>

<span data-ttu-id="518c1-1995">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="518c1-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="518c1-1996">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="518c1-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="518c1-1997">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-1997">A dash</span></span> 
- <span data-ttu-id="518c1-1998">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-1999">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-1999">Checksum</span></span>

<span data-ttu-id="518c1-2000">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2001">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2001">Definition</span></span>

<span data-ttu-id="518c1-2002">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2003">正規表現 Regex_greece_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2004">Keyword_greece_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2005">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="518c1-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="518c1-2007">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="518c1-2007">Greek identity Card</span></span>
- <span data-ttu-id="518c1-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="518c1-2008">Tautotita</span></span>
- <span data-ttu-id="518c1-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="518c1-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="518c1-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="518c1-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="518c1-2011">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2012">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2012">Format</span></span>

<span data-ttu-id="518c1-2013">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="518c1-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2014">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2014">Pattern</span></span>

<span data-ttu-id="518c1-2015">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="518c1-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="518c1-2016">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2017">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2017">Six digits</span></span> 
- <span data-ttu-id="518c1-2018">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="518c1-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2019">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2019">Checksum</span></span>

<span data-ttu-id="518c1-2020">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2021">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2021">Definition</span></span>

<span data-ttu-id="518c1-2022">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2023">関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2024">Keyword_hong_kong_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="518c1-2025">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2025">The checksum passes.</span></span>

<span data-ttu-id="518c1-2026">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2027">関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2028">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2029">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="518c1-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="518c1-2031">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="518c1-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="518c1-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="518c1-2032">HKID</span></span>
- <span data-ttu-id="518c1-2033">ID card</span><span class="sxs-lookup"><span data-stu-id="518c1-2033">ID card</span></span>
- <span data-ttu-id="518c1-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2034">香港身份證</span></span> 
- <span data-ttu-id="518c1-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="518c1-2036">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="518c1-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2037">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2037">Format</span></span>

<span data-ttu-id="518c1-2038">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2039">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2039">Pattern</span></span>

<span data-ttu-id="518c1-2040">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2040">10 letters or digits:</span></span>
- <span data-ttu-id="518c1-2041">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2042">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2042">Four digits</span></span> 
- <span data-ttu-id="518c1-2043">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="518c1-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2044">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2044">Checksum</span></span>

<span data-ttu-id="518c1-2045">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2046">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2046">Definition</span></span>

<span data-ttu-id="518c1-2047">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2048">正規表現 Regex_india_permanent_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2049">Keyword_india_permanent_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="518c1-2050">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2051">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="518c1-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="518c1-2053">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="518c1-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="518c1-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="518c1-2055">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2056">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2056">Format</span></span>

<span data-ttu-id="518c1-2057">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2058">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2058">Pattern</span></span>

<span data-ttu-id="518c1-2059">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2059">12 digits:</span></span>
- <span data-ttu-id="518c1-2060">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2060">Four digits</span></span> 
- <span data-ttu-id="518c1-2061">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2061">An optional space or dash</span></span> 
- <span data-ttu-id="518c1-2062">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2062">Four digits</span></span> 
- <span data-ttu-id="518c1-2063">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2063">An optional space or dash</span></span> 
- <span data-ttu-id="518c1-2064">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="518c1-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2065">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2065">Checksum</span></span>

<span data-ttu-id="518c1-2066">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2067">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2067">Definition</span></span>

<span data-ttu-id="518c1-p133">DLP ポリシーとは、85% をこの種類の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_india_aadhaar 関数は、パターンに一致するコンテンツを検索します。。Keyword_india_aadhar からキーワードを検出するとします。チェックサムが渡されます。DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_india_aadhaar 関数は、パターンに一致するコンテンツを検索します。。チェックサムが渡されます。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="518c1-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="518c1-2074">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="518c1-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="518c1-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="518c1-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="518c1-2076">Aadhar</span></span>
- <span data-ttu-id="518c1-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="518c1-2077">Aadhaar</span></span>
- <span data-ttu-id="518c1-2078">UID</span><span class="sxs-lookup"><span data-stu-id="518c1-2078">UID</span></span>
- <span data-ttu-id="518c1-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="518c1-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="518c1-2080">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2081">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2081">Format</span></span>

<span data-ttu-id="518c1-2082">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2083">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2083">Pattern</span></span>

<span data-ttu-id="518c1-2084">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2084">16 digits:</span></span>
- <span data-ttu-id="518c1-2085">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="518c1-2085">Two-digit province code</span></span> 
- <span data-ttu-id="518c1-2086">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2086">A period (optional)</span></span> 
- <span data-ttu-id="518c1-2087">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="518c1-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="518c1-2088">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="518c1-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="518c1-2089">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2089">A period (optional)</span></span> 
- <span data-ttu-id="518c1-2090">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="518c1-2091">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2091">A period (optional)</span></span> 
- <span data-ttu-id="518c1-2092">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2093">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2093">Checksum</span></span>

<span data-ttu-id="518c1-2094">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2095">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2095">Definition</span></span>

<span data-ttu-id="518c1-2096">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2097">正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2098">Keyword_indonesia_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="518c1-2099">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2100">正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2101">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="518c1-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="518c1-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="518c1-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="518c1-2103">KTP</span></span>
- <span data-ttu-id="518c1-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="518c1-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="518c1-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="518c1-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="518c1-2106">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="518c1-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2107">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2107">Format</span></span>

<span data-ttu-id="518c1-2108">国コード (2 文字)、チェック ディジット (2 桁)、bban 番号 (最大 30 文字)</span><span class="sxs-lookup"><span data-stu-id="518c1-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2109">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2109">Pattern</span></span>

<span data-ttu-id="518c1-2110">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="518c1-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="518c1-2111">2 文字の国コード</span><span class="sxs-lookup"><span data-stu-id="518c1-2111">Two-letter country code</span></span>
- <span data-ttu-id="518c1-2112">2 桁のチェック ディジット (省略可能なスペースが続く) </span><span class="sxs-lookup"><span data-stu-id="518c1-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="518c1-2113">4 個の文字または数字で構成される 1 から 7 個のグループ (スペースで区切ることができる)</span><span class="sxs-lookup"><span data-stu-id="518c1-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="518c1-2114">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2114">1-3 letters or digits</span></span>

<span data-ttu-id="518c1-p134">各国の形式は多少異なります。IBAN 機密情報の型は、次の 60 か国をカバーしています。</span><span class="sxs-lookup"><span data-stu-id="518c1-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="518c1-2117">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、gi、gl、gr、hr、hu、ie、il、is、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="518c1-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2118">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2118">Checksum</span></span>

<span data-ttu-id="518c1-2119">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2120">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2120">Definition</span></span>

<span data-ttu-id="518c1-2121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2122">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2123">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2124">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2124">Keywords</span></span>

<span data-ttu-id="518c1-2125">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="518c1-2126">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="518c1-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2127">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="518c1-2128">IPv4:</span><span class="sxs-lookup"><span data-stu-id="518c1-2128">IPv4:</span></span>
<span data-ttu-id="518c1-2129">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="518c1-2130">IPv6:</span><span class="sxs-lookup"><span data-stu-id="518c1-2130">IPv6:</span></span>
<span data-ttu-id="518c1-2131"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2132">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2133">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2133">Checksum</span></span>

<span data-ttu-id="518c1-2134">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2135">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2135">Definition</span></span>

<span data-ttu-id="518c1-2136">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2137">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2138">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="518c1-2139">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2140">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2141">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="518c1-2142">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2143">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2144">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2145">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="518c1-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="518c1-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="518c1-2147">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="518c1-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="518c1-2148">ip address
</span><span class="sxs-lookup"><span data-stu-id="518c1-2148">ip address</span></span> 
- <span data-ttu-id="518c1-2149">ip addresses</span><span class="sxs-lookup"><span data-stu-id="518c1-2149">ip addresses</span></span>
- <span data-ttu-id="518c1-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="518c1-2150">internet protocol</span></span>
- <span data-ttu-id="518c1-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="518c1-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="518c1-2152">病気 (ICD 10 CM) の国際的な分類</span><span class="sxs-lookup"><span data-stu-id="518c1-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2153">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2153">Format</span></span>

<span data-ttu-id="518c1-2154">辞書</span><span class="sxs-lookup"><span data-stu-id="518c1-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2155">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2155">Pattern</span></span>

<span data-ttu-id="518c1-2156">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2157">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2157">Checksum</span></span>

<span data-ttu-id="518c1-2158">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2159">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2159">Definition</span></span>

<span data-ttu-id="518c1-2160">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2161">Dictionary_icd_10_cm からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="518c1-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="518c1-2162">Keywords</span><span class="sxs-lookup"><span data-stu-id="518c1-2162">Keywords</span></span>

<span data-ttu-id="518c1-p135">Dictionary_icd_10_cm キーワード辞書からすべての用語をに基づいて[病気の分類を国際、10 分のリビジョン、臨床変更 (ICD 10 CM)](https://go.microsoft.com/fwlink/?linkid=852604)。このタイプは、用語、保険のコードではないのだけを検索します。</span><span class="sxs-lookup"><span data-stu-id="518c1-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="518c1-2165">病気 (ICD 9 CM) の国際的な分類</span><span class="sxs-lookup"><span data-stu-id="518c1-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2166">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2166">Format</span></span>

<span data-ttu-id="518c1-2167">辞書</span><span class="sxs-lookup"><span data-stu-id="518c1-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2168">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2168">Pattern</span></span>

<span data-ttu-id="518c1-2169">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2170">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2170">Checksum</span></span>

<span data-ttu-id="518c1-2171">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2172">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2172">Definition</span></span>

<span data-ttu-id="518c1-2173">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2174">Dictionary_icd_9_cm からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="518c1-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2175">Keywords</span><span class="sxs-lookup"><span data-stu-id="518c1-2175">Keywords</span></span>

<span data-ttu-id="518c1-p136">Dictionary_icd_9_cm キーワード辞書からすべての用語をに基づいて[病気の分類を国際、9 番目のリビジョン、臨床変更 (ICD 9 CM)](https://go.microsoft.com/fwlink/?linkid=852605)。このタイプは、用語、保険のコードではないのだけを検索します。</span><span class="sxs-lookup"><span data-stu-id="518c1-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="518c1-2178">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2179">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2179">Format</span></span>

<span data-ttu-id="518c1-2180">(2012 年 5 年 12 月 31日) までの古い形式:</span><span class="sxs-lookup"><span data-stu-id="518c1-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="518c1-2181">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="518c1-2182">新しい形式 (1 年 2013年 1 月と後)。</span><span class="sxs-lookup"><span data-stu-id="518c1-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="518c1-2183">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="518c1-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2184">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2184">Pattern</span></span>

<span data-ttu-id="518c1-2185">(2012 年 5 年 12 月 31日) までの古い形式:</span><span class="sxs-lookup"><span data-stu-id="518c1-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="518c1-2186">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2186">Seven digits</span></span> 
- <span data-ttu-id="518c1-2187">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="518c1-2188">新しい形式 (1 年 2013年 1 月と後)。</span><span class="sxs-lookup"><span data-stu-id="518c1-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="518c1-2189">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2189">Seven digits</span></span> 
- <span data-ttu-id="518c1-2190">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="518c1-2191">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="518c1-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2192">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2192">Checksum</span></span>

<span data-ttu-id="518c1-2193">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2194">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2194">Definition</span></span>

<span data-ttu-id="518c1-2195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2196">関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2197">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-2197">One of the following is true:</span></span>
    - <span data-ttu-id="518c1-2198">Keyword_ireland_pps のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="518c1-2199">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="518c1-2200">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2200">The checksum passes.</span></span>

<span data-ttu-id="518c1-2201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2202">関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2203">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2204">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="518c1-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="518c1-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="518c1-2206">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="518c1-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="518c1-2207">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2207">PPS Number</span></span> 
- <span data-ttu-id="518c1-2208">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="518c1-2208">PPS Num</span></span> 
- <span data-ttu-id="518c1-2209">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2209">PPS No.</span></span> 
- <span data-ttu-id="518c1-2210">PPS #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2210">PPS #</span></span> 
- <span data-ttu-id="518c1-2211">PPS #</span><span class="sxs-lookup"><span data-stu-id="518c1-2211">PPS#</span></span> 
- <span data-ttu-id="518c1-2212">PPSN
</span><span class="sxs-lookup"><span data-stu-id="518c1-2212">PPSN</span></span> 
- <span data-ttu-id="518c1-2213">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-2213">Public Services Card</span></span> 
- <span data-ttu-id="518c1-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="518c1-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="518c1-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="518c1-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="518c1-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="518c1-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="518c1-2218">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2219">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2219">Format</span></span>

<span data-ttu-id="518c1-2220">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2221">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2221">Pattern</span></span>

<span data-ttu-id="518c1-2222">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-2222">Formatted:</span></span>
- <span data-ttu-id="518c1-2223">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2223">Two digits</span></span> 
- <span data-ttu-id="518c1-2224">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-2224">A dash</span></span> 
- <span data-ttu-id="518c1-2225">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2225">Three digits</span></span> 
- <span data-ttu-id="518c1-2226">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-2226">A dash</span></span> 
- <span data-ttu-id="518c1-2227">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2227">Eight digits</span></span>

<span data-ttu-id="518c1-2228">書式設定されていない場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-2228">Unformatted:</span></span>
- <span data-ttu-id="518c1-2229">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2230">Checksum</span></span>

<span data-ttu-id="518c1-2231">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2232">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2232">Definition</span></span>

<span data-ttu-id="518c1-2233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2234">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2235">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2236">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="518c1-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="518c1-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2238">Bank Account Number</span></span> 
- <span data-ttu-id="518c1-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="518c1-2239">Bank Account</span></span> 
- <span data-ttu-id="518c1-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2240">Account Number</span></span> 
- <span data-ttu-id="518c1-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="518c1-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="518c1-2242">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2243">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2243">Format</span></span>

<span data-ttu-id="518c1-2244">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2245">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2245">Pattern</span></span>

<span data-ttu-id="518c1-2246">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2247">Checksum</span></span>

<span data-ttu-id="518c1-2248">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2249">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2249">Definition</span></span>

<span data-ttu-id="518c1-2250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2251">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2252">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="518c1-2253">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2254">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="518c1-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="518c1-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="518c1-2256">מספר זהות</span></span> 
- <span data-ttu-id="518c1-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="518c1-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="518c1-2258">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2259">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2259">Format</span></span>

<span data-ttu-id="518c1-2260">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="518c1-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2261">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2261">Pattern</span></span>

- <span data-ttu-id="518c1-2262">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="518c1-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="518c1-2263">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2264">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2265">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="518c1-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="518c1-2266">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2267">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2267">Checksum</span></span>

<span data-ttu-id="518c1-2268">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2269">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2269">Definition</span></span>

<span data-ttu-id="518c1-2270">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2271">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2272">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2273">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="518c1-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="518c1-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="518c1-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="518c1-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="518c1-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="518c1-2277">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2278">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2278">Format</span></span>

<span data-ttu-id="518c1-2279">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2280">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2280">Pattern</span></span>

<span data-ttu-id="518c1-2281">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="518c1-2281">Bank account number:</span></span>
- <span data-ttu-id="518c1-2282">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2282">Seven or eight digits</span></span>
- <span data-ttu-id="518c1-2283">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="518c1-2283">Bank account branch code:</span></span>
- <span data-ttu-id="518c1-2284">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2284">Four digits</span></span> 
- <span data-ttu-id="518c1-2285">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="518c1-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="518c1-2286">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2286">Three digits</span></span>

<span data-ttu-id="518c1-2287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2287">Checksum</span></span>

<span data-ttu-id="518c1-2288">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2289">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2289">Definition</span></span>

<span data-ttu-id="518c1-2290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2291">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2292">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="518c1-2293">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-2293">One of the following is true:</span></span>
- <span data-ttu-id="518c1-2294">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2295">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="518c1-2296">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2297">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2298">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2299">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="518c1-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="518c1-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="518c1-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2301">Checking Account Number</span></span> 
- <span data-ttu-id="518c1-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="518c1-2302">Checking Account</span></span> 
- <span data-ttu-id="518c1-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2303">Checking Account #</span></span> 
- <span data-ttu-id="518c1-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="518c1-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2305">Checking Acct #</span></span> 
- <span data-ttu-id="518c1-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="518c1-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2307">Checking Account No.</span></span> 
- <span data-ttu-id="518c1-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2308">Bank Account Number</span></span> 
- <span data-ttu-id="518c1-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="518c1-2309">Bank Account</span></span> 
- <span data-ttu-id="518c1-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2310">Bank Account #</span></span> 
- <span data-ttu-id="518c1-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="518c1-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2312">Bank Acct #</span></span> 
- <span data-ttu-id="518c1-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="518c1-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2314">Bank Account No.</span></span> 
- <span data-ttu-id="518c1-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2315">Savings Account Number</span></span> 
- <span data-ttu-id="518c1-2316">預金/貯蓄口座</span><span class="sxs-lookup"><span data-stu-id="518c1-2316">Savings Account</span></span> 
- <span data-ttu-id="518c1-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2317">Savings Account #</span></span> 
- <span data-ttu-id="518c1-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="518c1-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2319">Savings Acct #</span></span> 
- <span data-ttu-id="518c1-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="518c1-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2321">Savings Account No.</span></span> 
- <span data-ttu-id="518c1-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2322">Debit Account Number</span></span> 
- <span data-ttu-id="518c1-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="518c1-2323">Debit Account</span></span> 
- <span data-ttu-id="518c1-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2324">Debit Account #</span></span> 
- <span data-ttu-id="518c1-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="518c1-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2326">Debit Acct #</span></span> 
- <span data-ttu-id="518c1-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="518c1-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2328">Debit Account No.</span></span> 
- <span data-ttu-id="518c1-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="518c1-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="518c1-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="518c1-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="518c1-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="518c1-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="518c1-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="518c1-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="518c1-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="518c1-2333">口座番号の確認</span></span> 
- <span data-ttu-id="518c1-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2334">銀行口座番号</span></span> 
- <span data-ttu-id="518c1-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="518c1-2335">銀行口座</span></span> 
- <span data-ttu-id="518c1-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2336">銀行口座＃</span></span> 
- <span data-ttu-id="518c1-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="518c1-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="518c1-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="518c1-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="518c1-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2340">銀行口座番号</span></span>
- <span data-ttu-id="518c1-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="518c1-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="518c1-2342">預金口座</span></span> 
- <span data-ttu-id="518c1-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="518c1-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="518c1-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="518c1-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="518c1-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="518c1-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="518c1-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="518c1-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2349">口座番号</span></span> 
- <span data-ttu-id="518c1-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2350">口座番号＃</span></span> 
- <span data-ttu-id="518c1-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="518c1-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="518c1-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="518c1-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="518c1-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="518c1-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="518c1-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="518c1-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="518c1-2357">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2358">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2358">Format</span></span>

<span data-ttu-id="518c1-2359">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2360">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2360">Pattern</span></span>

<span data-ttu-id="518c1-2361">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2362">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2362">Checksum</span></span>

<span data-ttu-id="518c1-2363">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2364">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2364">Definition</span></span>

<span data-ttu-id="518c1-2365">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2366">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2367">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2368">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="518c1-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="518c1-2370">dl#</span><span class="sxs-lookup"><span data-stu-id="518c1-2370">dl#</span></span> 
- <span data-ttu-id="518c1-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="518c1-2371">DL＃</span></span> 
- <span data-ttu-id="518c1-2372">dls#</span><span class="sxs-lookup"><span data-stu-id="518c1-2372">dls#</span></span> 
- <span data-ttu-id="518c1-2373">DL #</span><span class="sxs-lookup"><span data-stu-id="518c1-2373">DLS＃</span></span> 
- <span data-ttu-id="518c1-2374">driver license</span><span class="sxs-lookup"><span data-stu-id="518c1-2374">driver license</span></span> 
- <span data-ttu-id="518c1-2375">driver licenses</span><span class="sxs-lookup"><span data-stu-id="518c1-2375">driver licenses</span></span> 
- <span data-ttu-id="518c1-2376">drivers license</span><span class="sxs-lookup"><span data-stu-id="518c1-2376">drivers license</span></span> 
- <span data-ttu-id="518c1-2377">driver's license</span><span class="sxs-lookup"><span data-stu-id="518c1-2377">driver's license</span></span> 
- <span data-ttu-id="518c1-2378">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="518c1-2378">drivers licenses</span></span> 
- <span data-ttu-id="518c1-2379">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="518c1-2379">driver's licenses</span></span> 
- <span data-ttu-id="518c1-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-2380">driving licence</span></span> 
- <span data-ttu-id="518c1-2381">lic#</span><span class="sxs-lookup"><span data-stu-id="518c1-2381">lic#</span></span> 
- <span data-ttu-id="518c1-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="518c1-2382">LIC＃</span></span> 
- <span data-ttu-id="518c1-2383">lics#</span><span class="sxs-lookup"><span data-stu-id="518c1-2383">lics#</span></span> 
- <span data-ttu-id="518c1-2384">状態 id</span><span class="sxs-lookup"><span data-stu-id="518c1-2384">state id</span></span> 
- <span data-ttu-id="518c1-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="518c1-2385">state identification</span></span> 
- <span data-ttu-id="518c1-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2386">state identification number</span></span> 
- <span data-ttu-id="518c1-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2387">低所得国＃</span></span> 
- <span data-ttu-id="518c1-2388">免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-2388">免許証</span></span> 
- <span data-ttu-id="518c1-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2389">状態ID</span></span>
- <span data-ttu-id="518c1-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="518c1-2390">状態の識別</span></span> 
- <span data-ttu-id="518c1-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2391">状態の識別番号</span></span> 
- <span data-ttu-id="518c1-2392">運転免許</span><span class="sxs-lookup"><span data-stu-id="518c1-2392">運転免許</span></span> 
- <span data-ttu-id="518c1-2393">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-2393">運転免許証</span></span> 
- <span data-ttu-id="518c1-2394">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="518c1-2395">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2396">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2396">Format</span></span>

<span data-ttu-id="518c1-2397">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2398">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2398">Pattern</span></span>

<span data-ttu-id="518c1-2399">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2400">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2400">Checksum</span></span>

<span data-ttu-id="518c1-2401">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2402">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2402">Definition</span></span>

<span data-ttu-id="518c1-2403">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2404">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2405">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2406">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="518c1-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="518c1-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="518c1-2408">パスポート</span></span> 
- <span data-ttu-id="518c1-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2409">パスポート番号</span></span> 
- <span data-ttu-id="518c1-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="518c1-2410">パスポートのNum</span></span> 
- <span data-ttu-id="518c1-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="518c1-2412">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2413">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2413">Format</span></span>

<span data-ttu-id="518c1-2414">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2415">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2415">Pattern</span></span>

<span data-ttu-id="518c1-2416">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2417">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2417">Checksum</span></span>

<span data-ttu-id="518c1-2418">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2419">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2419">Definition</span></span>

<span data-ttu-id="518c1-2420">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2421">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2422">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2423">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="518c1-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="518c1-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="518c1-2425">Resident Registration Number</span></span>
- <span data-ttu-id="518c1-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2426">Resident Register Number</span></span> 
- <span data-ttu-id="518c1-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="518c1-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="518c1-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2429">Resident Register No.</span></span> 
- <span data-ttu-id="518c1-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="518c1-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="518c1-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="518c1-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="518c1-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="518c1-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="518c1-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="518c1-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="518c1-2436">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="518c1-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2437">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2437">Format</span></span>

<span data-ttu-id="518c1-2438">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2439">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2439">Pattern</span></span>

<span data-ttu-id="518c1-2440">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2440">7-12 digits:</span></span>
- <span data-ttu-id="518c1-2441">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2441">Four digits</span></span> 
- <span data-ttu-id="518c1-2442">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="518c1-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="518c1-2443">6 桁または</span><span class="sxs-lookup"><span data-stu-id="518c1-2443">Six digits OR</span></span>
- <span data-ttu-id="518c1-2444">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2445">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2445">Checksum</span></span>

<span data-ttu-id="518c1-2446">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2447">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2447">Definition</span></span>

<span data-ttu-id="518c1-2448">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2449">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2450">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="518c1-2451">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2452">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2453">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2454">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="518c1-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="518c1-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="518c1-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="518c1-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="518c1-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="518c1-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="518c1-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="518c1-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="518c1-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="518c1-2461">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2462">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2462">Format</span></span>

<span data-ttu-id="518c1-2463">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2464">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2464">Pattern</span></span>

<span data-ttu-id="518c1-2465">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2465">12 digits:</span></span>
- <span data-ttu-id="518c1-2466">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="518c1-2467">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2467">A dash (optional)</span></span> 
- <span data-ttu-id="518c1-2468">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="518c1-2469">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2469">A dash (optional)</span></span> 
- <span data-ttu-id="518c1-2470">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2470">Three random digits</span></span> 
- <span data-ttu-id="518c1-2471">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="518c1-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2472">Checksum</span></span>

<span data-ttu-id="518c1-2473">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2474">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2474">Definition</span></span>

<span data-ttu-id="518c1-2475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2476">正規表現 Regex_malaysia_id_card_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2477">Keyword_malaysia_id_card_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2478">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="518c1-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="518c1-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="518c1-2480">MyKad</span></span> 
- <span data-ttu-id="518c1-2481">Identity Card</span><span class="sxs-lookup"><span data-stu-id="518c1-2481">Identity Card</span></span> 
- <span data-ttu-id="518c1-2482">ID カード</span><span class="sxs-lookup"><span data-stu-id="518c1-2482">ID Card</span></span> 
- <span data-ttu-id="518c1-2483">Id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-2483">Identification Card</span></span> 
- <span data-ttu-id="518c1-2484">Digital Application Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-2484">Digital Application Card</span></span> 
- <span data-ttu-id="518c1-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="518c1-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="518c1-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="518c1-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="518c1-2487">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2488">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2488">Format</span></span>

<span data-ttu-id="518c1-2489">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2490">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2490">Pattern</span></span>

<span data-ttu-id="518c1-2491">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2491">8-9 digits:</span></span>
- <span data-ttu-id="518c1-2492">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2492">Three digits</span></span> 
- <span data-ttu-id="518c1-2493">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2493">A space (optional)</span></span> 
- <span data-ttu-id="518c1-2494">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2494">Three digits</span></span> 
- <span data-ttu-id="518c1-2495">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="518c1-2495">A space (optional)</span></span> 
- <span data-ttu-id="518c1-2496">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2497">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2497">Checksum</span></span>

<span data-ttu-id="518c1-2498">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2499">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2499">Definition</span></span>

<span data-ttu-id="518c1-2500">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2501">関数 Func_netherlands_bsn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2502">Keyword_netherlands_bsn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="518c1-2503">関数 Func_eu_date2 が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="518c1-2504">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2505">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="518c1-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="518c1-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="518c1-2507">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2507">Citizen service number</span></span> 
- <span data-ttu-id="518c1-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="518c1-2508">BSN</span></span> 
- <span data-ttu-id="518c1-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="518c1-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-2510">Sofinummer</span></span> 
- <span data-ttu-id="518c1-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="518c1-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="518c1-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="518c1-2513">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2514">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2514">Format</span></span>

<span data-ttu-id="518c1-2515">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2516">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2516">Pattern</span></span>

<span data-ttu-id="518c1-2517">3 つの文字を (大文字小文字を区別)、スペース (省略可能) 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2518">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2518">Checksum</span></span>

<span data-ttu-id="518c1-2519">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2520">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2520">Definition</span></span>

<span data-ttu-id="518c1-2521">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2522">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2523">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="518c1-2524">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2524">The checksum passes.</span></span>

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

<span data-ttu-id="518c1-2525">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2525">Keywords</span></span>

<span data-ttu-id="518c1-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="518c1-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="518c1-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="518c1-2527">NHI</span></span> 
- <span data-ttu-id="518c1-2528">ニュージーランド</span><span class="sxs-lookup"><span data-stu-id="518c1-2528">New Zealand</span></span> 
- <span data-ttu-id="518c1-2529">正常性</span><span class="sxs-lookup"><span data-stu-id="518c1-2529">Health</span></span> 
- <span data-ttu-id="518c1-2530">treatment
</span><span class="sxs-lookup"><span data-stu-id="518c1-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="518c1-2531">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2532">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2532">Format</span></span>

<span data-ttu-id="518c1-2533">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2534">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2534">Pattern</span></span>

<span data-ttu-id="518c1-2535">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2535">11 digits:</span></span>
- <span data-ttu-id="518c1-2536">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="518c1-2537">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="518c1-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="518c1-2538">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="518c1-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2539">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2539">Checksum</span></span>

<span data-ttu-id="518c1-2540">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2541">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2541">Definition</span></span>

<span data-ttu-id="518c1-2542">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2543">関数 Func_norway_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2544">Keyword_norway_id_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="518c1-2545">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2545">The checksum passes.</span></span>
- <span data-ttu-id="518c1-2546">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2547">関数 Func_norway_id_numbe がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2548">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2549">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="518c1-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="518c1-2551">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="518c1-2551">Personal identification number</span></span>
- <span data-ttu-id="518c1-2552">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="518c1-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="518c1-2553">ID Number</span><span class="sxs-lookup"><span data-stu-id="518c1-2553">ID Number</span></span>
- <span data-ttu-id="518c1-2554">Identification</span><span class="sxs-lookup"><span data-stu-id="518c1-2554">Identification</span></span>
- <span data-ttu-id="518c1-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-2555">Personnummer</span></span>
- <span data-ttu-id="518c1-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="518c1-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="518c1-2557">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2558">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2558">Format</span></span>

<span data-ttu-id="518c1-2559">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2560">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2560">Pattern</span></span>

<span data-ttu-id="518c1-2561">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2561">12 digits:</span></span>
- <span data-ttu-id="518c1-2562">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2562">Four digits</span></span> 
- <span data-ttu-id="518c1-2563">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-2563">A hyphen</span></span> 
- <span data-ttu-id="518c1-2564">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2564">Seven digits</span></span> 
- <span data-ttu-id="518c1-2565">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-2565">A hyphen</span></span> 
- <span data-ttu-id="518c1-2566">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2567">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2567">Checksum</span></span>

<span data-ttu-id="518c1-2568">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2569">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2569">Definition</span></span>

<span data-ttu-id="518c1-2570">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2571">正規表現 Regex_philippines_unified_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2572">Keyword_philippines_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2573">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="518c1-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="518c1-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="518c1-2575">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="518c1-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="518c1-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="518c1-2576">UMID</span></span> 
- <span data-ttu-id="518c1-2577">Identity Card</span><span class="sxs-lookup"><span data-stu-id="518c1-2577">Identity Card</span></span> 
- <span data-ttu-id="518c1-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="518c1-2579">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="518c1-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2580">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2580">Format</span></span>

<span data-ttu-id="518c1-2581">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2582">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2582">Pattern</span></span>

<span data-ttu-id="518c1-2583">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2584">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2584">Checksum</span></span>

<span data-ttu-id="518c1-2585">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2586">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2586">Definition</span></span>

<span data-ttu-id="518c1-p138">DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_polish_national_id 関数は、パターンに一致するコンテンツを検索します。。Keyword_polish_national_id_passport_number からキーワードを検出するとします。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="518c1-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2590">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="518c1-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="518c1-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="518c1-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="518c1-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="518c1-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="518c1-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="518c1-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="518c1-2596">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="518c1-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2597">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2597">Format</span></span>

<span data-ttu-id="518c1-2598">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2599">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2599">Pattern</span></span>

<span data-ttu-id="518c1-2600">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2601">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2601">Checksum</span></span>

<span data-ttu-id="518c1-2602">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2603">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2603">Definition</span></span>

<span data-ttu-id="518c1-2604">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2605">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2606">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="518c1-2607">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2608">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="518c1-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="518c1-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="518c1-2610">Nr PESEL</span></span>
- <span data-ttu-id="518c1-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="518c1-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="518c1-2612">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="518c1-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2613">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2613">Format</span></span>

<span data-ttu-id="518c1-2614">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2615">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2615">Pattern</span></span>

<span data-ttu-id="518c1-2616">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2617">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2617">Checksum</span></span>

<span data-ttu-id="518c1-2618">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2619">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2619">Definition</span></span>

<span data-ttu-id="518c1-2620">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2621">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2622">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="518c1-2623">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2624">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="518c1-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="518c1-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="518c1-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="518c1-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="518c1-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="518c1-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="518c1-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="518c1-2630">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2631">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2631">Format</span></span>

<span data-ttu-id="518c1-2632">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2633">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2633">Pattern</span></span>

<span data-ttu-id="518c1-2634">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2635">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2635">Checksum</span></span>

<span data-ttu-id="518c1-2636">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2637">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2637">Definition</span></span>

<span data-ttu-id="518c1-2638">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2639">正規表現 Regex_portugal_citizen_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2640">Keyword_portugal_citizen_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2641">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="518c1-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="518c1-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="518c1-2643">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="518c1-2643">Citizen Card</span></span>
- <span data-ttu-id="518c1-2644">National ID Card</span><span class="sxs-lookup"><span data-stu-id="518c1-2644">National ID Card</span></span>
- <span data-ttu-id="518c1-2645">CC</span><span class="sxs-lookup"><span data-stu-id="518c1-2645">CC</span></span>
- <span data-ttu-id="518c1-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="518c1-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="518c1-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="518c1-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="518c1-2648">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2649">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2649">Format</span></span>

<span data-ttu-id="518c1-2650">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2651">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2651">Pattern</span></span>

<span data-ttu-id="518c1-2652">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2653">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2653">Checksum</span></span>

<span data-ttu-id="518c1-2654">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2655">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2655">Definition</span></span>

<span data-ttu-id="518c1-2656">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2657">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2658">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2659">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="518c1-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="518c1-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="518c1-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-2661">Identification Card</span></span> 
- <span data-ttu-id="518c1-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2662">I card number</span></span> 
- <span data-ttu-id="518c1-2663">ID number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2663">ID number</span></span> 
- <span data-ttu-id="518c1-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="518c1-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="518c1-2665">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2666">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2666">Format</span></span>

<span data-ttu-id="518c1-2667">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2668">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2668">Pattern</span></span>

- <span data-ttu-id="518c1-2669">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="518c1-2670">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2671">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2671">Seven digits</span></span> 
- <span data-ttu-id="518c1-2672">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="518c1-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2673">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2673">Checksum</span></span>

<span data-ttu-id="518c1-2674">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2675">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2675">Definition</span></span>

<span data-ttu-id="518c1-2676">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2677">正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2678">Keyword_singapore_nric のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="518c1-2679">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2679">The checksum passes.</span></span>

<span data-ttu-id="518c1-2680">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2681">正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2682">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2683">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="518c1-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="518c1-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="518c1-2685">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="518c1-2686">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2686">Identity Card Number</span></span> 
- <span data-ttu-id="518c1-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="518c1-2687">NRIC</span></span> 
- <span data-ttu-id="518c1-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="518c1-2688">IC</span></span> 
- <span data-ttu-id="518c1-2689">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="518c1-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="518c1-2690">FIN</span></span> 
- <span data-ttu-id="518c1-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="518c1-2691">身份证</span></span> 
- <span data-ttu-id="518c1-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="518c1-2693">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2694">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2694">Format</span></span>

<span data-ttu-id="518c1-2695">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2696">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2696">Pattern</span></span>

<span data-ttu-id="518c1-2697">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2697">13 digits:</span></span>
- <span data-ttu-id="518c1-2698">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="518c1-2699">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2699">Four digits</span></span> 
- <span data-ttu-id="518c1-2700">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="518c1-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="518c1-2701">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="518c1-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="518c1-2702">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2703">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2703">Checksum</span></span>

<span data-ttu-id="518c1-2704">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2705">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2705">Definition</span></span>

<span data-ttu-id="518c1-2706">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2707">関数 Func_south_africa_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2708">Keyword_south_africa_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="518c1-2709">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2710">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="518c1-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="518c1-2712">Identity card</span><span class="sxs-lookup"><span data-stu-id="518c1-2712">Identity card</span></span>
- <span data-ttu-id="518c1-2713">ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2713">ID</span></span>
- <span data-ttu-id="518c1-2714">Identification</span><span class="sxs-lookup"><span data-stu-id="518c1-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="518c1-2715">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2716">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2716">Format</span></span>

<span data-ttu-id="518c1-2717">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2718">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2718">Pattern</span></span>

<span data-ttu-id="518c1-2719">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2719">13 digits:</span></span>
- <span data-ttu-id="518c1-2720">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="518c1-2721">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="518c1-2721">A hyphen</span></span> 
- <span data-ttu-id="518c1-2722">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="518c1-2723">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="518c1-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="518c1-2724">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="518c1-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="518c1-2725">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="518c1-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2726">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2726">Checksum</span></span>

<span data-ttu-id="518c1-2727">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2728">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2728">Definition</span></span>

<span data-ttu-id="518c1-2729">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2730">関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2731">Keyword_south_korea_resident_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="518c1-2732">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2732">The checksum passes.</span></span>

<span data-ttu-id="518c1-2733">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2734">関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2735">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2736">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="518c1-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="518c1-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="518c1-2738">National ID card
</span><span class="sxs-lookup"><span data-stu-id="518c1-2738">National ID card</span></span> 
- <span data-ttu-id="518c1-2739">Citizen's Registration Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="518c1-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="518c1-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="518c1-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="518c1-2741">RRN</span></span> 
- <span data-ttu-id="518c1-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="518c1-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="518c1-2743">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="518c1-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2744">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2744">Format</span></span>

<span data-ttu-id="518c1-2745">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2746">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2746">Pattern</span></span>

<span data-ttu-id="518c1-2747">11-12 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="518c1-2747">11-12 digits:</span></span>
- <span data-ttu-id="518c1-2748">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2748">Two digits</span></span> 
- <span data-ttu-id="518c1-2749">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="518c1-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="518c1-2750">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2750">7-8 digits</span></span> 
- <span data-ttu-id="518c1-2751">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="518c1-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="518c1-2752">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2753">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2753">Checksum</span></span>

<span data-ttu-id="518c1-2754">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2755">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2755">Definition</span></span>

<span data-ttu-id="518c1-2756">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2757">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2758">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2759">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2759">Keywords</span></span>

<span data-ttu-id="518c1-2760">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="518c1-2761">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2762">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2762">Format</span></span>

<span data-ttu-id="518c1-2763">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="518c1-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2764">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2764">Pattern</span></span>

<span data-ttu-id="518c1-2765">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="518c1-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="518c1-2766">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="518c1-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="518c1-2767">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="518c1-2768">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="518c1-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="518c1-2769">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2770">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2770">Checksum</span></span>

<span data-ttu-id="518c1-2771">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2772">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2772">Definition</span></span>

<span data-ttu-id="518c1-2773">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2774">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2775">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2776">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2776">Keywords</span></span>

<span data-ttu-id="518c1-2777">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="518c1-2778">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2779">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2779">Format</span></span>

<span data-ttu-id="518c1-2780">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2781">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2781">Pattern</span></span>

<span data-ttu-id="518c1-2782">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2783">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2783">Checksum</span></span>

<span data-ttu-id="518c1-2784">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2785">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2785">Definition</span></span>

<span data-ttu-id="518c1-2786">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2787">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2788">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-2788">One of the following is true:</span></span>
    - <span data-ttu-id="518c1-2789">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="518c1-2790">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-2791">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="518c1-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="518c1-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="518c1-2793">visa requirements</span></span> 
- <span data-ttu-id="518c1-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="518c1-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="518c1-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="518c1-2795">Schengen visas</span></span> 
- <span data-ttu-id="518c1-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="518c1-2796">Schengen visa</span></span> 
- <span data-ttu-id="518c1-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="518c1-2797">Visa Processing</span></span> 
- <span data-ttu-id="518c1-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="518c1-2798">Visa Type</span></span> 
- <span data-ttu-id="518c1-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="518c1-2799">Single Entry</span></span> 
- <span data-ttu-id="518c1-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="518c1-2800">Multiple Entry</span></span> 
- <span data-ttu-id="518c1-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="518c1-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="518c1-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-2802">Keyword_passport</span></span>

- <span data-ttu-id="518c1-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="518c1-2803">Passport Number</span></span> 
- <span data-ttu-id="518c1-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="518c1-2804">Passport No</span></span> 
- <span data-ttu-id="518c1-2805">Passport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2805">Passport #</span></span> 
- <span data-ttu-id="518c1-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-2806">Passport#</span></span> 
- <span data-ttu-id="518c1-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="518c1-2807">PassportID</span></span> 
- <span data-ttu-id="518c1-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="518c1-2808">Passportno</span></span> 
- <span data-ttu-id="518c1-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-2809">passportnumber</span></span> 
- <span data-ttu-id="518c1-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="518c1-2810">パスポート</span></span> 
- <span data-ttu-id="518c1-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2811">パスポート番号</span></span> 
- <span data-ttu-id="518c1-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="518c1-2812">パスポートのNum</span></span> 
- <span data-ttu-id="518c1-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2813">パスポート＃</span></span> 
- <span data-ttu-id="518c1-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="518c1-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="518c1-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="518c1-2815">Passeport n °</span></span> 
- <span data-ttu-id="518c1-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="518c1-2816">Passeport Non</span></span> 
- <span data-ttu-id="518c1-2817">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2817">Passeport #</span></span> 
- <span data-ttu-id="518c1-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-2818">Passeport#</span></span> 
- <span data-ttu-id="518c1-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="518c1-2819">PasseportNon</span></span> 
- <span data-ttu-id="518c1-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="518c1-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="518c1-2821">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="518c1-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2822">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2822">Format</span></span>

<span data-ttu-id="518c1-2823">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2824">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2824">Pattern</span></span>

<span data-ttu-id="518c1-2825">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="518c1-2826">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="518c1-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2827">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="518c1-2827">An optional space</span></span> 
- <span data-ttu-id="518c1-2828">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="518c1-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="518c1-2829">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="518c1-2829">An optional space</span></span> 
- <span data-ttu-id="518c1-2830">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="518c1-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2831">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2831">Checksum</span></span>

<span data-ttu-id="518c1-2832">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2833">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2833">Definition</span></span>

<span data-ttu-id="518c1-2834">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2835">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2836">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2837">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="518c1-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="518c1-2838">Keyword_swift</span></span>

- <span data-ttu-id="518c1-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="518c1-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="518c1-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="518c1-2840">iso 9362</span></span> 
- <span data-ttu-id="518c1-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="518c1-2841">iso9362</span></span> 
- <span data-ttu-id="518c1-2842">swift\#</span><span class="sxs-lookup"><span data-stu-id="518c1-2842">swift\#</span></span> 
- <span data-ttu-id="518c1-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="518c1-2843">swiftcode</span></span> 
- <span data-ttu-id="518c1-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-2844">swiftnumber</span></span> 
- <span data-ttu-id="518c1-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="518c1-2846">swift コード</span><span class="sxs-lookup"><span data-stu-id="518c1-2846">swift code</span></span> 
- <span data-ttu-id="518c1-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2847">swift number #</span></span> 
- <span data-ttu-id="518c1-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2848">swift routing number</span></span> 
- <span data-ttu-id="518c1-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2849">bic number</span></span> 
- <span data-ttu-id="518c1-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="518c1-2850">bic code</span></span> 
- <span data-ttu-id="518c1-2851">bic\#</span><span class="sxs-lookup"><span data-stu-id="518c1-2851">bic \#</span></span> 
- <span data-ttu-id="518c1-2852">bic\#</span><span class="sxs-lookup"><span data-stu-id="518c1-2852">bic\#</span></span> 
- <span data-ttu-id="518c1-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="518c1-2853">bank identifier code</span></span> 
- <span data-ttu-id="518c1-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="518c1-2854">標準化9362</span></span> 
- <span data-ttu-id="518c1-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-2855">迅速＃</span></span> 
- <span data-ttu-id="518c1-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="518c1-2856">SWIFTコード</span></span> 
- <span data-ttu-id="518c1-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2857">SWIFT番号</span></span> 
- <span data-ttu-id="518c1-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="518c1-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-2859">BIC番号</span></span> 
- <span data-ttu-id="518c1-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="518c1-2860">BICコード</span></span> 
- <span data-ttu-id="518c1-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="518c1-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="518c1-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="518c1-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="518c1-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="518c1-2863">rapide \#</span></span> 
- <span data-ttu-id="518c1-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="518c1-2864">code SWIFT</span></span> 
- <span data-ttu-id="518c1-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="518c1-2865">le numéro de swift</span></span> 
- <span data-ttu-id="518c1-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="518c1-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="518c1-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="518c1-2867">le numéro BIC</span></span> 
- <span data-ttu-id="518c1-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="518c1-2868">\# BIC</span></span> 
- <span data-ttu-id="518c1-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="518c1-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="518c1-2870">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="518c1-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2871">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2871">Format</span></span>

<span data-ttu-id="518c1-2872">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2873">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2873">Pattern</span></span>

<span data-ttu-id="518c1-2874">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="518c1-2875">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="518c1-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2876">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="518c1-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="518c1-2877">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2878">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2878">Checksum</span></span>

<span data-ttu-id="518c1-2879">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2880">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2880">Definition</span></span>

<span data-ttu-id="518c1-2881">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2882">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2883">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="518c1-2884">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2885">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="518c1-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="518c1-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="518c1-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="518c1-2887">身份證字號</span></span> 
- <span data-ttu-id="518c1-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2888">身份證</span></span> 
- <span data-ttu-id="518c1-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="518c1-2889">身份證號碼</span></span> 
- <span data-ttu-id="518c1-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="518c1-2890">身份證號</span></span> 
- <span data-ttu-id="518c1-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="518c1-2891">身分證字號</span></span> 
- <span data-ttu-id="518c1-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="518c1-2892">身分證</span></span> 
- <span data-ttu-id="518c1-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="518c1-2893">身分證號碼</span></span> 
- <span data-ttu-id="518c1-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="518c1-2894">身份證號</span></span> 
- <span data-ttu-id="518c1-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="518c1-2895">身分證統一編號</span></span> 
- <span data-ttu-id="518c1-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="518c1-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="518c1-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="518c1-2897">簽名</span></span> 
- <span data-ttu-id="518c1-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="518c1-2898">蓋章</span></span> 
- <span data-ttu-id="518c1-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="518c1-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="518c1-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="518c1-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="518c1-2901">台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2902">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2902">Format</span></span>

- <span data-ttu-id="518c1-2903">生体認証パスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="518c1-2904">非生体認証パスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2905">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2905">Pattern</span></span>
<span data-ttu-id="518c1-2906">生体認証パスポートの番号:</span><span class="sxs-lookup"><span data-stu-id="518c1-2906">Biometric passport number:</span></span>
- <span data-ttu-id="518c1-2907">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="518c1-2907">The digit "3"</span></span> 
- <span data-ttu-id="518c1-2908">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2908">Eight digits</span></span>

<span data-ttu-id="518c1-2909">非生体認証パスポートの番号:</span><span class="sxs-lookup"><span data-stu-id="518c1-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="518c1-2910">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2911">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2911">Checksum</span></span>

<span data-ttu-id="518c1-2912">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2913">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2913">Definition</span></span>

<span data-ttu-id="518c1-2914">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2915">正規表現 Regex_taiwan_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2916">Keyword_taiwan_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2917">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="518c1-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="518c1-2919">ROC passport number
</span><span class="sxs-lookup"><span data-stu-id="518c1-2919">ROC passport number</span></span> 
- <span data-ttu-id="518c1-2920">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2920">Passport number</span></span> 
- <span data-ttu-id="518c1-2921">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="518c1-2921">Passport no</span></span> 
- <span data-ttu-id="518c1-2922">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="518c1-2922">Passport Num</span></span> 
- <span data-ttu-id="518c1-2923">Passport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-2923">Passport #</span></span> 
- <span data-ttu-id="518c1-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="518c1-2924">护照</span></span> 
- <span data-ttu-id="518c1-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="518c1-2925">中華民國護照</span></span> 
- <span data-ttu-id="518c1-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="518c1-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="518c1-2927">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="518c1-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2928">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2928">Format</span></span>

<span data-ttu-id="518c1-2929">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2930">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2930">Pattern</span></span>

<span data-ttu-id="518c1-2931">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2931">10 letters and digits:</span></span>
- <span data-ttu-id="518c1-2932">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="518c1-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="518c1-2933">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2934">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2934">Checksum</span></span>

<span data-ttu-id="518c1-2935">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2936">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2936">Definition</span></span>

<span data-ttu-id="518c1-2937">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2938">正規表現 Regex_taiwan_resident_certificate がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2939">Keyword_taiwan_resident_certificate のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2940">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="518c1-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="518c1-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="518c1-2942">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="518c1-2942">Resident Certificate</span></span> 
- <span data-ttu-id="518c1-2943">常駐の証明書</span><span class="sxs-lookup"><span data-stu-id="518c1-2943">Resident Cert</span></span> 
- <span data-ttu-id="518c1-2944">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="518c1-2944">Resident Cert.</span></span> 
- <span data-ttu-id="518c1-2945">Id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-2945">Identification card</span></span> 
- <span data-ttu-id="518c1-2946">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="518c1-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="518c1-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="518c1-2947">ARC</span></span> 
- <span data-ttu-id="518c1-2948">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="518c1-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="518c1-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="518c1-2949">TARC</span></span> 
- <span data-ttu-id="518c1-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2950">居留證</span></span> 
- <span data-ttu-id="518c1-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2951">外僑居留證</span></span> 
- <span data-ttu-id="518c1-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="518c1-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="518c1-p141">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2955">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2955">Format</span></span>

<span data-ttu-id="518c1-2956">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2957">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2957">Pattern</span></span>

<span data-ttu-id="518c1-2958">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-2958">18 letters and digits:</span></span>
- <span data-ttu-id="518c1-2959">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="518c1-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="518c1-2960">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2960">One digit</span></span> 
- <span data-ttu-id="518c1-2961">誕生日を示す DDMMY という日付形式の 5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="518c1-2962">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="518c1-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="518c1-2963">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2964">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2964">Checksum</span></span>

<span data-ttu-id="518c1-2965">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2966">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2966">Definition</span></span>

<span data-ttu-id="518c1-2967">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2968">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2969">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="518c1-2970">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-2971">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="518c1-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="518c1-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="518c1-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="518c1-2973">DVLA</span></span> 
- <span data-ttu-id="518c1-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="518c1-2974">light vans</span></span> 
- <span data-ttu-id="518c1-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="518c1-2975">quadbikes</span></span> 
- <span data-ttu-id="518c1-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="518c1-2976">motor cars</span></span> 
- <span data-ttu-id="518c1-2977">125cc</span><span class="sxs-lookup"><span data-stu-id="518c1-2977">125cc</span></span> 
- <span data-ttu-id="518c1-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="518c1-2978">sidecar</span></span> 
- <span data-ttu-id="518c1-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="518c1-2979">tricycles</span></span> 
- <span data-ttu-id="518c1-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="518c1-2980">motorcycles</span></span> 
- <span data-ttu-id="518c1-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-2981">photocard licence</span></span> 
- <span data-ttu-id="518c1-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="518c1-2982">learner drivers</span></span> 
- <span data-ttu-id="518c1-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="518c1-2983">licence holder</span></span> 
- <span data-ttu-id="518c1-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="518c1-2984">licence holders</span></span> 
- <span data-ttu-id="518c1-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="518c1-2985">driving licences</span></span> 
- <span data-ttu-id="518c1-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="518c1-2986">driving licence</span></span> 
- <span data-ttu-id="518c1-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="518c1-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="518c1-p142">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="518c1-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-2990">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-2990">Format</span></span>

<span data-ttu-id="518c1-2991">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-2992">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-2992">Pattern</span></span>

<span data-ttu-id="518c1-2993">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-2994">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-2994">Checksum</span></span>

<span data-ttu-id="518c1-2995">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-2996">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-2996">Definition</span></span>

<span data-ttu-id="518c1-2997">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-2998">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-2999">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-3000">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="518c1-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="518c1-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="518c1-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="518c1-3002">council nomination</span></span> 
- <span data-ttu-id="518c1-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="518c1-3003">nomination form</span></span> 
- <span data-ttu-id="518c1-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="518c1-3004">electoral register</span></span> 
- <span data-ttu-id="518c1-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="518c1-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="518c1-p143">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="518c1-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3008">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3008">Format</span></span>

<span data-ttu-id="518c1-3009">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3010">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3010">Pattern</span></span>

<span data-ttu-id="518c1-3011">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="518c1-3011">10-17 digits:</span></span>
- <span data-ttu-id="518c1-3012">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="518c1-3013">スペース</span><span class="sxs-lookup"><span data-stu-id="518c1-3013">A space</span></span> 
- <span data-ttu-id="518c1-3014">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3014">Three digits</span></span> 
- <span data-ttu-id="518c1-3015">スペース</span><span class="sxs-lookup"><span data-stu-id="518c1-3015">A space</span></span> 
- <span data-ttu-id="518c1-3016">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3017">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3017">Checksum</span></span>

<span data-ttu-id="518c1-3018">はい</span><span class="sxs-lookup"><span data-stu-id="518c1-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-3019">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3019">Definition</span></span>

<span data-ttu-id="518c1-3020">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3021">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3022">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-3022">One of the following is true:</span></span>
    - <span data-ttu-id="518c1-3023">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="518c1-3024">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="518c1-3025">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="518c1-3026">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="518c1-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-3027">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="518c1-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="518c1-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="518c1-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="518c1-3029">national health service</span></span> 
- <span data-ttu-id="518c1-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="518c1-3030">nhs</span></span> 
- <span data-ttu-id="518c1-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="518c1-3031">health services authority</span></span> 
- <span data-ttu-id="518c1-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="518c1-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="518c1-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="518c1-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="518c1-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="518c1-3034">patient id</span></span> 
- <span data-ttu-id="518c1-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="518c1-3035">patient identification</span></span> 
- <span data-ttu-id="518c1-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="518c1-3036">patient no</span></span> 
- <span data-ttu-id="518c1-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="518c1-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="518c1-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="518c1-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="518c1-3039">GP</span><span class="sxs-lookup"><span data-stu-id="518c1-3039">GP</span></span> 
- <span data-ttu-id="518c1-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="518c1-3040">DOB</span></span> 
- <span data-ttu-id="518c1-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="518c1-3041">D.O.B</span></span> 
- <span data-ttu-id="518c1-3042">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="518c1-3042">Date of Birth</span></span> 
- <span data-ttu-id="518c1-3043">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="518c1-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="518c1-p144">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="518c1-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3046">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3046">Format</span></span>

<span data-ttu-id="518c1-3047">7 文字またはスペースまたはハイフンで区切られた 9 の文字</span><span class="sxs-lookup"><span data-stu-id="518c1-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3048">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3048">Pattern</span></span>

<span data-ttu-id="518c1-3049">2 つの可能なパターン:</span><span class="sxs-lookup"><span data-stu-id="518c1-3049">Two possible patterns:</span></span>

- <span data-ttu-id="518c1-3050">2 つの文字 (有効な NINOs では、特定の文字のみを使用して、このプレフィックスは、このパターンを検証します大文字と小文字を区別しない)。</span><span class="sxs-lookup"><span data-stu-id="518c1-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="518c1-3051">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3051">Six digits</span></span>
- <span data-ttu-id="518c1-3052">どちらか '、' 'B'、'C'、または必要がある ' (などの接頭辞、のみ特定の文字が許可、サフィックスのない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="518c1-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="518c1-3053">OR</span><span class="sxs-lookup"><span data-stu-id="518c1-3053">OR</span></span>

- <span data-ttu-id="518c1-3054">2 つの文字</span><span class="sxs-lookup"><span data-stu-id="518c1-3054">Two letters</span></span>
- <span data-ttu-id="518c1-3055">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-3055">A space or dash</span></span>
- <span data-ttu-id="518c1-3056">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3056">Two digits</span></span>
- <span data-ttu-id="518c1-3057">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-3057">A space or dash</span></span>
- <span data-ttu-id="518c1-3058">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3058">Two digits</span></span>
- <span data-ttu-id="518c1-3059">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-3059">A space or dash</span></span>
- <span data-ttu-id="518c1-3060">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3060">Two digits</span></span>
- <span data-ttu-id="518c1-3061">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-3061">A space or dash</span></span>
- <span data-ttu-id="518c1-3062">どちらか '、'、'B'、'C'、または必要がある '</span><span class="sxs-lookup"><span data-stu-id="518c1-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3063">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3063">Checksum</span></span>

<span data-ttu-id="518c1-3064">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-3065">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3065">Definition</span></span>

<span data-ttu-id="518c1-3066">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3067">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3068">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="518c1-3069">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3070">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3071">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-3072">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="518c1-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="518c1-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="518c1-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3074">national insurance number</span></span> 
- <span data-ttu-id="518c1-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="518c1-3075">national insurance contributions</span></span> 
- <span data-ttu-id="518c1-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="518c1-3076">protection act</span></span> 
- <span data-ttu-id="518c1-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="518c1-3077">insurance</span></span> 
- <span data-ttu-id="518c1-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3078">social security number</span></span> 
- <span data-ttu-id="518c1-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="518c1-3079">insurance application</span></span> 
- <span data-ttu-id="518c1-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="518c1-3080">medical application</span></span> 
- <span data-ttu-id="518c1-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="518c1-3081">social insurance</span></span> 
- <span data-ttu-id="518c1-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="518c1-3082">medical attention</span></span> 
- <span data-ttu-id="518c1-3083">社会保障</span><span class="sxs-lookup"><span data-stu-id="518c1-3083">social security</span></span> 
- <span data-ttu-id="518c1-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="518c1-3084">great britain</span></span> 
- <span data-ttu-id="518c1-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="518c1-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="518c1-p145">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="518c1-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3088">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3088">Format</span></span>

<span data-ttu-id="518c1-3089">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3090">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3090">Pattern</span></span>

<span data-ttu-id="518c1-3091">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3092">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3092">Checksum</span></span>

<span data-ttu-id="518c1-3093">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-3094">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3094">Definition</span></span>

<span data-ttu-id="518c1-3095">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3096">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3097">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-3098">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="518c1-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="518c1-3099">Keyword_passport</span></span>

- <span data-ttu-id="518c1-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="518c1-3100">Passport Number</span></span> 
- <span data-ttu-id="518c1-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="518c1-3101">Passport No</span></span> 
- <span data-ttu-id="518c1-3102">Passport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3102">Passport #</span></span> 
- <span data-ttu-id="518c1-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3103">Passport#</span></span> 
- <span data-ttu-id="518c1-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="518c1-3104">PassportID</span></span> 
- <span data-ttu-id="518c1-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="518c1-3105">Passportno</span></span> 
- <span data-ttu-id="518c1-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="518c1-3106">passportnumber</span></span> 
- <span data-ttu-id="518c1-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="518c1-3107">パスポート</span></span> 
- <span data-ttu-id="518c1-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="518c1-3108">パスポート番号</span></span> 
- <span data-ttu-id="518c1-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="518c1-3109">パスポートのNum</span></span> 
- <span data-ttu-id="518c1-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="518c1-3110">パスポート＃</span></span> 
- <span data-ttu-id="518c1-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="518c1-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="518c1-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="518c1-3112">Passeport n °</span></span> 
- <span data-ttu-id="518c1-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="518c1-3113">Passeport Non</span></span> 
- <span data-ttu-id="518c1-3114">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3114">Passeport #</span></span> 
- <span data-ttu-id="518c1-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3115">Passeport#</span></span> 
- <span data-ttu-id="518c1-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="518c1-3116">PasseportNon</span></span> 
- <span data-ttu-id="518c1-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="518c1-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="518c1-3118">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="518c1-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3119">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3119">Format</span></span>

<span data-ttu-id="518c1-3120">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3121">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3121">Pattern</span></span>

<span data-ttu-id="518c1-3122">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3123">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3123">Checksum</span></span>

<span data-ttu-id="518c1-3124">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-3125">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3125">Definition</span></span>

<span data-ttu-id="518c1-3126">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3127">正規表現 Regex_usa_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3128">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="518c1-3129">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="518c1-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="518c1-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="518c1-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3131">Checking Account Number</span></span> 
- <span data-ttu-id="518c1-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="518c1-3132">Checking Account</span></span> 
- <span data-ttu-id="518c1-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3133">Checking Account #</span></span> 
- <span data-ttu-id="518c1-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="518c1-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3135">Checking Acct #</span></span> 
- <span data-ttu-id="518c1-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="518c1-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3137">Checking Account No.</span></span> 
- <span data-ttu-id="518c1-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3138">Bank Account Number</span></span> 
- <span data-ttu-id="518c1-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3139">Bank Account #</span></span> 
- <span data-ttu-id="518c1-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="518c1-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3141">Bank Acct #</span></span> 
- <span data-ttu-id="518c1-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="518c1-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3143">Bank Account No.</span></span> 
- <span data-ttu-id="518c1-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3144">Savings Account Number</span></span> 
- <span data-ttu-id="518c1-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3145">Savings Account.</span></span> 
- <span data-ttu-id="518c1-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3146">Savings Account #</span></span> 
- <span data-ttu-id="518c1-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="518c1-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3148">Savings Acct #</span></span> 
- <span data-ttu-id="518c1-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="518c1-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3150">Savings Account No.</span></span> 
- <span data-ttu-id="518c1-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3151">Debit Account Number</span></span> 
- <span data-ttu-id="518c1-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="518c1-3152">Debit Account</span></span> 
- <span data-ttu-id="518c1-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3153">Debit Account #</span></span> 
- <span data-ttu-id="518c1-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="518c1-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3155">Debit Acct #</span></span> 
- <span data-ttu-id="518c1-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="518c1-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="518c1-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="518c1-3158">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3159">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3159">Format</span></span>

<span data-ttu-id="518c1-3160">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="518c1-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3161">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3161">Pattern</span></span>

<span data-ttu-id="518c1-3162">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="518c1-3163">ddd ddd ddd のような形式の 9 桁の数字がマッチします。</span><span class="sxs-lookup"><span data-stu-id="518c1-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="518c1-3164">ddddddddd のような 9 桁の数字はマッチしません。</span><span class="sxs-lookup"><span data-stu-id="518c1-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3165">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3165">Checksum</span></span>

<span data-ttu-id="518c1-3166">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-3167">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3167">Definition</span></span>

<span data-ttu-id="518c1-3168">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3169">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3170">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="518c1-3171">Keyword_us_drivers_license のキーワードを検出しました。</span><span class="sxs-lookup"><span data-stu-id="518c1-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="518c1-3172">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3173">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3174">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="518c1-3175">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="518c1-3176">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-3177">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="518c1-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="518c1-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="518c1-3179">DL</span><span class="sxs-lookup"><span data-stu-id="518c1-3179">DL</span></span> 
- <span data-ttu-id="518c1-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="518c1-3180">DLS</span></span> 
- <span data-ttu-id="518c1-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="518c1-3181">CDL</span></span> 
- <span data-ttu-id="518c1-3182">CDL</span><span class="sxs-lookup"><span data-stu-id="518c1-3182">CDLS</span></span> 
- <span data-ttu-id="518c1-3183">ID</span><span class="sxs-lookup"><span data-stu-id="518c1-3183">ID</span></span> 
- <span data-ttu-id="518c1-3184">Id</span><span class="sxs-lookup"><span data-stu-id="518c1-3184">IDs</span></span> 
- <span data-ttu-id="518c1-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="518c1-3185">DL#</span></span> 
- <span data-ttu-id="518c1-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3186">DLS#</span></span> 
- <span data-ttu-id="518c1-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3187">CDL#</span></span> 
- <span data-ttu-id="518c1-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3188">CDLS#</span></span> 
- <span data-ttu-id="518c1-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="518c1-3189">ID#</span></span>
- <span data-ttu-id="518c1-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3190">IDs#</span></span> 
- <span data-ttu-id="518c1-3191">ID number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3191">ID number</span></span> 
- <span data-ttu-id="518c1-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-3192">ID numbers</span></span> 
- <span data-ttu-id="518c1-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="518c1-3193">LIC</span></span> 
- <span data-ttu-id="518c1-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="518c1-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="518c1-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="518c1-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="518c1-3196">DriverLic</span></span> 
- <span data-ttu-id="518c1-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="518c1-3197">DriverLics</span></span> 
- <span data-ttu-id="518c1-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="518c1-3198">DriverLicense</span></span> 
- <span data-ttu-id="518c1-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-3199">DriverLicenses</span></span> 
- <span data-ttu-id="518c1-3200">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-3200">Driver Lic</span></span> 
- <span data-ttu-id="518c1-3201">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-3201">Driver Lics</span></span> 
- <span data-ttu-id="518c1-3202">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-3202">Driver License</span></span> 
- <span data-ttu-id="518c1-3203">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-3203">Driver Licenses</span></span> 
- <span data-ttu-id="518c1-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="518c1-3204">DriversLic</span></span> 
- <span data-ttu-id="518c1-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="518c1-3205">DriversLics</span></span> 
- <span data-ttu-id="518c1-3206">証</span><span class="sxs-lookup"><span data-stu-id="518c1-3206">DriversLicense</span></span> 
- <span data-ttu-id="518c1-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-3207">DriversLicenses</span></span> 
- <span data-ttu-id="518c1-3208">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-3208">Drivers Lic</span></span> 
- <span data-ttu-id="518c1-3209">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-3209">Drivers Lics</span></span> 
- <span data-ttu-id="518c1-3210">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-3210">Drivers License</span></span> 
- <span data-ttu-id="518c1-3211">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="518c1-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-3212">Driver'Lic</span></span> 
- <span data-ttu-id="518c1-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-3213">Driver'Lics</span></span> 
- <span data-ttu-id="518c1-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="518c1-3214">Driver'License</span></span> 
- <span data-ttu-id="518c1-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="518c1-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="518c1-3216">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-3216">Driver' Lic</span></span> 
- <span data-ttu-id="518c1-3217">ドライバー ' Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-3217">Driver' Lics</span></span> 
- <span data-ttu-id="518c1-3218">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-3218">Driver' License</span></span> 
- <span data-ttu-id="518c1-3219">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="518c1-3219">Driver' Licenses</span></span>
- <span data-ttu-id="518c1-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="518c1-3220">Driver'sLic</span></span> 
- <span data-ttu-id="518c1-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="518c1-3221">Driver'sLics</span></span> 
- <span data-ttu-id="518c1-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="518c1-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="518c1-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="518c1-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="518c1-3224">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="518c1-3224">Driver's Lic</span></span> 
- <span data-ttu-id="518c1-3225">ドライバーの Lics</span><span class="sxs-lookup"><span data-stu-id="518c1-3225">Driver's Lics</span></span> 
- <span data-ttu-id="518c1-3226">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-3226">Driver's License</span></span> 
- <span data-ttu-id="518c1-3227">運転免許証</span><span class="sxs-lookup"><span data-stu-id="518c1-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="518c1-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="518c1-3228">identification number</span></span> 
- <span data-ttu-id="518c1-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="518c1-3229">identification numbers</span></span> 
- <span data-ttu-id="518c1-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="518c1-3230">identification #</span></span> 
- <span data-ttu-id="518c1-3231">id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-3231">id card</span></span> 
- <span data-ttu-id="518c1-3232">id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-3232">id cards</span></span> 
- <span data-ttu-id="518c1-3233">id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-3233">identification card</span></span> 
- <span data-ttu-id="518c1-3234">id カード</span><span class="sxs-lookup"><span data-stu-id="518c1-3234">identification cards</span></span> 
- <span data-ttu-id="518c1-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-3235">DriverLic#</span></span> 
- <span data-ttu-id="518c1-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-3236">DriverLics#</span></span> 
- <span data-ttu-id="518c1-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="518c1-3237">DriverLicense#</span></span> 
- <span data-ttu-id="518c1-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="518c1-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="518c1-3239">Driver Lic#</span></span> 
- <span data-ttu-id="518c1-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3240">Driver Lics#</span></span> 
- <span data-ttu-id="518c1-3241">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-3241">Driver License#</span></span> 
- <span data-ttu-id="518c1-3242">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="518c1-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-3243">DriversLic#</span></span> 
- <span data-ttu-id="518c1-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-3244">DriversLics#</span></span> 
- <span data-ttu-id="518c1-3245">証番号</span><span class="sxs-lookup"><span data-stu-id="518c1-3245">DriversLicense#</span></span> 
- <span data-ttu-id="518c1-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="518c1-3247">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="518c1-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="518c1-3248">ドライバー Lics #</span><span class="sxs-lookup"><span data-stu-id="518c1-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="518c1-3249">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-3249">Drivers License#</span></span> 
- <span data-ttu-id="518c1-3250">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="518c1-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="518c1-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="518c1-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="518c1-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3253">Driver'License#</span></span> 
- <span data-ttu-id="518c1-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="518c1-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="518c1-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="518c1-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3257">Driver' License#</span></span> 
- <span data-ttu-id="518c1-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="518c1-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="518c1-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="518c1-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="518c1-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="518c1-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="518c1-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="518c1-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="518c1-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="518c1-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="518c1-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="518c1-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3265">Driver's License#</span></span> 
- <span data-ttu-id="518c1-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="518c1-3267">id のカード番号</span><span class="sxs-lookup"><span data-stu-id="518c1-3267">id card#</span></span> 
- <span data-ttu-id="518c1-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3268">id cards#</span></span> 
- <span data-ttu-id="518c1-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3269">identification card#</span></span> 
- <span data-ttu-id="518c1-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="518c1-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="518c1-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="518c1-3272">州の略号 (たとえば、"NY")
</span><span class="sxs-lookup"><span data-stu-id="518c1-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="518c1-3273">州の名前 (たとえば、"New York")
</span><span class="sxs-lookup"><span data-stu-id="518c1-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="518c1-3274">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="518c1-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3275">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3275">Format</span></span>

<span data-ttu-id="518c1-3276">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="518c1-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3277">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3277">Pattern</span></span>

<span data-ttu-id="518c1-3278">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-3278">Formatted:</span></span>
- <span data-ttu-id="518c1-3279">数字「9」</span><span class="sxs-lookup"><span data-stu-id="518c1-3279">The digit "9"</span></span> 
- <span data-ttu-id="518c1-3280">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3280">Two digits</span></span> 
- <span data-ttu-id="518c1-3281">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-3281">A space or dash</span></span> 
- <span data-ttu-id="518c1-3282">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="518c1-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="518c1-3283">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3283">A digit</span></span> 
- <span data-ttu-id="518c1-3284">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="518c1-3284">A space, or dash</span></span> 
- <span data-ttu-id="518c1-3285">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3285">Four digits</span></span>

<span data-ttu-id="518c1-3286">書式設定されていない場合:</span><span class="sxs-lookup"><span data-stu-id="518c1-3286">Unformatted:</span></span>
- <span data-ttu-id="518c1-3287">数字「9」</span><span class="sxs-lookup"><span data-stu-id="518c1-3287">The digit "9"</span></span> 
- <span data-ttu-id="518c1-3288">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3288">Two digits</span></span> 
- <span data-ttu-id="518c1-3289">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="518c1-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="518c1-3290">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3291">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3291">Checksum</span></span>

<span data-ttu-id="518c1-3292">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="518c1-3293">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3293">Definition</span></span>

<span data-ttu-id="518c1-3294">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3295">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3296">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="518c1-3297">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="518c1-3298">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="518c1-3299">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="518c1-3300">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="518c1-3301">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3302">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3303">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="518c1-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="518c1-3304">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="518c1-3305">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="518c1-3306">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-3307">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="518c1-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="518c1-3308">Keyword_itin</span></span>

- <span data-ttu-id="518c1-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="518c1-3309">taxpayer</span></span> 
- <span data-ttu-id="518c1-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="518c1-3310">tax id</span></span> 
- <span data-ttu-id="518c1-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="518c1-3311">tax identification</span></span> 
- <span data-ttu-id="518c1-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="518c1-3312">itin</span></span> 
- <span data-ttu-id="518c1-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="518c1-3313">ssn</span></span> 
- <span data-ttu-id="518c1-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="518c1-3314">tin</span></span> 
- <span data-ttu-id="518c1-3315">社会保障</span><span class="sxs-lookup"><span data-stu-id="518c1-3315">social security</span></span> 
- <span data-ttu-id="518c1-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="518c1-3316">tax payer</span></span> 
- <span data-ttu-id="518c1-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="518c1-3317">itins</span></span> 
- <span data-ttu-id="518c1-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="518c1-3318">taxid</span></span> 
- <span data-ttu-id="518c1-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="518c1-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="518c1-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="518c1-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="518c1-3321">License</span><span class="sxs-lookup"><span data-stu-id="518c1-3321">License</span></span> 
- <span data-ttu-id="518c1-3322">DL</span><span class="sxs-lookup"><span data-stu-id="518c1-3322">DL</span></span> 
- <span data-ttu-id="518c1-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="518c1-3323">DOB</span></span> 
- <span data-ttu-id="518c1-3324">誕生日</span><span class="sxs-lookup"><span data-stu-id="518c1-3324">Birthdate</span></span> 
- <span data-ttu-id="518c1-3325">誕生日 </span><span class="sxs-lookup"><span data-stu-id="518c1-3325">Birthday</span></span> 
- <span data-ttu-id="518c1-3326">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="518c1-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="518c1-3327">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="518c1-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="518c1-3328">形式</span><span class="sxs-lookup"><span data-stu-id="518c1-3328">Format</span></span>

<span data-ttu-id="518c1-3329">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="518c1-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="518c1-3330">2011 年の中旬より前に発行されている場合、SSN には厳密な書式があり、数値の特定の部分が一定の範囲内に入っていなければ有効になりません。</span><span class="sxs-lookup"><span data-stu-id="518c1-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="518c1-3331">パターン</span><span class="sxs-lookup"><span data-stu-id="518c1-3331">Pattern</span></span>

<span data-ttu-id="518c1-3332">4 つの異なるパターンで SSN を検索する 4 つの関数を次に示します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="518c1-3333">Func_ssn は 2011 年以前の、厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="518c1-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="518c1-3334">Func_unformatted_ssn は 2011 年以前の、厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="518c1-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="518c1-3335">Func_randomized_formatted_ssn は 2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="518c1-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="518c1-3336">Func_randomized_unformatted_ssn は 2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="518c1-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="518c1-3337">チェックサム</span><span class="sxs-lookup"><span data-stu-id="518c1-3337">Checksum</span></span>

<span data-ttu-id="518c1-3338">なし</span><span class="sxs-lookup"><span data-stu-id="518c1-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="518c1-3339">定義</span><span class="sxs-lookup"><span data-stu-id="518c1-3339">Definition</span></span>

<span data-ttu-id="518c1-3340">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3341">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3342">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="518c1-3343">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3344">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3345">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="518c1-3346">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3347">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3348">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="518c1-3349">関数 Func_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="518c1-3350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="518c1-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="518c1-3351">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="518c1-3352">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="518c1-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="518c1-3353">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="518c1-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="518c1-3354">キーワード</span><span class="sxs-lookup"><span data-stu-id="518c1-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="518c1-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="518c1-3355">Keyword_ssn</span></span>

- <span data-ttu-id="518c1-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="518c1-3356">Social Security</span></span> 
- <span data-ttu-id="518c1-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3357">Social Security#</span></span> 
- <span data-ttu-id="518c1-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="518c1-3358">Soc Sec</span></span> 
- <span data-ttu-id="518c1-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="518c1-3359">SSN</span></span> 
- <span data-ttu-id="518c1-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="518c1-3360">SSNS</span></span> 
- <span data-ttu-id="518c1-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3361">SSN#</span></span> 
- <span data-ttu-id="518c1-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="518c1-3362">SS#</span></span> 
- <span data-ttu-id="518c1-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="518c1-3363">SSID</span></span> 
   

