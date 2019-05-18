---
title: EU 税務識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: adcd9be9b5f8775ad39010d771ff2ac214df1e17
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152959"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="c11a9-104">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-104">EU Tax Identification Number</span></span>

<span data-ttu-id="c11a9-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="c11a9-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="c11a9-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c11a9-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="c11a9-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-108">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-108">Format</span></span>

<span data-ttu-id="c11a9-109">任意指定のハイフンとスラッシュ (/) を含む9桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-110">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-110">Pattern</span></span>

<span data-ttu-id="c11a9-111">任意指定のハイフンとスラッシュ (/) を含む9桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="c11a9-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-112">Two digits</span></span> 
    
- <span data-ttu-id="c11a9-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="c11a9-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="c11a9-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-114">Three digits</span></span>
    
- <span data-ttu-id="c11a9-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="c11a9-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="c11a9-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-117">Checksum</span></span>

<span data-ttu-id="c11a9-118">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-119">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-119">Definition</span></span>

<span data-ttu-id="c11a9-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-121">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-122">From `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-124">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-125">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="c11a9-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-127">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-127">tax number</span></span>
  
<span data-ttu-id="c11a9-128">番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-128">number</span></span>
  
<span data-ttu-id="c11a9-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-129">tax registration number</span></span>
  
<span data-ttu-id="c11a9-130">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-130">tax id</span></span>
  
<span data-ttu-id="c11a9-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="c11a9-131">st.nr.</span></span>
  
<span data-ttu-id="c11a9-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="c11a9-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="c11a9-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-134">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-134">Format</span></span>

<span data-ttu-id="c11a9-135">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-136">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-136">Pattern</span></span>

<span data-ttu-id="c11a9-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-137">11 digits:</span></span>
  
- <span data-ttu-id="c11a9-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-138">Two digits</span></span>
    
- <span data-ttu-id="c11a9-139">"0" または "1"</span><span class="sxs-lookup"><span data-stu-id="c11a9-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="c11a9-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-140">One digit</span></span>
    
- <span data-ttu-id="c11a9-141">"0" または "1" または "2" または "3"</span><span class="sxs-lookup"><span data-stu-id="c11a9-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="c11a9-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-143">Checksum</span></span>

<span data-ttu-id="c11a9-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-145">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-145">Definition</span></span>

<span data-ttu-id="c11a9-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-147">正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-148">From `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c11a9-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="c11a9-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-151">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-151">tax number</span></span>
  
<span data-ttu-id="c11a9-152">国内登録番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-152">national registration number</span></span>
  
<span data-ttu-id="c11a9-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-153">tax registration number</span></span>
  
<span data-ttu-id="c11a9-154">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-154">tax id</span></span>
  
<span data-ttu-id="c11a9-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="c11a9-155">nif</span></span>
  
<span data-ttu-id="c11a9-156">\n\n</span><span class="sxs-lookup"><span data-stu-id="c11a9-156">nif#</span></span>
  
<span data-ttu-id="c11a9-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="c11a9-157">numéro de registre national</span></span>
  
<span data-ttu-id="c11a9-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="c11a9-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="c11a9-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="c11a9-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-160">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-160">Format</span></span>

<span data-ttu-id="c11a9-161">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-162">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-162">Pattern</span></span>

<span data-ttu-id="c11a9-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-164">Checksum</span></span>

<span data-ttu-id="c11a9-165">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-166">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-166">Definition</span></span>

<span data-ttu-id="c11a9-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-168">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-169">From `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-171">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-172">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="c11a9-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-174">bucn</span><span class="sxs-lookup"><span data-stu-id="c11a9-174">bucn</span></span>
  
<span data-ttu-id="c11a9-175">一律の民事番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-175">uniform civil number</span></span>
  
<span data-ttu-id="c11a9-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="c11a9-176">bucn#</span></span>
  
<span data-ttu-id="c11a9-177">uniformcivilnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="c11a9-178">uniform 民事 id</span><span class="sxs-lookup"><span data-stu-id="c11a9-178">uniform civil id</span></span>
  
<span data-ttu-id="c11a9-179">uniform 民事 no</span><span class="sxs-lookup"><span data-stu-id="c11a9-179">uniform civil no</span></span>
  
<span data-ttu-id="c11a9-180">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="c11a9-180">egn</span></span>
  
<span data-ttu-id="c11a9-181">ブルガリアの一様な民事訴訟番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="c11a9-182">uniformcivilno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-182">uniformcivilno#</span></span>
  
<span data-ttu-id="c11a9-183">"/入力 id"</span><span class="sxs-lookup"><span data-stu-id="c11a9-183">egn#</span></span>
  
<span data-ttu-id="c11a9-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="c11a9-184">униформ граждански номер</span></span>
  
<span data-ttu-id="c11a9-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="c11a9-185">униформ id</span></span>
  
<span data-ttu-id="c11a9-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="c11a9-186">униформ граждански id</span></span>
  
<span data-ttu-id="c11a9-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="c11a9-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="c11a9-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="c11a9-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-189">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-189">Format</span></span>

<span data-ttu-id="c11a9-190">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-191">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-191">Pattern</span></span>

<span data-ttu-id="c11a9-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-192">11 digits:</span></span>
  
- <span data-ttu-id="c11a9-193">ランダムに選択された10桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="c11a9-194">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-195">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-195">Checksum</span></span>

<span data-ttu-id="c11a9-196">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-197">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-197">Definition</span></span>

<span data-ttu-id="c11a9-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-199">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-200">From `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-202">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-203">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="c11a9-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-205">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-205">tax number</span></span>
  
<span data-ttu-id="c11a9-206">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-206">tax</span></span>
  
<span data-ttu-id="c11a9-207">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-207">tax id</span></span>
  
<span data-ttu-id="c11a9-208">oid</span><span class="sxs-lookup"><span data-stu-id="c11a9-208">oid</span></span>
  
<span data-ttu-id="c11a9-209">ドーナツ</span><span class="sxs-lookup"><span data-stu-id="c11a9-209">oid#</span></span>
  
<span data-ttu-id="c11a9-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="c11a9-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="c11a9-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="c11a9-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-212">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-212">Format</span></span>

