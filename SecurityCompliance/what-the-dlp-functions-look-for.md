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
# <a name="what-the-dlp-functions-look-for"></a>DLP 関数の検索対象

データ損失防止 (DLP) には、クレジット カード番号や EU のデビット カード番号などの機密情報の種類が含まれ、これらは DLP ポリシーですぐに使用できる状態になっています。これらの機密情報の種類は特定のパターンを検索し、書式設定が正しいことの確認、チェックサムの適用、関連するキーワードやその他の情報の検索を行うことでパターンを裏付けます。この機能の一部は、内部関数で実行されます。たとえば、クレジット カード番号の機密情報の種類は、有効期限日に似た形式の日付を探す関数を使用して、番号がクレジット カード番号であることを確認します。
  
このトピックではこうした関数の検索対象について取り上げ、事前に定義された機密情報の種類のしくみを理解できるようにします。詳細については、「[What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)」をご覧ください。
  
## <a name="funcusdate"></a>Func_us_date

この関数は、米国で一般的に使用される形式の日付の検索します。形式を「月/日/年」、「月-日-年」、および「1 日の年の月」が含まれています。名前または数か月の省略名は、大文字小文字を区別ではありません。 
  
例:
  
- 2016 年 12 月 2 日
    
- 2016 年 12 月 2 日
    
- 02 2016 年 12
    
- 2016/12/2
    
- 12/02/16
    
- 2016 年 12 月-2-
    
- 12-2-16
    
使用可能な月の名前:
  
- 英語
    
  - 年 1 月、2 月、3 月、4 月、可能性があります、6 月、7 月、8 月、9 月、10 月、11 月 12 月
    
  - 年 1 月 2 月年年 4 月では、6 月 7 月 8 月 9 月 10 月 11 月 12 月があります。
    
## <a name="funceudate"></a>Func_eu_date

この関数は、EU (および米国以外のほとんどの場所) で一般的に使用される形式の日付を検索します。これには、「day/month/year」、「day-month-year」、「day month year」という形式が含まれます。月の名前または省略形では、大文字小文字を区別しません。
  
例:
  
- 2 年 12 月 2016
    
- 2016 年 12 月の 02
    
- 2 年 12 月 16 日
    
- 2016/2/12
    
- 02/12/16
    
- 2016 年 12 月-2-
    
- 2-12-16
    
使用可能な月の名前:
  
- 英語
    
  - 年 1 月、2 月、3 月、4 月、可能性があります、6 月、7 月、8 月、9 月、10 月、11 月 12 月
    
  - 年 1 月 2 月年年 4 月では、6 月 7 月 8 月 9 月 10 月 11 月 12 月があります。
    
- オランダ語
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - 1 月 2 月の maart 年 4 月 mei 6 月 7 月 8 月 9 月 9 月 10 okt 年 11 月 12 月
    
- フランス語
    
  - janvier、février、mars、avril、mai、juin juillet、août、septembre、octobre、novembre、décembre
    
  - janv。févr。avril の juin juil を mars します。août 9 月。10 月 11 月。déc。
    
- ドイツ語
    
  - jänuar、februar、märz、4 月、mai、juni juli、8 月、9 月、oktober、11 月、dezember
    
  - Jan。/Jän です。2 月 März 月の Juni Juli の 8 月 9 月 Okt。Dez の 11 月です。
    
- イタリア語
    
  - gennaio、febbraio、marzo、aprile、maggio、giugno、luglio、agosto、settembre、ottobre、novembre、dicembre
    
  - genn。febbr。3 月 3 日です。4 月です。magg。giugno luglio ag。設定します。ott。11 月です。dic。
    
- ポルトガル語
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - 1 月 fev 年 3 月の abr の 6 月 7 月前 11 月の dez を設定
    
- スペイン語
    
  - enero、febrero、marzo、abril、mayo、junio、julio、agosto、septiembre、octubre、noviembre、diciembre
    
  - enero 年 2 月。marzo abr. mayo jun. 年 7 月。agosto 9 月を設定します。10 月 11 月。dic。
    
