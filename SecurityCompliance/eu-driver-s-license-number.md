---
title: EU 運転免許証番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: be9497c325866a670dff8d82b5170f4ca947c4ad
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255775"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="b718e-104">EU 運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-104">EU Driver's License Number</span></span>

<span data-ttu-id="b718e-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 運転免許証番号の機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="b718e-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="b718e-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="b718e-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="b718e-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="b718e-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="b718e-108">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-108">Format</span></span>

<span data-ttu-id="b718e-109">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-110">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-110">Pattern</span></span>

<span data-ttu-id="b718e-111">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-112">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-112">Checksum</span></span>

<span data-ttu-id="b718e-113">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-114">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-114">Definition</span></span>

<span data-ttu-id="b718e-115">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-116">正規表現`Regex_austria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-117">from `Keywords_austria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="b718e-118">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-118">Keywords</span></span>

<span data-ttu-id="b718e-119">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-119"></span></span>
|<span data-ttu-id="b718e-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-121">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-121">dl#</span></span>  <br/> <span data-ttu-id="b718e-122">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-122">driver license</span></span>  <br/> <span data-ttu-id="b718e-123">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-123">driver license number</span></span>  <br/> <span data-ttu-id="b718e-124">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-124">driver licence</span></span>  <br/> <span data-ttu-id="b718e-125">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-125">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-126">drivers license</span></span>  <br/> <span data-ttu-id="b718e-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="b718e-127">driver's licence</span></span>  <br/> <span data-ttu-id="b718e-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-128">driver's license</span></span>  <br/> <span data-ttu-id="b718e-129">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-129">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-130">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="b718e-131">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-131">driving license number</span></span>  <br/> <span data-ttu-id="b718e-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-132">dlno#</span></span>  <br/> <span data-ttu-id="b718e-133">futex</span><span class="sxs-lookup"><span data-stu-id="b718e-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="b718e-134">futex (futex) republik osterreich</span><span class="sxs-lookup"><span data-stu-id="b718e-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="b718e-135">ベルギー</span><span class="sxs-lookup"><span data-stu-id="b718e-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="b718e-136">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-136">Format</span></span>

<span data-ttu-id="b718e-137">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-138">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-138">Pattern</span></span>

<span data-ttu-id="b718e-139">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-140">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-140">Checksum</span></span>

<span data-ttu-id="b718e-141">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-142">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-142">Definition</span></span>

<span data-ttu-id="b718e-143">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-144">正規表現`Regex_belgium_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-145">from `Keywords_belgium_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b718e-146">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-146">Keywords</span></span>

<span data-ttu-id="b718e-147">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-147"></span></span>
|<span data-ttu-id="b718e-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-149">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-149">dl#</span></span>  <br/> <span data-ttu-id="b718e-150">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-150">driver license</span></span>  <br/> <span data-ttu-id="b718e-151">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-151">driver license number</span></span>  <br/> <span data-ttu-id="b718e-152">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-152">driver licence</span></span>  <br/> <span data-ttu-id="b718e-153">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-153">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-154">drivers license</span></span>  <br/> <span data-ttu-id="b718e-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-155">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-156">driver's license</span></span>  <br/> <span data-ttu-id="b718e-157">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-157">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-158">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-158">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-159">dlno#</span></span>  <br/> <span data-ttu-id="b718e-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="b718e-160">rijbewijs</span></span>  <br/> <span data-ttu-id="b718e-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="b718e-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="b718e-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="b718e-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="b718e-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="b718e-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="b718e-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="b718e-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="b718e-165">führerschein-nr</span><span class="sxs-lookup"><span data-stu-id="b718e-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="b718e-166">futex の eh/Nr</span><span class="sxs-lookup"><span data-stu-id="b718e-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="b718e-167">futex の eh/nr</span><span class="sxs-lookup"><span data-stu-id="b718e-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="b718e-168">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="b718e-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="b718e-169">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-169">Format</span></span>

<span data-ttu-id="b718e-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-171">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-171">Pattern</span></span>

<span data-ttu-id="b718e-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-173">Checksum</span></span>

<span data-ttu-id="b718e-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-175">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-175">Definition</span></span>

<span data-ttu-id="b718e-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-177">正規表現`Regex_bulgaria_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-178">from `Keywords_bulgaria_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="b718e-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-179">Keywords</span></span>

<span data-ttu-id="b718e-180">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-180"></span></span>
|<span data-ttu-id="b718e-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-182">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-182">dl#</span></span>  <br/> <span data-ttu-id="b718e-183">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-183">driver license</span></span>  <br/> <span data-ttu-id="b718e-184">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-184">driver license number</span></span>  <br/> <span data-ttu-id="b718e-185">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-185">driver licence</span></span>  <br/> <span data-ttu-id="b718e-186">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-186">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-187">drivers license</span></span>  <br/> <span data-ttu-id="b718e-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-188">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-189">driver's license</span></span>  <br/> <span data-ttu-id="b718e-190">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-190">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-191">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-191">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-192">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-192">driving license number</span></span>  <br/> <span data-ttu-id="b718e-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-193">dlno#</span></span>  <br/> <span data-ttu-id="b718e-194">свидетелствозауправлениенампс</span><span class="sxs-lookup"><span data-stu-id="b718e-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="b718e-195">свидетелствозауправлениенамоторнопревозносредство</span><span class="sxs-lookup"><span data-stu-id="b718e-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="b718e-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="b718e-196">сумпс</span></span>  <br/> <span data-ttu-id="b718e-197">шофьорскакнижка</span><span class="sxs-lookup"><span data-stu-id="b718e-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="b718e-198">クロアチア</span><span class="sxs-lookup"><span data-stu-id="b718e-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="b718e-199">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-199">Format</span></span>

