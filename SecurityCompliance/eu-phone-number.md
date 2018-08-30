---
title: EU の電話番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1c90ca41-1681-46bf-8ad6-6bf4cec5c426
description: Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、EU の電話番号の機密性の高い情報の種類について説明します。
ms.openlocfilehash: 9dd878e3385312982f9f3a4927205e3ebb27aabb
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532222"
---
# <a name="eu-phone-number"></a><span data-ttu-id="edb50-104">EU の電話番号</span><span class="sxs-lookup"><span data-stu-id="edb50-104">EU Phone Number</span></span>

<span data-ttu-id="edb50-p102">Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、EU の電話番号の機密性の高い情報の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="edb50-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU Phone Number sensitive information type.</span></span> 
  
## <a name="austria"></a><span data-ttu-id="edb50-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="edb50-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="edb50-108">形式</span><span class="sxs-lookup"><span data-stu-id="edb50-108">Format</span></span>

<span data-ttu-id="edb50-109">標準の長さではありません。</span><span class="sxs-lookup"><span data-stu-id="edb50-109">No standard length</span></span>
  
### <a name="pattern"></a><span data-ttu-id="edb50-110">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-110">Pattern</span></span>

- <span data-ttu-id="edb50-111">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-111">Digits</span></span> 
    
- <span data-ttu-id="edb50-112">携帯電話番号だけが数字の「6」で始まる</span><span class="sxs-lookup"><span data-stu-id="edb50-112">Only mobile phone numbers begin with the digit "6"</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-113">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-113">Checksum</span></span>

<span data-ttu-id="edb50-114">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-114">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-115">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-115">Definition</span></span>

<span data-ttu-id="edb50-116">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-116">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-117">正規表現`Regex_austria_eu_telephone_number_1`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-117">The regular expression  `Regex_austria_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-118">キーワードの`Keywords_austria_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-118">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-119">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-119">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-120">正規表現`Regex_austria_eu_telephone_number_2`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-120">The regular expression  `Regex_austria_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-121">キーワードの`Keywords_austria_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-121">A keyword from  `Keywords_austria_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_1" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_telephone_number_2" />
          <Match idRef="Keywords_austria_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_austria_eu_formatted_telephone_number_2" />
          </Pattern>
</Entity>
```

## <a name="belgium"></a><span data-ttu-id="edb50-122">ベルギー</span><span class="sxs-lookup"><span data-stu-id="edb50-122">Belgium</span></span>

### <a name="definition"></a><span data-ttu-id="edb50-123">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-123">Definition</span></span>

