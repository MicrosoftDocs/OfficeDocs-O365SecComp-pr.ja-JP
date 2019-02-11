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
ms.openlocfilehash: 7a7fc1ff826aab4096c46535686eb0fd68173c6f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "25840326"
---
# <a name="eu-passport-number"></a><span data-ttu-id="e7294-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-104">EU Passport Number</span></span>

<span data-ttu-id="e7294-p102">このトピックでは、データ損失防止 (DLP) ポリシーがどの EU パスポート番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。</span><span class="sxs-lookup"><span data-stu-id="e7294-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e7294-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="e7294-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e7294-108">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-108">Format</span></span>

<span data-ttu-id="e7294-109">省略可能なスペースと 7 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-110">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-110">Pattern</span></span>

<span data-ttu-id="e7294-111">1 つの文字、7 桁の数字、およびスペースを 1 つの組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="e7294-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="e7294-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="e7294-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="e7294-113">1 つのスペース (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e7294-113">One space (optional)</span></span>
    
- <span data-ttu-id="e7294-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-115">Checksum</span></span>

<span data-ttu-id="e7294-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7294-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-117">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-117">Definition</span></span>

<span data-ttu-id="e7294-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-119">正規表現`Regex_austria_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-120">キーワードの`Keywords_austria_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-121">Keywords</span></span>

<span data-ttu-id="e7294-122">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-122"></span></span>
|<span data-ttu-id="e7294-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-124">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-124">passport number</span></span>  <br/> <span data-ttu-id="e7294-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-125">austrian passport number</span></span>  <br/> <span data-ttu-id="e7294-126">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-126">passport no</span></span>  <br/> <span data-ttu-id="e7294-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="e7294-127">reisepass</span></span>  <br/> <span data-ttu-id="e7294-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="e7294-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="e7294-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="e7294-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e7294-130">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-130">Format</span></span>

<span data-ttu-id="e7294-131">スペースや区切り文字なしで 6 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-132">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-132">Pattern</span></span>

<span data-ttu-id="e7294-133">2 文字 6 桁の後に、</span><span class="sxs-lookup"><span data-stu-id="e7294-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-134">Checksum</span></span>

<span data-ttu-id="e7294-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7294-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-136">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-136">Definition</span></span>

<span data-ttu-id="e7294-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-138">正規表現`Regex_belgium_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-139">キーワードの`Keywords_belgium_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-140">Keywords</span></span>

<span data-ttu-id="e7294-141">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-141"></span></span>
|<span data-ttu-id="e7294-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-143">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-143">passport number</span></span>  <br/> <span data-ttu-id="e7294-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-144">belgian passport number</span></span>  <br/> <span data-ttu-id="e7294-145">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-145">passport no</span></span>  <br/> <span data-ttu-id="e7294-146">paspoort</span><span class="sxs-lookup"><span data-stu-id="e7294-146">paspoort</span></span>  <br/> <span data-ttu-id="e7294-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="e7294-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="e7294-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="e7294-148">reisepass kein</span></span>  <br/> <span data-ttu-id="e7294-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="e7294-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="e7294-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="e7294-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e7294-151">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-151">Format</span></span>

<span data-ttu-id="e7294-152">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="e7294-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-153">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-153">Pattern</span></span>

 <span data-ttu-id="e7294-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e7294-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-155">Checksum</span></span>

<span data-ttu-id="e7294-156">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-157">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-157">Definition</span></span>

<span data-ttu-id="e7294-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-159">正規表現`Regex_bulgaria_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-160">キーワードの`Keywords_bulgaria_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-161">Keywords</span></span>

<span data-ttu-id="e7294-162">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-162"></span></span>
|<span data-ttu-id="e7294-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-164">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-164">passport number</span></span>  <br/> <span data-ttu-id="e7294-165">ブルガリア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="e7294-166">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-166">passport no</span></span>  <br/> <span data-ttu-id="e7294-167">НОМЕР НА ПАСПОРТА</span><span class="sxs-lookup"><span data-stu-id="e7294-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="e7294-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="e7294-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e7294-169">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-169">Format</span></span>

