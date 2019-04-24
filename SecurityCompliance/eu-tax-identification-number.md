---
title: EU 税務識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 4914ff078695519c2a298190d82c86a6abebceb9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255525"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="a7123-104">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-104">EU Tax Identification Number</span></span>

<span data-ttu-id="a7123-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="a7123-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="a7123-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="a7123-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="a7123-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="a7123-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="a7123-108">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-108">Format</span></span>

<span data-ttu-id="a7123-109">任意指定のハイフンとスラッシュ (/) を含む9桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-110">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-110">Pattern</span></span>

<span data-ttu-id="a7123-111">任意指定のハイフンとスラッシュ (/) を含む9桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="a7123-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-112">Two digits</span></span> 
    
- <span data-ttu-id="a7123-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a7123-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="a7123-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-114">Three digits</span></span>
    
- <span data-ttu-id="a7123-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a7123-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="a7123-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-117">Checksum</span></span>

<span data-ttu-id="a7123-118">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-119">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-119">Definition</span></span>

<span data-ttu-id="a7123-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-121">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-122">from `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-124">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-125">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="a7123-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-127">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-127">tax number</span></span>
  
<span data-ttu-id="a7123-128">number</span><span class="sxs-lookup"><span data-stu-id="a7123-128">number</span></span>
  
<span data-ttu-id="a7123-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="a7123-129">tax registration number</span></span>
  
<span data-ttu-id="a7123-130">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-130">tax id</span></span>
  
<span data-ttu-id="a7123-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="a7123-131">st.nr.</span></span>
  
<span data-ttu-id="a7123-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="a7123-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="a7123-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="a7123-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="a7123-134">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-134">Format</span></span>

<span data-ttu-id="a7123-135">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-136">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-136">Pattern</span></span>

<span data-ttu-id="a7123-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-137">11 digits:</span></span>
  
- <span data-ttu-id="a7123-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-138">Two digits</span></span>
    
- <span data-ttu-id="a7123-139">"0" または "1"</span><span class="sxs-lookup"><span data-stu-id="a7123-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="a7123-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-140">One digit</span></span>
    
- <span data-ttu-id="a7123-141">"0" または "1" または "2" または "3"</span><span class="sxs-lookup"><span data-stu-id="a7123-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="a7123-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-143">Checksum</span></span>

<span data-ttu-id="a7123-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-145">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-145">Definition</span></span>

<span data-ttu-id="a7123-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-147">正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a7123-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-148">from `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="a7123-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-151">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-151">tax number</span></span>
  
<span data-ttu-id="a7123-152">国内登録番号</span><span class="sxs-lookup"><span data-stu-id="a7123-152">national registration number</span></span>
  
<span data-ttu-id="a7123-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="a7123-153">tax registration number</span></span>
  
<span data-ttu-id="a7123-154">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-154">tax id</span></span>
  
<span data-ttu-id="a7123-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="a7123-155">nif</span></span>
  
<span data-ttu-id="a7123-156">\n\n</span><span class="sxs-lookup"><span data-stu-id="a7123-156">nif#</span></span>
  
<span data-ttu-id="a7123-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="a7123-157">numéro de registre national</span></span>
  
<span data-ttu-id="a7123-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="a7123-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="a7123-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="a7123-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="a7123-160">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-160">Format</span></span>

<span data-ttu-id="a7123-161">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-162">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-162">Pattern</span></span>

<span data-ttu-id="a7123-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-164">Checksum</span></span>

<span data-ttu-id="a7123-165">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-166">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-166">Definition</span></span>

<span data-ttu-id="a7123-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-168">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-169">from `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-171">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-172">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="a7123-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-174">bucn</span><span class="sxs-lookup"><span data-stu-id="a7123-174">bucn</span></span>
  
<span data-ttu-id="a7123-175">一律の民事番号</span><span class="sxs-lookup"><span data-stu-id="a7123-175">uniform civil number</span></span>
  
<span data-ttu-id="a7123-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="a7123-176">bucn#</span></span>
  
<span data-ttu-id="a7123-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="a7123-178">uniform 民事 id</span><span class="sxs-lookup"><span data-stu-id="a7123-178">uniform civil id</span></span>
  
<span data-ttu-id="a7123-179">uniform 民事 no</span><span class="sxs-lookup"><span data-stu-id="a7123-179">uniform civil no</span></span>
  
<span data-ttu-id="a7123-180">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="a7123-180">egn</span></span>
  
<span data-ttu-id="a7123-181">ブルガリアの一様な民事訴訟番号</span><span class="sxs-lookup"><span data-stu-id="a7123-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="a7123-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="a7123-182">uniformcivilno#</span></span>
  
<span data-ttu-id="a7123-183">"/入力 id"</span><span class="sxs-lookup"><span data-stu-id="a7123-183">egn#</span></span>
  
<span data-ttu-id="a7123-184">униформгражданскиномер</span><span class="sxs-lookup"><span data-stu-id="a7123-184">униформ граждански номер</span></span>
  
<span data-ttu-id="a7123-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="a7123-185">униформ id</span></span>
  
<span data-ttu-id="a7123-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="a7123-186">униформ граждански id</span></span>
  
<span data-ttu-id="a7123-187">униформгражданскине</span><span class="sxs-lookup"><span data-stu-id="a7123-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="a7123-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="a7123-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="a7123-189">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-189">Format</span></span>

<span data-ttu-id="a7123-190">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-191">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-191">Pattern</span></span>

<span data-ttu-id="a7123-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-192">11 digits:</span></span>
  
- <span data-ttu-id="a7123-193">ランダムに選択された10桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="a7123-194">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-195">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-195">Checksum</span></span>

<span data-ttu-id="a7123-196">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-197">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-197">Definition</span></span>

<span data-ttu-id="a7123-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-199">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-200">from `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-202">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-203">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="a7123-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-205">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-205">tax number</span></span>
  
<span data-ttu-id="a7123-206">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-206">tax</span></span>
  
<span data-ttu-id="a7123-207">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-207">tax id</span></span>
  
<span data-ttu-id="a7123-208">oid</span><span class="sxs-lookup"><span data-stu-id="a7123-208">oid</span></span>
  
<span data-ttu-id="a7123-209">ドーナツ</span><span class="sxs-lookup"><span data-stu-id="a7123-209">oid#</span></span>
  
