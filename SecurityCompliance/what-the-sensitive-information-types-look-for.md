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
ms.collection: Strat_O365_IP
ms.assetid: fd505979-76be-4d9f-b459-abef3fc9e86b
description: Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できる状態で、80の機密情報の種類が含まれています。このトピックでは、これらすべての機密情報の種類を一覧表示し、各種類を検出したときに DLP ポリシーがどのように検索されるかを示します。
ms.openlocfilehash: 17fb0b8d745168f8000fba9e6fc42f3c255a1937
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216357"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="a2b91-104">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="a2b91-104">What the sensitive information types look for</span></span>

<span data-ttu-id="a2b91-p102">Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。このトピックでは、これらすべての機密情報の種類を一覧表示し、各種類を検出したときに DLP ポリシーがどのように検索されるかを示します。機密情報の種類は、正規表現または関数で識別できるパターンによって定義されます。また、キーワードやチェックサムなどの補強証拠を使用して、機密情報の種類を識別することもできます。評価プロセスでは、信頼度と近接性も使用されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type. A sensitive information type is defined by a pattern that can be identified by a regular expression or a function. In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type. Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="a2b91-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-111">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-111">Format</span></span>

<span data-ttu-id="a2b91-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-113">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-113">Pattern</span></span>

<span data-ttu-id="a2b91-114">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-114">Formatted:</span></span>
- <span data-ttu-id="a2b91-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="a2b91-116">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-116">A hyphen</span></span>
- <span data-ttu-id="a2b91-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-117">Four digits</span></span>
- <span data-ttu-id="a2b91-118">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-118">A hyphen</span></span>
- <span data-ttu-id="a2b91-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-119">A digit</span></span>

<span data-ttu-id="a2b91-120">書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="a2b91-121">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-121">Checksum</span></span>

<span data-ttu-id="a2b91-122">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-123">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-123">Definition</span></span>

<span data-ttu-id="a2b91-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="a2b91-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-127">Keywords</span></span>

#### <a name="keywordabarouting"></a><span data-ttu-id="a2b91-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="a2b91-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="a2b91-129">aba</span><span class="sxs-lookup"><span data-stu-id="a2b91-129">aba</span></span>
- <span data-ttu-id="a2b91-130">
aba #</span><span class="sxs-lookup"><span data-stu-id="a2b91-130">aba #</span></span>
- <span data-ttu-id="a2b91-131">
aba routing #</span><span class="sxs-lookup"><span data-stu-id="a2b91-131">aba routing #</span></span>
- <span data-ttu-id="a2b91-132">aba ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-132">aba routing number</span></span>
- <span data-ttu-id="a2b91-133">
aba#</span><span class="sxs-lookup"><span data-stu-id="a2b91-133">aba#</span></span>
- <span data-ttu-id="a2b91-134">
abarouting#</span><span class="sxs-lookup"><span data-stu-id="a2b91-134">abarouting#</span></span>
- <span data-ttu-id="a2b91-135">
aba number</span><span class="sxs-lookup"><span data-stu-id="a2b91-135">aba number</span></span>
- <span data-ttu-id="a2b91-136">
abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a2b91-136">abaroutingnumber</span></span>
- <span data-ttu-id="a2b91-137">
american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="a2b91-137">american bank association routing #</span></span>
- <span data-ttu-id="a2b91-138">
american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="a2b91-138">american bank association routing number</span></span>
- <span data-ttu-id="a2b91-139">
americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="a2b91-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="a2b91-140">
americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a2b91-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="a2b91-141">
bank routing number</span><span class="sxs-lookup"><span data-stu-id="a2b91-141">bank routing number</span></span>
- <span data-ttu-id="a2b91-142">
bankrouting#</span><span class="sxs-lookup"><span data-stu-id="a2b91-142">bankrouting#</span></span>
- <span data-ttu-id="a2b91-143">
bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="a2b91-143">bankroutingnumber</span></span>
- <span data-ttu-id="a2b91-144">
routing transit number</span><span class="sxs-lookup"><span data-stu-id="a2b91-144">routing transit number</span></span>
- <span data-ttu-id="a2b91-145">
RTN
</span><span class="sxs-lookup"><span data-stu-id="a2b91-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="a2b91-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-147">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-147">Format</span></span>

<span data-ttu-id="a2b91-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-149">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-149">Pattern</span></span>

<span data-ttu-id="a2b91-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-150">Eight digits:</span></span>
- <span data-ttu-id="a2b91-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-151">Two digits</span></span>
- <span data-ttu-id="a2b91-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-152">A period</span></span>
- <span data-ttu-id="a2b91-153">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-153">Three digits</span></span>
- <span data-ttu-id="a2b91-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-154">A period</span></span>
- <span data-ttu-id="a2b91-155">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-156">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-156">Checksum</span></span>

<span data-ttu-id="a2b91-157">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-158">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-158">Definition</span></span>

<span data-ttu-id="a2b91-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-160">正規表現 Regex_argentina_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-161">Keyword_argentina_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-162">Keywords</span></span>

#### <a name="keywordargentinanationalid"></a><span data-ttu-id="a2b91-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="a2b91-164">Argentina National Identity number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="a2b91-165">ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-165">Identity</span></span> 
- <span data-ttu-id="a2b91-166">識別国の id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="a2b91-167">DNI
</span><span class="sxs-lookup"><span data-stu-id="a2b91-167">DNI</span></span> 
- <span data-ttu-id="a2b91-168">個人の NIC National レジストリ</span><span class="sxs-lookup"><span data-stu-id="a2b91-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="a2b91-169">Documento Nacional de Identidad
</span><span class="sxs-lookup"><span data-stu-id="a2b91-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="a2b91-170">Registro Nacional de las Personas
</span><span class="sxs-lookup"><span data-stu-id="a2b91-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="a2b91-171">Identidad
</span><span class="sxs-lookup"><span data-stu-id="a2b91-171">Identidad</span></span> 
- <span data-ttu-id="a2b91-172">Identificación
</span><span class="sxs-lookup"><span data-stu-id="a2b91-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="a2b91-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-174">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-174">Format</span></span>

<span data-ttu-id="a2b91-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-176">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-176">Pattern</span></span>

<span data-ttu-id="a2b91-p103">アカウント番号は6-10 桁です。オーストラリアの銀行都道府県の支店番号:</span><span class="sxs-lookup"><span data-stu-id="a2b91-p103">Account number is 6-10 digits. Australia bank state branch number:</span></span>
- <span data-ttu-id="a2b91-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-179">Three digits</span></span> 
- <span data-ttu-id="a2b91-180">ハイフン</span><span class="sxs-lookup"><span data-stu-id="a2b91-180">A hyphen</span></span> 
- <span data-ttu-id="a2b91-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-182">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-182">Checksum</span></span>

<span data-ttu-id="a2b91-183">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-184">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-184">Definition</span></span>

<span data-ttu-id="a2b91-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a2b91-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="a2b91-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="a2b91-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="a2b91-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-192">Keywords</span></span>

#### <a name="keywordaustraliabankaccountnumber"></a><span data-ttu-id="a2b91-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="a2b91-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="a2b91-194">swift bank code</span></span>
- <span data-ttu-id="a2b91-195">
correspondent bank</span><span class="sxs-lookup"><span data-stu-id="a2b91-195">correspondent bank</span></span>
- <span data-ttu-id="a2b91-196">
base currency</span><span class="sxs-lookup"><span data-stu-id="a2b91-196">base currency</span></span>
- <span data-ttu-id="a2b91-197">
usa account</span><span class="sxs-lookup"><span data-stu-id="a2b91-197">usa account</span></span>
- <span data-ttu-id="a2b91-198">
holder address</span><span class="sxs-lookup"><span data-stu-id="a2b91-198">holder address</span></span>
- <span data-ttu-id="a2b91-199">
bank address</span><span class="sxs-lookup"><span data-stu-id="a2b91-199">bank address</span></span>
- <span data-ttu-id="a2b91-200">
information account</span><span class="sxs-lookup"><span data-stu-id="a2b91-200">information account</span></span>
- <span data-ttu-id="a2b91-201">
fund transfers</span><span class="sxs-lookup"><span data-stu-id="a2b91-201">fund transfers</span></span>
- <span data-ttu-id="a2b91-202">
bank charges</span><span class="sxs-lookup"><span data-stu-id="a2b91-202">bank charges</span></span>
- <span data-ttu-id="a2b91-203">
bank details</span><span class="sxs-lookup"><span data-stu-id="a2b91-203">bank details</span></span>
- <span data-ttu-id="a2b91-204">
banking information</span><span class="sxs-lookup"><span data-stu-id="a2b91-204">banking information</span></span>
- <span data-ttu-id="a2b91-205">
full names</span><span class="sxs-lookup"><span data-stu-id="a2b91-205">full names</span></span>
- <span data-ttu-id="a2b91-206">

iaea</span><span class="sxs-lookup"><span data-stu-id="a2b91-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="a2b91-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-208">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-208">Format</span></span>

<span data-ttu-id="a2b91-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-210">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-210">Pattern</span></span>

<span data-ttu-id="a2b91-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="a2b91-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a2b91-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-213">Two digits</span></span> 
- <span data-ttu-id="a2b91-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a2b91-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="a2b91-215">または</span><span class="sxs-lookup"><span data-stu-id="a2b91-215">OR</span></span>

- <span data-ttu-id="a2b91-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-217">4-9 digits</span></span>

<span data-ttu-id="a2b91-218">または</span><span class="sxs-lookup"><span data-stu-id="a2b91-218">OR</span></span>

- <span data-ttu-id="a2b91-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="a2b91-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-220">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-220">Checksum</span></span>

<span data-ttu-id="a2b91-221">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-222">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-222">Definition</span></span>

<span data-ttu-id="a2b91-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="a2b91-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-227">Keywords</span></span>

#### <a name="keywordaustraliadriverslicensenumber"></a><span data-ttu-id="a2b91-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="a2b91-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="a2b91-229">international driving permits</span></span>
- <span data-ttu-id="a2b91-230">
australian automobile association</span><span class="sxs-lookup"><span data-stu-id="a2b91-230">australian automobile association</span></span>
- <span data-ttu-id="a2b91-231">
international driving permit</span><span class="sxs-lookup"><span data-stu-id="a2b91-231">international driving permit</span></span>
- <span data-ttu-id="a2b91-232">driverlicence</span><span class="sxs-lookup"><span data-stu-id="a2b91-232">DriverLicence</span></span>
- <span data-ttu-id="a2b91-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a2b91-233">DriverLicences</span></span>
- <span data-ttu-id="a2b91-234">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-234">Driver Lic</span></span>
- <span data-ttu-id="a2b91-235">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-235">Driver Licence</span></span>
- <span data-ttu-id="a2b91-236">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-236">Driver Licences</span></span>
- <span data-ttu-id="a2b91-237">driverslic</span><span class="sxs-lookup"><span data-stu-id="a2b91-237">DriversLic</span></span>
- <span data-ttu-id="a2b91-238">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-238">DriversLicence</span></span>
- <span data-ttu-id="a2b91-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a2b91-239">DriversLicences</span></span>
- <span data-ttu-id="a2b91-240">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-240">Drivers Lic</span></span>
- <span data-ttu-id="a2b91-241">ドライバー lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-241">Drivers Lics</span></span>
- <span data-ttu-id="a2b91-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-242">Drivers Licence</span></span>
- <span data-ttu-id="a2b91-243">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-243">Drivers Licences</span></span>
- <span data-ttu-id="a2b91-244">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-244">Driver'Lic</span></span>
- <span data-ttu-id="a2b91-245">driver' lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-245">Driver'Lics</span></span>
- <span data-ttu-id="a2b91-246">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-246">Driver'Licence</span></span>
- <span data-ttu-id="a2b91-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a2b91-247">Driver'Licences</span></span>
- <span data-ttu-id="a2b91-248">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-248">Driver' Lic</span></span>
- <span data-ttu-id="a2b91-249">ドライバー ' lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-249">Driver' Lics</span></span>
- <span data-ttu-id="a2b91-250">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-250">Driver' Licence</span></span>
- <span data-ttu-id="a2b91-251">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-251">Driver' Licences</span></span>
- <span data-ttu-id="a2b91-252">driver' slic</span><span class="sxs-lookup"><span data-stu-id="a2b91-252">Driver'sLic</span></span>
- <span data-ttu-id="a2b91-253">driver' slics</span><span class="sxs-lookup"><span data-stu-id="a2b91-253">Driver'sLics</span></span>
- <span data-ttu-id="a2b91-254">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="a2b91-254">Driver'sLicence</span></span>
- <span data-ttu-id="a2b91-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a2b91-255">Driver'sLicences</span></span>
- <span data-ttu-id="a2b91-256">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-256">Driver's Lic</span></span>
- <span data-ttu-id="a2b91-257">ドライバーの lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-257">Driver's Lics</span></span>
- <span data-ttu-id="a2b91-258">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-258">Driver's Licence</span></span>
- <span data-ttu-id="a2b91-259">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-259">Driver's Licences</span></span>
- <span data-ttu-id="a2b91-260">driverlic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-260">DriverLic#</span></span>
- <span data-ttu-id="a2b91-261">driverlics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-261">DriverLics#</span></span>
- <span data-ttu-id="a2b91-262">driverlicence #</span><span class="sxs-lookup"><span data-stu-id="a2b91-262">DriverLicence#</span></span>
- <span data-ttu-id="a2b91-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a2b91-263">DriverLicences#</span></span>
- <span data-ttu-id="a2b91-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a2b91-264">Driver Lic#</span></span>
- <span data-ttu-id="a2b91-265">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-265">Driver Lics#</span></span>
- <span data-ttu-id="a2b91-266">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-266">Driver Licence#</span></span>
- <span data-ttu-id="a2b91-267">Driver ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-267">Driver Licences#</span></span>
- <span data-ttu-id="a2b91-268">driverslic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-268">DriversLic#</span></span>
- <span data-ttu-id="a2b91-269">driverslics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-269">DriversLics#</span></span>
- <span data-ttu-id="a2b91-270">のデモライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-270">DriversLicence#</span></span>
- <span data-ttu-id="a2b91-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a2b91-271">DriversLicences#</span></span>
- <span data-ttu-id="a2b91-272">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-272">Drivers Lic#</span></span>
- <span data-ttu-id="a2b91-273">ドライバー lics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-273">Drivers Lics#</span></span>
- <span data-ttu-id="a2b91-274">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-274">Drivers Licence#</span></span>
- <span data-ttu-id="a2b91-275">Drivers ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-275">Drivers Licences#</span></span>
- <span data-ttu-id="a2b91-276">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-276">Driver'Lic#</span></span>
- <span data-ttu-id="a2b91-277">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-277">Driver'Lics#</span></span>
- <span data-ttu-id="a2b91-278">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-278">Driver'Licence#</span></span>
- <span data-ttu-id="a2b91-279">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-279">Driver'Licences#</span></span>
- <span data-ttu-id="a2b91-280">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-280">Driver' Lic#</span></span>
- <span data-ttu-id="a2b91-281">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-281">Driver' Lics#</span></span>
- <span data-ttu-id="a2b91-282">ドライバー ' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-282">Driver' Licence#</span></span>
- <span data-ttu-id="a2b91-283">ドライバー ' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-283">Driver' Licences#</span></span>
- <span data-ttu-id="a2b91-284">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-284">Driver'sLic#</span></span>
- <span data-ttu-id="a2b91-285">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-285">Driver'sLics#</span></span>
- <span data-ttu-id="a2b91-286">ドライバ ' スライスの持続性 #</span><span class="sxs-lookup"><span data-stu-id="a2b91-286">Driver'sLicence#</span></span>
- <span data-ttu-id="a2b91-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a2b91-287">Driver'sLicences#</span></span>
- <span data-ttu-id="a2b91-288">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-288">Driver's Lic#</span></span>
- <span data-ttu-id="a2b91-289">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-289">Driver's Lics#</span></span>
- <span data-ttu-id="a2b91-290">ドライバーのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-290">Driver's Licence#</span></span>
- <span data-ttu-id="a2b91-291">ドライバーのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-291">Driver's Licences#</span></span> 

#### <a name="keywordaustraliadriverslicensenumberexclusions"></a><span data-ttu-id="a2b91-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a2b91-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="a2b91-293">aaa</span><span class="sxs-lookup"><span data-stu-id="a2b91-293">aaa</span></span>
- <span data-ttu-id="a2b91-294">driverlicense</span><span class="sxs-lookup"><span data-stu-id="a2b91-294">DriverLicense</span></span>
- <span data-ttu-id="a2b91-295">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="a2b91-295">DriverLicenses</span></span>
- <span data-ttu-id="a2b91-296">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-296">Driver License</span></span>
- <span data-ttu-id="a2b91-297">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-297">Driver Licenses</span></span>
- <span data-ttu-id="a2b91-298">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="a2b91-298">DriversLicense</span></span>
- <span data-ttu-id="a2b91-299">このライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-299">DriversLicenses</span></span>
- <span data-ttu-id="a2b91-300">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-300">Drivers License</span></span>
- <span data-ttu-id="a2b91-301">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-301">Drivers Licenses</span></span>
- <span data-ttu-id="a2b91-302">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-302">Driver'License</span></span>
- <span data-ttu-id="a2b91-303">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-303">Driver'Licenses</span></span>
- <span data-ttu-id="a2b91-304">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-304">Driver' License</span></span>
- <span data-ttu-id="a2b91-305">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-305">Driver' Licenses</span></span>
- <span data-ttu-id="a2b91-306">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-306">Driver'sLicense</span></span>
- <span data-ttu-id="a2b91-307">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-307">Driver'sLicenses</span></span>
- <span data-ttu-id="a2b91-308">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a2b91-308">Driver's License</span></span>
- <span data-ttu-id="a2b91-309">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-309">Driver's Licenses</span></span>
- <span data-ttu-id="a2b91-310">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="a2b91-310">DriverLicense#</span></span>
- <span data-ttu-id="a2b91-311">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="a2b91-311">DriverLicenses#</span></span>
- <span data-ttu-id="a2b91-312">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-312">Driver License#</span></span>
- <span data-ttu-id="a2b91-313">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-313">Driver Licenses#</span></span>
- <span data-ttu-id="a2b91-314">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-314">DriversLicense#</span></span>
- <span data-ttu-id="a2b91-315">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-315">DriversLicenses#</span></span>
- <span data-ttu-id="a2b91-316">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-316">Drivers License#</span></span>
- <span data-ttu-id="a2b91-317">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-317">Drivers Licenses#</span></span>
- <span data-ttu-id="a2b91-318">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-318">Driver'License#</span></span>
- <span data-ttu-id="a2b91-319">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-319">Driver'Licenses#</span></span>
- <span data-ttu-id="a2b91-320">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-320">Driver' License#</span></span>
- <span data-ttu-id="a2b91-321">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-321">Driver' Licenses#</span></span>
- <span data-ttu-id="a2b91-322">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-322">Driver'sLicense#</span></span>
- <span data-ttu-id="a2b91-323">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="a2b91-324">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-324">Driver's License#</span></span>
- <span data-ttu-id="a2b91-325">

Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="a2b91-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="a2b91-326">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-327">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-327">Format</span></span>

<span data-ttu-id="a2b91-328">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-329">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-329">Pattern</span></span>

<span data-ttu-id="a2b91-330">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-330">10-11 digits:</span></span>
- <span data-ttu-id="a2b91-331">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="a2b91-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="a2b91-332">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a2b91-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="a2b91-333">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="a2b91-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="a2b91-334">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-335">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-335">Checksum</span></span>

<span data-ttu-id="a2b91-336">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-337">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-337">Definition</span></span>

<span data-ttu-id="a2b91-338">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-339">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-340">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="a2b91-341">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-341">The checksum passes.</span></span>

<span data-ttu-id="a2b91-342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-343">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-344">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-344">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-345">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-345">Keywords</span></span>

#### <a name="keywordaustraliamedicalaccountnumber"></a><span data-ttu-id="a2b91-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="a2b91-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="a2b91-347">bank account details</span></span>
- <span data-ttu-id="a2b91-348">
medicare payments</span><span class="sxs-lookup"><span data-stu-id="a2b91-348">medicare payments</span></span>
- <span data-ttu-id="a2b91-349">
mortgage account</span><span class="sxs-lookup"><span data-stu-id="a2b91-349">mortgage account</span></span>
- <span data-ttu-id="a2b91-350">
bank payments</span><span class="sxs-lookup"><span data-stu-id="a2b91-350">bank payments</span></span>
- <span data-ttu-id="a2b91-351">
information branch</span><span class="sxs-lookup"><span data-stu-id="a2b91-351">information branch</span></span>
- <span data-ttu-id="a2b91-352">
credit card loan</span><span class="sxs-lookup"><span data-stu-id="a2b91-352">credit card loan</span></span>
- <span data-ttu-id="a2b91-353">
department of human services</span><span class="sxs-lookup"><span data-stu-id="a2b91-353">department of human services</span></span>
- <span data-ttu-id="a2b91-354">ローカルサービス</span><span class="sxs-lookup"><span data-stu-id="a2b91-354">local service</span></span>
- <span data-ttu-id="a2b91-355">

medicare</span><span class="sxs-lookup"><span data-stu-id="a2b91-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="a2b91-356">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-357">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-357">Format</span></span>

<span data-ttu-id="a2b91-358">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-359">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-359">Pattern</span></span>

<span data-ttu-id="a2b91-360">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-361">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-361">Checksum</span></span>

<span data-ttu-id="a2b91-362">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-363">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-363">Definition</span></span>

<span data-ttu-id="a2b91-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-365">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-366">Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-367">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-367">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a2b91-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-368">Keyword_passport</span></span>

- <span data-ttu-id="a2b91-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-369">Passport Number</span></span>
- <span data-ttu-id="a2b91-370">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a2b91-370">Passport No</span></span>
- <span data-ttu-id="a2b91-371">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-371">Passport #</span></span>
- <span data-ttu-id="a2b91-372">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-372">Passport#</span></span>
- <span data-ttu-id="a2b91-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="a2b91-373">PassportID</span></span>
- <span data-ttu-id="a2b91-374">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a2b91-374">Passportno</span></span>
- <span data-ttu-id="a2b91-375">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-375">passportnumber</span></span>
- <span data-ttu-id="a2b91-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="a2b91-376">パスポート</span></span>
- <span data-ttu-id="a2b91-377">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-377">パスポート番号</span></span>
- <span data-ttu-id="a2b91-378">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-378">パスポートのNum</span></span>
- <span data-ttu-id="a2b91-379">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-379">パスポート ＃</span></span> 
- <span data-ttu-id="a2b91-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a2b91-380">Numéro de passeport</span></span>
- <span data-ttu-id="a2b91-381">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a2b91-381">Passeport n °</span></span>
- <span data-ttu-id="a2b91-382">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a2b91-382">Passeport Non</span></span>
- <span data-ttu-id="a2b91-383">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-383">Passeport #</span></span>
- <span data-ttu-id="a2b91-384">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-384">Passeport#</span></span>
- <span data-ttu-id="a2b91-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a2b91-385">PasseportNon</span></span>
- <span data-ttu-id="a2b91-386">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="a2b91-386">Passeportn °</span></span>

#### <a name="keywordaustraliapassportnumber"></a><span data-ttu-id="a2b91-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="a2b91-388">passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-388">passport</span></span>
- <span data-ttu-id="a2b91-389">
passport details</span><span class="sxs-lookup"><span data-stu-id="a2b91-389">passport details</span></span>
- <span data-ttu-id="a2b91-390">
immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a2b91-390">immigration and citizenship</span></span>
- <span data-ttu-id="a2b91-391">
commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="a2b91-391">commonwealth of australia</span></span>
- <span data-ttu-id="a2b91-392">
department of immigration</span><span class="sxs-lookup"><span data-stu-id="a2b91-392">department of immigration</span></span>
- <span data-ttu-id="a2b91-393">
residential address</span><span class="sxs-lookup"><span data-stu-id="a2b91-393">residential address</span></span>
- <span data-ttu-id="a2b91-394">
department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="a2b91-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="a2b91-395">visa
</span><span class="sxs-lookup"><span data-stu-id="a2b91-395">visa</span></span>
- <span data-ttu-id="a2b91-396">
national identity card</span><span class="sxs-lookup"><span data-stu-id="a2b91-396">national identity card</span></span>
- <span data-ttu-id="a2b91-397">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-397">passport number</span></span>
- <span data-ttu-id="a2b91-398">
travel document</span><span class="sxs-lookup"><span data-stu-id="a2b91-398">travel document</span></span>
- <span data-ttu-id="a2b91-399">

issuing authority</span><span class="sxs-lookup"><span data-stu-id="a2b91-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="a2b91-400">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-401">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-401">Format</span></span>

<span data-ttu-id="a2b91-402">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-403">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-403">Pattern</span></span>

<span data-ttu-id="a2b91-404">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="a2b91-405">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-405">Three digits</span></span> 
- <span data-ttu-id="a2b91-406">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-406">An optional space</span></span> 
- <span data-ttu-id="a2b91-407">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-407">Three digits</span></span> 
- <span data-ttu-id="a2b91-408">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-408">An optional space</span></span> 
- <span data-ttu-id="a2b91-409">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="a2b91-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-410">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-410">Checksum</span></span>

<span data-ttu-id="a2b91-411">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-412">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-412">Definition</span></span>

<span data-ttu-id="a2b91-413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-414">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-415">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="a2b91-416">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-416">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-417">Keywords</span></span>

#### <a name="keywordaustraliataxfilenumber"></a><span data-ttu-id="a2b91-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="a2b91-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="a2b91-419">australian business number</span></span>
- <span data-ttu-id="a2b91-420">
marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="a2b91-420">marginal tax rate</span></span>
- <span data-ttu-id="a2b91-421">
medicare levy</span><span class="sxs-lookup"><span data-stu-id="a2b91-421">medicare levy</span></span>
- <span data-ttu-id="a2b91-422">
portfolio number</span><span class="sxs-lookup"><span data-stu-id="a2b91-422">portfolio number</span></span>
- <span data-ttu-id="a2b91-423">
service veterans</span><span class="sxs-lookup"><span data-stu-id="a2b91-423">service veterans</span></span>
- <span data-ttu-id="a2b91-424">
withholding tax</span><span class="sxs-lookup"><span data-stu-id="a2b91-424">withholding tax</span></span>
- <span data-ttu-id="a2b91-425">
individual tax return</span><span class="sxs-lookup"><span data-stu-id="a2b91-425">individual tax return</span></span>
- <span data-ttu-id="a2b91-426">

tax file number</span><span class="sxs-lookup"><span data-stu-id="a2b91-426">tax file number</span></span>

#### <a name="keywordnumberexclusions"></a><span data-ttu-id="a2b91-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="a2b91-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="a2b91-428">00000000</span><span class="sxs-lookup"><span data-stu-id="a2b91-428">00000000</span></span>
- <span data-ttu-id="a2b91-429">11111111</span><span class="sxs-lookup"><span data-stu-id="a2b91-429">11111111</span></span>
- <span data-ttu-id="a2b91-430">22222222</span><span class="sxs-lookup"><span data-stu-id="a2b91-430">22222222</span></span>
- <span data-ttu-id="a2b91-431">33333333</span><span class="sxs-lookup"><span data-stu-id="a2b91-431">33333333</span></span>
- <span data-ttu-id="a2b91-432">44444444</span><span class="sxs-lookup"><span data-stu-id="a2b91-432">44444444</span></span>
- <span data-ttu-id="a2b91-433">55555555</span><span class="sxs-lookup"><span data-stu-id="a2b91-433">55555555</span></span>
- <span data-ttu-id="a2b91-434">66666666</span><span class="sxs-lookup"><span data-stu-id="a2b91-434">66666666</span></span>
- <span data-ttu-id="a2b91-435">77777777</span><span class="sxs-lookup"><span data-stu-id="a2b91-435">77777777</span></span>
- <span data-ttu-id="a2b91-436">88888888</span><span class="sxs-lookup"><span data-stu-id="a2b91-436">88888888</span></span>
- <span data-ttu-id="a2b91-437">99999999</span><span class="sxs-lookup"><span data-stu-id="a2b91-437">99999999</span></span>
- <span data-ttu-id="a2b91-438">000000000</span><span class="sxs-lookup"><span data-stu-id="a2b91-438">000000000</span></span>
- <span data-ttu-id="a2b91-439">111111111</span><span class="sxs-lookup"><span data-stu-id="a2b91-439">111111111</span></span>
- <span data-ttu-id="a2b91-440">222222222</span><span class="sxs-lookup"><span data-stu-id="a2b91-440">222222222</span></span>
- <span data-ttu-id="a2b91-441">333333333</span><span class="sxs-lookup"><span data-stu-id="a2b91-441">333333333</span></span>
- <span data-ttu-id="a2b91-442">444444444</span><span class="sxs-lookup"><span data-stu-id="a2b91-442">444444444</span></span>
- <span data-ttu-id="a2b91-443">555555555</span><span class="sxs-lookup"><span data-stu-id="a2b91-443">555555555</span></span>
- <span data-ttu-id="a2b91-444">666666666</span><span class="sxs-lookup"><span data-stu-id="a2b91-444">666666666</span></span>
- <span data-ttu-id="a2b91-445">777777777</span><span class="sxs-lookup"><span data-stu-id="a2b91-445">777777777</span></span>
- <span data-ttu-id="a2b91-446">888888888</span><span class="sxs-lookup"><span data-stu-id="a2b91-446">888888888</span></span>
- <span data-ttu-id="a2b91-447">999999999</span><span class="sxs-lookup"><span data-stu-id="a2b91-447">999999999</span></span>
- <span data-ttu-id="a2b91-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="a2b91-448">0000000000</span></span>
- <span data-ttu-id="a2b91-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="a2b91-449">1111111111</span></span>
- <span data-ttu-id="a2b91-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="a2b91-450">2222222222</span></span>
- <span data-ttu-id="a2b91-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="a2b91-451">3333333333</span></span>
- <span data-ttu-id="a2b91-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="a2b91-452">4444444444</span></span>
- <span data-ttu-id="a2b91-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="a2b91-453">5555555555</span></span>
- <span data-ttu-id="a2b91-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="a2b91-454">6666666666</span></span>
- <span data-ttu-id="a2b91-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="a2b91-455">7777777777</span></span>
- <span data-ttu-id="a2b91-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="a2b91-456">8888888888</span></span>
- <span data-ttu-id="a2b91-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="a2b91-457">9999999999</span></span>
   
## <a name="belgium-national-number"></a><span data-ttu-id="a2b91-458">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-458">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-459">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-459">Format</span></span>

<span data-ttu-id="a2b91-460">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-460">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-461">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-461">Pattern</span></span>

<span data-ttu-id="a2b91-462">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-462">11 digits plus delimiters:</span></span>
- <span data-ttu-id="a2b91-463">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="a2b91-463">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="a2b91-464">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-464">A hyphen</span></span> 
- <span data-ttu-id="a2b91-465">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="a2b91-465">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="a2b91-466">ピリオド</span><span class="sxs-lookup"><span data-stu-id="a2b91-466">A period</span></span> 
- <span data-ttu-id="a2b91-467">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-467">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-468">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-468">Checksum</span></span>

<span data-ttu-id="a2b91-469">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-469">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-470">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-470">Definition</span></span>

<span data-ttu-id="a2b91-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-472">関数 Func_belgium_national_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-472">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-473">Keyword_belgium_national_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-473">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="a2b91-474">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-474">The checksum passes.</span></span>

