---
title: EU の携帯電話番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 555e7675-2ae8-42d1-9b8e-2c8f8cd21337
description: Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、EU の携帯電話番号の機密性の高い情報の種類について説明します。
ms.openlocfilehash: d0818759dae8ed86cc9aef6f7fad48cbd2acf24f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532054"
---
# <a name="eu-mobile-phone-number"></a><span data-ttu-id="28f93-104">EU の携帯電話番号</span><span class="sxs-lookup"><span data-stu-id="28f93-104">EU Mobile Phone Number</span></span>

<span data-ttu-id="28f93-p102">Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、EU の携帯電話番号の機密性の高い情報の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="28f93-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Mobile Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="28f93-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="28f93-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="28f93-108">形式</span><span class="sxs-lookup"><span data-stu-id="28f93-108">Format</span></span>

<span data-ttu-id="28f93-109">標準的な長さのない数字</span><span class="sxs-lookup"><span data-stu-id="28f93-109">Digits without standard lengths</span></span>
  
### <a name="pattern"></a><span data-ttu-id="28f93-110">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-110">Pattern</span></span>

-  <span data-ttu-id="28f93-111">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-111">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="28f93-112">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-112">Definition</span></span>

<span data-ttu-id="28f93-113">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-113">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-114">正規表現`Regex_austria_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-114">The regular expression  `Regex_austria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-115">正規表現`Regex_austria_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-115">The regular expression  `Regex_austria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-116">キーワードの`Keywords_austria_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-116">A keyword from  `Keywords_austria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_mobile_number"/>
          <Match idRef="Keywords_austria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_austria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="28f93-117">ベルギー</span><span class="sxs-lookup"><span data-stu-id="28f93-117">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-118">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-118">Pattern</span></span>

-  <span data-ttu-id="28f93-119">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-119">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="28f93-120">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-120">Definition</span></span>

<span data-ttu-id="28f93-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-122">正規表現`Regex_belgium_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-122">The regular expression  `Regex_belgium_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-123">正規表現`Regex_belgium_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-123">The regular expression  `Regex_belgium_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-124">キーワードの`Keywords_belgium_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-124">A keyword from  `Keywords_belgium_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_mobile_number"/>
          <Match idRef="Keywords_belgium_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_belgium_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="28f93-125">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="28f93-125">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-126">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-126">Pattern</span></span>

-  <span data-ttu-id="28f93-127">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-127">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="28f93-128">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-128">Definition</span></span>

<span data-ttu-id="28f93-129">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-129">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-130">正規表現`Regex_bulgaria_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-130">The regular expression  `Regex_bulgaria_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-131">正規表現`Regex_bulgaria_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-131">The regular expression  `Regex_bulgaria_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-132">キーワードの`Keywords_bulgaria_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-132">A keyword from  `Keywords_bulgaria_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_mobile_number"/>
          <Match idRef="Keywords_bulgaria_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_bulgaria_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="28f93-133">クロアチア</span><span class="sxs-lookup"><span data-stu-id="28f93-133">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-134">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-134">Pattern</span></span>

-  <span data-ttu-id="28f93-135">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-135">Digits</span></span> 
    
### <a name="definition"></a><span data-ttu-id="28f93-136">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-136">Definition</span></span>

<span data-ttu-id="28f93-137">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-138">正規表現`Regex_croatia_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-138">The regular expression  `Regex_croatia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-139">正規表現`Regex_croatia_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-139">The regular expression  `Regex_croatia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-140">キーワードの`Keywords_croatia_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-140">A keyword from  `Keywords_croatia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_mobile_number"/>
          <Match idRef="Keywords_croatia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_croatia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="28f93-141">キプロス</span><span class="sxs-lookup"><span data-stu-id="28f93-141">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-142">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-142">Pattern</span></span>

-  <span data-ttu-id="28f93-143">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-144">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-144">Checksum</span></span>

<span data-ttu-id="28f93-145">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-146">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-146">Definition</span></span>

<span data-ttu-id="28f93-147">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-148">正規表現`Regex_cyprus_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-148">The regular expression  `Regex_cyprus_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-149">正規表現`Regex_cyprus_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-149">The regular expression  `Regex_cyprus_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-150">キーワードの`Keywords_cyprus_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-150">A keyword from  `Keywords_cyprus_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_mobile_number"/>
          <Match idRef="Keywords_cyprus_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_cyprus_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="28f93-151">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="28f93-151">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-152">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-152">Pattern</span></span>

