---
title: EU 社会保障番号または同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号または同等の ID の機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: abcefb6930e9c02d2f32d84b65accfecf1e20d95
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216527"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="bcd95-104">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="bcd95-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="bcd95-p102">このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号 (SSN) または同等の ID 機密情報の種類を検出したときにどのように検索されるかを示します。この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="bcd95-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="bcd95-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="bcd95-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-108">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-108">Format</span></span>

<span data-ttu-id="bcd95-109">指定した形式の10桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-110">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-110">Pattern</span></span>

<span data-ttu-id="bcd95-111">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="bcd95-111">10 digits:</span></span>
  
-  <span data-ttu-id="bcd95-112">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="bcd95-113">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="bcd95-113">One check digit</span></span>
    
- <span data-ttu-id="bcd95-114">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="bcd95-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bcd95-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-115">Checksum</span></span>

<span data-ttu-id="bcd95-116">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-117">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-117">Definition</span></span>

<span data-ttu-id="bcd95-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-119">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-120">from `Keywords_austria_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-122">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-123">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="bcd95-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-125">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="bcd95-125">social security no</span></span>
  
<span data-ttu-id="bcd95-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-126">social security number</span></span>
  
<span data-ttu-id="bcd95-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="bcd95-127">social security code</span></span>
  
<span data-ttu-id="bcd95-128">保険番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-128">insurance number</span></span>
  
<span data-ttu-id="bcd95-129">オーストリア ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-129">austrian ssn</span></span>
  
<span data-ttu-id="bcd95-130">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-130">ssn#</span></span>
  
<span data-ttu-id="bcd95-131">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-131">ssn</span></span>
  
<span data-ttu-id="bcd95-132">保険コード</span><span class="sxs-lookup"><span data-stu-id="bcd95-132">insurance code</span></span>
  
<span data-ttu-id="bcd95-133">保険コード #</span><span class="sxs-lookup"><span data-stu-id="bcd95-133">insurance code#</span></span>
  
<span data-ttu-id="bcd95-134">"社会 securityno"</span><span class="sxs-lookup"><span data-stu-id="bcd95-134">socialsecurityno#</span></span>
  
<span data-ttu-id="bcd95-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="bcd95-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="bcd95-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="bcd95-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="bcd95-138">ベルギー</span><span class="sxs-lookup"><span data-stu-id="bcd95-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-139">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-139">Format</span></span>

<span data-ttu-id="bcd95-140">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="bcd95-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-141">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-141">Pattern</span></span>

<span data-ttu-id="bcd95-142">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="bcd95-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-143">Checksum</span></span>

<span data-ttu-id="bcd95-144">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-145">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-145">Definition</span></span>

<span data-ttu-id="bcd95-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-147">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-148">from `Keywords_belgium_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-149">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-150">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-151">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="bcd95-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-153">ベルギーの国番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-153">belgian national number</span></span>
  
<span data-ttu-id="bcd95-154">国番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-154">national number</span></span>
  
<span data-ttu-id="bcd95-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-155">social security number</span></span>
  
<span data-ttu-id="bcd95-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-156">nationalnumber#</span></span>
  
<span data-ttu-id="bcd95-157">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-157">ssn#</span></span>
  
<span data-ttu-id="bcd95-158">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-158">ssn</span></span>
  
<span data-ttu-id="bcd95-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="bcd95-159">nationalnumber</span></span>
  
<span data-ttu-id="bcd95-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="bcd95-160">bnn#</span></span>
  
<span data-ttu-id="bcd95-161">bnn</span><span class="sxs-lookup"><span data-stu-id="bcd95-161">bnn</span></span>
  
<span data-ttu-id="bcd95-162">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-162">personal id number</span></span>
  
<span data-ttu-id="bcd95-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-163">personalidnumber#</span></span>
  
<span data-ttu-id="bcd95-164">numéro national</span><span class="sxs-lookup"><span data-stu-id="bcd95-164">numéro national</span></span>
  