<span data-ttu-id="c11a9-213">指定したパターンの8桁の数字と1文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-214">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-214">Pattern</span></span>

<span data-ttu-id="c11a9-215">8桁の数字と1つの文字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="c11a9-216">"0"</span><span class="sxs-lookup"><span data-stu-id="c11a9-216">A "0"</span></span> 
    
- <span data-ttu-id="c11a9-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-217">Seven digits</span></span>
    
- <span data-ttu-id="c11a9-218">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="c11a9-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-219">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-219">Checksum</span></span>

<span data-ttu-id="c11a9-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-221">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-221">Definition</span></span>

<span data-ttu-id="c11a9-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-223">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-224">From `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-226">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="c11a9-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-229">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-229">tax number</span></span>
  
<span data-ttu-id="c11a9-230">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-230">tax</span></span>
  
<span data-ttu-id="c11a9-231">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-231">tax id</span></span>
  
<span data-ttu-id="c11a9-232">税 id コード</span><span class="sxs-lookup"><span data-stu-id="c11a9-232">tax identification code</span></span>
  
<span data-ttu-id="c11a9-233">認め</span><span class="sxs-lookup"><span data-stu-id="c11a9-233">tic</span></span>
  
<span data-ttu-id="c11a9-234">認め</span><span class="sxs-lookup"><span data-stu-id="c11a9-234">tic#</span></span>
  
<span data-ttu-id="c11a9-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c11a9-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="c11a9-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="c11a9-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="c11a9-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c11a9-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="c11a9-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="c11a9-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-239">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-239">Format</span></span>

<span data-ttu-id="c11a9-240">9桁または10桁の数字 (省略可能な円記号付き)</span><span class="sxs-lookup"><span data-stu-id="c11a9-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-241">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-241">Pattern</span></span>

<span data-ttu-id="c11a9-242">9桁または10桁の数字で、省略可能な backslashl を指定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="c11a9-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-243">Six digits</span></span> 
    
- <span data-ttu-id="c11a9-244">円記号 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="c11a9-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="c11a9-245">3桁または4桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-246">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-246">Checksum</span></span>

<span data-ttu-id="c11a9-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-248">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-248">Definition</span></span>

<span data-ttu-id="c11a9-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-250">正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-251">From `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c11a9-252">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="c11a9-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-254">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-254">tax number</span></span>
  
<span data-ttu-id="c11a9-255">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-255">tax</span></span>
  
<span data-ttu-id="c11a9-256">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-256">tax id</span></span>
  
<span data-ttu-id="c11a9-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-257">personal number</span></span>
  
<span data-ttu-id="c11a9-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="c11a9-258">daňové číslo</span></span>
  
<span data-ttu-id="c11a9-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="c11a9-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="c11a9-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="c11a9-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-261">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-261">Format</span></span>

<span data-ttu-id="c11a9-262">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="c11a9-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-263">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-263">Pattern</span></span>

<span data-ttu-id="c11a9-264">Hyphenl を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="c11a9-265">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="c11a9-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="c11a9-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="c11a9-266">A hyphen</span></span>
    
- <span data-ttu-id="c11a9-267">1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="c11a9-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-268">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-268">Checksum</span></span>

<span data-ttu-id="c11a9-269">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-270">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-270">Definition</span></span>

<span data-ttu-id="c11a9-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-272">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-273">From `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-275">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-276">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="c11a9-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-278">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-278">tax number</span></span>
  
<span data-ttu-id="c11a9-279">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-279">tax</span></span>
  
<span data-ttu-id="c11a9-280">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-280">tax id</span></span>
  
<span data-ttu-id="c11a9-281">cpr 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-281">cpr number</span></span>
  
<span data-ttu-id="c11a9-282">cpr</span><span class="sxs-lookup"><span data-stu-id="c11a9-282">cpr#</span></span>
  
<span data-ttu-id="c11a9-283">nummer の sk</span><span class="sxs-lookup"><span data-stu-id="c11a9-283">skat nummer</span></span>
  
<span data-ttu-id="c11a9-284">id の sk</span><span class="sxs-lookup"><span data-stu-id="c11a9-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="c11a9-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="c11a9-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-286">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-286">Format</span></span>

<span data-ttu-id="c11a9-287">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-288">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-288">Pattern</span></span>

<span data-ttu-id="c11a9-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-289">11 digits:</span></span>
  
-  <span data-ttu-id="c11a9-290">性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。</span><span class="sxs-lookup"><span data-stu-id="c11a9-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="c11a9-291">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="c11a9-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="c11a9-292">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="c11a9-293">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-294">Checksum</span></span>

<span data-ttu-id="c11a9-295">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-296">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-296">Definition</span></span>

<span data-ttu-id="c11a9-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-298">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-299">From `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-301">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-302">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="c11a9-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-304">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-304">tax number</span></span>
  
<span data-ttu-id="c11a9-305">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-305">tax</span></span>
  
<span data-ttu-id="c11a9-306">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-306">tax id</span></span>
  
<span data-ttu-id="c11a9-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="c11a9-307">personal code</span></span>
  
<span data-ttu-id="c11a9-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-308">maksunumber</span></span>
  
<span data-ttu-id="c11a9-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="c11a9-309">maksu id</span></span>
  
<span data-ttu-id="c11a9-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="c11a9-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="c11a9-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="c11a9-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-312">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-312">Format</span></span>

<span data-ttu-id="c11a9-313">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="c11a9-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-314">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-314">Pattern</span></span>

<span data-ttu-id="c11a9-315">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="c11a9-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="c11a9-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-316">Six digits</span></span>
    
- <span data-ttu-id="c11a9-317">プラス記号、マイナス記号、または文字 "A" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味2000します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="c11a9-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-318">Three digits</span></span>
    
- <span data-ttu-id="c11a9-319">1つの文字または1つの番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-320">Checksum</span></span>

<span data-ttu-id="c11a9-321">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-322">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-322">Definition</span></span>

<span data-ttu-id="c11a9-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-324">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-325">From `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-327">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-328">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="c11a9-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-330">identification number</span><span class="sxs-lookup"><span data-stu-id="c11a9-330">identification number</span></span>
  
