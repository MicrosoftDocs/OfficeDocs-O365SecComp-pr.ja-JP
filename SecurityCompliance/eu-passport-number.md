---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152969"
---
# <a name="eu-passport-number"></a><span data-ttu-id="aee12-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-104">EU Passport Number</span></span>

<span data-ttu-id="aee12-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="aee12-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="aee12-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="aee12-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="aee12-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="aee12-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="aee12-108">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-108">Format</span></span>

<span data-ttu-id="aee12-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-110">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-110">Pattern</span></span>

<span data-ttu-id="aee12-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="aee12-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="aee12-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="aee12-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="aee12-113">One space (optional)</span></span>
    
- <span data-ttu-id="aee12-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-115">Checksum</span></span>

<span data-ttu-id="aee12-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="aee12-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-117">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-117">Definition</span></span>

<span data-ttu-id="aee12-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-120">From `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-121">Keywords</span></span>

<span data-ttu-id="aee12-122">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-122"></span></span>
|<span data-ttu-id="aee12-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-124">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-124">passport number</span></span>  <br/> <span data-ttu-id="aee12-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-125">austrian passport number</span></span>  <br/> <span data-ttu-id="aee12-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-126">passport no</span></span>  <br/> <span data-ttu-id="aee12-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="aee12-127">reisepass</span></span>  <br/> <span data-ttu-id="aee12-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="aee12-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="aee12-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="aee12-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="aee12-130">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-130">Format</span></span>

<span data-ttu-id="aee12-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="aee12-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-132">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-132">Pattern</span></span>

<span data-ttu-id="aee12-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-134">Checksum</span></span>

<span data-ttu-id="aee12-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="aee12-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-136">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-136">Definition</span></span>

<span data-ttu-id="aee12-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-139">From `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-140">Keywords</span></span>

<span data-ttu-id="aee12-141">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-141"></span></span>
|<span data-ttu-id="aee12-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-143">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-143">passport number</span></span>  <br/> <span data-ttu-id="aee12-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-144">belgian passport number</span></span>  <br/> <span data-ttu-id="aee12-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-145">passport no</span></span>  <br/> <span data-ttu-id="aee12-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="aee12-146">paspoort</span></span>  <br/> <span data-ttu-id="aee12-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="aee12-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="aee12-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="aee12-148">reisepass kein</span></span>  <br/> <span data-ttu-id="aee12-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="aee12-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="aee12-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="aee12-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="aee12-151">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-151">Format</span></span>

<span data-ttu-id="aee12-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-153">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-153">Pattern</span></span>

 <span data-ttu-id="aee12-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="aee12-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-155">Checksum</span></span>

<span data-ttu-id="aee12-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-157">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-157">Definition</span></span>

<span data-ttu-id="aee12-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-160">From `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-161">Keywords</span></span>

<span data-ttu-id="aee12-162">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-162"></span></span>
|<span data-ttu-id="aee12-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-164">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-164">passport number</span></span>  <br/> <span data-ttu-id="aee12-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="aee12-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-166">passport no</span></span>  <br/> <span data-ttu-id="aee12-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="aee12-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="aee12-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="aee12-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="aee12-169">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-169">Format</span></span>

<span data-ttu-id="aee12-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-171">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-171">Pattern</span></span>

 <span data-ttu-id="aee12-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="aee12-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-173">Checksum</span></span>

<span data-ttu-id="aee12-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-175">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-175">Definition</span></span>

<span data-ttu-id="aee12-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-178">From `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-179">Keywords</span></span>

<span data-ttu-id="aee12-180">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-180"></span></span>
|<span data-ttu-id="aee12-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-182">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-182">passport number</span></span>  <br/> <span data-ttu-id="aee12-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-183">croatian passport number</span></span>  <br/> <span data-ttu-id="aee12-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-184">passport no</span></span>  <br/> <span data-ttu-id="aee12-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="aee12-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="aee12-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="aee12-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="aee12-187">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-187">Format</span></span>

<span data-ttu-id="aee12-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-189">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-189">Pattern</span></span>

<span data-ttu-id="aee12-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-191">Checksum</span></span>

