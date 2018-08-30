---
title: EU 国民 Id 番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 2ea971bf-9434-4b61-b825-2bbd28ae6064
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 国の識別番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 29d2126b937ff46039284a74eb2a84f2ebbacb41
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532090"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="b306e-104">EU 国民 Id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-104">EU National Identification Number</span></span>

<span data-ttu-id="b306e-p102">このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 国の識別番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。</span><span class="sxs-lookup"><span data-stu-id="b306e-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="b306e-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="b306e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="b306e-108">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-108">Format</span></span>

<span data-ttu-id="b306e-109">文字、数字、特殊文字の 24 文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="b306e-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-110">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-110">Pattern</span></span>

<span data-ttu-id="b306e-111">24 文字。</span><span class="sxs-lookup"><span data-stu-id="b306e-111">24 characters:</span></span>
  
-  <span data-ttu-id="b306e-112">22 の文字列の文字、数字、円記号 ()、スラッシュ、またはプラス記号</span><span class="sxs-lookup"><span data-stu-id="b306e-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="b306e-113">(いない大文字小文字を区別) の 2 つの文字、数字、円記号 ()、スラッシュのプラス記号または等号</span><span class="sxs-lookup"><span data-stu-id="b306e-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-114">Checksum</span></span>

<span data-ttu-id="b306e-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="b306e-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-116">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-116">Definition</span></span>

<span data-ttu-id="b306e-117">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-118">正規表現`Regex_austria_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-119">キーワードの`Keywords_austria_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-120">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="b306e-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="b306e-122">オーストリアの id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-122">austrian identity number</span></span>
  
<span data-ttu-id="b306e-123">国内の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-123">national identity number</span></span>
  
<span data-ttu-id="b306e-124">id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-124">identity number</span></span>
  
<span data-ttu-id="b306e-125">
national id</span><span class="sxs-lookup"><span data-stu-id="b306e-125">national id</span></span>
  
<span data-ttu-id="b306e-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="b306e-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="b306e-127">ベルギー</span><span class="sxs-lookup"><span data-stu-id="b306e-127">Belgium</span></span>

<span data-ttu-id="b306e-128">詳細についてを参照してください「ベルギーの国番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="b306e-129">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="b306e-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="b306e-130">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-130">Format</span></span>

<span data-ttu-id="b306e-131">スペースや区切り記号なしの 10 桁</span><span class="sxs-lookup"><span data-stu-id="b306e-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-132">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-132">Pattern</span></span>

<span data-ttu-id="b306e-133">スペースや区切り記号なしの 10 桁</span><span class="sxs-lookup"><span data-stu-id="b306e-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="b306e-134">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="b306e-135">誕生の順序に対応する 2 つの数字</span><span class="sxs-lookup"><span data-stu-id="b306e-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="b306e-136">性別に対応する 1 つの数字: 男性と女性の場合、奇数桁の偶数</span><span class="sxs-lookup"><span data-stu-id="b306e-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="b306e-137">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-138">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-138">Checksum</span></span>

<span data-ttu-id="b306e-139">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-140">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-140">Definition</span></span>

<span data-ttu-id="b306e-141">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-142">関数`Func_bulgaria_national_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-143">キーワードの`Keywords_bulgaria_national_number`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="b306e-144">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-145">関数`Func_bulgaria_national_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_national_number" />
          <Match idRef="Keywords_bulgaria_national_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-146">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="b306e-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="b306e-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="b306e-148">egn</span><span class="sxs-lookup"><span data-stu-id="b306e-148">egn</span></span>
  
<span data-ttu-id="b306e-149">egn #</span><span class="sxs-lookup"><span data-stu-id="b306e-149">egn#</span></span>
  
<span data-ttu-id="b306e-150">ブルガリアの国番号</span><span class="sxs-lookup"><span data-stu-id="b306e-150">bulgarian national number</span></span>
  
<span data-ttu-id="b306e-151">国番号</span><span class="sxs-lookup"><span data-stu-id="b306e-151">national number</span></span>
  
<span data-ttu-id="b306e-152">social security number
</span><span class="sxs-lookup"><span data-stu-id="b306e-152">social security number</span></span>
  
<span data-ttu-id="b306e-153">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-153">nationalnumber#</span></span>
  
<span data-ttu-id="b306e-154">ssn #</span><span class="sxs-lookup"><span data-stu-id="b306e-154">ssn#</span></span>
  
<span data-ttu-id="b306e-155">ssn</span><span class="sxs-lookup"><span data-stu-id="b306e-155">ssn</span></span>
  
<span data-ttu-id="b306e-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="b306e-156">nationalnumber</span></span>
  
<span data-ttu-id="b306e-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="b306e-157">bnn#</span></span>
  
<span data-ttu-id="b306e-158">bnn</span><span class="sxs-lookup"><span data-stu-id="b306e-158">bnn</span></span>
  
<span data-ttu-id="b306e-159">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-159">personal id number</span></span>
  
<span data-ttu-id="b306e-160">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-160">personalidnumber#</span></span>
  
<span data-ttu-id="b306e-161">ЕДИНЕН ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="b306e-161">единен граждански номер</span></span>
  
<span data-ttu-id="b306e-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="b306e-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="b306e-163">ЕГН</span><span class="sxs-lookup"><span data-stu-id="b306e-163">егн</span></span>
  
<span data-ttu-id="b306e-164">ЕГН #</span><span class="sxs-lookup"><span data-stu-id="b306e-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="b306e-165">クロアチア</span><span class="sxs-lookup"><span data-stu-id="b306e-165">Croatia</span></span>

<span data-ttu-id="b306e-166">詳細についてを参照してください「クロアチア Id 番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="b306e-167">キプロス</span><span class="sxs-lookup"><span data-stu-id="b306e-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="b306e-168">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-168">Format</span></span>

<span data-ttu-id="b306e-169">スペースや区切り記号なしの 10 桁</span><span class="sxs-lookup"><span data-stu-id="b306e-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-170">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-170">Pattern</span></span>

 <span data-ttu-id="b306e-171">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b306e-172">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-172">Checksum</span></span>

<span data-ttu-id="b306e-173">該当なし</span><span class="sxs-lookup"><span data-stu-id="b306e-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-174">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-174">Definition</span></span>

<span data-ttu-id="b306e-175">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-176">正規表現`Regex_cyprus_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-177">キーワードの`Keywords_cyprus_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-178">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="b306e-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="b306e-180">id のカード番号</span><span class="sxs-lookup"><span data-stu-id="b306e-180">id card number</span></span>
  
