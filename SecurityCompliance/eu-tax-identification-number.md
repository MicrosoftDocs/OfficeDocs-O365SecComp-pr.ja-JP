---
title: EU 税務識別番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号の機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: f851cce4be70fd41c24a7876d97c452f0a738eda
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213827"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="5393a-104">EU 税務識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-104">EU Tax Identification Number</span></span>

<span data-ttu-id="5393a-p102">このトピックでは、データ損失防止 (DLP) ポリシーが EU 税務識別番号 (TIN) 機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="5393a-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="5393a-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="5393a-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="5393a-108">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-108">Format</span></span>

<span data-ttu-id="5393a-109">任意指定のハイフンとスラッシュ (/) を含む9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-110">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-110">Pattern</span></span>

<span data-ttu-id="5393a-111">任意指定のハイフンとスラッシュ (/) を含む9桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="5393a-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-112">Two digits</span></span> 
    
- <span data-ttu-id="5393a-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5393a-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="5393a-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-114">Three digits</span></span>
    
- <span data-ttu-id="5393a-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5393a-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="5393a-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-117">Checksum</span></span>

<span data-ttu-id="5393a-118">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-119">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-119">Definition</span></span>

<span data-ttu-id="5393a-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-121">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-122">from `Keywords_austria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-124">関数`Func_austria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-125">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="5393a-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-127">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-127">tax number</span></span>
  
<span data-ttu-id="5393a-128">件数</span><span class="sxs-lookup"><span data-stu-id="5393a-128">number</span></span>
  
<span data-ttu-id="5393a-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="5393a-129">tax registration number</span></span>
  
<span data-ttu-id="5393a-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-130">tax id</span></span>
  
<span data-ttu-id="5393a-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="5393a-131">st.nr.</span></span>
  
<span data-ttu-id="5393a-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="5393a-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="5393a-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="5393a-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="5393a-134">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-134">Format</span></span>

<span data-ttu-id="5393a-135">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-136">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-136">Pattern</span></span>

<span data-ttu-id="5393a-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-137">11 digits:</span></span>
  
- <span data-ttu-id="5393a-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-138">Two digits</span></span>
    
- <span data-ttu-id="5393a-139">"0" または "1"</span><span class="sxs-lookup"><span data-stu-id="5393a-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="5393a-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-140">One digit</span></span>
    
- <span data-ttu-id="5393a-141">"0" または "1" または "2" または "3"</span><span class="sxs-lookup"><span data-stu-id="5393a-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="5393a-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-143">Checksum</span></span>

<span data-ttu-id="5393a-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-145">Definition</span><span class="sxs-lookup"><span data-stu-id="5393a-145">Definition</span></span>

<span data-ttu-id="5393a-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-147">正規表現`Regex_belgium_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5393a-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-148">from `Keywords_belgium_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5393a-149">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="5393a-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-151">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-151">tax number</span></span>
  
<span data-ttu-id="5393a-152">国内登録番号</span><span class="sxs-lookup"><span data-stu-id="5393a-152">national registration number</span></span>
  
<span data-ttu-id="5393a-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="5393a-153">tax registration number</span></span>
  
<span data-ttu-id="5393a-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-154">tax id</span></span>
  
<span data-ttu-id="5393a-155">\n\n</span><span class="sxs-lookup"><span data-stu-id="5393a-155">nif</span></span>
  
<span data-ttu-id="5393a-156">\n\n</span><span class="sxs-lookup"><span data-stu-id="5393a-156">nif#</span></span>
  
<span data-ttu-id="5393a-157">numéro de registre national</span><span class="sxs-lookup"><span data-stu-id="5393a-157">numéro de registre national</span></span>
  
<span data-ttu-id="5393a-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="5393a-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="5393a-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="5393a-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="5393a-160">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-160">Format</span></span>

<span data-ttu-id="5393a-161">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-162">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-162">Pattern</span></span>

<span data-ttu-id="5393a-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-164">Checksum</span></span>

<span data-ttu-id="5393a-165">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-166">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-166">Definition</span></span>

<span data-ttu-id="5393a-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-168">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-169">from `Keywords_bulgaria_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-171">関数`Func_bulgaria_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-172">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="5393a-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-174">bucn</span><span class="sxs-lookup"><span data-stu-id="5393a-174">bucn</span></span>
  
<span data-ttu-id="5393a-175">一律の民事番号</span><span class="sxs-lookup"><span data-stu-id="5393a-175">uniform civil number</span></span>
  
<span data-ttu-id="5393a-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="5393a-176">bucn#</span></span>
  
<span data-ttu-id="5393a-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="5393a-178">uniform 民事 id</span><span class="sxs-lookup"><span data-stu-id="5393a-178">uniform civil id</span></span>
  
<span data-ttu-id="5393a-179">uniform 民事 no</span><span class="sxs-lookup"><span data-stu-id="5393a-179">uniform civil no</span></span>
  
<span data-ttu-id="5393a-180">「//入力 n」</span><span class="sxs-lookup"><span data-stu-id="5393a-180">egn</span></span>
  
<span data-ttu-id="5393a-181">ブルガリアの一様な民事訴訟番号</span><span class="sxs-lookup"><span data-stu-id="5393a-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="5393a-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="5393a-182">uniformcivilno#</span></span>
  
<span data-ttu-id="5393a-183">"/入力 id"</span><span class="sxs-lookup"><span data-stu-id="5393a-183">egn#</span></span>
  
<span data-ttu-id="5393a-184">униформгражданскиномер</span><span class="sxs-lookup"><span data-stu-id="5393a-184">униформ граждански номер</span></span>
  
<span data-ttu-id="5393a-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="5393a-185">униформ id</span></span>
  
<span data-ttu-id="5393a-186">униформграждански id</span><span class="sxs-lookup"><span data-stu-id="5393a-186">униформ граждански id</span></span>
  
<span data-ttu-id="5393a-187">униформгражданскине</span><span class="sxs-lookup"><span data-stu-id="5393a-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="5393a-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="5393a-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="5393a-189">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-189">Format</span></span>

<span data-ttu-id="5393a-190">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-191">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-191">Pattern</span></span>

<span data-ttu-id="5393a-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-192">11 digits:</span></span>
  
- <span data-ttu-id="5393a-193">ランダムに選択された10桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="5393a-194">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-195">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-195">Checksum</span></span>

<span data-ttu-id="5393a-196">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-197">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-197">Definition</span></span>

<span data-ttu-id="5393a-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-199">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-200">from `Keywords_croatia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-202">関数`Func_croatia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-203">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="5393a-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-205">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-205">tax number</span></span>
  
<span data-ttu-id="5393a-206">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-206">tax</span></span>
  
<span data-ttu-id="5393a-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-207">tax id</span></span>
  
<span data-ttu-id="5393a-208">ドーナツ</span><span class="sxs-lookup"><span data-stu-id="5393a-208">oid</span></span>
  
