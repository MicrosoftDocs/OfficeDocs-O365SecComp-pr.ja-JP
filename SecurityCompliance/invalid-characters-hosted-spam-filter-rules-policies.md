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
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>スパム フィルターのルールに無効な文字を回避し、スパム フィルターのポリシー 

以前は、Office 365 の管理者が設定され、Exchange 管理センター (EAC) を使用して迷惑メール フィルターのルールと、迷惑メール フィルターのポリシーを構成します。セキュリティを使用するようになりましたが、&amp;を管理するためのコンプライアンス センターのスパム対策の構成です。次の文字は、EAC でサポートされていましたが、セキュリティでの使用はサポートされていません&amp;コンプライアンス センターです。  

**無効な文字。**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

場合は、スパム フィルターのルールや、迷惑メール フィルターのポリシーは、無効な文字のいずれかを含む、これらの問題の一部またはすべてが発生する可能性があります。
- セキュリティ ポリシーまたはルールを検索できない場合があります&amp;コンプライアンス センターです。
- Windows PowerShell を使用して、ルールまたはポリシーを取得しようとするときエラーが発生する可能性があります。
- ポリシーまたは設定は動作しない場合や正常な動作が得られます。

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>迷惑メール フィルターのポリシーとルールの無効な文字を削除します。

無効な文字が含まれている規則とポリシーを識別した後は、Windows PowerShell コマンドレットを使用して名前を変更できます。 

1. [オンライン リモート PowerShell を使用して Exchange に接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)します。
    
2. スパム フィルター ポリシーの名前を変更するには、次のようにセット HostedContentFilterPolicy コマンドレットを実行します。
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. 迷惑メール フィルターの規則の名前を変更するには、次のようにセット HostedContentFilterRule コマンドレットを実行します。
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>詳細情報

[管理、セキュリティの脅威の&amp;コンプライアンス センター](threat-management.md)
  
[セット HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[セット HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