<span data-ttu-id="aee12-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-193">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-193">Definition</span></span>

<span data-ttu-id="aee12-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-196">From `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-197">Keywords</span></span>

<span data-ttu-id="aee12-198">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-198"></span></span>
|<span data-ttu-id="aee12-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-200">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-200">passport number</span></span>  <br/> <span data-ttu-id="aee12-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="aee12-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-202">passport no</span></span>  <br/> <span data-ttu-id="aee12-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="aee12-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="aee12-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="aee12-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="aee12-205">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-205">Format</span></span>

<span data-ttu-id="aee12-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-207">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-207">Pattern</span></span>

<span data-ttu-id="aee12-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-209">Checksum</span></span>

<span data-ttu-id="aee12-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-211">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-211">Definition</span></span>

<span data-ttu-id="aee12-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-214">From `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-215">Keywords</span></span>

<span data-ttu-id="aee12-216">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-216"></span></span>
|<span data-ttu-id="aee12-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-218">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-218">passport number</span></span>  <br/> <span data-ttu-id="aee12-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-219">czech passport number</span></span>  <br/> <span data-ttu-id="aee12-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-220">passport no</span></span>  <br/> <span data-ttu-id="aee12-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="aee12-221">cestovní pas</span></span>  <br/> <span data-ttu-id="aee12-222">pas</span><span class="sxs-lookup"><span data-stu-id="aee12-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="aee12-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="aee12-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="aee12-224">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-224">Format</span></span>

<span data-ttu-id="aee12-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-226">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-226">Pattern</span></span>

 <span data-ttu-id="aee12-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="aee12-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-228">Checksum</span></span>

<span data-ttu-id="aee12-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-230">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-230">Definition</span></span>

<span data-ttu-id="aee12-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-233">From `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-234">Keywords</span></span>

<span data-ttu-id="aee12-235">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-235"></span></span>
|<span data-ttu-id="aee12-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-237">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-237">passport number</span></span>  <br/> <span data-ttu-id="aee12-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-238">danish passport number</span></span>  <br/> <span data-ttu-id="aee12-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-239">passport no</span></span>  <br/> <span data-ttu-id="aee12-240">pas</span><span class="sxs-lookup"><span data-stu-id="aee12-240">pas</span></span>  <br/> <span data-ttu-id="aee12-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="aee12-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="aee12-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="aee12-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="aee12-243">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-243">Format</span></span>

<span data-ttu-id="aee12-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="aee12-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-245">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-245">Pattern</span></span>

<span data-ttu-id="aee12-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-247">Checksum</span></span>

<span data-ttu-id="aee12-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-249">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-249">Definition</span></span>

<span data-ttu-id="aee12-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-252">From `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-253">Keywords</span></span>

<span data-ttu-id="aee12-254">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-254"></span></span>
|<span data-ttu-id="aee12-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-256">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-256">passport number</span></span>  <br/> <span data-ttu-id="aee12-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-257">estonian passport number</span></span>  <br/> <span data-ttu-id="aee12-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-258">passport no</span></span>  <br/> <span data-ttu-id="aee12-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="aee12-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="aee12-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="aee12-260">Finland</span></span>

<span data-ttu-id="aee12-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee12-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="aee12-262">フランス</span><span class="sxs-lookup"><span data-stu-id="aee12-262">France</span></span>

<span data-ttu-id="aee12-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee12-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="aee12-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="aee12-264">Germany</span></span>

<span data-ttu-id="aee12-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee12-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="aee12-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="aee12-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="aee12-267">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-267">Format</span></span>

<span data-ttu-id="aee12-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-269">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-269">Pattern</span></span>

<span data-ttu-id="aee12-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-271">Checksum</span></span>

<span data-ttu-id="aee12-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-273">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-273">Definition</span></span>