<span data-ttu-id="b718e-200">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-201">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-201">Pattern</span></span>

<span data-ttu-id="b718e-202">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-203">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-203">Checksum</span></span>

<span data-ttu-id="b718e-204">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-205">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-205">Definition</span></span>

<span data-ttu-id="b718e-206">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-207">正規表現`Regex_croatia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-208">from `Keywords_croatia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b718e-209">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-209">Keywords</span></span>

<span data-ttu-id="b718e-210">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-210"></span></span>
|<span data-ttu-id="b718e-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-212">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-212">dl#</span></span>  <br/> <span data-ttu-id="b718e-213">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-213">driver license</span></span>  <br/> <span data-ttu-id="b718e-214">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-214">driver license number</span></span>  <br/> <span data-ttu-id="b718e-215">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-215">driver licence</span></span>  <br/> <span data-ttu-id="b718e-216">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-216">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-217">drivers license</span></span>  <br/> <span data-ttu-id="b718e-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-218">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-219">driver's license</span></span>  <br/> <span data-ttu-id="b718e-220">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-220">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-221">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-221">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-222">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-222">driving license number</span></span>  <br/> <span data-ttu-id="b718e-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-223">dlno#</span></span>  <br/> <span data-ttu-id="b718e-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="b718e-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="b718e-225">キプロス</span><span class="sxs-lookup"><span data-stu-id="b718e-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="b718e-226">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-226">Format</span></span>

<span data-ttu-id="b718e-227">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="b718e-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-228">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-228">Pattern</span></span>

<span data-ttu-id="b718e-229">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-230">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-230">Checksum</span></span>

<span data-ttu-id="b718e-231">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-232">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-232">Definition</span></span>

<span data-ttu-id="b718e-233">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-234">正規表現`Regex_cyprus_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-235">from `Keywords_cyprus_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-236">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-236">Keywords</span></span>

<span data-ttu-id="b718e-237">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-237"></span></span>
|<span data-ttu-id="b718e-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-239">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-239">dl#</span></span>  <br/> <span data-ttu-id="b718e-240">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-240">driver license</span></span>  <br/> <span data-ttu-id="b718e-241">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-241">driver license number</span></span>  <br/> <span data-ttu-id="b718e-242">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-242">driver licence</span></span>  <br/> <span data-ttu-id="b718e-243">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-243">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-244">drivers license</span></span>  <br/> <span data-ttu-id="b718e-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-245">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-246">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-246">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-247">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-247">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-248">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-248">driving license number</span></span>  <br/> <span data-ttu-id="b718e-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-249">dlno#</span></span>  <br/> <span data-ttu-id="b718e-250">άδειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="b718e-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="b718e-251">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="b718e-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="b718e-252">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-252">Format</span></span>

<span data-ttu-id="b718e-253">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-254">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-254">Pattern</span></span>

<span data-ttu-id="b718e-255">8つの文字と数字:</span><span class="sxs-lookup"><span data-stu-id="b718e-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="b718e-256">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="b718e-257">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="b718e-257">A space (optional)</span></span>
    
- <span data-ttu-id="b718e-258">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-259">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-259">Checksum</span></span>

<span data-ttu-id="b718e-260">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-261">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-261">Definition</span></span>

<span data-ttu-id="b718e-262">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-263">正規表現`Regex_czech_republic_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-264">from `Keywords_czech_republic_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b718e-265">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-265">Keywords</span></span>

<span data-ttu-id="b718e-266">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-266"></span></span>
|<span data-ttu-id="b718e-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-268">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-268">dl#</span></span>  <br/> <span data-ttu-id="b718e-269">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-269">driver license</span></span>  <br/> <span data-ttu-id="b718e-270">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-270">driver license number</span></span>  <br/> <span data-ttu-id="b718e-271">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-271">driver licence</span></span>  <br/> <span data-ttu-id="b718e-272">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-272">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-273">drivers license</span></span>  <br/> <span data-ttu-id="b718e-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-274">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-275">driver's license</span></span>  <br/> <span data-ttu-id="b718e-276">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-276">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-277">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-277">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-278">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-278">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-279">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-279">driving license number</span></span>  <br/> <span data-ttu-id="b718e-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-280">dlno#</span></span>  <br/> <span data-ttu-id="b718e-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="b718e-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="b718e-282">デンマーク</span><span class="sxs-lookup"><span data-stu-id="b718e-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="b718e-283">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-283">Format</span></span>

<span data-ttu-id="b718e-284">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-285">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-285">Pattern</span></span>

<span data-ttu-id="b718e-286">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-287">Checksum</span></span>

<span data-ttu-id="b718e-288">はい</span><span class="sxs-lookup"><span data-stu-id="b718e-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-289">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-289">Definition</span></span>

<span data-ttu-id="b718e-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-291">正規表現`Regex_denmark_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-292">from `Keywords_denmark_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b718e-293">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-293">Keywords</span></span>

