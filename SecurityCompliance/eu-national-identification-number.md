---
title: EU 国家識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 国内の識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: b784b7509eed899f9f03db96ee5e827b9bf70d2e
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852749"
---
# <a name="eu-national-identification-number"></a><span data-ttu-id="4f517-104">EU 国家識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-104">EU National Identification Number</span></span>

<span data-ttu-id="4f517-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 国内の識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="4f517-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU National Identification Number sensitive information type.</span></span> <span data-ttu-id="4f517-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="4f517-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="4f517-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="4f517-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="4f517-108">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-108">Format</span></span>

<span data-ttu-id="4f517-109">24文字の文字、数字、特殊文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="4f517-109">A 24-character combination of letters, digits, and special characters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-110">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-110">Pattern</span></span>

<span data-ttu-id="4f517-111">24文字:</span><span class="sxs-lookup"><span data-stu-id="4f517-111">24 characters:</span></span>
  
-  <span data-ttu-id="4f517-112">22文字 (大文字小文字を区別しない)、数字、円記号、スラッシュ、またはプラス記号</span><span class="sxs-lookup"><span data-stu-id="4f517-112">22 letters (not case-sensitive), digits, backslashes, forward slashes, or plus signs</span></span> 
    
- <span data-ttu-id="4f517-113">2つの文字 (大文字小文字を区別しない)、数字、バックスラッシュ、スラッシュ、プラス記号、または等号</span><span class="sxs-lookup"><span data-stu-id="4f517-113">Two letters (not case-sensitive), digits, backslashes, forward slashes, plus signs, or equal signs</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-114">Checksum</span></span>

<span data-ttu-id="4f517-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="4f517-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-116">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-116">Definition</span></span>

<span data-ttu-id="4f517-117">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-118">正規表現`Regex_austria_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="4f517-118">The regular expression  `Regex_austria_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-119">From `Keywords_austria_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-119">A keyword from  `Keywords_austria_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_national_id_card" />
          <Match idRef="Keywords_austria_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4f517-120">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-120">Keywords</span></span>

#### <a name="keywords_austria_eu_national_id_card"></a><span data-ttu-id="4f517-121">Keywords_austria_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-121">Keywords_austria_eu_national_id_card</span></span>

<span data-ttu-id="4f517-122">オーストリアの id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-122">austrian identity number</span></span>
  
<span data-ttu-id="4f517-123">国内の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-123">national identity number</span></span>
  
<span data-ttu-id="4f517-124">id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-124">identity number</span></span>
  
<span data-ttu-id="4f517-125">national id</span><span class="sxs-lookup"><span data-stu-id="4f517-125">national id</span></span>
  
<span data-ttu-id="4f517-126">personalausweis republik österreich</span><span class="sxs-lookup"><span data-stu-id="4f517-126">personalausweis republik österreich</span></span>
  
## <a name="belgium"></a><span data-ttu-id="4f517-127">ベルギー</span><span class="sxs-lookup"><span data-stu-id="4f517-127">Belgium</span></span>

<span data-ttu-id="4f517-128">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ベルギー国立番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-128">For details, see the section "Belgium National Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="4f517-129">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="4f517-129">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="4f517-130">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-130">Format</span></span>

<span data-ttu-id="4f517-131">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-131">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-132">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-132">Pattern</span></span>

<span data-ttu-id="4f517-133">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-133">Ten digits without spaces and delimiters</span></span>
  
-  <span data-ttu-id="4f517-134">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="4f517-134">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="4f517-135">誕生日の順序に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-135">Two digits that correspond to the birth order</span></span>
    
- <span data-ttu-id="4f517-136">性別に対応する1桁の数字: 男性の偶数桁で、女性に奇数の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-136">One digit that corresponds to gender: An even digit for male and an odd digit for female</span></span>
    
- <span data-ttu-id="4f517-137">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-137">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-138">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-138">Checksum</span></span>

<span data-ttu-id="4f517-139">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-139">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-140">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-140">Definition</span></span>

<span data-ttu-id="4f517-141">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-141">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-142">関数`Func_bulgaria_national_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-142">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-143">From `Keywords_bulgaria_national_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-143">A keyword from  `Keywords_bulgaria_national_number` is found.</span></span> 
    
<span data-ttu-id="4f517-144">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-144">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-145">関数`Func_bulgaria_national_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-145">The function  `Func_bulgaria_national_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-146">Keywords</span></span>

#### <a name="keywords_bulgaria_national_number"></a><span data-ttu-id="4f517-147">Keywords_bulgaria_national_number</span><span class="sxs-lookup"><span data-stu-id="4f517-147">Keywords_bulgaria_national_number</span></span>

<span data-ttu-id="4f517-148">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="4f517-148">egn</span></span>
  
<span data-ttu-id="4f517-149">「//入力 n」#</span><span class="sxs-lookup"><span data-stu-id="4f517-149">egn#</span></span>
  
<span data-ttu-id="4f517-150">ブルガリアの国番号</span><span class="sxs-lookup"><span data-stu-id="4f517-150">bulgarian national number</span></span>
  
<span data-ttu-id="4f517-151">国番号</span><span class="sxs-lookup"><span data-stu-id="4f517-151">national number</span></span>
  
<span data-ttu-id="4f517-152">social security number</span><span class="sxs-lookup"><span data-stu-id="4f517-152">social security number</span></span>
  
<span data-ttu-id="4f517-153">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-153">nationalnumber#</span></span>
  
<span data-ttu-id="4f517-154">ssn#</span><span class="sxs-lookup"><span data-stu-id="4f517-154">ssn#</span></span>
  
<span data-ttu-id="4f517-155">ssn</span><span class="sxs-lookup"><span data-stu-id="4f517-155">ssn</span></span>
  
<span data-ttu-id="4f517-156">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="4f517-156">nationalnumber</span></span>
  
<span data-ttu-id="4f517-157">bnn#</span><span class="sxs-lookup"><span data-stu-id="4f517-157">bnn#</span></span>
  
<span data-ttu-id="4f517-158">bnn</span><span class="sxs-lookup"><span data-stu-id="4f517-158">bnn</span></span>
  
<span data-ttu-id="4f517-159">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-159">personal id number</span></span>
  
<span data-ttu-id="4f517-160">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-160">personalidnumber#</span></span>
  
<span data-ttu-id="4f517-161">единен граждански номер</span><span class="sxs-lookup"><span data-stu-id="4f517-161">единен граждански номер</span></span>
  
<span data-ttu-id="4f517-162">edinen grazhdanski nomer</span><span class="sxs-lookup"><span data-stu-id="4f517-162">edinen grazhdanski nomer</span></span>
  
<span data-ttu-id="4f517-163">егн</span><span class="sxs-lookup"><span data-stu-id="4f517-163">егн</span></span>
  