<span data-ttu-id="edb50-124">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-125">正規表現`Regex_belgium_eu_telephone_number_1`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-125">The regular expression  `Regex_belgium_eu_telephone_number_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-126">キーワードの`Keywords_belgium_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-126">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-127">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-127">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-128">正規表現`Regex_belgium_eu_telephone_number_2`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-128">The regular expression  `Regex_belgium_eu_telephone_number_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-129">キーワードの`Keywords_belgium_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-129">A keyword from  `Keywords_belgium_eu_telephone_number` is found.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_1" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_telephone_number_2" />
          <Match idRef="Keywords_belgium_eu_telephone_number" />
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_1" />
          </Pattern>
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_belgium_eu_formatted_telephone_number_2" />
          </Pattern></Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="edb50-130">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="edb50-130">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-131">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-131">Pattern</span></span>

- <span data-ttu-id="edb50-132">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-132">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-133">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-133">Checksum</span></span>

<span data-ttu-id="edb50-134">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-134">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-135">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-135">Definition</span></span>

<span data-ttu-id="edb50-136">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-136">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-137">正規表現`Regex_bulgaria_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-137">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-138">キーワードの`Keywords_bulgaria_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-138">A keyword from  `Keywords_bulgaria_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-139">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-139">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-140">正規表現`Regex_bulgaria_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-140">The regular expression  `Regex_bulgaria_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_telephone_number" />
          <Match idRef="Keywords_bulgaria_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_bulgaria_eu_formatted_telephone_number" />
          </Pattern>
          
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="edb50-141">クロアチア</span><span class="sxs-lookup"><span data-stu-id="edb50-141">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-142">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-142">Pattern</span></span>

- <span data-ttu-id="edb50-143">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-143">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-144">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-144">Checksum</span></span>

<span data-ttu-id="edb50-145">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-145">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-146">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-146">Definition</span></span>

<span data-ttu-id="edb50-147">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-148">正規表現`Regex_croatia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-148">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-149">キーワードの`Keywords_croatia_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-149">A keyword from  `Keywords_croatia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-150">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-150">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-151">正規表現`Regex_croatia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-151">The regular expression  `Regex_croatia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_telephone_number" />
          <Match idRef="Keywords_croatia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_croatia_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="cyprus"></a><span data-ttu-id="edb50-152">キプロス</span><span class="sxs-lookup"><span data-stu-id="edb50-152">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-153">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-153">Pattern</span></span>

- <span data-ttu-id="edb50-154">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-154">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-155">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-155">Checksum</span></span>

<span data-ttu-id="edb50-156">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-156">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-157">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-157">Definition</span></span>

<span data-ttu-id="edb50-158">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-159">正規表現`Regex_cyprus_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-159">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-160">キーワードの`Keywords_cyprus_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-160">A keyword from  `Keywords_cyprus_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-161">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-161">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-162">正規表現`Regex_cyprus_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-162">The regular expression  `Regex_cyprus_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_telephone_number" />
          <Match idRef="Keywords_cyprus_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_cyprus_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="edb50-163">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="edb50-163">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-164">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-164">Pattern</span></span>

- <span data-ttu-id="edb50-165">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-165">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-166">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-166">Checksum</span></span>

<span data-ttu-id="edb50-167">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-167">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-168">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-168">Definition</span></span>

<span data-ttu-id="edb50-169">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-169">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-170">正規表現`Regex_czech_republic_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-170">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-171">キーワードの`Keywords_czech_republic_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-171">A keyword from  `Keywords_czech_republic_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-172">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-172">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-173">正規表現`Regex_czech_republic_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-173">The regular expression  `Regex_czech_republic_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_telephone_number" />
          <Match idRef="Keywords_czech_republic_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_czech_republic_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="denmark"></a><span data-ttu-id="edb50-174">デンマーク</span><span class="sxs-lookup"><span data-stu-id="edb50-174">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-175">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-175">Pattern</span></span>

- <span data-ttu-id="edb50-176">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-176">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-177">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-177">Checksum</span></span>

<span data-ttu-id="edb50-178">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-178">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-179">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-179">Definition</span></span>

<span data-ttu-id="edb50-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-180">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-181">正規表現`Regex_denmark_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-181">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-182">キーワードの`Keywords_denmark_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-182">A keyword from  `Keywords_denmark_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-184">正規表現`Regex_denmark_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-184">The regular expression  `Regex_denmark_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_telephone_number" />
          <Match idRef="Keywords_denmark_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_denmark_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="estonia"></a><span data-ttu-id="edb50-185">エストニア</span><span class="sxs-lookup"><span data-stu-id="edb50-185">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-186">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-186">Pattern</span></span>

- <span data-ttu-id="edb50-187">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-187">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-188">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-188">Checksum</span></span>

<span data-ttu-id="edb50-189">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-189">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-190">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-190">Definition</span></span>

<span data-ttu-id="edb50-191">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-191">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-192">正規表現`Regex_estonia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-192">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-193">キーワードの`Keywords_estonia_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-193">A keyword from  `Keywords_estonia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-194">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-195">正規表現`Regex_estonia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-195">The regular expression  `Regex_estonia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_telephone_number" />
          <Match idRef="Keywords_estonia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_estonia_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="finland"></a><span data-ttu-id="edb50-196">フィンランド</span><span class="sxs-lookup"><span data-stu-id="edb50-196">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-197">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-197">Pattern</span></span>

