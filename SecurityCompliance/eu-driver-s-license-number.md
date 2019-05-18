---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152979"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="33f26-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-104">EU Driver's License Number</span></span>

<span data-ttu-id="33f26-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="33f26-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="33f26-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="33f26-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="33f26-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="33f26-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="33f26-108">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-108">Format</span></span>

<span data-ttu-id="33f26-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-110">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-110">Pattern</span></span>

<span data-ttu-id="33f26-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-112">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-112">Checksum</span></span>

<span data-ttu-id="33f26-113">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-114">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-114">Definition</span></span>

<span data-ttu-id="33f26-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-117">From `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="33f26-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-118">Keywords</span></span>

<span data-ttu-id="33f26-119">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-119"></span></span>
|<span data-ttu-id="33f26-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-121">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-121">dl#</span></span>  <br/> <span data-ttu-id="33f26-122">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-122">driver license</span></span>  <br/> <span data-ttu-id="33f26-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-123">driver license number</span></span>  <br/> <span data-ttu-id="33f26-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-124">driver licence</span></span>  <br/> <span data-ttu-id="33f26-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-125">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-126">drivers license</span></span>  <br/> <span data-ttu-id="33f26-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="33f26-127">driver's licence</span></span>  <br/> <span data-ttu-id="33f26-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-128">driver's license</span></span>  <br/> <span data-ttu-id="33f26-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-129">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="33f26-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-131">driving license number</span></span>  <br/> <span data-ttu-id="33f26-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-132">dlno#</span></span>  <br/> <span data-ttu-id="33f26-133">futex</span><span class="sxs-lookup"><span data-stu-id="33f26-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="33f26-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="33f26-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="33f26-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="33f26-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="33f26-136">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-136">Format</span></span>

<span data-ttu-id="33f26-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-138">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-138">Pattern</span></span>

<span data-ttu-id="33f26-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-140">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-140">Checksum</span></span>

<span data-ttu-id="33f26-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-142">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-142">Definition</span></span>

<span data-ttu-id="33f26-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-145">From `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="33f26-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-146">Keywords</span></span>

<span data-ttu-id="33f26-147">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-147"></span></span>
|<span data-ttu-id="33f26-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-149">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-149">dl#</span></span>  <br/> <span data-ttu-id="33f26-150">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-150">driver license</span></span>  <br/> <span data-ttu-id="33f26-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-151">driver license number</span></span>  <br/> <span data-ttu-id="33f26-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-152">driver licence</span></span>  <br/> <span data-ttu-id="33f26-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-153">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-154">drivers license</span></span>  <br/> <span data-ttu-id="33f26-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-155">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-156">driver's license</span></span>  <br/> <span data-ttu-id="33f26-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-157">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-158">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-159">dlno#</span></span>  <br/> <span data-ttu-id="33f26-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="33f26-160">rijbewijs</span></span>  <br/> <span data-ttu-id="33f26-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="33f26-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="33f26-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="33f26-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="33f26-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="33f26-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="33f26-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="33f26-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="33f26-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="33f26-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="33f26-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="33f26-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="33f26-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="33f26-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="33f26-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="33f26-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="33f26-169">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-169">Format</span></span>

<span data-ttu-id="33f26-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-171">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-171">Pattern</span></span>

<span data-ttu-id="33f26-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-173">Checksum</span></span>

<span data-ttu-id="33f26-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-175">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-175">Definition</span></span>

<span data-ttu-id="33f26-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-178">From `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="33f26-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-179">Keywords</span></span>

<span data-ttu-id="33f26-180">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-180"></span></span>
|<span data-ttu-id="33f26-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-182">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-182">dl#</span></span>  <br/> <span data-ttu-id="33f26-183">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-183">driver license</span></span>  <br/> <span data-ttu-id="33f26-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-184">driver license number</span></span>  <br/> <span data-ttu-id="33f26-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-185">driver licence</span></span>  <br/> <span data-ttu-id="33f26-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-186">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-187">drivers license</span></span>  <br/> <span data-ttu-id="33f26-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-188">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-189">driver's license</span></span>  <br/> <span data-ttu-id="33f26-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-190">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-191">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-192">driving license number</span></span>  <br/> <span data-ttu-id="33f26-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-193">dlno#</span></span>  <br/> <span data-ttu-id="33f26-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="33f26-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="33f26-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="33f26-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="33f26-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="33f26-196">сумпс</span></span>  <br/> <span data-ttu-id="33f26-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="33f26-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="33f26-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="33f26-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="33f26-199">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-199">Format</span></span>

<span data-ttu-id="33f26-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-201">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-201">Pattern</span></span>

<span data-ttu-id="33f26-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-203">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-203">Checksum</span></span>

<span data-ttu-id="33f26-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-205">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-205">Definition</span></span>

<span data-ttu-id="33f26-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-208">From `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="33f26-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-209">Keywords</span></span>

