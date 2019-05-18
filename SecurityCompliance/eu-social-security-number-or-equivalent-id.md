---
title: EU 社会保障番号または同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号または同等の ID の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154489"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="d0837-104">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="d0837-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="d0837-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号 (SSN) または同等の ID 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="d0837-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="d0837-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="d0837-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="d0837-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="d0837-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="d0837-108">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-108">Format</span></span>

<span data-ttu-id="d0837-109">指定した形式の10桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-110">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-110">Pattern</span></span>

<span data-ttu-id="d0837-111">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="d0837-111">10 digits:</span></span>
  
-  <span data-ttu-id="d0837-112">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="d0837-113">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="d0837-113">One check digit</span></span>
    
- <span data-ttu-id="d0837-114">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="d0837-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d0837-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-115">Checksum</span></span>

<span data-ttu-id="d0837-116">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-117">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-117">Definition</span></span>

<span data-ttu-id="d0837-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-119">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-120">From `Keywords_austria_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-122">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-123">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="d0837-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-125">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="d0837-125">social security no</span></span>
  
<span data-ttu-id="d0837-126">social security number</span><span class="sxs-lookup"><span data-stu-id="d0837-126">social security number</span></span>
  
<span data-ttu-id="d0837-127">social security code</span><span class="sxs-lookup"><span data-stu-id="d0837-127">social security code</span></span>
  
<span data-ttu-id="d0837-128">保険番号</span><span class="sxs-lookup"><span data-stu-id="d0837-128">insurance number</span></span>
  
<span data-ttu-id="d0837-129">オーストリア ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-129">austrian ssn</span></span>
  
<span data-ttu-id="d0837-130">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-130">ssn#</span></span>
  
<span data-ttu-id="d0837-131">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-131">ssn</span></span>
  
<span data-ttu-id="d0837-132">保険コード</span><span class="sxs-lookup"><span data-stu-id="d0837-132">insurance code</span></span>
  
<span data-ttu-id="d0837-133">保険コード #</span><span class="sxs-lookup"><span data-stu-id="d0837-133">insurance code#</span></span>
  
<span data-ttu-id="d0837-134">"社会 securityno"</span><span class="sxs-lookup"><span data-stu-id="d0837-134">socialsecurityno#</span></span>
  
<span data-ttu-id="d0837-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0837-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="d0837-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="d0837-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="d0837-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="d0837-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="d0837-138">ベルギー</span><span class="sxs-lookup"><span data-stu-id="d0837-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="d0837-139">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-139">Format</span></span>

<span data-ttu-id="d0837-140">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="d0837-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-141">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-141">Pattern</span></span>

<span data-ttu-id="d0837-142">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d0837-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-143">Checksum</span></span>

<span data-ttu-id="d0837-144">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-145">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-145">Definition</span></span>

<span data-ttu-id="d0837-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-147">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-148">From `Keywords_belgium_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-149">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-150">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-151">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="d0837-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-153">ベルギーの国番号</span><span class="sxs-lookup"><span data-stu-id="d0837-153">belgian national number</span></span>
  
<span data-ttu-id="d0837-154">国番号</span><span class="sxs-lookup"><span data-stu-id="d0837-154">national number</span></span>
  
<span data-ttu-id="d0837-155">social security number</span><span class="sxs-lookup"><span data-stu-id="d0837-155">social security number</span></span>
  
<span data-ttu-id="d0837-156">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-156">nationalnumber#</span></span>
  
<span data-ttu-id="d0837-157">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-157">ssn#</span></span>
  
<span data-ttu-id="d0837-158">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-158">ssn</span></span>
  
<span data-ttu-id="d0837-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d0837-159">nationalnumber</span></span>
  
<span data-ttu-id="d0837-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="d0837-160">bnn#</span></span>
  
<span data-ttu-id="d0837-161">bnn</span><span class="sxs-lookup"><span data-stu-id="d0837-161">bnn</span></span>
  
<span data-ttu-id="d0837-162">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-162">personal id number</span></span>
  
<span data-ttu-id="d0837-163">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-163">personalidnumber#</span></span>
  
