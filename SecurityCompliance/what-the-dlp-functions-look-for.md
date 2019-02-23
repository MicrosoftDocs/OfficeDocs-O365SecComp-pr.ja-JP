---
title: DLP 関数の検索対象
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/18/2016
ms.audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 94349ed4-5351-4ee2-bbda-70813c9ed693
description: 機密情報の種類では、特定のパターンが検索され、適切な書式設定とチェックサムの適用を確認し、関連するキーワードやその他の情報を検索することによって、corroborate を行います。この機能の一部は、内部機能によって実行されます。このトピックでは、定義済みの機密情報の種類がどのように機能するかを理解するために、これらの関数がどのようなものかを説明します。
ms.openlocfilehash: 55c740e892e92902b368b2dcf7b0999cbc60f3ed
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219357"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="24ef0-105">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="24ef0-105">What the DLP functions look for</span></span>

<span data-ttu-id="24ef0-p102">データ損失防止 (DLP) には、クレジット カード番号や EU のデビット カード番号などの機密情報の種類が含まれ、これらは DLP ポリシーですぐに使用できる状態になっています。これらの機密情報の種類は特定のパターンを検索し、書式設定が正しいことの確認、チェックサムの適用、関連するキーワードやその他の情報の検索を行うことでパターンを裏付けます。この機能の一部は、内部関数で実行されます。たとえば、クレジット カード番号の機密情報の種類は、有効期限日に似た形式の日付を探す関数を使用して、番号がクレジット カード番号であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="24ef0-p103">このトピックではこうした関数の検索対象について取り上げ、事前に定義された機密情報の種類のしくみを理解できるようにします。詳細については、「[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p103">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work. For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="funcusdate"></a><span data-ttu-id="24ef0-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="24ef0-112">Func_us_date</span></span>

<span data-ttu-id="24ef0-p104">この関数は、米国でよく使用される形式の日付を検索します。これには、"月/日/年"、"月-日-年"、"月間年月日" の形式が含まれます。月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p104">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ". The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="24ef0-115">例:</span><span class="sxs-lookup"><span data-stu-id="24ef0-115">Examples:</span></span>
  
- <span data-ttu-id="24ef0-116">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="24ef0-116">December 2, 2016</span></span>
    
- <span data-ttu-id="24ef0-117">2016年12月2</span><span class="sxs-lookup"><span data-stu-id="24ef0-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="24ef0-118">02 2016 年12月</span><span class="sxs-lookup"><span data-stu-id="24ef0-118">dec 02 2016</span></span>
    
- <span data-ttu-id="24ef0-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-119">12/2/2016</span></span>
    
- <span data-ttu-id="24ef0-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="24ef0-120">12/02/16</span></span>
    
- <span data-ttu-id="24ef0-121">2-2016 年12月</span><span class="sxs-lookup"><span data-stu-id="24ef0-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="24ef0-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="24ef0-122">12-2-16</span></span>
    
<span data-ttu-id="24ef0-123">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="24ef0-123">Accepted month names:</span></span>
  
- <span data-ttu-id="24ef0-124">英語</span><span class="sxs-lookup"><span data-stu-id="24ef0-124">English</span></span>
    
  - <span data-ttu-id="24ef0-125">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="24ef0-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="24ef0-126">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="24ef0-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="funceudate"></a><span data-ttu-id="24ef0-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="24ef0-127">Func_eu_date</span></span>

<span data-ttu-id="24ef0-p105">この関数は、EU (および米国以外のほとんどの場所) で一般的に使用される形式の日付を検索します。これには、「day/month/year」、「day-month-year」、「day month year」という形式が含まれます。月の名前または省略形では、大文字小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="24ef0-132">例:</span><span class="sxs-lookup"><span data-stu-id="24ef0-132">Examples:</span></span>
  
- <span data-ttu-id="24ef0-133">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="24ef0-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="24ef0-134">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-134">02 dec 2016</span></span>
    
- <span data-ttu-id="24ef0-135">2月16時</span><span class="sxs-lookup"><span data-stu-id="24ef0-135">2 Dec 16</span></span>
    
- <span data-ttu-id="24ef0-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-136">2/12/2016</span></span>
    
- <span data-ttu-id="24ef0-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="24ef0-137">02/12/16</span></span>
    
- <span data-ttu-id="24ef0-138">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="24ef0-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="24ef0-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="24ef0-139">2-12-16</span></span>
    
<span data-ttu-id="24ef0-140">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="24ef0-140">Accepted month names:</span></span>
  
- <span data-ttu-id="24ef0-141">英語</span><span class="sxs-lookup"><span data-stu-id="24ef0-141">English</span></span>
    
  - <span data-ttu-id="24ef0-142">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="24ef0-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="24ef0-143">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="24ef0-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="24ef0-144">オランダ語</span><span class="sxs-lookup"><span data-stu-id="24ef0-144">Dutch</span></span>
    
  - <span data-ttu-id="24ef0-145">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="24ef0-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="24ef0-146">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="24ef0-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="24ef0-147">フランス語</span><span class="sxs-lookup"><span data-stu-id="24ef0-147">French</span></span>
    
  - <span data-ttu-id="24ef0-148">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="24ef0-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="24ef0-p106">janv。févr。mars avril mai juin juil。août 9 月11月11月déc。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p106">janv. févr. mars avril mai juin juil. août sept. oct. nov. déc.</span></span>
    
- <span data-ttu-id="24ef0-156">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="24ef0-156">German</span></span>
    
  - <span data-ttu-id="24ef0-157">jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember</span><span class="sxs-lookup"><span data-stu-id="24ef0-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="24ef0-p107">Jan./Jän。März Mai Juni Juli 年8月9日。11月. dez。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p107">Jan./Jän. Feb. März Apr. Mai Juni Juli Aug. Sept. Okt. Nov. Dez.</span></span>
    
- <span data-ttu-id="24ef0-161">イタリア語</span><span class="sxs-lookup"><span data-stu-id="24ef0-161">Italian</span></span>
    
  - <span data-ttu-id="24ef0-162">gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="24ef0-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="24ef0-p108">genn。febbr。年.4.magggiluglio ag はありません。設定.ott。年11月..dic.</span><span class="sxs-lookup"><span data-stu-id="24ef0-p108">genn. febbr. mar. apr. magg. giugno luglio ag. sett. ott. nov. dic.</span></span>
    
- <span data-ttu-id="24ef0-173">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="24ef0-173">Portuguese</span></span>
    
  - <span data-ttu-id="24ef0-174">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="24ef0-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="24ef0-175">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="24ef0-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="24ef0-176">スペイン語</span><span class="sxs-lookup"><span data-stu-id="24ef0-176">Spanish</span></span>
    
  - <span data-ttu-id="24ef0-177">enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="24ef0-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="24ef0-p109">enero febmarzo。7月7日/set. 年9月.11月11月.dic.</span><span class="sxs-lookup"><span data-stu-id="24ef0-p109">enero feb. marzo abr. mayo jun. jul. agosto sept./set. oct. nov. dic.</span></span>
    
## <a name="funceudate1-deprecated"></a><span data-ttu-id="24ef0-186">Func_eu_date1 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="24ef0-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="24ef0-187">この関数は、上記の`Func_eu_date`関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました。</span><span class="sxs-lookup"><span data-stu-id="24ef0-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="24ef0-p110">この関数は、ポルトガル語でよく使用される形式で日付を検索します。この関数の形式は、使用され`Func_eu_date`ている言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p110">This function looks for a date in the format commonly used in Portuguese. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="24ef0-190">例:</span><span class="sxs-lookup"><span data-stu-id="24ef0-190">Examples:</span></span>
  
- <span data-ttu-id="24ef0-191">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="24ef0-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-192">02 dez 2016</span></span>
    
- <span data-ttu-id="24ef0-193">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="24ef0-193">2 Dez 16</span></span>
    
- <span data-ttu-id="24ef0-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-194">2/12/2016</span></span>
    
- <span data-ttu-id="24ef0-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="24ef0-195">02/12/16</span></span>
    
- <span data-ttu-id="24ef0-196">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="24ef0-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="24ef0-197">2-12-16</span></span>
    
<span data-ttu-id="24ef0-198">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="24ef0-198">Accepted month names:</span></span>
  
- <span data-ttu-id="24ef0-199">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="24ef0-199">Portuguese</span></span>
    
  - <span data-ttu-id="24ef0-200">janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="24ef0-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="24ef0-201">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="24ef0-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="funceudate2-deprecated"></a><span data-ttu-id="24ef0-202">Func_eu_date2 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="24ef0-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="24ef0-203">この関数は、上の`Func_eu_date`関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました。</span><span class="sxs-lookup"><span data-stu-id="24ef0-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="24ef0-p111">この関数は、オランダ語でよく使用される形式で日付を検索します。この関数の形式は、使用され`Func_eu_date`ている言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p111">This function looks for a date in the format commonly used in Dutch. The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="24ef0-206">例:</span><span class="sxs-lookup"><span data-stu-id="24ef0-206">Examples:</span></span>
  
- <span data-ttu-id="24ef0-207">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="24ef0-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-208">02 mei 2016</span></span>
    
- <span data-ttu-id="24ef0-209">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="24ef0-209">2 Mei 16</span></span>
    
- <span data-ttu-id="24ef0-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-210">2/12/2016</span></span>
    
- <span data-ttu-id="24ef0-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="24ef0-211">02/12/16</span></span>
    
- <span data-ttu-id="24ef0-212">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="24ef0-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="24ef0-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="24ef0-213">2-12-16</span></span>
    
<span data-ttu-id="24ef0-214">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="24ef0-214">Accepted month names:</span></span>
  
- <span data-ttu-id="24ef0-215">オランダ語</span><span class="sxs-lookup"><span data-stu-id="24ef0-215">Dutch</span></span>
    
  - <span data-ttu-id="24ef0-216">januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December</span><span class="sxs-lookup"><span data-stu-id="24ef0-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="24ef0-217">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="24ef0-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="funcexpirationdate"></a><span data-ttu-id="24ef0-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="24ef0-218">Func_expiration_date</span></span>

<span data-ttu-id="24ef0-p112">この関数は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。これにより、月の代わりに日付が除外されます。この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p112">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months. This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="24ef0-222">例:</span><span class="sxs-lookup"><span data-stu-id="24ef0-222">Examples:</span></span>
  
- <span data-ttu-id="24ef0-223">MM/YY -- たとえば、01/11 または 1/11</span><span class="sxs-lookup"><span data-stu-id="24ef0-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="24ef0-224">MM/YYYY -- たとえば、01/2011 または 1/2011</span><span class="sxs-lookup"><span data-stu-id="24ef0-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="24ef0-225">MM-YY -- たとえば、01-22 または 1-11</span><span class="sxs-lookup"><span data-stu-id="24ef0-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="24ef0-226">MM-YYYY -- たとえば、01-2000 または 1-2000</span><span class="sxs-lookup"><span data-stu-id="24ef0-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="24ef0-227">次の形式では、YY または YYYY をサポートします。</span><span class="sxs-lookup"><span data-stu-id="24ef0-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="24ef0-228">Month-YYYY -- たとえば、Jan-2010、january-2010、Jan-10、または january-10</span><span class="sxs-lookup"><span data-stu-id="24ef0-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="24ef0-229">Month YYYY -- たとえば、'january 2010'、'Jan 2010'、'january 10'、または 'Jan 10'</span><span class="sxs-lookup"><span data-stu-id="24ef0-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="24ef0-230">MonthYYYY -- たとえば、'january2010'、'Jan2010'、'january10'、または 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="24ef0-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="24ef0-231">Month/YYYY--たとえば、' january/2010 '、' jan/2010 '、' jan/10 '、または ' jan/10 '</span><span class="sxs-lookup"><span data-stu-id="24ef0-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="24ef0-232">使用可能な月の名前:</span><span class="sxs-lookup"><span data-stu-id="24ef0-232">Accepted month names:</span></span>
  
- <span data-ttu-id="24ef0-233">英語</span><span class="sxs-lookup"><span data-stu-id="24ef0-233">English</span></span>
    
  - <span data-ttu-id="24ef0-234">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="24ef0-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="24ef0-235">1月2日から4月5日 (年7月)</span><span class="sxs-lookup"><span data-stu-id="24ef0-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="funcusaddress"></a><span data-ttu-id="24ef0-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="24ef0-236">Func_us_address</span></span>

<span data-ttu-id="24ef0-p113">この関数は、郵便の送付先住所に使用されるような、米国の州名または郵便番号の省略形の後に正しい ZIP コードが続いたものを検索します。ZIP コードには、米国の州名またはその省略形に関連付けられた正しい ZIP コードを指定する必要があります。米国の州名と ZIP コードを句読点や文字で区切ることはできません。</span><span class="sxs-lookup"><span data-stu-id="24ef0-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="24ef0-240">例</span><span class="sxs-lookup"><span data-stu-id="24ef0-240">Examples:</span></span>
  
- <span data-ttu-id="24ef0-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="24ef0-241">Washington 98052</span></span>
    
- <span data-ttu-id="24ef0-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="24ef0-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="24ef0-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="24ef0-243">WA 98052</span></span>
    
- <span data-ttu-id="24ef0-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="24ef0-244">WA 98052-9998</span></span>
    