<span data-ttu-id="5393a-209">ドーナツ</span><span class="sxs-lookup"><span data-stu-id="5393a-209">oid#</span></span>
  
<span data-ttu-id="5393a-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="5393a-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="5393a-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="5393a-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="5393a-212">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-212">Format</span></span>

<span data-ttu-id="5393a-213">指定したパターンの8桁の数字と1文字</span><span class="sxs-lookup"><span data-stu-id="5393a-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-214">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-214">Pattern</span></span>

<span data-ttu-id="5393a-215">8桁の数字と1つの文字:</span><span class="sxs-lookup"><span data-stu-id="5393a-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="5393a-216">"0"</span><span class="sxs-lookup"><span data-stu-id="5393a-216">A "0"</span></span> 
    
- <span data-ttu-id="5393a-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-217">Seven digits</span></span>
    
- <span data-ttu-id="5393a-218">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5393a-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-219">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-219">Checksum</span></span>

<span data-ttu-id="5393a-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-221">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-221">Definition</span></span>

<span data-ttu-id="5393a-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-223">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-224">from `Keywords_cyprus_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-226">関数`Func_cyprus_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-227">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="5393a-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-229">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-229">tax number</span></span>
  
<span data-ttu-id="5393a-230">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-230">tax</span></span>
  
<span data-ttu-id="5393a-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-231">tax id</span></span>
  
<span data-ttu-id="5393a-232">税 id コード</span><span class="sxs-lookup"><span data-stu-id="5393a-232">tax identification code</span></span>
  
<span data-ttu-id="5393a-233">認め</span><span class="sxs-lookup"><span data-stu-id="5393a-233">tic</span></span>
  
<span data-ttu-id="5393a-234">認め</span><span class="sxs-lookup"><span data-stu-id="5393a-234">tic#</span></span>
  
<span data-ttu-id="5393a-235">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="5393a-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="5393a-236">φορολογικήταυτότητα</span><span class="sxs-lookup"><span data-stu-id="5393a-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="5393a-237">κωδικόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="5393a-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="5393a-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="5393a-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="5393a-239">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-239">Format</span></span>

<span data-ttu-id="5393a-240">9桁または10桁の数字 (省略可能な円記号付き)</span><span class="sxs-lookup"><span data-stu-id="5393a-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-241">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-241">Pattern</span></span>

<span data-ttu-id="5393a-242">9桁または10桁の数字で、省略可能な backslashl を指定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="5393a-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-243">Six digits</span></span> 
    
- <span data-ttu-id="5393a-244">円記号 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="5393a-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="5393a-245">3桁または4桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-246">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-246">Checksum</span></span>

<span data-ttu-id="5393a-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-248">Definition</span><span class="sxs-lookup"><span data-stu-id="5393a-248">Definition</span></span>

<span data-ttu-id="5393a-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-250">正規表現`Regex_czech_republic_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5393a-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-251">from `Keywords_czech_republic_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5393a-252">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="5393a-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-254">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-254">tax number</span></span>
  
<span data-ttu-id="5393a-255">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-255">tax</span></span>
  
<span data-ttu-id="5393a-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-256">tax id</span></span>
  
<span data-ttu-id="5393a-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="5393a-257">personal number</span></span>
  
<span data-ttu-id="5393a-258">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="5393a-258">daňové číslo</span></span>
  
<span data-ttu-id="5393a-259">osobníčíslo</span><span class="sxs-lookup"><span data-stu-id="5393a-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="5393a-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="5393a-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="5393a-261">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-261">Format</span></span>

<span data-ttu-id="5393a-262">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="5393a-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-263">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-263">Pattern</span></span>

<span data-ttu-id="5393a-264">hyphenl を含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="5393a-265">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="5393a-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="5393a-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="5393a-266">A hyphen</span></span>
    
- <span data-ttu-id="5393a-267">1桁目が誕生日の世紀に対応し、最後の桁は個人の性別に対応する4桁の数字 (男性の場合は奇数、女性の場合もあります)。</span><span class="sxs-lookup"><span data-stu-id="5393a-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-268">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-268">Checksum</span></span>

<span data-ttu-id="5393a-269">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-270">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-270">Definition</span></span>

<span data-ttu-id="5393a-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-272">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-273">from `Keywords_denmark_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-275">関数`Func_denmark_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-276">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="5393a-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-278">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-278">tax number</span></span>
  
<span data-ttu-id="5393a-279">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-279">tax</span></span>
  
<span data-ttu-id="5393a-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-280">tax id</span></span>
  
<span data-ttu-id="5393a-281">cpr 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-281">cpr number</span></span>
  
<span data-ttu-id="5393a-282">cpr</span><span class="sxs-lookup"><span data-stu-id="5393a-282">cpr#</span></span>
  
<span data-ttu-id="5393a-283">nummer の sk</span><span class="sxs-lookup"><span data-stu-id="5393a-283">skat nummer</span></span>
  
<span data-ttu-id="5393a-284">id の sk</span><span class="sxs-lookup"><span data-stu-id="5393a-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="5393a-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="5393a-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="5393a-286">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-286">Format</span></span>

<span data-ttu-id="5393a-287">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-288">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-288">Pattern</span></span>

<span data-ttu-id="5393a-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-289">11 digits:</span></span>
  
-  <span data-ttu-id="5393a-290">性別と世紀に対応する1桁の数字。奇数は男性を表し、偶数の場合は1、2は19世紀に対しては女性を示します。20世紀に3、4世紀。21世紀の場合は5、6。</span><span class="sxs-lookup"><span data-stu-id="5393a-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="5393a-291">誕生日に対応する6桁の数字 (yymmdd という)</span><span class="sxs-lookup"><span data-stu-id="5393a-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="5393a-292">同じ日付に出生地を分けるシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="5393a-293">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-294">Checksum</span></span>

<span data-ttu-id="5393a-295">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-296">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-296">Definition</span></span>

<span data-ttu-id="5393a-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-298">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-299">from `Keywords_estonia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-301">関数`Func_estonia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-302">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="5393a-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-304">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-304">tax number</span></span>
  
<span data-ttu-id="5393a-305">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-305">tax</span></span>
  
<span data-ttu-id="5393a-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-306">tax id</span></span>
  
<span data-ttu-id="5393a-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="5393a-307">personal code</span></span>
  
<span data-ttu-id="5393a-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="5393a-308">maksunumber</span></span>
  
<span data-ttu-id="5393a-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="5393a-309">maksu id</span></span>
  
<span data-ttu-id="5393a-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="5393a-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="5393a-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="5393a-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="5393a-312">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-312">Format</span></span>

<span data-ttu-id="5393a-313">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="5393a-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-314">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-314">Pattern</span></span>

<span data-ttu-id="5393a-315">数字、文字、プラス記号とマイナス記号の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="5393a-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="5393a-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-316">Six digits</span></span>
    
