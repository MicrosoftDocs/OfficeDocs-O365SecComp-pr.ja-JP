---
title: スパムフィルタールールおよびスパムフィルターポリシーに無効な文字を使用しない
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: スパム対策構成に無効な文字が含まれていて、セキュリティ&amp; /コンプライアンスセンターを使用しようとしたときに問題が発生する管理者向けのヘルプを提供します。
ms.openlocfilehash: 0e7dcb40d8e54045caa55083e2cbf0585a80869d
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154165"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>スパムフィルタールールおよびスパムフィルターポリシーに無効な文字を使用しない 

以前の Office 365 管理者は、Exchange 管理センター (EAC) を使用して、スパムフィルタールールおよびスパムフィルターポリシーをセットアップおよび構成します。 ここで、セキュリティ&amp;コンプライアンスセンターを使用して、スパム対策構成を管理します。 次の文字は EAC でサポートされていますが、セキュリティ&amp;コンプライアンスセンターでは使用できません。  

**無効な文字:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

スパムフィルタールールまたはスパムフィルターポリシーに無効な文字が含まれている場合は、次のいずれかまたはすべての問題が発生する可能性があります。
- セキュリティ&amp; /コンプライアンスセンターでポリシーまたはルールを見つけることができない場合があります。
- Windows PowerShell を使用してルールまたはポリシーを取得しようとすると、エラーが発生することがあります。
- ポリシーまたは設定が期待どおりに実行されない、または実行されないことがあります。

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>スパムフィルターポリシーとルールから無効な文字を削除する

無効な文字を含むポリシーとルールを特定したら、Windows PowerShell コマンドレットを使用して名前を変更できます。 

1. [リモート PowerShell を使用して Exchange Online に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。
    
2. スパムフィルターポリシーの名前を変更するには、次のように Set-hostedcontentfilterpolicy コマンドレットを実行します。
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. スパムフィルタールールの名前を変更するには、次のように Disable-hostedcontentfilterrule コマンドレットを実行します。
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>関連情報

[セキュリティ&amp; /コンプライアンスセンターでの脅威管理](threat-management.md)
  
[Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Disable-hostedcontentfilterrule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