<span data-ttu-id="aee12-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-276">From `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-277">Keywords</span></span>

<span data-ttu-id="aee12-278">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-278"></span></span>
|<span data-ttu-id="aee12-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-280">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-280">passport number</span></span>  <br/> <span data-ttu-id="aee12-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-281">greek passport number</span></span>  <br/> <span data-ttu-id="aee12-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-282">passport no</span></span>  <br/> <span data-ttu-id="aee12-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="aee12-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="aee12-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="aee12-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="aee12-285">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-285">Format</span></span>

<span data-ttu-id="aee12-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-287">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-287">Pattern</span></span>

<span data-ttu-id="aee12-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-289">Checksum</span></span>

<span data-ttu-id="aee12-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-291">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-291">Definition</span></span>

<span data-ttu-id="aee12-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-294">From `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-295">Keywords</span></span>

<span data-ttu-id="aee12-296">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-296"></span></span>
|<span data-ttu-id="aee12-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-298">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-298">passport number</span></span>  <br/> <span data-ttu-id="aee12-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="aee12-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-300">passport no</span></span>  <br/> <span data-ttu-id="aee12-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="aee12-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="aee12-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="aee12-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="aee12-303">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-303">Format</span></span>

<span data-ttu-id="aee12-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-305">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-305">Pattern</span></span>

<span data-ttu-id="aee12-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="aee12-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="aee12-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="aee12-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-309">Checksum</span></span>

<span data-ttu-id="aee12-310">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-311">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-311">Definition</span></span>

<span data-ttu-id="aee12-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-314">From `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-315">Keywords</span></span>

<span data-ttu-id="aee12-316">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-316"></span></span>
|<span data-ttu-id="aee12-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-318">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-318">passport number</span></span>  <br/> <span data-ttu-id="aee12-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-319">irish passport number</span></span>  <br/> <span data-ttu-id="aee12-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-320">passport no</span></span>  <br/> <span data-ttu-id="aee12-321">pas</span><span class="sxs-lookup"><span data-stu-id="aee12-321">pas</span></span>  <br/> <span data-ttu-id="aee12-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="aee12-322">passport</span></span>  <br/> <span data-ttu-id="aee12-323">passeport</span><span class="sxs-lookup"><span data-stu-id="aee12-323">passeport</span></span>  <br/> <span data-ttu-id="aee12-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="aee12-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="aee12-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="aee12-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="aee12-326">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-326">Format</span></span>

<span data-ttu-id="aee12-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-328">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-328">Pattern</span></span>

<span data-ttu-id="aee12-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="aee12-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="aee12-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="aee12-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-332">Checksum</span></span>

<span data-ttu-id="aee12-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="aee12-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-334">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-334">Definition</span></span>

<span data-ttu-id="aee12-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-337">From `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-338">Keywords</span></span>

<span data-ttu-id="aee12-339">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-339"></span></span>
|<span data-ttu-id="aee12-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-341">italian passport number</span></span>  <br/> <span data-ttu-id="aee12-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="aee12-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="aee12-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="aee12-343">passaporto</span></span>  <br/> <span data-ttu-id="aee12-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="aee12-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="aee12-345">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-345">passport number</span></span>  <br/> <span data-ttu-id="aee12-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="aee12-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="aee12-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="aee12-347">passaporto numero</span></span>  <br/> <span data-ttu-id="aee12-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="aee12-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="aee12-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="aee12-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="aee12-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="aee12-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="aee12-351">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-351">Format</span></span>

<span data-ttu-id="aee12-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-353">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-353">Pattern</span></span>

<span data-ttu-id="aee12-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="aee12-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="aee12-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="aee12-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-357">Checksum</span></span>

<span data-ttu-id="aee12-358">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-359">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-359">Definition</span></span>

<span data-ttu-id="aee12-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-362">From `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-363">Keywords</span></span>

<span data-ttu-id="aee12-364">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-364"></span></span>
|<span data-ttu-id="aee12-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-366">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-366">passport number</span></span>  <br/> <span data-ttu-id="aee12-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-367">latvian passport number</span></span>  <br/> <span data-ttu-id="aee12-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-368">passport no</span></span>  <br/> <span data-ttu-id="aee12-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="aee12-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="aee12-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="aee12-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="aee12-371">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-371">Format</span></span>

<span data-ttu-id="aee12-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="aee12-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-373">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-373">Pattern</span></span>

<span data-ttu-id="aee12-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-375">Checksum</span></span>

<span data-ttu-id="aee12-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="aee12-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-377">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-377">Definition</span></span>

<span data-ttu-id="aee12-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-380">From `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-381">Keywords</span></span>