- <span data-ttu-id="5393a-317">プラス記号、マイナス記号、または文字 "a" (大文字小文字を区別しない) の1つ。プラス記号を1800-1899 の間に置きます。マイナス記号は、1900-1999 の間に出生することを意味します。</span><span class="sxs-lookup"><span data-stu-id="5393a-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="5393a-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-318">Three digits</span></span>
    
- <span data-ttu-id="5393a-319">1つの文字または1つの番号</span><span class="sxs-lookup"><span data-stu-id="5393a-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-320">Checksum</span></span>

<span data-ttu-id="5393a-321">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-322">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-322">Definition</span></span>

<span data-ttu-id="5393a-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-324">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-325">from `Keywords_finland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-327">関数`Func_finland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-328">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="5393a-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="5393a-330">identification number</span></span>
  
<span data-ttu-id="5393a-331">個人 id</span><span class="sxs-lookup"><span data-stu-id="5393a-331">personal id</span></span>
  
<span data-ttu-id="5393a-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-332">identity number</span></span>
  
<span data-ttu-id="5393a-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-333">finnish national id number</span></span>
  
<span data-ttu-id="5393a-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-334">personalidnumber#</span></span>
  
<span data-ttu-id="5393a-335">国別の識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-335">national identification number</span></span>
  
<span data-ttu-id="5393a-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-336">id number</span></span>
  
<span data-ttu-id="5393a-337">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-337">national id no.</span></span>
  
<span data-ttu-id="5393a-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-338">national id number</span></span>
  
<span data-ttu-id="5393a-339">id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-339">id no</span></span>
  
<span data-ttu-id="5393a-340">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="5393a-340">tunnistenumero</span></span>
  
<span data-ttu-id="5393a-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="5393a-341">henkilötunnus</span></span>
  
<span data-ttu-id="5393a-342">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="5393a-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="5393a-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="5393a-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="5393a-344">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="5393a-344">identiteetti numero</span></span>
  
<span data-ttu-id="5393a-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="5393a-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="5393a-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="5393a-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="5393a-347">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="5393a-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="5393a-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="5393a-348">tunnusnumero</span></span>
  
<span data-ttu-id="5393a-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="5393a-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="5393a-350">フランス</span><span class="sxs-lookup"><span data-stu-id="5393a-350">France</span></span>

### <a name="format"></a><span data-ttu-id="5393a-351">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-351">Format</span></span>

<span data-ttu-id="5393a-352">各ユーザーの13桁の数字、およびエンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-353">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-353">Pattern</span></span>

<span data-ttu-id="5393a-354">個人の場合は13桁。</span><span class="sxs-lookup"><span data-stu-id="5393a-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="5393a-355">0、1、2、または3である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="5393a-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-356">12 digits</span></span>
    
<span data-ttu-id="5393a-357">エンティティの9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-358">Checksum</span></span>

<span data-ttu-id="5393a-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-360">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-360">Definition</span></span>

<span data-ttu-id="5393a-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-362">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-363">from `Keywords_france_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-365">関数`Func_france_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-366">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="5393a-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-368">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-368">tax identification number</span></span>
  
<span data-ttu-id="5393a-369">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-369">tax number</span></span>
  
<span data-ttu-id="5393a-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-370">tax id</span></span>
  
<span data-ttu-id="5393a-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="5393a-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="5393a-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="5393a-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="5393a-373">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-373">Format</span></span>

<span data-ttu-id="5393a-374">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-375">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-375">Pattern</span></span>

<span data-ttu-id="5393a-376">11桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-376">11 digits :</span></span>
  
-  <span data-ttu-id="5393a-377">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-377">Ten digits</span></span> 
    
- <span data-ttu-id="5393a-378">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-379">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-379">Checksum</span></span>

<span data-ttu-id="5393a-380">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-381">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-381">Definition</span></span>

<span data-ttu-id="5393a-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-383">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-384">from `Keywords_germany_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-386">関数`Func_germany_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-387">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="5393a-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-389">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-389">tax number</span></span>
  
<span data-ttu-id="5393a-390">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-390">tax no.</span></span>
  
<span data-ttu-id="5393a-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-391">taxno#</span></span>
  
<span data-ttu-id="5393a-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-392">taxnumber#</span></span>
  
<span data-ttu-id="5393a-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-393">taxnumber</span></span>
  
<span data-ttu-id="5393a-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-394">tax id</span></span>
  
<span data-ttu-id="5393a-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-395">taxid#</span></span>
  
<span data-ttu-id="5393a-396">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-396">tax identification number</span></span>
  
<span data-ttu-id="5393a-397">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-397">tax identification no.</span></span>
  
<span data-ttu-id="5393a-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="5393a-398">steuernummer</span></span>
  
<span data-ttu-id="5393a-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="5393a-399">steuer id</span></span>
  
<span data-ttu-id="5393a-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="5393a-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="5393a-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="5393a-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="5393a-402">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-402">Format</span></span>

<span data-ttu-id="5393a-403">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-404">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-404">Pattern</span></span>

<span data-ttu-id="5393a-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-406">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-406">Checksum</span></span>

<span data-ttu-id="5393a-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-408">Definition</span><span class="sxs-lookup"><span data-stu-id="5393a-408">Definition</span></span>

<span data-ttu-id="5393a-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-410">正規表現`Regex_greece_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5393a-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-411">from `Keywords_greece_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5393a-412">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="5393a-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-414">afm</span><span class="sxs-lookup"><span data-stu-id="5393a-414">afm</span></span>
  
<span data-ttu-id="5393a-415">tin
</span><span class="sxs-lookup"><span data-stu-id="5393a-415">tin</span></span>
  
<span data-ttu-id="5393a-416">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-416">tax id no.</span></span>
  
<span data-ttu-id="5393a-417">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-417">tax id no</span></span>
  
<span data-ttu-id="5393a-418">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-418">tax identification number</span></span>
  
<span data-ttu-id="5393a-419">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-419">tax registry number</span></span>
  
<span data-ttu-id="5393a-420">納税レジストリ番号</span><span class="sxs-lookup"><span data-stu-id="5393a-420">tax registry no.</span></span>
  
<span data-ttu-id="5393a-421">afm</span><span class="sxs-lookup"><span data-stu-id="5393a-421">afm#</span></span>
  
<span data-ttu-id="5393a-422">は</span><span class="sxs-lookup"><span data-stu-id="5393a-422">tin#</span></span>
  
<span data-ttu-id="5393a-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="5393a-423">taxidno#</span></span>
  
<span data-ttu-id="5393a-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="5393a-424">taxregistryno#</span></span>
  
<span data-ttu-id="5393a-425">αριθμόςφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="5393a-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="5393a-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="5393a-426">aφμ</span></span>
  
<span data-ttu-id="5393a-427">aφμαριθμός</span><span class="sxs-lookup"><span data-stu-id="5393a-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="5393a-428">φορολογικούμητρώουνο。</span><span class="sxs-lookup"><span data-stu-id="5393a-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="5393a-429">τοναριθμόφορολογικούμητρώου</span><span class="sxs-lookup"><span data-stu-id="5393a-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="5393a-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="5393a-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="5393a-431">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-431">Format</span></span>