<span data-ttu-id="33f26-210">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-210"></span></span>
|<span data-ttu-id="33f26-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-212">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-212">dl#</span></span>  <br/> <span data-ttu-id="33f26-213">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-213">driver license</span></span>  <br/> <span data-ttu-id="33f26-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-214">driver license number</span></span>  <br/> <span data-ttu-id="33f26-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-215">driver licence</span></span>  <br/> <span data-ttu-id="33f26-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-216">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-217">drivers license</span></span>  <br/> <span data-ttu-id="33f26-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-218">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-219">driver's license</span></span>  <br/> <span data-ttu-id="33f26-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-220">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-221">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-222">driving license number</span></span>  <br/> <span data-ttu-id="33f26-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-223">dlno#</span></span>  <br/> <span data-ttu-id="33f26-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="33f26-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="33f26-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="33f26-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="33f26-226">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-226">Format</span></span>

<span data-ttu-id="33f26-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="33f26-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-228">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-228">Pattern</span></span>

<span data-ttu-id="33f26-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-230">Checksum</span></span>

<span data-ttu-id="33f26-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-232">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-232">Definition</span></span>

<span data-ttu-id="33f26-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-235">From `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-236">Keywords</span></span>

<span data-ttu-id="33f26-237">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-237"></span></span>
|<span data-ttu-id="33f26-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-239">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-239">dl#</span></span>  <br/> <span data-ttu-id="33f26-240">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-240">driver license</span></span>  <br/> <span data-ttu-id="33f26-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-241">driver license number</span></span>  <br/> <span data-ttu-id="33f26-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-242">driver licence</span></span>  <br/> <span data-ttu-id="33f26-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-243">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-244">drivers license</span></span>  <br/> <span data-ttu-id="33f26-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-245">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-246">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-247">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-248">driving license number</span></span>  <br/> <span data-ttu-id="33f26-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-249">dlno#</span></span>  <br/> <span data-ttu-id="33f26-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="33f26-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="33f26-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="33f26-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="33f26-252">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-252">Format</span></span>

<span data-ttu-id="33f26-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-254">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-254">Pattern</span></span>

<span data-ttu-id="33f26-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="33f26-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="33f26-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="33f26-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="33f26-257">A space (optional)</span></span>
    
- <span data-ttu-id="33f26-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-259">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-259">Checksum</span></span>

<span data-ttu-id="33f26-260">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-261">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-261">Definition</span></span>

<span data-ttu-id="33f26-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-264">From `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="33f26-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-265">Keywords</span></span>

<span data-ttu-id="33f26-266">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-266"></span></span>
|<span data-ttu-id="33f26-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-268">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-268">dl#</span></span>  <br/> <span data-ttu-id="33f26-269">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-269">driver license</span></span>  <br/> <span data-ttu-id="33f26-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-270">driver license number</span></span>  <br/> <span data-ttu-id="33f26-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-271">driver licence</span></span>  <br/> <span data-ttu-id="33f26-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-272">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-273">drivers license</span></span>  <br/> <span data-ttu-id="33f26-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-274">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-275">driver's license</span></span>  <br/> <span data-ttu-id="33f26-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-276">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-277">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-278">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-279">driving license number</span></span>  <br/> <span data-ttu-id="33f26-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-280">dlno#</span></span>  <br/> <span data-ttu-id="33f26-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="33f26-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="33f26-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="33f26-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="33f26-283">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-283">Format</span></span>

<span data-ttu-id="33f26-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-285">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-285">Pattern</span></span>

<span data-ttu-id="33f26-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-287">Checksum</span></span>

<span data-ttu-id="33f26-288">はい</span><span class="sxs-lookup"><span data-stu-id="33f26-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-289">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-289">Definition</span></span>

