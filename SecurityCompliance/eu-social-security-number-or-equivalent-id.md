---
title: EU 社会保障番号または同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号または同等の ID の機密情報の種類を検出したときにどのように検索されるかを示します。 この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。
ms.openlocfilehash: c0c808eafa52209c79f3b4e8a2113f587fd8a771
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255555"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="668ea-104">EU 社会保障番号または同等の ID</span><span class="sxs-lookup"><span data-stu-id="668ea-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="668ea-105">このトピックでは、データ損失防止 (DLP) ポリシーが EU 社会保障番号 (SSN) または同等の ID 機密情報の種類を検出したときにどのように検索されるかを示します。</span><span class="sxs-lookup"><span data-stu-id="668ea-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="668ea-106">この機密情報の種類には、国ごとに異なるパターン、キーワード、およびその他の証拠が定義されています。</span><span class="sxs-lookup"><span data-stu-id="668ea-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="668ea-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="668ea-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="668ea-108">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-108">Format</span></span>

<span data-ttu-id="668ea-109">指定した形式の10桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-110">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-110">Pattern</span></span>

<span data-ttu-id="668ea-111">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="668ea-111">10 digits:</span></span>
  
-  <span data-ttu-id="668ea-112">シリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="668ea-113">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="668ea-113">One check digit</span></span>
    
- <span data-ttu-id="668ea-114">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="668ea-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="668ea-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-115">Checksum</span></span>

<span data-ttu-id="668ea-116">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-117">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-117">Definition</span></span>

<span data-ttu-id="668ea-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-119">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-120">from `Keywords_austria_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-122">関数`Func_austria_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-123">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="668ea-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-125">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="668ea-125">social security no</span></span>
  
<span data-ttu-id="668ea-126">social security number</span><span class="sxs-lookup"><span data-stu-id="668ea-126">social security number</span></span>
  
<span data-ttu-id="668ea-127">social security code</span><span class="sxs-lookup"><span data-stu-id="668ea-127">social security code</span></span>
  
<span data-ttu-id="668ea-128">保険番号</span><span class="sxs-lookup"><span data-stu-id="668ea-128">insurance number</span></span>
  
<span data-ttu-id="668ea-129">オーストリア ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-129">austrian ssn</span></span>
  
<span data-ttu-id="668ea-130">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-130">ssn#</span></span>
  
<span data-ttu-id="668ea-131">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-131">ssn</span></span>
  
<span data-ttu-id="668ea-132">保険コード</span><span class="sxs-lookup"><span data-stu-id="668ea-132">insurance code</span></span>
  
<span data-ttu-id="668ea-133">保険コード #</span><span class="sxs-lookup"><span data-stu-id="668ea-133">insurance code#</span></span>
  
<span data-ttu-id="668ea-134">"社会 securityno"</span><span class="sxs-lookup"><span data-stu-id="668ea-134">socialsecurityno#</span></span>
  
<span data-ttu-id="668ea-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="668ea-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="668ea-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="668ea-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="668ea-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="668ea-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="668ea-138">ベルギー</span><span class="sxs-lookup"><span data-stu-id="668ea-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="668ea-139">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-139">Format</span></span>

<span data-ttu-id="668ea-140">11桁の数字 (スペースまたは区切り文字なし)</span><span class="sxs-lookup"><span data-stu-id="668ea-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-141">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-141">Pattern</span></span>

<span data-ttu-id="668ea-142">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="668ea-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-143">Checksum</span></span>

<span data-ttu-id="668ea-144">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-145">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-145">Definition</span></span>

<span data-ttu-id="668ea-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-147">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-148">from `Keywords_belgium_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-149">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-150">関数`Func_belgium_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-151">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="668ea-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-153">ベルギーの国番号</span><span class="sxs-lookup"><span data-stu-id="668ea-153">belgian national number</span></span>
  
<span data-ttu-id="668ea-154">国番号</span><span class="sxs-lookup"><span data-stu-id="668ea-154">national number</span></span>
  
<span data-ttu-id="668ea-155">social security number</span><span class="sxs-lookup"><span data-stu-id="668ea-155">social security number</span></span>
  
<span data-ttu-id="668ea-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-156">nationalnumber#</span></span>
  
<span data-ttu-id="668ea-157">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-157">ssn#</span></span>
  
<span data-ttu-id="668ea-158">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-158">ssn</span></span>
  
<span data-ttu-id="668ea-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="668ea-159">nationalnumber</span></span>
  
<span data-ttu-id="668ea-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="668ea-160">bnn#</span></span>
  
<span data-ttu-id="668ea-161">bnn</span><span class="sxs-lookup"><span data-stu-id="668ea-161">bnn</span></span>
  
<span data-ttu-id="668ea-162">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-162">personal id number</span></span>
  
<span data-ttu-id="668ea-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-163">personalidnumber#</span></span>
  
<span data-ttu-id="668ea-164">numéro national</span><span class="sxs-lookup"><span data-stu-id="668ea-164">numéro national</span></span>
  
<span data-ttu-id="668ea-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="668ea-165">numéro de sécurité</span></span>
  
<span data-ttu-id="668ea-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="668ea-166">numéro d'assuré</span></span>
  
<span data-ttu-id="668ea-167">identifiant national</span><span class="sxs-lookup"><span data-stu-id="668ea-167">identifiant national</span></span>
  
<span data-ttu-id="668ea-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="668ea-168">identifiantnational#</span></span>
  
<span data-ttu-id="668ea-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="668ea-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="668ea-170">クロアチア</span><span class="sxs-lookup"><span data-stu-id="668ea-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="668ea-171">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-171">Format</span></span>

<span data-ttu-id="668ea-172">スペースと区切り文字を含まない11桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-173">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-173">Pattern</span></span>

 <span data-ttu-id="668ea-174">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="668ea-174">11 digits:</span></span> 
  
-  <span data-ttu-id="668ea-175">10桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-175">Ten digits</span></span> 
    
- <span data-ttu-id="668ea-176">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="668ea-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="668ea-177">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-177">Checksum</span></span>

<span data-ttu-id="668ea-178">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-179">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-179">Definition</span></span>

<span data-ttu-id="668ea-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-181">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-182">from `Keywords_croatia_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-184">関数`Func_croatia_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-185">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="668ea-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-187">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="668ea-187">personal identification number</span></span>
  