<span data-ttu-id="4f517-164">егн#</span><span class="sxs-lookup"><span data-stu-id="4f517-164">егн#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="4f517-165">クロアチア</span><span class="sxs-lookup"><span data-stu-id="4f517-165">Croatia</span></span>

<span data-ttu-id="4f517-166">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「クロアチアの id 番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-166">For details, see the section "Croatia Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="4f517-167">キプロス</span><span class="sxs-lookup"><span data-stu-id="4f517-167">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="4f517-168">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-168">Format</span></span>

<span data-ttu-id="4f517-169">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-169">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-170">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-170">Pattern</span></span>

 <span data-ttu-id="4f517-171">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-171">Ten digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="4f517-172">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-172">Checksum</span></span>

<span data-ttu-id="4f517-173">該当なし</span><span class="sxs-lookup"><span data-stu-id="4f517-173">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-174">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-174">Definition</span></span>

<span data-ttu-id="4f517-175">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-175">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-176">正規表現`Regex_cyprus_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="4f517-176">The regular expression  `Regex_cyprus_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-177">From `Keywords_cyprus_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-177">A keyword from  `Keywords_cyprus_eu_national_id_card` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_national_id_card" />
          <Match idRef="Keywords_cyprus_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4f517-178">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-178">Keywords</span></span>

#### <a name="keywords_cyprus_eu_national_id_card"></a><span data-ttu-id="4f517-179">Keywords_cyprus_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-179">Keywords_cyprus_eu_national_id_card</span></span>

<span data-ttu-id="4f517-180">id カード番号</span><span class="sxs-lookup"><span data-stu-id="4f517-180">id card number</span></span>
  
<span data-ttu-id="4f517-181">national identification number</span><span class="sxs-lookup"><span data-stu-id="4f517-181">national identification number</span></span>
  
<span data-ttu-id="4f517-182">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-182">personal id number</span></span>
  
<span data-ttu-id="4f517-183">id カード番号</span><span class="sxs-lookup"><span data-stu-id="4f517-183">identity card number</span></span>
  
<span data-ttu-id="4f517-184">ταυτοτητασ</span><span class="sxs-lookup"><span data-stu-id="4f517-184">ταυτοτητασ</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="4f517-185">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="4f517-185">Czech Republic</span></span>

<span data-ttu-id="4f517-186">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「チェコ国立 id 番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-186">For details, see the section "Czech National Identity Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="denmark"></a><span data-ttu-id="4f517-187">デンマーク</span><span class="sxs-lookup"><span data-stu-id="4f517-187">Denmark</span></span>

<span data-ttu-id="4f517-188">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「デンマークの個人識別番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-188">For details, see the section "Denmark Personal Identification Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="estonia"></a><span data-ttu-id="4f517-189">エストニア</span><span class="sxs-lookup"><span data-stu-id="4f517-189">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="4f517-190">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-190">Format</span></span>

<span data-ttu-id="4f517-191">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-191">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-192">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-192">Pattern</span></span>

<span data-ttu-id="4f517-193">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="4f517-193">11 digits:</span></span>
  
- <span data-ttu-id="4f517-194">性別と世紀に対応する1桁の数字 (奇数個の男性、偶数の女性、1-2:19 世紀、3-4:20 世紀、5-6:21 世紀)</span><span class="sxs-lookup"><span data-stu-id="4f517-194">One digit that corresponds to sex and century of birth (odd number male, even number female; 1-2: 19th century; 3-4: 20th century; 5-6: 21st century)</span></span>
    
- <span data-ttu-id="4f517-195">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="4f517-195">Six digits that correspond to date of birth (YYMMDD)</span></span>
    
- <span data-ttu-id="4f517-196">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-196">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="4f517-197">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-197">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-198">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-198">Checksum</span></span>

<span data-ttu-id="4f517-199">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-199">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-200">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-200">Definition</span></span>

<span data-ttu-id="4f517-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-201">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-202">関数`Func_estonia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-202">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-203">From `Keywords_estonia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-203">A keyword from  `Keywords_estonia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-204">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-204">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-205">関数`Func_estonia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-205">The function  `Func_estonia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-206">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-206">Keywords</span></span>

#### <a name="keywords_estonia_eu_national_id_card"></a><span data-ttu-id="4f517-207">Keywords_estonia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-207">Keywords_estonia_eu_national_id_card</span></span>

<span data-ttu-id="4f517-208">個人識別コード</span><span class="sxs-lookup"><span data-stu-id="4f517-208">personal identification code</span></span>
  
<span data-ttu-id="4f517-209">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-209">personal identification number</span></span>
  
<span data-ttu-id="4f517-210">national identification number</span><span class="sxs-lookup"><span data-stu-id="4f517-210">national identification number</span></span>
  
<span data-ttu-id="4f517-211">国番号</span><span class="sxs-lookup"><span data-stu-id="4f517-211">national number</span></span>
  
<span data-ttu-id="4f517-212">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-212">personal id number</span></span>
  
<span data-ttu-id="4f517-213">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-213">personalidnumber#</span></span>
  
<span data-ttu-id="4f517-214">ik</span><span class="sxs-lookup"><span data-stu-id="4f517-214">ik</span></span>
  
<span data-ttu-id="4f517-215">isikukood</span><span class="sxs-lookup"><span data-stu-id="4f517-215">isikukood</span></span>
  
<span data-ttu-id="4f517-216">id-kaart</span><span class="sxs-lookup"><span data-stu-id="4f517-216">id-kaart</span></span>
  
## <a name="finland"></a><span data-ttu-id="4f517-217">フィンランド</span><span class="sxs-lookup"><span data-stu-id="4f517-217">Finland</span></span>

<span data-ttu-id="4f517-218">詳細については、「フィンランド国立 ID」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-218">For details, see the section "Finland National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="4f517-219">フランス</span><span class="sxs-lookup"><span data-stu-id="4f517-219">France</span></span>

<span data-ttu-id="4f517-220">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランス国立 ID カード (CNI)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-220">For details, see the section "France National ID Card (CNI)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="4f517-221">ドイツ</span><span class="sxs-lookup"><span data-stu-id="4f517-221">Germany</span></span>

<span data-ttu-id="4f517-222">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの Id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-222">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="4f517-223">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="4f517-223">Greece</span></span>

<span data-ttu-id="4f517-224">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-224">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="4f517-225">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="4f517-225">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="4f517-226">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-226">Format</span></span>

<span data-ttu-id="4f517-227">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-227">11 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-228">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-228">Pattern</span></span>

<span data-ttu-id="4f517-229">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="4f517-229">11 digits:</span></span>
  