<span data-ttu-id="33f26-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-292">From `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="33f26-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-293">Keywords</span></span>

<span data-ttu-id="33f26-294">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-294"></span></span>
|<span data-ttu-id="33f26-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-296">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-296">dl#</span></span>  <br/> <span data-ttu-id="33f26-297">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-297">driver license</span></span>  <br/> <span data-ttu-id="33f26-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-298">driver license number</span></span>  <br/> <span data-ttu-id="33f26-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-299">driver licence</span></span>  <br/> <span data-ttu-id="33f26-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-300">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-301">drivers license</span></span>  <br/> <span data-ttu-id="33f26-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-302">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-303">driver's license</span></span>  <br/> <span data-ttu-id="33f26-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-304">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-305">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-306">driving license number</span></span>  <br/> <span data-ttu-id="33f26-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-307">dlno#</span></span>  <br/> <span data-ttu-id="33f26-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="33f26-308">kørekort</span></span>  <br/> <span data-ttu-id="33f26-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="33f26-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="33f26-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="33f26-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="33f26-311">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-311">Format</span></span>

<span data-ttu-id="33f26-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-313">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-313">Pattern</span></span>

<span data-ttu-id="33f26-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="33f26-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="33f26-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="33f26-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-317">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-317">Checksum</span></span>

<span data-ttu-id="33f26-318">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-319">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-319">Definition</span></span>

<span data-ttu-id="33f26-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-322">From `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-323">Keywords</span></span>

<span data-ttu-id="33f26-324">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-324"></span></span>
|<span data-ttu-id="33f26-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-326">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-326">dl#</span></span>  <br/> <span data-ttu-id="33f26-327">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-327">driver license</span></span>  <br/> <span data-ttu-id="33f26-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-328">driver license number</span></span>  <br/> <span data-ttu-id="33f26-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-329">driver license number</span></span>  <br/> <span data-ttu-id="33f26-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-330">driver licence</span></span>  <br/> <span data-ttu-id="33f26-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-331">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-332">drivers license</span></span>  <br/> <span data-ttu-id="33f26-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-333">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-334">driver's license</span></span>  <br/> <span data-ttu-id="33f26-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-335">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-336">driving license number</span></span>  <br/> <span data-ttu-id="33f26-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-337">dlno#</span></span>  <br/> <span data-ttu-id="33f26-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="33f26-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="33f26-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="33f26-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="33f26-340">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-340">Format</span></span>

<span data-ttu-id="33f26-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-342">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-342">Pattern</span></span>

<span data-ttu-id="33f26-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="33f26-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="33f26-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-344">Six digits</span></span> 
    
- <span data-ttu-id="33f26-345">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="33f26-345">A hyphen</span></span>
    
-  <span data-ttu-id="33f26-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="33f26-347">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-347">Checksum</span></span>

<span data-ttu-id="33f26-348">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-349">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-349">Definition</span></span>

<span data-ttu-id="33f26-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-352">From `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-353">Keywords</span></span>

<span data-ttu-id="33f26-354">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-354"></span></span>
|<span data-ttu-id="33f26-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-356">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-356">dl#</span></span>  <br/> <span data-ttu-id="33f26-357">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-357">driver license</span></span>  <br/> <span data-ttu-id="33f26-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-358">driver license number</span></span>  <br/> <span data-ttu-id="33f26-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-359">driver licence</span></span>  <br/> <span data-ttu-id="33f26-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-360">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-361">drivers license</span></span>  <br/> <span data-ttu-id="33f26-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-362">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-363">driver's license</span></span>  <br/> <span data-ttu-id="33f26-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-364">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-365">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-366">driving license number</span></span>  <br/> <span data-ttu-id="33f26-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-367">dlno#</span></span>  <br/> <span data-ttu-id="33f26-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="33f26-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="33f26-369">フランス</span><span class="sxs-lookup"><span data-stu-id="33f26-369">France</span></span>

<span data-ttu-id="33f26-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33f26-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="33f26-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="33f26-371">Germany</span></span>

<span data-ttu-id="33f26-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33f26-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="33f26-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="33f26-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="33f26-374">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-374">Format</span></span>

<span data-ttu-id="33f26-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-376">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-376">Pattern</span></span>

 <span data-ttu-id="33f26-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33f26-378">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-378">Checksum</span></span>

<span data-ttu-id="33f26-379">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-380">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-380">Definition</span></span>

<span data-ttu-id="33f26-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-383">From `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-384">Keywords</span></span>

<span data-ttu-id="33f26-385">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-385"></span></span>
|<span data-ttu-id="33f26-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-387">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="33f26-387">dlL#</span></span>  <br/> <span data-ttu-id="33f26-388">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-388">driver license</span></span>  <br/> <span data-ttu-id="33f26-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-389">driver license number</span></span>  <br/> <span data-ttu-id="33f26-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-390">driver licence</span></span>  <br/> <span data-ttu-id="33f26-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-391">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-392">drivers license</span></span>  <br/> <span data-ttu-id="33f26-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-393">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-394">driver's license</span></span>  <br/> <span data-ttu-id="33f26-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-395">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-396">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-397">driving license number</span></span>  <br/> <span data-ttu-id="33f26-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-398">dlno#</span></span>  <br/> <span data-ttu-id="33f26-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="33f26-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="33f26-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="33f26-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="33f26-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="33f26-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="33f26-402">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-402">Format</span></span>

