---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 86be7b52aed7581fd62ab595ac2c4b63ab33aab3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217747"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="379a3-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-104">EU Driver's License Number</span></span>

<span data-ttu-id="379a3-p102">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="379a3-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="379a3-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="379a3-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="379a3-108">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-108">Format</span></span>

<span data-ttu-id="379a3-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-110">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-110">Pattern</span></span>

<span data-ttu-id="379a3-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-112">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-112">Checksum</span></span>

<span data-ttu-id="379a3-113">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-114">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-114">Definition</span></span>

<span data-ttu-id="379a3-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-117">from `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="379a3-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-118">Keywords</span></span>

<span data-ttu-id="379a3-119">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-119"></span></span>
|<span data-ttu-id="379a3-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-121">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-121">dl#</span></span>  <br/> <span data-ttu-id="379a3-122">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-122">driver license</span></span>  <br/> <span data-ttu-id="379a3-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-123">driver license number</span></span>  <br/> <span data-ttu-id="379a3-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-124">driver licence</span></span>  <br/> <span data-ttu-id="379a3-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-125">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-126">drivers license</span></span>  <br/> <span data-ttu-id="379a3-127">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-127">driver's licence</span></span>  <br/> <span data-ttu-id="379a3-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-128">driver's license</span></span>  <br/> <span data-ttu-id="379a3-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-129">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="379a3-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-131">driving license number</span></span>  <br/> <span data-ttu-id="379a3-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-132">dlno#</span></span>  <br/> <span data-ttu-id="379a3-133">futex</span><span class="sxs-lookup"><span data-stu-id="379a3-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="379a3-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="379a3-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="379a3-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="379a3-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="379a3-136">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-136">Format</span></span>

<span data-ttu-id="379a3-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-138">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-138">Pattern</span></span>

<span data-ttu-id="379a3-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-140">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-140">Checksum</span></span>

<span data-ttu-id="379a3-141">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-142">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-142">Definition</span></span>

<span data-ttu-id="379a3-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-145">from `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="379a3-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-146">Keywords</span></span>

<span data-ttu-id="379a3-147">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-147"></span></span>
|<span data-ttu-id="379a3-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-149">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-149">dl#</span></span>  <br/> <span data-ttu-id="379a3-150">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-150">driver license</span></span>  <br/> <span data-ttu-id="379a3-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-151">driver license number</span></span>  <br/> <span data-ttu-id="379a3-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-152">driver licence</span></span>  <br/> <span data-ttu-id="379a3-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-153">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-154">drivers license</span></span>  <br/> <span data-ttu-id="379a3-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-155">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-156">driver's license</span></span>  <br/> <span data-ttu-id="379a3-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-157">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-158">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-159">dlno#</span></span>  <br/> <span data-ttu-id="379a3-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="379a3-160">rijbewijs</span></span>  <br/> <span data-ttu-id="379a3-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="379a3-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="379a3-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="379a3-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="379a3-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="379a3-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="379a3-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="379a3-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="379a3-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="379a3-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="379a3-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="379a3-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="379a3-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="379a3-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="379a3-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="379a3-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="379a3-169">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-169">Format</span></span>

<span data-ttu-id="379a3-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-171">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-171">Pattern</span></span>

<span data-ttu-id="379a3-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-173">Checksum</span></span>

<span data-ttu-id="379a3-174">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-175">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-175">Definition</span></span>

<span data-ttu-id="379a3-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-178">from `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="379a3-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-179">Keywords</span></span>

<span data-ttu-id="379a3-180">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-180"></span></span>
|<span data-ttu-id="379a3-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-182">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-182">dl#</span></span>  <br/> <span data-ttu-id="379a3-183">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-183">driver license</span></span>  <br/> <span data-ttu-id="379a3-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-184">driver license number</span></span>  <br/> <span data-ttu-id="379a3-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-185">driver licence</span></span>  <br/> <span data-ttu-id="379a3-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-186">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-187">drivers license</span></span>  <br/> <span data-ttu-id="379a3-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-188">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-189">driver's license</span></span>  <br/> <span data-ttu-id="379a3-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-190">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-191">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-192">driving license number</span></span>  <br/> <span data-ttu-id="379a3-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-193">dlno#</span></span>  <br/> <span data-ttu-id="379a3-194">свидетелствозауправлениенампс</span><span class="sxs-lookup"><span data-stu-id="379a3-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="379a3-195">свидетелствозауправлениенамоторнопревозносредство</span><span class="sxs-lookup"><span data-stu-id="379a3-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="379a3-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="379a3-196">сумпс</span></span>  <br/> <span data-ttu-id="379a3-197">шофьорскакнижка</span><span class="sxs-lookup"><span data-stu-id="379a3-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="379a3-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="379a3-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="379a3-199">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-199">Format</span></span>

<span data-ttu-id="379a3-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-201">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-201">Pattern</span></span>

<span data-ttu-id="379a3-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-203">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-203">Checksum</span></span>

<span data-ttu-id="379a3-204">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-205">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-205">Definition</span></span>

<span data-ttu-id="379a3-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-208">from `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="379a3-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-209">Keywords</span></span>

