---
title: EU 税 Id 番号
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: f04919c8-2356-4de2-bb2a-b9f67f339726
description: このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 税 Id 番号の機密性の高い情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 5192496b393d15fd6d063e09c9bfe1cb3dd7e2dd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532123"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="7aaa2-104">EU 税 Id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-104">EU Tax Identification Number</span></span>

<span data-ttu-id="7aaa2-p102">このトピックでは、データ損失防止 (DLP) ポリシーがどの EU 税 Id 番号 (TIN) 機密情報の種類が検出されたときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="7aaa2-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-108">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-108">Format</span></span>

<span data-ttu-id="7aaa2-109">任意指定のハイフンとスラッシュの 9 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-110">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-110">Pattern</span></span>

<span data-ttu-id="7aaa2-111">任意指定のハイフンとスラッシュで 9 つの数字。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="7aaa2-112">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-112">Two digits</span></span> 
    
- <span data-ttu-id="7aaa2-113">ハイフン (省略可能)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="7aaa2-114">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-114">Three digits</span></span>
    
- <span data-ttu-id="7aaa2-115">スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="7aaa2-116">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-117">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-117">Checksum</span></span>

<span data-ttu-id="7aaa2-118">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-119">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-119">Definition</span></span>

<span data-ttu-id="7aaa2-120">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-121">関数`Func_austria_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-122">キーワードの`Keywords_austria_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-123">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-124">関数`Func_austria_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-125">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-125">Keywords</span></span>

#### <a name="keywordsaustriaeutaxfilenumber"></a><span data-ttu-id="7aaa2-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-127">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-127">tax number</span></span>
  
<span data-ttu-id="7aaa2-128">番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-128">number</span></span>
  
<span data-ttu-id="7aaa2-129">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-129">tax registration number</span></span>
  
<span data-ttu-id="7aaa2-130">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-130">tax id</span></span>
  
<span data-ttu-id="7aaa2-131">st.nr。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-131">st.nr.</span></span>
  
<span data-ttu-id="7aaa2-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="7aaa2-133">ベルギー</span><span class="sxs-lookup"><span data-stu-id="7aaa2-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-134">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-134">Format</span></span>

<span data-ttu-id="7aaa2-135">スペースや区切り記号なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-136">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-136">Pattern</span></span>

<span data-ttu-id="7aaa2-137">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-137">11 digits:</span></span>
  
- <span data-ttu-id="7aaa2-138">2 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-138">Two digits</span></span>
    
- <span data-ttu-id="7aaa2-139">「0」または「1」</span><span class="sxs-lookup"><span data-stu-id="7aaa2-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="7aaa2-140">1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-140">One digit</span></span>
    
- <span data-ttu-id="7aaa2-141">「0」または「1」または「2」または「3」</span><span class="sxs-lookup"><span data-stu-id="7aaa2-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="7aaa2-142">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-143">Checksum</span></span>

<span data-ttu-id="7aaa2-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-145">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-145">Definition</span></span>

<span data-ttu-id="7aaa2-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-147">正規表現`Regex_belgium_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-148">キーワードの`Keywords_belgium_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-149">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-149">Keywords</span></span>

#### <a name="keywordsbelgiumeutaxfilenumber"></a><span data-ttu-id="7aaa2-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-151">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-151">tax number</span></span>
  
<span data-ttu-id="7aaa2-152">国内の登録番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-152">national registration number</span></span>
  
<span data-ttu-id="7aaa2-153">税務登録番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-153">tax registration number</span></span>
  
<span data-ttu-id="7aaa2-154">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-154">tax id</span></span>
  
<span data-ttu-id="7aaa2-155">%n</span><span class="sxs-lookup"><span data-stu-id="7aaa2-155">nif</span></span>
  
<span data-ttu-id="7aaa2-156">%n #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-156">nif#</span></span>
  
<span data-ttu-id="7aaa2-157">numéro de registre の国</span><span class="sxs-lookup"><span data-stu-id="7aaa2-157">numéro de registre national</span></span>
  
<span data-ttu-id="7aaa2-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="7aaa2-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="7aaa2-159">ブルガリア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-160">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-160">Format</span></span>

<span data-ttu-id="7aaa2-161">スペースや区切り記号なしの 10 桁</span><span class="sxs-lookup"><span data-stu-id="7aaa2-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-162">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-162">Pattern</span></span>

<span data-ttu-id="7aaa2-163">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-164">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-164">Checksum</span></span>

<span data-ttu-id="7aaa2-165">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-166">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-166">Definition</span></span>

<span data-ttu-id="7aaa2-167">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-168">関数`Func_bulgaria_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-169">キーワードの`Keywords_bulgaria_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-170">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-171">関数`Func_bulgaria_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-172">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-172">Keywords</span></span>

#### <a name="keywordsbulgariaeutaxfilenumber"></a><span data-ttu-id="7aaa2-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-174">bucn</span><span class="sxs-lookup"><span data-stu-id="7aaa2-174">bucn</span></span>
  
<span data-ttu-id="7aaa2-175">統一された民事上の数</span><span class="sxs-lookup"><span data-stu-id="7aaa2-175">uniform civil number</span></span>
  
<span data-ttu-id="7aaa2-176">bucn #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-176">bucn#</span></span>
  
<span data-ttu-id="7aaa2-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="7aaa2-178">民事 id の統一</span><span class="sxs-lookup"><span data-stu-id="7aaa2-178">uniform civil id</span></span>
  
<span data-ttu-id="7aaa2-179">民事なしの統一されました。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-179">uniform civil no</span></span>
  
<span data-ttu-id="7aaa2-180">egn</span><span class="sxs-lookup"><span data-stu-id="7aaa2-180">egn</span></span>
  
<span data-ttu-id="7aaa2-181">ブルガリア語の統一された民事数</span><span class="sxs-lookup"><span data-stu-id="7aaa2-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="7aaa2-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-182">uniformcivilno#</span></span>
  
<span data-ttu-id="7aaa2-183">egn #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-183">egn#</span></span>
  
<span data-ttu-id="7aaa2-184">УНИФОРМ ГРАЖДАНСКИ НОМЕР</span><span class="sxs-lookup"><span data-stu-id="7aaa2-184">униформ граждански номер</span></span>
  
<span data-ttu-id="7aaa2-185">Униформ id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-185">униформ id</span></span>
  
<span data-ttu-id="7aaa2-186">Униформ граждански id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-186">униформ граждански id</span></span>
  
<span data-ttu-id="7aaa2-187">УНИФОРМ ГРАЖДАНСКИ НЕ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="7aaa2-188">クロアチア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-189">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-189">Format</span></span>

<span data-ttu-id="7aaa2-190">スペースや区切り文字なしで 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-191">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-191">Pattern</span></span>

<span data-ttu-id="7aaa2-192">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-192">11 digits:</span></span>
  
- <span data-ttu-id="7aaa2-193">ランダムに選択した 10 個の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="7aaa2-194">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-195">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-195">Checksum</span></span>

<span data-ttu-id="7aaa2-196">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-197">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-197">Definition</span></span>

<span data-ttu-id="7aaa2-198">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-199">関数`Func_croatia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-200">キーワードの`Keywords_croatia_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-201">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-202">関数`Func_croatia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-203">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-203">Keywords</span></span>

#### <a name="keywordscroatiaeutaxfilenumber"></a><span data-ttu-id="7aaa2-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-205">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-205">tax number</span></span>
  