```
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-475">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-475">Keywords</span></span>

#### <a name="keywordbelgiumnationalnumber"></a><span data-ttu-id="a2b91-476">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-476">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="a2b91-477">Identity</span><span class="sxs-lookup"><span data-stu-id="a2b91-477">Identity</span></span>
- <span data-ttu-id="a2b91-478">Registration</span><span class="sxs-lookup"><span data-stu-id="a2b91-478">Registration</span></span>
- <span data-ttu-id="a2b91-479">Identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-479">Identification</span></span> 
- <span data-ttu-id="a2b91-480">ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-480">ID</span></span> 
- <span data-ttu-id="a2b91-481">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="a2b91-481">Identiteitskaart</span></span>
- <span data-ttu-id="a2b91-482">Registratie nummer 
</span><span class="sxs-lookup"><span data-stu-id="a2b91-482">Registratie nummer</span></span> 
- <span data-ttu-id="a2b91-483">Identificatie nummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-483">Identificatie nummer</span></span> 
- <span data-ttu-id="a2b91-484">Identiteit</span><span class="sxs-lookup"><span data-stu-id="a2b91-484">Identiteit</span></span>
- <span data-ttu-id="a2b91-485">Registratie</span><span class="sxs-lookup"><span data-stu-id="a2b91-485">Registratie</span></span>
- <span data-ttu-id="a2b91-486">Identificatie

</span><span class="sxs-lookup"><span data-stu-id="a2b91-486">Identificatie</span></span> 
- <span data-ttu-id="a2b91-487">Carte d’identité
</span><span class="sxs-lookup"><span data-stu-id="a2b91-487">Carte d’identité</span></span> 
- <span data-ttu-id="a2b91-488">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="a2b91-488">numéro d'immatriculation</span></span>
- <span data-ttu-id="a2b91-489">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-489">numéro d'identification</span></span>
- <span data-ttu-id="a2b91-490">
identité
</span><span class="sxs-lookup"><span data-stu-id="a2b91-490">identité</span></span> 
- <span data-ttu-id="a2b91-491">inscription
</span><span class="sxs-lookup"><span data-stu-id="a2b91-491">inscription</span></span> 
- <span data-ttu-id="a2b91-492">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a2b91-492">Identifikation</span></span>
- <span data-ttu-id="a2b91-493">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="a2b91-493">Identifizierung</span></span>
- <span data-ttu-id="a2b91-494">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-494">Identifikationsnummer</span></span>
- <span data-ttu-id="a2b91-495">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a2b91-495">Personalausweis</span></span>
- <span data-ttu-id="a2b91-496">Registrierung</span><span class="sxs-lookup"><span data-stu-id="a2b91-496">Registrierung</span></span>
- <span data-ttu-id="a2b91-497">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-497">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="a2b91-498">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-498">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-499">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-499">Format</span></span>

<span data-ttu-id="a2b91-500">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-500">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-501">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-501">Pattern</span></span>

<span data-ttu-id="a2b91-502">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-502">Formatted:</span></span>
- <span data-ttu-id="a2b91-503">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-503">Three digits</span></span> 
- <span data-ttu-id="a2b91-504">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-504">A period</span></span> 
- <span data-ttu-id="a2b91-505">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-505">Three digits</span></span> 
- <span data-ttu-id="a2b91-506">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-506">A period</span></span> 
- <span data-ttu-id="a2b91-507">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-507">Three digits</span></span> 
- <span data-ttu-id="a2b91-508">ハイフン</span><span class="sxs-lookup"><span data-stu-id="a2b91-508">A hyphen</span></span> 
- <span data-ttu-id="a2b91-509">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-509">Two digits which are check digits</span></span>

<span data-ttu-id="a2b91-510">書式設定なし:</span><span class="sxs-lookup"><span data-stu-id="a2b91-510">Unformatted:</span></span>
- <span data-ttu-id="a2b91-511">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="a2b91-511">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-512">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-512">Checksum</span></span>

<span data-ttu-id="a2b91-513">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-514">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-514">Definition</span></span>

<span data-ttu-id="a2b91-515">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-515">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-516">関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-516">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-517">Keyword_brazil_cpf のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-517">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="a2b91-518">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-518">The checksum passes.</span></span>

<span data-ttu-id="a2b91-519">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-519">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-520">関数 Func_brazil_cpf がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-520">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-521">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-521">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-522">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-522">Keywords</span></span>

#### <a name="keywordbrazilcpf"></a><span data-ttu-id="a2b91-523">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="a2b91-523">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="a2b91-524">CPF</span><span class="sxs-lookup"><span data-stu-id="a2b91-524">CPF</span></span>
- <span data-ttu-id="a2b91-525">Identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-525">Identification</span></span>
- <span data-ttu-id="a2b91-526">Registration</span><span class="sxs-lookup"><span data-stu-id="a2b91-526">Registration</span></span>
- <span data-ttu-id="a2b91-527">Revenue</span><span class="sxs-lookup"><span data-stu-id="a2b91-527">Revenue</span></span>
- <span data-ttu-id="a2b91-528">Cadastro de Pessoas Físicas
</span><span class="sxs-lookup"><span data-stu-id="a2b91-528">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="a2b91-529">Imposto
</span><span class="sxs-lookup"><span data-stu-id="a2b91-529">Imposto</span></span> 
- <span data-ttu-id="a2b91-530">Identificação
</span><span class="sxs-lookup"><span data-stu-id="a2b91-530">Identificação</span></span> 
- <span data-ttu-id="a2b91-531">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="a2b91-531">Inscrição</span></span> 
- <span data-ttu-id="a2b91-532">Receita

</span><span class="sxs-lookup"><span data-stu-id="a2b91-532">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="a2b91-533">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="a2b91-533">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-534">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-534">Format</span></span>

<span data-ttu-id="a2b91-535">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-535">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-536">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-536">Pattern</span></span>
<span data-ttu-id="a2b91-537">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-537">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="a2b91-538">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-538">Two digits</span></span> 
- <span data-ttu-id="a2b91-539">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-539">A period</span></span> 
- <span data-ttu-id="a2b91-540">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-540">Three digits</span></span> 
- <span data-ttu-id="a2b91-541">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-541">A period</span></span> 
- <span data-ttu-id="a2b91-542">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="a2b91-542">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="a2b91-543">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-543">A forward slash</span></span> 
- <span data-ttu-id="a2b91-544">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="a2b91-544">Four-digit branch number</span></span> 
- <span data-ttu-id="a2b91-545">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-545">A hyphen</span></span> 
- <span data-ttu-id="a2b91-546">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-546">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-547">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-547">Checksum</span></span>

<span data-ttu-id="a2b91-548">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-548">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-549">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-549">Definition</span></span>

<span data-ttu-id="a2b91-550">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-550">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-551">関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-551">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-552">Keyword_brazil_cnpj のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-552">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="a2b91-553">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-553">The checksum passes.</span></span>

<span data-ttu-id="a2b91-554">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-554">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-555">関数 Func_brazil_cnpj がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-555">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-556">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-556">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-557">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-557">Keywords</span></span>

#### <a name="keywordbrazilcnpj"></a><span data-ttu-id="a2b91-558">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="a2b91-558">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="a2b91-559">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="a2b91-559">CNPJ</span></span> 
- <span data-ttu-id="a2b91-560">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="a2b91-560">CNPJ/MF</span></span> 
- <span data-ttu-id="a2b91-561">CNPJ-MF
</span><span class="sxs-lookup"><span data-stu-id="a2b91-561">CNPJ-MF</span></span> 
- <span data-ttu-id="a2b91-562">National Registry of Legal Entities
</span><span class="sxs-lookup"><span data-stu-id="a2b91-562">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="a2b91-563">Taxpayers Registry
</span><span class="sxs-lookup"><span data-stu-id="a2b91-563">Taxpayers Registry</span></span> 
- <span data-ttu-id="a2b91-564">Legal entity
</span><span class="sxs-lookup"><span data-stu-id="a2b91-564">Legal entity</span></span> 
- <span data-ttu-id="a2b91-565">Legal entities
</span><span class="sxs-lookup"><span data-stu-id="a2b91-565">Legal entities</span></span> 
- <span data-ttu-id="a2b91-566">Registration Status
</span><span class="sxs-lookup"><span data-stu-id="a2b91-566">Registration Status</span></span> 
- <span data-ttu-id="a2b91-567">Business
</span><span class="sxs-lookup"><span data-stu-id="a2b91-567">Business</span></span> 
- <span data-ttu-id="a2b91-568">Company</span><span class="sxs-lookup"><span data-stu-id="a2b91-568">Company</span></span>
- <span data-ttu-id="a2b91-569">CNPJ
</span><span class="sxs-lookup"><span data-stu-id="a2b91-569">CNPJ</span></span> 
- <span data-ttu-id="a2b91-570">Cadastro Nacional da Pessoa Jurídica
</span><span class="sxs-lookup"><span data-stu-id="a2b91-570">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="a2b91-571">Cadastro Geral de Contribuintes
</span><span class="sxs-lookup"><span data-stu-id="a2b91-571">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="a2b91-572">CGC
</span><span class="sxs-lookup"><span data-stu-id="a2b91-572">CGC</span></span> 
- <span data-ttu-id="a2b91-573">Pessoa jurídica
</span><span class="sxs-lookup"><span data-stu-id="a2b91-573">Pessoa jurídica</span></span> 
- <span data-ttu-id="a2b91-574">Pessoas jurídicas
</span><span class="sxs-lookup"><span data-stu-id="a2b91-574">Pessoas jurídicas</span></span> 
- <span data-ttu-id="a2b91-575">Situação cadastral
</span><span class="sxs-lookup"><span data-stu-id="a2b91-575">Situação cadastral</span></span> 
- <span data-ttu-id="a2b91-576">Inscrição
</span><span class="sxs-lookup"><span data-stu-id="a2b91-576">Inscrição</span></span> 
- <span data-ttu-id="a2b91-577">Empresa
</span><span class="sxs-lookup"><span data-stu-id="a2b91-577">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="a2b91-578">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="a2b91-578">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-579">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-579">Format</span></span>

<span data-ttu-id="a2b91-580">Registro geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-580">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="a2b91-581">Registro de 識別子 dade (ric) (新しい形式):11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-581">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-582">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-582">Pattern</span></span>

<span data-ttu-id="a2b91-583">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="a2b91-583">Registro Geral (old format):</span></span>
- <span data-ttu-id="a2b91-584">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-584">Two digits</span></span> 
- <span data-ttu-id="a2b91-585">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-585">A period</span></span> 
- <span data-ttu-id="a2b91-586">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-586">Three digits</span></span> 
- <span data-ttu-id="a2b91-587">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-587">A period</span></span> 
- <span data-ttu-id="a2b91-588">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-588">Three digits</span></span> 
- <span data-ttu-id="a2b91-589">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-589">A hyphen</span></span> 
- <span data-ttu-id="a2b91-590">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-590">One digit which is a check digit</span></span>

<span data-ttu-id="a2b91-591">Registro de 識別子 dade (ric) (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="a2b91-591">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="a2b91-592">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-592">10 digits</span></span> 
- <span data-ttu-id="a2b91-593">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-593">A hyphen</span></span> 
- <span data-ttu-id="a2b91-594">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-594">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-595">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-595">Checksum</span></span>

<span data-ttu-id="a2b91-596">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-596">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-597">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-597">Definition</span></span>

<span data-ttu-id="a2b91-598">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-598">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-599">関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-599">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-600">Keyword_brazil_rg のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-600">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="a2b91-601">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-601">The checksum passes.</span></span>

<span data-ttu-id="a2b91-602">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-602">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-603">関数 Func_brazil_rg がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-603">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-604">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-604">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-605">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-605">Keywords</span></span>

#### <a name="keywordbrazilrg"></a><span data-ttu-id="a2b91-606">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="a2b91-606">Keyword_brazil_rg</span></span>

<span data-ttu-id="a2b91-607">Cédula de 識別子 dade id カード national id número de rregistro registro de i識別子 dade registro geral このキーワードは大文字と小文字を区別します) ric (このキーワードは大文字と小文字を区別します)</span><span class="sxs-lookup"><span data-stu-id="a2b91-607">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="a2b91-608">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-608">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-609">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-609">Format</span></span>

<span data-ttu-id="a2b91-610">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-610">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-611">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-611">Pattern</span></span>

<span data-ttu-id="a2b91-612">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="a2b91-612">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="a2b91-613">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="a2b91-613">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="a2b91-614">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-614">Five digits</span></span> 
- <span data-ttu-id="a2b91-615">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-615">A hyphen</span></span> 
- <span data-ttu-id="a2b91-616">3桁の数字または</span><span class="sxs-lookup"><span data-stu-id="a2b91-616">Three digits OR</span></span>
- <span data-ttu-id="a2b91-617">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="a2b91-617">A zero "0"</span></span> 
- <span data-ttu-id="a2b91-618">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-618">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-619">Checksum</span></span>

<span data-ttu-id="a2b91-620">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-620">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-621">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-621">Definition</span></span>

<span data-ttu-id="a2b91-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-622">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-623">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-623">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-624">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-624">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="a2b91-625">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-625">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="a2b91-626">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-627">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-627">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-628">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-628">A keyword from Keyword_canada_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-629">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-629">Keywords</span></span>

#### <a name="keywordcanadabankaccountnumber"></a><span data-ttu-id="a2b91-630">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-630">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="a2b91-631">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="a2b91-631">canada savings bonds</span></span>
- <span data-ttu-id="a2b91-632">
canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="a2b91-632">canada revenue agency</span></span>
- <span data-ttu-id="a2b91-633">
canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="a2b91-633">canadian financial institution</span></span>
- <span data-ttu-id="a2b91-634">
direct deposit form</span><span class="sxs-lookup"><span data-stu-id="a2b91-634">direct deposit form</span></span>
- <span data-ttu-id="a2b91-635">
canadian citizen</span><span class="sxs-lookup"><span data-stu-id="a2b91-635">canadian citizen</span></span>
- <span data-ttu-id="a2b91-636">
legal representative</span><span class="sxs-lookup"><span data-stu-id="a2b91-636">legal representative</span></span>
- <span data-ttu-id="a2b91-637">
notary public</span><span class="sxs-lookup"><span data-stu-id="a2b91-637">notary public</span></span>
- <span data-ttu-id="a2b91-638">
commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="a2b91-638">commissioner for oaths</span></span>
- <span data-ttu-id="a2b91-639">
child care benefit</span><span class="sxs-lookup"><span data-stu-id="a2b91-639">child care benefit</span></span>
- <span data-ttu-id="a2b91-640">
universal child care</span><span class="sxs-lookup"><span data-stu-id="a2b91-640">universal child care</span></span>
- <span data-ttu-id="a2b91-641">
canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a2b91-641">canada child tax benefit</span></span>
- <span data-ttu-id="a2b91-642">
income tax benefit</span><span class="sxs-lookup"><span data-stu-id="a2b91-642">income tax benefit</span></span>
- <span data-ttu-id="a2b91-643">
harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="a2b91-643">harmonized sales tax</span></span>
- <span data-ttu-id="a2b91-644">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a2b91-644">social insurance number</span></span>
- <span data-ttu-id="a2b91-645">
income tax refund</span><span class="sxs-lookup"><span data-stu-id="a2b91-645">income tax refund</span></span>
- <span data-ttu-id="a2b91-646">
child tax benefit</span><span class="sxs-lookup"><span data-stu-id="a2b91-646">child tax benefit</span></span>
- <span data-ttu-id="a2b91-647">
territorial payments</span><span class="sxs-lookup"><span data-stu-id="a2b91-647">territorial payments</span></span>
- <span data-ttu-id="a2b91-648">
institution number</span><span class="sxs-lookup"><span data-stu-id="a2b91-648">institution number</span></span>
- <span data-ttu-id="a2b91-649">
deposit request</span><span class="sxs-lookup"><span data-stu-id="a2b91-649">deposit request</span></span>
- <span data-ttu-id="a2b91-650">
banking information</span><span class="sxs-lookup"><span data-stu-id="a2b91-650">banking information</span></span>
- <span data-ttu-id="a2b91-651">

direct deposit</span><span class="sxs-lookup"><span data-stu-id="a2b91-651">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="a2b91-652">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-652">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-653">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-653">Format</span></span>

<span data-ttu-id="a2b91-654">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="a2b91-654">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-655">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-655">Pattern</span></span>

<span data-ttu-id="a2b91-656">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-656">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-657">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-657">Checksum</span></span>

<span data-ttu-id="a2b91-658">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-658">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-659">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-659">Definition</span></span>

<span data-ttu-id="a2b91-660">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-660">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-661">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-661">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-662">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-662">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a2b91-663">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-663">A keyword from Keyword_canada_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-664">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-664">Keywords</span></span>

#### <a name="keywordprovincenamedriverslicensename"></a><span data-ttu-id="a2b91-665">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a2b91-665">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="a2b91-666">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="a2b91-666">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="a2b91-667">
州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="a2b91-667">The province name, for example Alberta</span></span>

#### <a name="keywordcanadadriverslicense"></a><span data-ttu-id="a2b91-668">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a2b91-668">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="a2b91-669">DL</span><span class="sxs-lookup"><span data-stu-id="a2b91-669">DL</span></span>
- <span data-ttu-id="a2b91-670">DLS</span><span class="sxs-lookup"><span data-stu-id="a2b91-670">DLS</span></span>
- <span data-ttu-id="a2b91-671">CDL</span><span class="sxs-lookup"><span data-stu-id="a2b91-671">CDL</span></span>
- <span data-ttu-id="a2b91-672">cdls</span><span class="sxs-lookup"><span data-stu-id="a2b91-672">CDLS</span></span>
- <span data-ttu-id="a2b91-673">driverlic</span><span class="sxs-lookup"><span data-stu-id="a2b91-673">DriverLic</span></span>
- <span data-ttu-id="a2b91-674">driverlics</span><span class="sxs-lookup"><span data-stu-id="a2b91-674">DriverLics</span></span>
- <span data-ttu-id="a2b91-675">driverlicense</span><span class="sxs-lookup"><span data-stu-id="a2b91-675">DriverLicense</span></span>
- <span data-ttu-id="a2b91-676">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="a2b91-676">DriverLicenses</span></span>
- <span data-ttu-id="a2b91-677">driverlicence</span><span class="sxs-lookup"><span data-stu-id="a2b91-677">DriverLicence</span></span>
- <span data-ttu-id="a2b91-678">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="a2b91-678">DriverLicences</span></span>
- <span data-ttu-id="a2b91-679">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-679">Driver Lic</span></span>
- <span data-ttu-id="a2b91-680">ドライバー lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-680">Driver Lics</span></span>
- <span data-ttu-id="a2b91-681">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-681">Driver License</span></span>
- <span data-ttu-id="a2b91-682">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-682">Driver Licenses</span></span>
- <span data-ttu-id="a2b91-683">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-683">Driver Licence</span></span>
- <span data-ttu-id="a2b91-684">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-684">Driver Licences</span></span>
- <span data-ttu-id="a2b91-685">driverslic</span><span class="sxs-lookup"><span data-stu-id="a2b91-685">DriversLic</span></span>
- <span data-ttu-id="a2b91-686">driverslics</span><span class="sxs-lookup"><span data-stu-id="a2b91-686">DriversLics</span></span>
- <span data-ttu-id="a2b91-687">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-687">DriversLicence</span></span>
- <span data-ttu-id="a2b91-688">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="a2b91-688">DriversLicences</span></span>
- <span data-ttu-id="a2b91-689">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="a2b91-689">DriversLicense</span></span>
- <span data-ttu-id="a2b91-690">このライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-690">DriversLicenses</span></span>
- <span data-ttu-id="a2b91-691">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-691">Drivers Lic</span></span>
- <span data-ttu-id="a2b91-692">ドライバー lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-692">Drivers Lics</span></span>
- <span data-ttu-id="a2b91-693">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-693">Drivers License</span></span>
- <span data-ttu-id="a2b91-694">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-694">Drivers Licenses</span></span>
- <span data-ttu-id="a2b91-695">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-695">Drivers Licence</span></span>
- <span data-ttu-id="a2b91-696">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-696">Drivers Licences</span></span>
- <span data-ttu-id="a2b91-697">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-697">Driver'Lic</span></span>
- <span data-ttu-id="a2b91-698">driver' lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-698">Driver'Lics</span></span>
- <span data-ttu-id="a2b91-699">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-699">Driver'License</span></span>
- <span data-ttu-id="a2b91-700">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-700">Driver'Licenses</span></span>
- <span data-ttu-id="a2b91-701">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-701">Driver'Licence</span></span>
- <span data-ttu-id="a2b91-702">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="a2b91-702">Driver'Licences</span></span>
- <span data-ttu-id="a2b91-703">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-703">Driver' Lic</span></span>
- <span data-ttu-id="a2b91-704">ドライバー ' lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-704">Driver' Lics</span></span>
- <span data-ttu-id="a2b91-705">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-705">Driver' License</span></span>
- <span data-ttu-id="a2b91-706">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-706">Driver' Licenses</span></span>
- <span data-ttu-id="a2b91-707">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-707">Driver' Licence</span></span>
- <span data-ttu-id="a2b91-708">ドライバー ' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-708">Driver' Licences</span></span>
- <span data-ttu-id="a2b91-709">driver' slic</span><span class="sxs-lookup"><span data-stu-id="a2b91-709">Driver'sLic</span></span>
- <span data-ttu-id="a2b91-710">driver' slics</span><span class="sxs-lookup"><span data-stu-id="a2b91-710">Driver'sLics</span></span>
- <span data-ttu-id="a2b91-711">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-711">Driver'sLicense</span></span>
- <span data-ttu-id="a2b91-712">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-712">Driver'sLicenses</span></span>
- <span data-ttu-id="a2b91-713">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="a2b91-713">Driver'sLicence</span></span>
- <span data-ttu-id="a2b91-714">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="a2b91-714">Driver'sLicences</span></span>
- <span data-ttu-id="a2b91-715">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-715">Driver's Lic</span></span>
- <span data-ttu-id="a2b91-716">ドライバーの lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-716">Driver's Lics</span></span>
- <span data-ttu-id="a2b91-717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a2b91-717">Driver's License</span></span>
- <span data-ttu-id="a2b91-718">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-718">Driver's Licenses</span></span>
- <span data-ttu-id="a2b91-719">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-719">Driver's Licence</span></span>
- <span data-ttu-id="a2b91-720">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-720">Driver's Licences</span></span>
- <span data-ttu-id="a2b91-721">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="a2b91-721">Permis de Conduire</span></span>
- <span data-ttu-id="a2b91-722">id</span><span class="sxs-lookup"><span data-stu-id="a2b91-722">id</span></span>
- <span data-ttu-id="a2b91-723">rid</span><span class="sxs-lookup"><span data-stu-id="a2b91-723">ids</span></span>
- <span data-ttu-id="a2b91-724">
idcard number</span><span class="sxs-lookup"><span data-stu-id="a2b91-724">idcard number</span></span>
- <span data-ttu-id="a2b91-725">
idcard numbers</span><span class="sxs-lookup"><span data-stu-id="a2b91-725">idcard numbers</span></span>
- <span data-ttu-id="a2b91-726">
idcard #</span><span class="sxs-lookup"><span data-stu-id="a2b91-726">idcard #</span></span>
- <span data-ttu-id="a2b91-727">
idcard #s</span><span class="sxs-lookup"><span data-stu-id="a2b91-727">idcard #s</span></span>
- <span data-ttu-id="a2b91-728">idcard カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-728">idcard card</span></span>
- <span data-ttu-id="a2b91-729">idcard カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-729">idcard cards</span></span>
- <span data-ttu-id="a2b91-730">idcard</span><span class="sxs-lookup"><span data-stu-id="a2b91-730">idcard</span></span>
- <span data-ttu-id="a2b91-731">identification number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-731">identification number</span></span>
- <span data-ttu-id="a2b91-732">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-732">identification numbers</span></span>
- <span data-ttu-id="a2b91-733">identification #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-733">identification #</span></span>
- <span data-ttu-id="a2b91-734">
identification #s</span><span class="sxs-lookup"><span data-stu-id="a2b91-734">identification #s</span></span>
- <span data-ttu-id="a2b91-735">識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-735">identification card</span></span>
- <span data-ttu-id="a2b91-736">識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-736">identification cards</span></span>
- <span data-ttu-id="a2b91-737">
identification
</span><span class="sxs-lookup"><span data-stu-id="a2b91-737">identification</span></span> 
- <span data-ttu-id="a2b91-738">DL#</span><span class="sxs-lookup"><span data-stu-id="a2b91-738">DL#</span></span>
- <span data-ttu-id="a2b91-739">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-739">DLS#</span></span> 
- <span data-ttu-id="a2b91-740">CDL#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-740">CDL#</span></span> 
- <span data-ttu-id="a2b91-741">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-741">CDLS#</span></span> 
- <span data-ttu-id="a2b91-742">driverlic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-742">DriverLic#</span></span> 
- <span data-ttu-id="a2b91-743">driverlics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-743">DriverLics#</span></span> 
- <span data-ttu-id="a2b91-744">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="a2b91-744">DriverLicense#</span></span> 
- <span data-ttu-id="a2b91-745">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="a2b91-745">DriverLicenses#</span></span> 
- <span data-ttu-id="a2b91-746">driverlicence #</span><span class="sxs-lookup"><span data-stu-id="a2b91-746">DriverLicence#</span></span> 
- <span data-ttu-id="a2b91-747">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="a2b91-747">DriverLicences#</span></span> 
- <span data-ttu-id="a2b91-748">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a2b91-748">Driver Lic#</span></span>
- <span data-ttu-id="a2b91-749">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-749">Driver Lics#</span></span> 
- <span data-ttu-id="a2b91-750">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-750">Driver License#</span></span> 
- <span data-ttu-id="a2b91-751">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-751">Driver Licenses#</span></span> 
- <span data-ttu-id="a2b91-752">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-752">Driver License#</span></span> 
- <span data-ttu-id="a2b91-753">Driver ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-753">Driver Licences#</span></span> 
- <span data-ttu-id="a2b91-754">driverslic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-754">DriversLic#</span></span> 
- <span data-ttu-id="a2b91-755">driverslics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-755">DriversLics#</span></span> 
- <span data-ttu-id="a2b91-756">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-756">DriversLicense#</span></span> 
- <span data-ttu-id="a2b91-757">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-757">DriversLicenses#</span></span> 
- <span data-ttu-id="a2b91-758">のデモライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-758">DriversLicence#</span></span> 
- <span data-ttu-id="a2b91-759">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="a2b91-759">DriversLicences#</span></span> 
- <span data-ttu-id="a2b91-760">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-760">Drivers Lic#</span></span> 
- <span data-ttu-id="a2b91-761">ドライバー lics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-761">Drivers Lics#</span></span> 
- <span data-ttu-id="a2b91-762">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-762">Drivers License#</span></span> 
- <span data-ttu-id="a2b91-763">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-763">Drivers Licenses#</span></span> 
- <span data-ttu-id="a2b91-764">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-764">Drivers Licence#</span></span> 
- <span data-ttu-id="a2b91-765">Drivers ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-765">Drivers Licences#</span></span> 
- <span data-ttu-id="a2b91-766">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-766">Driver'Lic#</span></span> 
- <span data-ttu-id="a2b91-767">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-767">Driver'Lics#</span></span> 
- <span data-ttu-id="a2b91-768">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-768">Driver'License#</span></span> 
- <span data-ttu-id="a2b91-769">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-769">Driver'Licenses#</span></span> 
- <span data-ttu-id="a2b91-770">Driver'Licence#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-770">Driver'Licence#</span></span> 
- <span data-ttu-id="a2b91-771">Driver'Licences#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-771">Driver'Licences#</span></span> 
- <span data-ttu-id="a2b91-772">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-772">Driver' Lic#</span></span> 
- <span data-ttu-id="a2b91-773">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-773">Driver' Lics#</span></span> 
- <span data-ttu-id="a2b91-774">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-774">Driver' License#</span></span> 
- <span data-ttu-id="a2b91-775">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-775">Driver' Licenses#</span></span> 
- <span data-ttu-id="a2b91-776">ドライバー ' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-776">Driver' Licence#</span></span> 
- <span data-ttu-id="a2b91-777">ドライバー ' ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-777">Driver' Licences#</span></span> 
- <span data-ttu-id="a2b91-778">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-778">Driver'sLic#</span></span> 
- <span data-ttu-id="a2b91-779">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-779">Driver'sLics#</span></span> 
- <span data-ttu-id="a2b91-780">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-780">Driver'sLicense#</span></span> 
- <span data-ttu-id="a2b91-781">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-781">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a2b91-782">ドライバ ' スライスの持続性 #</span><span class="sxs-lookup"><span data-stu-id="a2b91-782">Driver'sLicence#</span></span> 
- <span data-ttu-id="a2b91-783">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="a2b91-783">Driver'sLicences#</span></span> 
- <span data-ttu-id="a2b91-784">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-784">Driver's Lic#</span></span> 
- <span data-ttu-id="a2b91-785">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-785">Driver's Lics#</span></span> 
- <span data-ttu-id="a2b91-786">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-786">Driver's License#</span></span> 
- <span data-ttu-id="a2b91-787">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-787">Driver's Licenses#</span></span> 
- <span data-ttu-id="a2b91-788">ドライバーのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-788">Driver's Licence#</span></span> 
- <span data-ttu-id="a2b91-789">ドライバーのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-789">Driver's Licences#</span></span> 
- <span data-ttu-id="a2b91-790">Permis de Conduire #</span><span class="sxs-lookup"><span data-stu-id="a2b91-790">Permis de Conduire#</span></span> 
- <span data-ttu-id="a2b91-791">rid</span><span class="sxs-lookup"><span data-stu-id="a2b91-791">id#</span></span> 
- <span data-ttu-id="a2b91-792">rid</span><span class="sxs-lookup"><span data-stu-id="a2b91-792">ids#</span></span> 
- <span data-ttu-id="a2b91-793">idcard card#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-793">idcard card#</span></span> 
- <span data-ttu-id="a2b91-794">idcard cards#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-794">idcard cards#</span></span> 
- <span data-ttu-id="a2b91-795">idcard#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-795">idcard#</span></span> 
- <span data-ttu-id="a2b91-796">identification card#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-796">identification card#</span></span> 
- <span data-ttu-id="a2b91-797">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-797">identification cards#</span></span> 
- <span data-ttu-id="a2b91-798">identification#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-798">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="a2b91-799">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-799">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-800">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-800">Format</span></span>

<span data-ttu-id="a2b91-801">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-801">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-802">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-802">Pattern</span></span>

<span data-ttu-id="a2b91-803">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-803">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-804">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-804">Checksum</span></span>

<span data-ttu-id="a2b91-805">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-805">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-806">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-806">Definition</span></span>

<span data-ttu-id="a2b91-807">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-807">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-808">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-808">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-809">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-809">A keyword from Keyword_canada_health_service_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-810">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-810">Keywords</span></span>

#### <a name="keywordcanadahealthservicenumber"></a><span data-ttu-id="a2b91-811">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-811">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="a2b91-812">personal health number</span><span class="sxs-lookup"><span data-stu-id="a2b91-812">personal health number</span></span>
- <span data-ttu-id="a2b91-813">
patient information</span><span class="sxs-lookup"><span data-stu-id="a2b91-813">patient information</span></span>
- <span data-ttu-id="a2b91-814">正常性サービス</span><span class="sxs-lookup"><span data-stu-id="a2b91-814">health services</span></span>
- <span data-ttu-id="a2b91-815">
speciality services</span><span class="sxs-lookup"><span data-stu-id="a2b91-815">speciality services</span></span>
- <span data-ttu-id="a2b91-816">
automobile accident</span><span class="sxs-lookup"><span data-stu-id="a2b91-816">automobile accident</span></span>
- <span data-ttu-id="a2b91-817">
patient hospital</span><span class="sxs-lookup"><span data-stu-id="a2b91-817">patient hospital</span></span>
- <span data-ttu-id="a2b91-818">
psychiatrist</span><span class="sxs-lookup"><span data-stu-id="a2b91-818">psychiatrist</span></span>
- <span data-ttu-id="a2b91-819">
workers compensation</span><span class="sxs-lookup"><span data-stu-id="a2b91-819">workers compensation</span></span>
- <span data-ttu-id="a2b91-820">
disability</span><span class="sxs-lookup"><span data-stu-id="a2b91-820">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="a2b91-821">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-821">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-822">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-822">Format</span></span>

<span data-ttu-id="a2b91-823">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-823">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-824">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-824">Pattern</span></span>

<span data-ttu-id="a2b91-825">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-825">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-826">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-826">Checksum</span></span>

<span data-ttu-id="a2b91-827">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-827">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-828">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-828">Definition</span></span>

<span data-ttu-id="a2b91-829">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-829">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-830">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-830">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-831">Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-831">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-832">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-832">Keywords</span></span>

#### <a name="keywordcanadapassportnumber"></a><span data-ttu-id="a2b91-833">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-833">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="a2b91-834">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="a2b91-834">canadian citizenship</span></span>
- <span data-ttu-id="a2b91-835">
canadian passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-835">canadian passport</span></span>
- <span data-ttu-id="a2b91-836">
passport application</span><span class="sxs-lookup"><span data-stu-id="a2b91-836">passport application</span></span>
- <span data-ttu-id="a2b91-837">
passport photos</span><span class="sxs-lookup"><span data-stu-id="a2b91-837">passport photos</span></span>
- <span data-ttu-id="a2b91-838">
certified translator</span><span class="sxs-lookup"><span data-stu-id="a2b91-838">certified translator</span></span>
- <span data-ttu-id="a2b91-839">
canadian citizens</span><span class="sxs-lookup"><span data-stu-id="a2b91-839">canadian citizens</span></span>
- <span data-ttu-id="a2b91-840">
processing times</span><span class="sxs-lookup"><span data-stu-id="a2b91-840">processing times</span></span>
- <span data-ttu-id="a2b91-841">

renewal application</span><span class="sxs-lookup"><span data-stu-id="a2b91-841">renewal application</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a2b91-842">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-842">Keyword_passport</span></span>

- <span data-ttu-id="a2b91-843">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-843">Passport Number</span></span>
- <span data-ttu-id="a2b91-844">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a2b91-844">Passport No</span></span>
- <span data-ttu-id="a2b91-845">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-845">Passport #</span></span>
- <span data-ttu-id="a2b91-846">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-846">Passport#</span></span>
- <span data-ttu-id="a2b91-847">PassportID</span><span class="sxs-lookup"><span data-stu-id="a2b91-847">PassportID</span></span>
- <span data-ttu-id="a2b91-848">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a2b91-848">Passportno</span></span>
- <span data-ttu-id="a2b91-849">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-849">passportnumber</span></span>
- <span data-ttu-id="a2b91-850">パスポート</span><span class="sxs-lookup"><span data-stu-id="a2b91-850">パスポート</span></span>
- <span data-ttu-id="a2b91-851">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-851">パスポート番号</span></span>
- <span data-ttu-id="a2b91-852">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-852">パスポートのNum</span></span>
- <span data-ttu-id="a2b91-853">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-853">パスポート＃</span></span>
- <span data-ttu-id="a2b91-854">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a2b91-854">Numéro de passeport</span></span>
- <span data-ttu-id="a2b91-855">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a2b91-855">Passeport n °</span></span>
- <span data-ttu-id="a2b91-856">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a2b91-856">Passeport Non</span></span>
- <span data-ttu-id="a2b91-857">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-857">Passeport #</span></span>
- <span data-ttu-id="a2b91-858">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-858">Passeport#</span></span>
- <span data-ttu-id="a2b91-859">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a2b91-859">PasseportNon</span></span>
- <span data-ttu-id="a2b91-860">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a2b91-860">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="a2b91-861">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-861">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-862">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-862">Format</span></span>

<span data-ttu-id="a2b91-863">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-863">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-864">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-864">Pattern</span></span>

<span data-ttu-id="a2b91-865">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-865">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-866">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-866">Checksum</span></span>

<span data-ttu-id="a2b91-867">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-867">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-868">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-868">Definition</span></span>

<span data-ttu-id="a2b91-p104">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。Keyword_canada_phin または Keyword_canada_provinces から、少なくとも2つのキーワードが見つかります。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p104">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern. At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-871">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-871">Keywords</span></span>

#### <a name="keywordcanadaphin"></a><span data-ttu-id="a2b91-872">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="a2b91-872">Keyword_canada_phin</span></span>

- <span data-ttu-id="a2b91-873">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a2b91-873">social insurance number</span></span>
- <span data-ttu-id="a2b91-874">
health information act</span><span class="sxs-lookup"><span data-stu-id="a2b91-874">health information act</span></span>
- <span data-ttu-id="a2b91-875">
income tax information</span><span class="sxs-lookup"><span data-stu-id="a2b91-875">income tax information</span></span>
- <span data-ttu-id="a2b91-876">
manitoba health</span><span class="sxs-lookup"><span data-stu-id="a2b91-876">manitoba health</span></span>
- <span data-ttu-id="a2b91-877">
health registration</span><span class="sxs-lookup"><span data-stu-id="a2b91-877">health registration</span></span>
- <span data-ttu-id="a2b91-878">
prescription purchases</span><span class="sxs-lookup"><span data-stu-id="a2b91-878">prescription purchases</span></span>
- <span data-ttu-id="a2b91-879">
benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="a2b91-879">benefit eligibility</span></span>
- <span data-ttu-id="a2b91-880">
personal health</span><span class="sxs-lookup"><span data-stu-id="a2b91-880">personal health</span></span>
- <span data-ttu-id="a2b91-881">
power of attorney</span><span class="sxs-lookup"><span data-stu-id="a2b91-881">power of attorney</span></span>
- <span data-ttu-id="a2b91-882">
registration number</span><span class="sxs-lookup"><span data-stu-id="a2b91-882">registration number</span></span>
- <span data-ttu-id="a2b91-883">personal health number</span><span class="sxs-lookup"><span data-stu-id="a2b91-883">personal health number</span></span>
- <span data-ttu-id="a2b91-884">
practitioner referral</span><span class="sxs-lookup"><span data-stu-id="a2b91-884">practitioner referral</span></span>
- <span data-ttu-id="a2b91-885">
wellness professional</span><span class="sxs-lookup"><span data-stu-id="a2b91-885">wellness professional</span></span>
- <span data-ttu-id="a2b91-886">
patient referral</span><span class="sxs-lookup"><span data-stu-id="a2b91-886">patient referral</span></span>
- <span data-ttu-id="a2b91-887">

health and wellness</span><span class="sxs-lookup"><span data-stu-id="a2b91-887">health and wellness</span></span>

#### <a name="keywordcanadaprovinces"></a><span data-ttu-id="a2b91-888">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="a2b91-888">Keyword_canada_provinces</span></span>

- <span data-ttu-id="a2b91-889">Nunavut</span><span class="sxs-lookup"><span data-stu-id="a2b91-889">Nunavut</span></span>
- <span data-ttu-id="a2b91-890">
Quebec</span><span class="sxs-lookup"><span data-stu-id="a2b91-890">Quebec</span></span>
- <span data-ttu-id="a2b91-891">
Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="a2b91-891">Northwest Territories</span></span>
- <span data-ttu-id="a2b91-892">
Ontario</span><span class="sxs-lookup"><span data-stu-id="a2b91-892">Ontario</span></span>
- <span data-ttu-id="a2b91-893">
British Columbia</span><span class="sxs-lookup"><span data-stu-id="a2b91-893">British Columbia</span></span>
- <span data-ttu-id="a2b91-894">
Alberta</span><span class="sxs-lookup"><span data-stu-id="a2b91-894">Alberta</span></span>
- <span data-ttu-id="a2b91-895">
Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="a2b91-895">Saskatchewan</span></span>
- <span data-ttu-id="a2b91-896">
Manitoba</span><span class="sxs-lookup"><span data-stu-id="a2b91-896">Manitoba</span></span>
- <span data-ttu-id="a2b91-897">
Yukon</span><span class="sxs-lookup"><span data-stu-id="a2b91-897">Yukon</span></span>
- <span data-ttu-id="a2b91-898">
Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="a2b91-898">Newfoundland and Labrador</span></span>
- <span data-ttu-id="a2b91-899">
New Brunswick</span><span class="sxs-lookup"><span data-stu-id="a2b91-899">New Brunswick</span></span>
- <span data-ttu-id="a2b91-900">
Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="a2b91-900">Nova Scotia</span></span>
- <span data-ttu-id="a2b91-901">
Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="a2b91-901">Prince Edward Island</span></span>
- <span data-ttu-id="a2b91-902">カナダ</span><span class="sxs-lookup"><span data-stu-id="a2b91-902">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="a2b91-903">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-903">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-904">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-904">Format</span></span>

<span data-ttu-id="a2b91-905">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-905">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-906">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-906">Pattern</span></span>

<span data-ttu-id="a2b91-907">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-907">Formatted:</span></span>
- <span data-ttu-id="a2b91-908">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-908">Three digits</span></span> 
- <span data-ttu-id="a2b91-909">ハイフンまたはスペース 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-909">A hyphen or space</span></span> 
- <span data-ttu-id="a2b91-910">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-910">Three digits</span></span> 
- <span data-ttu-id="a2b91-911">ハイフンまたはスペース 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-911">A hyphen or space</span></span> 
- <span data-ttu-id="a2b91-912">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-912">Three digits</span></span>

<span data-ttu-id="a2b91-913">書式なし: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-913">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-914">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-914">Checksum</span></span>

<span data-ttu-id="a2b91-915">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-915">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-916">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-916">Definition</span></span>

<span data-ttu-id="a2b91-917">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-917">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-918">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-918">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-919">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-919">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="a2b91-920">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-920">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="a2b91-921">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-921">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="a2b91-922">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-922">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a2b91-923">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-923">The checksum passes.</span></span>

<span data-ttu-id="a2b91-924">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-924">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-925">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-925">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-926">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-926">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="a2b91-927">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-927">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-928">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-928">Keywords</span></span>

#### <a name="keywordsin"></a><span data-ttu-id="a2b91-929">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="a2b91-929">Keyword_sin</span></span>

- <span data-ttu-id="a2b91-930">sin</span><span class="sxs-lookup"><span data-stu-id="a2b91-930">sin</span></span> 
- <span data-ttu-id="a2b91-931">social insurance
</span><span class="sxs-lookup"><span data-stu-id="a2b91-931">social insurance</span></span> 
- <span data-ttu-id="a2b91-932">numero d'assurance sociale
</span><span class="sxs-lookup"><span data-stu-id="a2b91-932">numero d'assurance sociale</span></span> 
- <span data-ttu-id="a2b91-933">sins
</span><span class="sxs-lookup"><span data-stu-id="a2b91-933">sins</span></span> 
- <span data-ttu-id="a2b91-934">ssn</span><span class="sxs-lookup"><span data-stu-id="a2b91-934">ssn</span></span> 
- <span data-ttu-id="a2b91-935">ssn</span><span class="sxs-lookup"><span data-stu-id="a2b91-935">ssns</span></span> 
- <span data-ttu-id="a2b91-936">ソーシャルセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a2b91-936">social security</span></span> 
- <span data-ttu-id="a2b91-937">numero d'assurance social
</span><span class="sxs-lookup"><span data-stu-id="a2b91-937">numero d'assurance social</span></span> 
- <span data-ttu-id="a2b91-938">国別の識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-938">national identification number</span></span> 
- <span data-ttu-id="a2b91-939">
national id</span><span class="sxs-lookup"><span data-stu-id="a2b91-939">national id</span></span> 
- <span data-ttu-id="a2b91-940">sin#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-940">sin#</span></span> 
- <span data-ttu-id="a2b91-941">soc ins
</span><span class="sxs-lookup"><span data-stu-id="a2b91-941">soc ins</span></span> 
- <span data-ttu-id="a2b91-942">social ins
</span><span class="sxs-lookup"><span data-stu-id="a2b91-942">social ins</span></span> 

#### <a name="keywordsincollaborative"></a><span data-ttu-id="a2b91-943">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a2b91-943">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="a2b91-944">driver's license</span><span class="sxs-lookup"><span data-stu-id="a2b91-944">driver's license</span></span> 
- <span data-ttu-id="a2b91-945">drivers license</span><span class="sxs-lookup"><span data-stu-id="a2b91-945">drivers license</span></span> 
- <span data-ttu-id="a2b91-946">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-946">driver's licence</span></span> 
- <span data-ttu-id="a2b91-947">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a2b91-947">drivers licence</span></span> 
- <span data-ttu-id="a2b91-948">DOB
</span><span class="sxs-lookup"><span data-stu-id="a2b91-948">DOB</span></span> 
- <span data-ttu-id="a2b91-949">誕生日</span><span class="sxs-lookup"><span data-stu-id="a2b91-949">Birthdate</span></span> 
- <span data-ttu-id="a2b91-950">誕生日 </span><span class="sxs-lookup"><span data-stu-id="a2b91-950">Birthday</span></span> 
- <span data-ttu-id="a2b91-951">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="a2b91-951">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="a2b91-952">チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-952">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-953">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-953">Format</span></span>

<span data-ttu-id="a2b91-954">7-8 桁の数字と区切り文字のチェックディジットまたは文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-954">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-955">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-955">Pattern</span></span>

<span data-ttu-id="a2b91-956">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-956">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="a2b91-957">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-957">1-2 digits</span></span> 
- <span data-ttu-id="a2b91-958">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-958">A period</span></span> 
- <span data-ttu-id="a2b91-959">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-959">Three digits</span></span> 
- <span data-ttu-id="a2b91-960">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-960">A period</span></span> 
- <span data-ttu-id="a2b91-961">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-961">Three digits</span></span> 
- <span data-ttu-id="a2b91-962">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-962">A dash</span></span> 
- <span data-ttu-id="a2b91-963">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="a2b91-963">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-964">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-964">Checksum</span></span>

<span data-ttu-id="a2b91-965">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-965">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-966">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-966">Definition</span></span>

<span data-ttu-id="a2b91-967">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-967">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-968">関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-968">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-969">Keyword_chile_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-969">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="a2b91-970">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-970">The checksum passes.</span></span>

<span data-ttu-id="a2b91-971">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-971">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-972">関数 Func_chile_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-972">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-973">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-973">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-974">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-974">Keywords</span></span>

#### <a name="keywordchileidcard"></a><span data-ttu-id="a2b91-975">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-975">Keyword_chile_id_card</span></span>

- <span data-ttu-id="a2b91-976">National Identification Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-976">National Identification Number</span></span> 
- <span data-ttu-id="a2b91-977">Identity card</span><span class="sxs-lookup"><span data-stu-id="a2b91-977">Identity card</span></span> 
- <span data-ttu-id="a2b91-978">ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-978">ID</span></span> 
- <span data-ttu-id="a2b91-979">Identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-979">Identification</span></span> 
- <span data-ttu-id="a2b91-980">Rol Único Nacional
</span><span class="sxs-lookup"><span data-stu-id="a2b91-980">Rol Único Nacional</span></span> 
- <span data-ttu-id="a2b91-981">実行</span><span class="sxs-lookup"><span data-stu-id="a2b91-981">RUN</span></span> 
- <span data-ttu-id="a2b91-982">Rol Único Tributario
</span><span class="sxs-lookup"><span data-stu-id="a2b91-982">Rol Único Tributario</span></span> 
- <span data-ttu-id="a2b91-983">RUT
</span><span class="sxs-lookup"><span data-stu-id="a2b91-983">RUT</span></span> 
- <span data-ttu-id="a2b91-984">Cédula de Identidad
</span><span class="sxs-lookup"><span data-stu-id="a2b91-984">Cédula de Identidad</span></span> 
- <span data-ttu-id="a2b91-985">Número De Identificación Nacional
</span><span class="sxs-lookup"><span data-stu-id="a2b91-985">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="a2b91-986">Tarjeta de identificación
</span><span class="sxs-lookup"><span data-stu-id="a2b91-986">Tarjeta de identificación</span></span> 
- <span data-ttu-id="a2b91-987">Identificación
</span><span class="sxs-lookup"><span data-stu-id="a2b91-987">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="a2b91-988">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-988">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-989">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-989">Format</span></span>

<span data-ttu-id="a2b91-990">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-990">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-991">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-991">Pattern</span></span>

<span data-ttu-id="a2b91-992">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-992">18 digits:</span></span>
- <span data-ttu-id="a2b91-993">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-993">Six digits which are an address code</span></span> 
- <span data-ttu-id="a2b91-994">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-994">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-995">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-995">Three digits which are an order code</span></span> 
- <span data-ttu-id="a2b91-996">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-996">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-997">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-997">Checksum</span></span>

<span data-ttu-id="a2b91-998">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-998">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-999">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-999">Definition</span></span>

<span data-ttu-id="a2b91-1000">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1000">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1001">関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1001">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1002">Keyword_china_resident_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1002">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="a2b91-1003">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1003">The checksum passes.</span></span>

<span data-ttu-id="a2b91-1004">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1004">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1005">関数 Func_china_resident_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1005">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1006">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1006">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1007">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1007">Keywords</span></span>

### <a name="keywordchinaresidentid"></a><span data-ttu-id="a2b91-1008">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-1008">Keyword_china_resident_id</span></span>

- <span data-ttu-id="a2b91-1009">Resident Identity Card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1009">Resident Identity Card</span></span> 
- <span data-ttu-id="a2b91-1010">PRC</span><span class="sxs-lookup"><span data-stu-id="a2b91-1010">PRC</span></span> 
- <span data-ttu-id="a2b91-1011">National Identification Card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1011">National Identification Card</span></span> 
- <span data-ttu-id="a2b91-1012">身份证 </span><span class="sxs-lookup"><span data-stu-id="a2b91-1012">身份证</span></span> 
- <span data-ttu-id="a2b91-1013">居民 身份证 </span><span class="sxs-lookup"><span data-stu-id="a2b91-1013">居民 身份证</span></span> 
- <span data-ttu-id="a2b91-1014">居民身份证
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1014">居民身份证</span></span> 
- <span data-ttu-id="a2b91-1015">鉴定

</span><span class="sxs-lookup"><span data-stu-id="a2b91-1015">鉴定</span></span> 
- <span data-ttu-id="a2b91-1016">身分證 </span><span class="sxs-lookup"><span data-stu-id="a2b91-1016">身分證</span></span> 
- <span data-ttu-id="a2b91-1017">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="a2b91-1017">居民 身份證</span></span>
- <span data-ttu-id="a2b91-1018">鑑定 </span><span class="sxs-lookup"><span data-stu-id="a2b91-1018">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="a2b91-1019">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1019">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1020">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1020">Format</span></span>

<span data-ttu-id="a2b91-1021">書式設定または書式設定ができない16桁の数字 (dddddddddddddddd)。 luhn テストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1021">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1022">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1022">Pattern</span></span>

<span data-ttu-id="a2b91-1023">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1023">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1024">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1024">Checksum</span></span>

<span data-ttu-id="a2b91-1025">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1025">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1026">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1026">Definition</span></span>

<span data-ttu-id="a2b91-1027">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1027">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1028">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1028">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1029">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1029">One of the following is true:</span></span>
    - <span data-ttu-id="a2b91-1030">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1030">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="a2b91-1031">Keyword_cc_name からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1031">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="a2b91-1032">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1032">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a2b91-1033">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1033">The checksum passes.</span></span>

<span data-ttu-id="a2b91-1034">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1034">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1035">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1035">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1036">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1036">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1037">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1037">Keywords</span></span>

#### <a name="keywordccverification"></a><span data-ttu-id="a2b91-1038">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="a2b91-1038">Keyword_cc_verification</span></span>

- <span data-ttu-id="a2b91-1039">card verification</span><span class="sxs-lookup"><span data-stu-id="a2b91-1039">card verification</span></span>
- <span data-ttu-id="a2b91-1040">card identification number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1040">card identification number</span></span>
- <span data-ttu-id="a2b91-1041">cvn
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1041">cvn</span></span>
- <span data-ttu-id="a2b91-1042">cid
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1042">cid</span></span>
- <span data-ttu-id="a2b91-1043">cvc2</span><span class="sxs-lookup"><span data-stu-id="a2b91-1043">cvc2</span></span>
- <span data-ttu-id="a2b91-1044">cvv2</span><span class="sxs-lookup"><span data-stu-id="a2b91-1044">cvv2</span></span>
- <span data-ttu-id="a2b91-1045">pin block
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1045">pin block</span></span>
- <span data-ttu-id="a2b91-1046">security code
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1046">security code</span></span>
- <span data-ttu-id="a2b91-1047">security number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1047">security number</span></span>
- <span data-ttu-id="a2b91-1048">security no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1048">security no</span></span>
- <span data-ttu-id="a2b91-1049">issue number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1049">issue number</span></span>
- <span data-ttu-id="a2b91-1050">issue no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1050">issue no</span></span>
- <span data-ttu-id="a2b91-1051">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1051">cryptogramme</span></span>
- <span data-ttu-id="a2b91-1052">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1052">numéro de sécurité</span></span>
- <span data-ttu-id="a2b91-1053">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1053">numero de securite</span></span>
- <span data-ttu-id="a2b91-1054">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1054">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="a2b91-1055">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1055">kreditkartenprufnummer</span></span>
- <span data-ttu-id="a2b91-1056">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1056">prüfziffer</span></span>
- <span data-ttu-id="a2b91-1057">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1057">prufziffer</span></span>
- <span data-ttu-id="a2b91-1058">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="a2b91-1058">sicherheits Kode</span></span>
- <span data-ttu-id="a2b91-1059">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1059">sicherheitscode</span></span>
- <span data-ttu-id="a2b91-1060">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1060">sicherheitsnummer</span></span>
- <span data-ttu-id="a2b91-1061">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1061">verfalldatum</span></span>
- <span data-ttu-id="a2b91-1062">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1062">codice di verifica</span></span>
- <span data-ttu-id="a2b91-p105">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p105">cod. sicurezza</span></span>
- <span data-ttu-id="a2b91-1065">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2b91-1065">cod sicurezza</span></span>
- <span data-ttu-id="a2b91-1066">
n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="a2b91-1066">n autorizzazione</span></span>
- <span data-ttu-id="a2b91-1067">código
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1067">código</span></span>
- <span data-ttu-id="a2b91-1068">codigo
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1068">codigo</span></span>
- <span data-ttu-id="a2b91-p106">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p106">cod. seg</span></span>
- <span data-ttu-id="a2b91-1071">cod セグメント</span><span class="sxs-lookup"><span data-stu-id="a2b91-1071">cod seg</span></span>
- <span data-ttu-id="a2b91-1072">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1072">código de segurança</span></span>
- <span data-ttu-id="a2b91-1073">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1073">codigo de seguranca</span></span>
- <span data-ttu-id="a2b91-1074">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1074">codigo de segurança</span></span>
- <span data-ttu-id="a2b91-1075">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1075">código de seguranca</span></span>
- <span data-ttu-id="a2b91-p107">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p107">cód. segurança</span></span>
- <span data-ttu-id="a2b91-p108">cod.seguranca cod。segurança</span><span class="sxs-lookup"><span data-stu-id="a2b91-p108">cod. seguranca cod. segurança</span></span>
- <span data-ttu-id="a2b91-p109">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p109">cód. seguranca</span></span>
- <span data-ttu-id="a2b91-1083">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a2b91-1083">cód segurança</span></span>
- <span data-ttu-id="a2b91-1084">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="a2b91-1084">cod seguranca cod segurança</span></span>
- <span data-ttu-id="a2b91-1085">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a2b91-1085">cód seguranca</span></span>
- <span data-ttu-id="a2b91-1086">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1086">número de verificação</span></span>
- <span data-ttu-id="a2b91-1087">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1087">numero de verificacao</span></span>
- <span data-ttu-id="a2b91-1088">ablauf
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1088">ablauf</span></span>
- <span data-ttu-id="a2b91-1089">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1089">gültig bis</span></span>
- <span data-ttu-id="a2b91-1090">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1090">gültigkeitsdatum</span></span>
- <span data-ttu-id="a2b91-1091">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1091">gultig bis</span></span>
- <span data-ttu-id="a2b91-1092">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1092">gultigkeitsdatum</span></span>
- <span data-ttu-id="a2b91-1093">scadenza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1093">scadenza</span></span>
- <span data-ttu-id="a2b91-1094">data scad
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1094">data scad</span></span>
- <span data-ttu-id="a2b91-1095">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1095">fecha de expiracion</span></span>
- <span data-ttu-id="a2b91-1096">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1096">fecha de venc</span></span>
- <span data-ttu-id="a2b91-1097">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1097">vencimiento</span></span>
- <span data-ttu-id="a2b91-1098">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1098">válido hasta</span></span>
- <span data-ttu-id="a2b91-1099">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1099">valido hasta</span></span>
- <span data-ttu-id="a2b91-1100">vto
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1100">vto</span></span>
- <span data-ttu-id="a2b91-1101">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1101">data de expiração</span></span>
- <span data-ttu-id="a2b91-1102">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1102">data de expiracao</span></span>
- <span data-ttu-id="a2b91-1103">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1103">data em que expira</span></span>
- <span data-ttu-id="a2b91-1104">validade
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1104">validade</span></span>
- <span data-ttu-id="a2b91-1105">valor
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1105">valor</span></span>
- <span data-ttu-id="a2b91-1106">vencimento
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1106">vencimento</span></span>
- <span data-ttu-id="a2b91-1107">venc</span><span class="sxs-lookup"><span data-stu-id="a2b91-1107">Venc</span></span> 

#### <a name="keywordccname"></a><span data-ttu-id="a2b91-1108">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="a2b91-1108">Keyword_cc_name</span></span>

- <span data-ttu-id="a2b91-1109">amex</span><span class="sxs-lookup"><span data-stu-id="a2b91-1109">amex</span></span>
- <span data-ttu-id="a2b91-1110">
american express</span><span class="sxs-lookup"><span data-stu-id="a2b91-1110">american express</span></span>
- <span data-ttu-id="a2b91-1111">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1111">americanexpress</span></span>
- <span data-ttu-id="a2b91-1112">Visa</span><span class="sxs-lookup"><span data-stu-id="a2b91-1112">Visa</span></span>
- <span data-ttu-id="a2b91-1113">mastercard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1113">mastercard</span></span>
- <span data-ttu-id="a2b91-1114">master card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1114">master card</span></span>
- <span data-ttu-id="a2b91-1115">
mc
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1115">mc</span></span> 
- <span data-ttu-id="a2b91-1116">mastercards</span><span class="sxs-lookup"><span data-stu-id="a2b91-1116">mastercards</span></span>
- <span data-ttu-id="a2b91-1117">
master cards</span><span class="sxs-lookup"><span data-stu-id="a2b91-1117">master cards</span></span>
- <span data-ttu-id="a2b91-1118">ダイナースのクラブ</span><span class="sxs-lookup"><span data-stu-id="a2b91-1118">diner's Club</span></span>
- <span data-ttu-id="a2b91-1119">diners club
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1119">diners club</span></span>
- <span data-ttu-id="a2b91-1120">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1120">dinersclub</span></span>
- <span data-ttu-id="a2b91-1121">discover card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1121">discover card</span></span>
- <span data-ttu-id="a2b91-1122">discovercard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1122">discovercard</span></span>
- <span data-ttu-id="a2b91-1123">discover cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1123">discover cards</span></span>
- <span data-ttu-id="a2b91-1124">JCB</span><span class="sxs-lookup"><span data-stu-id="a2b91-1124">JCB</span></span>
- <span data-ttu-id="a2b91-1125">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1125">japanese card bureau</span></span>
- <span data-ttu-id="a2b91-1126">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1126">carte blanche</span></span>
- <span data-ttu-id="a2b91-1127">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1127">carteblanche</span></span>
- <span data-ttu-id="a2b91-1128">credit card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1128">credit card</span></span>
- <span data-ttu-id="a2b91-1129">]</span><span class="sxs-lookup"><span data-stu-id="a2b91-1129">cc#</span></span>
- <span data-ttu-id="a2b91-1130">cc #:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1130">cc#:</span></span>
- <span data-ttu-id="a2b91-1131">
expiration date</span><span class="sxs-lookup"><span data-stu-id="a2b91-1131">expiration date</span></span>
- <span data-ttu-id="a2b91-1132">exp date
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1132">exp date</span></span>
- <span data-ttu-id="a2b91-1133">
expiry date</span><span class="sxs-lookup"><span data-stu-id="a2b91-1133">expiry date</span></span>
- <span data-ttu-id="a2b91-1134">
date d’expiration</span><span class="sxs-lookup"><span data-stu-id="a2b91-1134">date d’expiration</span></span>
- <span data-ttu-id="a2b91-1135">
date d'exp</span><span class="sxs-lookup"><span data-stu-id="a2b91-1135">date d'exp</span></span>
- <span data-ttu-id="a2b91-1136">
date expiration</span><span class="sxs-lookup"><span data-stu-id="a2b91-1136">date expiration</span></span>
- <span data-ttu-id="a2b91-1137">bank card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1137">bank card</span></span>
- <span data-ttu-id="a2b91-1138">
bankcard</span><span class="sxs-lookup"><span data-stu-id="a2b91-1138">bankcard</span></span>
- <span data-ttu-id="a2b91-1139">card number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1139">card number</span></span>
- <span data-ttu-id="a2b91-1140">card num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1140">card num</span></span>
- <span data-ttu-id="a2b91-1141">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1141">cardnumber</span></span>
- <span data-ttu-id="a2b91-1142">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1142">cardnumbers</span></span>
- <span data-ttu-id="a2b91-1143">card numbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1143">card numbers</span></span>
- <span data-ttu-id="a2b91-1144">creditcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1144">creditcard</span></span>
- <span data-ttu-id="a2b91-1145">credit cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1145">credit cards</span></span>
- <span data-ttu-id="a2b91-1146">creditcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1146">creditcards</span></span>
- <span data-ttu-id="a2b91-1147">ccn
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1147">ccn</span></span>
- <span data-ttu-id="a2b91-1148">card holder
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1148">card holder</span></span>
- <span data-ttu-id="a2b91-1149">cardholder
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1149">cardholder</span></span>
- <span data-ttu-id="a2b91-1150">card holders
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1150">card holders</span></span>
- <span data-ttu-id="a2b91-1151">cardholders
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1151">cardholders</span></span>
- <span data-ttu-id="a2b91-1152">check card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1152">check card</span></span>
- <span data-ttu-id="a2b91-1153">checkcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1153">checkcard</span></span>
- <span data-ttu-id="a2b91-1154">check cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1154">check cards</span></span>
- <span data-ttu-id="a2b91-1155">checkcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1155">checkcards</span></span>
- <span data-ttu-id="a2b91-1156">debit card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1156">debit card</span></span>
- <span data-ttu-id="a2b91-1157">debitcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1157">debitcard</span></span>
- <span data-ttu-id="a2b91-1158">debit cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1158">debit cards</span></span>
- <span data-ttu-id="a2b91-1159">debitcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1159">debitcards</span></span>
- <span data-ttu-id="a2b91-1160">atm card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1160">atm card</span></span>
- <span data-ttu-id="a2b91-1161">atmcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1161">atmcard</span></span>
- <span data-ttu-id="a2b91-1162">atm cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1162">atm cards</span></span>
- <span data-ttu-id="a2b91-1163">atmcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1163">atmcards</span></span>
- <span data-ttu-id="a2b91-1164">
enroute</span><span class="sxs-lookup"><span data-stu-id="a2b91-1164">enroute</span></span>
- <span data-ttu-id="a2b91-1165">
en route</span><span class="sxs-lookup"><span data-stu-id="a2b91-1165">en route</span></span>
- <span data-ttu-id="a2b91-1166">card type
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1166">card type</span></span>
- <span data-ttu-id="a2b91-1167">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1167">carte bancaire</span></span>
- <span data-ttu-id="a2b91-1168">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1168">carte de crédit</span></span>
- <span data-ttu-id="a2b91-1169">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1169">carte de credit</span></span>
- <span data-ttu-id="a2b91-1170">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1170">numéro de carte</span></span>
- <span data-ttu-id="a2b91-1171">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1171">numero de carte</span></span>
- <span data-ttu-id="a2b91-1172">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1172">nº de la carte</span></span>
- <span data-ttu-id="a2b91-1173">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1173">nº de carte</span></span>
- <span data-ttu-id="a2b91-1174">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1174">kreditkarte</span></span>
- <span data-ttu-id="a2b91-1175">karte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1175">karte</span></span>
- <span data-ttu-id="a2b91-1176">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1176">karteninhaber</span></span>
- <span data-ttu-id="a2b91-1177">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a2b91-1177">karteninhabers</span></span>
- <span data-ttu-id="a2b91-1178">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1178">kreditkarteninhaber</span></span>
- <span data-ttu-id="a2b91-1179">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1179">kreditkarteninstitut</span></span>
- <span data-ttu-id="a2b91-1180">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1180">kreditkartentyp</span></span>
- <span data-ttu-id="a2b91-1181">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1181">eigentümername</span></span>
- <span data-ttu-id="a2b91-1182">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1182">kartennr</span></span> 
- <span data-ttu-id="a2b91-1183">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1183">kartennummer</span></span>
- <span data-ttu-id="a2b91-1184">
kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1184">kreditkartennummer</span></span>
- <span data-ttu-id="a2b91-1185">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1185">kreditkarten-nummer</span></span>
- <span data-ttu-id="a2b91-1186">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1186">carta di credito</span></span>
- <span data-ttu-id="a2b91-1187">carta credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1187">carta credito</span></span>
- <span data-ttu-id="a2b91-1188">carta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1188">carta</span></span>
- <span data-ttu-id="a2b91-1189">n carta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1189">n carta</span></span>
- <span data-ttu-id="a2b91-p110">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p110">nr. carta</span></span>
- <span data-ttu-id="a2b91-1192">nr carta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1192">nr carta</span></span>
- <span data-ttu-id="a2b91-1193">numero carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1193">numero carta</span></span>
- <span data-ttu-id="a2b91-1194">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1194">numero della carta</span></span>
- <span data-ttu-id="a2b91-1195">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1195">numero di carta</span></span>
- <span data-ttu-id="a2b91-1196">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1196">tarjeta credito</span></span>
- <span data-ttu-id="a2b91-1197">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1197">tarjeta de credito</span></span>
- <span data-ttu-id="a2b91-1198">
tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="a2b91-1198">tarjeta crédito</span></span>
- <span data-ttu-id="a2b91-1199">
tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="a2b91-1199">tarjeta de crédito</span></span>
- <span data-ttu-id="a2b91-1200">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1200">tarjeta de atm</span></span>
- <span data-ttu-id="a2b91-1201">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1201">tarjeta atm</span></span>
- <span data-ttu-id="a2b91-1202">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1202">tarjeta debito</span></span>
- <span data-ttu-id="a2b91-1203">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1203">tarjeta de debito</span></span>
- <span data-ttu-id="a2b91-1204">
tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="a2b91-1204">tarjeta débito</span></span>
- <span data-ttu-id="a2b91-1205">
tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="a2b91-1205">tarjeta de débito</span></span>
- <span data-ttu-id="a2b91-1206">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1206">nº de tarjeta</span></span>
- <span data-ttu-id="a2b91-p111">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p111">no. de tarjeta</span></span>
- <span data-ttu-id="a2b91-1209">非の tarjeta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1209">no de tarjeta</span></span>
- <span data-ttu-id="a2b91-1210">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1210">numero de tarjeta</span></span>
- <span data-ttu-id="a2b91-1211">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1211">número de tarjeta</span></span>
- <span data-ttu-id="a2b91-1212">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1212">tarjeta no</span></span>
- <span data-ttu-id="a2b91-1213">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1213">tarjetahabiente</span></span>
- <span data-ttu-id="a2b91-1214">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1214">cartão de crédito</span></span>
- <span data-ttu-id="a2b91-1215">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1215">cartão de credito</span></span>
- <span data-ttu-id="a2b91-1216">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1216">cartao de crédito</span></span>
- <span data-ttu-id="a2b91-1217">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1217">cartao de credito</span></span>
- <span data-ttu-id="a2b91-1218">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1218">cartão de débito</span></span>
- <span data-ttu-id="a2b91-1219">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1219">cartao de débito</span></span>
- <span data-ttu-id="a2b91-1220">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1220">cartão de debito</span></span>
- <span data-ttu-id="a2b91-1221">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1221">cartao de debito</span></span>
- <span data-ttu-id="a2b91-1222">débito automático</span><span class="sxs-lookup"><span data-stu-id="a2b91-1222">débito automático</span></span>
- <span data-ttu-id="a2b91-1223">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1223">debito automatico</span></span>
- <span data-ttu-id="a2b91-1224">
número do cartão</span><span class="sxs-lookup"><span data-stu-id="a2b91-1224">número do cartão</span></span>
- <span data-ttu-id="a2b91-1225">
numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1225">numero do cartão</span></span> 
- <span data-ttu-id="a2b91-1226">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a2b91-1226">número do cartao</span></span>
- <span data-ttu-id="a2b91-1227">
numero do cartao</span><span class="sxs-lookup"><span data-stu-id="a2b91-1227">numero do cartao</span></span>
- <span data-ttu-id="a2b91-1228">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1228">número de cartão</span></span>
- <span data-ttu-id="a2b91-1229">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1229">numero de cartão</span></span>
- <span data-ttu-id="a2b91-1230">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1230">número de cartao</span></span>
- <span data-ttu-id="a2b91-1231">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1231">numero de cartao</span></span>
- <span data-ttu-id="a2b91-1232">n ° do cartão</span><span class="sxs-lookup"><span data-stu-id="a2b91-1232">nº do cartão</span></span>
- <span data-ttu-id="a2b91-1233">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1233">nº do cartao</span></span>
- <span data-ttu-id="a2b91-p112">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p112">nº. do cartão</span></span>
- <span data-ttu-id="a2b91-1236">no do cartão</span><span class="sxs-lookup"><span data-stu-id="a2b91-1236">no do cartão</span></span>
- <span data-ttu-id="a2b91-1237">いいえ。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1237">no do cartao</span></span>
- <span data-ttu-id="a2b91-p113">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p113">no. do cartão</span></span>
- <span data-ttu-id="a2b91-p114">
no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p114">no. do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="a2b91-1242">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1242">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1243">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1243">Format</span></span>

<span data-ttu-id="a2b91-1244">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1244">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1245">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1245">Pattern</span></span>

<span data-ttu-id="a2b91-1246">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1246">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1247">Checksum</span></span>

<span data-ttu-id="a2b91-1248">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1248">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1249">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-1249">Definition</span></span>

<span data-ttu-id="a2b91-1250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1251">関数 Func_croatia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1251">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1252">Keyword_croatia_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1252">A keyword from Keyword_croatia_id_card is found.</span></span>

```
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1253">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1253">Keywords</span></span>