<span data-ttu-id="c11a9-331">個人 id</span><span class="sxs-lookup"><span data-stu-id="c11a9-331">personal id</span></span>
  
<span data-ttu-id="c11a9-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-332">identity number</span></span>
  
<span data-ttu-id="c11a9-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-333">finnish national id number</span></span>
  
<span data-ttu-id="c11a9-334">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-334">personalidnumber#</span></span>
  
<span data-ttu-id="c11a9-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="c11a9-335">national identification number</span></span>
  
<span data-ttu-id="c11a9-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-336">id number</span></span>
  
<span data-ttu-id="c11a9-337">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-337">national id no.</span></span>
  
<span data-ttu-id="c11a9-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-338">national id number</span></span>
  
<span data-ttu-id="c11a9-339">id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-339">id no</span></span>
  
<span data-ttu-id="c11a9-340">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="c11a9-340">tunnistenumero</span></span>
  
<span data-ttu-id="c11a9-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="c11a9-341">henkilötunnus</span></span>
  
<span data-ttu-id="c11a9-342">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="c11a9-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="c11a9-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="c11a9-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="c11a9-344">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="c11a9-344">identiteetti numero</span></span>
  
<span data-ttu-id="c11a9-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="c11a9-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="c11a9-346">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="c11a9-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="c11a9-347">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="c11a9-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="c11a9-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="c11a9-348">tunnusnumero</span></span>
  
<span data-ttu-id="c11a9-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="c11a9-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="c11a9-350">フランス</span><span class="sxs-lookup"><span data-stu-id="c11a9-350">France</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-351">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-351">Format</span></span>

<span data-ttu-id="c11a9-352">各ユーザーの13桁の数字、およびエンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-353">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-353">Pattern</span></span>

<span data-ttu-id="c11a9-354">個人の場合は13桁。</span><span class="sxs-lookup"><span data-stu-id="c11a9-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="c11a9-355">0、1、2、または3である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="c11a9-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-356">12 digits</span></span>
    
<span data-ttu-id="c11a9-357">エンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-358">Checksum</span></span>

<span data-ttu-id="c11a9-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-360">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-360">Definition</span></span>

<span data-ttu-id="c11a9-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-362">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-363">From `Keywords_france_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-365">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-366">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="c11a9-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-368">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-368">tax identification number</span></span>
  
<span data-ttu-id="c11a9-369">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-369">tax number</span></span>
  
<span data-ttu-id="c11a9-370">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-370">tax id</span></span>
  
<span data-ttu-id="c11a9-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="c11a9-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="c11a9-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="c11a9-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-373">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-373">Format</span></span>

<span data-ttu-id="c11a9-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-375">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-375">Pattern</span></span>

<span data-ttu-id="c11a9-376">11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-376">11 digits :</span></span>
  
-  <span data-ttu-id="c11a9-377">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-377">Ten digits</span></span> 
    
- <span data-ttu-id="c11a9-378">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-379">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-379">Checksum</span></span>

<span data-ttu-id="c11a9-380">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-381">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-381">Definition</span></span>

<span data-ttu-id="c11a9-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-383">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-384">From `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-386">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="c11a9-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-389">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-389">tax number</span></span>
  
<span data-ttu-id="c11a9-390">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-390">tax no.</span></span>
  
<span data-ttu-id="c11a9-391">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-391">taxno#</span></span>
  
<span data-ttu-id="c11a9-392">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-392">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-393">taxnumber</span></span>
  
<span data-ttu-id="c11a9-394">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-394">tax id</span></span>
  
<span data-ttu-id="c11a9-395">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-395">taxid#</span></span>
  
<span data-ttu-id="c11a9-396">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-396">tax identification number</span></span>
  
<span data-ttu-id="c11a9-397">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-397">tax identification no.</span></span>
  
<span data-ttu-id="c11a9-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-398">steuernummer</span></span>
  
<span data-ttu-id="c11a9-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="c11a9-399">steuer id</span></span>
  
<span data-ttu-id="c11a9-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="c11a9-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="c11a9-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-402">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-402">Format</span></span>

<span data-ttu-id="c11a9-403">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-404">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-404">Pattern</span></span>

<span data-ttu-id="c11a9-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-406">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-406">Checksum</span></span>

<span data-ttu-id="c11a9-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-408">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-408">Definition</span></span>

<span data-ttu-id="c11a9-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-410">正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-411">From `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c11a9-412">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="c11a9-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-414">afm</span><span class="sxs-lookup"><span data-stu-id="c11a9-414">afm</span></span>
  
<span data-ttu-id="c11a9-415">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-415">tin</span></span>
  
<span data-ttu-id="c11a9-416">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-416">tax id no.</span></span>
  
<span data-ttu-id="c11a9-417">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-417">tax id no</span></span>
  
<span data-ttu-id="c11a9-418">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-418">tax identification number</span></span>
  
<span data-ttu-id="c11a9-419">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-419">tax registry number</span></span>
  
<span data-ttu-id="c11a9-420">納税レジストリ番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-420">tax registry no.</span></span>
  
<span data-ttu-id="c11a9-421">afm</span><span class="sxs-lookup"><span data-stu-id="c11a9-421">afm#</span></span>
  
<span data-ttu-id="c11a9-422">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-422">tin#</span></span>
  
<span data-ttu-id="c11a9-423">taxidno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-423">taxidno#</span></span>
  
<span data-ttu-id="c11a9-424">taxregistryno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-424">taxregistryno#</span></span>
  
<span data-ttu-id="c11a9-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c11a9-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="c11a9-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="c11a9-426">aφμ</span></span>
  
<span data-ttu-id="c11a9-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="c11a9-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="c11a9-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="c11a9-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="c11a9-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="c11a9-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="c11a9-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="c11a9-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-431">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-431">Format</span></span>

<span data-ttu-id="c11a9-432">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-433">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-433">Pattern</span></span>

<span data-ttu-id="c11a9-434">10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-434">Ten digits:</span></span>
  
-  <span data-ttu-id="c11a9-435">"8" である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="c11a9-436">日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="c11a9-437">同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="c11a9-438">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-439">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-439">Checksum</span></span>

<span data-ttu-id="c11a9-440">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-441">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-441">Definition</span></span>

