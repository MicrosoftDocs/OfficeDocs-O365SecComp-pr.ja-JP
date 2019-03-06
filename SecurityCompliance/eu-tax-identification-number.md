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
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410912"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="2c7f7-104">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-104">EU Tax Identification Number</span></span>

<span data-ttu-id="2c7f7-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="2c7f7-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="2c7f7-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-108">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-108">Format</span></span>

<span data-ttu-id="2c7f7-109">任意指定のハイフンとスラッシュ (/) を含む9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-110">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-110">Pattern</span></span>

<span data-ttu-id="2c7f7-111">任意指定のハイフンとスラッシュ (/) を含む9桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="2c7f7-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-112">Two digits</span></span> 
    
- <span data-ttu-id="2c7f7-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="2c7f7-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-114">Three digits</span></span>
    
- <span data-ttu-id="2c7f7-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="2c7f7-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-117">Checksum</span></span>

<span data-ttu-id="2c7f7-118">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-119">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-119">Definition</span></span>

<span data-ttu-id="2c7f7-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-121">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-122">from `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-124">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-125">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="2c7f7-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-127">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-127">tax number</span></span>
  
<span data-ttu-id="2c7f7-128">number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-128">number</span></span>
  
<span data-ttu-id="2c7f7-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-129">tax registration number</span></span>
  
<span data-ttu-id="2c7f7-130">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-130">tax id</span></span>
  
<span data-ttu-id="2c7f7-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-131">st.nr.</span></span>
  
<span data-ttu-id="2c7f7-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="2c7f7-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="2c7f7-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-134">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-134">Format</span></span>

<span data-ttu-id="2c7f7-135">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-136">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-136">Pattern</span></span>

<span data-ttu-id="2c7f7-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-137">11 digits:</span></span>
  
- <span data-ttu-id="2c7f7-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-138">Two digits</span></span>
    
- <span data-ttu-id="2c7f7-139">"0" または "1"</span><span class="sxs-lookup"><span data-stu-id="2c7f7-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="2c7f7-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-140">One digit</span></span>
    
- <span data-ttu-id="2c7f7-141">"0" または "1" または "2" または "3"</span><span class="sxs-lookup"><span data-stu-id="2c7f7-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="2c7f7-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-143">Checksum</span></span>

<span data-ttu-id="2c7f7-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-145">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-145">Definition</span></span>

<span data-ttu-id="2c7f7-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-147">正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-148">from `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2c7f7-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="2c7f7-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-151">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-151">tax number</span></span>
  
<span data-ttu-id="2c7f7-152">国内登録番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-152">national registration number</span></span>
  
<span data-ttu-id="2c7f7-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-153">tax registration number</span></span>
  
<span data-ttu-id="2c7f7-154">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-154">tax id</span></span>
  
<span data-ttu-id="2c7f7-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="2c7f7-155">nif</span></span>
  
<span data-ttu-id="2c7f7-156">\n\n</span><span class="sxs-lookup"><span data-stu-id="2c7f7-156">nif#</span></span>
  
<span data-ttu-id="2c7f7-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="2c7f7-157">numéro de registre national</span></span>
  
<span data-ttu-id="2c7f7-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="2c7f7-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="2c7f7-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-160">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-160">Format</span></span>

<span data-ttu-id="2c7f7-161">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-162">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-162">Pattern</span></span>

<span data-ttu-id="2c7f7-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-164">Checksum</span></span>

<span data-ttu-id="2c7f7-165">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-166">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-166">Definition</span></span>

<span data-ttu-id="2c7f7-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-168">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-169">from `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-171">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-172">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="2c7f7-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-174">bucn</span><span class="sxs-lookup"><span data-stu-id="2c7f7-174">bucn</span></span>
  
<span data-ttu-id="2c7f7-175">一律の民事番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-175">uniform civil number</span></span>
  
<span data-ttu-id="2c7f7-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-176">bucn#</span></span>
  
<span data-ttu-id="2c7f7-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="2c7f7-178">uniform 民事 id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-178">uniform civil id</span></span>
  
<span data-ttu-id="2c7f7-179">uniform 民事 no</span><span class="sxs-lookup"><span data-stu-id="2c7f7-179">uniform civil no</span></span>
  
<span data-ttu-id="2c7f7-180">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="2c7f7-180">egn</span></span>
  
<span data-ttu-id="2c7f7-181">ブルガリアの一様な民事訴訟番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="2c7f7-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-182">uniformcivilno#</span></span>
  
<span data-ttu-id="2c7f7-183">"/入力 id"</span><span class="sxs-lookup"><span data-stu-id="2c7f7-183">egn#</span></span>
  
<span data-ttu-id="2c7f7-184">униформгражданскиномер</span><span class="sxs-lookup"><span data-stu-id="2c7f7-184">униформ граждански номер</span></span>
  
<span data-ttu-id="2c7f7-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-185">униформ id</span></span>
  
<span data-ttu-id="2c7f7-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-186">униформ граждански id</span></span>
  
<span data-ttu-id="2c7f7-187">униформгражданскине</span><span class="sxs-lookup"><span data-stu-id="2c7f7-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="2c7f7-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-189">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-189">Format</span></span>

<span data-ttu-id="2c7f7-190">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-191">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-191">Pattern</span></span>

<span data-ttu-id="2c7f7-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-192">11 digits:</span></span>
  
- <span data-ttu-id="2c7f7-193">ランダムに選択された10桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="2c7f7-194">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-195">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-195">Checksum</span></span>

<span data-ttu-id="2c7f7-196">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-197">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-197">Definition</span></span>

<span data-ttu-id="2c7f7-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-199">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-200">from `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-202">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-203">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="2c7f7-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-205">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-205">tax number</span></span>
  
<span data-ttu-id="2c7f7-206">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-206">tax</span></span>
  
<span data-ttu-id="2c7f7-207">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-207">tax id</span></span>
  