<span data-ttu-id="b718e-294">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-294"></span></span>
|<span data-ttu-id="b718e-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-296">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-296">dl#</span></span>  <br/> <span data-ttu-id="b718e-297">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-297">driver license</span></span>  <br/> <span data-ttu-id="b718e-298">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-298">driver license number</span></span>  <br/> <span data-ttu-id="b718e-299">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-299">driver licence</span></span>  <br/> <span data-ttu-id="b718e-300">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-300">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-301">drivers license</span></span>  <br/> <span data-ttu-id="b718e-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-302">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-303">driver's license</span></span>  <br/> <span data-ttu-id="b718e-304">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-304">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-305">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-305">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-306">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-306">driving license number</span></span>  <br/> <span data-ttu-id="b718e-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-307">dlno#</span></span>  <br/> <span data-ttu-id="b718e-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="b718e-308">kørekort</span></span>  <br/> <span data-ttu-id="b718e-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="b718e-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="b718e-310">エストニア</span><span class="sxs-lookup"><span data-stu-id="b718e-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="b718e-311">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-311">Format</span></span>

<span data-ttu-id="b718e-312">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-313">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-313">Pattern</span></span>

<span data-ttu-id="b718e-314">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b718e-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="b718e-315">文字 "ET" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b718e-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-317">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-317">Checksum</span></span>

<span data-ttu-id="b718e-318">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-319">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-319">Definition</span></span>

<span data-ttu-id="b718e-320">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-321">正規表現`Regex_estonia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-322">from `Keywords_estonia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-323">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-323">Keywords</span></span>

<span data-ttu-id="b718e-324">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-324"></span></span>
|<span data-ttu-id="b718e-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-326">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-326">dl#</span></span>  <br/> <span data-ttu-id="b718e-327">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-327">driver license</span></span>  <br/> <span data-ttu-id="b718e-328">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-328">driver license number</span></span>  <br/> <span data-ttu-id="b718e-329">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-329">driver license number</span></span>  <br/> <span data-ttu-id="b718e-330">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-330">driver licence</span></span>  <br/> <span data-ttu-id="b718e-331">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-331">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-332">drivers license</span></span>  <br/> <span data-ttu-id="b718e-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-333">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-334">driver's license</span></span>  <br/> <span data-ttu-id="b718e-335">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-335">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-336">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-336">driving license number</span></span>  <br/> <span data-ttu-id="b718e-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-337">dlno#</span></span>  <br/> <span data-ttu-id="b718e-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="b718e-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="b718e-339">フィンランド</span><span class="sxs-lookup"><span data-stu-id="b718e-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="b718e-340">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-340">Format</span></span>

<span data-ttu-id="b718e-341">ハイフンを 1 つ含む 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-342">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-342">Pattern</span></span>

<span data-ttu-id="b718e-343">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b718e-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="b718e-344">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-344">Six digits</span></span> 
    
- <span data-ttu-id="b718e-345">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="b718e-345">A hyphen</span></span>
    
-  <span data-ttu-id="b718e-346">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b718e-347">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-347">Checksum</span></span>

<span data-ttu-id="b718e-348">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-349">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-349">Definition</span></span>

<span data-ttu-id="b718e-350">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-351">正規表現`Regex_finland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-352">from `Keywords_finland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-353">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-353">Keywords</span></span>

<span data-ttu-id="b718e-354">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-354"></span></span>
|<span data-ttu-id="b718e-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-356">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-356">dl#</span></span>  <br/> <span data-ttu-id="b718e-357">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-357">driver license</span></span>  <br/> <span data-ttu-id="b718e-358">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-358">driver license number</span></span>  <br/> <span data-ttu-id="b718e-359">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-359">driver licence</span></span>  <br/> <span data-ttu-id="b718e-360">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-360">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-361">drivers license</span></span>  <br/> <span data-ttu-id="b718e-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-362">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-363">driver's license</span></span>  <br/> <span data-ttu-id="b718e-364">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-364">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-365">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-365">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-366">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-366">driving license number</span></span>  <br/> <span data-ttu-id="b718e-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-367">dlno#</span></span>  <br/> <span data-ttu-id="b718e-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="b718e-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="b718e-369">フランス</span><span class="sxs-lookup"><span data-stu-id="b718e-369">France</span></span>

<span data-ttu-id="b718e-370">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b718e-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="b718e-371">ドイツ</span><span class="sxs-lookup"><span data-stu-id="b718e-371">Germany</span></span>

<span data-ttu-id="b718e-372">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」に記載されている「ドイツの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b718e-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="b718e-373">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="b718e-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="b718e-374">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-374">Format</span></span>

<span data-ttu-id="b718e-375">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-376">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-376">Pattern</span></span>

 <span data-ttu-id="b718e-377">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b718e-378">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-378">Checksum</span></span>

<span data-ttu-id="b718e-379">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-380">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-380">Definition</span></span>

<span data-ttu-id="b718e-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-382">正規表現`Regex_greece_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-383">from `Keywords_greece_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-384">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-384">Keywords</span></span>

<span data-ttu-id="b718e-385">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-385"></span></span>
|<span data-ttu-id="b718e-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-387">ライブラリ</span><span class="sxs-lookup"><span data-stu-id="b718e-387">dlL#</span></span>  <br/> <span data-ttu-id="b718e-388">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-388">driver license</span></span>  <br/> <span data-ttu-id="b718e-389">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-389">driver license number</span></span>  <br/> <span data-ttu-id="b718e-390">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-390">driver licence</span></span>  <br/> <span data-ttu-id="b718e-391">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-391">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-392">drivers license</span></span>  <br/> <span data-ttu-id="b718e-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-393">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-394">driver's license</span></span>  <br/> <span data-ttu-id="b718e-395">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-395">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-396">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-396">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-397">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-397">driving license number</span></span>  <br/> <span data-ttu-id="b718e-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-398">dlno#</span></span>  <br/> <span data-ttu-id="b718e-399">δειαοδήγησης</span><span class="sxs-lookup"><span data-stu-id="b718e-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="b718e-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="b718e-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="b718e-401">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="b718e-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="b718e-402">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-402">Format</span></span>