<span data-ttu-id="e7294-170">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="e7294-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-171">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-171">Pattern</span></span>

 <span data-ttu-id="e7294-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e7294-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-173">Checksum</span></span>

<span data-ttu-id="e7294-174">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-175">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-175">Definition</span></span>

<span data-ttu-id="e7294-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-177">正規表現`Regex_croatia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-178">キーワードの`Keywords_croatia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-179">Keywords</span></span>

<span data-ttu-id="e7294-180">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-180"></span></span>
|<span data-ttu-id="e7294-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-182">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-182">passport number</span></span>  <br/> <span data-ttu-id="e7294-183">クロアチア パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-183">croatian passport number</span></span>  <br/> <span data-ttu-id="e7294-184">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-184">passport no</span></span>  <br/> <span data-ttu-id="e7294-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="e7294-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="e7294-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="e7294-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e7294-187">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-187">Format</span></span>

<span data-ttu-id="e7294-188">スペースや区切り文字なしで 6-8 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-189">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-189">Pattern</span></span>

<span data-ttu-id="e7294-190">6 ~ 8 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-191">Checksum</span></span>

<span data-ttu-id="e7294-192">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-193">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-193">Definition</span></span>

<span data-ttu-id="e7294-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-195">正規表現`Regex_cyprus_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-196">キーワードの`Keywords_cyprus_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-197">Keywords</span></span>

<span data-ttu-id="e7294-198">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-198"></span></span>
|<span data-ttu-id="e7294-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-200">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-200">passport number</span></span>  <br/> <span data-ttu-id="e7294-201">キプロス パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="e7294-202">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-202">passport no</span></span>  <br/> <span data-ttu-id="e7294-203">ΑΡΙΘΜΌ ΔΙΑΒΑΤΗΡΊΟΥ</span><span class="sxs-lookup"><span data-stu-id="e7294-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="e7294-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="e7294-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e7294-205">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-205">Format</span></span>

<span data-ttu-id="e7294-206">8 桁のスペースや区切り文字なし</span><span class="sxs-lookup"><span data-stu-id="e7294-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-207">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-207">Pattern</span></span>

<span data-ttu-id="e7294-208">8 桁のスペースや区切り文字なし</span><span class="sxs-lookup"><span data-stu-id="e7294-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-209">Checksum</span></span>

<span data-ttu-id="e7294-210">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-211">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-211">Definition</span></span>

<span data-ttu-id="e7294-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-213">正規表現`Regex_czech_republic_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-214">キーワードの`Keywords_czech_republic_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-215">Keywords</span></span>

<span data-ttu-id="e7294-216">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-216"></span></span>
|<span data-ttu-id="e7294-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-218">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-218">passport number</span></span>  <br/> <span data-ttu-id="e7294-219">チェコ語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-219">czech passport number</span></span>  <br/> <span data-ttu-id="e7294-220">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-220">passport no</span></span>  <br/> <span data-ttu-id="e7294-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="e7294-221">cestovní pas</span></span>  <br/> <span data-ttu-id="e7294-222">pas</span><span class="sxs-lookup"><span data-stu-id="e7294-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="e7294-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="e7294-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e7294-224">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-224">Format</span></span>

<span data-ttu-id="e7294-225">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="e7294-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-226">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-226">Pattern</span></span>

 <span data-ttu-id="e7294-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e7294-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-228">Checksum</span></span>

<span data-ttu-id="e7294-229">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-230">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-230">Definition</span></span>

<span data-ttu-id="e7294-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-232">正規表現`Regex_denmark_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-233">キーワードの`Keywords_denmark_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-234">Keywords</span></span>