<span data-ttu-id="2c7f7-208">oid</span><span class="sxs-lookup"><span data-stu-id="2c7f7-208">oid</span></span>
  
<span data-ttu-id="2c7f7-209">ドーナツ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-209">oid#</span></span>
  
<span data-ttu-id="2c7f7-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="2c7f7-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="2c7f7-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="2c7f7-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-212">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-212">Format</span></span>

<span data-ttu-id="2c7f7-213">指定したパターンの8桁の数字と1文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-214">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-214">Pattern</span></span>

<span data-ttu-id="2c7f7-215">8桁の数字と1つの文字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="2c7f7-216">"0"</span><span class="sxs-lookup"><span data-stu-id="2c7f7-216">A "0"</span></span> 
    
- <span data-ttu-id="2c7f7-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-217">Seven digits</span></span>
    
- <span data-ttu-id="2c7f7-218">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-219">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-219">Checksum</span></span>

<span data-ttu-id="2c7f7-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-221">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-221">Definition</span></span>

<span data-ttu-id="2c7f7-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-223">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-224">from `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-226">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="2c7f7-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-229">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-229">tax number</span></span>
  
<span data-ttu-id="2c7f7-230">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-230">tax</span></span>
  
<span data-ttu-id="2c7f7-231">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-231">tax id</span></span>
  
<span data-ttu-id="2c7f7-232">税 id コード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-232">tax identification code</span></span>
  
<span data-ttu-id="2c7f7-233">認め</span><span class="sxs-lookup"><span data-stu-id="2c7f7-233">tic</span></span>
  
<span data-ttu-id="2c7f7-234">認め</span><span class="sxs-lookup"><span data-stu-id="2c7f7-234">tic#</span></span>
  
<span data-ttu-id="2c7f7-235">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="2c7f7-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="2c7f7-236">φορολογικήταυτότητα</span><span class="sxs-lookup"><span data-stu-id="2c7f7-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="2c7f7-237">κωδικόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="2c7f7-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="2c7f7-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="2c7f7-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-239">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-239">Format</span></span>

<span data-ttu-id="2c7f7-240">9桁または10桁の数字 (省略可能な円記号付き)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-241">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-241">Pattern</span></span>

<span data-ttu-id="2c7f7-242">9桁または10桁の数字で、省略可能な backslashl を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="2c7f7-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-243">Six digits</span></span> 
    
- <span data-ttu-id="2c7f7-244">円記号 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="2c7f7-245">3桁または4桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-246">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-246">Checksum</span></span>

<span data-ttu-id="2c7f7-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-248">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-248">Definition</span></span>

<span data-ttu-id="2c7f7-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-250">正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-251">from `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2c7f7-252">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="2c7f7-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-254">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-254">tax number</span></span>
  
<span data-ttu-id="2c7f7-255">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-255">tax</span></span>
  
<span data-ttu-id="2c7f7-256">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-256">tax id</span></span>
  
<span data-ttu-id="2c7f7-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-257">personal number</span></span>
  
<span data-ttu-id="2c7f7-258">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="2c7f7-258">daňové číslo</span></span>
  
<span data-ttu-id="2c7f7-259">osobníčíslo</span><span class="sxs-lookup"><span data-stu-id="2c7f7-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="2c7f7-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="2c7f7-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-261">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-261">Format</span></span>

<span data-ttu-id="2c7f7-262">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-263">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-263">Pattern</span></span>

<span data-ttu-id="2c7f7-264">hyphenl を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="2c7f7-265">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="2c7f7-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="2c7f7-266">A hyphen</span></span>
    
- <span data-ttu-id="2c7f7-267">1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-268">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-268">Checksum</span></span>

<span data-ttu-id="2c7f7-269">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-270">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-270">Definition</span></span>

<span data-ttu-id="2c7f7-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-272">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-273">from `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-275">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-276">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="2c7f7-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-278">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-278">tax number</span></span>
  
<span data-ttu-id="2c7f7-279">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-279">tax</span></span>
  
<span data-ttu-id="2c7f7-280">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-280">tax id</span></span>
  
<span data-ttu-id="2c7f7-281">cpr 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-281">cpr number</span></span>
  
<span data-ttu-id="2c7f7-282">cpr</span><span class="sxs-lookup"><span data-stu-id="2c7f7-282">cpr#</span></span>
  
<span data-ttu-id="2c7f7-283">nummer の sk</span><span class="sxs-lookup"><span data-stu-id="2c7f7-283">skat nummer</span></span>
  
<span data-ttu-id="2c7f7-284">id の sk</span><span class="sxs-lookup"><span data-stu-id="2c7f7-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="2c7f7-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-286">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-286">Format</span></span>

<span data-ttu-id="2c7f7-287">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-288">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-288">Pattern</span></span>

<span data-ttu-id="2c7f7-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-289">11 digits:</span></span>
  
-  <span data-ttu-id="2c7f7-290">性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="2c7f7-291">誕生日に対応する6桁の数字 (yymmdd という)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="2c7f7-292">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="2c7f7-293">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-294">Checksum</span></span>

<span data-ttu-id="2c7f7-295">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-296">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-296">Definition</span></span>

<span data-ttu-id="2c7f7-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-298">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-299">from `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-301">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-302">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="2c7f7-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-304">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-304">tax number</span></span>
  
<span data-ttu-id="2c7f7-305">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-305">tax</span></span>
  
<span data-ttu-id="2c7f7-306">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-306">tax id</span></span>
  
<span data-ttu-id="2c7f7-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-307">personal code</span></span>
  
<span data-ttu-id="2c7f7-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-308">maksunumber</span></span>
  
<span data-ttu-id="2c7f7-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-309">maksu id</span></span>
  
<span data-ttu-id="2c7f7-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="2c7f7-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="2c7f7-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="2c7f7-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-312">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-312">Format</span></span>

<span data-ttu-id="2c7f7-313">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-314">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-314">Pattern</span></span>