<span data-ttu-id="b718e-403">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-404">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-404">Pattern</span></span>

<span data-ttu-id="b718e-405">2つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b718e-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="b718e-406">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b718e-407">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-408">Checksum</span></span>

<span data-ttu-id="b718e-409">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-410">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-410">Definition</span></span>

<span data-ttu-id="b718e-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-412">正規表現`Regex_hungary_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-413">from `Keywords_hungary_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-414">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-414">Keywords</span></span>

<span data-ttu-id="b718e-415">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-415"></span></span>
|<span data-ttu-id="b718e-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-417">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-417">dl#</span></span>  <br/> <span data-ttu-id="b718e-418">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-418">driver license</span></span>  <br/> <span data-ttu-id="b718e-419">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-419">driver license number</span></span>  <br/> <span data-ttu-id="b718e-420">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-420">driver licence</span></span>  <br/> <span data-ttu-id="b718e-421">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-421">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-422">drivers license</span></span>  <br/> <span data-ttu-id="b718e-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-423">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-424">driver's license</span></span>  <br/> <span data-ttu-id="b718e-425">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-425">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-426">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-426">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-427">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-427">driving license number</span></span>  <br/> <span data-ttu-id="b718e-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-428">dlno#</span></span>  <br/> <span data-ttu-id="b718e-429">vezetoi engedely</span><span class="sxs-lookup"><span data-stu-id="b718e-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="b718e-430">アイルランド</span><span class="sxs-lookup"><span data-stu-id="b718e-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="b718e-431">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-431">Format</span></span>

<span data-ttu-id="b718e-432">6桁の数字の後に4文字</span><span class="sxs-lookup"><span data-stu-id="b718e-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-433">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-433">Pattern</span></span>

<span data-ttu-id="b718e-434">6桁の数字と4文字:</span><span class="sxs-lookup"><span data-stu-id="b718e-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="b718e-435">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-435">Six digits</span></span>
    
- <span data-ttu-id="b718e-436">4桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-437">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-437">Checksum</span></span>

<span data-ttu-id="b718e-438">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-439">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-439">Definition</span></span>

<span data-ttu-id="b718e-440">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-441">正規表現`Regex_ireland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-442">from `Keywords_ireland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-443">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-443">Keywords</span></span>

<span data-ttu-id="b718e-444">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-444"></span></span>
|<span data-ttu-id="b718e-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-446">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-446">dl#</span></span>  <br/> <span data-ttu-id="b718e-447">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-447">driver license</span></span>  <br/> <span data-ttu-id="b718e-448">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-448">driver license number</span></span>  <br/> <span data-ttu-id="b718e-449">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-449">driver licence</span></span>  <br/> <span data-ttu-id="b718e-450">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-450">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-451">drivers license</span></span>  <br/> <span data-ttu-id="b718e-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-452">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-453">driver's license</span></span>  <br/> <span data-ttu-id="b718e-454">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-454">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-455">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-455">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-456">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-456">driving license number</span></span>  <br/> <span data-ttu-id="b718e-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-457">dlno#</span></span>  <br/> <span data-ttu-id="b718e-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="b718e-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="b718e-459">イタリア</span><span class="sxs-lookup"><span data-stu-id="b718e-459">Italy</span></span>

<span data-ttu-id="b718e-460">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「イタリアの運転免許証番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b718e-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="b718e-461">ラトビア</span><span class="sxs-lookup"><span data-stu-id="b718e-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="b718e-462">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-462">Format</span></span>

<span data-ttu-id="b718e-463">3つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-464">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-464">Pattern</span></span>

<span data-ttu-id="b718e-465">3つの文字と6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b718e-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="b718e-466">3桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b718e-467">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-468">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-468">Checksum</span></span>

<span data-ttu-id="b718e-469">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-470">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-470">Definition</span></span>

<span data-ttu-id="b718e-471">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-472">正規表現`Regex_latvia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-473">from `Keywords_latvia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-474">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-474">Keywords</span></span>

<span data-ttu-id="b718e-475">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-475"></span></span>
|<span data-ttu-id="b718e-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-477">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-477">dl#</span></span>  <br/> <span data-ttu-id="b718e-478">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-478">driver license</span></span>  <br/> <span data-ttu-id="b718e-479">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-479">driver license number</span></span>  <br/> <span data-ttu-id="b718e-480">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-480">driver licence</span></span>  <br/> <span data-ttu-id="b718e-481">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-481">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-482">drivers license</span></span>  <br/> <span data-ttu-id="b718e-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-483">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-484">driver's license</span></span>  <br/> <span data-ttu-id="b718e-485">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-485">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-486">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-486">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-487">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-487">driving license number</span></span>  <br/> <span data-ttu-id="b718e-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-488">dlno#</span></span>  <br/> <span data-ttu-id="b718e-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="b718e-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="b718e-490">リトアニア</span><span class="sxs-lookup"><span data-stu-id="b718e-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="b718e-491">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-491">Format</span></span>

<span data-ttu-id="b718e-492">スペースと区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-493">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-493">Pattern</span></span>

 <span data-ttu-id="b718e-494">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b718e-495">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-495">Checksum</span></span>

<span data-ttu-id="b718e-496">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-497">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-497">Definition</span></span>

