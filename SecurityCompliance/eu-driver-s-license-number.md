---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: c3923cd3-ec84-435f-bf41-cadc37996a4b
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 運転免許証番号機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 065684249f9766d567c63e6b8170d36f56692e45
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532112"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="42ca3-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-104">EU Driver's License Number</span></span>

<span data-ttu-id="42ca3-p102">このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 運転免許証番号機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="42ca3-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="42ca3-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-108">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-108">Format</span></span>

<span data-ttu-id="42ca3-109">8 桁の空白と区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-110">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-110">Pattern</span></span>

<span data-ttu-id="42ca3-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-112">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-112">Checksum</span></span>

<span data-ttu-id="42ca3-113">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-114">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-114">Definition</span></span>

<span data-ttu-id="42ca3-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-116">正規表現`Regex_austria_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-117">キーワードの`Keywords_austria_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="42ca3-118">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-118">Keywords</span></span>

<span data-ttu-id="42ca3-119">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-119"></span></span>
|<span data-ttu-id="42ca3-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-121">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-121">dl#</span></span>  <br/> <span data-ttu-id="42ca3-122">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-122">driver license</span></span>  <br/> <span data-ttu-id="42ca3-123">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-123">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-124">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-124">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-125">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-125">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-126">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-127">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-127">driver's licence</span></span>  <br/> <span data-ttu-id="42ca3-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-128">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-129">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-130">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="42ca3-131">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-131">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-132">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="42ca3-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="42ca3-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="42ca3-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="42ca3-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="42ca3-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-136">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-136">Format</span></span>

<span data-ttu-id="42ca3-137">スペースや区切り記号なしの 10 桁</span><span class="sxs-lookup"><span data-stu-id="42ca3-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-138">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-138">Pattern</span></span>

<span data-ttu-id="42ca3-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-140">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-140">Checksum</span></span>

<span data-ttu-id="42ca3-141">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-142">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-142">Definition</span></span>

<span data-ttu-id="42ca3-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-144">正規表現`Regex_belgium_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-145">キーワードの`Keywords_belgium_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="42ca3-146">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-146">Keywords</span></span>

<span data-ttu-id="42ca3-147">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-147"></span></span>
|<span data-ttu-id="42ca3-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-149">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-149">dl#</span></span>  <br/> <span data-ttu-id="42ca3-150">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-150">driver license</span></span>  <br/> <span data-ttu-id="42ca3-151">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-151">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-152">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-152">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-153">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-153">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-154">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-155">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-156">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-157">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-158">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-158">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-159">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="42ca3-160">rijbewijs</span></span>  <br/> <span data-ttu-id="42ca3-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="42ca3-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="42ca3-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="42ca3-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="42ca3-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="42ca3-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="42ca3-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="42ca3-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="42ca3-165">führerschein nr</span><span class="sxs-lookup"><span data-stu-id="42ca3-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="42ca3-166">fuehrerschein Nr</span><span class="sxs-lookup"><span data-stu-id="42ca3-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="42ca3-167">fuehrerschein nr</span><span class="sxs-lookup"><span data-stu-id="42ca3-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="42ca3-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="42ca3-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-169">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-169">Format</span></span>

<span data-ttu-id="42ca3-170">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="42ca3-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-171">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-171">Pattern</span></span>

<span data-ttu-id="42ca3-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-173">Checksum</span></span>

<span data-ttu-id="42ca3-174">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-175">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-175">Definition</span></span>

<span data-ttu-id="42ca3-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-177">正規表現`Regex_bulgaria_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-178">キーワードの`Keywords_bulgaria_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="42ca3-179">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-179">Keywords</span></span>

<span data-ttu-id="42ca3-180">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-180"></span></span>
|<span data-ttu-id="42ca3-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-182">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-182">dl#</span></span>  <br/> <span data-ttu-id="42ca3-183">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-183">driver license</span></span>  <br/> <span data-ttu-id="42ca3-184">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-184">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-185">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-185">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-186">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-186">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-187">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-188">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-189">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-190">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-191">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-191">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-192">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-192">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-193">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-194">ЗА УПРАВЛЕНИЕ НА МПС の СВИДЕТЕЛСТВО</span><span class="sxs-lookup"><span data-stu-id="42ca3-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="42ca3-195">СВИДЕТЕЛСТВО ЗА УПРАВЛЕНИЕ НА МОТОРНО ПРЕВОЗНО СРЕДСТВО</span><span class="sxs-lookup"><span data-stu-id="42ca3-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="42ca3-196">СУМПС</span><span class="sxs-lookup"><span data-stu-id="42ca3-196">сумпс</span></span>  <br/> <span data-ttu-id="42ca3-197">ШОФЬОРСКА КНИЖКА</span><span class="sxs-lookup"><span data-stu-id="42ca3-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="42ca3-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="42ca3-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-199">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-199">Format</span></span>

