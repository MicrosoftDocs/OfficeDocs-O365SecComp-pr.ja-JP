---
title: スパム フィルターのルールと、迷惑メール フィルターのポリシーに無効な文字を回避します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: スパム対策の構成で無効な文字があり、セキュリティを使用するときに問題が発生する管理者のためのヘルプが用意されています&amp;コンプライアンス センターです。
ms.openlocfilehash: ca409b4daa7bec01417adb7cbfdfa2a128929e81
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018736"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="22107-103">スパム フィルターのルールに無効な文字を回避し、スパム フィルターのポリシー</span><span class="sxs-lookup"><span data-stu-id="22107-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="22107-p101">以前は、Office 365 の管理者が設定され、Exchange 管理センター (EAC) を使用して迷惑メール フィルターのルールと、迷惑メール フィルターのポリシーを構成します。セキュリティを使用するようになりましたが、&amp;を管理するためのコンプライアンス センターのスパム対策の構成です。次の文字は、EAC でサポートされていましたが、セキュリティでの使用はサポートされていません&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="22107-p101">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange Admin Center (EAC). Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration. The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="22107-107">**無効な文字。**</span><span class="sxs-lookup"><span data-stu-id="22107-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="22107-108">場合は、スパム フィルターのルールや、迷惑メール フィルターのポリシーは、無効な文字のいずれかを含む、これらの問題の一部またはすべてが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22107-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="22107-109">セキュリティ ポリシーまたはルールを検索できない場合があります&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="22107-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="22107-110">Windows PowerShell を使用して、ルールまたはポリシーを取得しようとするときエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="22107-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="22107-111">ポリシーまたは設定は動作しない場合や正常な動作が得られます。</span><span class="sxs-lookup"><span data-stu-id="22107-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="22107-112">迷惑メール フィルターのポリシーとルールの無効な文字を削除します。</span><span class="sxs-lookup"><span data-stu-id="22107-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="22107-113">無効な文字が含まれている規則とポリシーを識別した後は、Windows PowerShell コマンドレットを使用して名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="22107-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="22107-114">[オンライン リモート PowerShell を使用して Exchange に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="22107-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="22107-115">スパム フィルター ポリシーの名前を変更するには、次のようにセット HostedContentFilterPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22107-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="22107-116">迷惑メール フィルターの規則の名前を変更するには、次のようにセット HostedContentFilterRule コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="22107-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="22107-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="22107-117">For more information</span></span>

[<span data-ttu-id="22107-118">管理、セキュリティの脅威の&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="22107-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="22107-119">セット HostedContentFilterPolicy</span><span class="sxs-lookup"><span data-stu-id="22107-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="22107-120">セット HostedContentFilterRule</span><span class="sxs-lookup"><span data-stu-id="22107-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