<span data-ttu-id="b718e-498">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-499">正規表現`Regex_lithuania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-500">from `Keywords_lithuania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-501">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-501">Keywords</span></span>

<span data-ttu-id="b718e-502">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-502"></span></span>
|<span data-ttu-id="b718e-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-504">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-504">dl#</span></span>  <br/> <span data-ttu-id="b718e-505">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-505">driver license</span></span>  <br/> <span data-ttu-id="b718e-506">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-506">driver license number</span></span>  <br/> <span data-ttu-id="b718e-507">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-507">driver licence</span></span>  <br/> <span data-ttu-id="b718e-508">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-508">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-509">drivers license</span></span>  <br/> <span data-ttu-id="b718e-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-510">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-511">driver's license</span></span>  <br/> <span data-ttu-id="b718e-512">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-512">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-513">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-513">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-514">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-514">driving license number</span></span>  <br/> <span data-ttu-id="b718e-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-515">dlno#</span></span>  <br/> <span data-ttu-id="b718e-516">vエア uotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="b718e-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="b718e-517">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="b718e-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="b718e-518">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-518">Format</span></span>

<span data-ttu-id="b718e-519">スペースと区切り文字を含まない6桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-520">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-520">Pattern</span></span>

 <span data-ttu-id="b718e-521">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b718e-522">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-522">Checksum</span></span>

<span data-ttu-id="b718e-523">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-524">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-524">Definition</span></span>

<span data-ttu-id="b718e-525">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-526">正規表現`Regex_luxemburg_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-527">from `Keywords_luxemburg_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-528">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-528">Keywords</span></span>

<span data-ttu-id="b718e-529">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-529"></span></span>
|<span data-ttu-id="b718e-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-531">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-531">dl#</span></span>  <br/> <span data-ttu-id="b718e-532">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-532">driver license</span></span>  <br/> <span data-ttu-id="b718e-533">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-533">driver license number</span></span>  <br/> <span data-ttu-id="b718e-534">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-534">driver licence</span></span>  <br/> <span data-ttu-id="b718e-535">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-535">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-536">drivers license</span></span>  <br/> <span data-ttu-id="b718e-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-537">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-538">driver's license</span></span>  <br/> <span data-ttu-id="b718e-539">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-539">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-540">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-540">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-541">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-541">driving license number</span></span>  <br/> <span data-ttu-id="b718e-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-542">dlno#</span></span>  <br/> <span data-ttu-id="b718e-543">fahて fabnis</span><span class="sxs-lookup"><span data-stu-id="b718e-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="b718e-544">マルタ</span><span class="sxs-lookup"><span data-stu-id="b718e-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="b718e-545">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-545">Format</span></span>

<span data-ttu-id="b718e-546">指定したパターンの2つの文字と6桁の数字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="b718e-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-547">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-547">Pattern</span></span>

<span data-ttu-id="b718e-548">2つの文字と6桁の数字の組み合わせ:</span><span class="sxs-lookup"><span data-stu-id="b718e-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="b718e-549">2つの文字 (大文字小文字を区別しない数字または文字)</span><span class="sxs-lookup"><span data-stu-id="b718e-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="b718e-550">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="b718e-550">A space (optional)</span></span>
    
- <span data-ttu-id="b718e-551">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-551">Three digits</span></span>
    
- <span data-ttu-id="b718e-552">スペース 1 つ (省略可能) </span><span class="sxs-lookup"><span data-stu-id="b718e-552">A space (optional)</span></span>
    
- <span data-ttu-id="b718e-553">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-554">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-554">Checksum</span></span>

<span data-ttu-id="b718e-555">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-556">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-556">Definition</span></span>

<span data-ttu-id="b718e-557">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-558">正規表現`Regex_malta_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-559">from `Keywords_malta_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-560">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-560">Keywords</span></span>

<span data-ttu-id="b718e-561">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-561"></span></span>
|<span data-ttu-id="b718e-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-563">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-563">dl#</span></span>  <br/> <span data-ttu-id="b718e-564">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-564">driver license</span></span>  <br/> <span data-ttu-id="b718e-565">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-565">driver license number</span></span>  <br/> <span data-ttu-id="b718e-566">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-566">driver licence</span></span>  <br/> <span data-ttu-id="b718e-567">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-567">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-568">drivers license</span></span>  <br/> <span data-ttu-id="b718e-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-569">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-570">driver's license</span></span>  <br/> <span data-ttu-id="b718e-571">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-571">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-572">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-572">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-573">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-573">driving license number</span></span>  <br/> <span data-ttu-id="b718e-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-574">dlno#</span></span>  <br/> <span data-ttu-id="b718e-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="b718e-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="b718e-576">オランダ</span><span class="sxs-lookup"><span data-stu-id="b718e-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="b718e-577">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-577">Format</span></span>

<span data-ttu-id="b718e-578">スペースと区切り文字を含まない10桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-579">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-579">Pattern</span></span>

<span data-ttu-id="b718e-580">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-581">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-581">Checksum</span></span>

<span data-ttu-id="b718e-582">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-583">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-583">Definition</span></span>

<span data-ttu-id="b718e-584">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-585">正規表現`Regex_netherlands_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-586">from `Keywords_netherlands_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-587">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-587">Keywords</span></span>