<span data-ttu-id="a7123-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="a7123-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="a7123-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="a7123-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="a7123-212">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-212">Format</span></span>

<span data-ttu-id="a7123-213">指定したパターンの8桁の数字と1文字</span><span class="sxs-lookup"><span data-stu-id="a7123-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-214">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-214">Pattern</span></span>

<span data-ttu-id="a7123-215">8桁の数字と1つの文字:</span><span class="sxs-lookup"><span data-stu-id="a7123-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="a7123-216">"0"</span><span class="sxs-lookup"><span data-stu-id="a7123-216">A "0"</span></span> 
    
- <span data-ttu-id="a7123-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-217">Seven digits</span></span>
    
- <span data-ttu-id="a7123-218">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a7123-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-219">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-219">Checksum</span></span>

<span data-ttu-id="a7123-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-221">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-221">Definition</span></span>

<span data-ttu-id="a7123-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-223">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-224">from `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-226">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="a7123-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-229">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-229">tax number</span></span>
  
<span data-ttu-id="a7123-230">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-230">tax</span></span>
  
<span data-ttu-id="a7123-231">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-231">tax id</span></span>
  
<span data-ttu-id="a7123-232">税 id コード</span><span class="sxs-lookup"><span data-stu-id="a7123-232">tax identification code</span></span>
  
<span data-ttu-id="a7123-233">認め</span><span class="sxs-lookup"><span data-stu-id="a7123-233">tic</span></span>
  
<span data-ttu-id="a7123-234">認め</span><span class="sxs-lookup"><span data-stu-id="a7123-234">tic#</span></span>
  
<span data-ttu-id="a7123-235">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="a7123-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="a7123-236">φορολογικήταυτότητα</span><span class="sxs-lookup"><span data-stu-id="a7123-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="a7123-237">κωδικόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="a7123-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="a7123-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="a7123-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="a7123-239">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-239">Format</span></span>

<span data-ttu-id="a7123-240">9桁または10桁の数字 (省略可能な円記号付き)</span><span class="sxs-lookup"><span data-stu-id="a7123-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-241">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-241">Pattern</span></span>

<span data-ttu-id="a7123-242">9桁または10桁の数字で、省略可能な backslashl を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="a7123-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-243">Six digits</span></span> 
    
- <span data-ttu-id="a7123-244">円記号 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="a7123-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="a7123-245">3桁または4桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-246">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-246">Checksum</span></span>

<span data-ttu-id="a7123-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-248">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-248">Definition</span></span>

<span data-ttu-id="a7123-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-250">正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a7123-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-251">from `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-252">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="a7123-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-254">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-254">tax number</span></span>
  
<span data-ttu-id="a7123-255">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-255">tax</span></span>
  
<span data-ttu-id="a7123-256">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-256">tax id</span></span>
  
<span data-ttu-id="a7123-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="a7123-257">personal number</span></span>
  
<span data-ttu-id="a7123-258">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="a7123-258">daňové číslo</span></span>
  
<span data-ttu-id="a7123-259">osobníčíslo</span><span class="sxs-lookup"><span data-stu-id="a7123-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="a7123-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="a7123-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="a7123-261">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-261">Format</span></span>

<span data-ttu-id="a7123-262">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="a7123-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-263">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-263">Pattern</span></span>

<span data-ttu-id="a7123-264">hyphenl を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="a7123-265">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="a7123-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="a7123-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="a7123-266">A hyphen</span></span>
    
- <span data-ttu-id="a7123-267">1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="a7123-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-268">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-268">Checksum</span></span>

<span data-ttu-id="a7123-269">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-270">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-270">Definition</span></span>

<span data-ttu-id="a7123-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-272">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-273">from `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-275">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-276">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="a7123-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-278">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-278">tax number</span></span>
  
<span data-ttu-id="a7123-279">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-279">tax</span></span>
  
<span data-ttu-id="a7123-280">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-280">tax id</span></span>
  
<span data-ttu-id="a7123-281">cpr 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-281">cpr number</span></span>
  
<span data-ttu-id="a7123-282">cpr</span><span class="sxs-lookup"><span data-stu-id="a7123-282">cpr#</span></span>
  
<span data-ttu-id="a7123-283">nummer の sk</span><span class="sxs-lookup"><span data-stu-id="a7123-283">skat nummer</span></span>
  
<span data-ttu-id="a7123-284">id の sk</span><span class="sxs-lookup"><span data-stu-id="a7123-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="a7123-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="a7123-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="a7123-286">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-286">Format</span></span>

<span data-ttu-id="a7123-287">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-288">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-288">Pattern</span></span>

<span data-ttu-id="a7123-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-289">11 digits:</span></span>
  
-  <span data-ttu-id="a7123-290">性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。</span><span class="sxs-lookup"><span data-stu-id="a7123-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="a7123-291">誕生日に対応する6桁の数字 (yymmdd という)</span><span class="sxs-lookup"><span data-stu-id="a7123-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="a7123-292">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="a7123-293">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-294">Checksum</span></span>

<span data-ttu-id="a7123-295">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-296">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-296">Definition</span></span>

<span data-ttu-id="a7123-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-298">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-299">from `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-301">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-302">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="a7123-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-304">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-304">tax number</span></span>
  
<span data-ttu-id="a7123-305">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-305">tax</span></span>
  
<span data-ttu-id="a7123-306">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-306">tax id</span></span>
  
<span data-ttu-id="a7123-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="a7123-307">personal code</span></span>
  
<span data-ttu-id="a7123-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="a7123-308">maksunumber</span></span>
  
<span data-ttu-id="a7123-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="a7123-309">maksu id</span></span>
  
<span data-ttu-id="a7123-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="a7123-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="a7123-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="a7123-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="a7123-312">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-312">Format</span></span>

<span data-ttu-id="a7123-313">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="a7123-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-314">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-314">Pattern</span></span>

<span data-ttu-id="a7123-315">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="a7123-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="a7123-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-316">Six digits</span></span>
    
- <span data-ttu-id="a7123-317">プラス記号、マイナス記号、または文字 "a" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味します。</span><span class="sxs-lookup"><span data-stu-id="a7123-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="a7123-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-318">Three digits</span></span>
    
- <span data-ttu-id="a7123-319">1つの文字または1つの番号</span><span class="sxs-lookup"><span data-stu-id="a7123-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-320">Checksum</span></span>

