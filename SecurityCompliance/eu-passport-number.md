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
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256825"
---
# <a name="eu-passport-number"></a><span data-ttu-id="00943-104">EU パスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-104">EU Passport Number</span></span>

<span data-ttu-id="00943-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU Passport 番号機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="00943-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="00943-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="00943-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="00943-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="00943-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="00943-108">Format</span><span class="sxs-lookup"><span data-stu-id="00943-108">Format</span></span>

<span data-ttu-id="00943-109">1文字の後にオプションのスペースと7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-110">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-110">Pattern</span></span>

<span data-ttu-id="00943-111">1つの文字、7桁の数字、および1つのスペースの組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="00943-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="00943-112">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="00943-113">スペース1つ (オプション)</span><span class="sxs-lookup"><span data-stu-id="00943-113">One space (optional)</span></span>
    
- <span data-ttu-id="00943-114">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-115">Checksum</span></span>

<span data-ttu-id="00943-116">該当なし</span><span class="sxs-lookup"><span data-stu-id="00943-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-117">定義</span><span class="sxs-lookup"><span data-stu-id="00943-117">Definition</span></span>

<span data-ttu-id="00943-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-119">正規表現`Regex_austria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-120">from `Keywords_austria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-121">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-121">Keywords</span></span>

<span data-ttu-id="00943-122">| |</span><span class="sxs-lookup"><span data-stu-id="00943-122"></span></span>
|<span data-ttu-id="00943-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-124">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-124">passport number</span></span>  <br/> <span data-ttu-id="00943-125">オーストリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-125">austrian passport number</span></span>  <br/> <span data-ttu-id="00943-126">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-126">passport no</span></span>  <br/> <span data-ttu-id="00943-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="00943-127">reisepass</span></span>  <br/> <span data-ttu-id="00943-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="00943-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="00943-129">ベルギー</span><span class="sxs-lookup"><span data-stu-id="00943-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="00943-130">Format</span><span class="sxs-lookup"><span data-stu-id="00943-130">Format</span></span>

<span data-ttu-id="00943-131">2つの文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="00943-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-132">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-132">Pattern</span></span>

<span data-ttu-id="00943-133">2つの文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-134">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-134">Checksum</span></span>

<span data-ttu-id="00943-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="00943-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-136">定義</span><span class="sxs-lookup"><span data-stu-id="00943-136">Definition</span></span>

<span data-ttu-id="00943-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-138">正規表現`Regex_belgium_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-139">from `Keywords_belgium_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-140">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-140">Keywords</span></span>

<span data-ttu-id="00943-141">| |</span><span class="sxs-lookup"><span data-stu-id="00943-141"></span></span>
|<span data-ttu-id="00943-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-143">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-143">passport number</span></span>  <br/> <span data-ttu-id="00943-144">ベルギーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-144">belgian passport number</span></span>  <br/> <span data-ttu-id="00943-145">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-145">passport no</span></span>  <br/> <span data-ttu-id="00943-146">大き poort</span><span class="sxs-lookup"><span data-stu-id="00943-146">paspoort</span></span>  <br/> <span data-ttu-id="00943-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="00943-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="00943-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="00943-148">reisepass kein</span></span>  <br/> <span data-ttu-id="00943-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="00943-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="00943-150">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="00943-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="00943-151">Format</span><span class="sxs-lookup"><span data-stu-id="00943-151">Format</span></span>

<span data-ttu-id="00943-152">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-153">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-153">Pattern</span></span>

 <span data-ttu-id="00943-154">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="00943-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-155">Checksum</span></span>

<span data-ttu-id="00943-156">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-157">定義</span><span class="sxs-lookup"><span data-stu-id="00943-157">Definition</span></span>

<span data-ttu-id="00943-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-159">正規表現`Regex_bulgaria_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-160">from `Keywords_bulgaria_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-161">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-161">Keywords</span></span>

