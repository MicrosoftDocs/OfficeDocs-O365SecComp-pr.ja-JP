---
title: 機密情報の種類の検索基準：
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 05/20/2019
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
ms.openlocfilehash: d486510c35aaf147e6d63e28d1df36ef689e3975
ms.sourcegitcommit: a5a7e43822336ed18d8f5879167766686cf6b2a3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2019
ms.locfileid: "36478256"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="11037-104">機密情報の種類の検索基準</span><span class="sxs-lookup"><span data-stu-id="11037-104">What the sensitive information types look for</span></span>

<span data-ttu-id="11037-105">Office 365 セキュリティ&amp;コンプライアンスセンターのデータ損失防止 (DLP) には、dlp ポリシーで使用できるさまざまな機密情報の種類が含まれています。</span><span class="sxs-lookup"><span data-stu-id="11037-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="11037-106">このトピックでは、機密情報の種類をすべて一覧表示し、各種類を検出したときに DLP ポリシーが調査する内容を示します。</span><span class="sxs-lookup"><span data-stu-id="11037-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="11037-107">機密情報の種類はパターンで定義され、正規表現または関数で識別できます。</span><span class="sxs-lookup"><span data-stu-id="11037-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="11037-108">機密情報の種類はさらに、キーワードやチェックサムなどの確証的な証拠を使用して識別することもできます。</span><span class="sxs-lookup"><span data-stu-id="11037-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="11037-109">信頼レベルと近接も、評価プロセスで使用されます。</span><span class="sxs-lookup"><span data-stu-id="11037-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="11037-110">ABA ルーティング番号</span><span class="sxs-lookup"><span data-stu-id="11037-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-111">Format</span><span class="sxs-lookup"><span data-stu-id="11037-111">Format</span></span>

<span data-ttu-id="11037-112">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-113">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-113">Pattern</span></span>

<span data-ttu-id="11037-114">さ</span><span class="sxs-lookup"><span data-stu-id="11037-114">Formatted:</span></span>
- <span data-ttu-id="11037-115">0、1、2、3、6、7、または 8 で始まる 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="11037-116">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-116">A hyphen</span></span>
- <span data-ttu-id="11037-117">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-117">Four digits</span></span>
- <span data-ttu-id="11037-118">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-118">A hyphen</span></span>
- <span data-ttu-id="11037-119">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-119">A digit</span></span>

<span data-ttu-id="11037-120">書式なし: 0、1、2、3、6、7、または8で始まる9桁の連続した数字</span><span class="sxs-lookup"><span data-stu-id="11037-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="11037-121">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-121">Checksum</span></span>

<span data-ttu-id="11037-122">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-123">定義</span><span class="sxs-lookup"><span data-stu-id="11037-123">Definition</span></span>

<span data-ttu-id="11037-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-125">関数 Func_aba_routing がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-126">Keyword_ABA_Routing のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="11037-127">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="11037-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="11037-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="11037-129">aba</span><span class="sxs-lookup"><span data-stu-id="11037-129">aba</span></span>
- <span data-ttu-id="11037-130">aba #</span><span class="sxs-lookup"><span data-stu-id="11037-130">aba #</span></span>
- <span data-ttu-id="11037-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="11037-131">aba routing #</span></span>
- <span data-ttu-id="11037-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="11037-132">aba routing number</span></span>
- <span data-ttu-id="11037-133">aba#</span><span class="sxs-lookup"><span data-stu-id="11037-133">aba#</span></span>
- <span data-ttu-id="11037-134">abarouting#</span><span class="sxs-lookup"><span data-stu-id="11037-134">abarouting#</span></span>
- <span data-ttu-id="11037-135">aba number</span><span class="sxs-lookup"><span data-stu-id="11037-135">aba number</span></span>
- <span data-ttu-id="11037-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="11037-136">abaroutingnumber</span></span>
- <span data-ttu-id="11037-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="11037-137">american bank association routing #</span></span>
- <span data-ttu-id="11037-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="11037-138">american bank association routing number</span></span>
- <span data-ttu-id="11037-139">americanbankassociationrouting#</span><span class="sxs-lookup"><span data-stu-id="11037-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="11037-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="11037-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="11037-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="11037-141">bank routing number</span></span>
- <span data-ttu-id="11037-142">bankrouting#</span><span class="sxs-lookup"><span data-stu-id="11037-142">bankrouting#</span></span>
- <span data-ttu-id="11037-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="11037-143">bankroutingnumber</span></span>
- <span data-ttu-id="11037-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="11037-144">routing transit number</span></span>
- <span data-ttu-id="11037-145">RTN</span><span class="sxs-lookup"><span data-stu-id="11037-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="11037-146">アルゼンチンの国民識別 (DNI) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-147">Format</span><span class="sxs-lookup"><span data-stu-id="11037-147">Format</span></span>

<span data-ttu-id="11037-148">ピリオドで区切られた 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-149">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-149">Pattern</span></span>

<span data-ttu-id="11037-150">8 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-150">Eight digits:</span></span>
- <span data-ttu-id="11037-151">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-151">Two digits</span></span>
- <span data-ttu-id="11037-152">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-152">A period</span></span>
- <span data-ttu-id="11037-153">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-153">Three digits</span></span>
- <span data-ttu-id="11037-154">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-154">A period</span></span>
- <span data-ttu-id="11037-155">3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-156">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-156">Checksum</span></span>

<span data-ttu-id="11037-157">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-158">定義</span><span class="sxs-lookup"><span data-stu-id="11037-158">Definition</span></span>

<span data-ttu-id="11037-159">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-160">正規表現 Regex_argentina_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-161">Keyword_argentina_national_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-162">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="11037-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="11037-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="11037-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="11037-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="11037-165">ID</span><span class="sxs-lookup"><span data-stu-id="11037-165">Identity</span></span> 
- <span data-ttu-id="11037-166">識別国の Id カード</span><span class="sxs-lookup"><span data-stu-id="11037-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="11037-167">DNI</span><span class="sxs-lookup"><span data-stu-id="11037-167">DNI</span></span> 
- <span data-ttu-id="11037-168">個人の NIC National レジストリ</span><span class="sxs-lookup"><span data-stu-id="11037-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="11037-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="11037-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="11037-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="11037-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="11037-171">Dad の識別子</span><span class="sxs-lookup"><span data-stu-id="11037-171">Identidad</span></span> 
- <span data-ttu-id="11037-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="11037-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="11037-173">オーストラリアの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-174">Format</span><span class="sxs-lookup"><span data-stu-id="11037-174">Format</span></span>

<span data-ttu-id="11037-175">銀行支店識別コード (BSB) を含むまたは含まない 6 ～ 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-176">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-176">Pattern</span></span>

<span data-ttu-id="11037-177">口座番号は 6 ～ 10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="11037-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="11037-178">オーストラリアの銀行の州支店番号:</span><span class="sxs-lookup"><span data-stu-id="11037-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="11037-179">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-179">Three digits</span></span> 
- <span data-ttu-id="11037-180">ハイフン</span><span class="sxs-lookup"><span data-stu-id="11037-180">A hyphen</span></span> 
- <span data-ttu-id="11037-181">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-182">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-182">Checksum</span></span>

<span data-ttu-id="11037-183">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-184">定義</span><span class="sxs-lookup"><span data-stu-id="11037-184">Definition</span></span>

<span data-ttu-id="11037-185">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-186">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="11037-187">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="11037-188">正規表現 Regex_australia_bank_account_number_bsb がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="11037-189">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-190">正規表現 Regex_australia_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="11037-191">Keyword_australia_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-192">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="11037-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="11037-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="11037-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="11037-194">swift bank code</span></span>
- <span data-ttu-id="11037-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="11037-195">correspondent bank</span></span>
- <span data-ttu-id="11037-196">base currency</span><span class="sxs-lookup"><span data-stu-id="11037-196">base currency</span></span>
- <span data-ttu-id="11037-197">usa account</span><span class="sxs-lookup"><span data-stu-id="11037-197">usa account</span></span>
- <span data-ttu-id="11037-198">holder address</span><span class="sxs-lookup"><span data-stu-id="11037-198">holder address</span></span>
- <span data-ttu-id="11037-199">bank address</span><span class="sxs-lookup"><span data-stu-id="11037-199">bank address</span></span>
- <span data-ttu-id="11037-200">information account</span><span class="sxs-lookup"><span data-stu-id="11037-200">information account</span></span>
- <span data-ttu-id="11037-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="11037-201">fund transfers</span></span>
- <span data-ttu-id="11037-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="11037-202">bank charges</span></span>
- <span data-ttu-id="11037-203">bank details</span><span class="sxs-lookup"><span data-stu-id="11037-203">bank details</span></span>
- <span data-ttu-id="11037-204">banking information</span><span class="sxs-lookup"><span data-stu-id="11037-204">banking information</span></span>
- <span data-ttu-id="11037-205">full names</span><span class="sxs-lookup"><span data-stu-id="11037-205">full names</span></span>
- <span data-ttu-id="11037-206">iaea</span><span class="sxs-lookup"><span data-stu-id="11037-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="11037-207">オーストラリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-208">Format</span><span class="sxs-lookup"><span data-stu-id="11037-208">Format</span></span>

<span data-ttu-id="11037-209">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="11037-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-210">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-210">Pattern</span></span>

<span data-ttu-id="11037-211">9 つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="11037-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="11037-212">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="11037-213">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-213">Two digits</span></span> 
- <span data-ttu-id="11037-214">5 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="11037-215">OR</span><span class="sxs-lookup"><span data-stu-id="11037-215">OR</span></span>

- <span data-ttu-id="11037-216">1 ～ 2 桁の省略可能な文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="11037-217">4 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-217">4-9 digits</span></span>

<span data-ttu-id="11037-218">OR</span><span class="sxs-lookup"><span data-stu-id="11037-218">OR</span></span>

- <span data-ttu-id="11037-219">9 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="11037-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-220">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-220">Checksum</span></span>

<span data-ttu-id="11037-221">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-222">定義</span><span class="sxs-lookup"><span data-stu-id="11037-222">Definition</span></span>

<span data-ttu-id="11037-223">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-224">正規表現 Regex_australia_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-225">Keyword_australia_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="11037-226">Keyword_australia_drivers_license_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="11037-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="11037-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="11037-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="11037-229">international driving permits</span></span>
- <span data-ttu-id="11037-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="11037-230">australian automobile association</span></span>
- <span data-ttu-id="11037-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="11037-231">international driving permit</span></span>
- <span data-ttu-id="11037-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="11037-232">DriverLicence</span></span>
- <span data-ttu-id="11037-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="11037-233">DriverLicences</span></span>
- <span data-ttu-id="11037-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="11037-234">Driver Lic</span></span>
- <span data-ttu-id="11037-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="11037-235">Driver Licence</span></span>
- <span data-ttu-id="11037-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="11037-236">Driver Licences</span></span>
- <span data-ttu-id="11037-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="11037-237">DriversLic</span></span>
- <span data-ttu-id="11037-238">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-238">DriversLicence</span></span>
- <span data-ttu-id="11037-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="11037-239">DriversLicences</span></span>
- <span data-ttu-id="11037-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="11037-240">Drivers Lic</span></span>
- <span data-ttu-id="11037-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="11037-241">Drivers Lics</span></span>
- <span data-ttu-id="11037-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="11037-242">Drivers Licence</span></span>
- <span data-ttu-id="11037-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="11037-243">Drivers Licences</span></span>
- <span data-ttu-id="11037-244">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="11037-244">Driver'Lic</span></span>
- <span data-ttu-id="11037-245">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="11037-245">Driver'Lics</span></span>
- <span data-ttu-id="11037-246">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-246">Driver'Licence</span></span>
- <span data-ttu-id="11037-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="11037-247">Driver'Licences</span></span>
- <span data-ttu-id="11037-248">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="11037-248">Driver' Lic</span></span>
- <span data-ttu-id="11037-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="11037-249">Driver' Lics</span></span>
- <span data-ttu-id="11037-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="11037-250">Driver' Licence</span></span>
- <span data-ttu-id="11037-251">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="11037-251">Driver' Licences</span></span>
- <span data-ttu-id="11037-252">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="11037-252">Driver'sLic</span></span>
- <span data-ttu-id="11037-253">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="11037-253">Driver'sLics</span></span>
- <span data-ttu-id="11037-254">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="11037-254">Driver'sLicence</span></span>
- <span data-ttu-id="11037-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="11037-255">Driver'sLicences</span></span>
- <span data-ttu-id="11037-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="11037-256">Driver's Lic</span></span>
- <span data-ttu-id="11037-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="11037-257">Driver's Lics</span></span>
- <span data-ttu-id="11037-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="11037-258">Driver's Licence</span></span>
- <span data-ttu-id="11037-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="11037-259">Driver's Licences</span></span>
- <span data-ttu-id="11037-260">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="11037-260">DriverLic#</span></span>
- <span data-ttu-id="11037-261">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="11037-261">DriverLics#</span></span>
- <span data-ttu-id="11037-262">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="11037-262">DriverLicence#</span></span>
- <span data-ttu-id="11037-263">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="11037-263">DriverLicences#</span></span>
- <span data-ttu-id="11037-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-264">Driver Lic#</span></span>
- <span data-ttu-id="11037-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-265">Driver Lics#</span></span>
- <span data-ttu-id="11037-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-266">Driver Licence#</span></span>
- <span data-ttu-id="11037-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-267">Driver Licences#</span></span>
- <span data-ttu-id="11037-268">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="11037-268">DriversLic#</span></span>
- <span data-ttu-id="11037-269">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="11037-269">DriversLics#</span></span>
- <span data-ttu-id="11037-270">その他のライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-270">DriversLicence#</span></span>
- <span data-ttu-id="11037-271">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="11037-271">DriversLicences#</span></span>
- <span data-ttu-id="11037-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-272">Drivers Lic#</span></span>
- <span data-ttu-id="11037-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-273">Drivers Lics#</span></span>
- <span data-ttu-id="11037-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-274">Drivers Licence#</span></span>
- <span data-ttu-id="11037-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-275">Drivers Licences#</span></span>
- <span data-ttu-id="11037-276">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-276">Driver'Lic#</span></span>
- <span data-ttu-id="11037-277">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-277">Driver'Lics#</span></span>
- <span data-ttu-id="11037-278">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-278">Driver'Licence#</span></span>
- <span data-ttu-id="11037-279">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-279">Driver'Licences#</span></span>
- <span data-ttu-id="11037-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-280">Driver' Lic#</span></span>
- <span data-ttu-id="11037-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-281">Driver' Lics#</span></span>
- <span data-ttu-id="11037-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-282">Driver' Licence#</span></span>
- <span data-ttu-id="11037-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-283">Driver' Licences#</span></span>
- <span data-ttu-id="11037-284">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="11037-284">Driver'sLic#</span></span>
- <span data-ttu-id="11037-285">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="11037-285">Driver'sLics#</span></span>
- <span data-ttu-id="11037-286">ドライバ ' スライスの持続性#</span><span class="sxs-lookup"><span data-stu-id="11037-286">Driver'sLicence#</span></span>
- <span data-ttu-id="11037-287">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="11037-287">Driver'sLicences#</span></span>
- <span data-ttu-id="11037-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-288">Driver's Lic#</span></span>
- <span data-ttu-id="11037-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-289">Driver's Lics#</span></span>
- <span data-ttu-id="11037-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-290">Driver's Licence#</span></span>
- <span data-ttu-id="11037-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="11037-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="11037-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="11037-293">aaa</span><span class="sxs-lookup"><span data-stu-id="11037-293">aaa</span></span>
- <span data-ttu-id="11037-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="11037-294">DriverLicense</span></span>
- <span data-ttu-id="11037-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="11037-295">DriverLicenses</span></span>
- <span data-ttu-id="11037-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="11037-296">Driver License</span></span>
- <span data-ttu-id="11037-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-297">Driver Licenses</span></span>
- <span data-ttu-id="11037-298">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="11037-298">DriversLicense</span></span>
- <span data-ttu-id="11037-299">このライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-299">DriversLicenses</span></span>
- <span data-ttu-id="11037-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="11037-300">Drivers License</span></span>
- <span data-ttu-id="11037-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-301">Drivers Licenses</span></span>
- <span data-ttu-id="11037-302">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-302">Driver'License</span></span>
- <span data-ttu-id="11037-303">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-303">Driver'Licenses</span></span>
- <span data-ttu-id="11037-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="11037-304">Driver' License</span></span>
- <span data-ttu-id="11037-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-305">Driver' Licenses</span></span>
- <span data-ttu-id="11037-306">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-306">Driver'sLicense</span></span>
- <span data-ttu-id="11037-307">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-307">Driver'sLicenses</span></span>
- <span data-ttu-id="11037-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="11037-308">Driver's License</span></span>
- <span data-ttu-id="11037-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-309">Driver's Licenses</span></span>
- <span data-ttu-id="11037-310">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="11037-310">DriverLicense#</span></span>
- <span data-ttu-id="11037-311">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="11037-311">DriverLicenses#</span></span>
- <span data-ttu-id="11037-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="11037-312">Driver License#</span></span>
- <span data-ttu-id="11037-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-313">Driver Licenses#</span></span>
- <span data-ttu-id="11037-314">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="11037-314">DriversLicense#</span></span>
- <span data-ttu-id="11037-315">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-315">DriversLicenses#</span></span>
- <span data-ttu-id="11037-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="11037-316">Drivers License#</span></span>
- <span data-ttu-id="11037-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-317">Drivers Licenses#</span></span>
- <span data-ttu-id="11037-318">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-318">Driver'License#</span></span>
- <span data-ttu-id="11037-319">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-319">Driver'Licenses#</span></span>
- <span data-ttu-id="11037-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="11037-320">Driver' License#</span></span>
- <span data-ttu-id="11037-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-321">Driver' Licenses#</span></span>
- <span data-ttu-id="11037-322">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-322">Driver'sLicense#</span></span>
- <span data-ttu-id="11037-323">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="11037-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="11037-324">Driver's License#</span></span>
- <span data-ttu-id="11037-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="11037-326">オーストラリアの医療口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-327">Format</span><span class="sxs-lookup"><span data-stu-id="11037-327">Format</span></span>

<span data-ttu-id="11037-328">10 ～ 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-329">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-329">Pattern</span></span>

<span data-ttu-id="11037-330">10 ～ 11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-330">10-11 digits:</span></span>
- <span data-ttu-id="11037-331">最初の桁は 2 ～ 6 のいずれか</span><span class="sxs-lookup"><span data-stu-id="11037-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="11037-332">9 桁目はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="11037-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="11037-333">10 桁目は発行桁</span><span class="sxs-lookup"><span data-stu-id="11037-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="11037-334">11 桁目 (省略可能) は個人番号</span><span class="sxs-lookup"><span data-stu-id="11037-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-335">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-335">Checksum</span></span>

<span data-ttu-id="11037-336">はい</span><span class="sxs-lookup"><span data-stu-id="11037-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-337">定義</span><span class="sxs-lookup"><span data-stu-id="11037-337">Definition</span></span>

<span data-ttu-id="11037-338">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-339">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-340">Keyword_Australia_Medical_Account_Number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="11037-341">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-341">The checksum passes.</span></span>

<span data-ttu-id="11037-342">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-343">関数 Func_australian_medical_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-344">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-344">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-345">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="11037-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="11037-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="11037-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="11037-347">bank account details</span></span>
- <span data-ttu-id="11037-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="11037-348">medicare payments</span></span>
- <span data-ttu-id="11037-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="11037-349">mortgage account</span></span>
- <span data-ttu-id="11037-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="11037-350">bank payments</span></span>
- <span data-ttu-id="11037-351">information branch</span><span class="sxs-lookup"><span data-stu-id="11037-351">information branch</span></span>
- <span data-ttu-id="11037-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="11037-352">credit card loan</span></span>
- <span data-ttu-id="11037-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="11037-353">department of human services</span></span>
- <span data-ttu-id="11037-354">local service</span><span class="sxs-lookup"><span data-stu-id="11037-354">local service</span></span>
- <span data-ttu-id="11037-355">medicare</span><span class="sxs-lookup"><span data-stu-id="11037-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="11037-356">オーストラリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-357">Format</span><span class="sxs-lookup"><span data-stu-id="11037-357">Format</span></span>

<span data-ttu-id="11037-358">1 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-359">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-359">Pattern</span></span>

<span data-ttu-id="11037-360">1 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-361">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-361">Checksum</span></span>

<span data-ttu-id="11037-362">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-363">定義</span><span class="sxs-lookup"><span data-stu-id="11037-363">Definition</span></span>

<span data-ttu-id="11037-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-365">正規表現 Regex_australia_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-366">Keyword_passport または Keyword_australia_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-367">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="11037-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="11037-368">Keyword_passport</span></span>

- <span data-ttu-id="11037-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="11037-369">Passport Number</span></span>
- <span data-ttu-id="11037-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="11037-370">Passport No</span></span>
- <span data-ttu-id="11037-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="11037-371">Passport #</span></span>
- <span data-ttu-id="11037-372">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="11037-372">Passport#</span></span>
- <span data-ttu-id="11037-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="11037-373">PassportID</span></span>
- <span data-ttu-id="11037-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="11037-374">Passportno</span></span>
- <span data-ttu-id="11037-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="11037-375">passportnumber</span></span>
- <span data-ttu-id="11037-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="11037-376">パスポート</span></span>
- <span data-ttu-id="11037-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-377">パスポート番号</span></span>
- <span data-ttu-id="11037-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="11037-378">パスポートのNum</span></span>
- <span data-ttu-id="11037-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="11037-379">パスポート ＃</span></span> 
- <span data-ttu-id="11037-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="11037-380">Numéro de passeport</span></span>
- <span data-ttu-id="11037-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="11037-381">Passeport n °</span></span>
- <span data-ttu-id="11037-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="11037-382">Passeport Non</span></span>
- <span data-ttu-id="11037-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="11037-383">Passeport #</span></span>
- <span data-ttu-id="11037-384">Passeport#</span><span class="sxs-lookup"><span data-stu-id="11037-384">Passeport#</span></span>
- <span data-ttu-id="11037-385">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="11037-385">PasseportNon</span></span>
- <span data-ttu-id="11037-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="11037-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="11037-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="11037-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="11037-388">サインアウト</span><span class="sxs-lookup"><span data-stu-id="11037-388">passport</span></span>
- <span data-ttu-id="11037-389">passport details</span><span class="sxs-lookup"><span data-stu-id="11037-389">passport details</span></span>
- <span data-ttu-id="11037-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="11037-390">immigration and citizenship</span></span>
- <span data-ttu-id="11037-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="11037-391">commonwealth of australia</span></span>
- <span data-ttu-id="11037-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="11037-392">department of immigration</span></span>
- <span data-ttu-id="11037-393">residential address</span><span class="sxs-lookup"><span data-stu-id="11037-393">residential address</span></span>
- <span data-ttu-id="11037-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="11037-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="11037-395">visa</span><span class="sxs-lookup"><span data-stu-id="11037-395">visa</span></span>
- <span data-ttu-id="11037-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="11037-396">national identity card</span></span>
- <span data-ttu-id="11037-397">passport number</span><span class="sxs-lookup"><span data-stu-id="11037-397">passport number</span></span>
- <span data-ttu-id="11037-398">travel document</span><span class="sxs-lookup"><span data-stu-id="11037-398">travel document</span></span>
- <span data-ttu-id="11037-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="11037-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="11037-400">オーストラリアの納税者番号</span><span class="sxs-lookup"><span data-stu-id="11037-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-401">Format</span><span class="sxs-lookup"><span data-stu-id="11037-401">Format</span></span>

<span data-ttu-id="11037-402">8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-403">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-403">Pattern</span></span>

<span data-ttu-id="11037-404">8 ～ 9 桁の数字。通常は次のようにスペースが含まれます。</span><span class="sxs-lookup"><span data-stu-id="11037-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="11037-405">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-405">Three digits</span></span> 
- <span data-ttu-id="11037-406">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="11037-406">An optional space</span></span> 
- <span data-ttu-id="11037-407">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-407">Three digits</span></span> 
- <span data-ttu-id="11037-408">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="11037-408">An optional space</span></span> 
- <span data-ttu-id="11037-409">2 ～ 3 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="11037-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-410">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-410">Checksum</span></span>

<span data-ttu-id="11037-411">はい</span><span class="sxs-lookup"><span data-stu-id="11037-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-412">定義</span><span class="sxs-lookup"><span data-stu-id="11037-412">Definition</span></span>

<span data-ttu-id="11037-413">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-414">関数 Func_australian_tax_file_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-415">Keyword_Australia_Tax_File_Number または Keyword_number_exclusions のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="11037-416">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="11037-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="11037-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="11037-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="11037-419">australian business number</span></span>
- <span data-ttu-id="11037-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="11037-420">marginal tax rate</span></span>
- <span data-ttu-id="11037-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="11037-421">medicare levy</span></span>
- <span data-ttu-id="11037-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="11037-422">portfolio number</span></span>
- <span data-ttu-id="11037-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="11037-423">service veterans</span></span>
- <span data-ttu-id="11037-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="11037-424">withholding tax</span></span>
- <span data-ttu-id="11037-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="11037-425">individual tax return</span></span>
- <span data-ttu-id="11037-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="11037-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="11037-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="11037-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="11037-428">00000000</span><span class="sxs-lookup"><span data-stu-id="11037-428">00000000</span></span>
- <span data-ttu-id="11037-429">11111111</span><span class="sxs-lookup"><span data-stu-id="11037-429">11111111</span></span>
- <span data-ttu-id="11037-430">22222222</span><span class="sxs-lookup"><span data-stu-id="11037-430">22222222</span></span>
- <span data-ttu-id="11037-431">33333333</span><span class="sxs-lookup"><span data-stu-id="11037-431">33333333</span></span>
- <span data-ttu-id="11037-432">44444444</span><span class="sxs-lookup"><span data-stu-id="11037-432">44444444</span></span>
- <span data-ttu-id="11037-433">55555555</span><span class="sxs-lookup"><span data-stu-id="11037-433">55555555</span></span>
- <span data-ttu-id="11037-434">66666666</span><span class="sxs-lookup"><span data-stu-id="11037-434">66666666</span></span>
- <span data-ttu-id="11037-435">77777777</span><span class="sxs-lookup"><span data-stu-id="11037-435">77777777</span></span>
- <span data-ttu-id="11037-436">88888888</span><span class="sxs-lookup"><span data-stu-id="11037-436">88888888</span></span>
- <span data-ttu-id="11037-437">99999999</span><span class="sxs-lookup"><span data-stu-id="11037-437">99999999</span></span>
- <span data-ttu-id="11037-438">000000000</span><span class="sxs-lookup"><span data-stu-id="11037-438">000000000</span></span>
- <span data-ttu-id="11037-439">111111111</span><span class="sxs-lookup"><span data-stu-id="11037-439">111111111</span></span>
- <span data-ttu-id="11037-440">222222222</span><span class="sxs-lookup"><span data-stu-id="11037-440">222222222</span></span>
- <span data-ttu-id="11037-441">333333333</span><span class="sxs-lookup"><span data-stu-id="11037-441">333333333</span></span>
- <span data-ttu-id="11037-442">444444444</span><span class="sxs-lookup"><span data-stu-id="11037-442">444444444</span></span>
- <span data-ttu-id="11037-443">555555555</span><span class="sxs-lookup"><span data-stu-id="11037-443">555555555</span></span>
- <span data-ttu-id="11037-444">666666666</span><span class="sxs-lookup"><span data-stu-id="11037-444">666666666</span></span>
- <span data-ttu-id="11037-445">777777777</span><span class="sxs-lookup"><span data-stu-id="11037-445">777777777</span></span>
- <span data-ttu-id="11037-446">888888888</span><span class="sxs-lookup"><span data-stu-id="11037-446">888888888</span></span>
- <span data-ttu-id="11037-447">999999999</span><span class="sxs-lookup"><span data-stu-id="11037-447">999999999</span></span>
- <span data-ttu-id="11037-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="11037-448">0000000000</span></span>
- <span data-ttu-id="11037-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="11037-449">1111111111</span></span>
- <span data-ttu-id="11037-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="11037-450">2222222222</span></span>
- <span data-ttu-id="11037-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="11037-451">3333333333</span></span>
- <span data-ttu-id="11037-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="11037-452">4444444444</span></span>
- <span data-ttu-id="11037-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="11037-453">5555555555</span></span>
- <span data-ttu-id="11037-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="11037-454">6666666666</span></span>
- <span data-ttu-id="11037-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="11037-455">7777777777</span></span>
- <span data-ttu-id="11037-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="11037-456">8888888888</span></span>
- <span data-ttu-id="11037-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="11037-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="11037-458">Azure DocumentDB 認証キー</span><span class="sxs-lookup"><span data-stu-id="11037-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="11037-459">Format</span><span class="sxs-lookup"><span data-stu-id="11037-459">Format</span></span>

<span data-ttu-id="11037-460">文字列 "DocumentDb" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="11037-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-461">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-461">Pattern</span></span>

- <span data-ttu-id="11037-462">文字列 "DocumentDb"</span><span class="sxs-lookup"><span data-stu-id="11037-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="11037-463">3-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-464">より大きい記号 (>)、等号 (=)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="11037-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="11037-465">86の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="11037-466">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-467">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-467">Checksum</span></span>

<span data-ttu-id="11037-468">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-469">定義</span><span class="sxs-lookup"><span data-stu-id="11037-469">Definition</span></span>

<span data-ttu-id="11037-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-471">正規表現 CEP_Regex_AzureDocumentDBAuthKey は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-472">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-473">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-475">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-476">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-476">contoso</span></span>
- <span data-ttu-id="11037-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-477">fabrikam</span></span>
- <span data-ttu-id="11037-478">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-478">northwind</span></span>
- <span data-ttu-id="11037-479">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-479">sandbox</span></span>
- <span data-ttu-id="11037-480">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-480">onebox</span></span>
- <span data-ttu-id="11037-481">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-481">localhost</span></span>
- <span data-ttu-id="11037-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-482">127.0.0.1</span></span>
- <span data-ttu-id="11037-483">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-484">com</span><span class="sxs-lookup"><span data-stu-id="11037-484">com</span></span>
- <span data-ttu-id="11037-485">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-486">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="11037-487">Azure IAAS データベースの接続文字列と Azure SQL 接続文字列</span><span class="sxs-lookup"><span data-stu-id="11037-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="11037-488">Format</span><span class="sxs-lookup"><span data-stu-id="11037-488">Format</span></span>

<span data-ttu-id="11037-489">文字列 "Server"、"server"、または "data source" の後に、次のパターンで概説されている文字と文字列を指定します (文字列 "cloudapp" を含む)。</span><span class="sxs-lookup"><span data-stu-id="11037-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="11037-490">com または "cloudapp azure。</span><span class="sxs-lookup"><span data-stu-id="11037-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="11037-491">net "または" database "です。</span><span class="sxs-lookup"><span data-stu-id="11037-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="11037-492">net "、および" Password "または" pwd "という文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="11037-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-493">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-493">Pattern</span></span>

