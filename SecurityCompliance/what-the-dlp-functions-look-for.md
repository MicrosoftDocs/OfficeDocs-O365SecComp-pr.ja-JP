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
# <a name="what-the-dlp-functions-look-for"></a>DLP 関数の検索対象

データ損失防止 (DLP) には、クレジット カード番号や EU のデビット カード番号などの機密情報の種類が含まれ、これらは DLP ポリシーですぐに使用できる状態になっています。これらの機密情報の種類は特定のパターンを検索し、書式設定が正しいことの確認、チェックサムの適用、関連するキーワードやその他の情報の検索を行うことでパターンを裏付けます。この機能の一部は、内部関数で実行されます。たとえば、クレジット カード番号の機密情報の種類は、有効期限日に似た形式の日付を探す関数を使用して、番号がクレジット カード番号であることを確認します。
  
このトピックではこうした関数の検索対象について取り上げ、事前に定義された機密情報の種類のしくみを理解できるようにします。詳細については、「[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)」をご覧ください。
  
## <a name="funcusdate"></a>Func_us_date

この関数は、米国でよく使用される形式の日付を検索します。これには、"月/日/年"、"月-日-年"、"月間年月日" の形式が含まれます。月の名前または省略形は、大文字と小文字を区別しません。 
  
例:
  
- 2016年12月2日
    
- 2016年12月2
    
- 02 2016 年12月
    
- 12/2/2016
    
- 12/02/16
    
- 2-2016 年12月
    
- 12-2-16
    
使用可能な月の名前:
  
- 英語
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - Jan 7 月2日5月5日5月5日5月5日。
    
## <a name="funceudate"></a>Func_eu_date

この関数は、EU (および米国以外のほとんどの場所) で一般的に使用される形式の日付を検索します。これには、「day/month/year」、「day-month-year」、「day month year」という形式が含まれます。月の名前または省略形では、大文字小文字を区別しません。
  
例:
  
- 2016年12月2時
    
- 02 dec 2016
    
- 2月16時
    
- 2/12/2016
    
- 02/12/16
    
- 2016年12月2時
    
- 2-12-16
    
使用可能な月の名前:
  
- 英語
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - Jan 7 月2日5月5日5月5日5月5日。
    
- オランダ語
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - 1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)
    
- フランス語
    
  - janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv。févr。mars avril mai juin juil。août 9 月11月11月déc。
    
- ドイツ語
    
  - jänuar、februar、märz、エイプリル、mai、juni juli、8月、9月、oktober、11月、dezember
    
  - Jan./Jän。März Mai Juni Juli 年8月9日。11月. dez。
    
- イタリア語
    
  - gennaio、febbraio、marzo、aprile、maggio、gifeno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn。febbr。年.4.magggiluglio ag はありません。設定.ott。年11月..dic.
    
- ポルトガル語
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev 3 月 abr mai 6 月5日前にセットアップする
    
- スペイン語
    
  - enero、febrero、marzo、abril、ago、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero febmarzo。7月7日/set. 年9月.11月11月.dic.
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (非推奨)

> [!NOTE]
> この関数は、上記の`Func_eu_date`関数に含まれているポルトガル語の月の名前のみをサポートしているため、廃止されました。 
  
この関数は、ポルトガル語でよく使用される形式で日付を検索します。この関数の形式は、使用され`Func_eu_date`ている言語でのみ異なります。
  
例:
  
- 2 dez 2016
    
- 02 dez 2016
    
- 2 dez 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-dez-2016
    
- 2-12-16
    
使用可能な月の名前:
  
- ポルトガル語
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - jan fev 3 月 abr mai 6 月5日前にセットアップする
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (非推奨)

> [!NOTE]
> この関数は、上の`Func_eu_date`関数に含まれるオランダ語の月の名前のみをサポートしているため、廃止されました。 
  
この関数は、オランダ語でよく使用される形式で日付を検索します。この関数の形式は、使用され`Func_eu_date`ている言語でのみ異なります。
  
例:
  
- 2 mei 2016
    
- 02 mei 2016
    
- 2 mei 16
    
- 2/12/2016
    
- 02/12/16
    
- 2-mei-2016
    
- 2-12-16
    
使用可能な月の名前:
  
- オランダ語
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - 1月1日6月 (2001 年11月) (oct) 7 月7日9月 | 8 月7日 (oct)
    
## <a name="funcexpirationdate"></a>Func_expiration_date

この関数は、クレジットカードとデビットカードでよく使用される形式の日付を検索します。これにより、月の代わりに日付が除外されます。この関数は、日付を "月/年"、"月-年"、"[月名] 年"、"月の省略名] 年" の形式で照合します。月の名前または省略形は、大文字と小文字を区別しません。
  
例:
  
- MM/YY -- たとえば、01/11 または 1/11
    
- MM/YYYY -- たとえば、01/2011 または 1/2011
    
- MM-YY -- たとえば、01-22 または 1-11
    
- MM-YYYY -- たとえば、01-2000 または 1-2000
    
次の形式では、YY または YYYY をサポートします。
  
- Month-YYYY -- たとえば、Jan-2010、january-2010、Jan-10、または january-10
    
- Month YYYY -- たとえば、'january 2010'、'Jan 2010'、'january 10'、または 'Jan 10'
    
- MonthYYYY -- たとえば、'january2010'、'Jan2010'、'january10'、または 'Jan10'
    
- Month/YYYY--たとえば、' january/2010 '、' jan/2010 '、' jan/10 '、または ' jan/10 '
    
使用可能な月の名前:
  
- 英語
    
  - 1月、2月、3月、4月、5月、6月、7月、5月、7月、7月、11月、10月、11月、12月
    
  - 1月2日から4月5日 (年7月)
    
## <a name="funcusaddress"></a>Func_us_address

この関数は、郵便の送付先住所に使用されるような、米国の州名または郵便番号の省略形の後に正しい ZIP コードが続いたものを検索します。ZIP コードには、米国の州名またはその省略形に関連付けられた正しい ZIP コードを指定する必要があります。米国の州名と ZIP コードを句読点や文字で区切ることはできません。
  
例
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