<span data-ttu-id="00943-162">| |</span><span class="sxs-lookup"><span data-stu-id="00943-162"></span></span>
|<span data-ttu-id="00943-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-164">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-164">passport number</span></span>  <br/> <span data-ttu-id="00943-165">ブルガリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="00943-166">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-166">passport no</span></span>  <br/> <span data-ttu-id="00943-167">номернапаспорта</span><span class="sxs-lookup"><span data-stu-id="00943-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="00943-168">クロアチア</span><span class="sxs-lookup"><span data-stu-id="00943-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="00943-169">Format</span><span class="sxs-lookup"><span data-stu-id="00943-169">Format</span></span>

<span data-ttu-id="00943-170">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-171">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-171">Pattern</span></span>

 <span data-ttu-id="00943-172">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="00943-173">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-173">Checksum</span></span>

<span data-ttu-id="00943-174">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-175">定義</span><span class="sxs-lookup"><span data-stu-id="00943-175">Definition</span></span>

<span data-ttu-id="00943-176">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-177">正規表現`Regex_croatia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-178">from `Keywords_croatia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-179">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-179">Keywords</span></span>

<span data-ttu-id="00943-180">| |</span><span class="sxs-lookup"><span data-stu-id="00943-180"></span></span>
|<span data-ttu-id="00943-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-182">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-182">passport number</span></span>  <br/> <span data-ttu-id="00943-183">クロアチア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-183">croatian passport number</span></span>  <br/> <span data-ttu-id="00943-184">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-184">passport no</span></span>  <br/> <span data-ttu-id="00943-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="00943-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="00943-186">キプロス</span><span class="sxs-lookup"><span data-stu-id="00943-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="00943-187">Format</span><span class="sxs-lookup"><span data-stu-id="00943-187">Format</span></span>

<span data-ttu-id="00943-188">1文字の後に、スペースまたは区切り記号を含まない6-8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-189">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-189">Pattern</span></span>

<span data-ttu-id="00943-190">1文字の後に6桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-191">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-191">Checksum</span></span>

<span data-ttu-id="00943-192">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-193">定義</span><span class="sxs-lookup"><span data-stu-id="00943-193">Definition</span></span>

<span data-ttu-id="00943-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-195">正規表現`Regex_cyprus_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-196">from `Keywords_cyprus_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-197">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-197">Keywords</span></span>

<span data-ttu-id="00943-198">| |</span><span class="sxs-lookup"><span data-stu-id="00943-198"></span></span>
|<span data-ttu-id="00943-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-200">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-200">passport number</span></span>  <br/> <span data-ttu-id="00943-201">キプロスパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="00943-202">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-202">passport no</span></span>  <br/> <span data-ttu-id="00943-203">αριθμόδιαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="00943-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="00943-204">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="00943-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="00943-205">Format</span><span class="sxs-lookup"><span data-stu-id="00943-205">Format</span></span>

<span data-ttu-id="00943-206">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-207">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-207">Pattern</span></span>

<span data-ttu-id="00943-208">スペースまたは区切り文字を含まない8桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-209">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-209">Checksum</span></span>

<span data-ttu-id="00943-210">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-211">定義</span><span class="sxs-lookup"><span data-stu-id="00943-211">Definition</span></span>

<span data-ttu-id="00943-212">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-213">正規表現`Regex_czech_republic_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-214">from `Keywords_czech_republic_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-215">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-215">Keywords</span></span>

<span data-ttu-id="00943-216">| |</span><span class="sxs-lookup"><span data-stu-id="00943-216"></span></span>
|<span data-ttu-id="00943-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-218">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-218">passport number</span></span>  <br/> <span data-ttu-id="00943-219">チェコのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-219">czech passport number</span></span>  <br/> <span data-ttu-id="00943-220">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-220">passport no</span></span>  <br/> <span data-ttu-id="00943-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="00943-221">cestovní pas</span></span>  <br/> <span data-ttu-id="00943-222">pas</span><span class="sxs-lookup"><span data-stu-id="00943-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="00943-223">デンマーク</span><span class="sxs-lookup"><span data-stu-id="00943-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="00943-224">Format</span><span class="sxs-lookup"><span data-stu-id="00943-224">Format</span></span>

<span data-ttu-id="00943-225">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-226">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-226">Pattern</span></span>

 <span data-ttu-id="00943-227">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="00943-228">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-228">Checksum</span></span>

<span data-ttu-id="00943-229">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-230">定義</span><span class="sxs-lookup"><span data-stu-id="00943-230">Definition</span></span>

<span data-ttu-id="00943-231">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-232">正規表現`Regex_denmark_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-233">from `Keywords_denmark_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-234">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-234">Keywords</span></span>