<span data-ttu-id="d0837-164">numéro national</span><span class="sxs-lookup"><span data-stu-id="d0837-164">numéro national</span></span>
  
<span data-ttu-id="d0837-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="d0837-165">numéro de sécurité</span></span>
  
<span data-ttu-id="d0837-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="d0837-166">numéro d'assuré</span></span>
  
<span data-ttu-id="d0837-167">identifiant national</span><span class="sxs-lookup"><span data-stu-id="d0837-167">identifiant national</span></span>
  
<span data-ttu-id="d0837-168">identifiantnational#</span><span class="sxs-lookup"><span data-stu-id="d0837-168">identifiantnational#</span></span>
  
<span data-ttu-id="d0837-169">numéronational#</span><span class="sxs-lookup"><span data-stu-id="d0837-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="d0837-170">クロアチア</span><span class="sxs-lookup"><span data-stu-id="d0837-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="d0837-171">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-171">Format</span></span>

<span data-ttu-id="d0837-172">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-173">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-173">Pattern</span></span>

 <span data-ttu-id="d0837-174">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="d0837-174">11 digits:</span></span> 
  
-  <span data-ttu-id="d0837-175">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-175">Ten digits</span></span> 
    
- <span data-ttu-id="d0837-176">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="d0837-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d0837-177">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-177">Checksum</span></span>

<span data-ttu-id="d0837-178">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-179">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-179">Definition</span></span>

<span data-ttu-id="d0837-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-181">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-182">From `Keywords_croatia_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-184">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-185">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="d0837-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-187">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="d0837-187">personal identification number</span></span>
  
<span data-ttu-id="d0837-188">マスター市民番号</span><span class="sxs-lookup"><span data-stu-id="d0837-188">master citizen number</span></span>
  
<span data-ttu-id="d0837-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="d0837-189">national identification number</span></span>
  
<span data-ttu-id="d0837-190">social security number</span><span class="sxs-lookup"><span data-stu-id="d0837-190">social security number</span></span>
  
<span data-ttu-id="d0837-191">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-191">nationalnumber#</span></span>
  
<span data-ttu-id="d0837-192">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-192">ssn#</span></span>
  
<span data-ttu-id="d0837-193">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-193">ssn</span></span>
  
<span data-ttu-id="d0837-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="d0837-194">nationalnumber</span></span>
  
<span data-ttu-id="d0837-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="d0837-195">bnn#</span></span>
  
<span data-ttu-id="d0837-196">bnn</span><span class="sxs-lookup"><span data-stu-id="d0837-196">bnn</span></span>
  
<span data-ttu-id="d0837-197">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-197">personal id number</span></span>
  
<span data-ttu-id="d0837-198">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-198">personalidnumber#</span></span>
  
<span data-ttu-id="d0837-199">oib</span><span class="sxs-lookup"><span data-stu-id="d0837-199">oib</span></span>
  
<span data-ttu-id="d0837-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="d0837-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="d0837-201">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="d0837-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="d0837-202">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-202">Format</span></span>

<span data-ttu-id="d0837-203">指定したパターンの10桁の数字と円記号</span><span class="sxs-lookup"><span data-stu-id="d0837-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-204">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-204">Pattern</span></span>

<span data-ttu-id="d0837-205">10桁の数字と円記号:</span><span class="sxs-lookup"><span data-stu-id="d0837-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="d0837-206">誕生日に対応する6桁の数字 (YYMMDD という):</span><span class="sxs-lookup"><span data-stu-id="d0837-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="d0837-207">円記号</span><span class="sxs-lookup"><span data-stu-id="d0837-207">A backslash</span></span>
    
- <span data-ttu-id="d0837-208">同じ日付で個人の出生を区切るシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="d0837-209">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="d0837-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d0837-210">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-210">Checksum</span></span>

<span data-ttu-id="d0837-211">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-212">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-212">Definition</span></span>

<span data-ttu-id="d0837-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-214">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-215">From `Keywords_czech_republic_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-217">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-218">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="d0837-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-220">出生地番号</span><span class="sxs-lookup"><span data-stu-id="d0837-220">birth number</span></span>
  
<span data-ttu-id="d0837-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="d0837-221">national identification number</span></span>
  