<span data-ttu-id="33f26-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-404">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-404">Pattern</span></span>

<span data-ttu-id="33f26-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="33f26-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="33f26-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="33f26-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-408">Checksum</span></span>

<span data-ttu-id="33f26-409">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-410">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-410">Definition</span></span>

<span data-ttu-id="33f26-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-413">From `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-414">Keywords</span></span>

<span data-ttu-id="33f26-415">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-415"></span></span>
|<span data-ttu-id="33f26-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-417">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-417">dl#</span></span>  <br/> <span data-ttu-id="33f26-418">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-418">driver license</span></span>  <br/> <span data-ttu-id="33f26-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-419">driver license number</span></span>  <br/> <span data-ttu-id="33f26-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-420">driver licence</span></span>  <br/> <span data-ttu-id="33f26-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-421">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-422">drivers license</span></span>  <br/> <span data-ttu-id="33f26-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-423">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-424">driver's license</span></span>  <br/> <span data-ttu-id="33f26-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-425">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-426">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-427">driving license number</span></span>  <br/> <span data-ttu-id="33f26-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-428">dlno#</span></span>  <br/> <span data-ttu-id="33f26-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="33f26-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="33f26-430">アイルランド</span><span class="sxs-lookup"><span data-stu-id="33f26-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="33f26-431">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-431">Format</span></span>

<span data-ttu-id="33f26-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="33f26-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-433">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-433">Pattern</span></span>

<span data-ttu-id="33f26-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="33f26-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="33f26-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-435">Six digits</span></span>
    
- <span data-ttu-id="33f26-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-437">Checksum</span></span>

<span data-ttu-id="33f26-438">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-439">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-439">Definition</span></span>

<span data-ttu-id="33f26-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-442">From `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-443">Keywords</span></span>

<span data-ttu-id="33f26-444">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-444"></span></span>
|<span data-ttu-id="33f26-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-446">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-446">dl#</span></span>  <br/> <span data-ttu-id="33f26-447">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-447">driver license</span></span>  <br/> <span data-ttu-id="33f26-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-448">driver license number</span></span>  <br/> <span data-ttu-id="33f26-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-449">driver licence</span></span>  <br/> <span data-ttu-id="33f26-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-450">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-451">drivers license</span></span>  <br/> <span data-ttu-id="33f26-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-452">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-453">driver's license</span></span>  <br/> <span data-ttu-id="33f26-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-454">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-455">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-456">driving license number</span></span>  <br/> <span data-ttu-id="33f26-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-457">dlno#</span></span>  <br/> <span data-ttu-id="33f26-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="33f26-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="33f26-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="33f26-459">Italy</span></span>

<span data-ttu-id="33f26-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="33f26-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="33f26-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="33f26-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="33f26-462">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-462">Format</span></span>

<span data-ttu-id="33f26-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-464">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-464">Pattern</span></span>

<span data-ttu-id="33f26-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="33f26-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="33f26-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="33f26-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-468">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-468">Checksum</span></span>

<span data-ttu-id="33f26-469">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-470">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-470">Definition</span></span>

<span data-ttu-id="33f26-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-473">From `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-474">Keywords</span></span>

<span data-ttu-id="33f26-475">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-475"></span></span>
|<span data-ttu-id="33f26-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-477">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-477">dl#</span></span>  <br/> <span data-ttu-id="33f26-478">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-478">driver license</span></span>  <br/> <span data-ttu-id="33f26-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-479">driver license number</span></span>  <br/> <span data-ttu-id="33f26-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-480">driver licence</span></span>  <br/> <span data-ttu-id="33f26-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-481">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-482">drivers license</span></span>  <br/> <span data-ttu-id="33f26-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-483">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-484">driver's license</span></span>  <br/> <span data-ttu-id="33f26-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-485">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-486">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-487">driving license number</span></span>  <br/> <span data-ttu-id="33f26-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-488">dlno#</span></span>  <br/> <span data-ttu-id="33f26-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="33f26-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="33f26-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="33f26-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="33f26-491">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-491">Format</span></span>

<span data-ttu-id="33f26-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-493">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-493">Pattern</span></span>

 <span data-ttu-id="33f26-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33f26-495">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-495">Checksum</span></span>

<span data-ttu-id="33f26-496">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-497">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-497">Definition</span></span>

<span data-ttu-id="33f26-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-500">From `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-501">Keywords</span></span>