<span data-ttu-id="00943-235">| |</span><span class="sxs-lookup"><span data-stu-id="00943-235"></span></span>
|<span data-ttu-id="00943-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-237">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-237">passport number</span></span>  <br/> <span data-ttu-id="00943-238">デンマークのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-238">danish passport number</span></span>  <br/> <span data-ttu-id="00943-239">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-239">passport no</span></span>  <br/> <span data-ttu-id="00943-240">pas</span><span class="sxs-lookup"><span data-stu-id="00943-240">pas</span></span>  <br/> <span data-ttu-id="00943-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="00943-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="00943-242">エストニア</span><span class="sxs-lookup"><span data-stu-id="00943-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="00943-243">Format</span><span class="sxs-lookup"><span data-stu-id="00943-243">Format</span></span>

<span data-ttu-id="00943-244">1文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="00943-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-245">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-245">Pattern</span></span>

<span data-ttu-id="00943-246">1文字の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-247">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-247">Checksum</span></span>

<span data-ttu-id="00943-248">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-249">定義</span><span class="sxs-lookup"><span data-stu-id="00943-249">Definition</span></span>

<span data-ttu-id="00943-250">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-251">正規表現`Regex_estonia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-252">from `Keywords_estonia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-253">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-253">Keywords</span></span>

<span data-ttu-id="00943-254">| |</span><span class="sxs-lookup"><span data-stu-id="00943-254"></span></span>
|<span data-ttu-id="00943-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-256">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-256">passport number</span></span>  <br/> <span data-ttu-id="00943-257">エストニア語のパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-257">estonian passport number</span></span>  <br/> <span data-ttu-id="00943-258">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-258">passport no</span></span>  <br/> <span data-ttu-id="00943-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="00943-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="00943-260">フィンランド</span><span class="sxs-lookup"><span data-stu-id="00943-260">Finland</span></span>

<span data-ttu-id="00943-261">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フィンランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00943-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="00943-262">フランス</span><span class="sxs-lookup"><span data-stu-id="00943-262">France</span></span>

<span data-ttu-id="00943-263">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00943-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="00943-264">ドイツ</span><span class="sxs-lookup"><span data-stu-id="00943-264">Germany</span></span>

<span data-ttu-id="00943-265">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00943-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="00943-266">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="00943-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="00943-267">Format</span><span class="sxs-lookup"><span data-stu-id="00943-267">Format</span></span>

<span data-ttu-id="00943-268">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-269">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-269">Pattern</span></span>

<span data-ttu-id="00943-270">2 桁の文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-271">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-271">Checksum</span></span>

<span data-ttu-id="00943-272">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-273">定義</span><span class="sxs-lookup"><span data-stu-id="00943-273">Definition</span></span>

<span data-ttu-id="00943-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-275">正規表現`Regex_greece_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-276">from `Keywords_greece_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-277">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-277">Keywords</span></span>

<span data-ttu-id="00943-278">| |</span><span class="sxs-lookup"><span data-stu-id="00943-278"></span></span>
|<span data-ttu-id="00943-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-280">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-280">passport number</span></span>  <br/> <span data-ttu-id="00943-281">ギリシャのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-281">greek passport number</span></span>  <br/> <span data-ttu-id="00943-282">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-282">passport no</span></span>  <br/> <span data-ttu-id="00943-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="00943-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="00943-284">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="00943-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="00943-285">Format</span><span class="sxs-lookup"><span data-stu-id="00943-285">Format</span></span>

