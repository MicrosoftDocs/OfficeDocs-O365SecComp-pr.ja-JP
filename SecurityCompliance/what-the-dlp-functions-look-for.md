---
title: DLP 関数の検索対象
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 機密情報の種類では、特定のパターンが検索され、適切な書式設定とチェックサムの適用を確認し、関連するキーワードやその他の情報を検索することによって、corroborate を行います。 この機能の一部は、内部機能によって実行されます。 このトピックでは、定義済みの機密情報の種類がどのように機能するかを理解するために、これらの関数がどのようなものかを説明します。
ms.openlocfilehash: c192a17c488e5a7252a3599204d2bdeda4d0637c
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230321"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="f2961-105">DLP 関数の検索対象</span><span class="sxs-lookup"><span data-stu-id="f2961-105">What the DLP functions look for</span></span>

<span data-ttu-id="f2961-106">データ損失防止 (DLP) には、クレジットカード番号、EU デビットカード番号などの機密情報の種類が含まれています。これは、DLP ポリシーで使用する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="f2961-106">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="f2961-107">これらの機密情報の種類では、特定のパターンが検索され、適切な書式設定とチェックサムを適用し、関連するキーワードまたはその他の情報を検索することによって、corroborate します。</span><span class="sxs-lookup"><span data-stu-id="f2961-107">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="f2961-108">この機能の一部は、内部機能によって実行されます。</span><span class="sxs-lookup"><span data-stu-id="f2961-108">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="f2961-109">たとえば、クレジットカード番号の機密情報の種類では、有効期限として書式設定された日付を検索するために関数を使用しています。これは、corroborate がクレジットカード番号であることを示すために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="f2961-109">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="f2961-110">このトピックでは、定義済みの機密情報の種類がどのように機能するかを理解するために、これらの関数がどのようなものかを説明します。</span><span class="sxs-lookup"><span data-stu-id="f2961-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="f2961-111">詳細については、「[機密情報の種類](what-the-sensitive-information-types-look-for.md)を調べる」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2961-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="f2961-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="f2961-112">Func_us_date</span></span>

<span data-ttu-id="f2961-113">この関数は、米国でよく使用される形式の日付を検索します。これには、"月/日/年"、"月-日-年"、"月間年月日" の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2961-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="f2961-114">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="f2961-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="f2961-115">例:</span><span class="sxs-lookup"><span data-stu-id="f2961-115">Examples:</span></span>
  
- <span data-ttu-id="f2961-116">2016年12月2日</span><span class="sxs-lookup"><span data-stu-id="f2961-116">December 2, 2016</span></span>
    
- <span data-ttu-id="f2961-117">2016年12月2</span><span class="sxs-lookup"><span data-stu-id="f2961-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="f2961-118">02 2016 年12月</span><span class="sxs-lookup"><span data-stu-id="f2961-118">dec 02 2016</span></span>
    
- <span data-ttu-id="f2961-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="f2961-119">12/2/2016</span></span>
    
- <span data-ttu-id="f2961-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="f2961-120">12/02/16</span></span>
    
- <span data-ttu-id="f2961-121">2-2016 年12月</span><span class="sxs-lookup"><span data-stu-id="f2961-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="f2961-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="f2961-122">12-2-16</span></span>
    
<span data-ttu-id="f2961-123">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="f2961-123">Accepted month names:</span></span>
  
- <span data-ttu-id="f2961-124">英語</span><span class="sxs-lookup"><span data-stu-id="f2961-124">English</span></span>
    
  - <span data-ttu-id="f2961-125">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="f2961-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="f2961-126">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="f2961-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="f2961-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="f2961-127">Func_eu_date</span></span>

<span data-ttu-id="f2961-128">この関数は、E.U. でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2961-128">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="f2961-129">(米国以外の場所)。</span><span class="sxs-lookup"><span data-stu-id="f2961-129">(and most places outside the U.S.).</span></span> <span data-ttu-id="f2961-130">これには、"日/月/年"、"年月日"、"day month" の形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f2961-130">This includes the formats "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="f2961-131">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="f2961-131">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="f2961-132">例:</span><span class="sxs-lookup"><span data-stu-id="f2961-132">Examples:</span></span>
  
- <span data-ttu-id="f2961-133">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="f2961-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="f2961-134">02 dec 2016</span><span class="sxs-lookup"><span data-stu-id="f2961-134">02 dec 2016</span></span>
    
- <span data-ttu-id="f2961-135">2月16時</span><span class="sxs-lookup"><span data-stu-id="f2961-135">2 Dec 16</span></span>
    