- <span data-ttu-id="edb50-198">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-198">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-199">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-199">Checksum</span></span>

<span data-ttu-id="edb50-200">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-200">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-201">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-201">Definition</span></span>

<span data-ttu-id="edb50-202">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-203">正規表現`Regex_finland_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-203">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-204">キーワードの`Keywords_finland_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-204">A keyword from  `Keywords_finland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-205">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-205">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-206">正規表現`Regex_finland_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-206">The regular expression  `Regex_finland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_telephone_number" />
          <Match idRef="Keywords_finland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_finland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="edb50-207">フランス</span><span class="sxs-lookup"><span data-stu-id="edb50-207">France</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-208">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-208">Pattern</span></span>

- <span data-ttu-id="edb50-209">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-209">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-210">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-210">Checksum</span></span>

<span data-ttu-id="edb50-211">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-211">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-212">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-212">Definition</span></span>

<span data-ttu-id="edb50-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-213">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-214">正規表現`Regex_france_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-214">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-215">キーワードの`Keywords_france_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-215">A keyword from  `Keywords_france_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-217">正規表現`Regex_france_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-217">The regular expression  `Regex_france_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_telephone_number" />
          <Match idRef="Keywords_france_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_france_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="germany"></a><span data-ttu-id="edb50-218">ドイツ</span><span class="sxs-lookup"><span data-stu-id="edb50-218">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-219">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-219">Pattern</span></span>

- <span data-ttu-id="edb50-220">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-220">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-221">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-221">Checksum</span></span>

<span data-ttu-id="edb50-222">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-222">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-223">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-223">Definition</span></span>

<span data-ttu-id="edb50-224">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-224">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-225">正規表現`Regex_germany_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-225">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-226">キーワードの`Keywords_germany_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-226">A keyword from  `Keywords_germany_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-227">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-227">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-228">正規表現`Regex_germany_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-228">The regular expression  `Regex_germany_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_telephone_number" />
          <Match idRef="Keywords_germany_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_germany_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="greece"></a><span data-ttu-id="edb50-229">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="edb50-229">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-230">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-230">Pattern</span></span>

- <span data-ttu-id="edb50-231">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-231">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-232">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-232">Checksum</span></span>

<span data-ttu-id="edb50-233">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-233">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-234">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-234">Definition</span></span>

<span data-ttu-id="edb50-235">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-235">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-236">正規表現`Regex_greece_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-236">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-237">キーワードの`Keywords_greece_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-237">A keyword from  `Keywords_greece_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-238">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-238">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-239">正規表現`Regex_greece_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-239">The regular expression  `Regex_greece_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_telephone_number" />
          <Match idRef="Keywords_greece_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_greece_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="hungary"></a><span data-ttu-id="edb50-240">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="edb50-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-241">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-241">Pattern</span></span>

- <span data-ttu-id="edb50-242">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-242">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-243">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-243">Checksum</span></span>

<span data-ttu-id="edb50-244">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-245">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-245">Definition</span></span>

<span data-ttu-id="edb50-246">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-247">正規表現`Regex_hungary_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-247">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-248">キーワードの`Keywords_hungary_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-248">A keyword from  `Keywords_hungary_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-250">正規表現`Regex_hungary_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-250">The regular expression  `Regex_hungary_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_telephone_number" />
          <Match idRef="Keywords_hungary_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_hungary_eu_formatted_telephone_number" />
          </Pattern>
       </Entity>
