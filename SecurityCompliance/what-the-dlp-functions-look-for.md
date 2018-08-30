---
title: DLP 関数の検索対象
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: 機密性の高い情報の種類は、特定のパターンを検索し、適切な書式設定、チェックサムを適用することと関連するキーワードまたはその他の情報を探すことを確認して、それを裏付けます。この機能の一部は、内部関数によって実行されます。このトピックでは、どのようなこれらの関数を探して、機密情報の定義済みの型がどのように動作するかを理解するためについて説明します。
ms.openlocfilehash: 510f98e2b4e1d2480550f11026cf445be6ffc931
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013761"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="453f5-105">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="453f5-105">What the DLP functions look for</span></span>

<span data-ttu-id="453f5-p102">データ損失防止 (DLP) には、クレジット カード番号や EU のデビット カード番号などの機密情報の種類が含まれ、これらは DLP ポリシーですぐに使用できる状態になっています。これらの機密情報の種類は特定のパターンを検索し、書式設定が正しいことの確認、チェックサムの適用、関連するキーワードやその他の情報の検索を行うことでパターンを裏付けます。この機能の一部は、内部関数で実行されます。たとえば、クレジット カード番号の機密情報の種類は、有効期限日に似た形式の日付を探す関数を使用して、番号がクレジット カード番号であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="453f5-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="453f5-p103">このトピックではこうした関数の検索対象について取り上げ、事前に定義された機密情報の種類のしくみを理解できるようにします。詳細については、「[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="453f5-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="453f5-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="453f5-112">Func_us_date</span></span>

<span data-ttu-id="453f5-p104">この関数は、米国で一般的に使用される形式の日付の検索します。形式を「月/日/年」、「月-日-年」、および「1 日の年の月」が含まれています。名前または数か月の省略名は、大文字小文字を区別ではありません。</span><span class="sxs-lookup"><span data-stu-id="453f5-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="453f5-115">例:</span><span class="sxs-lookup"><span data-stu-id="453f5-115">Examples:</span></span>
  
- <span data-ttu-id="453f5-116">2016 年 12 月 2 日</span><span class="sxs-lookup"><span data-stu-id="453f5-116">December 2, 2016</span></span>
    
- <span data-ttu-id="453f5-117">2016 年 12 月 2 日</span><span class="sxs-lookup"><span data-stu-id="453f5-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="453f5-118">02 2016 年 12</span><span class="sxs-lookup"><span data-stu-id="453f5-118">dec 02 2016</span></span>
    
- <span data-ttu-id="453f5-119">2016/12/2</span><span class="sxs-lookup"><span data-stu-id="453f5-119">12/2/2016</span></span>
    
- <span data-ttu-id="453f5-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="453f5-120">12/02/16</span></span>
    
- <span data-ttu-id="453f5-121">2016 年 12 月-2-</span><span class="sxs-lookup"><span data-stu-id="453f5-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="453f5-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="453f5-122">12-2-16</span></span>
    
<span data-ttu-id="453f5-123">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="453f5-123">Accepted month names:</span></span>
  
- <span data-ttu-id="453f5-124">英語</span><span class="sxs-lookup"><span data-stu-id="453f5-124">English</span></span>
    
  - <span data-ttu-id="453f5-125">年 1 月、2 月、3 月、4 月、可能性があります、6 月、7 月、8 月、9 月、10 月、11 月 12 月</span><span class="sxs-lookup"><span data-stu-id="453f5-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="453f5-126">年 1 月 2 月年年 4 月では、6 月 7 月 8 月 9 月 10 月 11 月 12 月があります。</span><span class="sxs-lookup"><span data-stu-id="453f5-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="453f5-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="453f5-127">Func_eu_date</span></span>

<span data-ttu-id="453f5-p105">この関数は、EU (および米国以外のほとんどの場所) で一般的に使用される形式の日付を検索します。これには、「day/month/year」、「day-month-year」、「day month year」という形式が含まれます。月の名前または省略形では、大文字小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="453f5-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="453f5-132">例:</span><span class="sxs-lookup"><span data-stu-id="453f5-132">Examples:</span></span>
  