<span data-ttu-id="d0837-222">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="d0837-222">personal identification number</span></span>
  
<span data-ttu-id="d0837-223">social security number</span><span class="sxs-lookup"><span data-stu-id="d0837-223">social security number</span></span>
  
<span data-ttu-id="d0837-224">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-224">nationalnumber#</span></span>
  
<span data-ttu-id="d0837-225">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-225">ssn#</span></span>
  
<span data-ttu-id="d0837-226">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-226">ssn</span></span>
  
<span data-ttu-id="d0837-227">国番号</span><span class="sxs-lookup"><span data-stu-id="d0837-227">national number</span></span>
  
<span data-ttu-id="d0837-228">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-228">personal id number</span></span>
  
<span data-ttu-id="d0837-229">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-229">personalidnumber#</span></span>
  
<span data-ttu-id="d0837-230">rč</span><span class="sxs-lookup"><span data-stu-id="d0837-230">rč</span></span>
  
<span data-ttu-id="d0837-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="d0837-231">rodné číslo</span></span>
  
<span data-ttu-id="d0837-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="d0837-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="d0837-233">デンマーク</span><span class="sxs-lookup"><span data-stu-id="d0837-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="d0837-234">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-234">Format</span></span>

<span data-ttu-id="d0837-235">指定したパターンの10桁の数字とハイフン</span><span class="sxs-lookup"><span data-stu-id="d0837-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-236">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-236">Pattern</span></span>

<span data-ttu-id="d0837-237">10桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="d0837-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="d0837-238">誕生日に対応する6桁の数字 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="d0837-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="d0837-239">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="d0837-239">A hyphen</span></span>
    
- <span data-ttu-id="d0837-240">シーケンス番号に対応する4桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d0837-241">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-241">Checksum</span></span>

<span data-ttu-id="d0837-242">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-243">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-243">Definition</span></span>

<span data-ttu-id="d0837-244">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-245">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-246">From `Keywords_denmark_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-248">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-249">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="d0837-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-251">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="d0837-251">personal identification number</span></span>
  
<span data-ttu-id="d0837-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="d0837-252">national identification number</span></span>
  
<span data-ttu-id="d0837-253">social security number</span><span class="sxs-lookup"><span data-stu-id="d0837-253">social security number</span></span>
  
<span data-ttu-id="d0837-254">nationalnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-254">nationalnumber#</span></span>
  
<span data-ttu-id="d0837-255">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-255">ssn#</span></span>
  
<span data-ttu-id="d0837-256">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-256">ssn</span></span>
  
<span data-ttu-id="d0837-257">国番号</span><span class="sxs-lookup"><span data-stu-id="d0837-257">national number</span></span>
  
<span data-ttu-id="d0837-258">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-258">personal id number</span></span>
  
<span data-ttu-id="d0837-259">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-259">personalidnumber#</span></span>
  
<span data-ttu-id="d0837-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="d0837-260">cpr-nummer</span></span>
  
<span data-ttu-id="d0837-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="d0837-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="d0837-262">フィンランド</span><span class="sxs-lookup"><span data-stu-id="d0837-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="d0837-263">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-263">Format</span></span>

<span data-ttu-id="d0837-264">指定した書式の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="d0837-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-265">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-265">Pattern</span></span>

<span data-ttu-id="d0837-266">指定した形式の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="d0837-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="d0837-267">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-267">Six digits</span></span> 
    
- <span data-ttu-id="d0837-268">次のいずれかのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="d0837-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="d0837-269">プラス記号</span><span class="sxs-lookup"><span data-stu-id="d0837-269">Plus symbol</span></span>
    
  - <span data-ttu-id="d0837-270">マイナス記号</span><span class="sxs-lookup"><span data-stu-id="d0837-270">Minus symbol</span></span>
    
  - <span data-ttu-id="d0837-271">文字 "A" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="d0837-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="d0837-272">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-272">Three digits</span></span>
    
- <span data-ttu-id="d0837-273">1文字または1桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d0837-274">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-274">Checksum</span></span>

<span data-ttu-id="d0837-275">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-276">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-276">Definition</span></span>

<span data-ttu-id="d0837-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-278">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-279">From `Keywords_finland_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-281">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-282">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="d0837-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-284">identification number</span><span class="sxs-lookup"><span data-stu-id="d0837-284">identification number</span></span>
  