- <span data-ttu-id="f2961-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="f2961-136">2/12/2016</span></span>
    
- <span data-ttu-id="f2961-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="f2961-137">02/12/16</span></span>
    
- <span data-ttu-id="f2961-138">2016年12月2時</span><span class="sxs-lookup"><span data-stu-id="f2961-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="f2961-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="f2961-139">2-12-16</span></span>
    
<span data-ttu-id="f2961-140">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="f2961-140">Accepted month names:</span></span>
  
- <span data-ttu-id="f2961-141">英語</span><span class="sxs-lookup"><span data-stu-id="f2961-141">English</span></span>
    
  - <span data-ttu-id="f2961-142">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="f2961-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="f2961-143">Jan 7 月2日5月5日5月5日5月5日。</span><span class="sxs-lookup"><span data-stu-id="f2961-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="f2961-144">オランダ語</span><span class="sxs-lookup"><span data-stu-id="f2961-144">Dutch</span></span>
    
  - <span data-ttu-id="f2961-145">januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="f2961-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="f2961-146">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="f2961-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="f2961-147">フランス語</span><span class="sxs-lookup"><span data-stu-id="f2961-147">French</span></span>
    
  - <span data-ttu-id="f2961-148">janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre</span><span class="sxs-lookup"><span data-stu-id="f2961-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="f2961-149">janv.</span><span class="sxs-lookup"><span data-stu-id="f2961-149">janv.</span></span> <span data-ttu-id="f2961-150">févr.</span><span class="sxs-lookup"><span data-stu-id="f2961-150">févr.</span></span> <span data-ttu-id="f2961-151">mars avril mai juin juil。</span><span class="sxs-lookup"><span data-stu-id="f2961-151">mars avril mai juin juil.</span></span> <span data-ttu-id="f2961-152">août 9 月</span><span class="sxs-lookup"><span data-stu-id="f2961-152">août sept.</span></span> <span data-ttu-id="f2961-153">oct.</span><span class="sxs-lookup"><span data-stu-id="f2961-153">oct.</span></span> <span data-ttu-id="f2961-154">年11月.</span><span class="sxs-lookup"><span data-stu-id="f2961-154">nov.</span></span> <span data-ttu-id="f2961-155">déc.</span><span class="sxs-lookup"><span data-stu-id="f2961-155">déc.</span></span>
    
- <span data-ttu-id="f2961-156">ドイツ語</span><span class="sxs-lookup"><span data-stu-id="f2961-156">German</span></span>
    
  - <span data-ttu-id="f2961-157">jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember</span><span class="sxs-lookup"><span data-stu-id="f2961-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="f2961-158">Jan./Jän。</span><span class="sxs-lookup"><span data-stu-id="f2961-158">Jan./Jän.</span></span> <span data-ttu-id="f2961-159">März Mai Juni Juli 年8月9日。</span><span class="sxs-lookup"><span data-stu-id="f2961-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="f2961-160">11月. Dez。</span><span class="sxs-lookup"><span data-stu-id="f2961-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="f2961-161">イタリア語</span><span class="sxs-lookup"><span data-stu-id="f2961-161">Italian</span></span>
    
  - <span data-ttu-id="f2961-162">gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre</span><span class="sxs-lookup"><span data-stu-id="f2961-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="f2961-163">genn。</span><span class="sxs-lookup"><span data-stu-id="f2961-163">genn.</span></span> <span data-ttu-id="f2961-164">febbr。</span><span class="sxs-lookup"><span data-stu-id="f2961-164">febbr.</span></span> <span data-ttu-id="f2961-165">年.</span><span class="sxs-lookup"><span data-stu-id="f2961-165">mar.</span></span> <span data-ttu-id="f2961-166">4.</span><span class="sxs-lookup"><span data-stu-id="f2961-166">apr.</span></span> <span data-ttu-id="f2961-167">magg</span><span class="sxs-lookup"><span data-stu-id="f2961-167">magg.</span></span> <span data-ttu-id="f2961-168">giluglio ag はありません。</span><span class="sxs-lookup"><span data-stu-id="f2961-168">giugno luglio ag.</span></span> <span data-ttu-id="f2961-169">設定.</span><span class="sxs-lookup"><span data-stu-id="f2961-169">sett.</span></span> <span data-ttu-id="f2961-170">ott。</span><span class="sxs-lookup"><span data-stu-id="f2961-170">ott.</span></span> <span data-ttu-id="f2961-171">年11月.</span><span class="sxs-lookup"><span data-stu-id="f2961-171">nov.</span></span> <span data-ttu-id="f2961-172">.dic.</span><span class="sxs-lookup"><span data-stu-id="f2961-172">dic.</span></span>
    