<span data-ttu-id="a7123-321">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-322">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-322">Definition</span></span>

<span data-ttu-id="a7123-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-324">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-325">from `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-327">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-328">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="a7123-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-330">identification number</span><span class="sxs-lookup"><span data-stu-id="a7123-330">identification number</span></span>
  
<span data-ttu-id="a7123-331">個人 id</span><span class="sxs-lookup"><span data-stu-id="a7123-331">personal id</span></span>
  
<span data-ttu-id="a7123-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-332">identity number</span></span>
  
<span data-ttu-id="a7123-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-333">finnish national id number</span></span>
  
<span data-ttu-id="a7123-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-334">personalidnumber#</span></span>
  
<span data-ttu-id="a7123-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="a7123-335">national identification number</span></span>
  
<span data-ttu-id="a7123-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-336">id number</span></span>
  
<span data-ttu-id="a7123-337">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-337">national id no.</span></span>
  
<span data-ttu-id="a7123-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-338">national id number</span></span>
  
<span data-ttu-id="a7123-339">id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-339">id no</span></span>
  
<span data-ttu-id="a7123-340">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="a7123-340">tunnistenumero</span></span>
  
<span data-ttu-id="a7123-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="a7123-341">henkilötunnus</span></span>
  
<span data-ttu-id="a7123-342">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="a7123-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="a7123-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="a7123-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="a7123-344">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="a7123-344">identiteetti numero</span></span>
  
<span data-ttu-id="a7123-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="a7123-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="a7123-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="a7123-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="a7123-347">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="a7123-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="a7123-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="a7123-348">tunnusnumero</span></span>
  
<span data-ttu-id="a7123-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="a7123-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="a7123-350">フランス</span><span class="sxs-lookup"><span data-stu-id="a7123-350">France</span></span>

### <a name="format"></a><span data-ttu-id="a7123-351">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-351">Format</span></span>

<span data-ttu-id="a7123-352">各ユーザーの13桁の数字、およびエンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-353">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-353">Pattern</span></span>

<span data-ttu-id="a7123-354">個人の場合は13桁。</span><span class="sxs-lookup"><span data-stu-id="a7123-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="a7123-355">0、1、2、または3である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="a7123-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-356">12 digits</span></span>
    
<span data-ttu-id="a7123-357">エンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-358">Checksum</span></span>

<span data-ttu-id="a7123-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-360">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-360">Definition</span></span>

<span data-ttu-id="a7123-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-362">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-363">from `Keywords_france_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-365">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-366">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="a7123-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-368">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-368">tax identification number</span></span>
  
<span data-ttu-id="a7123-369">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-369">tax number</span></span>
  
<span data-ttu-id="a7123-370">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-370">tax id</span></span>
  
<span data-ttu-id="a7123-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="a7123-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="a7123-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="a7123-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="a7123-373">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-373">Format</span></span>

<span data-ttu-id="a7123-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-375">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-375">Pattern</span></span>

<span data-ttu-id="a7123-376">11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-376">11 digits :</span></span>
  
-  <span data-ttu-id="a7123-377">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-377">Ten digits</span></span> 
    
- <span data-ttu-id="a7123-378">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-379">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-379">Checksum</span></span>

<span data-ttu-id="a7123-380">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-381">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-381">Definition</span></span>

<span data-ttu-id="a7123-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-383">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-384">from `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-386">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="a7123-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-389">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-389">tax number</span></span>
  
<span data-ttu-id="a7123-390">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-390">tax no.</span></span>
  
<span data-ttu-id="a7123-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-391">taxno#</span></span>
  
<span data-ttu-id="a7123-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-392">taxnumber#</span></span>
  
<span data-ttu-id="a7123-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-393">taxnumber</span></span>
  
<span data-ttu-id="a7123-394">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-394">tax id</span></span>
  
<span data-ttu-id="a7123-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-395">taxid#</span></span>
  
<span data-ttu-id="a7123-396">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-396">tax identification number</span></span>
  
<span data-ttu-id="a7123-397">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-397">tax identification no.</span></span>
  
<span data-ttu-id="a7123-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="a7123-398">steuernummer</span></span>
  
<span data-ttu-id="a7123-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="a7123-399">steuer id</span></span>
  
<span data-ttu-id="a7123-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a7123-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="a7123-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="a7123-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="a7123-402">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-402">Format</span></span>

<span data-ttu-id="a7123-403">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-404">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-404">Pattern</span></span>

<span data-ttu-id="a7123-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-406">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-406">Checksum</span></span>

<span data-ttu-id="a7123-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-408">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-408">Definition</span></span>

<span data-ttu-id="a7123-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-410">正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a7123-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-411">from `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-412">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="a7123-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-414">afm</span><span class="sxs-lookup"><span data-stu-id="a7123-414">afm</span></span>
  
<span data-ttu-id="a7123-415">は</span><span class="sxs-lookup"><span data-stu-id="a7123-415">tin</span></span>
  
<span data-ttu-id="a7123-416">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-416">tax id no.</span></span>
  
<span data-ttu-id="a7123-417">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-417">tax id no</span></span>
  
<span data-ttu-id="a7123-418">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-418">tax identification number</span></span>
  
<span data-ttu-id="a7123-419">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-419">tax registry number</span></span>
  
<span data-ttu-id="a7123-420">納税レジストリ番号</span><span class="sxs-lookup"><span data-stu-id="a7123-420">tax registry no.</span></span>
  
<span data-ttu-id="a7123-421">afm</span><span class="sxs-lookup"><span data-stu-id="a7123-421">afm#</span></span>
  
<span data-ttu-id="a7123-422">は</span><span class="sxs-lookup"><span data-stu-id="a7123-422">tin#</span></span>
  
<span data-ttu-id="a7123-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="a7123-423">taxidno#</span></span>
  
<span data-ttu-id="a7123-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="a7123-424">taxregistryno#</span></span>
  
<span data-ttu-id="a7123-425">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="a7123-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="a7123-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="a7123-426">aφμ</span></span>
  
<span data-ttu-id="a7123-427">aφμαριθμός</span><span class="sxs-lookup"><span data-stu-id="a7123-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="a7123-428">φορολογικούμητρώουνο。</span><span class="sxs-lookup"><span data-stu-id="a7123-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="a7123-429">τοναριθμόφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="a7123-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="a7123-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="a7123-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="a7123-431">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-431">Format</span></span>