<span data-ttu-id="5393a-432">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-433">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-433">Pattern</span></span>

<span data-ttu-id="5393a-434">10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-434">Ten digits:</span></span>
  
-  <span data-ttu-id="5393a-435">"8" である1桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="5393a-436">日付01/01/1867 と個人の誕生日との間の日数に対応する5桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="5393a-437">同じ日に生まれた個人を区別する機会によって生成された番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="5393a-438">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-439">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-439">Checksum</span></span>

<span data-ttu-id="5393a-440">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-441">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-441">Definition</span></span>

<span data-ttu-id="5393a-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-443">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-444">from `Keywords_hungary_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-446">関数`Func_hungary_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-447">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="5393a-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-449">ハンガリーの税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="5393a-450">ハンガリー tin</span><span class="sxs-lookup"><span data-stu-id="5393a-450">hungarian tin</span></span>
  
<span data-ttu-id="5393a-451">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-451">tax id number</span></span>
  
<span data-ttu-id="5393a-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-452">vat number</span></span>
  
<span data-ttu-id="5393a-453">税務当局番号</span><span class="sxs-lookup"><span data-stu-id="5393a-453">tax authority no</span></span>
  
<span data-ttu-id="5393a-454">課税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-454">tax id tax identity number</span></span>
  
<span data-ttu-id="5393a-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-455">taxidnumber#</span></span>
  
<span data-ttu-id="5393a-456">は</span><span class="sxs-lookup"><span data-stu-id="5393a-456">tin#</span></span>
  
<span data-ttu-id="5393a-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="5393a-457">hungatiantin#</span></span>
  
<span data-ttu-id="5393a-458">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-458">tax identification no</span></span>
  
<span data-ttu-id="5393a-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="5393a-459">taxidno#</span></span>
  
<span data-ttu-id="5393a-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="5393a-460">adóazonosító szám</span></span>
  
<span data-ttu-id="5393a-461">adószám</span><span class="sxs-lookup"><span data-stu-id="5393a-461">adószám</span></span>
  
<span data-ttu-id="5393a-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="5393a-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="5393a-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="5393a-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="5393a-464">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-464">Format</span></span>

<span data-ttu-id="5393a-465">7桁の数字の後にスペースまたは区切り文字を含まない文字</span><span class="sxs-lookup"><span data-stu-id="5393a-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-466">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-466">Pattern</span></span>

<span data-ttu-id="5393a-467">7桁の数字の後に、文字を続けます。</span><span class="sxs-lookup"><span data-stu-id="5393a-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="5393a-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-468">Seven digits</span></span> 
    
- <span data-ttu-id="5393a-469">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5393a-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-470">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-470">Checksum</span></span>

<span data-ttu-id="5393a-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-472">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-472">Definition</span></span>

<span data-ttu-id="5393a-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-474">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-475">from `Keywords_ireland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-477">関数`Func_ireland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="5393a-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-480">パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="5393a-480">public service no</span></span>
  
<span data-ttu-id="5393a-481">個人用パブリックサービスいいえ</span><span class="sxs-lookup"><span data-stu-id="5393a-481">personal public service no</span></span>
  
<span data-ttu-id="5393a-482">pps no</span><span class="sxs-lookup"><span data-stu-id="5393a-482">pps no</span></span>
  
<span data-ttu-id="5393a-483">個人サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="5393a-483">personal service no</span></span>
  
<span data-ttu-id="5393a-484">pps サービスいいえ</span><span class="sxs-lookup"><span data-stu-id="5393a-484">pps service no</span></span>
  
<span data-ttu-id="5393a-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="5393a-485">ppsno#</span></span>
  
<span data-ttu-id="5393a-486">アイルランド語 (pps)</span><span class="sxs-lookup"><span data-stu-id="5393a-486">irish pps no</span></span>
  
<span data-ttu-id="5393a-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="5393a-487">publicserviceno#</span></span>
  
<span data-ttu-id="5393a-488">個人用パブリックサービス番号</span><span class="sxs-lookup"><span data-stu-id="5393a-488">personal public service number</span></span>
  
<span data-ttu-id="5393a-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="5393a-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="5393a-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="5393a-490">pps uimh</span></span>
  
<span data-ttu-id="5393a-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="5393a-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="5393a-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="5393a-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="5393a-493">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-493">Format</span></span>

<span data-ttu-id="5393a-494">指定したパターンの16桁の文字と数字</span><span class="sxs-lookup"><span data-stu-id="5393a-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-495">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-495">Pattern</span></span>

<span data-ttu-id="5393a-496">16桁の文字と数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="5393a-497">ファミリ名の最初の3つの子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="5393a-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="5393a-498">最初の名前の最初、3番目、および4番目の子音に対応する3つの文字</span><span class="sxs-lookup"><span data-stu-id="5393a-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="5393a-499">誕生年の最後の桁に対応する2桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="5393a-500">誕生日に対応する1桁の数字。文字はアルファベット順に使用されますが、a から E、H、L、M、P、R から T までの文字が使用されます (つまり、1月は a と10月は r)。</span><span class="sxs-lookup"><span data-stu-id="5393a-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="5393a-501">誕生日に対応する2桁の数字。40が男性と区別するために女性の誕生日に追加されます。</span><span class="sxs-lookup"><span data-stu-id="5393a-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="5393a-502">個人が生まれた municipality に固有のエリアコードに対応する4桁の数字。国全体のコードが外国の国に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5393a-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="5393a-503">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-504">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-504">Checksum</span></span>

<span data-ttu-id="5393a-505">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-506">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-506">Definition</span></span>

<span data-ttu-id="5393a-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-508">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-509">from `Keywords_italy_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-511">関数`Func_italy_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-512">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="5393a-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-514">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-514">tax number</span></span>
  
<span data-ttu-id="5393a-515">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-515">tax no.</span></span>
  
<span data-ttu-id="5393a-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-516">taxno#</span></span>
  
<span data-ttu-id="5393a-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-517">taxnumber#</span></span>
  
<span data-ttu-id="5393a-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-518">taxnumber</span></span>
  
<span data-ttu-id="5393a-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-519">tax id</span></span>
  
<span data-ttu-id="5393a-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-520">taxid#</span></span>
  
<span data-ttu-id="5393a-521">会計コード</span><span class="sxs-lookup"><span data-stu-id="5393a-521">fiscal code</span></span>
  
<span data-ttu-id="5393a-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="5393a-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="5393a-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="5393a-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="5393a-524">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-524">Format</span></span>

<span data-ttu-id="5393a-525">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-526">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-526">Pattern</span></span>

<span data-ttu-id="5393a-527">指定したパターンの11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="5393a-528">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="5393a-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="5393a-529">"0" が19世紀に対応する1桁の数字、"1" は20世紀に、"2" は21世紀に対応します。</span><span class="sxs-lookup"><span data-stu-id="5393a-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="5393a-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-531">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-531">Checksum</span></span>

<span data-ttu-id="5393a-532">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-533">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-533">Definition</span></span>

<span data-ttu-id="5393a-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-535">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-536">from `Keywords_latvia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-538">関数`Func_latvia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-539">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="5393a-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-541">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-541">tax number</span></span>
  
