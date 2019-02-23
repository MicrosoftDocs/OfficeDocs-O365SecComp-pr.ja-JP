---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8c00df57-9fb3-459c-ba87-40480c87bd55
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: c46f683bd1baf651bcf13c1766dfff3cb953b341
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218267"
---
# <a name="eu-passport-number"></a><span data-ttu-id="d9a8f-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-104">EU Passport Number</span></span>

<span data-ttu-id="d9a8f-p102">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d9a8f-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-108">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-108">Format</span></span>

<span data-ttu-id="d9a8f-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-110">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-110">Pattern</span></span>

<span data-ttu-id="d9a8f-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="d9a8f-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="d9a8f-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-113">One space (optional)</span></span>
    
- <span data-ttu-id="d9a8f-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-115">Checksum</span></span>

<span data-ttu-id="d9a8f-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-117">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-117">Definition</span></span>

<span data-ttu-id="d9a8f-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-120">from `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-121">Keywords</span></span>

<span data-ttu-id="d9a8f-122">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-122"></span></span>
|<span data-ttu-id="d9a8f-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-124">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-124">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-125">austrian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-126">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="d9a8f-127">reisepass</span></span>  <br/> <span data-ttu-id="d9a8f-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="d9a8f-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="d9a8f-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="d9a8f-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-130">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-130">Format</span></span>

<span data-ttu-id="d9a8f-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-132">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-132">Pattern</span></span>

<span data-ttu-id="d9a8f-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-134">Checksum</span></span>

<span data-ttu-id="d9a8f-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-136">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-136">Definition</span></span>

<span data-ttu-id="d9a8f-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-139">from `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-140">Keywords</span></span>

<span data-ttu-id="d9a8f-141">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-141"></span></span>
|<span data-ttu-id="d9a8f-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-143">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-143">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-144">belgian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-145">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="d9a8f-146">paspoort</span></span>  <br/> <span data-ttu-id="d9a8f-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d9a8f-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="d9a8f-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="d9a8f-148">reisepass kein</span></span>  <br/> <span data-ttu-id="d9a8f-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="d9a8f-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="d9a8f-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-151">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-151">Format</span></span>

<span data-ttu-id="d9a8f-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-153">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-153">Pattern</span></span>

 <span data-ttu-id="d9a8f-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-155">Checksum</span></span>

<span data-ttu-id="d9a8f-156">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-157">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-157">Definition</span></span>

<span data-ttu-id="d9a8f-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-160">from `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-161">Keywords</span></span>

<span data-ttu-id="d9a8f-162">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-162"></span></span>
|<span data-ttu-id="d9a8f-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-164">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-164">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-166">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-167">номернапаспорта</span><span class="sxs-lookup"><span data-stu-id="d9a8f-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="d9a8f-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-169">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-169">Format</span></span>

<span data-ttu-id="d9a8f-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-171">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-171">Pattern</span></span>

 <span data-ttu-id="d9a8f-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-173">Checksum</span></span>

<span data-ttu-id="d9a8f-174">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-175">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-175">Definition</span></span>

<span data-ttu-id="d9a8f-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-178">from `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-179">Keywords</span></span>

<span data-ttu-id="d9a8f-180">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-180"></span></span>
|<span data-ttu-id="d9a8f-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-182">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-182">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-183">croatian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-184">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="d9a8f-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="d9a8f-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="d9a8f-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-187">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-187">Format</span></span>

<span data-ttu-id="d9a8f-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-189">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-189">Pattern</span></span>

<span data-ttu-id="d9a8f-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-191">Checksum</span></span>

<span data-ttu-id="d9a8f-192">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-193">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-193">Definition</span></span>

<span data-ttu-id="d9a8f-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-196">from `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-197">Keywords</span></span>

<span data-ttu-id="d9a8f-198">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-198"></span></span>
|<span data-ttu-id="d9a8f-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-200">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-200">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="d9a8f-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-202">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-203">αριθμόδιαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="d9a8f-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="d9a8f-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="d9a8f-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-205">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-205">Format</span></span>

<span data-ttu-id="d9a8f-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-207">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-207">Pattern</span></span>

<span data-ttu-id="d9a8f-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-209">Checksum</span></span>

<span data-ttu-id="d9a8f-210">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-211">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-211">Definition</span></span>

<span data-ttu-id="d9a8f-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-214">from `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-215">Keywords</span></span>