- <span data-ttu-id="453f5-133">2 年 12 月 2016</span><span class="sxs-lookup"><span data-stu-id="453f5-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="453f5-134">2016 年 12 月の 02</span><span class="sxs-lookup"><span data-stu-id="453f5-134">02 dec 2016</span></span>
    
- <span data-ttu-id="453f5-135">2 年 12 月 16 日</span><span class="sxs-lookup"><span data-stu-id="453f5-135">2 Dec 16</span></span>
    
- <span data-ttu-id="453f5-136">2016/2/12</span><span class="sxs-lookup"><span data-stu-id="453f5-136">2/12/2016</span></span>
    
- <span data-ttu-id="453f5-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="453f5-137">02/12/16</span></span>
    
- <span data-ttu-id="453f5-138">2016 年 12 月-2-</span><span class="sxs-lookup"><span data-stu-id="453f5-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="453f5-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="453f5-139">2-12-16</span></span>
    
<span data-ttu-id="453f5-140">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="453f5-140">Accepted month names:</span></span>
  
- <span data-ttu-id="453f5-141">英語</span><span class="sxs-lookup"><span data-stu-id="453f5-141">English</span></span>
    
  - <span data-ttu-id="453f5-142">年 1 月、2 月、3 月、4 月、可能性があります、6 月、7 月、8 月、9 月、10 月、11 月 12 月</span><span class="sxs-lookup"><span data-stu-id="453f5-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="453f5-143">年 1 月 2 月年年 4 月では、6 月 7 月 8 月 9 月 10 月 11 月 12 月があります。</span><span class="sxs-lookup"><span data-stu-id="453f5-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="453f5-144">オランダ語</span><span class="sxs-lookup"><span data-stu-id="453f5-144">Dutch</span></span>
    
  - <span data-ttu-id="453f5-145">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="453f5-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="453f5-146">1 月 2 月の maart 年 4 月 mei 6 月 7 月 8 月 9 月 9 月 10 okt 年 11 月 12 月</span><span class="sxs-lookup"><span data-stu-id="453f5-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="453f5-147">フランス語</span><span class="sxs-lookup"><span data-stu-id="453f5-147">French</span></span>
    
  - <span data-ttu-id="453f5-148">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="453f5-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="453f5-p106">janv。févr。avril の juin juil を mars します。août 9 月。10 月 11 月。déc。</span><span class="sxs-lookup"><span data-stu-id="453f5-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="453f5-156">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="453f5-156">German</span></span>
    
  - <span data-ttu-id="453f5-157">jänuar、februar、märz、4 月、mai、juni juli、8 月、9 月、oktober、11 月、dezember</span><span class="sxs-lookup"><span data-stu-id="453f5-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="453f5-p107">Jan。/Jän です。2 月 März 月の Juni Juli の 8 月 9 月 Okt。Dez の 11 月です。</span><span class="sxs-lookup"><span data-stu-id="453f5-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="453f5-161">イタリア語</span><span class="sxs-lookup"><span data-stu-id="453f5-161">Italian</span></span>
    
  - <span data-ttu-id="453f5-162">gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="453f5-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="453f5-p108">genn。febbr。3 月 3 日です。4 月です。magg。giugno luglio ag。設定します。ott。11 月です。dic。</span><span class="sxs-lookup"><span data-stu-id="453f5-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="453f5-173">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="453f5-173">Portuguese</span></span>
    
  - <span data-ttu-id="453f5-174">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="453f5-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="453f5-175">1 月 fev 年 3 月の abr の 6 月 7 月前 11 月の dez を設定</span><span class="sxs-lookup"><span data-stu-id="453f5-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="453f5-176">スペイン語</span><span class="sxs-lookup"><span data-stu-id="453f5-176">Spanish</span></span>
    
  - <span data-ttu-id="453f5-177">enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="453f5-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="453f5-p109">enero 年 2 月。marzo abr. mayo jun. 年 7 月。agosto 9 月を設定します。10 月 11 月。dic。</span><span class="sxs-lookup"><span data-stu-id="453f5-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="453f5-186">Func_eu_date1 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="453f5-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="453f5-187">ポルトガル語の月名に含まれるようになりましたがサポートしているためこの関数は廃止されました、`Func_eu_date`上の関数です。</span><span class="sxs-lookup"><span data-stu-id="453f5-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="453f5-p110">この関数は、ポルトガル語でよく使用される形式の日付を検索します。この関数の形式は、 `Func_eu_date`、使用される言語でのみ異なる。</span><span class="sxs-lookup"><span data-stu-id="453f5-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="453f5-190">例:</span><span class="sxs-lookup"><span data-stu-id="453f5-190">Examples:</span></span>
  