<span data-ttu-id="379a3-210">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-210"></span></span>
|<span data-ttu-id="379a3-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-212">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-212">dl#</span></span>  <br/> <span data-ttu-id="379a3-213">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-213">driver license</span></span>  <br/> <span data-ttu-id="379a3-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-214">driver license number</span></span>  <br/> <span data-ttu-id="379a3-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-215">driver licence</span></span>  <br/> <span data-ttu-id="379a3-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-216">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-217">drivers license</span></span>  <br/> <span data-ttu-id="379a3-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-218">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-219">driver's license</span></span>  <br/> <span data-ttu-id="379a3-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-220">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-221">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-222">driving license number</span></span>  <br/> <span data-ttu-id="379a3-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-223">dlno#</span></span>  <br/> <span data-ttu-id="379a3-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="379a3-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="379a3-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="379a3-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="379a3-226">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-226">Format</span></span>

<span data-ttu-id="379a3-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="379a3-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-228">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-228">Pattern</span></span>

<span data-ttu-id="379a3-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-230">Checksum</span></span>

<span data-ttu-id="379a3-231">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-232">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-232">Definition</span></span>

<span data-ttu-id="379a3-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-235">from `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-236">Keywords</span></span>

<span data-ttu-id="379a3-237">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-237"></span></span>
|<span data-ttu-id="379a3-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-239">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-239">dl#</span></span>  <br/> <span data-ttu-id="379a3-240">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-240">driver license</span></span>  <br/> <span data-ttu-id="379a3-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-241">driver license number</span></span>  <br/> <span data-ttu-id="379a3-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-242">driver licence</span></span>  <br/> <span data-ttu-id="379a3-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-243">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-244">drivers license</span></span>  <br/> <span data-ttu-id="379a3-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-245">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-246">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-247">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-248">driving license number</span></span>  <br/> <span data-ttu-id="379a3-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-249">dlno#</span></span>  <br/> <span data-ttu-id="379a3-250">άδειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="379a3-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="379a3-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="379a3-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="379a3-252">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-252">Format</span></span>

<span data-ttu-id="379a3-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-254">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-254">Pattern</span></span>

<span data-ttu-id="379a3-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="379a3-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="379a3-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="379a3-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="379a3-257">A space (optional)</span></span>
    
- <span data-ttu-id="379a3-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-259">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-259">Checksum</span></span>

<span data-ttu-id="379a3-260">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-261">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-261">Definition</span></span>

<span data-ttu-id="379a3-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-264">from `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="379a3-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-265">Keywords</span></span>

<span data-ttu-id="379a3-266">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-266"></span></span>
|<span data-ttu-id="379a3-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-268">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-268">dl#</span></span>  <br/> <span data-ttu-id="379a3-269">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-269">driver license</span></span>  <br/> <span data-ttu-id="379a3-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-270">driver license number</span></span>  <br/> <span data-ttu-id="379a3-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-271">driver licence</span></span>  <br/> <span data-ttu-id="379a3-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-272">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-273">drivers license</span></span>  <br/> <span data-ttu-id="379a3-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-274">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-275">driver's license</span></span>  <br/> <span data-ttu-id="379a3-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-276">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-277">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-278">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-279">driving license number</span></span>  <br/> <span data-ttu-id="379a3-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-280">dlno#</span></span>  <br/> <span data-ttu-id="379a3-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="379a3-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="379a3-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="379a3-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="379a3-283">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-283">Format</span></span>

<span data-ttu-id="379a3-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-285">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-285">Pattern</span></span>

<span data-ttu-id="379a3-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-287">Checksum</span></span>

<span data-ttu-id="379a3-288">はい</span><span class="sxs-lookup"><span data-stu-id="379a3-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-289">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-289">Definition</span></span>