<span data-ttu-id="aee12-382">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-382"></span></span>
|<span data-ttu-id="aee12-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-384">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-384">passport number</span></span>  <br/> <span data-ttu-id="aee12-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="aee12-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-386">passport no</span></span>  <br/> <span data-ttu-id="aee12-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="aee12-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="aee12-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="aee12-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="aee12-389">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-389">Format</span></span>

<span data-ttu-id="aee12-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="aee12-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-391">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-391">Pattern</span></span>

<span data-ttu-id="aee12-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-393">Checksum</span></span>

<span data-ttu-id="aee12-394">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-395">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-395">Definition</span></span>

<span data-ttu-id="aee12-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-398">From `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-399">Keywords</span></span>

<span data-ttu-id="aee12-400">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-400"></span></span>
|<span data-ttu-id="aee12-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-402">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-402">passport number</span></span>  <br/> <span data-ttu-id="aee12-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-403">latvian passport number</span></span>  <br/> <span data-ttu-id="aee12-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-404">passport no</span></span>  <br/> <span data-ttu-id="aee12-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="aee12-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="aee12-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="aee12-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="aee12-407">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-407">Format</span></span>

<span data-ttu-id="aee12-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-409">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-409">Pattern</span></span>

 <span data-ttu-id="aee12-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="aee12-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-411">Checksum</span></span>

<span data-ttu-id="aee12-412">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-413">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-413">Definition</span></span>

<span data-ttu-id="aee12-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-416">From `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-417">Keywords</span></span>

<span data-ttu-id="aee12-418">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-418"></span></span>
|<span data-ttu-id="aee12-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-420">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-420">passport number</span></span>  <br/> <span data-ttu-id="aee12-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-421">maltese passport number</span></span>  <br/> <span data-ttu-id="aee12-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-422">passport no</span></span>  <br/> <span data-ttu-id="aee12-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="aee12-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="aee12-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="aee12-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="aee12-425">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-425">Format</span></span>

<span data-ttu-id="aee12-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="aee12-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-427">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-427">Pattern</span></span>

<span data-ttu-id="aee12-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="aee12-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-429">Checksum</span></span>

<span data-ttu-id="aee12-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="aee12-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-431">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-431">Definition</span></span>

<span data-ttu-id="aee12-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-434">From `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-435">Keywords</span></span>

<span data-ttu-id="aee12-436">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-436"></span></span>
|<span data-ttu-id="aee12-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-438">dutch passport number</span></span>  <br/> <span data-ttu-id="aee12-439">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-439">passport number</span></span>  <br/> <span data-ttu-id="aee12-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="aee12-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="aee12-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="aee12-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="aee12-442">paspoort</span></span>  <br/> <span data-ttu-id="aee12-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="aee12-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="aee12-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="aee12-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="aee12-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="aee12-445">Poland</span></span>

<span data-ttu-id="aee12-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee12-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="aee12-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="aee12-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="aee12-448">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-448">Format</span></span>

<span data-ttu-id="aee12-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="aee12-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-450">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-450">Pattern</span></span>

<span data-ttu-id="aee12-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="aee12-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="aee12-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="aee12-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="aee12-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-454">Checksum</span></span>

<span data-ttu-id="aee12-455">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-456">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-456">Definition</span></span>

<span data-ttu-id="aee12-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-459">From `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-460">Keywords</span></span>

<span data-ttu-id="aee12-461">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-461"></span></span>
|<span data-ttu-id="aee12-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-463">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-463">passport number</span></span>  <br/> <span data-ttu-id="aee12-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="aee12-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-465">passport no</span></span>  <br/> <span data-ttu-id="aee12-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="aee12-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="aee12-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="aee12-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="aee12-468">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-468">Format</span></span>

<span data-ttu-id="aee12-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-470">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-470">Pattern</span></span>

<span data-ttu-id="aee12-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-472">Checksum</span></span>

<span data-ttu-id="aee12-473">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-474">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-474">Definition</span></span>