<span data-ttu-id="668ea-188">マスター市民番号</span><span class="sxs-lookup"><span data-stu-id="668ea-188">master citizen number</span></span>
  
<span data-ttu-id="668ea-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="668ea-189">national identification number</span></span>
  
<span data-ttu-id="668ea-190">social security number</span><span class="sxs-lookup"><span data-stu-id="668ea-190">social security number</span></span>
  
<span data-ttu-id="668ea-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-191">nationalnumber#</span></span>
  
<span data-ttu-id="668ea-192">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-192">ssn#</span></span>
  
<span data-ttu-id="668ea-193">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-193">ssn</span></span>
  
<span data-ttu-id="668ea-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="668ea-194">nationalnumber</span></span>
  
<span data-ttu-id="668ea-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="668ea-195">bnn#</span></span>
  
<span data-ttu-id="668ea-196">bnn</span><span class="sxs-lookup"><span data-stu-id="668ea-196">bnn</span></span>
  
<span data-ttu-id="668ea-197">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-197">personal id number</span></span>
  
<span data-ttu-id="668ea-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-198">personalidnumber#</span></span>
  
<span data-ttu-id="668ea-199">oib</span><span class="sxs-lookup"><span data-stu-id="668ea-199">oib</span></span>
  
<span data-ttu-id="668ea-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="668ea-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="668ea-201">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="668ea-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="668ea-202">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-202">Format</span></span>

<span data-ttu-id="668ea-203">指定したパターンの10桁の数字と円記号</span><span class="sxs-lookup"><span data-stu-id="668ea-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-204">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-204">Pattern</span></span>

<span data-ttu-id="668ea-205">10桁の数字と円記号:</span><span class="sxs-lookup"><span data-stu-id="668ea-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="668ea-206">誕生日に対応する6桁の数字 (yymmdd という):</span><span class="sxs-lookup"><span data-stu-id="668ea-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="668ea-207">円記号</span><span class="sxs-lookup"><span data-stu-id="668ea-207">A backslash</span></span>
    
- <span data-ttu-id="668ea-208">同じ日付で個人の出生を区切るシリアル番号に対応する3桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="668ea-209">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="668ea-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="668ea-210">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-210">Checksum</span></span>

<span data-ttu-id="668ea-211">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-212">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-212">Definition</span></span>