<span data-ttu-id="379a3-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-292">from `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="379a3-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-293">Keywords</span></span>

<span data-ttu-id="379a3-294">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-294"></span></span>
|<span data-ttu-id="379a3-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-296">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-296">dl#</span></span>  <br/> <span data-ttu-id="379a3-297">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-297">driver license</span></span>  <br/> <span data-ttu-id="379a3-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-298">driver license number</span></span>  <br/> <span data-ttu-id="379a3-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-299">driver licence</span></span>  <br/> <span data-ttu-id="379a3-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-300">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-301">drivers license</span></span>  <br/> <span data-ttu-id="379a3-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-302">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-303">driver's license</span></span>  <br/> <span data-ttu-id="379a3-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-304">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-305">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-306">driving license number</span></span>  <br/> <span data-ttu-id="379a3-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-307">dlno#</span></span>  <br/> <span data-ttu-id="379a3-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="379a3-308">kørekort</span></span>  <br/> <span data-ttu-id="379a3-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="379a3-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="379a3-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="379a3-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="379a3-311">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-311">Format</span></span>

<span data-ttu-id="379a3-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-313">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-313">Pattern</span></span>

<span data-ttu-id="379a3-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="379a3-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="379a3-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="379a3-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-317">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-317">Checksum</span></span>

<span data-ttu-id="379a3-318">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-319">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-319">Definition</span></span>

<span data-ttu-id="379a3-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-322">from `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-323">Keywords</span></span>

<span data-ttu-id="379a3-324">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-324"></span></span>
|<span data-ttu-id="379a3-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-326">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-326">dl#</span></span>  <br/> <span data-ttu-id="379a3-327">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-327">driver license</span></span>  <br/> <span data-ttu-id="379a3-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-328">driver license number</span></span>  <br/> <span data-ttu-id="379a3-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-329">driver license number</span></span>  <br/> <span data-ttu-id="379a3-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-330">driver licence</span></span>  <br/> <span data-ttu-id="379a3-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-331">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-332">drivers license</span></span>  <br/> <span data-ttu-id="379a3-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-333">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-334">driver's license</span></span>  <br/> <span data-ttu-id="379a3-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-335">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-336">driving license number</span></span>  <br/> <span data-ttu-id="379a3-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-337">dlno#</span></span>  <br/> <span data-ttu-id="379a3-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="379a3-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="379a3-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="379a3-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="379a3-340">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-340">Format</span></span>

<span data-ttu-id="379a3-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-342">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-342">Pattern</span></span>

<span data-ttu-id="379a3-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="379a3-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="379a3-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-344">Six digits</span></span> 
    
- <span data-ttu-id="379a3-345">ハイフン</span><span class="sxs-lookup"><span data-stu-id="379a3-345">A hyphen</span></span>
    
-  <span data-ttu-id="379a3-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="379a3-347">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-347">Checksum</span></span>

<span data-ttu-id="379a3-348">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-349">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-349">Definition</span></span>

<span data-ttu-id="379a3-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-352">from `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-353">Keywords</span></span>

<span data-ttu-id="379a3-354">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-354"></span></span>
|<span data-ttu-id="379a3-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-356">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-356">dl#</span></span>  <br/> <span data-ttu-id="379a3-357">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-357">driver license</span></span>  <br/> <span data-ttu-id="379a3-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-358">driver license number</span></span>  <br/> <span data-ttu-id="379a3-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-359">driver licence</span></span>  <br/> <span data-ttu-id="379a3-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-360">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-361">drivers license</span></span>  <br/> <span data-ttu-id="379a3-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-362">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-363">driver's license</span></span>  <br/> <span data-ttu-id="379a3-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-364">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-365">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-366">driving license number</span></span>  <br/> <span data-ttu-id="379a3-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-367">dlno#</span></span>  <br/> <span data-ttu-id="379a3-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="379a3-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="379a3-369">フランス</span><span class="sxs-lookup"><span data-stu-id="379a3-369">France</span></span>

<span data-ttu-id="379a3-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="379a3-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="379a3-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="379a3-371">Germany</span></span>

<span data-ttu-id="379a3-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="379a3-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="379a3-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="379a3-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="379a3-374">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-374">Format</span></span>

<span data-ttu-id="379a3-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-376">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-376">Pattern</span></span>

 <span data-ttu-id="379a3-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="379a3-378">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-378">Checksum</span></span>

<span data-ttu-id="379a3-379">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-380">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-380">Definition</span></span>

<span data-ttu-id="379a3-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-383">from `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-384">Keywords</span></span>