<span data-ttu-id="5393a-542">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-542">tax no.</span></span>
  
<span data-ttu-id="5393a-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-543">taxno#</span></span>
  
<span data-ttu-id="5393a-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-544">taxnumber#</span></span>
  
<span data-ttu-id="5393a-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-545">taxnumber</span></span>
  
<span data-ttu-id="5393a-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-546">tax id</span></span>
  
<span data-ttu-id="5393a-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-547">taxid#</span></span>
  
<span data-ttu-id="5393a-548">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-548">tax identification number</span></span>
  
<span data-ttu-id="5393a-549">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-549">tax identification no.</span></span>
  
<span data-ttu-id="5393a-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="5393a-550">nodokļa numurs</span></span>
  
<span data-ttu-id="5393a-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="5393a-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="5393a-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="5393a-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="5393a-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="5393a-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="5393a-554">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-554">Format</span></span>

<span data-ttu-id="5393a-555">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="5393a-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-556">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-556">Pattern</span></span>

<span data-ttu-id="5393a-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-558">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-558">Checksum</span></span>

<span data-ttu-id="5393a-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-560">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-560">Definition</span></span>

<span data-ttu-id="5393a-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-562">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-563">from `Keywords_lithuania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-565">関数`Func_lithuania_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-566">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="5393a-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-568">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-568">tax number</span></span>
  
<span data-ttu-id="5393a-569">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-569">tax no.</span></span>
  
<span data-ttu-id="5393a-570">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="5393a-570">tax no#</span></span>
  
<span data-ttu-id="5393a-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-571">taxnumber#</span></span>
  
<span data-ttu-id="5393a-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-572">taxnumber</span></span>
  
<span data-ttu-id="5393a-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-573">tax id</span></span>
  
<span data-ttu-id="5393a-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-574">taxid#</span></span>
  
<span data-ttu-id="5393a-575">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-575">tax identification number</span></span>
  
<span data-ttu-id="5393a-576">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-576">tax identification no.</span></span>
  
<span data-ttu-id="5393a-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="5393a-577">mokesčių id</span></span>
  
<span data-ttu-id="5393a-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="5393a-578">mokesčių numeris</span></span>
  
<span data-ttu-id="5393a-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="5393a-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="5393a-580">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="5393a-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="5393a-581">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-581">Format</span></span>

<span data-ttu-id="5393a-582">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="5393a-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-583">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-583">Pattern</span></span>

<span data-ttu-id="5393a-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-584">13 digits:</span></span>
  
-  <span data-ttu-id="5393a-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-585">11 digits</span></span> 
    
- <span data-ttu-id="5393a-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-587">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-587">Checksum</span></span>

<span data-ttu-id="5393a-588">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-589">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-589">Definition</span></span>

<span data-ttu-id="5393a-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-591">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-592">from `Keywords_luxemburg_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-594">関数`Func_luxemburg_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-595">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="5393a-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-597">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-597">tax number</span></span>
  
<span data-ttu-id="5393a-598">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-598">tax no.</span></span>
  
<span data-ttu-id="5393a-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-599">taxno#</span></span>
  
<span data-ttu-id="5393a-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-600">taxnumber#</span></span>
  
<span data-ttu-id="5393a-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-601">taxnumber</span></span>
  
<span data-ttu-id="5393a-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-602">tax id</span></span>
  
<span data-ttu-id="5393a-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-603">taxid#</span></span>
  
<span data-ttu-id="5393a-604">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-604">tax identification number</span></span>
  
<span data-ttu-id="5393a-605">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-605">tax identification no.</span></span>
  
<span data-ttu-id="5393a-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="5393a-606">steuernummer</span></span>
  
<span data-ttu-id="5393a-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="5393a-607">steuer id</span></span>
  
<span data-ttu-id="5393a-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="5393a-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="5393a-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="5393a-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="5393a-610">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-610">Format</span></span>

<span data-ttu-id="5393a-611">マルタ nationals の場合: 7 桁の数字と、指定したパターンの1文字</span><span class="sxs-lookup"><span data-stu-id="5393a-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="5393a-612">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-613">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-613">Pattern</span></span>

<span data-ttu-id="5393a-614">マルタ nationals: 7 桁と1文字</span><span class="sxs-lookup"><span data-stu-id="5393a-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="5393a-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-615">Seven digits</span></span> 
    
- <span data-ttu-id="5393a-616">1文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="5393a-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="5393a-617">非マルタ nationals およびマルタエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="5393a-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5393a-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-619">Checksum</span></span>

<span data-ttu-id="5393a-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-621">Definition</span><span class="sxs-lookup"><span data-stu-id="5393a-621">Definition</span></span>

<span data-ttu-id="5393a-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-623">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-624">from `Keywords_malta_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-626">関数`Func_malta_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-627">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="5393a-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-629">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-629">tax number</span></span>
  
<span data-ttu-id="5393a-630">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-630">tax no.</span></span>
  
<span data-ttu-id="5393a-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-631">taxno#</span></span>
  
<span data-ttu-id="5393a-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-632">taxnumber#</span></span>
  
<span data-ttu-id="5393a-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-633">taxnumber</span></span>
  
<span data-ttu-id="5393a-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-634">tax id</span></span>
  
<span data-ttu-id="5393a-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-635">taxid#</span></span>
  
<span data-ttu-id="5393a-636">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-636">tax identification number</span></span>
  
<span data-ttu-id="5393a-637">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-637">tax identification no.</span></span>
  
<span data-ttu-id="5393a-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="5393a-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="5393a-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="5393a-639">id tat-taxxa</span></span>
  
<span data-ttu-id="5393a-640">numru ta ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="5393a-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="5393a-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="5393a-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="5393a-642">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-642">Format</span></span>

<span data-ttu-id="5393a-643">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-644">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-644">Pattern</span></span>

<span data-ttu-id="5393a-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="5393a-646">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-646">Checksum</span></span>

<span data-ttu-id="5393a-647">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-648">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-648">Definition</span></span>

<span data-ttu-id="5393a-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-650">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-651">from `Keywords_netherlands_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-653">関数`Func_netherlands_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-654">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="5393a-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-656">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="5393a-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="5393a-657">netherlands tax identification</span></span>
  
<span data-ttu-id="5393a-658">netherland の税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="5393a-659">netherland の税 id</span><span class="sxs-lookup"><span data-stu-id="5393a-659">netherland's tax identification</span></span>
  
<span data-ttu-id="5393a-660">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-660">tax identification number</span></span>
  
<span data-ttu-id="5393a-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-661">dutch tax id</span></span>
  