-  <span data-ttu-id="28f93-153">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-153">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-154">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-154">Checksum</span></span>

<span data-ttu-id="28f93-155">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-155">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-156">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-156">Definition</span></span>

<span data-ttu-id="28f93-157">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-157">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-158">正規表現`Regex_czech_republic_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-158">The regular expression  `Regex_czech_republic_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-159">正規表現`Regex_czech_republic_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-159">The regular expression  `Regex_czech_republic_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-160">キーワードの`Keywords_czech_republic_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-160">A keyword from  `Keywords_czech_republic_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_mobile_number"/>
          <Match idRef="Keywords_czech_republic_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_czech_republic_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="28f93-161">デンマーク</span><span class="sxs-lookup"><span data-stu-id="28f93-161">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-162">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-162">Pattern</span></span>

-  <span data-ttu-id="28f93-163">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-163">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-164">Checksum</span></span>

<span data-ttu-id="28f93-165">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-165">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-166">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-166">Definition</span></span>

<span data-ttu-id="28f93-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-167">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-168">正規表現`Regex_denmark_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-168">The regular expression  `Regex_denmark_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-169">正規表現`Regex_denmark_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-169">The regular expression  `Regex_denmark_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-170">キーワードの`Keywords_denmark_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-170">A keyword from  `Keywords_denmark_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_mobile_number"/>
          <Match idRef="Keywords_denmark_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_denmark_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="28f93-171">エストニア</span><span class="sxs-lookup"><span data-stu-id="28f93-171">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-172">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-172">Pattern</span></span>

-  <span data-ttu-id="28f93-173">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-173">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-174">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-174">Checksum</span></span>

<span data-ttu-id="28f93-175">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-175">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-176">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-176">Definition</span></span>

<span data-ttu-id="28f93-177">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-177">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-178">正規表現`Regex_estonia_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-178">The regular expression  `Regex_estonia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-179">正規表現`Regex_estonia_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-179">The regular expression  `Regex_estonia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-180">キーワードの`Keywords_estonia_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-180">A keyword from  `Keywords_estonia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_mobile_number"/>
          <Match idRef="Keywords_estonia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_estonia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="28f93-181">フィンランド</span><span class="sxs-lookup"><span data-stu-id="28f93-181">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-182">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-182">Pattern</span></span>

-  <span data-ttu-id="28f93-183">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-183">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-184">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-184">Checksum</span></span>

<span data-ttu-id="28f93-185">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-185">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-186">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-186">Definition</span></span>

<span data-ttu-id="28f93-187">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-187">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-188">正規表現`Regex_finland_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-188">The regular expression  `Regex_finland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-189">正規表現`Regex_finland_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-189">The regular expression  `Regex_finland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-190">キーワードの`Keywords_finland_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-190">A keyword from  `Keywords_finland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_mobile_number"/>
          <Match idRef="Keywords_finland_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_finland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="28f93-191">フランス</span><span class="sxs-lookup"><span data-stu-id="28f93-191">France</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-192">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-192">Pattern</span></span>

-  <span data-ttu-id="28f93-193">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-193">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-194">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-194">Checksum</span></span>

<span data-ttu-id="28f93-195">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-195">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-196">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-196">Definition</span></span>

<span data-ttu-id="28f93-197">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-198">正規表現`Regex_france_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-198">The regular expression  `Regex_france_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-199">正規表現`Regex_france_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-199">The regular expression  `Regex_france_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-200">キーワードの`Keywords_france_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-200">A keyword from  `Keywords_france_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_mobile_number"/>
          <Match idRef="Keywords_france_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_france_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="28f93-201">ドイツ</span><span class="sxs-lookup"><span data-stu-id="28f93-201">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-202">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-202">Pattern</span></span>

-  <span data-ttu-id="28f93-203">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-203">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-204">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-204">Checksum</span></span>

<span data-ttu-id="28f93-205">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-205">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-206">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-206">Definition</span></span>

<span data-ttu-id="28f93-207">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-207">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-208">正規表現`Regex_germany_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-208">The regular expression  `Regex_germany_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-209">正規表現`Regex_germany_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-209">The regular expression  `Regex_germany_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-210">キーワードの`Keywords_germany_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-210">A keyword from  `Keywords_germany_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_mobile_number"/>
          <Match idRef="Keywords_germany_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_germany_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="28f93-211">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="28f93-211">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-212">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-212">Pattern</span></span>