<span data-ttu-id="c11a9-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-443">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-444">From `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-446">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-447">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="c11a9-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-449">ハンガリーの税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="c11a9-450">ハンガリー tin</span><span class="sxs-lookup"><span data-stu-id="c11a9-450">hungarian tin</span></span>
  
<span data-ttu-id="c11a9-451">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-451">tax id number</span></span>
  
<span data-ttu-id="c11a9-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-452">vat number</span></span>
  
<span data-ttu-id="c11a9-453">税務当局番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-453">tax authority no</span></span>
  
<span data-ttu-id="c11a9-454">課税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-454">tax id tax identity number</span></span>
  
<span data-ttu-id="c11a9-455">taxidnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-455">taxidnumber#</span></span>
  
<span data-ttu-id="c11a9-456">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-456">tin#</span></span>
  
<span data-ttu-id="c11a9-457">hungatiantin#</span><span class="sxs-lookup"><span data-stu-id="c11a9-457">hungatiantin#</span></span>
  
<span data-ttu-id="c11a9-458">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-458">tax identification no</span></span>
  
<span data-ttu-id="c11a9-459">taxidno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-459">taxidno#</span></span>
  
<span data-ttu-id="c11a9-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="c11a9-460">adóazonosító szám</span></span>
  
<span data-ttu-id="c11a9-461">adószám</span><span class="sxs-lookup"><span data-stu-id="c11a9-461">adószám</span></span>
  
<span data-ttu-id="c11a9-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="c11a9-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="c11a9-463">アイルランド</span><span class="sxs-lookup"><span data-stu-id="c11a9-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-464">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-464">Format</span></span>

<span data-ttu-id="c11a9-465">7桁の数字の後にスペースまたは区切り文字を含まない文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-466">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-466">Pattern</span></span>

<span data-ttu-id="c11a9-467">7桁の数字の後に、文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="c11a9-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="c11a9-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-468">Seven digits</span></span> 
    
- <span data-ttu-id="c11a9-469">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="c11a9-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-470">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-470">Checksum</span></span>

<span data-ttu-id="c11a9-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-472">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-472">Definition</span></span>

<span data-ttu-id="c11a9-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-474">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-475">From `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-477">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="c11a9-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-480">パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="c11a9-480">public service no</span></span>
  
<span data-ttu-id="c11a9-481">個人用パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="c11a9-481">personal public service no</span></span>
  
<span data-ttu-id="c11a9-482">pps no</span><span class="sxs-lookup"><span data-stu-id="c11a9-482">pps no</span></span>
  
<span data-ttu-id="c11a9-483">個人サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="c11a9-483">personal service no</span></span>
  
<span data-ttu-id="c11a9-484">pps サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="c11a9-484">pps service no</span></span>
  
<span data-ttu-id="c11a9-485">ppsno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-485">ppsno#</span></span>
  
<span data-ttu-id="c11a9-486">アイルランド語 (pps)</span><span class="sxs-lookup"><span data-stu-id="c11a9-486">irish pps no</span></span>
  
<span data-ttu-id="c11a9-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="c11a9-487">publicserviceno#</span></span>
  
<span data-ttu-id="c11a9-488">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-488">personal public service number</span></span>
  
<span data-ttu-id="c11a9-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="c11a9-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="c11a9-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="c11a9-490">pps uimh</span></span>
  
<span data-ttu-id="c11a9-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="c11a9-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="c11a9-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="c11a9-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-493">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-493">Format</span></span>

<span data-ttu-id="c11a9-494">指定したパターンの16桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-495">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-495">Pattern</span></span>

<span data-ttu-id="c11a9-496">16桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="c11a9-497">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="c11a9-498">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="c11a9-499">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="c11a9-500">誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、A から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は A と10月は R)。</span><span class="sxs-lookup"><span data-stu-id="c11a9-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="c11a9-501">誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。</span><span class="sxs-lookup"><span data-stu-id="c11a9-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="c11a9-502">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。</span><span class="sxs-lookup"><span data-stu-id="c11a9-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="c11a9-503">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-504">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-504">Checksum</span></span>

<span data-ttu-id="c11a9-505">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-506">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-506">Definition</span></span>

<span data-ttu-id="c11a9-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-508">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-509">From `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-511">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-512">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="c11a9-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-514">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-514">tax number</span></span>
  
<span data-ttu-id="c11a9-515">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-515">tax no.</span></span>
  
<span data-ttu-id="c11a9-516">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-516">taxno#</span></span>
  
<span data-ttu-id="c11a9-517">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-517">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-518">taxnumber</span></span>
  
<span data-ttu-id="c11a9-519">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-519">tax id</span></span>
  
<span data-ttu-id="c11a9-520">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-520">taxid#</span></span>
  
<span data-ttu-id="c11a9-521">会計コード</span><span class="sxs-lookup"><span data-stu-id="c11a9-521">fiscal code</span></span>
  
<span data-ttu-id="c11a9-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="c11a9-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="c11a9-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="c11a9-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-524">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-524">Format</span></span>

<span data-ttu-id="c11a9-525">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-526">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-526">Pattern</span></span>

<span data-ttu-id="c11a9-527">指定したパターンの11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="c11a9-528">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="c11a9-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="c11a9-529">"0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="c11a9-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-531">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-531">Checksum</span></span>

<span data-ttu-id="c11a9-532">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-533">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-533">Definition</span></span>

<span data-ttu-id="c11a9-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-535">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-536">From `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-538">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-539">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="c11a9-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-541">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-541">tax number</span></span>
  
<span data-ttu-id="c11a9-542">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-542">tax no.</span></span>
  
<span data-ttu-id="c11a9-543">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-543">taxno#</span></span>
  
<span data-ttu-id="c11a9-544">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-544">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-545">taxnumber</span></span>
  
<span data-ttu-id="c11a9-546">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-546">tax id</span></span>
  
<span data-ttu-id="c11a9-547">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-547">taxid#</span></span>
  
<span data-ttu-id="c11a9-548">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-548">tax identification number</span></span>
  
<span data-ttu-id="c11a9-549">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-549">tax identification no.</span></span>
  
<span data-ttu-id="c11a9-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="c11a9-550">nodokļa numurs</span></span>
  