<span data-ttu-id="00943-286">2つの文字の後に、スペースや区切り文字を含まない6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-287">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-287">Pattern</span></span>

<span data-ttu-id="00943-288">2つの文字の後に6桁または7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-289">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-289">Checksum</span></span>

<span data-ttu-id="00943-290">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-291">定義</span><span class="sxs-lookup"><span data-stu-id="00943-291">Definition</span></span>

<span data-ttu-id="00943-292">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-293">正規表現`Regex_hungary_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-294">from `Keywords_hungary_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-295">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-295">Keywords</span></span>

<span data-ttu-id="00943-296">| |</span><span class="sxs-lookup"><span data-stu-id="00943-296"></span></span>
|<span data-ttu-id="00943-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-298">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-298">passport number</span></span>  <br/> <span data-ttu-id="00943-299">ハンガリーのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="00943-300">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-300">passport no</span></span>  <br/> <span data-ttu-id="00943-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="00943-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="00943-302">アイルランド</span><span class="sxs-lookup"><span data-stu-id="00943-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="00943-303">Format</span><span class="sxs-lookup"><span data-stu-id="00943-303">Format</span></span>

<span data-ttu-id="00943-304">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-305">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-305">Pattern</span></span>

<span data-ttu-id="00943-306">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="00943-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="00943-307">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="00943-308">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-309">Checksum</span></span>

<span data-ttu-id="00943-310">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-311">定義</span><span class="sxs-lookup"><span data-stu-id="00943-311">Definition</span></span>

<span data-ttu-id="00943-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-313">正規表現`Regex_ireland_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-314">from `Keywords_ireland_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-315">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-315">Keywords</span></span>

<span data-ttu-id="00943-316">| |</span><span class="sxs-lookup"><span data-stu-id="00943-316"></span></span>
|<span data-ttu-id="00943-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-318">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-318">passport number</span></span>  <br/> <span data-ttu-id="00943-319">アイルランドのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-319">irish passport number</span></span>  <br/> <span data-ttu-id="00943-320">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-320">passport no</span></span>  <br/> <span data-ttu-id="00943-321">pas</span><span class="sxs-lookup"><span data-stu-id="00943-321">pas</span></span>  <br/> <span data-ttu-id="00943-322">サインアウト</span><span class="sxs-lookup"><span data-stu-id="00943-322">passport</span></span>  <br/> <span data-ttu-id="00943-323">passeport</span><span class="sxs-lookup"><span data-stu-id="00943-323">passeport</span></span>  <br/> <span data-ttu-id="00943-324">passeport numero</span><span class="sxs-lookup"><span data-stu-id="00943-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="00943-325">イタリア</span><span class="sxs-lookup"><span data-stu-id="00943-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="00943-326">Format</span><span class="sxs-lookup"><span data-stu-id="00943-326">Format</span></span>

<span data-ttu-id="00943-327">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-328">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-328">Pattern</span></span>

<span data-ttu-id="00943-329">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="00943-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="00943-330">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="00943-331">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-332">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-332">Checksum</span></span>

<span data-ttu-id="00943-333">該当なし</span><span class="sxs-lookup"><span data-stu-id="00943-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-334">定義</span><span class="sxs-lookup"><span data-stu-id="00943-334">Definition</span></span>

