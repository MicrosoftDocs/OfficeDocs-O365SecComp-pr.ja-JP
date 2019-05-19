---
title: EU 国家識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 国内の識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 205019d040648f0600f3dbf4403063edf9f31c41
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154461"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="619a2-104">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-104">EU National Identification Number</span></span>

<span data-ttu-id="619a2-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 国内の識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="619a2-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="619a2-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="619a2-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="619a2-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="619a2-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="619a2-108">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-108">Format</span></span>

<span data-ttu-id="619a2-109">24文字の文字、数字、特殊文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="619a2-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-110">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-110">Pattern</span></span>

<span data-ttu-id="619a2-111">24文字:</span><span class="sxs-lookup"><span data-stu-id="619a2-111">24 characters:</span></span>
  
-  <span data-ttu-id="619a2-112">22文字 (大文字小文字を区別しない)、数字、円記号、スラッシュ、またはプラス記号</span><span class="sxs-lookup"><span data-stu-id="619a2-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="619a2-113">2つの文字 (大文字小文字を区別しない)、数字、バックスラッシュ、スラッシュ、プラス記号、または等号</span><span class="sxs-lookup"><span data-stu-id="619a2-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-114">Checksum</span></span>

<span data-ttu-id="619a2-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="619a2-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-116">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-116">Definition</span></span>

<span data-ttu-id="619a2-117">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-118">正規表現`Regex_austria_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="619a2-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-119">From `Keywords_austria_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="619a2-120">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-120">Keywords</span></span>

#### <a name="keywordsaustriaeunationalidcard"></a><span data-ttu-id="619a2-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="619a2-122">オーストリアの id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-122">austrian identity number</span></span>
  
<span data-ttu-id="619a2-123">国内の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-123">national identity number</span></span>
  
<span data-ttu-id="619a2-124">id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-124">identity number</span></span>
  
<span data-ttu-id="619a2-125">national id</span><span class="sxs-lookup"><span data-stu-id="619a2-125">national id</span></span>
  
<span data-ttu-id="619a2-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="619a2-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="619a2-127">ベルギー</span><span class="sxs-lookup"><span data-stu-id="619a2-127">Belgium</span></span>

<span data-ttu-id="619a2-128">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ベルギー国立番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="619a2-129">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="619a2-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="619a2-130">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-130">Format</span></span>

<span data-ttu-id="619a2-131">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-132">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-132">Pattern</span></span>

<span data-ttu-id="619a2-133">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="619a2-134">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="619a2-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="619a2-135">誕生日の順序に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="619a2-136">性別に対応する1桁の数字: 男性の偶数桁で、女性に奇数の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="619a2-137">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-138">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-138">Checksum</span></span>

<span data-ttu-id="619a2-139">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-140">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-140">Definition</span></span>

<span data-ttu-id="619a2-141">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-142">関数`Func_bulgaria_national_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-143">From `Keywords_bulgaria_national_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="619a2-144">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-145">関数`Func_bulgaria_national_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-146">Keywords</span></span>

#### <a name="keywordsbulgarianationalnumber"></a><span data-ttu-id="619a2-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="619a2-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="619a2-148">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="619a2-148">egn</span></span>
  
<span data-ttu-id="619a2-149">"/入力 id"</span><span class="sxs-lookup"><span data-stu-id="619a2-149">egn#</span></span>
  
<span data-ttu-id="619a2-150">ブルガリアの国番号</span><span class="sxs-lookup"><span data-stu-id="619a2-150">bulgarian national number</span></span>
  
<span data-ttu-id="619a2-151">国番号</span><span class="sxs-lookup"><span data-stu-id="619a2-151">national number</span></span>
  
<span data-ttu-id="619a2-152">social security number</span><span class="sxs-lookup"><span data-stu-id="619a2-152">social security number</span></span>
  
<span data-ttu-id="619a2-153">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-153">nationalnumber#</span></span>
  
<span data-ttu-id="619a2-154">ssn</span><span class="sxs-lookup"><span data-stu-id="619a2-154">ssn#</span></span>
  
<span data-ttu-id="619a2-155">ssn</span><span class="sxs-lookup"><span data-stu-id="619a2-155">ssn</span></span>
  
<span data-ttu-id="619a2-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="619a2-156">nationalnumber</span></span>
  
<span data-ttu-id="619a2-157">bnn #</span><span class="sxs-lookup"><span data-stu-id="619a2-157">bnn#</span></span>
  
<span data-ttu-id="619a2-158">bnn</span><span class="sxs-lookup"><span data-stu-id="619a2-158">bnn</span></span>
  
<span data-ttu-id="619a2-159">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-159">personal id number</span></span>
  
<span data-ttu-id="619a2-160">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-160">personalidnumber#</span></span>
  
<span data-ttu-id="619a2-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="619a2-161">единен граждански номер</span></span>
  
<span data-ttu-id="619a2-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="619a2-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="619a2-163">егн</span><span class="sxs-lookup"><span data-stu-id="619a2-163">егн</span></span>
  
