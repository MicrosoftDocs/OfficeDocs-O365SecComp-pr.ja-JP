---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU パスポート番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 71acc39b885c057e1771ec13b2f3c25017ac1bb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532233"
---
# <a name="eu-passport-number"></a><span data-ttu-id="828ce-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-104">EU Passport Number</span></span>

<span data-ttu-id="828ce-p102">このトピックでは、データ損失防止 (DLP) ポリシーがどの EU パスポート番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。</span><span class="sxs-lookup"><span data-stu-id="828ce-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="828ce-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="828ce-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="828ce-108">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-108">Format</span></span>

<span data-ttu-id="828ce-109">省略可能なスペースと 7 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-110">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-110">Pattern</span></span>

<span data-ttu-id="828ce-111">1 つの文字、7 桁の数字、およびスペースを 1 つの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="828ce-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="828ce-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="828ce-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="828ce-113">1 つのスペース (省略可能)</span><span class="sxs-lookup"><span data-stu-id="828ce-113">One space (optional)</span></span>
    
- <span data-ttu-id="828ce-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-115">Checksum</span></span>

<span data-ttu-id="828ce-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="828ce-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-117">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-117">Definition</span></span>

<span data-ttu-id="828ce-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-119">正規表現`Regex_austria_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-120">キーワードの`Keywords_austria_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-121">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-121">Keywords</span></span>

<span data-ttu-id="828ce-122">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-122"></span></span>
|<span data-ttu-id="828ce-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-124">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-124">passport number</span></span>  <br/> <span data-ttu-id="828ce-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-125">austrian passport number</span></span>  <br/> <span data-ttu-id="828ce-126">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-126">passport no</span></span>  <br/> <span data-ttu-id="828ce-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="828ce-127">reisepass</span></span>  <br/> <span data-ttu-id="828ce-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="828ce-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="828ce-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="828ce-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="828ce-130">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-130">Format</span></span>

<span data-ttu-id="828ce-131">スペースや区切り文字なしで 6 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-132">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-132">Pattern</span></span>

<span data-ttu-id="828ce-133">2 文字 6 桁の後に、</span><span class="sxs-lookup"><span data-stu-id="828ce-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-134">Checksum</span></span>

<span data-ttu-id="828ce-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="828ce-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-136">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-136">Definition</span></span>

<span data-ttu-id="828ce-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-138">正規表現`Regex_belgium_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-139">キーワードの`Keywords_belgium_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-140">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-140">Keywords</span></span>

<span data-ttu-id="828ce-141">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-141"></span></span>
|<span data-ttu-id="828ce-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-143">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-143">passport number</span></span>  <br/> <span data-ttu-id="828ce-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-144">belgian passport number</span></span>  <br/> <span data-ttu-id="828ce-145">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-145">passport no</span></span>  <br/> <span data-ttu-id="828ce-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="828ce-146">paspoort</span></span>  <br/> <span data-ttu-id="828ce-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="828ce-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="828ce-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="828ce-148">reisepass kein</span></span>  <br/> <span data-ttu-id="828ce-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="828ce-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="828ce-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="828ce-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="828ce-151">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-151">Format</span></span>

<span data-ttu-id="828ce-152">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="828ce-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-153">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-153">Pattern</span></span>

 <span data-ttu-id="828ce-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="828ce-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-155">Checksum</span></span>

<span data-ttu-id="828ce-156">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-157">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-157">Definition</span></span>

<span data-ttu-id="828ce-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-159">正規表現`Regex_bulgaria_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-160">キーワードの`Keywords_bulgaria_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-161">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-161">Keywords</span></span>

<span data-ttu-id="828ce-162">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-162"></span></span>
|<span data-ttu-id="828ce-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-164">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-164">passport number</span></span>  <br/> <span data-ttu-id="828ce-165">ブルガリア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="828ce-166">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-166">passport no</span></span>  <br/> <span data-ttu-id="828ce-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="828ce-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="828ce-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="828ce-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="828ce-169">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-169">Format</span></span>

<span data-ttu-id="828ce-170">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="828ce-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-171">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-171">Pattern</span></span>

 <span data-ttu-id="828ce-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="828ce-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-173">Checksum</span></span>

<span data-ttu-id="828ce-174">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-175">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-175">Definition</span></span>

<span data-ttu-id="828ce-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-177">正規表現`Regex_croatia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-178">キーワードの`Keywords_croatia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-179">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-179">Keywords</span></span>