<span data-ttu-id="c11a9-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="c11a9-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="c11a9-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="c11a9-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="c11a9-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="c11a9-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-554">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-554">Format</span></span>

<span data-ttu-id="c11a9-555">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="c11a9-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-556">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-556">Pattern</span></span>

<span data-ttu-id="c11a9-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-558">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-558">Checksum</span></span>

<span data-ttu-id="c11a9-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-560">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-560">Definition</span></span>

<span data-ttu-id="c11a9-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-562">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-563">From `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-565">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="c11a9-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-568">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-568">tax number</span></span>
  
<span data-ttu-id="c11a9-569">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-569">tax no.</span></span>
  
<span data-ttu-id="c11a9-570">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="c11a9-570">tax no#</span></span>
  
<span data-ttu-id="c11a9-571">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-571">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-572">taxnumber</span></span>
  
<span data-ttu-id="c11a9-573">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-573">tax id</span></span>
  
<span data-ttu-id="c11a9-574">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-574">taxid#</span></span>
  
<span data-ttu-id="c11a9-575">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-575">tax identification number</span></span>
  
<span data-ttu-id="c11a9-576">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-576">tax identification no.</span></span>
  
<span data-ttu-id="c11a9-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="c11a9-577">mokesčių id</span></span>
  
<span data-ttu-id="c11a9-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="c11a9-578">mokesčių numeris</span></span>
  
<span data-ttu-id="c11a9-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="c11a9-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="c11a9-580">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="c11a9-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-581">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-581">Format</span></span>

<span data-ttu-id="c11a9-582">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-583">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-583">Pattern</span></span>

<span data-ttu-id="c11a9-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-584">13 digits:</span></span>
  
-  <span data-ttu-id="c11a9-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-585">11 digits</span></span> 
    
- <span data-ttu-id="c11a9-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-587">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-587">Checksum</span></span>

<span data-ttu-id="c11a9-588">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-589">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-589">Definition</span></span>

<span data-ttu-id="c11a9-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-591">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-592">From `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-594">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-595">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="c11a9-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-597">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-597">tax number</span></span>
  
<span data-ttu-id="c11a9-598">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-598">tax no.</span></span>
  
<span data-ttu-id="c11a9-599">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-599">taxno#</span></span>
  
<span data-ttu-id="c11a9-600">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-600">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-601">taxnumber</span></span>
  
<span data-ttu-id="c11a9-602">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-602">tax id</span></span>
  
<span data-ttu-id="c11a9-603">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-603">taxid#</span></span>
  
<span data-ttu-id="c11a9-604">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-604">tax identification number</span></span>
  
<span data-ttu-id="c11a9-605">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-605">tax identification no.</span></span>
  
<span data-ttu-id="c11a9-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-606">steuernummer</span></span>
  
<span data-ttu-id="c11a9-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="c11a9-607">steuer id</span></span>
  
<span data-ttu-id="c11a9-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="c11a9-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="c11a9-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-610">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-610">Format</span></span>

<span data-ttu-id="c11a9-611">マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="c11a9-612">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-613">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-613">Pattern</span></span>

<span data-ttu-id="c11a9-614">マルタ nationals: 7 桁と1文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="c11a9-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-615">Seven digits</span></span> 
    
- <span data-ttu-id="c11a9-616">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="c11a9-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="c11a9-617">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="c11a9-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c11a9-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-619">Checksum</span></span>

<span data-ttu-id="c11a9-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-621">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-621">Definition</span></span>

<span data-ttu-id="c11a9-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-623">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-624">From `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-626">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-627">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="c11a9-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-629">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-629">tax number</span></span>
  
<span data-ttu-id="c11a9-630">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-630">tax no.</span></span>
  
<span data-ttu-id="c11a9-631">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-631">taxno#</span></span>
  
<span data-ttu-id="c11a9-632">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-632">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-633">taxnumber</span></span>
  
<span data-ttu-id="c11a9-634">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-634">tax id</span></span>
  
<span data-ttu-id="c11a9-635">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-635">taxid#</span></span>
  
<span data-ttu-id="c11a9-636">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-636">tax identification number</span></span>
  
<span data-ttu-id="c11a9-637">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-637">tax identification no.</span></span>
  
<span data-ttu-id="c11a9-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="c11a9-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="c11a9-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="c11a9-639">id tat-taxxa</span></span>
  
<span data-ttu-id="c11a9-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="c11a9-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="c11a9-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="c11a9-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-642">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-642">Format</span></span>

<span data-ttu-id="c11a9-643">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-644">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-644">Pattern</span></span>

<span data-ttu-id="c11a9-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c11a9-646">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-646">Checksum</span></span>

<span data-ttu-id="c11a9-647">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-648">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-648">Definition</span></span>

<span data-ttu-id="c11a9-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-650">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-651">From `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-653">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-654">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="c11a9-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-656">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="c11a9-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="c11a9-657">netherlands tax identification</span></span>
  
<span data-ttu-id="c11a9-658">netherland の税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="c11a9-659">netherland の税 id</span><span class="sxs-lookup"><span data-stu-id="c11a9-659">netherland's tax identification</span></span>
  
<span data-ttu-id="c11a9-660">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-660">tax identification number</span></span>
  
<span data-ttu-id="c11a9-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-661">dutch tax id</span></span>
  
<span data-ttu-id="c11a9-662">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-662">dutch tax identification number</span></span>
  
<span data-ttu-id="c11a9-663">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-663">tax id</span></span>
  
<span data-ttu-id="c11a9-664">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-664">tax id#</span></span>
  
<span data-ttu-id="c11a9-665">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-665">tax number</span></span>
  
<span data-ttu-id="c11a9-666">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="c11a9-666">tax no#</span></span>
  
<span data-ttu-id="c11a9-667">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-667">tax#</span></span>
  
<span data-ttu-id="c11a9-668">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-668">tin</span></span>
  
<span data-ttu-id="c11a9-669">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-669">tin#</span></span>
  
<span data-ttu-id="c11a9-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="c11a9-670">netherlands tin</span></span>
  
<span data-ttu-id="c11a9-671">netherland の tin</span><span class="sxs-lookup"><span data-stu-id="c11a9-671">netherland's tin</span></span>
  