<span data-ttu-id="619a2-164">егн#</span><span class="sxs-lookup"><span data-stu-id="619a2-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="619a2-165">クロアチア</span><span class="sxs-lookup"><span data-stu-id="619a2-165">Croatia</span></span>

<span data-ttu-id="619a2-166">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「クロアチアの id 番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="619a2-167">キプロス</span><span class="sxs-lookup"><span data-stu-id="619a2-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="619a2-168">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-168">Format</span></span>

<span data-ttu-id="619a2-169">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-170">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-170">Pattern</span></span>

 <span data-ttu-id="619a2-171">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="619a2-172">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-172">Checksum</span></span>

<span data-ttu-id="619a2-173">該当なし</span><span class="sxs-lookup"><span data-stu-id="619a2-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-174">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-174">Definition</span></span>

<span data-ttu-id="619a2-175">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-176">正規表現`Regex_cyprus_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="619a2-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-177">From `Keywords_cyprus_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="619a2-178">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-178">Keywords</span></span>

#### <a name="keywordscypruseunationalidcard"></a><span data-ttu-id="619a2-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="619a2-180">id カード番号</span><span class="sxs-lookup"><span data-stu-id="619a2-180">id card number</span></span>
  
<span data-ttu-id="619a2-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="619a2-181">national identification number</span></span>
  
<span data-ttu-id="619a2-182">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-182">personal id number</span></span>
  
<span data-ttu-id="619a2-183">id カード番号</span><span class="sxs-lookup"><span data-stu-id="619a2-183">identity card number</span></span>
  
<span data-ttu-id="619a2-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="619a2-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="619a2-185">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="619a2-185">Czech Republic</span></span>

<span data-ttu-id="619a2-186">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「チェコ国立 id 番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="619a2-187">デンマーク</span><span class="sxs-lookup"><span data-stu-id="619a2-187">Denmark</span></span>

<span data-ttu-id="619a2-188">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「デンマークの個人識別番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="619a2-189">エストニア</span><span class="sxs-lookup"><span data-stu-id="619a2-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="619a2-190">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-190">Format</span></span>

<span data-ttu-id="619a2-191">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-192">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-192">Pattern</span></span>

<span data-ttu-id="619a2-193">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="619a2-193">11 digits:</span></span>
  
- <span data-ttu-id="619a2-194">性別と世紀に対応する1桁の数字 (奇数個の男性、偶数の女性、1-2:19 世紀、3-4:20 世紀、5-6:21 世紀)</span><span class="sxs-lookup"><span data-stu-id="619a2-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="619a2-195">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="619a2-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="619a2-196">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="619a2-197">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-198">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-198">Checksum</span></span>

<span data-ttu-id="619a2-199">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-200">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-200">Definition</span></span>

<span data-ttu-id="619a2-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-202">関数`Func_estonia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-203">From `Keywords_estonia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-204">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-205">関数`Func_estonia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-206">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-206">Keywords</span></span>

#### <a name="keywordsestoniaeunationalidcard"></a><span data-ttu-id="619a2-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="619a2-208">個人識別コード</span><span class="sxs-lookup"><span data-stu-id="619a2-208">personal identification code</span></span>
  
<span data-ttu-id="619a2-209">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-209">personal identification number</span></span>
  
<span data-ttu-id="619a2-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="619a2-210">national identification number</span></span>
  
<span data-ttu-id="619a2-211">国番号</span><span class="sxs-lookup"><span data-stu-id="619a2-211">national number</span></span>
  
<span data-ttu-id="619a2-212">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-212">personal id number</span></span>
  
<span data-ttu-id="619a2-213">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-213">personalidnumber#</span></span>
  
<span data-ttu-id="619a2-214">ik</span><span class="sxs-lookup"><span data-stu-id="619a2-214">ik</span></span>
  
<span data-ttu-id="619a2-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="619a2-215">isikukood</span></span>
  
<span data-ttu-id="619a2-216">id-kaart</span><span class="sxs-lookup"><span data-stu-id="619a2-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="619a2-217">フィンランド</span><span class="sxs-lookup"><span data-stu-id="619a2-217">Finland</span></span>

<span data-ttu-id="619a2-218">詳細については、「フィンランド国立 ID」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="619a2-219">フランス</span><span class="sxs-lookup"><span data-stu-id="619a2-219">France</span></span>

<span data-ttu-id="619a2-220">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランス国立 ID カード (CNI)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="619a2-221">ドイツ</span><span class="sxs-lookup"><span data-stu-id="619a2-221">Germany</span></span>

<span data-ttu-id="619a2-222">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの Id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="619a2-223">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="619a2-223">Greece</span></span>

<span data-ttu-id="619a2-224">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="619a2-225">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="619a2-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="619a2-226">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-226">Format</span></span>

<span data-ttu-id="619a2-227">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-228">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-228">Pattern</span></span>

<span data-ttu-id="619a2-229">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="619a2-229">11 digits:</span></span>
  
-  <span data-ttu-id="619a2-230">性別に対応する1桁の数字 (1-オス、2-女性、その他の数字は1900または市民が二重市民権を持つ市民の場合もあります)</span><span class="sxs-lookup"><span data-stu-id="619a2-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="619a2-231">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="619a2-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="619a2-232">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="619a2-233">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-234">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-234">Checksum</span></span>

<span data-ttu-id="619a2-235">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-236">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-236">Definition</span></span>

<span data-ttu-id="619a2-237">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-238">関数`Func_hungary_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-239">From `Keywords_hungary_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-240">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-241">関数`Func_hungary_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-242">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-242">Keywords</span></span>