<span data-ttu-id="33f26-502">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-502"></span></span>
|<span data-ttu-id="33f26-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-504">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-504">dl#</span></span>  <br/> <span data-ttu-id="33f26-505">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-505">driver license</span></span>  <br/> <span data-ttu-id="33f26-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-506">driver license number</span></span>  <br/> <span data-ttu-id="33f26-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-507">driver licence</span></span>  <br/> <span data-ttu-id="33f26-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-508">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-509">drivers license</span></span>  <br/> <span data-ttu-id="33f26-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-510">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-511">driver's license</span></span>  <br/> <span data-ttu-id="33f26-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-512">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-513">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-514">driving license number</span></span>  <br/> <span data-ttu-id="33f26-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-515">dlno#</span></span>  <br/> <span data-ttu-id="33f26-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="33f26-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="33f26-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="33f26-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="33f26-518">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-518">Format</span></span>

<span data-ttu-id="33f26-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-520">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-520">Pattern</span></span>

 <span data-ttu-id="33f26-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="33f26-522">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-522">Checksum</span></span>

<span data-ttu-id="33f26-523">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-524">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-524">Definition</span></span>

<span data-ttu-id="33f26-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-527">From `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-528">Keywords</span></span>

<span data-ttu-id="33f26-529">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-529"></span></span>
|<span data-ttu-id="33f26-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-531">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-531">dl#</span></span>  <br/> <span data-ttu-id="33f26-532">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-532">driver license</span></span>  <br/> <span data-ttu-id="33f26-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-533">driver license number</span></span>  <br/> <span data-ttu-id="33f26-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-534">driver licence</span></span>  <br/> <span data-ttu-id="33f26-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-535">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-536">drivers license</span></span>  <br/> <span data-ttu-id="33f26-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-537">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-538">driver's license</span></span>  <br/> <span data-ttu-id="33f26-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-539">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-540">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-541">driving license number</span></span>  <br/> <span data-ttu-id="33f26-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-542">dlno#</span></span>  <br/> <span data-ttu-id="33f26-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="33f26-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="33f26-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="33f26-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="33f26-545">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-545">Format</span></span>

<span data-ttu-id="33f26-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="33f26-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-547">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-547">Pattern</span></span>

<span data-ttu-id="33f26-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="33f26-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="33f26-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="33f26-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="33f26-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="33f26-550">A space (optional)</span></span>
    
- <span data-ttu-id="33f26-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-551">Three digits</span></span>
    
- <span data-ttu-id="33f26-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="33f26-552">A space (optional)</span></span>
    
- <span data-ttu-id="33f26-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-554">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-554">Checksum</span></span>

<span data-ttu-id="33f26-555">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-556">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-556">Definition</span></span>

<span data-ttu-id="33f26-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-559">From `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-560">Keywords</span></span>

<span data-ttu-id="33f26-561">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-561"></span></span>
|<span data-ttu-id="33f26-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-563">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-563">dl#</span></span>  <br/> <span data-ttu-id="33f26-564">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-564">driver license</span></span>  <br/> <span data-ttu-id="33f26-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-565">driver license number</span></span>  <br/> <span data-ttu-id="33f26-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-566">driver licence</span></span>  <br/> <span data-ttu-id="33f26-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-567">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-568">drivers license</span></span>  <br/> <span data-ttu-id="33f26-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-569">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-570">driver's license</span></span>  <br/> <span data-ttu-id="33f26-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-571">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-572">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-573">driving license number</span></span>  <br/> <span data-ttu-id="33f26-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-574">dlno#</span></span>  <br/> <span data-ttu-id="33f26-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="33f26-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="33f26-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="33f26-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="33f26-577">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-577">Format</span></span>

<span data-ttu-id="33f26-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-579">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-579">Pattern</span></span>

<span data-ttu-id="33f26-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-581">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-581">Checksum</span></span>

<span data-ttu-id="33f26-582">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-583">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-583">Definition</span></span>