<span data-ttu-id="42ca3-200">8 桁の空白と区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-201">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-201">Pattern</span></span>

<span data-ttu-id="42ca3-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-203">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-203">Checksum</span></span>

<span data-ttu-id="42ca3-204">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-205">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-205">Definition</span></span>

<span data-ttu-id="42ca3-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-207">正規表現`Regex_croatia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-208">キーワードの`Keywords_croatia_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="42ca3-209">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-209">Keywords</span></span>

<span data-ttu-id="42ca3-210">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-210"></span></span>
|<span data-ttu-id="42ca3-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-212">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-212">dl#</span></span>  <br/> <span data-ttu-id="42ca3-213">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-213">driver license</span></span>  <br/> <span data-ttu-id="42ca3-214">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-214">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-215">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-215">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-216">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-216">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-217">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-218">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-219">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-220">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-221">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-221">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-222">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-222">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-223">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="42ca3-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="42ca3-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="42ca3-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-226">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-226">Format</span></span>

<span data-ttu-id="42ca3-227">スペースや区切り記号のない 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-228">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-228">Pattern</span></span>

<span data-ttu-id="42ca3-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-230">Checksum</span></span>

<span data-ttu-id="42ca3-231">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-232">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-232">Definition</span></span>

<span data-ttu-id="42ca3-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-234">正規表現`Regex_cyprus_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-235">キーワードの`Keywords_cyprus_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-236">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-236">Keywords</span></span>

<span data-ttu-id="42ca3-237">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-237"></span></span>
|<span data-ttu-id="42ca3-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-239">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-239">dl#</span></span>  <br/> <span data-ttu-id="42ca3-240">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-240">driver license</span></span>  <br/> <span data-ttu-id="42ca3-241">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-241">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-242">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-242">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-243">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-243">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-244">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-245">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-246">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-247">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-247">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-248">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-248">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-249">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-250">ΆΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="42ca3-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="42ca3-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="42ca3-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-252">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-252">Format</span></span>

<span data-ttu-id="42ca3-253">6 桁の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-254">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-254">Pattern</span></span>

<span data-ttu-id="42ca3-255">8 つの文字と数字の場合。</span><span class="sxs-lookup"><span data-stu-id="42ca3-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="42ca3-256">2 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="42ca3-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="42ca3-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="42ca3-257">A space (optional)</span></span>
    
- <span data-ttu-id="42ca3-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-259">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-259">Checksum</span></span>

<span data-ttu-id="42ca3-260">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-261">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-261">Definition</span></span>

<span data-ttu-id="42ca3-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-263">正規表現`Regex_czech_republic_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-264">キーワードの`Keywords_czech_republic_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="42ca3-265">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-265">Keywords</span></span>

<span data-ttu-id="42ca3-266">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-266"></span></span>
|<span data-ttu-id="42ca3-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-268">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-268">dl#</span></span>  <br/> <span data-ttu-id="42ca3-269">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-269">driver license</span></span>  <br/> <span data-ttu-id="42ca3-270">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-270">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-271">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-271">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-272">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-272">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-273">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-274">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-275">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-276">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-277">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-278">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-278">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-279">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-279">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-280">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-281">Řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="42ca3-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="42ca3-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="42ca3-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-283">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-283">Format</span></span>

<span data-ttu-id="42ca3-284">8 桁の空白と区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-285">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-285">Pattern</span></span>

<span data-ttu-id="42ca3-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-287">Checksum</span></span>

<span data-ttu-id="42ca3-288">はい</span><span class="sxs-lookup"><span data-stu-id="42ca3-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-289">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-289">Definition</span></span>

<span data-ttu-id="42ca3-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-291">正規表現`Regex_denmark_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-292">キーワードの`Keywords_denmark_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="42ca3-293">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-293">Keywords</span></span>