<span data-ttu-id="828ce-180">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-180"></span></span>
|<span data-ttu-id="828ce-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-182">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-182">passport number</span></span>  <br/> <span data-ttu-id="828ce-183">クロアチア パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-183">croatian passport number</span></span>  <br/> <span data-ttu-id="828ce-184">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-184">passport no</span></span>  <br/> <span data-ttu-id="828ce-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="828ce-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="828ce-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="828ce-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="828ce-187">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-187">Format</span></span>

<span data-ttu-id="828ce-188">スペースや区切り文字なしで 6-8 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-189">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-189">Pattern</span></span>

<span data-ttu-id="828ce-190">6 ~ 8 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-191">Checksum</span></span>

<span data-ttu-id="828ce-192">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-193">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-193">Definition</span></span>

<span data-ttu-id="828ce-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-195">正規表現`Regex_cyprus_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-196">キーワードの`Keywords_cyprus_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-197">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-197">Keywords</span></span>

<span data-ttu-id="828ce-198">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-198"></span></span>
|<span data-ttu-id="828ce-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-200">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-200">passport number</span></span>  <br/> <span data-ttu-id="828ce-201">キプロス パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="828ce-202">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-202">passport no</span></span>  <br/> <span data-ttu-id="828ce-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="828ce-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="828ce-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="828ce-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="828ce-205">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-205">Format</span></span>

<span data-ttu-id="828ce-206">8 桁のスペースや区切り文字なし</span><span class="sxs-lookup"><span data-stu-id="828ce-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-207">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-207">Pattern</span></span>

<span data-ttu-id="828ce-208">8 桁のスペースや区切り文字なし</span><span class="sxs-lookup"><span data-stu-id="828ce-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-209">Checksum</span></span>

<span data-ttu-id="828ce-210">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-211">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-211">Definition</span></span>

<span data-ttu-id="828ce-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-213">正規表現`Regex_czech_republic_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-214">キーワードの`Keywords_czech_republic_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-215">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-215">Keywords</span></span>

<span data-ttu-id="828ce-216">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-216"></span></span>
|<span data-ttu-id="828ce-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-218">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-218">passport number</span></span>  <br/> <span data-ttu-id="828ce-219">チェコ語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-219">czech passport number</span></span>  <br/> <span data-ttu-id="828ce-220">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-220">passport no</span></span>  <br/> <span data-ttu-id="828ce-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="828ce-221">cestovní pas</span></span>  <br/> <span data-ttu-id="828ce-222">pas</span><span class="sxs-lookup"><span data-stu-id="828ce-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="828ce-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="828ce-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="828ce-224">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-224">Format</span></span>

<span data-ttu-id="828ce-225">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="828ce-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-226">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-226">Pattern</span></span>

 <span data-ttu-id="828ce-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="828ce-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-228">Checksum</span></span>

<span data-ttu-id="828ce-229">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-230">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-230">Definition</span></span>

<span data-ttu-id="828ce-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-232">正規表現`Regex_denmark_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-233">キーワードの`Keywords_denmark_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-234">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-234">Keywords</span></span>

<span data-ttu-id="828ce-235">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-235"></span></span>
|<span data-ttu-id="828ce-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-237">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-237">passport number</span></span>  <br/> <span data-ttu-id="828ce-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-238">danish passport number</span></span>  <br/> <span data-ttu-id="828ce-239">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-239">passport no</span></span>  <br/> <span data-ttu-id="828ce-240">pas</span><span class="sxs-lookup"><span data-stu-id="828ce-240">pas</span></span>  <br/> <span data-ttu-id="828ce-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="828ce-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="828ce-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="828ce-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="828ce-243">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-243">Format</span></span>

<span data-ttu-id="828ce-244">スペースや区切り文字なしで 7 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-245">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-245">Pattern</span></span>

<span data-ttu-id="828ce-246">7 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-247">Checksum</span></span>

<span data-ttu-id="828ce-248">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-249">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-249">Definition</span></span>

<span data-ttu-id="828ce-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-251">正規表現`Regex_estonia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-252">キーワードの`Keywords_estonia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-253">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-253">Keywords</span></span>

<span data-ttu-id="828ce-254">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-254"></span></span>
|<span data-ttu-id="828ce-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-256">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-256">passport number</span></span>  <br/> <span data-ttu-id="828ce-257">エストニア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-257">estonian passport number</span></span>  <br/> <span data-ttu-id="828ce-258">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-258">passport no</span></span>  <br/> <span data-ttu-id="828ce-259">eesti kodaniku パス</span><span class="sxs-lookup"><span data-stu-id="828ce-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="828ce-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="828ce-260">Finland</span></span>

