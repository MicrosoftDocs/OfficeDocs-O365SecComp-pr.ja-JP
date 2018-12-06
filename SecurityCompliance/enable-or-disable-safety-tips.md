---
title: Office 365 で安全性のヒントを有効または無効にする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
description: Office 365 および EOP の管理者に電子メール メッセージで安全性のヒントを無効にする方法を指示します。
ms.openlocfilehash: 8e5d8bf1d2f831b5d74ca3accd8b434519bfeaab
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180857"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Office 365 で安全性のヒントを有効または無効にする

Exchange オンライン保護 (EOP) を追加、またはその電子メール メッセージにスタンプ、安全性のヒントです。メッセージがマークされている場合迷惑メールとして、Office 365 で、メッセージに、フィッシング詐欺などで不審なものが含まれている場合、または外部の画像がある場合、送信者を確認するこれらの安全性に関するヒントを確認するメッセージから安全で、簡単かつ視覚的方法で受信者を提供します。ブロックされています。Office 365 と EOP スタンドアロンの管理者は、迷惑メール ポリシー設定を有効にするか、Outlook およびその他のデスクトップの電子メール クライアントで電子メールに表示されているから安全性のヒントを無効にするを編集できます。 
  
Office 365 は、既定では、組織の安全性のヒントを有効にし、スパムやフィッシング攻撃の戦闘を支援するを有効にしておくことをお勧めします。Web 上の Outlook の安全性のヒントを無効にすることはできません。
  
例を参照してくださいと、安全性のヒントに表示される情報の詳細についてを参照してください[Office 365 で電子メール メッセージでの安全性のヒントです](safety-tips-in-office-365.md)。
  
このトピックの内容
  
- [有効にするか、Office 365 のセキュリティを使用して安全性のヒントを無効にする&amp;コンプライアンス センター](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [有効にするまたは PowerShell を使用して安全性のヒントを無効にするには](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>有効にするか、Office 365 のセキュリティを使用して安全性のヒントを無効にする&amp;コンプライアンス センター
<a name="SandCCsafetytip"> </a>

1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 職場または学校アカウントで Office 365 にサインインします。
    
3. **脅威の管理**を選択して\>**ポリシー**です。 
    
4. [**ポリシー** ] ページでは、**スパム対策**を選択します。
    
    ![このスクリーン ショットは、スパム対策設定] ページで、セキュリティを取得する方法を示しています&amp;コンプライアンス センターです。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. **スパム対策の設定**] ページで、[**ユーザー設定**] タブを選択します。 
    
    ![このスクリーン ショットのスパム対策設定] ページで、セキュリティ上のユーザー設定] タブの位置を示しています&amp;コンプライアンス センターです。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. 必要に応じて、カスタム設定を有効にするのには**カスタム設定**スイッチを選択します。カスタム設定のスイッチは、**オフ**に設定されている場合迷惑メール フィルターのポリシーを変更することはできません。
    
    ![このスクリーン ショットは、ポリシーの設定がオフになっている独自のスパム対策フィルターを示しています。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. 迷惑メール ポリシーを変更し、[**ポリシーの編集**] をクリックするを展開します。たとえば、**ポリシーのフィルターを適用する既定の迷惑メール**の横にある下向きの矢印を選択します。または、**ポリシーの追加**] をクリックして新しいポリシーを作成する場合は、します。
    
8. **スパムおよび一括**操作を展開します。 
    
9. **安全性のヒント**は、下の安全性に関するヒントを有効にするには、チェック ボックス**に**します。安全性のヒントを無効にするには、 **[** 保存] チェック ボックスをオフにします。 
    
10. [ **保存**] を選びます。
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>有効にするまたは PowerShell を使用して安全性のヒントを無効にするには
<a name="pshellsafetytip"> </a>

管理者は、有効または安全性のヒントを無効にする、Exchange オンライン PowerShell を使用できます。セット HostedContentFilterPolicy コマンドレットを使用して、有効または迷惑メール フィルターのポリシーで安全性のヒントを無効にします。
  
1. オンライン PowerShell を交換するために接続します。については、 [Exchange オンライン PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。
    
2. 有効または安全性のヒントを無効にするセット HostedContentFilterPolicy コマンドレットを実行します。
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

詳細は次のとおりです。
    
  -  *ポリシー名*はなどの**既定値**を変更するポリシーの名前です。
    
  -  `$true`スパム フィルター ポリシーの安全性のヒントを有効にします。 
    
  -  `$false`スパム フィルター ポリシーの安全性のヒントを無効にします。 
    
    たとえば、迷惑メール フィルターの既定のポリシーの安全性のヒントを無効にするには、次のコマンドを実行します。
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

このコマンドレットの詳細については、[一連の HostedContentFilterPolicy](https://technet.microsoft.com/library/jj200781.aspx)を参照してください。
    
## <a name="still-need-help"></a>さらにサポートが必要な場合
<a name="pshellsafetytip"> </a>

安全性のヒントを無効には、電子メール メッセージに表示する場合は、これらのことを確認します。
  
- Web 上の Outlook の安全性のヒントを無効にすることはできません。Outlook などの別のクライアントに同じ電子メールを表示してみてください。
    
- 安全性のヒントは既定ではすべて 1 つの EOP を使用するには、すべての Office 365 ユーザーが含まれます。電子メールに表示されない安全性のヒントを無効にするのにはこのトピックで説明したように迷惑メール フィルターのポリシーを使用して無効にする必要があります。ポリシーを設定したら後、は、それが有効になっているを確認します。スパム フィルター ポリシーを有効にする方法の詳細については、[スパム フィルター ポリシーの構成](https://technet.microsoft.com/library/jj200684.aspx)を参照してください。
    
スパムやフィッシング詐欺に対抗するためのより多くの方法は、 [Office 365 の電子メール スパム対策の保護](anti-spam-protection.md)を参照してください。
  