<span data-ttu-id="00943-335">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-336">正規表現`Regex_italy_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-337">from `Keywords_italy_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-338">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-338">Keywords</span></span>

<span data-ttu-id="00943-339">| |</span><span class="sxs-lookup"><span data-stu-id="00943-339"></span></span>
|<span data-ttu-id="00943-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-341">イタリアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-341">italian passport number</span></span>  <br/> <span data-ttu-id="00943-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="00943-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="00943-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="00943-343">passaporto</span></span>  <br/> <span data-ttu-id="00943-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="00943-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="00943-345">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-345">passport number</span></span>  <br/> <span data-ttu-id="00943-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="00943-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="00943-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="00943-347">passaporto numero</span></span>  <br/> <span data-ttu-id="00943-348">numéro passeport italien</span><span class="sxs-lookup"><span data-stu-id="00943-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="00943-349">numéro passeport</span><span class="sxs-lookup"><span data-stu-id="00943-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="00943-350">ラトビア</span><span class="sxs-lookup"><span data-stu-id="00943-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="00943-351">Format</span><span class="sxs-lookup"><span data-stu-id="00943-351">Format</span></span>

<span data-ttu-id="00943-352">2つの文字または数字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-353">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-353">Pattern</span></span>

<span data-ttu-id="00943-354">2つの文字または数字の後に7桁の数字が続きます。</span><span class="sxs-lookup"><span data-stu-id="00943-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="00943-355">2 つの数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="00943-356">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-357">Checksum</span></span>

<span data-ttu-id="00943-358">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-359">定義</span><span class="sxs-lookup"><span data-stu-id="00943-359">Definition</span></span>

<span data-ttu-id="00943-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-361">正規表現`Regex_latvia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-362">from `Keywords_latvia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-363">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-363">Keywords</span></span>

<span data-ttu-id="00943-364">| |</span><span class="sxs-lookup"><span data-stu-id="00943-364"></span></span>
|<span data-ttu-id="00943-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-366">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-366">passport number</span></span>  <br/> <span data-ttu-id="00943-367">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-367">latvian passport number</span></span>  <br/> <span data-ttu-id="00943-368">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-368">passport no</span></span>  <br/> <span data-ttu-id="00943-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="00943-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="00943-370">リトアニア</span><span class="sxs-lookup"><span data-stu-id="00943-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="00943-371">Format</span><span class="sxs-lookup"><span data-stu-id="00943-371">Format</span></span>

<span data-ttu-id="00943-372">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="00943-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-373">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-373">Pattern</span></span>

<span data-ttu-id="00943-374">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-375">Checksum</span></span>

<span data-ttu-id="00943-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="00943-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-377">定義</span><span class="sxs-lookup"><span data-stu-id="00943-377">Definition</span></span>

<span data-ttu-id="00943-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-379">正規表現`Regex_lithuania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-380">from `Keywords_lithuania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-381">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-381">Keywords</span></span>

<span data-ttu-id="00943-382">| |</span><span class="sxs-lookup"><span data-stu-id="00943-382"></span></span>
|<span data-ttu-id="00943-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-384">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-384">passport number</span></span>  <br/> <span data-ttu-id="00943-385">lithunian パスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="00943-386">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-386">passport no</span></span>  <br/> <span data-ttu-id="00943-387">大き o numeris</span><span class="sxs-lookup"><span data-stu-id="00943-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="00943-388">ルクセンブルク</span><span class="sxs-lookup"><span data-stu-id="00943-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="00943-389">Format</span><span class="sxs-lookup"><span data-stu-id="00943-389">Format</span></span>

<span data-ttu-id="00943-390">8桁の数字または文字、スペースまたは区切り記号なし</span><span class="sxs-lookup"><span data-stu-id="00943-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-391">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-391">Pattern</span></span>

<span data-ttu-id="00943-392">8桁の数字または文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-393">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-393">Checksum</span></span>

<span data-ttu-id="00943-394">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-395">定義</span><span class="sxs-lookup"><span data-stu-id="00943-395">Definition</span></span>