<span data-ttu-id="379a3-385">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-385"></span></span>
|<span data-ttu-id="379a3-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-387">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="379a3-387">dlL#</span></span>  <br/> <span data-ttu-id="379a3-388">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-388">driver license</span></span>  <br/> <span data-ttu-id="379a3-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-389">driver license number</span></span>  <br/> <span data-ttu-id="379a3-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-390">driver licence</span></span>  <br/> <span data-ttu-id="379a3-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-391">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-392">drivers license</span></span>  <br/> <span data-ttu-id="379a3-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-393">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-394">driver's license</span></span>  <br/> <span data-ttu-id="379a3-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-395">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-396">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-397">driving license number</span></span>  <br/> <span data-ttu-id="379a3-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-398">dlno#</span></span>  <br/> <span data-ttu-id="379a3-399">δειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="379a3-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="379a3-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="379a3-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="379a3-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="379a3-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="379a3-402">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-402">Format</span></span>

<span data-ttu-id="379a3-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-404">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-404">Pattern</span></span>

<span data-ttu-id="379a3-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="379a3-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="379a3-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="379a3-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-408">Checksum</span></span>

<span data-ttu-id="379a3-409">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-410">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-410">Definition</span></span>

<span data-ttu-id="379a3-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-413">from `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-414">Keywords</span></span>

<span data-ttu-id="379a3-415">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-415"></span></span>
|<span data-ttu-id="379a3-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-417">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-417">dl#</span></span>  <br/> <span data-ttu-id="379a3-418">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-418">driver license</span></span>  <br/> <span data-ttu-id="379a3-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-419">driver license number</span></span>  <br/> <span data-ttu-id="379a3-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-420">driver licence</span></span>  <br/> <span data-ttu-id="379a3-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-421">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-422">drivers license</span></span>  <br/> <span data-ttu-id="379a3-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-423">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-424">driver's license</span></span>  <br/> <span data-ttu-id="379a3-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-425">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-426">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-427">driving license number</span></span>  <br/> <span data-ttu-id="379a3-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-428">dlno#</span></span>  <br/> <span data-ttu-id="379a3-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="379a3-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="379a3-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="379a3-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="379a3-431">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-431">Format</span></span>

<span data-ttu-id="379a3-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="379a3-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-433">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-433">Pattern</span></span>

<span data-ttu-id="379a3-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="379a3-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="379a3-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-435">Six digits</span></span>
    
- <span data-ttu-id="379a3-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-437">Checksum</span></span>

<span data-ttu-id="379a3-438">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-439">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-439">Definition</span></span>

<span data-ttu-id="379a3-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-442">from `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-443">Keywords</span></span>

<span data-ttu-id="379a3-444">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-444"></span></span>
|<span data-ttu-id="379a3-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-446">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-446">dl#</span></span>  <br/> <span data-ttu-id="379a3-447">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-447">driver license</span></span>  <br/> <span data-ttu-id="379a3-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-448">driver license number</span></span>  <br/> <span data-ttu-id="379a3-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-449">driver licence</span></span>  <br/> <span data-ttu-id="379a3-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-450">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-451">drivers license</span></span>  <br/> <span data-ttu-id="379a3-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-452">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-453">driver's license</span></span>  <br/> <span data-ttu-id="379a3-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-454">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-455">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-456">driving license number</span></span>  <br/> <span data-ttu-id="379a3-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-457">dlno#</span></span>  <br/> <span data-ttu-id="379a3-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="379a3-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="379a3-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="379a3-459">Italy</span></span>

<span data-ttu-id="379a3-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="379a3-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="379a3-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="379a3-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="379a3-462">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-462">Format</span></span>

<span data-ttu-id="379a3-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-464">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-464">Pattern</span></span>

<span data-ttu-id="379a3-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="379a3-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="379a3-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="379a3-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-468">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-468">Checksum</span></span>

<span data-ttu-id="379a3-469">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-470">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-470">Definition</span></span>

<span data-ttu-id="379a3-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-473">from `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-474">Keywords</span></span>

<span data-ttu-id="379a3-475">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-475"></span></span>
|<span data-ttu-id="379a3-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-477">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-477">dl#</span></span>  <br/> <span data-ttu-id="379a3-478">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-478">driver license</span></span>  <br/> <span data-ttu-id="379a3-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-479">driver license number</span></span>  <br/> <span data-ttu-id="379a3-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-480">driver licence</span></span>  <br/> <span data-ttu-id="379a3-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-481">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-482">drivers license</span></span>  <br/> <span data-ttu-id="379a3-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-483">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-484">driver's license</span></span>  <br/> <span data-ttu-id="379a3-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-485">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-486">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-487">driving license number</span></span>  <br/> <span data-ttu-id="379a3-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-488">dlno#</span></span>  <br/> <span data-ttu-id="379a3-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="379a3-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="379a3-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="379a3-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="379a3-491">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-491">Format</span></span>

<span data-ttu-id="379a3-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-493">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-493">Pattern</span></span>

 <span data-ttu-id="379a3-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="379a3-495">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-495">Checksum</span></span>

<span data-ttu-id="379a3-496">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-497">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-497">Definition</span></span>

<span data-ttu-id="379a3-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-500">from `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-501">Keywords</span></span>