<span data-ttu-id="a7123-432">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-433">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-433">Pattern</span></span>

<span data-ttu-id="a7123-434">10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-434">Ten digits:</span></span>
  
-  <span data-ttu-id="a7123-435">"8" である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="a7123-436">日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="a7123-437">同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="a7123-438">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-439">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-439">Checksum</span></span>

<span data-ttu-id="a7123-440">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-441">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-441">Definition</span></span>

<span data-ttu-id="a7123-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-443">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-444">from `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-446">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-447">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="a7123-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-449">ハンガリーの税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="a7123-450">ハンガリー tin</span><span class="sxs-lookup"><span data-stu-id="a7123-450">hungarian tin</span></span>
  
<span data-ttu-id="a7123-451">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-451">tax id number</span></span>
  
<span data-ttu-id="a7123-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-452">vat number</span></span>
  
<span data-ttu-id="a7123-453">税務当局番号</span><span class="sxs-lookup"><span data-stu-id="a7123-453">tax authority no</span></span>
  
<span data-ttu-id="a7123-454">課税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-454">tax id tax identity number</span></span>
  
<span data-ttu-id="a7123-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-455">taxidnumber#</span></span>
  
<span data-ttu-id="a7123-456">は</span><span class="sxs-lookup"><span data-stu-id="a7123-456">tin#</span></span>
  
<span data-ttu-id="a7123-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="a7123-457">hungatiantin#</span></span>
  
<span data-ttu-id="a7123-458">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-458">tax identification no</span></span>
  
<span data-ttu-id="a7123-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="a7123-459">taxidno#</span></span>
  
<span data-ttu-id="a7123-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="a7123-460">adóazonosító szám</span></span>
  
<span data-ttu-id="a7123-461">adószám</span><span class="sxs-lookup"><span data-stu-id="a7123-461">adószám</span></span>
  
<span data-ttu-id="a7123-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="a7123-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="a7123-463">アイルランド</span><span class="sxs-lookup"><span data-stu-id="a7123-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="a7123-464">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-464">Format</span></span>

<span data-ttu-id="a7123-465">7桁の数字の後にスペースまたは区切り文字を含まない文字</span><span class="sxs-lookup"><span data-stu-id="a7123-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-466">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-466">Pattern</span></span>

<span data-ttu-id="a7123-467">7桁の数字の後に、文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="a7123-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="a7123-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-468">Seven digits</span></span> 
    
- <span data-ttu-id="a7123-469">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a7123-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-470">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-470">Checksum</span></span>

<span data-ttu-id="a7123-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-472">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-472">Definition</span></span>

<span data-ttu-id="a7123-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-474">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-475">from `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-477">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="a7123-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-480">パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="a7123-480">public service no</span></span>
  
<span data-ttu-id="a7123-481">個人用パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="a7123-481">personal public service no</span></span>
  
<span data-ttu-id="a7123-482">pps no</span><span class="sxs-lookup"><span data-stu-id="a7123-482">pps no</span></span>
  
<span data-ttu-id="a7123-483">個人サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="a7123-483">personal service no</span></span>
  
<span data-ttu-id="a7123-484">pps サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="a7123-484">pps service no</span></span>
  
<span data-ttu-id="a7123-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="a7123-485">ppsno#</span></span>
  
<span data-ttu-id="a7123-486">アイルランド語 (pps)</span><span class="sxs-lookup"><span data-stu-id="a7123-486">irish pps no</span></span>
  
<span data-ttu-id="a7123-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="a7123-487">publicserviceno#</span></span>
  
<span data-ttu-id="a7123-488">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="a7123-488">personal public service number</span></span>
  
<span data-ttu-id="a7123-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="a7123-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="a7123-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="a7123-490">pps uimh</span></span>
  
<span data-ttu-id="a7123-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="a7123-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="a7123-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="a7123-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="a7123-493">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-493">Format</span></span>

<span data-ttu-id="a7123-494">指定したパターンの16桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="a7123-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-495">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-495">Pattern</span></span>

<span data-ttu-id="a7123-496">16桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="a7123-497">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="a7123-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="a7123-498">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="a7123-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="a7123-499">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="a7123-500">誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、a から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は a と10月は r)。</span><span class="sxs-lookup"><span data-stu-id="a7123-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="a7123-501">誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。</span><span class="sxs-lookup"><span data-stu-id="a7123-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="a7123-502">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。</span><span class="sxs-lookup"><span data-stu-id="a7123-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="a7123-503">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-504">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-504">Checksum</span></span>

<span data-ttu-id="a7123-505">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-506">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-506">Definition</span></span>

<span data-ttu-id="a7123-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-508">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-509">from `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-511">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-512">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="a7123-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-514">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-514">tax number</span></span>
  
<span data-ttu-id="a7123-515">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-515">tax no.</span></span>
  
<span data-ttu-id="a7123-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-516">taxno#</span></span>
  
<span data-ttu-id="a7123-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-517">taxnumber#</span></span>
  
<span data-ttu-id="a7123-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-518">taxnumber</span></span>
  
<span data-ttu-id="a7123-519">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-519">tax id</span></span>
  
<span data-ttu-id="a7123-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-520">taxid#</span></span>
  
<span data-ttu-id="a7123-521">会計コード</span><span class="sxs-lookup"><span data-stu-id="a7123-521">fiscal code</span></span>
  
<span data-ttu-id="a7123-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="a7123-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="a7123-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="a7123-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="a7123-524">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-524">Format</span></span>

<span data-ttu-id="a7123-525">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-526">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-526">Pattern</span></span>

<span data-ttu-id="a7123-527">指定したパターンの11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="a7123-528">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="a7123-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="a7123-529">"0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。</span><span class="sxs-lookup"><span data-stu-id="a7123-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="a7123-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-531">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-531">Checksum</span></span>

<span data-ttu-id="a7123-532">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-533">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-533">Definition</span></span>

<span data-ttu-id="a7123-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-535">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-536">from `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-538">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-539">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="a7123-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-541">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-541">tax number</span></span>
  
<span data-ttu-id="a7123-542">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-542">tax no.</span></span>
  
<span data-ttu-id="a7123-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-543">taxno#</span></span>
  
<span data-ttu-id="a7123-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-544">taxnumber#</span></span>
  