<span data-ttu-id="2c7f7-315">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="2c7f7-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-316">Six digits</span></span>
    
- <span data-ttu-id="2c7f7-317">プラス記号、マイナス記号、または文字 "a" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="2c7f7-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-318">Three digits</span></span>
    
- <span data-ttu-id="2c7f7-319">1つの文字または1つの番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-320">Checksum</span></span>

<span data-ttu-id="2c7f7-321">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-322">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-322">Definition</span></span>

<span data-ttu-id="2c7f7-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-324">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-325">from `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-327">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-328">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="2c7f7-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-330">identification number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-330">identification number</span></span>
  
<span data-ttu-id="2c7f7-331">個人 id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-331">personal id</span></span>
  
<span data-ttu-id="2c7f7-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-332">identity number</span></span>
  
<span data-ttu-id="2c7f7-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-333">finnish national id number</span></span>
  
<span data-ttu-id="2c7f7-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-334">personalidnumber#</span></span>
  
<span data-ttu-id="2c7f7-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-335">national identification number</span></span>
  
<span data-ttu-id="2c7f7-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-336">id number</span></span>
  
<span data-ttu-id="2c7f7-337">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-337">national id no.</span></span>
  
<span data-ttu-id="2c7f7-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-338">national id number</span></span>
  
<span data-ttu-id="2c7f7-339">id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-339">id no</span></span>
  
<span data-ttu-id="2c7f7-340">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="2c7f7-340">tunnistenumero</span></span>
  
<span data-ttu-id="2c7f7-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="2c7f7-341">henkilötunnus</span></span>
  
<span data-ttu-id="2c7f7-342">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="2c7f7-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="2c7f7-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="2c7f7-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="2c7f7-344">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="2c7f7-344">identiteetti numero</span></span>
  
<span data-ttu-id="2c7f7-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="2c7f7-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="2c7f7-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="2c7f7-347">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="2c7f7-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="2c7f7-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="2c7f7-348">tunnusnumero</span></span>
  
<span data-ttu-id="2c7f7-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="2c7f7-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="2c7f7-350">フランス</span><span class="sxs-lookup"><span data-stu-id="2c7f7-350">France</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-351">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-351">Format</span></span>

<span data-ttu-id="2c7f7-352">各ユーザーの13桁の数字、およびエンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-353">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-353">Pattern</span></span>

<span data-ttu-id="2c7f7-354">個人の場合は13桁。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="2c7f7-355">0、1、2、または3である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="2c7f7-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-356">12 digits</span></span>
    
<span data-ttu-id="2c7f7-357">エンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-358">Checksum</span></span>

<span data-ttu-id="2c7f7-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-360">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-360">Definition</span></span>

<span data-ttu-id="2c7f7-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-362">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-363">from `Keywords_france_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-365">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-366">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="2c7f7-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-368">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-368">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-369">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-369">tax number</span></span>
  
<span data-ttu-id="2c7f7-370">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-370">tax id</span></span>
  
<span data-ttu-id="2c7f7-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="2c7f7-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="2c7f7-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-373">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-373">Format</span></span>

<span data-ttu-id="2c7f7-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-375">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-375">Pattern</span></span>

<span data-ttu-id="2c7f7-376">11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-376">11 digits :</span></span>
  
-  <span data-ttu-id="2c7f7-377">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-377">Ten digits</span></span> 
    
- <span data-ttu-id="2c7f7-378">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-379">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-379">Checksum</span></span>

<span data-ttu-id="2c7f7-380">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-381">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-381">Definition</span></span>

<span data-ttu-id="2c7f7-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-383">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-384">from `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-386">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="2c7f7-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-389">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-389">tax number</span></span>
  
<span data-ttu-id="2c7f7-390">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-390">tax no.</span></span>
  
<span data-ttu-id="2c7f7-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-391">taxno#</span></span>
  
<span data-ttu-id="2c7f7-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-392">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-393">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-394">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-394">tax id</span></span>
  
<span data-ttu-id="2c7f7-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-395">taxid#</span></span>
  
<span data-ttu-id="2c7f7-396">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-396">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-397">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-397">tax identification no.</span></span>
  
<span data-ttu-id="2c7f7-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-398">steuernummer</span></span>
  
<span data-ttu-id="2c7f7-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-399">steuer id</span></span>
  
<span data-ttu-id="2c7f7-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="2c7f7-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-402">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-402">Format</span></span>

<span data-ttu-id="2c7f7-403">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-404">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-404">Pattern</span></span>

<span data-ttu-id="2c7f7-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-406">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-406">Checksum</span></span>

<span data-ttu-id="2c7f7-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-408">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-408">Definition</span></span>

<span data-ttu-id="2c7f7-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-410">正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-411">from `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2c7f7-412">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="2c7f7-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-414">afm</span><span class="sxs-lookup"><span data-stu-id="2c7f7-414">afm</span></span>
  
<span data-ttu-id="2c7f7-415">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-415">tin</span></span>
  
<span data-ttu-id="2c7f7-416">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-416">tax id no.</span></span>
  
<span data-ttu-id="2c7f7-417">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-417">tax id no</span></span>
  
<span data-ttu-id="2c7f7-418">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-418">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-419">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-419">tax registry number</span></span>
  
<span data-ttu-id="2c7f7-420">納税レジストリ番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-420">tax registry no.</span></span>
  
<span data-ttu-id="2c7f7-421">afm</span><span class="sxs-lookup"><span data-stu-id="2c7f7-421">afm#</span></span>
  
<span data-ttu-id="2c7f7-422">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-422">tin#</span></span>
  
<span data-ttu-id="2c7f7-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-423">taxidno#</span></span>
  
<span data-ttu-id="2c7f7-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-424">taxregistryno#</span></span>
  
<span data-ttu-id="2c7f7-425">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="2c7f7-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="2c7f7-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-426">aφμ</span></span>
  