#### <a name="keywordcroatiaidcard"></a><span data-ttu-id="a2b91-1254">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-1254">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="a2b91-1255">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="a2b91-1255">Croatian identity card</span></span>
- <span data-ttu-id="a2b91-1256">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="a2b91-1256">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="a2b91-1257">クロアチアの個人識別 (OIB) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1257">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1258">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1258">Format</span></span>

<span data-ttu-id="a2b91-1259">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1259">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1260">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1260">Pattern</span></span>

<span data-ttu-id="a2b91-1261">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1261">11 digits:</span></span>
- <span data-ttu-id="a2b91-1262">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1262">10 digits</span></span> 
- <span data-ttu-id="a2b91-1263">最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1263">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1264">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1264">Checksum</span></span>

<span data-ttu-id="a2b91-1265">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1265">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1266">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1266">Definition</span></span>

<span data-ttu-id="a2b91-1267">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1267">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1268">関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1268">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1269">Keyword_croatia_oib_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1269">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="a2b91-1270">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1270">The checksum passes.</span></span>

<span data-ttu-id="a2b91-1271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1272">関数 Func_croatia_oib_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1272">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1273">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1273">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1274">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1274">Keywords</span></span>

#### <a name="keywordcroatiaoibnumber"></a><span data-ttu-id="a2b91-1275">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1275">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="a2b91-1276">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1276">Personal Identification Number</span></span>
- <span data-ttu-id="a2b91-1277">Osobni identifikacijski broj
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1277">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="a2b91-1278">OIB
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1278">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="a2b91-1279">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1279">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1280">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1280">Format</span></span>