<span data-ttu-id="a7123-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-545">taxnumber</span></span>
  
<span data-ttu-id="a7123-546">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-546">tax id</span></span>
  
<span data-ttu-id="a7123-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-547">taxid#</span></span>
  
<span data-ttu-id="a7123-548">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-548">tax identification number</span></span>
  
<span data-ttu-id="a7123-549">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-549">tax identification no.</span></span>
  
<span data-ttu-id="a7123-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="a7123-550">nodokļa numurs</span></span>
  
<span data-ttu-id="a7123-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="a7123-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="a7123-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="a7123-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="a7123-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="a7123-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="a7123-554">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-554">Format</span></span>

<span data-ttu-id="a7123-555">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="a7123-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-556">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-556">Pattern</span></span>

<span data-ttu-id="a7123-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-558">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-558">Checksum</span></span>

<span data-ttu-id="a7123-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-560">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-560">Definition</span></span>

<span data-ttu-id="a7123-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-562">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-563">from `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-565">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="a7123-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-568">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-568">tax number</span></span>
  
<span data-ttu-id="a7123-569">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-569">tax no.</span></span>
  
<span data-ttu-id="a7123-570">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="a7123-570">tax no#</span></span>
  
<span data-ttu-id="a7123-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-571">taxnumber#</span></span>
  
<span data-ttu-id="a7123-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-572">taxnumber</span></span>
  
<span data-ttu-id="a7123-573">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-573">tax id</span></span>
  
<span data-ttu-id="a7123-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-574">taxid#</span></span>
  
<span data-ttu-id="a7123-575">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-575">tax identification number</span></span>
  
<span data-ttu-id="a7123-576">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-576">tax identification no.</span></span>
  
<span data-ttu-id="a7123-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="a7123-577">mokesčių id</span></span>
  
<span data-ttu-id="a7123-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="a7123-578">mokesčių numeris</span></span>
  
<span data-ttu-id="a7123-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="a7123-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="a7123-580">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="a7123-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="a7123-581">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-581">Format</span></span>

<span data-ttu-id="a7123-582">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="a7123-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-583">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-583">Pattern</span></span>

<span data-ttu-id="a7123-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-584">13 digits:</span></span>
  
-  <span data-ttu-id="a7123-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-585">11 digits</span></span> 
    
- <span data-ttu-id="a7123-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-587">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-587">Checksum</span></span>

<span data-ttu-id="a7123-588">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-589">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-589">Definition</span></span>

<span data-ttu-id="a7123-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-591">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-592">from `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-594">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-595">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="a7123-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-597">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-597">tax number</span></span>
  
<span data-ttu-id="a7123-598">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-598">tax no.</span></span>
  
<span data-ttu-id="a7123-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-599">taxno#</span></span>
  
<span data-ttu-id="a7123-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-600">taxnumber#</span></span>
  
<span data-ttu-id="a7123-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-601">taxnumber</span></span>
  
<span data-ttu-id="a7123-602">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-602">tax id</span></span>
  
<span data-ttu-id="a7123-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-603">taxid#</span></span>
  
<span data-ttu-id="a7123-604">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-604">tax identification number</span></span>
  
<span data-ttu-id="a7123-605">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-605">tax identification no.</span></span>
  
<span data-ttu-id="a7123-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="a7123-606">steuernummer</span></span>
  
<span data-ttu-id="a7123-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="a7123-607">steuer id</span></span>
  
<span data-ttu-id="a7123-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="a7123-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="a7123-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="a7123-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="a7123-610">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-610">Format</span></span>

<span data-ttu-id="a7123-611">マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字</span><span class="sxs-lookup"><span data-stu-id="a7123-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="a7123-612">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-613">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-613">Pattern</span></span>

<span data-ttu-id="a7123-614">マルタ nationals: 7 桁と1文字</span><span class="sxs-lookup"><span data-stu-id="a7123-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="a7123-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-615">Seven digits</span></span> 
    
- <span data-ttu-id="a7123-616">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="a7123-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="a7123-617">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="a7123-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="a7123-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-619">Checksum</span></span>

<span data-ttu-id="a7123-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-621">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-621">Definition</span></span>

<span data-ttu-id="a7123-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-623">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-624">from `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-626">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-627">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="a7123-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-629">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-629">tax number</span></span>
  
<span data-ttu-id="a7123-630">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-630">tax no.</span></span>
  
<span data-ttu-id="a7123-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-631">taxno#</span></span>
  
<span data-ttu-id="a7123-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-632">taxnumber#</span></span>
  
<span data-ttu-id="a7123-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-633">taxnumber</span></span>
  
<span data-ttu-id="a7123-634">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-634">tax id</span></span>
  
<span data-ttu-id="a7123-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-635">taxid#</span></span>
  
<span data-ttu-id="a7123-636">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-636">tax identification number</span></span>
  
<span data-ttu-id="a7123-637">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-637">tax identification no.</span></span>
  
<span data-ttu-id="a7123-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="a7123-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="a7123-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="a7123-639">id tat-taxxa</span></span>
  
<span data-ttu-id="a7123-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="a7123-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="a7123-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="a7123-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="a7123-642">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-642">Format</span></span>

<span data-ttu-id="a7123-643">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-644">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-644">Pattern</span></span>

<span data-ttu-id="a7123-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="a7123-646">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-646">Checksum</span></span>

<span data-ttu-id="a7123-647">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-648">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-648">Definition</span></span>

<span data-ttu-id="a7123-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-650">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-651">from `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-653">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-654">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="a7123-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-656">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="a7123-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="a7123-657">netherlands tax identification</span></span>
  
<span data-ttu-id="a7123-658">netherland の税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="a7123-659">netherland の税 id</span><span class="sxs-lookup"><span data-stu-id="a7123-659">netherland's tax identification</span></span>
  
<span data-ttu-id="a7123-660">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-660">tax identification number</span></span>
  
<span data-ttu-id="a7123-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-661">dutch tax id</span></span>
  
<span data-ttu-id="a7123-662">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-662">dutch tax identification number</span></span>
  
<span data-ttu-id="a7123-663">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-663">tax id</span></span>
  
<span data-ttu-id="a7123-664">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-664">tax id#</span></span>
  
<span data-ttu-id="a7123-665">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-665">tax number</span></span>
  
<span data-ttu-id="a7123-666">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="a7123-666">tax no#</span></span>
  