<span data-ttu-id="bcd95-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="bcd95-165">numéro de sécurité</span></span>
  
<span data-ttu-id="bcd95-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="bcd95-166">numéro d'assuré</span></span>
  
<span data-ttu-id="bcd95-167">identifiant national</span><span class="sxs-lookup"><span data-stu-id="bcd95-167">identifiant national</span></span>
  
<span data-ttu-id="bcd95-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="bcd95-168">identifiantnational#</span></span>
  
<span data-ttu-id="bcd95-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="bcd95-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="bcd95-170">クロアチア</span><span class="sxs-lookup"><span data-stu-id="bcd95-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-171">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-171">Format</span></span>

<span data-ttu-id="bcd95-172">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-173">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-173">Pattern</span></span>

 <span data-ttu-id="bcd95-174">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="bcd95-174">11 digits:</span></span> 
  
-  <span data-ttu-id="bcd95-175">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-175">Ten digits</span></span> 
    
- <span data-ttu-id="bcd95-176">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="bcd95-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bcd95-177">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-177">Checksum</span></span>

<span data-ttu-id="bcd95-178">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-179">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-179">Definition</span></span>

<span data-ttu-id="bcd95-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-181">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-182">from `Keywords_croatia_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-184">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-185">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="bcd95-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-187">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-187">personal identification number</span></span>
  
<span data-ttu-id="bcd95-188">マスター市民番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-188">master citizen number</span></span>
  
<span data-ttu-id="bcd95-189">国別の識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-189">national identification number</span></span>
  
<span data-ttu-id="bcd95-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-190">social security number</span></span>
  
<span data-ttu-id="bcd95-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-191">nationalnumber#</span></span>
  
<span data-ttu-id="bcd95-192">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-192">ssn#</span></span>
  
<span data-ttu-id="bcd95-193">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-193">ssn</span></span>
  
<span data-ttu-id="bcd95-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="bcd95-194">nationalnumber</span></span>
  
<span data-ttu-id="bcd95-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="bcd95-195">bnn#</span></span>
  
<span data-ttu-id="bcd95-196">bnn</span><span class="sxs-lookup"><span data-stu-id="bcd95-196">bnn</span></span>
  
<span data-ttu-id="bcd95-197">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-197">personal id number</span></span>
  
<span data-ttu-id="bcd95-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-198">personalidnumber#</span></span>
  
<span data-ttu-id="bcd95-199">oib</span><span class="sxs-lookup"><span data-stu-id="bcd95-199">oib</span></span>
  
<span data-ttu-id="bcd95-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="bcd95-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="bcd95-201">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="bcd95-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-202">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-202">Format</span></span>

<span data-ttu-id="bcd95-203">指定したパターンの10桁の数字と円記号</span><span class="sxs-lookup"><span data-stu-id="bcd95-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-204">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-204">Pattern</span></span>

<span data-ttu-id="bcd95-205">10桁の数字と円記号:</span><span class="sxs-lookup"><span data-stu-id="bcd95-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="bcd95-206">誕生日に対応する6桁の数字 (yymmdd という):</span><span class="sxs-lookup"><span data-stu-id="bcd95-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="bcd95-207">円記号</span><span class="sxs-lookup"><span data-stu-id="bcd95-207">A backslash</span></span>
    
- <span data-ttu-id="bcd95-208">同じ日付で個人の出生を区切るシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="bcd95-209">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="bcd95-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bcd95-210">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-210">Checksum</span></span>

<span data-ttu-id="bcd95-211">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-212">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-212">Definition</span></span>

<span data-ttu-id="bcd95-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-214">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-215">from `Keywords_czech_republic_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-217">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-218">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="bcd95-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-220">出生地番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-220">birth number</span></span>
  
<span data-ttu-id="bcd95-221">国別の識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-221">national identification number</span></span>
  