<span data-ttu-id="379a3-502">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-502"></span></span>
|<span data-ttu-id="379a3-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-504">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-504">dl#</span></span>  <br/> <span data-ttu-id="379a3-505">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-505">driver license</span></span>  <br/> <span data-ttu-id="379a3-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-506">driver license number</span></span>  <br/> <span data-ttu-id="379a3-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-507">driver licence</span></span>  <br/> <span data-ttu-id="379a3-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-508">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-509">drivers license</span></span>  <br/> <span data-ttu-id="379a3-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-510">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-511">driver's license</span></span>  <br/> <span data-ttu-id="379a3-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-512">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-513">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-514">driving license number</span></span>  <br/> <span data-ttu-id="379a3-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-515">dlno#</span></span>  <br/> <span data-ttu-id="379a3-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="379a3-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="379a3-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="379a3-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="379a3-518">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-518">Format</span></span>

<span data-ttu-id="379a3-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-520">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-520">Pattern</span></span>

 <span data-ttu-id="379a3-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="379a3-522">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-522">Checksum</span></span>

<span data-ttu-id="379a3-523">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-524">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-524">Definition</span></span>

<span data-ttu-id="379a3-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-527">from `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-528">Keywords</span></span>

<span data-ttu-id="379a3-529">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-529"></span></span>
|<span data-ttu-id="379a3-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-531">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-531">dl#</span></span>  <br/> <span data-ttu-id="379a3-532">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-532">driver license</span></span>  <br/> <span data-ttu-id="379a3-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-533">driver license number</span></span>  <br/> <span data-ttu-id="379a3-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-534">driver licence</span></span>  <br/> <span data-ttu-id="379a3-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-535">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-536">drivers license</span></span>  <br/> <span data-ttu-id="379a3-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-537">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-538">driver's license</span></span>  <br/> <span data-ttu-id="379a3-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-539">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-540">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-541">driving license number</span></span>  <br/> <span data-ttu-id="379a3-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-542">dlno#</span></span>  <br/> <span data-ttu-id="379a3-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="379a3-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="379a3-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="379a3-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="379a3-545">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-545">Format</span></span>

<span data-ttu-id="379a3-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="379a3-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-547">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-547">Pattern</span></span>

<span data-ttu-id="379a3-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="379a3-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="379a3-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="379a3-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="379a3-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="379a3-550">A space (optional)</span></span>
    
- <span data-ttu-id="379a3-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-551">Three digits</span></span>
    
- <span data-ttu-id="379a3-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="379a3-552">A space (optional)</span></span>
    
- <span data-ttu-id="379a3-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-554">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-554">Checksum</span></span>

<span data-ttu-id="379a3-555">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-556">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-556">Definition</span></span>

<span data-ttu-id="379a3-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-559">from `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-560">Keywords</span></span>

<span data-ttu-id="379a3-561">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-561"></span></span>
|<span data-ttu-id="379a3-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-563">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-563">dl#</span></span>  <br/> <span data-ttu-id="379a3-564">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-564">driver license</span></span>  <br/> <span data-ttu-id="379a3-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-565">driver license number</span></span>  <br/> <span data-ttu-id="379a3-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-566">driver licence</span></span>  <br/> <span data-ttu-id="379a3-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-567">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-568">drivers license</span></span>  <br/> <span data-ttu-id="379a3-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-569">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-570">driver's license</span></span>  <br/> <span data-ttu-id="379a3-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-571">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-572">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-573">driving license number</span></span>  <br/> <span data-ttu-id="379a3-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-574">dlno#</span></span>  <br/> <span data-ttu-id="379a3-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="379a3-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="379a3-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="379a3-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="379a3-577">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-577">Format</span></span>

<span data-ttu-id="379a3-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-579">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-579">Pattern</span></span>

<span data-ttu-id="379a3-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-581">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-581">Checksum</span></span>

<span data-ttu-id="379a3-582">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-583">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-583">Definition</span></span>