-  <span data-ttu-id="4f517-230">性別に対応する1桁の数字 (1-オス、2-女性、その他の数字は1900または市民が二重市民権を持つ市民の場合もあります)</span><span class="sxs-lookup"><span data-stu-id="4f517-230">One digit that corresponds to gender (1-male, 2-female, other numbers are also possible for citizens born before 1900 or citizens with double citizenship)</span></span> 
    
- <span data-ttu-id="4f517-231">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="4f517-231">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="4f517-232">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-232">Three digits that correspond to a serial number</span></span>
    
- <span data-ttu-id="4f517-233">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-233">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-234">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-234">Checksum</span></span>

<span data-ttu-id="4f517-235">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-235">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-236">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-236">Definition</span></span>

<span data-ttu-id="4f517-237">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-237">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-238">関数`Func_hungary_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-238">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-239">From `Keywords_hungary_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-239">A keyword from  `Keywords_hungary_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-240">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-240">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-241">関数`Func_hungary_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-241">The function  `Func_hungary_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-242">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-242">Keywords</span></span>

#### <a name="keywords_hungary_eu_national_id_card"></a><span data-ttu-id="4f517-243">Keywords_hungary_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-243">Keywords_hungary_eu_national_id_card</span></span>

<span data-ttu-id="4f517-244">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-244">personal identification number</span></span>
  
<span data-ttu-id="4f517-245">identification number</span><span class="sxs-lookup"><span data-stu-id="4f517-245">identification number</span></span>
  
<span data-ttu-id="4f517-246">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-246">personal id number</span></span>
  
<span data-ttu-id="4f517-247">személyazonosító igazolvány</span><span class="sxs-lookup"><span data-stu-id="4f517-247">személyazonosító igazolvány</span></span>
  
## <a name="ireland"></a><span data-ttu-id="4f517-248">アイルランド</span><span class="sxs-lookup"><span data-stu-id="4f517-248">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="4f517-249">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-249">Format</span></span>

<span data-ttu-id="4f517-250">指定したパターンの文字、数字、スペースの9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="4f517-250">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-251">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-251">Pattern</span></span>

<span data-ttu-id="4f517-252">指定したパターンの文字、数字、スペースの9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="4f517-252">A nine-character combination of letters, digits, and a space in the specified pattern</span></span>
  
<span data-ttu-id="4f517-253">01年 1 2013 月から今すぐに。</span><span class="sxs-lookup"><span data-stu-id="4f517-253">From 01 January 2013 to now:</span></span>
  
-  <span data-ttu-id="4f517-254">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="4f517-254">Seven digits</span></span> 
    
- <span data-ttu-id="4f517-255">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-255">One check digit</span></span>
    
