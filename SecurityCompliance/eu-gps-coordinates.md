---
title: EU の GPS 座標
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/14/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: fdf2aebc-d5a4-4138-b10f-4a81dd70415a
description: Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、GPS 座標を EU の機密情報の種類について説明します。
ms.openlocfilehash: 89fb8420e479b9f793fc2be9aa3a9a9fd5741691
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532067"
---
# <a name="eu-gps-coordinates"></a><span data-ttu-id="e8882-104">EU の GPS 座標</span><span class="sxs-lookup"><span data-stu-id="e8882-104">EU GPS Coordinates</span></span>

<span data-ttu-id="e8882-p102">Office 365 のセキュリティでは、データ損失防止 (DLP)&amp;コンプライアンス センターには、DLP ポリシーに使用する準備ができている多くの機密性の高い情報の種類が含まれています。このトピックでは、GPS 座標を EU の機密情報の種類について説明します。</span><span class="sxs-lookup"><span data-stu-id="e8882-p102">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies. This topic describes the EU GPS Coordinates sensitive information type.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e8882-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="e8882-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e8882-108">形式</span><span class="sxs-lookup"><span data-stu-id="e8882-108">Format</span></span>

<span data-ttu-id="e8882-109">座標の範囲では、オーストリアの都市の: 緯度 46.526 から 48.816 と 16.945 に、9.6 からの経度です。</span><span class="sxs-lookup"><span data-stu-id="e8882-109">Coordinates for cities in Austria are in range: Latitude from 46.526 to 48.816 and longitude from 9.6 to 16.945.</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8882-110">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-110">Pattern</span></span>

<span data-ttu-id="e8882-111">各座標、最大 6 桁の数字と小数点の位置の組み合わせです。</span><span class="sxs-lookup"><span data-stu-id="e8882-111">For each coordinate, combination of up to 6 digits and a decimal point.</span></span>
  
- <span data-ttu-id="e8882-112">最大 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="e8882-112">Up to 6 digits</span></span>
    
- <span data-ttu-id="e8882-113">最初または 2 番目の数字の後の 10 進ポイントです。</span><span class="sxs-lookup"><span data-stu-id="e8882-113">A decimal point after first or second digit.</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8882-114">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-114">Checksum</span></span>

<span data-ttu-id="e8882-115">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-115">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-116">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-116">Definition</span></span>

<span data-ttu-id="e8882-117">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-117">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-118">正規表現`Regex_austria_eu_gps_data_1`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-118">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8882-119">キーワードの`Keywords_austria_eu_gps_data`があります。</span><span class="sxs-lookup"><span data-stu-id="e8882-119">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="e8882-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-120">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-121">正規表現`Regex_austria_eu_gps_data_1`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-121">The regular expression  `Regex_austria_eu_gps_data_1` finds content that matches the pattern.</span></span> 
    
<span data-ttu-id="e8882-122">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-122">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-123">正規表現`Regex_austria_eu_gps_data_2`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-123">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8882-124">キーワードの`Keywords_austria_eu_gps_data`があります。</span><span class="sxs-lookup"><span data-stu-id="e8882-124">A keyword from  `Keywords_austria_eu_gps_data` is found.</span></span> 
    
<span data-ttu-id="e8882-125">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-125">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-126">正規表現`Regex_austria_eu_gps_data_2`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-126">The regular expression  `Regex_austria_eu_gps_data_2` finds content that matches the pattern.</span></span> 
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
          <Match idRef="Keywords_austria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_austria_eu_gps_data_2" />
        </Pattern>