<span data-ttu-id="c11a9-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="c11a9-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="c11a9-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="c11a9-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="c11a9-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="c11a9-675">nederlands belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="c11a9-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="c11a9-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="c11a9-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="c11a9-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-678">btw nummer</span></span>
  
<span data-ttu-id="c11a9-679">nederlandse belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="c11a9-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="c11a9-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="c11a9-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-681">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-681">Format</span></span>

<span data-ttu-id="c11a9-682">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-683">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-683">Pattern</span></span>

<span data-ttu-id="c11a9-684">11桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-685">Checksum</span></span>

<span data-ttu-id="c11a9-686">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-687">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-687">Definition</span></span>

<span data-ttu-id="c11a9-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-689">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-690">From `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-692">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-693">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="c11a9-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-695">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-695">tax number</span></span>
  
<span data-ttu-id="c11a9-696">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-696">tax no.</span></span>
  
<span data-ttu-id="c11a9-697">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-697">taxno#</span></span>
  
<span data-ttu-id="c11a9-698">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-698">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-699">taxnumber</span></span>
  
<span data-ttu-id="c11a9-700">nip</span><span class="sxs-lookup"><span data-stu-id="c11a9-700">nip</span></span>
  
<span data-ttu-id="c11a9-701">nip #</span><span class="sxs-lookup"><span data-stu-id="c11a9-701">nip#</span></span>
  
<span data-ttu-id="c11a9-702">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-702">tax id</span></span>
  
<span data-ttu-id="c11a9-703">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-703">tax id#</span></span>
  
<span data-ttu-id="c11a9-704">nip id</span><span class="sxs-lookup"><span data-stu-id="c11a9-704">nip id</span></span>
  
<span data-ttu-id="c11a9-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="c11a9-705">nip id#</span></span>
  
<span data-ttu-id="c11a9-706">税識別番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-706">tax identification number</span></span>
  
<span data-ttu-id="c11a9-707">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-707">tax identification no.</span></span>
  
<span data-ttu-id="c11a9-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-708">vat number</span></span>
  
<span data-ttu-id="c11a9-709">vat 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-709">vat no.</span></span>
  
<span data-ttu-id="c11a9-710">vatno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-710">vatno#</span></span>
  
<span data-ttu-id="c11a9-711">vat id</span><span class="sxs-lookup"><span data-stu-id="c11a9-711">vat id</span></span>
  
<span data-ttu-id="c11a9-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="c11a9-712">vat id#</span></span>
  
<span data-ttu-id="c11a9-713">特定 identyfikacji podat・ wewej</span><span class="sxs-lookup"><span data-stu-id="c11a9-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="c11a9-714">polski 特定 identyfikacji podat・ wej</span><span class="sxs-lookup"><span data-stu-id="c11a9-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="c11a9-715">numeridentyfikacjipodatkowej#</span><span class="sxs-lookup"><span data-stu-id="c11a9-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="c11a9-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="c11a9-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-717">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-717">Format</span></span>

<span data-ttu-id="c11a9-718">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-719">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-719">Pattern</span></span>

<span data-ttu-id="c11a9-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-721">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-721">Checksum</span></span>

<span data-ttu-id="c11a9-722">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-723">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-723">Definition</span></span>

<span data-ttu-id="c11a9-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-725">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-726">From `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-728">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-729">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="c11a9-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-731">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-731">tax number</span></span>
  
<span data-ttu-id="c11a9-732">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-732">tax no.</span></span>
  
<span data-ttu-id="c11a9-733">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-733">taxno#</span></span>
  
<span data-ttu-id="c11a9-734">taxnumber#</span><span class="sxs-lookup"><span data-stu-id="c11a9-734">taxnumber#</span></span>
  
<span data-ttu-id="c11a9-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="c11a9-735">taxnumber</span></span>
  
<span data-ttu-id="c11a9-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="c11a9-736">nif</span></span>
  
<span data-ttu-id="c11a9-737">\n\n</span><span class="sxs-lookup"><span data-stu-id="c11a9-737">nif#</span></span>
  
<span data-ttu-id="c11a9-738">numero 会計</span><span class="sxs-lookup"><span data-stu-id="c11a9-738">numero fiscal</span></span>
  
<span data-ttu-id="c11a9-739">número de identificação 会計</span><span class="sxs-lookup"><span data-stu-id="c11a9-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="c11a9-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="c11a9-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-741">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-741">Format</span></span>

<span data-ttu-id="c11a9-742">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-743">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-743">Pattern</span></span>

<span data-ttu-id="c11a9-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-745">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-745">Checksum</span></span>

<span data-ttu-id="c11a9-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-747">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-747">Definition</span></span>

<span data-ttu-id="c11a9-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-749">正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-750">From `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c11a9-751">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="c11a9-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-753">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-753">tax id</span></span>
  
<span data-ttu-id="c11a9-754">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-754">tax id number</span></span>
  
<span data-ttu-id="c11a9-755">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-755">tax file no</span></span>
  
<span data-ttu-id="c11a9-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="c11a9-756">tax file number</span></span>
  
<span data-ttu-id="c11a9-757">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-757">tax no</span></span>
  
<span data-ttu-id="c11a9-758">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-758">tax number</span></span>
  
<span data-ttu-id="c11a9-759">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-759">taxid#</span></span>
  
<span data-ttu-id="c11a9-760">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-760">taxno#</span></span>
  
<span data-ttu-id="c11a9-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="c11a9-761">id-ul taxei</span></span>
  
<span data-ttu-id="c11a9-762">numărul de 識別子は fiscală</span><span class="sxs-lookup"><span data-stu-id="c11a9-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="c11a9-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="c11a9-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-764">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-764">Format</span></span>

<span data-ttu-id="c11a9-765">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-766">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-766">Pattern</span></span>

<span data-ttu-id="c11a9-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-768">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-768">Checksum</span></span>

<span data-ttu-id="c11a9-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="c11a9-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-770">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-770">Definition</span></span>

<span data-ttu-id="c11a9-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-772">正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-773">From `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c11a9-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="c11a9-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-776">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-776">tax id</span></span>
  
<span data-ttu-id="c11a9-777">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-777">tax id number</span></span>
  