<span data-ttu-id="2c7f7-427">aφμαριθμός</span><span class="sxs-lookup"><span data-stu-id="2c7f7-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="2c7f7-428">φορολογικούμητρώουνο。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="2c7f7-429">τοναριθμόφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="2c7f7-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="2c7f7-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="2c7f7-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-431">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-431">Format</span></span>

<span data-ttu-id="2c7f7-432">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-433">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-433">Pattern</span></span>

<span data-ttu-id="2c7f7-434">10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-434">Ten digits:</span></span>
  
-  <span data-ttu-id="2c7f7-435">"8" である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="2c7f7-436">日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="2c7f7-437">同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="2c7f7-438">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-439">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-439">Checksum</span></span>

<span data-ttu-id="2c7f7-440">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-441">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-441">Definition</span></span>

<span data-ttu-id="2c7f7-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-443">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-444">from `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-446">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-447">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="2c7f7-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-449">ハンガリーの税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="2c7f7-450">ハンガリー tin</span><span class="sxs-lookup"><span data-stu-id="2c7f7-450">hungarian tin</span></span>
  
<span data-ttu-id="2c7f7-451">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-451">tax id number</span></span>
  
<span data-ttu-id="2c7f7-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-452">vat number</span></span>
  
<span data-ttu-id="2c7f7-453">税務当局番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-453">tax authority no</span></span>
  
<span data-ttu-id="2c7f7-454">課税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-454">tax id tax identity number</span></span>
  
<span data-ttu-id="2c7f7-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-455">taxidnumber#</span></span>
  
<span data-ttu-id="2c7f7-456">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-456">tin#</span></span>
  
<span data-ttu-id="2c7f7-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-457">hungatiantin#</span></span>
  
<span data-ttu-id="2c7f7-458">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-458">tax identification no</span></span>
  
<span data-ttu-id="2c7f7-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-459">taxidno#</span></span>
  
<span data-ttu-id="2c7f7-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="2c7f7-460">adóazonosító szám</span></span>
  
<span data-ttu-id="2c7f7-461">adószám</span><span class="sxs-lookup"><span data-stu-id="2c7f7-461">adószám</span></span>
  
<span data-ttu-id="2c7f7-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="2c7f7-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="2c7f7-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="2c7f7-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-464">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-464">Format</span></span>

<span data-ttu-id="2c7f7-465">7桁の数字の後にスペースまたは区切り文字を含まない文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-466">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-466">Pattern</span></span>

<span data-ttu-id="2c7f7-467">7桁の数字の後に、文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="2c7f7-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-468">Seven digits</span></span> 
    
- <span data-ttu-id="2c7f7-469">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-470">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-470">Checksum</span></span>

<span data-ttu-id="2c7f7-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-472">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-472">Definition</span></span>

<span data-ttu-id="2c7f7-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-474">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-475">from `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-477">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="2c7f7-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-480">パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-480">public service no</span></span>
  
<span data-ttu-id="2c7f7-481">個人用パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-481">personal public service no</span></span>
  
<span data-ttu-id="2c7f7-482">pps no</span><span class="sxs-lookup"><span data-stu-id="2c7f7-482">pps no</span></span>
  
<span data-ttu-id="2c7f7-483">個人サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-483">personal service no</span></span>
  
<span data-ttu-id="2c7f7-484">pps サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-484">pps service no</span></span>
  
<span data-ttu-id="2c7f7-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-485">ppsno#</span></span>
  
<span data-ttu-id="2c7f7-486">アイルランド語 (pps)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-486">irish pps no</span></span>
  
<span data-ttu-id="2c7f7-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-487">publicserviceno#</span></span>
  
<span data-ttu-id="2c7f7-488">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-488">personal public service number</span></span>
  
<span data-ttu-id="2c7f7-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="2c7f7-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="2c7f7-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="2c7f7-490">pps uimh</span></span>
  
<span data-ttu-id="2c7f7-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="2c7f7-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="2c7f7-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-493">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-493">Format</span></span>

<span data-ttu-id="2c7f7-494">指定したパターンの16桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-495">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-495">Pattern</span></span>

<span data-ttu-id="2c7f7-496">16桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="2c7f7-497">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="2c7f7-498">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="2c7f7-499">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="2c7f7-500">誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、a から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は a と10月は r)。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="2c7f7-501">誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="2c7f7-502">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="2c7f7-503">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-504">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-504">Checksum</span></span>

<span data-ttu-id="2c7f7-505">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-506">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-506">Definition</span></span>

<span data-ttu-id="2c7f7-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-508">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-509">from `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-511">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-512">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="2c7f7-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-514">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-514">tax number</span></span>
  
<span data-ttu-id="2c7f7-515">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-515">tax no.</span></span>
  
<span data-ttu-id="2c7f7-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-516">taxno#</span></span>
  
<span data-ttu-id="2c7f7-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-517">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-518">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-519">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-519">tax id</span></span>
  
<span data-ttu-id="2c7f7-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-520">taxid#</span></span>
  
<span data-ttu-id="2c7f7-521">会計コード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-521">fiscal code</span></span>
  
<span data-ttu-id="2c7f7-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="2c7f7-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="2c7f7-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-524">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-524">Format</span></span>

<span data-ttu-id="2c7f7-525">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-526">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-526">Pattern</span></span>

<span data-ttu-id="2c7f7-527">指定したパターンの11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="2c7f7-528">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="2c7f7-529">"0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="2c7f7-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-531">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-531">Checksum</span></span>

<span data-ttu-id="2c7f7-532">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-533">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-533">Definition</span></span>

<span data-ttu-id="2c7f7-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-535">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-536">from `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-538">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-539">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="2c7f7-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-541">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-541">tax number</span></span>
  
<span data-ttu-id="2c7f7-542">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-542">tax no.</span></span>
  
<span data-ttu-id="2c7f7-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-543">taxno#</span></span>
  