<span data-ttu-id="a7123-667">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-667">tax#</span></span>
  
<span data-ttu-id="a7123-668">は</span><span class="sxs-lookup"><span data-stu-id="a7123-668">tin</span></span>
  
<span data-ttu-id="a7123-669">は</span><span class="sxs-lookup"><span data-stu-id="a7123-669">tin#</span></span>
  
<span data-ttu-id="a7123-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="a7123-670">netherlands tin</span></span>
  
<span data-ttu-id="a7123-671">netherland の tin</span><span class="sxs-lookup"><span data-stu-id="a7123-671">netherland's tin</span></span>
  
<span data-ttu-id="a7123-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="a7123-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="a7123-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="a7123-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="a7123-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="a7123-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="a7123-675">nederlands belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="a7123-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="a7123-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="a7123-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="a7123-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="a7123-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="a7123-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="a7123-678">btw nummer</span></span>
  
<span data-ttu-id="a7123-679">nederlandse belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="a7123-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="a7123-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="a7123-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="a7123-681">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-681">Format</span></span>

<span data-ttu-id="a7123-682">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-683">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-683">Pattern</span></span>

<span data-ttu-id="a7123-684">11桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-685">Checksum</span></span>

<span data-ttu-id="a7123-686">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-687">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-687">Definition</span></span>

<span data-ttu-id="a7123-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-689">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-690">from `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-692">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-693">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="a7123-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-695">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-695">tax number</span></span>
  
<span data-ttu-id="a7123-696">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-696">tax no.</span></span>
  
<span data-ttu-id="a7123-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-697">taxno#</span></span>
  
<span data-ttu-id="a7123-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-698">taxnumber#</span></span>
  
<span data-ttu-id="a7123-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-699">taxnumber</span></span>
  
<span data-ttu-id="a7123-700">nip</span><span class="sxs-lookup"><span data-stu-id="a7123-700">nip</span></span>
  
<span data-ttu-id="a7123-701">nip #</span><span class="sxs-lookup"><span data-stu-id="a7123-701">nip#</span></span>
  
<span data-ttu-id="a7123-702">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-702">tax id</span></span>
  
<span data-ttu-id="a7123-703">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-703">tax id#</span></span>
  
<span data-ttu-id="a7123-704">nip id</span><span class="sxs-lookup"><span data-stu-id="a7123-704">nip id</span></span>
  
<span data-ttu-id="a7123-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="a7123-705">nip id#</span></span>
  
<span data-ttu-id="a7123-706">税識別番号</span><span class="sxs-lookup"><span data-stu-id="a7123-706">tax identification number</span></span>
  
<span data-ttu-id="a7123-707">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-707">tax identification no.</span></span>
  
<span data-ttu-id="a7123-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-708">vat number</span></span>
  
<span data-ttu-id="a7123-709">vat 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-709">vat no.</span></span>
  
<span data-ttu-id="a7123-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="a7123-710">vatno#</span></span>
  
<span data-ttu-id="a7123-711">vat id</span><span class="sxs-lookup"><span data-stu-id="a7123-711">vat id</span></span>
  
<span data-ttu-id="a7123-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="a7123-712">vat id#</span></span>
  
<span data-ttu-id="a7123-713">特定 identyfikacji podat・ wewej</span><span class="sxs-lookup"><span data-stu-id="a7123-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="a7123-714">polski 特定 identyfikacji podat・ wej</span><span class="sxs-lookup"><span data-stu-id="a7123-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="a7123-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="a7123-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="a7123-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="a7123-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="a7123-717">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-717">Format</span></span>

<span data-ttu-id="a7123-718">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-719">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-719">Pattern</span></span>

<span data-ttu-id="a7123-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-721">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-721">Checksum</span></span>

<span data-ttu-id="a7123-722">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-723">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-723">Definition</span></span>

<span data-ttu-id="a7123-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-725">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-726">from `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-728">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-729">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="a7123-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-731">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-731">tax number</span></span>
  
<span data-ttu-id="a7123-732">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-732">tax no.</span></span>
  
<span data-ttu-id="a7123-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-733">taxno#</span></span>
  
<span data-ttu-id="a7123-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="a7123-734">taxnumber#</span></span>
  
<span data-ttu-id="a7123-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="a7123-735">taxnumber</span></span>
  
<span data-ttu-id="a7123-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="a7123-736">nif</span></span>
  
<span data-ttu-id="a7123-737">\n\n</span><span class="sxs-lookup"><span data-stu-id="a7123-737">nif#</span></span>
  
<span data-ttu-id="a7123-738">numero 会計</span><span class="sxs-lookup"><span data-stu-id="a7123-738">numero fiscal</span></span>
  
<span data-ttu-id="a7123-739">número de identificação 会計</span><span class="sxs-lookup"><span data-stu-id="a7123-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="a7123-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="a7123-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="a7123-741">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-741">Format</span></span>

<span data-ttu-id="a7123-742">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="a7123-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-743">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-743">Pattern</span></span>

<span data-ttu-id="a7123-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-745">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-745">Checksum</span></span>

<span data-ttu-id="a7123-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-747">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-747">Definition</span></span>

<span data-ttu-id="a7123-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-749">正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a7123-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-750">from `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-751">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="a7123-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-753">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-753">tax id</span></span>
  
<span data-ttu-id="a7123-754">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-754">tax id number</span></span>
  
<span data-ttu-id="a7123-755">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="a7123-755">tax file no</span></span>
  
<span data-ttu-id="a7123-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="a7123-756">tax file number</span></span>
  
<span data-ttu-id="a7123-757">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-757">tax no</span></span>
  
<span data-ttu-id="a7123-758">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-758">tax number</span></span>
  
<span data-ttu-id="a7123-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-759">taxid#</span></span>
  
<span data-ttu-id="a7123-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-760">taxno#</span></span>
  
<span data-ttu-id="a7123-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="a7123-761">id-ul taxei</span></span>
  
<span data-ttu-id="a7123-762">numărul de 識別子は fiscală</span><span class="sxs-lookup"><span data-stu-id="a7123-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="a7123-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="a7123-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="a7123-764">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-764">Format</span></span>

<span data-ttu-id="a7123-765">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-766">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-766">Pattern</span></span>

<span data-ttu-id="a7123-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-768">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-768">Checksum</span></span>