```

### <a name="keywords"></a><span data-ttu-id="e8882-127">Keywords</span><span class="sxs-lookup"><span data-stu-id="e8882-127">Keywords</span></span>

#### <a name="keywordsaustriaeugpsdata"></a><span data-ttu-id="e8882-128">Keywords_austria_eu_gps_data</span><span class="sxs-lookup"><span data-stu-id="e8882-128">Keywords_austria_eu_gps_data</span></span>

<span data-ttu-id="e8882-129">gps の追跡ツール</span><span class="sxs-lookup"><span data-stu-id="e8882-129">gps tracker</span></span>
  
<span data-ttu-id="e8882-130">gps 座標</span><span class="sxs-lookup"><span data-stu-id="e8882-130">gps coordinates</span></span>
  
<span data-ttu-id="e8882-131">場所</span><span class="sxs-lookup"><span data-stu-id="e8882-131">location</span></span>
  
<span data-ttu-id="e8882-132">地図</span><span class="sxs-lookup"><span data-stu-id="e8882-132">map</span></span>
  
<span data-ttu-id="e8882-133">緯度</span><span class="sxs-lookup"><span data-stu-id="e8882-133">latitude</span></span>
  
<span data-ttu-id="e8882-134">経度</span><span class="sxs-lookup"><span data-stu-id="e8882-134">longitude</span></span>
  
<span data-ttu-id="e8882-135">GPS トラッカー</span><span class="sxs-lookup"><span data-stu-id="e8882-135">GPS-Tracker</span></span>
  
<span data-ttu-id="e8882-136">GPS Koordinaten</span><span class="sxs-lookup"><span data-stu-id="e8882-136">GPS-Koordinaten</span></span>
  
<span data-ttu-id="e8882-137">Standort Karte</span><span class="sxs-lookup"><span data-stu-id="e8882-137">Standort Karte</span></span>
  
<span data-ttu-id="e8882-138">Breitengrad</span><span class="sxs-lookup"><span data-stu-id="e8882-138">Breitengrad</span></span>
  
<span data-ttu-id="e8882-139">Längengrad</span><span class="sxs-lookup"><span data-stu-id="e8882-139">Längengrad</span></span>
  
## <a name="belgium"></a><span data-ttu-id="e8882-140">ベルギー</span><span class="sxs-lookup"><span data-stu-id="e8882-140">Belgium</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-141">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-141">Pattern</span></span>

-  <span data-ttu-id="e8882-142">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-142">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-143">Checksum</span></span>

<span data-ttu-id="e8882-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-145">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-145">Definition</span></span>

<span data-ttu-id="e8882-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-147">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-147">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-148">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-148">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
          <Match idRef="Keywords_belgium_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="bulgaria"></a><span data-ttu-id="e8882-149">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="e8882-149">Bulgaria</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-150">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-150">Pattern</span></span>

-  <span data-ttu-id="e8882-151">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-151">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-152">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-152">Checksum</span></span>

<span data-ttu-id="e8882-153">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-153">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-154">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-154">Definition</span></span>

<span data-ttu-id="e8882-155">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-155">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-156">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-156">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-157">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-157">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75>
</Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_belgium_eu_gps_data_2" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_gps_data_2" />
          <Match idRef="Keywords_bulgaria_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="croatia"></a><span data-ttu-id="e8882-158">クロアチア</span><span class="sxs-lookup"><span data-stu-id="e8882-158">Croatia</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-159">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-159">Pattern</span></span>

-  <span data-ttu-id="e8882-160">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-160">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-161">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-161">Checksum</span></span>

<span data-ttu-id="e8882-162">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-162">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-163">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-163">Definition</span></span>

<span data-ttu-id="e8882-164">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-164">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-165">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-165">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-166">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-166">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
          <Match idRef="Keywords_croatia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_croatia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="cyprus"></a><span data-ttu-id="e8882-167">キプロス</span><span class="sxs-lookup"><span data-stu-id="e8882-167">Cyprus</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-168">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-168">Pattern</span></span>

-  <span data-ttu-id="e8882-169">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-169">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-170">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-170">Checksum</span></span>

<span data-ttu-id="e8882-171">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-171">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-172">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-172">Definition</span></span>

<span data-ttu-id="e8882-173">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-173">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-174">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-174">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-175">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-175">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
          <Match idRef="Keywords_cyprus_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_cyprus_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="czech-republic"></a><span data-ttu-id="e8882-176">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="e8882-176">Czech Republic</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-177">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-177">Pattern</span></span>

-  <span data-ttu-id="e8882-178">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-178">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-179">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-179">Checksum</span></span>

<span data-ttu-id="e8882-180">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-180">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-181">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-181">Definition</span></span>

<span data-ttu-id="e8882-182">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-182">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
<span data-ttu-id="e8882-183">DLP ポリシーとは、この種の機密情報を検出したことを必ず、近くにある文字以内の場合。</span><span class="sxs-lookup"><span data-stu-id="e8882-183">A DLP policy is % confident that it's detected this type of sensitive information if, within a proximity of characters:</span></span>
  
- <span data-ttu-id="e8882-184">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-184">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-185">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-185">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
          <Match idRef="Keywords_czech_republic_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_czech_republic_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="denmark"></a><span data-ttu-id="e8882-186">デンマーク</span><span class="sxs-lookup"><span data-stu-id="e8882-186">Denmark</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-187">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-187">Pattern</span></span>

-  <span data-ttu-id="e8882-188">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-188">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-189">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-189">Checksum</span></span>

<span data-ttu-id="e8882-190">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-190">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-191">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-191">Definition</span></span>

<span data-ttu-id="e8882-192">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-192">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-193">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-193">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-194">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-194">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
          <Match idRef="Keywords_denmark_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_denmark_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="estonia"></a><span data-ttu-id="e8882-195">エストニア</span><span class="sxs-lookup"><span data-stu-id="e8882-195">Estonia</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-196">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-196">Pattern</span></span>

-  <span data-ttu-id="e8882-197">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-197">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-198">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-198">Checksum</span></span>

<span data-ttu-id="e8882-199">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-199">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-200">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-200">Definition</span></span>

<span data-ttu-id="e8882-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-202">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-202">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-203">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-203">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
          <Match idRef="Keywords_estonia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_estonia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="finland"></a><span data-ttu-id="e8882-204">フィンランド</span><span class="sxs-lookup"><span data-stu-id="e8882-204">Finland</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-205">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-205">Pattern</span></span>

-  <span data-ttu-id="e8882-206">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-206">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-207">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-207">Checksum</span></span>

<span data-ttu-id="e8882-208">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-208">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-209">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-209">Definition</span></span>

<span data-ttu-id="e8882-210">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-210">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-211">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-211">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-212">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-212">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
          <Match idRef="Keywords_finland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_finland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="france"></a><span data-ttu-id="e8882-213">フランス</span><span class="sxs-lookup"><span data-stu-id="e8882-213">France</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-214">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-214">Pattern</span></span>

-  <span data-ttu-id="e8882-215">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-215">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-216">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-216">Checksum</span></span>

<span data-ttu-id="e8882-217">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-217">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-218">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-218">Definition</span></span>

<span data-ttu-id="e8882-219">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-219">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-220">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-220">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-221">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-221">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
          <Match idRef="Keywords_france_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_france_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="germany"></a><span data-ttu-id="e8882-222">ドイツ</span><span class="sxs-lookup"><span data-stu-id="e8882-222">Germany</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-223">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-223">Pattern</span></span>

-  <span data-ttu-id="e8882-224">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-224">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-225">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-225">Checksum</span></span>

<span data-ttu-id="e8882-226">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-226">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-227">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-227">Definition</span></span>

<span data-ttu-id="e8882-228">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-228">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-229">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-229">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-230">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-230">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
          <Match idRef="Keywords_germany_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_germany_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="greece"></a><span data-ttu-id="e8882-231">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="e8882-231">Greece</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-232">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-232">Pattern</span></span>

-  <span data-ttu-id="e8882-233">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-233">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-234">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-234">Checksum</span></span>

<span data-ttu-id="e8882-235">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-235">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-236">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-236">Definition</span></span>

<span data-ttu-id="e8882-237">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-237">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-238">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-238">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-239">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-239">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_greece_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_gps_data_2" />
          <Match idRef="Keywords_greece_eu_gps_data" />
        </Pattern>
</Entity>
```

