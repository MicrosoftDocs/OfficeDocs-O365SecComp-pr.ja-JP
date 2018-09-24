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
ms.openlocfilehash: 2e59b322730ca7fa828a685ed3a80c48ebdbbfd8
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972359"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="55801-104">機密情報の種類の検索基準：</span><span class="sxs-lookup"><span data-stu-id="55801-104">What the sensitive information types look for</span></span>

<span data-ttu-id="55801-p102">Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、機密性の高い情報の種類のすべてを一覧表示しを示しています DLP ポリシーそれぞれの種類を検出したとき。機密性の高い情報の種類は、正規表現、または関数を識別可能なパターンによって定義されます。さらに、機密性の高い情報の種類を識別するキーワードやチェックサムなどの corroborative の証拠を使用できます。信頼レベルと近接は、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="55801-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="55801-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="55801-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-111">形式</span><span class="sxs-lookup"><span data-stu-id="55801-111">Format</span></span>

<span data-ttu-id="55801-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-113">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-113">Pattern</span></span>

<span data-ttu-id="55801-114">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="55801-114">Formatted:</span></span>
- <span data-ttu-id="55801-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="55801-116">ハイフン</span><span class="sxs-lookup"><span data-stu-id="55801-116">A hyphen</span></span>
- <span data-ttu-id="55801-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-117">Four digits</span></span>
- <span data-ttu-id="55801-118">ハイフン</span><span class="sxs-lookup"><span data-stu-id="55801-118">A hyphen</span></span>
- <span data-ttu-id="55801-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-119">A digit</span></span>

<span data-ttu-id="55801-120">以降では 0、1、2、3、6、7、8 または 9 連続した数字をフォーマットします。</span><span class="sxs-lookup"><span data-stu-id="55801-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="55801-121">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-121">Checksum</span></span>

<span data-ttu-id="55801-122">なし</span><span class="sxs-lookup"><span data-stu-id="55801-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-123">定義</span><span class="sxs-lookup"><span data-stu-id="55801-123">Definition</span></span>

<span data-ttu-id="55801-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="55801-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="55801-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="55801-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="55801-129">aba</span><span class="sxs-lookup"><span data-stu-id="55801-129">aba</span></span>
- <span data-ttu-id="55801-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="55801-130">aba #</span></span>
- <span data-ttu-id="55801-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="55801-131">aba routing #</span></span>
- <span data-ttu-id="55801-132">aba ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="55801-132">aba routing number</span></span>
- <span data-ttu-id="55801-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="55801-133">aba#</span></span>
- <span data-ttu-id="55801-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="55801-134">abarouting#</span></span>
- <span data-ttu-id="55801-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="55801-135">aba number</span></span>
- <span data-ttu-id="55801-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="55801-136">abaroutingnumber</span></span>
- <span data-ttu-id="55801-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="55801-137">american bank association routing #</span></span>
- <span data-ttu-id="55801-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="55801-138">american bank association routing number</span></span>
- <span data-ttu-id="55801-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="55801-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="55801-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="55801-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="55801-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="55801-141">bank routing number</span></span>
- <span data-ttu-id="55801-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="55801-142">bankrouting#</span></span>
- <span data-ttu-id="55801-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="55801-143">bankroutingnumber</span></span>
- <span data-ttu-id="55801-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="55801-144">routing transit number</span></span>
- <span data-ttu-id="55801-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="55801-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="55801-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-147">形式</span><span class="sxs-lookup"><span data-stu-id="55801-147">Format</span></span>

<span data-ttu-id="55801-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-149">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-149">Pattern</span></span>

<span data-ttu-id="55801-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-150">Eight digits:</span></span>
- <span data-ttu-id="55801-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-151">Two digits</span></span>
- <span data-ttu-id="55801-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-152">A period</span></span>
- <span data-ttu-id="55801-153">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-153">Three digits</span></span>
- <span data-ttu-id="55801-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-154">A period</span></span>
- <span data-ttu-id="55801-155">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-156">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-156">Checksum</span></span>

<span data-ttu-id="55801-157">なし</span><span class="sxs-lookup"><span data-stu-id="55801-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-158">定義</span><span class="sxs-lookup"><span data-stu-id="55801-158">Definition</span></span>

<span data-ttu-id="55801-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-160">正規表現 Regex_argentina_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-161">Keyword_argentina_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="55801-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="55801-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="55801-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="55801-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="55801-165">ID</span><span class="sxs-lookup"><span data-stu-id="55801-165">Identity</span></span> 
- <span data-ttu-id="55801-166">国家身分証明書の識別</span><span class="sxs-lookup"><span data-stu-id="55801-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="55801-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="55801-167">DNI</span></span> 
- <span data-ttu-id="55801-168">担当者の NIC の国別レジストリ</span><span class="sxs-lookup"><span data-stu-id="55801-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="55801-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="55801-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="55801-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="55801-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="55801-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="55801-171">Identidad</span></span> 
- <span data-ttu-id="55801-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="55801-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="55801-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-174">形式</span><span class="sxs-lookup"><span data-stu-id="55801-174">Format</span></span>

<span data-ttu-id="55801-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-176">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-176">Pattern</span></span>

<span data-ttu-id="55801-p103">勘定番号は、6-10 桁の数字です。オーストラリアの銀行の状態の枝番号。</span><span class="sxs-lookup"><span data-stu-id="55801-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="55801-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-179">Three digits</span></span> 
- <span data-ttu-id="55801-180">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-180">A hyphen</span></span> 
- <span data-ttu-id="55801-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-182">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-182">Checksum</span></span>

<span data-ttu-id="55801-183">なし</span><span class="sxs-lookup"><span data-stu-id="55801-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-184">定義</span><span class="sxs-lookup"><span data-stu-id="55801-184">Definition</span></span>

<span data-ttu-id="55801-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="55801-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="55801-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="55801-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="55801-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="55801-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="55801-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="55801-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="55801-194">swift bank code</span></span>
- <span data-ttu-id="55801-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="55801-195">correspondent bank</span></span>
- <span data-ttu-id="55801-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="55801-196">base currency</span></span>
- <span data-ttu-id="55801-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="55801-197">usa account</span></span>
- <span data-ttu-id="55801-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="55801-198">holder address</span></span>
- <span data-ttu-id="55801-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="55801-199">bank address</span></span>
- <span data-ttu-id="55801-200">
information account</span><span class="sxs-lookup"><span data-stu-id="55801-200">information account</span></span>
- <span data-ttu-id="55801-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="55801-201">fund transfers</span></span>
- <span data-ttu-id="55801-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="55801-202">bank charges</span></span>
- <span data-ttu-id="55801-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="55801-203">bank details</span></span>
- <span data-ttu-id="55801-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="55801-204">banking information</span></span>
- <span data-ttu-id="55801-205">
full names</span><span class="sxs-lookup"><span data-stu-id="55801-205">full names</span></span>
- <span data-ttu-id="55801-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="55801-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="55801-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-208">形式</span><span class="sxs-lookup"><span data-stu-id="55801-208">Format</span></span>

<span data-ttu-id="55801-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="55801-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-210">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-210">Pattern</span></span>

<span data-ttu-id="55801-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="55801-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="55801-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="55801-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-213">Two digits</span></span> 
- <span data-ttu-id="55801-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="55801-215">または</span><span class="sxs-lookup"><span data-stu-id="55801-215">OR</span></span>

- <span data-ttu-id="55801-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="55801-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-217">4-9 digits</span></span>

<span data-ttu-id="55801-218">または</span><span class="sxs-lookup"><span data-stu-id="55801-218">OR</span></span>

- <span data-ttu-id="55801-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="55801-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-220">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-220">Checksum</span></span>

<span data-ttu-id="55801-221">なし</span><span class="sxs-lookup"><span data-stu-id="55801-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-222">定義</span><span class="sxs-lookup"><span data-stu-id="55801-222">Definition</span></span>

<span data-ttu-id="55801-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="55801-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="55801-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="55801-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="55801-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="55801-229">international driving permits</span></span>
- <span data-ttu-id="55801-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="55801-230">australian automobile association</span></span>
- <span data-ttu-id="55801-231">
sydney nsw</span><span class="sxs-lookup"><span data-stu-id="55801-231">sydney nsw</span></span>
- <span data-ttu-id="55801-232">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="55801-232">international driving permit</span></span>
- <span data-ttu-id="55801-233">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="55801-233">DriverLicence</span></span>
- <span data-ttu-id="55801-234">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="55801-234">DriverLicences</span></span>
- <span data-ttu-id="55801-235">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-235">Driver Lic</span></span>
- <span data-ttu-id="55801-236">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-236">Driver Licence</span></span>
- <span data-ttu-id="55801-237">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-237">Driver Licences</span></span>
- <span data-ttu-id="55801-238">DriversLic</span><span class="sxs-lookup"><span data-stu-id="55801-238">DriversLic</span></span>
- <span data-ttu-id="55801-239">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="55801-239">DriversLicence</span></span>
- <span data-ttu-id="55801-240">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="55801-240">DriversLicences</span></span>
- <span data-ttu-id="55801-241">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-241">Drivers Lic</span></span>
- <span data-ttu-id="55801-242">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="55801-242">Drivers Lics</span></span>
- <span data-ttu-id="55801-243">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-243">Drivers Licence</span></span>
- <span data-ttu-id="55801-244">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-244">Drivers Licences</span></span>
- <span data-ttu-id="55801-245">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="55801-245">Driver'Lic</span></span>
- <span data-ttu-id="55801-246">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="55801-246">Driver'Lics</span></span>
- <span data-ttu-id="55801-247">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="55801-247">Driver'Licence</span></span>
- <span data-ttu-id="55801-248">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="55801-248">Driver'Licences</span></span>
- <span data-ttu-id="55801-249">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="55801-249">Driver' Lic</span></span>
- <span data-ttu-id="55801-250">ドライバー ' Lics</span><span class="sxs-lookup"><span data-stu-id="55801-250">Driver' Lics</span></span>
- <span data-ttu-id="55801-251">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-251">Driver' Licence</span></span>
- <span data-ttu-id="55801-252">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-252">Driver' Licences</span></span>
- <span data-ttu-id="55801-253">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="55801-253">Driver'sLic</span></span>
- <span data-ttu-id="55801-254">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="55801-254">Driver'sLics</span></span>
- <span data-ttu-id="55801-255">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="55801-255">Driver'sLicence</span></span>
- <span data-ttu-id="55801-256">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="55801-256">Driver'sLicences</span></span>
- <span data-ttu-id="55801-257">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="55801-257">Driver's Lic</span></span>
- <span data-ttu-id="55801-258">ドライバーの Lics</span><span class="sxs-lookup"><span data-stu-id="55801-258">Driver's Lics</span></span>
- <span data-ttu-id="55801-259">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-259">Driver's Licence</span></span>
- <span data-ttu-id="55801-260">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-260">Driver's Licences</span></span>
- <span data-ttu-id="55801-261">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="55801-261">DriverLic#</span></span>
- <span data-ttu-id="55801-262">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="55801-262">DriverLics#</span></span>
- <span data-ttu-id="55801-263">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="55801-263">DriverLicence#</span></span>
- <span data-ttu-id="55801-264">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="55801-264">DriverLicences#</span></span>
- <span data-ttu-id="55801-265">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="55801-265">Driver Lic#</span></span>
- <span data-ttu-id="55801-266">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-266">Driver Lics#</span></span>
- <span data-ttu-id="55801-267">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-267">Driver Licence#</span></span>
- <span data-ttu-id="55801-268">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-268">Driver Licences#</span></span>
- <span data-ttu-id="55801-269">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="55801-269">DriversLic#</span></span>
- <span data-ttu-id="55801-270">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="55801-270">DriversLics#</span></span>
- <span data-ttu-id="55801-271">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="55801-271">DriversLicence#</span></span>
- <span data-ttu-id="55801-272">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="55801-272">DriversLicences#</span></span>
- <span data-ttu-id="55801-273">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="55801-273">Drivers Lic#</span></span>
- <span data-ttu-id="55801-274">ドライバー Lics #</span><span class="sxs-lookup"><span data-stu-id="55801-274">Drivers Lics#</span></span>
- <span data-ttu-id="55801-275">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-275">Drivers Licence#</span></span>
- <span data-ttu-id="55801-276">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-276">Drivers Licences#</span></span>
- <span data-ttu-id="55801-277">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-277">Driver'Lic#</span></span>
- <span data-ttu-id="55801-278">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-278">Driver'Lics#</span></span>
- <span data-ttu-id="55801-279">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="55801-279">Driver'Licence#</span></span>
- <span data-ttu-id="55801-280">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="55801-280">Driver'Licences#</span></span>
- <span data-ttu-id="55801-281">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-281">Driver' Lic#</span></span>
- <span data-ttu-id="55801-282">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-282">Driver' Lics#</span></span>
- <span data-ttu-id="55801-283">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-283">Driver' Licence#</span></span>
- <span data-ttu-id="55801-284">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-284">Driver' Licences#</span></span>
- <span data-ttu-id="55801-285">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="55801-285">Driver'sLic#</span></span>
- <span data-ttu-id="55801-286">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="55801-286">Driver'sLics#</span></span>
- <span data-ttu-id="55801-287">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="55801-287">Driver'sLicence#</span></span>
- <span data-ttu-id="55801-288">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="55801-288">Driver'sLicences#</span></span>
- <span data-ttu-id="55801-289">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-289">Driver's Lic#</span></span>
- <span data-ttu-id="55801-290">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-290">Driver's Lics#</span></span>
- <span data-ttu-id="55801-291">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-291">Driver's Licence#</span></span>
- <span data-ttu-id="55801-292">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-292">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="55801-293">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="55801-293">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="55801-294">aaa</span><span class="sxs-lookup"><span data-stu-id="55801-294">aaa</span></span>
- <span data-ttu-id="55801-295">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="55801-295">DriverLicense</span></span>
- <span data-ttu-id="55801-296">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-296">DriverLicenses</span></span>
- <span data-ttu-id="55801-297">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-297">Driver License</span></span>
- <span data-ttu-id="55801-298">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-298">Driver Licenses</span></span>
- <span data-ttu-id="55801-299">証</span><span class="sxs-lookup"><span data-stu-id="55801-299">DriversLicense</span></span>
- <span data-ttu-id="55801-300">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-300">DriversLicenses</span></span>
- <span data-ttu-id="55801-301">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-301">Drivers License</span></span>
- <span data-ttu-id="55801-302">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-302">Drivers Licenses</span></span>
- <span data-ttu-id="55801-303">Driver'License</span><span class="sxs-lookup"><span data-stu-id="55801-303">Driver'License</span></span>
- <span data-ttu-id="55801-304">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="55801-304">Driver'Licenses</span></span>
- <span data-ttu-id="55801-305">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-305">Driver' License</span></span>
- <span data-ttu-id="55801-306">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-306">Driver' Licenses</span></span>
- <span data-ttu-id="55801-307">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="55801-307">Driver'sLicense</span></span>
- <span data-ttu-id="55801-308">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-308">Driver'sLicenses</span></span>
- <span data-ttu-id="55801-309">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-309">Driver's License</span></span>
- <span data-ttu-id="55801-310">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-310">Driver's Licenses</span></span>
- <span data-ttu-id="55801-311">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="55801-311">DriverLicense#</span></span>
- <span data-ttu-id="55801-312">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-312">DriverLicenses#</span></span>
- <span data-ttu-id="55801-313">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-313">Driver License#</span></span>
- <span data-ttu-id="55801-314">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-314">Driver Licenses#</span></span>
- <span data-ttu-id="55801-315">証番号</span><span class="sxs-lookup"><span data-stu-id="55801-315">DriversLicense#</span></span>
- <span data-ttu-id="55801-316">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-316">DriversLicenses#</span></span>
- <span data-ttu-id="55801-317">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-317">Drivers License#</span></span>
- <span data-ttu-id="55801-318">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-318">Drivers Licenses#</span></span>
- <span data-ttu-id="55801-319">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="55801-319">Driver'License#</span></span>
- <span data-ttu-id="55801-320">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-320">Driver'Licenses#</span></span>
- <span data-ttu-id="55801-321">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="55801-321">Driver' License#</span></span>
- <span data-ttu-id="55801-322">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-322">Driver' Licenses#</span></span>
- <span data-ttu-id="55801-323">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="55801-323">Driver'sLicense#</span></span>
- <span data-ttu-id="55801-324">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-324">Driver'sLicenses#</span></span>
- <span data-ttu-id="55801-325">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="55801-325">Driver's License#</span></span>
- <span data-ttu-id="55801-326">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="55801-326">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="55801-327">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-327">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-328">形式</span><span class="sxs-lookup"><span data-stu-id="55801-328">Format</span></span>

<span data-ttu-id="55801-329">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-329">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-330">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-330">Pattern</span></span>

<span data-ttu-id="55801-331">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-331">10-11 digits:</span></span>
- <span data-ttu-id="55801-332">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="55801-332">First digit is in the range 2-6</span></span>
- <span data-ttu-id="55801-333">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="55801-333">Ninth digit is a check digit</span></span>
- <span data-ttu-id="55801-334">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="55801-334">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="55801-335">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="55801-335">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-336">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-336">Checksum</span></span>

<span data-ttu-id="55801-337">はい</span><span class="sxs-lookup"><span data-stu-id="55801-337">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-338">定義</span><span class="sxs-lookup"><span data-stu-id="55801-338">Definition</span></span>

<span data-ttu-id="55801-339">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-339">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-340">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-340">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-341">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-341">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="55801-342">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-342">The checksum passes.</span></span>

<span data-ttu-id="55801-343">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-343">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-344">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-344">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-345">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-345">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-346">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-346">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="55801-347">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="55801-347">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="55801-348">bank account details</span><span class="sxs-lookup"><span data-stu-id="55801-348">bank account details</span></span>
- <span data-ttu-id="55801-349">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="55801-349">medicare payments</span></span>
- <span data-ttu-id="55801-350">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="55801-350">mortgage account</span></span>
- <span data-ttu-id="55801-351">
bank payments</span><span class="sxs-lookup"><span data-stu-id="55801-351">bank payments</span></span>
- <span data-ttu-id="55801-352">
information branch</span><span class="sxs-lookup"><span data-stu-id="55801-352">information branch</span></span>
- <span data-ttu-id="55801-353">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="55801-353">credit card loan</span></span>
- <span data-ttu-id="55801-354">
department of human services</span><span class="sxs-lookup"><span data-stu-id="55801-354">department of human services</span></span>
- <span data-ttu-id="55801-355">ローカル サービス</span><span class="sxs-lookup"><span data-stu-id="55801-355">local service</span></span>
- <span data-ttu-id="55801-356">

medicare</span><span class="sxs-lookup"><span data-stu-id="55801-356">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="55801-357">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-357">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-358">形式</span><span class="sxs-lookup"><span data-stu-id="55801-358">Format</span></span>

<span data-ttu-id="55801-359">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-359">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-360">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-360">Pattern</span></span>

<span data-ttu-id="55801-361">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-361">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-362">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-362">Checksum</span></span>

<span data-ttu-id="55801-363">なし</span><span class="sxs-lookup"><span data-stu-id="55801-363">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-364">定義</span><span class="sxs-lookup"><span data-stu-id="55801-364">Definition</span></span>

<span data-ttu-id="55801-365">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-366">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-366">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-367">Keyword_passport または Keyword_australia_passport_number からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="55801-367">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-368">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-368">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="55801-369">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="55801-369">Keyword_passport</span></span>

- <span data-ttu-id="55801-370">Passport Number</span><span class="sxs-lookup"><span data-stu-id="55801-370">Passport Number</span></span>
- <span data-ttu-id="55801-371">
Passport No</span><span class="sxs-lookup"><span data-stu-id="55801-371">Passport No</span></span>
- <span data-ttu-id="55801-372">Passport #
</span><span class="sxs-lookup"><span data-stu-id="55801-372">Passport #</span></span>
- <span data-ttu-id="55801-373">Passport#
</span><span class="sxs-lookup"><span data-stu-id="55801-373">Passport#</span></span>
- <span data-ttu-id="55801-374">PassportID</span><span class="sxs-lookup"><span data-stu-id="55801-374">PassportID</span></span>
- <span data-ttu-id="55801-375">Passportno
</span><span class="sxs-lookup"><span data-stu-id="55801-375">Passportno</span></span>
- <span data-ttu-id="55801-376">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-376">passportnumber</span></span>
- <span data-ttu-id="55801-377">パスポート</span><span class="sxs-lookup"><span data-stu-id="55801-377">パスポート</span></span>
- <span data-ttu-id="55801-378">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="55801-378">パスポート番号</span></span>
- <span data-ttu-id="55801-379">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="55801-379">パスポートのNum</span></span>
- <span data-ttu-id="55801-380">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="55801-380">パスポート ＃</span></span> 
- <span data-ttu-id="55801-381">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="55801-381">Numéro de passeport</span></span>
- <span data-ttu-id="55801-382">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="55801-382">Passeport n °</span></span>
- <span data-ttu-id="55801-383">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="55801-383">Passeport Non</span></span>
- <span data-ttu-id="55801-384">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="55801-384">Passeport #</span></span>
- <span data-ttu-id="55801-385">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="55801-385">Passeport#</span></span>
- <span data-ttu-id="55801-386">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="55801-386">PasseportNon</span></span>
- <span data-ttu-id="55801-387">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="55801-387">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="55801-388">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="55801-388">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="55801-389">passport</span><span class="sxs-lookup"><span data-stu-id="55801-389">passport</span></span>
- <span data-ttu-id="55801-390">
passport details</span><span class="sxs-lookup"><span data-stu-id="55801-390">passport details</span></span>
- <span data-ttu-id="55801-391">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="55801-391">immigration and citizenship</span></span>
- <span data-ttu-id="55801-392">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="55801-392">commonwealth of australia</span></span>
- <span data-ttu-id="55801-393">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="55801-393">department of immigration</span></span>
- <span data-ttu-id="55801-394">
residential address</span><span class="sxs-lookup"><span data-stu-id="55801-394">residential address</span></span>
- <span data-ttu-id="55801-395">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="55801-395">department of immigration and citizenship</span></span>
- <span data-ttu-id="55801-396">visa
</span><span class="sxs-lookup"><span data-stu-id="55801-396">visa</span></span>
- <span data-ttu-id="55801-397">
national identity card</span><span class="sxs-lookup"><span data-stu-id="55801-397">national identity card</span></span>
- <span data-ttu-id="55801-398">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-398">passport number</span></span>
- <span data-ttu-id="55801-399">
travel document</span><span class="sxs-lookup"><span data-stu-id="55801-399">travel document</span></span>
- <span data-ttu-id="55801-400">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="55801-400">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="55801-401">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="55801-401">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-402">形式</span><span class="sxs-lookup"><span data-stu-id="55801-402">Format</span></span>

<span data-ttu-id="55801-403">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-403">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-404">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-404">Pattern</span></span>

<span data-ttu-id="55801-405">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="55801-405">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="55801-406">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-406">Three digits</span></span> 
- <span data-ttu-id="55801-407">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="55801-407">An optional space</span></span> 
- <span data-ttu-id="55801-408">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-408">Three digits</span></span> 
- <span data-ttu-id="55801-409">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="55801-409">An optional space</span></span> 
- <span data-ttu-id="55801-410">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="55801-410">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-411">Checksum</span></span>

<span data-ttu-id="55801-412">はい</span><span class="sxs-lookup"><span data-stu-id="55801-412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-413">定義</span><span class="sxs-lookup"><span data-stu-id="55801-413">Definition</span></span>

<span data-ttu-id="55801-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-415">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-415">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-416">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-416">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="55801-417">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-417">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-418">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-418">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="55801-419">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="55801-419">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="55801-420">australian business number</span><span class="sxs-lookup"><span data-stu-id="55801-420">australian business number</span></span>
- <span data-ttu-id="55801-421">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="55801-421">marginal tax rate</span></span>
- <span data-ttu-id="55801-422">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="55801-422">medicare levy</span></span>
- <span data-ttu-id="55801-423">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="55801-423">portfolio number</span></span>
- <span data-ttu-id="55801-424">
service veterans</span><span class="sxs-lookup"><span data-stu-id="55801-424">service veterans</span></span>
- <span data-ttu-id="55801-425">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="55801-425">withholding tax</span></span>
- <span data-ttu-id="55801-426">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="55801-426">individual tax return</span></span>
- <span data-ttu-id="55801-427">

tax file number</span><span class="sxs-lookup"><span data-stu-id="55801-427">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="55801-428">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="55801-428">Keyword_number_exclusions</span></span>

- <span data-ttu-id="55801-429">00000000</span><span class="sxs-lookup"><span data-stu-id="55801-429">00000000</span></span>
- <span data-ttu-id="55801-430">11111111</span><span class="sxs-lookup"><span data-stu-id="55801-430">11111111</span></span>
- <span data-ttu-id="55801-431">22222222</span><span class="sxs-lookup"><span data-stu-id="55801-431">22222222</span></span>
- <span data-ttu-id="55801-432">33333333</span><span class="sxs-lookup"><span data-stu-id="55801-432">33333333</span></span>
- <span data-ttu-id="55801-433">44444444</span><span class="sxs-lookup"><span data-stu-id="55801-433">44444444</span></span>
- <span data-ttu-id="55801-434">55555555</span><span class="sxs-lookup"><span data-stu-id="55801-434">55555555</span></span>
- <span data-ttu-id="55801-435">66666666</span><span class="sxs-lookup"><span data-stu-id="55801-435">66666666</span></span>
- <span data-ttu-id="55801-436">77777777</span><span class="sxs-lookup"><span data-stu-id="55801-436">77777777</span></span>
- <span data-ttu-id="55801-437">88888888</span><span class="sxs-lookup"><span data-stu-id="55801-437">88888888</span></span>
- <span data-ttu-id="55801-438">99999999</span><span class="sxs-lookup"><span data-stu-id="55801-438">99999999</span></span>
- <span data-ttu-id="55801-439">000000000</span><span class="sxs-lookup"><span data-stu-id="55801-439">000000000</span></span>
- <span data-ttu-id="55801-440">111111111</span><span class="sxs-lookup"><span data-stu-id="55801-440">111111111</span></span>
- <span data-ttu-id="55801-441">222222222</span><span class="sxs-lookup"><span data-stu-id="55801-441">222222222</span></span>
- <span data-ttu-id="55801-442">333333333</span><span class="sxs-lookup"><span data-stu-id="55801-442">333333333</span></span>
- <span data-ttu-id="55801-443">444444444</span><span class="sxs-lookup"><span data-stu-id="55801-443">444444444</span></span>
- <span data-ttu-id="55801-444">555555555</span><span class="sxs-lookup"><span data-stu-id="55801-444">555555555</span></span>
- <span data-ttu-id="55801-445">666666666</span><span class="sxs-lookup"><span data-stu-id="55801-445">666666666</span></span>
- <span data-ttu-id="55801-446">777777777</span><span class="sxs-lookup"><span data-stu-id="55801-446">777777777</span></span>
- <span data-ttu-id="55801-447">888888888</span><span class="sxs-lookup"><span data-stu-id="55801-447">888888888</span></span>
- <span data-ttu-id="55801-448">999999999</span><span class="sxs-lookup"><span data-stu-id="55801-448">999999999</span></span>
- <span data-ttu-id="55801-449">0000000000</span><span class="sxs-lookup"><span data-stu-id="55801-449">0000000000</span></span>
- <span data-ttu-id="55801-450">1111111111</span><span class="sxs-lookup"><span data-stu-id="55801-450">1111111111</span></span>
- <span data-ttu-id="55801-451">2222222222</span><span class="sxs-lookup"><span data-stu-id="55801-451">2222222222</span></span>
- <span data-ttu-id="55801-452">3333333333</span><span class="sxs-lookup"><span data-stu-id="55801-452">3333333333</span></span>
- <span data-ttu-id="55801-453">4444444444</span><span class="sxs-lookup"><span data-stu-id="55801-453">4444444444</span></span>
- <span data-ttu-id="55801-454">5555555555</span><span class="sxs-lookup"><span data-stu-id="55801-454">5555555555</span></span>
- <span data-ttu-id="55801-455">6666666666</span><span class="sxs-lookup"><span data-stu-id="55801-455">6666666666</span></span>
- <span data-ttu-id="55801-456">7777777777</span><span class="sxs-lookup"><span data-stu-id="55801-456">7777777777</span></span>
- <span data-ttu-id="55801-457">8888888888</span><span class="sxs-lookup"><span data-stu-id="55801-457">8888888888</span></span>
- <span data-ttu-id="55801-458">9999999999</span><span class="sxs-lookup"><span data-stu-id="55801-458">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="55801-459">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="55801-459">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-460">形式</span><span class="sxs-lookup"><span data-stu-id="55801-460">Format</span></span>

<span data-ttu-id="55801-461">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="55801-461">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-462">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-462">Pattern</span></span>

<span data-ttu-id="55801-463">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="55801-463">11 digits plus delimiters:</span></span>
- <span data-ttu-id="55801-464">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="55801-464">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="55801-465">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-465">A hyphen</span></span> 
- <span data-ttu-id="55801-466">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="55801-466">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="55801-467">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-467">A period</span></span> 
- <span data-ttu-id="55801-468">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-468">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-469">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-469">Checksum</span></span>

<span data-ttu-id="55801-470">はい</span><span class="sxs-lookup"><span data-stu-id="55801-470">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-471">定義</span><span class="sxs-lookup"><span data-stu-id="55801-471">Definition</span></span>

<span data-ttu-id="55801-472">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-472">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-473">関数 Func_belgium_national_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-473">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-474">Keyword_belgium_national_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-474">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="55801-475">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-475">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-476">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-476">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="55801-477">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="55801-477">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="55801-478">Identity</span><span class="sxs-lookup"><span data-stu-id="55801-478">Identity</span></span>
- <span data-ttu-id="55801-479">Registration</span><span class="sxs-lookup"><span data-stu-id="55801-479">Registration</span></span>
- <span data-ttu-id="55801-480">Identification</span><span class="sxs-lookup"><span data-stu-id="55801-480">Identification</span></span> 
- <span data-ttu-id="55801-481">ID</span><span class="sxs-lookup"><span data-stu-id="55801-481">ID</span></span> 
- <span data-ttu-id="55801-482">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="55801-482">Identiteitskaart</span></span>
- <span data-ttu-id="55801-483">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="55801-483">Registratie nummer</span></span> 
- <span data-ttu-id="55801-484">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="55801-484">Identificatie nummer</span></span> 
- <span data-ttu-id="55801-485">Identiteit</span><span class="sxs-lookup"><span data-stu-id="55801-485">Identiteit</span></span>
- <span data-ttu-id="55801-486">Registratie</span><span class="sxs-lookup"><span data-stu-id="55801-486">Registratie</span></span>
- <span data-ttu-id="55801-487">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="55801-487">Identificatie</span></span> 
- <span data-ttu-id="55801-488">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="55801-488">Carte d’identité</span></span> 
- <span data-ttu-id="55801-489">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="55801-489">numéro d'immatriculation</span></span>
- <span data-ttu-id="55801-490">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="55801-490">numéro d'identification</span></span>
- <span data-ttu-id="55801-491">
identité
</span><span class="sxs-lookup"><span data-stu-id="55801-491">identité</span></span> 
- <span data-ttu-id="55801-492">inscription
</span><span class="sxs-lookup"><span data-stu-id="55801-492">inscription</span></span> 
- <span data-ttu-id="55801-493">Identifikation</span><span class="sxs-lookup"><span data-stu-id="55801-493">Identifikation</span></span>
- <span data-ttu-id="55801-494">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="55801-494">Identifizierung</span></span>
- <span data-ttu-id="55801-495">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="55801-495">Identifikationsnummer</span></span>
- <span data-ttu-id="55801-496">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="55801-496">Personalausweis</span></span>
- <span data-ttu-id="55801-497">Registrierung</span><span class="sxs-lookup"><span data-stu-id="55801-497">Registrierung</span></span>
- <span data-ttu-id="55801-498">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="55801-498">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="55801-499">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="55801-499">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-500">形式</span><span class="sxs-lookup"><span data-stu-id="55801-500">Format</span></span>

<span data-ttu-id="55801-501">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-501">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-502">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-502">Pattern</span></span>

<span data-ttu-id="55801-503">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="55801-503">Formatted:</span></span>
- <span data-ttu-id="55801-504">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-504">Three digits</span></span> 
- <span data-ttu-id="55801-505">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-505">A period</span></span> 
- <span data-ttu-id="55801-506">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-506">Three digits</span></span> 
- <span data-ttu-id="55801-507">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-507">A period</span></span> 
- <span data-ttu-id="55801-508">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-508">Three digits</span></span> 
- <span data-ttu-id="55801-509">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-509">A hyphen</span></span> 
- <span data-ttu-id="55801-510">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-510">Two digits which are check digits</span></span>