<span data-ttu-id="42ca3-294">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-294"></span></span>
|<span data-ttu-id="42ca3-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-296">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-296">dl#</span></span>  <br/> <span data-ttu-id="42ca3-297">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-297">driver license</span></span>  <br/> <span data-ttu-id="42ca3-298">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-298">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-299">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-299">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-300">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-300">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-301">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-302">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-303">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-304">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-305">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-305">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-306">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-306">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-307">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="42ca3-308">kørekort</span></span>  <br/> <span data-ttu-id="42ca3-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="42ca3-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="42ca3-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="42ca3-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-311">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-311">Format</span></span>

<span data-ttu-id="42ca3-312">6 桁の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-313">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-313">Pattern</span></span>

<span data-ttu-id="42ca3-314">2 つの文字と 6 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="42ca3-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="42ca3-315">文字"ET"(いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="42ca3-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="42ca3-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-317">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-317">Checksum</span></span>

<span data-ttu-id="42ca3-318">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-319">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-319">Definition</span></span>

<span data-ttu-id="42ca3-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-321">正規表現`Regex_estonia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-322">キーワードの`Keywords_estonia_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-323">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-323">Keywords</span></span>

<span data-ttu-id="42ca3-324">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-324"></span></span>
|<span data-ttu-id="42ca3-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-326">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-326">dl#</span></span>  <br/> <span data-ttu-id="42ca3-327">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-327">driver license</span></span>  <br/> <span data-ttu-id="42ca3-328">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-328">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-329">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-329">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-330">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-330">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-331">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-331">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-332">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-333">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-334">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-335">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-336">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-336">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-337">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-338">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="42ca3-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="42ca3-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="42ca3-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-340">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-340">Format</span></span>

<span data-ttu-id="42ca3-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-342">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-342">Pattern</span></span>

<span data-ttu-id="42ca3-343">ハイフンが含まれている 10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="42ca3-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="42ca3-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-344">Six digits</span></span> 
    
- <span data-ttu-id="42ca3-345">ハイフン</span><span class="sxs-lookup"><span data-stu-id="42ca3-345">A hyphen</span></span>
    
-  <span data-ttu-id="42ca3-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="42ca3-347">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-347">Checksum</span></span>

<span data-ttu-id="42ca3-348">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-349">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-349">Definition</span></span>

<span data-ttu-id="42ca3-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-351">正規表現`Regex_finland_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-352">キーワードの`Keywords_finland_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-353">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-353">Keywords</span></span>

<span data-ttu-id="42ca3-354">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-354"></span></span>
|<span data-ttu-id="42ca3-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-356">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-356">dl#</span></span>  <br/> <span data-ttu-id="42ca3-357">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-357">driver license</span></span>  <br/> <span data-ttu-id="42ca3-358">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-358">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-359">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-359">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-360">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-360">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-361">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-362">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-363">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-364">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-365">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-365">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-366">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-366">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-367">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="42ca3-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="42ca3-369">フランス</span><span class="sxs-lookup"><span data-stu-id="42ca3-369">France</span></span>

<span data-ttu-id="42ca3-370">詳細についてを参照してください「フランスのドライバーのライセンス番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="42ca3-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="42ca3-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="42ca3-371">Germany</span></span>

<span data-ttu-id="42ca3-372">詳細についてを参照してください「ドイツ語の運転免許証番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="42ca3-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="42ca3-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="42ca3-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-374">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-374">Format</span></span>

<span data-ttu-id="42ca3-375">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="42ca3-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-376">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-376">Pattern</span></span>

 <span data-ttu-id="42ca3-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="42ca3-378">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-378">Checksum</span></span>

<span data-ttu-id="42ca3-379">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-380">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-380">Definition</span></span>

<span data-ttu-id="42ca3-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-382">正規表現`Regex_greece_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-383">キーワードの`Keywords_greece_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-384">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-384">Keywords</span></span>

<span data-ttu-id="42ca3-385">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-385"></span></span>
|<span data-ttu-id="42ca3-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-387">dlL の場合</span><span class="sxs-lookup"><span data-stu-id="42ca3-387">dlL#</span></span>  <br/> <span data-ttu-id="42ca3-388">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-388">driver license</span></span>  <br/> <span data-ttu-id="42ca3-389">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-389">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-390">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-390">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-391">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-391">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-392">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-393">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-394">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-395">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-396">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-396">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-397">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-397">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-398">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-399">ΔΕΙΑ ΟΔΉΓΗΣΗΣ</span><span class="sxs-lookup"><span data-stu-id="42ca3-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="42ca3-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="42ca3-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="42ca3-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="42ca3-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-402">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-402">Format</span></span>

