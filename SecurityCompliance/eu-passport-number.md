---
title: EU パスポート番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: 3ab92e87607f41cffa8c15f1179a4eef5369cb29
ms.sourcegitcommit: ed822a776d3419853453583e882f3c61ca26d4b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2019
ms.locfileid: "30410932"
---
# <a name="eu-passport-number"></a><span data-ttu-id="1dfd7-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-104">EU Passport Number</span></span>

<span data-ttu-id="1dfd7-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="1dfd7-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="1dfd7-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-108">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-108">Format</span></span>

<span data-ttu-id="1dfd7-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-110">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-110">Pattern</span></span>

<span data-ttu-id="1dfd7-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="1dfd7-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1dfd7-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-113">One space (optional)</span></span>
    
- <span data-ttu-id="1dfd7-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-115">Checksum</span></span>

<span data-ttu-id="1dfd7-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-117">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-117">Definition</span></span>

<span data-ttu-id="1dfd7-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-120">from `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-121">Keywords</span></span>

<span data-ttu-id="1dfd7-122">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-122"></span></span>
|<span data-ttu-id="1dfd7-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-124">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-124">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-125">austrian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-126">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="1dfd7-127">reisepass</span></span>  <br/> <span data-ttu-id="1dfd7-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="1dfd7-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="1dfd7-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="1dfd7-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-130">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-130">Format</span></span>

<span data-ttu-id="1dfd7-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-132">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-132">Pattern</span></span>

<span data-ttu-id="1dfd7-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-134">Checksum</span></span>

<span data-ttu-id="1dfd7-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-136">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-136">Definition</span></span>

<span data-ttu-id="1dfd7-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-139">from `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-140">Keywords</span></span>

<span data-ttu-id="1dfd7-141">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-141"></span></span>
|<span data-ttu-id="1dfd7-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-143">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-143">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-144">belgian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-145">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="1dfd7-146">paspoort</span></span>  <br/> <span data-ttu-id="1dfd7-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1dfd7-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="1dfd7-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="1dfd7-148">reisepass kein</span></span>  <br/> <span data-ttu-id="1dfd7-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="1dfd7-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="1dfd7-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-151">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-151">Format</span></span>

<span data-ttu-id="1dfd7-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-153">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-153">Pattern</span></span>

 <span data-ttu-id="1dfd7-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-155">Checksum</span></span>

<span data-ttu-id="1dfd7-156">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-157">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-157">Definition</span></span>

<span data-ttu-id="1dfd7-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-160">from `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-161">Keywords</span></span>

<span data-ttu-id="1dfd7-162">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-162"></span></span>
|<span data-ttu-id="1dfd7-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-164">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-164">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-166">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-167">номернапаспорта</span><span class="sxs-lookup"><span data-stu-id="1dfd7-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="1dfd7-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-169">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-169">Format</span></span>

<span data-ttu-id="1dfd7-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-171">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-171">Pattern</span></span>

 <span data-ttu-id="1dfd7-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-173">Checksum</span></span>

<span data-ttu-id="1dfd7-174">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-175">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-175">Definition</span></span>

<span data-ttu-id="1dfd7-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-178">from `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-179">Keywords</span></span>

<span data-ttu-id="1dfd7-180">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-180"></span></span>
|<span data-ttu-id="1dfd7-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-182">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-182">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-183">croatian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-184">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="1dfd7-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="1dfd7-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="1dfd7-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-187">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-187">Format</span></span>

<span data-ttu-id="1dfd7-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-189">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-189">Pattern</span></span>

<span data-ttu-id="1dfd7-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-191">Checksum</span></span>

<span data-ttu-id="1dfd7-192">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-193">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-193">Definition</span></span>

<span data-ttu-id="1dfd7-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-196">from `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-197">Keywords</span></span>

<span data-ttu-id="1dfd7-198">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-198"></span></span>
|<span data-ttu-id="1dfd7-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-200">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-200">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="1dfd7-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-202">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-203">αριθμόδιαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="1dfd7-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="1dfd7-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="1dfd7-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-205">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-205">Format</span></span>

<span data-ttu-id="1dfd7-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-207">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-207">Pattern</span></span>

<span data-ttu-id="1dfd7-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-209">Checksum</span></span>

<span data-ttu-id="1dfd7-210">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-211">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-211">Definition</span></span>

<span data-ttu-id="1dfd7-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-214">from `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-215">Keywords</span></span>