<span data-ttu-id="d0837-285">個人 id</span><span class="sxs-lookup"><span data-stu-id="d0837-285">personal id</span></span>
  
<span data-ttu-id="d0837-286">id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-286">identity number</span></span>
  
<span data-ttu-id="d0837-287">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-287">finnish national id number</span></span>
  
<span data-ttu-id="d0837-288">personalidnumber#</span><span class="sxs-lookup"><span data-stu-id="d0837-288">personalidnumber#</span></span>
  
<span data-ttu-id="d0837-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="d0837-289">national identification number</span></span>
  
<span data-ttu-id="d0837-290">id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-290">id number</span></span>
  
<span data-ttu-id="d0837-291">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-291">national id no.</span></span>
  
<span data-ttu-id="d0837-292">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-292">national id number</span></span>
  
<span data-ttu-id="d0837-293">id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-293">id no</span></span>
  
<span data-ttu-id="d0837-294">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="d0837-294">tunnistenumero</span></span>
  
<span data-ttu-id="d0837-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="d0837-295">henkilötunnus</span></span>
  
<span data-ttu-id="d0837-296">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="d0837-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="d0837-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="d0837-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="d0837-298">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="d0837-298">identiteetti numero</span></span>
  
<span data-ttu-id="d0837-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="d0837-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="d0837-300">henkilötunnusnumero#</span><span class="sxs-lookup"><span data-stu-id="d0837-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="d0837-301">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="d0837-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="d0837-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="d0837-302">tunnusnumero</span></span>
  
<span data-ttu-id="d0837-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="d0837-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="d0837-304">hetu</span><span class="sxs-lookup"><span data-stu-id="d0837-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="d0837-305">フランス</span><span class="sxs-lookup"><span data-stu-id="d0837-305">France</span></span>

<span data-ttu-id="d0837-306">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの社会保障番号 (insee)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0837-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="d0837-307">ドイツ</span><span class="sxs-lookup"><span data-stu-id="d0837-307">Germany</span></span>

<span data-ttu-id="d0837-308">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの Id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0837-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="d0837-309">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="d0837-309">Greece</span></span>

<span data-ttu-id="d0837-310">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0837-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="d0837-311">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="d0837-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="d0837-312">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-312">Format</span></span>

<span data-ttu-id="d0837-313">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-314">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-314">Pattern</span></span>

<span data-ttu-id="d0837-315">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="d0837-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="d0837-316">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-316">Checksum</span></span>

<span data-ttu-id="d0837-317">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-318">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-318">Definition</span></span>

