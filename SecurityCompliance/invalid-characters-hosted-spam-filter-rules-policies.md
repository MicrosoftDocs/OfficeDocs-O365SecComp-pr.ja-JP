---
title: スパムフィルタールールおよびスパムフィルターポリシーに無効な文字を使用しない
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: スパム対策構成に無効な文字が含まれていて、セキュリティ&amp; /コンプライアンスセンターを使用しようとしたときに問題が発生する管理者向けのヘルプを提供します。
ms.openlocfilehash: 90cf89d019a34658b676f02baa84c70f27200262
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276078"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a><span data-ttu-id="fd7d5-103">スパムフィルタールールおよびスパムフィルターポリシーに無効な文字を使用しない</span><span class="sxs-lookup"><span data-stu-id="fd7d5-103">Avoid invalid characters in your spam filter rules and spam filter policy</span></span> 

<span data-ttu-id="fd7d5-p101">以前の Office 365 管理者は、Exchange 管理センター (EAC) を使用して、スパムフィルタールールおよびスパムフィルターポリシーをセットアップおよび構成します。ここで、セキュリティ&amp;コンプライアンスセンターを使用して、スパム対策構成を管理します。次の文字は EAC でサポートされていますが、セキュリティ&amp;コンプライアンスセンターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-p101">Previously, Office 365 administrators set up and configured spam filter rules and the spam filter policy by using the Exchange Admin Center (EAC). Now, you use the Security &amp; Compliance Center to manage the your anti-spam configuration. The following characters were supported in the EAC but are not supported for use in the Security &amp; Compliance Center.</span></span>  

<span data-ttu-id="fd7d5-107">**無効な文字:**</span><span class="sxs-lookup"><span data-stu-id="fd7d5-107">**Invalid characters:**</span></span>
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

<span data-ttu-id="fd7d5-108">スパムフィルタールールまたはスパムフィルターポリシーに無効な文字が含まれている場合は、次のいずれかまたはすべての問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-108">If your spam filter rules or your spam filter policy contains any of the invalid characters, you might encounter any or all of these issues:</span></span>
- <span data-ttu-id="fd7d5-109">セキュリティ&amp; /コンプライアンスセンターでポリシーまたはルールを見つけることができない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-109">You might be unable to find the policy or rules in the Security &amp; Compliance Center.</span></span>
- <span data-ttu-id="fd7d5-110">Windows PowerShell を使用してルールまたはポリシーを取得しようとすると、エラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-110">You might receive errors when trying to get the rules or policy by using Windows PowerShell.</span></span>
- <span data-ttu-id="fd7d5-111">ポリシーまたは設定が期待どおりに実行されない、または実行されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-111">You might find that the policy or settings do not run or perform as expected.</span></span>

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a><span data-ttu-id="fd7d5-112">スパムフィルターポリシーとルールから無効な文字を削除する</span><span class="sxs-lookup"><span data-stu-id="fd7d5-112">Remove the invalid characters from the spam filter policy and rules</span></span>

<span data-ttu-id="fd7d5-113">無効な文字を含むポリシーとルールを特定したら、Windows PowerShell コマンドレットを使用して名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-113">Once you have identified the policy and rules that contain invalid characters, you can change the names by using the Windows PowerShell cmdlets.</span></span> 

1. <span data-ttu-id="fd7d5-114">[リモート PowerShell を使用して Exchange Online に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-114">[Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="fd7d5-115">スパムフィルターポリシーの名前を変更するには、次のように set-hostedcontentfilterpolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-115">To change the name of the spam filter policy, run the Set-HostedContentFilterPolicy cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. <span data-ttu-id="fd7d5-116">スパムフィルタールールの名前を変更するには、次のように disable-hostedcontentfilterrule コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd7d5-116">To change the name of a spam filter rule, run the Set-HostedContentFilterRule cmdlet as follows:</span></span>
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a><span data-ttu-id="fd7d5-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fd7d5-117">For more information</span></span>

[<span data-ttu-id="fd7d5-118">セキュリティ&amp; /コンプライアンスセンターでの脅威管理</span><span class="sxs-lookup"><span data-stu-id="fd7d5-118">Threat management in the Security &amp; Compliance Center</span></span>](threat-management.md)
  
[<span data-ttu-id="fd7d5-119">set-hostedcontentfilterpolicy</span><span class="sxs-lookup"><span data-stu-id="fd7d5-119">Set-HostedContentFilterPolicy</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[<span data-ttu-id="fd7d5-120">disable-hostedcontentfilterrule</span><span class="sxs-lookup"><span data-stu-id="fd7d5-120">Set-HostedContentFilterRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