<span data-ttu-id="2c7f7-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-544">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-545">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-546">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-546">tax id</span></span>
  
<span data-ttu-id="2c7f7-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-547">taxid#</span></span>
  
<span data-ttu-id="2c7f7-548">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-548">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-549">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-549">tax identification no.</span></span>
  
<span data-ttu-id="2c7f7-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="2c7f7-550">nodokļa numurs</span></span>
  
<span data-ttu-id="2c7f7-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="2c7f7-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="2c7f7-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="2c7f7-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="2c7f7-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-554">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-554">Format</span></span>

<span data-ttu-id="2c7f7-555">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-556">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-556">Pattern</span></span>

<span data-ttu-id="2c7f7-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-558">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-558">Checksum</span></span>

<span data-ttu-id="2c7f7-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-560">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-560">Definition</span></span>

<span data-ttu-id="2c7f7-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-562">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-563">from `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-565">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="2c7f7-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-568">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-568">tax number</span></span>
  
<span data-ttu-id="2c7f7-569">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-569">tax no.</span></span>
  
<span data-ttu-id="2c7f7-570">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-570">tax no#</span></span>
  
<span data-ttu-id="2c7f7-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-571">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-572">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-573">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-573">tax id</span></span>
  
<span data-ttu-id="2c7f7-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-574">taxid#</span></span>
  
<span data-ttu-id="2c7f7-575">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-575">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-576">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-576">tax identification no.</span></span>
  
<span data-ttu-id="2c7f7-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-577">mokesčių id</span></span>
  
<span data-ttu-id="2c7f7-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="2c7f7-578">mokesčių numeris</span></span>
  
<span data-ttu-id="2c7f7-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="2c7f7-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="2c7f7-580">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="2c7f7-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-581">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-581">Format</span></span>

<span data-ttu-id="2c7f7-582">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-583">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-583">Pattern</span></span>

<span data-ttu-id="2c7f7-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-584">13 digits:</span></span>
  
-  <span data-ttu-id="2c7f7-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-585">11 digits</span></span> 
    
- <span data-ttu-id="2c7f7-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-587">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-587">Checksum</span></span>

<span data-ttu-id="2c7f7-588">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-589">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-589">Definition</span></span>

<span data-ttu-id="2c7f7-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-591">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-592">from `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-594">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-595">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="2c7f7-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-597">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-597">tax number</span></span>
  
<span data-ttu-id="2c7f7-598">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-598">tax no.</span></span>
  
<span data-ttu-id="2c7f7-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-599">taxno#</span></span>
  
<span data-ttu-id="2c7f7-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-600">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-601">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-602">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-602">tax id</span></span>
  
<span data-ttu-id="2c7f7-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-603">taxid#</span></span>
  
<span data-ttu-id="2c7f7-604">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-604">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-605">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-605">tax identification no.</span></span>
  
<span data-ttu-id="2c7f7-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-606">steuernummer</span></span>
  
<span data-ttu-id="2c7f7-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-607">steuer id</span></span>
  
<span data-ttu-id="2c7f7-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="2c7f7-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-610">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-610">Format</span></span>

<span data-ttu-id="2c7f7-611">マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="2c7f7-612">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-613">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-613">Pattern</span></span>

<span data-ttu-id="2c7f7-614">マルタ nationals: 7 桁と1文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="2c7f7-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-615">Seven digits</span></span> 
    
- <span data-ttu-id="2c7f7-616">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="2c7f7-617">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="2c7f7-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-619">Checksum</span></span>

<span data-ttu-id="2c7f7-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-621">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-621">Definition</span></span>

<span data-ttu-id="2c7f7-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-623">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-624">from `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-626">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-627">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="2c7f7-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-629">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-629">tax number</span></span>
  
<span data-ttu-id="2c7f7-630">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-630">tax no.</span></span>
  
<span data-ttu-id="2c7f7-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-631">taxno#</span></span>
  
<span data-ttu-id="2c7f7-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-632">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-633">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-634">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-634">tax id</span></span>
  
<span data-ttu-id="2c7f7-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-635">taxid#</span></span>
  
<span data-ttu-id="2c7f7-636">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-636">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-637">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-637">tax identification no.</span></span>
  
<span data-ttu-id="2c7f7-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="2c7f7-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="2c7f7-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="2c7f7-639">id tat-taxxa</span></span>
  
<span data-ttu-id="2c7f7-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="2c7f7-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="2c7f7-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="2c7f7-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-642">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-642">Format</span></span>

<span data-ttu-id="2c7f7-643">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-644">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-644">Pattern</span></span>

<span data-ttu-id="2c7f7-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-646">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-646">Checksum</span></span>

<span data-ttu-id="2c7f7-647">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-648">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-648">Definition</span></span>

<span data-ttu-id="2c7f7-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-650">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-651">from `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-653">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-654">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="2c7f7-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-656">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="2c7f7-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-657">netherlands tax identification</span></span>
  
<span data-ttu-id="2c7f7-658">netherland の税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="2c7f7-659">netherland の税 id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-659">netherland's tax identification</span></span>
  
<span data-ttu-id="2c7f7-660">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-660">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-661">dutch tax id</span></span>
  
<span data-ttu-id="2c7f7-662">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-662">dutch tax identification number</span></span>
  
<span data-ttu-id="2c7f7-663">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-663">tax id</span></span>
  
<span data-ttu-id="2c7f7-664">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-664">tax id#</span></span>
  
<span data-ttu-id="2c7f7-665">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-665">tax number</span></span>
  
<span data-ttu-id="2c7f7-666">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-666">tax no#</span></span>
  
<span data-ttu-id="2c7f7-667">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-667">tax#</span></span>
  
<span data-ttu-id="2c7f7-668">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-668">tin</span></span>
  
<span data-ttu-id="2c7f7-669">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-669">tin#</span></span>
  