```

## <a name="ireland"></a><span data-ttu-id="edb50-251">Ireland</span><span class="sxs-lookup"><span data-stu-id="edb50-251">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-252">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-252">Pattern</span></span>

- <span data-ttu-id="edb50-253">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-253">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-254">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-254">Checksum</span></span>

<span data-ttu-id="edb50-255">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-255">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-256">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-256">Definition</span></span>

<span data-ttu-id="edb50-257">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-257">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-258">正規表現`Regex_ireland_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-258">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-259">キーワードの`Keywords_ireland_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-259">A keyword from  `Keywords_ireland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-260">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-260">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-261">正規表現`Regex_ireland_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-261">The regular expression  `Regex_ireland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_telephone_number" />
          <Match idRef="Keywords_ireland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_ireland_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="italy"></a><span data-ttu-id="edb50-262">イタリア</span><span class="sxs-lookup"><span data-stu-id="edb50-262">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-263">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-263">Pattern</span></span>

- <span data-ttu-id="edb50-264">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-264">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-265">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-265">Checksum</span></span>

<span data-ttu-id="edb50-266">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-266">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-267">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-267">Definition</span></span>

<span data-ttu-id="edb50-268">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-268">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-269">正規表現`Regex_italy_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-269">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-270">キーワードの`Keywords_italy_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-270">A keyword from  `Keywords_italy_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-271">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-272">正規表現`Regex_italy_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-272">The regular expression  `Regex_italy_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_telephone_number" />
          <Match idRef="Keywords_italy_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_italy_eu_formatted_telephone_number" />
          </Pattern>
         </Entity>
```

## <a name="latvia"></a><span data-ttu-id="edb50-273">ラトビア</span><span class="sxs-lookup"><span data-stu-id="edb50-273">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-274">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-274">Pattern</span></span>

- <span data-ttu-id="edb50-275">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-275">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-276">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-276">Checksum</span></span>

<span data-ttu-id="edb50-277">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-277">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-278">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-278">Definition</span></span>

<span data-ttu-id="edb50-279">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-279">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-280">正規表現`Regex_latvia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-280">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-281">キーワードの`Keywords_latvia_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-281">A keyword from  `Keywords_latvia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-282">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-283">正規表現`Regex_latvia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-283">The regular expression  `Regex_latvia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_telephone_number" />
          <Match idRef="Keywords_latvia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_latvia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="lithuania"></a><span data-ttu-id="edb50-284">リトアニア</span><span class="sxs-lookup"><span data-stu-id="edb50-284">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-285">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-285">Pattern</span></span>

- <span data-ttu-id="edb50-286">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-286">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-287">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-287">Checksum</span></span>

<span data-ttu-id="edb50-288">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-288">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-289">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-289">Definition</span></span>

<span data-ttu-id="edb50-290">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-291">正規表現`Regex_lithuania_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-291">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-292">キーワードの`Keywords_lithuania_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-292">A keyword from  `Keywords_lithuania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-293">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-293">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-294">正規表現`Regex_lithuania_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-294">The regular expression  `Regex_lithuania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_telephone_number" />
          <Match idRef="Keywords_lithuania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_lithuania_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="edb50-295">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="edb50-295">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-296">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-296">Pattern</span></span>

- <span data-ttu-id="edb50-297">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-297">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-298">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-298">Checksum</span></span>

<span data-ttu-id="edb50-299">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-299">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-300">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-300">Definition</span></span>

<span data-ttu-id="edb50-301">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-301">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-302">正規表現`Regex_luxemburg_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-302">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-303">キーワードの`Keywords_luxemburg_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-303">A keyword from  `Keywords_luxemburg_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-304">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-304">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-305">正規表現`Regex_luxemburg_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-305">The regular expression  `Regex_luxemburg_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_telephone_number" />
          <Match idRef="Keywords_luxemburg_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_luxemburg_eu_formatted_telephone_number" />
                  </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="edb50-306">マルタ</span><span class="sxs-lookup"><span data-stu-id="edb50-306">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-307">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-307">Pattern</span></span>

- <span data-ttu-id="edb50-308">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-308">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-309">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-309">Checksum</span></span>

<span data-ttu-id="edb50-310">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-310">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-311">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-311">Definition</span></span>

<span data-ttu-id="edb50-312">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-313">正規表現`Regex_malta_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-313">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-314">キーワードの`Keywords_malta_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-314">A keyword from  `Keywords_malta_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-315">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-315">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-316">正規表現`Regex_malta_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-316">The regular expression  `Regex_malta_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_telephone_number" />
          <Match idRef="Keywords_malta_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_malta_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="edb50-317">オランダ</span><span class="sxs-lookup"><span data-stu-id="edb50-317">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-318">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-318">Pattern</span></span>