<span data-ttu-id="33f26-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-586">From `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-587">Keywords</span></span>

<span data-ttu-id="33f26-588">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-588"></span></span>
|<span data-ttu-id="33f26-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-590">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-590">dl#</span></span>  <br/> <span data-ttu-id="33f26-591">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-591">driver license</span></span>  <br/> <span data-ttu-id="33f26-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-592">driver license number</span></span>  <br/> <span data-ttu-id="33f26-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-593">driver licence</span></span>  <br/> <span data-ttu-id="33f26-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-594">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-595">drivers license</span></span>  <br/> <span data-ttu-id="33f26-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-596">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-597">driver's license</span></span>  <br/> <span data-ttu-id="33f26-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-598">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-599">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-600">driving license number</span></span>  <br/> <span data-ttu-id="33f26-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-601">dlno#</span></span>  <br/> <span data-ttu-id="33f26-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="33f26-602">permis de conduire</span></span>  <br/> <span data-ttu-id="33f26-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="33f26-603">rijbewijs</span></span>  <br/> <span data-ttu-id="33f26-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="33f26-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="33f26-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="33f26-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="33f26-606">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-606">Format</span></span>

<span data-ttu-id="33f26-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-608">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-608">Pattern</span></span>

<span data-ttu-id="33f26-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="33f26-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="33f26-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-610">Five digits</span></span> 
    
- <span data-ttu-id="33f26-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="33f26-611">A forward slash</span></span>
    
- <span data-ttu-id="33f26-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-612">Two digits</span></span>
    
- <span data-ttu-id="33f26-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="33f26-613">A forward slash</span></span>
    
- <span data-ttu-id="33f26-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-615">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-615">Checksum</span></span>

<span data-ttu-id="33f26-616">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-617">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-617">Definition</span></span>

<span data-ttu-id="33f26-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-620">From `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-621">Keywords</span></span>

<span data-ttu-id="33f26-622">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-622"></span></span>
|<span data-ttu-id="33f26-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-624">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-624">dl#</span></span>  <br/> <span data-ttu-id="33f26-625">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-625">driver license</span></span>  <br/> <span data-ttu-id="33f26-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-626">driver license number</span></span>  <br/> <span data-ttu-id="33f26-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-627">driver licence</span></span>  <br/> <span data-ttu-id="33f26-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-628">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-629">drivers license</span></span>  <br/> <span data-ttu-id="33f26-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-630">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-631">driver's license</span></span>  <br/> <span data-ttu-id="33f26-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-632">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-633">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-634">driving license number</span></span>  <br/> <span data-ttu-id="33f26-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-635">dlno#</span></span>  <br/> <span data-ttu-id="33f26-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="33f26-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="33f26-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="33f26-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="33f26-638">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-638">Format</span></span>

<span data-ttu-id="33f26-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-640">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-640">Pattern</span></span>

<span data-ttu-id="33f26-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="33f26-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="33f26-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="33f26-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="33f26-643">A hyphen</span></span>
    
- <span data-ttu-id="33f26-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-644">Six digits</span></span>
    
- <span data-ttu-id="33f26-645">スペース</span><span class="sxs-lookup"><span data-stu-id="33f26-645">A space</span></span>
    
- <span data-ttu-id="33f26-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-647">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-647">Checksum</span></span>

<span data-ttu-id="33f26-648">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-649">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-649">Definition</span></span>

<span data-ttu-id="33f26-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-652">From `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-653">Keywords</span></span>

<span data-ttu-id="33f26-654">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-654"></span></span>
|<span data-ttu-id="33f26-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-656">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-656">dl#</span></span>  <br/> <span data-ttu-id="33f26-657">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-657">driver license</span></span>  <br/> <span data-ttu-id="33f26-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-658">driver license number</span></span>  <br/> <span data-ttu-id="33f26-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-659">driver licence</span></span>  <br/> <span data-ttu-id="33f26-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-660">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-661">drivers license</span></span>  <br/> <span data-ttu-id="33f26-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-662">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-663">driver's license</span></span>  <br/> <span data-ttu-id="33f26-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-664">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-665">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-666">driving license number</span></span>  <br/> <span data-ttu-id="33f26-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-667">dlno#</span></span>  <br/> <span data-ttu-id="33f26-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="33f26-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="33f26-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="33f26-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="33f26-670">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-670">Format</span></span>

<span data-ttu-id="33f26-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-672">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-672">Pattern</span></span>

<span data-ttu-id="33f26-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="33f26-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="33f26-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="33f26-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="33f26-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-676">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-676">Checksum</span></span>

<span data-ttu-id="33f26-677">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-678">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-678">Definition</span></span>

<span data-ttu-id="33f26-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-681">From `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-682">Keywords</span></span>