<span data-ttu-id="42ca3-403">6 桁の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-404">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-404">Pattern</span></span>

<span data-ttu-id="42ca3-405">2 つの文字と 6 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="42ca3-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="42ca3-406">2 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="42ca3-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="42ca3-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-408">Checksum</span></span>

<span data-ttu-id="42ca3-409">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-410">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-410">Definition</span></span>

<span data-ttu-id="42ca3-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-412">正規表現`Regex_hungary_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-413">キーワードの`Keywords_hungary_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-414">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-414">Keywords</span></span>

<span data-ttu-id="42ca3-415">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-415"></span></span>
|<span data-ttu-id="42ca3-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-417">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-417">dl#</span></span>  <br/> <span data-ttu-id="42ca3-418">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-418">driver license</span></span>  <br/> <span data-ttu-id="42ca3-419">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-419">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-420">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-420">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-421">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-421">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-422">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-423">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-424">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-425">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-426">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-426">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-427">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-427">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-428">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="42ca3-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="42ca3-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="42ca3-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-431">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-431">Format</span></span>

<span data-ttu-id="42ca3-432">4 文字の後に 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-433">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-433">Pattern</span></span>

<span data-ttu-id="42ca3-434">6 桁および 4 つの文字。</span><span class="sxs-lookup"><span data-stu-id="42ca3-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="42ca3-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-435">Six digits</span></span>
    
- <span data-ttu-id="42ca3-436">4 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="42ca3-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-437">Checksum</span></span>

<span data-ttu-id="42ca3-438">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-439">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-439">Definition</span></span>

<span data-ttu-id="42ca3-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-441">正規表現`Regex_ireland_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-442">キーワードの`Keywords_ireland_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-443">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-443">Keywords</span></span>

<span data-ttu-id="42ca3-444">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-444"></span></span>
|<span data-ttu-id="42ca3-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-446">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-446">dl#</span></span>  <br/> <span data-ttu-id="42ca3-447">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-447">driver license</span></span>  <br/> <span data-ttu-id="42ca3-448">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-448">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-449">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-449">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-450">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-450">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-451">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-452">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-453">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-454">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-455">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-455">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-456">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-456">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-457">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="42ca3-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="42ca3-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="42ca3-459">Italy</span></span>

<span data-ttu-id="42ca3-460">詳細についてを参照してください「イタリア ドライバー ライセンスの数」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="42ca3-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="42ca3-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="42ca3-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-462">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-462">Format</span></span>

<span data-ttu-id="42ca3-463">6 桁の後に次の 3 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-464">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-464">Pattern</span></span>

<span data-ttu-id="42ca3-465">3 文字と 6 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="42ca3-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="42ca3-466">3 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="42ca3-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="42ca3-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-468">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-468">Checksum</span></span>

<span data-ttu-id="42ca3-469">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-470">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-470">Definition</span></span>

<span data-ttu-id="42ca3-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-472">正規表現`Regex_latvia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-473">キーワードの`Keywords_latvia_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-474">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-474">Keywords</span></span>

<span data-ttu-id="42ca3-475">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-475"></span></span>
|<span data-ttu-id="42ca3-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-477">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-477">dl#</span></span>  <br/> <span data-ttu-id="42ca3-478">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-478">driver license</span></span>  <br/> <span data-ttu-id="42ca3-479">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-479">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-480">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-480">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-481">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-481">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-482">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-483">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-484">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-485">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-486">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-486">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-487">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-487">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-488">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="42ca3-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="42ca3-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="42ca3-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-491">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-491">Format</span></span>

<span data-ttu-id="42ca3-492">8 桁の空白と区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-493">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-493">Pattern</span></span>

 <span data-ttu-id="42ca3-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="42ca3-495">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-495">Checksum</span></span>

<span data-ttu-id="42ca3-496">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-497">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-497">Definition</span></span>

<span data-ttu-id="42ca3-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-499">正規表現`Regex_lithuania_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-500">キーワードの`Keywords_lithuania_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-501">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-501">Keywords</span></span>