<span data-ttu-id="b718e-588">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-588"></span></span>
|<span data-ttu-id="b718e-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-590">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-590">dl#</span></span>  <br/> <span data-ttu-id="b718e-591">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-591">driver license</span></span>  <br/> <span data-ttu-id="b718e-592">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-592">driver license number</span></span>  <br/> <span data-ttu-id="b718e-593">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-593">driver licence</span></span>  <br/> <span data-ttu-id="b718e-594">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-594">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-595">drivers license</span></span>  <br/> <span data-ttu-id="b718e-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-596">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-597">driver's license</span></span>  <br/> <span data-ttu-id="b718e-598">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-598">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-599">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-599">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-600">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-600">driving license number</span></span>  <br/> <span data-ttu-id="b718e-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-601">dlno#</span></span>  <br/> <span data-ttu-id="b718e-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="b718e-602">permis de conduire</span></span>  <br/> <span data-ttu-id="b718e-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="b718e-603">rijbewijs</span></span>  <br/> <span data-ttu-id="b718e-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="b718e-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="b718e-605">ポーランド</span><span class="sxs-lookup"><span data-stu-id="b718e-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="b718e-606">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-606">Format</span></span>

<span data-ttu-id="b718e-607">2つのスラッシュを含む14桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-608">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-608">Pattern</span></span>

<span data-ttu-id="b718e-609">14桁の数字と2つのスラッシュ:</span><span class="sxs-lookup"><span data-stu-id="b718e-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="b718e-610">5 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-610">Five digits</span></span> 
    
- <span data-ttu-id="b718e-611">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="b718e-611">A forward slash</span></span>
    
- <span data-ttu-id="b718e-612">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-612">Two digits</span></span>
    
- <span data-ttu-id="b718e-613">スラッシュ 1 つ </span><span class="sxs-lookup"><span data-stu-id="b718e-613">A forward slash</span></span>
    
- <span data-ttu-id="b718e-614">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-615">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-615">Checksum</span></span>

<span data-ttu-id="b718e-616">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-617">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-617">Definition</span></span>

<span data-ttu-id="b718e-618">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-619">正規表現`Regex_poland_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-620">from `Keywords_poland_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-621">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-621">Keywords</span></span>

<span data-ttu-id="b718e-622">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-622"></span></span>
|<span data-ttu-id="b718e-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-624">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-624">dl#</span></span>  <br/> <span data-ttu-id="b718e-625">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-625">driver license</span></span>  <br/> <span data-ttu-id="b718e-626">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-626">driver license number</span></span>  <br/> <span data-ttu-id="b718e-627">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-627">driver licence</span></span>  <br/> <span data-ttu-id="b718e-628">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-628">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-629">drivers license</span></span>  <br/> <span data-ttu-id="b718e-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-630">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-631">driver's license</span></span>  <br/> <span data-ttu-id="b718e-632">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-632">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-633">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-633">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-634">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-634">driving license number</span></span>  <br/> <span data-ttu-id="b718e-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-635">dlno#</span></span>  <br/> <span data-ttu-id="b718e-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="b718e-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="b718e-637">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="b718e-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="b718e-638">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-638">Format</span></span>

<span data-ttu-id="b718e-639">指定したパターンの2文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-640">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-640">Pattern</span></span>

<span data-ttu-id="b718e-641">2つの文字の後に特殊文字を含む7個の数字。</span><span class="sxs-lookup"><span data-stu-id="b718e-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="b718e-642">2桁の文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b718e-643">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="b718e-643">A hyphen</span></span>
    
- <span data-ttu-id="b718e-644">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-644">Six digits</span></span>
    
- <span data-ttu-id="b718e-645">スペース</span><span class="sxs-lookup"><span data-stu-id="b718e-645">A space</span></span>
    
- <span data-ttu-id="b718e-646">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-647">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-647">Checksum</span></span>

<span data-ttu-id="b718e-648">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-649">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-649">Definition</span></span>

<span data-ttu-id="b718e-650">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-651">正規表現`Regex_portugal_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-652">from `Keywords_portugal_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-653">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-653">Keywords</span></span>

<span data-ttu-id="b718e-654">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-654"></span></span>
|<span data-ttu-id="b718e-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-656">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-656">dl#</span></span>  <br/> <span data-ttu-id="b718e-657">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-657">driver license</span></span>  <br/> <span data-ttu-id="b718e-658">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-658">driver license number</span></span>  <br/> <span data-ttu-id="b718e-659">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-659">driver licence</span></span>  <br/> <span data-ttu-id="b718e-660">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-660">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-661">drivers license</span></span>  <br/> <span data-ttu-id="b718e-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-662">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-663">driver's license</span></span>  <br/> <span data-ttu-id="b718e-664">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-664">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-665">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-665">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-666">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-666">driving license number</span></span>  <br/> <span data-ttu-id="b718e-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-667">dlno#</span></span>  <br/> <span data-ttu-id="b718e-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="b718e-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="b718e-669">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="b718e-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="b718e-670">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-670">Format</span></span>

<span data-ttu-id="b718e-671">1文字の後に8桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-672">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-672">Pattern</span></span>

<span data-ttu-id="b718e-673">1文字の後に8桁の数字。</span><span class="sxs-lookup"><span data-stu-id="b718e-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="b718e-674">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="b718e-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="b718e-675">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-676">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-676">Checksum</span></span>

<span data-ttu-id="b718e-677">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-678">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-678">Definition</span></span>