## <a name="hungary"></a><span data-ttu-id="e8882-240">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="e8882-240">Hungary</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-241">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-241">Pattern</span></span>

-  <span data-ttu-id="e8882-242">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-242">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-243">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-243">Checksum</span></span>

<span data-ttu-id="e8882-244">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-244">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-245">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-245">Definition</span></span>

<span data-ttu-id="e8882-246">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-246">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-247">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-247">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-248">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-248">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
          <Match idRef="Keywords_hungary_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_hungary_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="ireland"></a><span data-ttu-id="e8882-249">Ireland</span><span class="sxs-lookup"><span data-stu-id="e8882-249">Ireland</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-250">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-250">Pattern</span></span>

-  <span data-ttu-id="e8882-251">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-251">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-252">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-252">Checksum</span></span>

<span data-ttu-id="e8882-253">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-253">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-254">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-254">Definition</span></span>

<span data-ttu-id="e8882-255">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-255">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-256">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-256">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-257">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-257">A keyword from is found.</span></span>
    
```
 
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
          <Match idRef="Keywords_ireland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_ireland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="italy"></a><span data-ttu-id="e8882-258">イタリア</span><span class="sxs-lookup"><span data-stu-id="e8882-258">Italy</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-259">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-259">Pattern</span></span>

-  <span data-ttu-id="e8882-260">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-260">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-261">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-261">Checksum</span></span>

<span data-ttu-id="e8882-262">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-262">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-263">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-263">Definition</span></span>

<span data-ttu-id="e8882-264">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-264">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-265">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-265">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-266">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-266">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
          <Match idRef="Keywords_italy_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_italy_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="latvia"></a><span data-ttu-id="e8882-267">ラトビア</span><span class="sxs-lookup"><span data-stu-id="e8882-267">Latvia</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-268">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-268">Pattern</span></span>

-  <span data-ttu-id="e8882-269">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-269">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-270">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-270">Checksum</span></span>

<span data-ttu-id="e8882-271">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-271">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-272">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-272">Definition</span></span>

<span data-ttu-id="e8882-273">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-273">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-274">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-274">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-275">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-275">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
          <Match idRef="Keywords_latvia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_latvia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="lithuania"></a><span data-ttu-id="e8882-276">リトアニア</span><span class="sxs-lookup"><span data-stu-id="e8882-276">Lithuania</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-277">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-277">Pattern</span></span>

-  <span data-ttu-id="e8882-278">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-278">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-279">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-279">Checksum</span></span>

<span data-ttu-id="e8882-280">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-280">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-281">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-281">Definition</span></span>

<span data-ttu-id="e8882-282">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-283">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-283">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-284">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-284">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
          <Match idRef="Keywords_lithuania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_lithuania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="luxemburg"></a><span data-ttu-id="e8882-285">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="e8882-285">Luxemburg</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-286">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-286">Pattern</span></span>

-  <span data-ttu-id="e8882-287">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-287">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-288">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-288">Checksum</span></span>

<span data-ttu-id="e8882-289">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-289">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-290">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-290">Definition</span></span>

<span data-ttu-id="e8882-291">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-291">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-292">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-292">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-293">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-293">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
          <Match idRef="Keywords_luxemburg_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_luxemburg_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="malta"></a><span data-ttu-id="e8882-294">マルタ</span><span class="sxs-lookup"><span data-stu-id="e8882-294">Malta</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-295">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-295">Pattern</span></span>

-  <span data-ttu-id="e8882-296">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-296">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-297">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-297">Checksum</span></span>

<span data-ttu-id="e8882-298">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-298">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-299">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-299">Definition</span></span>

<span data-ttu-id="e8882-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-301">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-301">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-302">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-302">A keyword from is found.</span></span>
    
```
<Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
          <Match idRef="Keywords_malta_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="netherlands"></a><span data-ttu-id="e8882-303">オランダ</span><span class="sxs-lookup"><span data-stu-id="e8882-303">Netherlands</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-304">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-304">Pattern</span></span>