- <span data-ttu-id="f2961-173">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="f2961-173">Portuguese</span></span>
    
  - <span data-ttu-id="f2961-174">ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="f2961-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="f2961-175">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="f2961-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="f2961-176">スペイン語</span><span class="sxs-lookup"><span data-stu-id="f2961-176">Spanish</span></span>
    
  - <span data-ttu-id="f2961-177">enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre</span><span class="sxs-lookup"><span data-stu-id="f2961-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="f2961-178">enero feb</span><span class="sxs-lookup"><span data-stu-id="f2961-178">enero feb.</span></span> <span data-ttu-id="f2961-179">marzo abr。</span><span class="sxs-lookup"><span data-stu-id="f2961-179">marzo abr.</span></span> <span data-ttu-id="f2961-180">6月 o 日</span><span class="sxs-lookup"><span data-stu-id="f2961-180">mayo jun.</span></span> <span data-ttu-id="f2961-181">年.</span><span class="sxs-lookup"><span data-stu-id="f2961-181">jul.</span></span> <span data-ttu-id="f2961-182">/set. 年9月.</span><span class="sxs-lookup"><span data-stu-id="f2961-182">agosto sept./set.</span></span> <span data-ttu-id="f2961-183">oct.</span><span class="sxs-lookup"><span data-stu-id="f2961-183">oct.</span></span> <span data-ttu-id="f2961-184">年11月.</span><span class="sxs-lookup"><span data-stu-id="f2961-184">nov.</span></span> <span data-ttu-id="f2961-185">.dic.</span><span class="sxs-lookup"><span data-stu-id="f2961-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="f2961-186">Func_eu_date1 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="f2961-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="f2961-187">この関数は、上記の`Func_eu_date`関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました。</span><span class="sxs-lookup"><span data-stu-id="f2961-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="f2961-188">この関数は、ポルトガル語でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2961-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="f2961-189">この関数の形式は、使用され`Func_eu_date`ている言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="f2961-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="f2961-190">例:</span><span class="sxs-lookup"><span data-stu-id="f2961-190">Examples:</span></span>
  
- <span data-ttu-id="f2961-191">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="f2961-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="f2961-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="f2961-192">02 dez 2016</span></span>
    
- <span data-ttu-id="f2961-193">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="f2961-193">2 Dez 16</span></span>
    
- <span data-ttu-id="f2961-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="f2961-194">2/12/2016</span></span>
    
- <span data-ttu-id="f2961-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="f2961-195">02/12/16</span></span>
    
- <span data-ttu-id="f2961-196">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="f2961-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="f2961-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="f2961-197">2-12-16</span></span>
    
<span data-ttu-id="f2961-198">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="f2961-198">Accepted month names:</span></span>
  
- <span data-ttu-id="f2961-199">ポルトガル語</span><span class="sxs-lookup"><span data-stu-id="f2961-199">Portuguese</span></span>
    
  - <span data-ttu-id="f2961-200">ジャネイロ、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro</span><span class="sxs-lookup"><span data-stu-id="f2961-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="f2961-201">jan fev 3 月 abr mai 6 月5日前にセットアップする</span><span class="sxs-lookup"><span data-stu-id="f2961-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="f2961-202">Func_eu_date2 (非推奨)</span><span class="sxs-lookup"><span data-stu-id="f2961-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="f2961-203">この関数は、上の`Func_eu_date`関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました。</span><span class="sxs-lookup"><span data-stu-id="f2961-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="f2961-204">この関数は、オランダ語でよく使用される形式で日付を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2961-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="f2961-205">この関数の形式は、使用され`Func_eu_date`ている言語でのみ異なります。</span><span class="sxs-lookup"><span data-stu-id="f2961-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="f2961-206">例:</span><span class="sxs-lookup"><span data-stu-id="f2961-206">Examples:</span></span>
  
- <span data-ttu-id="f2961-207">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="f2961-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="f2961-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="f2961-208">02 mei 2016</span></span>
    
- <span data-ttu-id="f2961-209">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="f2961-209">2 Mei 16</span></span>
    
- <span data-ttu-id="f2961-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="f2961-210">2/12/2016</span></span>
    