<span data-ttu-id="55801-511">書式設定なし:</span><span class="sxs-lookup"><span data-stu-id="55801-511">Unformatted:</span></span>
- <span data-ttu-id="55801-512">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="55801-512">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-513">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-513">Checksum</span></span>

<span data-ttu-id="55801-514">はい</span><span class="sxs-lookup"><span data-stu-id="55801-514">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-515">定義</span><span class="sxs-lookup"><span data-stu-id="55801-515">Definition</span></span>

<span data-ttu-id="55801-516">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-516">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-517">関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-517">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-518">Keyword_brazil_cpf のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-518">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="55801-519">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-519">The checksum passes.</span></span>

<span data-ttu-id="55801-520">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-521">関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-521">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-522">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-522">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-523">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-523">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="55801-524">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="55801-524">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="55801-525">CPF</span><span class="sxs-lookup"><span data-stu-id="55801-525">CPF</span></span>
- <span data-ttu-id="55801-526">Identification</span><span class="sxs-lookup"><span data-stu-id="55801-526">Identification</span></span>
- <span data-ttu-id="55801-527">Registration</span><span class="sxs-lookup"><span data-stu-id="55801-527">Registration</span></span>
- <span data-ttu-id="55801-528">Revenue</span><span class="sxs-lookup"><span data-stu-id="55801-528">Revenue</span></span>
- <span data-ttu-id="55801-529">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="55801-529">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="55801-530">Imposto
</span><span class="sxs-lookup"><span data-stu-id="55801-530">Imposto</span></span> 
- <span data-ttu-id="55801-531">Identificação
</span><span class="sxs-lookup"><span data-stu-id="55801-531">Identificação</span></span> 
- <span data-ttu-id="55801-532">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="55801-532">Inscrição</span></span> 
- <span data-ttu-id="55801-533">Receita

</span><span class="sxs-lookup"><span data-stu-id="55801-533">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="55801-534">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="55801-534">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="55801-535">形式</span><span class="sxs-lookup"><span data-stu-id="55801-535">Format</span></span>

<span data-ttu-id="55801-536">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-536">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-537">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-537">Pattern</span></span>
<span data-ttu-id="55801-538">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="55801-538">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="55801-539">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-539">Two digits</span></span> 
- <span data-ttu-id="55801-540">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-540">A period</span></span> 
- <span data-ttu-id="55801-541">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-541">Three digits</span></span> 
- <span data-ttu-id="55801-542">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-542">A period</span></span> 
- <span data-ttu-id="55801-543">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="55801-543">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="55801-544">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-544">A forward slash</span></span> 
- <span data-ttu-id="55801-545">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="55801-545">Four-digit branch number</span></span> 
- <span data-ttu-id="55801-546">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-546">A hyphen</span></span> 
- <span data-ttu-id="55801-547">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-547">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-548">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-548">Checksum</span></span>

<span data-ttu-id="55801-549">はい</span><span class="sxs-lookup"><span data-stu-id="55801-549">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-550">定義</span><span class="sxs-lookup"><span data-stu-id="55801-550">Definition</span></span>

<span data-ttu-id="55801-551">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-551">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-552">関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-552">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-553">Keyword_brazil_cnpj のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-553">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="55801-554">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-554">The checksum passes.</span></span>

<span data-ttu-id="55801-555">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-555">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-556">関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-556">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-557">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-557">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-558">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-558">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="55801-559">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="55801-559">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="55801-560">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="55801-560">CNPJ</span></span> 
- <span data-ttu-id="55801-561">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="55801-561">CNPJ/MF</span></span> 
- <span data-ttu-id="55801-562">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="55801-562">CNPJ-MF</span></span> 
- <span data-ttu-id="55801-563">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="55801-563">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="55801-564">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="55801-564">Taxpayers Registry</span></span> 
- <span data-ttu-id="55801-565">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="55801-565">Legal entity</span></span> 
- <span data-ttu-id="55801-566">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="55801-566">Legal entities</span></span> 
- <span data-ttu-id="55801-567">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="55801-567">Registration Status</span></span> 
- <span data-ttu-id="55801-568">Business
</span><span class="sxs-lookup"><span data-stu-id="55801-568">Business</span></span> 
- <span data-ttu-id="55801-569">Company</span><span class="sxs-lookup"><span data-stu-id="55801-569">Company</span></span>
- <span data-ttu-id="55801-570">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="55801-570">CNPJ</span></span> 
- <span data-ttu-id="55801-571">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="55801-571">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="55801-572">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="55801-572">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="55801-573">CGC
</span><span class="sxs-lookup"><span data-stu-id="55801-573">CGC</span></span> 
- <span data-ttu-id="55801-574">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="55801-574">Pessoa jurídica</span></span> 
- <span data-ttu-id="55801-575">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="55801-575">Pessoas jurídicas</span></span> 
- <span data-ttu-id="55801-576">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="55801-576">Situação cadastral</span></span> 
- <span data-ttu-id="55801-577">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="55801-577">Inscrição</span></span> 
- <span data-ttu-id="55801-578">Empresa
</span><span class="sxs-lookup"><span data-stu-id="55801-578">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="55801-579">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="55801-579">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="55801-580">形式</span><span class="sxs-lookup"><span data-stu-id="55801-580">Format</span></span>

<span data-ttu-id="55801-581">Registro Geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-581">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="55801-582">Registro de Identidade (RIC) (新しい形式): 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-582">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-583">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-583">Pattern</span></span>

<span data-ttu-id="55801-584">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="55801-584">Registro Geral (old format):</span></span>
- <span data-ttu-id="55801-585">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-585">Two digits</span></span> 
- <span data-ttu-id="55801-586">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-586">A period</span></span> 
- <span data-ttu-id="55801-587">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-587">Three digits</span></span> 
- <span data-ttu-id="55801-588">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-588">A period</span></span> 
- <span data-ttu-id="55801-589">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-589">Three digits</span></span> 
- <span data-ttu-id="55801-590">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-590">A hyphen</span></span> 
- <span data-ttu-id="55801-591">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-591">One digit which is a check digit</span></span>

<span data-ttu-id="55801-592">Registro de Identidade (RIC) (新しい形式)。</span><span class="sxs-lookup"><span data-stu-id="55801-592">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="55801-593">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-593">10 digits</span></span> 
- <span data-ttu-id="55801-594">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-594">A hyphen</span></span> 
- <span data-ttu-id="55801-595">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-595">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-596">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-596">Checksum</span></span>

<span data-ttu-id="55801-597">はい</span><span class="sxs-lookup"><span data-stu-id="55801-597">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-598">定義</span><span class="sxs-lookup"><span data-stu-id="55801-598">Definition</span></span>

<span data-ttu-id="55801-599">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-599">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-600">関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-600">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-601">Keyword_brazil_rg のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-601">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="55801-602">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-602">The checksum passes.</span></span>

<span data-ttu-id="55801-603">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-603">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-604">関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-604">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-605">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-605">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-606">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-606">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="55801-607">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="55801-607">Keyword_brazil_rg</span></span>

<span data-ttu-id="55801-608">Cédula de identidade 身分証明書国民 id número de rregistro registro de Iidentidade registro geral (このキーワードでは大文字小文字を区別) RG (このキーワードでは大文字小文字を区別) RIC</span><span class="sxs-lookup"><span data-stu-id="55801-608">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="55801-609">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-609">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-610">形式</span><span class="sxs-lookup"><span data-stu-id="55801-610">Format</span></span>

<span data-ttu-id="55801-611">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-611">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-612">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-612">Pattern</span></span>

<span data-ttu-id="55801-613">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="55801-613">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="55801-614">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="55801-614">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="55801-615">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-615">Five digits</span></span> 
- <span data-ttu-id="55801-616">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-616">A hyphen</span></span> 
- <span data-ttu-id="55801-617">3 桁の数字または</span><span class="sxs-lookup"><span data-stu-id="55801-617">Three digits OR</span></span>
- <span data-ttu-id="55801-618">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="55801-618">A zero "0"</span></span> 
- <span data-ttu-id="55801-619">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-619">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-620">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-620">Checksum</span></span>

<span data-ttu-id="55801-621">なし</span><span class="sxs-lookup"><span data-stu-id="55801-621">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-622">定義</span><span class="sxs-lookup"><span data-stu-id="55801-622">Definition</span></span>

<span data-ttu-id="55801-623">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-623">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-624">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-624">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-625">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-625">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="55801-626">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-626">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="55801-627">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-627">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-628">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-628">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-629">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-629">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-630">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-630">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="55801-631">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="55801-631">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="55801-632">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="55801-632">canada savings bonds</span></span>
- <span data-ttu-id="55801-633">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="55801-633">canada revenue agency</span></span>
- <span data-ttu-id="55801-634">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="55801-634">canadian financial institution</span></span>
- <span data-ttu-id="55801-635">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="55801-635">direct deposit form</span></span>
- <span data-ttu-id="55801-636">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="55801-636">canadian citizen</span></span>
- <span data-ttu-id="55801-637">
legal representative</span><span class="sxs-lookup"><span data-stu-id="55801-637">legal representative</span></span>
- <span data-ttu-id="55801-638">
notary public</span><span class="sxs-lookup"><span data-stu-id="55801-638">notary public</span></span>
- <span data-ttu-id="55801-639">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="55801-639">commissioner for oaths</span></span>
- <span data-ttu-id="55801-640">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="55801-640">child care benefit</span></span>
- <span data-ttu-id="55801-641">
universal child care</span><span class="sxs-lookup"><span data-stu-id="55801-641">universal child care</span></span>
- <span data-ttu-id="55801-642">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="55801-642">canada child tax benefit</span></span>
- <span data-ttu-id="55801-643">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="55801-643">income tax benefit</span></span>
- <span data-ttu-id="55801-644">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="55801-644">harmonized sales tax</span></span>
- <span data-ttu-id="55801-645">social insurance number</span><span class="sxs-lookup"><span data-stu-id="55801-645">social insurance number</span></span>
- <span data-ttu-id="55801-646">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="55801-646">income tax refund</span></span>
- <span data-ttu-id="55801-647">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="55801-647">child tax benefit</span></span>
- <span data-ttu-id="55801-648">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="55801-648">territorial payments</span></span>
- <span data-ttu-id="55801-649">
institution number</span><span class="sxs-lookup"><span data-stu-id="55801-649">institution number</span></span>
- <span data-ttu-id="55801-650">
deposit request</span><span class="sxs-lookup"><span data-stu-id="55801-650">deposit request</span></span>
- <span data-ttu-id="55801-651">
banking information</span><span class="sxs-lookup"><span data-stu-id="55801-651">banking information</span></span>
- <span data-ttu-id="55801-652">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="55801-652">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="55801-653">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-653">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-654">形式</span><span class="sxs-lookup"><span data-stu-id="55801-654">Format</span></span>

<span data-ttu-id="55801-655">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="55801-655">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-656">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-656">Pattern</span></span>

<span data-ttu-id="55801-657">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="55801-657">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-658">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-658">Checksum</span></span>

<span data-ttu-id="55801-659">なし</span><span class="sxs-lookup"><span data-stu-id="55801-659">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-660">定義</span><span class="sxs-lookup"><span data-stu-id="55801-660">Definition</span></span>

<span data-ttu-id="55801-661">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-661">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-662">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-662">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-663">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-663">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="55801-664">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-664">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-665">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-665">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="55801-666">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="55801-666">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="55801-667">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="55801-667">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="55801-668">
州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="55801-668">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="55801-669">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="55801-669">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="55801-670">DL</span><span class="sxs-lookup"><span data-stu-id="55801-670">DL</span></span>
- <span data-ttu-id="55801-671">DLS</span><span class="sxs-lookup"><span data-stu-id="55801-671">DLS</span></span>
- <span data-ttu-id="55801-672">CDL</span><span class="sxs-lookup"><span data-stu-id="55801-672">CDL</span></span>
- <span data-ttu-id="55801-673">CDL</span><span class="sxs-lookup"><span data-stu-id="55801-673">CDLS</span></span>
- <span data-ttu-id="55801-674">DriverLic</span><span class="sxs-lookup"><span data-stu-id="55801-674">DriverLic</span></span>
- <span data-ttu-id="55801-675">DriverLics</span><span class="sxs-lookup"><span data-stu-id="55801-675">DriverLics</span></span>
- <span data-ttu-id="55801-676">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="55801-676">DriverLicense</span></span>
- <span data-ttu-id="55801-677">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-677">DriverLicenses</span></span>
- <span data-ttu-id="55801-678">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="55801-678">DriverLicence</span></span>
- <span data-ttu-id="55801-679">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="55801-679">DriverLicences</span></span>
- <span data-ttu-id="55801-680">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-680">Driver Lic</span></span>
- <span data-ttu-id="55801-681">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="55801-681">Driver Lics</span></span>
- <span data-ttu-id="55801-682">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-682">Driver License</span></span>
- <span data-ttu-id="55801-683">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-683">Driver Licenses</span></span>
- <span data-ttu-id="55801-684">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-684">Driver Licence</span></span>
- <span data-ttu-id="55801-685">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-685">Driver Licences</span></span>
- <span data-ttu-id="55801-686">DriversLic</span><span class="sxs-lookup"><span data-stu-id="55801-686">DriversLic</span></span>
- <span data-ttu-id="55801-687">DriversLics</span><span class="sxs-lookup"><span data-stu-id="55801-687">DriversLics</span></span>
- <span data-ttu-id="55801-688">DriversLicence</span><span class="sxs-lookup"><span data-stu-id="55801-688">DriversLicence</span></span>
- <span data-ttu-id="55801-689">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="55801-689">DriversLicences</span></span>
- <span data-ttu-id="55801-690">証</span><span class="sxs-lookup"><span data-stu-id="55801-690">DriversLicense</span></span>
- <span data-ttu-id="55801-691">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-691">DriversLicenses</span></span>
- <span data-ttu-id="55801-692">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-692">Drivers Lic</span></span>
- <span data-ttu-id="55801-693">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="55801-693">Drivers Lics</span></span>
- <span data-ttu-id="55801-694">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-694">Drivers License</span></span>
- <span data-ttu-id="55801-695">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-695">Drivers Licenses</span></span>
- <span data-ttu-id="55801-696">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-696">Drivers Licence</span></span>
- <span data-ttu-id="55801-697">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-697">Drivers Licences</span></span>
- <span data-ttu-id="55801-698">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="55801-698">Driver'Lic</span></span>
- <span data-ttu-id="55801-699">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="55801-699">Driver'Lics</span></span>
- <span data-ttu-id="55801-700">Driver'License</span><span class="sxs-lookup"><span data-stu-id="55801-700">Driver'License</span></span>
- <span data-ttu-id="55801-701">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="55801-701">Driver'Licenses</span></span>
- <span data-ttu-id="55801-702">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="55801-702">Driver'Licence</span></span>
- <span data-ttu-id="55801-703">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="55801-703">Driver'Licences</span></span>
- <span data-ttu-id="55801-704">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="55801-704">Driver' Lic</span></span>
- <span data-ttu-id="55801-705">ドライバー ' Lics</span><span class="sxs-lookup"><span data-stu-id="55801-705">Driver' Lics</span></span>
- <span data-ttu-id="55801-706">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-706">Driver' License</span></span>
- <span data-ttu-id="55801-707">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-707">Driver' Licenses</span></span>
- <span data-ttu-id="55801-708">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-708">Driver' Licence</span></span>
- <span data-ttu-id="55801-709">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-709">Driver' Licences</span></span>
- <span data-ttu-id="55801-710">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="55801-710">Driver'sLic</span></span>
- <span data-ttu-id="55801-711">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="55801-711">Driver'sLics</span></span>
- <span data-ttu-id="55801-712">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="55801-712">Driver'sLicense</span></span>
- <span data-ttu-id="55801-713">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-713">Driver'sLicenses</span></span>
- <span data-ttu-id="55801-714">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="55801-714">Driver'sLicence</span></span>
- <span data-ttu-id="55801-715">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="55801-715">Driver'sLicences</span></span>
- <span data-ttu-id="55801-716">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="55801-716">Driver's Lic</span></span>
- <span data-ttu-id="55801-717">ドライバーの Lics</span><span class="sxs-lookup"><span data-stu-id="55801-717">Driver's Lics</span></span>
- <span data-ttu-id="55801-718">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-718">Driver's License</span></span>
- <span data-ttu-id="55801-719">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-719">Driver's Licenses</span></span>
- <span data-ttu-id="55801-720">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-720">Driver's Licence</span></span>
- <span data-ttu-id="55801-721">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-721">Driver's Licences</span></span>
- <span data-ttu-id="55801-722">Permis デ Conduire</span><span class="sxs-lookup"><span data-stu-id="55801-722">Permis de Conduire</span></span>
- <span data-ttu-id="55801-723">id</span><span class="sxs-lookup"><span data-stu-id="55801-723">id</span></span>
- <span data-ttu-id="55801-724">id</span><span class="sxs-lookup"><span data-stu-id="55801-724">ids</span></span>
- <span data-ttu-id="55801-725">
idcard number</span><span class="sxs-lookup"><span data-stu-id="55801-725">idcard number</span></span>
- <span data-ttu-id="55801-726">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="55801-726">idcard numbers</span></span>
- <span data-ttu-id="55801-727">
idcard #</span><span class="sxs-lookup"><span data-stu-id="55801-727">idcard #</span></span>
- <span data-ttu-id="55801-728">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="55801-728">idcard #s</span></span>
- <span data-ttu-id="55801-729">idcard カード</span><span class="sxs-lookup"><span data-stu-id="55801-729">idcard card</span></span>
- <span data-ttu-id="55801-730">idcard カード</span><span class="sxs-lookup"><span data-stu-id="55801-730">idcard cards</span></span>
- <span data-ttu-id="55801-731">idcard</span><span class="sxs-lookup"><span data-stu-id="55801-731">idcard</span></span>
- <span data-ttu-id="55801-732">identification number
</span><span class="sxs-lookup"><span data-stu-id="55801-732">identification number</span></span>
- <span data-ttu-id="55801-733">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="55801-733">identification numbers</span></span>
- <span data-ttu-id="55801-734">identification #
</span><span class="sxs-lookup"><span data-stu-id="55801-734">identification #</span></span>
- <span data-ttu-id="55801-735">
identification #s</span><span class="sxs-lookup"><span data-stu-id="55801-735">identification #s</span></span>
- <span data-ttu-id="55801-736">id カード</span><span class="sxs-lookup"><span data-stu-id="55801-736">identification card</span></span>
- <span data-ttu-id="55801-737">id カード</span><span class="sxs-lookup"><span data-stu-id="55801-737">identification cards</span></span>
- <span data-ttu-id="55801-738">
identification
</span><span class="sxs-lookup"><span data-stu-id="55801-738">identification</span></span> 
- <span data-ttu-id="55801-739">DL#</span><span class="sxs-lookup"><span data-stu-id="55801-739">DL#</span></span>
- <span data-ttu-id="55801-740">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="55801-740">DLS#</span></span> 
- <span data-ttu-id="55801-741">CDL#
</span><span class="sxs-lookup"><span data-stu-id="55801-741">CDL#</span></span> 
- <span data-ttu-id="55801-742">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="55801-742">CDLS#</span></span> 
- <span data-ttu-id="55801-743">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="55801-743">DriverLic#</span></span> 
- <span data-ttu-id="55801-744">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="55801-744">DriverLics#</span></span> 
- <span data-ttu-id="55801-745">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="55801-745">DriverLicense#</span></span> 
- <span data-ttu-id="55801-746">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-746">DriverLicenses#</span></span> 
- <span data-ttu-id="55801-747">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="55801-747">DriverLicence#</span></span> 
- <span data-ttu-id="55801-748">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="55801-748">DriverLicences#</span></span> 
- <span data-ttu-id="55801-749">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="55801-749">Driver Lic#</span></span>
- <span data-ttu-id="55801-750">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-750">Driver Lics#</span></span> 
- <span data-ttu-id="55801-751">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-751">Driver License#</span></span> 
- <span data-ttu-id="55801-752">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-752">Driver Licenses#</span></span> 
- <span data-ttu-id="55801-753">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-753">Driver License#</span></span> 
- <span data-ttu-id="55801-754">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-754">Driver Licences#</span></span> 
- <span data-ttu-id="55801-755">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="55801-755">DriversLic#</span></span> 
- <span data-ttu-id="55801-756">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="55801-756">DriversLics#</span></span> 
- <span data-ttu-id="55801-757">証番号</span><span class="sxs-lookup"><span data-stu-id="55801-757">DriversLicense#</span></span> 
- <span data-ttu-id="55801-758">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-758">DriversLicenses#</span></span> 
- <span data-ttu-id="55801-759">DriversLicence #</span><span class="sxs-lookup"><span data-stu-id="55801-759">DriversLicence#</span></span> 
- <span data-ttu-id="55801-760">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="55801-760">DriversLicences#</span></span> 
- <span data-ttu-id="55801-761">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="55801-761">Drivers Lic#</span></span> 
- <span data-ttu-id="55801-762">ドライバー Lics #</span><span class="sxs-lookup"><span data-stu-id="55801-762">Drivers Lics#</span></span> 
- <span data-ttu-id="55801-763">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-763">Drivers License#</span></span> 
- <span data-ttu-id="55801-764">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-764">Drivers Licenses#</span></span> 
- <span data-ttu-id="55801-765">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-765">Drivers Licence#</span></span> 
- <span data-ttu-id="55801-766">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-766">Drivers Licences#</span></span> 
- <span data-ttu-id="55801-767">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-767">Driver'Lic#</span></span> 
- <span data-ttu-id="55801-768">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-768">Driver'Lics#</span></span> 
- <span data-ttu-id="55801-769">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="55801-769">Driver'License#</span></span> 
- <span data-ttu-id="55801-770">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-770">Driver'Licenses#</span></span> 
- <span data-ttu-id="55801-771">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="55801-771">Driver'Licence#</span></span> 
- <span data-ttu-id="55801-772">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="55801-772">Driver'Licences#</span></span> 
- <span data-ttu-id="55801-773">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-773">Driver' Lic#</span></span> 
- <span data-ttu-id="55801-774">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-774">Driver' Lics#</span></span> 
- <span data-ttu-id="55801-775">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="55801-775">Driver' License#</span></span> 
- <span data-ttu-id="55801-776">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-776">Driver' Licenses#</span></span> 
- <span data-ttu-id="55801-777">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-777">Driver' Licence#</span></span> 
- <span data-ttu-id="55801-778">ドライバー ' ライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-778">Driver' Licences#</span></span> 
- <span data-ttu-id="55801-779">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="55801-779">Driver'sLic#</span></span> 
- <span data-ttu-id="55801-780">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="55801-780">Driver'sLics#</span></span> 
- <span data-ttu-id="55801-781">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="55801-781">Driver'sLicense#</span></span> 
- <span data-ttu-id="55801-782">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-782">Driver'sLicenses#</span></span> 
- <span data-ttu-id="55801-783">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="55801-783">Driver'sLicence#</span></span> 
- <span data-ttu-id="55801-784">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="55801-784">Driver'sLicences#</span></span> 
- <span data-ttu-id="55801-785">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-785">Driver's Lic#</span></span> 
- <span data-ttu-id="55801-786">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-786">Driver's Lics#</span></span> 
- <span data-ttu-id="55801-787">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="55801-787">Driver's License#</span></span> 
- <span data-ttu-id="55801-788">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-788">Driver's Licenses#</span></span> 
- <span data-ttu-id="55801-789">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-789">Driver's Licence#</span></span> 
- <span data-ttu-id="55801-790">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-790">Driver's Licences#</span></span> 
- <span data-ttu-id="55801-791">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="55801-791">Permis de Conduire#</span></span> 
- <span data-ttu-id="55801-792">id 番号</span><span class="sxs-lookup"><span data-stu-id="55801-792">id#</span></span> 
- <span data-ttu-id="55801-793">id #</span><span class="sxs-lookup"><span data-stu-id="55801-793">ids#</span></span> 
- <span data-ttu-id="55801-794">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="55801-794">idcard card#</span></span> 
- <span data-ttu-id="55801-795">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="55801-795">idcard cards#</span></span> 
- <span data-ttu-id="55801-796">idcard#
</span><span class="sxs-lookup"><span data-stu-id="55801-796">idcard#</span></span> 
- <span data-ttu-id="55801-797">identification card#
</span><span class="sxs-lookup"><span data-stu-id="55801-797">identification card#</span></span> 
- <span data-ttu-id="55801-798">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="55801-798">identification cards#</span></span> 
- <span data-ttu-id="55801-799">identification#
</span><span class="sxs-lookup"><span data-stu-id="55801-799">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="55801-800">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="55801-800">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-801">形式</span><span class="sxs-lookup"><span data-stu-id="55801-801">Format</span></span>

<span data-ttu-id="55801-802">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-802">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-803">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-803">Pattern</span></span>

<span data-ttu-id="55801-804">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-804">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-805">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-805">Checksum</span></span>

<span data-ttu-id="55801-806">なし</span><span class="sxs-lookup"><span data-stu-id="55801-806">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-807">定義</span><span class="sxs-lookup"><span data-stu-id="55801-807">Definition</span></span>

<span data-ttu-id="55801-808">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-808">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-809">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-809">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-810">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-810">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-811">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-811">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="55801-812">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="55801-812">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="55801-813">personal health number</span><span class="sxs-lookup"><span data-stu-id="55801-813">personal health number</span></span>
- <span data-ttu-id="55801-814">
patient information</span><span class="sxs-lookup"><span data-stu-id="55801-814">patient information</span></span>
- <span data-ttu-id="55801-815">正常性サービス</span><span class="sxs-lookup"><span data-stu-id="55801-815">health services</span></span>
- <span data-ttu-id="55801-816">
speciality services</span><span class="sxs-lookup"><span data-stu-id="55801-816">speciality services</span></span>
- <span data-ttu-id="55801-817">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="55801-817">automobile accident</span></span>
- <span data-ttu-id="55801-818">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="55801-818">patient hospital</span></span>
- <span data-ttu-id="55801-819">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="55801-819">psychiatrist</span></span>
- <span data-ttu-id="55801-820">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="55801-820">workers compensation</span></span>
- <span data-ttu-id="55801-821">
disability</span><span class="sxs-lookup"><span data-stu-id="55801-821">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="55801-822">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-822">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-823">形式</span><span class="sxs-lookup"><span data-stu-id="55801-823">Format</span></span>

<span data-ttu-id="55801-824">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-824">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-825">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-825">Pattern</span></span>

<span data-ttu-id="55801-826">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-826">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-827">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-827">Checksum</span></span>

<span data-ttu-id="55801-828">なし</span><span class="sxs-lookup"><span data-stu-id="55801-828">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-829">定義</span><span class="sxs-lookup"><span data-stu-id="55801-829">Definition</span></span>

<span data-ttu-id="55801-830">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-830">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-831">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-831">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-832">Keyword_canada_passport_number または Keyword_passport からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="55801-832">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-833">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-833">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="55801-834">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="55801-834">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="55801-835">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="55801-835">canadian citizenship</span></span>
- <span data-ttu-id="55801-836">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="55801-836">canadian passport</span></span>
- <span data-ttu-id="55801-837">
passport application</span><span class="sxs-lookup"><span data-stu-id="55801-837">passport application</span></span>
- <span data-ttu-id="55801-838">
passport photos</span><span class="sxs-lookup"><span data-stu-id="55801-838">passport photos</span></span>
- <span data-ttu-id="55801-839">
certified translator</span><span class="sxs-lookup"><span data-stu-id="55801-839">certified translator</span></span>
- <span data-ttu-id="55801-840">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="55801-840">canadian citizens</span></span>
- <span data-ttu-id="55801-841">
processing times</span><span class="sxs-lookup"><span data-stu-id="55801-841">processing times</span></span>
- <span data-ttu-id="55801-842">

renewal application</span><span class="sxs-lookup"><span data-stu-id="55801-842">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="55801-843">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="55801-843">Keyword_passport</span></span>

- <span data-ttu-id="55801-844">Passport Number</span><span class="sxs-lookup"><span data-stu-id="55801-844">Passport Number</span></span>
- <span data-ttu-id="55801-845">
Passport No</span><span class="sxs-lookup"><span data-stu-id="55801-845">Passport No</span></span>
- <span data-ttu-id="55801-846">Passport #
</span><span class="sxs-lookup"><span data-stu-id="55801-846">Passport #</span></span>
- <span data-ttu-id="55801-847">Passport#
</span><span class="sxs-lookup"><span data-stu-id="55801-847">Passport#</span></span>
- <span data-ttu-id="55801-848">PassportID</span><span class="sxs-lookup"><span data-stu-id="55801-848">PassportID</span></span>
- <span data-ttu-id="55801-849">Passportno
</span><span class="sxs-lookup"><span data-stu-id="55801-849">Passportno</span></span>
- <span data-ttu-id="55801-850">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-850">passportnumber</span></span>
- <span data-ttu-id="55801-851">パスポート</span><span class="sxs-lookup"><span data-stu-id="55801-851">パスポート</span></span>
- <span data-ttu-id="55801-852">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="55801-852">パスポート番号</span></span>
- <span data-ttu-id="55801-853">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="55801-853">パスポートのNum</span></span>
- <span data-ttu-id="55801-854">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="55801-854">パスポート＃</span></span>
- <span data-ttu-id="55801-855">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="55801-855">Numéro de passeport</span></span>
- <span data-ttu-id="55801-856">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="55801-856">Passeport n °</span></span>
- <span data-ttu-id="55801-857">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="55801-857">Passeport Non</span></span>
- <span data-ttu-id="55801-858">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="55801-858">Passeport #</span></span>
- <span data-ttu-id="55801-859">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="55801-859">Passeport#</span></span>
- <span data-ttu-id="55801-860">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="55801-860">PasseportNon</span></span>
- <span data-ttu-id="55801-861">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="55801-861">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="55801-862">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="55801-862">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-863">形式</span><span class="sxs-lookup"><span data-stu-id="55801-863">Format</span></span>

<span data-ttu-id="55801-864">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-864">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-865">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-865">Pattern</span></span>

<span data-ttu-id="55801-866">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-866">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-867">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-867">Checksum</span></span>

<span data-ttu-id="55801-868">なし</span><span class="sxs-lookup"><span data-stu-id="55801-868">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-869">定義</span><span class="sxs-lookup"><span data-stu-id="55801-869">Definition</span></span>

<span data-ttu-id="55801-p104">DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Regex_canada_phin の正規表現パターンに一致するコンテンツを検索します。Keyword_canada_phin または Keyword_canada_provinces からの 2 つ以上のキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="55801-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-872">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-872">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="55801-873">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="55801-873">Keyword_canada_phin</span></span>

- <span data-ttu-id="55801-874">social insurance number</span><span class="sxs-lookup"><span data-stu-id="55801-874">social insurance number</span></span>
- <span data-ttu-id="55801-875">
health information act</span><span class="sxs-lookup"><span data-stu-id="55801-875">health information act</span></span>
- <span data-ttu-id="55801-876">
income tax information</span><span class="sxs-lookup"><span data-stu-id="55801-876">income tax information</span></span>
- <span data-ttu-id="55801-877">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="55801-877">manitoba health</span></span>
- <span data-ttu-id="55801-878">
health registration</span><span class="sxs-lookup"><span data-stu-id="55801-878">health registration</span></span>
- <span data-ttu-id="55801-879">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="55801-879">prescription purchases</span></span>
- <span data-ttu-id="55801-880">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="55801-880">benefit eligibility</span></span>
- <span data-ttu-id="55801-881">
personal health</span><span class="sxs-lookup"><span data-stu-id="55801-881">personal health</span></span>
- <span data-ttu-id="55801-882">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="55801-882">power of attorney</span></span>
- <span data-ttu-id="55801-883">
registration number</span><span class="sxs-lookup"><span data-stu-id="55801-883">registration number</span></span>
- <span data-ttu-id="55801-884">personal health number</span><span class="sxs-lookup"><span data-stu-id="55801-884">personal health number</span></span>
- <span data-ttu-id="55801-885">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="55801-885">practitioner referral</span></span>
- <span data-ttu-id="55801-886">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="55801-886">wellness professional</span></span>
- <span data-ttu-id="55801-887">
patient referral</span><span class="sxs-lookup"><span data-stu-id="55801-887">patient referral</span></span>
- <span data-ttu-id="55801-888">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="55801-888">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="55801-889">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="55801-889">Keyword_canada_provinces</span></span>