<span data-ttu-id="2c7f7-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="2c7f7-670">netherlands tin</span></span>
  
<span data-ttu-id="2c7f7-671">netherland の tin</span><span class="sxs-lookup"><span data-stu-id="2c7f7-671">netherland's tin</span></span>
  
<span data-ttu-id="2c7f7-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="2c7f7-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="2c7f7-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="2c7f7-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="2c7f7-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="2c7f7-675">nederlands belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="2c7f7-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="2c7f7-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="2c7f7-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="2c7f7-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-678">btw nummer</span></span>
  
<span data-ttu-id="2c7f7-679">nederlandse belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="2c7f7-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="2c7f7-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="2c7f7-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-681">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-681">Format</span></span>

<span data-ttu-id="2c7f7-682">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-683">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-683">Pattern</span></span>

<span data-ttu-id="2c7f7-684">11桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-685">Checksum</span></span>

<span data-ttu-id="2c7f7-686">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-687">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-687">Definition</span></span>

<span data-ttu-id="2c7f7-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-689">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-690">from `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-692">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-693">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="2c7f7-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-695">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-695">tax number</span></span>
  
<span data-ttu-id="2c7f7-696">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-696">tax no.</span></span>
  
<span data-ttu-id="2c7f7-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-697">taxno#</span></span>
  
<span data-ttu-id="2c7f7-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-698">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-699">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-700">nip</span><span class="sxs-lookup"><span data-stu-id="2c7f7-700">nip</span></span>
  
<span data-ttu-id="2c7f7-701">nip #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-701">nip#</span></span>
  
<span data-ttu-id="2c7f7-702">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-702">tax id</span></span>
  
<span data-ttu-id="2c7f7-703">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-703">tax id#</span></span>
  
<span data-ttu-id="2c7f7-704">nip id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-704">nip id</span></span>
  
<span data-ttu-id="2c7f7-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-705">nip id#</span></span>
  
<span data-ttu-id="2c7f7-706">税識別番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-706">tax identification number</span></span>
  
<span data-ttu-id="2c7f7-707">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-707">tax identification no.</span></span>
  
<span data-ttu-id="2c7f7-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-708">vat number</span></span>
  
<span data-ttu-id="2c7f7-709">vat 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-709">vat no.</span></span>
  
<span data-ttu-id="2c7f7-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-710">vatno#</span></span>
  
<span data-ttu-id="2c7f7-711">vat id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-711">vat id</span></span>
  
<span data-ttu-id="2c7f7-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-712">vat id#</span></span>
  
<span data-ttu-id="2c7f7-713">特定 identyfikacji podat・ wewej</span><span class="sxs-lookup"><span data-stu-id="2c7f7-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="2c7f7-714">polski 特定 identyfikacji podat・ wej</span><span class="sxs-lookup"><span data-stu-id="2c7f7-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="2c7f7-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="2c7f7-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="2c7f7-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-717">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-717">Format</span></span>

<span data-ttu-id="2c7f7-718">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-719">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-719">Pattern</span></span>

<span data-ttu-id="2c7f7-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-721">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-721">Checksum</span></span>

<span data-ttu-id="2c7f7-722">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-723">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-723">Definition</span></span>

<span data-ttu-id="2c7f7-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-725">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-726">from `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-728">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-729">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="2c7f7-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-731">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-731">tax number</span></span>
  
<span data-ttu-id="2c7f7-732">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-732">tax no.</span></span>
  
<span data-ttu-id="2c7f7-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-733">taxno#</span></span>
  
<span data-ttu-id="2c7f7-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-734">taxnumber#</span></span>
  
<span data-ttu-id="2c7f7-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="2c7f7-735">taxnumber</span></span>
  
<span data-ttu-id="2c7f7-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="2c7f7-736">nif</span></span>
  
<span data-ttu-id="2c7f7-737">\n\n</span><span class="sxs-lookup"><span data-stu-id="2c7f7-737">nif#</span></span>
  
<span data-ttu-id="2c7f7-738">numero 会計</span><span class="sxs-lookup"><span data-stu-id="2c7f7-738">numero fiscal</span></span>
  
<span data-ttu-id="2c7f7-739">número de identificação 会計</span><span class="sxs-lookup"><span data-stu-id="2c7f7-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="2c7f7-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-741">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-741">Format</span></span>

<span data-ttu-id="2c7f7-742">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-743">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-743">Pattern</span></span>

<span data-ttu-id="2c7f7-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-745">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-745">Checksum</span></span>

<span data-ttu-id="2c7f7-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-747">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-747">Definition</span></span>

<span data-ttu-id="2c7f7-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-749">正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-750">from `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2c7f7-751">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="2c7f7-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-753">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-753">tax id</span></span>
  
<span data-ttu-id="2c7f7-754">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-754">tax id number</span></span>
  
<span data-ttu-id="2c7f7-755">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-755">tax file no</span></span>
  
<span data-ttu-id="2c7f7-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-756">tax file number</span></span>
  
<span data-ttu-id="2c7f7-757">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-757">tax no</span></span>
  
<span data-ttu-id="2c7f7-758">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-758">tax number</span></span>
  
<span data-ttu-id="2c7f7-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-759">taxid#</span></span>
  
<span data-ttu-id="2c7f7-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-760">taxno#</span></span>
  
<span data-ttu-id="2c7f7-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="2c7f7-761">id-ul taxei</span></span>
  
<span data-ttu-id="2c7f7-762">numărul de 識別子は fiscală</span><span class="sxs-lookup"><span data-stu-id="2c7f7-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="2c7f7-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-764">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-764">Format</span></span>

<span data-ttu-id="2c7f7-765">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-766">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-766">Pattern</span></span>

<span data-ttu-id="2c7f7-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-768">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-768">Checksum</span></span>

<span data-ttu-id="2c7f7-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="2c7f7-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-770">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-770">Definition</span></span>