<span data-ttu-id="7aaa2-206">税</span><span class="sxs-lookup"><span data-stu-id="7aaa2-206">tax</span></span>
  
<span data-ttu-id="7aaa2-207">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-207">tax id</span></span>
  
<span data-ttu-id="7aaa2-208">oid</span><span class="sxs-lookup"><span data-stu-id="7aaa2-208">oid</span></span>
  
<span data-ttu-id="7aaa2-209">oid 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-209">oid#</span></span>
  
<span data-ttu-id="7aaa2-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="7aaa2-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="7aaa2-211">キプロス</span><span class="sxs-lookup"><span data-stu-id="7aaa2-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-212">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-212">Format</span></span>

<span data-ttu-id="7aaa2-213">8 桁と指定されたパターンの 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-214">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-214">Pattern</span></span>

<span data-ttu-id="7aaa2-215">8 桁の数字および文字を 1 つ。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="7aaa2-216">「0」</span><span class="sxs-lookup"><span data-stu-id="7aaa2-216">A "0"</span></span> 
    
- <span data-ttu-id="7aaa2-217">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-217">Seven digits</span></span>
    
- <span data-ttu-id="7aaa2-218">1 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-219">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-219">Checksum</span></span>

<span data-ttu-id="7aaa2-220">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-221">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-221">Definition</span></span>

<span data-ttu-id="7aaa2-222">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-223">関数`Func_cyprus_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-224">キーワードの`Keywords_cyprus_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-225">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-226">関数`Func_cyprus_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-227">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-227">Keywords</span></span>

#### <a name="keywordscypruseutaxfilenumber"></a><span data-ttu-id="7aaa2-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-229">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-229">tax number</span></span>
  
<span data-ttu-id="7aaa2-230">税</span><span class="sxs-lookup"><span data-stu-id="7aaa2-230">tax</span></span>
  
<span data-ttu-id="7aaa2-231">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-231">tax id</span></span>
  
<span data-ttu-id="7aaa2-232">税の識別コード</span><span class="sxs-lookup"><span data-stu-id="7aaa2-232">tax identification code</span></span>
  
<span data-ttu-id="7aaa2-233">tic</span><span class="sxs-lookup"><span data-stu-id="7aaa2-233">tic</span></span>
  
<span data-ttu-id="7aaa2-234">tic #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-234">tic#</span></span>
  
<span data-ttu-id="7aaa2-235">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="7aaa2-236">ΦΟΡΟΛΟΓΙΚΉ ΤΑΥΤΌΤΗΤΑ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="7aaa2-237">ΚΩΔΙΚΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="7aaa2-238">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="7aaa2-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-239">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-239">Format</span></span>

<span data-ttu-id="7aaa2-240">オプションの円記号と 9 桁または 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-241">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-241">Pattern</span></span>

<span data-ttu-id="7aaa2-242">9 桁または 10 桁の数字、省略可能な backslashl で:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="7aaa2-243">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-243">Six digits</span></span> 
    
- <span data-ttu-id="7aaa2-244">バック スラッシュ (省略可能)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="7aaa2-245">3 つまたは 4 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-246">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-246">Checksum</span></span>

<span data-ttu-id="7aaa2-247">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-248">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-248">Definition</span></span>

<span data-ttu-id="7aaa2-249">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-250">正規表現`Regex_czech_republic_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-251">キーワードの`Keywords_czech_republic_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-252">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-252">Keywords</span></span>

#### <a name="keywordsczechrepubliceutaxfilenumber"></a><span data-ttu-id="7aaa2-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-254">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-254">tax number</span></span>
  
<span data-ttu-id="7aaa2-255">税</span><span class="sxs-lookup"><span data-stu-id="7aaa2-255">tax</span></span>
  
<span data-ttu-id="7aaa2-256">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-256">tax id</span></span>
  
<span data-ttu-id="7aaa2-257">個人番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-257">personal number</span></span>
  
<span data-ttu-id="7aaa2-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="7aaa2-258">daňové číslo</span></span>
  
<span data-ttu-id="7aaa2-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="7aaa2-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="7aaa2-260">デンマーク</span><span class="sxs-lookup"><span data-stu-id="7aaa2-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-261">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-261">Format</span></span>

<span data-ttu-id="7aaa2-262">10 桁の数字、ハイフンを含む</span><span class="sxs-lookup"><span data-stu-id="7aaa2-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-263">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-263">Pattern</span></span>

<span data-ttu-id="7aaa2-264">10 個の数字が、hyphenl が含まれています。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="7aaa2-265">6 桁の数字が日付の生年月日に対応します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="7aaa2-266">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="7aaa2-266">A hyphen</span></span>
    
- <span data-ttu-id="7aaa2-267">生年月日の 4 桁の年に最初の桁が対応するシーケンス番号に対応する 4 桁の数字と最後の桁は、個人の性別を (男性と女性の場合でも、奇数ページ) に対応します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-268">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-268">Checksum</span></span>

<span data-ttu-id="7aaa2-269">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-270">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-270">Definition</span></span>

<span data-ttu-id="7aaa2-271">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-272">関数`Func_denmark_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-273">キーワードの`Keywords_denmark_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-274">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-275">関数`Func_denmark_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-276">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-276">Keywords</span></span>

#### <a name="keywordsdenmarkeutaxfilenumber"></a><span data-ttu-id="7aaa2-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-278">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-278">tax number</span></span>
  
<span data-ttu-id="7aaa2-279">税</span><span class="sxs-lookup"><span data-stu-id="7aaa2-279">tax</span></span>
  
<span data-ttu-id="7aaa2-280">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-280">tax id</span></span>
  
<span data-ttu-id="7aaa2-281">cpr の数</span><span class="sxs-lookup"><span data-stu-id="7aaa2-281">cpr number</span></span>
  
<span data-ttu-id="7aaa2-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-282">cpr#</span></span>
  
<span data-ttu-id="7aaa2-283">skat nummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-283">skat nummer</span></span>
  
<span data-ttu-id="7aaa2-284">skat id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="7aaa2-285">エストニア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-286">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-286">Format</span></span>

<span data-ttu-id="7aaa2-287">スペースや区切り文字なしで 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-288">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-288">Pattern</span></span>

<span data-ttu-id="7aaa2-289">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-289">11 digits:</span></span>
  
-  <span data-ttu-id="7aaa2-290">性別および誕生日、奇数個 (オス) を示し、ことを示します (メス) を次のように、偶数の世紀に対応する 1 つの数字: 1, 2; 19 世紀の最後の3、4 の 20 世紀の年です。5、6、21 世紀の</span><span class="sxs-lookup"><span data-stu-id="7aaa2-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="7aaa2-291">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="7aaa2-292">シリアル番号が同じ日に生まれた人を分離することに対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="7aaa2-293">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-294">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-294">Checksum</span></span>

<span data-ttu-id="7aaa2-295">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-296">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-296">Definition</span></span>

<span data-ttu-id="7aaa2-297">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-298">関数`Func_estonia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-299">キーワードの`Keywords_estonia_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-300">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-301">関数`Func_estonia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-302">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-302">Keywords</span></span>

#### <a name="keywordsestoniaeutaxfilenumber"></a><span data-ttu-id="7aaa2-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-304">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-304">tax number</span></span>
  
<span data-ttu-id="7aaa2-305">税</span><span class="sxs-lookup"><span data-stu-id="7aaa2-305">tax</span></span>
  
<span data-ttu-id="7aaa2-306">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-306">tax id</span></span>
  