- <span data-ttu-id="4f517-256">1つのスペースまたは大文字の "W" (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="4f517-256">One space or the uppercase letter "W" (Case sensitive)</span></span>
    
<span data-ttu-id="4f517-257">01年1月2013前:</span><span class="sxs-lookup"><span data-stu-id="4f517-257">Prior to 01 January 2013:</span></span>
  
-  <span data-ttu-id="4f517-258">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="4f517-258">Seven digits</span></span> 
    
- <span data-ttu-id="4f517-259">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-259">One check digit</span></span>
    
- <span data-ttu-id="4f517-260">1つのスペースまたは大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="4f517-260">One space or an uppercase letter (Case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-261">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-261">Checksum</span></span>

<span data-ttu-id="4f517-262">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-262">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-263">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-263">Definition</span></span>

<span data-ttu-id="4f517-264">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-264">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-265">関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-265">The function finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="4f517-266">From キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-266">A keyword from is found.</span></span>
    
<span data-ttu-id="4f517-267">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-268">関数は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-268">The function finds content that matches the pattern.</span></span>
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-269">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-269">Keywords</span></span>

#### <a name="keywords_ireland_eu_national_id_card"></a><span data-ttu-id="4f517-270">Keywords_ireland_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-270">Keywords_ireland_eu_national_id_card</span></span>

<span data-ttu-id="4f517-271">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="4f517-271">personal public service number</span></span>
  
<span data-ttu-id="4f517-272">pps no</span><span class="sxs-lookup"><span data-stu-id="4f517-272">pps no</span></span>
  
<span data-ttu-id="4f517-273">収益および社会保険番号</span><span class="sxs-lookup"><span data-stu-id="4f517-273">revenue and social insurance number</span></span>
  
<span data-ttu-id="4f517-274">rsi no</span><span class="sxs-lookup"><span data-stu-id="4f517-274">rsi no</span></span>
  
<span data-ttu-id="4f517-275">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-275">personal identification number</span></span>
  
<span data-ttu-id="4f517-276">identification number</span><span class="sxs-lookup"><span data-stu-id="4f517-276">identification number</span></span>
  
<span data-ttu-id="4f517-277">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-277">personal id number</span></span>
  
<span data-ttu-id="4f517-278">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="4f517-278">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="4f517-279">uimh.</span><span class="sxs-lookup"><span data-stu-id="4f517-279">uimh.</span></span> <span data-ttu-id="4f517-280">psp</span><span class="sxs-lookup"><span data-stu-id="4f517-280">psp</span></span>
  
## <a name="italy"></a><span data-ttu-id="4f517-281">イタリア</span><span class="sxs-lookup"><span data-stu-id="4f517-281">Italy</span></span>

### <a name="format"></a><span data-ttu-id="4f517-282">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-282">Format</span></span>

<span data-ttu-id="4f517-283">指定したパターンの文字と数字の16文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="4f517-283">A 16-character combination of letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-284">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-284">Pattern</span></span>

<span data-ttu-id="4f517-285">文字と数字の16文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="4f517-285">A 16-character combination of letters and digits:</span></span>
  
- <span data-ttu-id="4f517-286">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="4f517-286">Three letters that correspond to the first three consonants in the family name</span></span>
    
- <span data-ttu-id="4f517-287">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="4f517-287">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="4f517-288">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-288">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="4f517-289">誕生日の文字に対応する1つの文字-文字はアルファベット順に使用されますが、A から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は A と10月は R)。</span><span class="sxs-lookup"><span data-stu-id="4f517-289">One letter that corresponds to the letter for the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="4f517-290">Genders を区別するために、誕生日に対応する2桁の数字は、女性の誕生日に40が追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f517-290">Two digits that correspond to the day of the month of birth—in order to differentiate between genders, 40 is added to the day of birth for women</span></span>
    
- <span data-ttu-id="4f517-291">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字 (国全体のコードは外国で使用されます)</span><span class="sxs-lookup"><span data-stu-id="4f517-291">Four digits that corresponds to the area code specific to the municipality where the person was born (country-wide codes are used for foreign countries)</span></span>
    
- <span data-ttu-id="4f517-292">1つのパリティ付き数字</span><span class="sxs-lookup"><span data-stu-id="4f517-292">One parity digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-293">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-293">Checksum</span></span>

<span data-ttu-id="4f517-294">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-294">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-295">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-295">Definition</span></span>

<span data-ttu-id="4f517-296">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-296">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-297">関数`Func_italy_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-297">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-298">From `Keywords_italy_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-298">A keyword from  `Keywords_italy_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-299">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-299">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-300">関数`Func_italy_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-300">The function  `Func_italy_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-301">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-301">Keywords</span></span>

#### <a name="keywords_italy_eu_national_id_card"></a><span data-ttu-id="4f517-302">Keywords_italy_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-302">Keywords_italy_eu_national_id_card</span></span>

<span data-ttu-id="4f517-303">個人コード</span><span class="sxs-lookup"><span data-stu-id="4f517-303">personal code</span></span>
  
<span data-ttu-id="4f517-304">個人コード番号</span><span class="sxs-lookup"><span data-stu-id="4f517-304">personal code number</span></span>
  
<span data-ttu-id="4f517-305">個人証明書番号</span><span class="sxs-lookup"><span data-stu-id="4f517-305">personal certificate number</span></span>
  
<span data-ttu-id="4f517-306">会計コード</span><span class="sxs-lookup"><span data-stu-id="4f517-306">fiscal code</span></span>
  
<span data-ttu-id="4f517-307">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="4f517-307">personalcodeno#</span></span>
  
<span data-ttu-id="4f517-308">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-308">personal id number</span></span>
  
<span data-ttu-id="4f517-309">個人 id コード</span><span class="sxs-lookup"><span data-stu-id="4f517-309">personal id code</span></span>
  
<span data-ttu-id="4f517-310">codice 個人 ale</span><span class="sxs-lookup"><span data-stu-id="4f517-310">codice personale</span></span>
  
<span data-ttu-id="4f517-311">numero certificato 個人 ale</span><span class="sxs-lookup"><span data-stu-id="4f517-311">numero certificato personale</span></span>
  
<span data-ttu-id="4f517-312">numero 個人 ale</span><span class="sxs-lookup"><span data-stu-id="4f517-312">numero personale</span></span>
  
<span data-ttu-id="4f517-313">numero id 個人 ale</span><span class="sxs-lookup"><span data-stu-id="4f517-313">numero id personale</span></span>
  
<span data-ttu-id="4f517-314">codice id 個人 ale</span><span class="sxs-lookup"><span data-stu-id="4f517-314">codice id personale</span></span>
  
<span data-ttu-id="4f517-315">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="4f517-315">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="4f517-316">ラトビア</span><span class="sxs-lookup"><span data-stu-id="4f517-316">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="4f517-317">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-317">Format</span></span>

<span data-ttu-id="4f517-318">11桁の数字と、指定された形式のハイフン</span><span class="sxs-lookup"><span data-stu-id="4f517-318">11 digits and a hyphen in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-319">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-319">Pattern</span></span>

<span data-ttu-id="4f517-320">11桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="4f517-320">11 digits and a hyphen:</span></span>
  
-  <span data-ttu-id="4f517-321">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="4f517-321">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="4f517-322">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="4f517-322">A hyphen</span></span>
    
- <span data-ttu-id="4f517-323">誕生日の世紀に対応する1桁の数字 (「0」、20世紀の場合は「1」、21世紀の場合は「2」)</span><span class="sxs-lookup"><span data-stu-id="4f517-323">One digit that corresponds to the century of birth ("0" for 19th century, "1" for 20th century, and "2" for 21st century)</span></span>
    
- <span data-ttu-id="4f517-324">ランダムに生成される4桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-324">Four digits, randomly generated</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-325">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-325">Checksum</span></span>

<span data-ttu-id="4f517-326">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-326">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-327">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-327">Definition</span></span>

<span data-ttu-id="4f517-328">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-328">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-329">関数`Func_latvia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-329">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-330">From `Keywords_latvia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-330">A keyword from  `Keywords_latvia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-331">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-331">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-332">関数`Func_latvia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-332">The function  `Func_latvia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-333">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-333">Keywords</span></span>

#### <a name="keywords_latvia_eu_national_id_card"></a><span data-ttu-id="4f517-334">Keywords_latvia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-334">Keywords_latvia_eu_national_id_card</span></span>

<span data-ttu-id="4f517-335">個人コード</span><span class="sxs-lookup"><span data-stu-id="4f517-335">personal code</span></span>
  
<span data-ttu-id="4f517-336">個人コード番号</span><span class="sxs-lookup"><span data-stu-id="4f517-336">personal code number</span></span>
  
<span data-ttu-id="4f517-337">個人証明書番号</span><span class="sxs-lookup"><span data-stu-id="4f517-337">personal certificate number</span></span>
  
<span data-ttu-id="4f517-338">personalcodeno#</span><span class="sxs-lookup"><span data-stu-id="4f517-338">personalcodeno#</span></span>
  
<span data-ttu-id="4f517-339">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-339">personal id number</span></span>
  
<span data-ttu-id="4f517-340">個人 id コード</span><span class="sxs-lookup"><span data-stu-id="4f517-340">personal id code</span></span>
  
<span data-ttu-id="4f517-341">ペルソナ kods</span><span class="sxs-lookup"><span data-stu-id="4f517-341">personas kods</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="4f517-342">リトアニア</span><span class="sxs-lookup"><span data-stu-id="4f517-342">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="4f517-343">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-343">Format</span></span>

<span data-ttu-id="4f517-344">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-344">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-345">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-345">Pattern</span></span>

<span data-ttu-id="4f517-346">スペースと区切り文字を含まない11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="4f517-346">11 digits without spaces and delimiters:</span></span>
  
- <span data-ttu-id="4f517-347">ユーザーの性別および誕生世紀に対応する1桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-347">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="4f517-348">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="4f517-348">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="4f517-349">誕生日のシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-349">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="4f517-350">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-350">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-351">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-351">Checksum</span></span>

<span data-ttu-id="4f517-352">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-352">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-353">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-353">Definition</span></span>

<span data-ttu-id="4f517-354">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-354">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-355">関数`Func_lithuania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-355">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-356">From `Keywords_lithuania_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-356">A keyword from  `Keywords_lithuania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-357">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-358">関数`Func_lithuania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-358">The function  `Func_lithuania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-359">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-359">Keywords</span></span>

#### <a name="keywords_lithuania_eu_national_id_card"></a><span data-ttu-id="4f517-360">Keywords_lithuania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-360">Keywords_lithuania_eu_national_id_card</span></span>

<span data-ttu-id="4f517-361">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="4f517-361">personal numeric code</span></span>
  
<span data-ttu-id="4f517-362">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-362">unique identification number</span></span>
  
<span data-ttu-id="4f517-363">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="4f517-363">citizen service number</span></span>
  
<span data-ttu-id="4f517-364">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-364">unique identity number</span></span>
  
<span data-ttu-id="4f517-365">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="4f517-365">uniqueidentityno#</span></span>
  
<span data-ttu-id="4f517-366">個人コード</span><span class="sxs-lookup"><span data-stu-id="4f517-366">personal code.</span></span>
  
<span data-ttu-id="4f517-367">asmeninis skaitmeninis das</span><span class="sxs-lookup"><span data-stu-id="4f517-367">asmeninis skaitmeninis kodas</span></span>
  
<span data-ttu-id="4f517-368">unikalus identifikavimo numeris</span><span class="sxs-lookup"><span data-stu-id="4f517-368">unikalus identifikavimo numeris</span></span>
  
<span data-ttu-id="4f517-369">piliečio paslaugos numeris</span><span class="sxs-lookup"><span data-stu-id="4f517-369">piliečio paslaugos numeris</span></span>
  
<span data-ttu-id="4f517-370">unikalus identifikavimo のための das</span><span class="sxs-lookup"><span data-stu-id="4f517-370">unikalus identifikavimo kodas</span></span>
  
<span data-ttu-id="4f517-371">asmens のためのものです。</span><span class="sxs-lookup"><span data-stu-id="4f517-371">asmens kodas.</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="4f517-372">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="4f517-372">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="4f517-373">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-373">Format</span></span>

<span data-ttu-id="4f517-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-375">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-375">Pattern</span></span>

<span data-ttu-id="4f517-376">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-376">11 digits</span></span>
  
- <span data-ttu-id="4f517-377">ユーザーの性別および誕生世紀に対応する1桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-377">One digit that corresponds to the person's gender and century of birth</span></span>
    
-  <span data-ttu-id="4f517-378">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="4f517-378">Six digits that correspond to birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="4f517-379">誕生日のシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-379">Three digits that correspond to the serial number of the date of birth</span></span>
    
- <span data-ttu-id="4f517-380">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-380">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-381">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-381">Checksum</span></span>

<span data-ttu-id="4f517-382">該当なし</span><span class="sxs-lookup"><span data-stu-id="4f517-382">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-383">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-383">Definition</span></span>

<span data-ttu-id="4f517-384">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-384">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-385">正規表現`Regex_luxemburg_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="4f517-385">The regular expression  `Regex_luxemburg_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-386">From `Keywords_luxemburg_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-386">A keyword from  `Keywords_luxemburg_eu_national_id_card` is found.</span></span> 
    
```
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_national_id_card" />
          <Match idRef="Keywords_luxemburg_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4f517-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-387">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_national_id_card"></a><span data-ttu-id="4f517-388">Keywords_luxemburg_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-388">Keywords_luxemburg_eu_national_id_card</span></span>

<span data-ttu-id="4f517-389">個人 id</span><span class="sxs-lookup"><span data-stu-id="4f517-389">personal id</span></span>
  
<span data-ttu-id="4f517-390">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-390">personal id number</span></span>
  
<span data-ttu-id="4f517-391">パーソナル id no#</span><span class="sxs-lookup"><span data-stu-id="4f517-391">personalidno#</span></span>
  
<span data-ttu-id="4f517-392">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-392">unique id number</span></span>
  
<span data-ttu-id="4f517-393">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-393">personalidnumber#</span></span>
  
<span data-ttu-id="4f517-394">一意の id キー</span><span class="sxs-lookup"><span data-stu-id="4f517-394">unique id key</span></span>
  
<span data-ttu-id="4f517-395">個人 id コード</span><span class="sxs-lookup"><span data-stu-id="4f517-395">personal id code</span></span>
  
<span data-ttu-id="4f517-396">uniqueidkey#</span><span class="sxs-lookup"><span data-stu-id="4f517-396">uniqueidkey#</span></span>
  
<span data-ttu-id="4f517-397">個別のコード</span><span class="sxs-lookup"><span data-stu-id="4f517-397">individual code</span></span>
  
<span data-ttu-id="4f517-398">個別の id</span><span class="sxs-lookup"><span data-stu-id="4f517-398">individual id</span></span>
  
<span data-ttu-id="4f517-399">eindeutige id-nummer</span><span class="sxs-lookup"><span data-stu-id="4f517-399">eindeutige id-nummer</span></span>
  
<span data-ttu-id="4f517-400">eindeutige id</span><span class="sxs-lookup"><span data-stu-id="4f517-400">eindeutige id</span></span>
  
<span data-ttu-id="4f517-401">id personnelle</span><span class="sxs-lookup"><span data-stu-id="4f517-401">id personnelle</span></span>
  
<span data-ttu-id="4f517-402">numéro d'identification 職員</span><span class="sxs-lookup"><span data-stu-id="4f517-402">numéro d'identification personnel</span></span>
  
<span data-ttu-id="4f517-403">idpersonnelle#</span><span class="sxs-lookup"><span data-stu-id="4f517-403">idpersonnelle#</span></span>
  
<span data-ttu-id="4f517-404">persönliche identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="4f517-404">persönliche identifikationsnummer</span></span>
  
<span data-ttu-id="4f517-405">eindeutigeid#</span><span class="sxs-lookup"><span data-stu-id="4f517-405">eindeutigeid#</span></span>
  
## <a name="malta"></a><span data-ttu-id="4f517-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="4f517-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="4f517-407">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-407">Format</span></span>

<span data-ttu-id="4f517-408">7桁の数字の後に1文字</span><span class="sxs-lookup"><span data-stu-id="4f517-408">Seven digits followed by one letter</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-409">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-409">Pattern</span></span>

<span data-ttu-id="4f517-410">7桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="4f517-410">Seven digits followed by one letter:</span></span>
  
-  <span data-ttu-id="4f517-411">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="4f517-411">Seven digits</span></span> 
    
- <span data-ttu-id="4f517-412">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="4f517-412">One uppercase letter (case sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-413">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-413">Checksum</span></span>

<span data-ttu-id="4f517-414">該当なし</span><span class="sxs-lookup"><span data-stu-id="4f517-414">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-415">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-415">Definition</span></span>

<span data-ttu-id="4f517-416">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-416">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-417">正規表現`Regex_malta_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="4f517-417">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-418">From `Keywords_malta_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-418">A keyword from  `Keywords_malta_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-419">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-419">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-420">正規表現`Regex_malta_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="4f517-420">The regular expression  `Regex_malta_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-421">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-421">Keywords</span></span>

#### <a name="keywords_malta_eu_national_id_card"></a><span data-ttu-id="4f517-422">Keywords_malta_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-422">Keywords_malta_eu_national_id_card</span></span>

<span data-ttu-id="4f517-423">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="4f517-423">personal numeric code</span></span>
  
<span data-ttu-id="4f517-424">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-424">unique identification number</span></span>
  
<span data-ttu-id="4f517-425">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="4f517-425">citizen service number</span></span>
  
<span data-ttu-id="4f517-426">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-426">unique identity number</span></span>
  
<span data-ttu-id="4f517-427">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="4f517-427">uniqueidentityno#</span></span>
  
<span data-ttu-id="4f517-428">kodiċi numerali パーソナル i</span><span class="sxs-lookup"><span data-stu-id="4f517-428">kodiċi numerali personali</span></span>
  
<span data-ttu-id="4f517-429">numru ta ' identifikazzjoni uniku</span><span class="sxs-lookup"><span data-stu-id="4f517-429">numru ta 'identifikazzjoni uniku</span></span>
  
<span data-ttu-id="4f517-430">numru tas-servizz taċ-ċittadin</span><span class="sxs-lookup"><span data-stu-id="4f517-430">numru tas-servizz taċ-ċittadin</span></span>
  
<span data-ttu-id="4f517-431">numru ta ' 識別子 tuniku</span><span class="sxs-lookup"><span data-stu-id="4f517-431">numru ta' identità uniku</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="4f517-432">オランダ</span><span class="sxs-lookup"><span data-stu-id="4f517-432">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="4f517-433">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-433">Format</span></span>

<span data-ttu-id="4f517-434">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-434">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-435">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-435">Pattern</span></span>

<span data-ttu-id="4f517-436">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-436">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4f517-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-437">Checksum</span></span>

<span data-ttu-id="4f517-438">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-438">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-439">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-439">Definition</span></span>

<span data-ttu-id="4f517-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-440">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-441">関数`Func_netherlands_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-441">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-442">From キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-442">A keyword from is found.</span></span>
    
<span data-ttu-id="4f517-443">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-443">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-444">関数`Func_netherlands_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-444">The function  `Func_netherlands_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-445">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-445">Keywords</span></span>

#### <a name="keywords_netherlands_eu_national_id_card"></a><span data-ttu-id="4f517-446">Keywords_netherlands_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-446">Keywords_netherlands_eu_national_id_card</span></span>

<span data-ttu-id="4f517-447">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="4f517-447">personal numeric code</span></span>
  
<span data-ttu-id="4f517-448">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-448">unique identification number</span></span>
  
<span data-ttu-id="4f517-449">市民サービス番号</span><span class="sxs-lookup"><span data-stu-id="4f517-449">citizen service number</span></span>
  
<span data-ttu-id="4f517-450">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-450">unique identity number</span></span>
  
<span data-ttu-id="4f517-451">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="4f517-451">uniqueidentityno#</span></span>
  
<span data-ttu-id="4f517-452">bsn</span><span class="sxs-lookup"><span data-stu-id="4f517-452">bsn</span></span>
  
<span data-ttu-id="4f517-453">bsn#</span><span class="sxs-lookup"><span data-stu-id="4f517-453">bsn#</span></span>
  
<span data-ttu-id="4f517-454">persoonlijke numerieke コード</span><span class="sxs-lookup"><span data-stu-id="4f517-454">persoonlijke numerieke code</span></span>
  
<span data-ttu-id="4f517-455">uniek identificatienummer</span><span class="sxs-lookup"><span data-stu-id="4f517-455">uniek identificatienummer</span></span>
  
<span data-ttu-id="4f517-456">burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="4f517-456">burgerservicenummer</span></span>
  
<span data-ttu-id="4f517-457">uniek identiteitsnummer</span><span class="sxs-lookup"><span data-stu-id="4f517-457">uniek identiteitsnummer</span></span>
  
## <a name="poland"></a><span data-ttu-id="4f517-458">ポーランド</span><span class="sxs-lookup"><span data-stu-id="4f517-458">Poland</span></span>

<span data-ttu-id="4f517-459">詳細については、「[機密情報の種類](what-the-sensitive-information-types-look-for.md)について」の「ポーランド国立 ID (pesel)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-459">For details, see the section "Poland National ID (PESEL)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="4f517-460">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="4f517-460">Portugal</span></span>

<span data-ttu-id="4f517-461">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-461">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="romania"></a><span data-ttu-id="4f517-462">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="4f517-462">Romania</span></span>

### <a name="format"></a><span data-ttu-id="4f517-463">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-463">Format</span></span>

<span data-ttu-id="4f517-464">13桁の数字 (スペースと区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="4f517-464">13 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-465">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-465">Pattern</span></span>

<span data-ttu-id="4f517-466">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-466">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4f517-467">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-467">Checksum</span></span>

<span data-ttu-id="4f517-468">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-468">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-469">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-469">Definition</span></span>

<span data-ttu-id="4f517-470">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-471">関数`Func_romania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-471">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-472">From `Keywords_romania_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-472">A keyword from  `Keywords_romania_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-473">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-474">関数`Func_romania_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-474">The function  `Func_romania_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-475">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-475">Keywords</span></span>

#### <a name="keywords_romania_eu_national_id_card"></a><span data-ttu-id="4f517-476">Keywords_romania_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-476">Keywords_romania_eu_national_id_card</span></span>

<span data-ttu-id="4f517-477">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="4f517-477">personal numeric code</span></span>
  
<span data-ttu-id="4f517-478">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-478">unique identification number</span></span>
  
<span data-ttu-id="4f517-479">cnp</span><span class="sxs-lookup"><span data-stu-id="4f517-479">cnp</span></span>
  
<span data-ttu-id="4f517-480">cnp#</span><span class="sxs-lookup"><span data-stu-id="4f517-480">cnp#</span></span>
  
<span data-ttu-id="4f517-481">pin</span><span class="sxs-lookup"><span data-stu-id="4f517-481">pin</span></span>
  
<span data-ttu-id="4f517-482">pin#</span><span class="sxs-lookup"><span data-stu-id="4f517-482">pin#</span></span>
  
<span data-ttu-id="4f517-483">保険番号</span><span class="sxs-lookup"><span data-stu-id="4f517-483">insurance number</span></span>
  
<span data-ttu-id="4f517-484">insurancenumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-484">insurancenumber#</span></span>
  
<span data-ttu-id="4f517-485">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-485">unique identity number</span></span>
  
<span data-ttu-id="4f517-486">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="4f517-486">uniqueidentityno#</span></span>
  
<span data-ttu-id="4f517-487">cod 数値個人</span><span class="sxs-lookup"><span data-stu-id="4f517-487">cod numeric personal</span></span>
  
<span data-ttu-id="4f517-488">cod 識別子 (個人)</span><span class="sxs-lookup"><span data-stu-id="4f517-488">cod identificare personal</span></span>
  
<span data-ttu-id="4f517-489">cod の識別子は</span><span class="sxs-lookup"><span data-stu-id="4f517-489">cod unic identificare</span></span>
  
<span data-ttu-id="4f517-490">număr 個人用非 ic</span><span class="sxs-lookup"><span data-stu-id="4f517-490">număr personal unic</span></span>
  
<span data-ttu-id="4f517-491">număr 識別子縦</span><span class="sxs-lookup"><span data-stu-id="4f517-491">număr identitate</span></span>
  
<span data-ttu-id="4f517-492">număr 識別子の個人情報</span><span class="sxs-lookup"><span data-stu-id="4f517-492">număr identificare personal</span></span>
  
<span data-ttu-id="4f517-493">număridentitate#</span><span class="sxs-lookup"><span data-stu-id="4f517-493">număridentitate#</span></span>
  
<span data-ttu-id="4f517-494">codnumericpersonal#</span><span class="sxs-lookup"><span data-stu-id="4f517-494">codnumericpersonal#</span></span>
  
<span data-ttu-id="4f517-495">numărpersonalunic#</span><span class="sxs-lookup"><span data-stu-id="4f517-495">numărpersonalunic#</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="4f517-496">スロバキア</span><span class="sxs-lookup"><span data-stu-id="4f517-496">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="4f517-497">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-497">Format</span></span>

<span data-ttu-id="4f517-498">1つの円記号を含む10桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-498">Ten digits containing one backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-499">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-499">Pattern</span></span>

<span data-ttu-id="4f517-500">1つの円記号を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="4f517-500">Ten digits containing one backslash:</span></span>
  
### <a name="checksum"></a><span data-ttu-id="4f517-501">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-501">Checksum</span></span>

<span data-ttu-id="4f517-502">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-502">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-503">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-503">Definition</span></span>

<span data-ttu-id="4f517-504">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-504">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-505">関数`Func_slovakia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-505">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-506">From `Keywords_slovakia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-506">A keyword from  `Keywords_slovakia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-507">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-508">関数`Func_slovakia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-508">The function  `Func_slovakia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-509">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-509">Keywords</span></span>

#### <a name="keywords_slovakia_eu_national_id_card"></a><span data-ttu-id="4f517-510">Keywords_slovakia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-510">Keywords_slovakia_eu_national_id_card</span></span>

<span data-ttu-id="4f517-511">出生地番号</span><span class="sxs-lookup"><span data-stu-id="4f517-511">birth number</span></span>
  
<span data-ttu-id="4f517-512">national identification number</span><span class="sxs-lookup"><span data-stu-id="4f517-512">national identification number</span></span>
  
<span data-ttu-id="4f517-513">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-513">personal identification number</span></span>
  
<span data-ttu-id="4f517-514">social security number</span><span class="sxs-lookup"><span data-stu-id="4f517-514">social security number</span></span>
  
<span data-ttu-id="4f517-515">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-515">nationalnumber#</span></span>
  
<span data-ttu-id="4f517-516">ssn#</span><span class="sxs-lookup"><span data-stu-id="4f517-516">ssn#</span></span>
  
<span data-ttu-id="4f517-517">ssn</span><span class="sxs-lookup"><span data-stu-id="4f517-517">ssn</span></span>
  
<span data-ttu-id="4f517-518">国番号</span><span class="sxs-lookup"><span data-stu-id="4f517-518">national number</span></span>
  
<span data-ttu-id="4f517-519">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-519">personal id number</span></span>
  
<span data-ttu-id="4f517-520">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="4f517-520">personalidnumber#</span></span>
  
<span data-ttu-id="4f517-521">rč</span><span class="sxs-lookup"><span data-stu-id="4f517-521">rč</span></span>
  
<span data-ttu-id="4f517-522">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="4f517-522">rodné číslo</span></span>
  
<span data-ttu-id="4f517-523">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="4f517-523">rodne cislo</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="4f517-524">スロベニア</span><span class="sxs-lookup"><span data-stu-id="4f517-524">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="4f517-525">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-525">Format</span></span>

<span data-ttu-id="4f517-526">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="4f517-526">13 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-527">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-527">Pattern</span></span>

<span data-ttu-id="4f517-528">指定したパターンの13桁の数字:</span><span class="sxs-lookup"><span data-stu-id="4f517-528">13 digits in the specified pattern:</span></span>
  
-  <span data-ttu-id="4f517-529">誕生日 (DDMMLLL) に対応する7桁の数字で、"LLL" は誕生年の最後の3桁に対応します。</span><span class="sxs-lookup"><span data-stu-id="4f517-529">Seven digits that correspond to the birth date (DDMMLLL) where "LLL" corresponds to the last three digits of the birth year</span></span> 
    
- <span data-ttu-id="4f517-530">誕生日の範囲に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-530">Two digits that correspond to the area of birth</span></span>
    
- <span data-ttu-id="4f517-531">同じ日に生まれた人物の性別とシリアル番号の組み合わせに対応する3つの数字 (女性の場合は男性と500-999 は 000-499)</span><span class="sxs-lookup"><span data-stu-id="4f517-531">Three digits that correspond to a combination of gender and serial number for persons born on the same day (000-499 for male and 500-999 for female)</span></span>
    
- <span data-ttu-id="4f517-532">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="4f517-532">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-533">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-533">Checksum</span></span>

<span data-ttu-id="4f517-534">はい</span><span class="sxs-lookup"><span data-stu-id="4f517-534">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-535">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-535">Definition</span></span>

<span data-ttu-id="4f517-536">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-536">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-537">関数`Func_slovenia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-537">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-538">From `Keywords_slovenia_eu_national_id_card`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-538">A keyword from  `Keywords_slovenia_eu_national_id_card` is found.</span></span> 
    
<span data-ttu-id="4f517-539">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-539">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-540">関数`Func_slovenia_eu_national_id_card`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="4f517-540">The function  `Func_slovenia_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="4f517-541">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-541">Keywords</span></span>

#### <a name="keywords_slovenia_eu_national_id_card"></a><span data-ttu-id="4f517-542">Keywords_slovenia_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-542">Keywords_slovenia_eu_national_id_card</span></span>

<span data-ttu-id="4f517-543">個人の数値コード</span><span class="sxs-lookup"><span data-stu-id="4f517-543">personal numeric code</span></span>
  
<span data-ttu-id="4f517-544">一意の識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-544">unique identification number</span></span>
  
<span data-ttu-id="4f517-545">一意の登録番号</span><span class="sxs-lookup"><span data-stu-id="4f517-545">unique registration number</span></span>
  
<span data-ttu-id="4f517-546">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-546">unique identity number</span></span>
  
<span data-ttu-id="4f517-547">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="4f517-547">uniqueidentityno#</span></span>
  
<span data-ttu-id="4f517-548">一意のマスター市民番号</span><span class="sxs-lookup"><span data-stu-id="4f517-548">unique master citizen number</span></span>
  
<span data-ttu-id="4f517-549">edinstベンダー a identifikacijska številka</span><span class="sxs-lookup"><span data-stu-id="4f517-549">edinstvena identifikacijska številka</span></span>
  
<span data-ttu-id="4f517-550">uniqueidentityno#</span><span class="sxs-lookup"><span data-stu-id="4f517-550">uniqueidentityno #</span></span>
  
<span data-ttu-id="4f517-551">edinstベンダー a številka glavnega državljana</span><span class="sxs-lookup"><span data-stu-id="4f517-551">edinstvena številka glavnega državljana</span></span>
  
<span data-ttu-id="4f517-552">emšo</span><span class="sxs-lookup"><span data-stu-id="4f517-552">emšo</span></span>
  
## <a name="spain"></a><span data-ttu-id="4f517-553">スペイン</span><span class="sxs-lookup"><span data-stu-id="4f517-553">Spain</span></span>

### <a name="format"></a><span data-ttu-id="4f517-554">Format</span><span class="sxs-lookup"><span data-stu-id="4f517-554">Format</span></span>

<span data-ttu-id="4f517-555">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="4f517-555">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="4f517-556">パターン</span><span class="sxs-lookup"><span data-stu-id="4f517-556">Pattern</span></span>

<span data-ttu-id="4f517-557">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="4f517-557">Eight digits followed by one character</span></span>
  
- <span data-ttu-id="4f517-558">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="4f517-558">Eight digits</span></span>
    
- <span data-ttu-id="4f517-559">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="4f517-559">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="4f517-560">チェックサム</span><span class="sxs-lookup"><span data-stu-id="4f517-560">Checksum</span></span>

<span data-ttu-id="4f517-561">該当なし</span><span class="sxs-lookup"><span data-stu-id="4f517-561">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="4f517-562">定義</span><span class="sxs-lookup"><span data-stu-id="4f517-562">Definition</span></span>

<span data-ttu-id="4f517-563">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="4f517-563">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="4f517-564">正規表現`Regex_spain_eu_national_id_card`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="4f517-564">The regular expression  `Regex_spain_eu_national_id_card` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="4f517-565">From `Keywords_spain_eu_national_id_card"`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="4f517-565">A keyword from  `Keywords_spain_eu_national_id_card"` is found.</span></span> 
    
```
 
<Entity id="419f449f-6d9d-4be1-a154-b531f7a91b41" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_national_id_card" />
          <Match idRef="Keywords_spain_eu_national_id_card" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4f517-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="4f517-566">Keywords</span></span>

#### <a name="keywords_spain_eu_national_id_card"></a><span data-ttu-id="4f517-567">Keywords_spain_eu_national_id_card</span><span class="sxs-lookup"><span data-stu-id="4f517-567">Keywords_spain_eu_national_id_card</span></span>

<span data-ttu-id="4f517-568">dni</span><span class="sxs-lookup"><span data-stu-id="4f517-568">dni</span></span>
  
<span data-ttu-id="4f517-569">national identification number</span><span class="sxs-lookup"><span data-stu-id="4f517-569">national identification number</span></span>
  
<span data-ttu-id="4f517-570">国内の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-570">national identity number</span></span>
  
<span data-ttu-id="4f517-571">保険番号</span><span class="sxs-lookup"><span data-stu-id="4f517-571">insurance number</span></span>
  
<span data-ttu-id="4f517-572">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="4f517-572">personal identification number</span></span>
  
<span data-ttu-id="4f517-573">国民 id</span><span class="sxs-lookup"><span data-stu-id="4f517-573">national identity</span></span>
  
<span data-ttu-id="4f517-574">個人 id いいえ</span><span class="sxs-lookup"><span data-stu-id="4f517-574">personal identity no</span></span>
  
<span data-ttu-id="4f517-575">一意の id 番号</span><span class="sxs-lookup"><span data-stu-id="4f517-575">unique identity number</span></span>
  
<span data-ttu-id="4f517-576">nationalidno#</span><span class="sxs-lookup"><span data-stu-id="4f517-576">nationalidno#</span></span>
  
<span data-ttu-id="4f517-577">見つから#</span><span class="sxs-lookup"><span data-stu-id="4f517-577">uniqueid#</span></span>
  
<span data-ttu-id="4f517-578">dni#</span><span class="sxs-lookup"><span data-stu-id="4f517-578">dni#</span></span>
  
<span data-ttu-id="4f517-579">nationalid#</span><span class="sxs-lookup"><span data-stu-id="4f517-579">nationalid#</span></span>
  
<span data-ttu-id="4f517-580">nie#</span><span class="sxs-lookup"><span data-stu-id="4f517-580">nie#</span></span>
  
<span data-ttu-id="4f517-581">nie</span><span class="sxs-lookup"><span data-stu-id="4f517-581">nie</span></span>
  
<span data-ttu-id="4f517-582">nienúmero#</span><span class="sxs-lookup"><span data-stu-id="4f517-582">nienúmero#</span></span>
  
<span data-ttu-id="4f517-583">nie número</span><span class="sxs-lookup"><span data-stu-id="4f517-583">nie número</span></span>
  
<span data-ttu-id="4f517-584">documento nacional de 識別子 dad</span><span class="sxs-lookup"><span data-stu-id="4f517-584">documento nacional de identidad</span></span>
  
<span data-ttu-id="4f517-585">dad único の識別子</span><span class="sxs-lookup"><span data-stu-id="4f517-585">identidad único</span></span>
  
<span data-ttu-id="4f517-586">número nacional 識別子 dad</span><span class="sxs-lookup"><span data-stu-id="4f517-586">número nacional identidad</span></span>
  
<span data-ttu-id="4f517-587">dni número</span><span class="sxs-lookup"><span data-stu-id="4f517-587">dni número</span></span>
  
<span data-ttu-id="4f517-588">dninúmero#</span><span class="sxs-lookup"><span data-stu-id="4f517-588">dninúmero#</span></span>
  
<span data-ttu-id="4f517-589">identidadúnico#</span><span class="sxs-lookup"><span data-stu-id="4f517-589">identidadúnico#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="4f517-590">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="4f517-590">Sweden</span></span>

<span data-ttu-id="4f517-591">詳細については、「スウェーデン国立 ID」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f517-591">For details, see the section "Sweden National ID" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4f517-592">関連項目</span><span class="sxs-lookup"><span data-stu-id="4f517-592">See also</span></span>

[<span data-ttu-id="4f517-593">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="4f517-593">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