-  <span data-ttu-id="e8882-305">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-305">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-306">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-306">Checksum</span></span>

<span data-ttu-id="e8882-307">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-307">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-308">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-308">Definition</span></span>

<span data-ttu-id="e8882-309">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-309">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-310">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-310">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-311">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-311">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
          <Match idRef="Keywords_netherlands_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_netherlands_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="poland"></a><span data-ttu-id="e8882-312">ポーランド</span><span class="sxs-lookup"><span data-stu-id="e8882-312">Poland</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-313">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-313">Pattern</span></span>

-  <span data-ttu-id="e8882-314">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-314">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-315">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-315">Checksum</span></span>

<span data-ttu-id="e8882-316">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-316">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-317">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-317">Definition</span></span>

<span data-ttu-id="e8882-318">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-318">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-319">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-319">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-320">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-320">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
          <Match idRef="Keywords_poland_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_poland_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="portugal"></a><span data-ttu-id="e8882-321">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="e8882-321">Portugal</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-322">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-322">Pattern</span></span>

-  <span data-ttu-id="e8882-323">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-323">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-324">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-324">Checksum</span></span>

<span data-ttu-id="e8882-325">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-325">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-326">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-326">Definition</span></span>

<span data-ttu-id="e8882-327">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-327">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-328">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-328">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-329">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-329">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
          <Match idRef="Keywords_portugal_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_portugal_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="romania"></a><span data-ttu-id="e8882-330">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="e8882-330">Romania</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-331">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-331">Pattern</span></span>