<span data-ttu-id="828ce-261">詳細についてを参照してください「フィンランドのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="828ce-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="828ce-262">フランス</span><span class="sxs-lookup"><span data-stu-id="828ce-262">France</span></span>

<span data-ttu-id="828ce-263">詳細についてを参照してください「東京都パスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="828ce-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="828ce-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="828ce-264">Germany</span></span>

<span data-ttu-id="828ce-265">詳細についてを参照してください「ドイツのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="828ce-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="828ce-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="828ce-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="828ce-267">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-267">Format</span></span>

<span data-ttu-id="828ce-268">スペースや区切り文字なしで 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-269">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-269">Pattern</span></span>

<span data-ttu-id="828ce-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-271">Checksum</span></span>

<span data-ttu-id="828ce-272">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-273">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-273">Definition</span></span>

<span data-ttu-id="828ce-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-275">正規表現`Regex_greece_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-276">キーワードの`Keywords_greece_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-277">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-277">Keywords</span></span>

<span data-ttu-id="828ce-278">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-278"></span></span>
|<span data-ttu-id="828ce-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-280">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-280">passport number</span></span>  <br/> <span data-ttu-id="828ce-281">ギリシャ語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-281">greek passport number</span></span>  <br/> <span data-ttu-id="828ce-282">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-282">passport no</span></span>  <br/> <span data-ttu-id="828ce-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="828ce-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="828ce-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="828ce-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="828ce-285">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-285">Format</span></span>

<span data-ttu-id="828ce-286">スペースや区切り文字なしで 6 または 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-287">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-287">Pattern</span></span>

<span data-ttu-id="828ce-288">6 または 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-289">Checksum</span></span>

<span data-ttu-id="828ce-290">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-291">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-291">Definition</span></span>

<span data-ttu-id="828ce-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-293">正規表現`Regex_hungary_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-294">キーワードの`Keywords_hungary_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-295">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-295">Keywords</span></span>

<span data-ttu-id="828ce-296">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-296"></span></span>
|<span data-ttu-id="828ce-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-298">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-298">passport number</span></span>  <br/> <span data-ttu-id="828ce-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="828ce-300">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-300">passport no</span></span>  <br/> <span data-ttu-id="828ce-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="828ce-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="828ce-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="828ce-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="828ce-303">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-303">Format</span></span>

<span data-ttu-id="828ce-304">2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-305">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-305">Pattern</span></span>

<span data-ttu-id="828ce-306">2 つの文字または数字が 7 桁の後に。</span><span class="sxs-lookup"><span data-stu-id="828ce-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="828ce-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="828ce-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="828ce-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-309">Checksum</span></span>

<span data-ttu-id="828ce-310">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-311">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-311">Definition</span></span>

<span data-ttu-id="828ce-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-313">正規表現`Regex_ireland_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-314">キーワードの`Keywords_ireland_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-315">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-315">Keywords</span></span>

<span data-ttu-id="828ce-316">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-316"></span></span>
|<span data-ttu-id="828ce-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-318">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-318">passport number</span></span>  <br/> <span data-ttu-id="828ce-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-319">irish passport number</span></span>  <br/> <span data-ttu-id="828ce-320">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-320">passport no</span></span>  <br/> <span data-ttu-id="828ce-321">pas</span><span class="sxs-lookup"><span data-stu-id="828ce-321">pas</span></span>  <br/> <span data-ttu-id="828ce-322">passport</span><span class="sxs-lookup"><span data-stu-id="828ce-322">passport</span></span>  <br/> <span data-ttu-id="828ce-323">passeport</span><span class="sxs-lookup"><span data-stu-id="828ce-323">passeport</span></span>  <br/> <span data-ttu-id="828ce-324">passeport して</span><span class="sxs-lookup"><span data-stu-id="828ce-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="828ce-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="828ce-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="828ce-326">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-326">Format</span></span>

<span data-ttu-id="828ce-327">2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-328">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-328">Pattern</span></span>

<span data-ttu-id="828ce-329">2 つの文字または数字が 7 桁の後に。</span><span class="sxs-lookup"><span data-stu-id="828ce-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="828ce-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="828ce-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="828ce-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-332">Checksum</span></span>

<span data-ttu-id="828ce-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="828ce-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-334">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-334">Definition</span></span>

<span data-ttu-id="828ce-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-336">正規表現`Regex_italy_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-337">キーワードの`Keywords_italy_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-338">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-338">Keywords</span></span>