<span data-ttu-id="00943-396">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-397">正規表現`Regex_nation_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-398">from `Keywords_nation_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-399">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-399">Keywords</span></span>

<span data-ttu-id="00943-400">| |</span><span class="sxs-lookup"><span data-stu-id="00943-400"></span></span>
|<span data-ttu-id="00943-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-402">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-402">passport number</span></span>  <br/> <span data-ttu-id="00943-403">ラトビアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-403">latvian passport number</span></span>  <br/> <span data-ttu-id="00943-404">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-404">passport no</span></span>  <br/> <span data-ttu-id="00943-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="00943-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="00943-406">マルタ</span><span class="sxs-lookup"><span data-stu-id="00943-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="00943-407">Format</span><span class="sxs-lookup"><span data-stu-id="00943-407">Format</span></span>

<span data-ttu-id="00943-408">スペースまたは区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-409">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-409">Pattern</span></span>

 <span data-ttu-id="00943-410">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="00943-411">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-411">Checksum</span></span>

<span data-ttu-id="00943-412">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-413">定義</span><span class="sxs-lookup"><span data-stu-id="00943-413">Definition</span></span>

<span data-ttu-id="00943-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-415">正規表現`Regex_malta_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-416">from `Keywords_malta_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-417">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-417">Keywords</span></span>

<span data-ttu-id="00943-418">| |</span><span class="sxs-lookup"><span data-stu-id="00943-418"></span></span>
|<span data-ttu-id="00943-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-420">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-420">passport number</span></span>  <br/> <span data-ttu-id="00943-421">マルタのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-421">maltese passport number</span></span>  <br/> <span data-ttu-id="00943-422">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-422">passport no</span></span>  <br/> <span data-ttu-id="00943-423">numru tal-passaport</span><span class="sxs-lookup"><span data-stu-id="00943-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="00943-424">オランダ</span><span class="sxs-lookup"><span data-stu-id="00943-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="00943-425">Format</span><span class="sxs-lookup"><span data-stu-id="00943-425">Format</span></span>

<span data-ttu-id="00943-426">9文字または数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="00943-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-427">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-427">Pattern</span></span>

<span data-ttu-id="00943-428">9桁の文字または数字</span><span class="sxs-lookup"><span data-stu-id="00943-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-429">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-429">Checksum</span></span>

<span data-ttu-id="00943-430">該当なし</span><span class="sxs-lookup"><span data-stu-id="00943-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-431">定義</span><span class="sxs-lookup"><span data-stu-id="00943-431">Definition</span></span>

<span data-ttu-id="00943-432">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-433">正規表現`Regex_netherlands_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-434">from `Keywords_netherlands_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-435">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-435">Keywords</span></span>

<span data-ttu-id="00943-436">| |</span><span class="sxs-lookup"><span data-stu-id="00943-436"></span></span>
|<span data-ttu-id="00943-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-438">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-438">dutch passport number</span></span>  <br/> <span data-ttu-id="00943-439">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-439">passport number</span></span>  <br/> <span data-ttu-id="00943-440">オランダのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="00943-441">nederlanden の nummer</span><span class="sxs-lookup"><span data-stu-id="00943-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="00943-442">大き poort</span><span class="sxs-lookup"><span data-stu-id="00943-442">paspoort</span></span>  <br/> <span data-ttu-id="00943-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="00943-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="00943-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="00943-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="00943-445">ポーランド</span><span class="sxs-lookup"><span data-stu-id="00943-445">Poland</span></span>

<span data-ttu-id="00943-446">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポーランドのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00943-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="00943-447">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="00943-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="00943-448">Format</span><span class="sxs-lookup"><span data-stu-id="00943-448">Format</span></span>

<span data-ttu-id="00943-449">1文字の後に6桁の数字 (スペースまたは区切り記号を付けない)</span><span class="sxs-lookup"><span data-stu-id="00943-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-450">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-450">Pattern</span></span>

<span data-ttu-id="00943-451">1文字の後に6桁の数字:</span><span class="sxs-lookup"><span data-stu-id="00943-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="00943-452">1 文字 (大文字小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="00943-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="00943-453">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-454">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-454">Checksum</span></span>

<span data-ttu-id="00943-455">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-456">定義</span><span class="sxs-lookup"><span data-stu-id="00943-456">Definition</span></span>

<span data-ttu-id="00943-457">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-458">正規表現`Regex_portugal_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-459">from `Keywords_portugal_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-460">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-460">Keywords</span></span>