<span data-ttu-id="5393a-662">オランダの税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-662">dutch tax identification number</span></span>
  
<span data-ttu-id="5393a-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-663">tax id</span></span>
  
<span data-ttu-id="5393a-664">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-664">tax id#</span></span>
  
<span data-ttu-id="5393a-665">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-665">tax number</span></span>
  
<span data-ttu-id="5393a-666">課税 no. #</span><span class="sxs-lookup"><span data-stu-id="5393a-666">tax no#</span></span>
  
<span data-ttu-id="5393a-667">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-667">tax#</span></span>
  
<span data-ttu-id="5393a-668">tin
</span><span class="sxs-lookup"><span data-stu-id="5393a-668">tin</span></span>
  
<span data-ttu-id="5393a-669">は</span><span class="sxs-lookup"><span data-stu-id="5393a-669">tin#</span></span>
  
<span data-ttu-id="5393a-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="5393a-670">netherlands tin</span></span>
  
<span data-ttu-id="5393a-671">netherland の tin</span><span class="sxs-lookup"><span data-stu-id="5393a-671">netherland's tin</span></span>
  
<span data-ttu-id="5393a-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="5393a-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="5393a-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="5393a-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="5393a-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="5393a-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="5393a-675">nederlands belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="5393a-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="5393a-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="5393a-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="5393a-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="5393a-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="5393a-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="5393a-678">btw nummer</span></span>
  
<span data-ttu-id="5393a-679">nederlandse belasting 識別子</span><span class="sxs-lookup"><span data-stu-id="5393a-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="5393a-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="5393a-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="5393a-681">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-681">Format</span></span>

<span data-ttu-id="5393a-682">スペースまたは区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-683">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-683">Pattern</span></span>

<span data-ttu-id="5393a-684">11桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-685">Checksum</span></span>

<span data-ttu-id="5393a-686">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-687">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-687">Definition</span></span>

<span data-ttu-id="5393a-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-689">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-690">from `Keywords_poland_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-692">関数`Func_poland_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-693">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="5393a-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-695">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-695">tax number</span></span>
  
<span data-ttu-id="5393a-696">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-696">tax no.</span></span>
  
<span data-ttu-id="5393a-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-697">taxno#</span></span>
  
<span data-ttu-id="5393a-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-698">taxnumber#</span></span>
  
<span data-ttu-id="5393a-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-699">taxnumber</span></span>
  
<span data-ttu-id="5393a-700">nip</span><span class="sxs-lookup"><span data-stu-id="5393a-700">nip</span></span>
  
<span data-ttu-id="5393a-701">nip #</span><span class="sxs-lookup"><span data-stu-id="5393a-701">nip#</span></span>
  
<span data-ttu-id="5393a-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-702">tax id</span></span>
  
<span data-ttu-id="5393a-703">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-703">tax id#</span></span>
  
<span data-ttu-id="5393a-704">nip id</span><span class="sxs-lookup"><span data-stu-id="5393a-704">nip id</span></span>
  
<span data-ttu-id="5393a-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="5393a-705">nip id#</span></span>
  
<span data-ttu-id="5393a-706">税識別番号</span><span class="sxs-lookup"><span data-stu-id="5393a-706">tax identification number</span></span>
  
<span data-ttu-id="5393a-707">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-707">tax identification no.</span></span>
  
<span data-ttu-id="5393a-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-708">vat number</span></span>
  
<span data-ttu-id="5393a-709">vat 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-709">vat no.</span></span>
  
<span data-ttu-id="5393a-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="5393a-710">vatno#</span></span>
  
<span data-ttu-id="5393a-711">vat id</span><span class="sxs-lookup"><span data-stu-id="5393a-711">vat id</span></span>
  
<span data-ttu-id="5393a-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="5393a-712">vat id#</span></span>
  
<span data-ttu-id="5393a-713">特定 identyfikacji podat・ wewej</span><span class="sxs-lookup"><span data-stu-id="5393a-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="5393a-714">polski 特定 identyfikacji podat・ wej</span><span class="sxs-lookup"><span data-stu-id="5393a-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="5393a-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="5393a-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="5393a-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="5393a-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="5393a-717">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-717">Format</span></span>

<span data-ttu-id="5393a-718">スペースまたは区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-719">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-719">Pattern</span></span>

<span data-ttu-id="5393a-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-721">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-721">Checksum</span></span>

<span data-ttu-id="5393a-722">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-723">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-723">Definition</span></span>

<span data-ttu-id="5393a-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-725">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-726">from `Keywords_portugal_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-728">関数`Func_portugal_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-729">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="5393a-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-731">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-731">tax number</span></span>
  
<span data-ttu-id="5393a-732">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-732">tax no.</span></span>
  
<span data-ttu-id="5393a-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-733">taxno#</span></span>
  
<span data-ttu-id="5393a-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="5393a-734">taxnumber#</span></span>
  
<span data-ttu-id="5393a-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="5393a-735">taxnumber</span></span>
  
<span data-ttu-id="5393a-736">\n\n</span><span class="sxs-lookup"><span data-stu-id="5393a-736">nif</span></span>
  
<span data-ttu-id="5393a-737">\n\n</span><span class="sxs-lookup"><span data-stu-id="5393a-737">nif#</span></span>
  
<span data-ttu-id="5393a-738">numero 会計</span><span class="sxs-lookup"><span data-stu-id="5393a-738">numero fiscal</span></span>
  
<span data-ttu-id="5393a-739">número de identificação 会計</span><span class="sxs-lookup"><span data-stu-id="5393a-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="5393a-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="5393a-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="5393a-741">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-741">Format</span></span>

<span data-ttu-id="5393a-742">13桁の数字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="5393a-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-743">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-743">Pattern</span></span>

<span data-ttu-id="5393a-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-745">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-745">Checksum</span></span>

<span data-ttu-id="5393a-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-747">Definition</span><span class="sxs-lookup"><span data-stu-id="5393a-747">Definition</span></span>

<span data-ttu-id="5393a-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-749">正規表現`Regex_romania_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5393a-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-750">from `Keywords_romania_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5393a-751">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="5393a-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-753">tax id</span></span>
  
<span data-ttu-id="5393a-754">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-754">tax id number</span></span>
  
<span data-ttu-id="5393a-755">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="5393a-755">tax file no</span></span>
  
<span data-ttu-id="5393a-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="5393a-756">tax file number</span></span>
  
<span data-ttu-id="5393a-757">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-757">tax no</span></span>
  
<span data-ttu-id="5393a-758">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-758">tax number</span></span>
  
<span data-ttu-id="5393a-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-759">taxid#</span></span>
  
<span data-ttu-id="5393a-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-760">taxno#</span></span>
  
<span data-ttu-id="5393a-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="5393a-761">id-ul taxei</span></span>
  
<span data-ttu-id="5393a-762">numărul de 識別子は fiscală</span><span class="sxs-lookup"><span data-stu-id="5393a-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="5393a-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="5393a-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="5393a-764">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-764">Format</span></span>