<span data-ttu-id="c11a9-778">tin id</span><span class="sxs-lookup"><span data-stu-id="c11a9-778">tin id</span></span>
  
<span data-ttu-id="c11a9-779">tin no</span><span class="sxs-lookup"><span data-stu-id="c11a9-779">tin no</span></span>
  
<span data-ttu-id="c11a9-780">スロバキア tin id</span><span class="sxs-lookup"><span data-stu-id="c11a9-780">slovakian tin id</span></span>
  
<span data-ttu-id="c11a9-781">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-781">tin</span></span>
  
<span data-ttu-id="c11a9-782">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-782">tax file no</span></span>
  
<span data-ttu-id="c11a9-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="c11a9-783">tax file number</span></span>
  
<span data-ttu-id="c11a9-784">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-784">tax no</span></span>
  
<span data-ttu-id="c11a9-785">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-785">tax number</span></span>
  
<span data-ttu-id="c11a9-786">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-786">taxid#</span></span>
  
<span data-ttu-id="c11a9-787">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-787">taxno#</span></span>
  
<span data-ttu-id="c11a9-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="c11a9-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="c11a9-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="c11a9-789">daňové číslo</span></span>
  
<span data-ttu-id="c11a9-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="c11a9-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="c11a9-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="c11a9-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-792">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-792">Format</span></span>

<span data-ttu-id="c11a9-793">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-794">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-794">Pattern</span></span>

<span data-ttu-id="c11a9-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-796">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-796">Checksum</span></span>

<span data-ttu-id="c11a9-797">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-798">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-798">Definition</span></span>

<span data-ttu-id="c11a9-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-800">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-801">From `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-803">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-804">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="c11a9-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-806">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-806">tax id</span></span>
  
<span data-ttu-id="c11a9-807">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-807">tax id number</span></span>
  
<span data-ttu-id="c11a9-808">tin id</span><span class="sxs-lookup"><span data-stu-id="c11a9-808">tin id</span></span>
  
<span data-ttu-id="c11a9-809">tin no</span><span class="sxs-lookup"><span data-stu-id="c11a9-809">tin no</span></span>
  
<span data-ttu-id="c11a9-810">スロベニア tin id</span><span class="sxs-lookup"><span data-stu-id="c11a9-810">slovenian tin id</span></span>
  
<span data-ttu-id="c11a9-811">は</span><span class="sxs-lookup"><span data-stu-id="c11a9-811">tin</span></span>
  
<span data-ttu-id="c11a9-812">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-812">tax file no</span></span>
  
<span data-ttu-id="c11a9-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="c11a9-813">tax file number</span></span>
  
<span data-ttu-id="c11a9-814">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-814">tax no</span></span>
  
<span data-ttu-id="c11a9-815">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-815">tax number</span></span>
  
<span data-ttu-id="c11a9-816">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-816">taxid#</span></span>
  
<span data-ttu-id="c11a9-817">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-817">taxno#</span></span>
  
<span data-ttu-id="c11a9-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="c11a9-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="c11a9-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="c11a9-819">davčna številka</span></span>
  
<span data-ttu-id="c11a9-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="c11a9-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="c11a9-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="c11a9-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-822">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-822">Format</span></span>

<span data-ttu-id="c11a9-823">7桁または8桁の数字と、指定したパターンの1文字または2文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-824">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-824">Pattern</span></span>

<span data-ttu-id="c11a9-825">スペインの国民 Id カードを持つスペインの自然の人物:</span><span class="sxs-lookup"><span data-stu-id="c11a9-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="c11a9-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-826">Eight digits</span></span> 
    
- <span data-ttu-id="c11a9-827">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="c11a9-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c11a9-828">スペインの国民 Id カードを持たない非常駐 Spaniards</span><span class="sxs-lookup"><span data-stu-id="c11a9-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="c11a9-829">1つの大文字の "L" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="c11a9-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="c11a9-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-830">Seven digits</span></span>
    
- <span data-ttu-id="c11a9-831">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="c11a9-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c11a9-832">Spaniards は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="c11a9-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="c11a9-833">1つの大文字の "K" (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="c11a9-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="c11a9-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-834">Seven digits</span></span> 
    
- <span data-ttu-id="c11a9-835">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="c11a9-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="c11a9-836">Foreigner の Id 番号を持つ Foreigners</span><span class="sxs-lookup"><span data-stu-id="c11a9-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="c11a9-837">"X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字</span><span class="sxs-lookup"><span data-stu-id="c11a9-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="c11a9-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-838">Seven digits</span></span>
    
- <span data-ttu-id="c11a9-839">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="c11a9-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="c11a9-840">Foreigner の識別番号のない Foreigners</span><span class="sxs-lookup"><span data-stu-id="c11a9-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="c11a9-841">1つの大文字の "M" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="c11a9-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="c11a9-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="c11a9-842">Seven digits</span></span>
    
- <span data-ttu-id="c11a9-843">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="c11a9-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="c11a9-844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-844">Checksum</span></span>

<span data-ttu-id="c11a9-845">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-846">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-846">Definition</span></span>

<span data-ttu-id="c11a9-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-848">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-849">From `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-851">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-852">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="c11a9-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-854">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-854">tax id</span></span>
  
<span data-ttu-id="c11a9-855">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-855">tax id number</span></span>
  
<span data-ttu-id="c11a9-856">cif id</span><span class="sxs-lookup"><span data-stu-id="c11a9-856">cif id</span></span>
  
<span data-ttu-id="c11a9-857">cif 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-857">cif no</span></span>
  
<span data-ttu-id="c11a9-858">スペインの cif id</span><span class="sxs-lookup"><span data-stu-id="c11a9-858">spanish cif id</span></span>
  
<span data-ttu-id="c11a9-859">cif</span><span class="sxs-lookup"><span data-stu-id="c11a9-859">cif</span></span>
  
<span data-ttu-id="c11a9-860">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-860">tax file no</span></span>
  
<span data-ttu-id="c11a9-861">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-861">spanish cif number</span></span>
  
<span data-ttu-id="c11a9-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="c11a9-862">tax file number</span></span>
  
<span data-ttu-id="c11a9-863">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-863">spanish cif no</span></span>
  