<span data-ttu-id="668ea-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-214">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-215">from `Keywords_czech_republic_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-217">関数`Func_czech_republic_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-218">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="668ea-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-220">出生地番号</span><span class="sxs-lookup"><span data-stu-id="668ea-220">birth number</span></span>
  
<span data-ttu-id="668ea-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="668ea-221">national identification number</span></span>
  
<span data-ttu-id="668ea-222">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="668ea-222">personal identification number</span></span>
  
<span data-ttu-id="668ea-223">social security number</span><span class="sxs-lookup"><span data-stu-id="668ea-223">social security number</span></span>
  
<span data-ttu-id="668ea-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-224">nationalnumber#</span></span>
  
<span data-ttu-id="668ea-225">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-225">ssn#</span></span>
  
<span data-ttu-id="668ea-226">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-226">ssn</span></span>
  
<span data-ttu-id="668ea-227">国番号</span><span class="sxs-lookup"><span data-stu-id="668ea-227">national number</span></span>
  
<span data-ttu-id="668ea-228">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-228">personal id number</span></span>
  
<span data-ttu-id="668ea-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-229">personalidnumber#</span></span>
  
<span data-ttu-id="668ea-230">rč</span><span class="sxs-lookup"><span data-stu-id="668ea-230">rč</span></span>
  
<span data-ttu-id="668ea-231">rodnéčíslo</span><span class="sxs-lookup"><span data-stu-id="668ea-231">rodné číslo</span></span>
  
<span data-ttu-id="668ea-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="668ea-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="668ea-233">デンマーク</span><span class="sxs-lookup"><span data-stu-id="668ea-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="668ea-234">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-234">Format</span></span>

<span data-ttu-id="668ea-235">指定したパターンの10桁の数字とハイフン</span><span class="sxs-lookup"><span data-stu-id="668ea-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-236">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-236">Pattern</span></span>

<span data-ttu-id="668ea-237">10桁の数字とハイフン:</span><span class="sxs-lookup"><span data-stu-id="668ea-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="668ea-238">誕生日に対応する6桁の数字 (ddmmyy)</span><span class="sxs-lookup"><span data-stu-id="668ea-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="668ea-239">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="668ea-239">A hyphen</span></span>
    
- <span data-ttu-id="668ea-240">シーケンス番号に対応する4桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="668ea-241">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-241">Checksum</span></span>

<span data-ttu-id="668ea-242">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-243">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-243">Definition</span></span>

<span data-ttu-id="668ea-244">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-245">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-246">from `Keywords_denmark_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-248">関数`Func_denmark_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-249">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="668ea-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-251">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="668ea-251">personal identification number</span></span>
  
<span data-ttu-id="668ea-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="668ea-252">national identification number</span></span>
  
<span data-ttu-id="668ea-253">social security number</span><span class="sxs-lookup"><span data-stu-id="668ea-253">social security number</span></span>
  
<span data-ttu-id="668ea-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-254">nationalnumber#</span></span>
  
<span data-ttu-id="668ea-255">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-255">ssn#</span></span>
  
<span data-ttu-id="668ea-256">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-256">ssn</span></span>
  
<span data-ttu-id="668ea-257">国番号</span><span class="sxs-lookup"><span data-stu-id="668ea-257">national number</span></span>
  
<span data-ttu-id="668ea-258">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-258">personal id number</span></span>
  
<span data-ttu-id="668ea-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-259">personalidnumber#</span></span>
  
<span data-ttu-id="668ea-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="668ea-260">cpr-nummer</span></span>
  
<span data-ttu-id="668ea-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="668ea-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="668ea-262">フィンランド</span><span class="sxs-lookup"><span data-stu-id="668ea-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="668ea-263">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-263">Format</span></span>

<span data-ttu-id="668ea-264">指定した書式の11文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="668ea-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-265">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-265">Pattern</span></span>

<span data-ttu-id="668ea-266">指定した形式の11文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="668ea-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="668ea-267">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-267">Six digits</span></span> 
    
- <span data-ttu-id="668ea-268">次のいずれかのインスタンス。</span><span class="sxs-lookup"><span data-stu-id="668ea-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="668ea-269">プラス記号</span><span class="sxs-lookup"><span data-stu-id="668ea-269">Plus symbol</span></span>
    
  - <span data-ttu-id="668ea-270">マイナス記号</span><span class="sxs-lookup"><span data-stu-id="668ea-270">Minus symbol</span></span>
    
  - <span data-ttu-id="668ea-271">文字 "A" (大文字と小文字を区別しない)</span><span class="sxs-lookup"><span data-stu-id="668ea-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="668ea-272">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-272">Three digits</span></span>
    
- <span data-ttu-id="668ea-273">1文字または1桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="668ea-274">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-274">Checksum</span></span>

<span data-ttu-id="668ea-275">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-276">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-276">Definition</span></span>