-  <span data-ttu-id="e8882-332">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-332">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-333">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-333">Checksum</span></span>

<span data-ttu-id="e8882-334">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-334">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-335">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-335">Definition</span></span>

<span data-ttu-id="e8882-336">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-336">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-337">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-337">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-338">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-338">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
          <Match idRef="Keywords_romania_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_romania_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovakia"></a><span data-ttu-id="e8882-339">スロバキア</span><span class="sxs-lookup"><span data-stu-id="e8882-339">Slovakia</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-340">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-340">Pattern</span></span>

-  <span data-ttu-id="e8882-341">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-341">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-342">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-342">Checksum</span></span>

<span data-ttu-id="e8882-343">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-343">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-344">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-344">Definition</span></span>

<span data-ttu-id="e8882-345">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-345">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-346">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-346">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-347">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-347">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
          <Match idRef="Keywords_slovakia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovakia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="slovenia"></a><span data-ttu-id="e8882-348">スロベニア</span><span class="sxs-lookup"><span data-stu-id="e8882-348">Slovenia</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-349">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-349">Pattern</span></span>

-  <span data-ttu-id="e8882-350">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-350">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-351">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-351">Checksum</span></span>

<span data-ttu-id="e8882-352">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-352">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-353">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-353">Definition</span></span>

<span data-ttu-id="e8882-354">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-354">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-355">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-355">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-356">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-356">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
          <Match idRef="Keywords_slovenia_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_slovenia_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="spain"></a><span data-ttu-id="e8882-357">スペイン</span><span class="sxs-lookup"><span data-stu-id="e8882-357">Spain</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-358">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-358">Pattern</span></span>

-  <span data-ttu-id="e8882-359">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-359">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-360">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-360">Checksum</span></span>

<span data-ttu-id="e8882-361">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-361">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-362">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-362">Definition</span></span>

<span data-ttu-id="e8882-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-364">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-364">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-365">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-365">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
          <Match idRef="Keywords_spain_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_spain_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="sweden"></a><span data-ttu-id="e8882-366">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="e8882-366">Sweden</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-367">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-367">Pattern</span></span>

-  <span data-ttu-id="e8882-368">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-368">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-369">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-369">Checksum</span></span>

<span data-ttu-id="e8882-370">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-370">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-371">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-371">Definition</span></span>

<span data-ttu-id="e8882-372">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-372">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-373">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-373">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-374">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-374">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
          <Match idRef="Keywords_sweden_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_sweden_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="uk"></a><span data-ttu-id="e8882-375">英国</span><span class="sxs-lookup"><span data-stu-id="e8882-375">UK</span></span>

### <a name="pattern"></a><span data-ttu-id="e8882-376">パターン</span><span class="sxs-lookup"><span data-stu-id="e8882-376">Pattern</span></span>

-  <span data-ttu-id="e8882-377">桁</span><span class="sxs-lookup"><span data-stu-id="e8882-377">digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8882-378">チェックサム</span><span class="sxs-lookup"><span data-stu-id="e8882-378">Checksum</span></span>

<span data-ttu-id="e8882-379">該当なし</span><span class="sxs-lookup"><span data-stu-id="e8882-379">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8882-380">定義</span><span class="sxs-lookup"><span data-stu-id="e8882-380">Definition</span></span>

<span data-ttu-id="e8882-381">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="e8882-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8882-382">正規表現パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="e8882-382">The regular expression finds content that matches the pattern.</span></span>
    
- <span data-ttu-id="e8882-383">キーワードを検出するとします。</span><span class="sxs-lookup"><span data-stu-id="e8882-383">A keyword from is found.</span></span>
    
```
 <Entity id="42ac9f40-0912-4ae3-b5e6-08967192dec0" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_1" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
          <Match idRef="Keywords_uk_eu_gps_data" />
        </Pattern>
        <Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_uk_eu_gps_data_2" />
        </Pattern>
</Entity>
```

## <a name="see-also"></a><span data-ttu-id="e8882-384">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8882-384">See also</span></span>

[<span data-ttu-id="e8882-385">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="e8882-385">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