<span data-ttu-id="7aaa2-307">個人コード</span><span class="sxs-lookup"><span data-stu-id="7aaa2-307">personal code</span></span>
  
<span data-ttu-id="7aaa2-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-308">maksunumber</span></span>
  
<span data-ttu-id="7aaa2-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-309">maksu id</span></span>
  
<span data-ttu-id="7aaa2-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="7aaa2-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="7aaa2-311">フィンランド</span><span class="sxs-lookup"><span data-stu-id="7aaa2-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-312">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-312">Format</span></span>

<span data-ttu-id="7aaa2-313">数字、11 文字の組み合わせは、次の文字、およびプラス記号とマイナス記号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-314">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-314">Pattern</span></span>

<span data-ttu-id="7aaa2-315">数字、11 文字の組み合わせは、次の文字、およびプラス記号とマイナス記号。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="7aaa2-316">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-316">Six digits</span></span>
    
- <span data-ttu-id="7aaa2-317">次のいずれか: プラス記号、マイナス記号またはプラス記号の意味、文字"A"(大文字小文字を区別) 1800-1899 の間に生まれたマイナスの署名との間に生まれた意味 1900-1999 年、および"2000 の誕生は A"し、</span><span class="sxs-lookup"><span data-stu-id="7aaa2-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="7aaa2-318">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-318">Three digits</span></span>
    
- <span data-ttu-id="7aaa2-319">1 つの文字または 1 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-320">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-320">Checksum</span></span>

<span data-ttu-id="7aaa2-321">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-322">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-322">Definition</span></span>

<span data-ttu-id="7aaa2-323">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-324">関数`Func_finland_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-325">キーワードの`Keywords_finland_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-326">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-327">関数`Func_finland_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-328">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-328">Keywords</span></span>

#### <a name="keywordsfinlandeutaxfilenumber"></a><span data-ttu-id="7aaa2-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-330">identification number
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-330">identification number</span></span>
  
<span data-ttu-id="7aaa2-331">パーソナル id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-331">personal id</span></span>
  
<span data-ttu-id="7aaa2-332">id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-332">identity number</span></span>
  
<span data-ttu-id="7aaa2-333">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-333">finnish national id number</span></span>
  
<span data-ttu-id="7aaa2-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-334">personalidnumber#</span></span>
  
<span data-ttu-id="7aaa2-335">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-335">national identification number</span></span>
  
<span data-ttu-id="7aaa2-336">id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-336">id number</span></span>
  
<span data-ttu-id="7aaa2-337">国民 id なし。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-337">national id no.</span></span>
  
<span data-ttu-id="7aaa2-338">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-338">national id number</span></span>
  
<span data-ttu-id="7aaa2-339">id なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-339">id no</span></span>
  
<span data-ttu-id="7aaa2-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7aaa2-340">tunnistenumero</span></span>
  
<span data-ttu-id="7aaa2-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="7aaa2-341">henkilötunnus</span></span>
  
<span data-ttu-id="7aaa2-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7aaa2-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="7aaa2-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="7aaa2-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="7aaa2-344">identiteetti して</span><span class="sxs-lookup"><span data-stu-id="7aaa2-344">identiteetti numero</span></span>
  
<span data-ttu-id="7aaa2-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="7aaa2-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="7aaa2-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="7aaa2-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="7aaa2-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="7aaa2-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="7aaa2-348">tunnusnumero</span></span>
  
<span data-ttu-id="7aaa2-349">kansallinen tunnus して</span><span class="sxs-lookup"><span data-stu-id="7aaa2-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="7aaa2-350">フランス</span><span class="sxs-lookup"><span data-stu-id="7aaa2-350">France</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-351">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-351">Format</span></span>

<span data-ttu-id="7aaa2-352">個人やエンティティの 9 桁の 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-353">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-353">Pattern</span></span>

<span data-ttu-id="7aaa2-354">個人の 13 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="7aaa2-355">1 桁の 0、1、2、または 3 にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="7aaa2-356">12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-356">12 digits</span></span>
    
<span data-ttu-id="7aaa2-357">エンティティの 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-358">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-358">Checksum</span></span>

<span data-ttu-id="7aaa2-359">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-360">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-360">Definition</span></span>

<span data-ttu-id="7aaa2-361">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-362">関数`Func_france_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-363">キーワードの`Keywords_france_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-364">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-365">関数`Func_france_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-366">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-366">Keywords</span></span>

#### <a name="keywordsfranceeutaxfilenumber"></a><span data-ttu-id="7aaa2-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-368">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-368">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-369">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-369">tax number</span></span>
  
<span data-ttu-id="7aaa2-370">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-370">tax id</span></span>
  
<span data-ttu-id="7aaa2-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="7aaa2-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="7aaa2-372">ドイツ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-373">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-373">Format</span></span>

<span data-ttu-id="7aaa2-374">スペースや区切り記号なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-375">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-375">Pattern</span></span>

<span data-ttu-id="7aaa2-376">11 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-376">11 digits :</span></span>
  
-  <span data-ttu-id="7aaa2-377">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-377">Ten digits</span></span> 
    
- <span data-ttu-id="7aaa2-378">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-379">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-379">Checksum</span></span>

<span data-ttu-id="7aaa2-380">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-381">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-381">Definition</span></span>

<span data-ttu-id="7aaa2-382">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-383">関数`Func_germany_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-384">キーワードの`Keywords_germany_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-385">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-386">関数`Func_germany_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-387">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-387">Keywords</span></span>

#### <a name="keywordsgermanyeutaxfilenumber"></a><span data-ttu-id="7aaa2-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-389">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-389">tax number</span></span>
  
<span data-ttu-id="7aaa2-390">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-390">tax no.</span></span>
  
<span data-ttu-id="7aaa2-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-391">taxno#</span></span>
  
<span data-ttu-id="7aaa2-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-392">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-393">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-394">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-394">tax id</span></span>
  
<span data-ttu-id="7aaa2-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-395">taxid#</span></span>
  
<span data-ttu-id="7aaa2-396">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-396">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-397">税 id が不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-397">tax identification no.</span></span>
  
<span data-ttu-id="7aaa2-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-398">steuernummer</span></span>
  
<span data-ttu-id="7aaa2-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-399">steuer id</span></span>
  
<span data-ttu-id="7aaa2-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="7aaa2-401">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-402">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-402">Format</span></span>

<span data-ttu-id="7aaa2-403">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="7aaa2-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-404">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-404">Pattern</span></span>

<span data-ttu-id="7aaa2-405">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-406">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-406">Checksum</span></span>

<span data-ttu-id="7aaa2-407">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-408">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-408">Definition</span></span>