<span data-ttu-id="2c7f7-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-772">正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-773">from `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2c7f7-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="2c7f7-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-776">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-776">tax id</span></span>
  
<span data-ttu-id="2c7f7-777">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-777">tax id number</span></span>
  
<span data-ttu-id="2c7f7-778">tin id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-778">tin id</span></span>
  
<span data-ttu-id="2c7f7-779">tin no</span><span class="sxs-lookup"><span data-stu-id="2c7f7-779">tin no</span></span>
  
<span data-ttu-id="2c7f7-780">スロバキア tin id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-780">slovakian tin id</span></span>
  
<span data-ttu-id="2c7f7-781">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-781">tin</span></span>
  
<span data-ttu-id="2c7f7-782">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-782">tax file no</span></span>
  
<span data-ttu-id="2c7f7-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-783">tax file number</span></span>
  
<span data-ttu-id="2c7f7-784">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-784">tax no</span></span>
  
<span data-ttu-id="2c7f7-785">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-785">tax number</span></span>
  
<span data-ttu-id="2c7f7-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-786">taxid#</span></span>
  
<span data-ttu-id="2c7f7-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-787">taxno#</span></span>
  
<span data-ttu-id="2c7f7-788">daňové identifikačnéčíslo</span><span class="sxs-lookup"><span data-stu-id="2c7f7-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="2c7f7-789">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="2c7f7-789">daňové číslo</span></span>
  
<span data-ttu-id="2c7f7-790">daňovéčíslo súboru</span><span class="sxs-lookup"><span data-stu-id="2c7f7-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="2c7f7-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="2c7f7-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-792">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-792">Format</span></span>

<span data-ttu-id="2c7f7-793">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-794">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-794">Pattern</span></span>

<span data-ttu-id="2c7f7-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-796">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-796">Checksum</span></span>

<span data-ttu-id="2c7f7-797">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-798">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-798">Definition</span></span>

<span data-ttu-id="2c7f7-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-800">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-801">from `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-803">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-804">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="2c7f7-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-806">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-806">tax id</span></span>
  
<span data-ttu-id="2c7f7-807">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-807">tax id number</span></span>
  
<span data-ttu-id="2c7f7-808">tin id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-808">tin id</span></span>
  
<span data-ttu-id="2c7f7-809">tin no</span><span class="sxs-lookup"><span data-stu-id="2c7f7-809">tin no</span></span>
  
<span data-ttu-id="2c7f7-810">スロベニア tin id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-810">slovenian tin id</span></span>
  
<span data-ttu-id="2c7f7-811">は</span><span class="sxs-lookup"><span data-stu-id="2c7f7-811">tin</span></span>
  
<span data-ttu-id="2c7f7-812">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-812">tax file no</span></span>
  
<span data-ttu-id="2c7f7-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-813">tax file number</span></span>
  
<span data-ttu-id="2c7f7-814">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-814">tax no</span></span>
  
<span data-ttu-id="2c7f7-815">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-815">tax number</span></span>
  
<span data-ttu-id="2c7f7-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-816">taxid#</span></span>
  
<span data-ttu-id="2c7f7-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-817">taxno#</span></span>
  
<span data-ttu-id="2c7f7-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="2c7f7-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="2c7f7-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="2c7f7-819">davčna številka</span></span>
  
<span data-ttu-id="2c7f7-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="2c7f7-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="2c7f7-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-822">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-822">Format</span></span>

<span data-ttu-id="2c7f7-823">7桁または8桁の数字と、指定したパターンの1文字または2文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-824">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-824">Pattern</span></span>

<span data-ttu-id="2c7f7-825">スペインの国民 id カードを持つスペインの自然の人物:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="2c7f7-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-826">Eight digits</span></span> 
    
- <span data-ttu-id="2c7f7-827">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="2c7f7-828">スペインの国民 id カードを持たない非常駐 Spaniards</span><span class="sxs-lookup"><span data-stu-id="2c7f7-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="2c7f7-829">1つの大文字の "L" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="2c7f7-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-830">Seven digits</span></span>
    