<span data-ttu-id="a7123-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="a7123-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-770">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-770">Definition</span></span>

<span data-ttu-id="a7123-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-772">正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="a7123-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-773">from `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="a7123-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-776">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-776">tax id</span></span>
  
<span data-ttu-id="a7123-777">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-777">tax id number</span></span>
  
<span data-ttu-id="a7123-778">tin id</span><span class="sxs-lookup"><span data-stu-id="a7123-778">tin id</span></span>
  
<span data-ttu-id="a7123-779">tin no</span><span class="sxs-lookup"><span data-stu-id="a7123-779">tin no</span></span>
  
<span data-ttu-id="a7123-780">スロバキア tin id</span><span class="sxs-lookup"><span data-stu-id="a7123-780">slovakian tin id</span></span>
  
<span data-ttu-id="a7123-781">は</span><span class="sxs-lookup"><span data-stu-id="a7123-781">tin</span></span>
  
<span data-ttu-id="a7123-782">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="a7123-782">tax file no</span></span>
  
<span data-ttu-id="a7123-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="a7123-783">tax file number</span></span>
  
<span data-ttu-id="a7123-784">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-784">tax no</span></span>
  
<span data-ttu-id="a7123-785">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-785">tax number</span></span>
  
<span data-ttu-id="a7123-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-786">taxid#</span></span>
  
<span data-ttu-id="a7123-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-787">taxno#</span></span>
  
<span data-ttu-id="a7123-788">daňové identifikačnéčíslo</span><span class="sxs-lookup"><span data-stu-id="a7123-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="a7123-789">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="a7123-789">daňové číslo</span></span>
  
<span data-ttu-id="a7123-790">daňovéčíslo súboru</span><span class="sxs-lookup"><span data-stu-id="a7123-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="a7123-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="a7123-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="a7123-792">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-792">Format</span></span>

<span data-ttu-id="a7123-793">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-794">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-794">Pattern</span></span>

<span data-ttu-id="a7123-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-796">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-796">Checksum</span></span>

<span data-ttu-id="a7123-797">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-798">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-798">Definition</span></span>

<span data-ttu-id="a7123-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-800">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-801">from `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-803">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-804">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="a7123-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-806">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-806">tax id</span></span>
  
<span data-ttu-id="a7123-807">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-807">tax id number</span></span>
  
<span data-ttu-id="a7123-808">tin id</span><span class="sxs-lookup"><span data-stu-id="a7123-808">tin id</span></span>
  
<span data-ttu-id="a7123-809">tin no</span><span class="sxs-lookup"><span data-stu-id="a7123-809">tin no</span></span>
  
<span data-ttu-id="a7123-810">スロベニア tin id</span><span class="sxs-lookup"><span data-stu-id="a7123-810">slovenian tin id</span></span>
  
<span data-ttu-id="a7123-811">は</span><span class="sxs-lookup"><span data-stu-id="a7123-811">tin</span></span>
  
<span data-ttu-id="a7123-812">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="a7123-812">tax file no</span></span>
  
<span data-ttu-id="a7123-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="a7123-813">tax file number</span></span>
  
<span data-ttu-id="a7123-814">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-814">tax no</span></span>
  
<span data-ttu-id="a7123-815">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-815">tax number</span></span>
  
<span data-ttu-id="a7123-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-816">taxid#</span></span>
  
<span data-ttu-id="a7123-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-817">taxno#</span></span>
  
<span data-ttu-id="a7123-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="a7123-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="a7123-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="a7123-819">davčna številka</span></span>
  
<span data-ttu-id="a7123-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="a7123-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="a7123-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="a7123-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="a7123-822">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-822">Format</span></span>

<span data-ttu-id="a7123-823">7桁または8桁の数字と、指定したパターンの1文字または2文字</span><span class="sxs-lookup"><span data-stu-id="a7123-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-824">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-824">Pattern</span></span>

<span data-ttu-id="a7123-825">スペインの国民 id カードを持つスペインの自然の人物:</span><span class="sxs-lookup"><span data-stu-id="a7123-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="a7123-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-826">Eight digits</span></span> 
    
- <span data-ttu-id="a7123-827">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="a7123-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="a7123-828">スペインの国民 id カードを持たない非常駐 Spaniards</span><span class="sxs-lookup"><span data-stu-id="a7123-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="a7123-829">1つの大文字の "L" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="a7123-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="a7123-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-830">Seven digits</span></span>
    
