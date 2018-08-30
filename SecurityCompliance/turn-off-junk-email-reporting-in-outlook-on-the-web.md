---
title: 迷惑メールを web 上の Outlook でレポートをオフにします。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/9/2015
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: Office 365 管理者としてことができますオフにする機能レポートの電子メールをユーザーの迷惑メールとして。
ms.openlocfilehash: 8ee5ff87408b80c443e4cf950ce49f624096becb
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272042"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>迷惑メールを web 上の Outlook でレポートをオフにします。

[レポートの迷惑メールおよび web 上の Outlook でのフィッシング詐欺](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の説明に従ってレポート作成のオプション、web の迷惑メールで Outlook を使用して分析するため、迷惑メール、フィッシング詐欺、迷惑メール メッセージをマイクロソフトに送信できます。これらのオプションを使用しない場合は、管理者がオフに[セット OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)コマンドレットを使用しています。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- 予想所要時間 : 5 分
    
- このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、 [Outlook Web App のアクセス許可](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)トピックの「Outlook Web App メールボックス ポリシーのエントリを参照してください。 
    
- 迷惑メールの報告を無効にするために必要なコマンドレットを実行する前に、 [Get OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)と[セットの OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)のトピックの参照情報を確認するのには役に立つ場合があります。 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>迷惑メール、フィッシング詐欺は、オフにし、マイクロソフトに報告する迷惑メール
<a name="sectionSection1"> </a>

最初に、レポートを無効にする仮想ディレクトリを取得するため、次のコマンドレットを実行します。
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

次に、迷惑メールである、および迷惑メールではないという Microsoft への報告をオフにするために、次のコマンドレットを実行します。
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

たとえば、次のコマンドレットでは、仮想ディレクトリ Contoso\owa に関する報告をオフにします。
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法
<a name="sectionSection2"> </a>

パラメーターの値を確認し、web 上で Outlook にアクセスするには、Get-OWAMailboxPolicy を実行し、フィッシング詐欺、迷惑メールを報告し、迷惑メールのオプションが使用できないことを確認します。まだメッセージを迷惑メール、フィッシング詐欺、としてマークすることと、迷惑メールが報告することはできません。 
  