<span data-ttu-id="5393a-765">スペースまたは区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-766">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-766">Pattern</span></span>

<span data-ttu-id="5393a-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-768">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-768">Checksum</span></span>

<span data-ttu-id="5393a-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="5393a-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-770">Definition</span><span class="sxs-lookup"><span data-stu-id="5393a-770">Definition</span></span>

<span data-ttu-id="5393a-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-772">正規表現`Regex_slovakia_eu_tax_file_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="5393a-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-773">from `Keywords_slovakia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5393a-774">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="5393a-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-776">tax id</span></span>
  
<span data-ttu-id="5393a-777">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-777">tax id number</span></span>
  
<span data-ttu-id="5393a-778">tin id</span><span class="sxs-lookup"><span data-stu-id="5393a-778">tin id</span></span>
  
<span data-ttu-id="5393a-779">tin no</span><span class="sxs-lookup"><span data-stu-id="5393a-779">tin no</span></span>
  
<span data-ttu-id="5393a-780">スロバキア tin id</span><span class="sxs-lookup"><span data-stu-id="5393a-780">slovakian tin id</span></span>
  
<span data-ttu-id="5393a-781">tin
</span><span class="sxs-lookup"><span data-stu-id="5393a-781">tin</span></span>
  
<span data-ttu-id="5393a-782">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="5393a-782">tax file no</span></span>
  
<span data-ttu-id="5393a-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="5393a-783">tax file number</span></span>
  
<span data-ttu-id="5393a-784">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-784">tax no</span></span>
  
<span data-ttu-id="5393a-785">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-785">tax number</span></span>
  
<span data-ttu-id="5393a-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-786">taxid#</span></span>
  
<span data-ttu-id="5393a-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-787">taxno#</span></span>
  
<span data-ttu-id="5393a-788">daňové identifikačnéčíslo</span><span class="sxs-lookup"><span data-stu-id="5393a-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="5393a-789">daňovéčíslo</span><span class="sxs-lookup"><span data-stu-id="5393a-789">daňové číslo</span></span>
  
<span data-ttu-id="5393a-790">daňovéčíslo súboru</span><span class="sxs-lookup"><span data-stu-id="5393a-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="5393a-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="5393a-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="5393a-792">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-792">Format</span></span>

<span data-ttu-id="5393a-793">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-794">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-794">Pattern</span></span>

<span data-ttu-id="5393a-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-796">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-796">Checksum</span></span>

<span data-ttu-id="5393a-797">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-798">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-798">Definition</span></span>

<span data-ttu-id="5393a-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-800">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-801">from `Keywords_slovenia_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-803">関数`Func_slovenia_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-804">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="5393a-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-806">tax id</span></span>
  
<span data-ttu-id="5393a-807">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-807">tax id number</span></span>
  
<span data-ttu-id="5393a-808">tin id</span><span class="sxs-lookup"><span data-stu-id="5393a-808">tin id</span></span>
  
<span data-ttu-id="5393a-809">tin no</span><span class="sxs-lookup"><span data-stu-id="5393a-809">tin no</span></span>
  
<span data-ttu-id="5393a-810">スロベニア tin id</span><span class="sxs-lookup"><span data-stu-id="5393a-810">slovenian tin id</span></span>
  
<span data-ttu-id="5393a-811">tin
</span><span class="sxs-lookup"><span data-stu-id="5393a-811">tin</span></span>
  
<span data-ttu-id="5393a-812">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="5393a-812">tax file no</span></span>
  
<span data-ttu-id="5393a-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="5393a-813">tax file number</span></span>
  
<span data-ttu-id="5393a-814">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-814">tax no</span></span>
  
<span data-ttu-id="5393a-815">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-815">tax number</span></span>
  
<span data-ttu-id="5393a-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-816">taxid#</span></span>
  
<span data-ttu-id="5393a-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-817">taxno#</span></span>
  
<span data-ttu-id="5393a-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="5393a-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="5393a-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="5393a-819">davčna številka</span></span>
  
<span data-ttu-id="5393a-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="5393a-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="5393a-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="5393a-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="5393a-822">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-822">Format</span></span>

<span data-ttu-id="5393a-823">7桁または8桁の数字と、指定したパターンの1文字または2文字</span><span class="sxs-lookup"><span data-stu-id="5393a-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-824">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-824">Pattern</span></span>

<span data-ttu-id="5393a-825">スペインの国民 id カードを持つスペインの自然の人物:</span><span class="sxs-lookup"><span data-stu-id="5393a-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="5393a-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-826">Eight digits</span></span> 
    
- <span data-ttu-id="5393a-827">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="5393a-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="5393a-828">スペインの国民 id カードを持たない非常駐 Spaniards</span><span class="sxs-lookup"><span data-stu-id="5393a-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="5393a-829">1つの大文字の "L" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="5393a-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="5393a-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-830">Seven digits</span></span>
    
- <span data-ttu-id="5393a-831">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="5393a-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="5393a-832">Spaniards は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="5393a-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="5393a-833">1つの大文字の "K" (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="5393a-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="5393a-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-834">Seven digits</span></span> 
    
- <span data-ttu-id="5393a-835">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="5393a-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="5393a-836">Foreigner の id 番号を持つ Foreigners</span><span class="sxs-lookup"><span data-stu-id="5393a-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="5393a-837">"X"、"Y"、または "Z" (大文字と小文字を区別) の1つの大文字</span><span class="sxs-lookup"><span data-stu-id="5393a-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="5393a-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-838">Seven digits</span></span>
    
- <span data-ttu-id="5393a-839">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="5393a-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="5393a-840">Foreigner の識別番号のない Foreigners</span><span class="sxs-lookup"><span data-stu-id="5393a-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="5393a-841">1つの大文字の "M" (大文字と小文字を区別する)</span><span class="sxs-lookup"><span data-stu-id="5393a-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="5393a-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="5393a-842">Seven digits</span></span>
    
- <span data-ttu-id="5393a-843">1つの大文字 (大文字と小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="5393a-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="5393a-844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-844">Checksum</span></span>

<span data-ttu-id="5393a-845">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-846">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-846">Definition</span></span>

<span data-ttu-id="5393a-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-848">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-849">from `Keywords_spain_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-851">関数`Func_spain_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-852">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="5393a-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-854">tax id</span></span>
  
<span data-ttu-id="5393a-855">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-855">tax id number</span></span>
  
<span data-ttu-id="5393a-856">cif id</span><span class="sxs-lookup"><span data-stu-id="5393a-856">cif id</span></span>
  
<span data-ttu-id="5393a-857">cif 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-857">cif no</span></span>
  
<span data-ttu-id="5393a-858">スペインの cif id</span><span class="sxs-lookup"><span data-stu-id="5393a-858">spanish cif id</span></span>
  
<span data-ttu-id="5393a-859">cif</span><span class="sxs-lookup"><span data-stu-id="5393a-859">cif</span></span>
  