<span data-ttu-id="bcd95-222">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-222">personal identification number</span></span>
  
<span data-ttu-id="bcd95-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-223">social security number</span></span>
  
<span data-ttu-id="bcd95-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-224">nationalnumber#</span></span>
  
<span data-ttu-id="bcd95-225">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-225">ssn#</span></span>
  
<span data-ttu-id="bcd95-226">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-226">ssn</span></span>
  
<span data-ttu-id="bcd95-227">国番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-227">national number</span></span>
  
<span data-ttu-id="bcd95-228">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-228">personal id number</span></span>
  
<span data-ttu-id="bcd95-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-229">personalidnumber#</span></span>
  
<span data-ttu-id="bcd95-230">rč</span><span class="sxs-lookup"><span data-stu-id="bcd95-230">rč</span></span>
  
<span data-ttu-id="bcd95-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="bcd95-231">rodné číslo</span></span>
  
<span data-ttu-id="bcd95-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="bcd95-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="bcd95-233">デンマーク</span><span class="sxs-lookup"><span data-stu-id="bcd95-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-234">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-234">Format</span></span>

<span data-ttu-id="bcd95-235">指定したパターンの10桁の数字とハイフン</span><span class="sxs-lookup"><span data-stu-id="bcd95-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-236">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-236">Pattern</span></span>

<span data-ttu-id="bcd95-237">10桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="bcd95-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="bcd95-238">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="bcd95-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="bcd95-239">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="bcd95-239">A hyphen</span></span>
    
- <span data-ttu-id="bcd95-240">シーケンス番号に対応する4桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bcd95-241">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-241">Checksum</span></span>

<span data-ttu-id="bcd95-242">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-243">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-243">Definition</span></span>

<span data-ttu-id="bcd95-244">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-245">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-246">from `Keywords_denmark_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-248">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-249">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="bcd95-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-251">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-251">personal identification number</span></span>
  
<span data-ttu-id="bcd95-252">国別の識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-252">national identification number</span></span>
  
<span data-ttu-id="bcd95-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-253">social security number</span></span>
  
<span data-ttu-id="bcd95-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-254">nationalnumber#</span></span>
  
<span data-ttu-id="bcd95-255">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-255">ssn#</span></span>
  
<span data-ttu-id="bcd95-256">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-256">ssn</span></span>
  
<span data-ttu-id="bcd95-257">国番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-257">national number</span></span>
  
<span data-ttu-id="bcd95-258">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-258">personal id number</span></span>
  
<span data-ttu-id="bcd95-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-259">personalidnumber#</span></span>
  
<span data-ttu-id="bcd95-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-260">cpr-nummer</span></span>
  
<span data-ttu-id="bcd95-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="bcd95-262">フィンランド</span><span class="sxs-lookup"><span data-stu-id="bcd95-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-263">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-263">Format</span></span>

<span data-ttu-id="bcd95-264">指定した書式の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="bcd95-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-265">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-265">Pattern</span></span>

<span data-ttu-id="bcd95-266">指定した形式の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="bcd95-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="bcd95-267">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-267">Six digits</span></span> 
    
- <span data-ttu-id="bcd95-268">次のいずれかのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="bcd95-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="bcd95-269">プラス記号</span><span class="sxs-lookup"><span data-stu-id="bcd95-269">Plus symbol</span></span>
    
  - <span data-ttu-id="bcd95-270">マイナス記号</span><span class="sxs-lookup"><span data-stu-id="bcd95-270">Minus symbol</span></span>
    
  - <span data-ttu-id="bcd95-271">文字 "A" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="bcd95-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="bcd95-272">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-272">Three digits</span></span>
    
- <span data-ttu-id="bcd95-273">1文字または1桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bcd95-274">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-274">Checksum</span></span>

<span data-ttu-id="bcd95-275">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-276">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-276">Definition</span></span>

<span data-ttu-id="bcd95-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-278">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-279">from `Keywords_finland_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-281">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-282">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="bcd95-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-284">identification number</span></span>
  