<span data-ttu-id="668ea-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-278">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-279">from `Keywords_finland_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-281">関数`Func_finland_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-282">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="668ea-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-284">identification number</span><span class="sxs-lookup"><span data-stu-id="668ea-284">identification number</span></span>
  
<span data-ttu-id="668ea-285">個人 id</span><span class="sxs-lookup"><span data-stu-id="668ea-285">personal id</span></span>
  
<span data-ttu-id="668ea-286">id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-286">identity number</span></span>
  
<span data-ttu-id="668ea-287">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-287">finnish national id number</span></span>
  
<span data-ttu-id="668ea-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="668ea-288">personalidnumber#</span></span>
  
<span data-ttu-id="668ea-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="668ea-289">national identification number</span></span>
  
<span data-ttu-id="668ea-290">id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-290">id number</span></span>
  
<span data-ttu-id="668ea-291">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-291">national id no.</span></span>
  
<span data-ttu-id="668ea-292">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-292">national id number</span></span>
  
<span data-ttu-id="668ea-293">id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-293">id no</span></span>
  
<span data-ttu-id="668ea-294">tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="668ea-294">tunnistenumero</span></span>
  
<span data-ttu-id="668ea-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="668ea-295">henkilötunnus</span></span>
  
<span data-ttu-id="668ea-296">yksilöllinen henkilökohtainen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="668ea-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="668ea-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="668ea-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="668ea-298">識別子 teetti numero</span><span class="sxs-lookup"><span data-stu-id="668ea-298">identiteetti numero</span></span>
  
<span data-ttu-id="668ea-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="668ea-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="668ea-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="668ea-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="668ea-301">kansallisen tun/st列挙 o</span><span class="sxs-lookup"><span data-stu-id="668ea-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="668ea-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="668ea-302">tunnusnumero</span></span>
  
<span data-ttu-id="668ea-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="668ea-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="668ea-304">hetu</span><span class="sxs-lookup"><span data-stu-id="668ea-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="668ea-305">フランス</span><span class="sxs-lookup"><span data-stu-id="668ea-305">France</span></span>

<span data-ttu-id="668ea-306">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「フランスの社会保障番号 (insee)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="668ea-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="668ea-307">ドイツ</span><span class="sxs-lookup"><span data-stu-id="668ea-307">Germany</span></span>

<span data-ttu-id="668ea-308">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ドイツの id カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="668ea-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="668ea-309">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="668ea-309">Greece</span></span>

<span data-ttu-id="668ea-310">詳細については、「ギリシャの国民 ID カード」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="668ea-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="668ea-311">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="668ea-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="668ea-312">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-312">Format</span></span>

<span data-ttu-id="668ea-313">スペースと区切り文字を含まない9桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-314">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-314">Pattern</span></span>

<span data-ttu-id="668ea-315">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="668ea-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="668ea-316">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-316">Checksum</span></span>

<span data-ttu-id="668ea-317">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-318">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-318">Definition</span></span>

<span data-ttu-id="668ea-319">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-320">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-321">from `Keywords_hungary_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-322">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-323">関数`Func_hungary_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-324">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="668ea-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-326">ハンガリーのソーシャルセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="668ea-326">hungarian social security number</span></span>
  
<span data-ttu-id="668ea-327">social security number</span><span class="sxs-lookup"><span data-stu-id="668ea-327">social security number</span></span>
  
<span data-ttu-id="668ea-328">指定した仮のセキュリティ番号</span><span class="sxs-lookup"><span data-stu-id="668ea-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="668ea-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="668ea-329">hssn#</span></span>
  
<span data-ttu-id="668ea-330">"対話型"</span><span class="sxs-lookup"><span data-stu-id="668ea-330">socialsecuritynno</span></span>
  
<span data-ttu-id="668ea-331">hssn</span><span class="sxs-lookup"><span data-stu-id="668ea-331">hssn</span></span>
  
<span data-ttu-id="668ea-332">taj</span><span class="sxs-lookup"><span data-stu-id="668ea-332">taj</span></span>
  
<span data-ttu-id="668ea-333">taj #</span><span class="sxs-lookup"><span data-stu-id="668ea-333">taj#</span></span>
  
<span data-ttu-id="668ea-334">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-334">ssn</span></span>
  
<span data-ttu-id="668ea-335">ssn</span><span class="sxs-lookup"><span data-stu-id="668ea-335">ssn#</span></span>
  
<span data-ttu-id="668ea-336">ソーシャルセキュリティなし</span><span class="sxs-lookup"><span data-stu-id="668ea-336">social security no</span></span>
  
<span data-ttu-id="668ea-337">áfa</span><span class="sxs-lookup"><span data-stu-id="668ea-337">áfa</span></span>
  
<span data-ttu-id="668ea-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="668ea-338">közösségi adószám</span></span>
  
<span data-ttu-id="668ea-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="668ea-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="668ea-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="668ea-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="668ea-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="668ea-341">áfa szám</span></span>
  
<span data-ttu-id="668ea-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="668ea-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="668ea-343">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="668ea-343">Portugal</span></span>

<span data-ttu-id="668ea-344">詳細については、「[機密情報の種類がどのようなもの](what-the-sensitive-information-types-look-for.md)か」の「ポルトガル市民カード番号」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="668ea-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="668ea-345">スペイン</span><span class="sxs-lookup"><span data-stu-id="668ea-345">Spain</span></span>

<span data-ttu-id="668ea-346">詳細については、「スペインの社会保障番号 (SSN)」の「[機密情報の種類の検索方法](what-the-sensitive-information-types-look-for.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="668ea-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="668ea-347">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="668ea-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="668ea-348">Format</span><span class="sxs-lookup"><span data-stu-id="668ea-348">Format</span></span>

<span data-ttu-id="668ea-349">12桁の数字 (スペースと区切り記号なし)</span><span class="sxs-lookup"><span data-stu-id="668ea-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="668ea-350">パターン</span><span class="sxs-lookup"><span data-stu-id="668ea-350">Pattern</span></span>

<span data-ttu-id="668ea-351">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="668ea-351">12 digits:</span></span>
  
-  <span data-ttu-id="668ea-352">誕生日に対応する8桁の数字 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="668ea-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="668ea-353">次の場合、シリアル番号に対応する3桁の数字です。</span><span class="sxs-lookup"><span data-stu-id="668ea-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="668ea-354">シリアル番号の最後の桁は、男性の場合は奇数、女性の場合は偶数の数字を指定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="668ea-355">1990までの間、シリアル番号 corresponded は、番号のベアラーが生まれたか (1947 以前に作成された場合)、特別なコード (通常は7番目の数字) を使用して、税務レコードに従って、そのユーザーが生活していた市区郡に割り当てられています。immigrants</span><span class="sxs-lookup"><span data-stu-id="668ea-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="668ea-356">1つのチェックディジット</span><span class="sxs-lookup"><span data-stu-id="668ea-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="668ea-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="668ea-357">Checksum</span></span>

<span data-ttu-id="668ea-358">はい</span><span class="sxs-lookup"><span data-stu-id="668ea-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="668ea-359">定義</span><span class="sxs-lookup"><span data-stu-id="668ea-359">Definition</span></span>

<span data-ttu-id="668ea-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-361">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="668ea-362">from `Keywords_sweden_eu_ssn_or_equivalent`キーワードが見つかりました。</span><span class="sxs-lookup"><span data-stu-id="668ea-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="668ea-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="668ea-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="668ea-364">関数`Func_sweden_eu_ssn_or_equivalent`は、パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="668ea-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="668ea-365">キーワード</span><span class="sxs-lookup"><span data-stu-id="668ea-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="668ea-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="668ea-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="668ea-367">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-367">personal id number</span></span>
  
<span data-ttu-id="668ea-368">identification number</span><span class="sxs-lookup"><span data-stu-id="668ea-368">identification number</span></span>
  
<span data-ttu-id="668ea-369">個人 id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-369">personal id no</span></span>
  
<span data-ttu-id="668ea-370">id 番号</span><span class="sxs-lookup"><span data-stu-id="668ea-370">identity no</span></span>
  
<span data-ttu-id="668ea-371">識別番号</span><span class="sxs-lookup"><span data-stu-id="668ea-371">identification no</span></span>
  
<span data-ttu-id="668ea-372">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="668ea-372">personal identification no</span></span>
  
<span data-ttu-id="668ea-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="668ea-373">personnummer id</span></span>
  
<span data-ttu-id="668ea-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="668ea-374">personligt id-nummer</span></span>
  
<span data-ttu-id="668ea-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="668ea-375">unikt id-nummer</span></span>
  
<span data-ttu-id="668ea-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="668ea-376">personnummer</span></span>
  
<span data-ttu-id="668ea-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="668ea-377">identifikationsnumret</span></span>
  
<span data-ttu-id="668ea-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="668ea-378">personnummer#</span></span>
  
<span data-ttu-id="668ea-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="668ea-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="668ea-380">関連項目</span><span class="sxs-lookup"><span data-stu-id="668ea-380">See also</span></span>

[<span data-ttu-id="668ea-381">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="668ea-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