<span data-ttu-id="7aaa2-409">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-410">正規表現`Regex_greece_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-411">キーワードの`Keywords_greece_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-412">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-412">Keywords</span></span>

#### <a name="keywordsgreeceeutaxfilenumber"></a><span data-ttu-id="7aaa2-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-414">afm</span><span class="sxs-lookup"><span data-stu-id="7aaa2-414">afm</span></span>
  
<span data-ttu-id="7aaa2-415">tin
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-415">tin</span></span>
  
<span data-ttu-id="7aaa2-416">税 id のないです。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-416">tax id no.</span></span>
  
<span data-ttu-id="7aaa2-417">税 id のないです。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-417">tax id no</span></span>
  
<span data-ttu-id="7aaa2-418">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-418">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-419">税登録番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-419">tax registry number</span></span>
  
<span data-ttu-id="7aaa2-420">レジストリを税不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-420">tax registry no.</span></span>
  
<span data-ttu-id="7aaa2-421">afm #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-421">afm#</span></span>
  
<span data-ttu-id="7aaa2-422">tin #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-422">tin#</span></span>
  
<span data-ttu-id="7aaa2-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-423">taxidno#</span></span>
  
<span data-ttu-id="7aaa2-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-424">taxregistryno#</span></span>
  
<span data-ttu-id="7aaa2-425">ΑΡΙΘΜΌΣ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="7aaa2-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-426">aφμ</span></span>
  
<span data-ttu-id="7aaa2-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="7aaa2-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="7aaa2-428">ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ ΝΟ。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="7aaa2-429">ΤΟΝ ΑΡΙΘΜΌ ΦΟΡΟΛΟΓΙΚΟΎ ΜΗΤΡΏΟΥ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="7aaa2-430">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="7aaa2-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-431">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-431">Format</span></span>

<span data-ttu-id="7aaa2-432">スペースや区切り文字で 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-433">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-433">Pattern</span></span>

<span data-ttu-id="7aaa2-434">10 桁の数字。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-434">Ten digits:</span></span>
  
-  <span data-ttu-id="7aaa2-435">1 桁の数字「8」をする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="7aaa2-436">日付間の日数に対応する 5 桁の数字 01/01/1867 および個人の生まれた日</span><span class="sxs-lookup"><span data-stu-id="7aaa2-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="7aaa2-437">同じ日に生まれた個人を区別するために偶然に生成された番号に対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="7aaa2-438">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-439">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-439">Checksum</span></span>

<span data-ttu-id="7aaa2-440">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-441">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-441">Definition</span></span>

<span data-ttu-id="7aaa2-442">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-443">関数`Func_hungary_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-444">キーワードの`Keywords_hungary_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-445">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-446">関数`Func_hungary_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-447">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-447">Keywords</span></span>

#### <a name="keywordshungaryeutaxfilenumber"></a><span data-ttu-id="7aaa2-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-449">ハンガリー語の税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="7aaa2-450">ハンガリー語の tin</span><span class="sxs-lookup"><span data-stu-id="7aaa2-450">hungarian tin</span></span>
  
<span data-ttu-id="7aaa2-451">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-451">tax id number</span></span>
  
<span data-ttu-id="7aaa2-452">vat 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-452">vat number</span></span>
  
<span data-ttu-id="7aaa2-453">税務当局がありません。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-453">tax authority no</span></span>
  
<span data-ttu-id="7aaa2-454">税 id 税 id の番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-454">tax id tax identity number</span></span>
  
<span data-ttu-id="7aaa2-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-455">taxidnumber#</span></span>
  
<span data-ttu-id="7aaa2-456">tin #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-456">tin#</span></span>
  
<span data-ttu-id="7aaa2-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-457">hungatiantin#</span></span>
  
<span data-ttu-id="7aaa2-458">税の識別をしません。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-458">tax identification no</span></span>
  
<span data-ttu-id="7aaa2-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-459">taxidno#</span></span>
  
<span data-ttu-id="7aaa2-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="7aaa2-460">adóazonosító szám</span></span>
  
<span data-ttu-id="7aaa2-461">adószám</span><span class="sxs-lookup"><span data-stu-id="7aaa2-461">adószám</span></span>
  
<span data-ttu-id="7aaa2-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="7aaa2-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="7aaa2-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="7aaa2-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-464">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-464">Format</span></span>

<span data-ttu-id="7aaa2-465">スペースや区切り記号のない文字の後に 7 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-466">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-466">Pattern</span></span>

<span data-ttu-id="7aaa2-467">文字の後に 7 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="7aaa2-468">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-468">Seven digits</span></span> 
    
- <span data-ttu-id="7aaa2-469">1 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-470">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-470">Checksum</span></span>

<span data-ttu-id="7aaa2-471">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-472">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-472">Definition</span></span>

<span data-ttu-id="7aaa2-473">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-474">関数`Func_ireland_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-475">キーワードの`Keywords_ireland_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-476">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-477">関数`Func_ireland_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-478">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-478">Keywords</span></span>

#### <a name="keywordsirelandeutaxfilenumber"></a><span data-ttu-id="7aaa2-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-480">公共サービスなし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-480">public service no</span></span>
  
<span data-ttu-id="7aaa2-481">個人の公的サービスなし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-481">personal public service no</span></span>
  
<span data-ttu-id="7aaa2-482">pps なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-482">pps no</span></span>
  
<span data-ttu-id="7aaa2-483">個人サービスなし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-483">personal service no</span></span>
  
<span data-ttu-id="7aaa2-484">pps のサービスなし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-484">pps service no</span></span>
  
<span data-ttu-id="7aaa2-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-485">ppsno#</span></span>
  
<span data-ttu-id="7aaa2-486">アイルランド pps なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-486">irish pps no</span></span>
  
<span data-ttu-id="7aaa2-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-487">publicserviceno#</span></span>
  
<span data-ttu-id="7aaa2-488">個人の公的サービスの数</span><span class="sxs-lookup"><span data-stu-id="7aaa2-488">personal public service number</span></span>
  
<span data-ttu-id="7aaa2-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="7aaa2-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="7aaa2-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="7aaa2-490">pps uimh</span></span>
  
<span data-ttu-id="7aaa2-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="7aaa2-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="7aaa2-492">イタリア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-493">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-493">Format</span></span>

<span data-ttu-id="7aaa2-494">16 文字と数字で指定されたパターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-495">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-495">Pattern</span></span>

<span data-ttu-id="7aaa2-496">16 の文字と数字の場合。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="7aaa2-497">ファミリ名の最初の 3 つの子音に対応する 3 つの文字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="7aaa2-498">第 1、3 番目および 4 番目に対応する 3 文字名の子音</span><span class="sxs-lookup"><span data-stu-id="7aaa2-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="7aaa2-499">2 桁の桁の誕生年の最後に対応しています。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="7aaa2-500">生年月日の月に対応する 1 つの数字、文字は、アルファベット順で使用されますが、た E、H、L、M、P、t、R には、使用 (つまり、1 月 A で、10 月 R)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="7aaa2-501">男女を区別するために女性の誕生日の日に 40 を追加する位置の生年月日の月の日付に対応する 2 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="7aaa2-502">個人の生まれた場所の自治体に特定の市外局番に対応する 4 桁の数字、国全体のコードを使用して外部の国</span><span class="sxs-lookup"><span data-stu-id="7aaa2-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="7aaa2-503">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-504">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-504">Checksum</span></span>

<span data-ttu-id="7aaa2-505">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-506">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-506">Definition</span></span>

<span data-ttu-id="7aaa2-507">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-508">関数`Func_italy_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-509">キーワードの`Keywords_italy_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-510">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-511">関数`Func_italy_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-512">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-512">Keywords</span></span>

#### <a name="keywordsitalyeutaxfilenumber"></a><span data-ttu-id="7aaa2-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-514">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-514">tax number</span></span>
  
<span data-ttu-id="7aaa2-515">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-515">tax no.</span></span>
  
<span data-ttu-id="7aaa2-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-516">taxno#</span></span>
  
<span data-ttu-id="7aaa2-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-517">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-518">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-519">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-519">tax id</span></span>
  
<span data-ttu-id="7aaa2-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-520">taxid#</span></span>
  
<span data-ttu-id="7aaa2-521">会計年度コード</span><span class="sxs-lookup"><span data-stu-id="7aaa2-521">fiscal code</span></span>
  