<span data-ttu-id="c11a9-864">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-864">tax no</span></span>
  
<span data-ttu-id="c11a9-865">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-865">tax number</span></span>
  
<span data-ttu-id="c11a9-866">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-866">taxid#</span></span>
  
<span data-ttu-id="c11a9-867">taxno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-867">taxno#</span></span>
  
<span data-ttu-id="c11a9-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="c11a9-868">cifid#</span></span>
  
<span data-ttu-id="c11a9-869">spanishcifid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-869">spanishcifid#</span></span>
  
<span data-ttu-id="c11a9-870">spanishcifno#</span><span class="sxs-lookup"><span data-stu-id="c11a9-870">spanishcifno#</span></span>
  
<span data-ttu-id="c11a9-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="c11a9-871">número de contribuyente</span></span>
  
<span data-ttu-id="c11a9-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="c11a9-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="c11a9-873">número de identificación 会計</span><span class="sxs-lookup"><span data-stu-id="c11a9-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="c11a9-874">cif número</span><span class="sxs-lookup"><span data-stu-id="c11a9-874">cif número</span></span>
  
<span data-ttu-id="c11a9-875">cifnúmero#</span><span class="sxs-lookup"><span data-stu-id="c11a9-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="c11a9-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="c11a9-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-877">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-877">Format</span></span>

<span data-ttu-id="c11a9-878">指定したパターンの10桁の数字と記号</span><span class="sxs-lookup"><span data-stu-id="c11a9-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-879">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-879">Pattern</span></span>

<span data-ttu-id="c11a9-880">10桁の数字と記号:</span><span class="sxs-lookup"><span data-stu-id="c11a9-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="c11a9-881">誕生日に対応する6桁の数字 (YYMMDD という)</span><span class="sxs-lookup"><span data-stu-id="c11a9-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="c11a9-882">プラス記号、マイナス記号、または円記号</span><span class="sxs-lookup"><span data-stu-id="c11a9-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="c11a9-883">識別番号を一意にするための3桁の数字:</span><span class="sxs-lookup"><span data-stu-id="c11a9-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="c11a9-884">1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="c11a9-885">9桁の数字は、男性に対して、または女性に対して、性別を示します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="c11a9-886">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="c11a9-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c11a9-887">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-887">Checksum</span></span>

<span data-ttu-id="c11a9-888">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-889">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-889">Definition</span></span>

<span data-ttu-id="c11a9-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-891">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-892">From `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="c11a9-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-894">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="c11a9-895">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="c11a9-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-897">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-897">tax id</span></span>
  
<span data-ttu-id="c11a9-898">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-898">tax id no.</span></span>
  
<span data-ttu-id="c11a9-899">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-899">tax id number</span></span>
  
<span data-ttu-id="c11a9-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="c11a9-900">tax identification</span></span>
  
<span data-ttu-id="c11a9-901">税 id #</span><span class="sxs-lookup"><span data-stu-id="c11a9-901">tax identification#</span></span>
  
<span data-ttu-id="c11a9-902">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-902">tax no.</span></span>
  
<span data-ttu-id="c11a9-903">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-903">tax#</span></span>
  
<span data-ttu-id="c11a9-904">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-904">taxid#</span></span>
  
<span data-ttu-id="c11a9-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="c11a9-905">tax file</span></span>
  
<span data-ttu-id="c11a9-906">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-906">tax file no.</span></span>
  
<span data-ttu-id="c11a9-907">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-907">personal id number</span></span>
  
<span data-ttu-id="c11a9-908">skatt id の nummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-908">skatt id nummer</span></span>
  
<span data-ttu-id="c11a9-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="c11a9-909">skatt identifikation</span></span>
  
<span data-ttu-id="c11a9-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="c11a9-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="c11a9-911">佐賀</span><span class="sxs-lookup"><span data-stu-id="c11a9-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="c11a9-912">Format</span><span class="sxs-lookup"><span data-stu-id="c11a9-912">Format</span></span>

<span data-ttu-id="c11a9-913">Unique 納税リファレンス (UTR): スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="c11a9-914">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="c11a9-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="c11a9-915">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c11a9-916">パターン</span><span class="sxs-lookup"><span data-stu-id="c11a9-916">Pattern</span></span>

<span data-ttu-id="c11a9-917">Unique 納税リファレンス (UTR):10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="c11a9-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="c11a9-918">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="c11a9-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="c11a9-919">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c11a9-920">チェックサム</span><span class="sxs-lookup"><span data-stu-id="c11a9-920">Checksum</span></span>

<span data-ttu-id="c11a9-921">はい</span><span class="sxs-lookup"><span data-stu-id="c11a9-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="c11a9-922">定義</span><span class="sxs-lookup"><span data-stu-id="c11a9-922">Definition</span></span>

<span data-ttu-id="c11a9-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c11a9-924">関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="c11a9-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c11a9-925">From `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="c11a9-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c11a9-926">キーワード</span><span class="sxs-lookup"><span data-stu-id="c11a9-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="c11a9-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="c11a9-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="c11a9-928">tax id</span><span class="sxs-lookup"><span data-stu-id="c11a9-928">tax id</span></span>
  
<span data-ttu-id="c11a9-929">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-929">tax id no.</span></span>
  
<span data-ttu-id="c11a9-930">納税者番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-930">tax id number</span></span>
  
<span data-ttu-id="c11a9-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="c11a9-931">tax identification</span></span>
  
<span data-ttu-id="c11a9-932">税 id #</span><span class="sxs-lookup"><span data-stu-id="c11a9-932">tax identification#</span></span>
  
<span data-ttu-id="c11a9-933">課税番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-933">tax no.</span></span>
  
<span data-ttu-id="c11a9-934">申告</span><span class="sxs-lookup"><span data-stu-id="c11a9-934">tax#</span></span>
  
<span data-ttu-id="c11a9-935">taxid#</span><span class="sxs-lookup"><span data-stu-id="c11a9-935">taxid#</span></span>
  
<span data-ttu-id="c11a9-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="c11a9-936">tax file</span></span>
  
<span data-ttu-id="c11a9-937">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="c11a9-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c11a9-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="c11a9-938">See also</span></span>

[<span data-ttu-id="c11a9-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="c11a9-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