<span data-ttu-id="b718e-679">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-680">正規表現`Regex_romania_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-681">from `Keywords_romania_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-682">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-682">Keywords</span></span>

<span data-ttu-id="b718e-683">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-683"></span></span>
|<span data-ttu-id="b718e-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-685">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-685">dl#</span></span>  <br/> <span data-ttu-id="b718e-686">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-686">driver license</span></span>  <br/> <span data-ttu-id="b718e-687">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-687">driver license number</span></span>  <br/> <span data-ttu-id="b718e-688">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-688">driver licence</span></span>  <br/> <span data-ttu-id="b718e-689">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-689">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-690">drivers license</span></span>  <br/> <span data-ttu-id="b718e-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-691">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-692">driver's license</span></span>  <br/> <span data-ttu-id="b718e-693">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-693">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-694">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-694">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-695">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-695">driving license number</span></span>  <br/> <span data-ttu-id="b718e-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-696">dlno#</span></span>  <br/> <span data-ttu-id="b718e-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="b718e-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="b718e-698">スロバキア</span><span class="sxs-lookup"><span data-stu-id="b718e-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="b718e-699">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-699">Format</span></span>

<span data-ttu-id="b718e-700">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-701">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-701">Pattern</span></span>

<span data-ttu-id="b718e-702">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="b718e-703">1文字 (大文字小文字を区別しない) または数字</span><span class="sxs-lookup"><span data-stu-id="b718e-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="b718e-704">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b718e-705">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-705">Checksum</span></span>

<span data-ttu-id="b718e-706">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-707">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-707">Definition</span></span>

<span data-ttu-id="b718e-708">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-709">正規表現`Regex_slovakia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-710">from `Keywords_slovakia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-711">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-711">Keywords</span></span>

<span data-ttu-id="b718e-712">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-712"></span></span>
|<span data-ttu-id="b718e-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-714">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-714">dl#</span></span>  <br/> <span data-ttu-id="b718e-715">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-715">driver license</span></span>  <br/> <span data-ttu-id="b718e-716">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-716">driver license number</span></span>  <br/> <span data-ttu-id="b718e-717">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-717">driver licence</span></span>  <br/> <span data-ttu-id="b718e-718">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-718">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-719">drivers license</span></span>  <br/> <span data-ttu-id="b718e-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-720">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-721">driver's license</span></span>  <br/> <span data-ttu-id="b718e-722">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-722">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-723">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-723">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-724">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-724">driving license number</span></span>  <br/> <span data-ttu-id="b718e-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-725">dlno#</span></span>  <br/> <span data-ttu-id="b718e-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="b718e-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="b718e-727">スロベニア</span><span class="sxs-lookup"><span data-stu-id="b718e-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="b718e-728">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-728">Format</span></span>

<span data-ttu-id="b718e-729">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-730">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-730">Pattern</span></span>

<span data-ttu-id="b718e-731">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b718e-732">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-732">Checksum</span></span>

<span data-ttu-id="b718e-733">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-734">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-734">Definition</span></span>

<span data-ttu-id="b718e-735">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-736">正規表現`Regex_slovenia_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-737">from `Keywords_slovenia_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-738">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-738">Keywords</span></span>

<span data-ttu-id="b718e-739">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-739"></span></span>
|<span data-ttu-id="b718e-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-741">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-741">dl#</span></span>  <br/> <span data-ttu-id="b718e-742">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-742">driver license</span></span>  <br/> <span data-ttu-id="b718e-743">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-743">driver license number</span></span>  <br/> <span data-ttu-id="b718e-744">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-744">driver licence</span></span>  <br/> <span data-ttu-id="b718e-745">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-745">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-746">drivers license</span></span>  <br/> <span data-ttu-id="b718e-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-747">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-748">driver's license</span></span>  <br/> <span data-ttu-id="b718e-749">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-749">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-750">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-750">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-751">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-751">driving license number</span></span>  <br/> <span data-ttu-id="b718e-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-752">dlno#</span></span>  <br/> <span data-ttu-id="b718e-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="b718e-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="b718e-754">スペイン</span><span class="sxs-lookup"><span data-stu-id="b718e-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="b718e-755">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-755">Format</span></span>

<span data-ttu-id="b718e-756">8桁の数字の後に1つの文字</span><span class="sxs-lookup"><span data-stu-id="b718e-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-757">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-757">Pattern</span></span>

<span data-ttu-id="b718e-758">8桁の数字の後に1文字。</span><span class="sxs-lookup"><span data-stu-id="b718e-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="b718e-759">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-759">Eight digits</span></span> 
    
- <span data-ttu-id="b718e-760">1桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="b718e-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-761">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-761">Checksum</span></span>

<span data-ttu-id="b718e-762">はい</span><span class="sxs-lookup"><span data-stu-id="b718e-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-763">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-763">Definition</span></span>

<span data-ttu-id="b718e-764">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-765">関数`Func_spain_eu_driver's_license_number`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="b718e-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-766">from `Keywords_spain_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b718e-767">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-767">Keywords</span></span>