<span data-ttu-id="7aaa2-522">codice fiscale</span><span class="sxs-lookup"><span data-stu-id="7aaa2-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="7aaa2-523">ラトビア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-524">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-524">Format</span></span>

<span data-ttu-id="7aaa2-525">スペースや区切り文字なしで 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-526">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-526">Pattern</span></span>

<span data-ttu-id="7aaa2-527">指定したパターンに 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="7aaa2-528">生年月日の日付に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="7aaa2-529">生年月日が「0」は、19 世紀に対応して、20 世紀年を「1」に対応して、"2"は、21 世紀の世紀に対応する 1 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="7aaa2-530">4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-531">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-531">Checksum</span></span>

<span data-ttu-id="7aaa2-532">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-533">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-533">Definition</span></span>

<span data-ttu-id="7aaa2-534">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-535">関数`Func_latvia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-536">キーワードの`Keywords_latvia_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-537">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-538">関数`Func_latvia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-539">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-539">Keywords</span></span>

#### <a name="keywordslatviaeutaxfilenumber"></a><span data-ttu-id="7aaa2-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-541">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-541">tax number</span></span>
  
<span data-ttu-id="7aaa2-542">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-542">tax no.</span></span>
  
<span data-ttu-id="7aaa2-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-543">taxno#</span></span>
  
<span data-ttu-id="7aaa2-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-544">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-545">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-546">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-546">tax id</span></span>
  
<span data-ttu-id="7aaa2-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-547">taxid#</span></span>
  
<span data-ttu-id="7aaa2-548">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-548">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-549">税 id が不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-549">tax identification no.</span></span>
  
<span data-ttu-id="7aaa2-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="7aaa2-550">nodokļa numurs</span></span>
  
<span data-ttu-id="7aaa2-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="7aaa2-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="7aaa2-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="7aaa2-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="7aaa2-553">リトアニア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-554">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-554">Format</span></span>

<span data-ttu-id="7aaa2-555">スペースや区切り文字なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-556">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-556">Pattern</span></span>

<span data-ttu-id="7aaa2-557">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-558">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-558">Checksum</span></span>

<span data-ttu-id="7aaa2-559">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-560">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-560">Definition</span></span>

<span data-ttu-id="7aaa2-561">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-562">関数`Func_lithuania_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-563">キーワードの`Keywords_lithuania_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-564">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-565">関数`Func_lithuania_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-566">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-566">Keywords</span></span>

#### <a name="keywordslithuaniaeutaxfilenumber"></a><span data-ttu-id="7aaa2-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-568">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-568">tax number</span></span>
  
<span data-ttu-id="7aaa2-569">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-569">tax no.</span></span>
  
<span data-ttu-id="7aaa2-570">税なしで</span><span class="sxs-lookup"><span data-stu-id="7aaa2-570">tax no#</span></span>
  
<span data-ttu-id="7aaa2-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-571">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-572">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-573">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-573">tax id</span></span>
  
<span data-ttu-id="7aaa2-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-574">taxid#</span></span>
  
<span data-ttu-id="7aaa2-575">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-575">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-576">税 id が不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-576">tax identification no.</span></span>
  
<span data-ttu-id="7aaa2-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-577">mokesčių id</span></span>
  
<span data-ttu-id="7aaa2-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="7aaa2-578">mokesčių numeris</span></span>
  
<span data-ttu-id="7aaa2-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="7aaa2-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="7aaa2-580">ルクセンブルグ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-581">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-581">Format</span></span>

<span data-ttu-id="7aaa2-582">スペースや区切り記号で 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-583">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-583">Pattern</span></span>

<span data-ttu-id="7aaa2-584">13 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-584">13 digits:</span></span>
  
-  <span data-ttu-id="7aaa2-585">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-585">11 digits</span></span> 
    
- <span data-ttu-id="7aaa2-586">2 桁のチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-587">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-587">Checksum</span></span>

<span data-ttu-id="7aaa2-588">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-589">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-589">Definition</span></span>

<span data-ttu-id="7aaa2-590">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-591">関数`Func_luxemburg_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-592">キーワードの`Keywords_luxemburg_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-593">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-594">関数`Func_luxemburg_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-595">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-595">Keywords</span></span>

#### <a name="keywordsluxemburgeutaxfilenumber"></a><span data-ttu-id="7aaa2-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-597">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-597">tax number</span></span>
  
<span data-ttu-id="7aaa2-598">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-598">tax no.</span></span>
  
<span data-ttu-id="7aaa2-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-599">taxno#</span></span>
  
<span data-ttu-id="7aaa2-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-600">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-601">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-602">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-602">tax id</span></span>
  
<span data-ttu-id="7aaa2-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-603">taxid#</span></span>
  
<span data-ttu-id="7aaa2-604">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-604">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-605">税 id が不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-605">tax identification no.</span></span>
  
<span data-ttu-id="7aaa2-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-606">steuernummer</span></span>
  
<span data-ttu-id="7aaa2-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-607">steuer id</span></span>
  
<span data-ttu-id="7aaa2-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="7aaa2-609">マルタ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-610">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-610">Format</span></span>

<span data-ttu-id="7aaa2-611">マルタ籍の人々 の: 7 桁と指定されたパターンの 1 つの文字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="7aaa2-612">マルタ語のない外国人向けのも、マルタ語のエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-613">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-613">Pattern</span></span>

<span data-ttu-id="7aaa2-614">マルタ籍の人々: 7 桁の数字および文字を 1 つ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="7aaa2-615">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-615">Seven digits</span></span> 
    
- <span data-ttu-id="7aaa2-616">1 つの文字 (文字列)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="7aaa2-617">マルタ語のない外国人向けのも、マルタ語のエンティティ: 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="7aaa2-618">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-619">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-619">Checksum</span></span>

<span data-ttu-id="7aaa2-620">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-621">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-621">Definition</span></span>

<span data-ttu-id="7aaa2-622">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-623">関数`Func_malta_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-624">キーワードの`Keywords_malta_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-625">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、65% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-626">関数`Func_malta_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-627">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-627">Keywords</span></span>

#### <a name="keywordsmaltaeutaxfilenumber"></a><span data-ttu-id="7aaa2-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-629">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-629">tax number</span></span>
  
<span data-ttu-id="7aaa2-630">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-630">tax no.</span></span>
  
<span data-ttu-id="7aaa2-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-631">taxno#</span></span>
  
<span data-ttu-id="7aaa2-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-632">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-633">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-634">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-634">tax id</span></span>
  
<span data-ttu-id="7aaa2-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-635">taxid#</span></span>
  
<span data-ttu-id="7aaa2-636">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-636">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-637">税 id が不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-637">tax identification no.</span></span>
  
<span data-ttu-id="7aaa2-638">numru tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="7aaa2-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="7aaa2-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="7aaa2-639">id tat-taxxa</span></span>
  
<span data-ttu-id="7aaa2-640">numru どっち ' identifikazzjoni tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="7aaa2-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="7aaa2-641">オランダ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-642">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-642">Format</span></span>

<span data-ttu-id="7aaa2-643">スペースや区切り文字なしの 9 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-644">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-644">Pattern</span></span>

<span data-ttu-id="7aaa2-645">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-646">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-646">Checksum</span></span>

<span data-ttu-id="7aaa2-647">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-648">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-648">Definition</span></span>

<span data-ttu-id="7aaa2-649">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-650">関数`Func_netherlands_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-651">キーワードの`Keywords_netherlands_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-652">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-653">関数`Func_netherlands_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-654">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-654">Keywords</span></span>