- <span data-ttu-id="11037-494">文字列 "Server"、"server"、または "data source"</span><span class="sxs-lookup"><span data-stu-id="11037-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="11037-495">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-496">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-496">An equal sign (=)</span></span>
- <span data-ttu-id="11037-497">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-498">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-499">文字列 "cloudapp。</span><span class="sxs-lookup"><span data-stu-id="11037-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="11037-500">com "," cloudapp。</span><span class="sxs-lookup"><span data-stu-id="11037-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="11037-501">net "、または" database "です。</span><span class="sxs-lookup"><span data-stu-id="11037-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="11037-502">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-502">net"</span></span>
- <span data-ttu-id="11037-503">1-300 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-504">文字列 "Password"、"password"、または "pwd"</span><span class="sxs-lookup"><span data-stu-id="11037-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="11037-505">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-506">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-506">An equal sign (=)</span></span>
- <span data-ttu-id="11037-507">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-508">セミコロンではない1つ以上の文字 (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="11037-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="11037-509">セミコロン (;)、引用符 (")、またはアポストロフィ (')</span><span class="sxs-lookup"><span data-stu-id="11037-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-510">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-510">Checksum</span></span>

<span data-ttu-id="11037-511">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-512">定義</span><span class="sxs-lookup"><span data-stu-id="11037-512">Definition</span></span>

<span data-ttu-id="11037-513">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-514">正規表現 CEP_Regex_AzureConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-515">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-516">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-518">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-519">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-519">contoso</span></span>
- <span data-ttu-id="11037-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-520">fabrikam</span></span>
- <span data-ttu-id="11037-521">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-521">northwind</span></span>
- <span data-ttu-id="11037-522">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-522">sandbox</span></span>
- <span data-ttu-id="11037-523">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-523">onebox</span></span>
- <span data-ttu-id="11037-524">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-524">localhost</span></span>
- <span data-ttu-id="11037-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-525">127.0.0.1</span></span>
- <span data-ttu-id="11037-526">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-527">com</span><span class="sxs-lookup"><span data-stu-id="11037-527">com</span></span>
- <span data-ttu-id="11037-528">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-529">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="11037-530">Azure IoT 接続文字列</span><span class="sxs-lookup"><span data-stu-id="11037-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="11037-531">Format</span><span class="sxs-lookup"><span data-stu-id="11037-531">Format</span></span>

<span data-ttu-id="11037-532">文字列 "HostName" の後に、次のパターンで概説されている文字と文字列 ("azure デバイス" を含む)。</span><span class="sxs-lookup"><span data-stu-id="11037-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="11037-533">net "および" SharedAccessKey "。</span><span class="sxs-lookup"><span data-stu-id="11037-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-534">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-534">Pattern</span></span>

- <span data-ttu-id="11037-535">文字列 "HostName"</span><span class="sxs-lookup"><span data-stu-id="11037-535">The string "HostName"</span></span>
- <span data-ttu-id="11037-536">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-537">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-537">An equal sign (=)</span></span>
- <span data-ttu-id="11037-538">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-539">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-540">文字列 "azure デバイス。</span><span class="sxs-lookup"><span data-stu-id="11037-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="11037-541">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-541">net"</span></span>
- <span data-ttu-id="11037-542">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-543">文字列 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="11037-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="11037-544">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-545">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-545">An equal sign (=)</span></span>
- <span data-ttu-id="11037-546">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-547">43の小文字または小文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="11037-548">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-549">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-549">Checksum</span></span>

<span data-ttu-id="11037-550">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-551">定義</span><span class="sxs-lookup"><span data-stu-id="11037-551">Definition</span></span>

<span data-ttu-id="11037-552">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-553">正規表現 CEP_Regex_AzureIoTConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-554">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-555">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-557">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-558">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-558">contoso</span></span>
- <span data-ttu-id="11037-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-559">fabrikam</span></span>
- <span data-ttu-id="11037-560">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-560">northwind</span></span>
- <span data-ttu-id="11037-561">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-561">sandbox</span></span>
- <span data-ttu-id="11037-562">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-562">onebox</span></span>
- <span data-ttu-id="11037-563">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-563">localhost</span></span>
- <span data-ttu-id="11037-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-564">127.0.0.1</span></span>
- <span data-ttu-id="11037-565">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-566">com</span><span class="sxs-lookup"><span data-stu-id="11037-566">com</span></span>
- <span data-ttu-id="11037-567">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-568">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="11037-569">Azure 発行設定パスワード</span><span class="sxs-lookup"><span data-stu-id="11037-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="11037-570">Format</span><span class="sxs-lookup"><span data-stu-id="11037-570">Format</span></span>

<span data-ttu-id="11037-571">文字列 "userpwd =" に続けて英数字の文字列を指定します。</span><span class="sxs-lookup"><span data-stu-id="11037-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-572">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-572">Pattern</span></span>

- <span data-ttu-id="11037-573">文字列 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="11037-573">The string "userpwd="</span></span>
- <span data-ttu-id="11037-574">60小文字または数字の任意の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="11037-575">二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="11037-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-576">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-576">Checksum</span></span>

<span data-ttu-id="11037-577">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-578">定義</span><span class="sxs-lookup"><span data-stu-id="11037-578">Definition</span></span>

<span data-ttu-id="11037-579">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-580">正規表現 CEP_Regex_AzurePublishSettingPasswords は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-581">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-582">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-584">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-585">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-585">contoso</span></span>
- <span data-ttu-id="11037-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-586">fabrikam</span></span>
- <span data-ttu-id="11037-587">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-587">northwind</span></span>
- <span data-ttu-id="11037-588">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-588">sandbox</span></span>
- <span data-ttu-id="11037-589">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-589">onebox</span></span>
- <span data-ttu-id="11037-590">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-590">localhost</span></span>
- <span data-ttu-id="11037-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-591">127.0.0.1</span></span>
- <span data-ttu-id="11037-592">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-593">com</span><span class="sxs-lookup"><span data-stu-id="11037-593">com</span></span>
- <span data-ttu-id="11037-594">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-595">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="11037-596">Azure Redis Cache 接続文字列</span><span class="sxs-lookup"><span data-stu-id="11037-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="11037-597">Format</span><span class="sxs-lookup"><span data-stu-id="11037-597">Format</span></span>

<span data-ttu-id="11037-598">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="11037-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="11037-599">net "の後に、次のパターンで概説されている文字と文字列を指定します。文字列" password "または" pwd "が含まれます。</span><span class="sxs-lookup"><span data-stu-id="11037-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-600">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-600">Pattern</span></span>

- <span data-ttu-id="11037-601">文字列 "redis...</span><span class="sxs-lookup"><span data-stu-id="11037-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="11037-602">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-602">net"</span></span>
- <span data-ttu-id="11037-603">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-604">文字列 "password" または "pwd"</span><span class="sxs-lookup"><span data-stu-id="11037-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="11037-605">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-606">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-606">An equal sign (=)</span></span>
- <span data-ttu-id="11037-607">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-608">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="11037-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="11037-609">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-610">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-610">Checksum</span></span>

<span data-ttu-id="11037-611">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-612">定義</span><span class="sxs-lookup"><span data-stu-id="11037-612">Definition</span></span>

<span data-ttu-id="11037-613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-614">正規表現 CEP_Regex_AzureRedisCacheConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="11037-615">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-616">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-618">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-619">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-619">contoso</span></span>
- <span data-ttu-id="11037-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-620">fabrikam</span></span>
- <span data-ttu-id="11037-621">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-621">northwind</span></span>
- <span data-ttu-id="11037-622">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-622">sandbox</span></span>
- <span data-ttu-id="11037-623">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-623">onebox</span></span>
- <span data-ttu-id="11037-624">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-624">localhost</span></span>
- <span data-ttu-id="11037-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-625">127.0.0.1</span></span>
- <span data-ttu-id="11037-626">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-627">com</span><span class="sxs-lookup"><span data-stu-id="11037-627">com</span></span>
- <span data-ttu-id="11037-628">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-629">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="11037-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="11037-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="11037-631">Format</span><span class="sxs-lookup"><span data-stu-id="11037-631">Format</span></span>

<span data-ttu-id="11037-632">文字列 "sig" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="11037-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-633">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-633">Pattern</span></span>

- <span data-ttu-id="11037-634">文字列 "sig"</span><span class="sxs-lookup"><span data-stu-id="11037-634">The string "sig"</span></span>
- <span data-ttu-id="11037-635">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-636">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-636">An equal sign (=)</span></span>
- <span data-ttu-id="11037-637">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-638">43-53 文字のうち、下位または大文字の文字、数字、またはパーセント記号 (%) の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="11037-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="11037-639">文字列 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="11037-639">The string "%3d"</span></span>
- <span data-ttu-id="11037-640">小文字または大文字、数字、パーセント記号 (%) 以外の文字</span><span class="sxs-lookup"><span data-stu-id="11037-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-641">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-641">Checksum</span></span>

<span data-ttu-id="11037-642">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-643">定義</span><span class="sxs-lookup"><span data-stu-id="11037-643">Definition</span></span>

<span data-ttu-id="11037-644">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-645">正規表現 CEP_Regex_AzureSAS は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="11037-646">Azure Service Bus の接続文字列</span><span class="sxs-lookup"><span data-stu-id="11037-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="11037-647">Format</span><span class="sxs-lookup"><span data-stu-id="11037-647">Format</span></span>

<span data-ttu-id="11037-648">文字列 "EndPoint" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="11037-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="11037-649">net "および" Shared' キー "。</span><span class="sxs-lookup"><span data-stu-id="11037-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-650">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-650">Pattern</span></span>

- <span data-ttu-id="11037-651">文字列 "EndPoint"</span><span class="sxs-lookup"><span data-stu-id="11037-651">The string "EndPoint"</span></span>
- <span data-ttu-id="11037-652">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-653">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-653">An equal sign (=)</span></span>
- <span data-ttu-id="11037-654">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-655">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-656">文字列 "windows.</span><span class="sxs-lookup"><span data-stu-id="11037-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="11037-657">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-657">net"</span></span>
- <span data-ttu-id="11037-658">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-659">文字列 "SharedAccessKey"</span><span class="sxs-lookup"><span data-stu-id="11037-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="11037-660">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-661">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-661">An equal sign (=)</span></span>
- <span data-ttu-id="11037-662">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-663">43文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="11037-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="11037-664">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-665">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-665">Checksum</span></span>

<span data-ttu-id="11037-666">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-667">定義</span><span class="sxs-lookup"><span data-stu-id="11037-667">Definition</span></span>

<span data-ttu-id="11037-668">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-669">正規表現 CEP_Regex_AzureServiceBusConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="11037-670">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-671">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-673">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-674">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-674">contoso</span></span>
- <span data-ttu-id="11037-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-675">fabrikam</span></span>
- <span data-ttu-id="11037-676">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-676">northwind</span></span>
- <span data-ttu-id="11037-677">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-677">sandbox</span></span>
- <span data-ttu-id="11037-678">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-678">onebox</span></span>
- <span data-ttu-id="11037-679">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-679">localhost</span></span>
- <span data-ttu-id="11037-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-680">127.0.0.1</span></span>
- <span data-ttu-id="11037-681">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-682">com</span><span class="sxs-lookup"><span data-stu-id="11037-682">com</span></span>
- <span data-ttu-id="11037-683">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-684">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="11037-685">Azure ストレージアカウントキー</span><span class="sxs-lookup"><span data-stu-id="11037-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="11037-686">Format</span><span class="sxs-lookup"><span data-stu-id="11037-686">Format</span></span>

<span data-ttu-id="11037-687">文字列 "DefaultEndpointsProtocol" の後に、文字列 "AccountKey" を含む、次のパターンで概説されている文字および文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="11037-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-688">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-688">Pattern</span></span>

- <span data-ttu-id="11037-689">文字列 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="11037-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="11037-690">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-691">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-691">An equal sign (=)</span></span>
- <span data-ttu-id="11037-692">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-693">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-694">文字列 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="11037-694">The string "AccountKey"</span></span>
- <span data-ttu-id="11037-695">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-696">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-696">An equal sign (=)</span></span>
- <span data-ttu-id="11037-697">0-2 空白文字</span><span class="sxs-lookup"><span data-stu-id="11037-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="11037-698">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="11037-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="11037-699">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-700">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-700">Checksum</span></span>

<span data-ttu-id="11037-701">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-702">定義</span><span class="sxs-lookup"><span data-stu-id="11037-702">Definition</span></span>

<span data-ttu-id="11037-703">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-704">正規表現 CEP_Regex_AzureStorageAccountKey は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-705">正規表現 CEP_AzureEmulatorStorageAccountFilter は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="11037-706">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-707">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="11037-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="11037-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="11037-709">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="11037-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-712">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-713">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-713">contoso</span></span>
- <span data-ttu-id="11037-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-714">fabrikam</span></span>
- <span data-ttu-id="11037-715">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-715">northwind</span></span>
- <span data-ttu-id="11037-716">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-716">sandbox</span></span>
- <span data-ttu-id="11037-717">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-717">onebox</span></span>
- <span data-ttu-id="11037-718">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-718">localhost</span></span>
- <span data-ttu-id="11037-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-719">127.0.0.1</span></span>
- <span data-ttu-id="11037-720">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-721">com</span><span class="sxs-lookup"><span data-stu-id="11037-721">com</span></span>
- <span data-ttu-id="11037-722">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-723">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="11037-724">Azure ストレージアカウントキー (汎用)</span><span class="sxs-lookup"><span data-stu-id="11037-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="11037-725">Format</span><span class="sxs-lookup"><span data-stu-id="11037-725">Format</span></span>

<span data-ttu-id="11037-726">86の下または大文字、数字、スラッシュ (/)、またはプラス記号 (+) の任意の組み合わせで、下のパターンで説明されている文字が前または後にある。</span><span class="sxs-lookup"><span data-stu-id="11037-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-727">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-727">Pattern</span></span>

- <span data-ttu-id="11037-728">0-1 より大きい記号 (>)、アポストロフィ (')、等号 (=)、引用符 (")、または番号記号 (#) を指定します。</span><span class="sxs-lookup"><span data-stu-id="11037-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="11037-729">86文字の任意の組み合わせ (小文字または大文字の文字、数字、スラッシュ (/)、プラス記号 (+))</span><span class="sxs-lookup"><span data-stu-id="11037-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="11037-730">2つの等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="11037-731">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-731">Checksum</span></span>

<span data-ttu-id="11037-732">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-733">定義</span><span class="sxs-lookup"><span data-stu-id="11037-733">Definition</span></span>

<span data-ttu-id="11037-734">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-735">正規表現 CEP_Regex_AzureStorageAccountKeyGeneric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="11037-736">ベルギーの国民番号</span><span class="sxs-lookup"><span data-stu-id="11037-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-737">Format</span><span class="sxs-lookup"><span data-stu-id="11037-737">Format</span></span>

<span data-ttu-id="11037-738">11 の数字と区切り文字</span><span class="sxs-lookup"><span data-stu-id="11037-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-739">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-739">Pattern</span></span>

<span data-ttu-id="11037-740">11 の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="11037-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="11037-741">YY.MM.DD の形式の生年月日を表す 6 桁の数字と 2 つピリオド </span><span class="sxs-lookup"><span data-stu-id="11037-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="11037-742">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-742">A hyphen</span></span> 
- <span data-ttu-id="11037-743">3 桁の連番 (男性の場合は奇数、女性の場合は偶数) </span><span class="sxs-lookup"><span data-stu-id="11037-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="11037-744">ピリオド 1 つ</span><span class="sxs-lookup"><span data-stu-id="11037-744">A period</span></span> 
- <span data-ttu-id="11037-745">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-746">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-746">Checksum</span></span>

<span data-ttu-id="11037-747">はい</span><span class="sxs-lookup"><span data-stu-id="11037-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-748">定義</span><span class="sxs-lookup"><span data-stu-id="11037-748">Definition</span></span>

<span data-ttu-id="11037-749">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-750">関数 Func_belgium_national_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-751">Keyword_belgium_national_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="11037-752">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-753">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="11037-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="11037-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="11037-755">ID</span><span class="sxs-lookup"><span data-stu-id="11037-755">Identity</span></span>
- <span data-ttu-id="11037-756">レジスタ</span><span class="sxs-lookup"><span data-stu-id="11037-756">Registration</span></span>
- <span data-ttu-id="11037-757">Fim</span><span class="sxs-lookup"><span data-stu-id="11037-757">Identification</span></span> 
- <span data-ttu-id="11037-758">ID</span><span class="sxs-lookup"><span data-stu-id="11037-758">ID</span></span> 
- <span data-ttu-id="11037-759">「識別子」</span><span class="sxs-lookup"><span data-stu-id="11037-759">Identiteitskaart</span></span>
- <span data-ttu-id="11037-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="11037-760">Registratie nummer</span></span> 
- <span data-ttu-id="11037-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="11037-761">Identificatie nummer</span></span> 
- <span data-ttu-id="11037-762">識別子</span><span class="sxs-lookup"><span data-stu-id="11037-762">Identiteit</span></span>
- <span data-ttu-id="11037-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="11037-763">Registratie</span></span>
- <span data-ttu-id="11037-764">識別子</span><span class="sxs-lookup"><span data-stu-id="11037-764">Identificatie</span></span> 
- <span data-ttu-id="11037-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="11037-765">Carte d’identité</span></span> 
- <span data-ttu-id="11037-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="11037-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="11037-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="11037-767">numéro d'identification</span></span>
- <span data-ttu-id="11037-768">識別子</span><span class="sxs-lookup"><span data-stu-id="11037-768">identité</span></span> 
- <span data-ttu-id="11037-769">inscription</span><span class="sxs-lookup"><span data-stu-id="11037-769">inscription</span></span> 
- <span data-ttu-id="11037-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="11037-770">Identifikation</span></span>
- <span data-ttu-id="11037-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="11037-771">Identifizierung</span></span>
- <span data-ttu-id="11037-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-772">Identifikationsnummer</span></span>
- <span data-ttu-id="11037-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="11037-773">Personalausweis</span></span>
- <span data-ttu-id="11037-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="11037-774">Registrierung</span></span>
- <span data-ttu-id="11037-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="11037-776">ブラジルの CPF 番号</span><span class="sxs-lookup"><span data-stu-id="11037-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-777">Format</span><span class="sxs-lookup"><span data-stu-id="11037-777">Format</span></span>

<span data-ttu-id="11037-778">書式設定ありまたは書式設定なしのチェック ディジットを含む 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-779">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-779">Pattern</span></span>

<span data-ttu-id="11037-780">さ</span><span class="sxs-lookup"><span data-stu-id="11037-780">Formatted:</span></span>
- <span data-ttu-id="11037-781">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-781">Three digits</span></span> 
- <span data-ttu-id="11037-782">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-782">A period</span></span> 
- <span data-ttu-id="11037-783">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-783">Three digits</span></span> 
- <span data-ttu-id="11037-784">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-784">A period</span></span> 
- <span data-ttu-id="11037-785">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-785">Three digits</span></span> 
- <span data-ttu-id="11037-786">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-786">A hyphen</span></span> 
- <span data-ttu-id="11037-787">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-787">Two digits which are check digits</span></span>

<span data-ttu-id="11037-788">なし</span><span class="sxs-lookup"><span data-stu-id="11037-788">Unformatted:</span></span>
- <span data-ttu-id="11037-789">11 桁の数字 (最後の 2 桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="11037-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-790">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-790">Checksum</span></span>

<span data-ttu-id="11037-791">はい</span><span class="sxs-lookup"><span data-stu-id="11037-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-792">定義</span><span class="sxs-lookup"><span data-stu-id="11037-792">Definition</span></span>

<span data-ttu-id="11037-793">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-794">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-795">Keyword_brazil_cpf からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="11037-796">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-796">The checksum passes.</span></span>

<span data-ttu-id="11037-797">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-798">関数 Func_brazil_cpf は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-799">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-799">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-800">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="11037-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="11037-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="11037-802">CPF</span><span class="sxs-lookup"><span data-stu-id="11037-802">CPF</span></span>
- <span data-ttu-id="11037-803">Fim</span><span class="sxs-lookup"><span data-stu-id="11037-803">Identification</span></span>
- <span data-ttu-id="11037-804">レジスタ</span><span class="sxs-lookup"><span data-stu-id="11037-804">Registration</span></span>
- <span data-ttu-id="11037-805">増大</span><span class="sxs-lookup"><span data-stu-id="11037-805">Revenue</span></span>
- <span data-ttu-id="11037-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="11037-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="11037-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="11037-807">Imposto</span></span> 
- <span data-ttu-id="11037-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="11037-808">Identificação</span></span> 
- <span data-ttu-id="11037-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="11037-809">Inscrição</span></span> 
- <span data-ttu-id="11037-810">Receita</span><span class="sxs-lookup"><span data-stu-id="11037-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="11037-811">Brazil Legal Entity Number (CNPJ)</span><span class="sxs-lookup"><span data-stu-id="11037-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="11037-812">Format</span><span class="sxs-lookup"><span data-stu-id="11037-812">Format</span></span>

<span data-ttu-id="11037-813">登録番号、枝番号、チェック ディジット、および区切り文字を含む 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-814">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-814">Pattern</span></span>
<span data-ttu-id="11037-815">14 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="11037-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="11037-816">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-816">Two digits</span></span> 
- <span data-ttu-id="11037-817">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-817">A period</span></span> 
- <span data-ttu-id="11037-818">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-818">Three digits</span></span> 
- <span data-ttu-id="11037-819">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-819">A period</span></span> 
- <span data-ttu-id="11037-820">3 桁の数字 (最初の 8 桁の数字は登録番号) </span><span class="sxs-lookup"><span data-stu-id="11037-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="11037-821">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-821">A forward slash</span></span> 
- <span data-ttu-id="11037-822">4 桁の枝番号 </span><span class="sxs-lookup"><span data-stu-id="11037-822">Four-digit branch number</span></span> 
- <span data-ttu-id="11037-823">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-823">A hyphen</span></span> 
- <span data-ttu-id="11037-824">チェック ディジットとして機能する 2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-825">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-825">Checksum</span></span>

<span data-ttu-id="11037-826">はい</span><span class="sxs-lookup"><span data-stu-id="11037-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-827">定義</span><span class="sxs-lookup"><span data-stu-id="11037-827">Definition</span></span>

<span data-ttu-id="11037-828">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-829">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-830">Keyword_brazil_cnpj からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="11037-831">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-831">The checksum passes.</span></span>

<span data-ttu-id="11037-832">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-833">関数 Func_brazil_cnpj は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-834">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-834">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-835">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="11037-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="11037-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="11037-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="11037-837">CNPJ</span></span> 
- <span data-ttu-id="11037-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="11037-838">CNPJ/MF</span></span> 
- <span data-ttu-id="11037-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="11037-839">CNPJ-MF</span></span> 
- <span data-ttu-id="11037-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="11037-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="11037-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="11037-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="11037-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="11037-842">Legal entity</span></span> 
- <span data-ttu-id="11037-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="11037-843">Legal entities</span></span> 
- <span data-ttu-id="11037-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="11037-844">Registration Status</span></span> 
- <span data-ttu-id="11037-845">Business</span><span class="sxs-lookup"><span data-stu-id="11037-845">Business</span></span> 
- <span data-ttu-id="11037-846">Company</span><span class="sxs-lookup"><span data-stu-id="11037-846">Company</span></span>
- <span data-ttu-id="11037-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="11037-847">CNPJ</span></span> 
- <span data-ttu-id="11037-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="11037-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="11037-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="11037-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="11037-850">CGC</span><span class="sxs-lookup"><span data-stu-id="11037-850">CGC</span></span> 
- <span data-ttu-id="11037-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="11037-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="11037-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="11037-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="11037-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="11037-853">Situação cadastral</span></span> 
- <span data-ttu-id="11037-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="11037-854">Inscrição</span></span> 
- <span data-ttu-id="11037-855">サイト</span><span class="sxs-lookup"><span data-stu-id="11037-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="11037-856">	ブラジルの国民識別カード (RG)</span><span class="sxs-lookup"><span data-stu-id="11037-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="11037-857">Format</span><span class="sxs-lookup"><span data-stu-id="11037-857">Format</span></span>

<span data-ttu-id="11037-858">Registro Geral (古い形式): 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="11037-859">Registro de 識別子 Dade (RIC) (新しい形式):11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-860">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-860">Pattern</span></span>

<span data-ttu-id="11037-861">Registro Geral (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="11037-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="11037-862">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-862">Two digits</span></span> 
- <span data-ttu-id="11037-863">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-863">A period</span></span> 
- <span data-ttu-id="11037-864">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-864">Three digits</span></span> 
- <span data-ttu-id="11037-865">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-865">A period</span></span> 
- <span data-ttu-id="11037-866">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-866">Three digits</span></span> 
- <span data-ttu-id="11037-867">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-867">A hyphen</span></span> 
- <span data-ttu-id="11037-868">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-868">One digit which is a check digit</span></span>

<span data-ttu-id="11037-869">Registro de 識別子 Dade (RIC) (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="11037-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="11037-870">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-870">10 digits</span></span> 
- <span data-ttu-id="11037-871">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-871">A hyphen</span></span> 
- <span data-ttu-id="11037-872">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-873">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-873">Checksum</span></span>

<span data-ttu-id="11037-874">はい</span><span class="sxs-lookup"><span data-stu-id="11037-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-875">定義</span><span class="sxs-lookup"><span data-stu-id="11037-875">Definition</span></span>

<span data-ttu-id="11037-876">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-877">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-878">Keyword_brazil_rg からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="11037-879">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-879">The checksum passes.</span></span>

<span data-ttu-id="11037-880">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-881">関数 Func_brazil_rg は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-882">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-882">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-883">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="11037-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="11037-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="11037-885">Cédula de 識別子 dade id カード national id número de rregistro registro de I識別子 Dade registro geral このキーワードは大文字と小文字を区別します) RIC (このキーワードは大文字と小文字を区別します)</span><span class="sxs-lookup"><span data-stu-id="11037-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="11037-886">カナダの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-887">Format</span><span class="sxs-lookup"><span data-stu-id="11037-887">Format</span></span>

<span data-ttu-id="11037-888">7 桁または 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-889">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-889">Pattern</span></span>

<span data-ttu-id="11037-890">カナダの銀行口座番号は 7 桁または 12 桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="11037-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="11037-891">カナダの銀行口座転送番号は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11037-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="11037-892">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-892">Five digits</span></span> 
- <span data-ttu-id="11037-893">ハイフン</span><span class="sxs-lookup"><span data-stu-id="11037-893">A hyphen</span></span> 
- <span data-ttu-id="11037-894">3桁の数字または</span><span class="sxs-lookup"><span data-stu-id="11037-894">Three digits OR</span></span>
- <span data-ttu-id="11037-895">1 桁のゼロ (0) </span><span class="sxs-lookup"><span data-stu-id="11037-895">A zero "0"</span></span> 
- <span data-ttu-id="11037-896">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-897">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-897">Checksum</span></span>

<span data-ttu-id="11037-898">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-899">定義</span><span class="sxs-lookup"><span data-stu-id="11037-899">Definition</span></span>

<span data-ttu-id="11037-900">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-901">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-902">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="11037-903">正規表現 Regex_canada_bank_account_transit_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="11037-904">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-905">正規表現 Regex_canada_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-906">Keyword_canada_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-907">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="11037-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="11037-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="11037-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="11037-909">canada savings bonds</span></span>
- <span data-ttu-id="11037-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="11037-910">canada revenue agency</span></span>
- <span data-ttu-id="11037-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="11037-911">canadian financial institution</span></span>
- <span data-ttu-id="11037-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="11037-912">direct deposit form</span></span>
- <span data-ttu-id="11037-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="11037-913">canadian citizen</span></span>
- <span data-ttu-id="11037-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="11037-914">legal representative</span></span>
- <span data-ttu-id="11037-915">notary public</span><span class="sxs-lookup"><span data-stu-id="11037-915">notary public</span></span>
- <span data-ttu-id="11037-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="11037-916">commissioner for oaths</span></span>
- <span data-ttu-id="11037-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="11037-917">child care benefit</span></span>
- <span data-ttu-id="11037-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="11037-918">universal child care</span></span>
- <span data-ttu-id="11037-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="11037-919">canada child tax benefit</span></span>
- <span data-ttu-id="11037-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="11037-920">income tax benefit</span></span>
- <span data-ttu-id="11037-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="11037-921">harmonized sales tax</span></span>
- <span data-ttu-id="11037-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="11037-922">social insurance number</span></span>
- <span data-ttu-id="11037-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="11037-923">income tax refund</span></span>
- <span data-ttu-id="11037-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="11037-924">child tax benefit</span></span>
- <span data-ttu-id="11037-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="11037-925">territorial payments</span></span>
- <span data-ttu-id="11037-926">institution number</span><span class="sxs-lookup"><span data-stu-id="11037-926">institution number</span></span>
- <span data-ttu-id="11037-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="11037-927">deposit request</span></span>
- <span data-ttu-id="11037-928">banking information</span><span class="sxs-lookup"><span data-stu-id="11037-928">banking information</span></span>
- <span data-ttu-id="11037-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="11037-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="11037-930">カナダの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-931">Format</span><span class="sxs-lookup"><span data-stu-id="11037-931">Format</span></span>

<span data-ttu-id="11037-932">州によって異なります</span><span class="sxs-lookup"><span data-stu-id="11037-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-933">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-933">Pattern</span></span>

<span data-ttu-id="11037-934">アルバータ州、ブリティッシュ コロンビア州、マニトバ州、ニュー ブランズウィック州、ニューファンドランド・ラブラドール州、ノバスコシア州、オンタリオ州、プリンス エドワード アイランド州、ケベック州、およびサスカチュワン州の各種パターン</span><span class="sxs-lookup"><span data-stu-id="11037-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-935">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-935">Checksum</span></span>

<span data-ttu-id="11037-936">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-937">定義</span><span class="sxs-lookup"><span data-stu-id="11037-937">Definition</span></span>

<span data-ttu-id="11037-938">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-939">関数 Func_[province_name]_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-940">Keyword_[province_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="11037-941">Keyword_canada_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-942">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="11037-943">Keyword_[province_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="11037-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="11037-944">州の略号、AB など</span><span class="sxs-lookup"><span data-stu-id="11037-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="11037-945">州名 (Alberta など)</span><span class="sxs-lookup"><span data-stu-id="11037-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="11037-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="11037-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="11037-947">DL</span><span class="sxs-lookup"><span data-stu-id="11037-947">DL</span></span>
- <span data-ttu-id="11037-948">DL</span><span class="sxs-lookup"><span data-stu-id="11037-948">DLS</span></span>
- <span data-ttu-id="11037-949">CDL</span><span class="sxs-lookup"><span data-stu-id="11037-949">CDL</span></span>
- <span data-ttu-id="11037-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="11037-950">CDLS</span></span>
- <span data-ttu-id="11037-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="11037-951">DriverLic</span></span>
- <span data-ttu-id="11037-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="11037-952">DriverLics</span></span>
- <span data-ttu-id="11037-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="11037-953">DriverLicense</span></span>
- <span data-ttu-id="11037-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="11037-954">DriverLicenses</span></span>
- <span data-ttu-id="11037-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="11037-955">DriverLicence</span></span>
- <span data-ttu-id="11037-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="11037-956">DriverLicences</span></span>
- <span data-ttu-id="11037-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="11037-957">Driver Lic</span></span>
- <span data-ttu-id="11037-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="11037-958">Driver Lics</span></span>
- <span data-ttu-id="11037-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="11037-959">Driver License</span></span>
- <span data-ttu-id="11037-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-960">Driver Licenses</span></span>
- <span data-ttu-id="11037-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="11037-961">Driver Licence</span></span>
- <span data-ttu-id="11037-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="11037-962">Driver Licences</span></span>
- <span data-ttu-id="11037-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="11037-963">DriversLic</span></span>
- <span data-ttu-id="11037-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="11037-964">DriversLics</span></span>
- <span data-ttu-id="11037-965">その他のライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-965">DriversLicence</span></span>
- <span data-ttu-id="11037-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="11037-966">DriversLicences</span></span>
- <span data-ttu-id="11037-967">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="11037-967">DriversLicense</span></span>
- <span data-ttu-id="11037-968">このライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-968">DriversLicenses</span></span>
- <span data-ttu-id="11037-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="11037-969">Drivers Lic</span></span>
- <span data-ttu-id="11037-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="11037-970">Drivers Lics</span></span>
- <span data-ttu-id="11037-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="11037-971">Drivers License</span></span>
- <span data-ttu-id="11037-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-972">Drivers Licenses</span></span>
- <span data-ttu-id="11037-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="11037-973">Drivers Licence</span></span>
- <span data-ttu-id="11037-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="11037-974">Drivers Licences</span></span>
- <span data-ttu-id="11037-975">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="11037-975">Driver'Lic</span></span>
- <span data-ttu-id="11037-976">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="11037-976">Driver'Lics</span></span>
- <span data-ttu-id="11037-977">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-977">Driver'License</span></span>
- <span data-ttu-id="11037-978">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-978">Driver'Licenses</span></span>
- <span data-ttu-id="11037-979">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-979">Driver'Licence</span></span>
- <span data-ttu-id="11037-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="11037-980">Driver'Licences</span></span>
- <span data-ttu-id="11037-981">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="11037-981">Driver' Lic</span></span>
- <span data-ttu-id="11037-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="11037-982">Driver' Lics</span></span>
- <span data-ttu-id="11037-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="11037-983">Driver' License</span></span>
- <span data-ttu-id="11037-984">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-984">Driver' Licenses</span></span>
- <span data-ttu-id="11037-985">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="11037-985">Driver' Licence</span></span>
- <span data-ttu-id="11037-986">Driver' Licences</span><span class="sxs-lookup"><span data-stu-id="11037-986">Driver' Licences</span></span>
- <span data-ttu-id="11037-987">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="11037-987">Driver'sLic</span></span>
- <span data-ttu-id="11037-988">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="11037-988">Driver'sLics</span></span>
- <span data-ttu-id="11037-989">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-989">Driver'sLicense</span></span>
- <span data-ttu-id="11037-990">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-990">Driver'sLicenses</span></span>
- <span data-ttu-id="11037-991">ドライバ ' スライスの持続性</span><span class="sxs-lookup"><span data-stu-id="11037-991">Driver'sLicence</span></span>
- <span data-ttu-id="11037-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="11037-992">Driver'sLicences</span></span>
- <span data-ttu-id="11037-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="11037-993">Driver's Lic</span></span>
- <span data-ttu-id="11037-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="11037-994">Driver's Lics</span></span>
- <span data-ttu-id="11037-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="11037-995">Driver's License</span></span>
- <span data-ttu-id="11037-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-996">Driver's Licenses</span></span>
- <span data-ttu-id="11037-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="11037-997">Driver's Licence</span></span>
- <span data-ttu-id="11037-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="11037-998">Driver's Licences</span></span>
- <span data-ttu-id="11037-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="11037-999">Permis de Conduire</span></span>
- <span data-ttu-id="11037-1000">id</span><span class="sxs-lookup"><span data-stu-id="11037-1000">id</span></span>
- <span data-ttu-id="11037-1001">ids</span><span class="sxs-lookup"><span data-stu-id="11037-1001">ids</span></span>
- <span data-ttu-id="11037-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="11037-1002">idcard number</span></span>
- <span data-ttu-id="11037-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="11037-1003">idcard numbers</span></span>
- <span data-ttu-id="11037-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="11037-1004">idcard #</span></span>
- <span data-ttu-id="11037-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="11037-1005">idcard #s</span></span>
- <span data-ttu-id="11037-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="11037-1006">idcard card</span></span>
- <span data-ttu-id="11037-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="11037-1007">idcard cards</span></span>
- <span data-ttu-id="11037-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="11037-1008">idcard</span></span>
- <span data-ttu-id="11037-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="11037-1009">identification number</span></span>
- <span data-ttu-id="11037-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="11037-1010">identification numbers</span></span>
- <span data-ttu-id="11037-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="11037-1011">identification #</span></span>
- <span data-ttu-id="11037-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="11037-1012">identification #s</span></span>
- <span data-ttu-id="11037-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="11037-1013">identification card</span></span>
- <span data-ttu-id="11037-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="11037-1014">identification cards</span></span>
- <span data-ttu-id="11037-1015">fim</span><span class="sxs-lookup"><span data-stu-id="11037-1015">identification</span></span> 
- <span data-ttu-id="11037-1016">DL#</span><span class="sxs-lookup"><span data-stu-id="11037-1016">DL#</span></span>
- <span data-ttu-id="11037-1017">DL#</span><span class="sxs-lookup"><span data-stu-id="11037-1017">DLS#</span></span> 
- <span data-ttu-id="11037-1018">CDL#</span><span class="sxs-lookup"><span data-stu-id="11037-1018">CDL#</span></span> 
- <span data-ttu-id="11037-1019">CDLS#</span><span class="sxs-lookup"><span data-stu-id="11037-1019">CDLS#</span></span> 
- <span data-ttu-id="11037-1020">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="11037-1020">DriverLic#</span></span> 
- <span data-ttu-id="11037-1021">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="11037-1021">DriverLics#</span></span> 
- <span data-ttu-id="11037-1022">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="11037-1022">DriverLicense#</span></span> 
- <span data-ttu-id="11037-1023">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="11037-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="11037-1024">DriverLicence#</span><span class="sxs-lookup"><span data-stu-id="11037-1024">DriverLicence#</span></span> 
- <span data-ttu-id="11037-1025">DriverLicences#</span><span class="sxs-lookup"><span data-stu-id="11037-1025">DriverLicences#</span></span> 
- <span data-ttu-id="11037-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-1026">Driver Lic#</span></span>
- <span data-ttu-id="11037-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-1027">Driver Lics#</span></span> 
- <span data-ttu-id="11037-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="11037-1028">Driver License#</span></span> 
- <span data-ttu-id="11037-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="11037-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="11037-1030">Driver License#</span></span> 
- <span data-ttu-id="11037-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-1031">Driver Licences#</span></span> 
- <span data-ttu-id="11037-1032">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="11037-1032">DriversLic#</span></span> 
- <span data-ttu-id="11037-1033">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="11037-1033">DriversLics#</span></span> 
- <span data-ttu-id="11037-1034">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="11037-1034">DriversLicense#</span></span> 
- <span data-ttu-id="11037-1035">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="11037-1036">その他のライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1036">DriversLicence#</span></span> 
- <span data-ttu-id="11037-1037">DriversLicences#</span><span class="sxs-lookup"><span data-stu-id="11037-1037">DriversLicences#</span></span> 
- <span data-ttu-id="11037-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="11037-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="11037-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="11037-1040">Drivers License#</span></span> 
- <span data-ttu-id="11037-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="11037-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="11037-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="11037-1044">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="11037-1045">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="11037-1046">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1046">Driver'License#</span></span> 
- <span data-ttu-id="11037-1047">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="11037-1048">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="11037-1049">Driver'Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="11037-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="11037-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="11037-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="11037-1052">Driver' License#</span></span> 
- <span data-ttu-id="11037-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="11037-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="11037-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="11037-1056">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="11037-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="11037-1057">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="11037-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="11037-1058">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="11037-1059">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="11037-1060">ドライバ ' スライスの持続性#</span><span class="sxs-lookup"><span data-stu-id="11037-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="11037-1061">Driver'sLicences#</span><span class="sxs-lookup"><span data-stu-id="11037-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="11037-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="11037-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="11037-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="11037-1064">Driver's License#</span></span> 
- <span data-ttu-id="11037-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="11037-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="11037-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="11037-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="11037-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="11037-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="11037-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="11037-1069">rid#</span><span class="sxs-lookup"><span data-stu-id="11037-1069">id#</span></span> 
- <span data-ttu-id="11037-1070">rid#</span><span class="sxs-lookup"><span data-stu-id="11037-1070">ids#</span></span> 
- <span data-ttu-id="11037-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="11037-1071">idcard card#</span></span> 
- <span data-ttu-id="11037-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="11037-1072">idcard cards#</span></span> 
- <span data-ttu-id="11037-1073">idcard#</span><span class="sxs-lookup"><span data-stu-id="11037-1073">idcard#</span></span> 
- <span data-ttu-id="11037-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="11037-1074">identification card#</span></span> 
- <span data-ttu-id="11037-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="11037-1075">identification cards#</span></span> 
- <span data-ttu-id="11037-1076">fim#</span><span class="sxs-lookup"><span data-stu-id="11037-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="11037-1077">カナダの健康保険番号</span><span class="sxs-lookup"><span data-stu-id="11037-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1078">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1078">Format</span></span>

<span data-ttu-id="11037-1079">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1080">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1080">Pattern</span></span>

<span data-ttu-id="11037-1081">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1082">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1082">Checksum</span></span>

<span data-ttu-id="11037-1083">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1084">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1084">Definition</span></span>

<span data-ttu-id="11037-1085">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1086">正規表現 Regex_canada_health_service_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1087">Keyword_canada_health_service_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1088">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="11037-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="11037-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="11037-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="11037-1090">personal health number</span></span>
- <span data-ttu-id="11037-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="11037-1091">patient information</span></span>
- <span data-ttu-id="11037-1092">health services</span><span class="sxs-lookup"><span data-stu-id="11037-1092">health services</span></span>
- <span data-ttu-id="11037-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="11037-1093">speciality services</span></span>
- <span data-ttu-id="11037-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="11037-1094">automobile accident</span></span>
- <span data-ttu-id="11037-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="11037-1095">patient hospital</span></span>
- <span data-ttu-id="11037-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="11037-1096">psychiatrist</span></span>
- <span data-ttu-id="11037-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="11037-1097">workers compensation</span></span>
- <span data-ttu-id="11037-1098">身体</span><span class="sxs-lookup"><span data-stu-id="11037-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="11037-1099">カナダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1100">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1100">Format</span></span>

<span data-ttu-id="11037-1101">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1102">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1102">Pattern</span></span>

<span data-ttu-id="11037-1103">2 桁の大文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1104">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1104">Checksum</span></span>

<span data-ttu-id="11037-1105">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1106">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1106">Definition</span></span>

<span data-ttu-id="11037-1107">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1108">正規表現 Regex_canada_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1109">Keyword_canada_passport_number または Keyword_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
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

### <a name="keywords"></a><span data-ttu-id="11037-1110">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="11037-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="11037-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="11037-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="11037-1112">canadian citizenship</span></span>
- <span data-ttu-id="11037-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="11037-1113">canadian passport</span></span>
- <span data-ttu-id="11037-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="11037-1114">passport application</span></span>
- <span data-ttu-id="11037-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="11037-1115">passport photos</span></span>
- <span data-ttu-id="11037-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="11037-1116">certified translator</span></span>
- <span data-ttu-id="11037-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="11037-1117">canadian citizens</span></span>
- <span data-ttu-id="11037-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="11037-1118">processing times</span></span>
- <span data-ttu-id="11037-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="11037-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="11037-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="11037-1120">Keyword_passport</span></span>

- <span data-ttu-id="11037-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="11037-1121">Passport Number</span></span>
- <span data-ttu-id="11037-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="11037-1122">Passport No</span></span>
- <span data-ttu-id="11037-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="11037-1123">Passport #</span></span>
- <span data-ttu-id="11037-1124">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="11037-1124">Passport#</span></span>
- <span data-ttu-id="11037-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="11037-1125">PassportID</span></span>
- <span data-ttu-id="11037-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="11037-1126">Passportno</span></span>
- <span data-ttu-id="11037-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="11037-1127">passportnumber</span></span>
- <span data-ttu-id="11037-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="11037-1128">パスポート</span></span>
- <span data-ttu-id="11037-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-1129">パスポート番号</span></span>
- <span data-ttu-id="11037-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="11037-1130">パスポートのNum</span></span>
- <span data-ttu-id="11037-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="11037-1131">パスポート＃</span></span>
- <span data-ttu-id="11037-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="11037-1132">Numéro de passeport</span></span>
- <span data-ttu-id="11037-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="11037-1133">Passeport n °</span></span>
- <span data-ttu-id="11037-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="11037-1134">Passeport Non</span></span>
- <span data-ttu-id="11037-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="11037-1135">Passeport #</span></span>
- <span data-ttu-id="11037-1136">Passeport#</span><span class="sxs-lookup"><span data-stu-id="11037-1136">Passeport#</span></span>
- <span data-ttu-id="11037-1137">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="11037-1137">PasseportNon</span></span>
- <span data-ttu-id="11037-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="11037-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="11037-1139">カナダの個人保健識別番号 (PHIN)</span><span class="sxs-lookup"><span data-stu-id="11037-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="11037-1140">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1140">Format</span></span>

<span data-ttu-id="11037-1141">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1142">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1142">Pattern</span></span>

<span data-ttu-id="11037-1143">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1144">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1144">Checksum</span></span>

<span data-ttu-id="11037-1145">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1146">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1146">Definition</span></span>

<span data-ttu-id="11037-1147">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_canada_phin は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-1148">Keyword_canada_phin または Keyword_canada_provinces から、少なくとも2つのキーワードが見つかります。</span><span class="sxs-lookup"><span data-stu-id="11037-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1149">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="11037-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="11037-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="11037-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="11037-1151">social insurance number</span></span>
- <span data-ttu-id="11037-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="11037-1152">health information act</span></span>
- <span data-ttu-id="11037-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="11037-1153">income tax information</span></span>
- <span data-ttu-id="11037-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="11037-1154">manitoba health</span></span>
- <span data-ttu-id="11037-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="11037-1155">health registration</span></span>
- <span data-ttu-id="11037-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="11037-1156">prescription purchases</span></span>
- <span data-ttu-id="11037-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="11037-1157">benefit eligibility</span></span>
- <span data-ttu-id="11037-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="11037-1158">personal health</span></span>
- <span data-ttu-id="11037-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="11037-1159">power of attorney</span></span>
- <span data-ttu-id="11037-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="11037-1160">registration number</span></span>
- <span data-ttu-id="11037-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="11037-1161">personal health number</span></span>
- <span data-ttu-id="11037-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="11037-1162">practitioner referral</span></span>
- <span data-ttu-id="11037-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="11037-1163">wellness professional</span></span>
- <span data-ttu-id="11037-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="11037-1164">patient referral</span></span>
- <span data-ttu-id="11037-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="11037-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="11037-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="11037-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="11037-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="11037-1167">Nunavut</span></span>
- <span data-ttu-id="11037-1168">州</span><span class="sxs-lookup"><span data-stu-id="11037-1168">Quebec</span></span>
- <span data-ttu-id="11037-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="11037-1169">Northwest Territories</span></span>
- <span data-ttu-id="11037-1170">オンタリオ州</span><span class="sxs-lookup"><span data-stu-id="11037-1170">Ontario</span></span>
- <span data-ttu-id="11037-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="11037-1171">British Columbia</span></span>
- <span data-ttu-id="11037-1172">州</span><span class="sxs-lookup"><span data-stu-id="11037-1172">Alberta</span></span>
- <span data-ttu-id="11037-1173">Saskatchewan</span><span class="sxs-lookup"><span data-stu-id="11037-1173">Saskatchewan</span></span>
- <span data-ttu-id="11037-1174">マニトバ州</span><span class="sxs-lookup"><span data-stu-id="11037-1174">Manitoba</span></span>
- <span data-ttu-id="11037-1175">州</span><span class="sxs-lookup"><span data-stu-id="11037-1175">Yukon</span></span>
- <span data-ttu-id="11037-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="11037-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="11037-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="11037-1177">New Brunswick</span></span>
- <span data-ttu-id="11037-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="11037-1178">Nova Scotia</span></span>
- <span data-ttu-id="11037-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="11037-1179">Prince Edward Island</span></span>
- <span data-ttu-id="11037-1180">カナダ</span><span class="sxs-lookup"><span data-stu-id="11037-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="11037-1181">カナダの社会保険番号</span><span class="sxs-lookup"><span data-stu-id="11037-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1182">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1182">Format</span></span>

<span data-ttu-id="11037-1183">9 桁の数字と省略可能なハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="11037-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1184">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1184">Pattern</span></span>

<span data-ttu-id="11037-1185">さ</span><span class="sxs-lookup"><span data-stu-id="11037-1185">Formatted:</span></span>
- <span data-ttu-id="11037-1186">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1186">Three digits</span></span> 
- <span data-ttu-id="11037-1187">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="11037-1187">A hyphen or space</span></span> 
- <span data-ttu-id="11037-1188">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1188">Three digits</span></span> 
- <span data-ttu-id="11037-1189">ハイフンまたはスペース</span><span class="sxs-lookup"><span data-stu-id="11037-1189">A hyphen or space</span></span> 
- <span data-ttu-id="11037-1190">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1190">Three digits</span></span>

<span data-ttu-id="11037-1191">書式なし: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1192">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1192">Checksum</span></span>

<span data-ttu-id="11037-1193">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1194">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1194">Definition</span></span>

<span data-ttu-id="11037-1195">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1196">関数 Func_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1197">以下の 2 つ以上の条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="11037-1198">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="11037-1199">Keyword_sin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="11037-1200">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-1201">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1201">The checksum passes.</span></span>

<span data-ttu-id="11037-1202">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1203">関数 Func_unformatted_canadian_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1204">Keyword_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="11037-1205">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1205">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1206">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="11037-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="11037-1207">Keyword_sin</span></span>

- <span data-ttu-id="11037-1208">sin</span><span class="sxs-lookup"><span data-stu-id="11037-1208">sin</span></span> 
- <span data-ttu-id="11037-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="11037-1209">social insurance</span></span> 
- <span data-ttu-id="11037-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="11037-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="11037-1211">大罪</span><span class="sxs-lookup"><span data-stu-id="11037-1211">sins</span></span> 
- <span data-ttu-id="11037-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="11037-1212">ssn</span></span> 
- <span data-ttu-id="11037-1213">ssn</span><span class="sxs-lookup"><span data-stu-id="11037-1213">ssns</span></span> 
- <span data-ttu-id="11037-1214">social security</span><span class="sxs-lookup"><span data-stu-id="11037-1214">social security</span></span> 
- <span data-ttu-id="11037-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="11037-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="11037-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="11037-1216">national identification number</span></span> 
- <span data-ttu-id="11037-1217">national id</span><span class="sxs-lookup"><span data-stu-id="11037-1217">national id</span></span> 
- <span data-ttu-id="11037-1218">sin#</span><span class="sxs-lookup"><span data-stu-id="11037-1218">sin#</span></span> 
- <span data-ttu-id="11037-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="11037-1219">soc ins</span></span> 
- <span data-ttu-id="11037-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="11037-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="11037-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="11037-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="11037-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="11037-1222">driver's license</span></span> 
- <span data-ttu-id="11037-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="11037-1223">drivers license</span></span> 
- <span data-ttu-id="11037-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="11037-1224">driver's licence</span></span> 
- <span data-ttu-id="11037-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="11037-1225">drivers licence</span></span> 
- <span data-ttu-id="11037-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="11037-1226">DOB</span></span> 
- <span data-ttu-id="11037-1227">誕生日</span><span class="sxs-lookup"><span data-stu-id="11037-1227">Birthdate</span></span> 
- <span data-ttu-id="11037-1228">Birthday</span><span class="sxs-lookup"><span data-stu-id="11037-1228">Birthday</span></span> 
- <span data-ttu-id="11037-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="11037-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="11037-1230">	チリの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="11037-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1231">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1231">Format</span></span>

<span data-ttu-id="11037-1232">7-8 桁の数字と区切り文字のチェックディジットまたは文字</span><span class="sxs-lookup"><span data-stu-id="11037-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1233">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1233">Pattern</span></span>

<span data-ttu-id="11037-1234">7 ～ 8 桁の数字と区切り文字:</span><span class="sxs-lookup"><span data-stu-id="11037-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="11037-1235">1 ～ 2 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-1235">1-2 digits</span></span> 
- <span data-ttu-id="11037-1236">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-1236">A period</span></span> 
- <span data-ttu-id="11037-1237">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1237">Three digits</span></span> 
- <span data-ttu-id="11037-1238">ピリオド 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-1238">A period</span></span> 
- <span data-ttu-id="11037-1239">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1239">Three digits</span></span> 
- <span data-ttu-id="11037-1240">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-1240">A dash</span></span> 
- <span data-ttu-id="11037-1241">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="11037-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1242">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1242">Checksum</span></span>

<span data-ttu-id="11037-1243">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1244">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1244">Definition</span></span>

<span data-ttu-id="11037-1245">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1246">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1247">Keyword_chile_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="11037-1248">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1248">The checksum passes.</span></span>

<span data-ttu-id="11037-1249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1250">関数 Func_chile_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1251">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1251">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1252">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="11037-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="11037-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="11037-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="11037-1254">National Identification Number</span></span> 
- <span data-ttu-id="11037-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="11037-1255">Identity card</span></span> 
- <span data-ttu-id="11037-1256">ID</span><span class="sxs-lookup"><span data-stu-id="11037-1256">ID</span></span> 
- <span data-ttu-id="11037-1257">Fim</span><span class="sxs-lookup"><span data-stu-id="11037-1257">Identification</span></span> 
- <span data-ttu-id="11037-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="11037-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="11037-1259">実行</span><span class="sxs-lookup"><span data-stu-id="11037-1259">RUN</span></span> 
- <span data-ttu-id="11037-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="11037-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="11037-1261">類型</span><span class="sxs-lookup"><span data-stu-id="11037-1261">RUT</span></span> 
- <span data-ttu-id="11037-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="11037-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="11037-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="11037-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="11037-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="11037-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="11037-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="11037-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="11037-1266">	中国の居民身分証明書 (PRC) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1267">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1267">Format</span></span>

<span data-ttu-id="11037-1268">18 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1269">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1269">Pattern</span></span>

<span data-ttu-id="11037-1270">18 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-1270">18 digits:</span></span>
- <span data-ttu-id="11037-1271">住所コードを表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="11037-1272">YYYYMMDD の形式で生年月日を表す 8 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="11037-1273">順序コードを表す 3 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="11037-1274">チェック ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1275">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1275">Checksum</span></span>

<span data-ttu-id="11037-1276">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1277">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1277">Definition</span></span>

<span data-ttu-id="11037-1278">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1279">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1280">Keyword_china_resident_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="11037-1281">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1281">The checksum passes.</span></span>

<span data-ttu-id="11037-1282">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1283">関数 Func_china_resident_id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1284">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1284">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1285">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="11037-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="11037-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="11037-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="11037-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="11037-1288">PRC</span><span class="sxs-lookup"><span data-stu-id="11037-1288">PRC</span></span> 
- <span data-ttu-id="11037-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="11037-1289">National Identification Card</span></span> 
- <span data-ttu-id="11037-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="11037-1290">身份证</span></span> 
- <span data-ttu-id="11037-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="11037-1291">居民 身份证</span></span> 
- <span data-ttu-id="11037-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="11037-1292">居民身份证</span></span> 
- <span data-ttu-id="11037-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="11037-1293">鉴定</span></span> 
- <span data-ttu-id="11037-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="11037-1294">身分證</span></span> 
- <span data-ttu-id="11037-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="11037-1295">居民 身份證</span></span>
- <span data-ttu-id="11037-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="11037-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="11037-1297">クレジット カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1298">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1298">Format</span></span>

<span data-ttu-id="11037-1299">書式設定または書式設定ができない16桁の数字 (dddddddddddddddd)。 Luhn テストに合格する必要があります。</span><span class="sxs-lookup"><span data-stu-id="11037-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1300">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1300">Pattern</span></span>

<span data-ttu-id="11037-1301">世界規模の主要ブランドのカード (Visa、MasterCard、Discover Card、JCB、American Express、ギフト カード、Dinars Club Card など) を検出する非常に複雑で信頼性の高いパターンです。</span><span class="sxs-lookup"><span data-stu-id="11037-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1302">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1302">Checksum</span></span>

<span data-ttu-id="11037-1303">あり (Luhn のチェックサム)</span><span class="sxs-lookup"><span data-stu-id="11037-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1304">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1304">Definition</span></span>

<span data-ttu-id="11037-1305">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1306">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1307">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-1307">One of the following is true:</span></span>
    - <span data-ttu-id="11037-1308">Keyword_cc_verification のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="11037-1309">Keyword_cc_name からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="11037-1310">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-1311">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1311">The checksum passes.</span></span>

<span data-ttu-id="11037-1312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1313">関数 Func_credit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1314">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1314">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1315">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="11037-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="11037-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="11037-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="11037-1317">card verification</span></span>
- <span data-ttu-id="11037-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="11037-1318">card identification number</span></span>
- <span data-ttu-id="11037-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="11037-1319">cvn</span></span>
- <span data-ttu-id="11037-1320">cid</span><span class="sxs-lookup"><span data-stu-id="11037-1320">cid</span></span>
- <span data-ttu-id="11037-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="11037-1321">cvc2</span></span>
- <span data-ttu-id="11037-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="11037-1322">cvv2</span></span>
- <span data-ttu-id="11037-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="11037-1323">pin block</span></span>
- <span data-ttu-id="11037-1324">security code</span><span class="sxs-lookup"><span data-stu-id="11037-1324">security code</span></span>
- <span data-ttu-id="11037-1325">security number</span><span class="sxs-lookup"><span data-stu-id="11037-1325">security number</span></span>
- <span data-ttu-id="11037-1326">security no</span><span class="sxs-lookup"><span data-stu-id="11037-1326">security no</span></span>
- <span data-ttu-id="11037-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="11037-1327">issue number</span></span>
- <span data-ttu-id="11037-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="11037-1328">issue no</span></span>
- <span data-ttu-id="11037-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="11037-1329">cryptogramme</span></span>
- <span data-ttu-id="11037-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="11037-1330">numéro de sécurité</span></span>
- <span data-ttu-id="11037-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="11037-1331">numero de securite</span></span>
- <span data-ttu-id="11037-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="11037-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="11037-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="11037-1334">prüfziffer</span></span>
- <span data-ttu-id="11037-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="11037-1335">prufziffer</span></span>
- <span data-ttu-id="11037-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="11037-1336">sicherheits Kode</span></span>
- <span data-ttu-id="11037-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="11037-1337">sicherheitscode</span></span>
- <span data-ttu-id="11037-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="11037-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="11037-1339">verfalldatum</span></span>
- <span data-ttu-id="11037-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="11037-1340">codice di verifica</span></span>
- <span data-ttu-id="11037-1341">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1341">cod.</span></span> <span data-ttu-id="11037-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1342">sicurezza</span></span>
- <span data-ttu-id="11037-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1343">cod sicurezza</span></span>
- <span data-ttu-id="11037-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="11037-1344">n autorizzazione</span></span>
- <span data-ttu-id="11037-1345">código</span><span class="sxs-lookup"><span data-stu-id="11037-1345">código</span></span>
- <span data-ttu-id="11037-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="11037-1346">codigo</span></span>
- <span data-ttu-id="11037-1347">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1347">cod.</span></span> <span data-ttu-id="11037-1348">seg</span><span class="sxs-lookup"><span data-stu-id="11037-1348">seg</span></span>
- <span data-ttu-id="11037-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="11037-1349">cod seg</span></span>
- <span data-ttu-id="11037-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1350">código de segurança</span></span>
- <span data-ttu-id="11037-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1351">codigo de seguranca</span></span>
- <span data-ttu-id="11037-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1352">codigo de segurança</span></span>
- <span data-ttu-id="11037-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1353">código de seguranca</span></span>
- <span data-ttu-id="11037-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="11037-1354">cód.</span></span> <span data-ttu-id="11037-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1355">segurança</span></span>
- <span data-ttu-id="11037-1356">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1356">cod.</span></span> <span data-ttu-id="11037-1357">seguranca cod。</span><span class="sxs-lookup"><span data-stu-id="11037-1357">seguranca cod.</span></span> <span data-ttu-id="11037-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1358">segurança</span></span>
- <span data-ttu-id="11037-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="11037-1359">cód.</span></span> <span data-ttu-id="11037-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1360">seguranca</span></span>
- <span data-ttu-id="11037-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1361">cód segurança</span></span>
- <span data-ttu-id="11037-1362">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="11037-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1363">cód seguranca</span></span>
- <span data-ttu-id="11037-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="11037-1364">número de verificação</span></span>
- <span data-ttu-id="11037-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="11037-1365">numero de verificacao</span></span>
- <span data-ttu-id="11037-1366">ablん f</span><span class="sxs-lookup"><span data-stu-id="11037-1366">ablauf</span></span>
- <span data-ttu-id="11037-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="11037-1367">gültig bis</span></span>
- <span data-ttu-id="11037-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="11037-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="11037-1369">gultig bis</span></span>
- <span data-ttu-id="11037-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="11037-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="11037-1371">scadenza</span></span>
- <span data-ttu-id="11037-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="11037-1372">data scad</span></span>
- <span data-ttu-id="11037-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="11037-1373">fecha de expiracion</span></span>
- <span data-ttu-id="11037-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="11037-1374">fecha de venc</span></span>
- <span data-ttu-id="11037-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="11037-1375">vencimiento</span></span>
- <span data-ttu-id="11037-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="11037-1376">válido hasta</span></span>
- <span data-ttu-id="11037-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="11037-1377">valido hasta</span></span>
- <span data-ttu-id="11037-1378">vto</span><span class="sxs-lookup"><span data-stu-id="11037-1378">vto</span></span>
- <span data-ttu-id="11037-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="11037-1379">data de expiração</span></span>
- <span data-ttu-id="11037-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="11037-1380">data de expiracao</span></span>
- <span data-ttu-id="11037-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="11037-1381">data em que expira</span></span>
- <span data-ttu-id="11037-1382">validade</span><span class="sxs-lookup"><span data-stu-id="11037-1382">validade</span></span>
- <span data-ttu-id="11037-1383">valor は</span><span class="sxs-lookup"><span data-stu-id="11037-1383">valor</span></span>
- <span data-ttu-id="11037-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="11037-1384">vencimento</span></span>
- <span data-ttu-id="11037-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="11037-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="11037-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="11037-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="11037-1387">amex</span><span class="sxs-lookup"><span data-stu-id="11037-1387">amex</span></span>
- <span data-ttu-id="11037-1388">american express</span><span class="sxs-lookup"><span data-stu-id="11037-1388">american express</span></span>
- <span data-ttu-id="11037-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="11037-1389">americanexpress</span></span>
- <span data-ttu-id="11037-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="11037-1390">Visa</span></span>
- <span data-ttu-id="11037-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="11037-1391">mastercard</span></span>
- <span data-ttu-id="11037-1392">master card</span><span class="sxs-lookup"><span data-stu-id="11037-1392">master card</span></span>
- <span data-ttu-id="11037-1393">mc</span><span class="sxs-lookup"><span data-stu-id="11037-1393">mc</span></span> 
- <span data-ttu-id="11037-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="11037-1394">mastercards</span></span>
- <span data-ttu-id="11037-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="11037-1395">master cards</span></span>
- <span data-ttu-id="11037-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="11037-1396">diner's Club</span></span>
- <span data-ttu-id="11037-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="11037-1397">diners club</span></span>
- <span data-ttu-id="11037-1398">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="11037-1398">dinersclub</span></span>
- <span data-ttu-id="11037-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="11037-1399">discover card</span></span>
- <span data-ttu-id="11037-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="11037-1400">discovercard</span></span>
- <span data-ttu-id="11037-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="11037-1401">discover cards</span></span>
- <span data-ttu-id="11037-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="11037-1402">JCB</span></span>
- <span data-ttu-id="11037-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="11037-1403">japanese card bureau</span></span>
- <span data-ttu-id="11037-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="11037-1404">carte blanche</span></span>
- <span data-ttu-id="11037-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="11037-1405">carteblanche</span></span>
- <span data-ttu-id="11037-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="11037-1406">credit card</span></span>
- <span data-ttu-id="11037-1407">]#</span><span class="sxs-lookup"><span data-stu-id="11037-1407">cc#</span></span>
- <span data-ttu-id="11037-1408">cc #:</span><span class="sxs-lookup"><span data-stu-id="11037-1408">cc#:</span></span>
- <span data-ttu-id="11037-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="11037-1409">expiration date</span></span>
- <span data-ttu-id="11037-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="11037-1410">exp date</span></span>
- <span data-ttu-id="11037-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="11037-1411">expiry date</span></span>
- <span data-ttu-id="11037-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="11037-1412">date d’expiration</span></span>
- <span data-ttu-id="11037-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="11037-1413">date d'exp</span></span>
- <span data-ttu-id="11037-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="11037-1414">date expiration</span></span>
- <span data-ttu-id="11037-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="11037-1415">bank card</span></span>
- <span data-ttu-id="11037-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="11037-1416">bankcard</span></span>
- <span data-ttu-id="11037-1417">card number</span><span class="sxs-lookup"><span data-stu-id="11037-1417">card number</span></span>
- <span data-ttu-id="11037-1418">card num</span><span class="sxs-lookup"><span data-stu-id="11037-1418">card num</span></span>
- <span data-ttu-id="11037-1419">カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-1419">cardnumber</span></span>
- <span data-ttu-id="11037-1420">カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-1420">cardnumbers</span></span>
- <span data-ttu-id="11037-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="11037-1421">card numbers</span></span>
- <span data-ttu-id="11037-1422">creditcard</span><span class="sxs-lookup"><span data-stu-id="11037-1422">creditcard</span></span>
- <span data-ttu-id="11037-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="11037-1423">credit cards</span></span>
- <span data-ttu-id="11037-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="11037-1424">creditcards</span></span>
- <span data-ttu-id="11037-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="11037-1425">ccn</span></span>
- <span data-ttu-id="11037-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="11037-1426">card holder</span></span>
- <span data-ttu-id="11037-1427">所有者</span><span class="sxs-lookup"><span data-stu-id="11037-1427">cardholder</span></span>
- <span data-ttu-id="11037-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="11037-1428">card holders</span></span>
- <span data-ttu-id="11037-1429">cardholders</span><span class="sxs-lookup"><span data-stu-id="11037-1429">cardholders</span></span>
- <span data-ttu-id="11037-1430">check card</span><span class="sxs-lookup"><span data-stu-id="11037-1430">check card</span></span>
- <span data-ttu-id="11037-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="11037-1431">checkcard</span></span>
- <span data-ttu-id="11037-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="11037-1432">check cards</span></span>
- <span data-ttu-id="11037-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="11037-1433">checkcards</span></span>
- <span data-ttu-id="11037-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="11037-1434">debit card</span></span>
- <span data-ttu-id="11037-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="11037-1435">debitcard</span></span>
- <span data-ttu-id="11037-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="11037-1436">debit cards</span></span>
- <span data-ttu-id="11037-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="11037-1437">debitcards</span></span>
- <span data-ttu-id="11037-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="11037-1438">atm card</span></span>
- <span data-ttu-id="11037-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="11037-1439">atmcard</span></span>
- <span data-ttu-id="11037-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="11037-1440">atm cards</span></span>
- <span data-ttu-id="11037-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="11037-1441">atmcards</span></span>
- <span data-ttu-id="11037-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="11037-1442">enroute</span></span>
- <span data-ttu-id="11037-1443">en route</span><span class="sxs-lookup"><span data-stu-id="11037-1443">en route</span></span>
- <span data-ttu-id="11037-1444">card type</span><span class="sxs-lookup"><span data-stu-id="11037-1444">card type</span></span>
- <span data-ttu-id="11037-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="11037-1445">carte bancaire</span></span>
- <span data-ttu-id="11037-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="11037-1446">carte de crédit</span></span>
- <span data-ttu-id="11037-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="11037-1447">carte de credit</span></span>
- <span data-ttu-id="11037-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="11037-1448">numéro de carte</span></span>
- <span data-ttu-id="11037-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="11037-1449">numero de carte</span></span>
- <span data-ttu-id="11037-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="11037-1450">nº de la carte</span></span>
- <span data-ttu-id="11037-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="11037-1451">nº de carte</span></span>
- <span data-ttu-id="11037-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="11037-1452">kreditkarte</span></span>
- <span data-ttu-id="11037-1453">karte</span><span class="sxs-lookup"><span data-stu-id="11037-1453">karte</span></span>
- <span data-ttu-id="11037-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="11037-1454">karteninhaber</span></span>
- <span data-ttu-id="11037-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="11037-1455">karteninhabers</span></span>
- <span data-ttu-id="11037-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="11037-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="11037-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="11037-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="11037-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="11037-1458">kreditkartentyp</span></span>
- <span data-ttu-id="11037-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="11037-1459">eigentümername</span></span>
- <span data-ttu-id="11037-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="11037-1460">kartennr</span></span> 
- <span data-ttu-id="11037-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="11037-1461">kartennummer</span></span>
- <span data-ttu-id="11037-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="11037-1462">kreditkartennummer</span></span>
- <span data-ttu-id="11037-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="11037-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="11037-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="11037-1464">carta di credito</span></span>
- <span data-ttu-id="11037-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="11037-1465">carta credito</span></span>
- <span data-ttu-id="11037-1466">carta</span><span class="sxs-lookup"><span data-stu-id="11037-1466">carta</span></span>
- <span data-ttu-id="11037-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="11037-1467">n carta</span></span>
- <span data-ttu-id="11037-1468">nr.</span><span class="sxs-lookup"><span data-stu-id="11037-1468">nr.</span></span> <span data-ttu-id="11037-1469">carta</span><span class="sxs-lookup"><span data-stu-id="11037-1469">carta</span></span>
- <span data-ttu-id="11037-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="11037-1470">nr carta</span></span>
- <span data-ttu-id="11037-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="11037-1471">numero carta</span></span>
- <span data-ttu-id="11037-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="11037-1472">numero della carta</span></span>
- <span data-ttu-id="11037-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="11037-1473">numero di carta</span></span>
- <span data-ttu-id="11037-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="11037-1474">tarjeta credito</span></span>
- <span data-ttu-id="11037-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="11037-1475">tarjeta de credito</span></span>
- <span data-ttu-id="11037-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="11037-1476">tarjeta crédito</span></span>
- <span data-ttu-id="11037-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="11037-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="11037-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="11037-1478">tarjeta de atm</span></span>
- <span data-ttu-id="11037-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="11037-1479">tarjeta atm</span></span>
- <span data-ttu-id="11037-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="11037-1480">tarjeta debito</span></span>
- <span data-ttu-id="11037-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="11037-1481">tarjeta de debito</span></span>
- <span data-ttu-id="11037-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="11037-1482">tarjeta débito</span></span>
- <span data-ttu-id="11037-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="11037-1483">tarjeta de débito</span></span>
- <span data-ttu-id="11037-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1484">nº de tarjeta</span></span>
- <span data-ttu-id="11037-1485">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1485">no.</span></span> <span data-ttu-id="11037-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1486">de tarjeta</span></span>
- <span data-ttu-id="11037-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1487">no de tarjeta</span></span>
- <span data-ttu-id="11037-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1488">numero de tarjeta</span></span>
- <span data-ttu-id="11037-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1489">número de tarjeta</span></span>
- <span data-ttu-id="11037-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="11037-1490">tarjeta no</span></span>
- <span data-ttu-id="11037-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="11037-1491">tarjetahabiente</span></span>
- <span data-ttu-id="11037-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="11037-1492">cartão de crédito</span></span>
- <span data-ttu-id="11037-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="11037-1493">cartão de credito</span></span>
- <span data-ttu-id="11037-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="11037-1494">cartao de crédito</span></span>
- <span data-ttu-id="11037-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="11037-1495">cartao de credito</span></span>
- <span data-ttu-id="11037-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="11037-1496">cartão de débito</span></span>
- <span data-ttu-id="11037-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="11037-1497">cartao de débito</span></span>
- <span data-ttu-id="11037-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="11037-1498">cartão de debito</span></span>
- <span data-ttu-id="11037-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="11037-1499">cartao de debito</span></span>
- <span data-ttu-id="11037-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="11037-1500">débito automático</span></span>
- <span data-ttu-id="11037-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="11037-1501">debito automatico</span></span>
- <span data-ttu-id="11037-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1502">número do cartão</span></span>
- <span data-ttu-id="11037-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1503">numero do cartão</span></span> 
- <span data-ttu-id="11037-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1504">número do cartao</span></span>
- <span data-ttu-id="11037-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1505">numero do cartao</span></span>
- <span data-ttu-id="11037-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1506">número de cartão</span></span>
- <span data-ttu-id="11037-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1507">numero de cartão</span></span>
- <span data-ttu-id="11037-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1508">número de cartao</span></span>
- <span data-ttu-id="11037-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1509">numero de cartao</span></span>
- <span data-ttu-id="11037-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1510">nº do cartão</span></span>
- <span data-ttu-id="11037-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1511">nº do cartao</span></span>
- <span data-ttu-id="11037-1512">n °</span><span class="sxs-lookup"><span data-stu-id="11037-1512">nº.</span></span> <span data-ttu-id="11037-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1513">do cartão</span></span>
- <span data-ttu-id="11037-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1514">no do cartão</span></span>
- <span data-ttu-id="11037-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1515">no do cartao</span></span>
- <span data-ttu-id="11037-1516">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1516">no.</span></span> <span data-ttu-id="11037-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1517">do cartão</span></span>
- <span data-ttu-id="11037-1518">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1518">no.</span></span> <span data-ttu-id="11037-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="11037-1520">クロアチアの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="11037-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1521">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1521">Format</span></span>

<span data-ttu-id="11037-1522">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1523">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1523">Pattern</span></span>

<span data-ttu-id="11037-1524">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1525">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1525">Checksum</span></span>

<span data-ttu-id="11037-1526">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1527">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1527">Definition</span></span>

<span data-ttu-id="11037-1528">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1529">関数 Func_croatia_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1530">Keyword_croatia_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-1531">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="11037-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="11037-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="11037-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="11037-1533">Croatian identity card</span></span>
- <span data-ttu-id="11037-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="11037-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="11037-1535">	Croatia Personal Identification (OIB) Number</span><span class="sxs-lookup"><span data-stu-id="11037-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1536">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1536">Format</span></span>

<span data-ttu-id="11037-1537">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1538">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1538">Pattern</span></span>

<span data-ttu-id="11037-1539">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-1539">11 digits:</span></span>
- <span data-ttu-id="11037-1540">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1540">10 digits</span></span> 
- <span data-ttu-id="11037-1541">最終桁は、国際的なデータ交換のためのチェックディジットです。 HR は11桁の数字の前に追加されます。</span><span class="sxs-lookup"><span data-stu-id="11037-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1542">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1542">Checksum</span></span>

<span data-ttu-id="11037-1543">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1544">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1544">Definition</span></span>

<span data-ttu-id="11037-1545">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1546">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1547">Keyword_croatia_oib_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="11037-1548">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1548">The checksum passes.</span></span>

<span data-ttu-id="11037-1549">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1550">関数 Func_croatia_oib_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1551">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1551">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1552">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="11037-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="11037-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="11037-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="11037-1554">Personal Identification Number</span></span>
- <span data-ttu-id="11037-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="11037-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="11037-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="11037-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="11037-1557">チェコの個人 Id 番号</span><span class="sxs-lookup"><span data-stu-id="11037-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1558">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1558">Format</span></span>

<span data-ttu-id="11037-1559">省略可能なスラッシュ (古い形式) を含む9桁の数字 (省略可能)。スラッシュ (新しい形式)</span><span class="sxs-lookup"><span data-stu-id="11037-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1560">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1560">Pattern</span></span>

<span data-ttu-id="11037-1561">9桁の数字 (古い形式):</span><span class="sxs-lookup"><span data-stu-id="11037-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="11037-1562">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1562">Nine digits</span></span>

<span data-ttu-id="11037-1563">OR</span><span class="sxs-lookup"><span data-stu-id="11037-1563">OR</span></span>

- <span data-ttu-id="11037-1564">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="11037-1565">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-1565">A forward slash</span></span>
- <span data-ttu-id="11037-1566">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1566">Three digits</span></span>

<span data-ttu-id="11037-1567">10桁の数字 (新しい形式):</span><span class="sxs-lookup"><span data-stu-id="11037-1567">10 digits (new format):</span></span>
- <span data-ttu-id="11037-1568">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1568">10 digits</span></span>

<span data-ttu-id="11037-1569">OR</span><span class="sxs-lookup"><span data-stu-id="11037-1569">OR</span></span>

- <span data-ttu-id="11037-1570">生年月日を表す6桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="11037-1571">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-1571">A forward slash</span></span> 
- <span data-ttu-id="11037-1572">4桁の数字 (最後の桁はチェックディジット)</span><span class="sxs-lookup"><span data-stu-id="11037-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1573">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1573">Checksum</span></span>

<span data-ttu-id="11037-1574">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1575">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1575">Definition</span></span>

<span data-ttu-id="11037-1576">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_czech_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-1577">Keyword_czech_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="11037-1578">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="11037-1579">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1579">Keywords</span></span>

- <span data-ttu-id="11037-1580">チェコの個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="11037-1580">czech personal identity number</span></span>
- <span data-ttu-id="11037-1581">Rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="11037-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="11037-1582">	Denmark Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="11037-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1583">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1583">Format</span></span>

<span data-ttu-id="11037-1584">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1585">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1585">Pattern</span></span>

<span data-ttu-id="11037-1586">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-1586">10 digits:</span></span>
- <span data-ttu-id="11037-1587">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="11037-1588">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-1588">A hyphen</span></span> 
- <span data-ttu-id="11037-1589">4 桁の数字 (最後の桁はチェック ディジット)</span><span class="sxs-lookup"><span data-stu-id="11037-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1590">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1590">Checksum</span></span>

<span data-ttu-id="11037-1591">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1592">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1592">Definition</span></span>

<span data-ttu-id="11037-1593">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。正規表現 Regex_denmark_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-1594">Keyword_denmark_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="11037-1595">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-1596">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="11037-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="11037-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="11037-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="11037-1598">Personal Identification Number</span></span>
- <span data-ttu-id="11037-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="11037-1599">CPR</span></span>
- <span data-ttu-id="11037-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="11037-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="11037-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="11037-1602">麻薬取締局 (DEA) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1603">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1603">Format</span></span>

<span data-ttu-id="11037-1604">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1605">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1605">Pattern</span></span>

<span data-ttu-id="11037-1606">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="11037-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="11037-1607">次の文字セットのいずれか 1 つの文字 (大文字小文字を区別しない):abcdefghjklmnprstux。これは登録者コードです</span><span class="sxs-lookup"><span data-stu-id="11037-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="11037-1608">1 文字 (大文字小文字を区別しない)。登録者の姓の最初の文字</span><span class="sxs-lookup"><span data-stu-id="11037-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="11037-1609">7 桁の数字。最後の桁はチェック ディジット用です</span><span class="sxs-lookup"><span data-stu-id="11037-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1610">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1610">Checksum</span></span>

<span data-ttu-id="11037-1611">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1612">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1612">Definition</span></span>

<span data-ttu-id="11037-1613">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1614">関数 Func_dea_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1615">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-1616">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1616">Keywords</span></span>

<span data-ttu-id="11037-1617">None</span><span class="sxs-lookup"><span data-stu-id="11037-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="11037-1618">欧州連合のデビット カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1619">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1619">Format</span></span>

<span data-ttu-id="11037-1620">16 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1621">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1621">Pattern</span></span>

<span data-ttu-id="11037-1622">非常に複雑で信頼性の高いパターン</span><span class="sxs-lookup"><span data-stu-id="11037-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1623">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1623">Checksum</span></span>

<span data-ttu-id="11037-1624">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1625">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1625">Definition</span></span>

<span data-ttu-id="11037-1626">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1627">関数 Func_eu_debit_card がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1628">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="11037-1629">Keyword_eu_debit_card のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="11037-1630">Keyword_card_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="11037-1631">Keyword_card_security_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="11037-1632">Keyword_card_expiration_terms_dict のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="11037-1633">関数 Func_expiration_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-1634">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1634">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1635">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="11037-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="11037-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="11037-1637">account number</span><span class="sxs-lookup"><span data-stu-id="11037-1637">account number</span></span> 
- <span data-ttu-id="11037-1638">card number</span><span class="sxs-lookup"><span data-stu-id="11037-1638">card number</span></span> 
- <span data-ttu-id="11037-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="11037-1639">card no.</span></span> 
- <span data-ttu-id="11037-1640">security number</span><span class="sxs-lookup"><span data-stu-id="11037-1640">security number</span></span> 
- <span data-ttu-id="11037-1641">]#</span><span class="sxs-lookup"><span data-stu-id="11037-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="11037-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="11037-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="11037-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="11037-1643">acct nbr</span></span> 
- <span data-ttu-id="11037-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="11037-1644">acct num</span></span> 
- <span data-ttu-id="11037-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="11037-1645">acct no</span></span> 
- <span data-ttu-id="11037-1646">american express</span><span class="sxs-lookup"><span data-stu-id="11037-1646">american express</span></span> 
- <span data-ttu-id="11037-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="11037-1647">americanexpress</span></span> 
- <span data-ttu-id="11037-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="11037-1648">americano espresso</span></span> 
- <span data-ttu-id="11037-1649">amex</span><span class="sxs-lookup"><span data-stu-id="11037-1649">amex</span></span> 
- <span data-ttu-id="11037-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="11037-1650">atm card</span></span> 
- <span data-ttu-id="11037-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="11037-1651">atm cards</span></span> 
- <span data-ttu-id="11037-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="11037-1652">atm kaart</span></span> 
- <span data-ttu-id="11037-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="11037-1653">atmcard</span></span> 
- <span data-ttu-id="11037-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="11037-1654">atmcards</span></span> 
- <span data-ttu-id="11037-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="11037-1655">atmkaart</span></span> 
- <span data-ttu-id="11037-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="11037-1656">atmkaarten</span></span> 
- <span data-ttu-id="11037-1657"># # の連絡先</span><span class="sxs-lookup"><span data-stu-id="11037-1657">bancontact</span></span> 
- <span data-ttu-id="11037-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="11037-1658">bank card</span></span> 
- <span data-ttu-id="11037-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="11037-1659">bankkaart</span></span> 
- <span data-ttu-id="11037-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="11037-1660">card holder</span></span> 
- <span data-ttu-id="11037-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="11037-1661">card holders</span></span> 
- <span data-ttu-id="11037-1662">card num</span><span class="sxs-lookup"><span data-stu-id="11037-1662">card num</span></span> 
- <span data-ttu-id="11037-1663">card number</span><span class="sxs-lookup"><span data-stu-id="11037-1663">card number</span></span> 
- <span data-ttu-id="11037-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="11037-1664">card numbers</span></span> 
- <span data-ttu-id="11037-1665">card type</span><span class="sxs-lookup"><span data-stu-id="11037-1665">card type</span></span> 
- <span data-ttu-id="11037-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="11037-1666">cardano numerico</span></span> 
- <span data-ttu-id="11037-1667">所有者</span><span class="sxs-lookup"><span data-stu-id="11037-1667">cardholder</span></span> 
- <span data-ttu-id="11037-1668">cardholders</span><span class="sxs-lookup"><span data-stu-id="11037-1668">cardholders</span></span> 
- <span data-ttu-id="11037-1669">カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-1669">cardnumber</span></span> 
- <span data-ttu-id="11037-1670">カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-1670">cardnumbers</span></span> 
- <span data-ttu-id="11037-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="11037-1671">carta bianca</span></span> 
- <span data-ttu-id="11037-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="11037-1672">carta credito</span></span> 
- <span data-ttu-id="11037-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="11037-1673">carta di credito</span></span> 
- <span data-ttu-id="11037-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="11037-1674">cartao de credito</span></span> 
- <span data-ttu-id="11037-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="11037-1675">cartao de crédito</span></span> 
- <span data-ttu-id="11037-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="11037-1676">cartao de debito</span></span> 
- <span data-ttu-id="11037-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="11037-1677">cartao de débito</span></span> 
- <span data-ttu-id="11037-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="11037-1678">carte bancaire</span></span> 
- <span data-ttu-id="11037-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="11037-1679">carte blanche</span></span> 
- <span data-ttu-id="11037-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="11037-1680">carte bleue</span></span> 
- <span data-ttu-id="11037-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="11037-1681">carte de credit</span></span> 
- <span data-ttu-id="11037-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="11037-1682">carte de crédit</span></span> 
- <span data-ttu-id="11037-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="11037-1683">carte di credito</span></span> 
- <span data-ttu-id="11037-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="11037-1684">carteblanche</span></span> 
- <span data-ttu-id="11037-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="11037-1685">cartão de credito</span></span> 
- <span data-ttu-id="11037-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="11037-1686">cartão de crédito</span></span> 
- <span data-ttu-id="11037-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="11037-1687">cartão de debito</span></span> 
- <span data-ttu-id="11037-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="11037-1688">cartão de débito</span></span> 
- <span data-ttu-id="11037-1689">cb</span><span class="sxs-lookup"><span data-stu-id="11037-1689">cb</span></span> 
- <span data-ttu-id="11037-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="11037-1690">ccn</span></span> 
- <span data-ttu-id="11037-1691">check card</span><span class="sxs-lookup"><span data-stu-id="11037-1691">check card</span></span> 
- <span data-ttu-id="11037-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="11037-1692">check cards</span></span> 
- <span data-ttu-id="11037-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="11037-1693">checkcard</span></span>
- <span data-ttu-id="11037-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="11037-1694">checkcards</span></span> 
- <span data-ttu-id="11037-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="11037-1695">chequekaart</span></span> 
- <span data-ttu-id="11037-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="11037-1696">cirrus</span></span> 
- <span data-ttu-id="11037-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="11037-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="11037-1698">lekaart の方法</span><span class="sxs-lookup"><span data-stu-id="11037-1698">controlekaart</span></span> 
- <span data-ttu-id="11037-1699">lekaar10 の場合</span><span class="sxs-lookup"><span data-stu-id="11037-1699">controlekaarten</span></span> 
- <span data-ttu-id="11037-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="11037-1700">credit card</span></span> 
- <span data-ttu-id="11037-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="11037-1701">credit cards</span></span> 
- <span data-ttu-id="11037-1702">creditcard</span><span class="sxs-lookup"><span data-stu-id="11037-1702">creditcard</span></span> 
- <span data-ttu-id="11037-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="11037-1703">creditcards</span></span> 
- <span data-ttu-id="11037-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="11037-1704">debetkaart</span></span> 
- <span data-ttu-id="11037-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="11037-1705">debetkaarten</span></span> 
- <span data-ttu-id="11037-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="11037-1706">debit card</span></span> 
- <span data-ttu-id="11037-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="11037-1707">debit cards</span></span> 
- <span data-ttu-id="11037-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="11037-1708">debitcard</span></span> 
- <span data-ttu-id="11037-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="11037-1709">debitcards</span></span> 
- <span data-ttu-id="11037-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="11037-1710">debito automatico</span></span> 
- <span data-ttu-id="11037-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="11037-1711">diners club</span></span> 
- <span data-ttu-id="11037-1712">din/クラブ</span><span class="sxs-lookup"><span data-stu-id="11037-1712">dinersclub</span></span> 
- <span data-ttu-id="11037-1713">開示</span><span class="sxs-lookup"><span data-stu-id="11037-1713">discover</span></span> 
- <span data-ttu-id="11037-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="11037-1714">discover card</span></span> 
- <span data-ttu-id="11037-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="11037-1715">discover cards</span></span> 
- <span data-ttu-id="11037-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="11037-1716">discovercard</span></span> 
- <span data-ttu-id="11037-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="11037-1717">discovercards</span></span> 
- <span data-ttu-id="11037-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="11037-1718">débito automático</span></span>
- <span data-ttu-id="11037-1719">edc</span><span class="sxs-lookup"><span data-stu-id="11037-1719">edc</span></span> 
- <span data-ttu-id="11037-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="11037-1720">eigentümername</span></span> 
- <span data-ttu-id="11037-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="11037-1721">european debit card</span></span> 
- <span data-ttu-id="11037-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="11037-1722">hoofdkaart</span></span> 
- <span data-ttu-id="11037-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="11037-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="11037-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="11037-1724">in viaggio</span></span> 
- <span data-ttu-id="11037-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="11037-1725">japanese card bureau</span></span> 
- <span data-ttu-id="11037-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="11037-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="11037-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="11037-1727">jcb</span></span> 
- <span data-ttu-id="11037-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="11037-1728">kaart</span></span> 
- <span data-ttu-id="11037-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="11037-1729">kaart num</span></span> 
- <span data-ttu-id="11037-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="11037-1730">kaartaantal</span></span> 
- <span data-ttu-id="11037-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="11037-1731">kaartaantallen</span></span> 
- <span data-ttu-id="11037-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="11037-1732">kaarthouder</span></span> 
- <span data-ttu-id="11037-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="11037-1733">kaarthouders</span></span> 
- <span data-ttu-id="11037-1734">karte</span><span class="sxs-lookup"><span data-stu-id="11037-1734">karte</span></span>  
- <span data-ttu-id="11037-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="11037-1735">karteninhaber</span></span> 
- <span data-ttu-id="11037-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="11037-1736">karteninhabers</span></span>
- <span data-ttu-id="11037-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="11037-1737">kartennr</span></span> 
- <span data-ttu-id="11037-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="11037-1738">kartennummer</span></span> 
- <span data-ttu-id="11037-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="11037-1739">kreditkarte</span></span> 
- <span data-ttu-id="11037-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="11037-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="11037-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="11037-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="11037-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="11037-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="11037-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="11037-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="11037-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="11037-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="11037-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="11037-1745">maestro</span></span> 
- <span data-ttu-id="11037-1746">master card</span><span class="sxs-lookup"><span data-stu-id="11037-1746">master card</span></span> 
- <span data-ttu-id="11037-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="11037-1747">master cards</span></span> 
- <span data-ttu-id="11037-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="11037-1748">mastercard</span></span> 
- <span data-ttu-id="11037-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="11037-1749">mastercards</span></span> 
- <span data-ttu-id="11037-1750">mc</span><span class="sxs-lookup"><span data-stu-id="11037-1750">mc</span></span> 
- <span data-ttu-id="11037-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="11037-1751">mister cash</span></span> 
- <span data-ttu-id="11037-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="11037-1752">n carta</span></span> 
- <span data-ttu-id="11037-1753">carta</span><span class="sxs-lookup"><span data-stu-id="11037-1753">carta</span></span> 
- <span data-ttu-id="11037-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1754">no de tarjeta</span></span> 
- <span data-ttu-id="11037-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1755">no do cartao</span></span> 
- <span data-ttu-id="11037-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1756">no do cartão</span></span> 
- <span data-ttu-id="11037-1757">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1757">no.</span></span> <span data-ttu-id="11037-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1758">de tarjeta</span></span> 
- <span data-ttu-id="11037-1759">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1759">no.</span></span> <span data-ttu-id="11037-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1760">do cartao</span></span> 
- <span data-ttu-id="11037-1761">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1761">no.</span></span> <span data-ttu-id="11037-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1762">do cartão</span></span> 
- <span data-ttu-id="11037-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="11037-1763">nr carta</span></span> 
- <span data-ttu-id="11037-1764">nr.</span><span class="sxs-lookup"><span data-stu-id="11037-1764">nr.</span></span> <span data-ttu-id="11037-1765">carta</span><span class="sxs-lookup"><span data-stu-id="11037-1765">carta</span></span> 
- <span data-ttu-id="11037-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1766">numeri di scheda</span></span> 
- <span data-ttu-id="11037-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="11037-1767">numero carta</span></span> 
- <span data-ttu-id="11037-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1768">numero de cartao</span></span> 
- <span data-ttu-id="11037-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="11037-1769">numero de carte</span></span> 
- <span data-ttu-id="11037-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1770">numero de cartão</span></span> 
- <span data-ttu-id="11037-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1771">numero de tarjeta</span></span>
- <span data-ttu-id="11037-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="11037-1772">numero della carta</span></span> 
- <span data-ttu-id="11037-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="11037-1773">numero di carta</span></span> 
- <span data-ttu-id="11037-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1774">numero di scheda</span></span> 
- <span data-ttu-id="11037-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1775">numero do cartao</span></span> 
- <span data-ttu-id="11037-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1776">numero do cartão</span></span> 
- <span data-ttu-id="11037-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="11037-1777">numéro de carte</span></span> 
- <span data-ttu-id="11037-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="11037-1778">nº carta</span></span> 
- <span data-ttu-id="11037-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="11037-1779">nº de carte</span></span> 
- <span data-ttu-id="11037-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="11037-1780">nº de la carte</span></span> 
- <span data-ttu-id="11037-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="11037-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1782">nº do cartao</span></span> 
- <span data-ttu-id="11037-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1783">nº do cartão</span></span> 
- <span data-ttu-id="11037-1784">n °</span><span class="sxs-lookup"><span data-stu-id="11037-1784">nº.</span></span> <span data-ttu-id="11037-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1785">do cartão</span></span> 
- <span data-ttu-id="11037-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1786">número de cartao</span></span> 
- <span data-ttu-id="11037-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="11037-1787">número de cartão</span></span> 
- <span data-ttu-id="11037-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="11037-1788">número de tarjeta</span></span> 
- <span data-ttu-id="11037-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="11037-1789">número do cartao</span></span> 
- <span data-ttu-id="11037-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="11037-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="11037-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="11037-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="11037-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="11037-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="11037-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="11037-1793">scheda della banca</span></span> 
- <span data-ttu-id="11037-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="11037-1794">scheda di controllo</span></span> 
- <span data-ttu-id="11037-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="11037-1795">scheda di debito</span></span> 
- <span data-ttu-id="11037-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="11037-1796">scheda matrice</span></span> 
- <span data-ttu-id="11037-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="11037-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="11037-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="11037-1798">schede di controllo</span></span> 
- <span data-ttu-id="11037-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="11037-1799">schede di debito</span></span> 
- <span data-ttu-id="11037-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="11037-1800">schede matrici</span></span> 
- <span data-ttu-id="11037-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="11037-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="11037-1802">scoprono le schede</span></span> 
- <span data-ttu-id="11037-1803">単独</span><span class="sxs-lookup"><span data-stu-id="11037-1803">solo</span></span> 
- <span data-ttu-id="11037-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1804">supporti di scheda</span></span> 
- <span data-ttu-id="11037-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1805">supporto di scheda</span></span> 
- <span data-ttu-id="11037-1806">switch</span><span class="sxs-lookup"><span data-stu-id="11037-1806">switch</span></span> 
- <span data-ttu-id="11037-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="11037-1807">tarjeta atm</span></span> 
- <span data-ttu-id="11037-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="11037-1808">tarjeta credito</span></span> 
- <span data-ttu-id="11037-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="11037-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="11037-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="11037-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="11037-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="11037-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="11037-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="11037-1812">tarjeta debito</span></span> 
- <span data-ttu-id="11037-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="11037-1813">tarjeta no</span></span>
- <span data-ttu-id="11037-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="11037-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="11037-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1815">tipo della scheda</span></span> 
- <span data-ttu-id="11037-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="11037-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="11037-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1817">scheda</span></span> 
- <span data-ttu-id="11037-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="11037-1818">v pay</span></span> 
- <span data-ttu-id="11037-1819">v-支払い</span><span class="sxs-lookup"><span data-stu-id="11037-1819">v-pay</span></span> 
- <span data-ttu-id="11037-1820">visa</span><span class="sxs-lookup"><span data-stu-id="11037-1820">visa</span></span> 
- <span data-ttu-id="11037-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="11037-1821">visa plus</span></span> 
- <span data-ttu-id="11037-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="11037-1822">visa electron</span></span> 
- <span data-ttu-id="11037-1823">visto</span><span class="sxs-lookup"><span data-stu-id="11037-1823">visto</span></span> 
- <span data-ttu-id="11037-1824">visum</span><span class="sxs-lookup"><span data-stu-id="11037-1824">visum</span></span> 
- <span data-ttu-id="11037-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="11037-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="11037-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="11037-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="11037-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="11037-1827">card identification number</span></span>
- <span data-ttu-id="11037-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="11037-1828">card verification</span></span> 
- <span data-ttu-id="11037-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="11037-1829">cardi la verifica</span></span> 
- <span data-ttu-id="11037-1830">cid</span><span class="sxs-lookup"><span data-stu-id="11037-1830">cid</span></span> 
- <span data-ttu-id="11037-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="11037-1831">cod seg</span></span> 
- <span data-ttu-id="11037-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1832">cod seguranca</span></span> 
- <span data-ttu-id="11037-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1833">cod segurança</span></span> 
- <span data-ttu-id="11037-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1834">cod sicurezza</span></span> 
- <span data-ttu-id="11037-1835">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1835">cod.</span></span> <span data-ttu-id="11037-1836">seg</span><span class="sxs-lookup"><span data-stu-id="11037-1836">seg</span></span> 
- <span data-ttu-id="11037-1837">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1837">cod.</span></span> <span data-ttu-id="11037-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1838">seguranca</span></span> 
- <span data-ttu-id="11037-1839">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1839">cod.</span></span> <span data-ttu-id="11037-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1840">segurança</span></span> 
- <span data-ttu-id="11037-1841">cod.</span><span class="sxs-lookup"><span data-stu-id="11037-1841">cod.</span></span> <span data-ttu-id="11037-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1842">sicurezza</span></span> 
- <span data-ttu-id="11037-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="11037-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="11037-1844">codice di verifica</span></span> 
- <span data-ttu-id="11037-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="11037-1845">codigo</span></span> 
- <span data-ttu-id="11037-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="11037-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1847">codigo de segurança</span></span> 
- <span data-ttu-id="11037-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="11037-1848">crittogramma</span></span> 
- <span data-ttu-id="11037-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="11037-1849">cryptogram</span></span> 
- <span data-ttu-id="11037-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="11037-1850">cryptogramme</span></span> 
- <span data-ttu-id="11037-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="11037-1851">cv2</span></span> 
- <span data-ttu-id="11037-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="11037-1852">cvc</span></span> 
- <span data-ttu-id="11037-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="11037-1853">cvc2</span></span> 
- <span data-ttu-id="11037-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="11037-1854">cvn</span></span> 
- <span data-ttu-id="11037-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="11037-1855">cvv</span></span> 
- <span data-ttu-id="11037-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="11037-1856">cvv2</span></span> 
- <span data-ttu-id="11037-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1857">cód seguranca</span></span> 
- <span data-ttu-id="11037-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1858">cód segurança</span></span> 
- <span data-ttu-id="11037-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="11037-1859">cód.</span></span> <span data-ttu-id="11037-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1860">seguranca</span></span> 
- <span data-ttu-id="11037-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="11037-1861">cód.</span></span> <span data-ttu-id="11037-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1862">segurança</span></span> 
- <span data-ttu-id="11037-1863">código</span><span class="sxs-lookup"><span data-stu-id="11037-1863">código</span></span> 
- <span data-ttu-id="11037-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="11037-1864">código de seguranca</span></span> 
- <span data-ttu-id="11037-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="11037-1865">código de segurança</span></span> 
- <span data-ttu-id="11037-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="11037-1866">de kaart controle</span></span> 
- <span data-ttu-id="11037-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="11037-1867">geeft nr uit</span></span> 
- <span data-ttu-id="11037-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="11037-1868">issue no</span></span> 
- <span data-ttu-id="11037-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="11037-1869">issue number</span></span> 
- <span data-ttu-id="11037-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="11037-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="11037-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="11037-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="11037-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="11037-1873">kwestieaantal</span></span> 
- <span data-ttu-id="11037-1874">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1874">no.</span></span> <span data-ttu-id="11037-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="11037-1875">dell'edizione</span></span> 
- <span data-ttu-id="11037-1876">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-1876">no.</span></span> <span data-ttu-id="11037-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1877">di sicurezza</span></span> 
- <span data-ttu-id="11037-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="11037-1878">numero de securite</span></span> 
- <span data-ttu-id="11037-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="11037-1879">numero de verificacao</span></span> 
- <span data-ttu-id="11037-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="11037-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="11037-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="11037-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="11037-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="11037-1882">scheda</span></span> 
- <span data-ttu-id="11037-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="11037-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="11037-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="11037-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="11037-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="11037-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="11037-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="11037-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="11037-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="11037-1887">número de verificação</span></span> 
- <span data-ttu-id="11037-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="11037-1888">perno il blocco</span></span> 
- <span data-ttu-id="11037-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="11037-1889">pin block</span></span> 
- <span data-ttu-id="11037-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="11037-1890">prufziffer</span></span> 
- <span data-ttu-id="11037-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="11037-1891">prüfziffer</span></span> 
- <span data-ttu-id="11037-1892">security code</span><span class="sxs-lookup"><span data-stu-id="11037-1892">security code</span></span> 
- <span data-ttu-id="11037-1893">security no</span><span class="sxs-lookup"><span data-stu-id="11037-1893">security no</span></span> 
- <span data-ttu-id="11037-1894">security number</span><span class="sxs-lookup"><span data-stu-id="11037-1894">security number</span></span> 
- <span data-ttu-id="11037-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="11037-1895">sicherheits kode</span></span> 
- <span data-ttu-id="11037-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="11037-1896">sicherheitscode</span></span> 
- <span data-ttu-id="11037-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="11037-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="11037-1898">speldblok</span></span> 
- <span data-ttu-id="11037-1899">veiligheid nr</span><span class="sxs-lookup"><span data-stu-id="11037-1899">veiligheid nr</span></span> 
- <span data-ttu-id="11037-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="11037-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="11037-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="11037-1901">veiligheidscode</span></span> 
- <span data-ttu-id="11037-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="11037-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="11037-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="11037-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="11037-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="11037-1905">ablん f</span><span class="sxs-lookup"><span data-stu-id="11037-1905">ablauf</span></span> 
- <span data-ttu-id="11037-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="11037-1906">data de expiracao</span></span> 
- <span data-ttu-id="11037-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="11037-1907">data de expiração</span></span> 
- <span data-ttu-id="11037-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="11037-1908">data del exp</span></span> 
- <span data-ttu-id="11037-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="11037-1909">data di exp</span></span> 
- <span data-ttu-id="11037-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="11037-1910">data di scadenza</span></span> 
- <span data-ttu-id="11037-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="11037-1911">data em que expira</span></span> 
- <span data-ttu-id="11037-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="11037-1912">data scad</span></span> 
- <span data-ttu-id="11037-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="11037-1913">data scadenza</span></span> 
- <span data-ttu-id="11037-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="11037-1914">date de validité</span></span> 
- <span data-ttu-id="11037-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="11037-1915">datum afloop</span></span> 
- <span data-ttu-id="11037-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="11037-1916">datum van exp</span></span> 
- <span data-ttu-id="11037-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="11037-1917">de afloop</span></span> 
- <span data-ttu-id="11037-1918">espira</span><span class="sxs-lookup"><span data-stu-id="11037-1918">espira</span></span> 
- <span data-ttu-id="11037-1919">espira</span><span class="sxs-lookup"><span data-stu-id="11037-1919">espira</span></span> 
- <span data-ttu-id="11037-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="11037-1920">exp date</span></span> 
- <span data-ttu-id="11037-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="11037-1921">exp datum</span></span> 
- <span data-ttu-id="11037-1922">nntp</span><span class="sxs-lookup"><span data-stu-id="11037-1922">expiration</span></span> 
- <span data-ttu-id="11037-1923">無効</span><span class="sxs-lookup"><span data-stu-id="11037-1923">expire</span></span> 
- <span data-ttu-id="11037-1924">期限</span><span class="sxs-lookup"><span data-stu-id="11037-1924">expires</span></span> 
- <span data-ttu-id="11037-1925">期限</span><span class="sxs-lookup"><span data-stu-id="11037-1925">expiry</span></span> 
- <span data-ttu-id="11037-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="11037-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="11037-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="11037-1927">fecha de venc</span></span> 
- <span data-ttu-id="11037-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="11037-1928">gultig bis</span></span> 
- <span data-ttu-id="11037-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="11037-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="11037-1930">gültig bis</span></span> 
- <span data-ttu-id="11037-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="11037-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="11037-1932">la scadenza</span></span> 
- <span data-ttu-id="11037-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="11037-1933">scadenza</span></span> 
- <span data-ttu-id="11037-1934">valable</span><span class="sxs-lookup"><span data-stu-id="11037-1934">valable</span></span> 
- <span data-ttu-id="11037-1935">validade</span><span class="sxs-lookup"><span data-stu-id="11037-1935">validade</span></span> 
- <span data-ttu-id="11037-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="11037-1936">valido hasta</span></span> 
- <span data-ttu-id="11037-1937">valor は</span><span class="sxs-lookup"><span data-stu-id="11037-1937">valor</span></span> 
- <span data-ttu-id="11037-1938">venc</span><span class="sxs-lookup"><span data-stu-id="11037-1938">venc</span></span> 
- <span data-ttu-id="11037-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="11037-1939">vencimento</span></span> 
- <span data-ttu-id="11037-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="11037-1940">vencimiento</span></span> 
- <span data-ttu-id="11037-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="11037-1941">verloopt</span></span> 
- <span data-ttu-id="11037-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="11037-1942">vervaldag</span></span> 
- <span data-ttu-id="11037-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="11037-1943">vervaldatum</span></span> 
- <span data-ttu-id="11037-1944">vto</span><span class="sxs-lookup"><span data-stu-id="11037-1944">vto</span></span> 
- <span data-ttu-id="11037-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="11037-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="11037-1946">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-1946">EU Driver's License Number</span></span>

<span data-ttu-id="11037-1947">詳細については、「 [EU ドライバーのライセンス番号の機密情報の種類](eu-driver-s-license-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11037-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="11037-1948">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-1948">EU National Identification Number</span></span>

<span data-ttu-id="11037-1949">詳細については、「 [EU 国立 Id 番号の機密情報の種類](eu-national-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11037-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="11037-1950">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-1950">EU Passport Number</span></span>

<span data-ttu-id="11037-1951">詳細については、「 [EU パスポート番号の機密情報の種類](eu-passport-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11037-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="11037-1952">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="11037-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="11037-1953">詳細については、「 [EU 社会保障番号または同等の ID の機密情報の種類](eu-social-security-number-or-equivalent-id.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11037-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="11037-1954">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="11037-1955">詳細については、「 [EU 税務識別番号の機密情報の種類](eu-tax-identification-number.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11037-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="11037-1956">フィンランドの国民 ID</span><span class="sxs-lookup"><span data-stu-id="11037-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="11037-1957">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1957">Format</span></span>

<span data-ttu-id="11037-1958">6 桁の数字、世紀を表す 1 桁の文字、3 桁の数字、1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="11037-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1959">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1959">Pattern</span></span>

<span data-ttu-id="11037-1960">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="11037-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="11037-1961">DDMMYY という形式の誕生日を示す 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="11037-1962">世紀マーカー (「-」、「+」、または「a」)</span><span class="sxs-lookup"><span data-stu-id="11037-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="11037-1963">3 桁の個人識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="11037-1964">チェック ディジットとして機能する 1 桁の数字または文字 (大文字小文字の区別あり)</span><span class="sxs-lookup"><span data-stu-id="11037-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1965">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1965">Checksum</span></span>

<span data-ttu-id="11037-1966">はい</span><span class="sxs-lookup"><span data-stu-id="11037-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1967">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1967">Definition</span></span>

<span data-ttu-id="11037-1968">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1969">関数 Func_finnish_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1970">Keyword_finnish_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="11037-1971">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-1972">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1972">Keywords</span></span>

- <span data-ttu-id="11037-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="11037-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="11037-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="11037-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="11037-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="11037-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="11037-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="11037-1976">Personbeteckning</span></span>
- <span data-ttu-id="11037-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="11037-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="11037-1978">フィンランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-1978">Finland Passport Number</span></span>

<span data-ttu-id="11037-1979">次の9つの文字と数字のパターンの組み合わせを書式設定します。9桁の文字 (大文字小文字を区別しない)、7桁のチェックサムを定義しません。 DLP ポリシーは 75% で、この種類の機密情報がある場合に、300文字の近接性: 正規表現 Regex_finland_passport_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-1980">Keyword_finland_passport_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="11037-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="11037-1981"></span></span>
<span data-ttu-id="11037-1982">キーワード Keyword_finland_passport_number Passport Passi</span><span class="sxs-lookup"><span data-stu-id="11037-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="11037-1983">フランスの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-1984">Format</span><span class="sxs-lookup"><span data-stu-id="11037-1984">Format</span></span>

<span data-ttu-id="11037-1985">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-1986">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-1986">Pattern</span></span>

<span data-ttu-id="11037-1987">フランスの電話番号などの同様のパターンと区別するための検証付きの 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-1988">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-1988">Checksum</span></span>

<span data-ttu-id="11037-1989">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-1990">定義</span><span class="sxs-lookup"><span data-stu-id="11037-1990">Definition</span></span>

<span data-ttu-id="11037-1991">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-1992">関数 Func_french_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-1993">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="11037-1994">Keyword_french_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="11037-1995">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-1996">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="11037-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="11037-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="11037-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="11037-1998">drivers licence</span></span>
- <span data-ttu-id="11037-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="11037-1999">drivers license</span></span>
- <span data-ttu-id="11037-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="11037-2000">driving licence</span></span>
- <span data-ttu-id="11037-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="11037-2001">driving license</span></span>
- <span data-ttu-id="11037-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="11037-2002">permis de conduire</span></span>
- <span data-ttu-id="11037-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="11037-2003">licence number</span></span>
- <span data-ttu-id="11037-2004">license number</span><span class="sxs-lookup"><span data-stu-id="11037-2004">license number</span></span>
- <span data-ttu-id="11037-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="11037-2005">licence numbers</span></span>
- <span data-ttu-id="11037-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="11037-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="11037-2007">フランスの国民識別カード (CNI)</span><span class="sxs-lookup"><span data-stu-id="11037-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2008">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2008">Format</span></span>

<span data-ttu-id="11037-2009">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2010">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2010">Pattern</span></span>

<span data-ttu-id="11037-2011">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2012">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2012">Checksum</span></span>

<span data-ttu-id="11037-2013">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2014">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2014">Definition</span></span>

<span data-ttu-id="11037-2015">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2016">正規表現 Regex_france_cni がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2017">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2017">Keywords</span></span>

<span data-ttu-id="11037-2018">None</span><span class="sxs-lookup"><span data-stu-id="11037-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="11037-2019">フランスのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2020">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2020">Format</span></span>

<span data-ttu-id="11037-2021">9 桁の数字と文字</span><span class="sxs-lookup"><span data-stu-id="11037-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2022">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2022">Pattern</span></span>

<span data-ttu-id="11037-2023">9 つの数字と文字:</span><span class="sxs-lookup"><span data-stu-id="11037-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="11037-2024">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2024">Two digits</span></span> 
- <span data-ttu-id="11037-2025">2 つの文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2026">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2027">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2027">Checksum</span></span>

<span data-ttu-id="11037-2028">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2029">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2029">Definition</span></span>

<span data-ttu-id="11037-2030">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2031">関数 Func_fr_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2032">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2033">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="11037-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="11037-2034">Keyword_passport</span></span>

- <span data-ttu-id="11037-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="11037-2035">Passport Number</span></span>
- <span data-ttu-id="11037-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="11037-2036">Passport No</span></span>
- <span data-ttu-id="11037-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="11037-2037">Passport #</span></span>
- <span data-ttu-id="11037-2038">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="11037-2038">Passport#</span></span>
- <span data-ttu-id="11037-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="11037-2039">PassportID</span></span>
- <span data-ttu-id="11037-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="11037-2040">Passportno</span></span>
- <span data-ttu-id="11037-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="11037-2041">passportnumber</span></span>
- <span data-ttu-id="11037-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="11037-2042">パスポート</span></span>
- <span data-ttu-id="11037-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-2043">パスポート番号</span></span>
- <span data-ttu-id="11037-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="11037-2044">パスポートのNum</span></span>
- <span data-ttu-id="11037-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="11037-2045">パスポート ＃</span></span> 
- <span data-ttu-id="11037-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="11037-2046">Numéro de passeport</span></span>
- <span data-ttu-id="11037-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="11037-2047">Passeport n °</span></span>
- <span data-ttu-id="11037-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="11037-2048">Passeport Non</span></span>
- <span data-ttu-id="11037-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="11037-2049">Passeport #</span></span>
- <span data-ttu-id="11037-2050">Passeport#</span><span class="sxs-lookup"><span data-stu-id="11037-2050">Passeport#</span></span>
- <span data-ttu-id="11037-2051">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="11037-2051">PasseportNon</span></span>
- <span data-ttu-id="11037-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="11037-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="11037-2053">フランスの社会保障番号 (INSEE)</span><span class="sxs-lookup"><span data-stu-id="11037-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2054">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2054">Format</span></span>

<span data-ttu-id="11037-2055">15 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2056">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2056">Pattern</span></span>

<span data-ttu-id="11037-2057">次のいずれかのパターンに一致する:</span><span class="sxs-lookup"><span data-stu-id="11037-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="11037-2058">13桁の数字の後にスペースを続け、2桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="11037-2059">または</span><span class="sxs-lookup"><span data-stu-id="11037-2059">or</span></span>
- <span data-ttu-id="11037-2060">15 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2061">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2061">Checksum</span></span>

<span data-ttu-id="11037-2062">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2063">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2063">Definition</span></span>

<span data-ttu-id="11037-2064">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2065">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2066">Keyword_fr_insee のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="11037-2067">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2067">The checksum passes.</span></span>

<span data-ttu-id="11037-2068">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2069">関数 Func_french_insee または Func_fr_insee は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2070">Keyword_fr_insee のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="11037-2071">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2071">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2072">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="11037-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="11037-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="11037-2074">insee</span><span class="sxs-lookup"><span data-stu-id="11037-2074">insee</span></span>
- <span data-ttu-id="11037-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="11037-2075">securité sociale</span></span>
- <span data-ttu-id="11037-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="11037-2076">securite sociale</span></span>
- <span data-ttu-id="11037-2077">national id</span><span class="sxs-lookup"><span data-stu-id="11037-2077">national id</span></span>
- <span data-ttu-id="11037-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="11037-2078">national identification</span></span>
- <span data-ttu-id="11037-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="11037-2079">numéro d'identité</span></span>
- <span data-ttu-id="11037-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="11037-2080">no d'identité</span></span>
- <span data-ttu-id="11037-2081">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-2081">no.</span></span> <span data-ttu-id="11037-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="11037-2082">d'identité</span></span>
- <span data-ttu-id="11037-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="11037-2083">numero d'identite</span></span>
- <span data-ttu-id="11037-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="11037-2084">no d'identite</span></span>
- <span data-ttu-id="11037-2085">違います。</span><span class="sxs-lookup"><span data-stu-id="11037-2085">no.</span></span> <span data-ttu-id="11037-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="11037-2086">d'identite</span></span>
- <span data-ttu-id="11037-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="11037-2087">social security number</span></span>
- <span data-ttu-id="11037-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="11037-2088">social security code</span></span>
- <span data-ttu-id="11037-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="11037-2089">social insurance number</span></span>
- <span data-ttu-id="11037-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="11037-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="11037-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="11037-2091">d'identité nationale</span></span>
- <span data-ttu-id="11037-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="11037-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="11037-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="11037-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="11037-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="11037-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="11037-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="11037-2095">numéro de sécu</span></span>
- <span data-ttu-id="11037-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="11037-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="11037-2097">ドイツの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2098">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2098">Format</span></span>

<span data-ttu-id="11037-2099">11 桁の数字と文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2100">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2100">Pattern</span></span>

<span data-ttu-id="11037-2101">11 個の数字と文字 (大文字小文字を区別しない):</span><span class="sxs-lookup"><span data-stu-id="11037-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="11037-2102">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="11037-2102">A digit or letter</span></span> 
- <span data-ttu-id="11037-2103">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2103">Two digits</span></span> 
- <span data-ttu-id="11037-2104">6 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="11037-2104">Six digits or letters</span></span> 
- <span data-ttu-id="11037-2105">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2105">A digit</span></span> 
- <span data-ttu-id="11037-2106">1 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="11037-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2107">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2107">Checksum</span></span>

<span data-ttu-id="11037-2108">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2109">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2109">Definition</span></span>

<span data-ttu-id="11037-2110">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2111">関数 Func_german_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2112">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="11037-2113">Keyword_german_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="11037-2114">Keyword_german_drivers_license_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="11037-2115">Keyword_german_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="11037-2116">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2116">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2117">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="11037-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="11037-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="11037-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2119">Führerschein</span></span>
- <span data-ttu-id="11037-2120">Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2120">Fuhrerschein</span></span>
- <span data-ttu-id="11037-2121">Futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="11037-2121">Fuehrerschein</span></span>
- <span data-ttu-id="11037-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="11037-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="11037-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="11037-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="11037-2125">Führerschein-</span></span> 
- <span data-ttu-id="11037-2126">Futex (中)</span><span class="sxs-lookup"><span data-stu-id="11037-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="11037-2127">Futex の ehのリリース</span><span class="sxs-lookup"><span data-stu-id="11037-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="11037-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="11037-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="11037-2129">Futex がある Hていません Einnumnr</span><span class="sxs-lookup"><span data-stu-id="11037-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="11037-2130">Futex の Ehの再リリース/Einnumnr</span><span class="sxs-lookup"><span data-stu-id="11037-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="11037-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="11037-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="11037-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="11037-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="11037-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="11037-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="11037-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="11037-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="11037-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="11037-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="11037-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="11037-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="11037-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="11037-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="11037-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="11037-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="11037-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="11037-2141">Futex がある Hていません Einnumnr</span><span class="sxs-lookup"><span data-stu-id="11037-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="11037-2142">Futex の Ehの再リリース/Einnumnr</span><span class="sxs-lookup"><span data-stu-id="11037-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="11037-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="11037-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="11037-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="11037-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="11037-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="11037-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="11037-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="11037-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="11037-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="11037-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="11037-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="11037-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="11037-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="11037-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="11037-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="11037-2152">DL</span><span class="sxs-lookup"><span data-stu-id="11037-2152">DL</span></span> 
- <span data-ttu-id="11037-2153">DL</span><span class="sxs-lookup"><span data-stu-id="11037-2153">DLS</span></span>
- <span data-ttu-id="11037-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="11037-2154">Driv Lic</span></span> 
- <span data-ttu-id="11037-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="11037-2155">Driv Licen</span></span> 
- <span data-ttu-id="11037-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="11037-2156">Driv License</span></span>
- <span data-ttu-id="11037-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2157">Driv Licenses</span></span> 
- <span data-ttu-id="11037-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="11037-2158">Driv Licence</span></span> 
- <span data-ttu-id="11037-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="11037-2159">Driv Licences</span></span> 
- <span data-ttu-id="11037-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="11037-2160">Driv Lic</span></span> 
- <span data-ttu-id="11037-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="11037-2161">Driver Licen</span></span> 
- <span data-ttu-id="11037-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="11037-2162">Driver License</span></span> 
- <span data-ttu-id="11037-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2163">Driver Licenses</span></span> 
- <span data-ttu-id="11037-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="11037-2164">Driver Licence</span></span> 
- <span data-ttu-id="11037-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="11037-2165">Driver Licences</span></span> 
- <span data-ttu-id="11037-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="11037-2166">Drivers Lic</span></span> 
- <span data-ttu-id="11037-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="11037-2167">Drivers Licen</span></span> 
- <span data-ttu-id="11037-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="11037-2168">Drivers License</span></span> 
- <span data-ttu-id="11037-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="11037-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="11037-2170">Drivers Licence</span></span> 
- <span data-ttu-id="11037-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="11037-2171">Drivers Licences</span></span> 
- <span data-ttu-id="11037-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="11037-2172">Driver's Lic</span></span> 
- <span data-ttu-id="11037-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="11037-2173">Driver's Licen</span></span> 
- <span data-ttu-id="11037-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="11037-2174">Driver's License</span></span> 
- <span data-ttu-id="11037-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="11037-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="11037-2176">Driver's Licence</span></span> 
- <span data-ttu-id="11037-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="11037-2177">Driver's Licences</span></span> 
- <span data-ttu-id="11037-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="11037-2178">Driving Lic</span></span> 
- <span data-ttu-id="11037-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="11037-2179">Driving Licen</span></span> 
- <span data-ttu-id="11037-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="11037-2180">Driving License</span></span> 
- <span data-ttu-id="11037-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2181">Driving Licenses</span></span> 
- <span data-ttu-id="11037-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="11037-2182">Driving Licence</span></span> 
- <span data-ttu-id="11037-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="11037-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="11037-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="11037-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="11037-2185">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="11037-2186">Nr-Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="11037-2187">"Nr" という Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="11037-2188">Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2188">No-Führerschein</span></span> 
- <span data-ttu-id="11037-2189">(Futex なし)</span><span class="sxs-lookup"><span data-stu-id="11037-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="11037-2190">その他の Ehの場合</span><span class="sxs-lookup"><span data-stu-id="11037-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="11037-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2191">N-Führerschein</span></span> 
- <span data-ttu-id="11037-2192">N の Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="11037-2193">N 桁の Ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="11037-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="11037-2194">Nr-Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="11037-2195">Nr-Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="11037-2196">"Nr" という Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="11037-2197">Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2197">No-Führerschein</span></span> 
- <span data-ttu-id="11037-2198">(Futex なし)</span><span class="sxs-lookup"><span data-stu-id="11037-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="11037-2199">その他の Ehの場合</span><span class="sxs-lookup"><span data-stu-id="11037-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="11037-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="11037-2200">N-Führerschein</span></span> 
- <span data-ttu-id="11037-2201">N の Futex</span><span class="sxs-lookup"><span data-stu-id="11037-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="11037-2202">N 桁の Ehた ehのリリース</span><span class="sxs-lookup"><span data-stu-id="11037-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="11037-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="11037-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="11037-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="11037-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="11037-2205">ausstellungsort</span></span>
- <span data-ttu-id="11037-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="11037-2206">ausstellende behöde</span></span>
- <span data-ttu-id="11037-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="11037-2207">ausstellende behorde</span></span>
- <span data-ttu-id="11037-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="11037-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="11037-2209">ドイツのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2210">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2210">Format</span></span>

<span data-ttu-id="11037-2211">10 桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="11037-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2212">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2212">Pattern</span></span>

<span data-ttu-id="11037-2213">パターンには、以下のすべてが含まれる必要があります。</span><span class="sxs-lookup"><span data-stu-id="11037-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="11037-2214">最初の文字は 1 桁の数字、またはこのセット (C、F、G、H、J、K) からの 1 文字</span><span class="sxs-lookup"><span data-stu-id="11037-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="11037-2215">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2215">Three digits</span></span> 
- <span data-ttu-id="11037-2216">数字またはこの文字セット (C、H、J から N、P、R、T、V から Z) から 5 個</span><span class="sxs-lookup"><span data-stu-id="11037-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="11037-2217">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2218">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2218">Checksum</span></span>

<span data-ttu-id="11037-2219">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2220">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2220">Definition</span></span>

<span data-ttu-id="11037-2221">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2222">関数 Func_german_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2223">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="11037-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="11037-2224">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2224">The checksum passes.</span></span>

<span data-ttu-id="11037-2225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2226">関数 Func_german_passport_data がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2227">5 つのキーワード リストのうちいずれかのキーワードを検索した。</span><span class="sxs-lookup"><span data-stu-id="11037-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="11037-2228">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2228">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2229">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="11037-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="11037-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="11037-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="11037-2231">reisepass</span></span>
- <span data-ttu-id="11037-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="11037-2232">reisepasse</span></span>
- <span data-ttu-id="11037-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2233">reisepassnummer</span></span>
- <span data-ttu-id="11037-2234">サインアウト</span><span class="sxs-lookup"><span data-stu-id="11037-2234">passport</span></span>
- <span data-ttu-id="11037-2235">passport</span><span class="sxs-lookup"><span data-stu-id="11037-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="11037-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="11037-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="11037-2237">ge気流 tsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-2237">geburtsdatum</span></span>
- <span data-ttu-id="11037-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="11037-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="11037-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="11037-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="11037-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="11037-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="11037-2241">Reisepass Nr-Reisepass</span><span class="sxs-lookup"><span data-stu-id="11037-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="11037-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="11037-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="11037-2243">Reisepass-Nr</span><span class="sxs-lookup"><span data-stu-id="11037-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="11037-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="11037-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="11037-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="11037-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="11037-2246">ドイツの身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="11037-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2247">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2247">Format</span></span>

<span data-ttu-id="11037-2248">2010年11月1日以降: 9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="11037-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="11037-2249">1987年4月1日から2010年10月31日まで:10 桁</span><span class="sxs-lookup"><span data-stu-id="11037-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2250">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2250">Pattern</span></span>

<span data-ttu-id="11037-2251">2010 年 11 月 1 日以降:</span><span class="sxs-lookup"><span data-stu-id="11037-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="11037-2252">1 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2253">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2253">Eight digits</span></span>

<span data-ttu-id="11037-2254">1987年4月1日から2010年10月31日まで。</span><span class="sxs-lookup"><span data-stu-id="11037-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="11037-2255">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2256">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2256">Checksum</span></span>

<span data-ttu-id="11037-2257">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2258">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2258">Definition</span></span>

<span data-ttu-id="11037-2259">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2260">正規表現 Regex_germany_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2261">Keyword_germany_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2262">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="11037-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="11037-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="11037-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="11037-2264">Identity Card</span></span>
- <span data-ttu-id="11037-2265">ID</span><span class="sxs-lookup"><span data-stu-id="11037-2265">ID</span></span>
- <span data-ttu-id="11037-2266">Fim</span><span class="sxs-lookup"><span data-stu-id="11037-2266">Identification</span></span>
- <span data-ttu-id="11037-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="11037-2267">Personalausweis</span></span>
- <span data-ttu-id="11037-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="11037-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="11037-2269">Ausweis</span></span>
- <span data-ttu-id="11037-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="11037-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="11037-2271">ギリシャの国民識別カード</span><span class="sxs-lookup"><span data-stu-id="11037-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="11037-2272">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2272">Format</span></span>

<span data-ttu-id="11037-2273">7 ～ 8 桁の文字と数字の組み合わせとハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="11037-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2274">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2274">Pattern</span></span>

<span data-ttu-id="11037-2275">7 桁の文字と数字 (従来の形式):</span><span class="sxs-lookup"><span data-stu-id="11037-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="11037-2276">1 桁の文字 (ギリシャ語のアルファベット文字) </span><span class="sxs-lookup"><span data-stu-id="11037-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="11037-2277">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-2277">A dash</span></span> 
- <span data-ttu-id="11037-2278">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2278">Six digits</span></span>

<span data-ttu-id="11037-2279">8 桁の文字と数字 (現在の形式):</span><span class="sxs-lookup"><span data-stu-id="11037-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="11037-2280">ギリシャ語にもラテン語にも大文字がある文字 (ABEZHIKMNOPTYX) を使用した 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="11037-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="11037-2281">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-2281">A dash</span></span> 
- <span data-ttu-id="11037-2282">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2283">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2283">Checksum</span></span>

<span data-ttu-id="11037-2284">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2285">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2285">Definition</span></span>

<span data-ttu-id="11037-2286">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2287">正規表現 Regex_greece_id_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2288">Keyword_greece_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2289">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="11037-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="11037-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="11037-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="11037-2291">Greek identity Card</span></span>
- <span data-ttu-id="11037-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="11037-2292">Tautotita</span></span>
- <span data-ttu-id="11037-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="11037-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="11037-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="11037-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="11037-2295">香港の ID カード (HKID) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2296">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2296">Format</span></span>

<span data-ttu-id="11037-2297">8 ～ 9 桁の文字と数字の組み合わせ、最後の文字はかっこで囲むことも可能</span><span class="sxs-lookup"><span data-stu-id="11037-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2298">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2298">Pattern</span></span>

<span data-ttu-id="11037-2299">8 ～ 9 桁の文字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="11037-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="11037-2300">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2301">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2301">Six digits</span></span> 
- <span data-ttu-id="11037-2302">チェック ディジットとして機能する最後の文字 (任意の数字か文字 A) はかっこで囲むことも可能。</span><span class="sxs-lookup"><span data-stu-id="11037-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2303">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2303">Checksum</span></span>

<span data-ttu-id="11037-2304">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2305">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2305">Definition</span></span>

<span data-ttu-id="11037-2306">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2307">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2308">Keyword_hong_kong_id_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="11037-2309">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2309">The checksum passes.</span></span>

<span data-ttu-id="11037-2310">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2311">関数 Func_hong_kong_id_card は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2312">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2312">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2313">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="11037-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="11037-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="11037-2315">香港の id カード</span><span class="sxs-lookup"><span data-stu-id="11037-2315">hong kong identity card</span></span>
- <span data-ttu-id="11037-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="11037-2316">HKIDC</span></span>
- <span data-ttu-id="11037-2317">id card</span><span class="sxs-lookup"><span data-stu-id="11037-2317">id card</span></span>
- <span data-ttu-id="11037-2318">Identity card</span><span class="sxs-lookup"><span data-stu-id="11037-2318">identity card</span></span>
- <span data-ttu-id="11037-2319">hk の id カード</span><span class="sxs-lookup"><span data-stu-id="11037-2319">hk identity card</span></span>
- <span data-ttu-id="11037-2320">香港特別行政 id</span><span class="sxs-lookup"><span data-stu-id="11037-2320">hong kong id</span></span>
- <span data-ttu-id="11037-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2321">香港身份證</span></span>
- <span data-ttu-id="11037-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="11037-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2323">身份證</span></span>
- <span data-ttu-id="11037-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2324">身份証</span></span>
- <span data-ttu-id="11037-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2325">身分證</span></span>
- <span data-ttu-id="11037-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2326">身分証</span></span>
- <span data-ttu-id="11037-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2327">香港身份証</span></span>
- <span data-ttu-id="11037-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2328">香港身分證</span></span>
- <span data-ttu-id="11037-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2329">香港身分証</span></span>
- <span data-ttu-id="11037-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2330">香港身份證</span></span>
- <span data-ttu-id="11037-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2331">香港居民身份證</span></span>
- <span data-ttu-id="11037-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2332">香港居民身份証</span></span>
- <span data-ttu-id="11037-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2333">香港居民身分證</span></span>
- <span data-ttu-id="11037-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2334">香港居民身分証</span></span>
- <span data-ttu-id="11037-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="11037-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="11037-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="11037-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="11037-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="11037-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="11037-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="11037-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="11037-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="11037-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="11037-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="11037-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="11037-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="11037-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="11037-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="11037-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="11037-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="11037-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="11037-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="11037-2351">インドの永久口座番号 (PAN)</span><span class="sxs-lookup"><span data-stu-id="11037-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2352">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2352">Format</span></span>

<span data-ttu-id="11037-2353">10 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="11037-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2354">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2354">Pattern</span></span>

<span data-ttu-id="11037-2355">10 桁の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2355">10 letters or digits:</span></span>
- <span data-ttu-id="11037-2356">5 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2357">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2357">Four digits</span></span> 
- <span data-ttu-id="11037-2358">チェック ディジットとして機能する 1 桁のアルファベット文字</span><span class="sxs-lookup"><span data-stu-id="11037-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2359">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2359">Checksum</span></span>

<span data-ttu-id="11037-2360">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2361">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2361">Definition</span></span>

<span data-ttu-id="11037-2362">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2363">正規表現 Regex_india_permanent_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2364">Keyword_india_permanent_account_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="11037-2365">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2366">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="11037-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="11037-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="11037-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="11037-2369">ペン</span><span class="sxs-lookup"><span data-stu-id="11037-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="11037-2370">インドの固有識別 (Aadhaar) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2371">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2371">Format</span></span>

<span data-ttu-id="11037-2372">省略可能なスペースまたはハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2373">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2373">Pattern</span></span>

<span data-ttu-id="11037-2374">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2374">12 digits:</span></span>
- <span data-ttu-id="11037-2375">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2375">Four digits</span></span> 
- <span data-ttu-id="11037-2376">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="11037-2376">An optional space or dash</span></span> 
- <span data-ttu-id="11037-2377">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2377">Four digits</span></span> 
- <span data-ttu-id="11037-2378">スペースまたはハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="11037-2378">An optional space or dash</span></span> 
- <span data-ttu-id="11037-2379">最後の数字はチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="11037-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2380">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2380">Checksum</span></span>

<span data-ttu-id="11037-2381">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2382">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2382">Definition</span></span>

<span data-ttu-id="11037-2383">DLP ポリシーは 85% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-2384">Keyword_india_aadhar からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="11037-2385">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2385">The checksum passes.</span></span>
<span data-ttu-id="11037-2386">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_india_aadhaar は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-2387">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>

### Keywords
   
#### Keyword_india_aadhar
- Aadhar
- Aadhaar
- UID
- आधार
   
## Indonesia Identity Card (KTP) Number

### Format

16 digits containing optional periods

### Pattern

16 digits:
- Two-digit province code 
- A period (optional) 
- Two-digit regency or city code 
- Two-digit subdistrict code 
- A period (optional) 
- Six digits in the format DDMMYY which are the date of birth 
- A period (optional) 
- Four digits

### Checksum

No

### Definition

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.
- A keyword from Keyword_indonesia_id_card is found.

A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The regular expression Regex_indonesia_id_card finds content that matches the pattern.

```
<!-- Indonesia Identity Card (KTP) Number -->
<span data-ttu-id="11037-2388"><Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300"> <Pattern confidenceLevel="85"> <IdMatch idRef="Regex_indonesia_id_card"/> <Match idRef="Keyword_indonesia_id_card"/> </Pattern> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_indonesia_id_card"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="11037-2388"></span></span>
```

### Keywords
   
#### Keyword_indonesia_id_card

- KTP
- Kartu Tanda Penduduk 
- Nomor Induk Kependudukan 
   
## International Banking Account Number (IBAN)

### Format

Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)

### Pattern

Pattern must include all of the following:

- Two-letter country code
- Two check digits (followed by an optional space) 
- 1-7 groups of four letters or digits (can be separated by spaces)
- 1-3 letters or digits

The format for each country is slightly different. The IBAN sensitive information type covers these 60 countries:

ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg

### Checksum

Yes

### Definition

A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:
- The function Func_iban finds content that matches the pattern.
- The checksum passes.

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2389">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2389">Keywords</span></span>

<span data-ttu-id="11037-2390">None</span><span class="sxs-lookup"><span data-stu-id="11037-2390">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="11037-2391">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="11037-2391">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="11037-2392">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2392">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="11037-2393">IPv4</span><span class="sxs-lookup"><span data-stu-id="11037-2393">IPv4:</span></span>
<span data-ttu-id="11037-2394">書式設定あり (ピリオド付き) または書式設定なし (ピリオドなし) のIPv4 アドレスを表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="11037-2394">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="11037-2395">IPv6</span><span class="sxs-lookup"><span data-stu-id="11037-2395">IPv6:</span></span>
<span data-ttu-id="11037-2396"> 書式設定あり (コロン付き) の IPv6 番号を表す複雑なパターン</span><span class="sxs-lookup"><span data-stu-id="11037-2396">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2397">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2397">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2398">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2398">Checksum</span></span>

<span data-ttu-id="11037-2399">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2399">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2400">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2400">Definition</span></span>

<span data-ttu-id="11037-2401">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2401">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2402">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2402">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2403">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-2403">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="11037-2404">IPv4 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2404">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2405">正規表現 Regex_ipv4_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2405">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2406">Keyword_ipaddress のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2406">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="11037-2407">IPv6 の場合、DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、95% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2407">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2408">正規表現 Regex_ipv6_address がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2408">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2409">Keyword_ipaddress のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-2409">No keyword from Keyword_ipaddress is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2410">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2410">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="11037-2411">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="11037-2411">Keyword_ipaddress</span></span>

- <span data-ttu-id="11037-2412">IP (このキーワードでは大文字と小文字が区別されます)</span><span class="sxs-lookup"><span data-stu-id="11037-2412">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="11037-2413">ip address</span><span class="sxs-lookup"><span data-stu-id="11037-2413">ip address</span></span> 
- <span data-ttu-id="11037-2414">ip addresses</span><span class="sxs-lookup"><span data-stu-id="11037-2414">ip addresses</span></span>
- <span data-ttu-id="11037-2415">internet protocol</span><span class="sxs-lookup"><span data-stu-id="11037-2415">internet protocol</span></span>
- <span data-ttu-id="11037-2416">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="11037-2416">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="11037-2417">Diseases の国際分類 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="11037-2417">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2418">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2418">Format</span></span>

<span data-ttu-id="11037-2419">Dictionary</span><span class="sxs-lookup"><span data-stu-id="11037-2419">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2420">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2420">Pattern</span></span>

<span data-ttu-id="11037-2421">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2421">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2422">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2422">Checksum</span></span>

<span data-ttu-id="11037-2423">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2423">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2424">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2424">Definition</span></span>

<span data-ttu-id="11037-2425">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2425">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2426">Dictionary_icd_10_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2426">A keyword from Dictionary_icd_10_cm is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_cm" />
        </Pattern>
      </Entity>
```

<span data-ttu-id="11037-2427">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2427">Keywords</span></span>

<span data-ttu-id="11037-2428">Dictionary_icd_10_cm キーワードディクショナリの用語。 [Diseases、10リビジョン、臨床修正 (icd-10-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852604)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="11037-2428">Any term from the Dictionary_icd_10_cm keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="11037-2429">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="11037-2429">This type looks only for the term, not the insurance codes.</span></span>

   
## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="11037-2430">Diseases の国際分類 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="11037-2430">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2431">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2431">Format</span></span>

<span data-ttu-id="11037-2432">Dictionary</span><span class="sxs-lookup"><span data-stu-id="11037-2432">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2433">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2433">Pattern</span></span>

<span data-ttu-id="11037-2434">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2434">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2435">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2435">Checksum</span></span>

<span data-ttu-id="11037-2436">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2436">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2437">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2437">Definition</span></span>

<span data-ttu-id="11037-2438">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2438">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2439">Dictionary_icd_9_cm からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2439">A keyword from Dictionary_icd_9_cm is found.</span></span>

```xml
      <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_cm" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2440">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2440">Keywords</span></span>

<span data-ttu-id="11037-2441">Dictionary_icd_9_cm キーワードディクショナリの用語。 [Diseases、9リビジョン、臨床修正 (icd-9-cm) の国際分類](https://go.microsoft.com/fwlink/?linkid=852605)に基づいています。</span><span class="sxs-lookup"><span data-stu-id="11037-2441">Any term from the Dictionary_icd_9_cm keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="11037-2442">この型は、保険コードではなく、用語に対してのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="11037-2442">This type looks only for the term, not the insurance codes.</span></span>
   
## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="11037-2443">アイルランドの個人公共サービス (PPS) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-2443">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2444">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2444">Format</span></span>

<span data-ttu-id="11037-2445">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="11037-2445">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="11037-2446">7 桁の数字の後に 1 ～ 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="11037-2446">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="11037-2447">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="11037-2447">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="11037-2448">7 桁の数字の後に 2 桁の文字</span><span class="sxs-lookup"><span data-stu-id="11037-2448">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2449">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2449">Pattern</span></span>

<span data-ttu-id="11037-2450">古い形式 (2012 年12月31日まで):</span><span class="sxs-lookup"><span data-stu-id="11037-2450">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="11037-2451">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2451">Seven digits</span></span> 
- <span data-ttu-id="11037-2452">1 ～ 2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2452">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="11037-2453">新しい形式 (1 Jan 2013 以降):</span><span class="sxs-lookup"><span data-stu-id="11037-2453">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="11037-2454">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2454">Seven digits</span></span> 
- <span data-ttu-id="11037-2455">チェック ディジットとして機能する 1 桁のアルファベット文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2455">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="11037-2456">文字「A」または「H」 (大文字小文字の区別なし)</span><span class="sxs-lookup"><span data-stu-id="11037-2456">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2457">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2457">Checksum</span></span>

<span data-ttu-id="11037-2458">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2458">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2459">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2459">Definition</span></span>

<span data-ttu-id="11037-2460">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2461">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2461">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2462">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-2462">One of the following is true:</span></span>
    - <span data-ttu-id="11037-2463">Keyword_ireland_pps からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2463">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="11037-2464">関数 Func_eu_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2464">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-2465">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2465">The checksum passes.</span></span>

<span data-ttu-id="11037-2466">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2466">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2467">関数 Func_ireland_pps は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2467">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2468">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2468">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2469">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2469">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="11037-2470">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="11037-2470">Keyword_ireland_pps</span></span>

- <span data-ttu-id="11037-2471">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="11037-2471">Personal Public Service Number</span></span> 
- <span data-ttu-id="11037-2472">PPS Number</span><span class="sxs-lookup"><span data-stu-id="11037-2472">PPS Number</span></span> 
- <span data-ttu-id="11037-2473">PPS Num</span><span class="sxs-lookup"><span data-stu-id="11037-2473">PPS Num</span></span> 
- <span data-ttu-id="11037-2474">PPS No.</span><span class="sxs-lookup"><span data-stu-id="11037-2474">PPS No.</span></span> 
- <span data-ttu-id="11037-2475">PPS #</span><span class="sxs-lookup"><span data-stu-id="11037-2475">PPS #</span></span> 
- <span data-ttu-id="11037-2476">PPS#</span><span class="sxs-lookup"><span data-stu-id="11037-2476">PPS#</span></span> 
- <span data-ttu-id="11037-2477">PPSN</span><span class="sxs-lookup"><span data-stu-id="11037-2477">PPSN</span></span> 
- <span data-ttu-id="11037-2478">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="11037-2478">Public Services Card</span></span> 
- <span data-ttu-id="11037-2479">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="11037-2479">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="11037-2480">Uimh.</span><span class="sxs-lookup"><span data-stu-id="11037-2480">Uimh.</span></span> <span data-ttu-id="11037-2481">PSP</span><span class="sxs-lookup"><span data-stu-id="11037-2481">PSP</span></span> 
- <span data-ttu-id="11037-2482">PSP</span><span class="sxs-lookup"><span data-stu-id="11037-2482">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="11037-2483">イスラエルの銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2483">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2484">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2484">Format</span></span>

<span data-ttu-id="11037-2485">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2485">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2486">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2486">Pattern</span></span>

<span data-ttu-id="11037-2487">さ</span><span class="sxs-lookup"><span data-stu-id="11037-2487">Formatted:</span></span>
- <span data-ttu-id="11037-2488">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2488">Two digits</span></span> 
- <span data-ttu-id="11037-2489">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-2489">A dash</span></span> 
- <span data-ttu-id="11037-2490">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2490">Three digits</span></span> 
- <span data-ttu-id="11037-2491">ダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-2491">A dash</span></span> 
- <span data-ttu-id="11037-2492">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2492">Eight digits</span></span>

<span data-ttu-id="11037-2493">なし</span><span class="sxs-lookup"><span data-stu-id="11037-2493">Unformatted:</span></span>
- <span data-ttu-id="11037-2494">	13 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2494">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2495">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2495">Checksum</span></span>

<span data-ttu-id="11037-2496">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2496">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2497">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2497">Definition</span></span>

<span data-ttu-id="11037-2498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2499">正規表現 Regex_israel_bank_account_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2499">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2500">Keyword_israel_bank_account_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2500">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2501">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2501">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="11037-2502">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="11037-2502">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="11037-2503">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2503">Bank Account Number</span></span> 
- <span data-ttu-id="11037-2504">Bank Account</span><span class="sxs-lookup"><span data-stu-id="11037-2504">Bank Account</span></span> 
- <span data-ttu-id="11037-2505">Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2505">Account Number</span></span> 
- <span data-ttu-id="11037-2506">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="11037-2506">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="11037-2507">イスラエルの国民 ID</span><span class="sxs-lookup"><span data-stu-id="11037-2507">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="11037-2508">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2508">Format</span></span>

<span data-ttu-id="11037-2509">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2509">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2510">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2510">Pattern</span></span>

<span data-ttu-id="11037-2511">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2511">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2512">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2512">Checksum</span></span>

<span data-ttu-id="11037-2513">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2513">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2514">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2514">Definition</span></span>

<span data-ttu-id="11037-2515">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2515">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2516">関数 Func_israeli_national_id_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2516">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2517">Keyword_Israel_National_ID のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2517">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="11037-2518">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2518">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2519">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2519">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="11037-2520">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="11037-2520">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="11037-2521">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="11037-2521">מספר זהות</span></span> 
- <span data-ttu-id="11037-2522">National ID Number</span><span class="sxs-lookup"><span data-stu-id="11037-2522">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="11037-2523">イタリアの運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-2523">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2524">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2524">Format</span></span>

<span data-ttu-id="11037-2525">10 桁の文字と数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-2525">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2526">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2526">Pattern</span></span>

- <span data-ttu-id="11037-2527">10 個の文字と数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="11037-2527">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="11037-2528">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-2528">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2529">文字 "A" または "V" (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-2529">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2530">7 つの文字 (大文字小文字を区別しない)、数字、またはアンダースコア文字</span><span class="sxs-lookup"><span data-stu-id="11037-2530">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="11037-2531">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-2531">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2532">Checksum</span></span>

<span data-ttu-id="11037-2533">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2533">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2534">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2534">Definition</span></span>

<span data-ttu-id="11037-2535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2536">正規表現 Regex_italy_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2536">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2537">Keyword_italy_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2537">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2538">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2538">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="11037-2539">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="11037-2539">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="11037-2540">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="11037-2540">numero di patente di guida</span></span> 
- <span data-ttu-id="11037-2541">patente di guida</span><span class="sxs-lookup"><span data-stu-id="11037-2541">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="11037-2542">日本の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2542">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2543">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2543">Format</span></span>

<span data-ttu-id="11037-2544">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2544">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2545">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2545">Pattern</span></span>

<span data-ttu-id="11037-2546">銀行口座番号:</span><span class="sxs-lookup"><span data-stu-id="11037-2546">Bank account number:</span></span>
- <span data-ttu-id="11037-2547">7 桁または 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2547">Seven or eight digits</span></span>
- <span data-ttu-id="11037-2548">銀行口座支店コード:</span><span class="sxs-lookup"><span data-stu-id="11037-2548">Bank account branch code:</span></span>
- <span data-ttu-id="11037-2549">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2549">Four digits</span></span> 
- <span data-ttu-id="11037-2550">スペースまたはダッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="11037-2550">A space or dash (optional)</span></span> 
- <span data-ttu-id="11037-2551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2551">Three digits</span></span>

<span data-ttu-id="11037-2552">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2552">Checksum</span></span>

<span data-ttu-id="11037-2553">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2553">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2554">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2554">Definition</span></span>

<span data-ttu-id="11037-2555">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2555">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2556">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2556">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2557">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2557">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="11037-2558">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-2558">One of the following is true:</span></span>
- <span data-ttu-id="11037-2559">関数 Func_jp_bank_account_branch_code がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2559">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2560">Keyword_jp_bank_branch_code のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2560">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="11037-2561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2561">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2562">関数 Func_jp_bank_account がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2562">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2563">Keyword_jp_bank_account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2563">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2564">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2564">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="11037-2565">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="11037-2565">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="11037-2566">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2566">Checking Account Number</span></span> 
- <span data-ttu-id="11037-2567">Checking Account</span><span class="sxs-lookup"><span data-stu-id="11037-2567">Checking Account</span></span> 
- <span data-ttu-id="11037-2568">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="11037-2568">Checking Account #</span></span> 
- <span data-ttu-id="11037-2569">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-2569">Checking Acct Number</span></span> 
- <span data-ttu-id="11037-2570">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-2570">Checking Acct #</span></span> 
- <span data-ttu-id="11037-2571">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-2571">Checking Acct No.</span></span> 
- <span data-ttu-id="11037-2572">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-2572">Checking Account No.</span></span> 
- <span data-ttu-id="11037-2573">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2573">Bank Account Number</span></span> 
- <span data-ttu-id="11037-2574">Bank Account</span><span class="sxs-lookup"><span data-stu-id="11037-2574">Bank Account</span></span> 
- <span data-ttu-id="11037-2575">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="11037-2575">Bank Account #</span></span> 
- <span data-ttu-id="11037-2576">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-2576">Bank Acct Number</span></span> 
- <span data-ttu-id="11037-2577">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-2577">Bank Acct #</span></span> 
- <span data-ttu-id="11037-2578">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-2578">Bank Acct No.</span></span> 
- <span data-ttu-id="11037-2579">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-2579">Bank Account No.</span></span> 
- <span data-ttu-id="11037-2580">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2580">Savings Account Number</span></span> 
- <span data-ttu-id="11037-2581">Savings Account</span><span class="sxs-lookup"><span data-stu-id="11037-2581">Savings Account</span></span> 
- <span data-ttu-id="11037-2582">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="11037-2582">Savings Account #</span></span> 
- <span data-ttu-id="11037-2583">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-2583">Savings Acct Number</span></span> 
- <span data-ttu-id="11037-2584">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-2584">Savings Acct #</span></span> 
- <span data-ttu-id="11037-2585">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-2585">Savings Acct No.</span></span> 
- <span data-ttu-id="11037-2586">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-2586">Savings Account No.</span></span> 
- <span data-ttu-id="11037-2587">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-2587">Debit Account Number</span></span> 
- <span data-ttu-id="11037-2588">Debit Account</span><span class="sxs-lookup"><span data-stu-id="11037-2588">Debit Account</span></span> 
- <span data-ttu-id="11037-2589">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="11037-2589">Debit Account #</span></span> 
- <span data-ttu-id="11037-2590">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-2590">Debit Acct Number</span></span> 
- <span data-ttu-id="11037-2591">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-2591">Debit Acct #</span></span> 
- <span data-ttu-id="11037-2592">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-2592">Debit Acct No.</span></span> 
- <span data-ttu-id="11037-2593">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-2593">Debit Account No.</span></span> 
- <span data-ttu-id="11037-2594">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="11037-2594">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="11037-2595">#アカウントの確認、勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="11037-2595">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="11037-2596">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="11037-2596">＃勘定の確認</span></span> 
- <span data-ttu-id="11037-2597">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="11037-2597">勘定番号の確認</span></span> 
- <span data-ttu-id="11037-2598">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="11037-2598">口座番号の確認</span></span> 
- <span data-ttu-id="11037-2599">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2599">銀行口座番号</span></span> 
- <span data-ttu-id="11037-2600">銀行口座</span><span class="sxs-lookup"><span data-stu-id="11037-2600">銀行口座</span></span> 
- <span data-ttu-id="11037-2601">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="11037-2601">銀行口座＃</span></span> 
- <span data-ttu-id="11037-2602">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="11037-2602">銀行の勘定番号</span></span> 
- <span data-ttu-id="11037-2603">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="11037-2603">銀行のacct＃</span></span> 
- <span data-ttu-id="11037-2604">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2604">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="11037-2605">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2605">銀行口座番号</span></span>
- <span data-ttu-id="11037-2606">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2606">普通預金口座番号</span></span> 
- <span data-ttu-id="11037-2607">預金口座</span><span class="sxs-lookup"><span data-stu-id="11037-2607">預金口座</span></span> 
- <span data-ttu-id="11037-2608">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="11037-2608">貯蓄口座＃</span></span> 
- <span data-ttu-id="11037-2609">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="11037-2609">貯蓄勘定の数</span></span> 
- <span data-ttu-id="11037-2610">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="11037-2610">貯蓄勘定＃</span></span> 
- <span data-ttu-id="11037-2611">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="11037-2611">貯蓄勘定番号</span></span> 
- <span data-ttu-id="11037-2612">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2612">普通預金口座番号</span></span> 
- <span data-ttu-id="11037-2613">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2613">引き落とし口座番号</span></span> 
- <span data-ttu-id="11037-2614">口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2614">口座番号</span></span> 
- <span data-ttu-id="11037-2615">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="11037-2615">口座番号＃</span></span> 
- <span data-ttu-id="11037-2616">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="11037-2616">デビットのacct番号</span></span> 
- <span data-ttu-id="11037-2617">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="11037-2617">デビット勘定＃</span></span> 
- <span data-ttu-id="11037-2618">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="11037-2618">デビットACCTの番号</span></span> 
- <span data-ttu-id="11037-2619">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-2619">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="11037-2620">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="11037-2620">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="11037-2621">Otemachi</span><span class="sxs-lookup"><span data-stu-id="11037-2621">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="11037-2622">日本の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-2622">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2623">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2623">Format</span></span>

<span data-ttu-id="11037-2624">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2624">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2625">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2625">Pattern</span></span>

<span data-ttu-id="11037-2626">12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2626">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2627">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2627">Checksum</span></span>

<span data-ttu-id="11037-2628">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2628">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2629">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2629">Definition</span></span>

<span data-ttu-id="11037-2630">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2630">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2631">関数 Func_jp_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2631">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2632">Keyword_jp_drivers_license_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2632">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2633">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2633">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="11037-2634">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="11037-2634">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="11037-2635">dl#</span><span class="sxs-lookup"><span data-stu-id="11037-2635">dl#</span></span> 
- <span data-ttu-id="11037-2636">DL</span><span class="sxs-lookup"><span data-stu-id="11037-2636">DL＃</span></span> 
- <span data-ttu-id="11037-2637">dl#</span><span class="sxs-lookup"><span data-stu-id="11037-2637">dls#</span></span> 
- <span data-ttu-id="11037-2638">DL</span><span class="sxs-lookup"><span data-stu-id="11037-2638">DLS＃</span></span> 
- <span data-ttu-id="11037-2639">driver license</span><span class="sxs-lookup"><span data-stu-id="11037-2639">driver license</span></span> 
- <span data-ttu-id="11037-2640">driver licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2640">driver licenses</span></span> 
- <span data-ttu-id="11037-2641">drivers license</span><span class="sxs-lookup"><span data-stu-id="11037-2641">drivers license</span></span> 
- <span data-ttu-id="11037-2642">driver's license</span><span class="sxs-lookup"><span data-stu-id="11037-2642">driver's license</span></span> 
- <span data-ttu-id="11037-2643">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2643">drivers licenses</span></span> 
- <span data-ttu-id="11037-2644">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="11037-2644">driver's licenses</span></span> 
- <span data-ttu-id="11037-2645">driving licence</span><span class="sxs-lookup"><span data-stu-id="11037-2645">driving licence</span></span> 
- <span data-ttu-id="11037-2646">そして#</span><span class="sxs-lookup"><span data-stu-id="11037-2646">lic#</span></span> 
- <span data-ttu-id="11037-2647">そして</span><span class="sxs-lookup"><span data-stu-id="11037-2647">LIC＃</span></span> 
- <span data-ttu-id="11037-2648">lics#</span><span class="sxs-lookup"><span data-stu-id="11037-2648">lics#</span></span> 
- <span data-ttu-id="11037-2649">state id</span><span class="sxs-lookup"><span data-stu-id="11037-2649">state id</span></span> 
- <span data-ttu-id="11037-2650">state identification</span><span class="sxs-lookup"><span data-stu-id="11037-2650">state identification</span></span> 
- <span data-ttu-id="11037-2651">state identification number</span><span class="sxs-lookup"><span data-stu-id="11037-2651">state identification number</span></span> 
- <span data-ttu-id="11037-2652">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="11037-2652">低所得国＃</span></span> 
- <span data-ttu-id="11037-2653">免許証</span><span class="sxs-lookup"><span data-stu-id="11037-2653">免許証</span></span> 
- <span data-ttu-id="11037-2654">状態ID</span><span class="sxs-lookup"><span data-stu-id="11037-2654">状態ID</span></span>
- <span data-ttu-id="11037-2655">状態の識別</span><span class="sxs-lookup"><span data-stu-id="11037-2655">状態の識別</span></span> 
- <span data-ttu-id="11037-2656">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-2656">状態の識別番号</span></span> 
- <span data-ttu-id="11037-2657">運転免許</span><span class="sxs-lookup"><span data-stu-id="11037-2657">運転免許</span></span> 
- <span data-ttu-id="11037-2658">運転免許証</span><span class="sxs-lookup"><span data-stu-id="11037-2658">運転免許証</span></span> 
- <span data-ttu-id="11037-2659">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-2659">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="11037-2660">日本のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-2660">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2661">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2661">Format</span></span>

<span data-ttu-id="11037-2662">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2662">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2663">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2663">Pattern</span></span>

<span data-ttu-id="11037-2664">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2664">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2665">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2665">Checksum</span></span>

<span data-ttu-id="11037-2666">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2666">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2667">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2667">Definition</span></span>

<span data-ttu-id="11037-2668">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2668">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2669">関数 Func_jp_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2669">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2670">Keyword_jp_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2670">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2671">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2671">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="11037-2672">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="11037-2672">Keyword_jp_passport</span></span>

- <span data-ttu-id="11037-2673">パスポート</span><span class="sxs-lookup"><span data-stu-id="11037-2673">パスポート</span></span> 
- <span data-ttu-id="11037-2674">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-2674">パスポート番号</span></span> 
- <span data-ttu-id="11037-2675">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="11037-2675">パスポートのNum</span></span> 
- <span data-ttu-id="11037-2676">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="11037-2676">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="11037-2677">日本の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="11037-2677">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2678">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2678">Format</span></span>

<span data-ttu-id="11037-2679">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2679">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2680">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2680">Pattern</span></span>

<span data-ttu-id="11037-2681">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2681">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2682">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2682">Checksum</span></span>

<span data-ttu-id="11037-2683">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2683">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2684">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2684">Definition</span></span>

<span data-ttu-id="11037-2685">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2685">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2686">関数 Func_jp_resident_registration_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2686">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2687">Keyword_jp_resident_registration_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2687">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2688">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2688">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="11037-2689">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="11037-2689">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="11037-2690">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="11037-2690">Resident Registration Number</span></span>
- <span data-ttu-id="11037-2691">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="11037-2691">Resident Register Number</span></span> 
- <span data-ttu-id="11037-2692">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="11037-2692">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="11037-2693">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="11037-2693">Resident Registration No.</span></span> 
- <span data-ttu-id="11037-2694">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="11037-2694">Resident Register No.</span></span> 
- <span data-ttu-id="11037-2695">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="11037-2695">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="11037-2696">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="11037-2696">Basic Resident Register No.</span></span> 
- <span data-ttu-id="11037-2697">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="11037-2697">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="11037-2698">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="11037-2698">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="11037-2699">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="11037-2699">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="11037-2700">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="11037-2700">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="11037-2701">日本の社会保険番号 (SIN)</span><span class="sxs-lookup"><span data-stu-id="11037-2701">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2702">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2702">Format</span></span>

<span data-ttu-id="11037-2703">7～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2703">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2704">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2704">Pattern</span></span>

<span data-ttu-id="11037-2705">7 ～ 12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2705">7-12 digits:</span></span>
- <span data-ttu-id="11037-2706">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2706">Four digits</span></span> 
- <span data-ttu-id="11037-2707">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="11037-2707">A hyphen (optional)</span></span> 
- <span data-ttu-id="11037-2708">6桁の数字または</span><span class="sxs-lookup"><span data-stu-id="11037-2708">Six digits OR</span></span>
- <span data-ttu-id="11037-2709">7 ～ 12 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2709">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2710">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2710">Checksum</span></span>

<span data-ttu-id="11037-2711">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2711">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2712">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2712">Definition</span></span>

<span data-ttu-id="11037-2713">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2713">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2714">関数 Func_jp_sin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2714">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2715">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2715">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="11037-2716">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2716">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2717">関数 Func_jp_sin_pre_1997 がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2717">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2718">Keyword_jp_sin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2718">A keyword from Keyword_jp_sin is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2719">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2719">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="11037-2720">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="11037-2720">Keyword_jp_sin</span></span>

- <span data-ttu-id="11037-2721">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="11037-2721">Social Insurance No.</span></span> 
- <span data-ttu-id="11037-2722">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="11037-2722">Social Insurance Num</span></span> 
- <span data-ttu-id="11037-2723">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="11037-2723">Social Insurance Number</span></span> 
- <span data-ttu-id="11037-2724">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="11037-2724">社会保険のテンキー</span></span> 
- <span data-ttu-id="11037-2725">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="11037-2725">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="11037-2726">日本の居住カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-2726">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2727">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2727">Format</span></span>

<span data-ttu-id="11037-2728">12桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="11037-2728">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2729">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2729">Pattern</span></span>

<span data-ttu-id="11037-2730">12桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2730">12 letters and digits:</span></span>
- <span data-ttu-id="11037-2731">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2731">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="11037-2732">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2732">Eight digits</span></span> 
- <span data-ttu-id="11037-2733">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2733">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2734">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2734">Checksum</span></span>

<span data-ttu-id="11037-2735">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2735">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2736">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2736">Definition</span></span>

<span data-ttu-id="11037-2737">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2737">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2738">正規表現 Regex_jp_residence_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2738">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2739">Keyword_jp_residence_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2739">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2740">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2740">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="11037-2741">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="11037-2741">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="11037-2742">居住カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-2742">Residence card number</span></span>
- <span data-ttu-id="11037-2743">住居カードなし</span><span class="sxs-lookup"><span data-stu-id="11037-2743">Residence card no</span></span>
- <span data-ttu-id="11037-2744">住居カード#</span><span class="sxs-lookup"><span data-stu-id="11037-2744">Residence card #</span></span>
- <span data-ttu-id="11037-2745">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-2745">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="11037-2746">マレーシアの ID カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-2746">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2747">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2747">Format</span></span>

<span data-ttu-id="11037-2748">省略可能なハイフンを含む 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2748">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2749">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2749">Pattern</span></span>

<span data-ttu-id="11037-2750">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2750">12 digits:</span></span>
- <span data-ttu-id="11037-2751">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2751">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="11037-2752">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="11037-2752">A dash (optional)</span></span> 
- <span data-ttu-id="11037-2753">出生地コードを表す 2 桁の文字 </span><span class="sxs-lookup"><span data-stu-id="11037-2753">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="11037-2754">ハイフン 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="11037-2754">A dash (optional)</span></span> 
- <span data-ttu-id="11037-2755">3 桁のランダムな数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2755">Three random digits</span></span> 
- <span data-ttu-id="11037-2756">1 桁の性別コード</span><span class="sxs-lookup"><span data-stu-id="11037-2756">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2757">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2757">Checksum</span></span>

<span data-ttu-id="11037-2758">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2758">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2759">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2759">Definition</span></span>

<span data-ttu-id="11037-2760">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2760">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2761">正規表現 Regex_malaysia_id_card_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2761">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2762">Keyword_malaysia_id_card_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2762">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2763">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2763">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="11037-2764">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="11037-2764">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="11037-2765">デジタルアプリケーションカード</span><span class="sxs-lookup"><span data-stu-id="11037-2765">digital application card</span></span>
- <span data-ttu-id="11037-2766">i/c</span><span class="sxs-lookup"><span data-stu-id="11037-2766">i/c</span></span>
- <span data-ttu-id="11037-2767">i/c いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2767">i/c no</span></span>
- <span data-ttu-id="11037-2768">ic</span><span class="sxs-lookup"><span data-stu-id="11037-2768">ic</span></span>
- <span data-ttu-id="11037-2769">ic no</span><span class="sxs-lookup"><span data-stu-id="11037-2769">ic no</span></span>
- <span data-ttu-id="11037-2770">id card</span><span class="sxs-lookup"><span data-stu-id="11037-2770">id card</span></span>
- <span data-ttu-id="11037-2771">識別カード</span><span class="sxs-lookup"><span data-stu-id="11037-2771">identification Card</span></span>
- <span data-ttu-id="11037-2772">Identity card</span><span class="sxs-lookup"><span data-stu-id="11037-2772">identity card</span></span>
- <span data-ttu-id="11037-2773">k/p</span><span class="sxs-lookup"><span data-stu-id="11037-2773">k/p</span></span>
- <span data-ttu-id="11037-2774">k/p no</span><span class="sxs-lookup"><span data-stu-id="11037-2774">k/p no</span></span>
- <span data-ttu-id="11037-2775">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="11037-2775">kad akuan diri</span></span>
- <span data-ttu-id="11037-2776">kad aplikasi digital</span><span class="sxs-lookup"><span data-stu-id="11037-2776">kad aplikasi digital</span></span>
- <span data-ttu-id="11037-2777">kad の genalan マレーシア</span><span class="sxs-lookup"><span data-stu-id="11037-2777">kad pengenalan malaysia</span></span>
- <span data-ttu-id="11037-2778">kp</span><span class="sxs-lookup"><span data-stu-id="11037-2778">kp</span></span>
- <span data-ttu-id="11037-2779">kp no</span><span class="sxs-lookup"><span data-stu-id="11037-2779">kp no</span></span>
- <span data-ttu-id="11037-2780">mykad</span><span class="sxs-lookup"><span data-stu-id="11037-2780">mykad</span></span>
- <span data-ttu-id="11037-2781">mykas</span><span class="sxs-lookup"><span data-stu-id="11037-2781">mykas</span></span>
- <span data-ttu-id="11037-2782">mykid</span><span class="sxs-lookup"><span data-stu-id="11037-2782">mykid</span></span>
- <span data-ttu-id="11037-2783">mypr</span><span class="sxs-lookup"><span data-stu-id="11037-2783">mypr</span></span>
- <span data-ttu-id="11037-2784">mytentera</span><span class="sxs-lookup"><span data-stu-id="11037-2784">mytentera</span></span>
- <span data-ttu-id="11037-2785">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="11037-2785">malaysia identity card</span></span>
- <span data-ttu-id="11037-2786">マレーシアの id カード</span><span class="sxs-lookup"><span data-stu-id="11037-2786">malaysian identity card</span></span>
- <span data-ttu-id="11037-2787">nric</span><span class="sxs-lookup"><span data-stu-id="11037-2787">nric</span></span>
- <span data-ttu-id="11037-2788">個人識別カード</span><span class="sxs-lookup"><span data-stu-id="11037-2788">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="11037-2789">オランダの市民サービス (BSN) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-2789">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2790">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2790">Format</span></span>

<span data-ttu-id="11037-2791">省略可能なハイフンを含む 8 ～ 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2791">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2792">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2792">Pattern</span></span>

<span data-ttu-id="11037-2793">8 ～ 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2793">8-9 digits:</span></span>
- <span data-ttu-id="11037-2794">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2794">Three digits</span></span> 
- <span data-ttu-id="11037-2795">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="11037-2795">A space (optional)</span></span> 
- <span data-ttu-id="11037-2796">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2796">Three digits</span></span> 
- <span data-ttu-id="11037-2797">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="11037-2797">A space (optional)</span></span> 
- <span data-ttu-id="11037-2798">2 ～ 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2798">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2799">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2799">Checksum</span></span>

<span data-ttu-id="11037-2800">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2800">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2801">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2801">Definition</span></span>

<span data-ttu-id="11037-2802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2802">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2803">関数 Func_netherlands_bsn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2803">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2804">Keyword_netherlands_bsn からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2804">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="11037-2805">関数 Func_eu_date2 は、日付を正しい日付形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2805">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-2806">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2806">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2807">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2807">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="11037-2808">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="11037-2808">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="11037-2809">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="11037-2809">Citizen service number</span></span> 
- <span data-ttu-id="11037-2810">BSN</span><span class="sxs-lookup"><span data-stu-id="11037-2810">BSN</span></span> 
- <span data-ttu-id="11037-2811">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="11037-2811">Burgerservicenummer</span></span> 
- <span data-ttu-id="11037-2812">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="11037-2812">Sofinummer</span></span> 
- <span data-ttu-id="11037-2813">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="11037-2813">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="11037-2814">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2814">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="11037-2815">ニュージーランドの保健省番号</span><span class="sxs-lookup"><span data-stu-id="11037-2815">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2816">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2816">Format</span></span>

<span data-ttu-id="11037-2817">3 桁の文字、スペース 1 つ (省略可能)、4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2817">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2818">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2818">Pattern</span></span>

<span data-ttu-id="11037-2819">3文字 (大文字小文字を区別しない) スペース (省略可能)、4桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2819">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2820">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2820">Checksum</span></span>

<span data-ttu-id="11037-2821">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2821">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2822">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2822">Definition</span></span>

<span data-ttu-id="11037-2823">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2823">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2824">関数 Func_new_zealand_ministry_of_health_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2824">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2825">Keyword_nz_terms のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2825">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="11037-2826">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2826">The checksum passes.</span></span>

```xml
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

<span data-ttu-id="11037-2827">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2827">Keywords</span></span>

<span data-ttu-id="11037-2828">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="11037-2828">Keyword_nz_terms</span></span>

- <span data-ttu-id="11037-2829">NHI</span><span class="sxs-lookup"><span data-stu-id="11037-2829">NHI</span></span> 
- <span data-ttu-id="11037-2830">New Zealand</span><span class="sxs-lookup"><span data-stu-id="11037-2830">New Zealand</span></span> 
- <span data-ttu-id="11037-2831">正常性</span><span class="sxs-lookup"><span data-stu-id="11037-2831">Health</span></span> 
- <span data-ttu-id="11037-2832">処理</span><span class="sxs-lookup"><span data-stu-id="11037-2832">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="11037-2833">ノルウェーの識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-2833">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2834">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2834">Format</span></span>

<span data-ttu-id="11037-2835">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2835">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2836">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2836">Pattern</span></span>

<span data-ttu-id="11037-2837">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2837">11 digits:</span></span>
- <span data-ttu-id="11037-2838">DDMMYY の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2838">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="11037-2839">3 桁の個人番号 </span><span class="sxs-lookup"><span data-stu-id="11037-2839">Three-digit individual number</span></span> 
- <span data-ttu-id="11037-2840">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="11037-2840">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2841">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2841">Checksum</span></span>

<span data-ttu-id="11037-2842">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2842">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2843">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2843">Definition</span></span>

<span data-ttu-id="11037-2844">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2844">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2845">関数 Func_norway_id_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2845">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2846">Keyword_norway_id_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2846">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="11037-2847">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2847">The checksum passes.</span></span>
- <span data-ttu-id="11037-2848">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2848">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2849">関数 Func_norway_id_numbe は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-2849">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2850">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2850">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2851">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2851">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="11037-2852">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="11037-2852">Keyword_norway_id_number</span></span>

- <span data-ttu-id="11037-2853">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="11037-2853">Personal identification number</span></span>
- <span data-ttu-id="11037-2854">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="11037-2854">Norwegian ID Number</span></span>
- <span data-ttu-id="11037-2855">ID Number</span><span class="sxs-lookup"><span data-stu-id="11037-2855">ID Number</span></span>
- <span data-ttu-id="11037-2856">Fim</span><span class="sxs-lookup"><span data-stu-id="11037-2856">Identification</span></span>
- <span data-ttu-id="11037-2857">Personnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2857">Personnummer</span></span>
- <span data-ttu-id="11037-2858">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="11037-2858">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="11037-2859">フィリピンの汎用多目的 ID 番号</span><span class="sxs-lookup"><span data-stu-id="11037-2859">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2860">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2860">Format</span></span>

<span data-ttu-id="11037-2861">ハイフンで区切られた 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2861">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2862">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2862">Pattern</span></span>

<span data-ttu-id="11037-2863">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2863">12 digits:</span></span>
- <span data-ttu-id="11037-2864">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2864">Four digits</span></span> 
- <span data-ttu-id="11037-2865">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-2865">A hyphen</span></span> 
- <span data-ttu-id="11037-2866">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2866">Seven digits</span></span> 
- <span data-ttu-id="11037-2867">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-2867">A hyphen</span></span> 
- <span data-ttu-id="11037-2868">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2868">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2869">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2869">Checksum</span></span>

<span data-ttu-id="11037-2870">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2870">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2871">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2871">Definition</span></span>

<span data-ttu-id="11037-2872">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2872">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2873">正規表現 Regex_philippines_unified_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2873">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2874">Keyword_philippines_id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2874">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2875">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2875">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="11037-2876">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="11037-2876">Keyword_philippines_id</span></span>

- <span data-ttu-id="11037-2877">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="11037-2877">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="11037-2878">UMID</span><span class="sxs-lookup"><span data-stu-id="11037-2878">UMID</span></span> 
- <span data-ttu-id="11037-2879">Identity Card</span><span class="sxs-lookup"><span data-stu-id="11037-2879">Identity Card</span></span> 
- <span data-ttu-id="11037-2880">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="11037-2880">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="11037-2881">ポーランドの ID カード</span><span class="sxs-lookup"><span data-stu-id="11037-2881">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="11037-2882">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2882">Format</span></span>

<span data-ttu-id="11037-2883">3 桁の文字と 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2883">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2884">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2884">Pattern</span></span>

<span data-ttu-id="11037-2885">3 桁の文字 (大文字小文字の区別なし) の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2885">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2886">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2886">Checksum</span></span>

<span data-ttu-id="11037-2887">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2887">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2888">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2888">Definition</span></span>

<span data-ttu-id="11037-2889">DLP ポリシーは 75% です。この種類の機密情報は、近接する300文字の中で検出されます。関数 Func_polish_national_id は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2889">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="11037-2890">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2890">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="11037-2891">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2891">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2892">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2892">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="11037-2893">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="11037-2893">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="11037-2894">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="11037-2894">Dowód osobisty</span></span>
- <span data-ttu-id="11037-2895">特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="11037-2895">Numer dowodu osobistego</span></span>
- <span data-ttu-id="11037-2896">Nazwa i 特定 dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="11037-2896">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="11037-2897">Nazwa i nr dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="11037-2897">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="11037-2898">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="11037-2898">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="11037-2899">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="11037-2899">Dowód Tożsamości</span></span>
- <span data-ttu-id="11037-2900">dow.</span><span class="sxs-lookup"><span data-stu-id="11037-2900">dow.</span></span> <span data-ttu-id="11037-2901">hp-ux.</span><span class="sxs-lookup"><span data-stu-id="11037-2901">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="11037-2902">ポーランドの国民 ID (PESEL)</span><span class="sxs-lookup"><span data-stu-id="11037-2902">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="11037-2903">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2903">Format</span></span>

<span data-ttu-id="11037-2904">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2904">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2905">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2905">Pattern</span></span>

<span data-ttu-id="11037-2906">11 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2906">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2907">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2907">Checksum</span></span>

<span data-ttu-id="11037-2908">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2908">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2909">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2909">Definition</span></span>

<span data-ttu-id="11037-2910">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2910">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2911">関数 Func_pesel_identification_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2911">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2912">Keyword_pesel_identification_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2912">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="11037-2913">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2913">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2914">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2914">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="11037-2915">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="11037-2915">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="11037-2916">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="11037-2916">Nr PESEL</span></span>
- <span data-ttu-id="11037-2917">PESEL</span><span class="sxs-lookup"><span data-stu-id="11037-2917">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="11037-2918">ポーランドのパスポート</span><span class="sxs-lookup"><span data-stu-id="11037-2918">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="11037-2919">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2919">Format</span></span>

<span data-ttu-id="11037-2920">2 桁の文字と 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2920">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2921">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2921">Pattern</span></span>

<span data-ttu-id="11037-2922">2 桁の文字 (大文字小文字の区別なし) の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2922">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2923">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2923">Checksum</span></span>

<span data-ttu-id="11037-2924">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2924">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2925">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2925">Definition</span></span>

<span data-ttu-id="11037-2926">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2926">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2927">関数 Func_polish_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2927">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2928">Keyword_polish_national_id_passport_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2928">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="11037-2929">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2929">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="11037-2930">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2930">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="11037-2931">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="11037-2931">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="11037-2932">特定の引数</span><span class="sxs-lookup"><span data-stu-id="11037-2932">Numer paszportu</span></span>
- <span data-ttu-id="11037-2933">Nr.</span><span class="sxs-lookup"><span data-stu-id="11037-2933">Nr.</span></span> <span data-ttu-id="11037-2934">大き zportu</span><span class="sxs-lookup"><span data-stu-id="11037-2934">Paszportu</span></span>
- <span data-ttu-id="11037-2935">があります</span><span class="sxs-lookup"><span data-stu-id="11037-2935">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="11037-2936">ポルトガルの市民カード番号</span><span class="sxs-lookup"><span data-stu-id="11037-2936">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2937">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2937">Format</span></span>

<span data-ttu-id="11037-2938">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2938">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2939">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2939">Pattern</span></span>

<span data-ttu-id="11037-2940">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2940">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2941">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2941">Checksum</span></span>

<span data-ttu-id="11037-2942">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2942">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2943">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2943">Definition</span></span>

<span data-ttu-id="11037-2944">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2944">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2945">正規表現 Regex_portugal_citizen_card は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2945">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2946">Keyword_portugal_citizen_card からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2946">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-2947">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2947">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="11037-2948">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="11037-2948">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="11037-2949">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="11037-2949">Citizen Card</span></span>
- <span data-ttu-id="11037-2950">National ID Card</span><span class="sxs-lookup"><span data-stu-id="11037-2950">National ID Card</span></span>
- <span data-ttu-id="11037-2951">CC</span><span class="sxs-lookup"><span data-stu-id="11037-2951">CC</span></span>
- <span data-ttu-id="11037-2952">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="11037-2952">Cartão de Cidadão</span></span>
- <span data-ttu-id="11037-2953">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="11037-2953">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="11037-2954">サウジアラビアの国民 ID</span><span class="sxs-lookup"><span data-stu-id="11037-2954">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="11037-2955">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2955">Format</span></span>

<span data-ttu-id="11037-2956">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-2956">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2957">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2957">Pattern</span></span>

<span data-ttu-id="11037-2958">10 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-2958">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2959">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2959">Checksum</span></span>

<span data-ttu-id="11037-2960">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-2960">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2961">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2961">Definition</span></span>

<span data-ttu-id="11037-2962">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2962">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2963">正規表現 Regex_saudi_arabia_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2963">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2964">Keyword_saudi_arabia_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-2964">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2965">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2965">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="11037-2966">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="11037-2966">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="11037-2967">Identification Card</span><span class="sxs-lookup"><span data-stu-id="11037-2967">Identification Card</span></span> 
- <span data-ttu-id="11037-2968">I card number</span><span class="sxs-lookup"><span data-stu-id="11037-2968">I card number</span></span> 
- <span data-ttu-id="11037-2969">ID number</span><span class="sxs-lookup"><span data-stu-id="11037-2969">ID number</span></span> 
- <span data-ttu-id="11037-2970">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="11037-2970">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="11037-2971">シンガポールの国民登録 ID カード (NRIC) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-2971">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-2972">Format</span><span class="sxs-lookup"><span data-stu-id="11037-2972">Format</span></span>

<span data-ttu-id="11037-2973">9 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="11037-2973">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-2974">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-2974">Pattern</span></span>

- <span data-ttu-id="11037-2975">9 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="11037-2975">Nine letters and digits:</span></span>
- <span data-ttu-id="11037-2976">文字「F」、「G」、「S」、または「T」 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-2976">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="11037-2977">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-2977">Seven digits</span></span> 
- <span data-ttu-id="11037-2978">1 桁のアルファベットのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="11037-2978">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-2979">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-2979">Checksum</span></span>

<span data-ttu-id="11037-2980">はい</span><span class="sxs-lookup"><span data-stu-id="11037-2980">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-2981">定義</span><span class="sxs-lookup"><span data-stu-id="11037-2981">Definition</span></span>

<span data-ttu-id="11037-2982">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2982">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2983">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2983">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2984">Keyword_singapore_nric からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-2984">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="11037-2985">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2985">The checksum passes.</span></span>

<span data-ttu-id="11037-2986">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-2986">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-2987">正規表現 Regex_singapore_nric は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-2987">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-2988">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-2988">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-2989">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-2989">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="11037-2990">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="11037-2990">Keyword_singapore_nric</span></span>

- <span data-ttu-id="11037-2991">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="11037-2991">National Registration Identity Card</span></span> 
- <span data-ttu-id="11037-2992">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="11037-2992">Identity Card Number</span></span> 
- <span data-ttu-id="11037-2993">NRIC</span><span class="sxs-lookup"><span data-stu-id="11037-2993">NRIC</span></span> 
- <span data-ttu-id="11037-2994">IC</span><span class="sxs-lookup"><span data-stu-id="11037-2994">IC</span></span> 
- <span data-ttu-id="11037-2995">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="11037-2995">Foreign Identification Number</span></span> 
- <span data-ttu-id="11037-2996">FIN</span><span class="sxs-lookup"><span data-stu-id="11037-2996">FIN</span></span> 
- <span data-ttu-id="11037-2997">身份证</span><span class="sxs-lookup"><span data-stu-id="11037-2997">身份证</span></span> 
- <span data-ttu-id="11037-2998">身份證</span><span class="sxs-lookup"><span data-stu-id="11037-2998">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="11037-2999">南アフリカの識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-2999">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3000">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3000">Format</span></span>

<span data-ttu-id="11037-3001">省略可能なスペースを含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3001">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3002">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3002">Pattern</span></span>

<span data-ttu-id="11037-3003">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3003">13 digits:</span></span>
- <span data-ttu-id="11037-3004">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-3004">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="11037-3005">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3005">Four digits</span></span> 
- <span data-ttu-id="11037-3006">1 桁の市民標識 </span><span class="sxs-lookup"><span data-stu-id="11037-3006">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="11037-3007">数字「8」または「9」 </span><span class="sxs-lookup"><span data-stu-id="11037-3007">The digit "8" or "9"</span></span> 
- <span data-ttu-id="11037-3008">チェックサム ディジットとして機能する 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3008">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3009">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3009">Checksum</span></span>

<span data-ttu-id="11037-3010">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3010">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3011">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3011">Definition</span></span>

<span data-ttu-id="11037-3012">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3012">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3013">関数 Func_south_africa_identification_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3013">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3014">Keyword_south_africa_identification_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3014">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="11037-3015">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3015">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3016">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3016">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="11037-3017">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="11037-3017">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="11037-3018">Identity card</span><span class="sxs-lookup"><span data-stu-id="11037-3018">Identity card</span></span>
- <span data-ttu-id="11037-3019">ID</span><span class="sxs-lookup"><span data-stu-id="11037-3019">ID</span></span>
- <span data-ttu-id="11037-3020">Fim</span><span class="sxs-lookup"><span data-stu-id="11037-3020">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="11037-3021">韓国の住民登録番号</span><span class="sxs-lookup"><span data-stu-id="11037-3021">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3022">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3022">Format</span></span>

<span data-ttu-id="11037-3023">ハイフンを 1 つ含む 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3023">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3024">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3024">Pattern</span></span>

<span data-ttu-id="11037-3025">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3025">13 digits:</span></span>
- <span data-ttu-id="11037-3026">YYMMDD の形式の生年月日を表す 6 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-3026">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="11037-3027">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="11037-3027">A hyphen</span></span> 
- <span data-ttu-id="11037-3028">世紀と性別によって決まる 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-3028">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="11037-3029">4 桁の出生地域コード </span><span class="sxs-lookup"><span data-stu-id="11037-3029">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="11037-3030">先頭の番号が同一である人々を区別するための 1 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="11037-3030">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="11037-3031">1 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="11037-3031">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3032">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3032">Checksum</span></span>

<span data-ttu-id="11037-3033">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3033">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3034">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3034">Definition</span></span>

<span data-ttu-id="11037-3035">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3035">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3036">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3036">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3037">Keyword_south_korea_resident_number からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3037">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="11037-3038">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3038">The checksum passes.</span></span>

<span data-ttu-id="11037-3039">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3039">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3040">関数 Func_south_korea_resident_number は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3040">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3041">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3041">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3042">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3042">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="11037-3043">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="11037-3043">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="11037-3044">National ID card</span><span class="sxs-lookup"><span data-stu-id="11037-3044">National ID card</span></span> 
- <span data-ttu-id="11037-3045">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="11037-3045">Citizen's Registration Number</span></span> 
- <span data-ttu-id="11037-3046">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="11037-3046">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="11037-3047">RRN</span><span class="sxs-lookup"><span data-stu-id="11037-3047">RRN</span></span> 
- <span data-ttu-id="11037-3048">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="11037-3048">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="11037-3049">スペインの社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="11037-3049">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="11037-3050">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3050">Format</span></span>

<span data-ttu-id="11037-3051">11 ～ 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3051">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3052">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3052">Pattern</span></span>

<span data-ttu-id="11037-3053">11-12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3053">11-12 digits:</span></span>
- <span data-ttu-id="11037-3054">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3054">Two digits</span></span> 
- <span data-ttu-id="11037-3055">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="11037-3055">A forward slash (optional)</span></span> 
- <span data-ttu-id="11037-3056">7 ～ 8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3056">7-8 digits</span></span> 
- <span data-ttu-id="11037-3057">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="11037-3057">A forward slash (optional)</span></span> 
- <span data-ttu-id="11037-3058">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3058">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3059">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3059">Checksum</span></span>

<span data-ttu-id="11037-3060">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3060">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3061">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3061">Definition</span></span>

<span data-ttu-id="11037-3062">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3062">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3063">関数 Func_spanish_social_security_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3063">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3064">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3064">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3065">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3065">Keywords</span></span>

<span data-ttu-id="11037-3066">None</span><span class="sxs-lookup"><span data-stu-id="11037-3066">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="11037-3067">SQL Server の接続文字列</span><span class="sxs-lookup"><span data-stu-id="11037-3067">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="11037-3068">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3068">Format</span></span>

<span data-ttu-id="11037-3069">文字列 "User Id"、"User ID"、"uid"、または "UserId" の後に、次のパターンで概説されている文字と文字列が続きます。</span><span class="sxs-lookup"><span data-stu-id="11037-3069">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3070">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3070">Pattern</span></span>

- <span data-ttu-id="11037-3071">文字列 "User Id"、"User ID"、"uid"、または "UserId"</span><span class="sxs-lookup"><span data-stu-id="11037-3071">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="11037-3072">1-200 の小文字または大文字、数字、記号、特殊文字、スペースのいずれかの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="11037-3072">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="11037-3073">文字列 "Password" または "pwd" ("pwd" の前に小文字が含まれていません)</span><span class="sxs-lookup"><span data-stu-id="11037-3073">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="11037-3074">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-3074">An equal sign (=)</span></span>
- <span data-ttu-id="11037-3075">ドル記号 ($)、パーセント記号 (%)、不等号 (>)、記号 (@)、二重引用符 (")、セミコロン (;)、左中かっこ ([)、左かっこ ({) のいずれでもない文字</span><span class="sxs-lookup"><span data-stu-id="11037-3075">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="11037-3076">セミコロンではない7-128 文字の任意の組み合わせ (;)、スラッシュ (/)、または引用符 (")</span><span class="sxs-lookup"><span data-stu-id="11037-3076">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="11037-3077">セミコロン (;)または二重引用符 (")</span><span class="sxs-lookup"><span data-stu-id="11037-3077">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3078">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3078">Checksum</span></span>

<span data-ttu-id="11037-3079">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3079">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3080">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3080">Definition</span></span>

<span data-ttu-id="11037-3081">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3081">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3082">正規表現 CEP_Regex_SQLServerConnectionString は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-3082">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3083">CEP_GlobalFilter からのキーワードが見つかり**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-3083">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="11037-3084">正規表現 CEP_PasswordPlaceHolder は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-3084">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3085">正規表現 CEP_CommonExampleKeywords は、このパターンに一致するコンテンツを検出し**ません**。</span><span class="sxs-lookup"><span data-stu-id="11037-3085">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
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

### <a name="keywords"></a><span data-ttu-id="11037-3086">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3086">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="11037-3087">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="11037-3087">CEP_GlobalFilter</span></span>

- <span data-ttu-id="11037-3088">パスワードの一部</span><span class="sxs-lookup"><span data-stu-id="11037-3088">some-password</span></span>
- <span data-ttu-id="11037-3089">パスワード</span><span class="sxs-lookup"><span data-stu-id="11037-3089">somepassword</span></span>
- <span data-ttu-id="11037-3090">secretPassword</span><span class="sxs-lookup"><span data-stu-id="11037-3090">secretPassword</span></span>
- <span data-ttu-id="11037-3091">示す</span><span class="sxs-lookup"><span data-stu-id="11037-3091">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="11037-3092">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="11037-3092">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="11037-3093">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-3093">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-3094">Password または pwd の後に、0-2 スペース、等号 (=)、0-2 スペース、アスタリスク (\*)、または--</span><span class="sxs-lookup"><span data-stu-id="11037-3094">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="11037-3095">Password または pwd の後に、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="11037-3095">Password or pwd followed by:</span></span>
    - <span data-ttu-id="11037-3096">等号 (=)</span><span class="sxs-lookup"><span data-stu-id="11037-3096">Equal sign (=)</span></span>
    - <span data-ttu-id="11037-3097">不等号 (<)</span><span class="sxs-lookup"><span data-stu-id="11037-3097">Less than symbol (<)</span></span>
    - <span data-ttu-id="11037-3098">1-200 文字の大文字と小文字、数字、アスタリスク (\*)、ハイフン (-)、下線 (_)、または空白文字の任意の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="11037-3098">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="11037-3099">不等号 (>)</span><span class="sxs-lookup"><span data-stu-id="11037-3099">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="11037-3100">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="11037-3100">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="11037-3101">(この機密情報の種類では、キーワードリストではなく正規表現を使用してこれらのキーワードを識別していることに注意してください)。</span><span class="sxs-lookup"><span data-stu-id="11037-3101">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="11037-3102">拠点</span><span class="sxs-lookup"><span data-stu-id="11037-3102">contoso</span></span>
- <span data-ttu-id="11037-3103">fabrikam</span><span class="sxs-lookup"><span data-stu-id="11037-3103">fabrikam</span></span>
- <span data-ttu-id="11037-3104">ノース</span><span class="sxs-lookup"><span data-stu-id="11037-3104">northwind</span></span>
- <span data-ttu-id="11037-3105">サンド</span><span class="sxs-lookup"><span data-stu-id="11037-3105">sandbox</span></span>
- <span data-ttu-id="11037-3106">onebox</span><span class="sxs-lookup"><span data-stu-id="11037-3106">onebox</span></span>
- <span data-ttu-id="11037-3107">localhost</span><span class="sxs-lookup"><span data-stu-id="11037-3107">localhost</span></span>
- <span data-ttu-id="11037-3108">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="11037-3108">127.0.0.1</span></span>
- <span data-ttu-id="11037-3109">testacs。</span><span class="sxs-lookup"><span data-stu-id="11037-3109">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="11037-3110">com</span><span class="sxs-lookup"><span data-stu-id="11037-3110">com</span></span>
- <span data-ttu-id="11037-3111">s-int。</span><span class="sxs-lookup"><span data-stu-id="11037-3111">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="11037-3112">ネット</span><span class="sxs-lookup"><span data-stu-id="11037-3112">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="11037-3113">スウェーデンの国民 ID</span><span class="sxs-lookup"><span data-stu-id="11037-3113">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="11037-3114">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3114">Format</span></span>

<span data-ttu-id="11037-3115">10 桁または 12 桁の数字とオプションの区切り記号 1 つ</span><span class="sxs-lookup"><span data-stu-id="11037-3115">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3116">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3116">Pattern</span></span>

<span data-ttu-id="11037-3117">10 桁または 12 桁の数字と省略可能な区切り記号:</span><span class="sxs-lookup"><span data-stu-id="11037-3117">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="11037-3118">2 ～ 4 桁の数字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="11037-3118">2-4 digits (optional)</span></span> 
- <span data-ttu-id="11037-3119">YYMMDD という日付形式の 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3119">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="11037-3120">区切り文字「-」または「+」(省略可能)、および</span><span class="sxs-lookup"><span data-stu-id="11037-3120">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="11037-3121">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3121">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3122">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3122">Checksum</span></span>

<span data-ttu-id="11037-3123">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3123">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3124">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3124">Definition</span></span>

<span data-ttu-id="11037-3125">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3125">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3126">関数 Func_swedish_national_identifier がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3126">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3127">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3127">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3128">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3128">Keywords</span></span>

<span data-ttu-id="11037-3129">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3129">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="11037-3130">スウェーデンのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-3130">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3131">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3131">Format</span></span>

<span data-ttu-id="11037-3132">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3132">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3133">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3133">Pattern</span></span>

<span data-ttu-id="11037-3134">8 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-3134">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3135">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3135">Checksum</span></span>

<span data-ttu-id="11037-3136">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3136">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3137">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3137">Definition</span></span>

<span data-ttu-id="11037-3138">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3138">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3139">正規表現 Regex_sweden_passport_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3139">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3140">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-3140">One of the following is true:</span></span>
    - <span data-ttu-id="11037-3141">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3141">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="11037-3142">Keyword_sweden_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3142">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3143">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3143">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="11037-3144">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="11037-3144">Keyword_sweden_passport</span></span>

- <span data-ttu-id="11037-3145">visa requirements</span><span class="sxs-lookup"><span data-stu-id="11037-3145">visa requirements</span></span> 
- <span data-ttu-id="11037-3146">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="11037-3146">Alien Registration Card</span></span> 
- <span data-ttu-id="11037-3147">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="11037-3147">Schengen visas</span></span> 
- <span data-ttu-id="11037-3148">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="11037-3148">Schengen visa</span></span> 
- <span data-ttu-id="11037-3149">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="11037-3149">Visa Processing</span></span> 
- <span data-ttu-id="11037-3150">Visa Type</span><span class="sxs-lookup"><span data-stu-id="11037-3150">Visa Type</span></span> 
- <span data-ttu-id="11037-3151">Single Entry</span><span class="sxs-lookup"><span data-stu-id="11037-3151">Single Entry</span></span> 
- <span data-ttu-id="11037-3152">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="11037-3152">Multiple Entry</span></span> 
- <span data-ttu-id="11037-3153">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="11037-3153">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="11037-3154">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="11037-3154">Keyword_passport</span></span>

- <span data-ttu-id="11037-3155">Passport Number</span><span class="sxs-lookup"><span data-stu-id="11037-3155">Passport Number</span></span> 
- <span data-ttu-id="11037-3156">Passport No</span><span class="sxs-lookup"><span data-stu-id="11037-3156">Passport No</span></span> 
- <span data-ttu-id="11037-3157">Passport #</span><span class="sxs-lookup"><span data-stu-id="11037-3157">Passport #</span></span> 
- <span data-ttu-id="11037-3158">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="11037-3158">Passport#</span></span> 
- <span data-ttu-id="11037-3159">PassportID</span><span class="sxs-lookup"><span data-stu-id="11037-3159">PassportID</span></span> 
- <span data-ttu-id="11037-3160">Passportno</span><span class="sxs-lookup"><span data-stu-id="11037-3160">Passportno</span></span> 
- <span data-ttu-id="11037-3161">passportnumber</span><span class="sxs-lookup"><span data-stu-id="11037-3161">passportnumber</span></span> 
- <span data-ttu-id="11037-3162">パスポート</span><span class="sxs-lookup"><span data-stu-id="11037-3162">パスポート</span></span> 
- <span data-ttu-id="11037-3163">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-3163">パスポート番号</span></span> 
- <span data-ttu-id="11037-3164">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="11037-3164">パスポートのNum</span></span> 
- <span data-ttu-id="11037-3165">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="11037-3165">パスポート＃</span></span> 
- <span data-ttu-id="11037-3166">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="11037-3166">Numéro de passeport</span></span> 
- <span data-ttu-id="11037-3167">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="11037-3167">Passeport n °</span></span> 
- <span data-ttu-id="11037-3168">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="11037-3168">Passeport Non</span></span> 
- <span data-ttu-id="11037-3169">Passeport #</span><span class="sxs-lookup"><span data-stu-id="11037-3169">Passeport #</span></span> 
- <span data-ttu-id="11037-3170">Passeport#</span><span class="sxs-lookup"><span data-stu-id="11037-3170">Passeport#</span></span> 
- <span data-ttu-id="11037-3171">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="11037-3171">PasseportNon</span></span> 
- <span data-ttu-id="11037-3172">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="11037-3172">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="11037-3173">SWIFT コード</span><span class="sxs-lookup"><span data-stu-id="11037-3173">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="11037-3174">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3174">Format</span></span>

<span data-ttu-id="11037-3175">4 桁の文字の後に 5 ～ 31 桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="11037-3175">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3176">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3176">Pattern</span></span>

<span data-ttu-id="11037-3177">4 文字の後に 5 ～ 31 個の文字または数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3177">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="11037-3178">4 文字の銀行コード (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="11037-3178">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="11037-3179">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="11037-3179">An optional space</span></span> 
- <span data-ttu-id="11037-3180">4 ～ 28 個の文字または数字 (基本的銀行口座番号 (BBAN))</span><span class="sxs-lookup"><span data-stu-id="11037-3180">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="11037-3181">省略可能なスペース</span><span class="sxs-lookup"><span data-stu-id="11037-3181">An optional space</span></span> 
- <span data-ttu-id="11037-3182">1 ～ 3 個の文字または数字 (BBAN の残りの部分)</span><span class="sxs-lookup"><span data-stu-id="11037-3182">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3183">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3183">Checksum</span></span>

<span data-ttu-id="11037-3184">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3184">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3185">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3185">Definition</span></span>

<span data-ttu-id="11037-3186">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3186">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3187">正規表現 Regex_swift がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3187">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3188">Keyword_swift のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3188">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3189">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3189">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="11037-3190">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="11037-3190">Keyword_swift</span></span>

- <span data-ttu-id="11037-3191">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="11037-3191">international organization for standardization 9362</span></span> 
- <span data-ttu-id="11037-3192">iso 9362</span><span class="sxs-lookup"><span data-stu-id="11037-3192">iso 9362</span></span> 
- <span data-ttu-id="11037-3193">iso9362</span><span class="sxs-lookup"><span data-stu-id="11037-3193">iso9362</span></span> 
- <span data-ttu-id="11037-3194">実現\#</span><span class="sxs-lookup"><span data-stu-id="11037-3194">swift\#</span></span> 
- <span data-ttu-id="11037-3195">swiftcode</span><span class="sxs-lookup"><span data-stu-id="11037-3195">swiftcode</span></span> 
- <span data-ttu-id="11037-3196">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="11037-3196">swiftnumber</span></span> 
- <span data-ttu-id="11037-3197">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="11037-3197">swiftroutingnumber</span></span> 
- <span data-ttu-id="11037-3198">swift code</span><span class="sxs-lookup"><span data-stu-id="11037-3198">swift code</span></span> 
- <span data-ttu-id="11037-3199">swift number #</span><span class="sxs-lookup"><span data-stu-id="11037-3199">swift number #</span></span> 
- <span data-ttu-id="11037-3200">swift routing number</span><span class="sxs-lookup"><span data-stu-id="11037-3200">swift routing number</span></span> 
- <span data-ttu-id="11037-3201">bic number</span><span class="sxs-lookup"><span data-stu-id="11037-3201">bic number</span></span> 
- <span data-ttu-id="11037-3202">bic code</span><span class="sxs-lookup"><span data-stu-id="11037-3202">bic code</span></span> 
- <span data-ttu-id="11037-3203">bic\#</span><span class="sxs-lookup"><span data-stu-id="11037-3203">bic \#</span></span> 
- <span data-ttu-id="11037-3204">bic\#</span><span class="sxs-lookup"><span data-stu-id="11037-3204">bic\#</span></span> 
- <span data-ttu-id="11037-3205">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="11037-3205">bank identifier code</span></span> 
- <span data-ttu-id="11037-3206">標準化9362</span><span class="sxs-lookup"><span data-stu-id="11037-3206">標準化9362</span></span> 
- <span data-ttu-id="11037-3207">迅速＃</span><span class="sxs-lookup"><span data-stu-id="11037-3207">迅速＃</span></span> 
- <span data-ttu-id="11037-3208">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="11037-3208">SWIFTコード</span></span> 
- <span data-ttu-id="11037-3209">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="11037-3209">SWIFT番号</span></span> 
- <span data-ttu-id="11037-3210">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="11037-3210">迅速なルーティング番号</span></span> 
- <span data-ttu-id="11037-3211">BIC番号</span><span class="sxs-lookup"><span data-stu-id="11037-3211">BIC番号</span></span> 
- <span data-ttu-id="11037-3212">BICコード</span><span class="sxs-lookup"><span data-stu-id="11037-3212">BICコード</span></span> 
- <span data-ttu-id="11037-3213">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="11037-3213">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="11037-3214">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="11037-3214">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="11037-3215">rapide\#</span><span class="sxs-lookup"><span data-stu-id="11037-3215">rapide \#</span></span> 
- <span data-ttu-id="11037-3216">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="11037-3216">code SWIFT</span></span> 
- <span data-ttu-id="11037-3217">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="11037-3217">le numéro de swift</span></span> 
- <span data-ttu-id="11037-3218">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="11037-3218">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="11037-3219">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="11037-3219">le numéro BIC</span></span> 
- <span data-ttu-id="11037-3220">\#BIC</span><span class="sxs-lookup"><span data-stu-id="11037-3220">\# BIC</span></span> 
- <span data-ttu-id="11037-3221">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="11037-3221">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="11037-3222">台湾の国民 ID</span><span class="sxs-lookup"><span data-stu-id="11037-3222">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="11037-3223">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3223">Format</span></span>

<span data-ttu-id="11037-3224">1 桁の文字 (アルファベット) の後に 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3224">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3225">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3225">Pattern</span></span>

<span data-ttu-id="11037-3226">1 文字 の後に 9 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3226">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="11037-3227">1 文字 (英語、大文字小文字を区別しません)</span><span class="sxs-lookup"><span data-stu-id="11037-3227">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="11037-3228">数字の「1」または「2」</span><span class="sxs-lookup"><span data-stu-id="11037-3228">The digit "1" or "2"</span></span> 
- <span data-ttu-id="11037-3229">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3229">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3230">Checksum</span></span>

<span data-ttu-id="11037-3231">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3231">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3232">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3232">Definition</span></span>

<span data-ttu-id="11037-3233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3233">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3234">関数 Func_taiwanese_national_id がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3234">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3235">Keyword_taiwanese_national_id のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3235">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="11037-3236">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3236">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3237">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3237">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="11037-3238">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="11037-3238">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="11037-3239">身份證字號</span><span class="sxs-lookup"><span data-stu-id="11037-3239">身份證字號</span></span> 
- <span data-ttu-id="11037-3240">身份證</span><span class="sxs-lookup"><span data-stu-id="11037-3240">身份證</span></span> 
- <span data-ttu-id="11037-3241">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="11037-3241">身份證號碼</span></span> 
- <span data-ttu-id="11037-3242">身份證號</span><span class="sxs-lookup"><span data-stu-id="11037-3242">身份證號</span></span> 
- <span data-ttu-id="11037-3243">身分證字號</span><span class="sxs-lookup"><span data-stu-id="11037-3243">身分證字號</span></span> 
- <span data-ttu-id="11037-3244">身分證</span><span class="sxs-lookup"><span data-stu-id="11037-3244">身分證</span></span> 
- <span data-ttu-id="11037-3245">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="11037-3245">身分證號碼</span></span> 
- <span data-ttu-id="11037-3246">身份證號</span><span class="sxs-lookup"><span data-stu-id="11037-3246">身份證號</span></span> 
- <span data-ttu-id="11037-3247">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="11037-3247">身分證統一編號</span></span> 
- <span data-ttu-id="11037-3248">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="11037-3248">國民身分證統一編號</span></span> 
- <span data-ttu-id="11037-3249">簽名</span><span class="sxs-lookup"><span data-stu-id="11037-3249">簽名</span></span> 
- <span data-ttu-id="11037-3250">蓋章</span><span class="sxs-lookup"><span data-stu-id="11037-3250">蓋章</span></span> 
- <span data-ttu-id="11037-3251">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="11037-3251">簽名或蓋章</span></span> 
- <span data-ttu-id="11037-3252">簽章</span><span class="sxs-lookup"><span data-stu-id="11037-3252">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="11037-3253">	台湾のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-3253">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3254">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3254">Format</span></span>

- <span data-ttu-id="11037-3255">バイオメトリックパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3255">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="11037-3256">バイオメトリクスでないパスポート番号: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3256">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3257">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3257">Pattern</span></span>
<span data-ttu-id="11037-3258">バイオメトリックパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="11037-3258">Biometric passport number:</span></span>
- <span data-ttu-id="11037-3259">数字「3」 </span><span class="sxs-lookup"><span data-stu-id="11037-3259">The digit "3"</span></span> 
- <span data-ttu-id="11037-3260">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3260">Eight digits</span></span>

<span data-ttu-id="11037-3261">バイオメトリクスではないパスポート番号:</span><span class="sxs-lookup"><span data-stu-id="11037-3261">Non-biometric passport number:</span></span>
- <span data-ttu-id="11037-3262">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3262">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3263">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3263">Checksum</span></span>

<span data-ttu-id="11037-3264">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3264">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3265">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3265">Definition</span></span>

<span data-ttu-id="11037-3266">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3266">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3267">正規表現 Regex_taiwan_passport は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-3267">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3268">Keyword_taiwan_passport からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3268">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3269">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3269">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="11037-3270">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="11037-3270">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="11037-3271">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="11037-3271">ROC passport number</span></span> 
- <span data-ttu-id="11037-3272">Passport number</span><span class="sxs-lookup"><span data-stu-id="11037-3272">Passport number</span></span> 
- <span data-ttu-id="11037-3273">Passport no</span><span class="sxs-lookup"><span data-stu-id="11037-3273">Passport no</span></span> 
- <span data-ttu-id="11037-3274">Passport Num</span><span class="sxs-lookup"><span data-stu-id="11037-3274">Passport Num</span></span> 
- <span data-ttu-id="11037-3275">Passport #</span><span class="sxs-lookup"><span data-stu-id="11037-3275">Passport #</span></span> 
- <span data-ttu-id="11037-3276">护照</span><span class="sxs-lookup"><span data-stu-id="11037-3276">护照</span></span> 
- <span data-ttu-id="11037-3277">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="11037-3277">中華民國護照</span></span> 
- <span data-ttu-id="11037-3278">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="11037-3278">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="11037-3279">台湾の在留証明書 (ARC/TARC) 番号</span><span class="sxs-lookup"><span data-stu-id="11037-3279">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3280">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3280">Format</span></span>

<span data-ttu-id="11037-3281">10 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="11037-3281">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3282">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3282">Pattern</span></span>

<span data-ttu-id="11037-3283">10 桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3283">10 letters and digits:</span></span>
- <span data-ttu-id="11037-3284">2 桁の文字 (大文字小文字の区別なし) </span><span class="sxs-lookup"><span data-stu-id="11037-3284">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="11037-3285">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3285">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3286">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3286">Checksum</span></span>

<span data-ttu-id="11037-3287">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3287">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3288">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3288">Definition</span></span>

<span data-ttu-id="11037-3289">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3289">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3290">正規表現 Regex_taiwan_resident_certificate は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-3290">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3291">Keyword_taiwan_resident_certificate からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3291">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3292">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3292">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="11037-3293">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="11037-3293">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="11037-3294">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="11037-3294">Resident Certificate</span></span> 
- <span data-ttu-id="11037-3295">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="11037-3295">Resident Cert</span></span> 
- <span data-ttu-id="11037-3296">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="11037-3296">Resident Cert.</span></span> 
- <span data-ttu-id="11037-3297">Identification card</span><span class="sxs-lookup"><span data-stu-id="11037-3297">Identification card</span></span> 
- <span data-ttu-id="11037-3298">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="11037-3298">Alien Resident Certificate</span></span> 
- <span data-ttu-id="11037-3299">円弧</span><span class="sxs-lookup"><span data-stu-id="11037-3299">ARC</span></span> 
- <span data-ttu-id="11037-3300">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="11037-3300">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="11037-3301">TARC</span><span class="sxs-lookup"><span data-stu-id="11037-3301">TARC</span></span> 
- <span data-ttu-id="11037-3302">居留證</span><span class="sxs-lookup"><span data-stu-id="11037-3302">居留證</span></span> 
- <span data-ttu-id="11037-3303">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="11037-3303">外僑居留證</span></span> 
- <span data-ttu-id="11037-3304">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="11037-3304">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="11037-3305">タイ語の母集団識別コード</span><span class="sxs-lookup"><span data-stu-id="11037-3305">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="11037-3306">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3306">Format</span></span>

<span data-ttu-id="11037-3307">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3307">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3308">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3308">Pattern</span></span>

<span data-ttu-id="11037-3309">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3309">13 digits:</span></span>
- <span data-ttu-id="11037-3310">最初の桁が0または9ではない</span><span class="sxs-lookup"><span data-stu-id="11037-3310">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="11037-3311">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3311">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3312">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3312">Checksum</span></span>

<span data-ttu-id="11037-3313">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3313">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3314">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3314">Definition</span></span>

<span data-ttu-id="11037-3315">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3315">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3316">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3316">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3317">Keyword_Thai_Citizen_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3317">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="11037-3318">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3319">関数 Func_Thai_Citizen_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3319">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3320">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3320">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="11037-3321">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="11037-3321">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="11037-3322">ID Number</span><span class="sxs-lookup"><span data-stu-id="11037-3322">ID Number</span></span>
- <span data-ttu-id="11037-3323">識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-3323">Identification Number</span></span>
- <span data-ttu-id="11037-3324">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="11037-3324">บัตรประชาชน</span></span>
- <span data-ttu-id="11037-3325">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="11037-3325">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="11037-3326">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="11037-3326">บัตรประชาชน</span></span>
- <span data-ttu-id="11037-3327">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="11037-3327">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="11037-3328">トルコの国の識別番号</span><span class="sxs-lookup"><span data-stu-id="11037-3328">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3329">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3329">Format</span></span>

<span data-ttu-id="11037-3330">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3330">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3331">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3331">Pattern</span></span>

<span data-ttu-id="11037-3332">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3332">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3333">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3333">Checksum</span></span>

<span data-ttu-id="11037-3334">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3334">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3335">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3335">Definition</span></span>

<span data-ttu-id="11037-3336">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3336">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3337">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3337">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3338">Keyword_Turkish_National_Id からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3338">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="11037-3339">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3339">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3340">関数 Func_Turkish_National_Id は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3340">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3341">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3341">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="11037-3342">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="11037-3342">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="11037-3343">TC Kimlik No</span><span class="sxs-lookup"><span data-stu-id="11037-3343">TC Kimlik No</span></span>
- <span data-ttu-id="11037-3344">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="11037-3344">TC Kimlik numarası</span></span>
- <span data-ttu-id="11037-3345">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="11037-3345">Vatandaşlık numarası</span></span>
- <span data-ttu-id="11037-3346">Vatandaşlık no</span><span class="sxs-lookup"><span data-stu-id="11037-3346">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="11037-p141">英国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-p141">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3349">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3349">Format</span></span>

<span data-ttu-id="11037-3350">指定の形式で組み合わせた 18 桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="11037-3350">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3351">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3351">Pattern</span></span>

<span data-ttu-id="11037-3352">18 個の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3352">18 letters and digits:</span></span>
- <span data-ttu-id="11037-3353">5 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="11037-3353">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="11037-3354">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3354">One digit</span></span> 
- <span data-ttu-id="11037-3355">誕生日を示す DDMMY という日付形式の 5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3355">Five digits in the date format DDMMY for date of birth</span></span> 
- <span data-ttu-id="11037-3356">2 文字 (大文字小文字を区別しない) または数字「9」(1 文字の代わり)</span><span class="sxs-lookup"><span data-stu-id="11037-3356">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="11037-3357">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3357">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3358">Checksum</span></span>

<span data-ttu-id="11037-3359">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3359">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3360">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3360">Definition</span></span>

<span data-ttu-id="11037-3361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3361">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3362">関数 Func_uk_drivers_license がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3362">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3363">Keyword_uk_drivers_license のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3363">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="11037-3364">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3364">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3365">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3365">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="11037-3366">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="11037-3366">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="11037-3367">DVLA</span><span class="sxs-lookup"><span data-stu-id="11037-3367">DVLA</span></span> 
- <span data-ttu-id="11037-3368">light vans</span><span class="sxs-lookup"><span data-stu-id="11037-3368">light vans</span></span> 
- <span data-ttu-id="11037-3369">quadbikes</span><span class="sxs-lookup"><span data-stu-id="11037-3369">quadbikes</span></span> 
- <span data-ttu-id="11037-3370">motor cars</span><span class="sxs-lookup"><span data-stu-id="11037-3370">motor cars</span></span> 
- <span data-ttu-id="11037-3371">125cc</span><span class="sxs-lookup"><span data-stu-id="11037-3371">125cc</span></span> 
- <span data-ttu-id="11037-3372">sidecar</span><span class="sxs-lookup"><span data-stu-id="11037-3372">sidecar</span></span> 
- <span data-ttu-id="11037-3373">tricycles</span><span class="sxs-lookup"><span data-stu-id="11037-3373">tricycles</span></span> 
- <span data-ttu-id="11037-3374">motorcycles</span><span class="sxs-lookup"><span data-stu-id="11037-3374">motorcycles</span></span> 
- <span data-ttu-id="11037-3375">photocard licence</span><span class="sxs-lookup"><span data-stu-id="11037-3375">photocard licence</span></span> 
- <span data-ttu-id="11037-3376">learner drivers</span><span class="sxs-lookup"><span data-stu-id="11037-3376">learner drivers</span></span> 
- <span data-ttu-id="11037-3377">licence holder</span><span class="sxs-lookup"><span data-stu-id="11037-3377">licence holder</span></span> 
- <span data-ttu-id="11037-3378">licence holders</span><span class="sxs-lookup"><span data-stu-id="11037-3378">licence holders</span></span> 
- <span data-ttu-id="11037-3379">driving licences</span><span class="sxs-lookup"><span data-stu-id="11037-3379">driving licences</span></span> 
- <span data-ttu-id="11037-3380">driving licence</span><span class="sxs-lookup"><span data-stu-id="11037-3380">driving licence</span></span> 
- <span data-ttu-id="11037-3381">dual control car</span><span class="sxs-lookup"><span data-stu-id="11037-3381">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="11037-p142">英国の選挙登録番号</span><span class="sxs-lookup"><span data-stu-id="11037-p142">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3384">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3384">Format</span></span>

<span data-ttu-id="11037-3385">2 桁の文字の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3385">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3386">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3386">Pattern</span></span>

<span data-ttu-id="11037-3387">2 桁の文字 (大文字小文字の区別なし) の後に 1 ～ 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3387">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3388">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3388">Checksum</span></span>

<span data-ttu-id="11037-3389">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3389">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3390">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3390">Definition</span></span>

<span data-ttu-id="11037-3391">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3391">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3392">正規表現 Regex_uk_electoral がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3392">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3393">Keyword_uk_electoral のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3393">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3394">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3394">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="11037-3395">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="11037-3395">Keyword_uk_electoral</span></span>

- <span data-ttu-id="11037-3396">council nomination</span><span class="sxs-lookup"><span data-stu-id="11037-3396">council nomination</span></span> 
- <span data-ttu-id="11037-3397">nomination form</span><span class="sxs-lookup"><span data-stu-id="11037-3397">nomination form</span></span> 
- <span data-ttu-id="11037-3398">electoral register</span><span class="sxs-lookup"><span data-stu-id="11037-3398">electoral register</span></span> 
- <span data-ttu-id="11037-3399">electoral roll</span><span class="sxs-lookup"><span data-stu-id="11037-3399">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="11037-p143">英国の国民健康保険番号</span><span class="sxs-lookup"><span data-stu-id="11037-p143">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3402">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3402">Format</span></span>

<span data-ttu-id="11037-3403">スペースで区切られた 10 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3403">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3404">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3404">Pattern</span></span>

<span data-ttu-id="11037-3405">10 ～ 17 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="11037-3405">10-17 digits:</span></span>
- <span data-ttu-id="11037-3406">3 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3406">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="11037-3407">スペース</span><span class="sxs-lookup"><span data-stu-id="11037-3407">A space</span></span> 
- <span data-ttu-id="11037-3408">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3408">Three digits</span></span> 
- <span data-ttu-id="11037-3409">スペース</span><span class="sxs-lookup"><span data-stu-id="11037-3409">A space</span></span> 
- <span data-ttu-id="11037-3410">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3410">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3411">Checksum</span></span>

<span data-ttu-id="11037-3412">はい</span><span class="sxs-lookup"><span data-stu-id="11037-3412">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3413">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3413">Definition</span></span>

<span data-ttu-id="11037-3414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3414">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3415">関数 Func_uk_nhs_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3415">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3416">次のいずれかの条件に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-3416">One of the following is true:</span></span>
    - <span data-ttu-id="11037-3417">Keyword_uk_nhs_number のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3417">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="11037-3418">Keyword_uk_nhs_number1 のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3418">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="11037-3419">Keyword_uk_nhs_number_dob のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3419">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="11037-3420">チェックサムが渡される。</span><span class="sxs-lookup"><span data-stu-id="11037-3420">The checksum passes.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3421">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3421">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="11037-3422">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="11037-3422">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="11037-3423">national health service</span><span class="sxs-lookup"><span data-stu-id="11037-3423">national health service</span></span> 
- <span data-ttu-id="11037-3424">nhs</span><span class="sxs-lookup"><span data-stu-id="11037-3424">nhs</span></span> 
- <span data-ttu-id="11037-3425">health services authority</span><span class="sxs-lookup"><span data-stu-id="11037-3425">health services authority</span></span> 
- <span data-ttu-id="11037-3426">health authority</span><span class="sxs-lookup"><span data-stu-id="11037-3426">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="11037-3427">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="11037-3427">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="11037-3428">patient id</span><span class="sxs-lookup"><span data-stu-id="11037-3428">patient id</span></span> 
- <span data-ttu-id="11037-3429">patient identification</span><span class="sxs-lookup"><span data-stu-id="11037-3429">patient identification</span></span> 
- <span data-ttu-id="11037-3430">patient no</span><span class="sxs-lookup"><span data-stu-id="11037-3430">patient no</span></span> 
- <span data-ttu-id="11037-3431">patient number</span><span class="sxs-lookup"><span data-stu-id="11037-3431">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="11037-3432">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="11037-3432">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="11037-3433">GP</span><span class="sxs-lookup"><span data-stu-id="11037-3433">GP</span></span> 
- <span data-ttu-id="11037-3434">DOB</span><span class="sxs-lookup"><span data-stu-id="11037-3434">DOB</span></span> 
- <span data-ttu-id="11037-3435">D.</span><span class="sxs-lookup"><span data-stu-id="11037-3435">D.O.B</span></span> 
- <span data-ttu-id="11037-3436">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="11037-3436">Date of Birth</span></span> 
- <span data-ttu-id="11037-3437">Birth Date</span><span class="sxs-lookup"><span data-stu-id="11037-3437">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="11037-p144">英国の国民保険番号 (NINO)</span><span class="sxs-lookup"><span data-stu-id="11037-p144">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="11037-3440">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3440">Format</span></span>

<span data-ttu-id="11037-3441">スペースまたはダッシュで区切られた7文字または9文字</span><span class="sxs-lookup"><span data-stu-id="11037-3441">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3442">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3442">Pattern</span></span>

<span data-ttu-id="11037-3443">次の2つのパターンを使用できます。</span><span class="sxs-lookup"><span data-stu-id="11037-3443">Two possible patterns:</span></span>

- <span data-ttu-id="11037-3444">2文字 (有効な NINOs このプレフィックスには特定の文字のみを使用します。このパターンは、大文字小文字を区別しません)。</span><span class="sxs-lookup"><span data-stu-id="11037-3444">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="11037-3445">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3445">Six digits</span></span>
- <span data-ttu-id="11037-3446">「A」、「B」、「C」、または「d」 (プレフィックスと同様に、サフィックスには特定の文字のみ指定できます。大文字と小文字は区別されません)</span><span class="sxs-lookup"><span data-stu-id="11037-3446">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="11037-3447">OR</span><span class="sxs-lookup"><span data-stu-id="11037-3447">OR</span></span>

- <span data-ttu-id="11037-3448">2文字</span><span class="sxs-lookup"><span data-stu-id="11037-3448">Two letters</span></span>
- <span data-ttu-id="11037-3449">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-3449">A space or dash</span></span>
- <span data-ttu-id="11037-3450">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3450">Two digits</span></span>
- <span data-ttu-id="11037-3451">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-3451">A space or dash</span></span>
- <span data-ttu-id="11037-3452">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3452">Two digits</span></span>
- <span data-ttu-id="11037-3453">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-3453">A space or dash</span></span>
- <span data-ttu-id="11037-3454">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3454">Two digits</span></span>
- <span data-ttu-id="11037-3455">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-3455">A space or dash</span></span>
- <span data-ttu-id="11037-3456">' A '、' B '、' C '、または ' d ' のどちらか</span><span class="sxs-lookup"><span data-stu-id="11037-3456">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3457">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3457">Checksum</span></span>

<span data-ttu-id="11037-3458">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3458">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3459">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3459">Definition</span></span>

<span data-ttu-id="11037-3460">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3460">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3461">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3461">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3462">Keyword_uk_nino のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3462">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="11037-3463">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3463">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3464">関数 Func_uk_nino がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3464">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3465">Keyword_uk_nino のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-3465">No keyword from Keyword_uk_nino is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3466">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3466">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="11037-3467">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="11037-3467">Keyword_uk_nino</span></span>

- <span data-ttu-id="11037-3468">national insurance number</span><span class="sxs-lookup"><span data-stu-id="11037-3468">national insurance number</span></span> 
- <span data-ttu-id="11037-3469">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="11037-3469">national insurance contributions</span></span> 
- <span data-ttu-id="11037-3470">protection act</span><span class="sxs-lookup"><span data-stu-id="11037-3470">protection act</span></span> 
- <span data-ttu-id="11037-3471">金</span><span class="sxs-lookup"><span data-stu-id="11037-3471">insurance</span></span> 
- <span data-ttu-id="11037-3472">social security number</span><span class="sxs-lookup"><span data-stu-id="11037-3472">social security number</span></span> 
- <span data-ttu-id="11037-3473">insurance application</span><span class="sxs-lookup"><span data-stu-id="11037-3473">insurance application</span></span> 
- <span data-ttu-id="11037-3474">medical application</span><span class="sxs-lookup"><span data-stu-id="11037-3474">medical application</span></span> 
- <span data-ttu-id="11037-3475">social insurance</span><span class="sxs-lookup"><span data-stu-id="11037-3475">social insurance</span></span> 
- <span data-ttu-id="11037-3476">medical attention</span><span class="sxs-lookup"><span data-stu-id="11037-3476">medical attention</span></span> 
- <span data-ttu-id="11037-3477">social security</span><span class="sxs-lookup"><span data-stu-id="11037-3477">social security</span></span> 
- <span data-ttu-id="11037-3478">great britain</span><span class="sxs-lookup"><span data-stu-id="11037-3478">great britain</span></span> 
- <span data-ttu-id="11037-3479">金</span><span class="sxs-lookup"><span data-stu-id="11037-3479">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="11037-p145">米国/英国のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-p145">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3482">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3482">Format</span></span>

<span data-ttu-id="11037-3483">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3483">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3484">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3484">Pattern</span></span>

<span data-ttu-id="11037-3485">9 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-3485">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3486">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3486">Checksum</span></span>

<span data-ttu-id="11037-3487">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3487">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3488">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3488">Definition</span></span>

<span data-ttu-id="11037-3489">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3489">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3490">関数 Func_usa_uk_passport がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3490">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3491">Keyword_passport のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3491">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3492">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3492">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="11037-3493">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="11037-3493">Keyword_passport</span></span>

- <span data-ttu-id="11037-3494">Passport Number</span><span class="sxs-lookup"><span data-stu-id="11037-3494">Passport Number</span></span> 
- <span data-ttu-id="11037-3495">Passport No</span><span class="sxs-lookup"><span data-stu-id="11037-3495">Passport No</span></span> 
- <span data-ttu-id="11037-3496">Passport #</span><span class="sxs-lookup"><span data-stu-id="11037-3496">Passport #</span></span> 
- <span data-ttu-id="11037-3497">サインアウト#</span><span class="sxs-lookup"><span data-stu-id="11037-3497">Passport#</span></span> 
- <span data-ttu-id="11037-3498">PassportID</span><span class="sxs-lookup"><span data-stu-id="11037-3498">PassportID</span></span> 
- <span data-ttu-id="11037-3499">Passportno</span><span class="sxs-lookup"><span data-stu-id="11037-3499">Passportno</span></span> 
- <span data-ttu-id="11037-3500">passportnumber</span><span class="sxs-lookup"><span data-stu-id="11037-3500">passportnumber</span></span> 
- <span data-ttu-id="11037-3501">パスポート</span><span class="sxs-lookup"><span data-stu-id="11037-3501">パスポート</span></span> 
- <span data-ttu-id="11037-3502">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="11037-3502">パスポート番号</span></span> 
- <span data-ttu-id="11037-3503">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="11037-3503">パスポートのNum</span></span> 
- <span data-ttu-id="11037-3504">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="11037-3504">パスポート＃</span></span> 
- <span data-ttu-id="11037-3505">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="11037-3505">Numéro de passeport</span></span> 
- <span data-ttu-id="11037-3506">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="11037-3506">Passeport n °</span></span> 
- <span data-ttu-id="11037-3507">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="11037-3507">Passeport Non</span></span> 
- <span data-ttu-id="11037-3508">Passeport #</span><span class="sxs-lookup"><span data-stu-id="11037-3508">Passeport #</span></span> 
- <span data-ttu-id="11037-3509">Passeport#</span><span class="sxs-lookup"><span data-stu-id="11037-3509">Passeport#</span></span> 
- <span data-ttu-id="11037-3510">PasseportNon</span><span class="sxs-lookup"><span data-stu-id="11037-3510">PasseportNon</span></span> 
- <span data-ttu-id="11037-3511">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="11037-3511">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="11037-3512">米国の銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="11037-3512">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3513">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3513">Format</span></span>

<span data-ttu-id="11037-3514">8 ～ 17 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3514">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3515">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3515">Pattern</span></span>

<span data-ttu-id="11037-3516">8 ～ 17 桁の連続する数字</span><span class="sxs-lookup"><span data-stu-id="11037-3516">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3517">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3517">Checksum</span></span>

<span data-ttu-id="11037-3518">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3518">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3519">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3519">Definition</span></span>

<span data-ttu-id="11037-3520">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3520">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3521">正規表現 Regex_usa_bank_account_number は、このパターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="11037-3521">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3522">Keyword_usa_Bank_Account のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3522">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3523">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3523">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="11037-3524">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="11037-3524">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="11037-3525">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-3525">Checking Account Number</span></span> 
- <span data-ttu-id="11037-3526">Checking Account</span><span class="sxs-lookup"><span data-stu-id="11037-3526">Checking Account</span></span> 
- <span data-ttu-id="11037-3527">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="11037-3527">Checking Account #</span></span> 
- <span data-ttu-id="11037-3528">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-3528">Checking Acct Number</span></span> 
- <span data-ttu-id="11037-3529">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-3529">Checking Acct #</span></span> 
- <span data-ttu-id="11037-3530">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-3530">Checking Acct No.</span></span> 
- <span data-ttu-id="11037-3531">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-3531">Checking Account No.</span></span> 
- <span data-ttu-id="11037-3532">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-3532">Bank Account Number</span></span> 
- <span data-ttu-id="11037-3533">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="11037-3533">Bank Account #</span></span> 
- <span data-ttu-id="11037-3534">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-3534">Bank Acct Number</span></span> 
- <span data-ttu-id="11037-3535">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-3535">Bank Acct #</span></span> 
- <span data-ttu-id="11037-3536">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-3536">Bank Acct No.</span></span> 
- <span data-ttu-id="11037-3537">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-3537">Bank Account No.</span></span> 
- <span data-ttu-id="11037-3538">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-3538">Savings Account Number</span></span> 
- <span data-ttu-id="11037-3539">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="11037-3539">Savings Account.</span></span> 
- <span data-ttu-id="11037-3540">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="11037-3540">Savings Account #</span></span> 
- <span data-ttu-id="11037-3541">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-3541">Savings Acct Number</span></span> 
- <span data-ttu-id="11037-3542">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-3542">Savings Acct #</span></span> 
- <span data-ttu-id="11037-3543">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-3543">Savings Acct No.</span></span> 
- <span data-ttu-id="11037-3544">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-3544">Savings Account No.</span></span> 
- <span data-ttu-id="11037-3545">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="11037-3545">Debit Account Number</span></span> 
- <span data-ttu-id="11037-3546">Debit Account</span><span class="sxs-lookup"><span data-stu-id="11037-3546">Debit Account</span></span> 
- <span data-ttu-id="11037-3547">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="11037-3547">Debit Account #</span></span> 
- <span data-ttu-id="11037-3548">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="11037-3548">Debit Acct Number</span></span> 
- <span data-ttu-id="11037-3549">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="11037-3549">Debit Acct #</span></span> 
- <span data-ttu-id="11037-3550">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="11037-3550">Debit Acct No.</span></span> 
- <span data-ttu-id="11037-3551">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="11037-3551">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="11037-3552">米国の運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="11037-3552">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="11037-3553">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3553">Format</span></span>

<span data-ttu-id="11037-3554">州に応じて異なる</span><span class="sxs-lookup"><span data-stu-id="11037-3554">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3555">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3555">Pattern</span></span>

<span data-ttu-id="11037-3556">州に応じて異なる - ニューヨークの場合:</span><span class="sxs-lookup"><span data-stu-id="11037-3556">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="11037-3557">Ddd ddd ddd のような形式の9桁の数字は一致します。</span><span class="sxs-lookup"><span data-stu-id="11037-3557">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="11037-3558">Ddddddddd のように9桁の数字は一致しません。</span><span class="sxs-lookup"><span data-stu-id="11037-3558">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3559">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3559">Checksum</span></span>

<span data-ttu-id="11037-3560">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3560">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3561">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3561">Definition</span></span>

<span data-ttu-id="11037-3562">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3562">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3563">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3563">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3564">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3564">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="11037-3565">Keyword_us_drivers_license からのキーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="11037-3565">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="11037-3566">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3566">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3567">関数 Func_new_york_drivers_license_number がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3567">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3568">Keyword_[state_name]_drivers_license_name のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3568">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="11037-3569">Keyword_us_drivers_license_abbreviations のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3569">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="11037-3570">Keyword_us_drivers_license のキーワードを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-3570">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3571">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3571">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="11037-3572">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="11037-3572">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="11037-3573">DL</span><span class="sxs-lookup"><span data-stu-id="11037-3573">DL</span></span> 
- <span data-ttu-id="11037-3574">DL</span><span class="sxs-lookup"><span data-stu-id="11037-3574">DLS</span></span> 
- <span data-ttu-id="11037-3575">CDL</span><span class="sxs-lookup"><span data-stu-id="11037-3575">CDL</span></span> 
- <span data-ttu-id="11037-3576">CDLS</span><span class="sxs-lookup"><span data-stu-id="11037-3576">CDLS</span></span> 
- <span data-ttu-id="11037-3577">ID</span><span class="sxs-lookup"><span data-stu-id="11037-3577">ID</span></span> 
- <span data-ttu-id="11037-3578">Rid</span><span class="sxs-lookup"><span data-stu-id="11037-3578">IDs</span></span> 
- <span data-ttu-id="11037-3579">DL#</span><span class="sxs-lookup"><span data-stu-id="11037-3579">DL#</span></span> 
- <span data-ttu-id="11037-3580">DL#</span><span class="sxs-lookup"><span data-stu-id="11037-3580">DLS#</span></span> 
- <span data-ttu-id="11037-3581">CDL#</span><span class="sxs-lookup"><span data-stu-id="11037-3581">CDL#</span></span> 
- <span data-ttu-id="11037-3582">CDLS#</span><span class="sxs-lookup"><span data-stu-id="11037-3582">CDLS#</span></span> 
- <span data-ttu-id="11037-3583">RID#</span><span class="sxs-lookup"><span data-stu-id="11037-3583">ID#</span></span>
- <span data-ttu-id="11037-3584">Rid#</span><span class="sxs-lookup"><span data-stu-id="11037-3584">IDs#</span></span> 
- <span data-ttu-id="11037-3585">ID number</span><span class="sxs-lookup"><span data-stu-id="11037-3585">ID number</span></span> 
- <span data-ttu-id="11037-3586">ID numbers</span><span class="sxs-lookup"><span data-stu-id="11037-3586">ID numbers</span></span> 
- <span data-ttu-id="11037-3587">そして</span><span class="sxs-lookup"><span data-stu-id="11037-3587">LIC</span></span> 
- <span data-ttu-id="11037-3588">そして#</span><span class="sxs-lookup"><span data-stu-id="11037-3588">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="11037-3589">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="11037-3589">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="11037-3590">DriverLic</span><span class="sxs-lookup"><span data-stu-id="11037-3590">DriverLic</span></span> 
- <span data-ttu-id="11037-3591">DriverLics</span><span class="sxs-lookup"><span data-stu-id="11037-3591">DriverLics</span></span> 
- <span data-ttu-id="11037-3592">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="11037-3592">DriverLicense</span></span> 
- <span data-ttu-id="11037-3593">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="11037-3593">DriverLicenses</span></span> 
- <span data-ttu-id="11037-3594">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="11037-3594">Driver Lic</span></span> 
- <span data-ttu-id="11037-3595">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="11037-3595">Driver Lics</span></span> 
- <span data-ttu-id="11037-3596">Driver License</span><span class="sxs-lookup"><span data-stu-id="11037-3596">Driver License</span></span> 
- <span data-ttu-id="11037-3597">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-3597">Driver Licenses</span></span> 
- <span data-ttu-id="11037-3598">DriversLic</span><span class="sxs-lookup"><span data-stu-id="11037-3598">DriversLic</span></span> 
- <span data-ttu-id="11037-3599">DriversLics</span><span class="sxs-lookup"><span data-stu-id="11037-3599">DriversLics</span></span> 
- <span data-ttu-id="11037-3600">製品の使用許諾</span><span class="sxs-lookup"><span data-stu-id="11037-3600">DriversLicense</span></span> 
- <span data-ttu-id="11037-3601">このライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-3601">DriversLicenses</span></span> 
- <span data-ttu-id="11037-3602">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="11037-3602">Drivers Lic</span></span> 
- <span data-ttu-id="11037-3603">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="11037-3603">Drivers Lics</span></span> 
- <span data-ttu-id="11037-3604">Drivers License</span><span class="sxs-lookup"><span data-stu-id="11037-3604">Drivers License</span></span> 
- <span data-ttu-id="11037-3605">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-3605">Drivers Licenses</span></span> 
- <span data-ttu-id="11037-3606">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="11037-3606">Driver'Lic</span></span> 
- <span data-ttu-id="11037-3607">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="11037-3607">Driver'Lics</span></span> 
- <span data-ttu-id="11037-3608">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-3608">Driver'License</span></span> 
- <span data-ttu-id="11037-3609">Driver' ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-3609">Driver'Licenses</span></span> 
- <span data-ttu-id="11037-3610">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="11037-3610">Driver' Lic</span></span> 
- <span data-ttu-id="11037-3611">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="11037-3611">Driver' Lics</span></span> 
- <span data-ttu-id="11037-3612">Driver' License</span><span class="sxs-lookup"><span data-stu-id="11037-3612">Driver' License</span></span> 
- <span data-ttu-id="11037-3613">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-3613">Driver' Licenses</span></span>
- <span data-ttu-id="11037-3614">Driver' Slic</span><span class="sxs-lookup"><span data-stu-id="11037-3614">Driver'sLic</span></span> 
- <span data-ttu-id="11037-3615">Driver' Slics</span><span class="sxs-lookup"><span data-stu-id="11037-3615">Driver'sLics</span></span> 
- <span data-ttu-id="11037-3616">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-3616">Driver'sLicense</span></span> 
- <span data-ttu-id="11037-3617">ドライバのライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-3617">Driver'sLicenses</span></span> 
- <span data-ttu-id="11037-3618">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="11037-3618">Driver's Lic</span></span> 
- <span data-ttu-id="11037-3619">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="11037-3619">Driver's Lics</span></span> 
- <span data-ttu-id="11037-3620">Driver's License</span><span class="sxs-lookup"><span data-stu-id="11037-3620">Driver's License</span></span> 
- <span data-ttu-id="11037-3621">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="11037-3621">Driver's Licenses</span></span> 
- <span data-ttu-id="11037-3622">identification number</span><span class="sxs-lookup"><span data-stu-id="11037-3622">identification number</span></span> 
- <span data-ttu-id="11037-3623">identification numbers</span><span class="sxs-lookup"><span data-stu-id="11037-3623">identification numbers</span></span> 
- <span data-ttu-id="11037-3624">identification #</span><span class="sxs-lookup"><span data-stu-id="11037-3624">identification #</span></span> 
- <span data-ttu-id="11037-3625">id card</span><span class="sxs-lookup"><span data-stu-id="11037-3625">id card</span></span> 
- <span data-ttu-id="11037-3626">id cards</span><span class="sxs-lookup"><span data-stu-id="11037-3626">id cards</span></span> 
- <span data-ttu-id="11037-3627">identification card</span><span class="sxs-lookup"><span data-stu-id="11037-3627">identification card</span></span> 
- <span data-ttu-id="11037-3628">identification cards</span><span class="sxs-lookup"><span data-stu-id="11037-3628">identification cards</span></span> 
- <span data-ttu-id="11037-3629">DriverLic#</span><span class="sxs-lookup"><span data-stu-id="11037-3629">DriverLic#</span></span> 
- <span data-ttu-id="11037-3630">DriverLics#</span><span class="sxs-lookup"><span data-stu-id="11037-3630">DriverLics#</span></span> 
- <span data-ttu-id="11037-3631">DriverLicense#</span><span class="sxs-lookup"><span data-stu-id="11037-3631">DriverLicense#</span></span> 
- <span data-ttu-id="11037-3632">DriverLicenses#</span><span class="sxs-lookup"><span data-stu-id="11037-3632">DriverLicenses#</span></span> 
- <span data-ttu-id="11037-3633">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-3633">Driver Lic#</span></span> 
- <span data-ttu-id="11037-3634">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-3634">Driver Lics#</span></span> 
- <span data-ttu-id="11037-3635">Driver License#</span><span class="sxs-lookup"><span data-stu-id="11037-3635">Driver License#</span></span> 
- <span data-ttu-id="11037-3636">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-3636">Driver Licenses#</span></span> 
- <span data-ttu-id="11037-3637">DriversLic#</span><span class="sxs-lookup"><span data-stu-id="11037-3637">DriversLic#</span></span> 
- <span data-ttu-id="11037-3638">DriversLics#</span><span class="sxs-lookup"><span data-stu-id="11037-3638">DriversLics#</span></span> 
- <span data-ttu-id="11037-3639">製品の使用許諾#</span><span class="sxs-lookup"><span data-stu-id="11037-3639">DriversLicense#</span></span> 
- <span data-ttu-id="11037-3640">このライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-3640">DriversLicenses#</span></span> 
- <span data-ttu-id="11037-3641">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-3641">Drivers Lic#</span></span> 
- <span data-ttu-id="11037-3642">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-3642">Drivers Lics#</span></span> 
- <span data-ttu-id="11037-3643">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="11037-3643">Drivers License#</span></span> 
- <span data-ttu-id="11037-3644">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-3644">Drivers Licenses#</span></span> 
- <span data-ttu-id="11037-3645">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-3645">Driver'Lic#</span></span> 
- <span data-ttu-id="11037-3646">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-3646">Driver'Lics#</span></span> 
- <span data-ttu-id="11037-3647">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-3647">Driver'License#</span></span> 
- <span data-ttu-id="11037-3648">Driver' ライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-3648">Driver'Licenses#</span></span> 
- <span data-ttu-id="11037-3649">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-3649">Driver' Lic#</span></span> 
- <span data-ttu-id="11037-3650">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-3650">Driver' Lics#</span></span> 
- <span data-ttu-id="11037-3651">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="11037-3651">Driver' License#</span></span> 
- <span data-ttu-id="11037-3652">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-3652">Driver' Licenses#</span></span> 
- <span data-ttu-id="11037-3653">Driver' Slic#</span><span class="sxs-lookup"><span data-stu-id="11037-3653">Driver'sLic#</span></span> 
- <span data-ttu-id="11037-3654">Driver' Slics#</span><span class="sxs-lookup"><span data-stu-id="11037-3654">Driver'sLics#</span></span> 
- <span data-ttu-id="11037-3655">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-3655">Driver'sLicense#</span></span> 
- <span data-ttu-id="11037-3656">ドライバのライセンス#</span><span class="sxs-lookup"><span data-stu-id="11037-3656">Driver'sLicenses#</span></span> 
- <span data-ttu-id="11037-3657">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="11037-3657">Driver's Lic#</span></span> 
- <span data-ttu-id="11037-3658">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="11037-3658">Driver's Lics#</span></span> 
- <span data-ttu-id="11037-3659">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="11037-3659">Driver's License#</span></span> 
- <span data-ttu-id="11037-3660">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="11037-3660">Driver's Licenses#</span></span> 
- <span data-ttu-id="11037-3661">id card#</span><span class="sxs-lookup"><span data-stu-id="11037-3661">id card#</span></span> 
- <span data-ttu-id="11037-3662">id cards#</span><span class="sxs-lookup"><span data-stu-id="11037-3662">id cards#</span></span> 
- <span data-ttu-id="11037-3663">identification card#</span><span class="sxs-lookup"><span data-stu-id="11037-3663">identification card#</span></span> 
- <span data-ttu-id="11037-3664">identification cards#</span><span class="sxs-lookup"><span data-stu-id="11037-3664">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="11037-3665">Keyword_[state_name]_drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="11037-3665">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="11037-3666">州の略号 (たとえば、"NY")</span><span class="sxs-lookup"><span data-stu-id="11037-3666">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="11037-3667">州の名前 (たとえば、"New York")</span><span class="sxs-lookup"><span data-stu-id="11037-3667">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="11037-3668">米国の個人納税者識別番号 (ITIN)</span><span class="sxs-lookup"><span data-stu-id="11037-3668">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="11037-3669">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3669">Format</span></span>

<span data-ttu-id="11037-3670">「9」で始まる 9 桁の数字、4 桁目は「7」または「8」、スペースまたはスラッシュによる書式設定は省略可能</span><span class="sxs-lookup"><span data-stu-id="11037-3670">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3671">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3671">Pattern</span></span>

<span data-ttu-id="11037-3672">さ</span><span class="sxs-lookup"><span data-stu-id="11037-3672">Formatted:</span></span>
- <span data-ttu-id="11037-3673">数字「9」</span><span class="sxs-lookup"><span data-stu-id="11037-3673">The digit "9"</span></span> 
- <span data-ttu-id="11037-3674">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3674">Two digits</span></span> 
- <span data-ttu-id="11037-3675">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-3675">A space or dash</span></span> 
- <span data-ttu-id="11037-3676">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="11037-3676">A "7" or "8"</span></span> 
- <span data-ttu-id="11037-3677">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3677">A digit</span></span> 
- <span data-ttu-id="11037-3678">スペースまたはダッシュ</span><span class="sxs-lookup"><span data-stu-id="11037-3678">A space, or dash</span></span> 
- <span data-ttu-id="11037-3679">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3679">Four digits</span></span>

<span data-ttu-id="11037-3680">なし</span><span class="sxs-lookup"><span data-stu-id="11037-3680">Unformatted:</span></span>
- <span data-ttu-id="11037-3681">数字「9」</span><span class="sxs-lookup"><span data-stu-id="11037-3681">The digit "9"</span></span> 
- <span data-ttu-id="11037-3682">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3682">Two digits</span></span> 
- <span data-ttu-id="11037-3683">「7」または「8」</span><span class="sxs-lookup"><span data-stu-id="11037-3683">A "7" or "8"</span></span> 
- <span data-ttu-id="11037-3684">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3684">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3685">Checksum</span></span>

<span data-ttu-id="11037-3686">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3686">No</span></span>

### <a name="definition"></a><span data-ttu-id="11037-3687">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3687">Definition</span></span>

<span data-ttu-id="11037-3688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3689">関数 Func_formatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3689">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3690">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-3690">At least one of the following is true:</span></span>
    - <span data-ttu-id="11037-3691">Keyword_itin のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3691">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="11037-3692">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3692">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="11037-3693">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3693">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="11037-3694">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3694">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="11037-3695">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3695">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3696">関数 Func_unformatted_itin がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3696">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3697">次の条件のうち 1 つ以上に該当する:</span><span class="sxs-lookup"><span data-stu-id="11037-3697">At least one of the following is true:</span></span>
    - <span data-ttu-id="11037-3698">Keyword_itin_collaborative のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3698">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="11037-3699">関数 Func_us_address が適切な形式の住所を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3699">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="11037-3700">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3700">The function Func_us_date finds a date in the right date format.</span></span>

```xml
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

### <a name="keywords"></a><span data-ttu-id="11037-3701">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3701">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="11037-3702">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="11037-3702">Keyword_itin</span></span>

- <span data-ttu-id="11037-3703">納税</span><span class="sxs-lookup"><span data-stu-id="11037-3703">taxpayer</span></span> 
- <span data-ttu-id="11037-3704">tax id</span><span class="sxs-lookup"><span data-stu-id="11037-3704">tax id</span></span> 
- <span data-ttu-id="11037-3705">tax identification</span><span class="sxs-lookup"><span data-stu-id="11037-3705">tax identification</span></span> 
- <span data-ttu-id="11037-3706">itin</span><span class="sxs-lookup"><span data-stu-id="11037-3706">itin</span></span> 
- <span data-ttu-id="11037-3707">ssn</span><span class="sxs-lookup"><span data-stu-id="11037-3707">ssn</span></span> 
- <span data-ttu-id="11037-3708">は</span><span class="sxs-lookup"><span data-stu-id="11037-3708">tin</span></span> 
- <span data-ttu-id="11037-3709">social security</span><span class="sxs-lookup"><span data-stu-id="11037-3709">social security</span></span> 
- <span data-ttu-id="11037-3710">tax payer</span><span class="sxs-lookup"><span data-stu-id="11037-3710">tax payer</span></span> 
- <span data-ttu-id="11037-3711">itins</span><span class="sxs-lookup"><span data-stu-id="11037-3711">itins</span></span> 
- <span data-ttu-id="11037-3712">taxid</span><span class="sxs-lookup"><span data-stu-id="11037-3712">taxid</span></span> 
- <span data-ttu-id="11037-3713">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="11037-3713">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="11037-3714">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="11037-3714">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="11037-3715">ライセンス</span><span class="sxs-lookup"><span data-stu-id="11037-3715">License</span></span> 
- <span data-ttu-id="11037-3716">DL</span><span class="sxs-lookup"><span data-stu-id="11037-3716">DL</span></span> 
- <span data-ttu-id="11037-3717">DOB</span><span class="sxs-lookup"><span data-stu-id="11037-3717">DOB</span></span> 
- <span data-ttu-id="11037-3718">誕生日</span><span class="sxs-lookup"><span data-stu-id="11037-3718">Birthdate</span></span> 
- <span data-ttu-id="11037-3719">Birthday</span><span class="sxs-lookup"><span data-stu-id="11037-3719">Birthday</span></span> 
- <span data-ttu-id="11037-3720">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="11037-3720">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="11037-3721">米国の社会保障番号 (SSN)</span><span class="sxs-lookup"><span data-stu-id="11037-3721">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="11037-3722">Format</span><span class="sxs-lookup"><span data-stu-id="11037-3722">Format</span></span>

<span data-ttu-id="11037-3723">書式設定ありまたは書式設定なしの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="11037-3723">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="11037-3724">2011より前に発行された場合、SSN の書式には、特定の範囲内にある特定の範囲内にある必要があり、チェックサムがないという厳密な形式があります。</span><span class="sxs-lookup"><span data-stu-id="11037-3724">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="11037-3725">パターン</span><span class="sxs-lookup"><span data-stu-id="11037-3725">Pattern</span></span>

<span data-ttu-id="11037-3726">次の4つの異なるパターンで SSNs を検索する4つの関数があります。</span><span class="sxs-lookup"><span data-stu-id="11037-3726">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="11037-3727">Func_ssn は、2011 年以前の厳密な書式の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="11037-3727">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="11037-3728">Func_unformatted_ssn は、2011 年以前の厳密な書式の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="11037-3728">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="11037-3729">Func_randomized_formatted_ssn は、2011 年以降の SSN を検索します。これはダッシュまたはスペース (ddd-dd-dddd または ddd dd dddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="11037-3729">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="11037-3730">Func_randomized_unformatted_ssn は、2011 年以降の SSN を検索します。これは 9 桁の連続した数字 (ddddddddd) の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="11037-3730">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="11037-3731">チェックサム</span><span class="sxs-lookup"><span data-stu-id="11037-3731">Checksum</span></span>

<span data-ttu-id="11037-3732">いいえ</span><span class="sxs-lookup"><span data-stu-id="11037-3732">No</span></span>


### <a name="definition"></a><span data-ttu-id="11037-3733">定義</span><span class="sxs-lookup"><span data-stu-id="11037-3733">Definition</span></span>

<span data-ttu-id="11037-3734">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3735">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3735">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3736">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3736">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="11037-3737">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3737">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-3738">関数 Func_us_address は、アドレスを正しい形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3738">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="11037-3739">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3739">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3740">関数 Func_unformatted_ssn は、このパターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3740">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3741">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3741">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="11037-3742">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3742">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-3743">関数 Func_us_address は、アドレスを正しい形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3743">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="11037-3744">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3744">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3745">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3745">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3746">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3746">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="11037-3747">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3747">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-3748">関数 Func_us_address は、アドレスを正しい形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3748">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="11037-3749">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に 55% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="11037-3749">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3750">関数 Func_randomized_unformatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3750">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3751">Keyword_ssn のキーワードを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3751">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="11037-3752">関数 Func_us_date が適切な日付形式の日付を検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3752">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="11037-3753">関数 Func_us_address は、アドレスを正しい形式で検索します。</span><span class="sxs-lookup"><span data-stu-id="11037-3753">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="11037-3754">DLP ポリシーの信頼度は 40% で、この種類の機密情報は、近接する300文字内で検出されます。</span><span class="sxs-lookup"><span data-stu-id="11037-3754">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="11037-3755">関数 Func_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3755">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3756">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-3756">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3757">関数 Func_randomized_unformatted_ssn は、このパターンに一致するコンテンツを検出しません。</span><span class="sxs-lookup"><span data-stu-id="11037-3757">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3758">Keyword_ssn からのキーワードが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="11037-3758">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="11037-3759">または</span><span class="sxs-lookup"><span data-stu-id="11037-3759">Or</span></span>

- <span data-ttu-id="11037-3760">関数 Func_randomized_formatted_ssn がパターンに一致するコンテンツを検出した。</span><span class="sxs-lookup"><span data-stu-id="11037-3760">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3761">関数 Func_unformatted_ssn がパターンに一致するコンテンツを検出しなかった。</span><span class="sxs-lookup"><span data-stu-id="11037-3761">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3762">関数 Func_randomized_unformatted_ssn は、このパターンに一致するコンテンツを検出しません。</span><span class="sxs-lookup"><span data-stu-id="11037-3762">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="11037-3763">Keyword_ssn からのキーワードが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="11037-3763">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="11037-3764">キーワード</span><span class="sxs-lookup"><span data-stu-id="11037-3764">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="11037-3765">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="11037-3765">Keyword_ssn</span></span>

- <span data-ttu-id="11037-3766">Social Security</span><span class="sxs-lookup"><span data-stu-id="11037-3766">Social Security</span></span> 
- <span data-ttu-id="11037-3767">Social Security#</span><span class="sxs-lookup"><span data-stu-id="11037-3767">Social Security#</span></span> 
- <span data-ttu-id="11037-3768">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="11037-3768">Soc Sec</span></span> 
- <span data-ttu-id="11037-3769">SSN</span><span class="sxs-lookup"><span data-stu-id="11037-3769">SSN</span></span> 
- <span data-ttu-id="11037-3770">SSN</span><span class="sxs-lookup"><span data-stu-id="11037-3770">SSNS</span></span> 
- <span data-ttu-id="11037-3771">SSN#</span><span class="sxs-lookup"><span data-stu-id="11037-3771">SSN#</span></span> 
- <span data-ttu-id="11037-3772">秒#</span><span class="sxs-lookup"><span data-stu-id="11037-3772">SS#</span></span> 
- <span data-ttu-id="11037-3773">SSID</span><span class="sxs-lookup"><span data-stu-id="11037-3773">SSID</span></span> 
   