## <a name="funceudate1-deprecated"></a>Func_eu_date1 (非推奨)

> [!NOTE]
> ポルトガル語の月名に含まれるようになりましたがサポートしているためこの関数は廃止されました、`Func_eu_date`上の関数です。 
  
この関数は、ポルトガル語でよく使用される形式の日付を検索します。この関数の形式は、 `Func_eu_date`、使用される言語でのみ異なる。
  
例:
  
- 2 Dez 2016
    
- 02 dez 2016
    
- 2 Dez 16
    
- 2016/2/12
    
- 02/12/16
    
- 2-Dez-2016
    
- 2-12-16
    
使用可能な月の名前:
  
- ポルトガル語
    
  - janeiro、fevereiro、março、marco、abril、maio、junho、julho、agosto、setembro、outubro、novembro、dezembro
    
  - 1 月 fev 年 3 月の abr の 6 月 7 月前 11 月の dez を設定
    
## <a name="funceudate2-deprecated"></a>Func_eu_date2 (非推奨)

> [!NOTE]
> オランダ語の月名に含まれるようになりましたがサポートしているためこの関数は廃止されました、`Func_eu_date`上の関数です。 
  
この関数は、オランダ語でよく使用される形式の日付を検索します。この関数の形式は、 `Func_eu_date`、使用される言語でのみ異なる。
  
例:
  
- 2 Mei 2016
    
- 02 mei 2016
    
- 2 Mei 16
    
- 2016/2/12
    
- 02/12/16
    
- 2016-2-Mei
    
- 2-12-16
    
使用可能な月の名前:
  
- オランダ語
    
  - januari、februari、maart、April、mei、juni、juli、augustus、September、ocktober、October、November、December
    
  - 1 月 2 月の maart 年 4 月 mei 6 月 7 月 8 月 9 月 9 月 10 okt 年 11 月 12 月
    
## <a name="funcexpirationdate"></a>Func_expiration_date

この関数は、数か月のための日を除外するクレジット_カードやデビット カードで一般的に使用される形式で日付を検索します。この関数には、「月」、「月-年」、「[月の名前] 年」と「[月の省略] 年」の形式で日付が一致します。名前または数か月の省略名は、大文字小文字を区別ではありません。
  
例:
  
- MM/YY -- たとえば、01/11 または 1/11
    
- MM/YYYY -- たとえば、01/2011 または 1/2011
    
- MM-YY -- たとえば、01-22 または 1-11
    
- MM-YYYY -- たとえば、01-2000 または 1-2000
    
次の形式では、YY または YYYY をサポートします。
  
- Month-YYYY -- たとえば、Jan-2010、january-2010、Jan-10、または january-10
    
- Month YYYY -- たとえば、'january 2010'、'Jan 2010'、'january 10'、または 'Jan 10'
    
- MonthYYYY -- たとえば、'january2010'、'Jan2010'、'january10'、または 'Jan10'
    
- 月/日 - たとえば、' 年 1 月/2010 'または' 1 月/2010 'または' 1 月 10' または ' 1 月 10'
    
使用可能な月の名前:
  
- 英語
    
  - 年 1 月、2 月、3 月、4 月、可能性があります、6 月、7 月、8 月、9 月、10 月、11 月 12 月
    
  - 6 月 7 月 8 月 9 月 10 月 11 月 12 月が 1 月 2 月 3 月 4 月に可能性があります。
    
## <a name="funcusaddress"></a>Func_us_address

この関数は、郵便の送付先住所に使用されるような、米国の州名または郵便番号の省略形の後に正しい ZIP コードが続いたものを検索します。ZIP コードには、米国の州名またはその省略形に関連付けられた正しい ZIP コードを指定する必要があります。米国の州名と ZIP コードを句読点や文字で区切ることはできません。
  
例
  
- Washington 98052
    
- Washington 98052-9998
    
- WA 98052
    
- WA 98052-9998
    