<span data-ttu-id="42ca3-502">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-502"></span></span>
|<span data-ttu-id="42ca3-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-504">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-504">dl#</span></span>  <br/> <span data-ttu-id="42ca3-505">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-505">driver license</span></span>  <br/> <span data-ttu-id="42ca3-506">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-506">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-507">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-507">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-508">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-508">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-509">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-510">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-511">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-512">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-513">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-513">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-514">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-514">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-515">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="42ca3-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="42ca3-517">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="42ca3-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-518">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-518">Format</span></span>

<span data-ttu-id="42ca3-519">スペースや区切り文字なしの 6 桁</span><span class="sxs-lookup"><span data-stu-id="42ca3-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-520">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-520">Pattern</span></span>

 <span data-ttu-id="42ca3-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="42ca3-522">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-522">Checksum</span></span>

<span data-ttu-id="42ca3-523">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-524">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-524">Definition</span></span>

<span data-ttu-id="42ca3-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-526">正規表現`Regex_luxemburg_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-527">キーワードの`Keywords_luxemburg_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-528">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-528">Keywords</span></span>

<span data-ttu-id="42ca3-529">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-529"></span></span>
|<span data-ttu-id="42ca3-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-531">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-531">dl#</span></span>  <br/> <span data-ttu-id="42ca3-532">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-532">driver license</span></span>  <br/> <span data-ttu-id="42ca3-533">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-533">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-534">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-534">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-535">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-535">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-536">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-537">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-538">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-539">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-540">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-540">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-541">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-541">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-542">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="42ca3-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="42ca3-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="42ca3-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-545">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-545">Format</span></span>

<span data-ttu-id="42ca3-546">2 つの文字と指定したパターンには 6 桁の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="42ca3-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-547">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-547">Pattern</span></span>