-  <span data-ttu-id="28f93-213">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-213">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-214">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-214">Checksum</span></span>

<span data-ttu-id="28f93-215">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-215">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-216">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-216">Definition</span></span>

<span data-ttu-id="28f93-217">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-217">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-218">正規表現`Regex_greece_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-218">The regular expression  `Regex_greece_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-219">正規表現`Regex_greece_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-219">The regular expression  `Regex_greece_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-220">キーワードの`Keywords_greece_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-220">A keyword from  `Keywords_greece_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_mobile_number"/>
          <Match idRef="Keywords_greece_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_greece_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="28f93-221">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="28f93-221">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-222">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-222">Pattern</span></span>

-  <span data-ttu-id="28f93-223">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-223">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-224">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-224">Checksum</span></span>

<span data-ttu-id="28f93-225">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-225">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-226">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-226">Definition</span></span>

<span data-ttu-id="28f93-227">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-228">正規表現`Regex_hungary_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-228">The regular expression  `Regex_hungary_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-229">正規表現`Regex_hungary_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-229">The regular expression  `Regex_hungary_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-230">キーワードの`Keywords_hungary_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-230">A keyword from  `Keywords_hungary_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_mobile_number"/>
          <Match idRef="Keywords_hungary_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_hungary_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="28f93-231">Ireland</span><span class="sxs-lookup"><span data-stu-id="28f93-231">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-232">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-232">Pattern</span></span>

-  <span data-ttu-id="28f93-233">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-233">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-234">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-234">Checksum</span></span>

<span data-ttu-id="28f93-235">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-236">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-236">Definition</span></span>

<span data-ttu-id="28f93-237">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-238">正規表現`Regex_ireland_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-238">The regular expression  `Regex_ireland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-239">正規表現`Regex_ireland_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-239">The regular expression  `Regex_ireland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-240">キーワードの`Keywords_ireland_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-240">A keyword from  `Keywords_ireland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_mobile_number"/>
          <Match idRef="Keywords_ireland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_ireland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="28f93-241">イタリア</span><span class="sxs-lookup"><span data-stu-id="28f93-241">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-242">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-242">Pattern</span></span>

-  <span data-ttu-id="28f93-243">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-243">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-244">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-244">Checksum</span></span>

<span data-ttu-id="28f93-245">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-245">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-246">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-246">Definition</span></span>

<span data-ttu-id="28f93-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-248">正規表現`Regex_italy_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-248">The regular expression  `Regex_italy_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-249">正規表現`Regex_italy_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-249">The regular expression  `Regex_italy_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-250">キーワードの`Keywords_italy_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-250">A keyword from  `Keywords_italy_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_mobile_number"/>
          <Match idRef="Keywords_italy_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_italy_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="28f93-251">ラトビア</span><span class="sxs-lookup"><span data-stu-id="28f93-251">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-252">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-252">Pattern</span></span>

-  <span data-ttu-id="28f93-253">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-254">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-254">Checksum</span></span>

<span data-ttu-id="28f93-255">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-256">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-256">Definition</span></span>

<span data-ttu-id="28f93-257">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-258">正規表現`Regex_latvia_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-258">The regular expression  `Regex_latvia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-259">正規表現`Regex_latvia_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-259">The regular expression  `Regex_latvia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-260">キーワードの`Keywords_latvia_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-260">A keyword from  `Keywords_latvia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_mobile_number"/>
          <Match idRef="Keywords_latvia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_latvia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="28f93-261">リトアニア</span><span class="sxs-lookup"><span data-stu-id="28f93-261">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-262">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-262">Pattern</span></span>

-  <span data-ttu-id="28f93-263">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-263">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-264">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-264">Checksum</span></span>

<span data-ttu-id="28f93-265">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-265">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-266">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-266">Definition</span></span>

<span data-ttu-id="28f93-267">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-267">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-268">正規表現`Regex_lithuania_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-268">The regular expression  `Regex_lithuania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-269">正規表現`Regex_lithuania_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-269">The regular expression  `Regex_lithuania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-270">キーワードの`Keywords_lithuania_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-270">A keyword from  `Keywords_lithuania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_mobile_number"/>
          <Match idRef="Keywords_lithuania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_lithuania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="28f93-271">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="28f93-271">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-272">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-272">Pattern</span></span>

-  <span data-ttu-id="28f93-273">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-273">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-274">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-274">Checksum</span></span>

<span data-ttu-id="28f93-275">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-275">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-276">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-276">Definition</span></span>