- <span data-ttu-id="edb50-319">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-319">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-320">Checksum</span></span>

<span data-ttu-id="edb50-321">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-321">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-322">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-322">Definition</span></span>

<span data-ttu-id="edb50-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-323">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-324">正規表現`Regex_netherlands_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-324">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-325">キーワードの`Keywords_netherlands_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-325">A keyword from  `Keywords_netherlands_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-327">正規表現`Regex_netherlands_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-327">The regular expression  `Regex_netherlands_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_telephone_number" />
          <Match idRef="Keywords_netherlands_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_netherlands_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="edb50-328">ポーランド</span><span class="sxs-lookup"><span data-stu-id="edb50-328">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-329">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-329">Pattern</span></span>

- <span data-ttu-id="edb50-330">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-330">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-331">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-331">Checksum</span></span>

<span data-ttu-id="edb50-332">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-332">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-333">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-333">Definition</span></span>

<span data-ttu-id="edb50-334">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-334">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-335">正規表現`Regex_poland_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-335">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-336">キーワードの`Keywords_poland_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-336">A keyword from  `Keywords_poland_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-337">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-337">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-338">正規表現`Regex_poland_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-338">The regular expression  `Regex_poland_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_telephone_number" />
          <Match idRef="Keywords_poland_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_poland_eu_formatted_telephone_number" />
             </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="edb50-339">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="edb50-339">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-340">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-340">Pattern</span></span>

- <span data-ttu-id="edb50-341">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-341">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-342">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-342">Checksum</span></span>

<span data-ttu-id="edb50-343">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-344">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-344">Definition</span></span>

<span data-ttu-id="edb50-345">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-346">正規表現`Regex_portugal_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-346">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-347">キーワードの`Keywords_portugal_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-347">A keyword from  `Keywords_portugal_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-348">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-349">正規表現`Regex_portugal_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-349">The regular expression  `Regex_portugal_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_telephone_number" />
          <Match idRef="Keywords_portugal_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_portugal_eu_formatted_telephone_number" />
          </Pattern>
        </Entity>