<span data-ttu-id="42ca3-548">2 つの文字と 6 桁の数字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="42ca3-549">2 つの文字 (数字または文字、大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="42ca3-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="42ca3-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="42ca3-550">A space (optional)</span></span>
    
- <span data-ttu-id="42ca3-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-551">Three digits</span></span>
    
- <span data-ttu-id="42ca3-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="42ca3-552">A space (optional)</span></span>
    
- <span data-ttu-id="42ca3-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-554">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-554">Checksum</span></span>

<span data-ttu-id="42ca3-555">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-556">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-556">Definition</span></span>

<span data-ttu-id="42ca3-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-558">正規表現`Regex_malta_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-559">キーワードの`Keywords_malta_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-560">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-560">Keywords</span></span>

<span data-ttu-id="42ca3-561">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-561"></span></span>
|<span data-ttu-id="42ca3-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-563">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-563">dl#</span></span>  <br/> <span data-ttu-id="42ca3-564">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-564">driver license</span></span>  <br/> <span data-ttu-id="42ca3-565">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-565">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-566">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-566">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-567">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-567">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-568">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-569">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-570">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-571">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-572">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-572">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-573">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-573">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-574">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-575">liċenzja タス-sewqan</span><span class="sxs-lookup"><span data-stu-id="42ca3-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="42ca3-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="42ca3-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-577">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-577">Format</span></span>

<span data-ttu-id="42ca3-578">スペースや区切り記号なしの 10 桁</span><span class="sxs-lookup"><span data-stu-id="42ca3-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-579">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-579">Pattern</span></span>

<span data-ttu-id="42ca3-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-581">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-581">Checksum</span></span>

<span data-ttu-id="42ca3-582">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-583">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-583">Definition</span></span>

<span data-ttu-id="42ca3-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-585">正規表現`Regex_netherlands_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-586">キーワードの`Keywords_netherlands_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-587">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-587">Keywords</span></span>

<span data-ttu-id="42ca3-588">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-588"></span></span>
|<span data-ttu-id="42ca3-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-590">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-590">dl#</span></span>  <br/> <span data-ttu-id="42ca3-591">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-591">driver license</span></span>  <br/> <span data-ttu-id="42ca3-592">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-592">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-593">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-593">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-594">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-594">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-595">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-596">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-597">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-598">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-599">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-599">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-600">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-600">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-601">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-602">
permis de conduire</span><span class="sxs-lookup"><span data-stu-id="42ca3-602">permis de conduire</span></span>  <br/> <span data-ttu-id="42ca3-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="42ca3-603">rijbewijs</span></span>  <br/> <span data-ttu-id="42ca3-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="42ca3-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="42ca3-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="42ca3-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-606">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-606">Format</span></span>

<span data-ttu-id="42ca3-607">2 つのスラッシュが含まれている 14 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-608">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-608">Pattern</span></span>

<span data-ttu-id="42ca3-609">14 桁の数字と 2 つのスラッシュ。</span><span class="sxs-lookup"><span data-stu-id="42ca3-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="42ca3-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-610">Five digits</span></span> 
    
- <span data-ttu-id="42ca3-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="42ca3-611">A forward slash</span></span>
    
- <span data-ttu-id="42ca3-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-612">Two digits</span></span>
    
- <span data-ttu-id="42ca3-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="42ca3-613">A forward slash</span></span>
    
- <span data-ttu-id="42ca3-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-615">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-615">Checksum</span></span>

<span data-ttu-id="42ca3-616">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-617">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-617">Definition</span></span>

<span data-ttu-id="42ca3-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-619">正規表現`Regex_poland_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-620">キーワードの`Keywords_poland_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-621">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-621">Keywords</span></span>

<span data-ttu-id="42ca3-622">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-622"></span></span>
|<span data-ttu-id="42ca3-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-624">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-624">dl#</span></span>  <br/> <span data-ttu-id="42ca3-625">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-625">driver license</span></span>  <br/> <span data-ttu-id="42ca3-626">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-626">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-627">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-627">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-628">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-628">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-629">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-630">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-631">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-632">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-633">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-633">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-634">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-634">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-635">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="42ca3-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="42ca3-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="42ca3-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-638">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-638">Format</span></span>

<span data-ttu-id="42ca3-639">2 つの文字が指定されたパターンで 7 つの数字が続く</span><span class="sxs-lookup"><span data-stu-id="42ca3-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-640">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-640">Pattern</span></span>

<span data-ttu-id="42ca3-641">2 つの文字が特殊文字を含む 7 つの数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="42ca3-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="42ca3-642">2 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="42ca3-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="42ca3-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="42ca3-643">A hyphen</span></span>
    
- <span data-ttu-id="42ca3-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-644">Six digits</span></span>
    
- <span data-ttu-id="42ca3-645">スペース</span><span class="sxs-lookup"><span data-stu-id="42ca3-645">A space</span></span>
    
- <span data-ttu-id="42ca3-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-647">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-647">Checksum</span></span>

<span data-ttu-id="42ca3-648">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-649">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-649">Definition</span></span>

<span data-ttu-id="42ca3-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-651">正規表現`Regex_portugal_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-652">キーワードの`Keywords_portugal_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-653">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-653">Keywords</span></span>

<span data-ttu-id="42ca3-654">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-654"></span></span>
|<span data-ttu-id="42ca3-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-656">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-656">dl#</span></span>  <br/> <span data-ttu-id="42ca3-657">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-657">driver license</span></span>  <br/> <span data-ttu-id="42ca3-658">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-658">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-659">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-659">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-660">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-660">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-661">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-662">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-663">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-664">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-665">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-665">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-666">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-666">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-667">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="42ca3-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="42ca3-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="42ca3-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-670">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-670">Format</span></span>

<span data-ttu-id="42ca3-671">8 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-672">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-672">Pattern</span></span>

<span data-ttu-id="42ca3-673">8 桁の数字の後に 1 つの文字。</span><span class="sxs-lookup"><span data-stu-id="42ca3-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="42ca3-674">1 つの文字列の文字または数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="42ca3-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-676">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-676">Checksum</span></span>

<span data-ttu-id="42ca3-677">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-678">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-678">Definition</span></span>

<span data-ttu-id="42ca3-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-680">正規表現`Regex_romania_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-681">キーワードの`Keywords_romania_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-682">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-682">Keywords</span></span>

<span data-ttu-id="42ca3-683">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-683"></span></span>
|<span data-ttu-id="42ca3-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-685">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-685">dl#</span></span>  <br/> <span data-ttu-id="42ca3-686">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-686">driver license</span></span>  <br/> <span data-ttu-id="42ca3-687">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-687">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-688">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-688">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-689">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-689">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-690">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-691">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-692">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-693">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-694">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-694">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-695">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-695">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-696">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-697">permis デ conducere</span><span class="sxs-lookup"><span data-stu-id="42ca3-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="42ca3-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="42ca3-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-699">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-699">Format</span></span>

<span data-ttu-id="42ca3-700">7 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-701">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-701">Pattern</span></span>

<span data-ttu-id="42ca3-702">7 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="42ca3-703">1 つの文字列の文字または数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="42ca3-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="42ca3-705">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-705">Checksum</span></span>

<span data-ttu-id="42ca3-706">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-707">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-707">Definition</span></span>

<span data-ttu-id="42ca3-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-709">正規表現`Regex_slovakia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-710">キーワードの`Keywords_slovakia_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-711">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-711">Keywords</span></span>

<span data-ttu-id="42ca3-712">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-712"></span></span>
|<span data-ttu-id="42ca3-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-714">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-714">dl#</span></span>  <br/> <span data-ttu-id="42ca3-715">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-715">driver license</span></span>  <br/> <span data-ttu-id="42ca3-716">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-716">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-717">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-717">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-718">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-718">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-719">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-720">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-721">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-722">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-723">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-723">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-724">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-724">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-725">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="42ca3-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="42ca3-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="42ca3-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-728">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-728">Format</span></span>

<span data-ttu-id="42ca3-729">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="42ca3-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-730">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-730">Pattern</span></span>

<span data-ttu-id="42ca3-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="42ca3-732">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-732">Checksum</span></span>

<span data-ttu-id="42ca3-733">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-734">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-734">Definition</span></span>

<span data-ttu-id="42ca3-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-736">正規表現`Regex_slovenia_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-737">キーワードの`Keywords_slovenia_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-738">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-738">Keywords</span></span>

<span data-ttu-id="42ca3-739">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-739"></span></span>
|<span data-ttu-id="42ca3-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-741">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-741">dl#</span></span>  <br/> <span data-ttu-id="42ca3-742">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-742">driver license</span></span>  <br/> <span data-ttu-id="42ca3-743">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-743">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-744">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-744">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-745">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-745">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-746">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-747">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-748">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-749">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-750">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-750">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-751">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-751">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-752">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="42ca3-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="42ca3-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="42ca3-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-755">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-755">Format</span></span>

<span data-ttu-id="42ca3-756">8 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="42ca3-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-757">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-757">Pattern</span></span>

<span data-ttu-id="42ca3-758">8 の数字が 1 つの文字が続きます。</span><span class="sxs-lookup"><span data-stu-id="42ca3-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="42ca3-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-759">Eight digits</span></span> 
    
- <span data-ttu-id="42ca3-760">1 つの数字または文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="42ca3-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-761">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-761">Checksum</span></span>

<span data-ttu-id="42ca3-762">はい</span><span class="sxs-lookup"><span data-stu-id="42ca3-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-763">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-763">Definition</span></span>

<span data-ttu-id="42ca3-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-765">関数`Func_spain_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-766">キーワードの`Keywords_spain_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="42ca3-767">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-767">Keywords</span></span>

<span data-ttu-id="42ca3-768">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-768"></span></span>
|<span data-ttu-id="42ca3-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-770">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-771">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-771">dl#</span></span>  <br/> <span data-ttu-id="42ca3-772">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-772">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-773">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-773">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-774">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-774">driver license</span></span>  <br/> <span data-ttu-id="42ca3-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-775">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-776">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-777">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-777">driver's licence</span></span>  <br/> <span data-ttu-id="42ca3-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-778">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-779">driving licence
</span><span class="sxs-lookup"><span data-stu-id="42ca3-779">driving licence</span></span>  <br/> <span data-ttu-id="42ca3-780">ライセンスを推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-780">driving license</span></span>  <br/> <span data-ttu-id="42ca3-781">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-781">driver licence number</span></span>  <br/> <span data-ttu-id="42ca3-782">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-782">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-783">ドライバーのライセンス数</span><span class="sxs-lookup"><span data-stu-id="42ca3-783">drivers licence number</span></span>  <br/> <span data-ttu-id="42ca3-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-784">drivers license number</span></span>  <br/> <span data-ttu-id="42ca3-785">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-785">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-786">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-787">駆動のライセンス数</span><span class="sxs-lookup"><span data-stu-id="42ca3-787">driving licence number</span></span>  <br/> <span data-ttu-id="42ca3-788">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-788">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-789">許可を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-789">driving permit</span></span>  <br/> <span data-ttu-id="42ca3-790">駆動の許可番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-790">driving permit number</span></span>  <br/> <span data-ttu-id="42ca3-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="42ca3-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="42ca3-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="42ca3-792">permiso conducción</span></span>  <br/> <span data-ttu-id="42ca3-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="42ca3-794">número de carnet de の conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="42ca3-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="42ca3-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-796">licencia conducir</span></span>  <br/> <span data-ttu-id="42ca3-797">número de permiso de の conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="42ca3-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="42ca3-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="42ca3-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-800">permiso conducir</span></span>  <br/> <span data-ttu-id="42ca3-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="42ca3-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="42ca3-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="42ca3-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="42ca3-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="42ca3-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="42ca3-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="42ca3-805">形式</span><span class="sxs-lookup"><span data-stu-id="42ca3-805">Format</span></span>

<span data-ttu-id="42ca3-806">10 桁の数字、ハイフンを含む</span><span class="sxs-lookup"><span data-stu-id="42ca3-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="42ca3-807">パターン</span><span class="sxs-lookup"><span data-stu-id="42ca3-807">Pattern</span></span>

<span data-ttu-id="42ca3-808">10 個の数字がハイフンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="42ca3-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="42ca3-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-809">Six digits</span></span> 
    
- <span data-ttu-id="42ca3-810">ハイフン</span><span class="sxs-lookup"><span data-stu-id="42ca3-810">A hyphen</span></span>
    
- <span data-ttu-id="42ca3-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="42ca3-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="42ca3-812">チェックサム</span><span class="sxs-lookup"><span data-stu-id="42ca3-812">Checksum</span></span>

<span data-ttu-id="42ca3-813">なし</span><span class="sxs-lookup"><span data-stu-id="42ca3-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="42ca3-814">定義</span><span class="sxs-lookup"><span data-stu-id="42ca3-814">Definition</span></span>

<span data-ttu-id="42ca3-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="42ca3-816">正規表現`Regex_sweden_eu_driver's_license_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="42ca3-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="42ca3-817">キーワードの`Keywords_sweden_eu_driver's_license_number`があります。</span><span class="sxs-lookup"><span data-stu-id="42ca3-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="42ca3-818">Keywords</span><span class="sxs-lookup"><span data-stu-id="42ca3-818">Keywords</span></span>

<span data-ttu-id="42ca3-819">| |</span><span class="sxs-lookup"><span data-stu-id="42ca3-819"></span></span>
|<span data-ttu-id="42ca3-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="42ca3-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="42ca3-821">dl#</span><span class="sxs-lookup"><span data-stu-id="42ca3-821">dl#</span></span>  <br/> <span data-ttu-id="42ca3-822">driver license</span><span class="sxs-lookup"><span data-stu-id="42ca3-822">driver license</span></span>  <br/> <span data-ttu-id="42ca3-823">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-823">driver license number</span></span>  <br/> <span data-ttu-id="42ca3-824">ドライバー ライセンス</span><span class="sxs-lookup"><span data-stu-id="42ca3-824">driver licence</span></span>  <br/> <span data-ttu-id="42ca3-825">lic のドライバーです。</span><span class="sxs-lookup"><span data-stu-id="42ca3-825">drivers lic.</span></span>  <br/> <span data-ttu-id="42ca3-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="42ca3-826">drivers license</span></span>  <br/> <span data-ttu-id="42ca3-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="42ca3-827">drivers licence</span></span>  <br/> <span data-ttu-id="42ca3-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="42ca3-828">driver's license</span></span>  <br/> <span data-ttu-id="42ca3-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="42ca3-829">driver's license number</span></span>  <br/> <span data-ttu-id="42ca3-830">ドライバーのライセンスの数</span><span class="sxs-lookup"><span data-stu-id="42ca3-830">driver's licence number</span></span>  <br/> <span data-ttu-id="42ca3-831">ライセンス番号を推進</span><span class="sxs-lookup"><span data-stu-id="42ca3-831">driving license number</span></span>  <br/> <span data-ttu-id="42ca3-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="42ca3-832">dlno#</span></span>  <br/> <span data-ttu-id="42ca3-833">körkort</span><span class="sxs-lookup"><span data-stu-id="42ca3-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="42ca3-834">英国</span><span class="sxs-lookup"><span data-stu-id="42ca3-834">UK</span></span>

<span data-ttu-id="42ca3-p103">詳細についてを参照してください「英国のドライバーのライセンスの数」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="42ca3-p103">For details, see the section "U.K. Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42ca3-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="42ca3-837">See also</span></span>

[<span data-ttu-id="42ca3-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="42ca3-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