<span data-ttu-id="b718e-768">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-768"></span></span>
|<span data-ttu-id="b718e-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-770">dlno#</span></span>  <br/> <span data-ttu-id="b718e-771">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-771">dl#</span></span>  <br/> <span data-ttu-id="b718e-772">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-772">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-773">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-773">driver licence</span></span>  <br/> <span data-ttu-id="b718e-774">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-774">driver license</span></span>  <br/> <span data-ttu-id="b718e-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-775">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-776">drivers license</span></span>  <br/> <span data-ttu-id="b718e-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="b718e-777">driver's licence</span></span>  <br/> <span data-ttu-id="b718e-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-778">driver's license</span></span>  <br/> <span data-ttu-id="b718e-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="b718e-779">driving licence</span></span>  <br/> <span data-ttu-id="b718e-780">driving license</span><span class="sxs-lookup"><span data-stu-id="b718e-780">driving license</span></span>  <br/> <span data-ttu-id="b718e-781">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-781">driver licence number</span></span>  <br/> <span data-ttu-id="b718e-782">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-782">driver license number</span></span>  <br/> <span data-ttu-id="b718e-783">ドライバーライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-783">drivers licence number</span></span>  <br/> <span data-ttu-id="b718e-784">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-784">drivers license number</span></span>  <br/> <span data-ttu-id="b718e-785">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-785">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-786">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-786">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-787">ライセンス番号の運転</span><span class="sxs-lookup"><span data-stu-id="b718e-787">driving licence number</span></span>  <br/> <span data-ttu-id="b718e-788">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-788">driving license number</span></span>  <br/> <span data-ttu-id="b718e-789">許可の推進</span><span class="sxs-lookup"><span data-stu-id="b718e-789">driving permit</span></span>  <br/> <span data-ttu-id="b718e-790">許可番号の運転</span><span class="sxs-lookup"><span data-stu-id="b718e-790">driving permit number</span></span>  <br/> <span data-ttu-id="b718e-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="b718e-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="b718e-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="b718e-792">permiso conducción</span></span>  <br/> <span data-ttu-id="b718e-793">número/encia conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="b718e-794">número デカーネット de conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="b718e-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="b718e-796">/暗号化 ia conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-796">licencia conducir</span></span>  <br/> <span data-ttu-id="b718e-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="b718e-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="b718e-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="b718e-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-800">permiso conducir</span></span>  <br/> <span data-ttu-id="b718e-801">-encia de manejo</span><span class="sxs-lookup"><span data-stu-id="b718e-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="b718e-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="b718e-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="b718e-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="b718e-804">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="b718e-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="b718e-805">Format</span><span class="sxs-lookup"><span data-stu-id="b718e-805">Format</span></span>

<span data-ttu-id="b718e-806">10桁の数字 (ハイフンを含む)</span><span class="sxs-lookup"><span data-stu-id="b718e-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b718e-807">パターン</span><span class="sxs-lookup"><span data-stu-id="b718e-807">Pattern</span></span>

<span data-ttu-id="b718e-808">ハイフンを含む10桁の数字:</span><span class="sxs-lookup"><span data-stu-id="b718e-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="b718e-809">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-809">Six digits</span></span> 
    
- <span data-ttu-id="b718e-810">ハイフン 1 つ</span><span class="sxs-lookup"><span data-stu-id="b718e-810">A hyphen</span></span>
    
- <span data-ttu-id="b718e-811">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="b718e-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b718e-812">チェックサム</span><span class="sxs-lookup"><span data-stu-id="b718e-812">Checksum</span></span>

<span data-ttu-id="b718e-813">いいえ</span><span class="sxs-lookup"><span data-stu-id="b718e-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b718e-814">定義</span><span class="sxs-lookup"><span data-stu-id="b718e-814">Definition</span></span>

<span data-ttu-id="b718e-815">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="b718e-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b718e-816">正規表現`Regex_sweden_eu_driver's_license_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="b718e-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b718e-817">from `Keywords_sweden_eu_driver's_license_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="b718e-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="b718e-818">キーワード</span><span class="sxs-lookup"><span data-stu-id="b718e-818">Keywords</span></span>

<span data-ttu-id="b718e-819">| |</span><span class="sxs-lookup"><span data-stu-id="b718e-819"></span></span>
|<span data-ttu-id="b718e-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="b718e-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b718e-821">dl</span><span class="sxs-lookup"><span data-stu-id="b718e-821">dl#</span></span>  <br/> <span data-ttu-id="b718e-822">driver license</span><span class="sxs-lookup"><span data-stu-id="b718e-822">driver license</span></span>  <br/> <span data-ttu-id="b718e-823">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-823">driver license number</span></span>  <br/> <span data-ttu-id="b718e-824">ドライバーのライセンス</span><span class="sxs-lookup"><span data-stu-id="b718e-824">driver licence</span></span>  <br/> <span data-ttu-id="b718e-825">ドライバー lic</span><span class="sxs-lookup"><span data-stu-id="b718e-825">drivers lic.</span></span>  <br/> <span data-ttu-id="b718e-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="b718e-826">drivers license</span></span>  <br/> <span data-ttu-id="b718e-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b718e-827">drivers licence</span></span>  <br/> <span data-ttu-id="b718e-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="b718e-828">driver's license</span></span>  <br/> <span data-ttu-id="b718e-829">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-829">driver's license number</span></span>  <br/> <span data-ttu-id="b718e-830">ドライバーのライセンス番号</span><span class="sxs-lookup"><span data-stu-id="b718e-830">driver's licence number</span></span>  <br/> <span data-ttu-id="b718e-831">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="b718e-831">driving license number</span></span>  <br/> <span data-ttu-id="b718e-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="b718e-832">dlno#</span></span>  <br/> <span data-ttu-id="b718e-833">körkort</span><span class="sxs-lookup"><span data-stu-id="b718e-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="b718e-834">佐賀</span><span class="sxs-lookup"><span data-stu-id="b718e-834">UK</span></span>

<span data-ttu-id="b718e-835">詳細については、「英国</span><span class="sxs-lookup"><span data-stu-id="b718e-835">For details, see the section "U.K.</span></span> <span data-ttu-id="b718e-836">[[機密情報の種類](what-the-sensitive-information-types-look-for.md)] に表示される運転免許証番号。</span><span class="sxs-lookup"><span data-stu-id="b718e-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b718e-837">関連項目</span><span class="sxs-lookup"><span data-stu-id="b718e-837">See also</span></span>

[<span data-ttu-id="b718e-838">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="b718e-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