- <span data-ttu-id="55801-890">Nunavut</span><span class="sxs-lookup"><span data-stu-id="55801-890">Nunavut</span></span>
- <span data-ttu-id="55801-891">
Quebec</span><span class="sxs-lookup"><span data-stu-id="55801-891">Quebec</span></span>
- <span data-ttu-id="55801-892">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="55801-892">Northwest Territories</span></span>
- <span data-ttu-id="55801-893">
Ontario</span><span class="sxs-lookup"><span data-stu-id="55801-893">Ontario</span></span>
- <span data-ttu-id="55801-894">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="55801-894">British Columbia</span></span>
- <span data-ttu-id="55801-895">
Alberta</span><span class="sxs-lookup"><span data-stu-id="55801-895">Alberta</span></span>
- <span data-ttu-id="55801-896">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="55801-896">Saskatchewan</span></span>
- <span data-ttu-id="55801-897">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="55801-897">Manitoba</span></span>
- <span data-ttu-id="55801-898">
Yukon</span><span class="sxs-lookup"><span data-stu-id="55801-898">Yukon</span></span>
- <span data-ttu-id="55801-899">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="55801-899">Newfoundland and Labrador</span></span>
- <span data-ttu-id="55801-900">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="55801-900">New Brunswick</span></span>
- <span data-ttu-id="55801-901">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="55801-901">Nova Scotia</span></span>
- <span data-ttu-id="55801-902">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="55801-902">Prince Edward Island</span></span>
- <span data-ttu-id="55801-903">カナダ</span><span class="sxs-lookup"><span data-stu-id="55801-903">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="55801-904">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="55801-904">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-905">形式</span><span class="sxs-lookup"><span data-stu-id="55801-905">Format</span></span>

<span data-ttu-id="55801-906">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="55801-906">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-907">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-907">Pattern</span></span>

<span data-ttu-id="55801-908">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="55801-908">Formatted:</span></span>
- <span data-ttu-id="55801-909">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-909">Three digits</span></span> 
- <span data-ttu-id="55801-910">ハイフンまたはスペース 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-910">A hyphen or space</span></span> 
- <span data-ttu-id="55801-911">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-911">Three digits</span></span> 
- <span data-ttu-id="55801-912">ハイフンまたはスペース 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-912">A hyphen or space</span></span> 
- <span data-ttu-id="55801-913">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-913">Three digits</span></span>

<span data-ttu-id="55801-914">9 桁のフォーマットされていません。</span><span class="sxs-lookup"><span data-stu-id="55801-914">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-915">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-915">Checksum</span></span>

<span data-ttu-id="55801-916">はい</span><span class="sxs-lookup"><span data-stu-id="55801-916">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-917">定義</span><span class="sxs-lookup"><span data-stu-id="55801-917">Definition</span></span>

<span data-ttu-id="55801-918">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-918">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-919">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-919">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-920">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-920">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="55801-921">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-921">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="55801-922">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-922">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="55801-923">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-923">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="55801-924">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-924">The checksum passes.</span></span>

<span data-ttu-id="55801-925">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-925">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-926">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-926">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-927">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-927">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="55801-928">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-928">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-929">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-929">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="55801-930">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="55801-930">Keyword_sin</span></span>

- <span data-ttu-id="55801-931">sin</span><span class="sxs-lookup"><span data-stu-id="55801-931">sin</span></span> 
- <span data-ttu-id="55801-932">social insurance
</span><span class="sxs-lookup"><span data-stu-id="55801-932">social insurance</span></span> 
- <span data-ttu-id="55801-933">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="55801-933">numero d'assurance sociale</span></span> 
- <span data-ttu-id="55801-934">sins
</span><span class="sxs-lookup"><span data-stu-id="55801-934">sins</span></span> 
- <span data-ttu-id="55801-935">ssn</span><span class="sxs-lookup"><span data-stu-id="55801-935">ssn</span></span> 
- <span data-ttu-id="55801-936">ssn</span><span class="sxs-lookup"><span data-stu-id="55801-936">ssns</span></span> 
- <span data-ttu-id="55801-937">社会保障</span><span class="sxs-lookup"><span data-stu-id="55801-937">social security</span></span> 
- <span data-ttu-id="55801-938">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="55801-938">numero d'assurance social</span></span> 
- <span data-ttu-id="55801-939">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="55801-939">national identification number</span></span> 
- <span data-ttu-id="55801-940">
national id</span><span class="sxs-lookup"><span data-stu-id="55801-940">national id</span></span> 
- <span data-ttu-id="55801-941">sin#
</span><span class="sxs-lookup"><span data-stu-id="55801-941">sin#</span></span> 
- <span data-ttu-id="55801-942">soc ins
</span><span class="sxs-lookup"><span data-stu-id="55801-942">soc ins</span></span> 
- <span data-ttu-id="55801-943">social ins
</span><span class="sxs-lookup"><span data-stu-id="55801-943">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="55801-944">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="55801-944">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="55801-945">driver's license</span><span class="sxs-lookup"><span data-stu-id="55801-945">driver's license</span></span> 
- <span data-ttu-id="55801-946">drivers license</span><span class="sxs-lookup"><span data-stu-id="55801-946">drivers license</span></span> 
- <span data-ttu-id="55801-947">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-947">driver's licence</span></span> 
- <span data-ttu-id="55801-948">drivers licence</span><span class="sxs-lookup"><span data-stu-id="55801-948">drivers licence</span></span> 
- <span data-ttu-id="55801-949">DOB
</span><span class="sxs-lookup"><span data-stu-id="55801-949">DOB</span></span> 
- <span data-ttu-id="55801-950">誕生日</span><span class="sxs-lookup"><span data-stu-id="55801-950">Birthdate</span></span> 
- <span data-ttu-id="55801-951">誕生日 </span><span class="sxs-lookup"><span data-stu-id="55801-951">Birthday</span></span> 
- <span data-ttu-id="55801-952">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="55801-952">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="55801-953">チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="55801-953">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-954">形式</span><span class="sxs-lookup"><span data-stu-id="55801-954">Format</span></span>

<span data-ttu-id="55801-955">7-8 桁の数字と区切り文字チェックの数字または文字</span><span class="sxs-lookup"><span data-stu-id="55801-955">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-956">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-956">Pattern</span></span>

<span data-ttu-id="55801-957">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="55801-957">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="55801-958">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-958">1-2 digits</span></span> 
- <span data-ttu-id="55801-959">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-959">A period</span></span> 
- <span data-ttu-id="55801-960">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-960">Three digits</span></span> 
- <span data-ttu-id="55801-961">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-961">A period</span></span> 
- <span data-ttu-id="55801-962">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-962">Three digits</span></span> 
- <span data-ttu-id="55801-963">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-963">A dash</span></span> 
- <span data-ttu-id="55801-964">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="55801-964">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-965">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-965">Checksum</span></span>

<span data-ttu-id="55801-966">はい</span><span class="sxs-lookup"><span data-stu-id="55801-966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-967">定義</span><span class="sxs-lookup"><span data-stu-id="55801-967">Definition</span></span>

<span data-ttu-id="55801-968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-969">関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-969">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-970">Keyword_chile_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-970">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="55801-971">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-971">The checksum passes.</span></span>

<span data-ttu-id="55801-972">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-972">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-973">関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-973">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-974">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-974">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-975">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-975">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="55801-976">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-976">Keyword_chile_id_card</span></span>

- <span data-ttu-id="55801-977">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="55801-977">National Identification Number</span></span> 
- <span data-ttu-id="55801-978">Identity card</span><span class="sxs-lookup"><span data-stu-id="55801-978">Identity card</span></span> 
- <span data-ttu-id="55801-979">ID</span><span class="sxs-lookup"><span data-stu-id="55801-979">ID</span></span> 
- <span data-ttu-id="55801-980">Identification</span><span class="sxs-lookup"><span data-stu-id="55801-980">Identification</span></span> 
- <span data-ttu-id="55801-981">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="55801-981">Rol Único Nacional</span></span> 
- <span data-ttu-id="55801-982">実行</span><span class="sxs-lookup"><span data-stu-id="55801-982">RUN</span></span> 
- <span data-ttu-id="55801-983">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="55801-983">Rol Único Tributario</span></span> 
- <span data-ttu-id="55801-984">RUT
</span><span class="sxs-lookup"><span data-stu-id="55801-984">RUT</span></span> 
- <span data-ttu-id="55801-985">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="55801-985">Cédula de Identidad</span></span> 
- <span data-ttu-id="55801-986">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="55801-986">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="55801-987">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="55801-987">Tarjeta de identificación</span></span> 
- <span data-ttu-id="55801-988">Identificación
</span><span class="sxs-lookup"><span data-stu-id="55801-988">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="55801-989">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-989">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-990">形式</span><span class="sxs-lookup"><span data-stu-id="55801-990">Format</span></span>

<span data-ttu-id="55801-991">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-991">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-992">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-992">Pattern</span></span>

<span data-ttu-id="55801-993">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-993">18 digits:</span></span>
- <span data-ttu-id="55801-994">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-994">Six digits which are an address code</span></span> 
- <span data-ttu-id="55801-995">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-995">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="55801-996">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-996">Three digits which are an order code</span></span> 
- <span data-ttu-id="55801-997">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-997">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-998">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-998">Checksum</span></span>

<span data-ttu-id="55801-999">はい</span><span class="sxs-lookup"><span data-stu-id="55801-999">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1000">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1000">Definition</span></span>

<span data-ttu-id="55801-1001">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1001">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1002">関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1002">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1003">Keyword_china_resident_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1003">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="55801-1004">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1004">The checksum passes.</span></span>

<span data-ttu-id="55801-1005">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1005">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1006">関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1006">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1007">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1007">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1008">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1008">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="55801-1009">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="55801-1009">Keyword_china_resident_id</span></span>

- <span data-ttu-id="55801-1010">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="55801-1010">Resident Identity Card</span></span> 
- <span data-ttu-id="55801-1011">PRC
</span><span class="sxs-lookup"><span data-stu-id="55801-1011">PRC</span></span> 
- <span data-ttu-id="55801-1012">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="55801-1012">National Identification Card</span></span> 
- <span data-ttu-id="55801-1013">身份证 </span><span class="sxs-lookup"><span data-stu-id="55801-1013">身份证</span></span> 
- <span data-ttu-id="55801-1014">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="55801-1014">居民 身份证</span></span> 
- <span data-ttu-id="55801-1015">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="55801-1015">居民身份证</span></span> 
- <span data-ttu-id="55801-1016">鉴定

</span><span class="sxs-lookup"><span data-stu-id="55801-1016">鉴定</span></span> 
- <span data-ttu-id="55801-1017">身分證 </span><span class="sxs-lookup"><span data-stu-id="55801-1017">身分證</span></span> 
- <span data-ttu-id="55801-1018">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="55801-1018">居民 身份證</span></span>
- <span data-ttu-id="55801-1019">鑑定 </span><span class="sxs-lookup"><span data-stu-id="55801-1019">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="55801-1020">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="55801-1020">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1021">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1021">Format</span></span>

<span data-ttu-id="55801-1022">16 桁の数字書式を設定することができますが、または書式設定されていない (dddddddddddddddd) と、Luhn のテストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55801-1022">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1023">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1023">Pattern</span></span>

<span data-ttu-id="55801-1024">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="55801-1024">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1025">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1025">Checksum</span></span>

<span data-ttu-id="55801-1026">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="55801-1026">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1027">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1027">Definition</span></span>

<span data-ttu-id="55801-1028">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1028">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1029">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1029">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1030">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-1030">One of the following is true:</span></span>
    - <span data-ttu-id="55801-1031">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1031">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="55801-1032">Keyword_cc_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1032">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="55801-1033">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1033">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="55801-1034">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1034">The checksum passes.</span></span>

<span data-ttu-id="55801-1035">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1035">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1036">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1036">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1037">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1037">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1038">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1038">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="55801-1039">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="55801-1039">Keyword_cc_verification</span></span>

- <span data-ttu-id="55801-1040">card verification</span><span class="sxs-lookup"><span data-stu-id="55801-1040">card verification</span></span>
- <span data-ttu-id="55801-1041">card identification number</span><span class="sxs-lookup"><span data-stu-id="55801-1041">card identification number</span></span>
- <span data-ttu-id="55801-1042">cvn
</span><span class="sxs-lookup"><span data-stu-id="55801-1042">cvn</span></span>
- <span data-ttu-id="55801-1043">cid
</span><span class="sxs-lookup"><span data-stu-id="55801-1043">cid</span></span>
- <span data-ttu-id="55801-1044">cvc2</span><span class="sxs-lookup"><span data-stu-id="55801-1044">cvc2</span></span>
- <span data-ttu-id="55801-1045">cvv2</span><span class="sxs-lookup"><span data-stu-id="55801-1045">cvv2</span></span>
- <span data-ttu-id="55801-1046">pin block
</span><span class="sxs-lookup"><span data-stu-id="55801-1046">pin block</span></span>
- <span data-ttu-id="55801-1047">security code
</span><span class="sxs-lookup"><span data-stu-id="55801-1047">security code</span></span>
- <span data-ttu-id="55801-1048">security number
</span><span class="sxs-lookup"><span data-stu-id="55801-1048">security number</span></span>
- <span data-ttu-id="55801-1049">security no
</span><span class="sxs-lookup"><span data-stu-id="55801-1049">security no</span></span>
- <span data-ttu-id="55801-1050">issue number
</span><span class="sxs-lookup"><span data-stu-id="55801-1050">issue number</span></span>
- <span data-ttu-id="55801-1051">issue no
</span><span class="sxs-lookup"><span data-stu-id="55801-1051">issue no</span></span>
- <span data-ttu-id="55801-1052">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="55801-1052">cryptogramme</span></span>
- <span data-ttu-id="55801-1053">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="55801-1053">numéro de sécurité</span></span>
- <span data-ttu-id="55801-1054">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="55801-1054">numero de securite</span></span>
- <span data-ttu-id="55801-1055">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1055">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="55801-1056">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1056">kreditkartenprufnummer</span></span>
- <span data-ttu-id="55801-1057">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="55801-1057">prüfziffer</span></span>
- <span data-ttu-id="55801-1058">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="55801-1058">prufziffer</span></span>
- <span data-ttu-id="55801-1059">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="55801-1059">sicherheits Kode</span></span>
- <span data-ttu-id="55801-1060">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="55801-1060">sicherheitscode</span></span>
- <span data-ttu-id="55801-1061">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1061">sicherheitsnummer</span></span>
- <span data-ttu-id="55801-1062">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1062">verfalldatum</span></span>
- <span data-ttu-id="55801-1063">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="55801-1063">codice di verifica</span></span>
- <span data-ttu-id="55801-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="55801-p105">cod. sicurezza</span></span>
- <span data-ttu-id="55801-1066">代金引換払いの sicurezza</span><span class="sxs-lookup"><span data-stu-id="55801-1066">cod sicurezza</span></span>
- <span data-ttu-id="55801-1067">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="55801-1067">n autorizzazione</span></span>
- <span data-ttu-id="55801-1068">código
</span><span class="sxs-lookup"><span data-stu-id="55801-1068">código</span></span>
- <span data-ttu-id="55801-1069">codigo
</span><span class="sxs-lookup"><span data-stu-id="55801-1069">codigo</span></span>
- <span data-ttu-id="55801-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="55801-p106">cod. seg</span></span>
- <span data-ttu-id="55801-1072">代金引換払い seg</span><span class="sxs-lookup"><span data-stu-id="55801-1072">cod seg</span></span>
- <span data-ttu-id="55801-1073">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-1073">código de segurança</span></span>
- <span data-ttu-id="55801-1074">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-1074">codigo de seguranca</span></span>
- <span data-ttu-id="55801-1075">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-1075">codigo de segurança</span></span>
- <span data-ttu-id="55801-1076">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-1076">código de seguranca</span></span>
- <span data-ttu-id="55801-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-p107">cód. segurança</span></span>
- <span data-ttu-id="55801-p108">代金引換払いです。seguranca 代金引換払いです。segurança</span><span class="sxs-lookup"><span data-stu-id="55801-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="55801-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-p109">cód. seguranca</span></span>
- <span data-ttu-id="55801-1084">cód segurança</span><span class="sxs-lookup"><span data-stu-id="55801-1084">cód segurança</span></span>
- <span data-ttu-id="55801-1085">代金引換払いの代金引換払い segurança の seguranca</span><span class="sxs-lookup"><span data-stu-id="55801-1085">cod seguranca cod segurança</span></span>
- <span data-ttu-id="55801-1086">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="55801-1086">cód seguranca</span></span>
- <span data-ttu-id="55801-1087">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="55801-1087">número de verificação</span></span>
- <span data-ttu-id="55801-1088">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="55801-1088">numero de verificacao</span></span>
- <span data-ttu-id="55801-1089">ablauf
</span><span class="sxs-lookup"><span data-stu-id="55801-1089">ablauf</span></span>
- <span data-ttu-id="55801-1090">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="55801-1090">gültig bis</span></span>
- <span data-ttu-id="55801-1091">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1091">gültigkeitsdatum</span></span>
- <span data-ttu-id="55801-1092">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="55801-1092">gultig bis</span></span>
- <span data-ttu-id="55801-1093">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1093">gultigkeitsdatum</span></span>
- <span data-ttu-id="55801-1094">scadenza
</span><span class="sxs-lookup"><span data-stu-id="55801-1094">scadenza</span></span>
- <span data-ttu-id="55801-1095">data scad
</span><span class="sxs-lookup"><span data-stu-id="55801-1095">data scad</span></span>
- <span data-ttu-id="55801-1096">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="55801-1096">fecha de expiracion</span></span>
- <span data-ttu-id="55801-1097">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="55801-1097">fecha de venc</span></span>
- <span data-ttu-id="55801-1098">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="55801-1098">vencimiento</span></span>
- <span data-ttu-id="55801-1099">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="55801-1099">válido hasta</span></span>
- <span data-ttu-id="55801-1100">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="55801-1100">valido hasta</span></span>
- <span data-ttu-id="55801-1101">vto
</span><span class="sxs-lookup"><span data-stu-id="55801-1101">vto</span></span>
- <span data-ttu-id="55801-1102">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="55801-1102">data de expiração</span></span>
- <span data-ttu-id="55801-1103">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="55801-1103">data de expiracao</span></span>
- <span data-ttu-id="55801-1104">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="55801-1104">data em que expira</span></span>
- <span data-ttu-id="55801-1105">validade
</span><span class="sxs-lookup"><span data-stu-id="55801-1105">validade</span></span>
- <span data-ttu-id="55801-1106">valor
</span><span class="sxs-lookup"><span data-stu-id="55801-1106">valor</span></span>
- <span data-ttu-id="55801-1107">vencimento
</span><span class="sxs-lookup"><span data-stu-id="55801-1107">vencimento</span></span>
- <span data-ttu-id="55801-1108">Venc</span><span class="sxs-lookup"><span data-stu-id="55801-1108">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="55801-1109">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="55801-1109">Keyword_cc_name</span></span>

- <span data-ttu-id="55801-1110">amex</span><span class="sxs-lookup"><span data-stu-id="55801-1110">amex</span></span>
- <span data-ttu-id="55801-1111">
american express</span><span class="sxs-lookup"><span data-stu-id="55801-1111">american express</span></span>
- <span data-ttu-id="55801-1112">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="55801-1112">americanexpress</span></span>
- <span data-ttu-id="55801-1113">Visa</span><span class="sxs-lookup"><span data-stu-id="55801-1113">Visa</span></span>
- <span data-ttu-id="55801-1114">mastercard
</span><span class="sxs-lookup"><span data-stu-id="55801-1114">mastercard</span></span>
- <span data-ttu-id="55801-1115">master card
</span><span class="sxs-lookup"><span data-stu-id="55801-1115">master card</span></span>
- <span data-ttu-id="55801-1116">
mc
</span><span class="sxs-lookup"><span data-stu-id="55801-1116">mc</span></span> 
- <span data-ttu-id="55801-1117">mastercards</span><span class="sxs-lookup"><span data-stu-id="55801-1117">mastercards</span></span>
- <span data-ttu-id="55801-1118">
master cards</span><span class="sxs-lookup"><span data-stu-id="55801-1118">master cards</span></span>
- <span data-ttu-id="55801-1119">給仕のクラブ</span><span class="sxs-lookup"><span data-stu-id="55801-1119">diner's Club</span></span>
- <span data-ttu-id="55801-1120">diners club
</span><span class="sxs-lookup"><span data-stu-id="55801-1120">diners club</span></span>
- <span data-ttu-id="55801-1121">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="55801-1121">dinersclub</span></span>
- <span data-ttu-id="55801-1122">discover card
</span><span class="sxs-lookup"><span data-stu-id="55801-1122">discover card</span></span>
- <span data-ttu-id="55801-1123">discovercard
</span><span class="sxs-lookup"><span data-stu-id="55801-1123">discovercard</span></span>
- <span data-ttu-id="55801-1124">discover cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1124">discover cards</span></span>
- <span data-ttu-id="55801-1125">安全</span><span class="sxs-lookup"><span data-stu-id="55801-1125">JCB</span></span>
- <span data-ttu-id="55801-1126">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="55801-1126">japanese card bureau</span></span>
- <span data-ttu-id="55801-1127">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="55801-1127">carte blanche</span></span>
- <span data-ttu-id="55801-1128">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="55801-1128">carteblanche</span></span>
- <span data-ttu-id="55801-1129">credit card
</span><span class="sxs-lookup"><span data-stu-id="55801-1129">credit card</span></span>
- <span data-ttu-id="55801-1130">cc #</span><span class="sxs-lookup"><span data-stu-id="55801-1130">cc#</span></span>
- <span data-ttu-id="55801-1131">cc # します。</span><span class="sxs-lookup"><span data-stu-id="55801-1131">cc#:</span></span>
- <span data-ttu-id="55801-1132">
expiration date</span><span class="sxs-lookup"><span data-stu-id="55801-1132">expiration date</span></span>
- <span data-ttu-id="55801-1133">exp date
</span><span class="sxs-lookup"><span data-stu-id="55801-1133">exp date</span></span>
- <span data-ttu-id="55801-1134">
expiry date</span><span class="sxs-lookup"><span data-stu-id="55801-1134">expiry date</span></span>
- <span data-ttu-id="55801-1135">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="55801-1135">date d’expiration</span></span>
- <span data-ttu-id="55801-1136">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="55801-1136">date d'exp</span></span>
- <span data-ttu-id="55801-1137">
date expiration</span><span class="sxs-lookup"><span data-stu-id="55801-1137">date expiration</span></span>
- <span data-ttu-id="55801-1138">bank card
</span><span class="sxs-lookup"><span data-stu-id="55801-1138">bank card</span></span>
- <span data-ttu-id="55801-1139">
bankcard</span><span class="sxs-lookup"><span data-stu-id="55801-1139">bankcard</span></span>
- <span data-ttu-id="55801-1140">card number
</span><span class="sxs-lookup"><span data-stu-id="55801-1140">card number</span></span>
- <span data-ttu-id="55801-1141">card num
</span><span class="sxs-lookup"><span data-stu-id="55801-1141">card num</span></span>
- <span data-ttu-id="55801-1142">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-1142">cardnumber</span></span>
- <span data-ttu-id="55801-1143">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="55801-1143">cardnumbers</span></span>
- <span data-ttu-id="55801-1144">card numbers
</span><span class="sxs-lookup"><span data-stu-id="55801-1144">card numbers</span></span>
- <span data-ttu-id="55801-1145">creditcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1145">creditcard</span></span>
- <span data-ttu-id="55801-1146">credit cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1146">credit cards</span></span>
- <span data-ttu-id="55801-1147">creditcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1147">creditcards</span></span>
- <span data-ttu-id="55801-1148">ccn
</span><span class="sxs-lookup"><span data-stu-id="55801-1148">ccn</span></span>
- <span data-ttu-id="55801-1149">card holder
</span><span class="sxs-lookup"><span data-stu-id="55801-1149">card holder</span></span>
- <span data-ttu-id="55801-1150">cardholder
</span><span class="sxs-lookup"><span data-stu-id="55801-1150">cardholder</span></span>
- <span data-ttu-id="55801-1151">card holders
</span><span class="sxs-lookup"><span data-stu-id="55801-1151">card holders</span></span>
- <span data-ttu-id="55801-1152">cardholders
</span><span class="sxs-lookup"><span data-stu-id="55801-1152">cardholders</span></span>
- <span data-ttu-id="55801-1153">check card
</span><span class="sxs-lookup"><span data-stu-id="55801-1153">check card</span></span>
- <span data-ttu-id="55801-1154">checkcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1154">checkcard</span></span>
- <span data-ttu-id="55801-1155">check cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1155">check cards</span></span>
- <span data-ttu-id="55801-1156">checkcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1156">checkcards</span></span>
- <span data-ttu-id="55801-1157">debit card
</span><span class="sxs-lookup"><span data-stu-id="55801-1157">debit card</span></span>
- <span data-ttu-id="55801-1158">debitcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1158">debitcard</span></span>
- <span data-ttu-id="55801-1159">debit cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1159">debit cards</span></span>
- <span data-ttu-id="55801-1160">debitcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1160">debitcards</span></span>
- <span data-ttu-id="55801-1161">atm card
</span><span class="sxs-lookup"><span data-stu-id="55801-1161">atm card</span></span>
- <span data-ttu-id="55801-1162">atmcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1162">atmcard</span></span>
- <span data-ttu-id="55801-1163">atm cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1163">atm cards</span></span>
- <span data-ttu-id="55801-1164">atmcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1164">atmcards</span></span>
- <span data-ttu-id="55801-1165">
enroute</span><span class="sxs-lookup"><span data-stu-id="55801-1165">enroute</span></span>
- <span data-ttu-id="55801-1166">
en route</span><span class="sxs-lookup"><span data-stu-id="55801-1166">en route</span></span>
- <span data-ttu-id="55801-1167">card type
</span><span class="sxs-lookup"><span data-stu-id="55801-1167">card type</span></span>
- <span data-ttu-id="55801-1168">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="55801-1168">carte bancaire</span></span>
- <span data-ttu-id="55801-1169">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="55801-1169">carte de crédit</span></span>
- <span data-ttu-id="55801-1170">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="55801-1170">carte de credit</span></span>
- <span data-ttu-id="55801-1171">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1171">numéro de carte</span></span>
- <span data-ttu-id="55801-1172">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1172">numero de carte</span></span>
- <span data-ttu-id="55801-1173">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1173">nº de la carte</span></span>
- <span data-ttu-id="55801-1174">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1174">nº de carte</span></span>
- <span data-ttu-id="55801-1175">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="55801-1175">kreditkarte</span></span>
- <span data-ttu-id="55801-1176">karte
</span><span class="sxs-lookup"><span data-stu-id="55801-1176">karte</span></span>
- <span data-ttu-id="55801-1177">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="55801-1177">karteninhaber</span></span>
- <span data-ttu-id="55801-1178">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="55801-1178">karteninhabers</span></span>
- <span data-ttu-id="55801-1179">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="55801-1179">kreditkarteninhaber</span></span>
- <span data-ttu-id="55801-1180">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="55801-1180">kreditkarteninstitut</span></span>
- <span data-ttu-id="55801-1181">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="55801-1181">kreditkartentyp</span></span>
- <span data-ttu-id="55801-1182">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="55801-1182">eigentümername</span></span>
- <span data-ttu-id="55801-1183">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="55801-1183">kartennr</span></span> 
- <span data-ttu-id="55801-1184">kartennummer</span><span class="sxs-lookup"><span data-stu-id="55801-1184">kartennummer</span></span>
- <span data-ttu-id="55801-1185">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="55801-1185">kreditkartennummer</span></span>
- <span data-ttu-id="55801-1186">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="55801-1186">kreditkarten-nummer</span></span>
- <span data-ttu-id="55801-1187">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1187">carta di credito</span></span>
- <span data-ttu-id="55801-1188">carta credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1188">carta credito</span></span>
- <span data-ttu-id="55801-1189">carta</span><span class="sxs-lookup"><span data-stu-id="55801-1189">carta</span></span>
- <span data-ttu-id="55801-1190">n carta</span><span class="sxs-lookup"><span data-stu-id="55801-1190">n carta</span></span>
- <span data-ttu-id="55801-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="55801-p110">nr. carta</span></span>
- <span data-ttu-id="55801-1193">nr carta</span><span class="sxs-lookup"><span data-stu-id="55801-1193">nr carta</span></span>
- <span data-ttu-id="55801-1194">numero carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1194">numero carta</span></span>
- <span data-ttu-id="55801-1195">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1195">numero della carta</span></span>
- <span data-ttu-id="55801-1196">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1196">numero di carta</span></span>
- <span data-ttu-id="55801-1197">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1197">tarjeta credito</span></span>
- <span data-ttu-id="55801-1198">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1198">tarjeta de credito</span></span>
- <span data-ttu-id="55801-1199">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="55801-1199">tarjeta crédito</span></span>
- <span data-ttu-id="55801-1200">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="55801-1200">tarjeta de crédito</span></span>
- <span data-ttu-id="55801-1201">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="55801-1201">tarjeta de atm</span></span>
- <span data-ttu-id="55801-1202">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="55801-1202">tarjeta atm</span></span>
- <span data-ttu-id="55801-1203">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1203">tarjeta debito</span></span>
- <span data-ttu-id="55801-1204">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1204">tarjeta de debito</span></span>
- <span data-ttu-id="55801-1205">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="55801-1205">tarjeta débito</span></span>
- <span data-ttu-id="55801-1206">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="55801-1206">tarjeta de débito</span></span>
- <span data-ttu-id="55801-1207">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-1207">nº de tarjeta</span></span>
- <span data-ttu-id="55801-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-p111">no. de tarjeta</span></span>
- <span data-ttu-id="55801-1210">なし de tarjeta</span><span class="sxs-lookup"><span data-stu-id="55801-1210">no de tarjeta</span></span>
- <span data-ttu-id="55801-1211">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-1211">numero de tarjeta</span></span>
- <span data-ttu-id="55801-1212">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-1212">número de tarjeta</span></span>
- <span data-ttu-id="55801-1213">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="55801-1213">tarjeta no</span></span>
- <span data-ttu-id="55801-1214">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="55801-1214">tarjetahabiente</span></span>
- <span data-ttu-id="55801-1215">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="55801-1215">cartão de crédito</span></span>
- <span data-ttu-id="55801-1216">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1216">cartão de credito</span></span>
- <span data-ttu-id="55801-1217">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="55801-1217">cartao de crédito</span></span>
- <span data-ttu-id="55801-1218">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1218">cartao de credito</span></span>
- <span data-ttu-id="55801-1219">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="55801-1219">cartão de débito</span></span>
- <span data-ttu-id="55801-1220">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="55801-1220">cartao de débito</span></span>
- <span data-ttu-id="55801-1221">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1221">cartão de debito</span></span>
- <span data-ttu-id="55801-1222">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1222">cartao de debito</span></span>
- <span data-ttu-id="55801-1223">débito automático</span><span class="sxs-lookup"><span data-stu-id="55801-1223">débito automático</span></span>
- <span data-ttu-id="55801-1224">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="55801-1224">debito automatico</span></span>
- <span data-ttu-id="55801-1225">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="55801-1225">número do cartão</span></span>
- <span data-ttu-id="55801-1226">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-1226">numero do cartão</span></span> 
- <span data-ttu-id="55801-1227">número do cartao</span><span class="sxs-lookup"><span data-stu-id="55801-1227">número do cartao</span></span>
- <span data-ttu-id="55801-1228">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="55801-1228">numero do cartao</span></span>
- <span data-ttu-id="55801-1229">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-1229">número de cartão</span></span>
- <span data-ttu-id="55801-1230">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-1230">numero de cartão</span></span>
- <span data-ttu-id="55801-1231">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1231">número de cartao</span></span>
- <span data-ttu-id="55801-1232">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1232">numero de cartao</span></span>
- <span data-ttu-id="55801-1233">nº は cartão</span><span class="sxs-lookup"><span data-stu-id="55801-1233">nº do cartão</span></span>
- <span data-ttu-id="55801-1234">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1234">nº do cartao</span></span>
- <span data-ttu-id="55801-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-p112">nº. do cartão</span></span>
- <span data-ttu-id="55801-1237">なしは cartão</span><span class="sxs-lookup"><span data-stu-id="55801-1237">no do cartão</span></span>
- <span data-ttu-id="55801-1238">なしは cartao</span><span class="sxs-lookup"><span data-stu-id="55801-1238">no do cartao</span></span>
- <span data-ttu-id="55801-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-p113">no. do cartão</span></span>
- <span data-ttu-id="55801-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="55801-1243">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="55801-1243">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1244">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1244">Format</span></span>