<span data-ttu-id="e7294-235">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-235"></span></span>
|<span data-ttu-id="e7294-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-237">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-237">passport number</span></span>  <br/> <span data-ttu-id="e7294-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-238">danish passport number</span></span>  <br/> <span data-ttu-id="e7294-239">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-239">passport no</span></span>  <br/> <span data-ttu-id="e7294-240">pas</span><span class="sxs-lookup"><span data-stu-id="e7294-240">pas</span></span>  <br/> <span data-ttu-id="e7294-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="e7294-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="e7294-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="e7294-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e7294-243">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-243">Format</span></span>

<span data-ttu-id="e7294-244">スペースや区切り文字なしで 7 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-245">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-245">Pattern</span></span>

<span data-ttu-id="e7294-246">7 桁の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-247">Checksum</span></span>

<span data-ttu-id="e7294-248">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-249">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-249">Definition</span></span>

<span data-ttu-id="e7294-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-251">正規表現`Regex_estonia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-252">キーワードの`Keywords_estonia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-253">Keywords</span></span>

<span data-ttu-id="e7294-254">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-254"></span></span>
|<span data-ttu-id="e7294-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-256">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-256">passport number</span></span>  <br/> <span data-ttu-id="e7294-257">エストニア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-257">estonian passport number</span></span>  <br/> <span data-ttu-id="e7294-258">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-258">passport no</span></span>  <br/> <span data-ttu-id="e7294-259">eesti kodaniku パス</span><span class="sxs-lookup"><span data-stu-id="e7294-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="e7294-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="e7294-260">Finland</span></span>

<span data-ttu-id="e7294-261">詳細についてを参照してください「フィンランドのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e7294-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="e7294-262">フランス</span><span class="sxs-lookup"><span data-stu-id="e7294-262">France</span></span>

<span data-ttu-id="e7294-263">詳細についてを参照してください「東京都パスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e7294-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="e7294-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="e7294-264">Germany</span></span>

<span data-ttu-id="e7294-265">詳細についてを参照してください「ドイツのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e7294-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="e7294-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="e7294-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e7294-267">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-267">Format</span></span>

<span data-ttu-id="e7294-268">スペースや区切り文字なしで 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-269">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-269">Pattern</span></span>

<span data-ttu-id="e7294-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-271">Checksum</span></span>

<span data-ttu-id="e7294-272">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-273">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-273">Definition</span></span>

<span data-ttu-id="e7294-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-275">正規表現`Regex_greece_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-276">キーワードの`Keywords_greece_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-277">Keywords</span></span>

<span data-ttu-id="e7294-278">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-278"></span></span>
|<span data-ttu-id="e7294-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-280">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-280">passport number</span></span>  <br/> <span data-ttu-id="e7294-281">ギリシャ語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-281">greek passport number</span></span>  <br/> <span data-ttu-id="e7294-282">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-282">passport no</span></span>  <br/> <span data-ttu-id="e7294-283">ΔΙΑΒΑΤΗΡΙΟ</span><span class="sxs-lookup"><span data-stu-id="e7294-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="e7294-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="e7294-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e7294-285">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-285">Format</span></span>

<span data-ttu-id="e7294-286">スペースや区切り文字なしで 6 または 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-287">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-287">Pattern</span></span>

<span data-ttu-id="e7294-288">6 または 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-289">Checksum</span></span>

<span data-ttu-id="e7294-290">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-291">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-291">Definition</span></span>

<span data-ttu-id="e7294-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-293">正規表現`Regex_hungary_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-294">キーワードの`Keywords_hungary_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-295">Keywords</span></span>

<span data-ttu-id="e7294-296">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-296"></span></span>
|<span data-ttu-id="e7294-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-298">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-298">passport number</span></span>  <br/> <span data-ttu-id="e7294-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="e7294-300">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-300">passport no</span></span>  <br/> <span data-ttu-id="e7294-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="e7294-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="e7294-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="e7294-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e7294-303">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-303">Format</span></span>

<span data-ttu-id="e7294-304">2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-305">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-305">Pattern</span></span>