<span data-ttu-id="379a3-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-586">from `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-587">Keywords</span></span>

<span data-ttu-id="379a3-588">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-588"></span></span>
|<span data-ttu-id="379a3-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-590">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-590">dl#</span></span>  <br/> <span data-ttu-id="379a3-591">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-591">driver license</span></span>  <br/> <span data-ttu-id="379a3-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-592">driver license number</span></span>  <br/> <span data-ttu-id="379a3-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-593">driver licence</span></span>  <br/> <span data-ttu-id="379a3-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-594">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-595">drivers license</span></span>  <br/> <span data-ttu-id="379a3-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-596">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-597">driver's license</span></span>  <br/> <span data-ttu-id="379a3-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-598">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-599">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-600">driving license number</span></span>  <br/> <span data-ttu-id="379a3-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-601">dlno#</span></span>  <br/> <span data-ttu-id="379a3-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="379a3-602">permis de conduire</span></span>  <br/> <span data-ttu-id="379a3-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="379a3-603">rijbewijs</span></span>  <br/> <span data-ttu-id="379a3-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="379a3-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="379a3-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="379a3-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="379a3-606">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-606">Format</span></span>

<span data-ttu-id="379a3-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-608">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-608">Pattern</span></span>

<span data-ttu-id="379a3-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="379a3-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="379a3-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-610">Five digits</span></span> 
    
- <span data-ttu-id="379a3-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="379a3-611">A forward slash</span></span>
    
- <span data-ttu-id="379a3-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-612">Two digits</span></span>
    
- <span data-ttu-id="379a3-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="379a3-613">A forward slash</span></span>
    
- <span data-ttu-id="379a3-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-615">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-615">Checksum</span></span>

<span data-ttu-id="379a3-616">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-617">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-617">Definition</span></span>

<span data-ttu-id="379a3-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-620">from `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-621">Keywords</span></span>

<span data-ttu-id="379a3-622">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-622"></span></span>
|<span data-ttu-id="379a3-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-624">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-624">dl#</span></span>  <br/> <span data-ttu-id="379a3-625">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-625">driver license</span></span>  <br/> <span data-ttu-id="379a3-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-626">driver license number</span></span>  <br/> <span data-ttu-id="379a3-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-627">driver licence</span></span>  <br/> <span data-ttu-id="379a3-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-628">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-629">drivers license</span></span>  <br/> <span data-ttu-id="379a3-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-630">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-631">driver's license</span></span>  <br/> <span data-ttu-id="379a3-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-632">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-633">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-634">driving license number</span></span>  <br/> <span data-ttu-id="379a3-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-635">dlno#</span></span>  <br/> <span data-ttu-id="379a3-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="379a3-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="379a3-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="379a3-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="379a3-638">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-638">Format</span></span>

<span data-ttu-id="379a3-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-640">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-640">Pattern</span></span>

<span data-ttu-id="379a3-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="379a3-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="379a3-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="379a3-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="379a3-643">A hyphen</span></span>
    
- <span data-ttu-id="379a3-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-644">Six digits</span></span>
    
- <span data-ttu-id="379a3-645">スペース</span><span class="sxs-lookup"><span data-stu-id="379a3-645">A space</span></span>
    
- <span data-ttu-id="379a3-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-647">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-647">Checksum</span></span>

<span data-ttu-id="379a3-648">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-649">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-649">Definition</span></span>

<span data-ttu-id="379a3-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-652">from `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-653">Keywords</span></span>

<span data-ttu-id="379a3-654">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-654"></span></span>
|<span data-ttu-id="379a3-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-656">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-656">dl#</span></span>  <br/> <span data-ttu-id="379a3-657">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-657">driver license</span></span>  <br/> <span data-ttu-id="379a3-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-658">driver license number</span></span>  <br/> <span data-ttu-id="379a3-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-659">driver licence</span></span>  <br/> <span data-ttu-id="379a3-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-660">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-661">drivers license</span></span>  <br/> <span data-ttu-id="379a3-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-662">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-663">driver's license</span></span>  <br/> <span data-ttu-id="379a3-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-664">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-665">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-666">driving license number</span></span>  <br/> <span data-ttu-id="379a3-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-667">dlno#</span></span>  <br/> <span data-ttu-id="379a3-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="379a3-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="379a3-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="379a3-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="379a3-670">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-670">Format</span></span>

<span data-ttu-id="379a3-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-672">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-672">Pattern</span></span>

<span data-ttu-id="379a3-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="379a3-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="379a3-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="379a3-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="379a3-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-676">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-676">Checksum</span></span>

<span data-ttu-id="379a3-677">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-678">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-678">Definition</span></span>

<span data-ttu-id="379a3-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-681">from `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-682">Keywords</span></span>

