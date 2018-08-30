---
title: EU の社会保障番号またはそれと同等の ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.assetid: 1fabd341-e594-4bfe-961c-62aa82893f60
description: このトピックでは、どのようなデータ損失防止 (DLP) ポリシーを検索、機密性の高い情報の種類として [EU の社会保障番号または同等の ID を検出したときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。
ms.openlocfilehash: 6f1027dcfb648ed937b8180d74d4bc6348dab650
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532030"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="9e9d2-104">EU の社会保障番号またはそれと同等の ID</span><span class="sxs-lookup"><span data-stu-id="9e9d2-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="9e9d2-p102">このトピックでは、どのようなデータ損失防止 (DLP) ポリシーを検索、機密性の高い情報の種類として [EU の社会保障番号 (SSN) または同等の ID を検出したときを示します。この機密性の高い情報の種類は、さまざまなパターン、キーワード、および各都道府県の他の証拠を定義します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-p102">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type. This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="9e9d2-107">オーストリア</span><span class="sxs-lookup"><span data-stu-id="9e9d2-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-108">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-108">Format</span></span>

<span data-ttu-id="9e9d2-109">指定した形式で 10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-110">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-110">Pattern</span></span>

<span data-ttu-id="9e9d2-111">10 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9e9d2-111">10 digits:</span></span>
  
-  <span data-ttu-id="9e9d2-112">シリアル番号に対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="9e9d2-113">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="9e9d2-113">One check digit</span></span>
    
- <span data-ttu-id="9e9d2-114">6 桁の数字が日付の生年月日に対応します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e9d2-115">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-115">Checksum</span></span>

<span data-ttu-id="9e9d2-116">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-117">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-117">Definition</span></span>

<span data-ttu-id="9e9d2-118">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-119">関数`Func_austria_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-120">キーワードの`Keywords_austria_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-121">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-122">関数`Func_austria_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-123">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-123">Keywords</span></span>

#### <a name="keywordsaustriaeussnorequivalent"></a><span data-ttu-id="9e9d2-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-125">社会保険なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-125">social security no</span></span>
  
<span data-ttu-id="9e9d2-126">social security number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-126">social security number</span></span>
  
<span data-ttu-id="9e9d2-127">
social security code</span><span class="sxs-lookup"><span data-stu-id="9e9d2-127">social security code</span></span>
  
<span data-ttu-id="9e9d2-128">保険番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-128">insurance number</span></span>
  
<span data-ttu-id="9e9d2-129">オーストリア ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-129">austrian ssn</span></span>
  
<span data-ttu-id="9e9d2-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-130">ssn#</span></span>
  
<span data-ttu-id="9e9d2-131">ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-131">ssn</span></span>
  
<span data-ttu-id="9e9d2-132">保険コード</span><span class="sxs-lookup"><span data-stu-id="9e9d2-132">insurance code</span></span>
  
<span data-ttu-id="9e9d2-133">保険コード番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-133">insurance code#</span></span>
  
<span data-ttu-id="9e9d2-134">socialsecurityno #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-134">socialsecurityno#</span></span>
  
<span data-ttu-id="9e9d2-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="9e9d2-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="9e9d2-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="9e9d2-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="9e9d2-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="9e9d2-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="9e9d2-138">ベルギー</span><span class="sxs-lookup"><span data-stu-id="9e9d2-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-139">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-139">Format</span></span>

<span data-ttu-id="9e9d2-140">スペースや区切り文字なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-141">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-141">Pattern</span></span>

<span data-ttu-id="9e9d2-142">11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e9d2-143">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-143">Checksum</span></span>

<span data-ttu-id="9e9d2-144">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-145">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-145">Definition</span></span>

<span data-ttu-id="9e9d2-146">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-147">関数`Func_belgium_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-148">キーワードの`Keywords_belgium_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-149">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-150">関数`Func_belgium_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-151">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-151">Keywords</span></span>

#### <a name="keywordsbelgiumeussnorequivalent"></a><span data-ttu-id="9e9d2-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-153">ベルギーの国番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-153">belgian national number</span></span>
  
<span data-ttu-id="9e9d2-154">国番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-154">national number</span></span>
  
<span data-ttu-id="9e9d2-155">social security number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-155">social security number</span></span>
  
<span data-ttu-id="9e9d2-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-156">nationalnumber#</span></span>
  
<span data-ttu-id="9e9d2-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-157">ssn#</span></span>
  
<span data-ttu-id="9e9d2-158">ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-158">ssn</span></span>
  
<span data-ttu-id="9e9d2-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="9e9d2-159">nationalnumber</span></span>
  
<span data-ttu-id="9e9d2-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-160">bnn#</span></span>
  
<span data-ttu-id="9e9d2-161">bnn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-161">bnn</span></span>
  
<span data-ttu-id="9e9d2-162">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-162">personal id number</span></span>
  
<span data-ttu-id="9e9d2-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-163">personalidnumber#</span></span>
  
<span data-ttu-id="9e9d2-164">numéro 国立</span><span class="sxs-lookup"><span data-stu-id="9e9d2-164">numéro national</span></span>
  
<span data-ttu-id="9e9d2-165">numéro de sécurité
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-165">numéro de sécurité</span></span>
  
<span data-ttu-id="9e9d2-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="9e9d2-166">numéro d'assuré</span></span>
  
<span data-ttu-id="9e9d2-167">国内 identifiant</span><span class="sxs-lookup"><span data-stu-id="9e9d2-167">identifiant national</span></span>
  
<span data-ttu-id="9e9d2-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-168">identifiantnational#</span></span>
  
<span data-ttu-id="9e9d2-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="9e9d2-170">クロアチア</span><span class="sxs-lookup"><span data-stu-id="9e9d2-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-171">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-171">Format</span></span>

<span data-ttu-id="9e9d2-172">スペースや区切り記号なし 11 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-173">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-173">Pattern</span></span>

 <span data-ttu-id="9e9d2-174">11 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9e9d2-174">11 digits:</span></span> 
  
-  <span data-ttu-id="9e9d2-175">10 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-175">Ten digits</span></span> 
    
- <span data-ttu-id="9e9d2-176">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="9e9d2-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e9d2-177">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-177">Checksum</span></span>

<span data-ttu-id="9e9d2-178">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-179">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-179">Definition</span></span>

<span data-ttu-id="9e9d2-180">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-181">関数`Func_croatia_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-182">キーワードの`Keywords_croatia_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-183">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-184">関数`Func_croatia_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-185">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-185">Keywords</span></span>

#### <a name="keywordscroatiaeussnorequivalent"></a><span data-ttu-id="9e9d2-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-187">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-187">personal identification number</span></span>
  
<span data-ttu-id="9e9d2-188">マスターの市民数</span><span class="sxs-lookup"><span data-stu-id="9e9d2-188">master citizen number</span></span>
  
<span data-ttu-id="9e9d2-189">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-189">national identification number</span></span>
  
<span data-ttu-id="9e9d2-190">social security number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-190">social security number</span></span>
  
<span data-ttu-id="9e9d2-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-191">nationalnumber#</span></span>
  
<span data-ttu-id="9e9d2-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-192">ssn#</span></span>
  
<span data-ttu-id="9e9d2-193">ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-193">ssn</span></span>
  
<span data-ttu-id="9e9d2-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="9e9d2-194">nationalnumber</span></span>
  
<span data-ttu-id="9e9d2-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-195">bnn#</span></span>
  
<span data-ttu-id="9e9d2-196">bnn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-196">bnn</span></span>
  
<span data-ttu-id="9e9d2-197">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-197">personal id number</span></span>
  
<span data-ttu-id="9e9d2-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-198">personalidnumber#</span></span>
  
<span data-ttu-id="9e9d2-199">oib</span><span class="sxs-lookup"><span data-stu-id="9e9d2-199">oib</span></span>
  
<span data-ttu-id="9e9d2-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="9e9d2-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="9e9d2-201">チェコ共和国</span><span class="sxs-lookup"><span data-stu-id="9e9d2-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-202">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-202">Format</span></span>

<span data-ttu-id="9e9d2-203">10 桁と指定したパターン内のバック スラッシュ</span><span class="sxs-lookup"><span data-stu-id="9e9d2-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-204">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-204">Pattern</span></span>

<span data-ttu-id="9e9d2-205">10 桁の数字と、円記号 ()。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="9e9d2-206">生年月日 (YYMMDD) に対応する 6 つの数字。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="9e9d2-207">円記号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-207">A backslash</span></span>
    
- <span data-ttu-id="9e9d2-208">同じ日に生まれた人を分離するためのシリアル番号に対応する 3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="9e9d2-209">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="9e9d2-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e9d2-210">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-210">Checksum</span></span>

<span data-ttu-id="9e9d2-211">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-212">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-212">Definition</span></span>

<span data-ttu-id="9e9d2-213">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-214">関数`Func_czech_republic_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-215">キーワードの`Keywords_czech_republic_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-216">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-217">関数`Func_czech_republic_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-218">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-218">Keywords</span></span>

#### <a name="keywordsczechrepubliceussnorequivalent"></a><span data-ttu-id="9e9d2-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-220">生年月日数</span><span class="sxs-lookup"><span data-stu-id="9e9d2-220">birth number</span></span>
  
<span data-ttu-id="9e9d2-221">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-221">national identification number</span></span>
  
<span data-ttu-id="9e9d2-222">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-222">personal identification number</span></span>
  
<span data-ttu-id="9e9d2-223">social security number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-223">social security number</span></span>
  
<span data-ttu-id="9e9d2-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-224">nationalnumber#</span></span>
  
<span data-ttu-id="9e9d2-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-225">ssn#</span></span>
  
<span data-ttu-id="9e9d2-226">ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-226">ssn</span></span>
  
<span data-ttu-id="9e9d2-227">国番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-227">national number</span></span>
  
<span data-ttu-id="9e9d2-228">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-228">personal id number</span></span>
  
<span data-ttu-id="9e9d2-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-229">personalidnumber#</span></span>
  
<span data-ttu-id="9e9d2-230">rč</span><span class="sxs-lookup"><span data-stu-id="9e9d2-230">rč</span></span>
  
<span data-ttu-id="9e9d2-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="9e9d2-231">rodné číslo</span></span>
  
<span data-ttu-id="9e9d2-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="9e9d2-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="9e9d2-233">デンマーク</span><span class="sxs-lookup"><span data-stu-id="9e9d2-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-234">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-234">Format</span></span>

<span data-ttu-id="9e9d2-235">10 桁の数字とハイフンで指定されたパターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-236">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-236">Pattern</span></span>

<span data-ttu-id="9e9d2-237">10 桁の数字とハイフン。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="9e9d2-238">6 桁の数字が日付の生年月日に対応します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="9e9d2-239">ハイフン 1 つ </span><span class="sxs-lookup"><span data-stu-id="9e9d2-239">A hyphen</span></span>
    
- <span data-ttu-id="9e9d2-240">シーケンス番号に対応する 4 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e9d2-241">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-241">Checksum</span></span>

<span data-ttu-id="9e9d2-242">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-243">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-243">Definition</span></span>

<span data-ttu-id="9e9d2-244">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-245">関数`Func_denmark_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-246">キーワードの`Keywords_denmark_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-247">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-248">関数`Func_denmark_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-249">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-249">Keywords</span></span>

#### <a name="keywordsdenmarkeussnorequivalent"></a><span data-ttu-id="9e9d2-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-251">個人識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-251">personal identification number</span></span>
  
<span data-ttu-id="9e9d2-252">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-252">national identification number</span></span>
  
<span data-ttu-id="9e9d2-253">social security number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-253">social security number</span></span>
  
<span data-ttu-id="9e9d2-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-254">nationalnumber#</span></span>
  
<span data-ttu-id="9e9d2-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-255">ssn#</span></span>
  
<span data-ttu-id="9e9d2-256">ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-256">ssn</span></span>
  
<span data-ttu-id="9e9d2-257">国番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-257">national number</span></span>
  
<span data-ttu-id="9e9d2-258">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-258">personal id number</span></span>
  
<span data-ttu-id="9e9d2-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-259">personalidnumber#</span></span>
  
<span data-ttu-id="9e9d2-260">cpr nummer</span><span class="sxs-lookup"><span data-stu-id="9e9d2-260">cpr-nummer</span></span>
  
<span data-ttu-id="9e9d2-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="9e9d2-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="9e9d2-262">フィンランド</span><span class="sxs-lookup"><span data-stu-id="9e9d2-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-263">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-263">Format</span></span>

<span data-ttu-id="9e9d2-264">指定した形式で、11 文字の組み合わせ</span><span class="sxs-lookup"><span data-stu-id="9e9d2-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-265">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-265">Pattern</span></span>

<span data-ttu-id="9e9d2-266">指定した形式での 11 文字の組み合わせ。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="9e9d2-267">6 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-267">Six digits</span></span> 
    
- <span data-ttu-id="9e9d2-268">次のいずれかのインスタンスを 1 つ。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="9e9d2-269">プラス記号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-269">Plus symbol</span></span>
    
  - <span data-ttu-id="9e9d2-270">マイナス記号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-270">Minus symbol</span></span>
    
  - <span data-ttu-id="9e9d2-271">文字"A"(いない大文字小文字を区別)</span><span class="sxs-lookup"><span data-stu-id="9e9d2-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="9e9d2-272">3 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-272">Three digits</span></span>
    
- <span data-ttu-id="9e9d2-273">1 つの文字または 1 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e9d2-274">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-274">Checksum</span></span>

<span data-ttu-id="9e9d2-275">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-276">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-276">Definition</span></span>

<span data-ttu-id="9e9d2-277">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-278">関数`Func_finland_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-279">キーワードの`Keywords_finland_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-280">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-281">関数`Func_finland_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-282">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-282">Keywords</span></span>

#### <a name="keywordsfinlandeussnorequivalent"></a><span data-ttu-id="9e9d2-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-284">identification number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-284">identification number</span></span>
  
<span data-ttu-id="9e9d2-285">パーソナル id</span><span class="sxs-lookup"><span data-stu-id="9e9d2-285">personal id</span></span>
  
<span data-ttu-id="9e9d2-286">id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-286">identity number</span></span>
  
<span data-ttu-id="9e9d2-287">フィンランドの国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-287">finnish national id number</span></span>
  
<span data-ttu-id="9e9d2-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-288">personalidnumber#</span></span>
  
<span data-ttu-id="9e9d2-289">国際識別番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-289">national identification number</span></span>
  
<span data-ttu-id="9e9d2-290">id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-290">id number</span></span>
  
<span data-ttu-id="9e9d2-291">国民 id なし。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-291">national id no.</span></span>
  
<span data-ttu-id="9e9d2-292">国民 id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-292">national id number</span></span>
  
<span data-ttu-id="9e9d2-293">id なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-293">id no</span></span>
  
<span data-ttu-id="9e9d2-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9e9d2-294">tunnistenumero</span></span>
  
<span data-ttu-id="9e9d2-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="9e9d2-295">henkilötunnus</span></span>
  
<span data-ttu-id="9e9d2-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9e9d2-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="9e9d2-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="9e9d2-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="9e9d2-298">identiteetti して</span><span class="sxs-lookup"><span data-stu-id="9e9d2-298">identiteetti numero</span></span>
  
<span data-ttu-id="9e9d2-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="9e9d2-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="9e9d2-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="9e9d2-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="9e9d2-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="9e9d2-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="9e9d2-302">tunnusnumero</span></span>
  
<span data-ttu-id="9e9d2-303">kansallinen tunnus して</span><span class="sxs-lookup"><span data-stu-id="9e9d2-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="9e9d2-304">hetu</span><span class="sxs-lookup"><span data-stu-id="9e9d2-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="9e9d2-305">フランス</span><span class="sxs-lookup"><span data-stu-id="9e9d2-305">France</span></span>

<span data-ttu-id="9e9d2-306">詳細についてを参照してください「フランスの社会保障番号 (INSEE)」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="9e9d2-307">ドイツ</span><span class="sxs-lookup"><span data-stu-id="9e9d2-307">Germany</span></span>

<span data-ttu-id="9e9d2-308">詳細についてを参照してください"ドイツの Id カードの番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="9e9d2-309">ギリシャ</span><span class="sxs-lookup"><span data-stu-id="9e9d2-309">Greece</span></span>

<span data-ttu-id="9e9d2-310">詳細についてを参照してください「ギリシャ国内の ID カード」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="9e9d2-311">ハンガリー</span><span class="sxs-lookup"><span data-stu-id="9e9d2-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-312">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-312">Format</span></span>

<span data-ttu-id="9e9d2-313">スペースや区切り記号なしの 9 桁</span><span class="sxs-lookup"><span data-stu-id="9e9d2-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-314">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-314">Pattern</span></span>

<span data-ttu-id="9e9d2-315">9 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="9e9d2-316">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-316">Checksum</span></span>

<span data-ttu-id="9e9d2-317">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-318">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-318">Definition</span></span>

<span data-ttu-id="9e9d2-319">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-320">関数`Func_hungary_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-321">キーワードの`Keywords_hungary_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-322">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-323">関数`Func_hungary_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-324">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-324">Keywords</span></span>

#### <a name="keywordshungaryeussnorequivalent"></a><span data-ttu-id="9e9d2-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-326">ハンガリー語の社会保障番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-326">hungarian social security number</span></span>
  
<span data-ttu-id="9e9d2-327">social security number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-327">social security number</span></span>
  
<span data-ttu-id="9e9d2-328">socialsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="9e9d2-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-329">hssn#</span></span>
  
<span data-ttu-id="9e9d2-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="9e9d2-330">socialsecuritynno</span></span>
  
<span data-ttu-id="9e9d2-331">hssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-331">hssn</span></span>
  
<span data-ttu-id="9e9d2-332">taj</span><span class="sxs-lookup"><span data-stu-id="9e9d2-332">taj</span></span>
  
<span data-ttu-id="9e9d2-333">taj #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-333">taj#</span></span>
  
<span data-ttu-id="9e9d2-334">ssn</span><span class="sxs-lookup"><span data-stu-id="9e9d2-334">ssn</span></span>
  
<span data-ttu-id="9e9d2-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-335">ssn#</span></span>
  
<span data-ttu-id="9e9d2-336">社会保険なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-336">social security no</span></span>
  
<span data-ttu-id="9e9d2-337">áfa</span><span class="sxs-lookup"><span data-stu-id="9e9d2-337">áfa</span></span>
  
<span data-ttu-id="9e9d2-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="9e9d2-338">közösségi adószám</span></span>
  
<span data-ttu-id="9e9d2-339">általános forgalmi adó szám</span><span class="sxs-lookup"><span data-stu-id="9e9d2-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="9e9d2-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="9e9d2-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="9e9d2-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="9e9d2-341">áfa szám</span></span>
  
<span data-ttu-id="9e9d2-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="9e9d2-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="9e9d2-343">ポルトガル</span><span class="sxs-lookup"><span data-stu-id="9e9d2-343">Portugal</span></span>

<span data-ttu-id="9e9d2-344">詳細についてを参照してください「ポルトガルの市民のカード番号」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="9e9d2-345">スペイン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-345">Spain</span></span>

<span data-ttu-id="9e9d2-346">詳細についてを参照してください「スペインの社会保障番号 (SSN)」で、[どのような機密性の高い情報の種類を探します](what-the-sensitive-information-types-look-for.md)。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="9e9d2-347">スウェーデン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="9e9d2-348">形式</span><span class="sxs-lookup"><span data-stu-id="9e9d2-348">Format</span></span>

<span data-ttu-id="9e9d2-349">スペースや区切り記号のない 12 桁の数字</span><span class="sxs-lookup"><span data-stu-id="9e9d2-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="9e9d2-350">パターン</span><span class="sxs-lookup"><span data-stu-id="9e9d2-350">Pattern</span></span>

<span data-ttu-id="9e9d2-351">12 桁の数字:</span><span class="sxs-lookup"><span data-stu-id="9e9d2-351">12 digits:</span></span>
  
-  <span data-ttu-id="9e9d2-352">8 桁の日付 (YYYYMMDD) の生年月日に対応します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="9e9d2-353">シリアル番号に対応する 3 つの桁位置。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="9e9d2-354">シリアル番号の最後の数字は、男性の数が奇数と偶数の女性の場合の割り当てによって性別を示します</span><span class="sxs-lookup"><span data-stu-id="9e9d2-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="9e9d2-355">1990 年までのシリアル番号の割り当てに当てはめて考える郡番号のベアラーが誕生した (1947年の前に生まれた) 場合や、本人が生活、税の記録による 1947 年 1 月 1日、上の特別なコード (通常 7 桁の数字としての 9) のimmigrants</span><span class="sxs-lookup"><span data-stu-id="9e9d2-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="9e9d2-356">1 つのチェック ディジット</span><span class="sxs-lookup"><span data-stu-id="9e9d2-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="9e9d2-357">チェックサム</span><span class="sxs-lookup"><span data-stu-id="9e9d2-357">Checksum</span></span>

<span data-ttu-id="9e9d2-358">はい</span><span class="sxs-lookup"><span data-stu-id="9e9d2-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="9e9d2-359">定義</span><span class="sxs-lookup"><span data-stu-id="9e9d2-359">Definition</span></span>

<span data-ttu-id="9e9d2-360">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、85% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-361">関数`Func_sweden_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="9e9d2-362">キーワードの`Keywords_sweden_eu_ssn_or_equivalent`があります。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="9e9d2-363">DLP ポリシーは、抽出した約 300 文字が次の条件に該当することを検出した場合に、75% の確証を持ってそれがこの種類の機密情報であると特定します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="9e9d2-364">関数`Func_sweden_eu_ssn_or_equivalent`パターンに一致するコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="9e9d2-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
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

### <a name="keywords"></a><span data-ttu-id="9e9d2-365">Keywords</span><span class="sxs-lookup"><span data-stu-id="9e9d2-365">Keywords</span></span>

#### <a name="keywordsswedeneussnorequivalent"></a><span data-ttu-id="9e9d2-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="9e9d2-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="9e9d2-367">個人の id 番号</span><span class="sxs-lookup"><span data-stu-id="9e9d2-367">personal id number</span></span>
  
<span data-ttu-id="9e9d2-368">identification number
</span><span class="sxs-lookup"><span data-stu-id="9e9d2-368">identification number</span></span>
  
<span data-ttu-id="9e9d2-369">パーソナル id なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-369">personal id no</span></span>
  
<span data-ttu-id="9e9d2-370">識別情報なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-370">identity no</span></span>
  
<span data-ttu-id="9e9d2-371">識別なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-371">identification no</span></span>
  
<span data-ttu-id="9e9d2-372">個人識別なし</span><span class="sxs-lookup"><span data-stu-id="9e9d2-372">personal identification no</span></span>
  
<span data-ttu-id="9e9d2-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="9e9d2-373">personnummer id</span></span>
  
<span data-ttu-id="9e9d2-374">- nummer personligt id</span><span class="sxs-lookup"><span data-stu-id="9e9d2-374">personligt id-nummer</span></span>
  
<span data-ttu-id="9e9d2-375">- nummer unikt id</span><span class="sxs-lookup"><span data-stu-id="9e9d2-375">unikt id-nummer</span></span>
  
<span data-ttu-id="9e9d2-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="9e9d2-376">personnummer</span></span>
  
<span data-ttu-id="9e9d2-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="9e9d2-377">identifikationsnumret</span></span>
  
<span data-ttu-id="9e9d2-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-378">personnummer#</span></span>
  
<span data-ttu-id="9e9d2-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="9e9d2-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9e9d2-380">関連項目</span><span class="sxs-lookup"><span data-stu-id="9e9d2-380">See also</span></span>

[<span data-ttu-id="9e9d2-381">機密情報の種類の検索基準:</span><span class="sxs-lookup"><span data-stu-id="9e9d2-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