<span data-ttu-id="d9a8f-216">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-216"></span></span>
|<span data-ttu-id="d9a8f-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-218">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-218">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-219">czech passport number</span></span>  <br/> <span data-ttu-id="d9a8f-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-220">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="d9a8f-221">cestovní pas</span></span>  <br/> <span data-ttu-id="d9a8f-222">pas</span><span class="sxs-lookup"><span data-stu-id="d9a8f-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="d9a8f-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="d9a8f-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-224">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-224">Format</span></span>

<span data-ttu-id="d9a8f-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-226">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-226">Pattern</span></span>

 <span data-ttu-id="d9a8f-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-228">Checksum</span></span>

<span data-ttu-id="d9a8f-229">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-230">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-230">Definition</span></span>

<span data-ttu-id="d9a8f-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-233">from `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-234">Keywords</span></span>

<span data-ttu-id="d9a8f-235">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-235"></span></span>
|<span data-ttu-id="d9a8f-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-237">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-237">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-238">danish passport number</span></span>  <br/> <span data-ttu-id="d9a8f-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-239">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-240">pas</span><span class="sxs-lookup"><span data-stu-id="d9a8f-240">pas</span></span>  <br/> <span data-ttu-id="d9a8f-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="d9a8f-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="d9a8f-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-243">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-243">Format</span></span>

<span data-ttu-id="d9a8f-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-245">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-245">Pattern</span></span>

<span data-ttu-id="d9a8f-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-247">Checksum</span></span>

<span data-ttu-id="d9a8f-248">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-249">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-249">Definition</span></span>

<span data-ttu-id="d9a8f-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-252">from `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-253">Keywords</span></span>

<span data-ttu-id="d9a8f-254">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-254"></span></span>
|<span data-ttu-id="d9a8f-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-256">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-256">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-257">estonian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-258">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="d9a8f-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="d9a8f-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="d9a8f-260">Finland</span></span>

<span data-ttu-id="d9a8f-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="d9a8f-262">フランス</span><span class="sxs-lookup"><span data-stu-id="d9a8f-262">France</span></span>

<span data-ttu-id="d9a8f-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d9a8f-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-264">Germany</span></span>

<span data-ttu-id="d9a8f-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d9a8f-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-267">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-267">Format</span></span>

<span data-ttu-id="d9a8f-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-269">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-269">Pattern</span></span>

<span data-ttu-id="d9a8f-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-271">Checksum</span></span>

<span data-ttu-id="d9a8f-272">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-273">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-273">Definition</span></span>

<span data-ttu-id="d9a8f-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-276">from `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-277">Keywords</span></span>

<span data-ttu-id="d9a8f-278">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-278"></span></span>
|<span data-ttu-id="d9a8f-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-280">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-280">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-281">greek passport number</span></span>  <br/> <span data-ttu-id="d9a8f-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-282">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="d9a8f-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="d9a8f-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="d9a8f-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-285">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-285">Format</span></span>

<span data-ttu-id="d9a8f-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-287">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-287">Pattern</span></span>

<span data-ttu-id="d9a8f-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-289">Checksum</span></span>

<span data-ttu-id="d9a8f-290">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-291">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-291">Definition</span></span>

<span data-ttu-id="d9a8f-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-294">from `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-295">Keywords</span></span>

<span data-ttu-id="d9a8f-296">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-296"></span></span>
|<span data-ttu-id="d9a8f-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-298">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-298">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-300">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="d9a8f-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="d9a8f-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="d9a8f-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-303">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-303">Format</span></span>

<span data-ttu-id="d9a8f-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-305">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-305">Pattern</span></span>

<span data-ttu-id="d9a8f-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d9a8f-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d9a8f-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-309">Checksum</span></span>

<span data-ttu-id="d9a8f-310">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-311">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-311">Definition</span></span>

<span data-ttu-id="d9a8f-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-314">from `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-315">Keywords</span></span>

<span data-ttu-id="d9a8f-316">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-316"></span></span>
|<span data-ttu-id="d9a8f-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-318">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-318">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-319">irish passport number</span></span>  <br/> <span data-ttu-id="d9a8f-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-320">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-321">pas</span><span class="sxs-lookup"><span data-stu-id="d9a8f-321">pas</span></span>  <br/> <span data-ttu-id="d9a8f-322">passport</span><span class="sxs-lookup"><span data-stu-id="d9a8f-322">passport</span></span>  <br/> <span data-ttu-id="d9a8f-323">passeport</span><span class="sxs-lookup"><span data-stu-id="d9a8f-323">passeport</span></span>  <br/> <span data-ttu-id="d9a8f-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="d9a8f-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="d9a8f-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-326">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-326">Format</span></span>

<span data-ttu-id="d9a8f-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-328">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-328">Pattern</span></span>

<span data-ttu-id="d9a8f-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d9a8f-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d9a8f-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-332">Checksum</span></span>

<span data-ttu-id="d9a8f-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-334">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-334">Definition</span></span>

<span data-ttu-id="d9a8f-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-337">from `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-338">Keywords</span></span>