<span data-ttu-id="33f26-683">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-683"></span></span>
|<span data-ttu-id="33f26-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-685">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-685">dl#</span></span>  <br/> <span data-ttu-id="33f26-686">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-686">driver license</span></span>  <br/> <span data-ttu-id="33f26-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-687">driver license number</span></span>  <br/> <span data-ttu-id="33f26-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-688">driver licence</span></span>  <br/> <span data-ttu-id="33f26-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-689">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-690">drivers license</span></span>  <br/> <span data-ttu-id="33f26-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-691">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-692">driver's license</span></span>  <br/> <span data-ttu-id="33f26-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-693">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-694">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-695">driving license number</span></span>  <br/> <span data-ttu-id="33f26-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-696">dlno#</span></span>  <br/> <span data-ttu-id="33f26-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="33f26-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="33f26-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="33f26-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="33f26-699">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-699">Format</span></span>

<span data-ttu-id="33f26-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-701">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-701">Pattern</span></span>

<span data-ttu-id="33f26-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="33f26-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="33f26-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="33f26-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="33f26-705">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-705">Checksum</span></span>

<span data-ttu-id="33f26-706">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-707">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-707">Definition</span></span>

<span data-ttu-id="33f26-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-710">From `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-711">Keywords</span></span>

<span data-ttu-id="33f26-712">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-712"></span></span>
|<span data-ttu-id="33f26-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-714">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-714">dl#</span></span>  <br/> <span data-ttu-id="33f26-715">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-715">driver license</span></span>  <br/> <span data-ttu-id="33f26-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-716">driver license number</span></span>  <br/> <span data-ttu-id="33f26-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-717">driver licence</span></span>  <br/> <span data-ttu-id="33f26-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-718">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-719">drivers license</span></span>  <br/> <span data-ttu-id="33f26-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-720">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-721">driver's license</span></span>  <br/> <span data-ttu-id="33f26-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-722">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-723">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-724">driving license number</span></span>  <br/> <span data-ttu-id="33f26-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-725">dlno#</span></span>  <br/> <span data-ttu-id="33f26-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="33f26-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="33f26-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="33f26-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="33f26-728">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-728">Format</span></span>

<span data-ttu-id="33f26-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-730">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-730">Pattern</span></span>

<span data-ttu-id="33f26-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="33f26-732">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-732">Checksum</span></span>

<span data-ttu-id="33f26-733">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-734">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-734">Definition</span></span>

<span data-ttu-id="33f26-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-737">From `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-738">Keywords</span></span>

<span data-ttu-id="33f26-739">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-739"></span></span>
|<span data-ttu-id="33f26-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-741">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-741">dl#</span></span>  <br/> <span data-ttu-id="33f26-742">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-742">driver license</span></span>  <br/> <span data-ttu-id="33f26-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-743">driver license number</span></span>  <br/> <span data-ttu-id="33f26-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-744">driver licence</span></span>  <br/> <span data-ttu-id="33f26-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-745">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-746">drivers license</span></span>  <br/> <span data-ttu-id="33f26-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-747">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-748">driver's license</span></span>  <br/> <span data-ttu-id="33f26-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-749">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-750">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-751">driving license number</span></span>  <br/> <span data-ttu-id="33f26-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-752">dlno#</span></span>  <br/> <span data-ttu-id="33f26-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="33f26-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="33f26-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="33f26-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="33f26-755">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-755">Format</span></span>

<span data-ttu-id="33f26-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="33f26-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-757">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-757">Pattern</span></span>

<span data-ttu-id="33f26-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="33f26-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="33f26-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-759">Eight digits</span></span> 
    
- <span data-ttu-id="33f26-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="33f26-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-761">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-761">Checksum</span></span>

<span data-ttu-id="33f26-762">はい</span><span class="sxs-lookup"><span data-stu-id="33f26-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-763">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-763">Definition</span></span>

<span data-ttu-id="33f26-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="33f26-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-766">From `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="33f26-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-767">Keywords</span></span>