<span data-ttu-id="28f93-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-277">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-278">正規表現`Regex_luxumburg_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-278">The regular expression  `Regex_luxumburg_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-279">正規表現`Regex_luxumburg_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-279">The regular expression  `Regex_luxumburg_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-280">キーワードの`Keywords_luxumburg_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-280">A keyword from  `Keywords_luxumburg_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxumburg_eu_mobile_number"/>
          <Match idRef="Keywords_luxumburg_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_luxumburg_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="28f93-281">マルタ</span><span class="sxs-lookup"><span data-stu-id="28f93-281">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-282">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-282">Pattern</span></span>

-  <span data-ttu-id="28f93-283">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-283">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-284">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-284">Checksum</span></span>

<span data-ttu-id="28f93-285">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-285">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-286">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-286">Definition</span></span>

<span data-ttu-id="28f93-287">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-287">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-288">正規表現`Regex_malta_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-288">The regular expression  `Regex_malta_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-289">正規表現`Regex_malta_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-289">The regular expression  `Regex_malta_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-290">キーワードの`Keywords_malta_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-290">A keyword from  `Keywords_malta_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_mobile_number"/>
          <Match idRef="Keywords_malta_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_malta_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="28f93-291">オランダ</span><span class="sxs-lookup"><span data-stu-id="28f93-291">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-292">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-292">Pattern</span></span>

-  <span data-ttu-id="28f93-293">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-293">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-294">Checksum</span></span>

<span data-ttu-id="28f93-295">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-295">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-296">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-296">Definition</span></span>

<span data-ttu-id="28f93-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-297">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-298">正規表現`Regex_netherlands_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-298">The regular expression  `Regex_netherlands_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-299">正規表現`Regex_netherlands_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-299">The regular expression  `Regex_netherlands_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-300">キーワードの`Keywords_netherlands_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-300">A keyword from  `Keywords_netherlands_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_mobile_number"/>
          <Match idRef="Keywords_netherlands_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_netherlands_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="28f93-301">ポーランド</span><span class="sxs-lookup"><span data-stu-id="28f93-301">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-302">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-302">Pattern</span></span>

-  <span data-ttu-id="28f93-303">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-303">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-304">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-304">Checksum</span></span>

<span data-ttu-id="28f93-305">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-305">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-306">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-306">Definition</span></span>

<span data-ttu-id="28f93-307">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-307">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-308">正規表現`Regex_poland_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-308">The regular expression  `Regex_poland_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-309">正規表現`Regex_poland_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-309">The regular expression  `Regex_poland_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-310">キーワードの`Keywords_poland_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-310">A keyword from  `Keywords_poland_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_mobile_number"/>
          <Match idRef="Keywords_poland_eu_mobile_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_poland_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="28f93-311">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="28f93-311">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-312">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-312">Pattern</span></span>

-  <span data-ttu-id="28f93-313">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-313">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-314">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-314">Checksum</span></span>

<span data-ttu-id="28f93-315">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-315">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-316">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-316">Definition</span></span>

<span data-ttu-id="28f93-317">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-317">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-318">正規表現`Regex_portugal_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-318">The regular expression  `Regex_portugal_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-319">正規表現`Regex_portugal_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-319">The regular expression  `Regex_portugal_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-320">キーワードの`Keywords_portugal_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-320">A keyword from  `Keywords_portugal_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_mobile_number"/>
          <Match idRef="Keywords_portugal_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_portugal_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="28f93-321">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="28f93-321">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-322">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-322">Pattern</span></span>

-  <span data-ttu-id="28f93-323">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-323">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-324">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-324">Checksum</span></span>

<span data-ttu-id="28f93-325">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-326">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-326">Definition</span></span>

<span data-ttu-id="28f93-327">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-328">正規表現`Regex_romania_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-328">The regular expression  `Regex_romania_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-329">正規表現`Regex_romania_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-329">The regular expression  `Regex_romania_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-330">キーワードの`Keywords_romania_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-330">A keyword from  `Keywords_romania_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_mobile_number"/>
          <Match idRef="Keywords_romania_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_romania_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="28f93-331">スロバキア</span><span class="sxs-lookup"><span data-stu-id="28f93-331">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-332">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-332">Pattern</span></span>

-  <span data-ttu-id="28f93-333">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-333">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-334">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-334">Checksum</span></span>

<span data-ttu-id="28f93-335">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-335">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-336">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-336">Definition</span></span>