<span data-ttu-id="d9a8f-339">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-339"></span></span>
|<span data-ttu-id="d9a8f-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-341">italian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="d9a8f-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="d9a8f-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="d9a8f-343">passaporto</span></span>  <br/> <span data-ttu-id="d9a8f-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="d9a8f-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="d9a8f-345">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-345">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="d9a8f-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="d9a8f-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="d9a8f-347">passaporto numero</span></span>  <br/> <span data-ttu-id="d9a8f-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="d9a8f-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="d9a8f-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="d9a8f-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="d9a8f-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-351">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-351">Format</span></span>

<span data-ttu-id="d9a8f-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-353">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-353">Pattern</span></span>

<span data-ttu-id="d9a8f-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="d9a8f-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="d9a8f-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-357">Checksum</span></span>

<span data-ttu-id="d9a8f-358">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-359">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-359">Definition</span></span>

<span data-ttu-id="d9a8f-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-362">from `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-363">Keywords</span></span>

<span data-ttu-id="d9a8f-364">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-364"></span></span>
|<span data-ttu-id="d9a8f-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-366">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-366">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-367">latvian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-368">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="d9a8f-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="d9a8f-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-371">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-371">Format</span></span>

<span data-ttu-id="d9a8f-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-373">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-373">Pattern</span></span>

<span data-ttu-id="d9a8f-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-375">Checksum</span></span>

<span data-ttu-id="d9a8f-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-377">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-377">Definition</span></span>

<span data-ttu-id="d9a8f-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-380">from `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-381">Keywords</span></span>

<span data-ttu-id="d9a8f-382">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-382"></span></span>
|<span data-ttu-id="d9a8f-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-384">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-384">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-386">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="d9a8f-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="d9a8f-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="d9a8f-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-389">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-389">Format</span></span>

<span data-ttu-id="d9a8f-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-391">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-391">Pattern</span></span>

<span data-ttu-id="d9a8f-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-393">Checksum</span></span>

<span data-ttu-id="d9a8f-394">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-395">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-395">Definition</span></span>

<span data-ttu-id="d9a8f-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-398">from `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-399">Keywords</span></span>

<span data-ttu-id="d9a8f-400">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-400"></span></span>
|<span data-ttu-id="d9a8f-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-402">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-402">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-403">latvian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-404">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="d9a8f-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="d9a8f-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-407">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-407">Format</span></span>

<span data-ttu-id="d9a8f-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-409">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-409">Pattern</span></span>

 <span data-ttu-id="d9a8f-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-411">Checksum</span></span>

<span data-ttu-id="d9a8f-412">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-413">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-413">Definition</span></span>

<span data-ttu-id="d9a8f-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-416">from `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-417">Keywords</span></span>

<span data-ttu-id="d9a8f-418">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-418"></span></span>
|<span data-ttu-id="d9a8f-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-420">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-420">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-421">maltese passport number</span></span>  <br/> <span data-ttu-id="d9a8f-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-422">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="d9a8f-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="d9a8f-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-425">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-425">Format</span></span>

<span data-ttu-id="d9a8f-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-427">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-427">Pattern</span></span>

<span data-ttu-id="d9a8f-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-429">Checksum</span></span>

<span data-ttu-id="d9a8f-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-431">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-431">Definition</span></span>

<span data-ttu-id="d9a8f-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-434">from `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-435">Keywords</span></span>

<span data-ttu-id="d9a8f-436">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-436"></span></span>
|<span data-ttu-id="d9a8f-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-438">dutch passport number</span></span>  <br/> <span data-ttu-id="d9a8f-439">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-439">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="d9a8f-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="d9a8f-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="d9a8f-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="d9a8f-442">paspoort</span></span>  <br/> <span data-ttu-id="d9a8f-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d9a8f-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="d9a8f-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="d9a8f-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="d9a8f-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="d9a8f-445">Poland</span></span>

<span data-ttu-id="d9a8f-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d9a8f-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="d9a8f-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-448">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-448">Format</span></span>

<span data-ttu-id="d9a8f-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-450">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-450">Pattern</span></span>

<span data-ttu-id="d9a8f-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="d9a8f-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="d9a8f-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="d9a8f-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-454">Checksum</span></span>

<span data-ttu-id="d9a8f-455">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-456">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-456">Definition</span></span>

<span data-ttu-id="d9a8f-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-459">from `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-460">Keywords</span></span>