<span data-ttu-id="1dfd7-216">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-216"></span></span>
|<span data-ttu-id="1dfd7-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-218">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-218">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-219">czech passport number</span></span>  <br/> <span data-ttu-id="1dfd7-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-220">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="1dfd7-221">cestovní pas</span></span>  <br/> <span data-ttu-id="1dfd7-222">pas</span><span class="sxs-lookup"><span data-stu-id="1dfd7-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="1dfd7-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="1dfd7-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-224">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-224">Format</span></span>

<span data-ttu-id="1dfd7-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-226">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-226">Pattern</span></span>

 <span data-ttu-id="1dfd7-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-228">Checksum</span></span>

<span data-ttu-id="1dfd7-229">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-230">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-230">Definition</span></span>

<span data-ttu-id="1dfd7-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-233">from `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-234">Keywords</span></span>

<span data-ttu-id="1dfd7-235">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-235"></span></span>
|<span data-ttu-id="1dfd7-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-237">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-237">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-238">danish passport number</span></span>  <br/> <span data-ttu-id="1dfd7-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-239">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-240">pas</span><span class="sxs-lookup"><span data-stu-id="1dfd7-240">pas</span></span>  <br/> <span data-ttu-id="1dfd7-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="1dfd7-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="1dfd7-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-243">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-243">Format</span></span>

<span data-ttu-id="1dfd7-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-245">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-245">Pattern</span></span>

<span data-ttu-id="1dfd7-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-247">Checksum</span></span>

<span data-ttu-id="1dfd7-248">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-249">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-249">Definition</span></span>

<span data-ttu-id="1dfd7-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-252">from `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-253">Keywords</span></span>

<span data-ttu-id="1dfd7-254">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-254"></span></span>
|<span data-ttu-id="1dfd7-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-256">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-256">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-257">estonian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-258">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="1dfd7-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="1dfd7-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="1dfd7-260">Finland</span></span>

<span data-ttu-id="1dfd7-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="1dfd7-262">フランス</span><span class="sxs-lookup"><span data-stu-id="1dfd7-262">France</span></span>

<span data-ttu-id="1dfd7-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="1dfd7-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-264">Germany</span></span>

<span data-ttu-id="1dfd7-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="1dfd7-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-267">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-267">Format</span></span>

<span data-ttu-id="1dfd7-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-269">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-269">Pattern</span></span>

<span data-ttu-id="1dfd7-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-271">Checksum</span></span>

<span data-ttu-id="1dfd7-272">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-273">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-273">Definition</span></span>

<span data-ttu-id="1dfd7-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-276">from `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-277">Keywords</span></span>

<span data-ttu-id="1dfd7-278">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-278"></span></span>
|<span data-ttu-id="1dfd7-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-280">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-280">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-281">greek passport number</span></span>  <br/> <span data-ttu-id="1dfd7-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-282">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="1dfd7-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="1dfd7-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="1dfd7-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-285">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-285">Format</span></span>

<span data-ttu-id="1dfd7-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-287">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-287">Pattern</span></span>

<span data-ttu-id="1dfd7-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-289">Checksum</span></span>

<span data-ttu-id="1dfd7-290">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-291">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-291">Definition</span></span>

<span data-ttu-id="1dfd7-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-294">from `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-295">Keywords</span></span>

<span data-ttu-id="1dfd7-296">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-296"></span></span>
|<span data-ttu-id="1dfd7-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-298">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-298">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-300">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="1dfd7-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="1dfd7-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="1dfd7-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-303">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-303">Format</span></span>

<span data-ttu-id="1dfd7-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-305">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-305">Pattern</span></span>

<span data-ttu-id="1dfd7-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1dfd7-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1dfd7-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-309">Checksum</span></span>

<span data-ttu-id="1dfd7-310">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-311">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-311">Definition</span></span>

<span data-ttu-id="1dfd7-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-314">from `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-315">Keywords</span></span>

<span data-ttu-id="1dfd7-316">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-316"></span></span>
|<span data-ttu-id="1dfd7-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-318">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-318">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-319">irish passport number</span></span>  <br/> <span data-ttu-id="1dfd7-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-320">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-321">pas</span><span class="sxs-lookup"><span data-stu-id="1dfd7-321">pas</span></span>  <br/> <span data-ttu-id="1dfd7-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="1dfd7-322">passport</span></span>  <br/> <span data-ttu-id="1dfd7-323">passeport</span><span class="sxs-lookup"><span data-stu-id="1dfd7-323">passeport</span></span>  <br/> <span data-ttu-id="1dfd7-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="1dfd7-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="1dfd7-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-326">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-326">Format</span></span>

<span data-ttu-id="1dfd7-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-328">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-328">Pattern</span></span>

<span data-ttu-id="1dfd7-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1dfd7-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1dfd7-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-332">Checksum</span></span>

<span data-ttu-id="1dfd7-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-334">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-334">Definition</span></span>

<span data-ttu-id="1dfd7-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-337">from `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-338">Keywords</span></span>