#### <a name="keywordshungaryeunationalidcard"></a><span data-ttu-id="619a2-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="619a2-244">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-244">personal identification number</span></span>
  
<span data-ttu-id="619a2-245">identification number</span><span class="sxs-lookup"><span data-stu-id="619a2-245">identification number</span></span>
  
<span data-ttu-id="619a2-246">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-246">personal id number</span></span>
  
<span data-ttu-id="619a2-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="619a2-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="619a2-248">アイルランド</span><span class="sxs-lookup"><span data-stu-id="619a2-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="619a2-249">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-249">Format</span></span>

<span data-ttu-id="619a2-250">指定したパターンの文字、数字、スペースの9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="619a2-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-251">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-251">Pattern</span></span>

<span data-ttu-id="619a2-252">指定したパターンの文字、数字、スペースの9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="619a2-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="619a2-253">01年 1 2013 月から今すぐに。</span><span class="sxs-lookup"><span data-stu-id="619a2-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="619a2-254">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="619a2-254">Seven digits</span></span> 
    
- <span data-ttu-id="619a2-255">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-255">One check digit</span></span>
    
- <span data-ttu-id="619a2-256">1つのスペースまたは大文字の "W" (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="619a2-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="619a2-257">01年1月2013前:</span><span class="sxs-lookup"><span data-stu-id="619a2-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="619a2-258">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="619a2-258">Seven digits</span></span> 
    
- <span data-ttu-id="619a2-259">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-259">One check digit</span></span>
    
- <span data-ttu-id="619a2-260">1つのスペースまたは大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="619a2-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-261">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-261">Checksum</span></span>

<span data-ttu-id="619a2-262">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-263">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-263">Definition</span></span>

<span data-ttu-id="619a2-264">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-265">関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="619a2-266">From キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-266">A keyword from is found.</span></span>
    
<span data-ttu-id="619a2-267">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-268">関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-269">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-269">Keywords</span></span>

#### <a name="keywordsirelandeunationalidcard"></a><span data-ttu-id="619a2-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="619a2-271">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="619a2-271">personal public service number</span></span>
  
<span data-ttu-id="619a2-272">pps no</span><span class="sxs-lookup"><span data-stu-id="619a2-272">pps no</span></span>
  
<span data-ttu-id="619a2-273">収益および社会保険番号</span><span class="sxs-lookup"><span data-stu-id="619a2-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="619a2-274">rsi no</span><span class="sxs-lookup"><span data-stu-id="619a2-274">rsi no</span></span>
  
<span data-ttu-id="619a2-275">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-275">personal identification number</span></span>
  
<span data-ttu-id="619a2-276">identification number</span><span class="sxs-lookup"><span data-stu-id="619a2-276">identification number</span></span>
  
<span data-ttu-id="619a2-277">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-277">personal id number</span></span>
  
<span data-ttu-id="619a2-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="619a2-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="619a2-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="619a2-279">uimh.</span></span> <span data-ttu-id="619a2-280">psp</span><span class="sxs-lookup"><span data-stu-id="619a2-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="619a2-281">イタリア</span><span class="sxs-lookup"><span data-stu-id="619a2-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="619a2-282">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-282">Format</span></span>

<span data-ttu-id="619a2-283">指定したパターンの文字と数字の16文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="619a2-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-284">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-284">Pattern</span></span>

<span data-ttu-id="619a2-285">文字と数字の16文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="619a2-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="619a2-286">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="619a2-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="619a2-287">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="619a2-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="619a2-288">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="619a2-289">誕生日の文字に対応する1つの文字-文字はアルファベット順に使用されますが、A から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は A と10月は R)。</span><span class="sxs-lookup"><span data-stu-id="619a2-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="619a2-290">Genders を区別するために、誕生日に対応する2桁の数字は、女性の誕生日に40が追加されます。</span><span class="sxs-lookup"><span data-stu-id="619a2-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="619a2-291">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字 (国全体のコードは外国で使用されます)</span><span class="sxs-lookup"><span data-stu-id="619a2-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="619a2-292">1つのパリティ付き数字</span><span class="sxs-lookup"><span data-stu-id="619a2-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-293">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-293">Checksum</span></span>

<span data-ttu-id="619a2-294">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-295">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-295">Definition</span></span>

<span data-ttu-id="619a2-296">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-297">関数`Func_italy_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-298">From `Keywords_italy_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-299">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-300">関数`Func_italy_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-301">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-301">Keywords</span></span>

#### <a name="keywordsitalyeunationalidcard"></a><span data-ttu-id="619a2-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="619a2-303">個人コード</span><span class="sxs-lookup"><span data-stu-id="619a2-303">personal code</span></span>
  
<span data-ttu-id="619a2-304">個人コード番号</span><span class="sxs-lookup"><span data-stu-id="619a2-304">personal code number</span></span>
  
<span data-ttu-id="619a2-305">個人証明書番号</span><span class="sxs-lookup"><span data-stu-id="619a2-305">personal certificate number</span></span>
  
<span data-ttu-id="619a2-306">会計コード</span><span class="sxs-lookup"><span data-stu-id="619a2-306">fiscal code</span></span>
  
<span data-ttu-id="619a2-307">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="619a2-307">personalcodeno#</span></span>
  
<span data-ttu-id="619a2-308">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-308">personal id number</span></span>
  
<span data-ttu-id="619a2-309">個人 id コード</span><span class="sxs-lookup"><span data-stu-id="619a2-309">personal id code</span></span>
  
<span data-ttu-id="619a2-310">codice 個人 ale</span><span class="sxs-lookup"><span data-stu-id="619a2-310">codice personale</span></span>
  
<span data-ttu-id="619a2-311">numero certificato 個人 ale</span><span class="sxs-lookup"><span data-stu-id="619a2-311">numero certificato personale</span></span>
  
<span data-ttu-id="619a2-312">numero 個人 ale</span><span class="sxs-lookup"><span data-stu-id="619a2-312">numero personale</span></span>
  
<span data-ttu-id="619a2-313">numero id 個人 ale</span><span class="sxs-lookup"><span data-stu-id="619a2-313">numero id personale</span></span>
  
<span data-ttu-id="619a2-314">codice id 個人 ale</span><span class="sxs-lookup"><span data-stu-id="619a2-314">codice id personale</span></span>
  
<span data-ttu-id="619a2-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="619a2-315">codice fiscale</span></span>
  
## <a name="italy"></a><span data-ttu-id="619a2-316">イタリア</span><span class="sxs-lookup"><span data-stu-id="619a2-316">Italy</span></span>

### <a name="format"></a><span data-ttu-id="619a2-317">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-317">Format</span></span>

<span data-ttu-id="619a2-318">11桁の数字と、指定された形式のハイフン</span><span class="sxs-lookup"><span data-stu-id="619a2-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-319">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-319">Pattern</span></span>

<span data-ttu-id="619a2-320">11桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="619a2-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="619a2-321">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="619a2-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="619a2-322">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="619a2-322">A hyphen</span></span>
    
- <span data-ttu-id="619a2-323">誕生日の世紀に対応する1桁の数字 (「0」、20世紀の場合は「1」、21世紀の場合は「2」)</span><span class="sxs-lookup"><span data-stu-id="619a2-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="619a2-324">ランダムに生成される4桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-325">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-325">Checksum</span></span>

<span data-ttu-id="619a2-326">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-327">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-327">Definition</span></span>

<span data-ttu-id="619a2-328">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-329">関数`Func_latvia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-330">From `Keywords_latvia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-331">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-332">関数`Func_latvia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-333">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-333">Keywords</span></span>

#### <a name="keywordslatviaeunationalidcard"></a><span data-ttu-id="619a2-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="619a2-335">個人コード</span><span class="sxs-lookup"><span data-stu-id="619a2-335">personal code</span></span>
  
<span data-ttu-id="619a2-336">個人コード番号</span><span class="sxs-lookup"><span data-stu-id="619a2-336">personal code number</span></span>
  
<span data-ttu-id="619a2-337">個人証明書番号</span><span class="sxs-lookup"><span data-stu-id="619a2-337">personal certificate number</span></span>
  
<span data-ttu-id="619a2-338">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="619a2-338">personalcodeno#</span></span>
  
<span data-ttu-id="619a2-339">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-339">personal id number</span></span>
  
<span data-ttu-id="619a2-340">個人 id コード</span><span class="sxs-lookup"><span data-stu-id="619a2-340">personal id code</span></span>
  
<span data-ttu-id="619a2-341">ペルソナ kods</span><span class="sxs-lookup"><span data-stu-id="619a2-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="619a2-342">リトアニア</span><span class="sxs-lookup"><span data-stu-id="619a2-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="619a2-343">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-343">Format</span></span>

<span data-ttu-id="619a2-344">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-345">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-345">Pattern</span></span>

<span data-ttu-id="619a2-346">スペースと区切り文字を含まない11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="619a2-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="619a2-347">ユーザーの性別および誕生世紀に対応する1桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="619a2-348">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="619a2-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="619a2-349">誕生日のシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="619a2-350">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-351">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-351">Checksum</span></span>

<span data-ttu-id="619a2-352">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-353">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-353">Definition</span></span>

<span data-ttu-id="619a2-354">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-355">関数`Func_lithuania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-356">From `Keywords_lithuania_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-357">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-358">関数`Func_lithuania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-359">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-359">Keywords</span></span>

#### <a name="keywordslithuaniaeunationalidcard"></a><span data-ttu-id="619a2-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="619a2-361">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="619a2-361">personal numeric code</span></span>
  
<span data-ttu-id="619a2-362">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-362">unique identification number</span></span>
  
<span data-ttu-id="619a2-363">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="619a2-363">citizen service number</span></span>
  
<span data-ttu-id="619a2-364">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-364">unique identity number</span></span>
  
<span data-ttu-id="619a2-365">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="619a2-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="619a2-366">個人コード</span><span class="sxs-lookup"><span data-stu-id="619a2-366">personal code.</span></span>
  
<span data-ttu-id="619a2-367">asmeninis skaitmeninis das</span><span class="sxs-lookup"><span data-stu-id="619a2-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="619a2-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="619a2-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="619a2-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="619a2-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="619a2-370">unikalus identifikavimo のための das</span><span class="sxs-lookup"><span data-stu-id="619a2-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="619a2-371">asmens のためのものです。</span><span class="sxs-lookup"><span data-stu-id="619a2-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="619a2-372">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="619a2-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="619a2-373">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-373">Format</span></span>

<span data-ttu-id="619a2-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-375">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-375">Pattern</span></span>

<span data-ttu-id="619a2-376">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-376">11 digits</span></span>
  
- <span data-ttu-id="619a2-377">ユーザーの性別および誕生世紀に対応する1桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="619a2-378">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="619a2-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="619a2-379">誕生日のシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="619a2-380">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-381">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-381">Checksum</span></span>

<span data-ttu-id="619a2-382">該当なし</span><span class="sxs-lookup"><span data-stu-id="619a2-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-383">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-383">Definition</span></span>

<span data-ttu-id="619a2-384">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-385">正規表現`Regex_luxemburg_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="619a2-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-386">From `Keywords_luxemburg_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="619a2-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-387">Keywords</span></span>

#### <a name="keywordsluxemburgeunationalidcard"></a><span data-ttu-id="619a2-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="619a2-389">個人 id</span><span class="sxs-lookup"><span data-stu-id="619a2-389">personal id</span></span>
  
<span data-ttu-id="619a2-390">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-390">personal id number</span></span>
  
<span data-ttu-id="619a2-391">パーソナル id no #</span><span class="sxs-lookup"><span data-stu-id="619a2-391">personalidno#</span></span>
  
<span data-ttu-id="619a2-392">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-392">unique id number</span></span>
  
<span data-ttu-id="619a2-393">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-393">personalidnumber#</span></span>
  
<span data-ttu-id="619a2-394">一意の id キー</span><span class="sxs-lookup"><span data-stu-id="619a2-394">unique id key</span></span>
  
<span data-ttu-id="619a2-395">個人 id コード</span><span class="sxs-lookup"><span data-stu-id="619a2-395">personal id code</span></span>
  
<span data-ttu-id="619a2-396">uniqueidkey#</span><span class="sxs-lookup"><span data-stu-id="619a2-396">uniqueidkey#</span></span>
  
<span data-ttu-id="619a2-397">個別のコード</span><span class="sxs-lookup"><span data-stu-id="619a2-397">individual code</span></span>
  
<span data-ttu-id="619a2-398">個別の id</span><span class="sxs-lookup"><span data-stu-id="619a2-398">individual id</span></span>
  
<span data-ttu-id="619a2-399">eindeutige id-nummer</span><span class="sxs-lookup"><span data-stu-id="619a2-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="619a2-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="619a2-400">eindeutige id</span></span>
  
<span data-ttu-id="619a2-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="619a2-401">id personnelle</span></span>
  
<span data-ttu-id="619a2-402">numéro d'identification 職員</span><span class="sxs-lookup"><span data-stu-id="619a2-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="619a2-403">idpersonnelle#</span><span class="sxs-lookup"><span data-stu-id="619a2-403">idpersonnelle#</span></span>
  
<span data-ttu-id="619a2-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="619a2-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="619a2-405">eindeutigeid#</span><span class="sxs-lookup"><span data-stu-id="619a2-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="619a2-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="619a2-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="619a2-407">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-407">Format</span></span>

<span data-ttu-id="619a2-408">7桁の数字の後に1文字</span><span class="sxs-lookup"><span data-stu-id="619a2-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-409">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-409">Pattern</span></span>

<span data-ttu-id="619a2-410">7桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="619a2-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="619a2-411">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="619a2-411">Seven digits</span></span> 
    
- <span data-ttu-id="619a2-412">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="619a2-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-413">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-413">Checksum</span></span>

<span data-ttu-id="619a2-414">該当なし</span><span class="sxs-lookup"><span data-stu-id="619a2-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-415">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-415">Definition</span></span>

<span data-ttu-id="619a2-416">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-417">正規表現`Regex_malta_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="619a2-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-418">From `Keywords_malta_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-419">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-420">正規表現`Regex_malta_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="619a2-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-421">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-421">Keywords</span></span>

#### <a name="keywordsmaltaeunationalidcard"></a><span data-ttu-id="619a2-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="619a2-423">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="619a2-423">personal numeric code</span></span>
  
<span data-ttu-id="619a2-424">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-424">unique identification number</span></span>
  
<span data-ttu-id="619a2-425">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="619a2-425">citizen service number</span></span>
  
<span data-ttu-id="619a2-426">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-426">unique identity number</span></span>
  
<span data-ttu-id="619a2-427">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="619a2-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="619a2-428">kodiċi numerali パーソナル i</span><span class="sxs-lookup"><span data-stu-id="619a2-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="619a2-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="619a2-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="619a2-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="619a2-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="619a2-431">numru ta ' 識別子 tuniku</span><span class="sxs-lookup"><span data-stu-id="619a2-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="619a2-432">オランダ</span><span class="sxs-lookup"><span data-stu-id="619a2-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="619a2-433">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-433">Format</span></span>

<span data-ttu-id="619a2-434">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-435">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-435">Pattern</span></span>

<span data-ttu-id="619a2-436">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="619a2-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-437">Checksum</span></span>

<span data-ttu-id="619a2-438">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-439">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-439">Definition</span></span>

<span data-ttu-id="619a2-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-441">関数`Func_netherlands_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-442">From キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-442">A keyword from is found.</span></span>
    
<span data-ttu-id="619a2-443">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-444">関数`Func_netherlands_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-445">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-445">Keywords</span></span>

#### <a name="keywordsnetherlandseunationalidcard"></a><span data-ttu-id="619a2-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="619a2-447">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="619a2-447">personal numeric code</span></span>
  
<span data-ttu-id="619a2-448">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-448">unique identification number</span></span>
  
<span data-ttu-id="619a2-449">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="619a2-449">citizen service number</span></span>
  
<span data-ttu-id="619a2-450">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-450">unique identity number</span></span>
  
<span data-ttu-id="619a2-451">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="619a2-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="619a2-452">bsn</span><span class="sxs-lookup"><span data-stu-id="619a2-452">bsn</span></span>
  
<span data-ttu-id="619a2-453">bsn</span><span class="sxs-lookup"><span data-stu-id="619a2-453">bsn#</span></span>
  
<span data-ttu-id="619a2-454">persoonlijke numerieke コード</span><span class="sxs-lookup"><span data-stu-id="619a2-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="619a2-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="619a2-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="619a2-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="619a2-456">burgerservicenummer</span></span>
  
<span data-ttu-id="619a2-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="619a2-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="619a2-458">ポーランド</span><span class="sxs-lookup"><span data-stu-id="619a2-458">Poland</span></span>

<span data-ttu-id="619a2-459">詳細については、「[機密情報の種類](what-the-sensitive-information-types-look-for.md)について」の「ポーランド国立 ID (pesel)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="619a2-460">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="619a2-460">Portugal</span></span>

<span data-ttu-id="619a2-461">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="619a2-462">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="619a2-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="619a2-463">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-463">Format</span></span>

<span data-ttu-id="619a2-464">13桁の数字 (スペースと区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="619a2-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-465">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-465">Pattern</span></span>

<span data-ttu-id="619a2-466">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="619a2-467">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-467">Checksum</span></span>

<span data-ttu-id="619a2-468">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-469">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-469">Definition</span></span>

<span data-ttu-id="619a2-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-471">関数`Func_romania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-472">From `Keywords_romania_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-474">関数`Func_romania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-475">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-475">Keywords</span></span>

#### <a name="keywordsromaniaeunationalidcard"></a><span data-ttu-id="619a2-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="619a2-477">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="619a2-477">personal numeric code</span></span>
  
<span data-ttu-id="619a2-478">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-478">unique identification number</span></span>
  
<span data-ttu-id="619a2-479">cnp</span><span class="sxs-lookup"><span data-stu-id="619a2-479">cnp</span></span>
  
<span data-ttu-id="619a2-480">cnp #</span><span class="sxs-lookup"><span data-stu-id="619a2-480">cnp#</span></span>
  
<span data-ttu-id="619a2-481">pin</span><span class="sxs-lookup"><span data-stu-id="619a2-481">pin</span></span>
  
<span data-ttu-id="619a2-482">pin</span><span class="sxs-lookup"><span data-stu-id="619a2-482">pin#</span></span>
  
<span data-ttu-id="619a2-483">保険番号</span><span class="sxs-lookup"><span data-stu-id="619a2-483">insurance number</span></span>
  
<span data-ttu-id="619a2-484">insurancenumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-484">insurancenumber#</span></span>
  
<span data-ttu-id="619a2-485">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-485">unique identity number</span></span>
  
<span data-ttu-id="619a2-486">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="619a2-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="619a2-487">cod 数値個人</span><span class="sxs-lookup"><span data-stu-id="619a2-487">cod numeric personal</span></span>
  
<span data-ttu-id="619a2-488">cod 識別子 (個人)</span><span class="sxs-lookup"><span data-stu-id="619a2-488">cod identificare personal</span></span>
  
<span data-ttu-id="619a2-489">cod の識別子は</span><span class="sxs-lookup"><span data-stu-id="619a2-489">cod unic identificare</span></span>
  
<span data-ttu-id="619a2-490">număr 個人用非 ic</span><span class="sxs-lookup"><span data-stu-id="619a2-490">număr personal unic</span></span>
  
<span data-ttu-id="619a2-491">număr 識別子縦</span><span class="sxs-lookup"><span data-stu-id="619a2-491">număr identitate</span></span>
  
<span data-ttu-id="619a2-492">număr 識別子の個人情報</span><span class="sxs-lookup"><span data-stu-id="619a2-492">număr identificare personal</span></span>
  
<span data-ttu-id="619a2-493">număridentitate#</span><span class="sxs-lookup"><span data-stu-id="619a2-493">număridentitate#</span></span>
  
<span data-ttu-id="619a2-494">codnumericpersonal#</span><span class="sxs-lookup"><span data-stu-id="619a2-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="619a2-495">numărpersonalunic#</span><span class="sxs-lookup"><span data-stu-id="619a2-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="619a2-496">スロバキア</span><span class="sxs-lookup"><span data-stu-id="619a2-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="619a2-497">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-497">Format</span></span>

<span data-ttu-id="619a2-498">1つの円記号を含む10桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-499">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-499">Pattern</span></span>

<span data-ttu-id="619a2-500">1つの円記号を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="619a2-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="619a2-501">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-501">Checksum</span></span>

<span data-ttu-id="619a2-502">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-503">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-503">Definition</span></span>

<span data-ttu-id="619a2-504">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-505">関数`Func_slovakia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-506">From `Keywords_slovakia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-508">関数`Func_slovakia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-509">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-509">Keywords</span></span>

#### <a name="keywordsslovakiaeunationalidcard"></a><span data-ttu-id="619a2-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="619a2-511">出生地番号</span><span class="sxs-lookup"><span data-stu-id="619a2-511">birth number</span></span>
  
<span data-ttu-id="619a2-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="619a2-512">national identification number</span></span>
  
<span data-ttu-id="619a2-513">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-513">personal identification number</span></span>
  
<span data-ttu-id="619a2-514">social security number</span><span class="sxs-lookup"><span data-stu-id="619a2-514">social security number</span></span>
  
<span data-ttu-id="619a2-515">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-515">nationalnumber#</span></span>
  
<span data-ttu-id="619a2-516">ssn</span><span class="sxs-lookup"><span data-stu-id="619a2-516">ssn#</span></span>
  
<span data-ttu-id="619a2-517">ssn</span><span class="sxs-lookup"><span data-stu-id="619a2-517">ssn</span></span>
  
<span data-ttu-id="619a2-518">国番号</span><span class="sxs-lookup"><span data-stu-id="619a2-518">national number</span></span>
  
<span data-ttu-id="619a2-519">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-519">personal id number</span></span>
  
<span data-ttu-id="619a2-520">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="619a2-520">personalidnumber#</span></span>
  
<span data-ttu-id="619a2-521">rč</span><span class="sxs-lookup"><span data-stu-id="619a2-521">rč</span></span>
  
<span data-ttu-id="619a2-522">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="619a2-522">rodné číslo</span></span>
  
<span data-ttu-id="619a2-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="619a2-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="619a2-524">スロベニア</span><span class="sxs-lookup"><span data-stu-id="619a2-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="619a2-525">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-525">Format</span></span>

<span data-ttu-id="619a2-526">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="619a2-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-527">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-527">Pattern</span></span>

<span data-ttu-id="619a2-528">指定したパターンの13桁の数字:</span><span class="sxs-lookup"><span data-stu-id="619a2-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="619a2-529">誕生日 (DDMMLLL) に対応する7桁の数字で、"LLL" は誕生年の最後の3桁に対応します。</span><span class="sxs-lookup"><span data-stu-id="619a2-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="619a2-530">誕生日の範囲に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="619a2-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="619a2-531">同じ日に生まれた人物の性別とシリアル番号の組み合わせに対応する3つの数字 (女性の場合は男性と500-999 は 000-499)</span><span class="sxs-lookup"><span data-stu-id="619a2-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="619a2-532">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="619a2-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-533">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-533">Checksum</span></span>

<span data-ttu-id="619a2-534">はい</span><span class="sxs-lookup"><span data-stu-id="619a2-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-535">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-535">Definition</span></span>

<span data-ttu-id="619a2-536">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-537">関数`Func_slovenia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-538">From `Keywords_slovenia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="619a2-539">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-540">関数`Func_slovenia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="619a2-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="619a2-541">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-541">Keywords</span></span>

#### <a name="keywordssloveniaeunationalidcard"></a><span data-ttu-id="619a2-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="619a2-543">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="619a2-543">personal numeric code</span></span>
  
<span data-ttu-id="619a2-544">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-544">unique identification number</span></span>
  
<span data-ttu-id="619a2-545">一意の登録番号</span><span class="sxs-lookup"><span data-stu-id="619a2-545">unique registration number</span></span>
  
<span data-ttu-id="619a2-546">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-546">unique identity number</span></span>
  
<span data-ttu-id="619a2-547">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="619a2-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="619a2-548">一意のマスター市民番号</span><span class="sxs-lookup"><span data-stu-id="619a2-548">unique master citizen number</span></span>
  
<span data-ttu-id="619a2-549">edinstベンダー a identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="619a2-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="619a2-550">uniqueidentityno #</span><span class="sxs-lookup"><span data-stu-id="619a2-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="619a2-551">edinstベンダー a številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="619a2-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="619a2-552">emšo</span><span class="sxs-lookup"><span data-stu-id="619a2-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="619a2-553">スペイン</span><span class="sxs-lookup"><span data-stu-id="619a2-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="619a2-554">Format</span><span class="sxs-lookup"><span data-stu-id="619a2-554">Format</span></span>

<span data-ttu-id="619a2-555">7桁の数字の後に1文字</span><span class="sxs-lookup"><span data-stu-id="619a2-555">Seven digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="619a2-556">パターン</span><span class="sxs-lookup"><span data-stu-id="619a2-556">Pattern</span></span>

<span data-ttu-id="619a2-557">7桁の数字の後に1文字</span><span class="sxs-lookup"><span data-stu-id="619a2-557">Seven digits followed by one character</span></span>
  
- <span data-ttu-id="619a2-558">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="619a2-558">Seven digits</span></span>
    
- <span data-ttu-id="619a2-559">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="619a2-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="619a2-560">チェックサム</span><span class="sxs-lookup"><span data-stu-id="619a2-560">Checksum</span></span>

<span data-ttu-id="619a2-561">該当なし</span><span class="sxs-lookup"><span data-stu-id="619a2-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="619a2-562">定義</span><span class="sxs-lookup"><span data-stu-id="619a2-562">Definition</span></span>

<span data-ttu-id="619a2-563">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="619a2-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="619a2-564">正規表現`Regex_spain_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="619a2-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="619a2-565">From `Keywords_spain_eu_national_id_card"`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="619a2-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="619a2-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="619a2-566">Keywords</span></span>

#### <a name="keywordsspaineunationalidcard"></a><span data-ttu-id="619a2-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="619a2-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="619a2-568">dni</span><span class="sxs-lookup"><span data-stu-id="619a2-568">dni</span></span>
  
<span data-ttu-id="619a2-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="619a2-569">national identification number</span></span>
  
<span data-ttu-id="619a2-570">国内の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-570">national identity number</span></span>
  
<span data-ttu-id="619a2-571">保険番号</span><span class="sxs-lookup"><span data-stu-id="619a2-571">insurance number</span></span>
  
<span data-ttu-id="619a2-572">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="619a2-572">personal identification number</span></span>
  
<span data-ttu-id="619a2-573">国民 id</span><span class="sxs-lookup"><span data-stu-id="619a2-573">national identity</span></span>
  
<span data-ttu-id="619a2-574">個人 id いいえ</span><span class="sxs-lookup"><span data-stu-id="619a2-574">personal identity no</span></span>
  
<span data-ttu-id="619a2-575">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="619a2-575">unique identity number</span></span>
  
<span data-ttu-id="619a2-576">nationalidno#</span><span class="sxs-lookup"><span data-stu-id="619a2-576">nationalidno#</span></span>
  
<span data-ttu-id="619a2-577">見つから</span><span class="sxs-lookup"><span data-stu-id="619a2-577">uniqueid#</span></span>
  
<span data-ttu-id="619a2-578">dni</span><span class="sxs-lookup"><span data-stu-id="619a2-578">dni#</span></span>
  
<span data-ttu-id="619a2-579">nationalid#</span><span class="sxs-lookup"><span data-stu-id="619a2-579">nationalid#</span></span>
  
<span data-ttu-id="619a2-580">nie#</span><span class="sxs-lookup"><span data-stu-id="619a2-580">nie#</span></span>
  
<span data-ttu-id="619a2-581">nie</span><span class="sxs-lookup"><span data-stu-id="619a2-581">nie</span></span>
  
<span data-ttu-id="619a2-582">nienúmero#</span><span class="sxs-lookup"><span data-stu-id="619a2-582">nienúmero#</span></span>
  
<span data-ttu-id="619a2-583">nie número</span><span class="sxs-lookup"><span data-stu-id="619a2-583">nie número</span></span>
  
<span data-ttu-id="619a2-584">documento nacional de 識別子 dad</span><span class="sxs-lookup"><span data-stu-id="619a2-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="619a2-585">dad único の識別子</span><span class="sxs-lookup"><span data-stu-id="619a2-585">identidad único</span></span>
  
<span data-ttu-id="619a2-586">número nacional 識別子 dad</span><span class="sxs-lookup"><span data-stu-id="619a2-586">número nacional identidad</span></span>
  
<span data-ttu-id="619a2-587">dni número</span><span class="sxs-lookup"><span data-stu-id="619a2-587">dni número</span></span>
  
<span data-ttu-id="619a2-588">dninúmero#</span><span class="sxs-lookup"><span data-stu-id="619a2-588">dninúmero#</span></span>
  
<span data-ttu-id="619a2-589">identidadúnico#</span><span class="sxs-lookup"><span data-stu-id="619a2-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="619a2-590">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="619a2-590">Sweden</span></span>

<span data-ttu-id="619a2-591">詳細については、「スウェーデン国立 ID」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="619a2-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="619a2-592">関連項目</span><span class="sxs-lookup"><span data-stu-id="619a2-592">See also</span></span>

[<span data-ttu-id="619a2-593">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="619a2-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