#### <a name="keywordsnetherlandseutaxfilenumber"></a><span data-ttu-id="7aaa2-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-656">オランダ税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="7aaa2-657">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-657">netherlands tax identification</span></span>
  
<span data-ttu-id="7aaa2-658">オランダの税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="7aaa2-659">オランダの税 id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-659">netherland's tax identification</span></span>
  
<span data-ttu-id="7aaa2-660">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-660">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-661">オランダの納税者番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-661">dutch tax id</span></span>
  
<span data-ttu-id="7aaa2-662">オランダ語の税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-662">dutch tax identification number</span></span>
  
<span data-ttu-id="7aaa2-663">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-663">tax id</span></span>
  
<span data-ttu-id="7aaa2-664">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-664">tax id#</span></span>
  
<span data-ttu-id="7aaa2-665">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-665">tax number</span></span>
  
<span data-ttu-id="7aaa2-666">税なしで</span><span class="sxs-lookup"><span data-stu-id="7aaa2-666">tax no#</span></span>
  
<span data-ttu-id="7aaa2-667">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-667">tax#</span></span>
  
<span data-ttu-id="7aaa2-668">tin
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-668">tin</span></span>
  
<span data-ttu-id="7aaa2-669">tin #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-669">tin#</span></span>
  
<span data-ttu-id="7aaa2-670">オランダ tin</span><span class="sxs-lookup"><span data-stu-id="7aaa2-670">netherlands tin</span></span>
  
<span data-ttu-id="7aaa2-671">オランダの tin</span><span class="sxs-lookup"><span data-stu-id="7aaa2-671">netherland's tin</span></span>
  
<span data-ttu-id="7aaa2-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="7aaa2-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="7aaa2-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="7aaa2-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="7aaa2-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="7aaa2-675">nederlands belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="7aaa2-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="7aaa2-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="7aaa2-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="7aaa2-678">ところで nummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-678">btw nummer</span></span>
  
<span data-ttu-id="7aaa2-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="7aaa2-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="7aaa2-680">ポーランド</span><span class="sxs-lookup"><span data-stu-id="7aaa2-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-681">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-681">Format</span></span>

<span data-ttu-id="7aaa2-682">スペースや区切り文字なしで 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-683">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-683">Pattern</span></span>

<span data-ttu-id="7aaa2-684">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-685">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-685">Checksum</span></span>

<span data-ttu-id="7aaa2-686">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-687">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-687">Definition</span></span>

<span data-ttu-id="7aaa2-688">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-689">関数`Func_poland_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-690">キーワードの`Keywords_poland_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-691">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-692">関数`Func_poland_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-693">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-693">Keywords</span></span>

#### <a name="keywordspolandeutaxfilenumber"></a><span data-ttu-id="7aaa2-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-695">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-695">tax number</span></span>
  
<span data-ttu-id="7aaa2-696">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-696">tax no.</span></span>
  
<span data-ttu-id="7aaa2-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-697">taxno#</span></span>
  
<span data-ttu-id="7aaa2-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-698">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-699">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-700">nip</span><span class="sxs-lookup"><span data-stu-id="7aaa2-700">nip</span></span>
  
<span data-ttu-id="7aaa2-701">nip #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-701">nip#</span></span>
  
<span data-ttu-id="7aaa2-702">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-702">tax id</span></span>
  
<span data-ttu-id="7aaa2-703">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-703">tax id#</span></span>
  
<span data-ttu-id="7aaa2-704">nip id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-704">nip id</span></span>
  
<span data-ttu-id="7aaa2-705">nip id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-705">nip id#</span></span>
  
<span data-ttu-id="7aaa2-706">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-706">tax identification number</span></span>
  
<span data-ttu-id="7aaa2-707">税 id が不要です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-707">tax identification no.</span></span>
  
<span data-ttu-id="7aaa2-708">vat 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-708">vat number</span></span>
  
<span data-ttu-id="7aaa2-709">いいえを vat です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-709">vat no.</span></span>
  
<span data-ttu-id="7aaa2-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-710">vatno#</span></span>
  
<span data-ttu-id="7aaa2-711">vat id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-711">vat id</span></span>
  
<span data-ttu-id="7aaa2-712">vat id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-712">vat id#</span></span>
  
<span data-ttu-id="7aaa2-713">数値 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="7aaa2-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="7aaa2-714">polski の数値 identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="7aaa2-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="7aaa2-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="7aaa2-716">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="7aaa2-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-717">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-717">Format</span></span>

<span data-ttu-id="7aaa2-718">スペースや区切り文字なしで 9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-719">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-719">Pattern</span></span>

<span data-ttu-id="7aaa2-720">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-721">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-721">Checksum</span></span>

<span data-ttu-id="7aaa2-722">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-723">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-723">Definition</span></span>

<span data-ttu-id="7aaa2-724">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-725">関数`Func_portugal_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-726">キーワードの`Keywords_portugal_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-727">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-728">関数`Func_portugal_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-729">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-729">Keywords</span></span>

#### <a name="keywordsportugaleutaxfilenumber"></a><span data-ttu-id="7aaa2-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-731">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-731">tax number</span></span>
  
<span data-ttu-id="7aaa2-732">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-732">tax no.</span></span>
  
<span data-ttu-id="7aaa2-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-733">taxno#</span></span>
  
<span data-ttu-id="7aaa2-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-734">taxnumber#</span></span>
  
<span data-ttu-id="7aaa2-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="7aaa2-735">taxnumber</span></span>
  
<span data-ttu-id="7aaa2-736">%n</span><span class="sxs-lookup"><span data-stu-id="7aaa2-736">nif</span></span>
  
<span data-ttu-id="7aaa2-737">%n #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-737">nif#</span></span>
  
<span data-ttu-id="7aaa2-738">会計して</span><span class="sxs-lookup"><span data-stu-id="7aaa2-738">numero fiscal</span></span>
  
<span data-ttu-id="7aaa2-739">número de identificação の会計</span><span class="sxs-lookup"><span data-stu-id="7aaa2-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="7aaa2-740">ルーマニア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-741">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-741">Format</span></span>

<span data-ttu-id="7aaa2-742">スペースや区切り記号で 13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-743">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-743">Pattern</span></span>

<span data-ttu-id="7aaa2-744">13 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-745">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-745">Checksum</span></span>

<span data-ttu-id="7aaa2-746">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-747">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-747">Definition</span></span>

<span data-ttu-id="7aaa2-748">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-749">正規表現`Regex_romania_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-750">キーワードの`Keywords_romania_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-751">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-751">Keywords</span></span>

#### <a name="keywordsromaniaeutaxfilenumber"></a><span data-ttu-id="7aaa2-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-753">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-753">tax id</span></span>
  
<span data-ttu-id="7aaa2-754">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-754">tax id number</span></span>
  
<span data-ttu-id="7aaa2-755">ファイルのない税します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-755">tax file no</span></span>
  
<span data-ttu-id="7aaa2-756">

tax file number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-756">tax file number</span></span>
  
<span data-ttu-id="7aaa2-757">税なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-757">tax no</span></span>
  
<span data-ttu-id="7aaa2-758">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-758">tax number</span></span>
  
<span data-ttu-id="7aaa2-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-759">taxid#</span></span>
  
<span data-ttu-id="7aaa2-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-760">taxno#</span></span>
  
<span data-ttu-id="7aaa2-761">id ul taxei</span><span class="sxs-lookup"><span data-stu-id="7aaa2-761">id-ul taxei</span></span>
  
<span data-ttu-id="7aaa2-762">numărul デ identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="7aaa2-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="7aaa2-763">スロバキア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-764">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-764">Format</span></span>

<span data-ttu-id="7aaa2-765">スペースや区切り文字で 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-766">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-766">Pattern</span></span>

<span data-ttu-id="7aaa2-767">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-768">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-768">Checksum</span></span>

<span data-ttu-id="7aaa2-769">該当なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-770">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-770">Definition</span></span>

<span data-ttu-id="7aaa2-771">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-772">正規表現`Regex_slovakia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-773">キーワードの`Keywords_slovakia_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-774">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-774">Keywords</span></span>