<span data-ttu-id="379a3-683">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-683"></span></span>
|<span data-ttu-id="379a3-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-685">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-685">dl#</span></span>  <br/> <span data-ttu-id="379a3-686">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-686">driver license</span></span>  <br/> <span data-ttu-id="379a3-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-687">driver license number</span></span>  <br/> <span data-ttu-id="379a3-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-688">driver licence</span></span>  <br/> <span data-ttu-id="379a3-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-689">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-690">drivers license</span></span>  <br/> <span data-ttu-id="379a3-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-691">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-692">driver's license</span></span>  <br/> <span data-ttu-id="379a3-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-693">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-694">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-695">driving license number</span></span>  <br/> <span data-ttu-id="379a3-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-696">dlno#</span></span>  <br/> <span data-ttu-id="379a3-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="379a3-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="379a3-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="379a3-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="379a3-699">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-699">Format</span></span>

<span data-ttu-id="379a3-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-701">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-701">Pattern</span></span>

<span data-ttu-id="379a3-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="379a3-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="379a3-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="379a3-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="379a3-705">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-705">Checksum</span></span>

<span data-ttu-id="379a3-706">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-707">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-707">Definition</span></span>

<span data-ttu-id="379a3-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-710">from `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-711">Keywords</span></span>

<span data-ttu-id="379a3-712">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-712"></span></span>
|<span data-ttu-id="379a3-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-714">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-714">dl#</span></span>  <br/> <span data-ttu-id="379a3-715">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-715">driver license</span></span>  <br/> <span data-ttu-id="379a3-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-716">driver license number</span></span>  <br/> <span data-ttu-id="379a3-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-717">driver licence</span></span>  <br/> <span data-ttu-id="379a3-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-718">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-719">drivers license</span></span>  <br/> <span data-ttu-id="379a3-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-720">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-721">driver's license</span></span>  <br/> <span data-ttu-id="379a3-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-722">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-723">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-724">driving license number</span></span>  <br/> <span data-ttu-id="379a3-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-725">dlno#</span></span>  <br/> <span data-ttu-id="379a3-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="379a3-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="379a3-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="379a3-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="379a3-728">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-728">Format</span></span>

<span data-ttu-id="379a3-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-730">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-730">Pattern</span></span>

<span data-ttu-id="379a3-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="379a3-732">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-732">Checksum</span></span>

<span data-ttu-id="379a3-733">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-734">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-734">Definition</span></span>

<span data-ttu-id="379a3-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-737">from `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-738">Keywords</span></span>

<span data-ttu-id="379a3-739">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-739"></span></span>
|<span data-ttu-id="379a3-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-741">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-741">dl#</span></span>  <br/> <span data-ttu-id="379a3-742">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-742">driver license</span></span>  <br/> <span data-ttu-id="379a3-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-743">driver license number</span></span>  <br/> <span data-ttu-id="379a3-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-744">driver licence</span></span>  <br/> <span data-ttu-id="379a3-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-745">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-746">drivers license</span></span>  <br/> <span data-ttu-id="379a3-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-747">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-748">driver's license</span></span>  <br/> <span data-ttu-id="379a3-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-749">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-750">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-751">driving license number</span></span>  <br/> <span data-ttu-id="379a3-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-752">dlno#</span></span>  <br/> <span data-ttu-id="379a3-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="379a3-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="379a3-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="379a3-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="379a3-755">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-755">Format</span></span>

<span data-ttu-id="379a3-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="379a3-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-757">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-757">Pattern</span></span>

<span data-ttu-id="379a3-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="379a3-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="379a3-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-759">Eight digits</span></span> 
    
- <span data-ttu-id="379a3-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="379a3-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-761">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-761">Checksum</span></span>

<span data-ttu-id="379a3-762">はい</span><span class="sxs-lookup"><span data-stu-id="379a3-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-763">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-763">Definition</span></span>

<span data-ttu-id="379a3-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="379a3-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-766">from `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="379a3-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-767">Keywords</span></span>