<span data-ttu-id="1dfd7-339">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-339"></span></span>
|<span data-ttu-id="1dfd7-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-341">italian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="1dfd7-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="1dfd7-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="1dfd7-343">passaporto</span></span>  <br/> <span data-ttu-id="1dfd7-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="1dfd7-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="1dfd7-345">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-345">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1dfd7-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="1dfd7-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="1dfd7-347">passaporto numero</span></span>  <br/> <span data-ttu-id="1dfd7-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="1dfd7-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="1dfd7-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="1dfd7-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="1dfd7-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-351">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-351">Format</span></span>

<span data-ttu-id="1dfd7-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-353">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-353">Pattern</span></span>

<span data-ttu-id="1dfd7-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="1dfd7-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="1dfd7-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-357">Checksum</span></span>

<span data-ttu-id="1dfd7-358">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-359">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-359">Definition</span></span>

<span data-ttu-id="1dfd7-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-362">from `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-363">Keywords</span></span>

<span data-ttu-id="1dfd7-364">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-364"></span></span>
|<span data-ttu-id="1dfd7-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-366">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-366">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-367">latvian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-368">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="1dfd7-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="1dfd7-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-371">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-371">Format</span></span>

<span data-ttu-id="1dfd7-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-373">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-373">Pattern</span></span>

<span data-ttu-id="1dfd7-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-375">Checksum</span></span>

<span data-ttu-id="1dfd7-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-377">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-377">Definition</span></span>

<span data-ttu-id="1dfd7-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-380">from `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-381">Keywords</span></span>

<span data-ttu-id="1dfd7-382">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-382"></span></span>
|<span data-ttu-id="1dfd7-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-384">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-384">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-386">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="1dfd7-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="1dfd7-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="1dfd7-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-389">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-389">Format</span></span>

<span data-ttu-id="1dfd7-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-391">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-391">Pattern</span></span>

<span data-ttu-id="1dfd7-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-393">Checksum</span></span>

<span data-ttu-id="1dfd7-394">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-395">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-395">Definition</span></span>

<span data-ttu-id="1dfd7-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-398">from `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-399">Keywords</span></span>

<span data-ttu-id="1dfd7-400">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-400"></span></span>
|<span data-ttu-id="1dfd7-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-402">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-402">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-403">latvian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-404">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="1dfd7-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="1dfd7-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-407">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-407">Format</span></span>

<span data-ttu-id="1dfd7-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-409">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-409">Pattern</span></span>

 <span data-ttu-id="1dfd7-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-411">Checksum</span></span>

<span data-ttu-id="1dfd7-412">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-413">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-413">Definition</span></span>

<span data-ttu-id="1dfd7-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-416">from `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-417">Keywords</span></span>

<span data-ttu-id="1dfd7-418">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-418"></span></span>
|<span data-ttu-id="1dfd7-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-420">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-420">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-421">maltese passport number</span></span>  <br/> <span data-ttu-id="1dfd7-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-422">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="1dfd7-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="1dfd7-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-425">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-425">Format</span></span>

<span data-ttu-id="1dfd7-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-427">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-427">Pattern</span></span>

<span data-ttu-id="1dfd7-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-429">Checksum</span></span>

<span data-ttu-id="1dfd7-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-431">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-431">Definition</span></span>

<span data-ttu-id="1dfd7-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-434">from `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-435">Keywords</span></span>

<span data-ttu-id="1dfd7-436">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-436"></span></span>
|<span data-ttu-id="1dfd7-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-438">dutch passport number</span></span>  <br/> <span data-ttu-id="1dfd7-439">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-439">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="1dfd7-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="1dfd7-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="1dfd7-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="1dfd7-442">paspoort</span></span>  <br/> <span data-ttu-id="1dfd7-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1dfd7-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="1dfd7-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="1dfd7-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="1dfd7-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="1dfd7-445">Poland</span></span>

<span data-ttu-id="1dfd7-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="1dfd7-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="1dfd7-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-448">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-448">Format</span></span>

<span data-ttu-id="1dfd7-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-450">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-450">Pattern</span></span>

<span data-ttu-id="1dfd7-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="1dfd7-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="1dfd7-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="1dfd7-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-454">Checksum</span></span>

<span data-ttu-id="1dfd7-455">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-456">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-456">Definition</span></span>

<span data-ttu-id="1dfd7-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-459">from `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-460">Keywords</span></span>