<span data-ttu-id="33f26-768">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-768"></span></span>
|<span data-ttu-id="33f26-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-770">dlno#</span></span>  <br/> <span data-ttu-id="33f26-771">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-771">dl#</span></span>  <br/> <span data-ttu-id="33f26-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-772">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-773">driver licence</span></span>  <br/> <span data-ttu-id="33f26-774">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-774">driver license</span></span>  <br/> <span data-ttu-id="33f26-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-775">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-776">drivers license</span></span>  <br/> <span data-ttu-id="33f26-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="33f26-777">driver's licence</span></span>  <br/> <span data-ttu-id="33f26-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-778">driver's license</span></span>  <br/> <span data-ttu-id="33f26-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="33f26-779">driving licence</span></span>  <br/> <span data-ttu-id="33f26-780">driving license</span><span class="sxs-lookup"><span data-stu-id="33f26-780">driving license</span></span>  <br/> <span data-ttu-id="33f26-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-781">driver licence number</span></span>  <br/> <span data-ttu-id="33f26-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-782">driver license number</span></span>  <br/> <span data-ttu-id="33f26-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-783">drivers licence number</span></span>  <br/> <span data-ttu-id="33f26-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-784">drivers license number</span></span>  <br/> <span data-ttu-id="33f26-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-785">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-786">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="33f26-787">driving licence number</span></span>  <br/> <span data-ttu-id="33f26-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-788">driving license number</span></span>  <br/> <span data-ttu-id="33f26-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="33f26-789">driving permit</span></span>  <br/> <span data-ttu-id="33f26-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="33f26-790">driving permit number</span></span>  <br/> <span data-ttu-id="33f26-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="33f26-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="33f26-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="33f26-792">permiso conducción</span></span>  <br/> <span data-ttu-id="33f26-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="33f26-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="33f26-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="33f26-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-796">licencia conducir</span></span>  <br/> <span data-ttu-id="33f26-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="33f26-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="33f26-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="33f26-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-800">permiso conducir</span></span>  <br/> <span data-ttu-id="33f26-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="33f26-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="33f26-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="33f26-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="33f26-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="33f26-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="33f26-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="33f26-805">Format</span><span class="sxs-lookup"><span data-stu-id="33f26-805">Format</span></span>

<span data-ttu-id="33f26-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="33f26-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="33f26-807">パターン</span><span class="sxs-lookup"><span data-stu-id="33f26-807">Pattern</span></span>

<span data-ttu-id="33f26-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="33f26-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="33f26-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-809">Six digits</span></span> 
    
- <span data-ttu-id="33f26-810">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="33f26-810">A hyphen</span></span>
    
- <span data-ttu-id="33f26-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="33f26-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="33f26-812">チェックサム</span><span class="sxs-lookup"><span data-stu-id="33f26-812">Checksum</span></span>

<span data-ttu-id="33f26-813">いいえ</span><span class="sxs-lookup"><span data-stu-id="33f26-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="33f26-814">定義</span><span class="sxs-lookup"><span data-stu-id="33f26-814">Definition</span></span>

<span data-ttu-id="33f26-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="33f26-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="33f26-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="33f26-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="33f26-817">From `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="33f26-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="33f26-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="33f26-818">Keywords</span></span>

<span data-ttu-id="33f26-819">| |</span><span class="sxs-lookup"><span data-stu-id="33f26-819"></span></span>
|<span data-ttu-id="33f26-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="33f26-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="33f26-821">dl</span><span class="sxs-lookup"><span data-stu-id="33f26-821">dl#</span></span>  <br/> <span data-ttu-id="33f26-822">driver license</span><span class="sxs-lookup"><span data-stu-id="33f26-822">driver license</span></span>  <br/> <span data-ttu-id="33f26-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-823">driver license number</span></span>  <br/> <span data-ttu-id="33f26-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="33f26-824">driver licence</span></span>  <br/> <span data-ttu-id="33f26-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="33f26-825">drivers lic.</span></span>  <br/> <span data-ttu-id="33f26-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="33f26-826">drivers license</span></span>  <br/> <span data-ttu-id="33f26-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="33f26-827">drivers licence</span></span>  <br/> <span data-ttu-id="33f26-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="33f26-828">driver's license</span></span>  <br/> <span data-ttu-id="33f26-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-829">driver's license number</span></span>  <br/> <span data-ttu-id="33f26-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="33f26-830">driver's licence number</span></span>  <br/> <span data-ttu-id="33f26-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="33f26-831">driving license number</span></span>  <br/> <span data-ttu-id="33f26-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="33f26-832">dlno#</span></span>  <br/> <span data-ttu-id="33f26-833">körkort</span><span class="sxs-lookup"><span data-stu-id="33f26-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="33f26-834">佐賀</span><span class="sxs-lookup"><span data-stu-id="33f26-834">UK</span></span>

<span data-ttu-id="33f26-835">詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="33f26-835">For details, see the section "U.K.</span></span> <span data-ttu-id="33f26-836">[[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。</span><span class="sxs-lookup"><span data-stu-id="33f26-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="33f26-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="33f26-837">See also</span></span>

[<span data-ttu-id="33f26-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="33f26-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