<span data-ttu-id="00943-461">| |</span><span class="sxs-lookup"><span data-stu-id="00943-461"></span></span>
|<span data-ttu-id="00943-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-463">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-463">passport number</span></span>  <br/> <span data-ttu-id="00943-464">ポルトガルのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="00943-465">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-465">passport no</span></span>  <br/> <span data-ttu-id="00943-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="00943-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="00943-467">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="00943-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="00943-468">Format</span><span class="sxs-lookup"><span data-stu-id="00943-468">Format</span></span>

<span data-ttu-id="00943-469">スペースと区切り文字を除いた8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-470">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-470">Pattern</span></span>

<span data-ttu-id="00943-471">8桁または9桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-472">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-472">Checksum</span></span>

<span data-ttu-id="00943-473">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-474">定義</span><span class="sxs-lookup"><span data-stu-id="00943-474">Definition</span></span>

<span data-ttu-id="00943-475">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-476">正規表現`Regex_romania_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-477">from `Keywords_romania_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-478">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-478">Keywords</span></span>

<span data-ttu-id="00943-479">| |</span><span class="sxs-lookup"><span data-stu-id="00943-479"></span></span>
|<span data-ttu-id="00943-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-481">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-481">passport number</span></span>  <br/> <span data-ttu-id="00943-482">ルーマニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-482">romanian passport number</span></span>  <br/> <span data-ttu-id="00943-483">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-483">passport no</span></span>  <br/> <span data-ttu-id="00943-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="00943-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="00943-485">スロバキア</span><span class="sxs-lookup"><span data-stu-id="00943-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="00943-486">Format</span><span class="sxs-lookup"><span data-stu-id="00943-486">Format</span></span>

<span data-ttu-id="00943-487">1つの数字または文字の後に7桁の数字 (スペースまたは区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="00943-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-488">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-488">Pattern</span></span>

<span data-ttu-id="00943-489">1桁の数字または文字 (大文字小文字を区別しない) の後に7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="00943-490">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-490">Checksum</span></span>

<span data-ttu-id="00943-491">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-492">定義</span><span class="sxs-lookup"><span data-stu-id="00943-492">Definition</span></span>

<span data-ttu-id="00943-493">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-494">正規表現`Regex_slovakia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-495">from `Keywords_slovakia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-496">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-496">Keywords</span></span>

<span data-ttu-id="00943-497">| |</span><span class="sxs-lookup"><span data-stu-id="00943-497"></span></span>
|<span data-ttu-id="00943-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-499">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-499">passport number</span></span>  <br/> <span data-ttu-id="00943-500">スロバキアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="00943-501">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-501">passport no</span></span>  <br/> <span data-ttu-id="00943-502">číslo/</span><span class="sxs-lookup"><span data-stu-id="00943-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="00943-503">スロベニア</span><span class="sxs-lookup"><span data-stu-id="00943-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="00943-504">Format</span><span class="sxs-lookup"><span data-stu-id="00943-504">Format</span></span>

<span data-ttu-id="00943-505">2つの文字の後に、スペースや区切り文字を含まない7桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-506">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-506">Pattern</span></span>

<span data-ttu-id="00943-507">2つの文字の後に7桁の数字:</span><span class="sxs-lookup"><span data-stu-id="00943-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="00943-508">文字 "P"</span><span class="sxs-lookup"><span data-stu-id="00943-508">The letter "P"</span></span>
    
- <span data-ttu-id="00943-509">1文字の大文字</span><span class="sxs-lookup"><span data-stu-id="00943-509">One uppercase letter</span></span>
    
- <span data-ttu-id="00943-510">7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-511">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-511">Checksum</span></span>

<span data-ttu-id="00943-512">いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-513">定義</span><span class="sxs-lookup"><span data-stu-id="00943-513">Definition</span></span>