<span data-ttu-id="aee12-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-477">From `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-478">Keywords</span></span>

<span data-ttu-id="aee12-479">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-479"></span></span>
|<span data-ttu-id="aee12-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-481">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-481">passport number</span></span>  <br/> <span data-ttu-id="aee12-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-482">romanian passport number</span></span>  <br/> <span data-ttu-id="aee12-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-483">passport no</span></span>  <br/> <span data-ttu-id="aee12-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="aee12-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="aee12-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="aee12-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="aee12-486">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-486">Format</span></span>

<span data-ttu-id="aee12-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="aee12-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-488">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-488">Pattern</span></span>

<span data-ttu-id="aee12-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="aee12-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-490">Checksum</span></span>

<span data-ttu-id="aee12-491">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-492">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-492">Definition</span></span>

<span data-ttu-id="aee12-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-495">From `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-496">Keywords</span></span>

<span data-ttu-id="aee12-497">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-497"></span></span>
|<span data-ttu-id="aee12-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-499">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-499">passport number</span></span>  <br/> <span data-ttu-id="aee12-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="aee12-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-501">passport no</span></span>  <br/> <span data-ttu-id="aee12-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="aee12-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="aee12-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="aee12-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="aee12-504">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-504">Format</span></span>

<span data-ttu-id="aee12-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-506">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-506">Pattern</span></span>

<span data-ttu-id="aee12-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="aee12-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="aee12-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="aee12-508">The letter "P"</span></span>
    
- <span data-ttu-id="aee12-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="aee12-509">One uppercase letter</span></span>
    
- <span data-ttu-id="aee12-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-511">Checksum</span></span>

<span data-ttu-id="aee12-512">いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-513">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-513">Definition</span></span>

<span data-ttu-id="aee12-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-516">From `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-517">Keywords</span></span>

<span data-ttu-id="aee12-518">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-518"></span></span>
|<span data-ttu-id="aee12-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-520">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-520">passport number</span></span>  <br/> <span data-ttu-id="aee12-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="aee12-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-522">passport no</span></span>  <br/> <span data-ttu-id="aee12-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="aee12-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="aee12-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="aee12-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="aee12-525">Format</span><span class="sxs-lookup"><span data-stu-id="aee12-525">Format</span></span>

<span data-ttu-id="aee12-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="aee12-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="aee12-527">パターン</span><span class="sxs-lookup"><span data-stu-id="aee12-527">Pattern</span></span>

<span data-ttu-id="aee12-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="aee12-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="aee12-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="aee12-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="aee12-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="aee12-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="aee12-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="aee12-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="aee12-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="aee12-532">Checksum</span></span>

<span data-ttu-id="aee12-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="aee12-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="aee12-534">定義</span><span class="sxs-lookup"><span data-stu-id="aee12-534">Definition</span></span>

<span data-ttu-id="aee12-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="aee12-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="aee12-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="aee12-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="aee12-537">From `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="aee12-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="aee12-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="aee12-538">Keywords</span></span>

<span data-ttu-id="aee12-539">| |</span><span class="sxs-lookup"><span data-stu-id="aee12-539"></span></span>
|<span data-ttu-id="aee12-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="aee12-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="aee12-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="aee12-541">passport</span></span>  <br/> <span data-ttu-id="aee12-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="aee12-542">spain passport</span></span>  <br/> <span data-ttu-id="aee12-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="aee12-543">passport book</span></span>  <br/> <span data-ttu-id="aee12-544">passport number</span><span class="sxs-lookup"><span data-stu-id="aee12-544">passport number</span></span>  <br/> <span data-ttu-id="aee12-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="aee12-545">passport no</span></span>  <br/> <span data-ttu-id="aee12-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="aee12-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="aee12-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="aee12-547">número pasaporte</span></span>  <br/> <span data-ttu-id="aee12-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="aee12-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="aee12-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="aee12-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="aee12-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="aee12-550">Sweden</span></span>

<span data-ttu-id="aee12-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee12-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="aee12-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="aee12-552">UK</span></span>

<span data-ttu-id="aee12-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aee12-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="aee12-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="aee12-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="aee12-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="aee12-555">See also</span></span>

[<span data-ttu-id="aee12-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="aee12-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