<span data-ttu-id="379a3-768">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-768"></span></span>
|<span data-ttu-id="379a3-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-770">dlno#</span></span>  <br/> <span data-ttu-id="379a3-771">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-771">dl#</span></span>  <br/> <span data-ttu-id="379a3-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-772">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-773">driver licence</span></span>  <br/> <span data-ttu-id="379a3-774">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-774">driver license</span></span>  <br/> <span data-ttu-id="379a3-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-775">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-776">drivers license</span></span>  <br/> <span data-ttu-id="379a3-777">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-777">driver's licence</span></span>  <br/> <span data-ttu-id="379a3-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-778">driver's license</span></span>  <br/> <span data-ttu-id="379a3-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="379a3-779">driving licence</span></span>  <br/> <span data-ttu-id="379a3-780">ライセンスの駆動</span><span class="sxs-lookup"><span data-stu-id="379a3-780">driving license</span></span>  <br/> <span data-ttu-id="379a3-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-781">driver licence number</span></span>  <br/> <span data-ttu-id="379a3-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-782">driver license number</span></span>  <br/> <span data-ttu-id="379a3-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-783">drivers licence number</span></span>  <br/> <span data-ttu-id="379a3-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-784">drivers license number</span></span>  <br/> <span data-ttu-id="379a3-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-785">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-786">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="379a3-787">driving licence number</span></span>  <br/> <span data-ttu-id="379a3-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-788">driving license number</span></span>  <br/> <span data-ttu-id="379a3-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="379a3-789">driving permit</span></span>  <br/> <span data-ttu-id="379a3-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="379a3-790">driving permit number</span></span>  <br/> <span data-ttu-id="379a3-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="379a3-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="379a3-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="379a3-792">permiso conducción</span></span>  <br/> <span data-ttu-id="379a3-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="379a3-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="379a3-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="379a3-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-796">licencia conducir</span></span>  <br/> <span data-ttu-id="379a3-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="379a3-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="379a3-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="379a3-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-800">permiso conducir</span></span>  <br/> <span data-ttu-id="379a3-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="379a3-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="379a3-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="379a3-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="379a3-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="379a3-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="379a3-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="379a3-805">形式</span><span class="sxs-lookup"><span data-stu-id="379a3-805">Format</span></span>

<span data-ttu-id="379a3-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="379a3-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="379a3-807">パターン</span><span class="sxs-lookup"><span data-stu-id="379a3-807">Pattern</span></span>

<span data-ttu-id="379a3-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="379a3-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="379a3-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-809">Six digits</span></span> 
    
- <span data-ttu-id="379a3-810">ハイフン</span><span class="sxs-lookup"><span data-stu-id="379a3-810">A hyphen</span></span>
    
- <span data-ttu-id="379a3-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="379a3-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="379a3-812">チェックサム</span><span class="sxs-lookup"><span data-stu-id="379a3-812">Checksum</span></span>

<span data-ttu-id="379a3-813">なし</span><span class="sxs-lookup"><span data-stu-id="379a3-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="379a3-814">定義</span><span class="sxs-lookup"><span data-stu-id="379a3-814">Definition</span></span>

<span data-ttu-id="379a3-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="379a3-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="379a3-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="379a3-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="379a3-817">from `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="379a3-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="379a3-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="379a3-818">Keywords</span></span>

<span data-ttu-id="379a3-819">| |</span><span class="sxs-lookup"><span data-stu-id="379a3-819"></span></span>
|<span data-ttu-id="379a3-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="379a3-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="379a3-821">dl#</span><span class="sxs-lookup"><span data-stu-id="379a3-821">dl#</span></span>  <br/> <span data-ttu-id="379a3-822">driver license</span><span class="sxs-lookup"><span data-stu-id="379a3-822">driver license</span></span>  <br/> <span data-ttu-id="379a3-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-823">driver license number</span></span>  <br/> <span data-ttu-id="379a3-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="379a3-824">driver licence</span></span>  <br/> <span data-ttu-id="379a3-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="379a3-825">drivers lic.</span></span>  <br/> <span data-ttu-id="379a3-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="379a3-826">drivers license</span></span>  <br/> <span data-ttu-id="379a3-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="379a3-827">drivers licence</span></span>  <br/> <span data-ttu-id="379a3-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="379a3-828">driver's license</span></span>  <br/> <span data-ttu-id="379a3-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-829">driver's license number</span></span>  <br/> <span data-ttu-id="379a3-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="379a3-830">driver's licence number</span></span>  <br/> <span data-ttu-id="379a3-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="379a3-831">driving license number</span></span>  <br/> <span data-ttu-id="379a3-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="379a3-832">dlno#</span></span>  <br/> <span data-ttu-id="379a3-833">körkort</span><span class="sxs-lookup"><span data-stu-id="379a3-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="379a3-834">英国</span><span class="sxs-lookup"><span data-stu-id="379a3-834">UK</span></span>

<span data-ttu-id="379a3-p103">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「英国運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="379a3-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="379a3-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="379a3-837">See also</span></span>

[<span data-ttu-id="379a3-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="379a3-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