- <span data-ttu-id="a7123-831">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="a7123-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="a7123-832">Spaniards は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="a7123-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="a7123-833">1つの大文字の "K" (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="a7123-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="a7123-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-834">Seven digits</span></span> 
    
- <span data-ttu-id="a7123-835">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="a7123-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="a7123-836">Foreigner の id 番号を持つ Foreigners</span><span class="sxs-lookup"><span data-stu-id="a7123-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="a7123-837">"X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字</span><span class="sxs-lookup"><span data-stu-id="a7123-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="a7123-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-838">Seven digits</span></span>
    
- <span data-ttu-id="a7123-839">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="a7123-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="a7123-840">Foreigner の識別番号のない Foreigners</span><span class="sxs-lookup"><span data-stu-id="a7123-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="a7123-841">1つの大文字の "M" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="a7123-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="a7123-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="a7123-842">Seven digits</span></span>
    
- <span data-ttu-id="a7123-843">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="a7123-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="a7123-844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-844">Checksum</span></span>

<span data-ttu-id="a7123-845">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-846">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-846">Definition</span></span>

<span data-ttu-id="a7123-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-848">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-849">from `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-851">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-852">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="a7123-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-854">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-854">tax id</span></span>
  
<span data-ttu-id="a7123-855">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-855">tax id number</span></span>
  
<span data-ttu-id="a7123-856">cif id</span><span class="sxs-lookup"><span data-stu-id="a7123-856">cif id</span></span>
  
<span data-ttu-id="a7123-857">cif 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-857">cif no</span></span>
  
<span data-ttu-id="a7123-858">スペインの cif id</span><span class="sxs-lookup"><span data-stu-id="a7123-858">spanish cif id</span></span>
  
<span data-ttu-id="a7123-859">cif</span><span class="sxs-lookup"><span data-stu-id="a7123-859">cif</span></span>
  
<span data-ttu-id="a7123-860">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="a7123-860">tax file no</span></span>
  
<span data-ttu-id="a7123-861">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-861">spanish cif number</span></span>
  
<span data-ttu-id="a7123-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="a7123-862">tax file number</span></span>
  
<span data-ttu-id="a7123-863">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-863">spanish cif no</span></span>
  
<span data-ttu-id="a7123-864">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-864">tax no</span></span>
  
<span data-ttu-id="a7123-865">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-865">tax number</span></span>
  
<span data-ttu-id="a7123-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-866">taxid#</span></span>
  
<span data-ttu-id="a7123-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="a7123-867">taxno#</span></span>
  
<span data-ttu-id="a7123-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="a7123-868">cifid#</span></span>
  
<span data-ttu-id="a7123-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="a7123-869">spanishcifid#</span></span>
  
<span data-ttu-id="a7123-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="a7123-870">spanishcifno#</span></span>
  
<span data-ttu-id="a7123-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="a7123-871">número de contribuyente</span></span>
  
<span data-ttu-id="a7123-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="a7123-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="a7123-873">número de identificación 会計</span><span class="sxs-lookup"><span data-stu-id="a7123-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="a7123-874">cif número</span><span class="sxs-lookup"><span data-stu-id="a7123-874">cif número</span></span>
  
<span data-ttu-id="a7123-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="a7123-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="a7123-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="a7123-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="a7123-877">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-877">Format</span></span>

<span data-ttu-id="a7123-878">指定したパターンの10桁の数字と記号</span><span class="sxs-lookup"><span data-stu-id="a7123-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-879">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-879">Pattern</span></span>

<span data-ttu-id="a7123-880">10桁の数字と記号:</span><span class="sxs-lookup"><span data-stu-id="a7123-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="a7123-881">誕生日に対応する6桁の数字 (yymmdd という)</span><span class="sxs-lookup"><span data-stu-id="a7123-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="a7123-882">プラス記号、マイナス記号、または円記号</span><span class="sxs-lookup"><span data-stu-id="a7123-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="a7123-883">識別番号を一意にするための3桁の数字:</span><span class="sxs-lookup"><span data-stu-id="a7123-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="a7123-884">1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。</span><span class="sxs-lookup"><span data-stu-id="a7123-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="a7123-885">9桁の数字は、男性に対して、または女性に対して、性別を示します。</span><span class="sxs-lookup"><span data-stu-id="a7123-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="a7123-886">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="a7123-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="a7123-887">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-887">Checksum</span></span>

<span data-ttu-id="a7123-888">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-889">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-889">Definition</span></span>

<span data-ttu-id="a7123-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-891">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-892">from `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="a7123-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-894">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-895">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="a7123-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-897">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-897">tax id</span></span>
  
<span data-ttu-id="a7123-898">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-898">tax id no.</span></span>
  
<span data-ttu-id="a7123-899">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-899">tax id number</span></span>
  
<span data-ttu-id="a7123-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="a7123-900">tax identification</span></span>
  
<span data-ttu-id="a7123-901">税 id #</span><span class="sxs-lookup"><span data-stu-id="a7123-901">tax identification#</span></span>
  
<span data-ttu-id="a7123-902">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-902">tax no.</span></span>
  
<span data-ttu-id="a7123-903">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-903">tax#</span></span>
  
<span data-ttu-id="a7123-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-904">taxid#</span></span>
  
<span data-ttu-id="a7123-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="a7123-905">tax file</span></span>
  
<span data-ttu-id="a7123-906">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="a7123-906">tax file no.</span></span>
  
<span data-ttu-id="a7123-907">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="a7123-907">personal id number</span></span>
  
<span data-ttu-id="a7123-908">skatt id の nummer</span><span class="sxs-lookup"><span data-stu-id="a7123-908">skatt id nummer</span></span>
  
<span data-ttu-id="a7123-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="a7123-909">skatt identifikation</span></span>
  
<span data-ttu-id="a7123-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="a7123-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="a7123-911">佐賀</span><span class="sxs-lookup"><span data-stu-id="a7123-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="a7123-912">Format</span><span class="sxs-lookup"><span data-stu-id="a7123-912">Format</span></span>

<span data-ttu-id="a7123-913">Unique 納税リファレンス (utr): スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="a7123-914">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="a7123-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="a7123-915">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="a7123-916">パターン</span><span class="sxs-lookup"><span data-stu-id="a7123-916">Pattern</span></span>

<span data-ttu-id="a7123-917">Unique 納税リファレンス (utr):10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="a7123-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="a7123-918">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="a7123-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="a7123-919">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="a7123-920">チェックサム</span><span class="sxs-lookup"><span data-stu-id="a7123-920">Checksum</span></span>

<span data-ttu-id="a7123-921">はい</span><span class="sxs-lookup"><span data-stu-id="a7123-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="a7123-922">定義</span><span class="sxs-lookup"><span data-stu-id="a7123-922">Definition</span></span>

<span data-ttu-id="a7123-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="a7123-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="a7123-924">関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="a7123-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="a7123-925">from `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="a7123-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="a7123-926">キーワード</span><span class="sxs-lookup"><span data-stu-id="a7123-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="a7123-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="a7123-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="a7123-928">tax id</span><span class="sxs-lookup"><span data-stu-id="a7123-928">tax id</span></span>
  
<span data-ttu-id="a7123-929">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-929">tax id no.</span></span>
  
<span data-ttu-id="a7123-930">納税者番号</span><span class="sxs-lookup"><span data-stu-id="a7123-930">tax id number</span></span>
  
<span data-ttu-id="a7123-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="a7123-931">tax identification</span></span>
  
<span data-ttu-id="a7123-932">税 id #</span><span class="sxs-lookup"><span data-stu-id="a7123-932">tax identification#</span></span>
  
<span data-ttu-id="a7123-933">課税番号</span><span class="sxs-lookup"><span data-stu-id="a7123-933">tax no.</span></span>
  
<span data-ttu-id="a7123-934">申告</span><span class="sxs-lookup"><span data-stu-id="a7123-934">tax#</span></span>
  
<span data-ttu-id="a7123-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="a7123-935">taxid#</span></span>
  
<span data-ttu-id="a7123-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="a7123-936">tax file</span></span>
  
<span data-ttu-id="a7123-937">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="a7123-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a7123-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="a7123-938">See also</span></span>

[<span data-ttu-id="a7123-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="a7123-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