<span data-ttu-id="d0837-319">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-320">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-321">From `Keywords_hungary_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-322">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-323">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-324">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="d0837-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-326">ハンガリーのソーシャルセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="d0837-326">hungarian social security number</span></span>
  
<span data-ttu-id="d0837-327">social security number</span><span class="sxs-lookup"><span data-stu-id="d0837-327">social security number</span></span>
  
<span data-ttu-id="d0837-328">指定した仮のセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="d0837-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="d0837-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="d0837-329">hssn#</span></span>
  
<span data-ttu-id="d0837-330">"対話型"</span><span class="sxs-lookup"><span data-stu-id="d0837-330">socialsecuritynno</span></span>
  
<span data-ttu-id="d0837-331">hssn</span><span class="sxs-lookup"><span data-stu-id="d0837-331">hssn</span></span>
  
<span data-ttu-id="d0837-332">taj</span><span class="sxs-lookup"><span data-stu-id="d0837-332">taj</span></span>
  
<span data-ttu-id="d0837-333">taj #</span><span class="sxs-lookup"><span data-stu-id="d0837-333">taj#</span></span>
  
<span data-ttu-id="d0837-334">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-334">ssn</span></span>
  
<span data-ttu-id="d0837-335">ssn</span><span class="sxs-lookup"><span data-stu-id="d0837-335">ssn#</span></span>
  
<span data-ttu-id="d0837-336">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="d0837-336">social security no</span></span>
  
<span data-ttu-id="d0837-337">áfa</span><span class="sxs-lookup"><span data-stu-id="d0837-337">áfa</span></span>
  
<span data-ttu-id="d0837-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="d0837-338">közösségi adószám</span></span>
  
<span data-ttu-id="d0837-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="d0837-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="d0837-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="d0837-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="d0837-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="d0837-341">áfa szám</span></span>
  
<span data-ttu-id="d0837-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="d0837-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="d0837-343">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="d0837-343">Portugal</span></span>

<span data-ttu-id="d0837-344">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0837-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="d0837-345">スペイン</span><span class="sxs-lookup"><span data-stu-id="d0837-345">Spain</span></span>

<span data-ttu-id="d0837-346">詳細については、「スペインの社会保障番号 (SSN)」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0837-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="d0837-347">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="d0837-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="d0837-348">Format</span><span class="sxs-lookup"><span data-stu-id="d0837-348">Format</span></span>

<span data-ttu-id="d0837-349">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="d0837-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="d0837-350">パターン</span><span class="sxs-lookup"><span data-stu-id="d0837-350">Pattern</span></span>

<span data-ttu-id="d0837-351">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="d0837-351">12 digits:</span></span>
  
-  <span data-ttu-id="d0837-352">誕生日に対応する8桁の数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="d0837-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="d0837-353">次の場合、シリアル番号に対応する3桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="d0837-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="d0837-354">シリアル番号の最後の桁は、男性の場合は奇数、女性の場合は偶数の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="d0837-355">1990までの間、シリアル番号 corresponded は、番号のベアラーが生まれたか (1947 以前に作成された場合)、特別なコード (通常は7番目の数字) を使用して、税務1947レコードに従って、そのユーザーが生活していた市区郡に割り当てられています。immigrants</span><span class="sxs-lookup"><span data-stu-id="d0837-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="d0837-356">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="d0837-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="d0837-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="d0837-357">Checksum</span></span>

<span data-ttu-id="d0837-358">はい</span><span class="sxs-lookup"><span data-stu-id="d0837-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="d0837-359">定義</span><span class="sxs-lookup"><span data-stu-id="d0837-359">Definition</span></span>

<span data-ttu-id="d0837-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-361">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="d0837-362">From `Keywords_sweden_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="d0837-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="d0837-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="d0837-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="d0837-364">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="d0837-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="d0837-365">キーワード</span><span class="sxs-lookup"><span data-stu-id="d0837-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="d0837-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="d0837-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="d0837-367">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-367">personal id number</span></span>
  
<span data-ttu-id="d0837-368">identification number</span><span class="sxs-lookup"><span data-stu-id="d0837-368">identification number</span></span>
  
<span data-ttu-id="d0837-369">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-369">personal id no</span></span>
  
<span data-ttu-id="d0837-370">id 番号</span><span class="sxs-lookup"><span data-stu-id="d0837-370">identity no</span></span>
  
<span data-ttu-id="d0837-371">識別番号</span><span class="sxs-lookup"><span data-stu-id="d0837-371">identification no</span></span>
  
<span data-ttu-id="d0837-372">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="d0837-372">personal identification no</span></span>
  
<span data-ttu-id="d0837-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="d0837-373">personnummer id</span></span>
  
<span data-ttu-id="d0837-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="d0837-374">personligt id-nummer</span></span>
  
<span data-ttu-id="d0837-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="d0837-375">unikt id-nummer</span></span>
  
<span data-ttu-id="d0837-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="d0837-376">personnummer</span></span>
  
<span data-ttu-id="d0837-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="d0837-377">identifikationsnumret</span></span>
  
<span data-ttu-id="d0837-378">personnummer#</span><span class="sxs-lookup"><span data-stu-id="d0837-378">personnummer#</span></span>
  
<span data-ttu-id="d0837-379">identifikationsnumret#</span><span class="sxs-lookup"><span data-stu-id="d0837-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d0837-380">関連項目</span><span class="sxs-lookup"><span data-stu-id="d0837-380">See also</span></span>

[<span data-ttu-id="d0837-381">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="d0837-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