<span data-ttu-id="55801-1245">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1245">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1246">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1246">Pattern</span></span>

<span data-ttu-id="55801-1247">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-1247">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1248">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1248">Checksum</span></span>

<span data-ttu-id="55801-1249">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1249">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1250">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1250">Definition</span></span>

<span data-ttu-id="55801-1251">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1251">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1252">関数 Func_croatia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1252">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1253">Keyword_croatia_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1253">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1254">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1254">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="55801-1255">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-1255">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="55801-1256">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="55801-1256">Croatian identity card</span></span>
- <span data-ttu-id="55801-1257">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="55801-1257">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="55801-1258">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-1258">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1259">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1259">Format</span></span>

<span data-ttu-id="55801-1260">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1260">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1261">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1261">Pattern</span></span>

<span data-ttu-id="55801-1262">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-1262">10 digits:</span></span>
- <span data-ttu-id="55801-1263">DDMMYY の形式で生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-1263">Six digits in the form DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="55801-1264">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="55801-1264">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1265">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1265">Checksum</span></span>

<span data-ttu-id="55801-1266">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1266">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1267">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1267">Definition</span></span>

<span data-ttu-id="55801-1268">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1268">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1269">関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1269">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1270">Keyword_croatia_oib_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1270">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="55801-1271">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1271">The checksum passes.</span></span>

<span data-ttu-id="55801-1272">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1272">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1273">関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1273">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1274">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1274">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1275">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1275">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="55801-1276">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="55801-1276">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="55801-1277">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="55801-1277">Personal Identification Number</span></span>
- <span data-ttu-id="55801-1278">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="55801-1278">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="55801-1279">OIB
</span><span class="sxs-lookup"><span data-stu-id="55801-1279">OIB</span></span> 

   
## <a name="czech-national-identity-card-number"></a><span data-ttu-id="55801-1280">チェコの国民身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="55801-1280">Czech National Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1281">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1281">Format</span></span>

<span data-ttu-id="55801-1282">スラッシュを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1282">10 digits containing a forward slash</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1283">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1283">Pattern</span></span>

<span data-ttu-id="55801-1284">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-1284">10 digits:</span></span>
- <span data-ttu-id="55801-1285">生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-1285">Six digits which are the date of birth</span></span> 
- <span data-ttu-id="55801-1286">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-1286">A forward slash</span></span> 
- <span data-ttu-id="55801-1287">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="55801-1287">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1288">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1288">Checksum</span></span>

<span data-ttu-id="55801-1289">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1289">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1290">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1290">Definition</span></span>

<span data-ttu-id="55801-p115">DLP ポリシーとは、85% をこの種類の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_czech_id_card 関数は、パターンに一致するコンテンツを検索します。。Keyword_czech_id_card からキーワードを検出するとします。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="55801-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech National Identity Card Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_czech_id_card"/>
     <Match idRef="Keyword_czech_id_card"/>
  </Pattern>