- <span data-ttu-id="2c7f7-831">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="2c7f7-832">Spaniards は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="2c7f7-833">1つの大文字の "K" (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="2c7f7-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-834">Seven digits</span></span> 
    
- <span data-ttu-id="2c7f7-835">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="2c7f7-836">Foreigner の id 番号を持つ Foreigners</span><span class="sxs-lookup"><span data-stu-id="2c7f7-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="2c7f7-837">"X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="2c7f7-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-838">Seven digits</span></span>
    
- <span data-ttu-id="2c7f7-839">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="2c7f7-840">Foreigner の識別番号のない Foreigners</span><span class="sxs-lookup"><span data-stu-id="2c7f7-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="2c7f7-841">1つの大文字の "M" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="2c7f7-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="2c7f7-842">Seven digits</span></span>
    
- <span data-ttu-id="2c7f7-843">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-844">Checksum</span></span>

<span data-ttu-id="2c7f7-845">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-846">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-846">Definition</span></span>

<span data-ttu-id="2c7f7-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-848">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-849">from `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-851">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-852">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="2c7f7-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-854">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-854">tax id</span></span>
  
<span data-ttu-id="2c7f7-855">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-855">tax id number</span></span>
  
<span data-ttu-id="2c7f7-856">cif id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-856">cif id</span></span>
  
<span data-ttu-id="2c7f7-857">cif 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-857">cif no</span></span>
  
<span data-ttu-id="2c7f7-858">スペインの cif id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-858">spanish cif id</span></span>
  
<span data-ttu-id="2c7f7-859">cif</span><span class="sxs-lookup"><span data-stu-id="2c7f7-859">cif</span></span>
  
<span data-ttu-id="2c7f7-860">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-860">tax file no</span></span>
  
<span data-ttu-id="2c7f7-861">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-861">spanish cif number</span></span>
  
<span data-ttu-id="2c7f7-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-862">tax file number</span></span>
  
<span data-ttu-id="2c7f7-863">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-863">spanish cif no</span></span>
  
<span data-ttu-id="2c7f7-864">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-864">tax no</span></span>
  
<span data-ttu-id="2c7f7-865">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-865">tax number</span></span>
  
<span data-ttu-id="2c7f7-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-866">taxid#</span></span>
  
<span data-ttu-id="2c7f7-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-867">taxno#</span></span>
  
<span data-ttu-id="2c7f7-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-868">cifid#</span></span>
  
<span data-ttu-id="2c7f7-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-869">spanishcifid#</span></span>
  
<span data-ttu-id="2c7f7-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-870">spanishcifno#</span></span>
  
<span data-ttu-id="2c7f7-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="2c7f7-871">número de contribuyente</span></span>
  
<span data-ttu-id="2c7f7-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="2c7f7-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="2c7f7-873">número de identificación 会計</span><span class="sxs-lookup"><span data-stu-id="2c7f7-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="2c7f7-874">cif número</span><span class="sxs-lookup"><span data-stu-id="2c7f7-874">cif número</span></span>
  
<span data-ttu-id="2c7f7-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="2c7f7-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-877">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-877">Format</span></span>

<span data-ttu-id="2c7f7-878">指定したパターンの10桁の数字と記号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-879">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-879">Pattern</span></span>

<span data-ttu-id="2c7f7-880">10桁の数字と記号:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="2c7f7-881">誕生日に対応する6桁の数字 (yymmdd という)</span><span class="sxs-lookup"><span data-stu-id="2c7f7-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="2c7f7-882">プラス記号、マイナス記号、または円記号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="2c7f7-883">識別番号を一意にするための3桁の数字:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="2c7f7-884">1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="2c7f7-885">9桁の数字は、男性に対して、または女性に対して、性別を示します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="2c7f7-886">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="2c7f7-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="2c7f7-887">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-887">Checksum</span></span>

<span data-ttu-id="2c7f7-888">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-889">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-889">Definition</span></span>

<span data-ttu-id="2c7f7-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-891">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-892">from `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="2c7f7-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-894">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="2c7f7-895">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="2c7f7-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-897">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-897">tax id</span></span>
  
<span data-ttu-id="2c7f7-898">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-898">tax id no.</span></span>
  
<span data-ttu-id="2c7f7-899">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-899">tax id number</span></span>
  
<span data-ttu-id="2c7f7-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="2c7f7-900">tax identification</span></span>
  
<span data-ttu-id="2c7f7-901">税 id #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-901">tax identification#</span></span>
  
<span data-ttu-id="2c7f7-902">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-902">tax no.</span></span>
  
<span data-ttu-id="2c7f7-903">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-903">tax#</span></span>
  
<span data-ttu-id="2c7f7-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-904">taxid#</span></span>
  
<span data-ttu-id="2c7f7-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="2c7f7-905">tax file</span></span>
  
<span data-ttu-id="2c7f7-906">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-906">tax file no.</span></span>
  
<span data-ttu-id="2c7f7-907">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-907">personal id number</span></span>
  
<span data-ttu-id="2c7f7-908">skatt id の nummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-908">skatt id nummer</span></span>
  
<span data-ttu-id="2c7f7-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="2c7f7-909">skatt identifikation</span></span>
  
<span data-ttu-id="2c7f7-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="2c7f7-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="2c7f7-911">佐賀</span><span class="sxs-lookup"><span data-stu-id="2c7f7-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="2c7f7-912">Format</span><span class="sxs-lookup"><span data-stu-id="2c7f7-912">Format</span></span>

<span data-ttu-id="2c7f7-913">Unique 納税リファレンス (utr): スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="2c7f7-914">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="2c7f7-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="2c7f7-915">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="2c7f7-916">パターン</span><span class="sxs-lookup"><span data-stu-id="2c7f7-916">Pattern</span></span>

<span data-ttu-id="2c7f7-917">Unique 納税リファレンス (utr):10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="2c7f7-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="2c7f7-918">国家保険番号 (NINO): 詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="2c7f7-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="2c7f7-919">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、国家保険番号 (NINO) "を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="2c7f7-920">チェックサム</span><span class="sxs-lookup"><span data-stu-id="2c7f7-920">Checksum</span></span>

<span data-ttu-id="2c7f7-921">はい</span><span class="sxs-lookup"><span data-stu-id="2c7f7-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="2c7f7-922">定義</span><span class="sxs-lookup"><span data-stu-id="2c7f7-922">Definition</span></span>

<span data-ttu-id="2c7f7-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="2c7f7-924">関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="2c7f7-925">from `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="2c7f7-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="2c7f7-926">キーワード</span><span class="sxs-lookup"><span data-stu-id="2c7f7-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="2c7f7-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="2c7f7-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="2c7f7-928">tax id</span><span class="sxs-lookup"><span data-stu-id="2c7f7-928">tax id</span></span>
  
<span data-ttu-id="2c7f7-929">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-929">tax id no.</span></span>
  
<span data-ttu-id="2c7f7-930">納税者番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-930">tax id number</span></span>
  
<span data-ttu-id="2c7f7-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="2c7f7-931">tax identification</span></span>
  
<span data-ttu-id="2c7f7-932">税 id #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-932">tax identification#</span></span>
  
<span data-ttu-id="2c7f7-933">課税番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-933">tax no.</span></span>
  
<span data-ttu-id="2c7f7-934">申告</span><span class="sxs-lookup"><span data-stu-id="2c7f7-934">tax#</span></span>
  
<span data-ttu-id="2c7f7-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="2c7f7-935">taxid#</span></span>
  
<span data-ttu-id="2c7f7-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="2c7f7-936">tax file</span></span>
  
<span data-ttu-id="2c7f7-937">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="2c7f7-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c7f7-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="2c7f7-938">See also</span></span>

[<span data-ttu-id="2c7f7-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="2c7f7-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

