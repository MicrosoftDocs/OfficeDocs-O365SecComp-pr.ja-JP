---
title: Office 365 で安全性のヒントを有効または無効にする
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f09668bd-fe1a-4c01-89e3-e88c370e66c7
ms.collection:
- M365-security-compliance
description: Office 365 と EOP admins に、電子メールメッセージの安全性に関するヒントを有効または無効にする方法を伝えます。
ms.openlocfilehash: a782c9a1eca874c2aa2128b6129257067c63219a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154759"
---
# <a name="enable-or-disable-safety-tips-in-office-365"></a>Office 365 で安全性のヒントを有効または無効にする

Exchange Online Protection (EOP) は、配信する電子メールメッセージに安全なヒントを追加またはスタンプします。 これらの安全なヒントにより、メッセージが安全であることを確認するための視覚的な方法、メッセージが Office 365 によってスパムとしてマークされている場合、メッセージにフィッシング詐欺などの疑わしいものが含まれている場合、または外部画像がある場合は、ブロックされています。 Office 365 と EOP の管理者は、スパムポリシー設定を編集して、Outlook およびその他のデスクトップ電子メールクライアントでの安全なヒントの表示を有効または無効にすることができます。 
  
Office 365 では、組織のために既定で安全なヒントが有効になっており、スパムやフィッシング攻撃に対処できるようにしておくことをお勧めします。 Web 上の Outlook の安全性に関するヒントを無効にすることはできません。
  
例を確認し、安全なヒントに表示される情報について詳しくは、「 [Office 365 の電子メールメッセージの安全性に関するヒント](safety-tips-in-office-365.md)」を参照してください。
  
このトピックの内容
  
- [Office 365 セキュリティ&amp;コンプライアンスセンターを使用して安全性ヒントを有効または無効にするには](enable-or-disable-safety-tips.md#SandCCsafetytip)
    
- [PowerShell を使用して安全性ヒントを有効または無効にするには](enable-or-disable-safety-tips.md#pshellsafetytip)
    
## <a name="to-enable-or-disable-safety-tips-by-using-the-office-365-security-amp-compliance-center"></a>Office 365 セキュリティ&amp;コンプライアンスセンターを使用して安全性ヒントを有効または無効にするには
<a name="SandCCsafetytip"> </a>

1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
3. [**脅威管理** \> **ポリシー**] を選択します。 
    
4. [**ポリシー** ] ページで、[**スパム対策**] を選択します。
    
    ![このスクリーンショットは、セキュリティ&amp; /コンプライアンスセンターの [スパム対策設定] ページにアクセスする方法を示しています。](media/b8eb2ee3-2eb1-4ea2-b138-f6d7fb2e23de.png)
  
5. [**スパム対策設定**] ページで、[**カスタム**] タブを選択します。 
    
    ![このスクリーンショットは、セキュリティ&amp; /コンプライアンスセンターの [スパム対策設定] ページの [ユーザー設定] タブの場所を示しています。](media/1d688d23-e6f3-4de5-84a7-e8ce31786193.png)
  
6. 必要に応じて、[**カスタム設定**] スイッチを選択して、カスタム設定を有効にします。 カスタム設定スイッチが [**オフ**] に設定されている場合は、スパムフィルターポリシーを変更することはできません。
    
    ![このスクリーンショットは、カスタムのスパム対策フィルターポリシー設定をオフにした状態を示しています。](media/94f900ad-b556-4a31-a3ac-acfcd72e71b8.png)
  
7. 変更するスパムポリシーを展開し、[ポリシーの**編集**] を選択します。 たとえば、[**既定のスパムフィルターポリシー**] の横にある下矢印を選択します。 または、必要に応じて、[**ポリシーの追加**] を選択して、新しいポリシーを作成することもできます。
    
8. **[スパムと一括**アクション] を展開します。 
    
9. 安全のヒントを有効にするには、[**安全性のヒント**] の [**オン**] チェックボックスをオンにします。 安全性のヒントを無効にするには、 **[オン**] チェックボックスをオフにします。 
    
10. **[保存]** を選択します。
    
## <a name="to-enable-or-disable-safety-tips-by-using-powershell"></a>PowerShell を使用して安全性ヒントを有効または無効にするには
<a name="pshellsafetytip"> </a>

管理者は、Exchange Online PowerShell を使用して安全性のヒントを有効または無効にすることができます。 スパムフィルターポリシーの安全性に関するヒントを有効または無効にするには、Set-hostedcontentfilterpolicy コマンドレットを使用します。
  
1. Exchange Online PowerShell への接続。 詳細については、「 [Exchange Online PowerShell への接続](http://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。
    
2. Set-hostedcontentfilterpolicy コマンドレットを実行して、安全性に関するヒントを有効または無効にします。
    
  ```
  Set-HostedContentFilterPolicy -Identity "policy name " -InlineSafetyTipsEnabled <$true|$false>
  ```

詳細は次のとおりです。
    
  -  [*ポリシー名*] は、変更するポリシーの名前です (例: **default**)。
    
  -  `$true`スパムフィルターポリシーの安全性に関するヒントを有効にします。 
    
  -  `$false`スパムフィルターポリシーの安全性に関するヒントを無効にします。 
    
    たとえば、既定のスパムフィルターポリシーの安全性のヒントを無効にするには、次のコマンドを実行します。
    
  ```
  PS C:\> Set-HostedContentFilterPolicy -Identity "default" -InlineSafetyTipsEnabled $false
  ```

このコマンドレットの詳細については、「 [set-hostedcontentfilterpolicy](https://technet.microsoft.com/library/jj200781.aspx)」を参照してください。
    
## <a name="still-need-help"></a>さらにサポートが必要な場合
<a name="pshellsafetytip"> </a>

安全のヒントを無効にしても、電子メールメッセージに表示されている場合は、次の点を確認してください。
  
- Web 上の Outlook の安全性に関するヒントを無効にすることはできません。 Outlook などの別のクライアントで同じ電子メールを表示してみてください。
    
- EOP を使用するすべてのユーザーについて、既定で安全性のヒントはオンになっています。これには、Office 365 を持つすべてのユーザーが含まれます。 セーフヒントが電子メールで表示されないようにするには、このトピックで説明されているように、スパムフィルターポリシーを使用して、それらを無効にする必要があります。 ポリシーを設定したら、そのポリシーが有効になっていることを確認します。 スパムフィルターポリシーの有効化の詳細については、「[スパムフィルターポリシーの構成](https://technet.microsoft.com/library/jj200684.aspx)」を参照してください。
    
スパムやフィッシングに対抗する方法については、「 [Office 365 電子メールのスパム対策保護](anti-spam-protection.md)」を参照してください。
  