<span data-ttu-id="a2b91-1281">省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1281">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1282">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1282">Pattern</span></span>

<span data-ttu-id="a2b91-1283">9桁の数字 (古い形式):</span><span class="sxs-lookup"><span data-stu-id="a2b91-1283">Nine digits (old format):</span></span>
- <span data-ttu-id="a2b91-1284">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1284">Nine digits</span></span>

<span data-ttu-id="a2b91-1285">または</span><span class="sxs-lookup"><span data-stu-id="a2b91-1285">OR</span></span>

- <span data-ttu-id="a2b91-1286">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1286">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a2b91-1287">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-1287">A forward slash</span></span>
- <span data-ttu-id="a2b91-1288">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1288">Three digits</span></span>

<span data-ttu-id="a2b91-1289">10桁の数字 (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="a2b91-1289">10 digits (new format):</span></span>
- <span data-ttu-id="a2b91-1290">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1290">10 digits</span></span>

<span data-ttu-id="a2b91-1291">または</span><span class="sxs-lookup"><span data-stu-id="a2b91-1291">OR</span></span>

- <span data-ttu-id="a2b91-1292">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1292">Six digits that represent date of birth</span></span>
- <span data-ttu-id="a2b91-1293">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-1293">A forward slash</span></span> 
- <span data-ttu-id="a2b91-1294">4桁の数字 (最後の桁はチェックディジット)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1294">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1295">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1295">Checksum</span></span>

<span data-ttu-id="a2b91-1296">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1296">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1297">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1297">Definition</span></span>

<span data-ttu-id="a2b91-p115">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。Keyword_czech_id_card からのキーワードが見つかりました。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p115">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern. A keyword from Keyword_czech_id_card is found. The checksum passes.</span></span>

```
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="a2b91-1301">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1301">Keywords</span></span>

- <span data-ttu-id="a2b91-1302">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1302">czech personal identity number</span></span>
- <span data-ttu-id="a2b91-1303">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="a2b91-1303">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="a2b91-1304">デンマークの個人識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1304">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1305">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1305">Format</span></span>

<span data-ttu-id="a2b91-1306">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1306">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1307">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1307">Pattern</span></span>

<span data-ttu-id="a2b91-1308">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1308">10 digits:</span></span>
- <span data-ttu-id="a2b91-1309">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-1309">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-1310">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-1310">A hyphen</span></span> 
- <span data-ttu-id="a2b91-1311">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1311">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1312">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1312">Checksum</span></span>

<span data-ttu-id="a2b91-1313">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1314">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1314">Definition</span></span>

<span data-ttu-id="a2b91-p116">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。Keyword_denmark_id からのキーワードが見つかりました。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern. A keyword from Keyword_denmark_id is found. The checksum passes.</span></span>

```
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1318">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1318">Keywords</span></span>

#### <a name="keyworddenmarkid"></a><span data-ttu-id="a2b91-1319">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-1319">Keyword_denmark_id</span></span>

- <span data-ttu-id="a2b91-1320">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1320">Personal Identification Number</span></span>
- <span data-ttu-id="a2b91-1321">CPR</span><span class="sxs-lookup"><span data-stu-id="a2b91-1321">CPR</span></span>
- <span data-ttu-id="a2b91-1322">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="a2b91-1322">Det Centrale Personregister</span></span>
- <span data-ttu-id="a2b91-1323">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1323">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="a2b91-1324">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1324">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1325">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1325">Format</span></span>

<span data-ttu-id="a2b91-1326">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1326">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1327">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1327">Pattern</span></span>

<span data-ttu-id="a2b91-1328">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1328">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a2b91-1329">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="a2b91-1329">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="a2b91-1330">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1330">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="a2b91-1331">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="a2b91-1331">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1332">Checksum</span></span>

<span data-ttu-id="a2b91-1333">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1333">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1334">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1334">Definition</span></span>

<span data-ttu-id="a2b91-1335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1335">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1336">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1336">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1337">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1337">The checksum passes.</span></span>

```
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1338">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1338">Keywords</span></span>

<span data-ttu-id="a2b91-1339">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1339">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="a2b91-1340">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1340">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1341">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1341">Format</span></span>

<span data-ttu-id="a2b91-1342">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1342">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1343">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1343">Pattern</span></span>

<span data-ttu-id="a2b91-1344">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1344">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1345">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1345">Checksum</span></span>

<span data-ttu-id="a2b91-1346">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1346">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1347">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1347">Definition</span></span>

<span data-ttu-id="a2b91-1348">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1348">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1349">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1349">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1350">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1350">At least one of the following is true:</span></span>
    - <span data-ttu-id="a2b91-1351">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1351">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="a2b91-1352">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1352">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="a2b91-1353">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1353">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="a2b91-1354">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1354">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="a2b91-1355">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1355">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a2b91-1356">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1356">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1357">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1357">Keywords</span></span>

#### <a name="keywordeudebitcard"></a><span data-ttu-id="a2b91-1358">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-1358">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="a2b91-1359">アカウント番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1359">account number</span></span> 
- <span data-ttu-id="a2b91-1360">card number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1360">card number</span></span> 
- <span data-ttu-id="a2b91-1361">card no.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1361">card no.</span></span> 
- <span data-ttu-id="a2b91-1362">security number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1362">security number</span></span> 
- <span data-ttu-id="a2b91-1363">]</span><span class="sxs-lookup"><span data-stu-id="a2b91-1363">cc#</span></span> 

#### <a name="keywordcardtermsdict"></a><span data-ttu-id="a2b91-1364">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a2b91-1364">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="a2b91-1365">acct nbr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1365">acct nbr</span></span> 
- <span data-ttu-id="a2b91-1366">acct num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1366">acct num</span></span> 
- <span data-ttu-id="a2b91-1367">acct no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1367">acct no</span></span> 
- <span data-ttu-id="a2b91-1368">american express
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1368">american express</span></span> 
- <span data-ttu-id="a2b91-1369">americanexpress
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1369">americanexpress</span></span> 
- <span data-ttu-id="a2b91-1370">americano espresso
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1370">americano espresso</span></span> 
- <span data-ttu-id="a2b91-1371">amex</span><span class="sxs-lookup"><span data-stu-id="a2b91-1371">amex</span></span> 
- <span data-ttu-id="a2b91-1372">atm card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1372">atm card</span></span> 
- <span data-ttu-id="a2b91-1373">atm cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1373">atm cards</span></span> 
- <span data-ttu-id="a2b91-1374">atm kaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1374">atm kaart</span></span> 
- <span data-ttu-id="a2b91-1375">atmcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1375">atmcard</span></span> 
- <span data-ttu-id="a2b91-1376">atmcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1376">atmcards</span></span> 
- <span data-ttu-id="a2b91-1377">atmkaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1377">atmkaart</span></span> 
- <span data-ttu-id="a2b91-1378">atmkaarten
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1378">atmkaarten</span></span> 
- <span data-ttu-id="a2b91-1379">bancontact
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1379">bancontact</span></span> 
- <span data-ttu-id="a2b91-1380">bank card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1380">bank card</span></span> 
- <span data-ttu-id="a2b91-1381">bankkaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1381">bankkaart</span></span> 
- <span data-ttu-id="a2b91-1382">card holder
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1382">card holder</span></span> 
- <span data-ttu-id="a2b91-1383">card holders
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1383">card holders</span></span> 
- <span data-ttu-id="a2b91-1384">card num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1384">card num</span></span> 
- <span data-ttu-id="a2b91-1385">card number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1385">card number</span></span> 
- <span data-ttu-id="a2b91-1386">card numbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1386">card numbers</span></span> 
- <span data-ttu-id="a2b91-1387">card type
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1387">card type</span></span> 
- <span data-ttu-id="a2b91-1388">cardano numerico
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1388">cardano numerico</span></span> 
- <span data-ttu-id="a2b91-1389">cardholder
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1389">cardholder</span></span> 
- <span data-ttu-id="a2b91-1390">cardholders
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1390">cardholders</span></span> 
- <span data-ttu-id="a2b91-1391">cardnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1391">cardnumber</span></span> 
- <span data-ttu-id="a2b91-1392">cardnumbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1392">cardnumbers</span></span> 
- <span data-ttu-id="a2b91-1393">carta bianca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1393">carta bianca</span></span> 
- <span data-ttu-id="a2b91-1394">carta credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1394">carta credito</span></span> 
- <span data-ttu-id="a2b91-1395">carta di credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1395">carta di credito</span></span> 
- <span data-ttu-id="a2b91-1396">cartao de credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1396">cartao de credito</span></span> 
- <span data-ttu-id="a2b91-1397">cartao de crédito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1397">cartao de crédito</span></span> 
- <span data-ttu-id="a2b91-1398">cartao de debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1398">cartao de debito</span></span> 
- <span data-ttu-id="a2b91-1399">cartao de débito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1399">cartao de débito</span></span> 
- <span data-ttu-id="a2b91-1400">carte bancaire
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1400">carte bancaire</span></span> 
- <span data-ttu-id="a2b91-1401">carte blanche
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1401">carte blanche</span></span> 
- <span data-ttu-id="a2b91-1402">carte bleue
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1402">carte bleue</span></span> 
- <span data-ttu-id="a2b91-1403">carte de credit
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1403">carte de credit</span></span> 
- <span data-ttu-id="a2b91-1404">carte de crédit
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1404">carte de crédit</span></span> 
- <span data-ttu-id="a2b91-1405">carte di credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1405">carte di credito</span></span> 
- <span data-ttu-id="a2b91-1406">carteblanche
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1406">carteblanche</span></span> 
- <span data-ttu-id="a2b91-1407">cartão de credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1407">cartão de credito</span></span> 
- <span data-ttu-id="a2b91-1408">cartão de crédito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1408">cartão de crédito</span></span> 
- <span data-ttu-id="a2b91-1409">cartão de debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1409">cartão de debito</span></span> 
- <span data-ttu-id="a2b91-1410">cartão de débito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1410">cartão de débito</span></span> 
- <span data-ttu-id="a2b91-1411">cb
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1411">cb</span></span> 
- <span data-ttu-id="a2b91-1412">ccn
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1412">ccn</span></span> 
- <span data-ttu-id="a2b91-1413">check card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1413">check card</span></span> 
- <span data-ttu-id="a2b91-1414">check cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1414">check cards</span></span> 
- <span data-ttu-id="a2b91-1415">checkcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1415">checkcard</span></span>
- <span data-ttu-id="a2b91-1416">checkcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1416">checkcards</span></span> 
- <span data-ttu-id="a2b91-1417">chequekaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1417">chequekaart</span></span> 
- <span data-ttu-id="a2b91-1418">cirrus
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1418">cirrus</span></span> 
- <span data-ttu-id="a2b91-1419">cirrus-edc-maestro
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1419">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="a2b91-1420">controlekaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1420">controlekaart</span></span> 
- <span data-ttu-id="a2b91-1421">controlekaarten
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1421">controlekaarten</span></span> 
- <span data-ttu-id="a2b91-1422">credit card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1422">credit card</span></span> 
- <span data-ttu-id="a2b91-1423">credit cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1423">credit cards</span></span> 
- <span data-ttu-id="a2b91-1424">creditcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1424">creditcard</span></span> 
- <span data-ttu-id="a2b91-1425">creditcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1425">creditcards</span></span> 
- <span data-ttu-id="a2b91-1426">debetkaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1426">debetkaart</span></span> 
- <span data-ttu-id="a2b91-1427">debetkaarten
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1427">debetkaarten</span></span> 
- <span data-ttu-id="a2b91-1428">debit card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1428">debit card</span></span> 
- <span data-ttu-id="a2b91-1429">debit cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1429">debit cards</span></span> 
- <span data-ttu-id="a2b91-1430">debitcard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1430">debitcard</span></span> 
- <span data-ttu-id="a2b91-1431">debitcards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1431">debitcards</span></span> 
- <span data-ttu-id="a2b91-1432">debito automatico
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1432">debito automatico</span></span> 
- <span data-ttu-id="a2b91-1433">diners club
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1433">diners club</span></span> 
- <span data-ttu-id="a2b91-1434">dinersclub
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1434">dinersclub</span></span> 
- <span data-ttu-id="a2b91-1435">開示</span><span class="sxs-lookup"><span data-stu-id="a2b91-1435">discover</span></span> 
- <span data-ttu-id="a2b91-1436">discover card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1436">discover card</span></span> 
- <span data-ttu-id="a2b91-1437">discover cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1437">discover cards</span></span> 
- <span data-ttu-id="a2b91-1438">discovercard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1438">discovercard</span></span> 
- <span data-ttu-id="a2b91-1439">discovercards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1439">discovercards</span></span> 
- <span data-ttu-id="a2b91-1440">débito automático</span><span class="sxs-lookup"><span data-stu-id="a2b91-1440">débito automático</span></span>
- <span data-ttu-id="a2b91-1441">
edc
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1441">edc</span></span> 
- <span data-ttu-id="a2b91-1442">eigentümername
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1442">eigentümername</span></span> 
- <span data-ttu-id="a2b91-1443">european debit card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1443">european debit card</span></span> 
- <span data-ttu-id="a2b91-1444">hoofdkaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1444">hoofdkaart</span></span> 
- <span data-ttu-id="a2b91-1445">hoofdkaarten
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1445">hoofdkaarten</span></span> 
- <span data-ttu-id="a2b91-1446">in viaggio
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1446">in viaggio</span></span> 
- <span data-ttu-id="a2b91-1447">japanese card bureau
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1447">japanese card bureau</span></span> 
- <span data-ttu-id="a2b91-1448">japanse kaartdienst
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1448">japanse kaartdienst</span></span> 
- <span data-ttu-id="a2b91-1449">jcb
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1449">jcb</span></span> 
- <span data-ttu-id="a2b91-1450">kaart
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1450">kaart</span></span> 
- <span data-ttu-id="a2b91-1451">kaart num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1451">kaart num</span></span> 
- <span data-ttu-id="a2b91-1452">kaartaantal
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1452">kaartaantal</span></span> 
- <span data-ttu-id="a2b91-1453">kaartaantallen
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1453">kaartaantallen</span></span> 
- <span data-ttu-id="a2b91-1454">kaarthouder
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1454">kaarthouder</span></span> 
- <span data-ttu-id="a2b91-1455">kaarthouders
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1455">kaarthouders</span></span> 
- <span data-ttu-id="a2b91-1456">karte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1456">karte</span></span>  
- <span data-ttu-id="a2b91-1457">karteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1457">karteninhaber</span></span> 
- <span data-ttu-id="a2b91-1458">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="a2b91-1458">karteninhabers</span></span>
- <span data-ttu-id="a2b91-1459">
kartennr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1459">kartennr</span></span> 
- <span data-ttu-id="a2b91-1460">kartennummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1460">kartennummer</span></span> 
- <span data-ttu-id="a2b91-1461">kreditkarte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1461">kreditkarte</span></span> 
- <span data-ttu-id="a2b91-1462">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1462">kreditkarten-nummer</span></span> 
- <span data-ttu-id="a2b91-1463">kreditkarteninhaber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1463">kreditkarteninhaber</span></span> 
- <span data-ttu-id="a2b91-1464">kreditkarteninstitut
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1464">kreditkarteninstitut</span></span> 
- <span data-ttu-id="a2b91-1465">kreditkartennummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1465">kreditkartennummer</span></span> 
- <span data-ttu-id="a2b91-1466">kreditkartentyp
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1466">kreditkartentyp</span></span> 
- <span data-ttu-id="a2b91-1467">maestro
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1467">maestro</span></span> 
- <span data-ttu-id="a2b91-1468">master card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1468">master card</span></span> 
- <span data-ttu-id="a2b91-1469">master cards
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1469">master cards</span></span> 
- <span data-ttu-id="a2b91-1470">mastercard
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1470">mastercard</span></span> 
- <span data-ttu-id="a2b91-1471">mastercards</span><span class="sxs-lookup"><span data-stu-id="a2b91-1471">mastercards</span></span> 
- <span data-ttu-id="a2b91-1472">mc</span><span class="sxs-lookup"><span data-stu-id="a2b91-1472">mc</span></span> 
- <span data-ttu-id="a2b91-1473">mister cash
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1473">mister cash</span></span> 
- <span data-ttu-id="a2b91-1474">n carta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1474">n carta</span></span> 
- <span data-ttu-id="a2b91-1475">carta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1475">carta</span></span> 
- <span data-ttu-id="a2b91-1476">非の tarjeta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1476">no de tarjeta</span></span> 
- <span data-ttu-id="a2b91-1477">いいえ。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1477">no do cartao</span></span> 
- <span data-ttu-id="a2b91-1478">no do cartão</span><span class="sxs-lookup"><span data-stu-id="a2b91-1478">no do cartão</span></span> 
- <span data-ttu-id="a2b91-p117">no. de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p117">no. de tarjeta</span></span> 
- <span data-ttu-id="a2b91-p118">no. do cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p118">no. do cartao</span></span> 
- <span data-ttu-id="a2b91-p119">no. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p119">no. do cartão</span></span> 
- <span data-ttu-id="a2b91-1485">nr carta</span><span class="sxs-lookup"><span data-stu-id="a2b91-1485">nr carta</span></span> 
- <span data-ttu-id="a2b91-p120">nr. carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p120">nr. carta</span></span> 
- <span data-ttu-id="a2b91-1488">numeri di scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1488">numeri di scheda</span></span> 
- <span data-ttu-id="a2b91-1489">numero carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1489">numero carta</span></span> 
- <span data-ttu-id="a2b91-1490">numero de cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1490">numero de cartao</span></span> 
- <span data-ttu-id="a2b91-1491">numero de carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1491">numero de carte</span></span> 
- <span data-ttu-id="a2b91-1492">numero de cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1492">numero de cartão</span></span> 
- <span data-ttu-id="a2b91-1493">numero de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1493">numero de tarjeta</span></span>
- <span data-ttu-id="a2b91-1494">numero della carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1494">numero della carta</span></span> 
- <span data-ttu-id="a2b91-1495">numero di carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1495">numero di carta</span></span> 
- <span data-ttu-id="a2b91-1496">numero di scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1496">numero di scheda</span></span> 
- <span data-ttu-id="a2b91-1497">numero do cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1497">numero do cartao</span></span> 
- <span data-ttu-id="a2b91-1498">numero do cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1498">numero do cartão</span></span> 
- <span data-ttu-id="a2b91-1499">numéro de carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1499">numéro de carte</span></span> 
- <span data-ttu-id="a2b91-1500">nº carta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1500">nº carta</span></span> 
- <span data-ttu-id="a2b91-1501">nº de carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1501">nº de carte</span></span> 
- <span data-ttu-id="a2b91-1502">nº de la carte
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1502">nº de la carte</span></span> 
- <span data-ttu-id="a2b91-1503">nº de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1503">nº de tarjeta</span></span> 
- <span data-ttu-id="a2b91-1504">nº do cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1504">nº do cartao</span></span> 
- <span data-ttu-id="a2b91-1505">n ° do cartão</span><span class="sxs-lookup"><span data-stu-id="a2b91-1505">nº do cartão</span></span> 
- <span data-ttu-id="a2b91-p121">nº. do cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p121">nº. do cartão</span></span> 
- <span data-ttu-id="a2b91-1508">número de cartao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1508">número de cartao</span></span> 
- <span data-ttu-id="a2b91-1509">número de cartão
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1509">número de cartão</span></span> 
- <span data-ttu-id="a2b91-1510">número de tarjeta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1510">número de tarjeta</span></span> 
- <span data-ttu-id="a2b91-1511">número do cartao</span><span class="sxs-lookup"><span data-stu-id="a2b91-1511">número do cartao</span></span> 
- <span data-ttu-id="a2b91-1512">scheda dell'assegno
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1512">scheda dell'assegno</span></span> 
- <span data-ttu-id="a2b91-1513">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1513">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a2b91-1514">scheda dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1514">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="a2b91-1515">scheda della banca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1515">scheda della banca</span></span> 
- <span data-ttu-id="a2b91-1516">scheda di controllo
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1516">scheda di controllo</span></span> 
- <span data-ttu-id="a2b91-1517">scheda di debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1517">scheda di debito</span></span> 
- <span data-ttu-id="a2b91-1518">scheda matrice
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1518">scheda matrice</span></span> 
- <span data-ttu-id="a2b91-1519">schede dell'atmosfera
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1519">schede dell'atmosfera</span></span> 
- <span data-ttu-id="a2b91-1520">schede di controllo
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1520">schede di controllo</span></span> 
- <span data-ttu-id="a2b91-1521">schede di debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1521">schede di debito</span></span> 
- <span data-ttu-id="a2b91-1522">schede matrici
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1522">schede matrici</span></span> 
- <span data-ttu-id="a2b91-1523">scoprono la scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1523">scoprono la scheda</span></span> 
- <span data-ttu-id="a2b91-1524">scoprono le schede
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1524">scoprono le schede</span></span> 
- <span data-ttu-id="a2b91-1525">solo
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1525">solo</span></span> 
- <span data-ttu-id="a2b91-1526">supporti di scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1526">supporti di scheda</span></span> 
- <span data-ttu-id="a2b91-1527">supporto di scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1527">supporto di scheda</span></span> 
- <span data-ttu-id="a2b91-1528">switch
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1528">switch</span></span> 
- <span data-ttu-id="a2b91-1529">tarjeta atm
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1529">tarjeta atm</span></span> 
- <span data-ttu-id="a2b91-1530">tarjeta credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1530">tarjeta credito</span></span> 
- <span data-ttu-id="a2b91-1531">tarjeta de atm
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1531">tarjeta de atm</span></span> 
- <span data-ttu-id="a2b91-1532">tarjeta de credito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1532">tarjeta de credito</span></span> 
- <span data-ttu-id="a2b91-1533">tarjeta de debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1533">tarjeta de debito</span></span> 
- <span data-ttu-id="a2b91-1534">tarjeta debito
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1534">tarjeta debito</span></span> 
- <span data-ttu-id="a2b91-1535">tarjeta no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1535">tarjeta no</span></span>
- <span data-ttu-id="a2b91-1536">tarjetahabiente
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1536">tarjetahabiente</span></span> 
- <span data-ttu-id="a2b91-1537">tipo della scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1537">tipo della scheda</span></span> 
- <span data-ttu-id="a2b91-1538">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="a2b91-1538">ufficio giapponese della</span></span> 
- <span data-ttu-id="a2b91-1539">scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1539">scheda</span></span> 
- <span data-ttu-id="a2b91-1540">v pay
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1540">v pay</span></span> 
- <span data-ttu-id="a2b91-1541">v-支払い</span><span class="sxs-lookup"><span data-stu-id="a2b91-1541">v-pay</span></span> 
- <span data-ttu-id="a2b91-1542">visa
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1542">visa</span></span> 
- <span data-ttu-id="a2b91-1543">visa plus
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1543">visa plus</span></span> 
- <span data-ttu-id="a2b91-1544">visa electron
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1544">visa electron</span></span> 
- <span data-ttu-id="a2b91-1545">visto
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1545">visto</span></span> 
- <span data-ttu-id="a2b91-1546">visum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1546">visum</span></span> 
- <span data-ttu-id="a2b91-1547">vpay
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1547">vpay</span></span>   

#### <a name="keywordcardsecuritytermsdict"></a><span data-ttu-id="a2b91-1548">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a2b91-1548">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="a2b91-1549">card identification number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1549">card identification number</span></span>
- <span data-ttu-id="a2b91-1550">card verification</span><span class="sxs-lookup"><span data-stu-id="a2b91-1550">card verification</span></span> 
- <span data-ttu-id="a2b91-1551">cardi la verifica
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1551">cardi la verifica</span></span> 
- <span data-ttu-id="a2b91-1552">cid
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1552">cid</span></span> 
- <span data-ttu-id="a2b91-1553">cod セグメント</span><span class="sxs-lookup"><span data-stu-id="a2b91-1553">cod seg</span></span> 
- <span data-ttu-id="a2b91-1554">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="a2b91-1554">cod seguranca</span></span> 
- <span data-ttu-id="a2b91-1555">cod segurança</span><span class="sxs-lookup"><span data-stu-id="a2b91-1555">cod segurança</span></span> 
- <span data-ttu-id="a2b91-1556">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="a2b91-1556">cod sicurezza</span></span> 
- <span data-ttu-id="a2b91-p122">cod. seg
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p122">cod. seg</span></span> 
- <span data-ttu-id="a2b91-p123">cod. seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p123">cod. seguranca</span></span> 
- <span data-ttu-id="a2b91-p124">cod. segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p124">cod. segurança</span></span> 
- <span data-ttu-id="a2b91-p125">cod. sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p125">cod. sicurezza</span></span> 
- <span data-ttu-id="a2b91-1565">codice di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1565">codice di sicurezza</span></span> 
- <span data-ttu-id="a2b91-1566">codice di verifica
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1566">codice di verifica</span></span> 
- <span data-ttu-id="a2b91-1567">codigo
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1567">codigo</span></span> 
- <span data-ttu-id="a2b91-1568">codigo de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1568">codigo de seguranca</span></span> 
- <span data-ttu-id="a2b91-1569">codigo de segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1569">codigo de segurança</span></span> 
- <span data-ttu-id="a2b91-1570">crittogramma
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1570">crittogramma</span></span> 
- <span data-ttu-id="a2b91-1571">cryptogram
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1571">cryptogram</span></span> 
- <span data-ttu-id="a2b91-1572">cryptogramme
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1572">cryptogramme</span></span> 
- <span data-ttu-id="a2b91-1573">cv2</span><span class="sxs-lookup"><span data-stu-id="a2b91-1573">cv2</span></span> 
- <span data-ttu-id="a2b91-1574">cvc
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1574">cvc</span></span> 
- <span data-ttu-id="a2b91-1575">cvc2</span><span class="sxs-lookup"><span data-stu-id="a2b91-1575">cvc2</span></span> 
- <span data-ttu-id="a2b91-1576">cvn
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1576">cvn</span></span> 
- <span data-ttu-id="a2b91-1577">cvv
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1577">cvv</span></span> 
- <span data-ttu-id="a2b91-1578">cvv2</span><span class="sxs-lookup"><span data-stu-id="a2b91-1578">cvv2</span></span> 
- <span data-ttu-id="a2b91-1579">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="a2b91-1579">cód seguranca</span></span> 
- <span data-ttu-id="a2b91-1580">cód segurança</span><span class="sxs-lookup"><span data-stu-id="a2b91-1580">cód segurança</span></span> 
- <span data-ttu-id="a2b91-p126">cód. seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p126">cód. seguranca</span></span> 
- <span data-ttu-id="a2b91-p127">cód. segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p127">cód. segurança</span></span> 
- <span data-ttu-id="a2b91-1585">código
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1585">código</span></span> 
- <span data-ttu-id="a2b91-1586">código de seguranca
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1586">código de seguranca</span></span> 
- <span data-ttu-id="a2b91-1587">código de segurança
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1587">código de segurança</span></span> 
- <span data-ttu-id="a2b91-1588">de kaart controle
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1588">de kaart controle</span></span> 
- <span data-ttu-id="a2b91-1589">geeft nr uit
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1589">geeft nr uit</span></span> 
- <span data-ttu-id="a2b91-1590">issue no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1590">issue no</span></span> 
- <span data-ttu-id="a2b91-1591">issue number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1591">issue number</span></span> 
- <span data-ttu-id="a2b91-1592">kaartidentificatienummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1592">kaartidentificatienummer</span></span> 
- <span data-ttu-id="a2b91-1593">kreditkartenprufnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1593">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="a2b91-1594">kreditkartenprüfnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1594">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="a2b91-1595">kwestieaantal
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1595">kwestieaantal</span></span> 
- <span data-ttu-id="a2b91-p128">no. dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p128">no. dell'edizione</span></span> 
- <span data-ttu-id="a2b91-p129">no. di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p129">no. di sicurezza</span></span> 
- <span data-ttu-id="a2b91-1600">numero de securite
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1600">numero de securite</span></span> 
- <span data-ttu-id="a2b91-1601">numero de verificacao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1601">numero de verificacao</span></span> 
- <span data-ttu-id="a2b91-1602">numero dell'edizione
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1602">numero dell'edizione</span></span> 
- <span data-ttu-id="a2b91-1603">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="a2b91-1603">numero di identificazione della</span></span> 
- <span data-ttu-id="a2b91-1604">scheda
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1604">scheda</span></span> 
- <span data-ttu-id="a2b91-1605">numero di sicurezza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1605">numero di sicurezza</span></span> 
- <span data-ttu-id="a2b91-1606">numero van veiligheid
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1606">numero van veiligheid</span></span> 
- <span data-ttu-id="a2b91-1607">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1607">numéro de sécurité</span></span> 
- <span data-ttu-id="a2b91-1608">nº autorizzazione
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1608">nº autorizzazione</span></span> 
- <span data-ttu-id="a2b91-1609">número de verificação
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1609">número de verificação</span></span> 
- <span data-ttu-id="a2b91-1610">perno il blocco
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1610">perno il blocco</span></span> 
- <span data-ttu-id="a2b91-1611">pin block
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1611">pin block</span></span> 
- <span data-ttu-id="a2b91-1612">prufziffer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1612">prufziffer</span></span> 
- <span data-ttu-id="a2b91-1613">prüfziffer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1613">prüfziffer</span></span> 
- <span data-ttu-id="a2b91-1614">security code
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1614">security code</span></span> 
- <span data-ttu-id="a2b91-1615">security no
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1615">security no</span></span> 
- <span data-ttu-id="a2b91-1616">security number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1616">security number</span></span> 
- <span data-ttu-id="a2b91-1617">sicherheits kode
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1617">sicherheits kode</span></span> 
- <span data-ttu-id="a2b91-1618">sicherheitscode
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1618">sicherheitscode</span></span> 
- <span data-ttu-id="a2b91-1619">sicherheitsnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1619">sicherheitsnummer</span></span> 
- <span data-ttu-id="a2b91-1620">speldblok
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1620">speldblok</span></span> 
- <span data-ttu-id="a2b91-1621">veiligheid nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1621">veiligheid nr</span></span> 
- <span data-ttu-id="a2b91-1622">veiligheidsaantal
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1622">veiligheidsaantal</span></span> 
- <span data-ttu-id="a2b91-1623">veiligheidscode
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1623">veiligheidscode</span></span> 
- <span data-ttu-id="a2b91-1624">veiligheidsnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1624">veiligheidsnummer</span></span> 
- <span data-ttu-id="a2b91-1625">verfalldatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1625">verfalldatum</span></span> 

#### <a name="keywordcardexpirationtermsdict"></a><span data-ttu-id="a2b91-1626">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="a2b91-1626">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="a2b91-1627">ablauf
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1627">ablauf</span></span> 
- <span data-ttu-id="a2b91-1628">data de expiracao
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1628">data de expiracao</span></span> 
- <span data-ttu-id="a2b91-1629">data de expiração
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1629">data de expiração</span></span> 
- <span data-ttu-id="a2b91-1630">data del exp
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1630">data del exp</span></span> 
- <span data-ttu-id="a2b91-1631">data di exp
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1631">data di exp</span></span> 
- <span data-ttu-id="a2b91-1632">data di scadenza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1632">data di scadenza</span></span> 
- <span data-ttu-id="a2b91-1633">data em que expira
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1633">data em que expira</span></span> 
- <span data-ttu-id="a2b91-1634">data scad
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1634">data scad</span></span> 
- <span data-ttu-id="a2b91-1635">data scadenza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1635">data scadenza</span></span> 
- <span data-ttu-id="a2b91-1636">date de validité
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1636">date de validité</span></span> 
- <span data-ttu-id="a2b91-1637">datum afloop
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1637">datum afloop</span></span> 
- <span data-ttu-id="a2b91-1638">datum van exp
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1638">datum van exp</span></span> 
- <span data-ttu-id="a2b91-1639">de afloop
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1639">de afloop</span></span> 
- <span data-ttu-id="a2b91-1640">espira
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1640">espira</span></span> 
- <span data-ttu-id="a2b91-1641">espira
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1641">espira</span></span> 
- <span data-ttu-id="a2b91-1642">exp date
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1642">exp date</span></span> 
- <span data-ttu-id="a2b91-1643">exp datum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1643">exp datum</span></span> 
- <span data-ttu-id="a2b91-1644">nntp</span><span class="sxs-lookup"><span data-stu-id="a2b91-1644">expiration</span></span> 
- <span data-ttu-id="a2b91-1645">expire
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1645">expire</span></span> 
- <span data-ttu-id="a2b91-1646">expires
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1646">expires</span></span> 
- <span data-ttu-id="a2b91-1647">expiry
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1647">expiry</span></span> 
- <span data-ttu-id="a2b91-1648">fecha de expiracion
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1648">fecha de expiracion</span></span> 
- <span data-ttu-id="a2b91-1649">fecha de venc
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1649">fecha de venc</span></span> 
- <span data-ttu-id="a2b91-1650">gultig bis
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1650">gultig bis</span></span> 
- <span data-ttu-id="a2b91-1651">gultigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1651">gultigkeitsdatum</span></span> 
- <span data-ttu-id="a2b91-1652">gültig bis
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1652">gültig bis</span></span> 
- <span data-ttu-id="a2b91-1653">gültigkeitsdatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1653">gültigkeitsdatum</span></span> 
- <span data-ttu-id="a2b91-1654">la scadenza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1654">la scadenza</span></span> 
- <span data-ttu-id="a2b91-1655">scadenza
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1655">scadenza</span></span> 
- <span data-ttu-id="a2b91-1656">valable
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1656">valable</span></span> 
- <span data-ttu-id="a2b91-1657">validade
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1657">validade</span></span> 
- <span data-ttu-id="a2b91-1658">valido hasta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1658">valido hasta</span></span> 
- <span data-ttu-id="a2b91-1659">valor
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1659">valor</span></span> 
- <span data-ttu-id="a2b91-1660">venc
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1660">venc</span></span> 
- <span data-ttu-id="a2b91-1661">vencimento
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1661">vencimento</span></span> 
- <span data-ttu-id="a2b91-1662">vencimiento
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1662">vencimiento</span></span> 
- <span data-ttu-id="a2b91-1663">verloopt
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1663">verloopt</span></span> 
- <span data-ttu-id="a2b91-1664">vervaldag
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1664">vervaldag</span></span> 
- <span data-ttu-id="a2b91-1665">vervaldatum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1665">vervaldatum</span></span> 
- <span data-ttu-id="a2b91-1666">vto
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1666">vto</span></span> 
- <span data-ttu-id="a2b91-1667">válido hasta
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1667">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="a2b91-1668">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1668">EU Driver's License Number</span></span>

<span data-ttu-id="a2b91-1669">詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1669">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="a2b91-1670">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1670">EU National Identification Number</span></span>

<span data-ttu-id="a2b91-1671">詳細については、「 [EU 国立 id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1671">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="a2b91-1672">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1672">EU Passport Number</span></span>

<span data-ttu-id="a2b91-1673">詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1673">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="a2b91-1674">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-1674">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="a2b91-1675">詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1675">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="a2b91-1676">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1676">EU Tax Identification Number</span></span>

<span data-ttu-id="a2b91-1677">詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1677">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="a2b91-1678">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-1678">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1679">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1679">Format</span></span>

<span data-ttu-id="a2b91-1680">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a2b91-1680">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1681">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1681">Pattern</span></span>

<span data-ttu-id="a2b91-1682">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1682">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a2b91-1683">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1683">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="a2b91-1684">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1684">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="a2b91-1685">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1685">Three-digit personal identification number</span></span> 
- <span data-ttu-id="a2b91-1686">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1686">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1687">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1687">Checksum</span></span>

<span data-ttu-id="a2b91-1688">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1688">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1689">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1689">Definition</span></span>

<span data-ttu-id="a2b91-1690">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1690">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1691">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1691">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1692">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1692">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="a2b91-1693">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1693">The checksum passes.</span></span>

```
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1694">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1694">Keywords</span></span>

- <span data-ttu-id="a2b91-1695">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-1695">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="a2b91-1696">

Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="a2b91-1696">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="a2b91-1697">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="a2b91-1697">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="a2b91-1698">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="a2b91-1698">Personbeteckning</span></span>
- <span data-ttu-id="a2b91-1699">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1699">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="a2b91-1700">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1700">Finland Passport Number</span></span>

<span data-ttu-id="a2b91-p130">次の9つの文字と数字のパターンの組み合わせを書式設定します。9桁の文字 (大文字小文字を区別しない)、7桁のチェックサムを定義しません。 DLP ポリシーは 75% で、この種類の機密情報がある場合に、300文字の近接性: 正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検出します。Keyword_finland_passport_number からのキーワードが見つかりました。キーワード Keyword_finland_passport_number <!-- Finland Passport Number --> 
 <Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern> 
 </Entity></span><span class="sxs-lookup"><span data-stu-id="a2b91-p130">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern. A keyword from Keyword_finland_passport_number is found. <!-- Finland Passport Number -->
<Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity> Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="a2b91-1705">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1705">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1706">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1706">Format</span></span>

<span data-ttu-id="a2b91-1707">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1707">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1708">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1708">Pattern</span></span>

<span data-ttu-id="a2b91-1709">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1709">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1710">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1710">Checksum</span></span>

<span data-ttu-id="a2b91-1711">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1711">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1712">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-1712">Definition</span></span>

<span data-ttu-id="a2b91-1713">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1713">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1714">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1714">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1715">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1715">At least one of the following is true:</span></span>
- <span data-ttu-id="a2b91-1716">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1716">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="a2b91-1717">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1717">The function Func_eu_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1718">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1718">Keywords</span></span>

#### <a name="keywordfrenchdriverslicense"></a><span data-ttu-id="a2b91-1719">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a2b91-1719">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="a2b91-1720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="a2b91-1720">drivers licence</span></span>
- <span data-ttu-id="a2b91-1721">drivers license</span><span class="sxs-lookup"><span data-stu-id="a2b91-1721">drivers license</span></span>
- <span data-ttu-id="a2b91-1722">driving licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1722">driving licence</span></span>
- <span data-ttu-id="a2b91-1723">ライセンスの駆動</span><span class="sxs-lookup"><span data-stu-id="a2b91-1723">driving license</span></span>
- <span data-ttu-id="a2b91-1724">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="a2b91-1724">permis de conduire</span></span>
- <span data-ttu-id="a2b91-1725">
licence number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1725">licence number</span></span>
- <span data-ttu-id="a2b91-1726">
license number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1726">license number</span></span>
- <span data-ttu-id="a2b91-1727">
licence numbers</span><span class="sxs-lookup"><span data-stu-id="a2b91-1727">licence numbers</span></span>
- <span data-ttu-id="a2b91-1728">

license numbers</span><span class="sxs-lookup"><span data-stu-id="a2b91-1728">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="a2b91-1729">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1729">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1730">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1730">Format</span></span>

<span data-ttu-id="a2b91-1731">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1731">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1732">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1732">Pattern</span></span>

<span data-ttu-id="a2b91-1733">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1733">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1734">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1734">Checksum</span></span>

<span data-ttu-id="a2b91-1735">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1735">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1736">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1736">Definition</span></span>

<span data-ttu-id="a2b91-1737">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1737">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1738">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1738">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1739">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1739">Keywords</span></span>

<span data-ttu-id="a2b91-1740">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1740">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="a2b91-1741">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1741">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1742">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1742">Format</span></span>

<span data-ttu-id="a2b91-1743">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1743">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1744">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1744">Pattern</span></span>

<span data-ttu-id="a2b91-1745">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1745">Nine digits and letters:</span></span>
- <span data-ttu-id="a2b91-1746">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1746">Two digits</span></span> 
- <span data-ttu-id="a2b91-1747">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-1747">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-1748">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1748">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1749">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1749">Checksum</span></span>

<span data-ttu-id="a2b91-1750">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1750">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1751">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-1751">Definition</span></span>

<span data-ttu-id="a2b91-1752">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1752">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1753">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1753">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1754">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1754">A keyword from Keyword_passport is found.</span></span>

```
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1755">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1755">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a2b91-1756">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-1756">Keyword_passport</span></span>

- <span data-ttu-id="a2b91-1757">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1757">Passport Number</span></span>
- <span data-ttu-id="a2b91-1758">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a2b91-1758">Passport No</span></span>
- <span data-ttu-id="a2b91-1759">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1759">Passport #</span></span>
- <span data-ttu-id="a2b91-1760">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1760">Passport#</span></span>
- <span data-ttu-id="a2b91-1761">PassportID</span><span class="sxs-lookup"><span data-stu-id="a2b91-1761">PassportID</span></span>
- <span data-ttu-id="a2b91-1762">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1762">Passportno</span></span>
- <span data-ttu-id="a2b91-1763">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1763">passportnumber</span></span>
- <span data-ttu-id="a2b91-1764">パスポート</span><span class="sxs-lookup"><span data-stu-id="a2b91-1764">パスポート</span></span>
- <span data-ttu-id="a2b91-1765">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1765">パスポート番号</span></span>
- <span data-ttu-id="a2b91-1766">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1766">パスポートのNum</span></span>
- <span data-ttu-id="a2b91-1767">
パスポート ＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1767">パスポート ＃</span></span> 
- <span data-ttu-id="a2b91-1768">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a2b91-1768">Numéro de passeport</span></span>
- <span data-ttu-id="a2b91-1769">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a2b91-1769">Passeport n °</span></span>
- <span data-ttu-id="a2b91-1770">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1770">Passeport Non</span></span>
- <span data-ttu-id="a2b91-1771">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1771">Passeport #</span></span>
- <span data-ttu-id="a2b91-1772">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1772">Passeport#</span></span>
- <span data-ttu-id="a2b91-1773">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a2b91-1773">PasseportNon</span></span>
- <span data-ttu-id="a2b91-1774">

Passeportn °</span><span class="sxs-lookup"><span data-stu-id="a2b91-1774">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="a2b91-1775">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1775">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1776">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1776">Format</span></span>

<span data-ttu-id="a2b91-1777">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1777">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1778">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1778">Pattern</span></span>

<span data-ttu-id="a2b91-1779">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1779">Must match one of two patterns:</span></span>
- <span data-ttu-id="a2b91-1780">13桁の数字の後にスペースを続け、2桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1780">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="a2b91-1781">または</span><span class="sxs-lookup"><span data-stu-id="a2b91-1781">or</span></span>
- <span data-ttu-id="a2b91-1782">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1782">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1783">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1783">Checksum</span></span>

<span data-ttu-id="a2b91-1784">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1784">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1785">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1785">Definition</span></span>

<span data-ttu-id="a2b91-1786">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1786">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1787">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1787">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1788">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1788">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a2b91-1789">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1789">The checksum passes.</span></span>

<span data-ttu-id="a2b91-1790">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1790">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1791">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1791">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1792">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1792">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="a2b91-1793">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1793">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1794">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1794">Keywords</span></span>

#### <a name="keywordfrinsee"></a><span data-ttu-id="a2b91-1795">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="a2b91-1795">Keyword_fr_insee</span></span>

- <span data-ttu-id="a2b91-1796">insee</span><span class="sxs-lookup"><span data-stu-id="a2b91-1796">insee</span></span>
- <span data-ttu-id="a2b91-1797">
securité sociale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1797">securité sociale</span></span>
- <span data-ttu-id="a2b91-1798">
securite sociale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1798">securite sociale</span></span>
- <span data-ttu-id="a2b91-1799">
national id</span><span class="sxs-lookup"><span data-stu-id="a2b91-1799">national id</span></span>
- <span data-ttu-id="a2b91-1800">
national identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-1800">national identification</span></span>
- <span data-ttu-id="a2b91-1801">
numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="a2b91-1801">numéro d'identité</span></span>
- <span data-ttu-id="a2b91-1802">d'identitéなし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1802">no d'identité</span></span>
- <span data-ttu-id="a2b91-p131">
no. d'identité</span><span class="sxs-lookup"><span data-stu-id="a2b91-p131">no. d'identité</span></span>
- <span data-ttu-id="a2b91-1805">
numero d'identite</span><span class="sxs-lookup"><span data-stu-id="a2b91-1805">numero d'identite</span></span>
- <span data-ttu-id="a2b91-1806">d'identite なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1806">no d'identite</span></span>
- <span data-ttu-id="a2b91-p132">
no. d'identite</span><span class="sxs-lookup"><span data-stu-id="a2b91-p132">no. d'identite</span></span>
- <span data-ttu-id="a2b91-1809">social security number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1809">social security number</span></span>
- <span data-ttu-id="a2b91-1810">
social security code</span><span class="sxs-lookup"><span data-stu-id="a2b91-1810">social security code</span></span>
- <span data-ttu-id="a2b91-1811">social insurance number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1811">social insurance number</span></span>
- <span data-ttu-id="a2b91-1812">
le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1812">le numéro d'identification nationale</span></span>
- <span data-ttu-id="a2b91-1813">
d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1813">d'identité nationale</span></span>
- <span data-ttu-id="a2b91-1814">
numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1814">numéro de sécurité sociale</span></span>
- <span data-ttu-id="a2b91-1815">
le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1815">le code de la sécurité sociale</span></span>
- <span data-ttu-id="a2b91-1816">
numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="a2b91-1816">numéro d'assurance sociale</span></span>
- <span data-ttu-id="a2b91-1817">
numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="a2b91-1817">numéro de sécu</span></span>
- <span data-ttu-id="a2b91-1818">
code sécu
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1818">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="a2b91-1819">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1819">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1820">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1820">Format</span></span>

<span data-ttu-id="a2b91-1821">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="a2b91-1821">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1822">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1822">Pattern</span></span>

<span data-ttu-id="a2b91-1823">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="a2b91-1823">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="a2b91-1824">1 桁の数字または文字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-1824">A digit or letter</span></span> 
- <span data-ttu-id="a2b91-1825">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1825">Two digits</span></span> 
- <span data-ttu-id="a2b91-1826">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1826">Six digits or letters</span></span> 
- <span data-ttu-id="a2b91-1827">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1827">A digit</span></span> 
- <span data-ttu-id="a2b91-1828">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1828">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1829">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1829">Checksum</span></span>

<span data-ttu-id="a2b91-1830">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1830">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1831">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1831">Definition</span></span>

<span data-ttu-id="a2b91-1832">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1833">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1833">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1834">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1834">At least one of the following is true:</span></span>
    - <span data-ttu-id="a2b91-1835">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1835">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="a2b91-1836">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1836">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="a2b91-1837">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1837">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="a2b91-1838">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1838">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1839">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1839">Keywords</span></span>

#### <a name="keywordgermandriverslicensenumber"></a><span data-ttu-id="a2b91-1840">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1840">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="a2b91-1841">Führerschein</span><span class="sxs-lookup"><span data-stu-id="a2b91-1841">Führerschein</span></span>
- <span data-ttu-id="a2b91-1842">
Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="a2b91-1842">Fuhrerschein</span></span>
- <span data-ttu-id="a2b91-1843">futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="a2b91-1843">Fuehrerschein</span></span>
- <span data-ttu-id="a2b91-1844">
Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1844">Führerscheinnummer</span></span>
- <span data-ttu-id="a2b91-1845">
Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1845">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="a2b91-1846">
Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1846">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="a2b91-1847">
Führerschein-
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1847">Führerschein-</span></span> 
- <span data-ttu-id="a2b91-1848">Fuhrerschein-
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1848">Fuhrerschein-</span></span> 
- <span data-ttu-id="a2b91-1849">Fuehrerschein-
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1849">Fuehrerschein-</span></span> 
- <span data-ttu-id="a2b91-1850">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a2b91-1850">FührerscheinnummerNr</span></span>
- <span data-ttu-id="a2b91-1851">futex がある hていません einnumnr</span><span class="sxs-lookup"><span data-stu-id="a2b91-1851">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="a2b91-1852">futex の ehの再リリース/einnumnr</span><span class="sxs-lookup"><span data-stu-id="a2b91-1852">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="a2b91-1853">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1853">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="a2b91-1854">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1854">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a2b91-1855">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1855">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="a2b91-1856">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1856">Führerschein- Nr</span></span>
- <span data-ttu-id="a2b91-1857">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1857">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="a2b91-1858">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1858">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a2b91-1859">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1859">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a2b91-1860">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1860">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a2b91-1861">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1861">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="a2b91-1862">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="a2b91-1862">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="a2b91-1863">futex がある hていません einnumnr</span><span class="sxs-lookup"><span data-stu-id="a2b91-1863">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="a2b91-1864">futex の ehの再リリース/einnumnr</span><span class="sxs-lookup"><span data-stu-id="a2b91-1864">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="a2b91-1865">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1865">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a2b91-1866">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1866">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a2b91-1867">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1867">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="a2b91-1868">Führerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1868">Führerschein- Nr</span></span> 
- <span data-ttu-id="a2b91-1869">Fuhrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1869">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="a2b91-1870">Fuehrerschein- Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1870">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="a2b91-1871">Führerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1871">Führerschein- Klasse</span></span> 
- <span data-ttu-id="a2b91-1872">Fuhrerschein- Klasse
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1872">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="a2b91-1873">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1873">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="a2b91-1874">DL</span><span class="sxs-lookup"><span data-stu-id="a2b91-1874">DL</span></span> 
- <span data-ttu-id="a2b91-1875">DLS</span><span class="sxs-lookup"><span data-stu-id="a2b91-1875">DLS</span></span>
- <span data-ttu-id="a2b91-1876">
Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1876">Driv Lic</span></span> 
- <span data-ttu-id="a2b91-1877">Driv Licen
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1877">Driv Licen</span></span> 
- <span data-ttu-id="a2b91-1878">Driv License</span><span class="sxs-lookup"><span data-stu-id="a2b91-1878">Driv License</span></span>
- <span data-ttu-id="a2b91-1879">
Driv Licenses
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1879">Driv Licenses</span></span> 
- <span data-ttu-id="a2b91-1880">Driv Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1880">Driv Licence</span></span> 
- <span data-ttu-id="a2b91-1881">Driv Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1881">Driv Licences</span></span> 
- <span data-ttu-id="a2b91-1882">Driv Lic
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1882">Driv Lic</span></span> 
- <span data-ttu-id="a2b91-1883">Driver Licen
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1883">Driver Licen</span></span> 
- <span data-ttu-id="a2b91-1884">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1884">Driver License</span></span> 
- <span data-ttu-id="a2b91-1885">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1885">Driver Licenses</span></span> 
- <span data-ttu-id="a2b91-1886">Driver Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1886">Driver Licence</span></span> 
- <span data-ttu-id="a2b91-1887">Driver Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1887">Driver Licences</span></span> 
- <span data-ttu-id="a2b91-1888">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-1888">Drivers Lic</span></span> 
- <span data-ttu-id="a2b91-1889">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1889">Drivers Licen</span></span> 
- <span data-ttu-id="a2b91-1890">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1890">Drivers License</span></span> 
- <span data-ttu-id="a2b91-1891">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1891">Drivers Licenses</span></span> 
- <span data-ttu-id="a2b91-1892">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1892">Drivers Licence</span></span> 
- <span data-ttu-id="a2b91-1893">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1893">Drivers Licences</span></span> 
- <span data-ttu-id="a2b91-1894">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-1894">Driver's Lic</span></span> 
- <span data-ttu-id="a2b91-1895">Driver's Licen
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1895">Driver's Licen</span></span> 
- <span data-ttu-id="a2b91-1896">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a2b91-1896">Driver's License</span></span> 
- <span data-ttu-id="a2b91-1897">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-1897">Driver's Licenses</span></span> 
- <span data-ttu-id="a2b91-1898">Driver's Licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1898">Driver's Licence</span></span> 
- <span data-ttu-id="a2b91-1899">Driver's Licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1899">Driver's Licences</span></span> 
- <span data-ttu-id="a2b91-1900">Driving Lic
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1900">Driving Lic</span></span> 
- <span data-ttu-id="a2b91-1901">Driving Licen
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1901">Driving Licen</span></span> 
- <span data-ttu-id="a2b91-1902">Driving License
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1902">Driving License</span></span> 
- <span data-ttu-id="a2b91-1903">Driving Licenses
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1903">Driving Licenses</span></span> 
- <span data-ttu-id="a2b91-1904">Driving Licence

</span><span class="sxs-lookup"><span data-stu-id="a2b91-1904">Driving Licence</span></span> 
- <span data-ttu-id="a2b91-1905">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="a2b91-1905">Driving Licences</span></span>

#### <a name="keywordgermandriverslicensecollaborative"></a><span data-ttu-id="a2b91-1906">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="a2b91-1906">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="a2b91-1907">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1907">Nr-Führerschein</span></span> 
- <span data-ttu-id="a2b91-1908">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1908">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a2b91-1909">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1909">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a2b91-1910">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1910">No-Führerschein</span></span> 
- <span data-ttu-id="a2b91-1911">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1911">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a2b91-1912">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1912">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a2b91-1913">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1913">N-Führerschein</span></span> 
- <span data-ttu-id="a2b91-1914">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1914">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a2b91-1915">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a2b91-1915">N-Fuehrerschein</span></span>
- <span data-ttu-id="a2b91-1916">
Nr-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1916">Nr-Führerschein</span></span> 
- <span data-ttu-id="a2b91-1917">Nr-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1917">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="a2b91-1918">Nr-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1918">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="a2b91-1919">No-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1919">No-Führerschein</span></span> 
- <span data-ttu-id="a2b91-1920">No-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1920">No-Fuhrerschein</span></span> 
- <span data-ttu-id="a2b91-1921">No-Fuehrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1921">No-Fuehrerschein</span></span> 
- <span data-ttu-id="a2b91-1922">N-Führerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1922">N-Führerschein</span></span> 
- <span data-ttu-id="a2b91-1923">N-Fuhrerschein
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1923">N-Fuhrerschein</span></span> 
- <span data-ttu-id="a2b91-1924">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="a2b91-1924">N-Fuehrerschein</span></span> 

#### <a name="keywordgermandriverslicense"></a><span data-ttu-id="a2b91-1925">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a2b91-1925">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="a2b91-1926">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a2b91-1926">ausstellungsdatum</span></span>
- <span data-ttu-id="a2b91-1927">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a2b91-1927">ausstellungsort</span></span>
- <span data-ttu-id="a2b91-1928">
ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="a2b91-1928">ausstellende behöde</span></span>
- <span data-ttu-id="a2b91-1929">
ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="a2b91-1929">ausstellende behorde</span></span>
- <span data-ttu-id="a2b91-1930">

ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="a2b91-1930">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="a2b91-1931">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1931">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1932">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1932">Format</span></span>

<span data-ttu-id="a2b91-1933">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1933">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1934">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1934">Pattern</span></span>

<span data-ttu-id="a2b91-1935">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1935">Pattern must include all of the following:</span></span>
- <span data-ttu-id="a2b91-1936">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1936">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="a2b91-1937">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1937">Three digits</span></span> 
- <span data-ttu-id="a2b91-1938">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="a2b91-1938">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="a2b91-1939">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1939">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1940">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1940">Checksum</span></span>

<span data-ttu-id="a2b91-1941">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-1941">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1942">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1942">Definition</span></span>

<span data-ttu-id="a2b91-1943">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1943">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1944">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1944">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1945">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1945">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a2b91-1946">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1946">The checksum passes.</span></span>

<span data-ttu-id="a2b91-1947">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1947">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1948">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1948">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1949">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1949">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="a2b91-1950">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1950">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-1951">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1951">Keywords</span></span>

#### <a name="keywordgermanpassport"></a><span data-ttu-id="a2b91-1952">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-1952">Keyword_german_passport</span></span>

- <span data-ttu-id="a2b91-1953">reisepass</span><span class="sxs-lookup"><span data-stu-id="a2b91-1953">reisepass</span></span>
- <span data-ttu-id="a2b91-1954">
reisepasse</span><span class="sxs-lookup"><span data-stu-id="a2b91-1954">reisepasse</span></span>
- <span data-ttu-id="a2b91-1955">
reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1955">reisepassnummer</span></span>
- <span data-ttu-id="a2b91-1956">passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-1956">passport</span></span>
- <span data-ttu-id="a2b91-1957">

passports</span><span class="sxs-lookup"><span data-stu-id="a2b91-1957">passports</span></span>

#### <a name="keywordgermanpassportcollaborative"></a><span data-ttu-id="a2b91-1958">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="a2b91-1958">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="a2b91-1959">geburtsdatum</span><span class="sxs-lookup"><span data-stu-id="a2b91-1959">geburtsdatum</span></span>
- <span data-ttu-id="a2b91-1960">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="a2b91-1960">ausstellungsdatum</span></span>
- <span data-ttu-id="a2b91-1961">
ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="a2b91-1961">ausstellungsort</span></span>

#### <a name="keywordgermanpassportnumber"></a><span data-ttu-id="a2b91-1962">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-1962">Keyword_german_passport_number</span></span>

<span data-ttu-id="a2b91-1963">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="a2b91-1963">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keywordgermanpassport1"></a><span data-ttu-id="a2b91-1964">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="a2b91-1964">Keyword_german_passport1</span></span>

<span data-ttu-id="a2b91-1965">Reisepass-Nr
</span><span class="sxs-lookup"><span data-stu-id="a2b91-1965">Reisepass-Nr</span></span>

#### <a name="keywordgermanpassport2"></a><span data-ttu-id="a2b91-1966">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="a2b91-1966">Keyword_german_passport2</span></span>

<span data-ttu-id="a2b91-1967">bnationalit</span><span class="sxs-lookup"><span data-stu-id="a2b91-1967">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="a2b91-1968">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-1968">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1969">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1969">Format</span></span>

<span data-ttu-id="a2b91-1970">2010年11月1日以降: 9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1970">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="a2b91-1971">1987年4月1日から2010年10月31日まで:10 桁</span><span class="sxs-lookup"><span data-stu-id="a2b91-1971">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1972">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1972">Pattern</span></span>

<span data-ttu-id="a2b91-1973">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="a2b91-1973">Since 1 November 2010:</span></span>
- <span data-ttu-id="a2b91-1974">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a2b91-1974">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-1975">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1975">Eight digits</span></span>

<span data-ttu-id="a2b91-1976">1987年4月1日から2010年10月31日まで。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1976">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="a2b91-1977">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-1977">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-1978">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-1978">Checksum</span></span>

<span data-ttu-id="a2b91-1979">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-1979">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-1980">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-1980">Definition</span></span>

<span data-ttu-id="a2b91-1981">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1981">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-1982">正規表現 Regex_germany_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1982">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-1983">Keyword_germany_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-1983">A keyword from Keyword_germany_id_card is found.</span></span>

```
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-1984">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1984">Keywords</span></span>

#### <a name="keywordgermanyidcard"></a><span data-ttu-id="a2b91-1985">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-1985">Keyword_germany_id_card</span></span>

- <span data-ttu-id="a2b91-1986">Identity Card</span><span class="sxs-lookup"><span data-stu-id="a2b91-1986">Identity Card</span></span>
- <span data-ttu-id="a2b91-1987">ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-1987">ID</span></span>
- <span data-ttu-id="a2b91-1988">Identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-1988">Identification</span></span>
- <span data-ttu-id="a2b91-1989">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="a2b91-1989">Personalausweis</span></span>
- <span data-ttu-id="a2b91-1990">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-1990">Identifizierungsnummer</span></span>
- <span data-ttu-id="a2b91-1991">Ausweis</span><span class="sxs-lookup"><span data-stu-id="a2b91-1991">Ausweis</span></span>
- <span data-ttu-id="a2b91-1992">Identifikation</span><span class="sxs-lookup"><span data-stu-id="a2b91-1992">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="a2b91-1993">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-1993">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-1994">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-1994">Format</span></span>

<span data-ttu-id="a2b91-1995">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-1995">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-1996">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-1996">Pattern</span></span>

<span data-ttu-id="a2b91-1997">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="a2b91-1997">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="a2b91-1998">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="a2b91-1998">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="a2b91-1999">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-1999">A dash</span></span> 
- <span data-ttu-id="a2b91-2000">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2000">Six digits</span></span>

<span data-ttu-id="a2b91-2001">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="a2b91-2001">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="a2b91-2002">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2002">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="a2b91-2003">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2003">A dash</span></span> 
- <span data-ttu-id="a2b91-2004">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2004">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2005">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2005">Checksum</span></span>

<span data-ttu-id="a2b91-2006">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2006">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2007">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2007">Definition</span></span>

<span data-ttu-id="a2b91-2008">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2008">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2009">正規表現 Regex_greece_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2009">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2010">Keyword_greece_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2010">A keyword from Keyword_greece_id_card is found.</span></span>

```
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2011">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2011">Keywords</span></span>

#### <a name="keywordgreeceidcard"></a><span data-ttu-id="a2b91-2012">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2012">Keyword_greece_id_card</span></span>

- <span data-ttu-id="a2b91-2013">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2013">Greek identity Card</span></span>
- <span data-ttu-id="a2b91-2014">Tautotita</span><span class="sxs-lookup"><span data-stu-id="a2b91-2014">Tautotita</span></span>
- <span data-ttu-id="a2b91-2015">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="a2b91-2015">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="a2b91-2016">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="a2b91-2016">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="a2b91-2017">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2017">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2018">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2018">Format</span></span>

<span data-ttu-id="a2b91-2019">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="a2b91-2019">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2020">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2020">Pattern</span></span>

<span data-ttu-id="a2b91-2021">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2021">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="a2b91-2022">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2022">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2023">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2023">Six digits</span></span> 
- <span data-ttu-id="a2b91-2024">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2024">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2025">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2025">Checksum</span></span>

<span data-ttu-id="a2b91-2026">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2026">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2027">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2027">Definition</span></span>

<span data-ttu-id="a2b91-2028">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2028">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2029">関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2029">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2030">Keyword_hong_kong_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2030">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="a2b91-2031">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2031">The checksum passes.</span></span>

<span data-ttu-id="a2b91-2032">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2032">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2033">関数 Func_hong_kong_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2033">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2034">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2034">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2035">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2035">Keywords</span></span>

#### <a name="keywordhongkongidcard"></a><span data-ttu-id="a2b91-2036">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2036">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="a2b91-2037">香港の id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2037">hong kong identity card</span></span>
- <span data-ttu-id="a2b91-2038">hkidc</span><span class="sxs-lookup"><span data-stu-id="a2b91-2038">HKIDC</span></span>
- <span data-ttu-id="a2b91-2039">id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2039">id card</span></span>
- <span data-ttu-id="a2b91-2040">Identity card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2040">identity card</span></span>
- <span data-ttu-id="a2b91-2041">hk の id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2041">hk identity card</span></span>
- <span data-ttu-id="a2b91-2042">香港特別行政 id</span><span class="sxs-lookup"><span data-stu-id="a2b91-2042">hong kong id</span></span>
- <span data-ttu-id="a2b91-2043">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2043">香港身份證</span></span>
- <span data-ttu-id="a2b91-2044">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2044">香港永久性居民身份證</span></span>
- <span data-ttu-id="a2b91-2045">身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2045">身份證</span></span>
- <span data-ttu-id="a2b91-2046">身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2046">身份証</span></span>
- <span data-ttu-id="a2b91-2047">身分證 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2047">身分證</span></span>
- <span data-ttu-id="a2b91-2048">身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2048">身分証</span></span>
- <span data-ttu-id="a2b91-2049">香港身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2049">香港身份証</span></span>
- <span data-ttu-id="a2b91-2050">香港身分證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2050">香港身分證</span></span>
- <span data-ttu-id="a2b91-2051">香港身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2051">香港身分証</span></span>
- <span data-ttu-id="a2b91-2052">香港身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2052">香港身份證</span></span>
- <span data-ttu-id="a2b91-2053">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2053">香港居民身份證</span></span>
- <span data-ttu-id="a2b91-2054">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2054">香港居民身份証</span></span>
- <span data-ttu-id="a2b91-2055">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2055">香港居民身分證</span></span>
- <span data-ttu-id="a2b91-2056">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2056">香港居民身分証</span></span>
- <span data-ttu-id="a2b91-2057">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2057">香港永久性居民身份証</span></span>
- <span data-ttu-id="a2b91-2058">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2058">香港永久性居民身分證</span></span>
- <span data-ttu-id="a2b91-2059">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2059">香港永久性居民身分証</span></span>
- <span data-ttu-id="a2b91-2060">香港永久性居民身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2060">香港永久性居民身份證</span></span>
- <span data-ttu-id="a2b91-2061">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2061">香港非永久性居民身份證</span></span>
- <span data-ttu-id="a2b91-2062">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2062">香港非永久性居民身份証</span></span>
- <span data-ttu-id="a2b91-2063">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2063">香港非永久性居民身分證</span></span>
- <span data-ttu-id="a2b91-2064">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2064">香港非永久性居民身分証</span></span>
- <span data-ttu-id="a2b91-2065">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2065">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="a2b91-2066">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2066">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="a2b91-2067">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2067">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="a2b91-2068">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2068">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="a2b91-2069">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2069">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="a2b91-2070">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2070">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="a2b91-2071">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="a2b91-2071">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="a2b91-2072">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2072">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="a2b91-2073">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2073">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2074">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2074">Format</span></span>

<span data-ttu-id="a2b91-2075">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2075">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2076">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2076">Pattern</span></span>

<span data-ttu-id="a2b91-2077">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2077">10 letters or digits:</span></span>
- <span data-ttu-id="a2b91-2078">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2078">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2079">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2079">Four digits</span></span> 
- <span data-ttu-id="a2b91-2080">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2080">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2081">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2081">Checksum</span></span>

<span data-ttu-id="a2b91-2082">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2082">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2083">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2083">Definition</span></span>

<span data-ttu-id="a2b91-2084">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2084">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2085">正規表現 Regex_india_permanent_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2085">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2086">Keyword_india_permanent_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2086">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="a2b91-2087">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2087">The checksum passes.</span></span>

```
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2088">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2088">Keywords</span></span>

#### <a name="keywordindiapermanentaccountnumber"></a><span data-ttu-id="a2b91-2089">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2089">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="a2b91-2090">Permanent Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2090">Permanent Account Number</span></span> 
- <span data-ttu-id="a2b91-2091">PAN
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2091">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="a2b91-2092">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2092">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2093">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2093">Format</span></span>

<span data-ttu-id="a2b91-2094">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2094">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2095">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2095">Pattern</span></span>

<span data-ttu-id="a2b91-2096">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2096">12 digits:</span></span>
- <span data-ttu-id="a2b91-2097">4 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2097">Four digits</span></span> 
- <span data-ttu-id="a2b91-2098">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2098">An optional space or dash</span></span> 
- <span data-ttu-id="a2b91-2099">4 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2099">Four digits</span></span> 
- <span data-ttu-id="a2b91-2100">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2100">An optional space or dash</span></span> 
- <span data-ttu-id="a2b91-2101">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a2b91-2101">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2102">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2102">Checksum</span></span>

<span data-ttu-id="a2b91-2103">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2103">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2104">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2104">Definition</span></span>

<span data-ttu-id="a2b91-p133">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。Keyword_india_aadhar からのキーワードが見つかりました。チェックサムが渡されます。DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。チェックサムが渡されます。<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="a2b91-p133">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. A keyword from Keyword_india_aadhar is found. The checksum passes. A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern. The checksum passes. <!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Func_india_aadhaar"/> <Match idRef="Keyword_india_aadhar"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Func_india_aadhaar"/> </Pattern>
</Entity></span></span>

### <a name="keywords"></a><span data-ttu-id="a2b91-2111">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2111">Keywords</span></span>
   
#### <a name="keywordindiaaadhar"></a><span data-ttu-id="a2b91-2112">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="a2b91-2112">Keyword_india_aadhar</span></span>
- <span data-ttu-id="a2b91-2113">Aadhar</span><span class="sxs-lookup"><span data-stu-id="a2b91-2113">Aadhar</span></span>
- <span data-ttu-id="a2b91-2114">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="a2b91-2114">Aadhaar</span></span>
- <span data-ttu-id="a2b91-2115">UID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2115">UID</span></span>
- <span data-ttu-id="a2b91-2116">आधार</span><span class="sxs-lookup"><span data-stu-id="a2b91-2116">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="a2b91-2117">インドネシアの身分証明書 (KTP) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2117">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2118">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2118">Format</span></span>

<span data-ttu-id="a2b91-2119">省略可能なピリオドを含む 16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2119">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2120">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2120">Pattern</span></span>

<span data-ttu-id="a2b91-2121">16 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2121">16 digits:</span></span>
- <span data-ttu-id="a2b91-2122">2 桁の行政区コード </span><span class="sxs-lookup"><span data-stu-id="a2b91-2122">Two-digit province code</span></span> 
- <span data-ttu-id="a2b91-2123">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2123">A period (optional)</span></span> 
- <span data-ttu-id="a2b91-2124">2 桁の行政区または市コード </span><span class="sxs-lookup"><span data-stu-id="a2b91-2124">Two-digit regency or city code</span></span> 
- <span data-ttu-id="a2b91-2125">2 桁の分区コード </span><span class="sxs-lookup"><span data-stu-id="a2b91-2125">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="a2b91-2126">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2126">A period (optional)</span></span> 
- <span data-ttu-id="a2b91-2127">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2127">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-2128">ピリオド 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2128">A period (optional)</span></span> 
- <span data-ttu-id="a2b91-2129">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2129">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2130">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2130">Checksum</span></span>

<span data-ttu-id="a2b91-2131">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2131">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2132">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2132">Definition</span></span>

<span data-ttu-id="a2b91-2133">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2133">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2134">正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2134">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2135">Keyword_indonesia_id_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2135">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="a2b91-2136">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2137">正規表現 Regex_indonesia_id_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2137">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2138">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2138">Keywords</span></span>
   
#### <a name="keywordindonesiaidcard"></a><span data-ttu-id="a2b91-2139">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2139">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="a2b91-2140">KTP</span><span class="sxs-lookup"><span data-stu-id="a2b91-2140">KTP</span></span>
- <span data-ttu-id="a2b91-2141">Kartu Tanda Penduduk
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2141">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="a2b91-2142">Nomor Induk Kependudukan
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2142">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="a2b91-2143">国際銀行口座番号 (IBAN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2143">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2144">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2144">Format</span></span>

<span data-ttu-id="a2b91-2145">国コード (2 文字)、チェック ディジット (2 桁)、bban 番号 (最大 30 文字)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2145">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2146">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2146">Pattern</span></span>

<span data-ttu-id="a2b91-2147">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2147">Pattern must include all of the following:</span></span>

- <span data-ttu-id="a2b91-2148">2 文字の国コード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2148">Two-letter country code</span></span>
- <span data-ttu-id="a2b91-2149">2 桁のチェック ディジット (省略可能なスペースが続く) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2149">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="a2b91-2150">4 個の文字または数字で構成される 1 から 7 個のグループ (スペースで区切ることができる)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2150">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="a2b91-2151">1 ～ 3 個の文字または数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2151">1-3 letters or digits</span></span>

<span data-ttu-id="a2b91-p134">各国の形式は多少異なります。IBAN 機密情報の型は、次の 60 か国をカバーしています。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p134">The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="a2b91-2154">ad、ae、al、at、az、ba、be、bg、bh、ch、cr、cy、cz、de、dk、do、ee、es、fi、fo、fr、gb、ge、gi、gl、gr、hr、hu、ie、il、is、it、kw、kz、lb、li、lt、lu、lv、mc、md、me、mk、mr、mt、mu、nl、no、pl、pt、ro、rs、sa、se、si、sk、sm、tn、tr、vg</span><span class="sxs-lookup"><span data-stu-id="a2b91-2154">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2155">Checksum</span></span>

<span data-ttu-id="a2b91-2156">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2156">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2157">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2157">Definition</span></span>

<span data-ttu-id="a2b91-2158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2158">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2159">関数 Func_iban がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2159">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2160">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2160">The checksum passes.</span></span>

```
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2161">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2161">Keywords</span></span>

<span data-ttu-id="a2b91-2162">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2162">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="a2b91-2163">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a2b91-2163">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2164">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2164">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="a2b91-2165">IPv4:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2165">IPv4:</span></span>
<span data-ttu-id="a2b91-2166">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2166">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="a2b91-2167">IPv6:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2167">IPv6:</span></span>
<span data-ttu-id="a2b91-2168"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2168">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2169">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2169">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2170">Checksum</span><span class="sxs-lookup"><span data-stu-id="a2b91-2170">Checksum</span></span>

<span data-ttu-id="a2b91-2171">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2171">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2172">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2172">Definition</span></span>

<span data-ttu-id="a2b91-2173">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2173">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2174">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2174">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2175">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2175">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a2b91-2176">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2176">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2177">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2177">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2178">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2178">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="a2b91-2179">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2179">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2180">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2180">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2181">Keyword_ipaddress のキーワードが検出されません。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2181">No keyword from Keyword_ipaddress is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2182">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2182">Keywords</span></span>

#### <a name="keywordipaddress"></a><span data-ttu-id="a2b91-2183">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="a2b91-2183">Keyword_ipaddress</span></span>

- <span data-ttu-id="a2b91-2184">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2184">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="a2b91-2185">ip address
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2185">ip address</span></span> 
- <span data-ttu-id="a2b91-2186">ip addresses</span><span class="sxs-lookup"><span data-stu-id="a2b91-2186">ip addresses</span></span>
- <span data-ttu-id="a2b91-2187">internet protocol</span><span class="sxs-lookup"><span data-stu-id="a2b91-2187">internet protocol</span></span>
- <span data-ttu-id="a2b91-2188">
IP-כתובת ה
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2188">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="a2b91-2189">Diseases の国際分類 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2189">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2190">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2190">Format</span></span>

<span data-ttu-id="a2b91-2191">欧文</span><span class="sxs-lookup"><span data-stu-id="a2b91-2191">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2192">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2192">Pattern</span></span>

<span data-ttu-id="a2b91-2193">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2193">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2194">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2194">Checksum</span></span>

<span data-ttu-id="a2b91-2195">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2195">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2196">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2196">Definition</span></span>

<span data-ttu-id="a2b91-2197">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2197">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2198">Dictionary_icd_10_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2198">A keyword from Dictionary_icd_10_cm is found.</span></span>

```
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="a2b91-2199">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2199">Keywords</span></span>

<span data-ttu-id="a2b91-p135">Dictionary_icd_10_cm キーワードディクショナリの用語。 [Diseases、10リビジョン、臨床修正 (icd-10-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p135">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604). This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="a2b91-2202">Diseases の国際分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2202">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2203">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2203">Format</span></span>

<span data-ttu-id="a2b91-2204">欧文</span><span class="sxs-lookup"><span data-stu-id="a2b91-2204">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2205">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2205">Pattern</span></span>

<span data-ttu-id="a2b91-2206">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2206">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2207">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2207">Checksum</span></span>

<span data-ttu-id="a2b91-2208">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2208">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2209">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2209">Definition</span></span>

<span data-ttu-id="a2b91-2210">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2210">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2211">Dictionary_icd_9_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2211">A keyword from Dictionary_icd_9_cm is found.</span></span>

```
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2212">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2212">Keywords</span></span>

<span data-ttu-id="a2b91-p136">Dictionary_icd_9_cm キーワードディクショナリの用語。 [Diseases、9リビジョン、臨床修正 (icd-9-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p136">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605). This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="a2b91-2215">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2215">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2216">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2216">Format</span></span>

<span data-ttu-id="a2b91-2217">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="a2b91-2217">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a2b91-2218">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2218">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="a2b91-2219">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="a2b91-2219">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a2b91-2220">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2220">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2221">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2221">Pattern</span></span>

<span data-ttu-id="a2b91-2222">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="a2b91-2222">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="a2b91-2223">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2223">Seven digits</span></span> 
- <span data-ttu-id="a2b91-2224">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2224">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="a2b91-2225">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="a2b91-2225">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="a2b91-2226">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2226">Seven digits</span></span> 
- <span data-ttu-id="a2b91-2227">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2227">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="a2b91-2228">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2228">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2229">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2229">Checksum</span></span>

<span data-ttu-id="a2b91-2230">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2230">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2231">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2231">Definition</span></span>

<span data-ttu-id="a2b91-2232">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2232">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2233">関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2233">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2234">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2234">One of the following is true:</span></span>
    - <span data-ttu-id="a2b91-2235">Keyword_ireland_pps のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2235">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="a2b91-2236">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2236">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="a2b91-2237">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2237">The checksum passes.</span></span>

<span data-ttu-id="a2b91-2238">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2238">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2239">関数 Func_ireland_pps がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2239">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2240">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2240">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2241">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2241">Keywords</span></span>

#### <a name="keywordirelandpps"></a><span data-ttu-id="a2b91-2242">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="a2b91-2242">Keyword_ireland_pps</span></span>

- <span data-ttu-id="a2b91-2243">Personal Public Service Number 
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2243">Personal Public Service Number</span></span> 
- <span data-ttu-id="a2b91-2244">PPS Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2244">PPS Number</span></span> 
- <span data-ttu-id="a2b91-2245">PPS Num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2245">PPS Num</span></span> 
- <span data-ttu-id="a2b91-2246">PPS No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2246">PPS No.</span></span> 
- <span data-ttu-id="a2b91-2247">PPS #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2247">PPS #</span></span> 
- <span data-ttu-id="a2b91-2248">PPS</span><span class="sxs-lookup"><span data-stu-id="a2b91-2248">PPS#</span></span> 
- <span data-ttu-id="a2b91-2249">PPSN
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2249">PPSN</span></span> 
- <span data-ttu-id="a2b91-2250">Public Services Card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2250">Public Services Card</span></span> 
- <span data-ttu-id="a2b91-2251">Uimhir Phearsanta Seirbhíse Poiblí
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2251">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="a2b91-p137">Uimh.PSP
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p137">Uimh. PSP</span></span> 
- <span data-ttu-id="a2b91-2254">PSP
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2254">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="a2b91-2255">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2255">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2256">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2256">Format</span></span>

<span data-ttu-id="a2b91-2257">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2257">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2258">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2258">Pattern</span></span>

<span data-ttu-id="a2b91-2259">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2259">Formatted:</span></span>
- <span data-ttu-id="a2b91-2260">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2260">Two digits</span></span> 
- <span data-ttu-id="a2b91-2261">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2261">A dash</span></span> 
- <span data-ttu-id="a2b91-2262">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2262">Three digits</span></span> 
- <span data-ttu-id="a2b91-2263">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2263">A dash</span></span> 
- <span data-ttu-id="a2b91-2264">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2264">Eight digits</span></span>

<span data-ttu-id="a2b91-2265">書式設定されていない場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2265">Unformatted:</span></span>
- <span data-ttu-id="a2b91-2266">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2266">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2267">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2267">Checksum</span></span>

<span data-ttu-id="a2b91-2268">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2268">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2269">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2269">Definition</span></span>

<span data-ttu-id="a2b91-2270">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2270">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2271">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2271">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2272">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2272">A keyword from Keyword_israel_bank_account_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2273">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2273">Keywords</span></span>

#### <a name="keywordisraelbankaccountnumber"></a><span data-ttu-id="a2b91-2274">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2274">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="a2b91-2275">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2275">Bank Account Number</span></span> 
- <span data-ttu-id="a2b91-2276">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2276">Bank Account</span></span> 
- <span data-ttu-id="a2b91-2277">Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2277">Account Number</span></span> 
- <span data-ttu-id="a2b91-2278">מספר חשבון בנק
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2278">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="a2b91-2279">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2279">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2280">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2280">Format</span></span>

<span data-ttu-id="a2b91-2281">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2281">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2282">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2282">Pattern</span></span>

<span data-ttu-id="a2b91-2283">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2283">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2284">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2284">Checksum</span></span>

<span data-ttu-id="a2b91-2285">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2285">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2286">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2286">Definition</span></span>

<span data-ttu-id="a2b91-2287">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2288">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2288">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2289">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2289">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="a2b91-2290">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2290">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2291">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2291">Keywords</span></span>

#### <a name="keywordisraelnationalid"></a><span data-ttu-id="a2b91-2292">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2292">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="a2b91-2293">מספר זהות
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2293">מספר זהות</span></span> 
- <span data-ttu-id="a2b91-2294">National ID Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2294">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="a2b91-2295">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2295">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2296">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2296">Format</span></span>

<span data-ttu-id="a2b91-2297">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2297">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2298">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2298">Pattern</span></span>

- <span data-ttu-id="a2b91-2299">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2299">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="a2b91-2300">1 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2300">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2301">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2301">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2302">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2302">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="a2b91-2303">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2303">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2304">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2304">Checksum</span></span>

<span data-ttu-id="a2b91-2305">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2305">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2306">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2306">Definition</span></span>

<span data-ttu-id="a2b91-2307">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2308">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2308">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2309">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2309">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2310">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2310">Keywords</span></span>

#### <a name="keyworditalydriverslicensenumber"></a><span data-ttu-id="a2b91-2311">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2311">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="a2b91-2312">numero di patente di guida
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2312">numero di patente di guida</span></span> 
- <span data-ttu-id="a2b91-2313">patente di guida
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2313">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="a2b91-2314">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2314">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2315">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2315">Format</span></span>

<span data-ttu-id="a2b91-2316">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2316">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2317">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2317">Pattern</span></span>

<span data-ttu-id="a2b91-2318">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2318">Bank account number:</span></span>
- <span data-ttu-id="a2b91-2319">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2319">Seven or eight digits</span></span>
- <span data-ttu-id="a2b91-2320">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2320">Bank account branch code:</span></span>
- <span data-ttu-id="a2b91-2321">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2321">Four digits</span></span> 
- <span data-ttu-id="a2b91-2322">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2322">A space or dash (optional)</span></span> 
- <span data-ttu-id="a2b91-2323">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2323">Three digits</span></span>

<span data-ttu-id="a2b91-2324">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2324">Checksum</span></span>

<span data-ttu-id="a2b91-2325">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2325">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2326">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2326">Definition</span></span>

<span data-ttu-id="a2b91-2327">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2327">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2328">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2328">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2329">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2329">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="a2b91-2330">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2330">One of the following is true:</span></span>
- <span data-ttu-id="a2b91-2331">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2331">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2332">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2332">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="a2b91-2333">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2333">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2334">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2334">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2335">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2335">A keyword from Keyword_jp_bank_account is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2336">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2336">Keywords</span></span>

#### <a name="keywordjpbankaccount"></a><span data-ttu-id="a2b91-2337">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="a2b91-2337">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="a2b91-2338">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2338">Checking Account Number</span></span> 
- <span data-ttu-id="a2b91-2339">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2339">Checking Account</span></span> 
- <span data-ttu-id="a2b91-2340">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2340">Checking Account #</span></span> 
- <span data-ttu-id="a2b91-2341">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2341">Checking Acct Number</span></span> 
- <span data-ttu-id="a2b91-2342">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2342">Checking Acct #</span></span> 
- <span data-ttu-id="a2b91-2343">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2343">Checking Acct No.</span></span> 
- <span data-ttu-id="a2b91-2344">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2344">Checking Account No.</span></span> 
- <span data-ttu-id="a2b91-2345">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2345">Bank Account Number</span></span> 
- <span data-ttu-id="a2b91-2346">Bank Account
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2346">Bank Account</span></span> 
- <span data-ttu-id="a2b91-2347">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2347">Bank Account #</span></span> 
- <span data-ttu-id="a2b91-2348">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2348">Bank Acct Number</span></span> 
- <span data-ttu-id="a2b91-2349">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2349">Bank Acct #</span></span> 
- <span data-ttu-id="a2b91-2350">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2350">Bank Acct No.</span></span> 
- <span data-ttu-id="a2b91-2351">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2351">Bank Account No.</span></span> 
- <span data-ttu-id="a2b91-2352">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2352">Savings Account Number</span></span> 
- <span data-ttu-id="a2b91-2353">預金口座</span><span class="sxs-lookup"><span data-stu-id="a2b91-2353">Savings Account</span></span> 
- <span data-ttu-id="a2b91-2354">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2354">Savings Account #</span></span> 
- <span data-ttu-id="a2b91-2355">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2355">Savings Acct Number</span></span> 
- <span data-ttu-id="a2b91-2356">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2356">Savings Acct #</span></span> 
- <span data-ttu-id="a2b91-2357">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2357">Savings Acct No.</span></span> 
- <span data-ttu-id="a2b91-2358">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2358">Savings Account No.</span></span> 
- <span data-ttu-id="a2b91-2359">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2359">Debit Account Number</span></span> 
- <span data-ttu-id="a2b91-2360">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2360">Debit Account</span></span> 
- <span data-ttu-id="a2b91-2361">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2361">Debit Account #</span></span> 
- <span data-ttu-id="a2b91-2362">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2362">Debit Acct Number</span></span> 
- <span data-ttu-id="a2b91-2363">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2363">Debit Acct #</span></span> 
- <span data-ttu-id="a2b91-2364">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2364">Debit Acct No.</span></span> 
- <span data-ttu-id="a2b91-2365">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2365">Debit Account No.</span></span> 
- <span data-ttu-id="a2b91-2366">口座番号を当座預金口座の確認
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2366">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="a2b91-2367">＃アカウントの確認、勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2367">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="a2b91-2368">＃勘定の確認
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2368">＃勘定の確認</span></span> 
- <span data-ttu-id="a2b91-2369">勘定番号の確認
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2369">勘定番号の確認</span></span> 
- <span data-ttu-id="a2b91-2370">口座番号の確認
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2370">口座番号の確認</span></span> 
- <span data-ttu-id="a2b91-2371">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2371">銀行口座番号</span></span> 
- <span data-ttu-id="a2b91-2372">銀行口座</span><span class="sxs-lookup"><span data-stu-id="a2b91-2372">銀行口座</span></span> 
- <span data-ttu-id="a2b91-2373">銀行口座＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2373">銀行口座＃</span></span> 
- <span data-ttu-id="a2b91-2374">銀行の勘定番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2374">銀行の勘定番号</span></span> 
- <span data-ttu-id="a2b91-2375">銀行のacct＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2375">銀行のacct＃</span></span> 
- <span data-ttu-id="a2b91-2376">銀行の勘定いいえ
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2376">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="a2b91-2377">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2377">銀行口座番号</span></span>
- <span data-ttu-id="a2b91-2378">
普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2378">普通預金口座番号</span></span> 
- <span data-ttu-id="a2b91-2379">預金口座
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2379">預金口座</span></span> 
- <span data-ttu-id="a2b91-2380">貯蓄口座＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2380">貯蓄口座＃</span></span> 
- <span data-ttu-id="a2b91-2381">貯蓄勘定の数
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2381">貯蓄勘定の数</span></span> 
- <span data-ttu-id="a2b91-2382">貯蓄勘定＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2382">貯蓄勘定＃</span></span> 
- <span data-ttu-id="a2b91-2383">貯蓄勘定番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2383">貯蓄勘定番号</span></span> 
- <span data-ttu-id="a2b91-2384">普通預金口座番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2384">普通預金口座番号</span></span> 
- <span data-ttu-id="a2b91-2385">引き落とし口座番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2385">引き落とし口座番号</span></span> 
- <span data-ttu-id="a2b91-2386">口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2386">口座番号</span></span> 
- <span data-ttu-id="a2b91-2387">口座番号＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2387">口座番号＃</span></span> 
- <span data-ttu-id="a2b91-2388">デビットのacct番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2388">デビットのacct番号</span></span> 
- <span data-ttu-id="a2b91-2389">デビット勘定＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2389">デビット勘定＃</span></span> 
- <span data-ttu-id="a2b91-2390">デビットACCTの番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2390">デビットACCTの番号</span></span> 
- <span data-ttu-id="a2b91-2391">デビット口座番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2391">デビット口座番号</span></span> 

#### <a name="keywordjpbankbranchcode"></a><span data-ttu-id="a2b91-2392">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="a2b91-2392">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="a2b91-2393">Otemachi</span><span class="sxs-lookup"><span data-stu-id="a2b91-2393">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="a2b91-2394">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2394">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2395">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2395">Format</span></span>

<span data-ttu-id="a2b91-2396">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2396">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2397">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2397">Pattern</span></span>

<span data-ttu-id="a2b91-2398">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2398">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2399">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2399">Checksum</span></span>

<span data-ttu-id="a2b91-2400">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2400">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2401">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2401">Definition</span></span>

<span data-ttu-id="a2b91-2402">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2402">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2403">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2403">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2404">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2404">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2405">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2405">Keywords</span></span>

#### <a name="keywordjpdriverslicensenumber"></a><span data-ttu-id="a2b91-2406">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2406">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="a2b91-2407">dl#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2407">dl#</span></span> 
- <span data-ttu-id="a2b91-2408">DL</span><span class="sxs-lookup"><span data-stu-id="a2b91-2408">DL＃</span></span> 
- <span data-ttu-id="a2b91-2409">dls#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2409">dls#</span></span> 
- <span data-ttu-id="a2b91-2410">dl</span><span class="sxs-lookup"><span data-stu-id="a2b91-2410">DLS＃</span></span> 
- <span data-ttu-id="a2b91-2411">driver license</span><span class="sxs-lookup"><span data-stu-id="a2b91-2411">driver license</span></span> 
- <span data-ttu-id="a2b91-2412">driver licenses</span><span class="sxs-lookup"><span data-stu-id="a2b91-2412">driver licenses</span></span> 
- <span data-ttu-id="a2b91-2413">drivers license</span><span class="sxs-lookup"><span data-stu-id="a2b91-2413">drivers license</span></span> 
- <span data-ttu-id="a2b91-2414">driver's license</span><span class="sxs-lookup"><span data-stu-id="a2b91-2414">driver's license</span></span> 
- <span data-ttu-id="a2b91-2415">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="a2b91-2415">drivers licenses</span></span> 
- <span data-ttu-id="a2b91-2416">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="a2b91-2416">driver's licenses</span></span> 
- <span data-ttu-id="a2b91-2417">driving licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2417">driving licence</span></span> 
- <span data-ttu-id="a2b91-2418">lic#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2418">lic#</span></span> 
- <span data-ttu-id="a2b91-2419">そして</span><span class="sxs-lookup"><span data-stu-id="a2b91-2419">LIC＃</span></span> 
- <span data-ttu-id="a2b91-2420">lics#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2420">lics#</span></span> 
- <span data-ttu-id="a2b91-2421">状態 id</span><span class="sxs-lookup"><span data-stu-id="a2b91-2421">state id</span></span> 
- <span data-ttu-id="a2b91-2422">state identification
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2422">state identification</span></span> 
- <span data-ttu-id="a2b91-2423">state identification number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2423">state identification number</span></span> 
- <span data-ttu-id="a2b91-2424">低所得国＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2424">低所得国＃</span></span> 
- <span data-ttu-id="a2b91-2425">免許証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2425">免許証</span></span> 
- <span data-ttu-id="a2b91-2426">状態ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2426">状態ID</span></span>
- <span data-ttu-id="a2b91-2427">
状態の識別
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2427">状態の識別</span></span> 
- <span data-ttu-id="a2b91-2428">状態の識別番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2428">状態の識別番号</span></span> 
- <span data-ttu-id="a2b91-2429">運転免許</span><span class="sxs-lookup"><span data-stu-id="a2b91-2429">運転免許</span></span> 
- <span data-ttu-id="a2b91-2430">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a2b91-2430">運転免許証</span></span> 
- <span data-ttu-id="a2b91-2431">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2431">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="a2b91-2432">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2432">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2433">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2433">Format</span></span>

<span data-ttu-id="a2b91-2434">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2434">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2435">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2435">Pattern</span></span>

<span data-ttu-id="a2b91-2436">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2436">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2437">Checksum</span></span>

<span data-ttu-id="a2b91-2438">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2438">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2439">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2439">Definition</span></span>

<span data-ttu-id="a2b91-2440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2441">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2441">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2442">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2442">A keyword from Keyword_jp_passport is found.</span></span>

```
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2443">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2443">Keywords</span></span>

#### <a name="keywordjppassport"></a><span data-ttu-id="a2b91-2444">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-2444">Keyword_jp_passport</span></span>

- <span data-ttu-id="a2b91-2445">パスポート
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2445">パスポート</span></span> 
- <span data-ttu-id="a2b91-2446">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2446">パスポート番号</span></span> 
- <span data-ttu-id="a2b91-2447">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2447">パスポートのNum</span></span> 
- <span data-ttu-id="a2b91-2448">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2448">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="a2b91-2449">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2449">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2450">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2450">Format</span></span>

<span data-ttu-id="a2b91-2451">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2451">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2452">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2452">Pattern</span></span>

<span data-ttu-id="a2b91-2453">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2453">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2454">Checksum</span></span>

<span data-ttu-id="a2b91-2455">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2455">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2456">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2456">Definition</span></span>

<span data-ttu-id="a2b91-2457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2458">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2458">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2459">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2459">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2460">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2460">Keywords</span></span>

#### <a name="keywordjpresidentregistrationnumber"></a><span data-ttu-id="a2b91-2461">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2461">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="a2b91-2462">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2462">Resident Registration Number</span></span>
- <span data-ttu-id="a2b91-2463">Resident Register Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2463">Resident Register Number</span></span> 
- <span data-ttu-id="a2b91-2464">Residents Basic Registry Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2464">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="a2b91-2465">Resident Registration No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2465">Resident Registration No.</span></span> 
- <span data-ttu-id="a2b91-2466">Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2466">Resident Register No.</span></span> 
- <span data-ttu-id="a2b91-2467">Residents Basic Registry No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2467">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="a2b91-2468">Basic Resident Register No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2468">Basic Resident Register No.</span></span> 
- <span data-ttu-id="a2b91-2469">住民登録番号、登録番号をレジデント
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2469">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="a2b91-2470">住民基本登録番号、登録番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2470">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="a2b91-2471">住民基本レジストリ番号を常駐
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2471">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="a2b91-2472">登録番号を常駐住民基本台帳登録番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2472">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="a2b91-2473">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2473">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2474">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2474">Format</span></span>

<span data-ttu-id="a2b91-2475">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2475">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2476">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2476">Pattern</span></span>

<span data-ttu-id="a2b91-2477">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2477">7-12 digits:</span></span>
- <span data-ttu-id="a2b91-2478">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2478">Four digits</span></span> 
- <span data-ttu-id="a2b91-2479">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2479">A hyphen (optional)</span></span> 
- <span data-ttu-id="a2b91-2480">6桁の数字または</span><span class="sxs-lookup"><span data-stu-id="a2b91-2480">Six digits OR</span></span>
- <span data-ttu-id="a2b91-2481">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2481">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2482">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2482">Checksum</span></span>

<span data-ttu-id="a2b91-2483">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2483">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2484">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2484">Definition</span></span>

<span data-ttu-id="a2b91-2485">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2485">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2486">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2486">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2487">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2487">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="a2b91-2488">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2488">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2489">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2489">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2490">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2490">A keyword from Keyword_jp_sin is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2491">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2491">Keywords</span></span>

#### <a name="keywordjpsin"></a><span data-ttu-id="a2b91-2492">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="a2b91-2492">Keyword_jp_sin</span></span>

- <span data-ttu-id="a2b91-2493">Social Insurance No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2493">Social Insurance No.</span></span> 
- <span data-ttu-id="a2b91-2494">Social Insurance Num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2494">Social Insurance Num</span></span> 
- <span data-ttu-id="a2b91-2495">Social Insurance Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2495">Social Insurance Number</span></span> 
- <span data-ttu-id="a2b91-2496">社会保険のテンキー
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2496">社会保険のテンキー</span></span> 
- <span data-ttu-id="a2b91-2497">社会保険番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2497">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="a2b91-2498">日本の居住カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2498">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2499">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2499">Format</span></span>

<span data-ttu-id="a2b91-2500">12桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2500">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2501">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2501">Pattern</span></span>

<span data-ttu-id="a2b91-2502">12桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2502">12 letters and digits:</span></span>
- <span data-ttu-id="a2b91-2503">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2503">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="a2b91-2504">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2504">Eight digits</span></span> 
- <span data-ttu-id="a2b91-2505">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2505">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2506">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2506">Checksum</span></span>

<span data-ttu-id="a2b91-2507">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2507">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2508">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2508">Definition</span></span>

<span data-ttu-id="a2b91-2509">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2509">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2510">正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2510">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2511">Keyword_jp_residence_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2511">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2512">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2512">Keywords</span></span>

#### <a name="keywordjpresidencecardnumber"></a><span data-ttu-id="a2b91-2513">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2513">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="a2b91-2514">居住カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2514">Residence card number</span></span>
- <span data-ttu-id="a2b91-2515">住居カードなし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2515">Residence card no</span></span>
- <span data-ttu-id="a2b91-2516">住居カード #</span><span class="sxs-lookup"><span data-stu-id="a2b91-2516">Residence card #</span></span>
- <span data-ttu-id="a2b91-2517">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2517">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="a2b91-2518">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2518">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2519">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2519">Format</span></span>

<span data-ttu-id="a2b91-2520">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2520">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2521">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2521">Pattern</span></span>

<span data-ttu-id="a2b91-2522">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2522">12 digits:</span></span>
- <span data-ttu-id="a2b91-2523">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2523">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-2524">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2524">A dash (optional)</span></span> 
- <span data-ttu-id="a2b91-2525">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2525">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="a2b91-2526">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2526">A dash (optional)</span></span> 
- <span data-ttu-id="a2b91-2527">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2527">Three random digits</span></span> 
- <span data-ttu-id="a2b91-2528">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2528">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2529">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2529">Checksum</span></span>

<span data-ttu-id="a2b91-2530">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2530">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2531">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2531">Definition</span></span>

<span data-ttu-id="a2b91-2532">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2532">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2533">正規表現 Regex_malaysia_id_card_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2533">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2534">Keyword_malaysia_id_card_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2534">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2535">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2535">Keywords</span></span>
   
#### <a name="keywordmalaysiaidcardnumber"></a><span data-ttu-id="a2b91-2536">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2536">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="a2b91-2537">デジタルアプリケーションカード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2537">digital application card</span></span>
- <span data-ttu-id="a2b91-2538">i/c</span><span class="sxs-lookup"><span data-stu-id="a2b91-2538">i/c</span></span>
- <span data-ttu-id="a2b91-2539">i/c いいえ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2539">i/c no</span></span>
- <span data-ttu-id="a2b91-2540">ic</span><span class="sxs-lookup"><span data-stu-id="a2b91-2540">ic</span></span>
- <span data-ttu-id="a2b91-2541">ic no</span><span class="sxs-lookup"><span data-stu-id="a2b91-2541">ic no</span></span>
- <span data-ttu-id="a2b91-2542">id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2542">id card</span></span>
- <span data-ttu-id="a2b91-2543">識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2543">identification Card</span></span>
- <span data-ttu-id="a2b91-2544">Identity card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2544">identity card</span></span>
- <span data-ttu-id="a2b91-2545">k/p</span><span class="sxs-lookup"><span data-stu-id="a2b91-2545">k/p</span></span>
- <span data-ttu-id="a2b91-2546">k/p no</span><span class="sxs-lookup"><span data-stu-id="a2b91-2546">k/p no</span></span>
- <span data-ttu-id="a2b91-2547">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="a2b91-2547">kad akuan diri</span></span>
- <span data-ttu-id="a2b91-2548">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="a2b91-2548">kad aplikasi digital</span></span>
- <span data-ttu-id="a2b91-2549">kad の genalan マレーシア</span><span class="sxs-lookup"><span data-stu-id="a2b91-2549">kad pengenalan malaysia</span></span>
- <span data-ttu-id="a2b91-2550">kp</span><span class="sxs-lookup"><span data-stu-id="a2b91-2550">kp</span></span>
- <span data-ttu-id="a2b91-2551">kp no</span><span class="sxs-lookup"><span data-stu-id="a2b91-2551">kp no</span></span>
- <span data-ttu-id="a2b91-2552">mykad</span><span class="sxs-lookup"><span data-stu-id="a2b91-2552">mykad</span></span>
- <span data-ttu-id="a2b91-2553">mykas</span><span class="sxs-lookup"><span data-stu-id="a2b91-2553">mykas</span></span>
- <span data-ttu-id="a2b91-2554">mykid</span><span class="sxs-lookup"><span data-stu-id="a2b91-2554">mykid</span></span>
- <span data-ttu-id="a2b91-2555">mypr</span><span class="sxs-lookup"><span data-stu-id="a2b91-2555">mypr</span></span>
- <span data-ttu-id="a2b91-2556">mytentera</span><span class="sxs-lookup"><span data-stu-id="a2b91-2556">mytentera</span></span>
- <span data-ttu-id="a2b91-2557">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2557">malaysia identity card</span></span>
- <span data-ttu-id="a2b91-2558">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2558">malaysian identity card</span></span>
- <span data-ttu-id="a2b91-2559">nric</span><span class="sxs-lookup"><span data-stu-id="a2b91-2559">nric</span></span>
- <span data-ttu-id="a2b91-2560">個人識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2560">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="a2b91-2561">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2561">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2562">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2562">Format</span></span>

<span data-ttu-id="a2b91-2563">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2563">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2564">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2564">Pattern</span></span>

<span data-ttu-id="a2b91-2565">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2565">8-9 digits:</span></span>
- <span data-ttu-id="a2b91-2566">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2566">Three digits</span></span> 
- <span data-ttu-id="a2b91-2567">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2567">A space (optional)</span></span> 
- <span data-ttu-id="a2b91-2568">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2568">Three digits</span></span> 
- <span data-ttu-id="a2b91-2569">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2569">A space (optional)</span></span> 
- <span data-ttu-id="a2b91-2570">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2570">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2571">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2571">Checksum</span></span>

<span data-ttu-id="a2b91-2572">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2573">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2573">Definition</span></span>

<span data-ttu-id="a2b91-2574">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2574">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2575">関数 Func_netherlands_bsn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2575">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2576">Keyword_netherlands_bsn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2576">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="a2b91-2577">関数 Func_eu_date2 が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2577">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="a2b91-2578">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2578">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2579">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2579">Keywords</span></span>

#### <a name="keywordnetherlandsbsn"></a><span data-ttu-id="a2b91-2580">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="a2b91-2580">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="a2b91-2581">Citizen service number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2581">Citizen service number</span></span> 
- <span data-ttu-id="a2b91-2582">BSN

</span><span class="sxs-lookup"><span data-stu-id="a2b91-2582">BSN</span></span> 
- <span data-ttu-id="a2b91-2583">Burgerservicenummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2583">Burgerservicenummer</span></span> 
- <span data-ttu-id="a2b91-2584">Sofinummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2584">Sofinummer</span></span> 
- <span data-ttu-id="a2b91-2585">Persoonsgebonden nummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2585">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="a2b91-2586">Persoonsnummer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2586">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="a2b91-2587">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2587">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2588">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2588">Format</span></span>

<span data-ttu-id="a2b91-2589">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2589">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2590">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2590">Pattern</span></span>

<span data-ttu-id="a2b91-2591">3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2591">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2592">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2592">Checksum</span></span>

<span data-ttu-id="a2b91-2593">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2593">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2594">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2594">Definition</span></span>

<span data-ttu-id="a2b91-2595">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2595">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2596">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2596">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2597">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2597">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="a2b91-2598">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2598">The checksum passes.</span></span>

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

<span data-ttu-id="a2b91-2599">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2599">Keywords</span></span>

<span data-ttu-id="a2b91-2600">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="a2b91-2600">Keyword_nz_terms</span></span>

- <span data-ttu-id="a2b91-2601">NHI
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2601">NHI</span></span> 
- <span data-ttu-id="a2b91-2602">ニュージーランド</span><span class="sxs-lookup"><span data-stu-id="a2b91-2602">New Zealand</span></span> 
- <span data-ttu-id="a2b91-2603">正常性</span><span class="sxs-lookup"><span data-stu-id="a2b91-2603">Health</span></span> 
- <span data-ttu-id="a2b91-2604">treatment
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2604">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="a2b91-2605">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2605">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2606">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2606">Format</span></span>

<span data-ttu-id="a2b91-2607">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2607">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2608">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2608">Pattern</span></span>

<span data-ttu-id="a2b91-2609">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2609">11 digits:</span></span>
- <span data-ttu-id="a2b91-2610">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2610">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-2611">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2611">Three-digit individual number</span></span> 
- <span data-ttu-id="a2b91-2612">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a2b91-2612">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2613">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2613">Checksum</span></span>

<span data-ttu-id="a2b91-2614">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2614">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2615">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2615">Definition</span></span>

<span data-ttu-id="a2b91-2616">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2616">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2617">関数 Func_norway_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2617">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2618">Keyword_norway_id_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2618">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="a2b91-2619">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2619">The checksum passes.</span></span>
- <span data-ttu-id="a2b91-2620">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2621">関数 Func_norway_id_numbe がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2621">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2622">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2622">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2623">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2623">Keywords</span></span>

#### <a name="keywordnorwayidnumber"></a><span data-ttu-id="a2b91-2624">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2624">Keyword_norway_id_number</span></span>

- <span data-ttu-id="a2b91-2625">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2625">Personal identification number</span></span>
- <span data-ttu-id="a2b91-2626">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2626">Norwegian ID Number</span></span>
- <span data-ttu-id="a2b91-2627">ID Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2627">ID Number</span></span>
- <span data-ttu-id="a2b91-2628">Identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-2628">Identification</span></span>
- <span data-ttu-id="a2b91-2629">Personnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-2629">Personnummer</span></span>
- <span data-ttu-id="a2b91-2630">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="a2b91-2630">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="a2b91-2631">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2631">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2632">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2632">Format</span></span>

<span data-ttu-id="a2b91-2633">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2633">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2634">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2634">Pattern</span></span>

<span data-ttu-id="a2b91-2635">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2635">12 digits:</span></span>
- <span data-ttu-id="a2b91-2636">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2636">Four digits</span></span> 
- <span data-ttu-id="a2b91-2637">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2637">A hyphen</span></span> 
- <span data-ttu-id="a2b91-2638">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2638">Seven digits</span></span> 
- <span data-ttu-id="a2b91-2639">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-2639">A hyphen</span></span> 
- <span data-ttu-id="a2b91-2640">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2640">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2641">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2641">Checksum</span></span>

<span data-ttu-id="a2b91-2642">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2642">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2643">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2643">Definition</span></span>

<span data-ttu-id="a2b91-2644">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2644">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2645">正規表現 Regex_philippines_unified_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2645">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2646">Keyword_philippines_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2646">A keyword from Keyword_philippines_id is found.</span></span>

```
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2647">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2647">Keywords</span></span>
   
#### <a name="keywordphilippinesid"></a><span data-ttu-id="a2b91-2648">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-2648">Keyword_philippines_id</span></span>

- <span data-ttu-id="a2b91-2649">Unified Multi-Purpose ID
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2649">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="a2b91-2650">UMID
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2650">UMID</span></span> 
- <span data-ttu-id="a2b91-2651">Identity Card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2651">Identity Card</span></span> 
- <span data-ttu-id="a2b91-2652">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2652">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="a2b91-2653">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2653">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2654">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2654">Format</span></span>

<span data-ttu-id="a2b91-2655">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2655">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2656">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2656">Pattern</span></span>

<span data-ttu-id="a2b91-2657">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2657">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2658">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2658">Checksum</span></span>

<span data-ttu-id="a2b91-2659">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2659">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2660">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2660">Definition</span></span>

<span data-ttu-id="a2b91-p138">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。Keyword_polish_national_id_passport_number からのキーワードが見つかりました。チェックサムが渡されます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-p138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern. A keyword from Keyword_polish_national_id_passport_number is found. The checksum passes.</span></span>

```
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2664">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2664">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="a2b91-2665">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2665">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a2b91-2666">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="a2b91-2666">Dowód osobisty</span></span>
- <span data-ttu-id="a2b91-2667">特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a2b91-2667">Numer dowodu osobistego</span></span>
- <span data-ttu-id="a2b91-2668">nazwa i 特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a2b91-2668">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="a2b91-2669">nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="a2b91-2669">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="a2b91-2670">Nazwa i nr dowodu tożsamości
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2670">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="a2b91-2671">Dowód Tożsamości
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2671">Dowód Tożsamości</span></span>
- <span data-ttu-id="a2b91-p139">dow. os.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-p139">dow. os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="a2b91-2674">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2674">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2675">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2675">Format</span></span>

<span data-ttu-id="a2b91-2676">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2676">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2677">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2677">Pattern</span></span>

<span data-ttu-id="a2b91-2678">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2678">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2679">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2679">Checksum</span></span>

<span data-ttu-id="a2b91-2680">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2680">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2681">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2681">Definition</span></span>

<span data-ttu-id="a2b91-2682">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2682">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2683">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2683">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2684">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2684">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="a2b91-2685">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2685">The checksum passes.</span></span>

```
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2686">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2686">Keywords</span></span>

#### <a name="keywordpeselidentificationnumber"></a><span data-ttu-id="a2b91-2687">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2687">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="a2b91-2688">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="a2b91-2688">Nr PESEL</span></span>
- <span data-ttu-id="a2b91-2689">PESEL</span><span class="sxs-lookup"><span data-stu-id="a2b91-2689">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="a2b91-2690">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="a2b91-2690">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2691">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2691">Format</span></span>

<span data-ttu-id="a2b91-2692">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2692">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2693">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2693">Pattern</span></span>

<span data-ttu-id="a2b91-2694">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2694">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2695">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2695">Checksum</span></span>

<span data-ttu-id="a2b91-2696">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2696">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2697">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2697">Definition</span></span>

<span data-ttu-id="a2b91-2698">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2698">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2699">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2699">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2700">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2700">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="a2b91-2701">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2701">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2702">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2702">Keywords</span></span>

#### <a name="keywordpolishnationalidpassportnumber"></a><span data-ttu-id="a2b91-2703">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2703">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="a2b91-2704">特定の引数</span><span class="sxs-lookup"><span data-stu-id="a2b91-2704">Numer paszportu</span></span>
- <span data-ttu-id="a2b91-p140">Nr zportu</span><span class="sxs-lookup"><span data-stu-id="a2b91-p140">Nr. Paszportu</span></span>
- <span data-ttu-id="a2b91-2707">があります</span><span class="sxs-lookup"><span data-stu-id="a2b91-2707">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="a2b91-2708">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2708">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2709">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2709">Format</span></span>

<span data-ttu-id="a2b91-2710">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2710">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2711">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2711">Pattern</span></span>

<span data-ttu-id="a2b91-2712">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2712">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2713">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2713">Checksum</span></span>

<span data-ttu-id="a2b91-2714">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2714">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2715">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2715">Definition</span></span>

<span data-ttu-id="a2b91-2716">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2716">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2717">正規表現 Regex_portugal_citizen_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2717">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2718">Keyword_portugal_citizen_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2718">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2719">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2719">Keywords</span></span>

#### <a name="keywordportugalcitizencard"></a><span data-ttu-id="a2b91-2720">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2720">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="a2b91-2721">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2721">Citizen Card</span></span>
- <span data-ttu-id="a2b91-2722">National ID Card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2722">National ID Card</span></span>
- <span data-ttu-id="a2b91-2723">CC</span><span class="sxs-lookup"><span data-stu-id="a2b91-2723">CC</span></span>
- <span data-ttu-id="a2b91-2724">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="a2b91-2724">Cartão de Cidadão</span></span>
- <span data-ttu-id="a2b91-2725">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="a2b91-2725">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="a2b91-2726">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2726">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2727">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2727">Format</span></span>

<span data-ttu-id="a2b91-2728">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2728">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2729">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2729">Pattern</span></span>

<span data-ttu-id="a2b91-2730">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2730">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2731">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2731">Checksum</span></span>

<span data-ttu-id="a2b91-2732">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2732">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2733">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2733">Definition</span></span>

<span data-ttu-id="a2b91-2734">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2734">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2735">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2735">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2736">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2736">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2737">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2737">Keywords</span></span>

#### <a name="keywordsaudiarabianationalid"></a><span data-ttu-id="a2b91-2738">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-2738">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="a2b91-2739">Identification Card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2739">Identification Card</span></span> 
- <span data-ttu-id="a2b91-2740">I card number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2740">I card number</span></span> 
- <span data-ttu-id="a2b91-2741">ID number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2741">ID number</span></span> 
- <span data-ttu-id="a2b91-2742">الوطنية الهوية بطاقة رقم
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2742">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="a2b91-2743">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2743">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2744">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2744">Format</span></span>

<span data-ttu-id="a2b91-2745">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2745">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2746">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2746">Pattern</span></span>

- <span data-ttu-id="a2b91-2747">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2747">Nine letters and digits:</span></span>
- <span data-ttu-id="a2b91-2748">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-2748">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2749">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2749">Seven digits</span></span> 
- <span data-ttu-id="a2b91-2750">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a2b91-2750">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2751">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2751">Checksum</span></span>

<span data-ttu-id="a2b91-2752">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2752">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2753">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2753">Definition</span></span>

<span data-ttu-id="a2b91-2754">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2754">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2755">正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2755">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2756">Keyword_singapore_nric のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2756">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="a2b91-2757">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2757">The checksum passes.</span></span>

<span data-ttu-id="a2b91-2758">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2758">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2759">正規表現 Regex_singapore_nric がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2759">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2760">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2760">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2761">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2761">Keywords</span></span>
   
#### <a name="keywordsingaporenric"></a><span data-ttu-id="a2b91-2762">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="a2b91-2762">Keyword_singapore_nric</span></span>

- <span data-ttu-id="a2b91-2763">National Registration Identity Card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2763">National Registration Identity Card</span></span> 
- <span data-ttu-id="a2b91-2764">Identity Card Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2764">Identity Card Number</span></span> 
- <span data-ttu-id="a2b91-2765">NRIC
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2765">NRIC</span></span> 
- <span data-ttu-id="a2b91-2766">IC
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2766">IC</span></span> 
- <span data-ttu-id="a2b91-2767">Foreign Identification Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2767">Foreign Identification Number</span></span> 
- <span data-ttu-id="a2b91-2768">FIN
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2768">FIN</span></span> 
- <span data-ttu-id="a2b91-2769">身份证 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2769">身份证</span></span> 
- <span data-ttu-id="a2b91-2770">身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2770">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="a2b91-2771">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2771">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2772">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2772">Format</span></span>

<span data-ttu-id="a2b91-2773">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2773">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2774">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2774">Pattern</span></span>

<span data-ttu-id="a2b91-2775">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2775">13 digits:</span></span>
- <span data-ttu-id="a2b91-2776">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2776">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-2777">4 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2777">Four digits</span></span> 
- <span data-ttu-id="a2b91-2778">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2778">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="a2b91-2779">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2779">The digit "8" or "9"</span></span> 
- <span data-ttu-id="a2b91-2780">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2780">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2781">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2781">Checksum</span></span>

<span data-ttu-id="a2b91-2782">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2782">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2783">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2783">Definition</span></span>

<span data-ttu-id="a2b91-2784">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2784">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2785">関数 Func_south_africa_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2785">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2786">Keyword_south_africa_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2786">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="a2b91-2787">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2787">The checksum passes.</span></span>

```
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2788">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2788">Keywords</span></span>
   
#### <a name="keywordsouthafricaidentificationnumber"></a><span data-ttu-id="a2b91-2789">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2789">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="a2b91-2790">Identity card</span><span class="sxs-lookup"><span data-stu-id="a2b91-2790">Identity card</span></span>
- <span data-ttu-id="a2b91-2791">ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2791">ID</span></span>
- <span data-ttu-id="a2b91-2792">Identification</span><span class="sxs-lookup"><span data-stu-id="a2b91-2792">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="a2b91-2793">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2793">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2794">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2794">Format</span></span>

<span data-ttu-id="a2b91-2795">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2795">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2796">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2796">Pattern</span></span>

<span data-ttu-id="a2b91-2797">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2797">13 digits:</span></span>
- <span data-ttu-id="a2b91-2798">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2798">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="a2b91-2799">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a2b91-2799">A hyphen</span></span> 
- <span data-ttu-id="a2b91-2800">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2800">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="a2b91-2801">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="a2b91-2801">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="a2b91-2802">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2802">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="a2b91-2803">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a2b91-2803">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2804">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2804">Checksum</span></span>

<span data-ttu-id="a2b91-2805">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2805">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2806">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2806">Definition</span></span>

<span data-ttu-id="a2b91-2807">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2807">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2808">関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2808">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2809">Keyword_south_korea_resident_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2809">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="a2b91-2810">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2810">The checksum passes.</span></span>

<span data-ttu-id="a2b91-2811">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2811">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2812">関数 Func_south_korea_resident_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2812">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2813">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2813">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2814">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2814">Keywords</span></span>
   
#### <a name="keywordsouthkorearesidentnumber"></a><span data-ttu-id="a2b91-2815">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2815">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="a2b91-2816">National ID card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2816">National ID card</span></span> 
- <span data-ttu-id="a2b91-2817">Citizen's Registration Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2817">Citizen's Registration Number</span></span> 
- <span data-ttu-id="a2b91-2818">Jumin deungnok beonho
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2818">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="a2b91-2819">RRN
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2819">RRN</span></span> 
- <span data-ttu-id="a2b91-2820">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="a2b91-2820">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="a2b91-2821">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2821">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2822">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2822">Format</span></span>

<span data-ttu-id="a2b91-2823">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2823">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2824">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2824">Pattern</span></span>

<span data-ttu-id="a2b91-2825">11-12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2825">11-12 digits:</span></span>
- <span data-ttu-id="a2b91-2826">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2826">Two digits</span></span> 
- <span data-ttu-id="a2b91-2827">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2827">A forward slash (optional)</span></span> 
- <span data-ttu-id="a2b91-2828">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2828">7-8 digits</span></span> 
- <span data-ttu-id="a2b91-2829">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2829">A forward slash (optional)</span></span> 
- <span data-ttu-id="a2b91-2830">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2830">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2831">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2831">Checksum</span></span>

<span data-ttu-id="a2b91-2832">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2832">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2833">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2833">Definition</span></span>

<span data-ttu-id="a2b91-2834">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2834">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2835">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2835">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2836">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2836">The checksum passes.</span></span>

```
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2837">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2837">Keywords</span></span>

<span data-ttu-id="a2b91-2838">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2838">None</span></span>
   
## <a name="sweden-national-id"></a><span data-ttu-id="a2b91-2839">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2839">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2840">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2840">Format</span></span>

<span data-ttu-id="a2b91-2841">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2841">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2842">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2842">Pattern</span></span>

<span data-ttu-id="a2b91-2843">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2843">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="a2b91-2844">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2844">2-4 digits (optional)</span></span> 
- <span data-ttu-id="a2b91-2845">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2845">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="a2b91-2846">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="a2b91-2846">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="a2b91-2847">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2847">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2848">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2848">Checksum</span></span>

<span data-ttu-id="a2b91-2849">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2849">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2850">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2850">Definition</span></span>

<span data-ttu-id="a2b91-2851">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2851">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2852">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2852">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2853">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2853">The checksum passes.</span></span>

```
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2854">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2854">Keywords</span></span>

<span data-ttu-id="a2b91-2855">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2855">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="a2b91-2856">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2856">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2857">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2857">Format</span></span>

<span data-ttu-id="a2b91-2858">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2858">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2859">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2859">Pattern</span></span>

<span data-ttu-id="a2b91-2860">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2860">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2861">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2861">Checksum</span></span>

<span data-ttu-id="a2b91-2862">いいえ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2862">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2863">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2863">Definition</span></span>

<span data-ttu-id="a2b91-2864">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2864">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2865">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2865">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2866">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2866">One of the following is true:</span></span>
    - <span data-ttu-id="a2b91-2867">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2867">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="a2b91-2868">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2868">A keyword from Keyword_sweden_passport is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-2869">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2869">Keywords</span></span>
   
#### <a name="keywordswedenpassport"></a><span data-ttu-id="a2b91-2870">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-2870">Keyword_sweden_passport</span></span>

- <span data-ttu-id="a2b91-2871">visa requirements
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2871">visa requirements</span></span> 
- <span data-ttu-id="a2b91-2872">Alien Registration Card
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2872">Alien Registration Card</span></span> 
- <span data-ttu-id="a2b91-2873">Schengen visas
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2873">Schengen visas</span></span> 
- <span data-ttu-id="a2b91-2874">Schengen visa
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2874">Schengen visa</span></span> 
- <span data-ttu-id="a2b91-2875">Visa Processing
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2875">Visa Processing</span></span> 
- <span data-ttu-id="a2b91-2876">Visa Type
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2876">Visa Type</span></span> 
- <span data-ttu-id="a2b91-2877">Single Entry
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2877">Single Entry</span></span> 
- <span data-ttu-id="a2b91-2878">Multiple Entry
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2878">Multiple Entry</span></span> 
- <span data-ttu-id="a2b91-2879">G3 Processing Fees

</span><span class="sxs-lookup"><span data-stu-id="a2b91-2879">G3 Processing Fees</span></span> 

#### <a name="keywordpassport"></a><span data-ttu-id="a2b91-2880">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-2880">Keyword_passport</span></span>

- <span data-ttu-id="a2b91-2881">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-2881">Passport Number</span></span> 
- <span data-ttu-id="a2b91-2882">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a2b91-2882">Passport No</span></span> 
- <span data-ttu-id="a2b91-2883">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2883">Passport #</span></span> 
- <span data-ttu-id="a2b91-2884">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2884">Passport#</span></span> 
- <span data-ttu-id="a2b91-2885">PassportID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2885">PassportID</span></span> 
- <span data-ttu-id="a2b91-2886">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2886">Passportno</span></span> 
- <span data-ttu-id="a2b91-2887">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2887">passportnumber</span></span> 
- <span data-ttu-id="a2b91-2888">パスポート</span><span class="sxs-lookup"><span data-stu-id="a2b91-2888">パスポート</span></span> 
- <span data-ttu-id="a2b91-2889">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2889">パスポート番号</span></span> 
- <span data-ttu-id="a2b91-2890">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2890">パスポートのNum</span></span> 
- <span data-ttu-id="a2b91-2891">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2891">パスポート＃</span></span> 
- <span data-ttu-id="a2b91-2892">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a2b91-2892">Numéro de passeport</span></span> 
- <span data-ttu-id="a2b91-2893">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a2b91-2893">Passeport n °</span></span> 
- <span data-ttu-id="a2b91-2894">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2894">Passeport Non</span></span> 
- <span data-ttu-id="a2b91-2895">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2895">Passeport #</span></span> 
- <span data-ttu-id="a2b91-2896">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2896">Passeport#</span></span> 
- <span data-ttu-id="a2b91-2897">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a2b91-2897">PasseportNon</span></span> 
- <span data-ttu-id="a2b91-2898">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2898">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="a2b91-2899">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2899">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2900">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2900">Format</span></span>

<span data-ttu-id="a2b91-2901">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2901">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2902">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2902">Pattern</span></span>

<span data-ttu-id="a2b91-2903">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2903">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="a2b91-2904">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2904">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2905">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-2905">An optional space</span></span> 
- <span data-ttu-id="a2b91-2906">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="a2b91-2906">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="a2b91-2907">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-2907">An optional space</span></span> 
- <span data-ttu-id="a2b91-2908">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2908">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2909">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2909">Checksum</span></span>

<span data-ttu-id="a2b91-2910">いいえ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2910">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2911">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2911">Definition</span></span>

<span data-ttu-id="a2b91-2912">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2912">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2913">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2913">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2914">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2914">A keyword from Keyword_swift is found.</span></span>

```
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2915">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2915">Keywords</span></span>
   
#### <a name="keywordswift"></a><span data-ttu-id="a2b91-2916">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="a2b91-2916">Keyword_swift</span></span>

- <span data-ttu-id="a2b91-2917">international organization for standardization 9362
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2917">international organization for standardization 9362</span></span> 
- <span data-ttu-id="a2b91-2918">iso 9362
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2918">iso 9362</span></span> 
- <span data-ttu-id="a2b91-2919">iso9362</span><span class="sxs-lookup"><span data-stu-id="a2b91-2919">iso9362</span></span> 
- <span data-ttu-id="a2b91-2920">実現\#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2920">swift\#</span></span> 
- <span data-ttu-id="a2b91-2921">swiftcode
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2921">swiftcode</span></span> 
- <span data-ttu-id="a2b91-2922">swiftnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2922">swiftnumber</span></span> 
- <span data-ttu-id="a2b91-2923">swiftroutingnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2923">swiftroutingnumber</span></span> 
- <span data-ttu-id="a2b91-2924">swift コード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2924">swift code</span></span> 
- <span data-ttu-id="a2b91-2925">swift number #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2925">swift number #</span></span> 
- <span data-ttu-id="a2b91-2926">swift routing number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2926">swift routing number</span></span> 
- <span data-ttu-id="a2b91-2927">bic number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2927">bic number</span></span> 
- <span data-ttu-id="a2b91-2928">bic code
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2928">bic code</span></span> 
- <span data-ttu-id="a2b91-2929">bic\#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2929">bic \#</span></span> 
- <span data-ttu-id="a2b91-2930">bic\#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2930">bic\#</span></span> 
- <span data-ttu-id="a2b91-2931">bank identifier code
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2931">bank identifier code</span></span> 
- <span data-ttu-id="a2b91-2932">標準化9362</span><span class="sxs-lookup"><span data-stu-id="a2b91-2932">標準化9362</span></span> 
- <span data-ttu-id="a2b91-2933">迅速＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2933">迅速＃</span></span> 
- <span data-ttu-id="a2b91-2934">SWIFTコード
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2934">SWIFTコード</span></span> 
- <span data-ttu-id="a2b91-2935">SWIFT番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2935">SWIFT番号</span></span> 
- <span data-ttu-id="a2b91-2936">迅速なルーティング番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2936">迅速なルーティング番号</span></span> 
- <span data-ttu-id="a2b91-2937">BIC番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2937">BIC番号</span></span> 
- <span data-ttu-id="a2b91-2938">BICコード
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2938">BICコード</span></span> 
- <span data-ttu-id="a2b91-2939">銀行識別コードのための国際組織
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2939">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="a2b91-2940">Organisation internationale de normalisation 9362
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2940">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="a2b91-2941">rapide\#</span><span class="sxs-lookup"><span data-stu-id="a2b91-2941">rapide \#</span></span> 
- <span data-ttu-id="a2b91-2942">code SWIFT
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2942">code SWIFT</span></span> 
- <span data-ttu-id="a2b91-2943">le numéro de swift
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2943">le numéro de swift</span></span> 
- <span data-ttu-id="a2b91-2944">swift numéro d'acheminement
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2944">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="a2b91-2945">le numéro BIC
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2945">le numéro BIC</span></span> 
- <span data-ttu-id="a2b91-2946">\#bic</span><span class="sxs-lookup"><span data-stu-id="a2b91-2946">\# BIC</span></span> 
- <span data-ttu-id="a2b91-2947">code identificateur de banque
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2947">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="a2b91-2948">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-2948">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2949">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2949">Format</span></span>

<span data-ttu-id="a2b91-2950">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2950">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2951">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2951">Pattern</span></span>

<span data-ttu-id="a2b91-2952">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2952">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="a2b91-2953">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="a2b91-2953">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-2954">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="a2b91-2954">The digit "1" or "2"</span></span> 
- <span data-ttu-id="a2b91-2955">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2955">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2956">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2956">Checksum</span></span>

<span data-ttu-id="a2b91-2957">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-2957">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2958">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-2958">Definition</span></span>

<span data-ttu-id="a2b91-2959">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2959">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2960">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2960">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2961">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2961">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="a2b91-2962">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2962">The checksum passes.</span></span>

```
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2963">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2963">Keywords</span></span>

#### <a name="keywordtaiwanesenationalid"></a><span data-ttu-id="a2b91-2964">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="a2b91-2964">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="a2b91-2965">身份證字號
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2965">身份證字號</span></span> 
- <span data-ttu-id="a2b91-2966">身份證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2966">身份證</span></span> 
- <span data-ttu-id="a2b91-2967">身份證號碼
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2967">身份證號碼</span></span> 
- <span data-ttu-id="a2b91-2968">身份證號
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2968">身份證號</span></span> 
- <span data-ttu-id="a2b91-2969">身分證字號
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2969">身分證字號</span></span> 
- <span data-ttu-id="a2b91-2970">身分證 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2970">身分證</span></span> 
- <span data-ttu-id="a2b91-2971">身分證號碼
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2971">身分證號碼</span></span> 
- <span data-ttu-id="a2b91-2972">身份證號
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2972">身份證號</span></span> 
- <span data-ttu-id="a2b91-2973">身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2973">身分證統一編號</span></span> 
- <span data-ttu-id="a2b91-2974">國民身分證統一編號
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2974">國民身分證統一編號</span></span> 
- <span data-ttu-id="a2b91-2975">簽名
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2975">簽名</span></span> 
- <span data-ttu-id="a2b91-2976">蓋章
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2976">蓋章</span></span> 
- <span data-ttu-id="a2b91-2977">簽名或蓋章

</span><span class="sxs-lookup"><span data-stu-id="a2b91-2977">簽名或蓋章</span></span> 
- <span data-ttu-id="a2b91-2978">簽章</span><span class="sxs-lookup"><span data-stu-id="a2b91-2978">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="a2b91-2979">台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2979">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-2980">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-2980">Format</span></span>

- <span data-ttu-id="a2b91-2981">バイオメトリックパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2981">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="a2b91-2982">バイオメトリクスでないパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2982">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-2983">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-2983">Pattern</span></span>
<span data-ttu-id="a2b91-2984">バイオメトリックパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2984">Biometric passport number:</span></span>
- <span data-ttu-id="a2b91-2985">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="a2b91-2985">The digit "3"</span></span> 
- <span data-ttu-id="a2b91-2986">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2986">Eight digits</span></span>

<span data-ttu-id="a2b91-2987">バイオメトリクスではないパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="a2b91-2987">Non-biometric passport number:</span></span>
- <span data-ttu-id="a2b91-2988">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-2988">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-2989">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-2989">Checksum</span></span>

<span data-ttu-id="a2b91-2990">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-2990">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-2991">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-2991">Definition</span></span>

<span data-ttu-id="a2b91-2992">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2992">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-2993">正規表現 Regex_taiwan_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2993">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-2994">Keyword_taiwan_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-2994">A keyword from Keyword_taiwan_passport is found.</span></span>

```
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-2995">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-2995">Keywords</span></span>

#### <a name="keywordtaiwanpassport"></a><span data-ttu-id="a2b91-2996">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-2996">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="a2b91-2997">ROC passport number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-2997">ROC passport number</span></span> 
- <span data-ttu-id="a2b91-2998">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-2998">Passport number</span></span> 
- <span data-ttu-id="a2b91-2999">Passport いいえ</span><span class="sxs-lookup"><span data-stu-id="a2b91-2999">Passport no</span></span> 
- <span data-ttu-id="a2b91-3000">Passport Num
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3000">Passport Num</span></span> 
- <span data-ttu-id="a2b91-3001">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3001">Passport #</span></span> 
- <span data-ttu-id="a2b91-3002">护照
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3002">护照</span></span> 
- <span data-ttu-id="a2b91-3003">中華民國護照
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3003">中華民國護照</span></span> 
- <span data-ttu-id="a2b91-3004">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="a2b91-3004">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="a2b91-3005">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3005">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3006">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3006">Format</span></span>

<span data-ttu-id="a2b91-3007">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3007">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3008">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3008">Pattern</span></span>

<span data-ttu-id="a2b91-3009">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3009">10 letters and digits:</span></span>
- <span data-ttu-id="a2b91-3010">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="a2b91-3010">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="a2b91-3011">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3011">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3012">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3012">Checksum</span></span>

<span data-ttu-id="a2b91-3013">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3013">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3014">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-3014">Definition</span></span>

<span data-ttu-id="a2b91-3015">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3015">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3016">正規表現 Regex_taiwan_resident_certificate がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3016">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3017">Keyword_taiwan_resident_certificate のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3017">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-3018">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3018">Keywords</span></span>

#### <a name="keywordtaiwanresidentcertificate"></a><span data-ttu-id="a2b91-3019">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="a2b91-3019">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="a2b91-3020">Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3020">Resident Certificate</span></span> 
- <span data-ttu-id="a2b91-3021">常駐証明書</span><span class="sxs-lookup"><span data-stu-id="a2b91-3021">Resident Cert</span></span> 
- <span data-ttu-id="a2b91-3022">Resident Cert.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3022">Resident Cert.</span></span> 
- <span data-ttu-id="a2b91-3023">識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3023">Identification card</span></span> 
- <span data-ttu-id="a2b91-3024">Alien Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3024">Alien Resident Certificate</span></span> 
- <span data-ttu-id="a2b91-3025">円弧</span><span class="sxs-lookup"><span data-stu-id="a2b91-3025">ARC</span></span> 
- <span data-ttu-id="a2b91-3026">Taiwan Area Resident Certificate
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3026">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="a2b91-3027">TARC
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3027">TARC</span></span> 
- <span data-ttu-id="a2b91-3028">居留證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3028">居留證</span></span> 
- <span data-ttu-id="a2b91-3029">外僑居留證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3029">外僑居留證</span></span> 
- <span data-ttu-id="a2b91-3030">台灣地區居留證
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3030">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="a2b91-3031">タイ語の母集団識別コード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3031">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3032">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3032">Format</span></span>

<span data-ttu-id="a2b91-3033">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3033">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3034">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3034">Pattern</span></span>

<span data-ttu-id="a2b91-3035">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3035">13 digits:</span></span>
- <span data-ttu-id="a2b91-3036">最初の桁が0または9ではない</span><span class="sxs-lookup"><span data-stu-id="a2b91-3036">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="a2b91-3037">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3037">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3038">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3038">Checksum</span></span>

<span data-ttu-id="a2b91-3039">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3040">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3040">Definition</span></span>

<span data-ttu-id="a2b91-3041">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3042">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3042">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3043">Keyword_Thai_Citizen_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3043">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="a2b91-3044">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3044">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3045">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3045">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3046">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3046">Keywords</span></span>

#### <a name="keywordthaicitizenid"></a><span data-ttu-id="a2b91-3047">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="a2b91-3047">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="a2b91-3048">ID Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-3048">ID Number</span></span>
- <span data-ttu-id="a2b91-3049">識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3049">Identification Number</span></span>
- <span data-ttu-id="a2b91-3050">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a2b91-3050">บัตรประชาชน</span></span>
- <span data-ttu-id="a2b91-3051">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a2b91-3051">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="a2b91-3052">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a2b91-3052">บัตรประชาชน</span></span>
- <span data-ttu-id="a2b91-3053">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="a2b91-3053">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="a2b91-3054">トルコの国の識別番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3054">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3055">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3055">Format</span></span>

<span data-ttu-id="a2b91-3056">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3056">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3057">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3057">Pattern</span></span>

<span data-ttu-id="a2b91-3058">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3058">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3059">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3059">Checksum</span></span>

<span data-ttu-id="a2b91-3060">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3061">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3061">Definition</span></span>

<span data-ttu-id="a2b91-3062">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3063">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3063">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3064">Keyword_Turkish_National_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3064">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="a2b91-3065">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3065">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3066">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3066">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3067">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3067">Keywords</span></span>

#### <a name="keywordturkishnationalid"></a><span data-ttu-id="a2b91-3068">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="a2b91-3068">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="a2b91-3069">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="a2b91-3069">TC Kimlik No</span></span>
- <span data-ttu-id="a2b91-3070">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="a2b91-3070">TC Kimlik numarası</span></span>
- <span data-ttu-id="a2b91-3071">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="a2b91-3071">Vatandaşlık numarası</span></span>
- <span data-ttu-id="a2b91-3072">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="a2b91-3072">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="a2b91-p141">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3075">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3075">Format</span></span>

<span data-ttu-id="a2b91-3076">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3076">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3077">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3077">Pattern</span></span>

<span data-ttu-id="a2b91-3078">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3078">18 letters and digits:</span></span>
- <span data-ttu-id="a2b91-3079">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="a2b91-3079">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a2b91-3080">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3080">One digit</span></span> 
- <span data-ttu-id="a2b91-3081">誕生日を示す DDMMY という日付形式の 5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3081">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="a2b91-3082">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="a2b91-3082">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="a2b91-3083">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3083">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3084">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3084">Checksum</span></span>

<span data-ttu-id="a2b91-3085">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-3085">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3086">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3086">Definition</span></span>

<span data-ttu-id="a2b91-3087">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3087">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3088">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3088">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3089">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3089">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="a2b91-3090">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3090">The checksum passes.</span></span>

```
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-3091">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3091">Keywords</span></span>

#### <a name="keywordukdriverslicense"></a><span data-ttu-id="a2b91-3092">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a2b91-3092">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="a2b91-3093">DVLA
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3093">DVLA</span></span> 
- <span data-ttu-id="a2b91-3094">light vans
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3094">light vans</span></span> 
- <span data-ttu-id="a2b91-3095">quadbikes
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3095">quadbikes</span></span> 
- <span data-ttu-id="a2b91-3096">motor cars
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3096">motor cars</span></span> 
- <span data-ttu-id="a2b91-3097">125cc</span><span class="sxs-lookup"><span data-stu-id="a2b91-3097">125cc</span></span> 
- <span data-ttu-id="a2b91-3098">sidecar
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3098">sidecar</span></span> 
- <span data-ttu-id="a2b91-3099">tricycles
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3099">tricycles</span></span> 
- <span data-ttu-id="a2b91-3100">motorcycles
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3100">motorcycles</span></span> 
- <span data-ttu-id="a2b91-3101">photocard licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3101">photocard licence</span></span> 
- <span data-ttu-id="a2b91-3102">learner drivers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3102">learner drivers</span></span> 
- <span data-ttu-id="a2b91-3103">licence holder
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3103">licence holder</span></span> 
- <span data-ttu-id="a2b91-3104">licence holders
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3104">licence holders</span></span> 
- <span data-ttu-id="a2b91-3105">driving licences
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3105">driving licences</span></span> 
- <span data-ttu-id="a2b91-3106">driving licence
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3106">driving licence</span></span> 
- <span data-ttu-id="a2b91-3107">dual control car
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3107">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="a2b91-p142">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3110">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3110">Format</span></span>

<span data-ttu-id="a2b91-3111">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3111">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3112">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3112">Pattern</span></span>

<span data-ttu-id="a2b91-3113">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3113">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3114">Checksum</span></span>

<span data-ttu-id="a2b91-3115">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3115">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3116">Definition</span><span class="sxs-lookup"><span data-stu-id="a2b91-3116">Definition</span></span>

<span data-ttu-id="a2b91-3117">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3118">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3118">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3119">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3119">A keyword from Keyword_uk_electoral is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3120">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3120">Keywords</span></span>

#### <a name="keywordukelectoral"></a><span data-ttu-id="a2b91-3121">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="a2b91-3121">Keyword_uk_electoral</span></span>

- <span data-ttu-id="a2b91-3122">council nomination
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3122">council nomination</span></span> 
- <span data-ttu-id="a2b91-3123">nomination form
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3123">nomination form</span></span> 
- <span data-ttu-id="a2b91-3124">electoral register

</span><span class="sxs-lookup"><span data-stu-id="a2b91-3124">electoral register</span></span> 
- <span data-ttu-id="a2b91-3125">electoral roll</span><span class="sxs-lookup"><span data-stu-id="a2b91-3125">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="a2b91-p143">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3128">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3128">Format</span></span>

<span data-ttu-id="a2b91-3129">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3129">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3130">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3130">Pattern</span></span>

<span data-ttu-id="a2b91-3131">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3131">10-17 digits:</span></span>
- <span data-ttu-id="a2b91-3132">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3132">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="a2b91-3133">スペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-3133">A space</span></span> 
- <span data-ttu-id="a2b91-3134">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3134">Three digits</span></span> 
- <span data-ttu-id="a2b91-3135">スペース</span><span class="sxs-lookup"><span data-stu-id="a2b91-3135">A space</span></span> 
- <span data-ttu-id="a2b91-3136">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3136">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3137">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3137">Checksum</span></span>

<span data-ttu-id="a2b91-3138">はい</span><span class="sxs-lookup"><span data-stu-id="a2b91-3138">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3139">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3139">Definition</span></span>

<span data-ttu-id="a2b91-3140">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3141">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3141">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3142">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3142">One of the following is true:</span></span>
    - <span data-ttu-id="a2b91-3143">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3143">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="a2b91-3144">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3144">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="a2b91-3145">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3145">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="a2b91-3146">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3146">The checksum passes.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3147">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3147">Keywords</span></span>
   
#### <a name="keyworduknhsnumber"></a><span data-ttu-id="a2b91-3148">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="a2b91-3148">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="a2b91-3149">national health service
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3149">national health service</span></span> 
- <span data-ttu-id="a2b91-3150">nhs
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3150">nhs</span></span> 
- <span data-ttu-id="a2b91-3151">health services authority

</span><span class="sxs-lookup"><span data-stu-id="a2b91-3151">health services authority</span></span> 
- <span data-ttu-id="a2b91-3152">health authority</span><span class="sxs-lookup"><span data-stu-id="a2b91-3152">health authority</span></span>

#### <a name="keyworduknhsnumber1"></a><span data-ttu-id="a2b91-3153">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="a2b91-3153">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="a2b91-3154">patient id
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3154">patient id</span></span> 
- <span data-ttu-id="a2b91-3155">patient identification
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3155">patient identification</span></span> 
- <span data-ttu-id="a2b91-3156">patient no

</span><span class="sxs-lookup"><span data-stu-id="a2b91-3156">patient no</span></span> 
- <span data-ttu-id="a2b91-3157">patient number</span><span class="sxs-lookup"><span data-stu-id="a2b91-3157">patient number</span></span>

#### <a name="keyworduknhsnumberdob"></a><span data-ttu-id="a2b91-3158">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="a2b91-3158">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="a2b91-3159">GP</span><span class="sxs-lookup"><span data-stu-id="a2b91-3159">GP</span></span> 
- <span data-ttu-id="a2b91-3160">DOB
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3160">DOB</span></span> 
- <span data-ttu-id="a2b91-3161">D.</span><span class="sxs-lookup"><span data-stu-id="a2b91-3161">D.O.B</span></span> 
- <span data-ttu-id="a2b91-3162">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3162">Date of Birth</span></span> 
- <span data-ttu-id="a2b91-3163">Birth Date
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3163">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="a2b91-p144">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="a2b91-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3166">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3166">Format</span></span>

<span data-ttu-id="a2b91-3167">スペースまたはダッシュで区切られた7文字または9文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3167">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3168">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3168">Pattern</span></span>

<span data-ttu-id="a2b91-3169">次の2つのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3169">Two possible patterns:</span></span>

- <span data-ttu-id="a2b91-3170">2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3170">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="a2b91-3171">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3171">Six digits</span></span>
- <span data-ttu-id="a2b91-3172">「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)</span><span class="sxs-lookup"><span data-stu-id="a2b91-3172">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="a2b91-3173">または</span><span class="sxs-lookup"><span data-stu-id="a2b91-3173">OR</span></span>

- <span data-ttu-id="a2b91-3174">2文字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3174">Two letters</span></span>
- <span data-ttu-id="a2b91-3175">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3175">A space or dash</span></span>
- <span data-ttu-id="a2b91-3176">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3176">Two digits</span></span>
- <span data-ttu-id="a2b91-3177">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3177">A space or dash</span></span>
- <span data-ttu-id="a2b91-3178">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3178">Two digits</span></span>
- <span data-ttu-id="a2b91-3179">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3179">A space or dash</span></span>
- <span data-ttu-id="a2b91-3180">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3180">Two digits</span></span>
- <span data-ttu-id="a2b91-3181">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3181">A space or dash</span></span>
- <span data-ttu-id="a2b91-3182">' A '、' B '、' C '、または ' d ' のどちらか</span><span class="sxs-lookup"><span data-stu-id="a2b91-3182">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3183">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3183">Checksum</span></span>

<span data-ttu-id="a2b91-3184">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3185">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3185">Definition</span></span>

<span data-ttu-id="a2b91-3186">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3186">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3187">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3187">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3188">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3188">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="a2b91-3189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3190">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3190">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3191">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3191">No keyword from Keyword_uk_nino is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3192">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3192">Keywords</span></span>

#### <a name="keyworduknino"></a><span data-ttu-id="a2b91-3193">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="a2b91-3193">Keyword_uk_nino</span></span>

- <span data-ttu-id="a2b91-3194">national insurance number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3194">national insurance number</span></span> 
- <span data-ttu-id="a2b91-3195">national insurance contributions
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3195">national insurance contributions</span></span> 
- <span data-ttu-id="a2b91-3196">protection act
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3196">protection act</span></span> 
- <span data-ttu-id="a2b91-3197">insurance
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3197">insurance</span></span> 
- <span data-ttu-id="a2b91-3198">social security number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3198">social security number</span></span> 
- <span data-ttu-id="a2b91-3199">insurance application
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3199">insurance application</span></span> 
- <span data-ttu-id="a2b91-3200">medical application
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3200">medical application</span></span> 
- <span data-ttu-id="a2b91-3201">social insurance
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3201">social insurance</span></span> 
- <span data-ttu-id="a2b91-3202">medical attention
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3202">medical attention</span></span> 
- <span data-ttu-id="a2b91-3203">ソーシャルセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3203">social security</span></span> 
- <span data-ttu-id="a2b91-3204">great britain
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3204">great britain</span></span> 
- <span data-ttu-id="a2b91-3205">insurance
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3205">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="a2b91-p145">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3208">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3208">Format</span></span>

<span data-ttu-id="a2b91-3209">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3209">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3210">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3210">Pattern</span></span>

<span data-ttu-id="a2b91-3211">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3211">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3212">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3212">Checksum</span></span>

<span data-ttu-id="a2b91-3213">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3213">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3214">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3214">Definition</span></span>

<span data-ttu-id="a2b91-3215">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3215">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3216">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3216">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3217">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3217">A keyword from Keyword_passport is found.</span></span>

```
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-3218">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3218">Keywords</span></span>

#### <a name="keywordpassport"></a><span data-ttu-id="a2b91-3219">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="a2b91-3219">Keyword_passport</span></span>

- <span data-ttu-id="a2b91-3220">Passport Number</span><span class="sxs-lookup"><span data-stu-id="a2b91-3220">Passport Number</span></span> 
- <span data-ttu-id="a2b91-3221">
Passport No</span><span class="sxs-lookup"><span data-stu-id="a2b91-3221">Passport No</span></span> 
- <span data-ttu-id="a2b91-3222">Passport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3222">Passport #</span></span> 
- <span data-ttu-id="a2b91-3223">Passport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3223">Passport#</span></span> 
- <span data-ttu-id="a2b91-3224">PassportID</span><span class="sxs-lookup"><span data-stu-id="a2b91-3224">PassportID</span></span> 
- <span data-ttu-id="a2b91-3225">Passportno
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3225">Passportno</span></span> 
- <span data-ttu-id="a2b91-3226">passportnumber
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3226">passportnumber</span></span> 
- <span data-ttu-id="a2b91-3227">パスポート</span><span class="sxs-lookup"><span data-stu-id="a2b91-3227">パスポート</span></span> 
- <span data-ttu-id="a2b91-3228">パスポート番号
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3228">パスポート番号</span></span> 
- <span data-ttu-id="a2b91-3229">パスポートのNum
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3229">パスポートのNum</span></span> 
- <span data-ttu-id="a2b91-3230">パスポート＃
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3230">パスポート＃</span></span> 
- <span data-ttu-id="a2b91-3231">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="a2b91-3231">Numéro de passeport</span></span> 
- <span data-ttu-id="a2b91-3232">
Passeport n °</span><span class="sxs-lookup"><span data-stu-id="a2b91-3232">Passeport n °</span></span> 
- <span data-ttu-id="a2b91-3233">Passeport Non
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3233">Passeport Non</span></span> 
- <span data-ttu-id="a2b91-3234">Passeport #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3234">Passeport #</span></span> 
- <span data-ttu-id="a2b91-3235">Passeport#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3235">Passeport#</span></span> 
- <span data-ttu-id="a2b91-3236">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="a2b91-3236">PasseportNon</span></span> 
- <span data-ttu-id="a2b91-3237">Passeportn °
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3237">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="a2b91-3238">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3238">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3239">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3239">Format</span></span>

<span data-ttu-id="a2b91-3240">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3240">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3241">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3241">Pattern</span></span>

<span data-ttu-id="a2b91-3242">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3242">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3243">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3243">Checksum</span></span>

<span data-ttu-id="a2b91-3244">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3244">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3245">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3245">Definition</span></span>

<span data-ttu-id="a2b91-3246">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3247">正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3247">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3248">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3248">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a2b91-3249">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3249">Keywords</span></span>

#### <a name="keywordusabankaccount"></a><span data-ttu-id="a2b91-3250">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="a2b91-3250">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="a2b91-3251">Checking Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3251">Checking Account Number</span></span> 
- <span data-ttu-id="a2b91-3252">Checking Account
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3252">Checking Account</span></span> 
- <span data-ttu-id="a2b91-3253">Checking Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3253">Checking Account #</span></span> 
- <span data-ttu-id="a2b91-3254">Checking Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3254">Checking Acct Number</span></span> 
- <span data-ttu-id="a2b91-3255">Checking Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3255">Checking Acct #</span></span> 
- <span data-ttu-id="a2b91-3256">Checking Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3256">Checking Acct No.</span></span> 
- <span data-ttu-id="a2b91-3257">Checking Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3257">Checking Account No.</span></span> 
- <span data-ttu-id="a2b91-3258">Bank Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3258">Bank Account Number</span></span> 
- <span data-ttu-id="a2b91-3259">Bank Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3259">Bank Account #</span></span> 
- <span data-ttu-id="a2b91-3260">Bank Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3260">Bank Acct Number</span></span> 
- <span data-ttu-id="a2b91-3261">Bank Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3261">Bank Acct #</span></span> 
- <span data-ttu-id="a2b91-3262">Bank Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3262">Bank Acct No.</span></span> 
- <span data-ttu-id="a2b91-3263">Bank Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3263">Bank Account No.</span></span> 
- <span data-ttu-id="a2b91-3264">Savings Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3264">Savings Account Number</span></span> 
- <span data-ttu-id="a2b91-3265">Savings Account.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3265">Savings Account.</span></span> 
- <span data-ttu-id="a2b91-3266">Savings Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3266">Savings Account #</span></span> 
- <span data-ttu-id="a2b91-3267">Savings Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3267">Savings Acct Number</span></span> 
- <span data-ttu-id="a2b91-3268">Savings Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3268">Savings Acct #</span></span> 
- <span data-ttu-id="a2b91-3269">Savings Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3269">Savings Acct No.</span></span> 
- <span data-ttu-id="a2b91-3270">Savings Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3270">Savings Account No.</span></span> 
- <span data-ttu-id="a2b91-3271">Debit Account Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3271">Debit Account Number</span></span> 
- <span data-ttu-id="a2b91-3272">Debit Account
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3272">Debit Account</span></span> 
- <span data-ttu-id="a2b91-3273">Debit Account #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3273">Debit Account #</span></span> 
- <span data-ttu-id="a2b91-3274">Debit Acct Number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3274">Debit Acct Number</span></span> 
- <span data-ttu-id="a2b91-3275">Debit Acct #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3275">Debit Acct #</span></span> 
- <span data-ttu-id="a2b91-3276">Debit Acct No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3276">Debit Acct No.</span></span> 
- <span data-ttu-id="a2b91-3277">Debit Account No.
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3277">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="a2b91-3278">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3278">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3279">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3279">Format</span></span>

<span data-ttu-id="a2b91-3280">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="a2b91-3280">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3281">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3281">Pattern</span></span>

<span data-ttu-id="a2b91-3282">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3282">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="a2b91-3283">ddd ddd ddd のような形式の 9 桁の数字がマッチします。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3283">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="a2b91-3284">ddddddddd のような 9 桁の数字はマッチしません。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3284">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3285">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3285">Checksum</span></span>

<span data-ttu-id="a2b91-3286">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3286">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3287">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3287">Definition</span></span>

<span data-ttu-id="a2b91-3288">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3288">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3289">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3289">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3290">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3290">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a2b91-3291">Keyword_us_drivers_license のキーワードを検出しました。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3291">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="a2b91-3292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3292">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3293">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3293">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3294">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3294">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="a2b91-3295">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3295">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="a2b91-3296">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3296">No keyword from Keyword_us_drivers_license is found.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3297">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3297">Keywords</span></span>

#### <a name="keywordusdriverslicenseabbreviations"></a><span data-ttu-id="a2b91-3298">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="a2b91-3298">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="a2b91-3299">DL</span><span class="sxs-lookup"><span data-stu-id="a2b91-3299">DL</span></span> 
- <span data-ttu-id="a2b91-3300">DLS</span><span class="sxs-lookup"><span data-stu-id="a2b91-3300">DLS</span></span> 
- <span data-ttu-id="a2b91-3301">CDL</span><span class="sxs-lookup"><span data-stu-id="a2b91-3301">CDL</span></span> 
- <span data-ttu-id="a2b91-3302">cdls</span><span class="sxs-lookup"><span data-stu-id="a2b91-3302">CDLS</span></span> 
- <span data-ttu-id="a2b91-3303">ID</span><span class="sxs-lookup"><span data-stu-id="a2b91-3303">ID</span></span> 
- <span data-ttu-id="a2b91-3304">rid</span><span class="sxs-lookup"><span data-stu-id="a2b91-3304">IDs</span></span> 
- <span data-ttu-id="a2b91-3305">DL#</span><span class="sxs-lookup"><span data-stu-id="a2b91-3305">DL#</span></span> 
- <span data-ttu-id="a2b91-3306">
DLS#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3306">DLS#</span></span> 
- <span data-ttu-id="a2b91-3307">CDL#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3307">CDL#</span></span> 
- <span data-ttu-id="a2b91-3308">CDLS#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3308">CDLS#</span></span> 
- <span data-ttu-id="a2b91-3309">ID#</span><span class="sxs-lookup"><span data-stu-id="a2b91-3309">ID#</span></span>
- <span data-ttu-id="a2b91-3310">
IDs#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3310">IDs#</span></span> 
- <span data-ttu-id="a2b91-3311">ID number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3311">ID number</span></span> 
- <span data-ttu-id="a2b91-3312">ID numbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3312">ID numbers</span></span> 
- <span data-ttu-id="a2b91-3313">そして</span><span class="sxs-lookup"><span data-stu-id="a2b91-3313">LIC</span></span> 
- <span data-ttu-id="a2b91-3314">LIC#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3314">LIC#</span></span> 

#### <a name="keywordusdriverslicense"></a><span data-ttu-id="a2b91-3315">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="a2b91-3315">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="a2b91-3316">driverlic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3316">DriverLic</span></span> 
- <span data-ttu-id="a2b91-3317">driverlics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3317">DriverLics</span></span> 
- <span data-ttu-id="a2b91-3318">driverlicense</span><span class="sxs-lookup"><span data-stu-id="a2b91-3318">DriverLicense</span></span> 
- <span data-ttu-id="a2b91-3319">driverlicenses</span><span class="sxs-lookup"><span data-stu-id="a2b91-3319">DriverLicenses</span></span> 
- <span data-ttu-id="a2b91-3320">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3320">Driver Lic</span></span> 
- <span data-ttu-id="a2b91-3321">ドライバー lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3321">Driver Lics</span></span> 
- <span data-ttu-id="a2b91-3322">ドライバーライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3322">Driver License</span></span> 
- <span data-ttu-id="a2b91-3323">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3323">Driver Licenses</span></span> 
- <span data-ttu-id="a2b91-3324">driverslic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3324">DriversLic</span></span> 
- <span data-ttu-id="a2b91-3325">driverslics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3325">DriversLics</span></span> 
- <span data-ttu-id="a2b91-3326">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="a2b91-3326">DriversLicense</span></span> 
- <span data-ttu-id="a2b91-3327">このライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3327">DriversLicenses</span></span> 
- <span data-ttu-id="a2b91-3328">ドライバー Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3328">Drivers Lic</span></span> 
- <span data-ttu-id="a2b91-3329">ドライバー lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3329">Drivers Lics</span></span> 
- <span data-ttu-id="a2b91-3330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3330">Drivers License</span></span> 
- <span data-ttu-id="a2b91-3331">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3331">Drivers Licenses</span></span> 
- <span data-ttu-id="a2b91-3332">driver' Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3332">Driver'Lic</span></span> 
- <span data-ttu-id="a2b91-3333">driver' lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3333">Driver'Lics</span></span> 
- <span data-ttu-id="a2b91-3334">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3334">Driver'License</span></span> 
- <span data-ttu-id="a2b91-3335">driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3335">Driver'Licenses</span></span> 
- <span data-ttu-id="a2b91-3336">ドライバー ' Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3336">Driver' Lic</span></span> 
- <span data-ttu-id="a2b91-3337">ドライバー ' lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3337">Driver' Lics</span></span> 
- <span data-ttu-id="a2b91-3338">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3338">Driver' License</span></span> 
- <span data-ttu-id="a2b91-3339">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3339">Driver' Licenses</span></span>
- <span data-ttu-id="a2b91-3340">driver' slic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3340">Driver'sLic</span></span> 
- <span data-ttu-id="a2b91-3341">driver' slics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3341">Driver'sLics</span></span> 
- <span data-ttu-id="a2b91-3342">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3342">Driver'sLicense</span></span> 
- <span data-ttu-id="a2b91-3343">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3343">Driver'sLicenses</span></span> 
- <span data-ttu-id="a2b91-3344">ドライバーの Lic</span><span class="sxs-lookup"><span data-stu-id="a2b91-3344">Driver's Lic</span></span> 
- <span data-ttu-id="a2b91-3345">ドライバーの lics</span><span class="sxs-lookup"><span data-stu-id="a2b91-3345">Driver's Lics</span></span> 
- <span data-ttu-id="a2b91-3346">運転免許証</span><span class="sxs-lookup"><span data-stu-id="a2b91-3346">Driver's License</span></span> 
- <span data-ttu-id="a2b91-3347">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="a2b91-3347">Driver's Licenses</span></span> 
- <span data-ttu-id="a2b91-3348">identification number
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3348">identification number</span></span> 
- <span data-ttu-id="a2b91-3349">identification numbers
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3349">identification numbers</span></span> 
- <span data-ttu-id="a2b91-3350">identification #
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3350">identification #</span></span> 
- <span data-ttu-id="a2b91-3351">id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3351">id card</span></span> 
- <span data-ttu-id="a2b91-3352">id カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3352">id cards</span></span> 
- <span data-ttu-id="a2b91-3353">識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3353">identification card</span></span> 
- <span data-ttu-id="a2b91-3354">識別カード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3354">identification cards</span></span> 
- <span data-ttu-id="a2b91-3355">driverlic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3355">DriverLic#</span></span> 
- <span data-ttu-id="a2b91-3356">driverlics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3356">DriverLics#</span></span> 
- <span data-ttu-id="a2b91-3357">driverlicense #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3357">DriverLicense#</span></span> 
- <span data-ttu-id="a2b91-3358">driverlicenses #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3358">DriverLicenses#</span></span> 
- <span data-ttu-id="a2b91-3359">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="a2b91-3359">Driver Lic#</span></span> 
- <span data-ttu-id="a2b91-3360">
Driver Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3360">Driver Lics#</span></span> 
- <span data-ttu-id="a2b91-3361">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3361">Driver License#</span></span> 
- <span data-ttu-id="a2b91-3362">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3362">Driver Licenses#</span></span> 
- <span data-ttu-id="a2b91-3363">driverslic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3363">DriversLic#</span></span> 
- <span data-ttu-id="a2b91-3364">driverslics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3364">DriversLics#</span></span> 
- <span data-ttu-id="a2b91-3365">製品のライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3365">DriversLicense#</span></span> 
- <span data-ttu-id="a2b91-3366">(c#) ライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3366">DriversLicenses#</span></span> 
- <span data-ttu-id="a2b91-3367">ドライバー Lic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3367">Drivers Lic#</span></span> 
- <span data-ttu-id="a2b91-3368">ドライバー lics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3368">Drivers Lics#</span></span> 
- <span data-ttu-id="a2b91-3369">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3369">Drivers License#</span></span> 
- <span data-ttu-id="a2b91-3370">ドライバーライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3370">Drivers Licenses#</span></span> 
- <span data-ttu-id="a2b91-3371">Driver'Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3371">Driver'Lic#</span></span> 
- <span data-ttu-id="a2b91-3372">Driver'Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3372">Driver'Lics#</span></span> 
- <span data-ttu-id="a2b91-3373">Driver'License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3373">Driver'License#</span></span> 
- <span data-ttu-id="a2b91-3374">Driver'Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3374">Driver'Licenses#</span></span> 
- <span data-ttu-id="a2b91-3375">Driver' Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3375">Driver' Lic#</span></span> 
- <span data-ttu-id="a2b91-3376">Driver' Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3376">Driver' Lics#</span></span> 
- <span data-ttu-id="a2b91-3377">Driver' License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3377">Driver' License#</span></span> 
- <span data-ttu-id="a2b91-3378">Driver' Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3378">Driver' Licenses#</span></span> 
- <span data-ttu-id="a2b91-3379">driver' slic #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3379">Driver'sLic#</span></span> 
- <span data-ttu-id="a2b91-3380">driver' slics #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3380">Driver'sLics#</span></span> 
- <span data-ttu-id="a2b91-3381">driverのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3381">Driver'sLicense#</span></span> 
- <span data-ttu-id="a2b91-3382">ドライバのライセンス #</span><span class="sxs-lookup"><span data-stu-id="a2b91-3382">Driver'sLicenses#</span></span> 
- <span data-ttu-id="a2b91-3383">Driver's Lic#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3383">Driver's Lic#</span></span> 
- <span data-ttu-id="a2b91-3384">Driver's Lics#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3384">Driver's Lics#</span></span> 
- <span data-ttu-id="a2b91-3385">Driver's License#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3385">Driver's License#</span></span> 
- <span data-ttu-id="a2b91-3386">Driver's Licenses#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3386">Driver's Licenses#</span></span> 
- <span data-ttu-id="a2b91-3387">id カード番号</span><span class="sxs-lookup"><span data-stu-id="a2b91-3387">id card#</span></span> 
- <span data-ttu-id="a2b91-3388">id cards#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3388">id cards#</span></span> 
- <span data-ttu-id="a2b91-3389">identification card#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3389">identification card#</span></span> 
- <span data-ttu-id="a2b91-3390">identification cards#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3390">identification cards#</span></span> 


#### <a name="keywordstatenamedriverslicensename"></a><span data-ttu-id="a2b91-3391">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="a2b91-3391">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="a2b91-3392">州の略号 (たとえば、"NY")
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3392">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="a2b91-3393">州の名前 (たとえば、"New York")
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3393">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="a2b91-3394">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-3394">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3395">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3395">Format</span></span>

<span data-ttu-id="a2b91-3396">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="a2b91-3396">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3397">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3397">Pattern</span></span>

<span data-ttu-id="a2b91-3398">書式設定されている場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3398">Formatted:</span></span>
- <span data-ttu-id="a2b91-3399">数字「9」</span><span class="sxs-lookup"><span data-stu-id="a2b91-3399">The digit "9"</span></span> 
- <span data-ttu-id="a2b91-3400">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3400">Two digits</span></span> 
- <span data-ttu-id="a2b91-3401">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3401">A space or dash</span></span> 
- <span data-ttu-id="a2b91-3402">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="a2b91-3402">A "7" or "8"</span></span> 
- <span data-ttu-id="a2b91-3403">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3403">A digit</span></span> 
- <span data-ttu-id="a2b91-3404">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3404">A space, or dash</span></span> 
- <span data-ttu-id="a2b91-3405">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3405">Four digits</span></span>

<span data-ttu-id="a2b91-3406">書式設定されていない場合:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3406">Unformatted:</span></span>
- <span data-ttu-id="a2b91-3407">数字「9」</span><span class="sxs-lookup"><span data-stu-id="a2b91-3407">The digit "9"</span></span> 
- <span data-ttu-id="a2b91-3408">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3408">Two digits</span></span> 
- <span data-ttu-id="a2b91-3409">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="a2b91-3409">A "7" or "8"</span></span> 
- <span data-ttu-id="a2b91-3410">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3410">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3411">Checksum</span></span>

<span data-ttu-id="a2b91-3412">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3412">No</span></span>

### <a name="definition"></a><span data-ttu-id="a2b91-3413">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3413">Definition</span></span>

<span data-ttu-id="a2b91-3414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3415">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3415">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3416">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3416">At least one of the following is true:</span></span>
    - <span data-ttu-id="a2b91-3417">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3417">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="a2b91-3418">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3418">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a2b91-3419">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3419">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="a2b91-3420">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3420">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="a2b91-3421">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3421">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3422">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3422">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3423">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="a2b91-3423">At least one of the following is true:</span></span>
    - <span data-ttu-id="a2b91-3424">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3424">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="a2b91-3425">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3425">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="a2b91-3426">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3426">The function Func_us_date finds a date in the right date format.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3427">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3427">Keywords</span></span>

#### <a name="keyworditin"></a><span data-ttu-id="a2b91-3428">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="a2b91-3428">Keyword_itin</span></span>

- <span data-ttu-id="a2b91-3429">taxpayer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3429">taxpayer</span></span> 
- <span data-ttu-id="a2b91-3430">tax id
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3430">tax id</span></span> 
- <span data-ttu-id="a2b91-3431">tax identification
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3431">tax identification</span></span> 
- <span data-ttu-id="a2b91-3432">itin
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3432">itin</span></span> 
- <span data-ttu-id="a2b91-3433">ssn</span><span class="sxs-lookup"><span data-stu-id="a2b91-3433">ssn</span></span> 
- <span data-ttu-id="a2b91-3434">tin
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3434">tin</span></span> 
- <span data-ttu-id="a2b91-3435">ソーシャルセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a2b91-3435">social security</span></span> 
- <span data-ttu-id="a2b91-3436">tax payer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3436">tax payer</span></span> 
- <span data-ttu-id="a2b91-3437">itins
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3437">itins</span></span> 
- <span data-ttu-id="a2b91-3438">taxid

</span><span class="sxs-lookup"><span data-stu-id="a2b91-3438">taxid</span></span> 
- <span data-ttu-id="a2b91-3439">individual taxpayer
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3439">individual taxpayer</span></span> 

#### <a name="keyworditincollaborative"></a><span data-ttu-id="a2b91-3440">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="a2b91-3440">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="a2b91-3441">License</span><span class="sxs-lookup"><span data-stu-id="a2b91-3441">License</span></span> 
- <span data-ttu-id="a2b91-3442">DL</span><span class="sxs-lookup"><span data-stu-id="a2b91-3442">DL</span></span> 
- <span data-ttu-id="a2b91-3443">DOB
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3443">DOB</span></span> 
- <span data-ttu-id="a2b91-3444">誕生日</span><span class="sxs-lookup"><span data-stu-id="a2b91-3444">Birthdate</span></span> 
- <span data-ttu-id="a2b91-3445">誕生日 </span><span class="sxs-lookup"><span data-stu-id="a2b91-3445">Birthday</span></span> 
- <span data-ttu-id="a2b91-3446">Date of Birth
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3446">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="a2b91-3447">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="a2b91-3447">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="a2b91-3448">形式</span><span class="sxs-lookup"><span data-stu-id="a2b91-3448">Format</span></span>

<span data-ttu-id="a2b91-3449">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a2b91-3449">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="a2b91-3450">2011 年の中旬より前に発行されている場合、SSN には厳密な書式があり、数値の特定の部分が一定の範囲内に入っていなければ有効になりません。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3450">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="a2b91-3451">パターン</span><span class="sxs-lookup"><span data-stu-id="a2b91-3451">Pattern</span></span>

<span data-ttu-id="a2b91-3452">4 つの異なるパターンで SSN を検索する 4 つの関数を次に示します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3452">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="a2b91-3453">Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3453">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a2b91-3454">Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3454">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="a2b91-3455">Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3455">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="a2b91-3456">Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3456">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="a2b91-3457">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a2b91-3457">Checksum</span></span>

<span data-ttu-id="a2b91-3458">なし</span><span class="sxs-lookup"><span data-stu-id="a2b91-3458">No</span></span>


### <a name="definition"></a><span data-ttu-id="a2b91-3459">定義</span><span class="sxs-lookup"><span data-stu-id="a2b91-3459">Definition</span></span>

<span data-ttu-id="a2b91-3460">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3461">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3461">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3462">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3462">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a2b91-3463">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3464">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3464">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3465">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3465">A keyword from Keyword_ssn is found.</span></span>

<span data-ttu-id="a2b91-3466">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3467">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3467">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3468">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3468">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a2b91-3469">関数 Func_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3469">The function Func_ssn does not find content that matches the pattern.</span></span>

<span data-ttu-id="a2b91-3470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3470">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="a2b91-3471">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3471">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="a2b91-3472">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3472">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="a2b91-3473">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="a2b91-3473">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>

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

### <a name="keywords"></a><span data-ttu-id="a2b91-3474">キーワード</span><span class="sxs-lookup"><span data-stu-id="a2b91-3474">Keywords</span></span>

#### <a name="keywordssn"></a><span data-ttu-id="a2b91-3475">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="a2b91-3475">Keyword_ssn</span></span>

- <span data-ttu-id="a2b91-3476">Social Security
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3476">Social Security</span></span> 
- <span data-ttu-id="a2b91-3477">Social Security#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3477">Social Security#</span></span> 
- <span data-ttu-id="a2b91-3478">Soc Sec
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3478">Soc Sec</span></span> 
- <span data-ttu-id="a2b91-3479">SSN</span><span class="sxs-lookup"><span data-stu-id="a2b91-3479">SSN</span></span> 
- <span data-ttu-id="a2b91-3480">SSNS
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3480">SSNS</span></span> 
- <span data-ttu-id="a2b91-3481">SSN#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3481">SSN#</span></span> 
- <span data-ttu-id="a2b91-3482">SS#
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3482">SS#</span></span> 
- <span data-ttu-id="a2b91-3483">SSID
</span><span class="sxs-lookup"><span data-stu-id="a2b91-3483">SSID</span></span> 
   