```

## <a name="romania"></a><span data-ttu-id="edb50-350">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="edb50-350">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-351">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-351">Pattern</span></span>

- <span data-ttu-id="edb50-352">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-352">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-353">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-353">Checksum</span></span>

<span data-ttu-id="edb50-354">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-354">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-355">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-355">Definition</span></span>

<span data-ttu-id="edb50-356">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-356">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-357">正規表現`Regex_romania_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-357">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-358">キーワードの`Keywords_romania_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-358">A keyword from  `Keywords_romania_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-359">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-359">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-360">正規表現`Regex_romania_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-360">The regular expression  `Regex_romania_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_telephone_number" />
          <Match idRef="Keywords_romania_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_romania_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="edb50-361">スロバキア</span><span class="sxs-lookup"><span data-stu-id="edb50-361">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-362">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-362">Pattern</span></span>

- <span data-ttu-id="edb50-363">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-363">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-364">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-364">Checksum</span></span>

<span data-ttu-id="edb50-365">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-365">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-366">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-366">Definition</span></span>

<span data-ttu-id="edb50-367">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-367">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-368">正規表現`Regex_slovakia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-368">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-369">キーワードの`Keywords_slovakia_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-369">A keyword from  `Keywords_slovakia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-370">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-370">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-371">正規表現`Regex_slovakia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-371">The regular expression  `Regex_slovakia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_telephone_number" />
          <Match idRef="Keywords_slovakia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovakia_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="edb50-372">スロベニア</span><span class="sxs-lookup"><span data-stu-id="edb50-372">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-373">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-373">Pattern</span></span>

- <span data-ttu-id="edb50-374">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-374">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-375">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-375">Checksum</span></span>

<span data-ttu-id="edb50-376">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-377">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-377">Definition</span></span>

<span data-ttu-id="edb50-378">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-379">正規表現`Regex_slovenia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-379">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-380">キーワードの`Keywords_slovenia_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-380">A keyword from  `Keywords_slovenia_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-382">正規表現`Regex_slovenia_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-382">The regular expression  `Regex_slovenia_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_telephone_number" />
          <Match idRef="Keywords_slovenia_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_slovenia_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="spain"></a><span data-ttu-id="edb50-383">スペイン</span><span class="sxs-lookup"><span data-stu-id="edb50-383">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-384">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-384">Pattern</span></span>

- <span data-ttu-id="edb50-385">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-385">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-386">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-386">Checksum</span></span>

<span data-ttu-id="edb50-387">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-387">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-388">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-388">Definition</span></span>

<span data-ttu-id="edb50-389">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-389">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-390">正規表現`Regex_spain_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-390">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-391">キーワードの`Keywords_spain_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-391">A keyword from  `Keywords_spain_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-392">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-392">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-393">正規表現`Regex_spain_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-393">The regular expression  `Regex_spain_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_telephone_number" />
          <Match idRef="Keywords_spain_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_spain_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="sweden"></a><span data-ttu-id="edb50-394">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="edb50-394">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-395">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-395">Pattern</span></span>

- <span data-ttu-id="edb50-396">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-396">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-397">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-397">Checksum</span></span>

<span data-ttu-id="edb50-398">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-398">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-399">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-399">Definition</span></span>

<span data-ttu-id="edb50-400">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-400">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-401">正規表現`Regex_sweden_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-401">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-402">キーワードの`Keywords_sweden_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-402">A keyword from  `Keywords_sweden_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-403">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-403">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-404">正規表現`Regex_sweden_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-404">The regular expression  `Regex_sweden_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_telephone_number" />
          <Match idRef="Keywords_sweden_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_sweden_eu_formatted_telephone_number" />
          </Pattern>
          </Entity>
```

## <a name="uk"></a><span data-ttu-id="edb50-405">英国</span><span class="sxs-lookup"><span data-stu-id="edb50-405">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="edb50-406">パターン</span><span class="sxs-lookup"><span data-stu-id="edb50-406">Pattern</span></span>

- <span data-ttu-id="edb50-407">桁</span><span class="sxs-lookup"><span data-stu-id="edb50-407">Digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="edb50-408">チェックサム</span><span class="sxs-lookup"><span data-stu-id="edb50-408">Checksum</span></span>

<span data-ttu-id="edb50-409">該当なし</span><span class="sxs-lookup"><span data-stu-id="edb50-409">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="edb50-410">定義</span><span class="sxs-lookup"><span data-stu-id="edb50-410">Definition</span></span>

<span data-ttu-id="edb50-411">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-412">正規表現`Regex_uk_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-412">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="edb50-413">キーワードの`Keywords_uk_eu_telephone_number`があります。</span><span class="sxs-lookup"><span data-stu-id="edb50-413">A keyword from  `Keywords_uk_eu_telephone_number` is found.</span></span> 
    
<span data-ttu-id="edb50-414">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="edb50-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="edb50-415">正規表現`Regex_uk_eu_telephone_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="edb50-415">The regular expression  `Regex_uk_eu_telephone_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Telephone Number -->
<Entity id="eb367e90-d826-40aa-a338-a1fdb3a4d99b" patternsProximity="300" recommendedConfidence="75">
<!-- Loosely formatted patterns with mandatory corroborative evidence -->
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_telephone_number" />
          <Match idRef="Keywords_uk_eu_telephone_number" />
        </Pattern>
<!-- Strictly formatted patterns without mandatory corroborative evidence -->
          <Pattern confidenceLevel="75">
            <IdMatch idRef="Regex_uk_eu_formatted_telephone_number" />
            </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="edb50-416">関連項目</span><span class="sxs-lookup"><span data-stu-id="edb50-416">See also</span></span>

[<span data-ttu-id="edb50-417">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="edb50-417">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