#### <a name="keywordsslovakiaeutaxfilenumber"></a><span data-ttu-id="7aaa2-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-776">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-776">tax id</span></span>
  
<span data-ttu-id="7aaa2-777">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-777">tax id number</span></span>
  
<span data-ttu-id="7aaa2-778">ティン id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-778">tin id</span></span>
  
<span data-ttu-id="7aaa2-779">ティンなし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-779">tin no</span></span>
  
<span data-ttu-id="7aaa2-780">スロバキア語ティン id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-780">slovakian tin id</span></span>
  
<span data-ttu-id="7aaa2-781">tin
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-781">tin</span></span>
  
<span data-ttu-id="7aaa2-782">ファイルのない税します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-782">tax file no</span></span>
  
<span data-ttu-id="7aaa2-783">

tax file number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-783">tax file number</span></span>
  
<span data-ttu-id="7aaa2-784">税なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-784">tax no</span></span>
  
<span data-ttu-id="7aaa2-785">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-785">tax number</span></span>
  
<span data-ttu-id="7aaa2-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-786">taxid#</span></span>
  
<span data-ttu-id="7aaa2-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-787">taxno#</span></span>
  
<span data-ttu-id="7aaa2-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="7aaa2-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="7aaa2-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="7aaa2-789">daňové číslo</span></span>
  
<span data-ttu-id="7aaa2-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="7aaa2-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="7aaa2-791">スロベニア</span><span class="sxs-lookup"><span data-stu-id="7aaa2-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-792">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-792">Format</span></span>

<span data-ttu-id="7aaa2-793">スペースや区切り文字なしで 8 つの数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-794">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-794">Pattern</span></span>

<span data-ttu-id="7aaa2-795">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-796">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-796">Checksum</span></span>

<span data-ttu-id="7aaa2-797">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-798">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-798">Definition</span></span>

<span data-ttu-id="7aaa2-799">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-800">関数`Func_slovenia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-801">キーワードの`Keywords_slovenia_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-802">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-803">関数`Func_slovenia_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-804">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-804">Keywords</span></span>

#### <a name="keywordssloveniaeutaxfilenumber"></a><span data-ttu-id="7aaa2-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-806">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-806">tax id</span></span>
  
<span data-ttu-id="7aaa2-807">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-807">tax id number</span></span>
  
<span data-ttu-id="7aaa2-808">ティン id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-808">tin id</span></span>
  
<span data-ttu-id="7aaa2-809">ティンなし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-809">tin no</span></span>
  
<span data-ttu-id="7aaa2-810">スロベニア語ティン id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-810">slovenian tin id</span></span>
  
<span data-ttu-id="7aaa2-811">tin
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-811">tin</span></span>
  
<span data-ttu-id="7aaa2-812">ファイルのない税します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-812">tax file no</span></span>
  
<span data-ttu-id="7aaa2-813">

tax file number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-813">tax file number</span></span>
  
<span data-ttu-id="7aaa2-814">税なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-814">tax no</span></span>
  
<span data-ttu-id="7aaa2-815">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-815">tax number</span></span>
  
<span data-ttu-id="7aaa2-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-816">taxid#</span></span>
  
<span data-ttu-id="7aaa2-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-817">taxno#</span></span>
  
<span data-ttu-id="7aaa2-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="7aaa2-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="7aaa2-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="7aaa2-819">davčna številka</span></span>
  
<span data-ttu-id="7aaa2-820">Številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="7aaa2-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="7aaa2-821">スペイン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-822">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-822">Format</span></span>

<span data-ttu-id="7aaa2-823">7 または 8 桁の数字と 1 つまたは 2 つの文字を指定したパターンに</span><span class="sxs-lookup"><span data-stu-id="7aaa2-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-824">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-824">Pattern</span></span>

<span data-ttu-id="7aaa2-825">スペイン国内の Id カードを使用して自然なスペイン語の担当者:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="7aaa2-826">8 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-826">Eight digits</span></span> 
    