<span data-ttu-id="d9a8f-461">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-461"></span></span>
|<span data-ttu-id="d9a8f-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-463">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-463">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="d9a8f-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-465">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="d9a8f-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="d9a8f-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-468">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-468">Format</span></span>

<span data-ttu-id="d9a8f-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-470">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-470">Pattern</span></span>

<span data-ttu-id="d9a8f-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-472">Checksum</span></span>

<span data-ttu-id="d9a8f-473">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-474">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-474">Definition</span></span>

<span data-ttu-id="d9a8f-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-477">from `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-478">Keywords</span></span>

<span data-ttu-id="d9a8f-479">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-479"></span></span>
|<span data-ttu-id="d9a8f-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-481">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-481">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-482">romanian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-483">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="d9a8f-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="d9a8f-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-486">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-486">Format</span></span>

<span data-ttu-id="d9a8f-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-488">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-488">Pattern</span></span>

<span data-ttu-id="d9a8f-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d9a8f-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-490">Checksum</span></span>

<span data-ttu-id="d9a8f-491">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-492">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-492">Definition</span></span>

<span data-ttu-id="d9a8f-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-495">from `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-496">Keywords</span></span>

<span data-ttu-id="d9a8f-497">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-497"></span></span>
|<span data-ttu-id="d9a8f-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-499">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-499">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-501">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="d9a8f-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="d9a8f-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="d9a8f-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-504">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-504">Format</span></span>

<span data-ttu-id="d9a8f-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-506">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-506">Pattern</span></span>

<span data-ttu-id="d9a8f-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="d9a8f-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="d9a8f-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="d9a8f-508">The letter "P"</span></span>
    
- <span data-ttu-id="d9a8f-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-509">One uppercase letter</span></span>
    
- <span data-ttu-id="d9a8f-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-511">Checksum</span></span>

<span data-ttu-id="d9a8f-512">なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-513">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-513">Definition</span></span>

<span data-ttu-id="d9a8f-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-516">from `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-517">Keywords</span></span>

<span data-ttu-id="d9a8f-518">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-518"></span></span>
|<span data-ttu-id="d9a8f-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-520">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-520">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="d9a8f-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-522">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="d9a8f-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="d9a8f-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="d9a8f-525">形式</span><span class="sxs-lookup"><span data-stu-id="d9a8f-525">Format</span></span>

<span data-ttu-id="d9a8f-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d9a8f-527">パターン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-527">Pattern</span></span>

<span data-ttu-id="d9a8f-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="d9a8f-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="d9a8f-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="d9a8f-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="d9a8f-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d9a8f-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d9a8f-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d9a8f-532">Checksum</span></span>

<span data-ttu-id="d9a8f-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="d9a8f-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="d9a8f-534">定義</span><span class="sxs-lookup"><span data-stu-id="d9a8f-534">Definition</span></span>

<span data-ttu-id="d9a8f-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d9a8f-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d9a8f-537">from `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="d9a8f-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="d9a8f-538">Keywords</span></span>

<span data-ttu-id="d9a8f-539">| |</span><span class="sxs-lookup"><span data-stu-id="d9a8f-539"></span></span>
|<span data-ttu-id="d9a8f-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="d9a8f-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="d9a8f-541">passport</span><span class="sxs-lookup"><span data-stu-id="d9a8f-541">passport</span></span>  <br/> <span data-ttu-id="d9a8f-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="d9a8f-542">spain passport</span></span>  <br/> <span data-ttu-id="d9a8f-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="d9a8f-543">passport book</span></span>  <br/> <span data-ttu-id="d9a8f-544">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="d9a8f-544">passport number</span></span>  <br/> <span data-ttu-id="d9a8f-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="d9a8f-545">passport no</span></span>  <br/> <span data-ttu-id="d9a8f-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="d9a8f-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="d9a8f-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="d9a8f-547">número pasaporte</span></span>  <br/> <span data-ttu-id="d9a8f-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="d9a8f-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="d9a8f-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="d9a8f-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="d9a8f-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="d9a8f-550">Sweden</span></span>

<span data-ttu-id="d9a8f-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="d9a8f-552">英国</span><span class="sxs-lookup"><span data-stu-id="d9a8f-552">UK</span></span>

<span data-ttu-id="d9a8f-p103">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「米国/英国のパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9a8f-p103">For details, see the section "U.S. / U.K. Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9a8f-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="d9a8f-555">See also</span></span>

[<span data-ttu-id="d9a8f-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="d9a8f-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

