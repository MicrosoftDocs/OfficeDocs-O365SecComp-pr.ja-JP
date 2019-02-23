---
title: Outlook on the web で迷惑メール報告機能をオフにする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
description: Office 365 管理者は、ユーザーが迷惑メールとして電子メールを報告する機能をオフにできます。
ms.openlocfilehash: 4c84ae6b92658d045675fd8e8ffe6a6cff516886
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213917"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="a69fe-103">Outlook on the web で迷惑メール報告機能をオフにする</span><span class="sxs-lookup"><span data-stu-id="a69fe-103">Turn off junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="a69fe-p101">web 上の outlook on the web (以前の outlook web App) の迷惑メール報告オプションを使用して、outlook on the web[上](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の outlook on the web を使用して分析することができます。これらのオプションを使用しない場合は、管理者は、次の[](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)コマンドレットを使用してオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="a69fe-p101">You can send junk, phishing, and not junk messages to Microsoft for analysis using the Outlook on the web (formerly known as Outlook Web App) junk email reporting options, as described in [Report junk email and phishing scams in Outlook on the web ](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md). If you don't want to use these options,admins can turn them off via the [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx) cmdlet.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a69fe-106">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="a69fe-106">What do you need to know before you begin?</span></span>
<span data-ttu-id="a69fe-107"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="a69fe-107"></span></span>

- <span data-ttu-id="a69fe-108">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="a69fe-108">Estimated time to complete: 5 minutes</span></span>
    
- <span data-ttu-id="a69fe-p102">この手順を実行する前に、アクセス許可を割り当てる必要があります。必要なアクセス許可を確認するには、「web 上の[outlook のアクセス許可](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp)」トピックの「web メールボックスポリシー」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a69fe-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Outlook on the web mailbox policies" entry in the [Outlook on the web permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx#OutlookWebApp) topic.</span></span> 

- <span data-ttu-id="a69fe-111">exchange online powershell に接続するには、「 [exchange online powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a69fe-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a><span data-ttu-id="a69fe-112">迷惑メール報告をオフにして Microsoft に通知しない</span><span class="sxs-lookup"><span data-stu-id="a69fe-112">Turn off junk, phishing, and not junk reporting to Microsoft</span></span>
<span data-ttu-id="a69fe-113"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="a69fe-113"></span></span>

<span data-ttu-id="a69fe-114">最初に、次のコマンドを実行して、web メールボックスポリシーで利用可能な Outlook の名前を取得します。</span><span class="sxs-lookup"><span data-stu-id="a69fe-114">First, run the following command to get the names of your available Outlook on the web mailbox policies:</span></span>
  
```
Get-OwaMailboxPolicy | Format-Table Name
```

<span data-ttu-id="a69fe-115">次に、以下の構文を使用して、Outlook on the web で迷惑メール報告を Microsoft に対して有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="a69fe-115">Next, use the following syntax to enable or disable junk and not junk reporting to Microsoft in Outlook on the web:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

<span data-ttu-id="a69fe-116">この例では、既定の Outlook web app メールボックスポリシーでのレポートをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a69fe-116">This example turns off reporting in the default Outlook web app mailbox policy:</span></span>
  
```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

<span data-ttu-id="a69fe-117">構文およびパラメーターの詳細については、「[収集](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx)」を参照し[](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx)てください。</span><span class="sxs-lookup"><span data-stu-id="a69fe-117">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](http://technet.microsoft.com/library/bdd580d3-8812-4b4a-93e8-c6401b0d2f0f.aspx) and [Set-OwaMailboxPolicy](http://technet.microsoft.com/library/530166f7-ab42-4609-ba73-9b5a39b567be.aspx).</span></span>

## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a69fe-118">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="a69fe-118">How do you know this worked?</span></span>
<span data-ttu-id="a69fe-119"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="a69fe-119"></span></span>

<span data-ttu-id="a69fe-p103">**Get-owamare boxpolicy**を実行してパラメーター値を確認した後、影響を受けるユーザー (web 上の outlook メールボックスポリシーが適用されているユーザー) に対して web 上の outlook を開き、迷惑メールを報告するオプションが使用できないことを確認します。引き続き迷惑メール、フィッシング、および迷惑メールとしてメッセージをマークすることはできますが、それらを報告することはできません。</span><span class="sxs-lookup"><span data-stu-id="a69fe-p103">Run **Get-OWAMailboxPolicy** to check the parameter values, and then open Outlook on the web for an affected user (who has the Outlook on the web mailbox policy applied to them) and verify that the options to report junk, phishing, and not junk are not available. You'll still be able to mark messages as junk, phishing, and not junk, but you won't be able to report them.</span></span> 