<span data-ttu-id="1dfd7-461">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-461"></span></span>
|<span data-ttu-id="1dfd7-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-463">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-463">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="1dfd7-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-465">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="1dfd7-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="1dfd7-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-468">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-468">Format</span></span>

<span data-ttu-id="1dfd7-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-470">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-470">Pattern</span></span>

<span data-ttu-id="1dfd7-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-472">Checksum</span></span>

<span data-ttu-id="1dfd7-473">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-474">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-474">Definition</span></span>

<span data-ttu-id="1dfd7-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-477">from `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-478">Keywords</span></span>

<span data-ttu-id="1dfd7-479">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-479"></span></span>
|<span data-ttu-id="1dfd7-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-481">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-481">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-482">romanian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-483">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="1dfd7-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="1dfd7-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-486">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-486">Format</span></span>

<span data-ttu-id="1dfd7-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-488">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-488">Pattern</span></span>

<span data-ttu-id="1dfd7-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="1dfd7-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-490">Checksum</span></span>

<span data-ttu-id="1dfd7-491">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-492">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-492">Definition</span></span>

<span data-ttu-id="1dfd7-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-495">from `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-496">Keywords</span></span>

<span data-ttu-id="1dfd7-497">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-497"></span></span>
|<span data-ttu-id="1dfd7-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-499">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-499">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-501">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="1dfd7-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="1dfd7-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="1dfd7-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-504">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-504">Format</span></span>

<span data-ttu-id="1dfd7-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-506">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-506">Pattern</span></span>

<span data-ttu-id="1dfd7-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="1dfd7-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="1dfd7-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="1dfd7-508">The letter "P"</span></span>
    
- <span data-ttu-id="1dfd7-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-509">One uppercase letter</span></span>
    
- <span data-ttu-id="1dfd7-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-511">Checksum</span></span>

<span data-ttu-id="1dfd7-512">不要</span><span class="sxs-lookup"><span data-stu-id="1dfd7-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-513">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-513">Definition</span></span>

<span data-ttu-id="1dfd7-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-516">from `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-517">Keywords</span></span>

<span data-ttu-id="1dfd7-518">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-518"></span></span>
|<span data-ttu-id="1dfd7-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-520">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-520">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="1dfd7-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-522">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="1dfd7-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="1dfd7-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="1dfd7-525">Format</span><span class="sxs-lookup"><span data-stu-id="1dfd7-525">Format</span></span>

<span data-ttu-id="1dfd7-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="1dfd7-527">パターン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-527">Pattern</span></span>

<span data-ttu-id="1dfd7-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="1dfd7-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="1dfd7-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="1dfd7-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="1dfd7-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="1dfd7-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="1dfd7-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="1dfd7-532">Checksum</span></span>

<span data-ttu-id="1dfd7-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="1dfd7-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="1dfd7-534">定義</span><span class="sxs-lookup"><span data-stu-id="1dfd7-534">Definition</span></span>

<span data-ttu-id="1dfd7-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="1dfd7-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="1dfd7-537">from `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="1dfd7-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="1dfd7-538">Keywords</span></span>

<span data-ttu-id="1dfd7-539">| |</span><span class="sxs-lookup"><span data-stu-id="1dfd7-539"></span></span>
|<span data-ttu-id="1dfd7-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="1dfd7-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="1dfd7-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="1dfd7-541">passport</span></span>  <br/> <span data-ttu-id="1dfd7-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="1dfd7-542">spain passport</span></span>  <br/> <span data-ttu-id="1dfd7-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="1dfd7-543">passport book</span></span>  <br/> <span data-ttu-id="1dfd7-544">passport number</span><span class="sxs-lookup"><span data-stu-id="1dfd7-544">passport number</span></span>  <br/> <span data-ttu-id="1dfd7-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="1dfd7-545">passport no</span></span>  <br/> <span data-ttu-id="1dfd7-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="1dfd7-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="1dfd7-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="1dfd7-547">número pasaporte</span></span>  <br/> <span data-ttu-id="1dfd7-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="1dfd7-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="1dfd7-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="1dfd7-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="1dfd7-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="1dfd7-550">Sweden</span></span>

<span data-ttu-id="1dfd7-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="1dfd7-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="1dfd7-552">UK</span></span>

<span data-ttu-id="1dfd7-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1dfd7-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="1dfd7-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="1dfd7-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1dfd7-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="1dfd7-555">See also</span></span>

[<span data-ttu-id="1dfd7-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="1dfd7-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

