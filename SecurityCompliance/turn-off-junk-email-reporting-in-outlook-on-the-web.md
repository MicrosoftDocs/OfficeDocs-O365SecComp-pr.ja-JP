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
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="aacb7-103">迷惑メールを web 上の Outlook でレポートをオフにします。</span><span class="sxs-lookup"><span data-stu-id="aacb7-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="aacb7-p101">[レポートの迷惑メールおよび web 上の Outlook でのフィッシング詐欺](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の説明に従ってレポート作成のオプション、web の迷惑メールで Outlook を使用して分析するため、迷惑メール、フィッシング詐欺、迷惑メール メッセージをマイクロソフトに送信できます。これらのオプションを使用しない場合は、管理者がオフに[セット OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)コマンドレットを使用しています。</span><span class="sxs-lookup"><span data-stu-id="aacb7-p101">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aacb7-106">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="aacb7-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="aacb7-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="aacb7-107"></span></span>

- <span data-ttu-id="aacb7-108">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="aacb7-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="aacb7-p102">このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、 [Outlook Web App のアクセス許可](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)トピックの「Outlook Web App メールボックス ポリシーのエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="aacb7-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Outlook Web App mailbox policies" entry in the [Outlook Web App permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 
    
- <span data-ttu-id="aacb7-111">迷惑メールの報告を無効にするために必要なコマンドレットを実行する前に、 [Get OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)と[セットの OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)のトピックの参照情報を確認するのには役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="aacb7-111">Before you run the cmdlets required to turn off junk email reporting, it might be helpful to review the reference information in the [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) topics.</span></span> 
    
## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="aacb7-112">迷惑メール、フィッシング詐欺は、オフにし、マイクロソフトに報告する迷惑メール</span><span class="sxs-lookup"><span data-stu-id="aacb7-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="aacb7-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="aacb7-113"></span></span>

<span data-ttu-id="aacb7-114">最初に、レポートを無効にする仮想ディレクトリを取得するため、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="aacb7-114">First, run the following cmdlet to get the virtual directories for which you want to turn off reporting:</span></span>
  
```
Get-OwaMailboxPolicy -Identity <parameter>
```

<span data-ttu-id="aacb7-115">次に、迷惑メールである、および迷惑メールではないという Microsoft への報告をオフにするために、次のコマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="aacb7-115">Next, run the following cmdlet to turn off junk and not junk reporting to Microsoft:</span></span>
  
```
Set-OwaMailboxPolicy -Identity <parameter> -ReportJunkEmailEnabled $false
```

<span data-ttu-id="aacb7-116">たとえば、次のコマンドレットでは、仮想ディレクトリ Contoso\owa に関する報告をオフにします。</span><span class="sxs-lookup"><span data-stu-id="aacb7-116">For example, the following cmdlet turns off reporting for virtual directory Contoso\owa:</span></span>
  
```
Set-OwaMailboxPolicy -Identity Default -ReportJunkEmailEnabled $false
```

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="aacb7-117">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="aacb7-117">How do you know this worked?</span></span>
<span data-ttu-id="aacb7-118"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="aacb7-118"></span></span>

<span data-ttu-id="aacb7-p103">パラメーターの値を確認し、web 上で Outlook にアクセスするには、Get-OWAMailboxPolicy を実行し、フィッシング詐欺、迷惑メールを報告し、迷惑メールのオプションが使用できないことを確認します。まだメッセージを迷惑メール、フィッシング詐欺、としてマークすることと、迷惑メールが報告することはできません。</span><span class="sxs-lookup"><span data-stu-id="aacb7-p103">Run Get-OWAMailboxPolicy to check the parameter values, and then access Outlook on the web and verify that the options to report junk, phishing, and not junk are not available. You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
  