<span data-ttu-id="5393a-860">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="5393a-860">tax file no</span></span>
  
<span data-ttu-id="5393a-861">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-861">spanish cif number</span></span>
  
<span data-ttu-id="5393a-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="5393a-862">tax file number</span></span>
  
<span data-ttu-id="5393a-863">スペインの cif 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-863">spanish cif no</span></span>
  
<span data-ttu-id="5393a-864">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-864">tax no</span></span>
  
<span data-ttu-id="5393a-865">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-865">tax number</span></span>
  
<span data-ttu-id="5393a-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-866">taxid#</span></span>
  
<span data-ttu-id="5393a-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="5393a-867">taxno#</span></span>
  
<span data-ttu-id="5393a-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="5393a-868">cifid#</span></span>
  
<span data-ttu-id="5393a-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="5393a-869">spanishcifid#</span></span>
  
<span data-ttu-id="5393a-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="5393a-870">spanishcifno#</span></span>
  
<span data-ttu-id="5393a-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="5393a-871">número de contribuyente</span></span>
  
<span data-ttu-id="5393a-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="5393a-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="5393a-873">número de identificación 会計</span><span class="sxs-lookup"><span data-stu-id="5393a-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="5393a-874">cif número</span><span class="sxs-lookup"><span data-stu-id="5393a-874">cif número</span></span>
  
<span data-ttu-id="5393a-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="5393a-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="5393a-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="5393a-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="5393a-877">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-877">Format</span></span>

<span data-ttu-id="5393a-878">指定したパターンの10桁の数字と記号</span><span class="sxs-lookup"><span data-stu-id="5393a-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-879">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-879">Pattern</span></span>

<span data-ttu-id="5393a-880">10桁の数字と記号:</span><span class="sxs-lookup"><span data-stu-id="5393a-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="5393a-881">誕生日に対応する6桁の数字 (yymmdd という)</span><span class="sxs-lookup"><span data-stu-id="5393a-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="5393a-882">プラス記号、マイナス記号、または円記号</span><span class="sxs-lookup"><span data-stu-id="5393a-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="5393a-883">識別番号を一意にするための3桁の数字:</span><span class="sxs-lookup"><span data-stu-id="5393a-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="5393a-884">1990より前に発行された番号については、7桁目と8桁目の数字は、誕生日または外国出身の人物を識別します。</span><span class="sxs-lookup"><span data-stu-id="5393a-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="5393a-885">9桁の数字は、男性に対して、または女性に対して、性別を示します。</span><span class="sxs-lookup"><span data-stu-id="5393a-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="5393a-886">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="5393a-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="5393a-887">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-887">Checksum</span></span>

<span data-ttu-id="5393a-888">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-889">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-889">Definition</span></span>

<span data-ttu-id="5393a-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-891">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-892">from `Keywords_sweden_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="5393a-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-894">関数`Func_sweden_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="5393a-895">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="5393a-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-897">tax id</span></span>
  
<span data-ttu-id="5393a-898">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-898">tax id no.</span></span>
  
<span data-ttu-id="5393a-899">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-899">tax id number</span></span>
  
<span data-ttu-id="5393a-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="5393a-900">tax identification</span></span>
  
<span data-ttu-id="5393a-901">税 id #</span><span class="sxs-lookup"><span data-stu-id="5393a-901">tax identification#</span></span>
  
<span data-ttu-id="5393a-902">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-902">tax no.</span></span>
  
<span data-ttu-id="5393a-903">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-903">tax#</span></span>
  
<span data-ttu-id="5393a-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-904">taxid#</span></span>
  
<span data-ttu-id="5393a-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="5393a-905">tax file</span></span>
  
<span data-ttu-id="5393a-906">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="5393a-906">tax file no.</span></span>
  
<span data-ttu-id="5393a-907">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="5393a-907">personal id number</span></span>
  
<span data-ttu-id="5393a-908">skatt id の nummer</span><span class="sxs-lookup"><span data-stu-id="5393a-908">skatt id nummer</span></span>
  
<span data-ttu-id="5393a-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="5393a-909">skatt identifikation</span></span>
  
<span data-ttu-id="5393a-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="5393a-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="5393a-911">英国</span><span class="sxs-lookup"><span data-stu-id="5393a-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="5393a-912">形式</span><span class="sxs-lookup"><span data-stu-id="5393a-912">Format</span></span>

<span data-ttu-id="5393a-913">Unique 納税リファレンス (utr): スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="5393a-p103">国家保険番号 (NINO): 詳細については、「[機密情報の種類がどのようなものか](what-the-sensitive-information-types-look-for.md)」の「英国国立保険番号 (NINO)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5393a-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="5393a-916">パターン</span><span class="sxs-lookup"><span data-stu-id="5393a-916">Pattern</span></span>

<span data-ttu-id="5393a-917">Unique 納税リファレンス (utr):10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="5393a-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="5393a-p104">国家保険番号 (NINO): 詳細については、「[機密情報の種類がどのようなものか](what-the-sensitive-information-types-look-for.md)」の「英国国立保険番号 (NINO)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5393a-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="5393a-920">チェックサム</span><span class="sxs-lookup"><span data-stu-id="5393a-920">Checksum</span></span>

<span data-ttu-id="5393a-921">はい</span><span class="sxs-lookup"><span data-stu-id="5393a-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="5393a-922">定義</span><span class="sxs-lookup"><span data-stu-id="5393a-922">Definition</span></span>

<span data-ttu-id="5393a-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="5393a-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="5393a-924">関数`Func_uk_eu_tax_file_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="5393a-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="5393a-925">from `Keywords_uk_eu_tax_file_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="5393a-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5393a-926">キーワード</span><span class="sxs-lookup"><span data-stu-id="5393a-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="5393a-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="5393a-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="5393a-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="5393a-928">tax id</span></span>
  
<span data-ttu-id="5393a-929">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-929">tax id no.</span></span>
  
<span data-ttu-id="5393a-930">納税者番号</span><span class="sxs-lookup"><span data-stu-id="5393a-930">tax id number</span></span>
  
<span data-ttu-id="5393a-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="5393a-931">tax identification</span></span>
  
<span data-ttu-id="5393a-932">税 id #</span><span class="sxs-lookup"><span data-stu-id="5393a-932">tax identification#</span></span>
  
<span data-ttu-id="5393a-933">課税番号</span><span class="sxs-lookup"><span data-stu-id="5393a-933">tax no.</span></span>
  
<span data-ttu-id="5393a-934">申告</span><span class="sxs-lookup"><span data-stu-id="5393a-934">tax#</span></span>
  
<span data-ttu-id="5393a-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="5393a-935">taxid#</span></span>
  
<span data-ttu-id="5393a-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="5393a-936">tax file</span></span>
  
<span data-ttu-id="5393a-937">税ファイル番号</span><span class="sxs-lookup"><span data-stu-id="5393a-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5393a-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="5393a-938">See also</span></span>

[<span data-ttu-id="5393a-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="5393a-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