<span data-ttu-id="00943-514">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-515">正規表現`Regex_slovenia_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-516">from `Keywords_slovenia_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-517">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-517">Keywords</span></span>

<span data-ttu-id="00943-518">| |</span><span class="sxs-lookup"><span data-stu-id="00943-518"></span></span>
|<span data-ttu-id="00943-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-520">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-520">passport number</span></span>  <br/> <span data-ttu-id="00943-521">スロベニアのパスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="00943-522">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-522">passport no</span></span>  <br/> <span data-ttu-id="00943-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="00943-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="00943-524">スペイン</span><span class="sxs-lookup"><span data-stu-id="00943-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="00943-525">Format</span><span class="sxs-lookup"><span data-stu-id="00943-525">Format</span></span>

<span data-ttu-id="00943-526">スペースまたは区切り記号を含まない、文字と数字の8文字または9文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="00943-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="00943-527">パターン</span><span class="sxs-lookup"><span data-stu-id="00943-527">Pattern</span></span>

<span data-ttu-id="00943-528">文字と数字の8文字または9文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="00943-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="00943-529">2桁の数字または文字</span><span class="sxs-lookup"><span data-stu-id="00943-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="00943-530">1桁の数字または文字 (省略可能)</span><span class="sxs-lookup"><span data-stu-id="00943-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="00943-531">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="00943-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="00943-532">チェックサム</span><span class="sxs-lookup"><span data-stu-id="00943-532">Checksum</span></span>

<span data-ttu-id="00943-533">該当なし</span><span class="sxs-lookup"><span data-stu-id="00943-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="00943-534">定義</span><span class="sxs-lookup"><span data-stu-id="00943-534">Definition</span></span>

<span data-ttu-id="00943-535">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="00943-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="00943-536">正規表現`Regex_spain_eu_passport_number`は、パターンに一致するコンテンツを検出します。</span><span class="sxs-lookup"><span data-stu-id="00943-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="00943-537">from `Keywords_spain_eu_passport_number`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="00943-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="00943-538">キーワード</span><span class="sxs-lookup"><span data-stu-id="00943-538">Keywords</span></span>

<span data-ttu-id="00943-539">| |</span><span class="sxs-lookup"><span data-stu-id="00943-539"></span></span>
|<span data-ttu-id="00943-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="00943-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="00943-541">サインアウト</span><span class="sxs-lookup"><span data-stu-id="00943-541">passport</span></span>  <br/> <span data-ttu-id="00943-542">スペインのパスポート</span><span class="sxs-lookup"><span data-stu-id="00943-542">spain passport</span></span>  <br/> <span data-ttu-id="00943-543">パスポートブック</span><span class="sxs-lookup"><span data-stu-id="00943-543">passport book</span></span>  <br/> <span data-ttu-id="00943-544">passport number</span><span class="sxs-lookup"><span data-stu-id="00943-544">passport number</span></span>  <br/> <span data-ttu-id="00943-545">passport いいえ</span><span class="sxs-lookup"><span data-stu-id="00943-545">passport no</span></span>  <br/> <span data-ttu-id="00943-546">libreta pasaporte</span><span class="sxs-lookup"><span data-stu-id="00943-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="00943-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="00943-547">número pasaporte</span></span>  <br/> <span data-ttu-id="00943-548">españ a pasaporte</span><span class="sxs-lookup"><span data-stu-id="00943-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="00943-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="00943-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="00943-550">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="00943-550">Sweden</span></span>

<span data-ttu-id="00943-551">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「スウェーデンのパスポート番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="00943-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="00943-552">佐賀</span><span class="sxs-lookup"><span data-stu-id="00943-552">UK</span></span>

<span data-ttu-id="00943-553">詳細については、「米国/英国」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00943-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="00943-554">[機密情報の種類がどのように表示されるか](what-the-sensitive-information-types-look-for.md)について、パスポート番号</span><span class="sxs-lookup"><span data-stu-id="00943-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00943-555">関連項目</span><span class="sxs-lookup"><span data-stu-id="00943-555">See also</span></span>

[<span data-ttu-id="00943-556">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="00943-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