<span data-ttu-id="b306e-181">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-181">national identification number</span></span>
  
<span data-ttu-id="b306e-182">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-182">personal id number</span></span>
  
<span data-ttu-id="b306e-183">身分証明書番号</span><span class="sxs-lookup"><span data-stu-id="b306e-183">identity card number</span></span>
  
<span data-ttu-id="b306e-184">ΤΑΥΤΟΤΗΤΑΣ</span><span class="sxs-lookup"><span data-stu-id="b306e-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="b306e-185">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="b306e-185">Czech Republic</span></span>

<span data-ttu-id="b306e-186">詳細についてを参照してください「チェコ国内の Id 番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="b306e-187">デンマーク</span><span class="sxs-lookup"><span data-stu-id="b306e-187">Denmark</span></span>

<span data-ttu-id="b306e-188">詳細についてを参照してください「千葉県個人識別番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="b306e-189">エストニア</span><span class="sxs-lookup"><span data-stu-id="b306e-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="b306e-190">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-190">Format</span></span>

<span data-ttu-id="b306e-191">スペースや区切り記号なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-192">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-192">Pattern</span></span>

<span data-ttu-id="b306e-193">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b306e-193">11 digits:</span></span>
  
- <span data-ttu-id="b306e-194">性別と生年月日の世紀に対応する 1 つの数字 (奇数番号 (オス)、偶数 (メス); 1-2: 19 世紀; 3-4: 20 世紀; 5-6: 21 世紀)</span><span class="sxs-lookup"><span data-stu-id="b306e-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="b306e-195">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="b306e-196">シリアル番号が同じ日に生まれた人を分離することに対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="b306e-197">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-198">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-198">Checksum</span></span>

<span data-ttu-id="b306e-199">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-200">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-200">Definition</span></span>

<span data-ttu-id="b306e-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-202">関数`Func_estonia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-203">キーワードの`Keywords_estonia_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-204">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-205">関数`Func_estonia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
          <Match idRef="Keywords_estonia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-206">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="b306e-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="b306e-208">個人識別コード</span><span class="sxs-lookup"><span data-stu-id="b306e-208">personal identification code</span></span>
  
<span data-ttu-id="b306e-209">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-209">personal identification number</span></span>
  
<span data-ttu-id="b306e-210">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-210">national identification number</span></span>
  
<span data-ttu-id="b306e-211">国番号</span><span class="sxs-lookup"><span data-stu-id="b306e-211">national number</span></span>
  
<span data-ttu-id="b306e-212">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-212">personal id number</span></span>
  
<span data-ttu-id="b306e-213">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-213">personalidnumber#</span></span>
  
<span data-ttu-id="b306e-214">ik</span><span class="sxs-lookup"><span data-stu-id="b306e-214">ik</span></span>
  
<span data-ttu-id="b306e-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="b306e-215">isikukood</span></span>
  
<span data-ttu-id="b306e-216">id kaart</span><span class="sxs-lookup"><span data-stu-id="b306e-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="b306e-217">フィンランド</span><span class="sxs-lookup"><span data-stu-id="b306e-217">Finland</span></span>

<span data-ttu-id="b306e-218">詳細についてを参照してください「フィンランドの国民 ID」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="b306e-219">フランス</span><span class="sxs-lookup"><span data-stu-id="b306e-219">France</span></span>

<span data-ttu-id="b306e-220">詳細についてを参照してください「フランス国内の ID カードいます (CNI)」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="b306e-221">ドイツ</span><span class="sxs-lookup"><span data-stu-id="b306e-221">Germany</span></span>

<span data-ttu-id="b306e-222">詳細についてを参照してください"ドイツの Id カードの番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="b306e-223">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="b306e-223">Greece</span></span>

<span data-ttu-id="b306e-224">詳細についてを参照してください「ギリシャ国内の ID カード」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="b306e-225">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="b306e-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="b306e-226">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-226">Format</span></span>

<span data-ttu-id="b306e-227">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-228">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-228">Pattern</span></span>

<span data-ttu-id="b306e-229">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b306e-229">11 digits:</span></span>
  
-  <span data-ttu-id="b306e-230">(1 男性 2 女性、その他の番号が 1900 年より前に生まれた市民や二重市民権を持つ市民も) 性別に対応する 1 つの数字</span><span class="sxs-lookup"><span data-stu-id="b306e-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="b306e-231">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="b306e-232">シリアル番号に対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="b306e-233">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-234">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-234">Checksum</span></span>

<span data-ttu-id="b306e-235">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-236">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-236">Definition</span></span>

<span data-ttu-id="b306e-237">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-238">関数`Func_hungary_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-239">キーワードの`Keywords_hungary_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-240">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-241">関数`Func_hungary_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
          <Match idRef="Keywords_hungary_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_national_id_card" />
</Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-242">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="b306e-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="b306e-244">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-244">personal identification number</span></span>
  
<span data-ttu-id="b306e-245">identification number
</span><span class="sxs-lookup"><span data-stu-id="b306e-245">identification number</span></span>
  
<span data-ttu-id="b306e-246">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-246">personal id number</span></span>
  
<span data-ttu-id="b306e-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="b306e-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="b306e-248">Ireland</span><span class="sxs-lookup"><span data-stu-id="b306e-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="b306e-249">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-249">Format</span></span>

<span data-ttu-id="b306e-250">文字、数字、および指定したパターンにスペースの 9 文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="b306e-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-251">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-251">Pattern</span></span>

<span data-ttu-id="b306e-252">文字、数字、および指定したパターンにスペースの 9 文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="b306e-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="b306e-253">現在までの 01 年 2013年 1 月。</span><span class="sxs-lookup"><span data-stu-id="b306e-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="b306e-254">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="b306e-254">Seven digits</span></span> 
    
- <span data-ttu-id="b306e-255">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-255">One check digit</span></span>
    
- <span data-ttu-id="b306e-256">1 つのスペースや大文字の"W"(大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="b306e-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="b306e-257">前の 01 年 2013年 1 月:</span><span class="sxs-lookup"><span data-stu-id="b306e-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="b306e-258">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="b306e-258">Seven digits</span></span> 
    
- <span data-ttu-id="b306e-259">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-259">One check digit</span></span>
    
- <span data-ttu-id="b306e-260">1 つのスペースや大文字の文字 (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="b306e-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-261">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-261">Checksum</span></span>

<span data-ttu-id="b306e-262">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-263">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-263">Definition</span></span>

<span data-ttu-id="b306e-264">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-265">関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="b306e-266">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="b306e-266">A keyword from is found.</span></span>
    
<span data-ttu-id="b306e-267">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-268">関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-268">The function finds content that matches the pattern.</span></span>
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
          <Match idRef="Keywords_ireland_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-269">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="b306e-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="b306e-271">個人の公的サービスの数</span><span class="sxs-lookup"><span data-stu-id="b306e-271">personal public service number</span></span>
  
<span data-ttu-id="b306e-272">pps なし</span><span class="sxs-lookup"><span data-stu-id="b306e-272">pps no</span></span>
  
<span data-ttu-id="b306e-273">収益と社会保険番号</span><span class="sxs-lookup"><span data-stu-id="b306e-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="b306e-274">rsi なし</span><span class="sxs-lookup"><span data-stu-id="b306e-274">rsi no</span></span>
  
<span data-ttu-id="b306e-275">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-275">personal identification number</span></span>
  
<span data-ttu-id="b306e-276">identification number
</span><span class="sxs-lookup"><span data-stu-id="b306e-276">identification number</span></span>
  
<span data-ttu-id="b306e-277">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-277">personal id number</span></span>
  
<span data-ttu-id="b306e-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="b306e-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="b306e-p103">uimh。psp</span><span class="sxs-lookup"><span data-stu-id="b306e-p103">uimh. psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="b306e-281">イタリア</span><span class="sxs-lookup"><span data-stu-id="b306e-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="b306e-282">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-282">Format</span></span>

<span data-ttu-id="b306e-283">文字と数字で指定されたパターンの 16 文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="b306e-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-284">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-284">Pattern</span></span>

<span data-ttu-id="b306e-285">文字と数字の 16 文字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="b306e-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="b306e-286">ファミリ名の最初の 3 つの子音に対応する 3 つの文字</span><span class="sxs-lookup"><span data-stu-id="b306e-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="b306e-287">第 1、3 番目および 4 番目に対応する 3 文字名の子音</span><span class="sxs-lookup"><span data-stu-id="b306e-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="b306e-288">2 桁の桁の誕生年の最後に対応しています。</span><span class="sxs-lookup"><span data-stu-id="b306e-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="b306e-289">生年月日の月の文字に対応する 1 つの文字、文字は、アルファベット順で使用されますが、た E、H、L、M、P、t、R には、使用 (つまり、1 月 A で、10 月 R)</span><span class="sxs-lookup"><span data-stu-id="b306e-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="b306e-290">生年月日の月の日付に対応する 2 つの数字、性別を区別するために 40、女性の誕生日の日に追加</span><span class="sxs-lookup"><span data-stu-id="b306e-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="b306e-291">個人の生まれた場所の自治体に固有の領域のコードに対応する 4 桁の数字 (外国の国全体のコードが使用されます)</span><span class="sxs-lookup"><span data-stu-id="b306e-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="b306e-292">1 桁のパリティ</span><span class="sxs-lookup"><span data-stu-id="b306e-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-293">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-293">Checksum</span></span>

<span data-ttu-id="b306e-294">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-295">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-295">Definition</span></span>

<span data-ttu-id="b306e-296">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-297">関数`Func_italy_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-298">キーワードの`Keywords_italy_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-299">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-300">関数`Func_italy_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
          <Match idRef="Keywords_italy_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-301">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="b306e-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="b306e-303">個人コード</span><span class="sxs-lookup"><span data-stu-id="b306e-303">personal code</span></span>
  
<span data-ttu-id="b306e-304">個人コード番号</span><span class="sxs-lookup"><span data-stu-id="b306e-304">personal code number</span></span>
  
<span data-ttu-id="b306e-305">個人証明書の番号</span><span class="sxs-lookup"><span data-stu-id="b306e-305">personal certificate number</span></span>
  
<span data-ttu-id="b306e-306">会計年度コード</span><span class="sxs-lookup"><span data-stu-id="b306e-306">fiscal code</span></span>
  
<span data-ttu-id="b306e-307">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="b306e-307">personalcodeno#</span></span>
  
<span data-ttu-id="b306e-308">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-308">personal id number</span></span>
  
<span data-ttu-id="b306e-309">個人の id コード</span><span class="sxs-lookup"><span data-stu-id="b306e-309">personal id code</span></span>
  
<span data-ttu-id="b306e-310">codice personale</span><span class="sxs-lookup"><span data-stu-id="b306e-310">codice personale</span></span>
  
<span data-ttu-id="b306e-311">certificato personale</span><span class="sxs-lookup"><span data-stu-id="b306e-311">numero certificato personale</span></span>
  
<span data-ttu-id="b306e-312">して personale</span><span class="sxs-lookup"><span data-stu-id="b306e-312">numero personale</span></span>
  
<span data-ttu-id="b306e-313">id personale</span><span class="sxs-lookup"><span data-stu-id="b306e-313">numero id personale</span></span>
  
<span data-ttu-id="b306e-314">codice id personale</span><span class="sxs-lookup"><span data-stu-id="b306e-314">codice id personale</span></span>
  
<span data-ttu-id="b306e-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="b306e-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="b306e-316">イタリア</span><span class="sxs-lookup"><span data-stu-id="b306e-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="b306e-317">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-317">Format</span></span>

<span data-ttu-id="b306e-318">11 桁の数字とハイフンで指定された形式</span><span class="sxs-lookup"><span data-stu-id="b306e-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-319">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-319">Pattern</span></span>

<span data-ttu-id="b306e-320">11 桁の数字とハイフン。</span><span class="sxs-lookup"><span data-stu-id="b306e-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="b306e-321">6 桁の数字が日付の生年月日に対応します。</span><span class="sxs-lookup"><span data-stu-id="b306e-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="b306e-322">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="b306e-322">A hyphen</span></span>
    
- <span data-ttu-id="b306e-323">1 桁の数字 (0: 19 世紀の 20 世紀の年の「1」と 21 世紀の"2") の生年月日の 4 桁年に対応します。</span><span class="sxs-lookup"><span data-stu-id="b306e-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="b306e-324">4 桁の数字をランダムに生成されます。</span><span class="sxs-lookup"><span data-stu-id="b306e-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-325">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-325">Checksum</span></span>

<span data-ttu-id="b306e-326">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-327">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-327">Definition</span></span>

<span data-ttu-id="b306e-328">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-329">関数`Func_latvia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-330">キーワードの`Keywords_latvia_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-331">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-332">関数`Func_latvia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
          <Match idRef="Keywords_latvia_eu_national_id_card" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-333">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="b306e-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="b306e-335">個人コード</span><span class="sxs-lookup"><span data-stu-id="b306e-335">personal code</span></span>
  
<span data-ttu-id="b306e-336">個人コード番号</span><span class="sxs-lookup"><span data-stu-id="b306e-336">personal code number</span></span>
  
<span data-ttu-id="b306e-337">個人証明書の番号</span><span class="sxs-lookup"><span data-stu-id="b306e-337">personal certificate number</span></span>
  
<span data-ttu-id="b306e-338">personalcodeno #</span><span class="sxs-lookup"><span data-stu-id="b306e-338">personalcodeno#</span></span>
  
<span data-ttu-id="b306e-339">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-339">personal id number</span></span>
  
<span data-ttu-id="b306e-340">個人の id コード</span><span class="sxs-lookup"><span data-stu-id="b306e-340">personal id code</span></span>
  
<span data-ttu-id="b306e-341">ペルソナ kods</span><span class="sxs-lookup"><span data-stu-id="b306e-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="b306e-342">リトアニア</span><span class="sxs-lookup"><span data-stu-id="b306e-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="b306e-343">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-343">Format</span></span>

<span data-ttu-id="b306e-344">スペースや区切り記号なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-345">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-345">Pattern</span></span>

<span data-ttu-id="b306e-346">スペースや区切り記号のない 11 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="b306e-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="b306e-347">人の性別と生年月日の世紀に対応する 1 つの数字</span><span class="sxs-lookup"><span data-stu-id="b306e-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="b306e-348">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="b306e-349">生年月日の日付のシリアル番号に対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="b306e-350">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-351">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-351">Checksum</span></span>

<span data-ttu-id="b306e-352">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-353">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-353">Definition</span></span>

<span data-ttu-id="b306e-354">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-355">関数`Func_lithuania_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-356">キーワードの`Keywords_lithuania_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-357">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-358">関数`Func_lithuania_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
          <Match idRef="Keywords_lithuania_eu_national_id_card" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-359">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="b306e-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="b306e-361">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="b306e-361">personal numeric code</span></span>
  
<span data-ttu-id="b306e-362">一意な識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-362">unique identification number</span></span>
  
<span data-ttu-id="b306e-363">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="b306e-363">citizen service number</span></span>
  
<span data-ttu-id="b306e-364">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-364">unique identity number</span></span>
  
<span data-ttu-id="b306e-365">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="b306e-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="b306e-366">個人コードです。</span><span class="sxs-lookup"><span data-stu-id="b306e-366">personal code.</span></span>
  
<span data-ttu-id="b306e-367">asmeninis skaitmeninis kodas</span><span class="sxs-lookup"><span data-stu-id="b306e-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="b306e-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="b306e-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="b306e-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="b306e-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="b306e-370">unikalus identifikavimo kodas</span><span class="sxs-lookup"><span data-stu-id="b306e-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="b306e-371">asmens kodas。</span><span class="sxs-lookup"><span data-stu-id="b306e-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="b306e-372">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="b306e-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="b306e-373">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-373">Format</span></span>

<span data-ttu-id="b306e-374">スペースや区切り記号なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-375">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-375">Pattern</span></span>

<span data-ttu-id="b306e-376">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-376">11 digits</span></span>
  
- <span data-ttu-id="b306e-377">人の性別と生年月日の世紀に対応する 1 つの数字</span><span class="sxs-lookup"><span data-stu-id="b306e-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="b306e-378">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="b306e-379">生年月日の日付のシリアル番号に対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="b306e-380">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-381">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-381">Checksum</span></span>

<span data-ttu-id="b306e-382">該当なし</span><span class="sxs-lookup"><span data-stu-id="b306e-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-383">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-383">Definition</span></span>

<span data-ttu-id="b306e-384">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-385">正規表現`Regex_luxemburg_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-386">キーワードの`Keywords_luxemburg_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-387">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="b306e-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="b306e-389">パーソナル id</span><span class="sxs-lookup"><span data-stu-id="b306e-389">personal id</span></span>
  
<span data-ttu-id="b306e-390">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-390">personal id number</span></span>
  
<span data-ttu-id="b306e-391">personalidno #</span><span class="sxs-lookup"><span data-stu-id="b306e-391">personalidno#</span></span>
  
<span data-ttu-id="b306e-392">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-392">unique id number</span></span>
  
<span data-ttu-id="b306e-393">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-393">personalidnumber#</span></span>
  
<span data-ttu-id="b306e-394">キーの一意の id</span><span class="sxs-lookup"><span data-stu-id="b306e-394">unique id key</span></span>
  
<span data-ttu-id="b306e-395">個人の id コード</span><span class="sxs-lookup"><span data-stu-id="b306e-395">personal id code</span></span>
  
<span data-ttu-id="b306e-396">uniqueidkey #</span><span class="sxs-lookup"><span data-stu-id="b306e-396">uniqueidkey#</span></span>
  
<span data-ttu-id="b306e-397">個々 のコード</span><span class="sxs-lookup"><span data-stu-id="b306e-397">individual code</span></span>
  
<span data-ttu-id="b306e-398">個々 の id</span><span class="sxs-lookup"><span data-stu-id="b306e-398">individual id</span></span>
  
<span data-ttu-id="b306e-399">- nummer eindeutige id</span><span class="sxs-lookup"><span data-stu-id="b306e-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="b306e-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="b306e-400">eindeutige id</span></span>
  
<span data-ttu-id="b306e-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="b306e-401">id personnelle</span></span>
  
<span data-ttu-id="b306e-402">numéro d'identification スタッフ</span><span class="sxs-lookup"><span data-stu-id="b306e-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="b306e-403">idpersonnelle #</span><span class="sxs-lookup"><span data-stu-id="b306e-403">idpersonnelle#</span></span>
  
<span data-ttu-id="b306e-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b306e-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="b306e-405">eindeutigeid #</span><span class="sxs-lookup"><span data-stu-id="b306e-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="b306e-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="b306e-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="b306e-407">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-407">Format</span></span>

<span data-ttu-id="b306e-408">1 つの文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-409">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-409">Pattern</span></span>

<span data-ttu-id="b306e-410">7 つの数字が 1 つの文字の後に。</span><span class="sxs-lookup"><span data-stu-id="b306e-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="b306e-411">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="b306e-411">Seven digits</span></span> 
    
- <span data-ttu-id="b306e-412">大文字を 1 つ (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="b306e-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-413">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-413">Checksum</span></span>

<span data-ttu-id="b306e-414">該当なし</span><span class="sxs-lookup"><span data-stu-id="b306e-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-415">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-415">Definition</span></span>

<span data-ttu-id="b306e-416">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-417">正規表現`Regex_malta_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-418">キーワードの`Keywords_malta_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-419">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-420">正規表現`Regex_malta_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
          <Match idRef="Keywords_malta_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-421">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="b306e-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="b306e-423">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="b306e-423">personal numeric code</span></span>
  
<span data-ttu-id="b306e-424">一意な識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-424">unique identification number</span></span>
  
<span data-ttu-id="b306e-425">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="b306e-425">citizen service number</span></span>
  
<span data-ttu-id="b306e-426">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-426">unique identity number</span></span>
  
<span data-ttu-id="b306e-427">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="b306e-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="b306e-428">kodiċi numerali personali</span><span class="sxs-lookup"><span data-stu-id="b306e-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="b306e-429">numru どっち ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="b306e-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="b306e-430">numru tas servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="b306e-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="b306e-431">numru どっち ' identità uniku</span><span class="sxs-lookup"><span data-stu-id="b306e-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="b306e-432">オランダ</span><span class="sxs-lookup"><span data-stu-id="b306e-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="b306e-433">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-433">Format</span></span>

<span data-ttu-id="b306e-434">スペースや区切り文字なしの 9 つの数字</span><span class="sxs-lookup"><span data-stu-id="b306e-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-435">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-435">Pattern</span></span>

<span data-ttu-id="b306e-436">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b306e-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-437">Checksum</span></span>

<span data-ttu-id="b306e-438">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-439">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-439">Definition</span></span>

<span data-ttu-id="b306e-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-441">関数`Func_netherlands_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-442">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="b306e-442">A keyword from is found.</span></span>
    
<span data-ttu-id="b306e-443">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-444">関数`Func_netherlands_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
          <Match idRef="Keywords_netherlands_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-445">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="b306e-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="b306e-447">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="b306e-447">personal numeric code</span></span>
  
<span data-ttu-id="b306e-448">一意な識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-448">unique identification number</span></span>
  
<span data-ttu-id="b306e-449">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="b306e-449">citizen service number</span></span>
  
<span data-ttu-id="b306e-450">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-450">unique identity number</span></span>
  
<span data-ttu-id="b306e-451">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="b306e-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="b306e-452">bsn</span><span class="sxs-lookup"><span data-stu-id="b306e-452">bsn</span></span>
  
<span data-ttu-id="b306e-453">bsn #</span><span class="sxs-lookup"><span data-stu-id="b306e-453">bsn#</span></span>
  
<span data-ttu-id="b306e-454">persoonlijke numerieke コード</span><span class="sxs-lookup"><span data-stu-id="b306e-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="b306e-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="b306e-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="b306e-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="b306e-456">burgerservicenummer</span></span>
  
<span data-ttu-id="b306e-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="b306e-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="b306e-458">ポーランド</span><span class="sxs-lookup"><span data-stu-id="b306e-458">Poland</span></span>

<span data-ttu-id="b306e-459">詳細についてを参照してください「ポーランド国 ID (PESEL)」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="b306e-460">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="b306e-460">Portugal</span></span>

<span data-ttu-id="b306e-461">詳細についてを参照してください「ポルトガルの市民のカード番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="b306e-462">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="b306e-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="b306e-463">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-463">Format</span></span>

<span data-ttu-id="b306e-464">スペースや区切り記号のない 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-465">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-465">Pattern</span></span>

<span data-ttu-id="b306e-466">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b306e-467">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-467">Checksum</span></span>

<span data-ttu-id="b306e-468">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-469">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-469">Definition</span></span>

<span data-ttu-id="b306e-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-471">関数`Func_romania_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-472">キーワードの`Keywords_romania_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-474">関数`Func_romania_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
          <Match idRef="Keywords_romania_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_romania_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-475">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="b306e-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="b306e-477">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="b306e-477">personal numeric code</span></span>
  
<span data-ttu-id="b306e-478">一意な識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-478">unique identification number</span></span>
  
<span data-ttu-id="b306e-479">cnp</span><span class="sxs-lookup"><span data-stu-id="b306e-479">cnp</span></span>
  
<span data-ttu-id="b306e-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="b306e-480">cnp#</span></span>
  
<span data-ttu-id="b306e-481">固定</span><span class="sxs-lookup"><span data-stu-id="b306e-481">pin</span></span>
  
<span data-ttu-id="b306e-482">暗証番号 (pin) #</span><span class="sxs-lookup"><span data-stu-id="b306e-482">pin#</span></span>
  
<span data-ttu-id="b306e-483">保険番号</span><span class="sxs-lookup"><span data-stu-id="b306e-483">insurance number</span></span>
  
<span data-ttu-id="b306e-484">insurancenumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-484">insurancenumber#</span></span>
  
<span data-ttu-id="b306e-485">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-485">unique identity number</span></span>
  
<span data-ttu-id="b306e-486">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="b306e-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="b306e-487">代金引換払いの個人の数値</span><span class="sxs-lookup"><span data-stu-id="b306e-487">cod numeric personal</span></span>
  
<span data-ttu-id="b306e-488">代金引換払いの個人 identificare</span><span class="sxs-lookup"><span data-stu-id="b306e-488">cod identificare personal</span></span>
  
<span data-ttu-id="b306e-489">代金引換払い unic identificare</span><span class="sxs-lookup"><span data-stu-id="b306e-489">cod unic identificare</span></span>
  
<span data-ttu-id="b306e-490">număr 個人 unic</span><span class="sxs-lookup"><span data-stu-id="b306e-490">număr personal unic</span></span>
  
<span data-ttu-id="b306e-491">număr identitate</span><span class="sxs-lookup"><span data-stu-id="b306e-491">număr identitate</span></span>
  
<span data-ttu-id="b306e-492">個人の număr identificare</span><span class="sxs-lookup"><span data-stu-id="b306e-492">număr identificare personal</span></span>
  
<span data-ttu-id="b306e-493">număridentitate #</span><span class="sxs-lookup"><span data-stu-id="b306e-493">număridentitate#</span></span>
  
<span data-ttu-id="b306e-494">codnumericpersonal #</span><span class="sxs-lookup"><span data-stu-id="b306e-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="b306e-495">numărpersonalunic #</span><span class="sxs-lookup"><span data-stu-id="b306e-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="b306e-496">スロバキア</span><span class="sxs-lookup"><span data-stu-id="b306e-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="b306e-497">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-497">Format</span></span>

<span data-ttu-id="b306e-498">1 つのバック スラッシュが含まれている 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-499">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-499">Pattern</span></span>

<span data-ttu-id="b306e-500">10 個の数字が 1 つのバック スラッシュが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b306e-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b306e-501">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-501">Checksum</span></span>

<span data-ttu-id="b306e-502">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-503">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-503">Definition</span></span>

<span data-ttu-id="b306e-504">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-505">関数`Func_slovakia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-506">キーワードの`Keywords_slovakia_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-508">関数`Func_slovakia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
          <Match idRef="Keywords_slovakia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovakia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-509">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="b306e-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="b306e-511">生年月日数</span><span class="sxs-lookup"><span data-stu-id="b306e-511">birth number</span></span>
  
<span data-ttu-id="b306e-512">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-512">national identification number</span></span>
  
<span data-ttu-id="b306e-513">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-513">personal identification number</span></span>
  
<span data-ttu-id="b306e-514">social security number
</span><span class="sxs-lookup"><span data-stu-id="b306e-514">social security number</span></span>
  
<span data-ttu-id="b306e-515">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-515">nationalnumber#</span></span>
  
<span data-ttu-id="b306e-516">ssn #</span><span class="sxs-lookup"><span data-stu-id="b306e-516">ssn#</span></span>
  
<span data-ttu-id="b306e-517">ssn</span><span class="sxs-lookup"><span data-stu-id="b306e-517">ssn</span></span>
  
<span data-ttu-id="b306e-518">国番号</span><span class="sxs-lookup"><span data-stu-id="b306e-518">national number</span></span>
  
<span data-ttu-id="b306e-519">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-519">personal id number</span></span>
  
<span data-ttu-id="b306e-520">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b306e-520">personalidnumber#</span></span>
  
<span data-ttu-id="b306e-521">rč</span><span class="sxs-lookup"><span data-stu-id="b306e-521">rč</span></span>
  
<span data-ttu-id="b306e-522">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="b306e-522">rodné číslo</span></span>
  
<span data-ttu-id="b306e-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="b306e-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="b306e-524">スロベニア</span><span class="sxs-lookup"><span data-stu-id="b306e-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="b306e-525">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-525">Format</span></span>

<span data-ttu-id="b306e-526">スペースや区切り文字のない 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-527">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-527">Pattern</span></span>

<span data-ttu-id="b306e-528">指定したパターンで 13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b306e-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="b306e-529">「LLL」が生まれた年の 3 桁の数字で対応最後に生年月日 (DDMMLLL) に対応する 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="b306e-530">生年月日の区分に対応する 2 つの数字</span><span class="sxs-lookup"><span data-stu-id="b306e-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="b306e-531">(000-499 男性の場合) と女性の場合に、500-999 は、同じ日に生まれた人の性別とシリアル番号の組み合わせに対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="b306e-532">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="b306e-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-533">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-533">Checksum</span></span>

<span data-ttu-id="b306e-534">はい</span><span class="sxs-lookup"><span data-stu-id="b306e-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-535">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-535">Definition</span></span>

<span data-ttu-id="b306e-536">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-537">関数`Func_slovenia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-538">キーワードの`Keywords_slovenia_eu_national_id_card`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="b306e-539">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-540">関数`Func_slovenia_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
          <Match idRef="Keywords_slovenia_eu_national_id_card" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-541">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="b306e-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="b306e-543">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="b306e-543">personal numeric code</span></span>
  
<span data-ttu-id="b306e-544">一意な識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-544">unique identification number</span></span>
  
<span data-ttu-id="b306e-545">一意の登録番号</span><span class="sxs-lookup"><span data-stu-id="b306e-545">unique registration number</span></span>
  
<span data-ttu-id="b306e-546">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-546">unique identity number</span></span>
  
<span data-ttu-id="b306e-547">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="b306e-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="b306e-548">一意のマスターの市民数</span><span class="sxs-lookup"><span data-stu-id="b306e-548">unique master citizen number</span></span>
  
<span data-ttu-id="b306e-549">edinstvena identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="b306e-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="b306e-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="b306e-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="b306e-551">edinstvena številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="b306e-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="b306e-552">emšo</span><span class="sxs-lookup"><span data-stu-id="b306e-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="b306e-553">スペイン</span><span class="sxs-lookup"><span data-stu-id="b306e-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="b306e-554">形式</span><span class="sxs-lookup"><span data-stu-id="b306e-554">Format</span></span>

<span data-ttu-id="b306e-555">1 つの文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b306e-556">パターン</span><span class="sxs-lookup"><span data-stu-id="b306e-556">Pattern</span></span>

<span data-ttu-id="b306e-557">1 つの文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b306e-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="b306e-558">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="b306e-558">Seven digits</span></span>
    
- <span data-ttu-id="b306e-559">1 つの数字または文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="b306e-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b306e-560">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b306e-560">Checksum</span></span>

<span data-ttu-id="b306e-561">該当なし</span><span class="sxs-lookup"><span data-stu-id="b306e-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b306e-562">定義</span><span class="sxs-lookup"><span data-stu-id="b306e-562">Definition</span></span>

<span data-ttu-id="b306e-563">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b306e-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b306e-564">正規表現`Regex_spain_eu_national_id_card`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b306e-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b306e-565">キーワードの`Keywords_spain_eu_national_id_card"`があります。</span><span class="sxs-lookup"><span data-stu-id="b306e-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b306e-566">Keywords</span><span class="sxs-lookup"><span data-stu-id="b306e-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="b306e-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="b306e-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="b306e-568">dni</span><span class="sxs-lookup"><span data-stu-id="b306e-568">dni</span></span>
  
<span data-ttu-id="b306e-569">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-569">national identification number</span></span>
  
<span data-ttu-id="b306e-570">国内の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-570">national identity number</span></span>
  
<span data-ttu-id="b306e-571">保険番号</span><span class="sxs-lookup"><span data-stu-id="b306e-571">insurance number</span></span>
  
<span data-ttu-id="b306e-572">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="b306e-572">personal identification number</span></span>
  
<span data-ttu-id="b306e-573">国家のアイデンティティ</span><span class="sxs-lookup"><span data-stu-id="b306e-573">national identity</span></span>
  
<span data-ttu-id="b306e-574">個人識別情報なし</span><span class="sxs-lookup"><span data-stu-id="b306e-574">personal identity no</span></span>
  
<span data-ttu-id="b306e-575">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="b306e-575">unique identity number</span></span>
  
<span data-ttu-id="b306e-576">nationalidno #</span><span class="sxs-lookup"><span data-stu-id="b306e-576">nationalidno#</span></span>
  
<span data-ttu-id="b306e-577">uniqueid #</span><span class="sxs-lookup"><span data-stu-id="b306e-577">uniqueid#</span></span>
  
<span data-ttu-id="b306e-578">dni #</span><span class="sxs-lookup"><span data-stu-id="b306e-578">dni#</span></span>
  
<span data-ttu-id="b306e-579">nationalid #</span><span class="sxs-lookup"><span data-stu-id="b306e-579">nationalid#</span></span>
  
<span data-ttu-id="b306e-580">nie #</span><span class="sxs-lookup"><span data-stu-id="b306e-580">nie#</span></span>
  
<span data-ttu-id="b306e-581">nie</span><span class="sxs-lookup"><span data-stu-id="b306e-581">nie</span></span>
  
<span data-ttu-id="b306e-582">nienúmero #</span><span class="sxs-lookup"><span data-stu-id="b306e-582">nienúmero#</span></span>
  
<span data-ttu-id="b306e-583">nie número</span><span class="sxs-lookup"><span data-stu-id="b306e-583">nie número</span></span>
  
<span data-ttu-id="b306e-584">documento nacional de identidad</span><span class="sxs-lookup"><span data-stu-id="b306e-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="b306e-585">identidad único</span><span class="sxs-lookup"><span data-stu-id="b306e-585">identidad único</span></span>
  
<span data-ttu-id="b306e-586">número nacional identidad</span><span class="sxs-lookup"><span data-stu-id="b306e-586">número nacional identidad</span></span>
  
<span data-ttu-id="b306e-587">dni número</span><span class="sxs-lookup"><span data-stu-id="b306e-587">dni número</span></span>
  
<span data-ttu-id="b306e-588">dninúmero #</span><span class="sxs-lookup"><span data-stu-id="b306e-588">dninúmero#</span></span>
  
<span data-ttu-id="b306e-589">identidadúnico #</span><span class="sxs-lookup"><span data-stu-id="b306e-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="b306e-590">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="b306e-590">Sweden</span></span>

<span data-ttu-id="b306e-591">詳細についてを参照してください「スウェーデン国民 ID」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="b306e-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b306e-592">関連項目</span><span class="sxs-lookup"><span data-stu-id="b306e-592">See also</span></span>

[<span data-ttu-id="b306e-593">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="b306e-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