<span data-ttu-id="e7294-306">2 つの文字または数字が 7 桁の後に。</span><span class="sxs-lookup"><span data-stu-id="e7294-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="e7294-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="e7294-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="e7294-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-309">Checksum</span></span>

<span data-ttu-id="e7294-310">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-311">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-311">Definition</span></span>

<span data-ttu-id="e7294-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-313">正規表現`Regex_ireland_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-314">キーワードの`Keywords_ireland_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-315">Keywords</span></span>

<span data-ttu-id="e7294-316">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-316"></span></span>
|<span data-ttu-id="e7294-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-318">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-318">passport number</span></span>  <br/> <span data-ttu-id="e7294-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-319">irish passport number</span></span>  <br/> <span data-ttu-id="e7294-320">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-320">passport no</span></span>  <br/> <span data-ttu-id="e7294-321">pas</span><span class="sxs-lookup"><span data-stu-id="e7294-321">pas</span></span>  <br/> <span data-ttu-id="e7294-322">passport</span><span class="sxs-lookup"><span data-stu-id="e7294-322">passport</span></span>  <br/> <span data-ttu-id="e7294-323">passeport</span><span class="sxs-lookup"><span data-stu-id="e7294-323">passeport</span></span>  <br/> <span data-ttu-id="e7294-324">passeport して</span><span class="sxs-lookup"><span data-stu-id="e7294-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="e7294-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="e7294-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="e7294-326">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-326">Format</span></span>

<span data-ttu-id="e7294-327">2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-328">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-328">Pattern</span></span>

<span data-ttu-id="e7294-329">2 つの文字または数字が 7 桁の後に。</span><span class="sxs-lookup"><span data-stu-id="e7294-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="e7294-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="e7294-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="e7294-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-332">Checksum</span></span>

<span data-ttu-id="e7294-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7294-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-334">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-334">Definition</span></span>

<span data-ttu-id="e7294-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-336">正規表現`Regex_italy_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-337">キーワードの`Keywords_italy_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-338">Keywords</span></span>

<span data-ttu-id="e7294-339">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-339"></span></span>
|<span data-ttu-id="e7294-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-341">italian passport number</span></span>  <br/> <span data-ttu-id="e7294-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="e7294-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="e7294-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="e7294-343">passaporto</span></span>  <br/> <span data-ttu-id="e7294-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="e7294-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="e7294-345">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-345">passport number</span></span>  <br/> <span data-ttu-id="e7294-346">italiana passaporto して</span><span class="sxs-lookup"><span data-stu-id="e7294-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="e7294-347">passaporto して</span><span class="sxs-lookup"><span data-stu-id="e7294-347">passaporto numero</span></span>  <br/> <span data-ttu-id="e7294-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="e7294-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="e7294-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="e7294-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="e7294-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="e7294-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e7294-351">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-351">Format</span></span>

<span data-ttu-id="e7294-352">2 つの文字または数字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-353">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-353">Pattern</span></span>

<span data-ttu-id="e7294-354">2 つの文字または数字が 7 桁の後に。</span><span class="sxs-lookup"><span data-stu-id="e7294-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="e7294-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="e7294-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="e7294-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-357">Checksum</span></span>

<span data-ttu-id="e7294-358">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-359">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-359">Definition</span></span>

<span data-ttu-id="e7294-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-361">正規表現`Regex_latvia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-362">キーワードの`Keywords_latvia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-363">Keywords</span></span>

<span data-ttu-id="e7294-364">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-364"></span></span>
|<span data-ttu-id="e7294-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-366">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-366">passport number</span></span>  <br/> <span data-ttu-id="e7294-367">ラトビア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-367">latvian passport number</span></span>  <br/> <span data-ttu-id="e7294-368">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-368">passport no</span></span>  <br/> <span data-ttu-id="e7294-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="e7294-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="e7294-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="e7294-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e7294-371">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-371">Format</span></span>

<span data-ttu-id="e7294-372">8 つのスペースや区切り記号付きの文字または数字</span><span class="sxs-lookup"><span data-stu-id="e7294-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-373">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-373">Pattern</span></span>