</Entity>
```


### <a name="keywords"></a><span data-ttu-id="55801-1294">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1294">Keywords</span></span>

- <span data-ttu-id="55801-1295">Keyword_czech_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-1295">Keyword_czech_id_card</span></span>
- <span data-ttu-id="55801-1296">Czech national identity card</span><span class="sxs-lookup"><span data-stu-id="55801-1296">Czech national identity card</span></span>
- <span data-ttu-id="55801-1297">Občanský průka</span><span class="sxs-lookup"><span data-stu-id="55801-1297">Občanský průka</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="55801-1298">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="55801-1298">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1299">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1299">Format</span></span>

<span data-ttu-id="55801-1300">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1300">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1301">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1301">Pattern</span></span>

<span data-ttu-id="55801-1302">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-1302">10 digits:</span></span>
- <span data-ttu-id="55801-1303">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-1303">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="55801-1304">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-1304">A hyphen</span></span> 
- <span data-ttu-id="55801-1305">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="55801-1305">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1306">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1306">Checksum</span></span>

<span data-ttu-id="55801-1307">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1307">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1308">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1308">Definition</span></span>

<span data-ttu-id="55801-p116">DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Regex_denmark_id の正規表現パターンに一致するコンテンツを検索します。Keyword_denmark_id からキーワードを検出するとします。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="55801-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1312">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1312">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="55801-1313">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="55801-1313">Keyword_denmark_id</span></span>

- <span data-ttu-id="55801-1314">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="55801-1314">Personal Identification Number</span></span>
- <span data-ttu-id="55801-1315">CPR</span><span class="sxs-lookup"><span data-stu-id="55801-1315">CPR</span></span>
- <span data-ttu-id="55801-1316">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="55801-1316">Det Centrale Personregister</span></span>
- <span data-ttu-id="55801-1317">Personnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1317">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="55801-1318">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-1318">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1319">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1319">Format</span></span>

<span data-ttu-id="55801-1320">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1320">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1321">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1321">Pattern</span></span>

<span data-ttu-id="55801-1322">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="55801-1322">Pattern must include all of the following:</span></span>
- <span data-ttu-id="55801-1323">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="55801-1323">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="55801-1324">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="55801-1324">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="55801-1325">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="55801-1325">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1326">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1326">Checksum</span></span>

<span data-ttu-id="55801-1327">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1327">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1328">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1328">Definition</span></span>

<span data-ttu-id="55801-1329">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1329">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1330">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1330">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1331">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1331">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1332">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1332">Keywords</span></span>

<span data-ttu-id="55801-1333">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1333">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="55801-1334">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="55801-1334">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1335">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1335">Format</span></span>

<span data-ttu-id="55801-1336">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1336">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1337">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1337">Pattern</span></span>

<span data-ttu-id="55801-1338">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="55801-1338">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1339">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1339">Checksum</span></span>

<span data-ttu-id="55801-1340">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1340">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1341">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1341">Definition</span></span>

<span data-ttu-id="55801-1342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1343">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1343">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1344">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-1344">At least one of the following is true:</span></span>
    - <span data-ttu-id="55801-1345">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1345">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="55801-1346">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1346">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="55801-1347">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1347">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="55801-1348">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1348">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="55801-1349">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1349">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="55801-1350">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1350">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1351">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1351">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="55801-1352">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="55801-1352">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="55801-1353">アカウント番号</span><span class="sxs-lookup"><span data-stu-id="55801-1353">account number</span></span> 
- <span data-ttu-id="55801-1354">card number
</span><span class="sxs-lookup"><span data-stu-id="55801-1354">card number</span></span> 
- <span data-ttu-id="55801-1355">card no.
</span><span class="sxs-lookup"><span data-stu-id="55801-1355">card no.</span></span> 
- <span data-ttu-id="55801-1356">security number
</span><span class="sxs-lookup"><span data-stu-id="55801-1356">security number</span></span> 
- <span data-ttu-id="55801-1357">cc #</span><span class="sxs-lookup"><span data-stu-id="55801-1357">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="55801-1358">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="55801-1358">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="55801-1359">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="55801-1359">acct nbr</span></span> 
- <span data-ttu-id="55801-1360">acct num
</span><span class="sxs-lookup"><span data-stu-id="55801-1360">acct num</span></span> 
- <span data-ttu-id="55801-1361">acct no
</span><span class="sxs-lookup"><span data-stu-id="55801-1361">acct no</span></span> 
- <span data-ttu-id="55801-1362">american express
</span><span class="sxs-lookup"><span data-stu-id="55801-1362">american express</span></span> 
- <span data-ttu-id="55801-1363">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="55801-1363">americanexpress</span></span> 
- <span data-ttu-id="55801-1364">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="55801-1364">americano espresso</span></span> 
- <span data-ttu-id="55801-1365">amex</span><span class="sxs-lookup"><span data-stu-id="55801-1365">amex</span></span> 
- <span data-ttu-id="55801-1366">atm card
</span><span class="sxs-lookup"><span data-stu-id="55801-1366">atm card</span></span> 
- <span data-ttu-id="55801-1367">atm cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1367">atm cards</span></span> 
- <span data-ttu-id="55801-1368">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1368">atm kaart</span></span> 
- <span data-ttu-id="55801-1369">atmcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1369">atmcard</span></span> 
- <span data-ttu-id="55801-1370">atmcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1370">atmcards</span></span> 
- <span data-ttu-id="55801-1371">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1371">atmkaart</span></span> 
- <span data-ttu-id="55801-1372">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="55801-1372">atmkaarten</span></span> 
- <span data-ttu-id="55801-1373">bancontact
</span><span class="sxs-lookup"><span data-stu-id="55801-1373">bancontact</span></span> 
- <span data-ttu-id="55801-1374">bank card
</span><span class="sxs-lookup"><span data-stu-id="55801-1374">bank card</span></span> 
- <span data-ttu-id="55801-1375">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1375">bankkaart</span></span> 
- <span data-ttu-id="55801-1376">card holder
</span><span class="sxs-lookup"><span data-stu-id="55801-1376">card holder</span></span> 
- <span data-ttu-id="55801-1377">card holders
</span><span class="sxs-lookup"><span data-stu-id="55801-1377">card holders</span></span> 
- <span data-ttu-id="55801-1378">card num
</span><span class="sxs-lookup"><span data-stu-id="55801-1378">card num</span></span> 
- <span data-ttu-id="55801-1379">card number
</span><span class="sxs-lookup"><span data-stu-id="55801-1379">card number</span></span> 
- <span data-ttu-id="55801-1380">card numbers
</span><span class="sxs-lookup"><span data-stu-id="55801-1380">card numbers</span></span> 
- <span data-ttu-id="55801-1381">card type
</span><span class="sxs-lookup"><span data-stu-id="55801-1381">card type</span></span> 
- <span data-ttu-id="55801-1382">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="55801-1382">cardano numerico</span></span> 
- <span data-ttu-id="55801-1383">cardholder
</span><span class="sxs-lookup"><span data-stu-id="55801-1383">cardholder</span></span> 
- <span data-ttu-id="55801-1384">cardholders
</span><span class="sxs-lookup"><span data-stu-id="55801-1384">cardholders</span></span> 
- <span data-ttu-id="55801-1385">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-1385">cardnumber</span></span> 
- <span data-ttu-id="55801-1386">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="55801-1386">cardnumbers</span></span> 
- <span data-ttu-id="55801-1387">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="55801-1387">carta bianca</span></span> 
- <span data-ttu-id="55801-1388">carta credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1388">carta credito</span></span> 
- <span data-ttu-id="55801-1389">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1389">carta di credito</span></span> 
- <span data-ttu-id="55801-1390">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1390">cartao de credito</span></span> 
- <span data-ttu-id="55801-1391">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="55801-1391">cartao de crédito</span></span> 
- <span data-ttu-id="55801-1392">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1392">cartao de debito</span></span> 
- <span data-ttu-id="55801-1393">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="55801-1393">cartao de débito</span></span> 
- <span data-ttu-id="55801-1394">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="55801-1394">carte bancaire</span></span> 
- <span data-ttu-id="55801-1395">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="55801-1395">carte blanche</span></span> 
- <span data-ttu-id="55801-1396">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="55801-1396">carte bleue</span></span> 
- <span data-ttu-id="55801-1397">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="55801-1397">carte de credit</span></span> 
- <span data-ttu-id="55801-1398">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="55801-1398">carte de crédit</span></span> 
- <span data-ttu-id="55801-1399">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1399">carte di credito</span></span> 
- <span data-ttu-id="55801-1400">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="55801-1400">carteblanche</span></span> 
- <span data-ttu-id="55801-1401">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1401">cartão de credito</span></span> 
- <span data-ttu-id="55801-1402">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="55801-1402">cartão de crédito</span></span> 
- <span data-ttu-id="55801-1403">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1403">cartão de debito</span></span> 
- <span data-ttu-id="55801-1404">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="55801-1404">cartão de débito</span></span> 
- <span data-ttu-id="55801-1405">cb
</span><span class="sxs-lookup"><span data-stu-id="55801-1405">cb</span></span> 
- <span data-ttu-id="55801-1406">ccn
</span><span class="sxs-lookup"><span data-stu-id="55801-1406">ccn</span></span> 
- <span data-ttu-id="55801-1407">check card
</span><span class="sxs-lookup"><span data-stu-id="55801-1407">check card</span></span> 
- <span data-ttu-id="55801-1408">check cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1408">check cards</span></span> 
- <span data-ttu-id="55801-1409">checkcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1409">checkcard</span></span>
- <span data-ttu-id="55801-1410">checkcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1410">checkcards</span></span> 
- <span data-ttu-id="55801-1411">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1411">chequekaart</span></span> 
- <span data-ttu-id="55801-1412">cirrus
</span><span class="sxs-lookup"><span data-stu-id="55801-1412">cirrus</span></span> 
- <span data-ttu-id="55801-1413">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="55801-1413">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="55801-1414">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1414">controlekaart</span></span> 
- <span data-ttu-id="55801-1415">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="55801-1415">controlekaarten</span></span> 
- <span data-ttu-id="55801-1416">credit card
</span><span class="sxs-lookup"><span data-stu-id="55801-1416">credit card</span></span> 
- <span data-ttu-id="55801-1417">credit cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1417">credit cards</span></span> 
- <span data-ttu-id="55801-1418">creditcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1418">creditcard</span></span> 
- <span data-ttu-id="55801-1419">creditcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1419">creditcards</span></span> 
- <span data-ttu-id="55801-1420">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1420">debetkaart</span></span> 
- <span data-ttu-id="55801-1421">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="55801-1421">debetkaarten</span></span> 
- <span data-ttu-id="55801-1422">debit card
</span><span class="sxs-lookup"><span data-stu-id="55801-1422">debit card</span></span> 
- <span data-ttu-id="55801-1423">debit cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1423">debit cards</span></span> 
- <span data-ttu-id="55801-1424">debitcard
</span><span class="sxs-lookup"><span data-stu-id="55801-1424">debitcard</span></span> 
- <span data-ttu-id="55801-1425">debitcards
</span><span class="sxs-lookup"><span data-stu-id="55801-1425">debitcards</span></span> 
- <span data-ttu-id="55801-1426">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="55801-1426">debito automatico</span></span> 
- <span data-ttu-id="55801-1427">diners club
</span><span class="sxs-lookup"><span data-stu-id="55801-1427">diners club</span></span> 
- <span data-ttu-id="55801-1428">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="55801-1428">dinersclub</span></span> 
- <span data-ttu-id="55801-1429">検出</span><span class="sxs-lookup"><span data-stu-id="55801-1429">discover</span></span> 
- <span data-ttu-id="55801-1430">discover card
</span><span class="sxs-lookup"><span data-stu-id="55801-1430">discover card</span></span> 
- <span data-ttu-id="55801-1431">discover cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1431">discover cards</span></span> 
- <span data-ttu-id="55801-1432">discovercard
</span><span class="sxs-lookup"><span data-stu-id="55801-1432">discovercard</span></span> 
- <span data-ttu-id="55801-1433">discovercards
</span><span class="sxs-lookup"><span data-stu-id="55801-1433">discovercards</span></span> 
- <span data-ttu-id="55801-1434">débito automático</span><span class="sxs-lookup"><span data-stu-id="55801-1434">débito automático</span></span>
- <span data-ttu-id="55801-1435">
edc
</span><span class="sxs-lookup"><span data-stu-id="55801-1435">edc</span></span> 
- <span data-ttu-id="55801-1436">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="55801-1436">eigentümername</span></span> 
- <span data-ttu-id="55801-1437">european debit card
</span><span class="sxs-lookup"><span data-stu-id="55801-1437">european debit card</span></span> 
- <span data-ttu-id="55801-1438">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1438">hoofdkaart</span></span> 
- <span data-ttu-id="55801-1439">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="55801-1439">hoofdkaarten</span></span> 
- <span data-ttu-id="55801-1440">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="55801-1440">in viaggio</span></span> 
- <span data-ttu-id="55801-1441">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="55801-1441">japanese card bureau</span></span> 
- <span data-ttu-id="55801-1442">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="55801-1442">japanse kaartdienst</span></span> 
- <span data-ttu-id="55801-1443">jcb
</span><span class="sxs-lookup"><span data-stu-id="55801-1443">jcb</span></span> 
- <span data-ttu-id="55801-1444">kaart
</span><span class="sxs-lookup"><span data-stu-id="55801-1444">kaart</span></span> 
- <span data-ttu-id="55801-1445">kaart num
</span><span class="sxs-lookup"><span data-stu-id="55801-1445">kaart num</span></span> 
- <span data-ttu-id="55801-1446">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="55801-1446">kaartaantal</span></span> 
- <span data-ttu-id="55801-1447">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="55801-1447">kaartaantallen</span></span> 
- <span data-ttu-id="55801-1448">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="55801-1448">kaarthouder</span></span> 
- <span data-ttu-id="55801-1449">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="55801-1449">kaarthouders</span></span> 
- <span data-ttu-id="55801-1450">karte
</span><span class="sxs-lookup"><span data-stu-id="55801-1450">karte</span></span>  
- <span data-ttu-id="55801-1451">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="55801-1451">karteninhaber</span></span> 
- <span data-ttu-id="55801-1452">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="55801-1452">karteninhabers</span></span>
- <span data-ttu-id="55801-1453">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="55801-1453">kartennr</span></span> 
- <span data-ttu-id="55801-1454">kartennummer</span><span class="sxs-lookup"><span data-stu-id="55801-1454">kartennummer</span></span> 
- <span data-ttu-id="55801-1455">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="55801-1455">kreditkarte</span></span> 
- <span data-ttu-id="55801-1456">kreditkarten nummer</span><span class="sxs-lookup"><span data-stu-id="55801-1456">kreditkarten-nummer</span></span> 
- <span data-ttu-id="55801-1457">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="55801-1457">kreditkarteninhaber</span></span> 
- <span data-ttu-id="55801-1458">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="55801-1458">kreditkarteninstitut</span></span> 
- <span data-ttu-id="55801-1459">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1459">kreditkartennummer</span></span> 
- <span data-ttu-id="55801-1460">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="55801-1460">kreditkartentyp</span></span> 
- <span data-ttu-id="55801-1461">maestro
</span><span class="sxs-lookup"><span data-stu-id="55801-1461">maestro</span></span> 
- <span data-ttu-id="55801-1462">master card
</span><span class="sxs-lookup"><span data-stu-id="55801-1462">master card</span></span> 
- <span data-ttu-id="55801-1463">master cards
</span><span class="sxs-lookup"><span data-stu-id="55801-1463">master cards</span></span> 
- <span data-ttu-id="55801-1464">mastercard
</span><span class="sxs-lookup"><span data-stu-id="55801-1464">mastercard</span></span> 
- <span data-ttu-id="55801-1465">mastercards</span><span class="sxs-lookup"><span data-stu-id="55801-1465">mastercards</span></span> 
- <span data-ttu-id="55801-1466">mc</span><span class="sxs-lookup"><span data-stu-id="55801-1466">mc</span></span> 
- <span data-ttu-id="55801-1467">mister cash
</span><span class="sxs-lookup"><span data-stu-id="55801-1467">mister cash</span></span> 
- <span data-ttu-id="55801-1468">n carta</span><span class="sxs-lookup"><span data-stu-id="55801-1468">n carta</span></span> 
- <span data-ttu-id="55801-1469">carta</span><span class="sxs-lookup"><span data-stu-id="55801-1469">carta</span></span> 
- <span data-ttu-id="55801-1470">なし de tarjeta</span><span class="sxs-lookup"><span data-stu-id="55801-1470">no de tarjeta</span></span> 
- <span data-ttu-id="55801-1471">なしは cartao</span><span class="sxs-lookup"><span data-stu-id="55801-1471">no do cartao</span></span> 
- <span data-ttu-id="55801-1472">なしは cartão</span><span class="sxs-lookup"><span data-stu-id="55801-1472">no do cartão</span></span> 
- <span data-ttu-id="55801-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="55801-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-p118">no. do cartao</span></span> 
- <span data-ttu-id="55801-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-p119">no. do cartão</span></span> 
- <span data-ttu-id="55801-1479">nr carta</span><span class="sxs-lookup"><span data-stu-id="55801-1479">nr carta</span></span> 
- <span data-ttu-id="55801-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="55801-p120">nr. carta</span></span> 
- <span data-ttu-id="55801-1482">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1482">numeri di scheda</span></span> 
- <span data-ttu-id="55801-1483">numero carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1483">numero carta</span></span> 
- <span data-ttu-id="55801-1484">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1484">numero de cartao</span></span> 
- <span data-ttu-id="55801-1485">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1485">numero de carte</span></span> 
- <span data-ttu-id="55801-1486">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-1486">numero de cartão</span></span> 
- <span data-ttu-id="55801-1487">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-1487">numero de tarjeta</span></span>
- <span data-ttu-id="55801-1488">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1488">numero della carta</span></span> 
- <span data-ttu-id="55801-1489">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1489">numero di carta</span></span> 
- <span data-ttu-id="55801-1490">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1490">numero di scheda</span></span> 
- <span data-ttu-id="55801-1491">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1491">numero do cartao</span></span> 
- <span data-ttu-id="55801-1492">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-1492">numero do cartão</span></span> 
- <span data-ttu-id="55801-1493">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1493">numéro de carte</span></span> 
- <span data-ttu-id="55801-1494">nº carta
</span><span class="sxs-lookup"><span data-stu-id="55801-1494">nº carta</span></span> 
- <span data-ttu-id="55801-1495">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1495">nº de carte</span></span> 
- <span data-ttu-id="55801-1496">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="55801-1496">nº de la carte</span></span> 
- <span data-ttu-id="55801-1497">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-1497">nº de tarjeta</span></span> 
- <span data-ttu-id="55801-1498">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1498">nº do cartao</span></span> 
- <span data-ttu-id="55801-1499">nº は cartão</span><span class="sxs-lookup"><span data-stu-id="55801-1499">nº do cartão</span></span> 
- <span data-ttu-id="55801-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-p121">nº. do cartão</span></span> 
- <span data-ttu-id="55801-1502">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="55801-1502">número de cartao</span></span> 
- <span data-ttu-id="55801-1503">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="55801-1503">número de cartão</span></span> 
- <span data-ttu-id="55801-1504">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="55801-1504">número de tarjeta</span></span> 
- <span data-ttu-id="55801-1505">número do cartao</span><span class="sxs-lookup"><span data-stu-id="55801-1505">número do cartao</span></span> 
- <span data-ttu-id="55801-1506">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="55801-1506">scheda dell'assegno</span></span> 
- <span data-ttu-id="55801-1507">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="55801-1507">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="55801-1508">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="55801-1508">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="55801-1509">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="55801-1509">scheda della banca</span></span> 
- <span data-ttu-id="55801-1510">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="55801-1510">scheda di controllo</span></span> 
- <span data-ttu-id="55801-1511">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1511">scheda di debito</span></span> 
- <span data-ttu-id="55801-1512">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="55801-1512">scheda matrice</span></span> 
- <span data-ttu-id="55801-1513">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="55801-1513">schede dell'atmosfera</span></span> 
- <span data-ttu-id="55801-1514">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="55801-1514">schede di controllo</span></span> 
- <span data-ttu-id="55801-1515">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1515">schede di debito</span></span> 
- <span data-ttu-id="55801-1516">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="55801-1516">schede matrici</span></span> 
- <span data-ttu-id="55801-1517">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1517">scoprono la scheda</span></span> 
- <span data-ttu-id="55801-1518">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="55801-1518">scoprono le schede</span></span> 
- <span data-ttu-id="55801-1519">solo
</span><span class="sxs-lookup"><span data-stu-id="55801-1519">solo</span></span> 
- <span data-ttu-id="55801-1520">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1520">supporti di scheda</span></span> 
- <span data-ttu-id="55801-1521">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1521">supporto di scheda</span></span> 
- <span data-ttu-id="55801-1522">switch
</span><span class="sxs-lookup"><span data-stu-id="55801-1522">switch</span></span> 
- <span data-ttu-id="55801-1523">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="55801-1523">tarjeta atm</span></span> 
- <span data-ttu-id="55801-1524">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1524">tarjeta credito</span></span> 
- <span data-ttu-id="55801-1525">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="55801-1525">tarjeta de atm</span></span> 
- <span data-ttu-id="55801-1526">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="55801-1526">tarjeta de credito</span></span> 
- <span data-ttu-id="55801-1527">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1527">tarjeta de debito</span></span> 
- <span data-ttu-id="55801-1528">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="55801-1528">tarjeta debito</span></span> 
- <span data-ttu-id="55801-1529">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="55801-1529">tarjeta no</span></span>
- <span data-ttu-id="55801-1530">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="55801-1530">tarjetahabiente</span></span> 
- <span data-ttu-id="55801-1531">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1531">tipo della scheda</span></span> 
- <span data-ttu-id="55801-1532">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="55801-1532">ufficio giapponese della</span></span> 
- <span data-ttu-id="55801-1533">scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1533">scheda</span></span> 
- <span data-ttu-id="55801-1534">v pay
</span><span class="sxs-lookup"><span data-stu-id="55801-1534">v pay</span></span> 
- <span data-ttu-id="55801-1535">v 支払</span><span class="sxs-lookup"><span data-stu-id="55801-1535">v-pay</span></span> 
- <span data-ttu-id="55801-1536">visa
</span><span class="sxs-lookup"><span data-stu-id="55801-1536">visa</span></span> 
- <span data-ttu-id="55801-1537">visa plus
</span><span class="sxs-lookup"><span data-stu-id="55801-1537">visa plus</span></span> 
- <span data-ttu-id="55801-1538">visa electron
</span><span class="sxs-lookup"><span data-stu-id="55801-1538">visa electron</span></span> 
- <span data-ttu-id="55801-1539">visto
</span><span class="sxs-lookup"><span data-stu-id="55801-1539">visto</span></span> 
- <span data-ttu-id="55801-1540">visum
</span><span class="sxs-lookup"><span data-stu-id="55801-1540">visum</span></span> 
- <span data-ttu-id="55801-1541">vpay
</span><span class="sxs-lookup"><span data-stu-id="55801-1541">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="55801-1542">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="55801-1542">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="55801-1543">card identification number</span><span class="sxs-lookup"><span data-stu-id="55801-1543">card identification number</span></span>
- <span data-ttu-id="55801-1544">card verification</span><span class="sxs-lookup"><span data-stu-id="55801-1544">card verification</span></span> 
- <span data-ttu-id="55801-1545">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="55801-1545">cardi la verifica</span></span> 
- <span data-ttu-id="55801-1546">cid
</span><span class="sxs-lookup"><span data-stu-id="55801-1546">cid</span></span> 
- <span data-ttu-id="55801-1547">代金引換払い seg</span><span class="sxs-lookup"><span data-stu-id="55801-1547">cod seg</span></span> 
- <span data-ttu-id="55801-1548">代金引換払い seguranca</span><span class="sxs-lookup"><span data-stu-id="55801-1548">cod seguranca</span></span> 
- <span data-ttu-id="55801-1549">代金引換払い segurança</span><span class="sxs-lookup"><span data-stu-id="55801-1549">cod segurança</span></span> 
- <span data-ttu-id="55801-1550">代金引換払いの sicurezza</span><span class="sxs-lookup"><span data-stu-id="55801-1550">cod sicurezza</span></span> 
- <span data-ttu-id="55801-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="55801-p122">cod. seg</span></span> 
- <span data-ttu-id="55801-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-p123">cod. seguranca</span></span> 
- <span data-ttu-id="55801-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-p124">cod. segurança</span></span> 
- <span data-ttu-id="55801-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="55801-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="55801-1559">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="55801-1559">codice di sicurezza</span></span> 
- <span data-ttu-id="55801-1560">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="55801-1560">codice di verifica</span></span> 
- <span data-ttu-id="55801-1561">codigo
</span><span class="sxs-lookup"><span data-stu-id="55801-1561">codigo</span></span> 
- <span data-ttu-id="55801-1562">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-1562">codigo de seguranca</span></span> 
- <span data-ttu-id="55801-1563">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-1563">codigo de segurança</span></span> 
- <span data-ttu-id="55801-1564">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="55801-1564">crittogramma</span></span> 
- <span data-ttu-id="55801-1565">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="55801-1565">cryptogram</span></span> 
- <span data-ttu-id="55801-1566">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="55801-1566">cryptogramme</span></span> 
- <span data-ttu-id="55801-1567">cv2</span><span class="sxs-lookup"><span data-stu-id="55801-1567">cv2</span></span> 
- <span data-ttu-id="55801-1568">cvc
</span><span class="sxs-lookup"><span data-stu-id="55801-1568">cvc</span></span> 
- <span data-ttu-id="55801-1569">cvc2</span><span class="sxs-lookup"><span data-stu-id="55801-1569">cvc2</span></span> 
- <span data-ttu-id="55801-1570">cvn
</span><span class="sxs-lookup"><span data-stu-id="55801-1570">cvn</span></span> 
- <span data-ttu-id="55801-1571">cvv
</span><span class="sxs-lookup"><span data-stu-id="55801-1571">cvv</span></span> 
- <span data-ttu-id="55801-1572">cvv2</span><span class="sxs-lookup"><span data-stu-id="55801-1572">cvv2</span></span> 
- <span data-ttu-id="55801-1573">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="55801-1573">cód seguranca</span></span> 
- <span data-ttu-id="55801-1574">cód segurança</span><span class="sxs-lookup"><span data-stu-id="55801-1574">cód segurança</span></span> 
- <span data-ttu-id="55801-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-p126">cód. seguranca</span></span> 
- <span data-ttu-id="55801-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-p127">cód. segurança</span></span> 
- <span data-ttu-id="55801-1579">código
</span><span class="sxs-lookup"><span data-stu-id="55801-1579">código</span></span> 
- <span data-ttu-id="55801-1580">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="55801-1580">código de seguranca</span></span> 
- <span data-ttu-id="55801-1581">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="55801-1581">código de segurança</span></span> 
- <span data-ttu-id="55801-1582">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="55801-1582">de kaart controle</span></span> 
- <span data-ttu-id="55801-1583">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="55801-1583">geeft nr uit</span></span> 
- <span data-ttu-id="55801-1584">issue no
</span><span class="sxs-lookup"><span data-stu-id="55801-1584">issue no</span></span> 
- <span data-ttu-id="55801-1585">issue number
</span><span class="sxs-lookup"><span data-stu-id="55801-1585">issue number</span></span> 
- <span data-ttu-id="55801-1586">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1586">kaartidentificatienummer</span></span> 
- <span data-ttu-id="55801-1587">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1587">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="55801-1588">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1588">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="55801-1589">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="55801-1589">kwestieaantal</span></span> 
- <span data-ttu-id="55801-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="55801-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="55801-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="55801-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="55801-1594">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="55801-1594">numero de securite</span></span> 
- <span data-ttu-id="55801-1595">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="55801-1595">numero de verificacao</span></span> 
- <span data-ttu-id="55801-1596">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="55801-1596">numero dell'edizione</span></span> 
- <span data-ttu-id="55801-1597">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="55801-1597">numero di identificazione della</span></span> 
- <span data-ttu-id="55801-1598">scheda
</span><span class="sxs-lookup"><span data-stu-id="55801-1598">scheda</span></span> 
- <span data-ttu-id="55801-1599">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="55801-1599">numero di sicurezza</span></span> 
- <span data-ttu-id="55801-1600">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="55801-1600">numero van veiligheid</span></span> 
- <span data-ttu-id="55801-1601">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="55801-1601">numéro de sécurité</span></span> 
- <span data-ttu-id="55801-1602">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="55801-1602">nº autorizzazione</span></span> 
- <span data-ttu-id="55801-1603">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="55801-1603">número de verificação</span></span> 
- <span data-ttu-id="55801-1604">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="55801-1604">perno il blocco</span></span> 
- <span data-ttu-id="55801-1605">pin block
</span><span class="sxs-lookup"><span data-stu-id="55801-1605">pin block</span></span> 
- <span data-ttu-id="55801-1606">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="55801-1606">prufziffer</span></span> 
- <span data-ttu-id="55801-1607">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="55801-1607">prüfziffer</span></span> 
- <span data-ttu-id="55801-1608">security code
</span><span class="sxs-lookup"><span data-stu-id="55801-1608">security code</span></span> 
- <span data-ttu-id="55801-1609">security no
</span><span class="sxs-lookup"><span data-stu-id="55801-1609">security no</span></span> 
- <span data-ttu-id="55801-1610">security number
</span><span class="sxs-lookup"><span data-stu-id="55801-1610">security number</span></span> 
- <span data-ttu-id="55801-1611">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="55801-1611">sicherheits kode</span></span> 
- <span data-ttu-id="55801-1612">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="55801-1612">sicherheitscode</span></span> 
- <span data-ttu-id="55801-1613">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1613">sicherheitsnummer</span></span> 
- <span data-ttu-id="55801-1614">speldblok
</span><span class="sxs-lookup"><span data-stu-id="55801-1614">speldblok</span></span> 
- <span data-ttu-id="55801-1615">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1615">veiligheid nr</span></span> 
- <span data-ttu-id="55801-1616">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="55801-1616">veiligheidsaantal</span></span> 
- <span data-ttu-id="55801-1617">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="55801-1617">veiligheidscode</span></span> 
- <span data-ttu-id="55801-1618">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-1618">veiligheidsnummer</span></span> 
- <span data-ttu-id="55801-1619">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1619">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="55801-1620">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="55801-1620">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="55801-1621">ablauf
</span><span class="sxs-lookup"><span data-stu-id="55801-1621">ablauf</span></span> 
- <span data-ttu-id="55801-1622">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="55801-1622">data de expiracao</span></span> 
- <span data-ttu-id="55801-1623">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="55801-1623">data de expiração</span></span> 
- <span data-ttu-id="55801-1624">data del exp
</span><span class="sxs-lookup"><span data-stu-id="55801-1624">data del exp</span></span> 
- <span data-ttu-id="55801-1625">data di exp
</span><span class="sxs-lookup"><span data-stu-id="55801-1625">data di exp</span></span> 
- <span data-ttu-id="55801-1626">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="55801-1626">data di scadenza</span></span> 
- <span data-ttu-id="55801-1627">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="55801-1627">data em que expira</span></span> 
- <span data-ttu-id="55801-1628">data scad
</span><span class="sxs-lookup"><span data-stu-id="55801-1628">data scad</span></span> 
- <span data-ttu-id="55801-1629">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="55801-1629">data scadenza</span></span> 
- <span data-ttu-id="55801-1630">date de validité
</span><span class="sxs-lookup"><span data-stu-id="55801-1630">date de validité</span></span> 
- <span data-ttu-id="55801-1631">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="55801-1631">datum afloop</span></span> 
- <span data-ttu-id="55801-1632">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="55801-1632">datum van exp</span></span> 
- <span data-ttu-id="55801-1633">de afloop
</span><span class="sxs-lookup"><span data-stu-id="55801-1633">de afloop</span></span> 
- <span data-ttu-id="55801-1634">espira
</span><span class="sxs-lookup"><span data-stu-id="55801-1634">espira</span></span> 
- <span data-ttu-id="55801-1635">espira
</span><span class="sxs-lookup"><span data-stu-id="55801-1635">espira</span></span> 
- <span data-ttu-id="55801-1636">exp date
</span><span class="sxs-lookup"><span data-stu-id="55801-1636">exp date</span></span> 
- <span data-ttu-id="55801-1637">exp datum
</span><span class="sxs-lookup"><span data-stu-id="55801-1637">exp datum</span></span> 
- <span data-ttu-id="55801-1638">有効期限</span><span class="sxs-lookup"><span data-stu-id="55801-1638">expiration</span></span> 
- <span data-ttu-id="55801-1639">expire
</span><span class="sxs-lookup"><span data-stu-id="55801-1639">expire</span></span> 
- <span data-ttu-id="55801-1640">expires
</span><span class="sxs-lookup"><span data-stu-id="55801-1640">expires</span></span> 
- <span data-ttu-id="55801-1641">expiry
</span><span class="sxs-lookup"><span data-stu-id="55801-1641">expiry</span></span> 
- <span data-ttu-id="55801-1642">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="55801-1642">fecha de expiracion</span></span> 
- <span data-ttu-id="55801-1643">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="55801-1643">fecha de venc</span></span> 
- <span data-ttu-id="55801-1644">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="55801-1644">gultig bis</span></span> 
- <span data-ttu-id="55801-1645">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1645">gultigkeitsdatum</span></span> 
- <span data-ttu-id="55801-1646">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="55801-1646">gültig bis</span></span> 
- <span data-ttu-id="55801-1647">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1647">gültigkeitsdatum</span></span> 
- <span data-ttu-id="55801-1648">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="55801-1648">la scadenza</span></span> 
- <span data-ttu-id="55801-1649">scadenza
</span><span class="sxs-lookup"><span data-stu-id="55801-1649">scadenza</span></span> 
- <span data-ttu-id="55801-1650">valable
</span><span class="sxs-lookup"><span data-stu-id="55801-1650">valable</span></span> 
- <span data-ttu-id="55801-1651">validade
</span><span class="sxs-lookup"><span data-stu-id="55801-1651">validade</span></span> 
- <span data-ttu-id="55801-1652">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="55801-1652">valido hasta</span></span> 
- <span data-ttu-id="55801-1653">valor
</span><span class="sxs-lookup"><span data-stu-id="55801-1653">valor</span></span> 
- <span data-ttu-id="55801-1654">venc
</span><span class="sxs-lookup"><span data-stu-id="55801-1654">venc</span></span> 
- <span data-ttu-id="55801-1655">vencimento
</span><span class="sxs-lookup"><span data-stu-id="55801-1655">vencimento</span></span> 
- <span data-ttu-id="55801-1656">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="55801-1656">vencimiento</span></span> 
- <span data-ttu-id="55801-1657">verloopt
</span><span class="sxs-lookup"><span data-stu-id="55801-1657">verloopt</span></span> 
- <span data-ttu-id="55801-1658">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="55801-1658">vervaldag</span></span> 
- <span data-ttu-id="55801-1659">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="55801-1659">vervaldatum</span></span> 
- <span data-ttu-id="55801-1660">vto
</span><span class="sxs-lookup"><span data-stu-id="55801-1660">vto</span></span> 
- <span data-ttu-id="55801-1661">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="55801-1661">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="55801-1662">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-1662">EU Driver's License Number</span></span>

<span data-ttu-id="55801-1663">詳細については、 [EU ドライバーのライセンス番号の機密性の高い情報の種類](eu-driver-s-license-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55801-1663">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="55801-1664">EU 国民 Id 番号</span><span class="sxs-lookup"><span data-stu-id="55801-1664">EU National Identification Number</span></span>

<span data-ttu-id="55801-1665">詳細については、 [EU 各国の識別番号の機密性の高い情報の種類](eu-national-identification-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55801-1665">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="55801-1666">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-1666">EU Passport Number</span></span>

<span data-ttu-id="55801-1667">詳細については、 [EU のパスポート番号の機密性の高い情報の種類](eu-passport-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55801-1667">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="55801-1668">EU の社会保障番号またはそれと同等の ID</span><span class="sxs-lookup"><span data-stu-id="55801-1668">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="55801-1669">詳細については、 [EU の社会保障番号、または機密性の高い情報の種類のと同じ ID](eu-social-security-number-or-equivalent-id.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55801-1669">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="55801-1670">EU 税 Id 番号</span><span class="sxs-lookup"><span data-stu-id="55801-1670">EU Tax Identification Number</span></span>

<span data-ttu-id="55801-1671">詳細については、 [EU の税 Id 番号の機密性の高い情報の種類](eu-tax-identification-number.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55801-1671">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="55801-1672">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="55801-1672">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="55801-1673">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1673">Format</span></span>

<span data-ttu-id="55801-1674">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="55801-1674">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1675">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1675">Pattern</span></span>

<span data-ttu-id="55801-1676">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="55801-1676">Pattern must include all of the following:</span></span>
- <span data-ttu-id="55801-1677">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1677">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="55801-1678">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="55801-1678">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="55801-1679">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="55801-1679">Three-digit personal identification number</span></span> 
- <span data-ttu-id="55801-1680">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="55801-1680">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1681">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1681">Checksum</span></span>

<span data-ttu-id="55801-1682">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1682">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1683">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1683">Definition</span></span>

<span data-ttu-id="55801-1684">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1684">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1685">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1685">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1686">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1686">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="55801-1687">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1687">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1688">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1688">Keywords</span></span>

- <span data-ttu-id="55801-1689">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="55801-1689">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="55801-1690">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="55801-1690">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="55801-1691">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="55801-1691">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="55801-1692">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="55801-1692">Personbeteckning</span></span>
- <span data-ttu-id="55801-1693">Personnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1693">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="55801-1694">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-1694">Finland Passport Number</span></span>

<span data-ttu-id="55801-p130">9 つの文字と数字の 9 つの文字と数字の組み合わせのパターンの組み合わせを書式設定: 2 つの文字 (いない大文字小文字を区別) の 7 桁のチェックサムなしの定義 A DLP ポリシーは、75% の場合はこの種の機密情報を検出したことを確信で、300 文字の長さ: Regex_finland_passport_number の正規表現パターンに一致するコンテンツを検索します。Keyword_finland_passport_number からキーワードを検出するとします。<!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity> Keyword_finland_passport_number Passport Passi のキーワード</span><span class="sxs-lookup"><span data-stu-id="55801-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="55801-1699">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-1699">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1700">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1700">Format</span></span>

<span data-ttu-id="55801-1701">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1701">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1702">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1702">Pattern</span></span>

<span data-ttu-id="55801-1703">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1703">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1704">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1704">Checksum</span></span>

<span data-ttu-id="55801-1705">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1705">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1706">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1706">Definition</span></span>

<span data-ttu-id="55801-1707">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1707">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1708">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1708">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1709">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-1709">At least one of the following is true:</span></span>
- <span data-ttu-id="55801-1710">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1710">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="55801-1711">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1711">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1712">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1712">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="55801-1713">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="55801-1713">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="55801-1714">drivers licence</span><span class="sxs-lookup"><span data-stu-id="55801-1714">drivers licence</span></span>
- <span data-ttu-id="55801-1715">drivers license</span><span class="sxs-lookup"><span data-stu-id="55801-1715">drivers license</span></span>
- <span data-ttu-id="55801-1716">driving licence
</span><span class="sxs-lookup"><span data-stu-id="55801-1716">driving licence</span></span>
- <span data-ttu-id="55801-1717">ライセンスを推進</span><span class="sxs-lookup"><span data-stu-id="55801-1717">driving license</span></span>
- <span data-ttu-id="55801-1718">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="55801-1718">permis de conduire</span></span>
- <span data-ttu-id="55801-1719">
licence number</span><span class="sxs-lookup"><span data-stu-id="55801-1719">licence number</span></span>
- <span data-ttu-id="55801-1720">
license number</span><span class="sxs-lookup"><span data-stu-id="55801-1720">license number</span></span>
- <span data-ttu-id="55801-1721">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="55801-1721">licence numbers</span></span>
- <span data-ttu-id="55801-1722">

license numbers</span><span class="sxs-lookup"><span data-stu-id="55801-1722">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="55801-1723">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="55801-1723">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="55801-1724">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1724">Format</span></span>

<span data-ttu-id="55801-1725">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1725">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1726">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1726">Pattern</span></span>

<span data-ttu-id="55801-1727">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1727">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1728">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1728">Checksum</span></span>

<span data-ttu-id="55801-1729">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1729">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1730">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1730">Definition</span></span>

<span data-ttu-id="55801-1731">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1731">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1732">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1732">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1733">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1733">Keywords</span></span>

<span data-ttu-id="55801-1734">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1734">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="55801-1735">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-1735">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1736">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1736">Format</span></span>

<span data-ttu-id="55801-1737">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="55801-1737">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1738">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1738">Pattern</span></span>

<span data-ttu-id="55801-1739">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="55801-1739">Nine digits and letters:</span></span>
- <span data-ttu-id="55801-1740">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1740">Two digits</span></span> 
- <span data-ttu-id="55801-1741">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-1741">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="55801-1742">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1742">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1743">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1743">Checksum</span></span>

<span data-ttu-id="55801-1744">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1744">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1745">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1745">Definition</span></span>

<span data-ttu-id="55801-1746">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1746">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1747">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1747">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1748">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1748">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1749">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1749">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="55801-1750">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="55801-1750">Keyword_passport</span></span>

- <span data-ttu-id="55801-1751">Passport Number</span><span class="sxs-lookup"><span data-stu-id="55801-1751">Passport Number</span></span>
- <span data-ttu-id="55801-1752">
Passport No</span><span class="sxs-lookup"><span data-stu-id="55801-1752">Passport No</span></span>
- <span data-ttu-id="55801-1753">Passport #
</span><span class="sxs-lookup"><span data-stu-id="55801-1753">Passport #</span></span>
- <span data-ttu-id="55801-1754">Passport#
</span><span class="sxs-lookup"><span data-stu-id="55801-1754">Passport#</span></span>
- <span data-ttu-id="55801-1755">PassportID</span><span class="sxs-lookup"><span data-stu-id="55801-1755">PassportID</span></span>
- <span data-ttu-id="55801-1756">Passportno
</span><span class="sxs-lookup"><span data-stu-id="55801-1756">Passportno</span></span>
- <span data-ttu-id="55801-1757">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-1757">passportnumber</span></span>
- <span data-ttu-id="55801-1758">パスポート</span><span class="sxs-lookup"><span data-stu-id="55801-1758">パスポート</span></span>
- <span data-ttu-id="55801-1759">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="55801-1759">パスポート番号</span></span>
- <span data-ttu-id="55801-1760">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="55801-1760">パスポートのNum</span></span>
- <span data-ttu-id="55801-1761">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="55801-1761">パスポート ＃</span></span> 
- <span data-ttu-id="55801-1762">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="55801-1762">Numéro de passeport</span></span>
- <span data-ttu-id="55801-1763">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="55801-1763">Passeport n °</span></span>
- <span data-ttu-id="55801-1764">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="55801-1764">Passeport Non</span></span>
- <span data-ttu-id="55801-1765">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="55801-1765">Passeport #</span></span>
- <span data-ttu-id="55801-1766">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="55801-1766">Passeport#</span></span>
- <span data-ttu-id="55801-1767">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="55801-1767">PasseportNon</span></span>
- <span data-ttu-id="55801-1768">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="55801-1768">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="55801-1769">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="55801-1769">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="55801-1770">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1770">Format</span></span>

<span data-ttu-id="55801-1771">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1771">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1772">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1772">Pattern</span></span>

<span data-ttu-id="55801-1773">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="55801-1773">Must match one of two patterns:</span></span>
- <span data-ttu-id="55801-1774">13 桁の数字が 2 桁の後にスペースの後に</span><span class="sxs-lookup"><span data-stu-id="55801-1774">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="55801-1775">または</span><span class="sxs-lookup"><span data-stu-id="55801-1775">or</span></span>
- <span data-ttu-id="55801-1776">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-1776">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1777">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1777">Checksum</span></span>

<span data-ttu-id="55801-1778">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1778">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1779">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1779">Definition</span></span>

<span data-ttu-id="55801-1780">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1780">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1781">Func_french_insee または Func_fr_insee 関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="55801-1781">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1782">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1782">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="55801-1783">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1783">The checksum passes.</span></span>

<span data-ttu-id="55801-1784">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1785">Func_french_insee または Func_fr_insee 関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="55801-1785">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1786">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-1786">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="55801-1787">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1787">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1788">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1788">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="55801-1789">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="55801-1789">Keyword_fr_insee</span></span>

- <span data-ttu-id="55801-1790">insee</span><span class="sxs-lookup"><span data-stu-id="55801-1790">insee</span></span>
- <span data-ttu-id="55801-1791">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="55801-1791">securité sociale</span></span>
- <span data-ttu-id="55801-1792">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="55801-1792">securite sociale</span></span>
- <span data-ttu-id="55801-1793">
national id</span><span class="sxs-lookup"><span data-stu-id="55801-1793">national id</span></span>
- <span data-ttu-id="55801-1794">
national identification</span><span class="sxs-lookup"><span data-stu-id="55801-1794">national identification</span></span>
- <span data-ttu-id="55801-1795">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="55801-1795">numéro d'identité</span></span>
- <span data-ttu-id="55801-1796">なし d'identité</span><span class="sxs-lookup"><span data-stu-id="55801-1796">no d'identité</span></span>
- <span data-ttu-id="55801-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="55801-p131">no. d'identité</span></span>
- <span data-ttu-id="55801-1799">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="55801-1799">numero d'identite</span></span>
- <span data-ttu-id="55801-1800">なし d'identite</span><span class="sxs-lookup"><span data-stu-id="55801-1800">no d'identite</span></span>
- <span data-ttu-id="55801-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="55801-p132">no. d'identite</span></span>
- <span data-ttu-id="55801-1803">social security number
</span><span class="sxs-lookup"><span data-stu-id="55801-1803">social security number</span></span>
- <span data-ttu-id="55801-1804">
social security code</span><span class="sxs-lookup"><span data-stu-id="55801-1804">social security code</span></span>
- <span data-ttu-id="55801-1805">social insurance number</span><span class="sxs-lookup"><span data-stu-id="55801-1805">social insurance number</span></span>
- <span data-ttu-id="55801-1806">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="55801-1806">le numéro d'identification nationale</span></span>
- <span data-ttu-id="55801-1807">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="55801-1807">d'identité nationale</span></span>
- <span data-ttu-id="55801-1808">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="55801-1808">numéro de sécurité sociale</span></span>
- <span data-ttu-id="55801-1809">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="55801-1809">le code de la sécurité sociale</span></span>
- <span data-ttu-id="55801-1810">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="55801-1810">numéro d'assurance sociale</span></span>
- <span data-ttu-id="55801-1811">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="55801-1811">numéro de sécu</span></span>
- <span data-ttu-id="55801-1812">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="55801-1812">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="55801-1813">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-1813">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1814">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1814">Format</span></span>

<span data-ttu-id="55801-1815">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="55801-1815">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1816">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1816">Pattern</span></span>

<span data-ttu-id="55801-1817">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="55801-1817">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="55801-1818">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="55801-1818">A digit or letter</span></span> 
- <span data-ttu-id="55801-1819">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1819">Two digits</span></span> 
- <span data-ttu-id="55801-1820">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="55801-1820">Six digits or letters</span></span> 
- <span data-ttu-id="55801-1821">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1821">A digit</span></span> 
- <span data-ttu-id="55801-1822">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="55801-1822">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1823">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1823">Checksum</span></span>

<span data-ttu-id="55801-1824">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1824">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1825">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1825">Definition</span></span>

<span data-ttu-id="55801-1826">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1826">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1827">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1827">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1828">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-1828">At least one of the following is true:</span></span>
    - <span data-ttu-id="55801-1829">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1829">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="55801-1830">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1830">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="55801-1831">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1831">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="55801-1832">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1832">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1833">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1833">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="55801-1834">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="55801-1834">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="55801-1835">Führerschein</span><span class="sxs-lookup"><span data-stu-id="55801-1835">Führerschein</span></span>
- <span data-ttu-id="55801-1836">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="55801-1836">Fuhrerschein</span></span>
- <span data-ttu-id="55801-1837">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="55801-1837">Fuehrerschein</span></span>
- <span data-ttu-id="55801-1838">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1838">Führerscheinnummer</span></span>
- <span data-ttu-id="55801-1839">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1839">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="55801-1840">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1840">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="55801-1841">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="55801-1841">Führerschein-</span></span> 
- <span data-ttu-id="55801-1842">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="55801-1842">Fuhrerschein-</span></span> 
- <span data-ttu-id="55801-1843">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="55801-1843">Fuehrerschein-</span></span> 
- <span data-ttu-id="55801-1844">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="55801-1844">FührerscheinnummerNr</span></span>
- <span data-ttu-id="55801-1845">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="55801-1845">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="55801-1846">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="55801-1846">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="55801-1847">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="55801-1847">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="55801-1848">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="55801-1848">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="55801-1849">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="55801-1849">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="55801-1850">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1850">Führerschein- Nr</span></span>
- <span data-ttu-id="55801-1851">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1851">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="55801-1852">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1852">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="55801-1853">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="55801-1853">Führerschein- Klasse</span></span> 
- <span data-ttu-id="55801-1854">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="55801-1854">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="55801-1855">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="55801-1855">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="55801-1856">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="55801-1856">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="55801-1857">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="55801-1857">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="55801-1858">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="55801-1858">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="55801-1859">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="55801-1859">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="55801-1860">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="55801-1860">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="55801-1861">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="55801-1861">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="55801-1862">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1862">Führerschein- Nr</span></span> 
- <span data-ttu-id="55801-1863">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1863">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="55801-1864">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1864">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="55801-1865">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="55801-1865">Führerschein- Klasse</span></span> 
- <span data-ttu-id="55801-1866">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="55801-1866">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="55801-1867">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="55801-1867">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="55801-1868">DL</span><span class="sxs-lookup"><span data-stu-id="55801-1868">DL</span></span> 
- <span data-ttu-id="55801-1869">DLS</span><span class="sxs-lookup"><span data-stu-id="55801-1869">DLS</span></span>
- <span data-ttu-id="55801-1870">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="55801-1870">Driv Lic</span></span> 
- <span data-ttu-id="55801-1871">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="55801-1871">Driv Licen</span></span> 
- <span data-ttu-id="55801-1872">Driv License</span><span class="sxs-lookup"><span data-stu-id="55801-1872">Driv License</span></span>
- <span data-ttu-id="55801-1873">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="55801-1873">Driv Licenses</span></span> 
- <span data-ttu-id="55801-1874">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-1874">Driv Licence</span></span> 
- <span data-ttu-id="55801-1875">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-1875">Driv Licences</span></span> 
- <span data-ttu-id="55801-1876">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="55801-1876">Driv Lic</span></span> 
- <span data-ttu-id="55801-1877">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="55801-1877">Driver Licen</span></span> 
- <span data-ttu-id="55801-1878">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-1878">Driver License</span></span> 
- <span data-ttu-id="55801-1879">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-1879">Driver Licenses</span></span> 
- <span data-ttu-id="55801-1880">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-1880">Driver Licence</span></span> 
- <span data-ttu-id="55801-1881">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-1881">Driver Licences</span></span> 
- <span data-ttu-id="55801-1882">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-1882">Drivers Lic</span></span> 
- <span data-ttu-id="55801-1883">ドライバー Licen</span><span class="sxs-lookup"><span data-stu-id="55801-1883">Drivers Licen</span></span> 
- <span data-ttu-id="55801-1884">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-1884">Drivers License</span></span> 
- <span data-ttu-id="55801-1885">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-1885">Drivers Licenses</span></span> 
- <span data-ttu-id="55801-1886">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-1886">Drivers Licence</span></span> 
- <span data-ttu-id="55801-1887">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-1887">Drivers Licences</span></span> 
- <span data-ttu-id="55801-1888">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="55801-1888">Driver's Lic</span></span> 
- <span data-ttu-id="55801-1889">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="55801-1889">Driver's Licen</span></span> 
- <span data-ttu-id="55801-1890">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-1890">Driver's License</span></span> 
- <span data-ttu-id="55801-1891">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-1891">Driver's Licenses</span></span> 
- <span data-ttu-id="55801-1892">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="55801-1892">Driver's Licence</span></span> 
- <span data-ttu-id="55801-1893">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="55801-1893">Driver's Licences</span></span> 
- <span data-ttu-id="55801-1894">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="55801-1894">Driving Lic</span></span> 
- <span data-ttu-id="55801-1895">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="55801-1895">Driving Licen</span></span> 
- <span data-ttu-id="55801-1896">Driving License
</span><span class="sxs-lookup"><span data-stu-id="55801-1896">Driving License</span></span> 
- <span data-ttu-id="55801-1897">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="55801-1897">Driving Licenses</span></span> 
- <span data-ttu-id="55801-1898">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="55801-1898">Driving Licence</span></span> 
- <span data-ttu-id="55801-1899">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="55801-1899">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="55801-1900">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="55801-1900">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="55801-1901">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1901">Nr-Führerschein</span></span> 
- <span data-ttu-id="55801-1902">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1902">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="55801-1903">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1903">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="55801-1904">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1904">No-Führerschein</span></span> 
- <span data-ttu-id="55801-1905">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1905">No-Fuhrerschein</span></span> 
- <span data-ttu-id="55801-1906">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1906">No-Fuehrerschein</span></span> 
- <span data-ttu-id="55801-1907">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1907">N-Führerschein</span></span> 
- <span data-ttu-id="55801-1908">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1908">N-Fuhrerschein</span></span> 
- <span data-ttu-id="55801-1909">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="55801-1909">N-Fuehrerschein</span></span>
- <span data-ttu-id="55801-1910">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1910">Nr-Führerschein</span></span> 
- <span data-ttu-id="55801-1911">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1911">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="55801-1912">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1912">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="55801-1913">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1913">No-Führerschein</span></span> 
- <span data-ttu-id="55801-1914">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1914">No-Fuhrerschein</span></span> 
- <span data-ttu-id="55801-1915">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1915">No-Fuehrerschein</span></span> 
- <span data-ttu-id="55801-1916">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1916">N-Führerschein</span></span> 
- <span data-ttu-id="55801-1917">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="55801-1917">N-Fuhrerschein</span></span> 
- <span data-ttu-id="55801-1918">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="55801-1918">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="55801-1919">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="55801-1919">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="55801-1920">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="55801-1920">ausstellungsdatum</span></span>
- <span data-ttu-id="55801-1921">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="55801-1921">ausstellungsort</span></span>
- <span data-ttu-id="55801-1922">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="55801-1922">ausstellende behöde</span></span>
- <span data-ttu-id="55801-1923">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="55801-1923">ausstellende behorde</span></span>
- <span data-ttu-id="55801-1924">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="55801-1924">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="55801-1925">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-1925">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1926">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1926">Format</span></span>

<span data-ttu-id="55801-1927">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="55801-1927">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1928">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1928">Pattern</span></span>

<span data-ttu-id="55801-1929">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="55801-1929">Pattern must include all of the following:</span></span>
- <span data-ttu-id="55801-1930">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="55801-1930">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="55801-1931">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1931">Three digits</span></span> 
- <span data-ttu-id="55801-1932">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="55801-1932">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="55801-1933">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1933">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1934">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1934">Checksum</span></span>

<span data-ttu-id="55801-1935">はい</span><span class="sxs-lookup"><span data-stu-id="55801-1935">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1936">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1936">Definition</span></span>

<span data-ttu-id="55801-1937">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1937">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1938">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1938">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1939">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="55801-1939">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="55801-1940">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1940">The checksum passes.</span></span>

<span data-ttu-id="55801-1941">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1941">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1942">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1942">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1943">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="55801-1943">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="55801-1944">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-1944">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-1945">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1945">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="55801-1946">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="55801-1946">Keyword_german_passport</span></span>

- <span data-ttu-id="55801-1947">reisepass</span><span class="sxs-lookup"><span data-stu-id="55801-1947">reisepass</span></span>
- <span data-ttu-id="55801-1948">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="55801-1948">reisepasse</span></span>
- <span data-ttu-id="55801-1949">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1949">reisepassnummer</span></span>
- <span data-ttu-id="55801-1950">passport</span><span class="sxs-lookup"><span data-stu-id="55801-1950">passport</span></span>
- <span data-ttu-id="55801-1951">

passports</span><span class="sxs-lookup"><span data-stu-id="55801-1951">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="55801-1952">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="55801-1952">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="55801-1953">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="55801-1953">geburtsdatum</span></span>
- <span data-ttu-id="55801-1954">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="55801-1954">ausstellungsdatum</span></span>
- <span data-ttu-id="55801-1955">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="55801-1955">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="55801-1956">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="55801-1956">Keyword_german_passport_number</span></span>

<span data-ttu-id="55801-1957">いいえ-Reisepass-Reisepass Nr</span><span class="sxs-lookup"><span data-stu-id="55801-1957">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="55801-1958">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="55801-1958">Keyword_german_passport1</span></span>

<span data-ttu-id="55801-1959">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="55801-1959">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="55801-1960">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="55801-1960">Keyword_german_passport2</span></span>

<span data-ttu-id="55801-1961">bnationalit.t</span><span class="sxs-lookup"><span data-stu-id="55801-1961">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="55801-1962">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="55801-1962">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-1963">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1963">Format</span></span>

<span data-ttu-id="55801-1964">1 2010 年 11 月以降: 9 つの文字と数字</span><span class="sxs-lookup"><span data-stu-id="55801-1964">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="55801-1965">31 10 月 2010: 10 桁までの 1 年 1987年 4 月から</span><span class="sxs-lookup"><span data-stu-id="55801-1965">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1966">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1966">Pattern</span></span>

<span data-ttu-id="55801-1967">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="55801-1967">Since 1 November 2010:</span></span>
- <span data-ttu-id="55801-1968">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-1968">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="55801-1969">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1969">Eight digits</span></span>

<span data-ttu-id="55801-1970">31 2010 年 10 月までの 1 年 1987年 4 月: から</span><span class="sxs-lookup"><span data-stu-id="55801-1970">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="55801-1971">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1971">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1972">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1972">Checksum</span></span>

<span data-ttu-id="55801-1973">なし</span><span class="sxs-lookup"><span data-stu-id="55801-1973">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-1974">定義</span><span class="sxs-lookup"><span data-stu-id="55801-1974">Definition</span></span>

<span data-ttu-id="55801-1975">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-1975">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-1976">正規表現 Regex_germany_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1976">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-1977">Keyword_germany_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-1977">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-1978">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-1978">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="55801-1979">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-1979">Keyword_germany_id_card</span></span>

- <span data-ttu-id="55801-1980">Identity Card</span><span class="sxs-lookup"><span data-stu-id="55801-1980">Identity Card</span></span>
- <span data-ttu-id="55801-1981">ID</span><span class="sxs-lookup"><span data-stu-id="55801-1981">ID</span></span>
- <span data-ttu-id="55801-1982">Identification</span><span class="sxs-lookup"><span data-stu-id="55801-1982">Identification</span></span>
- <span data-ttu-id="55801-1983">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="55801-1983">Personalausweis</span></span>
- <span data-ttu-id="55801-1984">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="55801-1984">Identifizierungsnummer</span></span>
- <span data-ttu-id="55801-1985">Ausweis</span><span class="sxs-lookup"><span data-stu-id="55801-1985">Ausweis</span></span>
- <span data-ttu-id="55801-1986">Identifikation</span><span class="sxs-lookup"><span data-stu-id="55801-1986">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="55801-1987">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="55801-1987">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="55801-1988">形式</span><span class="sxs-lookup"><span data-stu-id="55801-1988">Format</span></span>

<span data-ttu-id="55801-1989">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="55801-1989">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-1990">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-1990">Pattern</span></span>

<span data-ttu-id="55801-1991">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="55801-1991">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="55801-1992">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="55801-1992">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="55801-1993">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-1993">A dash</span></span> 
- <span data-ttu-id="55801-1994">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1994">Six digits</span></span>

<span data-ttu-id="55801-1995">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="55801-1995">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="55801-1996">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="55801-1996">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="55801-1997">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-1997">A dash</span></span> 
- <span data-ttu-id="55801-1998">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-1998">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-1999">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-1999">Checksum</span></span>

<span data-ttu-id="55801-2000">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2000">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2001">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2001">Definition</span></span>

<span data-ttu-id="55801-2002">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2002">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2003">正規表現 Regex_greece_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2003">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2004">Keyword_greece_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2004">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2005">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2005">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="55801-2006">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-2006">Keyword_greece_id_card</span></span>

- <span data-ttu-id="55801-2007">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="55801-2007">Greek identity Card</span></span>
- <span data-ttu-id="55801-2008">Tautotita</span><span class="sxs-lookup"><span data-stu-id="55801-2008">Tautotita</span></span>
- <span data-ttu-id="55801-2009">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="55801-2009">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="55801-2010">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="55801-2010">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="55801-2011">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2011">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2012">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2012">Format</span></span>

<span data-ttu-id="55801-2013">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="55801-2013">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2014">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2014">Pattern</span></span>

<span data-ttu-id="55801-2015">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="55801-2015">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="55801-2016">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-2016">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2017">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2017">Six digits</span></span> 
- <span data-ttu-id="55801-2018">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="55801-2018">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2019">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2019">Checksum</span></span>

<span data-ttu-id="55801-2020">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2020">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2021">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2021">Definition</span></span>

<span data-ttu-id="55801-2022">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2022">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2023">関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2023">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2024">Keyword_hong_kong_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2024">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="55801-2025">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2025">The checksum passes.</span></span>

<span data-ttu-id="55801-2026">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2026">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2027">関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2027">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2028">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2028">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2029">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2029">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="55801-2030">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-2030">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="55801-2031">Hong Kong Identity Card</span><span class="sxs-lookup"><span data-stu-id="55801-2031">Hong Kong Identity Card</span></span>
- <span data-ttu-id="55801-2032">HKID</span><span class="sxs-lookup"><span data-stu-id="55801-2032">HKID</span></span>
- <span data-ttu-id="55801-2033">ID card</span><span class="sxs-lookup"><span data-stu-id="55801-2033">ID card</span></span>
- <span data-ttu-id="55801-2034">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="55801-2034">香港身份證</span></span> 
- <span data-ttu-id="55801-2035">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="55801-2035">香港永久性居民身份證</span></span> 
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="55801-2036">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="55801-2036">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2037">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2037">Format</span></span>

<span data-ttu-id="55801-2038">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="55801-2038">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2039">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2039">Pattern</span></span>

<span data-ttu-id="55801-2040">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2040">10 letters or digits:</span></span>
- <span data-ttu-id="55801-2041">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-2041">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2042">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2042">Four digits</span></span> 
- <span data-ttu-id="55801-2043">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="55801-2043">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2044">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2044">Checksum</span></span>

<span data-ttu-id="55801-2045">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2045">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2046">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2046">Definition</span></span>

<span data-ttu-id="55801-2047">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2047">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2048">正規表現 Regex_india_permanent_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2048">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2049">Keyword_india_permanent_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2049">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="55801-2050">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2050">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2051">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2051">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="55801-2052">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="55801-2052">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="55801-2053">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2053">Permanent Account Number</span></span> 
- <span data-ttu-id="55801-2054">PAN
</span><span class="sxs-lookup"><span data-stu-id="55801-2054">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="55801-2055">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2055">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2056">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2056">Format</span></span>

<span data-ttu-id="55801-2057">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2057">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2058">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2058">Pattern</span></span>

<span data-ttu-id="55801-2059">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2059">12 digits:</span></span>
- <span data-ttu-id="55801-2060">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2060">Four digits</span></span> 
- <span data-ttu-id="55801-2061">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2061">An optional space or dash</span></span> 
- <span data-ttu-id="55801-2062">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2062">Four digits</span></span> 
- <span data-ttu-id="55801-2063">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2063">An optional space or dash</span></span> 
- <span data-ttu-id="55801-2064">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="55801-2064">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2065">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2065">Checksum</span></span>

<span data-ttu-id="55801-2066">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2066">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2067">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2067">Definition</span></span>

<span data-ttu-id="55801-p133">DLP ポリシーとは、85% をこの種類の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_india_aadhaar 関数は、パターンに一致するコンテンツを検索します。。Keyword_india_aadhar からキーワードを検出するとします。チェックサムが渡されます。DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_india_aadhaar 関数は、パターンに一致するコンテンツを検索します。。チェックサムが渡されます。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="55801-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="55801-2074">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2074">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="55801-2075">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="55801-2075">Keyword_india_aadhar</span></span>
- <span data-ttu-id="55801-2076">Aadhar</span><span class="sxs-lookup"><span data-stu-id="55801-2076">Aadhar</span></span>
- <span data-ttu-id="55801-2077">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="55801-2077">Aadhaar</span></span>
- <span data-ttu-id="55801-2078">UID</span><span class="sxs-lookup"><span data-stu-id="55801-2078">UID</span></span>
- <span data-ttu-id="55801-2079">आधार</span><span class="sxs-lookup"><span data-stu-id="55801-2079">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="55801-2080">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2080">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2081">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2081">Format</span></span>

<span data-ttu-id="55801-2082">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2082">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2083">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2083">Pattern</span></span>

<span data-ttu-id="55801-2084">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2084">16 digits:</span></span>
- <span data-ttu-id="55801-2085">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="55801-2085">Two-digit province code</span></span> 
- <span data-ttu-id="55801-2086">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2086">A period (optional)</span></span> 
- <span data-ttu-id="55801-2087">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="55801-2087">Two-digit regency or city code</span></span> 
- <span data-ttu-id="55801-2088">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="55801-2088">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="55801-2089">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2089">A period (optional)</span></span> 
- <span data-ttu-id="55801-2090">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2090">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="55801-2091">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2091">A period (optional)</span></span> 
- <span data-ttu-id="55801-2092">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2092">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2093">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2093">Checksum</span></span>

<span data-ttu-id="55801-2094">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2094">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2095">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2095">Definition</span></span>

<span data-ttu-id="55801-2096">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2096">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2097">正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2097">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2098">Keyword_indonesia_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2098">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="55801-2099">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2099">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2100">正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2100">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2101">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2101">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="55801-2102">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="55801-2102">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="55801-2103">KTP</span><span class="sxs-lookup"><span data-stu-id="55801-2103">KTP</span></span>
- <span data-ttu-id="55801-2104">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="55801-2104">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="55801-2105">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="55801-2105">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="55801-2106">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="55801-2106">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2107">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2107">Format</span></span>

<span data-ttu-id="55801-2108">国コード (2 文字)、チェック ディジット (2 桁)、bban 番号 (最大 30 文字)</span><span class="sxs-lookup"><span data-stu-id="55801-2108">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2109">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2109">Pattern</span></span>

<span data-ttu-id="55801-2110">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="55801-2110">Pattern must include all of the following:</span></span>

- <span data-ttu-id="55801-2111">2 文字の国コード</span><span class="sxs-lookup"><span data-stu-id="55801-2111">Two-letter country code</span></span>
- <span data-ttu-id="55801-2112">2 桁のチェック ディジット (省略可能なスペースが続く) </span><span class="sxs-lookup"><span data-stu-id="55801-2112">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="55801-2113">4 個の文字または数字で構成される 1 から 7 個のグループ (スペースで区切ることができる)</span><span class="sxs-lookup"><span data-stu-id="55801-2113">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="55801-2114">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="55801-2114">1-3 letters or digits</span></span>

<span data-ttu-id="55801-p134">各国の形式は多少異なります。IBAN 機密情報の型は、次の 60 か国をカバーしています。</span><span class="sxs-lookup"><span data-stu-id="55801-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="55801-2117">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、gi、gl、gr、hr、hu、ie、il、is、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="55801-2117">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2118">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2118">Checksum</span></span>

<span data-ttu-id="55801-2119">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2120">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2120">Definition</span></span>

<span data-ttu-id="55801-2121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2122">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2122">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2123">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2123">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2124">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2124">Keywords</span></span>

<span data-ttu-id="55801-2125">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2125">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="55801-2126">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="55801-2126">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="55801-2127">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2127">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="55801-2128">IPv4:</span><span class="sxs-lookup"><span data-stu-id="55801-2128">IPv4:</span></span>
<span data-ttu-id="55801-2129">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="55801-2129">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="55801-2130">IPv6:</span><span class="sxs-lookup"><span data-stu-id="55801-2130">IPv6:</span></span>
<span data-ttu-id="55801-2131"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="55801-2131">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2132">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2132">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2133">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2133">Checksum</span></span>

<span data-ttu-id="55801-2134">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2134">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2135">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2135">Definition</span></span>

<span data-ttu-id="55801-2136">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2136">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2137">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2137">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2138">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-2138">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="55801-2139">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2139">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2140">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2140">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2141">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2141">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="55801-2142">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2142">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2143">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2143">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2144">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-2144">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2145">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2145">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="55801-2146">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="55801-2146">Keyword_ipaddress</span></span>

- <span data-ttu-id="55801-2147">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="55801-2147">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="55801-2148">ip address
</span><span class="sxs-lookup"><span data-stu-id="55801-2148">ip address</span></span> 
- <span data-ttu-id="55801-2149">ip addresses</span><span class="sxs-lookup"><span data-stu-id="55801-2149">ip addresses</span></span>
- <span data-ttu-id="55801-2150">internet protocol</span><span class="sxs-lookup"><span data-stu-id="55801-2150">internet protocol</span></span>
- <span data-ttu-id="55801-2151">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="55801-2151">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="55801-2152">病気 (ICD 10 CM) の国際的な分類</span><span class="sxs-lookup"><span data-stu-id="55801-2152">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2153">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2153">Format</span></span>

<span data-ttu-id="55801-2154">辞書</span><span class="sxs-lookup"><span data-stu-id="55801-2154">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2155">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2155">Pattern</span></span>

<span data-ttu-id="55801-2156">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2156">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2157">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2157">Checksum</span></span>

<span data-ttu-id="55801-2158">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2158">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2159">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2159">Definition</span></span>

<span data-ttu-id="55801-2160">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2160">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2161">Dictionary_icd_10_cm からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="55801-2161">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="55801-2162">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2162">Keywords</span></span>

<span data-ttu-id="55801-p135">Dictionary_icd_10_cm キーワード辞書からすべての用語をに基づいて[病気の分類を国際、10 分のリビジョン、臨床変更 (ICD 10 CM)](https://go.microsoft.com/fwlink/?linkid=852604)。このタイプは、用語、保険のコードではないのだけを検索します。</span><span class="sxs-lookup"><span data-stu-id="55801-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="55801-2165">病気 (ICD 9 CM) の国際的な分類</span><span class="sxs-lookup"><span data-stu-id="55801-2165">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2166">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2166">Format</span></span>

<span data-ttu-id="55801-2167">辞書</span><span class="sxs-lookup"><span data-stu-id="55801-2167">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2168">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2168">Pattern</span></span>

<span data-ttu-id="55801-2169">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2169">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2170">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2170">Checksum</span></span>

<span data-ttu-id="55801-2171">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2172">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2172">Definition</span></span>

<span data-ttu-id="55801-2173">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2173">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2174">Dictionary_icd_9_cm からキーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="55801-2174">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2175">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2175">Keywords</span></span>

<span data-ttu-id="55801-p136">Dictionary_icd_9_cm キーワード辞書からすべての用語をに基づいて[病気の分類を国際、9 番目のリビジョン、臨床変更 (ICD 9 CM)](https://go.microsoft.com/fwlink/?linkid=852605)。このタイプは、用語、保険のコードではないのだけを検索します。</span><span class="sxs-lookup"><span data-stu-id="55801-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="55801-2178">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2178">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2179">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2179">Format</span></span>

<span data-ttu-id="55801-2180">(2012 年 5 年 12 月 31日) までの古い形式:</span><span class="sxs-lookup"><span data-stu-id="55801-2180">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="55801-2181">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="55801-2181">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="55801-2182">新しい形式 (1 年 2013年 1 月と後)。</span><span class="sxs-lookup"><span data-stu-id="55801-2182">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="55801-2183">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="55801-2183">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2184">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2184">Pattern</span></span>

<span data-ttu-id="55801-2185">(2012 年 5 年 12 月 31日) までの古い形式:</span><span class="sxs-lookup"><span data-stu-id="55801-2185">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="55801-2186">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2186">Seven digits</span></span> 
- <span data-ttu-id="55801-2187">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-2187">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="55801-2188">新しい形式 (1 年 2013年 1 月と後)。</span><span class="sxs-lookup"><span data-stu-id="55801-2188">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="55801-2189">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2189">Seven digits</span></span> 
- <span data-ttu-id="55801-2190">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-2190">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="55801-2191">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="55801-2191">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2192">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2192">Checksum</span></span>

<span data-ttu-id="55801-2193">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2194">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2194">Definition</span></span>

<span data-ttu-id="55801-2195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2196">関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2196">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2197">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-2197">One of the following is true:</span></span>
    - <span data-ttu-id="55801-2198">Keyword_ireland_pps のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2198">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="55801-2199">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2199">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="55801-2200">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2200">The checksum passes.</span></span>

<span data-ttu-id="55801-2201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2201">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2202">関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2202">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2203">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2203">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2204">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2204">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="55801-2205">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="55801-2205">Keyword_ireland_pps</span></span>

- <span data-ttu-id="55801-2206">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="55801-2206">Personal Public Service Number</span></span> 
- <span data-ttu-id="55801-2207">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2207">PPS Number</span></span> 
- <span data-ttu-id="55801-2208">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="55801-2208">PPS Num</span></span> 
- <span data-ttu-id="55801-2209">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2209">PPS No.</span></span> 
- <span data-ttu-id="55801-2210">PPS #
</span><span class="sxs-lookup"><span data-stu-id="55801-2210">PPS #</span></span> 
- <span data-ttu-id="55801-2211">PPS #</span><span class="sxs-lookup"><span data-stu-id="55801-2211">PPS#</span></span> 
- <span data-ttu-id="55801-2212">PPSN
</span><span class="sxs-lookup"><span data-stu-id="55801-2212">PPSN</span></span> 
- <span data-ttu-id="55801-2213">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="55801-2213">Public Services Card</span></span> 
- <span data-ttu-id="55801-2214">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="55801-2214">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="55801-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="55801-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="55801-2217">PSP
</span><span class="sxs-lookup"><span data-stu-id="55801-2217">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="55801-2218">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-2218">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2219">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2219">Format</span></span>

<span data-ttu-id="55801-2220">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2220">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2221">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2221">Pattern</span></span>

<span data-ttu-id="55801-2222">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="55801-2222">Formatted:</span></span>
- <span data-ttu-id="55801-2223">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2223">Two digits</span></span> 
- <span data-ttu-id="55801-2224">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-2224">A dash</span></span> 
- <span data-ttu-id="55801-2225">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2225">Three digits</span></span> 
- <span data-ttu-id="55801-2226">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-2226">A dash</span></span> 
- <span data-ttu-id="55801-2227">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2227">Eight digits</span></span>

<span data-ttu-id="55801-2228">書式設定されていない場合:</span><span class="sxs-lookup"><span data-stu-id="55801-2228">Unformatted:</span></span>
- <span data-ttu-id="55801-2229">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2229">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2230">Checksum</span></span>

<span data-ttu-id="55801-2231">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2231">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2232">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2232">Definition</span></span>

<span data-ttu-id="55801-2233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2234">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2234">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2235">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2235">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2236">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2236">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="55801-2237">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="55801-2237">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="55801-2238">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2238">Bank Account Number</span></span> 
- <span data-ttu-id="55801-2239">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="55801-2239">Bank Account</span></span> 
- <span data-ttu-id="55801-2240">Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2240">Account Number</span></span> 
- <span data-ttu-id="55801-2241">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="55801-2241">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="55801-2242">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="55801-2242">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="55801-2243">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2243">Format</span></span>

<span data-ttu-id="55801-2244">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2245">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2245">Pattern</span></span>

<span data-ttu-id="55801-2246">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2247">Checksum</span></span>

<span data-ttu-id="55801-2248">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2248">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2249">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2249">Definition</span></span>

<span data-ttu-id="55801-2250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2251">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2251">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2252">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2252">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="55801-2253">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2253">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2254">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2254">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="55801-2255">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="55801-2255">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="55801-2256">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="55801-2256">מספר זהות</span></span> 
- <span data-ttu-id="55801-2257">National ID Number</span><span class="sxs-lookup"><span data-stu-id="55801-2257">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="55801-2258">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-2258">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2259">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2259">Format</span></span>

<span data-ttu-id="55801-2260">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="55801-2260">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2261">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2261">Pattern</span></span>

- <span data-ttu-id="55801-2262">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="55801-2262">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="55801-2263">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-2263">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2264">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-2264">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2265">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="55801-2265">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="55801-2266">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-2266">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2267">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2267">Checksum</span></span>

<span data-ttu-id="55801-2268">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2269">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2269">Definition</span></span>

<span data-ttu-id="55801-2270">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2271">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2271">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2272">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2272">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2273">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2273">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="55801-2274">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="55801-2274">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="55801-2275">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="55801-2275">numero di patente di guida</span></span> 
- <span data-ttu-id="55801-2276">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="55801-2276">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="55801-2277">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-2277">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2278">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2278">Format</span></span>

<span data-ttu-id="55801-2279">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2279">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2280">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2280">Pattern</span></span>

<span data-ttu-id="55801-2281">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="55801-2281">Bank account number:</span></span>
- <span data-ttu-id="55801-2282">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2282">Seven or eight digits</span></span>
- <span data-ttu-id="55801-2283">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="55801-2283">Bank account branch code:</span></span>
- <span data-ttu-id="55801-2284">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2284">Four digits</span></span> 
- <span data-ttu-id="55801-2285">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="55801-2285">A space or dash (optional)</span></span> 
- <span data-ttu-id="55801-2286">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2286">Three digits</span></span>

<span data-ttu-id="55801-2287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2287">Checksum</span></span>

<span data-ttu-id="55801-2288">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2288">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2289">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2289">Definition</span></span>

<span data-ttu-id="55801-2290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2290">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2291">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2291">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2292">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2292">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="55801-2293">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-2293">One of the following is true:</span></span>
- <span data-ttu-id="55801-2294">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2294">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2295">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2295">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="55801-2296">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2296">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2297">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2297">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2298">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2298">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2299">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2299">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="55801-2300">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="55801-2300">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="55801-2301">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2301">Checking Account Number</span></span> 
- <span data-ttu-id="55801-2302">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="55801-2302">Checking Account</span></span> 
- <span data-ttu-id="55801-2303">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-2303">Checking Account #</span></span> 
- <span data-ttu-id="55801-2304">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2304">Checking Acct Number</span></span> 
- <span data-ttu-id="55801-2305">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-2305">Checking Acct #</span></span> 
- <span data-ttu-id="55801-2306">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2306">Checking Acct No.</span></span> 
- <span data-ttu-id="55801-2307">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2307">Checking Account No.</span></span> 
- <span data-ttu-id="55801-2308">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2308">Bank Account Number</span></span> 
- <span data-ttu-id="55801-2309">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="55801-2309">Bank Account</span></span> 
- <span data-ttu-id="55801-2310">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-2310">Bank Account #</span></span> 
- <span data-ttu-id="55801-2311">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2311">Bank Acct Number</span></span> 
- <span data-ttu-id="55801-2312">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-2312">Bank Acct #</span></span> 
- <span data-ttu-id="55801-2313">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2313">Bank Acct No.</span></span> 
- <span data-ttu-id="55801-2314">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2314">Bank Account No.</span></span> 
- <span data-ttu-id="55801-2315">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2315">Savings Account Number</span></span> 
- <span data-ttu-id="55801-2316">預金/貯蓄口座</span><span class="sxs-lookup"><span data-stu-id="55801-2316">Savings Account</span></span> 
- <span data-ttu-id="55801-2317">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-2317">Savings Account #</span></span> 
- <span data-ttu-id="55801-2318">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2318">Savings Acct Number</span></span> 
- <span data-ttu-id="55801-2319">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-2319">Savings Acct #</span></span> 
- <span data-ttu-id="55801-2320">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2320">Savings Acct No.</span></span> 
- <span data-ttu-id="55801-2321">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2321">Savings Account No.</span></span> 
- <span data-ttu-id="55801-2322">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2322">Debit Account Number</span></span> 
- <span data-ttu-id="55801-2323">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="55801-2323">Debit Account</span></span> 
- <span data-ttu-id="55801-2324">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-2324">Debit Account #</span></span> 
- <span data-ttu-id="55801-2325">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2325">Debit Acct Number</span></span> 
- <span data-ttu-id="55801-2326">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-2326">Debit Acct #</span></span> 
- <span data-ttu-id="55801-2327">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2327">Debit Acct No.</span></span> 
- <span data-ttu-id="55801-2328">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2328">Debit Account No.</span></span> 
- <span data-ttu-id="55801-2329">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="55801-2329">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="55801-2330">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="55801-2330">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="55801-2331">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="55801-2331">＃勘定の確認</span></span> 
- <span data-ttu-id="55801-2332">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="55801-2332">勘定番号の確認</span></span> 
- <span data-ttu-id="55801-2333">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="55801-2333">口座番号の確認</span></span> 
- <span data-ttu-id="55801-2334">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-2334">銀行口座番号</span></span> 
- <span data-ttu-id="55801-2335">銀行口座</span><span class="sxs-lookup"><span data-stu-id="55801-2335">銀行口座</span></span> 
- <span data-ttu-id="55801-2336">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2336">銀行口座＃</span></span> 
- <span data-ttu-id="55801-2337">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2337">銀行の勘定番号</span></span> 
- <span data-ttu-id="55801-2338">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2338">銀行のacct＃</span></span> 
- <span data-ttu-id="55801-2339">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="55801-2339">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="55801-2340">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-2340">銀行口座番号</span></span>
- <span data-ttu-id="55801-2341">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2341">普通預金口座番号</span></span> 
- <span data-ttu-id="55801-2342">預金口座
</span><span class="sxs-lookup"><span data-stu-id="55801-2342">預金口座</span></span> 
- <span data-ttu-id="55801-2343">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2343">貯蓄口座＃</span></span> 
- <span data-ttu-id="55801-2344">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="55801-2344">貯蓄勘定の数</span></span> 
- <span data-ttu-id="55801-2345">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2345">貯蓄勘定＃</span></span> 
- <span data-ttu-id="55801-2346">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2346">貯蓄勘定番号</span></span> 
- <span data-ttu-id="55801-2347">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2347">普通預金口座番号</span></span> 
- <span data-ttu-id="55801-2348">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2348">引き落とし口座番号</span></span> 
- <span data-ttu-id="55801-2349">口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-2349">口座番号</span></span> 
- <span data-ttu-id="55801-2350">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2350">口座番号＃</span></span> 
- <span data-ttu-id="55801-2351">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2351">デビットのacct番号</span></span> 
- <span data-ttu-id="55801-2352">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2352">デビット勘定＃</span></span> 
- <span data-ttu-id="55801-2353">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2353">デビットACCTの番号</span></span> 
- <span data-ttu-id="55801-2354">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2354">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="55801-2355">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="55801-2355">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="55801-2356">Otemachi</span><span class="sxs-lookup"><span data-stu-id="55801-2356">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="55801-2357">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-2357">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2358">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2358">Format</span></span>

<span data-ttu-id="55801-2359">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2359">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2360">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2360">Pattern</span></span>

<span data-ttu-id="55801-2361">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2361">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2362">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2362">Checksum</span></span>

<span data-ttu-id="55801-2363">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2363">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2364">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2364">Definition</span></span>

<span data-ttu-id="55801-2365">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2365">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2366">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2366">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2367">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2367">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2368">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2368">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="55801-2369">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="55801-2369">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="55801-2370">dl#</span><span class="sxs-lookup"><span data-stu-id="55801-2370">dl#</span></span> 
- <span data-ttu-id="55801-2371">DL #</span><span class="sxs-lookup"><span data-stu-id="55801-2371">DL＃</span></span> 
- <span data-ttu-id="55801-2372">dls#</span><span class="sxs-lookup"><span data-stu-id="55801-2372">dls#</span></span> 
- <span data-ttu-id="55801-2373">DL #</span><span class="sxs-lookup"><span data-stu-id="55801-2373">DLS＃</span></span> 
- <span data-ttu-id="55801-2374">driver license</span><span class="sxs-lookup"><span data-stu-id="55801-2374">driver license</span></span> 
- <span data-ttu-id="55801-2375">driver licenses</span><span class="sxs-lookup"><span data-stu-id="55801-2375">driver licenses</span></span> 
- <span data-ttu-id="55801-2376">drivers license</span><span class="sxs-lookup"><span data-stu-id="55801-2376">drivers license</span></span> 
- <span data-ttu-id="55801-2377">driver's license</span><span class="sxs-lookup"><span data-stu-id="55801-2377">driver's license</span></span> 
- <span data-ttu-id="55801-2378">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="55801-2378">drivers licenses</span></span> 
- <span data-ttu-id="55801-2379">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="55801-2379">driver's licenses</span></span> 
- <span data-ttu-id="55801-2380">driving licence
</span><span class="sxs-lookup"><span data-stu-id="55801-2380">driving licence</span></span> 
- <span data-ttu-id="55801-2381">lic#</span><span class="sxs-lookup"><span data-stu-id="55801-2381">lic#</span></span> 
- <span data-ttu-id="55801-2382">LIC #</span><span class="sxs-lookup"><span data-stu-id="55801-2382">LIC＃</span></span> 
- <span data-ttu-id="55801-2383">lics#</span><span class="sxs-lookup"><span data-stu-id="55801-2383">lics#</span></span> 
- <span data-ttu-id="55801-2384">状態 id</span><span class="sxs-lookup"><span data-stu-id="55801-2384">state id</span></span> 
- <span data-ttu-id="55801-2385">state identification
</span><span class="sxs-lookup"><span data-stu-id="55801-2385">state identification</span></span> 
- <span data-ttu-id="55801-2386">state identification number
</span><span class="sxs-lookup"><span data-stu-id="55801-2386">state identification number</span></span> 
- <span data-ttu-id="55801-2387">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2387">低所得国＃</span></span> 
- <span data-ttu-id="55801-2388">免許証</span><span class="sxs-lookup"><span data-stu-id="55801-2388">免許証</span></span> 
- <span data-ttu-id="55801-2389">状態ID</span><span class="sxs-lookup"><span data-stu-id="55801-2389">状態ID</span></span>
- <span data-ttu-id="55801-2390">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="55801-2390">状態の識別</span></span> 
- <span data-ttu-id="55801-2391">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2391">状態の識別番号</span></span> 
- <span data-ttu-id="55801-2392">運転免許</span><span class="sxs-lookup"><span data-stu-id="55801-2392">運転免許</span></span> 
- <span data-ttu-id="55801-2393">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-2393">運転免許証</span></span> 
- <span data-ttu-id="55801-2394">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-2394">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="55801-2395">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-2395">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2396">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2396">Format</span></span>

<span data-ttu-id="55801-2397">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2397">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2398">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2398">Pattern</span></span>

<span data-ttu-id="55801-2399">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2399">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2400">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2400">Checksum</span></span>

<span data-ttu-id="55801-2401">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2401">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2402">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2402">Definition</span></span>

<span data-ttu-id="55801-2403">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2404">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2404">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2405">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2405">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2406">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2406">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="55801-2407">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="55801-2407">Keyword_jp_passport</span></span>

- <span data-ttu-id="55801-2408">パスポート
</span><span class="sxs-lookup"><span data-stu-id="55801-2408">パスポート</span></span> 
- <span data-ttu-id="55801-2409">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2409">パスポート番号</span></span> 
- <span data-ttu-id="55801-2410">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="55801-2410">パスポートのNum</span></span> 
- <span data-ttu-id="55801-2411">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2411">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="55801-2412">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="55801-2412">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2413">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2413">Format</span></span>

<span data-ttu-id="55801-2414">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2414">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2415">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2415">Pattern</span></span>

<span data-ttu-id="55801-2416">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2416">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2417">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2417">Checksum</span></span>

<span data-ttu-id="55801-2418">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2418">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2419">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2419">Definition</span></span>

<span data-ttu-id="55801-2420">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2421">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2421">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2422">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2422">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2423">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2423">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="55801-2424">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="55801-2424">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="55801-2425">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="55801-2425">Resident Registration Number</span></span>
- <span data-ttu-id="55801-2426">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2426">Resident Register Number</span></span> 
- <span data-ttu-id="55801-2427">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2427">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="55801-2428">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2428">Resident Registration No.</span></span> 
- <span data-ttu-id="55801-2429">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2429">Resident Register No.</span></span> 
- <span data-ttu-id="55801-2430">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2430">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="55801-2431">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2431">Basic Resident Register No.</span></span> 
- <span data-ttu-id="55801-2432">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="55801-2432">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="55801-2433">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2433">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="55801-2434">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="55801-2434">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="55801-2435">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2435">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="55801-2436">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="55801-2436">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2437">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2437">Format</span></span>

<span data-ttu-id="55801-2438">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2438">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2439">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2439">Pattern</span></span>

<span data-ttu-id="55801-2440">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2440">7-12 digits:</span></span>
- <span data-ttu-id="55801-2441">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2441">Four digits</span></span> 
- <span data-ttu-id="55801-2442">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="55801-2442">A hyphen (optional)</span></span> 
- <span data-ttu-id="55801-2443">6 桁または</span><span class="sxs-lookup"><span data-stu-id="55801-2443">Six digits OR</span></span>
- <span data-ttu-id="55801-2444">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2444">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2445">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2445">Checksum</span></span>

<span data-ttu-id="55801-2446">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2446">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2447">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2447">Definition</span></span>

<span data-ttu-id="55801-2448">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2448">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2449">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2449">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2450">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2450">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="55801-2451">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2451">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2452">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2452">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2453">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2453">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2454">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2454">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="55801-2455">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="55801-2455">Keyword_jp_sin</span></span>

- <span data-ttu-id="55801-2456">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="55801-2456">Social Insurance No.</span></span> 
- <span data-ttu-id="55801-2457">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="55801-2457">Social Insurance Num</span></span> 
- <span data-ttu-id="55801-2458">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2458">Social Insurance Number</span></span> 
- <span data-ttu-id="55801-2459">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="55801-2459">社会保険のテンキー</span></span> 
- <span data-ttu-id="55801-2460">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2460">社会保険番号</span></span> 
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="55801-2461">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="55801-2461">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2462">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2462">Format</span></span>

<span data-ttu-id="55801-2463">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2463">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2464">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2464">Pattern</span></span>

<span data-ttu-id="55801-2465">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2465">12 digits:</span></span>
- <span data-ttu-id="55801-2466">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2466">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="55801-2467">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2467">A dash (optional)</span></span> 
- <span data-ttu-id="55801-2468">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="55801-2468">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="55801-2469">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2469">A dash (optional)</span></span> 
- <span data-ttu-id="55801-2470">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2470">Three random digits</span></span> 
- <span data-ttu-id="55801-2471">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="55801-2471">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2472">Checksum</span></span>

<span data-ttu-id="55801-2473">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2473">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2474">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2474">Definition</span></span>

<span data-ttu-id="55801-2475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2475">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2476">正規表現 Regex_malaysia_id_card_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2476">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2477">Keyword_malaysia_id_card_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2477">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2478">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2478">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="55801-2479">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="55801-2479">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="55801-2480">MyKad</span><span class="sxs-lookup"><span data-stu-id="55801-2480">MyKad</span></span> 
- <span data-ttu-id="55801-2481">Identity Card</span><span class="sxs-lookup"><span data-stu-id="55801-2481">Identity Card</span></span> 
- <span data-ttu-id="55801-2482">ID カード</span><span class="sxs-lookup"><span data-stu-id="55801-2482">ID Card</span></span> 
- <span data-ttu-id="55801-2483">Id カード</span><span class="sxs-lookup"><span data-stu-id="55801-2483">Identification Card</span></span> 
- <span data-ttu-id="55801-2484">Digital Application Card
</span><span class="sxs-lookup"><span data-stu-id="55801-2484">Digital Application Card</span></span> 
- <span data-ttu-id="55801-2485">Kad Akuan Diri
</span><span class="sxs-lookup"><span data-stu-id="55801-2485">Kad Akuan Diri</span></span> 
- <span data-ttu-id="55801-2486">Kad Aplikasi Digital
</span><span class="sxs-lookup"><span data-stu-id="55801-2486">Kad Aplikasi Digital</span></span> 
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="55801-2487">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2487">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2488">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2488">Format</span></span>

<span data-ttu-id="55801-2489">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2489">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2490">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2490">Pattern</span></span>

<span data-ttu-id="55801-2491">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2491">8-9 digits:</span></span>
- <span data-ttu-id="55801-2492">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2492">Three digits</span></span> 
- <span data-ttu-id="55801-2493">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2493">A space (optional)</span></span> 
- <span data-ttu-id="55801-2494">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2494">Three digits</span></span> 
- <span data-ttu-id="55801-2495">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="55801-2495">A space (optional)</span></span> 
- <span data-ttu-id="55801-2496">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2496">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2497">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2497">Checksum</span></span>

<span data-ttu-id="55801-2498">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2498">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2499">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2499">Definition</span></span>

<span data-ttu-id="55801-2500">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2500">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2501">関数 Func_netherlands_bsn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2501">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2502">Keyword_netherlands_bsn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2502">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="55801-2503">関数 Func_eu_date2 が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2503">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="55801-2504">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2504">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2505">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2505">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="55801-2506">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="55801-2506">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="55801-2507">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="55801-2507">Citizen service number</span></span> 
- <span data-ttu-id="55801-2508">BSN

</span><span class="sxs-lookup"><span data-stu-id="55801-2508">BSN</span></span> 
- <span data-ttu-id="55801-2509">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="55801-2509">Burgerservicenummer</span></span> 
- <span data-ttu-id="55801-2510">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="55801-2510">Sofinummer</span></span> 
- <span data-ttu-id="55801-2511">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="55801-2511">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="55801-2512">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="55801-2512">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="55801-2513">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="55801-2513">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2514">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2514">Format</span></span>

<span data-ttu-id="55801-2515">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2515">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2516">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2516">Pattern</span></span>

<span data-ttu-id="55801-2517">3 つの文字を (大文字小文字を区別)、スペース (省略可能) 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2517">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2518">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2518">Checksum</span></span>

<span data-ttu-id="55801-2519">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2519">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2520">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2520">Definition</span></span>

<span data-ttu-id="55801-2521">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2521">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2522">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2522">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2523">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2523">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="55801-2524">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2524">The checksum passes.</span></span>

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

<span data-ttu-id="55801-2525">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2525">Keywords</span></span>

<span data-ttu-id="55801-2526">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="55801-2526">Keyword_nz_terms</span></span>

- <span data-ttu-id="55801-2527">NHI
</span><span class="sxs-lookup"><span data-stu-id="55801-2527">NHI</span></span> 
- <span data-ttu-id="55801-2528">ニュージーランド</span><span class="sxs-lookup"><span data-stu-id="55801-2528">New Zealand</span></span> 
- <span data-ttu-id="55801-2529">正常性</span><span class="sxs-lookup"><span data-stu-id="55801-2529">Health</span></span> 
- <span data-ttu-id="55801-2530">treatment
</span><span class="sxs-lookup"><span data-stu-id="55801-2530">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="55801-2531">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="55801-2531">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2532">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2532">Format</span></span>

<span data-ttu-id="55801-2533">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2533">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2534">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2534">Pattern</span></span>

<span data-ttu-id="55801-2535">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2535">11 digits:</span></span>
- <span data-ttu-id="55801-2536">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2536">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="55801-2537">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="55801-2537">Three-digit individual number</span></span> 
- <span data-ttu-id="55801-2538">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="55801-2538">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2539">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2539">Checksum</span></span>

<span data-ttu-id="55801-2540">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2540">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2541">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2541">Definition</span></span>

<span data-ttu-id="55801-2542">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2542">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2543">関数 Func_norway_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2543">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2544">Keyword_norway_id_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2544">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="55801-2545">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2545">The checksum passes.</span></span>
- <span data-ttu-id="55801-2546">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2546">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2547">関数 Func_norway_id_numbe がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2547">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2548">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2548">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2549">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2549">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="55801-2550">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="55801-2550">Keyword_norway_id_number</span></span>

- <span data-ttu-id="55801-2551">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="55801-2551">Personal identification number</span></span>
- <span data-ttu-id="55801-2552">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="55801-2552">Norwegian ID Number</span></span>
- <span data-ttu-id="55801-2553">ID Number</span><span class="sxs-lookup"><span data-stu-id="55801-2553">ID Number</span></span>
- <span data-ttu-id="55801-2554">Identification</span><span class="sxs-lookup"><span data-stu-id="55801-2554">Identification</span></span>
- <span data-ttu-id="55801-2555">Personnummer</span><span class="sxs-lookup"><span data-stu-id="55801-2555">Personnummer</span></span>
- <span data-ttu-id="55801-2556">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="55801-2556">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="55801-2557">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2557">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2558">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2558">Format</span></span>

<span data-ttu-id="55801-2559">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2559">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2560">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2560">Pattern</span></span>

<span data-ttu-id="55801-2561">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2561">12 digits:</span></span>
- <span data-ttu-id="55801-2562">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2562">Four digits</span></span> 
- <span data-ttu-id="55801-2563">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-2563">A hyphen</span></span> 
- <span data-ttu-id="55801-2564">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2564">Seven digits</span></span> 
- <span data-ttu-id="55801-2565">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-2565">A hyphen</span></span> 
- <span data-ttu-id="55801-2566">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2566">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2567">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2567">Checksum</span></span>

<span data-ttu-id="55801-2568">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2568">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2569">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2569">Definition</span></span>

<span data-ttu-id="55801-2570">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2570">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2571">正規表現 Regex_philippines_unified_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2571">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2572">Keyword_philippines_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2572">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2573">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2573">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="55801-2574">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="55801-2574">Keyword_philippines_id</span></span>

- <span data-ttu-id="55801-2575">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="55801-2575">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="55801-2576">UMID
</span><span class="sxs-lookup"><span data-stu-id="55801-2576">UMID</span></span> 
- <span data-ttu-id="55801-2577">Identity Card</span><span class="sxs-lookup"><span data-stu-id="55801-2577">Identity Card</span></span> 
- <span data-ttu-id="55801-2578">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="55801-2578">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="55801-2579">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="55801-2579">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="55801-2580">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2580">Format</span></span>

<span data-ttu-id="55801-2581">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2581">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2582">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2582">Pattern</span></span>

<span data-ttu-id="55801-2583">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2583">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2584">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2584">Checksum</span></span>

<span data-ttu-id="55801-2585">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2585">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2586">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2586">Definition</span></span>

<span data-ttu-id="55801-p138">DLP ポリシーとは、75% がこの種の機密情報を検出したことを確信、近くにある 300 文字以内の場合: Func_polish_national_id 関数は、パターンに一致するコンテンツを検索します。。Keyword_polish_national_id_passport_number からキーワードを検出するとします。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="55801-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2590">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2590">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="55801-2591">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="55801-2591">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="55801-2592">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="55801-2592">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="55801-2593">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="55801-2593">Dowód Tożsamości</span></span> 
- <span data-ttu-id="55801-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="55801-p139">dow. os.</span></span> 

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="55801-2596">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="55801-2596">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2597">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2597">Format</span></span>

<span data-ttu-id="55801-2598">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2598">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2599">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2599">Pattern</span></span>

<span data-ttu-id="55801-2600">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2600">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2601">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2601">Checksum</span></span>

<span data-ttu-id="55801-2602">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2602">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2603">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2603">Definition</span></span>

<span data-ttu-id="55801-2604">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2604">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2605">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2605">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2606">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2606">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="55801-2607">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2607">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2608">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2608">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="55801-2609">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="55801-2609">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="55801-2610">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="55801-2610">Nr PESEL</span></span>
- <span data-ttu-id="55801-2611">PESEL</span><span class="sxs-lookup"><span data-stu-id="55801-2611">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="55801-2612">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="55801-2612">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="55801-2613">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2613">Format</span></span>

<span data-ttu-id="55801-2614">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2614">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2615">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2615">Pattern</span></span>

<span data-ttu-id="55801-2616">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2616">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2617">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2617">Checksum</span></span>

<span data-ttu-id="55801-2618">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2618">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2619">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2619">Definition</span></span>

<span data-ttu-id="55801-2620">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2620">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2621">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2621">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2622">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2622">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="55801-2623">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2623">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2624">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2624">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="55801-2625">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="55801-2625">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="55801-2626">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="55801-2626">Nazwa i nr dowodu tożsamości</span></span> 
- <span data-ttu-id="55801-2627">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="55801-2627">Dowód Tożsamości</span></span> 
- <span data-ttu-id="55801-p140">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="55801-p140">dow. os.</span></span> 

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="55801-2630">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="55801-2630">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2631">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2631">Format</span></span>

<span data-ttu-id="55801-2632">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2632">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2633">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2633">Pattern</span></span>

<span data-ttu-id="55801-2634">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2634">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2635">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2635">Checksum</span></span>

<span data-ttu-id="55801-2636">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2636">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2637">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2637">Definition</span></span>

<span data-ttu-id="55801-2638">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2638">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2639">正規表現 Regex_portugal_citizen_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2639">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2640">Keyword_portugal_citizen_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2640">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2641">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2641">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="55801-2642">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="55801-2642">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="55801-2643">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="55801-2643">Citizen Card</span></span>
- <span data-ttu-id="55801-2644">National ID Card</span><span class="sxs-lookup"><span data-stu-id="55801-2644">National ID Card</span></span>
- <span data-ttu-id="55801-2645">CC</span><span class="sxs-lookup"><span data-stu-id="55801-2645">CC</span></span>
- <span data-ttu-id="55801-2646">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="55801-2646">Cartão de Cidadão</span></span>
- <span data-ttu-id="55801-2647">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="55801-2647">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="55801-2648">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="55801-2648">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="55801-2649">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2649">Format</span></span>

<span data-ttu-id="55801-2650">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2650">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2651">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2651">Pattern</span></span>

<span data-ttu-id="55801-2652">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2652">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2653">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2653">Checksum</span></span>

<span data-ttu-id="55801-2654">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2654">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2655">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2655">Definition</span></span>

<span data-ttu-id="55801-2656">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2656">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2657">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2657">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2658">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2658">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2659">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2659">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="55801-2660">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="55801-2660">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="55801-2661">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="55801-2661">Identification Card</span></span> 
- <span data-ttu-id="55801-2662">I card number
</span><span class="sxs-lookup"><span data-stu-id="55801-2662">I card number</span></span> 
- <span data-ttu-id="55801-2663">ID number
</span><span class="sxs-lookup"><span data-stu-id="55801-2663">ID number</span></span> 
- <span data-ttu-id="55801-2664">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="55801-2664">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="55801-2665">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2665">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2666">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2666">Format</span></span>

<span data-ttu-id="55801-2667">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="55801-2667">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2668">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2668">Pattern</span></span>

- <span data-ttu-id="55801-2669">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2669">Nine letters and digits:</span></span>
- <span data-ttu-id="55801-2670">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-2670">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2671">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2671">Seven digits</span></span> 
- <span data-ttu-id="55801-2672">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="55801-2672">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2673">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2673">Checksum</span></span>

<span data-ttu-id="55801-2674">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2674">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2675">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2675">Definition</span></span>

<span data-ttu-id="55801-2676">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2676">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2677">正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2677">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2678">Keyword_singapore_nric のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2678">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="55801-2679">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2679">The checksum passes.</span></span>

<span data-ttu-id="55801-2680">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2680">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2681">正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2681">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2682">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2682">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2683">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2683">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="55801-2684">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="55801-2684">Keyword_singapore_nric</span></span>

- <span data-ttu-id="55801-2685">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="55801-2685">National Registration Identity Card</span></span> 
- <span data-ttu-id="55801-2686">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2686">Identity Card Number</span></span> 
- <span data-ttu-id="55801-2687">NRIC
</span><span class="sxs-lookup"><span data-stu-id="55801-2687">NRIC</span></span> 
- <span data-ttu-id="55801-2688">IC
</span><span class="sxs-lookup"><span data-stu-id="55801-2688">IC</span></span> 
- <span data-ttu-id="55801-2689">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2689">Foreign Identification Number</span></span> 
- <span data-ttu-id="55801-2690">FIN
</span><span class="sxs-lookup"><span data-stu-id="55801-2690">FIN</span></span> 
- <span data-ttu-id="55801-2691">身份证 </span><span class="sxs-lookup"><span data-stu-id="55801-2691">身份证</span></span> 
- <span data-ttu-id="55801-2692">身份證
</span><span class="sxs-lookup"><span data-stu-id="55801-2692">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="55801-2693">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="55801-2693">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2694">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2694">Format</span></span>

<span data-ttu-id="55801-2695">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2695">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2696">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2696">Pattern</span></span>

<span data-ttu-id="55801-2697">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2697">13 digits:</span></span>
- <span data-ttu-id="55801-2698">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2698">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="55801-2699">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2699">Four digits</span></span> 
- <span data-ttu-id="55801-2700">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="55801-2700">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="55801-2701">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="55801-2701">The digit "8" or "9"</span></span> 
- <span data-ttu-id="55801-2702">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2702">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2703">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2703">Checksum</span></span>

<span data-ttu-id="55801-2704">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2704">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2705">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2705">Definition</span></span>

<span data-ttu-id="55801-2706">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2706">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2707">関数 Func_south_africa_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2707">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2708">Keyword_south_africa_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2708">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="55801-2709">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2709">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2710">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2710">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="55801-2711">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="55801-2711">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="55801-2712">Identity card</span><span class="sxs-lookup"><span data-stu-id="55801-2712">Identity card</span></span>
- <span data-ttu-id="55801-2713">ID</span><span class="sxs-lookup"><span data-stu-id="55801-2713">ID</span></span>
- <span data-ttu-id="55801-2714">Identification</span><span class="sxs-lookup"><span data-stu-id="55801-2714">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="55801-2715">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="55801-2715">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2716">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2716">Format</span></span>

<span data-ttu-id="55801-2717">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2717">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2718">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2718">Pattern</span></span>

<span data-ttu-id="55801-2719">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2719">13 digits:</span></span>
- <span data-ttu-id="55801-2720">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2720">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="55801-2721">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="55801-2721">A hyphen</span></span> 
- <span data-ttu-id="55801-2722">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2722">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="55801-2723">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="55801-2723">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="55801-2724">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="55801-2724">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="55801-2725">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="55801-2725">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2726">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2726">Checksum</span></span>

<span data-ttu-id="55801-2727">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2727">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2728">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2728">Definition</span></span>

<span data-ttu-id="55801-2729">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2729">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2730">関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2730">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2731">Keyword_south_korea_resident_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2731">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="55801-2732">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2732">The checksum passes.</span></span>

<span data-ttu-id="55801-2733">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2733">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2734">関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2734">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2735">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2735">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2736">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2736">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="55801-2737">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="55801-2737">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="55801-2738">National ID card
</span><span class="sxs-lookup"><span data-stu-id="55801-2738">National ID card</span></span> 
- <span data-ttu-id="55801-2739">Citizen's Registration Number
</span><span class="sxs-lookup"><span data-stu-id="55801-2739">Citizen's Registration Number</span></span> 
- <span data-ttu-id="55801-2740">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="55801-2740">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="55801-2741">RRN
</span><span class="sxs-lookup"><span data-stu-id="55801-2741">RRN</span></span> 
- <span data-ttu-id="55801-2742">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="55801-2742">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="55801-2743">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="55801-2743">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-2744">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2744">Format</span></span>

<span data-ttu-id="55801-2745">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2745">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2746">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2746">Pattern</span></span>

<span data-ttu-id="55801-2747">11-12 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="55801-2747">11-12 digits:</span></span>
- <span data-ttu-id="55801-2748">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2748">Two digits</span></span> 
- <span data-ttu-id="55801-2749">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="55801-2749">A forward slash (optional)</span></span> 
- <span data-ttu-id="55801-2750">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2750">7-8 digits</span></span> 
- <span data-ttu-id="55801-2751">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="55801-2751">A forward slash (optional)</span></span> 
- <span data-ttu-id="55801-2752">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2752">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2753">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2753">Checksum</span></span>

<span data-ttu-id="55801-2754">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2754">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2755">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2755">Definition</span></span>

<span data-ttu-id="55801-2756">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2756">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2757">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2757">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2758">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2758">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2759">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2759">Keywords</span></span>

<span data-ttu-id="55801-2760">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2760">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="55801-2761">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="55801-2761">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="55801-2762">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2762">Format</span></span>

<span data-ttu-id="55801-2763">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="55801-2763">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2764">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2764">Pattern</span></span>

<span data-ttu-id="55801-2765">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="55801-2765">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="55801-2766">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="55801-2766">2-4 digits (optional)</span></span> 
- <span data-ttu-id="55801-2767">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2767">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="55801-2768">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="55801-2768">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="55801-2769">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2769">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2770">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2770">Checksum</span></span>

<span data-ttu-id="55801-2771">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2771">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2772">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2772">Definition</span></span>

<span data-ttu-id="55801-2773">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2773">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2774">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2774">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2775">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2775">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2776">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2776">Keywords</span></span>

<span data-ttu-id="55801-2777">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2777">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="55801-2778">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-2778">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2779">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2779">Format</span></span>

<span data-ttu-id="55801-2780">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2780">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2781">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2781">Pattern</span></span>

<span data-ttu-id="55801-2782">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-2782">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2783">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2783">Checksum</span></span>

<span data-ttu-id="55801-2784">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2784">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2785">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2785">Definition</span></span>

<span data-ttu-id="55801-2786">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2786">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2787">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2787">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2788">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-2788">One of the following is true:</span></span>
    - <span data-ttu-id="55801-2789">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2789">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="55801-2790">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2790">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-2791">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2791">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="55801-2792">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="55801-2792">Keyword_sweden_passport</span></span>

- <span data-ttu-id="55801-2793">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="55801-2793">visa requirements</span></span> 
- <span data-ttu-id="55801-2794">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="55801-2794">Alien Registration Card</span></span> 
- <span data-ttu-id="55801-2795">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="55801-2795">Schengen visas</span></span> 
- <span data-ttu-id="55801-2796">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="55801-2796">Schengen visa</span></span> 
- <span data-ttu-id="55801-2797">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="55801-2797">Visa Processing</span></span> 
- <span data-ttu-id="55801-2798">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="55801-2798">Visa Type</span></span> 
- <span data-ttu-id="55801-2799">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="55801-2799">Single Entry</span></span> 
- <span data-ttu-id="55801-2800">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="55801-2800">Multiple Entry</span></span> 
- <span data-ttu-id="55801-2801">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="55801-2801">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="55801-2802">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="55801-2802">Keyword_passport</span></span>

- <span data-ttu-id="55801-2803">Passport Number</span><span class="sxs-lookup"><span data-stu-id="55801-2803">Passport Number</span></span> 
- <span data-ttu-id="55801-2804">
Passport No</span><span class="sxs-lookup"><span data-stu-id="55801-2804">Passport No</span></span> 
- <span data-ttu-id="55801-2805">Passport #
</span><span class="sxs-lookup"><span data-stu-id="55801-2805">Passport #</span></span> 
- <span data-ttu-id="55801-2806">Passport#
</span><span class="sxs-lookup"><span data-stu-id="55801-2806">Passport#</span></span> 
- <span data-ttu-id="55801-2807">PassportID</span><span class="sxs-lookup"><span data-stu-id="55801-2807">PassportID</span></span> 
- <span data-ttu-id="55801-2808">Passportno
</span><span class="sxs-lookup"><span data-stu-id="55801-2808">Passportno</span></span> 
- <span data-ttu-id="55801-2809">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-2809">passportnumber</span></span> 
- <span data-ttu-id="55801-2810">パスポート</span><span class="sxs-lookup"><span data-stu-id="55801-2810">パスポート</span></span> 
- <span data-ttu-id="55801-2811">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2811">パスポート番号</span></span> 
- <span data-ttu-id="55801-2812">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="55801-2812">パスポートのNum</span></span> 
- <span data-ttu-id="55801-2813">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2813">パスポート＃</span></span> 
- <span data-ttu-id="55801-2814">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="55801-2814">Numéro de passeport</span></span> 
- <span data-ttu-id="55801-2815">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="55801-2815">Passeport n °</span></span> 
- <span data-ttu-id="55801-2816">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="55801-2816">Passeport Non</span></span> 
- <span data-ttu-id="55801-2817">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="55801-2817">Passeport #</span></span> 
- <span data-ttu-id="55801-2818">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="55801-2818">Passeport#</span></span> 
- <span data-ttu-id="55801-2819">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="55801-2819">PasseportNon</span></span> 
- <span data-ttu-id="55801-2820">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="55801-2820">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="55801-2821">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="55801-2821">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="55801-2822">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2822">Format</span></span>

<span data-ttu-id="55801-2823">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="55801-2823">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2824">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2824">Pattern</span></span>

<span data-ttu-id="55801-2825">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2825">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="55801-2826">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="55801-2826">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2827">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="55801-2827">An optional space</span></span> 
- <span data-ttu-id="55801-2828">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="55801-2828">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="55801-2829">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="55801-2829">An optional space</span></span> 
- <span data-ttu-id="55801-2830">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="55801-2830">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2831">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2831">Checksum</span></span>

<span data-ttu-id="55801-2832">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2832">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2833">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2833">Definition</span></span>

<span data-ttu-id="55801-2834">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2834">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2835">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2835">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2836">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2836">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2837">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2837">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="55801-2838">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="55801-2838">Keyword_swift</span></span>

- <span data-ttu-id="55801-2839">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="55801-2839">international organization for standardization 9362</span></span> 
- <span data-ttu-id="55801-2840">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="55801-2840">iso 9362</span></span> 
- <span data-ttu-id="55801-2841">iso9362</span><span class="sxs-lookup"><span data-stu-id="55801-2841">iso9362</span></span> 
- <span data-ttu-id="55801-2842">swift\#</span><span class="sxs-lookup"><span data-stu-id="55801-2842">swift\#</span></span> 
- <span data-ttu-id="55801-2843">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="55801-2843">swiftcode</span></span> 
- <span data-ttu-id="55801-2844">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-2844">swiftnumber</span></span> 
- <span data-ttu-id="55801-2845">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-2845">swiftroutingnumber</span></span> 
- <span data-ttu-id="55801-2846">swift コード</span><span class="sxs-lookup"><span data-stu-id="55801-2846">swift code</span></span> 
- <span data-ttu-id="55801-2847">swift number #
</span><span class="sxs-lookup"><span data-stu-id="55801-2847">swift number #</span></span> 
- <span data-ttu-id="55801-2848">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="55801-2848">swift routing number</span></span> 
- <span data-ttu-id="55801-2849">bic number
</span><span class="sxs-lookup"><span data-stu-id="55801-2849">bic number</span></span> 
- <span data-ttu-id="55801-2850">bic code
</span><span class="sxs-lookup"><span data-stu-id="55801-2850">bic code</span></span> 
- <span data-ttu-id="55801-2851">bic\#</span><span class="sxs-lookup"><span data-stu-id="55801-2851">bic \#</span></span> 
- <span data-ttu-id="55801-2852">bic\#</span><span class="sxs-lookup"><span data-stu-id="55801-2852">bic\#</span></span> 
- <span data-ttu-id="55801-2853">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="55801-2853">bank identifier code</span></span> 
- <span data-ttu-id="55801-2854">標準化9362</span><span class="sxs-lookup"><span data-stu-id="55801-2854">標準化9362</span></span> 
- <span data-ttu-id="55801-2855">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="55801-2855">迅速＃</span></span> 
- <span data-ttu-id="55801-2856">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="55801-2856">SWIFTコード</span></span> 
- <span data-ttu-id="55801-2857">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2857">SWIFT番号</span></span> 
- <span data-ttu-id="55801-2858">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2858">迅速なルーティング番号</span></span> 
- <span data-ttu-id="55801-2859">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="55801-2859">BIC番号</span></span> 
- <span data-ttu-id="55801-2860">BICコード
</span><span class="sxs-lookup"><span data-stu-id="55801-2860">BICコード</span></span> 
- <span data-ttu-id="55801-2861">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="55801-2861">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="55801-2862">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="55801-2862">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="55801-2863">rapide\#</span><span class="sxs-lookup"><span data-stu-id="55801-2863">rapide \#</span></span> 
- <span data-ttu-id="55801-2864">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="55801-2864">code SWIFT</span></span> 
- <span data-ttu-id="55801-2865">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="55801-2865">le numéro de swift</span></span> 
- <span data-ttu-id="55801-2866">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="55801-2866">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="55801-2867">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="55801-2867">le numéro BIC</span></span> 
- <span data-ttu-id="55801-2868">\#BIC</span><span class="sxs-lookup"><span data-stu-id="55801-2868">\# BIC</span></span> 
- <span data-ttu-id="55801-2869">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="55801-2869">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="55801-2870">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="55801-2870">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="55801-2871">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2871">Format</span></span>

<span data-ttu-id="55801-2872">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2872">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2873">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2873">Pattern</span></span>

<span data-ttu-id="55801-2874">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2874">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="55801-2875">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="55801-2875">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="55801-2876">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="55801-2876">The digit "1" or "2"</span></span> 
- <span data-ttu-id="55801-2877">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2877">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2878">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2878">Checksum</span></span>

<span data-ttu-id="55801-2879">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2879">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2880">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2880">Definition</span></span>

<span data-ttu-id="55801-2881">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2881">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2882">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2882">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2883">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2883">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="55801-2884">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2884">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2885">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2885">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="55801-2886">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="55801-2886">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="55801-2887">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="55801-2887">身份證字號</span></span> 
- <span data-ttu-id="55801-2888">身份證
</span><span class="sxs-lookup"><span data-stu-id="55801-2888">身份證</span></span> 
- <span data-ttu-id="55801-2889">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="55801-2889">身份證號碼</span></span> 
- <span data-ttu-id="55801-2890">身份證號
</span><span class="sxs-lookup"><span data-stu-id="55801-2890">身份證號</span></span> 
- <span data-ttu-id="55801-2891">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="55801-2891">身分證字號</span></span> 
- <span data-ttu-id="55801-2892">身分證 </span><span class="sxs-lookup"><span data-stu-id="55801-2892">身分證</span></span> 
- <span data-ttu-id="55801-2893">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="55801-2893">身分證號碼</span></span> 
- <span data-ttu-id="55801-2894">身份證號
</span><span class="sxs-lookup"><span data-stu-id="55801-2894">身份證號</span></span> 
- <span data-ttu-id="55801-2895">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="55801-2895">身分證統一編號</span></span> 
- <span data-ttu-id="55801-2896">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="55801-2896">國民身分證統一編號</span></span> 
- <span data-ttu-id="55801-2897">簽名
</span><span class="sxs-lookup"><span data-stu-id="55801-2897">簽名</span></span> 
- <span data-ttu-id="55801-2898">蓋章
</span><span class="sxs-lookup"><span data-stu-id="55801-2898">蓋章</span></span> 
- <span data-ttu-id="55801-2899">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="55801-2899">簽名或蓋章</span></span> 
- <span data-ttu-id="55801-2900">簽章</span><span class="sxs-lookup"><span data-stu-id="55801-2900">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="55801-2901">台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-2901">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2902">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2902">Format</span></span>

- <span data-ttu-id="55801-2903">生体認証パスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2903">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="55801-2904">非生体認証パスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2904">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2905">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2905">Pattern</span></span>
<span data-ttu-id="55801-2906">生体認証パスポートの番号:</span><span class="sxs-lookup"><span data-stu-id="55801-2906">Biometric passport number:</span></span>
- <span data-ttu-id="55801-2907">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="55801-2907">The digit "3"</span></span> 
- <span data-ttu-id="55801-2908">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2908">Eight digits</span></span>

<span data-ttu-id="55801-2909">非生体認証パスポートの番号:</span><span class="sxs-lookup"><span data-stu-id="55801-2909">Non-biometric passport number:</span></span>
- <span data-ttu-id="55801-2910">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2910">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2911">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2911">Checksum</span></span>

<span data-ttu-id="55801-2912">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2912">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2913">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2913">Definition</span></span>

<span data-ttu-id="55801-2914">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2914">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2915">正規表現 Regex_taiwan_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2915">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2916">Keyword_taiwan_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2916">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2917">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2917">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="55801-2918">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="55801-2918">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="55801-2919">ROC passport number
</span><span class="sxs-lookup"><span data-stu-id="55801-2919">ROC passport number</span></span> 
- <span data-ttu-id="55801-2920">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-2920">Passport number</span></span> 
- <span data-ttu-id="55801-2921">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="55801-2921">Passport no</span></span> 
- <span data-ttu-id="55801-2922">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="55801-2922">Passport Num</span></span> 
- <span data-ttu-id="55801-2923">Passport #
</span><span class="sxs-lookup"><span data-stu-id="55801-2923">Passport #</span></span> 
- <span data-ttu-id="55801-2924">护照
</span><span class="sxs-lookup"><span data-stu-id="55801-2924">护照</span></span> 
- <span data-ttu-id="55801-2925">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="55801-2925">中華民國護照</span></span> 
- <span data-ttu-id="55801-2926">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="55801-2926">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="55801-2927">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="55801-2927">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2928">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2928">Format</span></span>

<span data-ttu-id="55801-2929">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="55801-2929">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2930">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2930">Pattern</span></span>

<span data-ttu-id="55801-2931">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2931">10 letters and digits:</span></span>
- <span data-ttu-id="55801-2932">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="55801-2932">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="55801-2933">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2933">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2934">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2934">Checksum</span></span>

<span data-ttu-id="55801-2935">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2935">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2936">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2936">Definition</span></span>

<span data-ttu-id="55801-2937">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2937">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2938">正規表現 Regex_taiwan_resident_certificate がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2938">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2939">Keyword_taiwan_resident_certificate のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2939">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2940">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2940">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="55801-2941">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="55801-2941">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="55801-2942">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="55801-2942">Resident Certificate</span></span> 
- <span data-ttu-id="55801-2943">常駐の証明書</span><span class="sxs-lookup"><span data-stu-id="55801-2943">Resident Cert</span></span> 
- <span data-ttu-id="55801-2944">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="55801-2944">Resident Cert.</span></span> 
- <span data-ttu-id="55801-2945">Id カード</span><span class="sxs-lookup"><span data-stu-id="55801-2945">Identification card</span></span> 
- <span data-ttu-id="55801-2946">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="55801-2946">Alien Resident Certificate</span></span> 
- <span data-ttu-id="55801-2947">ARC
</span><span class="sxs-lookup"><span data-stu-id="55801-2947">ARC</span></span> 
- <span data-ttu-id="55801-2948">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="55801-2948">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="55801-2949">TARC
</span><span class="sxs-lookup"><span data-stu-id="55801-2949">TARC</span></span> 
- <span data-ttu-id="55801-2950">居留證
</span><span class="sxs-lookup"><span data-stu-id="55801-2950">居留證</span></span> 
- <span data-ttu-id="55801-2951">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="55801-2951">外僑居留證</span></span> 
- <span data-ttu-id="55801-2952">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="55801-2952">台灣地區居留證</span></span> 
   
## <a name="uk-drivers-license-number"></a><span data-ttu-id="55801-p141">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2955">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2955">Format</span></span>

<span data-ttu-id="55801-2956">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="55801-2956">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2957">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2957">Pattern</span></span>

<span data-ttu-id="55801-2958">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="55801-2958">18 letters and digits:</span></span>
- <span data-ttu-id="55801-2959">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="55801-2959">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="55801-2960">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2960">One digit</span></span> 
- <span data-ttu-id="55801-2961">誕生日を示す DDMMY という日付形式の 5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2961">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="55801-2962">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="55801-2962">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="55801-2963">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2963">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2964">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2964">Checksum</span></span>

<span data-ttu-id="55801-2965">はい</span><span class="sxs-lookup"><span data-stu-id="55801-2965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2966">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2966">Definition</span></span>

<span data-ttu-id="55801-2967">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2967">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2968">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2968">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2969">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2969">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="55801-2970">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-2970">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-2971">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-2971">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="55801-2972">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="55801-2972">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="55801-2973">DVLA
</span><span class="sxs-lookup"><span data-stu-id="55801-2973">DVLA</span></span> 
- <span data-ttu-id="55801-2974">light vans
</span><span class="sxs-lookup"><span data-stu-id="55801-2974">light vans</span></span> 
- <span data-ttu-id="55801-2975">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="55801-2975">quadbikes</span></span> 
- <span data-ttu-id="55801-2976">motor cars
</span><span class="sxs-lookup"><span data-stu-id="55801-2976">motor cars</span></span> 
- <span data-ttu-id="55801-2977">125cc</span><span class="sxs-lookup"><span data-stu-id="55801-2977">125cc</span></span> 
- <span data-ttu-id="55801-2978">sidecar
</span><span class="sxs-lookup"><span data-stu-id="55801-2978">sidecar</span></span> 
- <span data-ttu-id="55801-2979">tricycles
</span><span class="sxs-lookup"><span data-stu-id="55801-2979">tricycles</span></span> 
- <span data-ttu-id="55801-2980">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="55801-2980">motorcycles</span></span> 
- <span data-ttu-id="55801-2981">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="55801-2981">photocard licence</span></span> 
- <span data-ttu-id="55801-2982">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="55801-2982">learner drivers</span></span> 
- <span data-ttu-id="55801-2983">licence holder
</span><span class="sxs-lookup"><span data-stu-id="55801-2983">licence holder</span></span> 
- <span data-ttu-id="55801-2984">licence holders
</span><span class="sxs-lookup"><span data-stu-id="55801-2984">licence holders</span></span> 
- <span data-ttu-id="55801-2985">driving licences
</span><span class="sxs-lookup"><span data-stu-id="55801-2985">driving licences</span></span> 
- <span data-ttu-id="55801-2986">driving licence
</span><span class="sxs-lookup"><span data-stu-id="55801-2986">driving licence</span></span> 
- <span data-ttu-id="55801-2987">dual control car
</span><span class="sxs-lookup"><span data-stu-id="55801-2987">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="55801-p142">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="55801-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-2990">形式</span><span class="sxs-lookup"><span data-stu-id="55801-2990">Format</span></span>

<span data-ttu-id="55801-2991">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2991">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-2992">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-2992">Pattern</span></span>

<span data-ttu-id="55801-2993">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-2993">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-2994">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-2994">Checksum</span></span>

<span data-ttu-id="55801-2995">なし</span><span class="sxs-lookup"><span data-stu-id="55801-2995">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-2996">定義</span><span class="sxs-lookup"><span data-stu-id="55801-2996">Definition</span></span>

<span data-ttu-id="55801-2997">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-2997">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-2998">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2998">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-2999">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-2999">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-3000">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3000">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="55801-3001">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="55801-3001">Keyword_uk_electoral</span></span>

- <span data-ttu-id="55801-3002">council nomination
</span><span class="sxs-lookup"><span data-stu-id="55801-3002">council nomination</span></span> 
- <span data-ttu-id="55801-3003">nomination form
</span><span class="sxs-lookup"><span data-stu-id="55801-3003">nomination form</span></span> 
- <span data-ttu-id="55801-3004">electoral register

</span><span class="sxs-lookup"><span data-stu-id="55801-3004">electoral register</span></span> 
- <span data-ttu-id="55801-3005">electoral roll</span><span class="sxs-lookup"><span data-stu-id="55801-3005">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="55801-p143">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="55801-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-3008">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3008">Format</span></span>

<span data-ttu-id="55801-3009">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3009">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3010">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3010">Pattern</span></span>

<span data-ttu-id="55801-3011">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="55801-3011">10-17 digits:</span></span>
- <span data-ttu-id="55801-3012">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3012">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="55801-3013">スペース</span><span class="sxs-lookup"><span data-stu-id="55801-3013">A space</span></span> 
- <span data-ttu-id="55801-3014">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3014">Three digits</span></span> 
- <span data-ttu-id="55801-3015">スペース</span><span class="sxs-lookup"><span data-stu-id="55801-3015">A space</span></span> 
- <span data-ttu-id="55801-3016">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3016">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3017">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3017">Checksum</span></span>

<span data-ttu-id="55801-3018">はい</span><span class="sxs-lookup"><span data-stu-id="55801-3018">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="55801-3019">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3019">Definition</span></span>

<span data-ttu-id="55801-3020">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3020">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3021">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3021">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3022">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-3022">One of the following is true:</span></span>
    - <span data-ttu-id="55801-3023">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3023">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="55801-3024">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3024">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="55801-3025">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3025">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="55801-3026">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="55801-3026">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-3027">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3027">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="55801-3028">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="55801-3028">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="55801-3029">national health service
</span><span class="sxs-lookup"><span data-stu-id="55801-3029">national health service</span></span> 
- <span data-ttu-id="55801-3030">nhs
</span><span class="sxs-lookup"><span data-stu-id="55801-3030">nhs</span></span> 
- <span data-ttu-id="55801-3031">health services authority

</span><span class="sxs-lookup"><span data-stu-id="55801-3031">health services authority</span></span> 
- <span data-ttu-id="55801-3032">health authority</span><span class="sxs-lookup"><span data-stu-id="55801-3032">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="55801-3033">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="55801-3033">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="55801-3034">patient id
</span><span class="sxs-lookup"><span data-stu-id="55801-3034">patient id</span></span> 
- <span data-ttu-id="55801-3035">patient identification
</span><span class="sxs-lookup"><span data-stu-id="55801-3035">patient identification</span></span> 
- <span data-ttu-id="55801-3036">patient no

</span><span class="sxs-lookup"><span data-stu-id="55801-3036">patient no</span></span> 
- <span data-ttu-id="55801-3037">patient number</span><span class="sxs-lookup"><span data-stu-id="55801-3037">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="55801-3038">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="55801-3038">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="55801-3039">GP</span><span class="sxs-lookup"><span data-stu-id="55801-3039">GP</span></span> 
- <span data-ttu-id="55801-3040">DOB
</span><span class="sxs-lookup"><span data-stu-id="55801-3040">DOB</span></span> 
- <span data-ttu-id="55801-3041">D.O.B</span><span class="sxs-lookup"><span data-stu-id="55801-3041">D.O.B</span></span> 
- <span data-ttu-id="55801-3042">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="55801-3042">Date of Birth</span></span> 
- <span data-ttu-id="55801-3043">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="55801-3043">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="55801-p144">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="55801-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="55801-3046">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3046">Format</span></span>

<span data-ttu-id="55801-3047">7 文字またはスペースまたはハイフンで区切られた 9 の文字</span><span class="sxs-lookup"><span data-stu-id="55801-3047">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3048">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3048">Pattern</span></span>

<span data-ttu-id="55801-3049">2 つの可能なパターン:</span><span class="sxs-lookup"><span data-stu-id="55801-3049">Two possible patterns:</span></span>

- <span data-ttu-id="55801-3050">2 つの文字 (有効な NINOs では、特定の文字のみを使用して、このプレフィックスは、このパターンを検証します大文字と小文字を区別しない)。</span><span class="sxs-lookup"><span data-stu-id="55801-3050">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="55801-3051">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3051">Six digits</span></span>
- <span data-ttu-id="55801-3052">どちらか '、' 'B'、'C'、または必要がある ' (などの接頭辞、のみ特定の文字が許可、サフィックスのない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="55801-3052">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="55801-3053">OR</span><span class="sxs-lookup"><span data-stu-id="55801-3053">OR</span></span>

- <span data-ttu-id="55801-3054">2 つの文字</span><span class="sxs-lookup"><span data-stu-id="55801-3054">Two letters</span></span>
- <span data-ttu-id="55801-3055">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-3055">A space or dash</span></span>
- <span data-ttu-id="55801-3056">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3056">Two digits</span></span>
- <span data-ttu-id="55801-3057">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-3057">A space or dash</span></span>
- <span data-ttu-id="55801-3058">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3058">Two digits</span></span>
- <span data-ttu-id="55801-3059">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-3059">A space or dash</span></span>
- <span data-ttu-id="55801-3060">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3060">Two digits</span></span>
- <span data-ttu-id="55801-3061">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-3061">A space or dash</span></span>
- <span data-ttu-id="55801-3062">どちらか '、'、'B'、'C'、または必要がある '</span><span class="sxs-lookup"><span data-stu-id="55801-3062">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3063">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3063">Checksum</span></span>

<span data-ttu-id="55801-3064">なし</span><span class="sxs-lookup"><span data-stu-id="55801-3064">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-3065">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3065">Definition</span></span>

<span data-ttu-id="55801-3066">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3066">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3067">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3067">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3068">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3068">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="55801-3069">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3069">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3070">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3070">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3071">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-3071">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-3072">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3072">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="55801-3073">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="55801-3073">Keyword_uk_nino</span></span>

- <span data-ttu-id="55801-3074">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="55801-3074">national insurance number</span></span> 
- <span data-ttu-id="55801-3075">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="55801-3075">national insurance contributions</span></span> 
- <span data-ttu-id="55801-3076">protection act
</span><span class="sxs-lookup"><span data-stu-id="55801-3076">protection act</span></span> 
- <span data-ttu-id="55801-3077">insurance
</span><span class="sxs-lookup"><span data-stu-id="55801-3077">insurance</span></span> 
- <span data-ttu-id="55801-3078">social security number
</span><span class="sxs-lookup"><span data-stu-id="55801-3078">social security number</span></span> 
- <span data-ttu-id="55801-3079">insurance application
</span><span class="sxs-lookup"><span data-stu-id="55801-3079">insurance application</span></span> 
- <span data-ttu-id="55801-3080">medical application
</span><span class="sxs-lookup"><span data-stu-id="55801-3080">medical application</span></span> 
- <span data-ttu-id="55801-3081">social insurance
</span><span class="sxs-lookup"><span data-stu-id="55801-3081">social insurance</span></span> 
- <span data-ttu-id="55801-3082">medical attention
</span><span class="sxs-lookup"><span data-stu-id="55801-3082">medical attention</span></span> 
- <span data-ttu-id="55801-3083">社会保障</span><span class="sxs-lookup"><span data-stu-id="55801-3083">social security</span></span> 
- <span data-ttu-id="55801-3084">great britain
</span><span class="sxs-lookup"><span data-stu-id="55801-3084">great britain</span></span> 
- <span data-ttu-id="55801-3085">insurance
</span><span class="sxs-lookup"><span data-stu-id="55801-3085">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="55801-p145">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="55801-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-3088">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3088">Format</span></span>

<span data-ttu-id="55801-3089">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3089">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3090">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3090">Pattern</span></span>

<span data-ttu-id="55801-3091">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-3091">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3092">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3092">Checksum</span></span>

<span data-ttu-id="55801-3093">なし</span><span class="sxs-lookup"><span data-stu-id="55801-3093">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-3094">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3094">Definition</span></span>

<span data-ttu-id="55801-3095">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3095">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3096">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3096">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3097">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3097">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-3098">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3098">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="55801-3099">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="55801-3099">Keyword_passport</span></span>

- <span data-ttu-id="55801-3100">Passport Number</span><span class="sxs-lookup"><span data-stu-id="55801-3100">Passport Number</span></span> 
- <span data-ttu-id="55801-3101">
Passport No</span><span class="sxs-lookup"><span data-stu-id="55801-3101">Passport No</span></span> 
- <span data-ttu-id="55801-3102">Passport #
</span><span class="sxs-lookup"><span data-stu-id="55801-3102">Passport #</span></span> 
- <span data-ttu-id="55801-3103">Passport#
</span><span class="sxs-lookup"><span data-stu-id="55801-3103">Passport#</span></span> 
- <span data-ttu-id="55801-3104">PassportID</span><span class="sxs-lookup"><span data-stu-id="55801-3104">PassportID</span></span> 
- <span data-ttu-id="55801-3105">Passportno
</span><span class="sxs-lookup"><span data-stu-id="55801-3105">Passportno</span></span> 
- <span data-ttu-id="55801-3106">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="55801-3106">passportnumber</span></span> 
- <span data-ttu-id="55801-3107">パスポート</span><span class="sxs-lookup"><span data-stu-id="55801-3107">パスポート</span></span> 
- <span data-ttu-id="55801-3108">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="55801-3108">パスポート番号</span></span> 
- <span data-ttu-id="55801-3109">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="55801-3109">パスポートのNum</span></span> 
- <span data-ttu-id="55801-3110">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="55801-3110">パスポート＃</span></span> 
- <span data-ttu-id="55801-3111">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="55801-3111">Numéro de passeport</span></span> 
- <span data-ttu-id="55801-3112">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="55801-3112">Passeport n °</span></span> 
- <span data-ttu-id="55801-3113">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="55801-3113">Passeport Non</span></span> 
- <span data-ttu-id="55801-3114">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="55801-3114">Passeport #</span></span> 
- <span data-ttu-id="55801-3115">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="55801-3115">Passeport#</span></span> 
- <span data-ttu-id="55801-3116">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="55801-3116">PasseportNon</span></span> 
- <span data-ttu-id="55801-3117">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="55801-3117">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="55801-3118">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="55801-3118">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-3119">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3119">Format</span></span>

<span data-ttu-id="55801-3120">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3120">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3121">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3121">Pattern</span></span>

<span data-ttu-id="55801-3122">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="55801-3122">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3123">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3123">Checksum</span></span>

<span data-ttu-id="55801-3124">なし</span><span class="sxs-lookup"><span data-stu-id="55801-3124">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-3125">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3125">Definition</span></span>

<span data-ttu-id="55801-3126">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3126">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3127">正規表現 Regex_usa_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3127">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3128">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3128">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="55801-3129">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3129">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="55801-3130">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="55801-3130">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="55801-3131">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3131">Checking Account Number</span></span> 
- <span data-ttu-id="55801-3132">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="55801-3132">Checking Account</span></span> 
- <span data-ttu-id="55801-3133">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-3133">Checking Account #</span></span> 
- <span data-ttu-id="55801-3134">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3134">Checking Acct Number</span></span> 
- <span data-ttu-id="55801-3135">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-3135">Checking Acct #</span></span> 
- <span data-ttu-id="55801-3136">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3136">Checking Acct No.</span></span> 
- <span data-ttu-id="55801-3137">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3137">Checking Account No.</span></span> 
- <span data-ttu-id="55801-3138">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3138">Bank Account Number</span></span> 
- <span data-ttu-id="55801-3139">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-3139">Bank Account #</span></span> 
- <span data-ttu-id="55801-3140">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3140">Bank Acct Number</span></span> 
- <span data-ttu-id="55801-3141">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-3141">Bank Acct #</span></span> 
- <span data-ttu-id="55801-3142">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3142">Bank Acct No.</span></span> 
- <span data-ttu-id="55801-3143">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3143">Bank Account No.</span></span> 
- <span data-ttu-id="55801-3144">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3144">Savings Account Number</span></span> 
- <span data-ttu-id="55801-3145">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="55801-3145">Savings Account.</span></span> 
- <span data-ttu-id="55801-3146">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-3146">Savings Account #</span></span> 
- <span data-ttu-id="55801-3147">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3147">Savings Acct Number</span></span> 
- <span data-ttu-id="55801-3148">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-3148">Savings Acct #</span></span> 
- <span data-ttu-id="55801-3149">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3149">Savings Acct No.</span></span> 
- <span data-ttu-id="55801-3150">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3150">Savings Account No.</span></span> 
- <span data-ttu-id="55801-3151">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3151">Debit Account Number</span></span> 
- <span data-ttu-id="55801-3152">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="55801-3152">Debit Account</span></span> 
- <span data-ttu-id="55801-3153">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="55801-3153">Debit Account #</span></span> 
- <span data-ttu-id="55801-3154">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="55801-3154">Debit Acct Number</span></span> 
- <span data-ttu-id="55801-3155">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="55801-3155">Debit Acct #</span></span> 
- <span data-ttu-id="55801-3156">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3156">Debit Acct No.</span></span> 
- <span data-ttu-id="55801-3157">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="55801-3157">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="55801-3158">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-3158">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="55801-3159">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3159">Format</span></span>

<span data-ttu-id="55801-3160">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="55801-3160">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3161">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3161">Pattern</span></span>

<span data-ttu-id="55801-3162">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="55801-3162">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="55801-3163">ddd ddd ddd のような形式の 9 桁の数字がマッチします。</span><span class="sxs-lookup"><span data-stu-id="55801-3163">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="55801-3164">ddddddddd のような 9 桁の数字はマッチしません。</span><span class="sxs-lookup"><span data-stu-id="55801-3164">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3165">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3165">Checksum</span></span>

<span data-ttu-id="55801-3166">なし</span><span class="sxs-lookup"><span data-stu-id="55801-3166">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-3167">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3167">Definition</span></span>

<span data-ttu-id="55801-3168">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3168">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3169">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3169">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3170">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3170">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="55801-3171">Keyword_us_drivers_license のキーワードを検出しました。</span><span class="sxs-lookup"><span data-stu-id="55801-3171">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="55801-3172">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3172">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3173">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3173">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3174">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3174">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="55801-3175">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3175">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="55801-3176">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-3176">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-3177">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3177">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="55801-3178">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="55801-3178">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="55801-3179">DL</span><span class="sxs-lookup"><span data-stu-id="55801-3179">DL</span></span> 
- <span data-ttu-id="55801-3180">DLS</span><span class="sxs-lookup"><span data-stu-id="55801-3180">DLS</span></span> 
- <span data-ttu-id="55801-3181">CDL</span><span class="sxs-lookup"><span data-stu-id="55801-3181">CDL</span></span> 
- <span data-ttu-id="55801-3182">CDL</span><span class="sxs-lookup"><span data-stu-id="55801-3182">CDLS</span></span> 
- <span data-ttu-id="55801-3183">ID</span><span class="sxs-lookup"><span data-stu-id="55801-3183">ID</span></span> 
- <span data-ttu-id="55801-3184">Id</span><span class="sxs-lookup"><span data-stu-id="55801-3184">IDs</span></span> 
- <span data-ttu-id="55801-3185">DL#</span><span class="sxs-lookup"><span data-stu-id="55801-3185">DL#</span></span> 
- <span data-ttu-id="55801-3186">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="55801-3186">DLS#</span></span> 
- <span data-ttu-id="55801-3187">CDL#
</span><span class="sxs-lookup"><span data-stu-id="55801-3187">CDL#</span></span> 
- <span data-ttu-id="55801-3188">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="55801-3188">CDLS#</span></span> 
- <span data-ttu-id="55801-3189">ID#</span><span class="sxs-lookup"><span data-stu-id="55801-3189">ID#</span></span>
- <span data-ttu-id="55801-3190">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="55801-3190">IDs#</span></span> 
- <span data-ttu-id="55801-3191">ID number
</span><span class="sxs-lookup"><span data-stu-id="55801-3191">ID number</span></span> 
- <span data-ttu-id="55801-3192">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="55801-3192">ID numbers</span></span> 
- <span data-ttu-id="55801-3193">LIC</span><span class="sxs-lookup"><span data-stu-id="55801-3193">LIC</span></span> 
- <span data-ttu-id="55801-3194">LIC#
</span><span class="sxs-lookup"><span data-stu-id="55801-3194">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="55801-3195">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="55801-3195">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="55801-3196">DriverLic</span><span class="sxs-lookup"><span data-stu-id="55801-3196">DriverLic</span></span> 
- <span data-ttu-id="55801-3197">DriverLics</span><span class="sxs-lookup"><span data-stu-id="55801-3197">DriverLics</span></span> 
- <span data-ttu-id="55801-3198">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="55801-3198">DriverLicense</span></span> 
- <span data-ttu-id="55801-3199">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-3199">DriverLicenses</span></span> 
- <span data-ttu-id="55801-3200">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-3200">Driver Lic</span></span> 
- <span data-ttu-id="55801-3201">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="55801-3201">Driver Lics</span></span> 
- <span data-ttu-id="55801-3202">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-3202">Driver License</span></span> 
- <span data-ttu-id="55801-3203">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-3203">Driver Licenses</span></span> 
- <span data-ttu-id="55801-3204">DriversLic</span><span class="sxs-lookup"><span data-stu-id="55801-3204">DriversLic</span></span> 
- <span data-ttu-id="55801-3205">DriversLics</span><span class="sxs-lookup"><span data-stu-id="55801-3205">DriversLics</span></span> 
- <span data-ttu-id="55801-3206">証</span><span class="sxs-lookup"><span data-stu-id="55801-3206">DriversLicense</span></span> 
- <span data-ttu-id="55801-3207">DriversLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-3207">DriversLicenses</span></span> 
- <span data-ttu-id="55801-3208">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="55801-3208">Drivers Lic</span></span> 
- <span data-ttu-id="55801-3209">ドライバー Lics</span><span class="sxs-lookup"><span data-stu-id="55801-3209">Drivers Lics</span></span> 
- <span data-ttu-id="55801-3210">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="55801-3210">Drivers License</span></span> 
- <span data-ttu-id="55801-3211">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-3211">Drivers Licenses</span></span> 
- <span data-ttu-id="55801-3212">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="55801-3212">Driver'Lic</span></span> 
- <span data-ttu-id="55801-3213">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="55801-3213">Driver'Lics</span></span> 
- <span data-ttu-id="55801-3214">Driver'License</span><span class="sxs-lookup"><span data-stu-id="55801-3214">Driver'License</span></span> 
- <span data-ttu-id="55801-3215">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="55801-3215">Driver'Licenses</span></span> 
- <span data-ttu-id="55801-3216">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="55801-3216">Driver' Lic</span></span> 
- <span data-ttu-id="55801-3217">ドライバー ' Lics</span><span class="sxs-lookup"><span data-stu-id="55801-3217">Driver' Lics</span></span> 
- <span data-ttu-id="55801-3218">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-3218">Driver' License</span></span> 
- <span data-ttu-id="55801-3219">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="55801-3219">Driver' Licenses</span></span>
- <span data-ttu-id="55801-3220">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="55801-3220">Driver'sLic</span></span> 
- <span data-ttu-id="55801-3221">Driver'sLics</span><span class="sxs-lookup"><span data-stu-id="55801-3221">Driver'sLics</span></span> 
- <span data-ttu-id="55801-3222">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="55801-3222">Driver'sLicense</span></span> 
- <span data-ttu-id="55801-3223">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="55801-3223">Driver'sLicenses</span></span> 
- <span data-ttu-id="55801-3224">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="55801-3224">Driver's Lic</span></span> 
- <span data-ttu-id="55801-3225">ドライバーの Lics</span><span class="sxs-lookup"><span data-stu-id="55801-3225">Driver's Lics</span></span> 
- <span data-ttu-id="55801-3226">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-3226">Driver's License</span></span> 
- <span data-ttu-id="55801-3227">運転免許証</span><span class="sxs-lookup"><span data-stu-id="55801-3227">Driver's Licenses</span></span> 
- <span data-ttu-id="55801-3228">identification number
</span><span class="sxs-lookup"><span data-stu-id="55801-3228">identification number</span></span> 
- <span data-ttu-id="55801-3229">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="55801-3229">identification numbers</span></span> 
- <span data-ttu-id="55801-3230">identification #
</span><span class="sxs-lookup"><span data-stu-id="55801-3230">identification #</span></span> 
- <span data-ttu-id="55801-3231">id カード</span><span class="sxs-lookup"><span data-stu-id="55801-3231">id card</span></span> 
- <span data-ttu-id="55801-3232">id カード</span><span class="sxs-lookup"><span data-stu-id="55801-3232">id cards</span></span> 
- <span data-ttu-id="55801-3233">id カード</span><span class="sxs-lookup"><span data-stu-id="55801-3233">identification card</span></span> 
- <span data-ttu-id="55801-3234">id カード</span><span class="sxs-lookup"><span data-stu-id="55801-3234">identification cards</span></span> 
- <span data-ttu-id="55801-3235">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="55801-3235">DriverLic#</span></span> 
- <span data-ttu-id="55801-3236">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="55801-3236">DriverLics#</span></span> 
- <span data-ttu-id="55801-3237">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="55801-3237">DriverLicense#</span></span> 
- <span data-ttu-id="55801-3238">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-3238">DriverLicenses#</span></span> 
- <span data-ttu-id="55801-3239">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="55801-3239">Driver Lic#</span></span> 
- <span data-ttu-id="55801-3240">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-3240">Driver Lics#</span></span> 
- <span data-ttu-id="55801-3241">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-3241">Driver License#</span></span> 
- <span data-ttu-id="55801-3242">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-3242">Driver Licenses#</span></span> 
- <span data-ttu-id="55801-3243">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="55801-3243">DriversLic#</span></span> 
- <span data-ttu-id="55801-3244">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="55801-3244">DriversLics#</span></span> 
- <span data-ttu-id="55801-3245">証番号</span><span class="sxs-lookup"><span data-stu-id="55801-3245">DriversLicense#</span></span> 
- <span data-ttu-id="55801-3246">DriversLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-3246">DriversLicenses#</span></span> 
- <span data-ttu-id="55801-3247">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="55801-3247">Drivers Lic#</span></span> 
- <span data-ttu-id="55801-3248">ドライバー Lics #</span><span class="sxs-lookup"><span data-stu-id="55801-3248">Drivers Lics#</span></span> 
- <span data-ttu-id="55801-3249">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-3249">Drivers License#</span></span> 
- <span data-ttu-id="55801-3250">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="55801-3250">Drivers Licenses#</span></span> 
- <span data-ttu-id="55801-3251">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-3251">Driver'Lic#</span></span> 
- <span data-ttu-id="55801-3252">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-3252">Driver'Lics#</span></span> 
- <span data-ttu-id="55801-3253">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="55801-3253">Driver'License#</span></span> 
- <span data-ttu-id="55801-3254">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-3254">Driver'Licenses#</span></span> 
- <span data-ttu-id="55801-3255">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-3255">Driver' Lic#</span></span> 
- <span data-ttu-id="55801-3256">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-3256">Driver' Lics#</span></span> 
- <span data-ttu-id="55801-3257">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="55801-3257">Driver' License#</span></span> 
- <span data-ttu-id="55801-3258">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-3258">Driver' Licenses#</span></span> 
- <span data-ttu-id="55801-3259">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="55801-3259">Driver'sLic#</span></span> 
- <span data-ttu-id="55801-3260">Driver'sLics #</span><span class="sxs-lookup"><span data-stu-id="55801-3260">Driver'sLics#</span></span> 
- <span data-ttu-id="55801-3261">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="55801-3261">Driver'sLicense#</span></span> 
- <span data-ttu-id="55801-3262">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="55801-3262">Driver'sLicenses#</span></span> 
- <span data-ttu-id="55801-3263">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="55801-3263">Driver's Lic#</span></span> 
- <span data-ttu-id="55801-3264">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="55801-3264">Driver's Lics#</span></span> 
- <span data-ttu-id="55801-3265">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="55801-3265">Driver's License#</span></span> 
- <span data-ttu-id="55801-3266">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="55801-3266">Driver's Licenses#</span></span> 
- <span data-ttu-id="55801-3267">id のカード番号</span><span class="sxs-lookup"><span data-stu-id="55801-3267">id card#</span></span> 
- <span data-ttu-id="55801-3268">id cards#
</span><span class="sxs-lookup"><span data-stu-id="55801-3268">id cards#</span></span> 
- <span data-ttu-id="55801-3269">identification card#
</span><span class="sxs-lookup"><span data-stu-id="55801-3269">identification card#</span></span> 
- <span data-ttu-id="55801-3270">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="55801-3270">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="55801-3271">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="55801-3271">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="55801-3272">州の略号 (たとえば、"NY")
</span><span class="sxs-lookup"><span data-stu-id="55801-3272">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="55801-3273">州の名前 (たとえば、"New York")
</span><span class="sxs-lookup"><span data-stu-id="55801-3273">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="55801-3274">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="55801-3274">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-3275">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3275">Format</span></span>

<span data-ttu-id="55801-3276">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="55801-3276">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3277">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3277">Pattern</span></span>

<span data-ttu-id="55801-3278">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="55801-3278">Formatted:</span></span>
- <span data-ttu-id="55801-3279">数字「9」</span><span class="sxs-lookup"><span data-stu-id="55801-3279">The digit "9"</span></span> 
- <span data-ttu-id="55801-3280">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3280">Two digits</span></span> 
- <span data-ttu-id="55801-3281">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-3281">A space or dash</span></span> 
- <span data-ttu-id="55801-3282">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="55801-3282">A "7" or "8"</span></span> 
- <span data-ttu-id="55801-3283">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3283">A digit</span></span> 
- <span data-ttu-id="55801-3284">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="55801-3284">A space, or dash</span></span> 
- <span data-ttu-id="55801-3285">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3285">Four digits</span></span>

<span data-ttu-id="55801-3286">書式設定されていない場合:</span><span class="sxs-lookup"><span data-stu-id="55801-3286">Unformatted:</span></span>
- <span data-ttu-id="55801-3287">数字「9」</span><span class="sxs-lookup"><span data-stu-id="55801-3287">The digit "9"</span></span> 
- <span data-ttu-id="55801-3288">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3288">Two digits</span></span> 
- <span data-ttu-id="55801-3289">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="55801-3289">A "7" or "8"</span></span> 
- <span data-ttu-id="55801-3290">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3290">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3291">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3291">Checksum</span></span>

<span data-ttu-id="55801-3292">なし</span><span class="sxs-lookup"><span data-stu-id="55801-3292">No</span></span>

### <a name="definition"></a><span data-ttu-id="55801-3293">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3293">Definition</span></span>

<span data-ttu-id="55801-3294">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3294">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3295">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3295">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3296">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-3296">At least one of the following is true:</span></span>
    - <span data-ttu-id="55801-3297">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3297">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="55801-3298">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3298">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="55801-3299">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3299">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="55801-3300">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3300">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="55801-3301">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3302">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3302">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3303">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="55801-3303">At least one of the following is true:</span></span>
    - <span data-ttu-id="55801-3304">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3304">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="55801-3305">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3305">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="55801-3306">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3306">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-3307">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3307">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="55801-3308">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="55801-3308">Keyword_itin</span></span>

- <span data-ttu-id="55801-3309">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="55801-3309">taxpayer</span></span> 
- <span data-ttu-id="55801-3310">tax id
</span><span class="sxs-lookup"><span data-stu-id="55801-3310">tax id</span></span> 
- <span data-ttu-id="55801-3311">tax identification
</span><span class="sxs-lookup"><span data-stu-id="55801-3311">tax identification</span></span> 
- <span data-ttu-id="55801-3312">itin
</span><span class="sxs-lookup"><span data-stu-id="55801-3312">itin</span></span> 
- <span data-ttu-id="55801-3313">ssn</span><span class="sxs-lookup"><span data-stu-id="55801-3313">ssn</span></span> 
- <span data-ttu-id="55801-3314">tin
</span><span class="sxs-lookup"><span data-stu-id="55801-3314">tin</span></span> 
- <span data-ttu-id="55801-3315">社会保障</span><span class="sxs-lookup"><span data-stu-id="55801-3315">social security</span></span> 
- <span data-ttu-id="55801-3316">tax payer
</span><span class="sxs-lookup"><span data-stu-id="55801-3316">tax payer</span></span> 
- <span data-ttu-id="55801-3317">itins
</span><span class="sxs-lookup"><span data-stu-id="55801-3317">itins</span></span> 
- <span data-ttu-id="55801-3318">taxid

</span><span class="sxs-lookup"><span data-stu-id="55801-3318">taxid</span></span> 
- <span data-ttu-id="55801-3319">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="55801-3319">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="55801-3320">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="55801-3320">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="55801-3321">License</span><span class="sxs-lookup"><span data-stu-id="55801-3321">License</span></span> 
- <span data-ttu-id="55801-3322">DL</span><span class="sxs-lookup"><span data-stu-id="55801-3322">DL</span></span> 
- <span data-ttu-id="55801-3323">DOB
</span><span class="sxs-lookup"><span data-stu-id="55801-3323">DOB</span></span> 
- <span data-ttu-id="55801-3324">誕生日</span><span class="sxs-lookup"><span data-stu-id="55801-3324">Birthdate</span></span> 
- <span data-ttu-id="55801-3325">誕生日 </span><span class="sxs-lookup"><span data-stu-id="55801-3325">Birthday</span></span> 
- <span data-ttu-id="55801-3326">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="55801-3326">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="55801-3327">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="55801-3327">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="55801-3328">形式</span><span class="sxs-lookup"><span data-stu-id="55801-3328">Format</span></span>

<span data-ttu-id="55801-3329">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="55801-3329">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="55801-3330">2011 年の中旬より前に発行されている場合、SSN には厳密な書式があり、数値の特定の部分が一定の範囲内に入っていなければ有効になりません。</span><span class="sxs-lookup"><span data-stu-id="55801-3330">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="55801-3331">パターン</span><span class="sxs-lookup"><span data-stu-id="55801-3331">Pattern</span></span>

<span data-ttu-id="55801-3332">4 つの異なるパターンで SSN を検索する 4 つの関数を次に示します。</span><span class="sxs-lookup"><span data-stu-id="55801-3332">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="55801-3333">Func_ssn は 2011 年以前の、厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="55801-3333">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="55801-3334">Func_unformatted_ssn は 2011 年以前の、厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="55801-3334">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="55801-3335">Func_randomized_formatted_ssn は 2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="55801-3335">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="55801-3336">Func_randomized_unformatted_ssn は 2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="55801-3336">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="55801-3337">チェックサム</span><span class="sxs-lookup"><span data-stu-id="55801-3337">Checksum</span></span>

<span data-ttu-id="55801-3338">なし</span><span class="sxs-lookup"><span data-stu-id="55801-3338">No</span></span>


### <a name="definition"></a><span data-ttu-id="55801-3339">定義</span><span class="sxs-lookup"><span data-stu-id="55801-3339">Definition</span></span>

<span data-ttu-id="55801-3340">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3340">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3341">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3341">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3342">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3342">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="55801-3343">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3343">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3344">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3344">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3345">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3345">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="55801-3346">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3346">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3347">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3347">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3348">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3348">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="55801-3349">関数 Func_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-3349">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="55801-3350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="55801-3350">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="55801-3351">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3351">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="55801-3352">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="55801-3352">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="55801-3353">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="55801-3353">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="55801-3354">キーワード</span><span class="sxs-lookup"><span data-stu-id="55801-3354">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="55801-3355">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="55801-3355">Keyword_ssn</span></span>

- <span data-ttu-id="55801-3356">Social Security
</span><span class="sxs-lookup"><span data-stu-id="55801-3356">Social Security</span></span> 
- <span data-ttu-id="55801-3357">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="55801-3357">Social Security#</span></span> 
- <span data-ttu-id="55801-3358">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="55801-3358">Soc Sec</span></span> 
- <span data-ttu-id="55801-3359">SSN</span><span class="sxs-lookup"><span data-stu-id="55801-3359">SSN</span></span> 
- <span data-ttu-id="55801-3360">SSNS
</span><span class="sxs-lookup"><span data-stu-id="55801-3360">SSNS</span></span> 
- <span data-ttu-id="55801-3361">SSN#
</span><span class="sxs-lookup"><span data-stu-id="55801-3361">SSN#</span></span> 
- <span data-ttu-id="55801-3362">SS#
</span><span class="sxs-lookup"><span data-stu-id="55801-3362">SS#</span></span> 
- <span data-ttu-id="55801-3363">SSID
</span><span class="sxs-lookup"><span data-stu-id="55801-3363">SSID</span></span> 
   