<span data-ttu-id="28f93-337">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-338">正規表現`Regex_slovakia_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-338">The regular expression  `Regex_slovakia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-339">正規表現`Regex_slovakia_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-339">The regular expression  `Regex_slovakia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-340">キーワードの`Keywords_slovakia_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-340">A keyword from  `Keywords_slovakia_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_mobile_number"/>
          <Match idRef="Keywords_slovakia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovakia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="28f93-341">スロベニア</span><span class="sxs-lookup"><span data-stu-id="28f93-341">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-342">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-342">Pattern</span></span>

-  <span data-ttu-id="28f93-343">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-343">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-344">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-344">Checksum</span></span>

<span data-ttu-id="28f93-345">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-345">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-346">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-346">Definition</span></span>

<span data-ttu-id="28f93-347">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-347">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-348">正規表現`Regex_slovenia_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-348">The regular expression  `Regex_slovenia_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-349">正規表現`Regex_slovenia_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-349">The regular expression  `Regex_slovenia_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-350">キーワードの`Keywords_slovenia_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-350">A keyword from  `Keywords_slovenia_eu_mobile_number` is found.</span></span> 
    
```
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_mobile_number"/>
          <Match idRef="Keywords_slovenia_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_slovenia_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="28f93-351">スペイン</span><span class="sxs-lookup"><span data-stu-id="28f93-351">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-352">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-352">Pattern</span></span>

-  <span data-ttu-id="28f93-353">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-353">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-354">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-354">Checksum</span></span>

<span data-ttu-id="28f93-355">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-355">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-356">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-356">Definition</span></span>

<span data-ttu-id="28f93-357">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-357">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-358">正規表現`Regex_spain_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-358">The regular expression  `Regex_spain_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-359">正規表現`Regex_spain_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-359">The regular expression  `Regex_spain_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-360">キーワードの`Keywords_spain_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-360">A keyword from  `Keywords_spain_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_mobile_number"/>
          <Match idRef="Keywords_spain_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_spain_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="28f93-361">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="28f93-361">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-362">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-362">Pattern</span></span>

-  <span data-ttu-id="28f93-363">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-364">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-364">Checksum</span></span>

<span data-ttu-id="28f93-365">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-366">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-366">Definition</span></span>

<span data-ttu-id="28f93-367">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-368">正規表現`Regex_sweden_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-368">The regular expression  `Regex_sweden_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-369">正規表現`Regex_sweden_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-369">The regular expression  `Regex_sweden_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-370">キーワードの`Keywords_sweden_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-370">A keyword from  `Keywords_sweden_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_mobile_number"/>
          <Match idRef="Keywords_sweden_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_sweden_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="28f93-371">英国</span><span class="sxs-lookup"><span data-stu-id="28f93-371">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="28f93-372">パターン</span><span class="sxs-lookup"><span data-stu-id="28f93-372">Pattern</span></span>

-  <span data-ttu-id="28f93-373">桁</span><span class="sxs-lookup"><span data-stu-id="28f93-373">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="28f93-374">チェックサム</span><span class="sxs-lookup"><span data-stu-id="28f93-374">Checksum</span></span>

<span data-ttu-id="28f93-375">該当なし</span><span class="sxs-lookup"><span data-stu-id="28f93-375">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="28f93-376">定義</span><span class="sxs-lookup"><span data-stu-id="28f93-376">Definition</span></span>

<span data-ttu-id="28f93-377">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="28f93-377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="28f93-378">正規表現`Regex_uk_eu_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-378">The regular expression  `Regex_uk_eu_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-379">正規表現`Regex_uk_eu_formatted_mobile_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="28f93-379">The regular expression  `Regex_uk_eu_formatted_mobile_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="28f93-380">キーワードの`Keywords_uk_eu_mobile_number`があります。</span><span class="sxs-lookup"><span data-stu-id="28f93-380">A keyword from  `Keywords_uk_eu_mobile_number` is found.</span></span> 
    
```
 
<Entity id="a56a0418-136a-41ea-a337-4d0388b28e69" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_mobile_number"/>
          <Match idRef="Keywords_uk_eu_mobile_number" />
        </Pattern>
<Pattern confidenceLevel="75">
<IdMatch idRef="Regex_uk_eu_formatted_mobile_number" />
          </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="28f93-381">関連項目</span><span class="sxs-lookup"><span data-stu-id="28f93-381">See also</span></span>

[<span data-ttu-id="28f93-382">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="28f93-382">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