<span data-ttu-id="bcd95-285">個人 id</span><span class="sxs-lookup"><span data-stu-id="bcd95-285">personal id</span></span>
  
<span data-ttu-id="bcd95-286">id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-286">identity number</span></span>
  
<span data-ttu-id="bcd95-287">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-287">finnish national id number</span></span>
  
<span data-ttu-id="bcd95-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="bcd95-288">personalidnumber#</span></span>
  
<span data-ttu-id="bcd95-289">国別の識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-289">national identification number</span></span>
  
<span data-ttu-id="bcd95-290">id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-290">id number</span></span>
  
<span data-ttu-id="bcd95-291">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-291">national id no.</span></span>
  
<span data-ttu-id="bcd95-292">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-292">national id number</span></span>
  
<span data-ttu-id="bcd95-293">id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-293">id no</span></span>
  
<span data-ttu-id="bcd95-294">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="bcd95-294">tunnistenumero</span></span>
  
<span data-ttu-id="bcd95-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="bcd95-295">henkilötunnus</span></span>
  
<span data-ttu-id="bcd95-296">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="bcd95-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="bcd95-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="bcd95-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="bcd95-298">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="bcd95-298">identiteetti numero</span></span>
  
<span data-ttu-id="bcd95-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="bcd95-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="bcd95-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="bcd95-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="bcd95-301">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="bcd95-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="bcd95-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="bcd95-302">tunnusnumero</span></span>
  
<span data-ttu-id="bcd95-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="bcd95-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="bcd95-304">hetu</span><span class="sxs-lookup"><span data-stu-id="bcd95-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="bcd95-305">フランス</span><span class="sxs-lookup"><span data-stu-id="bcd95-305">France</span></span>

<span data-ttu-id="bcd95-306">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの社会保障番号 (insee)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcd95-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="bcd95-307">ドイツ</span><span class="sxs-lookup"><span data-stu-id="bcd95-307">Germany</span></span>

<span data-ttu-id="bcd95-308">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcd95-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="bcd95-309">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="bcd95-309">Greece</span></span>

<span data-ttu-id="bcd95-310">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcd95-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="bcd95-311">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="bcd95-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-312">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-312">Format</span></span>

<span data-ttu-id="bcd95-313">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-314">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-314">Pattern</span></span>

<span data-ttu-id="bcd95-315">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="bcd95-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="bcd95-316">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-316">Checksum</span></span>

<span data-ttu-id="bcd95-317">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-318">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-318">Definition</span></span>