<span data-ttu-id="e7294-374">8 つの数字または文字 (いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="e7294-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-375">Checksum</span></span>

<span data-ttu-id="e7294-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7294-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-377">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-377">Definition</span></span>

<span data-ttu-id="e7294-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-379">正規表現`Regex_lithuania_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-380">キーワードの`Keywords_lithuania_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-381">Keywords</span></span>

<span data-ttu-id="e7294-382">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-382"></span></span>
|<span data-ttu-id="e7294-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-384">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-384">passport number</span></span>  <br/> <span data-ttu-id="e7294-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="e7294-386">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-386">passport no</span></span>  <br/> <span data-ttu-id="e7294-387">paso numeris</span><span class="sxs-lookup"><span data-stu-id="e7294-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="e7294-388">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="e7294-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e7294-389">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-389">Format</span></span>

<span data-ttu-id="e7294-390">8 つのスペースや区切り記号付きの文字または数字</span><span class="sxs-lookup"><span data-stu-id="e7294-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-391">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-391">Pattern</span></span>

<span data-ttu-id="e7294-392">8 つの数字または文字 (いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="e7294-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-393">Checksum</span></span>

<span data-ttu-id="e7294-394">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-395">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-395">Definition</span></span>

<span data-ttu-id="e7294-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-397">正規表現`Regex_nation_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-398">キーワードの`Keywords_nation_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-399">Keywords</span></span>

<span data-ttu-id="e7294-400">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-400"></span></span>
|<span data-ttu-id="e7294-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-402">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-402">passport number</span></span>  <br/> <span data-ttu-id="e7294-403">ラトビア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-403">latvian passport number</span></span>  <br/> <span data-ttu-id="e7294-404">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-404">passport no</span></span>  <br/> <span data-ttu-id="e7294-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="e7294-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="e7294-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="e7294-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e7294-407">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-407">Format</span></span>

<span data-ttu-id="e7294-408">スペースや区切り文字なしの 7 桁</span><span class="sxs-lookup"><span data-stu-id="e7294-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-409">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-409">Pattern</span></span>

 <span data-ttu-id="e7294-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e7294-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-411">Checksum</span></span>

<span data-ttu-id="e7294-412">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-413">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-413">Definition</span></span>

<span data-ttu-id="e7294-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-415">正規表現`Regex_malta_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-416">キーワードの`Keywords_malta_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-417">Keywords</span></span>

<span data-ttu-id="e7294-418">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-418"></span></span>
|<span data-ttu-id="e7294-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-420">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-420">passport number</span></span>  <br/> <span data-ttu-id="e7294-421">マルタ語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-421">maltese passport number</span></span>  <br/> <span data-ttu-id="e7294-422">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-422">passport no</span></span>  <br/> <span data-ttu-id="e7294-423">numru tal ・ passaport</span><span class="sxs-lookup"><span data-stu-id="e7294-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="e7294-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="e7294-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e7294-425">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-425">Format</span></span>

<span data-ttu-id="e7294-426">9 つの文字またはスペースや区切り文字と数字</span><span class="sxs-lookup"><span data-stu-id="e7294-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-427">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-427">Pattern</span></span>

<span data-ttu-id="e7294-428">9 つの文字または数字</span><span class="sxs-lookup"><span data-stu-id="e7294-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-429">Checksum</span></span>

<span data-ttu-id="e7294-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7294-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-431">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-431">Definition</span></span>

<span data-ttu-id="e7294-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-433">正規表現`Regex_netherlands_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-434">キーワードの`Keywords_netherlands_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-435">Keywords</span></span>

<span data-ttu-id="e7294-436">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-436"></span></span>
|<span data-ttu-id="e7294-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-438">dutch passport number</span></span>  <br/> <span data-ttu-id="e7294-439">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-439">passport number</span></span>  <br/> <span data-ttu-id="e7294-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="e7294-441">nederlanden paspoort nummer</span><span class="sxs-lookup"><span data-stu-id="e7294-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="e7294-442">paspoort</span><span class="sxs-lookup"><span data-stu-id="e7294-442">paspoort</span></span>  <br/> <span data-ttu-id="e7294-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="e7294-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="e7294-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="e7294-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="e7294-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="e7294-445">Poland</span></span>

<span data-ttu-id="e7294-446">詳細についてを参照してください「ポーランド パスポート番号」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e7294-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="e7294-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="e7294-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e7294-448">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-448">Format</span></span>

<span data-ttu-id="e7294-449">スペースや区切り文字なしで 6 桁の数字の後に 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-450">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-450">Pattern</span></span>

<span data-ttu-id="e7294-451">6 桁の後に 1 つの文字。</span><span class="sxs-lookup"><span data-stu-id="e7294-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="e7294-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="e7294-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="e7294-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-454">Checksum</span></span>

<span data-ttu-id="e7294-455">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-456">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-456">Definition</span></span>

<span data-ttu-id="e7294-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-458">正規表現`Regex_portugal_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-459">キーワードの`Keywords_portugal_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-460">Keywords</span></span>

<span data-ttu-id="e7294-461">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-461"></span></span>
|<span data-ttu-id="e7294-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-463">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-463">passport number</span></span>  <br/> <span data-ttu-id="e7294-464">ポルトガル語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="e7294-465">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-465">passport no</span></span>  <br/> <span data-ttu-id="e7294-466">número は passaporte</span><span class="sxs-lookup"><span data-stu-id="e7294-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="e7294-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="e7294-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e7294-468">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-468">Format</span></span>

<span data-ttu-id="e7294-469">スペースや区切り記号なしの 8 または 9 の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-470">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-470">Pattern</span></span>

<span data-ttu-id="e7294-471">8 または 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-472">Checksum</span></span>

<span data-ttu-id="e7294-473">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-474">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-474">Definition</span></span>

<span data-ttu-id="e7294-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-476">正規表現`Regex_romania_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-477">キーワードの`Keywords_romania_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-478">Keywords</span></span>

<span data-ttu-id="e7294-479">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-479"></span></span>
|<span data-ttu-id="e7294-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-481">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-481">passport number</span></span>  <br/> <span data-ttu-id="e7294-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-482">romanian passport number</span></span>  <br/> <span data-ttu-id="e7294-483">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-483">passport no</span></span>  <br/> <span data-ttu-id="e7294-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="e7294-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="e7294-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="e7294-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e7294-486">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-486">Format</span></span>

<span data-ttu-id="e7294-487">1 つの数字または文字の後にスペースや区切り文字なしで 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-488">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-488">Pattern</span></span>

<span data-ttu-id="e7294-489">1 つの桁または 7 桁の後に文字 (いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="e7294-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e7294-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-490">Checksum</span></span>

<span data-ttu-id="e7294-491">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-492">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-492">Definition</span></span>

<span data-ttu-id="e7294-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-494">正規表現`Regex_slovakia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-495">キーワードの`Keywords_slovakia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-496">Keywords</span></span>

<span data-ttu-id="e7294-497">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-497"></span></span>
|<span data-ttu-id="e7294-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-499">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-499">passport number</span></span>  <br/> <span data-ttu-id="e7294-500">スロバキア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="e7294-501">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-501">passport no</span></span>  <br/> <span data-ttu-id="e7294-502">Číslo pasu</span><span class="sxs-lookup"><span data-stu-id="e7294-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="e7294-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="e7294-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e7294-504">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-504">Format</span></span>

<span data-ttu-id="e7294-505">スペースや区切り文字なしで 7 桁の数字の後に 2 つの文字</span><span class="sxs-lookup"><span data-stu-id="e7294-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-506">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-506">Pattern</span></span>

<span data-ttu-id="e7294-507">7 桁の後に 2 つの文字。</span><span class="sxs-lookup"><span data-stu-id="e7294-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="e7294-508">文字"P"</span><span class="sxs-lookup"><span data-stu-id="e7294-508">The letter "P"</span></span>
    
- <span data-ttu-id="e7294-509">大文字を 1 つ</span><span class="sxs-lookup"><span data-stu-id="e7294-509">One uppercase letter</span></span>
    
- <span data-ttu-id="e7294-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-511">Checksum</span></span>

<span data-ttu-id="e7294-512">なし</span><span class="sxs-lookup"><span data-stu-id="e7294-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-513">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-513">Definition</span></span>

<span data-ttu-id="e7294-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-515">正規表現`Regex_slovenia_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-516">キーワードの`Keywords_slovenia_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-517">Keywords</span></span>

<span data-ttu-id="e7294-518">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-518"></span></span>
|<span data-ttu-id="e7294-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-520">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-520">passport number</span></span>  <br/> <span data-ttu-id="e7294-521">スロベニア語パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="e7294-522">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-522">passport no</span></span>  <br/> <span data-ttu-id="e7294-523">Številka potnega リスト</span><span class="sxs-lookup"><span data-stu-id="e7294-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="e7294-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="e7294-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e7294-525">形式</span><span class="sxs-lookup"><span data-stu-id="e7294-525">Format</span></span>

<span data-ttu-id="e7294-526">文字とスペースや区切り記号と数字の 8 または 9 文字組み合わせ</span><span class="sxs-lookup"><span data-stu-id="e7294-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e7294-527">パターン</span><span class="sxs-lookup"><span data-stu-id="e7294-527">Pattern</span></span>

<span data-ttu-id="e7294-528">文字と数字の 8 または 9 文字の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="e7294-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="e7294-529">2 つの数字または文字</span><span class="sxs-lookup"><span data-stu-id="e7294-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="e7294-530">1 つの数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="e7294-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="e7294-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e7294-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e7294-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e7294-532">Checksum</span></span>

<span data-ttu-id="e7294-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="e7294-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e7294-534">定義</span><span class="sxs-lookup"><span data-stu-id="e7294-534">Definition</span></span>

<span data-ttu-id="e7294-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e7294-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e7294-536">正規表現`Regex_spain_eu_passport_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e7294-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e7294-537">キーワードの`Keywords_spain_eu_passport_number`があります。</span><span class="sxs-lookup"><span data-stu-id="e7294-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e7294-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="e7294-538">Keywords</span></span>

<span data-ttu-id="e7294-539">| |</span><span class="sxs-lookup"><span data-stu-id="e7294-539"></span></span>
|<span data-ttu-id="e7294-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="e7294-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="e7294-541">passport</span><span class="sxs-lookup"><span data-stu-id="e7294-541">passport</span></span>  <br/> <span data-ttu-id="e7294-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="e7294-542">spain passport</span></span>  <br/> <span data-ttu-id="e7294-543">パスポート帳</span><span class="sxs-lookup"><span data-stu-id="e7294-543">passport book</span></span>  <br/> <span data-ttu-id="e7294-544">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="e7294-544">passport number</span></span>  <br/> <span data-ttu-id="e7294-545">パスポートなし</span><span class="sxs-lookup"><span data-stu-id="e7294-545">passport no</span></span>  <br/> <span data-ttu-id="e7294-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="e7294-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="e7294-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="e7294-547">número pasaporte</span></span>  <br/> <span data-ttu-id="e7294-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="e7294-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="e7294-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="e7294-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="e7294-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="e7294-550">Sweden</span></span>

<span data-ttu-id="e7294-551">詳細についてを参照してください「スウェーデンのパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e7294-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="e7294-552">英国</span><span class="sxs-lookup"><span data-stu-id="e7294-552">UK</span></span>

<span data-ttu-id="e7294-p103">詳細についてを参照してください「米国/英国のパスポート番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="e7294-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e7294-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="e7294-555">See also</span></span>

[<span data-ttu-id="e7294-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="e7294-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