- <span data-ttu-id="7aaa2-827">大文字を 1 つ (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="7aaa2-828">非居住のスペイン スペイン国内の身分証明書なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="7aaa2-829">大文字"L"(大文字小文字を区別) を 1 つ</span><span class="sxs-lookup"><span data-stu-id="7aaa2-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="7aaa2-830">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-830">Seven digits</span></span>
    
- <span data-ttu-id="7aaa2-831">大文字を 1 つ (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="7aaa2-832">14 年にスペイン国内の Id カードの有効期間] の下のスペインを常駐。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="7aaa2-833">1 つの大文字文字"K"(大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="7aaa2-834">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-834">Seven digits</span></span> 
    
- <span data-ttu-id="7aaa2-835">大文字を 1 つ (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="7aaa2-836">他民族の識別番号を使って他の民族</span><span class="sxs-lookup"><span data-stu-id="7aaa2-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="7aaa2-837">大文字文字"X"、"Y"、または"Z"(大文字小文字を区別) では</span><span class="sxs-lookup"><span data-stu-id="7aaa2-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="7aaa2-838">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-838">Seven digits</span></span>
    
- <span data-ttu-id="7aaa2-839">大文字を 1 つ (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="7aaa2-840">他民族の Id 番号のない他</span><span class="sxs-lookup"><span data-stu-id="7aaa2-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="7aaa2-841">大文字を 1 つは"M"(大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="7aaa2-842">7 桁の数字 </span><span class="sxs-lookup"><span data-stu-id="7aaa2-842">Seven digits</span></span>
    
- <span data-ttu-id="7aaa2-843">大文字を 1 つ (大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-844">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-844">Checksum</span></span>

<span data-ttu-id="7aaa2-845">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-846">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-846">Definition</span></span>

<span data-ttu-id="7aaa2-847">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-848">関数`Func_spain_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-849">キーワードの`Keywords_spain_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-850">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-851">関数`Func_spain_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-852">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-852">Keywords</span></span>

#### <a name="keywordsspaineutaxfilenumber"></a><span data-ttu-id="7aaa2-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-854">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-854">tax id</span></span>
  
<span data-ttu-id="7aaa2-855">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-855">tax id number</span></span>
  
<span data-ttu-id="7aaa2-856">cif id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-856">cif id</span></span>
  
<span data-ttu-id="7aaa2-857">cif なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-857">cif no</span></span>
  
<span data-ttu-id="7aaa2-858">スペイン語の cif id</span><span class="sxs-lookup"><span data-stu-id="7aaa2-858">spanish cif id</span></span>
  
<span data-ttu-id="7aaa2-859">cif</span><span class="sxs-lookup"><span data-stu-id="7aaa2-859">cif</span></span>
  
<span data-ttu-id="7aaa2-860">ファイルのない税します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-860">tax file no</span></span>
  
<span data-ttu-id="7aaa2-861">スペイン語の cif 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-861">spanish cif number</span></span>
  
<span data-ttu-id="7aaa2-862">

tax file number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-862">tax file number</span></span>
  
<span data-ttu-id="7aaa2-863">スペイン語の cif なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-863">spanish cif no</span></span>
  
<span data-ttu-id="7aaa2-864">税なし</span><span class="sxs-lookup"><span data-stu-id="7aaa2-864">tax no</span></span>
  
<span data-ttu-id="7aaa2-865">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-865">tax number</span></span>
  
<span data-ttu-id="7aaa2-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-866">taxid#</span></span>
  
<span data-ttu-id="7aaa2-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-867">taxno#</span></span>
  
<span data-ttu-id="7aaa2-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-868">cifid#</span></span>
  
<span data-ttu-id="7aaa2-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-869">spanishcifid#</span></span>
  
<span data-ttu-id="7aaa2-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-870">spanishcifno#</span></span>
  
<span data-ttu-id="7aaa2-871">número デ contribuyente</span><span class="sxs-lookup"><span data-stu-id="7aaa2-871">número de contribuyente</span></span>
  
<span data-ttu-id="7aaa2-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="7aaa2-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="7aaa2-873">número de identificación の会計</span><span class="sxs-lookup"><span data-stu-id="7aaa2-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="7aaa2-874">cif número</span><span class="sxs-lookup"><span data-stu-id="7aaa2-874">cif número</span></span>
  
<span data-ttu-id="7aaa2-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="7aaa2-876">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-877">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-877">Format</span></span>

<span data-ttu-id="7aaa2-878">10 桁の数字と記号で指定されたパターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-879">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-879">Pattern</span></span>

<span data-ttu-id="7aaa2-880">10 桁の数字および記号。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="7aaa2-881">生年月日 (YYMMDD) に対応する 6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="7aaa2-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="7aaa2-882">プラス記号、マイナス記号、または円記号)</span><span class="sxs-lookup"><span data-stu-id="7aaa2-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="7aaa2-883">Id を構成する 3 桁の数字番号の一意の場所。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="7aaa2-884">1990 年以前に発行された番号の 7 番目と 8 番目の数字は生年月日や foreign-born の人の市区郡を識別します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="7aaa2-885">数字の 9 番目の位置では、男性または女性の場合も、どちらが奇数で性別を示します</span><span class="sxs-lookup"><span data-stu-id="7aaa2-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="7aaa2-886">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="7aaa2-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7aaa2-887">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-887">Checksum</span></span>

<span data-ttu-id="7aaa2-888">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-889">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-889">Definition</span></span>

<span data-ttu-id="7aaa2-890">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-891">関数`Func_sweden_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-892">キーワードの`Keywords_sweden_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="7aaa2-893">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-894">関数`Func_sweden_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-895">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-895">Keywords</span></span>

#### <a name="keywordsswedeneutaxfilenumber"></a><span data-ttu-id="7aaa2-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-897">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-897">tax id</span></span>
  
<span data-ttu-id="7aaa2-898">税 id のないです。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-898">tax id no.</span></span>
  
<span data-ttu-id="7aaa2-899">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-899">tax id number</span></span>
  
<span data-ttu-id="7aaa2-900">tax identification
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-900">tax identification</span></span>
  
<span data-ttu-id="7aaa2-901">税識別番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-901">tax identification#</span></span>
  
<span data-ttu-id="7aaa2-902">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-902">tax no.</span></span>
  
<span data-ttu-id="7aaa2-903">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-903">tax#</span></span>
  
<span data-ttu-id="7aaa2-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-904">taxid#</span></span>
  
<span data-ttu-id="7aaa2-905">税ファイル</span><span class="sxs-lookup"><span data-stu-id="7aaa2-905">tax file</span></span>
  
<span data-ttu-id="7aaa2-906">ファイルのない税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-906">tax file no.</span></span>
  
<span data-ttu-id="7aaa2-907">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-907">personal id number</span></span>
  
<span data-ttu-id="7aaa2-908">skatt id nummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-908">skatt id nummer</span></span>
  
<span data-ttu-id="7aaa2-909">skatt identifikation</span><span class="sxs-lookup"><span data-stu-id="7aaa2-909">skatt identifikation</span></span>
  
<span data-ttu-id="7aaa2-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="7aaa2-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="7aaa2-911">英国</span><span class="sxs-lookup"><span data-stu-id="7aaa2-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="7aaa2-912">形式</span><span class="sxs-lookup"><span data-stu-id="7aaa2-912">Format</span></span>

<span data-ttu-id="7aaa2-913">スペースや区切り記号のない 10 桁の一意な納税者 (UTR) を参照します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="7aaa2-p103">国民保険番号 (NINO): 詳細についてを参照してください「英国国民保険番号 (NINO)」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-p103">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7aaa2-916">パターン</span><span class="sxs-lookup"><span data-stu-id="7aaa2-916">Pattern</span></span>

<span data-ttu-id="7aaa2-917">10 桁の一意な納税者 (UTR) を参照します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="7aaa2-p104">国民保険番号 (NINO): 詳細についてを参照してください「英国国民保険番号 (NINO)」で、[どのような、機密性の高い情報種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-p104">National Insurance Number (NINO): For details, see the section "U.K. National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7aaa2-920">チェックサム</span><span class="sxs-lookup"><span data-stu-id="7aaa2-920">Checksum</span></span>

<span data-ttu-id="7aaa2-921">はい</span><span class="sxs-lookup"><span data-stu-id="7aaa2-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7aaa2-922">定義</span><span class="sxs-lookup"><span data-stu-id="7aaa2-922">Definition</span></span>

<span data-ttu-id="7aaa2-923">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7aaa2-924">関数`Func_uk_eu_tax_file_number`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7aaa2-925">キーワードの`Keywords_uk_eu_tax_file_number`があります。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7aaa2-926">Keywords</span><span class="sxs-lookup"><span data-stu-id="7aaa2-926">Keywords</span></span>

#### <a name="keywordsukeutaxfilenumber"></a><span data-ttu-id="7aaa2-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="7aaa2-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="7aaa2-928">tax id
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-928">tax id</span></span>
  
<span data-ttu-id="7aaa2-929">税 id のないです。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-929">tax id no.</span></span>
  
<span data-ttu-id="7aaa2-930">税 id 番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-930">tax id number</span></span>
  
<span data-ttu-id="7aaa2-931">tax identification
</span><span class="sxs-lookup"><span data-stu-id="7aaa2-931">tax identification</span></span>
  
<span data-ttu-id="7aaa2-932">税識別番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-932">tax identification#</span></span>
  
<span data-ttu-id="7aaa2-933">なしの税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-933">tax no.</span></span>
  
<span data-ttu-id="7aaa2-934">税番号</span><span class="sxs-lookup"><span data-stu-id="7aaa2-934">tax#</span></span>
  
<span data-ttu-id="7aaa2-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="7aaa2-935">taxid#</span></span>
  
<span data-ttu-id="7aaa2-936">税ファイル</span><span class="sxs-lookup"><span data-stu-id="7aaa2-936">tax file</span></span>
  
<span data-ttu-id="7aaa2-937">ファイルのない税です。</span><span class="sxs-lookup"><span data-stu-id="7aaa2-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7aaa2-938">関連項目</span><span class="sxs-lookup"><span data-stu-id="7aaa2-938">See also</span></span>

[<span data-ttu-id="7aaa2-939">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="7aaa2-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