<span data-ttu-id="828ce-339">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-339"></span></span>
|<span data-ttu-id="828ce-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-341">italian passport number</span></span>  <br/> <span data-ttu-id="828ce-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="828ce-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="828ce-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="828ce-343">passaporto</span></span>  <br/> <span data-ttu-id="828ce-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="828ce-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="828ce-345">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-345">passport number</span></span>  <br/> <span data-ttu-id="828ce-346">italiana passaporto して</span><span class="sxs-lookup"><span data-stu-id="828ce-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="828ce-347">passaporto して</span><span class="sxs-lookup"><span data-stu-id="828ce-347">passaporto numero</span></span>  <br/> <span data-ttu-id="828ce-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="828ce-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="828ce-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="828ce-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="828ce-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="828ce-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="828ce-351">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-351">Format</span></span>

<span data-ttu-id="828ce-352">2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-353">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-353">Pattern</span></span>

<span data-ttu-id="828ce-354">2 つの文字または数字が 7 桁の後に。</span><span class="sxs-lookup"><span data-stu-id="828ce-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="828ce-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="828ce-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="828ce-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-357">Checksum</span></span>

<span data-ttu-id="828ce-358">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-359">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-359">Definition</span></span>

<span data-ttu-id="828ce-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-361">正規表現`Regex_latvia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-362">キーワードの`Keywords_latvia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-363">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-363">Keywords</span></span>

<span data-ttu-id="828ce-364">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-364"></span></span>
|<span data-ttu-id="828ce-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-366">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-366">passport number</span></span>  <br/> <span data-ttu-id="828ce-367">ラトビア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-367">latvian passport number</span></span>  <br/> <span data-ttu-id="828ce-368">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-368">passport no</span></span>  <br/> <span data-ttu-id="828ce-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="828ce-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="828ce-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="828ce-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="828ce-371">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-371">Format</span></span>

<span data-ttu-id="828ce-372">8 つのスペースや区切り記号付きの文字または数字</span><span class="sxs-lookup"><span data-stu-id="828ce-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-373">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-373">Pattern</span></span>