- <span data-ttu-id="453f5-191">2 Dez 2016</span><span class="sxs-lookup"><span data-stu-id="453f5-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="453f5-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="453f5-192">02 dez 2016</span></span>
    
- <span data-ttu-id="453f5-193">2 Dez 16</span><span class="sxs-lookup"><span data-stu-id="453f5-193">2 Dez 16</span></span>
    
- <span data-ttu-id="453f5-194">2016/2/12</span><span class="sxs-lookup"><span data-stu-id="453f5-194">2/12/2016</span></span>
    
- <span data-ttu-id="453f5-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="453f5-195">02/12/16</span></span>
    
- <span data-ttu-id="453f5-196">2-Dez-2016</span><span class="sxs-lookup"><span data-stu-id="453f5-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="453f5-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="453f5-197">2-12-16</span></span>
    
<span data-ttu-id="453f5-198">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="453f5-198">Accepted month names:</span></span>
  
- <span data-ttu-id="453f5-199">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="453f5-199">Portuguese</span></span>
    
  - <span data-ttu-id="453f5-200">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="453f5-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="453f5-201">1 月 fev 年 3 月の abr の 6 月 7 月前 11 月の dez を設定</span><span class="sxs-lookup"><span data-stu-id="453f5-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="453f5-202">Func_eu_date2 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="453f5-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="453f5-203">オランダ語の月名に含まれるようになりましたがサポートしているためこの関数は廃止されました、`Func_eu_date`上の関数です。</span><span class="sxs-lookup"><span data-stu-id="453f5-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="453f5-p111">この関数は、オランダ語でよく使用される形式の日付を検索します。この関数の形式は、 `Func_eu_date`、使用される言語でのみ異なる。</span><span class="sxs-lookup"><span data-stu-id="453f5-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="453f5-206">例:</span><span class="sxs-lookup"><span data-stu-id="453f5-206">Examples:</span></span>
  
- <span data-ttu-id="453f5-207">2 Mei 2016</span><span class="sxs-lookup"><span data-stu-id="453f5-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="453f5-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="453f5-208">02 mei 2016</span></span>
    
- <span data-ttu-id="453f5-209">2 Mei 16</span><span class="sxs-lookup"><span data-stu-id="453f5-209">2 Mei 16</span></span>
    
- <span data-ttu-id="453f5-210">2016/2/12</span><span class="sxs-lookup"><span data-stu-id="453f5-210">2/12/2016</span></span>
    
- <span data-ttu-id="453f5-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="453f5-211">02/12/16</span></span>
    
- <span data-ttu-id="453f5-212">2016-2-Mei</span><span class="sxs-lookup"><span data-stu-id="453f5-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="453f5-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="453f5-213">2-12-16</span></span>
    
<span data-ttu-id="453f5-214">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="453f5-214">Accepted month names:</span></span>
  