<span data-ttu-id="bcd95-319">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-320">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-321">from `Keywords_hungary_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-322">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-323">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-324">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="bcd95-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-326">ハンガリーのソーシャルセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-326">hungarian social security number</span></span>
  
<span data-ttu-id="bcd95-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-327">social security number</span></span>
  
<span data-ttu-id="bcd95-328">指定した仮のセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="bcd95-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="bcd95-329">hssn#</span></span>
  
<span data-ttu-id="bcd95-330">"対話型"</span><span class="sxs-lookup"><span data-stu-id="bcd95-330">socialsecuritynno</span></span>
  
<span data-ttu-id="bcd95-331">hssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-331">hssn</span></span>
  
<span data-ttu-id="bcd95-332">taj</span><span class="sxs-lookup"><span data-stu-id="bcd95-332">taj</span></span>
  
<span data-ttu-id="bcd95-333">taj #</span><span class="sxs-lookup"><span data-stu-id="bcd95-333">taj#</span></span>
  
<span data-ttu-id="bcd95-334">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-334">ssn</span></span>
  
<span data-ttu-id="bcd95-335">ssn</span><span class="sxs-lookup"><span data-stu-id="bcd95-335">ssn#</span></span>
  
<span data-ttu-id="bcd95-336">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="bcd95-336">social security no</span></span>
  
<span data-ttu-id="bcd95-337">áfa</span><span class="sxs-lookup"><span data-stu-id="bcd95-337">áfa</span></span>
  
<span data-ttu-id="bcd95-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="bcd95-338">közösségi adószám</span></span>
  
<span data-ttu-id="bcd95-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="bcd95-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="bcd95-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="bcd95-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="bcd95-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="bcd95-341">áfa szám</span></span>
  
<span data-ttu-id="bcd95-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="bcd95-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="bcd95-343">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="bcd95-343">Portugal</span></span>

<span data-ttu-id="bcd95-344">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcd95-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="bcd95-345">スペイン</span><span class="sxs-lookup"><span data-stu-id="bcd95-345">Spain</span></span>

<span data-ttu-id="bcd95-346">詳細については、「スペインの社会保障番号 (SSN)」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bcd95-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="bcd95-347">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="bcd95-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="bcd95-348">形式</span><span class="sxs-lookup"><span data-stu-id="bcd95-348">Format</span></span>

<span data-ttu-id="bcd95-349">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="bcd95-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="bcd95-350">パターン</span><span class="sxs-lookup"><span data-stu-id="bcd95-350">Pattern</span></span>

<span data-ttu-id="bcd95-351">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="bcd95-351">12 digits:</span></span>
  
-  <span data-ttu-id="bcd95-352">誕生日に対応する8桁の数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="bcd95-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="bcd95-353">次の場合、シリアル番号に対応する3桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="bcd95-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="bcd95-354">シリアル番号の最後の桁は、男性の場合は奇数、女性の場合は偶数の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="bcd95-355">1990までの間、シリアル番号 corresponded は、番号のベアラーが生まれたか (1947 以前に作成された場合)、特別なコード (通常は7番目の数字) を使用して、税務レコードに従って、そのユーザーが生活していた市区郡に割り当てられています。immigrants</span><span class="sxs-lookup"><span data-stu-id="bcd95-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="bcd95-356">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="bcd95-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="bcd95-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="bcd95-357">Checksum</span></span>

<span data-ttu-id="bcd95-358">はい</span><span class="sxs-lookup"><span data-stu-id="bcd95-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="bcd95-359">定義</span><span class="sxs-lookup"><span data-stu-id="bcd95-359">Definition</span></span>

<span data-ttu-id="bcd95-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-361">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="bcd95-362">from `Keywords_sweden_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="bcd95-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="bcd95-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="bcd95-364">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bcd95-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="bcd95-365">キーワード</span><span class="sxs-lookup"><span data-stu-id="bcd95-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="bcd95-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="bcd95-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="bcd95-367">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-367">personal id number</span></span>
  
<span data-ttu-id="bcd95-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="bcd95-368">identification number</span></span>
  
<span data-ttu-id="bcd95-369">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-369">personal id no</span></span>
  
<span data-ttu-id="bcd95-370">id 番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-370">identity no</span></span>
  
<span data-ttu-id="bcd95-371">識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-371">identification no</span></span>
  
<span data-ttu-id="bcd95-372">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="bcd95-372">personal identification no</span></span>
  
<span data-ttu-id="bcd95-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="bcd95-373">personnummer id</span></span>
  
<span data-ttu-id="bcd95-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-374">personligt id-nummer</span></span>
  
<span data-ttu-id="bcd95-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-375">unikt id-nummer</span></span>
  
<span data-ttu-id="bcd95-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="bcd95-376">personnummer</span></span>
  
<span data-ttu-id="bcd95-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="bcd95-377">identifikationsnumret</span></span>
  
<span data-ttu-id="bcd95-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="bcd95-378">personnummer#</span></span>
  
<span data-ttu-id="bcd95-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="bcd95-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bcd95-380">関連項目</span><span class="sxs-lookup"><span data-stu-id="bcd95-380">See also</span></span>

[<span data-ttu-id="bcd95-381">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="bcd95-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