- <span data-ttu-id="f2961-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="f2961-211">02/12/16</span></span>
    
- <span data-ttu-id="f2961-212">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="f2961-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="f2961-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="f2961-213">2-12-16</span></span>
    
<span data-ttu-id="f2961-214">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="f2961-214">Accepted month names:</span></span>
  
- <span data-ttu-id="f2961-215">オランダ語</span><span class="sxs-lookup"><span data-stu-id="f2961-215">Dutch</span></span>
    
  - <span data-ttu-id="f2961-216">januari、februari、maart、エイプリル、mei、juni、juli、augustus、9月、ocktober、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="f2961-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="f2961-217">1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)</span><span class="sxs-lookup"><span data-stu-id="f2961-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="f2961-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="f2961-218">Func_expiration_date</span></span>

<span data-ttu-id="f2961-219">この関数は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。これにより、月の代わりに日付が除外されます。</span><span class="sxs-lookup"><span data-stu-id="f2961-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="f2961-220">この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。</span><span class="sxs-lookup"><span data-stu-id="f2961-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="f2961-221">月の名前または省略形は、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="f2961-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="f2961-222">例:</span><span class="sxs-lookup"><span data-stu-id="f2961-222">Examples:</span></span>
  
- <span data-ttu-id="f2961-223">MM/YY--たとえば、01/11 または1/11</span><span class="sxs-lookup"><span data-stu-id="f2961-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="f2961-224">MM/YYYY--たとえば、01/2011 または1/2011</span><span class="sxs-lookup"><span data-stu-id="f2961-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="f2961-225">MM-YY--たとえば、01-22 または1-11</span><span class="sxs-lookup"><span data-stu-id="f2961-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="f2961-226">MM-YYYY--たとえば、01-2000 または1-2000</span><span class="sxs-lookup"><span data-stu-id="f2961-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="f2961-227">次の形式では、YY または YYYY がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f2961-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="f2961-228">月-YYYY--たとえば、のようになります。2010または2010または1月10日または1月10日</span><span class="sxs-lookup"><span data-stu-id="f2961-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="f2961-229">月 YYYY--たとえば、' january 2010 ' または ' Jan 2010 ' または ' Jan 10 ' または ' Jan 10 ' のようになります。</span><span class="sxs-lookup"><span data-stu-id="f2961-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="f2961-230">月 Yyyy--たとえば、' january2010 ' または ' Jan2010 ' または ' january10 ' または ' Jan10 '</span><span class="sxs-lookup"><span data-stu-id="f2961-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="f2961-231">Month/YYYY--たとえば、' january/2010 '、' Jan/2010 '、' jan/10 '、または ' Jan/10 '</span><span class="sxs-lookup"><span data-stu-id="f2961-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="f2961-232">受諾された月の名前:</span><span class="sxs-lookup"><span data-stu-id="f2961-232">Accepted month names:</span></span>
  
- <span data-ttu-id="f2961-233">英語</span><span class="sxs-lookup"><span data-stu-id="f2961-233">English</span></span>
    
  - <span data-ttu-id="f2961-234">1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月</span><span class="sxs-lookup"><span data-stu-id="f2961-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="f2961-235">1月2日から4月5日 (年7月)</span><span class="sxs-lookup"><span data-stu-id="f2961-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="f2961-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="f2961-236">Func_us_address</span></span>

<span data-ttu-id="f2961-237">この関数は、米国の都道府県名または郵便省略形の後に、郵便番号で使用されるのと同様に、有効な郵便番号を検索します。</span><span class="sxs-lookup"><span data-stu-id="f2961-237">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses.</span></span> <span data-ttu-id="f2961-238">郵便番号は、米国の州名または略語に関連付けられている正しい zip コードのいずれかである必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2961-238">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="f2961-239">米国の都道府県名と郵便番号は、句読点または文字で区切ることはできません。</span><span class="sxs-lookup"><span data-stu-id="f2961-239">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="f2961-240">例:</span><span class="sxs-lookup"><span data-stu-id="f2961-240">Examples:</span></span>
  
- <span data-ttu-id="f2961-241">ワシントン98052</span><span class="sxs-lookup"><span data-stu-id="f2961-241">Washington 98052</span></span>
    
- <span data-ttu-id="f2961-242">ワシントン98052-9998</span><span class="sxs-lookup"><span data-stu-id="f2961-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="f2961-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="f2961-243">WA 98052</span></span>
    
- <span data-ttu-id="f2961-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="f2961-244">WA 98052-9998</span></span>
    