- <span data-ttu-id="453f5-215">オランダ語</span><span class="sxs-lookup"><span data-stu-id="453f5-215">Dutch</span></span>
    
  - <span data-ttu-id="453f5-216">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="453f5-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="453f5-217">1 月 2 月の maart 年 4 月 mei 6 月 7 月 8 月 9 月 9 月 10 okt 年 11 月 12 月</span><span class="sxs-lookup"><span data-stu-id="453f5-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="453f5-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="453f5-218">Func_expiration_date</span></span>

<span data-ttu-id="453f5-p112">この関数は、数か月のための日を除外するクレジット_カードやデビット カードで一般的に使用される形式で日付を検索します。この関数には、「月」、「月-年」、「[月の名前] 年」と「[月の省略] 年」の形式で日付が一致します。名前または数か月の省略名は、大文字小文字を区別ではありません。</span><span class="sxs-lookup"><span data-stu-id="453f5-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="453f5-222">例:</span><span class="sxs-lookup"><span data-stu-id="453f5-222">Examples:</span></span>
  
- <span data-ttu-id="453f5-223">MM/YY -- たとえば、01/11 または 1/11</span><span class="sxs-lookup"><span data-stu-id="453f5-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="453f5-224">MM/YYYY -- たとえば、01/2011 または 1/2011</span><span class="sxs-lookup"><span data-stu-id="453f5-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="453f5-225">MM-YY -- たとえば、01-22 または 1-11</span><span class="sxs-lookup"><span data-stu-id="453f5-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="453f5-226">MM-YYYY -- たとえば、01-2000 または 1-2000</span><span class="sxs-lookup"><span data-stu-id="453f5-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="453f5-227">次の形式では、YY または YYYY をサポートします。</span><span class="sxs-lookup"><span data-stu-id="453f5-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="453f5-228">Month-YYYY -- たとえば、Jan-2010、january-2010、Jan-10、または january-10</span><span class="sxs-lookup"><span data-stu-id="453f5-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="453f5-229">Month YYYY -- たとえば、'january 2010'、'Jan 2010'、'january 10'、または 'Jan 10'</span><span class="sxs-lookup"><span data-stu-id="453f5-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="453f5-230">MonthYYYY -- たとえば、'january2010'、'Jan2010'、'january10'、または 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="453f5-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="453f5-231">月/日 - たとえば、' 年 1 月/2010 'または' 1 月/2010 'または' 1 月 10' または ' 1 月 10'</span><span class="sxs-lookup"><span data-stu-id="453f5-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="453f5-232">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="453f5-232">Accepted month names:</span></span>
  
- <span data-ttu-id="453f5-233">英語</span><span class="sxs-lookup"><span data-stu-id="453f5-233">English</span></span>
    
  - <span data-ttu-id="453f5-234">年 1 月、2 月、3 月、4 月、可能性があります、6 月、7 月、8 月、9 月、10 月、11 月 12 月</span><span class="sxs-lookup"><span data-stu-id="453f5-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="453f5-235">6 月 7 月 8 月 9 月 10 月 11 月 12 月が 1 月 2 月 3 月 4 月に可能性があります。</span><span class="sxs-lookup"><span data-stu-id="453f5-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="453f5-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="453f5-236">Func_us_address</span></span>

<span data-ttu-id="453f5-p113">この関数は、郵便の送付先住所に使用されるような、米国の州名または郵便番号の省略形の後に正しい ZIP コードが続いたものを検索します。ZIP コードには、米国の州名またはその省略形に関連付けられた正しい ZIP コードを指定する必要があります。米国の州名と ZIP コードを句読点や文字で区切ることはできません。</span><span class="sxs-lookup"><span data-stu-id="453f5-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="453f5-240">例</span><span class="sxs-lookup"><span data-stu-id="453f5-240">Examples:</span></span>
  
- <span data-ttu-id="453f5-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="453f5-241">Washington 98052</span></span>
    
- <span data-ttu-id="453f5-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="453f5-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="453f5-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="453f5-243">WA 98052</span></span>
    
- <span data-ttu-id="453f5-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="453f5-244">WA 98052-9998</span></span>
    