<span data-ttu-id="828ce-374">8 つの数字または文字 (いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="828ce-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-375">Checksum</span></span>

<span data-ttu-id="828ce-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="828ce-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-377">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-377">Definition</span></span>

<span data-ttu-id="828ce-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-379">正規表現`Regex_lithuania_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-380">キーワードの`Keywords_lithuania_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-381">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-381">Keywords</span></span>

<span data-ttu-id="828ce-382">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-382"></span></span>
|<span data-ttu-id="828ce-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-384">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-384">passport number</span></span>  <br/> <span data-ttu-id="828ce-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="828ce-386">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-386">passport no</span></span>  <br/> <span data-ttu-id="828ce-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="828ce-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="828ce-388">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="828ce-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="828ce-389">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-389">Format</span></span>

<span data-ttu-id="828ce-390">8 つのスペースや区切り記号付きの文字または数字</span><span class="sxs-lookup"><span data-stu-id="828ce-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-391">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-391">Pattern</span></span>

<span data-ttu-id="828ce-392">8 つの数字または文字 (いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="828ce-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-393">Checksum</span></span>

<span data-ttu-id="828ce-394">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-395">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-395">Definition</span></span>

<span data-ttu-id="828ce-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-397">正規表現`Regex_nation_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-398">キーワードの`Keywords_nation_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-399">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-399">Keywords</span></span>

<span data-ttu-id="828ce-400">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-400"></span></span>
|<span data-ttu-id="828ce-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-402">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-402">passport number</span></span>  <br/> <span data-ttu-id="828ce-403">ラトビア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-403">latvian passport number</span></span>  <br/> <span data-ttu-id="828ce-404">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-404">passport no</span></span>  <br/> <span data-ttu-id="828ce-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="828ce-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="828ce-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="828ce-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="828ce-407">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-407">Format</span></span>

<span data-ttu-id="828ce-408">スペースや区切り文字なしの 7 桁</span><span class="sxs-lookup"><span data-stu-id="828ce-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-409">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-409">Pattern</span></span>

 <span data-ttu-id="828ce-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="828ce-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-411">Checksum</span></span>

<span data-ttu-id="828ce-412">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-413">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-413">Definition</span></span>

<span data-ttu-id="828ce-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-415">正規表現`Regex_malta_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-416">キーワードの`Keywords_malta_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-417">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-417">Keywords</span></span>

<span data-ttu-id="828ce-418">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-418"></span></span>
|<span data-ttu-id="828ce-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-420">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-420">passport number</span></span>  <br/> <span data-ttu-id="828ce-421">マルタ語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-421">maltese passport number</span></span>  <br/> <span data-ttu-id="828ce-422">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-422">passport no</span></span>  <br/> <span data-ttu-id="828ce-423">numru tal ・ passaport</span><span class="sxs-lookup"><span data-stu-id="828ce-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="828ce-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="828ce-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="828ce-425">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-425">Format</span></span>

<span data-ttu-id="828ce-426">9 つの文字またはスペースや区切り文字と数字</span><span class="sxs-lookup"><span data-stu-id="828ce-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-427">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-427">Pattern</span></span>

<span data-ttu-id="828ce-428">9 つの文字または数字</span><span class="sxs-lookup"><span data-stu-id="828ce-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-429">Checksum</span></span>

<span data-ttu-id="828ce-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="828ce-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-431">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-431">Definition</span></span>

<span data-ttu-id="828ce-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-433">正規表現`Regex_netherlands_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-434">キーワードの`Keywords_netherlands_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-435">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-435">Keywords</span></span>

<span data-ttu-id="828ce-436">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-436"></span></span>
|<span data-ttu-id="828ce-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-438">dutch passport number</span></span>  <br/> <span data-ttu-id="828ce-439">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-439">passport number</span></span>  <br/> <span data-ttu-id="828ce-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="828ce-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="828ce-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="828ce-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="828ce-442">paspoort</span></span>  <br/> <span data-ttu-id="828ce-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="828ce-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="828ce-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="828ce-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="828ce-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="828ce-445">Poland</span></span>

<span data-ttu-id="828ce-446">詳細についてを参照してください「ポーランド パスポート番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="828ce-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="828ce-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="828ce-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="828ce-448">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-448">Format</span></span>

<span data-ttu-id="828ce-449">スペースや区切り文字なしで 6 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-450">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-450">Pattern</span></span>

<span data-ttu-id="828ce-451">6 桁の後に 1 つの文字。</span><span class="sxs-lookup"><span data-stu-id="828ce-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="828ce-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="828ce-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="828ce-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-454">Checksum</span></span>

<span data-ttu-id="828ce-455">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-456">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-456">Definition</span></span>

<span data-ttu-id="828ce-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-458">正規表現`Regex_portugal_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-459">キーワードの`Keywords_portugal_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-460">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-460">Keywords</span></span>

<span data-ttu-id="828ce-461">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-461"></span></span>
|<span data-ttu-id="828ce-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-463">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-463">passport number</span></span>  <br/> <span data-ttu-id="828ce-464">ポルトガル語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-464">portugese passport number</span></span>  <br/> <span data-ttu-id="828ce-465">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-465">passport no</span></span>  <br/> <span data-ttu-id="828ce-466">número は passaporte</span><span class="sxs-lookup"><span data-stu-id="828ce-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="828ce-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="828ce-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="828ce-468">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-468">Format</span></span>

<span data-ttu-id="828ce-469">スペースや区切り記号なしの 8 または 9 の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-470">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-470">Pattern</span></span>

<span data-ttu-id="828ce-471">8 または 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-472">Checksum</span></span>

<span data-ttu-id="828ce-473">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-474">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-474">Definition</span></span>

<span data-ttu-id="828ce-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-476">正規表現`Regex_romania_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-477">キーワードの`Keywords_romania_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-478">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-478">Keywords</span></span>

<span data-ttu-id="828ce-479">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-479"></span></span>
|<span data-ttu-id="828ce-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-481">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-481">passport number</span></span>  <br/> <span data-ttu-id="828ce-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-482">romanian passport number</span></span>  <br/> <span data-ttu-id="828ce-483">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-483">passport no</span></span>  <br/> <span data-ttu-id="828ce-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="828ce-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="828ce-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="828ce-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="828ce-486">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-486">Format</span></span>

<span data-ttu-id="828ce-487">1 つの数字または文字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-488">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-488">Pattern</span></span>

<span data-ttu-id="828ce-489">1 つの桁または 7 桁の後に文字 (いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="828ce-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="828ce-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-490">Checksum</span></span>

<span data-ttu-id="828ce-491">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-492">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-492">Definition</span></span>

<span data-ttu-id="828ce-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-494">正規表現`Regex_slovakia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-495">キーワードの`Keywords_slovakia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-496">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-496">Keywords</span></span>

<span data-ttu-id="828ce-497">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-497"></span></span>
|<span data-ttu-id="828ce-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-499">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-499">passport number</span></span>  <br/> <span data-ttu-id="828ce-500">スロバキア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="828ce-501">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-501">passport no</span></span>  <br/> <span data-ttu-id="828ce-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="828ce-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="828ce-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="828ce-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="828ce-504">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-504">Format</span></span>

<span data-ttu-id="828ce-505">スペースや区切り文字なしで 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="828ce-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-506">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-506">Pattern</span></span>

<span data-ttu-id="828ce-507">7 桁の後に 2 つの文字。</span><span class="sxs-lookup"><span data-stu-id="828ce-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="828ce-508">文字"P"</span><span class="sxs-lookup"><span data-stu-id="828ce-508">The letter "P"</span></span>
    
- <span data-ttu-id="828ce-509">大文字を 1 つ</span><span class="sxs-lookup"><span data-stu-id="828ce-509">One uppercase letter</span></span>
    
- <span data-ttu-id="828ce-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-511">Checksum</span></span>

<span data-ttu-id="828ce-512">なし</span><span class="sxs-lookup"><span data-stu-id="828ce-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-513">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-513">Definition</span></span>

<span data-ttu-id="828ce-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-515">正規表現`Regex_slovenia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-516">キーワードの`Keywords_slovenia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-517">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-517">Keywords</span></span>

<span data-ttu-id="828ce-518">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-518"></span></span>
|<span data-ttu-id="828ce-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-520">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-520">passport number</span></span>  <br/> <span data-ttu-id="828ce-521">スロベニア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="828ce-522">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-522">passport no</span></span>  <br/> <span data-ttu-id="828ce-523">Številka potnega リスト</span><span class="sxs-lookup"><span data-stu-id="828ce-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="828ce-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="828ce-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="828ce-525">形式</span><span class="sxs-lookup"><span data-stu-id="828ce-525">Format</span></span>

<span data-ttu-id="828ce-526">文字とスペースや区切り記号と数字の 8 または 9 文字組み合わせ</span><span class="sxs-lookup"><span data-stu-id="828ce-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="828ce-527">パターン</span><span class="sxs-lookup"><span data-stu-id="828ce-527">Pattern</span></span>

<span data-ttu-id="828ce-528">文字と数字の 8 または 9 文字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="828ce-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="828ce-529">2 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="828ce-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="828ce-530">1 つの数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="828ce-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="828ce-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="828ce-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="828ce-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="828ce-532">Checksum</span></span>

<span data-ttu-id="828ce-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="828ce-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="828ce-534">定義</span><span class="sxs-lookup"><span data-stu-id="828ce-534">Definition</span></span>

<span data-ttu-id="828ce-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="828ce-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="828ce-536">正規表現`Regex_spain_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="828ce-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="828ce-537">キーワードの`Keywords_spain_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="828ce-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="828ce-538">Keywords</span><span class="sxs-lookup"><span data-stu-id="828ce-538">Keywords</span></span>

<span data-ttu-id="828ce-539">| |</span><span class="sxs-lookup"><span data-stu-id="828ce-539"></span></span>
|<span data-ttu-id="828ce-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="828ce-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="828ce-541">passport</span><span class="sxs-lookup"><span data-stu-id="828ce-541">passport</span></span>  <br/> <span data-ttu-id="828ce-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="828ce-542">spain passport</span></span>  <br/> <span data-ttu-id="828ce-543">パスポート帳</span><span class="sxs-lookup"><span data-stu-id="828ce-543">passport book</span></span>  <br/> <span data-ttu-id="828ce-544">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="828ce-544">passport number</span></span>  <br/> <span data-ttu-id="828ce-545">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="828ce-545">passport no</span></span>  <br/> <span data-ttu-id="828ce-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="828ce-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="828ce-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="828ce-547">número pasaporte</span></span>  <br/> <span data-ttu-id="828ce-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="828ce-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="828ce-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="828ce-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="828ce-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="828ce-550">Sweden</span></span>

<span data-ttu-id="828ce-551">詳細についてを参照してください「スウェーデンのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="828ce-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="828ce-552">英国</span><span class="sxs-lookup"><span data-stu-id="828ce-552">UK</span></span>

<span data-ttu-id="828ce-p103">詳細についてを参照してください「米国/英国のパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="828ce-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="828ce-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="828ce-555">See also</span></span>

[<span data-ttu-id="828ce-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="828ce-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

