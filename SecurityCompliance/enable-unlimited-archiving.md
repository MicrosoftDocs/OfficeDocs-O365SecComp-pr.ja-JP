---
title: Office 365 の管理者のヘルプで無制限のアーカイブを有効にします。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '管理者: アーカイブを無制限のストレージとオンラインの Exchange メールボックスのユーザーを提供する、Office 365 で自動拡張を有効にする方法について説明します。組織全体または特定のユーザーのためだけにアーカイブを自動拡張を有効にできます。'
ms.openlocfilehash: 823e4ed0049e7a28a6c97c4045fb75987f43db5f
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782154"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>Office 365 の管理者のヘルプで無制限のアーカイブを有効にします。

Office 365 で自動展開する Exchange のオンライン アーカイブ機能を使用するにはアーカイブ メールボックスの無制限のストレージ ・ スペースを有効にします。アーカイブの自動拡張を有効にすると、格納域の制限に近づくと追加の記憶域がユーザーのアーカイブ メールボックスに自動的に追加します。無制限のメールボックスの容量になります。有効にできます、組織内の全員に対して、または特定のユーザーのためだけのアーカイブの自動拡張します。自動拡張の詳細については、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。

## <a name="before-you-begin"></a>はじめに

- グローバル管理者、Office 365 の組織または組織全体または特定のユーザーをアーカイブする自動拡張を有効にするのには、Exchange Online 組織内の組織の管理役割グループのメンバーであります。代わりに、特定のユーザーのアーカイブを自動拡張を有効にするのには差し込み印刷の宛先役割が割り当てられている役割グループのメンバーである必要があります。
    
- ユーザーのアーカイブ メールボックスは、アーカイブの自動拡張を有効にする前に有効にするのには。ユーザーには、アーカイブ メールボックスを有効にするのには、Exchange オンライン計画 2 ライセンスを割り当てる必要があります。ユーザーには、Exchange オンライン計画 1 ライセンスが割り当てられているが場合、は、アーカイブ メールボックスを有効にするのには別の Exchange Online Archiving のライセンスを割り当てる必要があります。参照してください[Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)です。
    
- アーカイブ メールボックスを有効にするのに PowerShell を使用することもできます。組織内のすべてのユーザーのアーカイブ メールボックスを有効にするを使用することができます PowerShell コマンドの例については、[詳細について](#more-information)はを参照してください。 
    
- アーカイブ自動拡張は、共有メールボックスをサポートします。共有されているメールボックスのアーカイブを有効にするには、Exchange オンライン計画 2 ライセンスまたは Exchange Online Archiving のライセンスを持つ Exchange オンライン計画 1 ライセンスが必要です。
    
- Exchange 管理センターまたはセキュリティを使用することはできません&amp;コンプライアンスの中央アーカイブの自動拡張を有効にします。Exchange オンライン PowerShell を使用する必要があります。リモート PowerShell を使用して Exchange Online 組織に接続するには、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)を参照してください。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>組織全体のアーカイブを自動拡張を有効にします。

組織全体のアーカイブを自動拡張を有効にできます。有効にすると、アーカイブの自動拡張が有効にして作成される新しいユーザーのメールボックスのユーザーのメールボックスを既存の。新しいユーザーのメールボックスを作成する場合は、自動拡張のアーカイブ機能は新しいユーザーのメールボックスの使用、ユーザーのメインのアーカイブ メールボックスを有効にしてください。
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 組織全体のアーカイブを自動拡張を有効にするのには、Exchange オンライン PowerShell では、次のコマンドを実行します。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>自動拡張の特定のユーザーのアーカイブを有効にします。

組織内のすべてのユーザーのアーカイブを自動拡張を有効にするのではなくできるだけ有効にする特定のユーザーに対して。一部のユーザーだけでは非常に大規模なアーカイブ ・ ストレージが必要である可能性がありますのででこれを行う場合があります。
  
自動拡張の特定のユーザーのアーカイブを有効にすると、以下 2 つの構成も変更されます。
  
- (110 GB に 100 GB) から 10 GB では、ユーザーのアーカイブをプライマリ メールボックスの記憶域のクォータが増加します。アーカイブ警告クォータ (90 GB から 100 GB から 10 GB でも増加します。
    
- (110 GB に 100 GB) からも、10 GB で、ユーザーのプライマリ メールボックスの回復可能なアイテム フォルダーの記憶域のクォータを増加します。回復可能な項目の警告クォータ (90 GB から 100 GB から 10 GB でも増加します。上にメールボックスを保持または、Office 365 のリテンション ・ ポリシーに割り当てられている場合にのみ、これらの変更が適用されます。
    
自動拡張のアーカイブを準備する前に発生する記憶域の問題を防ぐためには、この追加の空き領域が追加されます。その追加のストレージ領域*は*前のセクションで説明したように、組織全体のアーカイブを自動拡張を有効にしたときに追加に注意してください。 
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 自動拡張の特定のユーザーのアーカイブを有効にする Exchange のオンライン PowerShell では、次のコマンドを実行します。説明したよう、ユーザーのアーカイブ メールボックス (メイン アーカイブ) する必要があります有効にするを有効にできます、ユーザーのアーカイブの自動拡張する前に。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> Exchange ハイブリッド展開の場合では、設置型では、プライマリ メールボックスを持つユーザーの固有のアーカイブの自動拡張を有効にする**有効にするメールボックス AutoExpandingArchive**コマンドを使用することはできませんし、クラウド ベースのアーカイブ メールボックスは、します。コマンドを実行する**セット OrganizationConfig AutoExpandingArchive** Exchange オンライン アーカイブを自動拡張を有効にする PowerShell がある Exchange ハイブリッド展開でのクラウド ・ ベースのアーカイブ メールボックスのアーカイブを自動拡張を有効にするには、全体の組織です。主のユーザーのアーカイブ メールボックスは、クラウド ベースの両方は、場合は、特定のユーザーに対してアーカイブを自動拡張を有効にするのには、**有効にするメールボックス AutoExpandingArchive**コマンドを使用できます。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>アーカイブの自動拡張が有効になっていることを確認します。

組織のアーカイブの自動拡張が有効になっていることを確認するには、Exchange オンライン PowerShell で次のコマンドを実行します。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

値の`True`、組織のアーカイブの自動拡張が有効になっていることを示します。 
  
自動拡張が特定のユーザーに対して有効にすることを確認するには、Exchange オンライン PowerShell で次のコマンドを実行します。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
値の`True`のユーザーのアーカイブの自動拡張が有効になっていることを示します。 
  
アーカイブの自動拡張を有効にした後、次の点に注意してください。
  
- 組織のアーカイブを自動拡張を有効に**設定 OrganizationConfig AutoExpandingArchive**コマンドを実行する場合は個々 のメールボックスに**メールボックスが有効にする AutoExpandingArchive**を実行する必要はありません。組織は、 *AutoExpandingArchiveEnabled*のプロパティを変更するユーザーのメールボックスのアーカイブ自動拡張を有効に**設定 OrganizationConfig**コマンドレットを実行することに注意してください`True`。
    
- 同様に、アーカイブの自動拡張を有効にすると、 *ArchiveQuota*と*ArchiveWarningQuota*のメールボックスのプロパティの値は変更されません。実際には、ユーザーのメールボックスのアーカイブを自動拡張を有効にして、 *AutoExpandingArchiveEnabled*プロパティ`True`、 *ArchiveQuota*および*ArchiveWarningQuota*プロパティは無視されます。ユーザーのメールボックスのアーカイブの自動拡張を有効にした後、これらのメールボックスのプロパティの例をここでは。 
    
    ![アーカイブの自動拡張を有効にした後、ArchiveQuota および ArchiveWarningQuota プロパティは無視されます。](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>詳細情報

- アーカイブ メールボックスを有効にするのに PowerShell を使用することもできます。などをオンラインで実行できる次のコマンド Exchange PowerShell のアーカイブ メールボックスが既に有効になっていないすべてのユーザーのアーカイブ メールボックスを有効にします。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 有効にした後組織のまたは特定のユーザーのアーカイブの自動拡張、アーカイブ先のメールボックス (回復可能な項目] フォルダーを含む) が 90 GB に達すると、自動拡張のアーカイブ、アーカイブ メールボックスが変換されます。準備する追加の記憶域の最大 30 日間がかかることができます。
    
- を有効にするアーカイブの自動展開後は、オフにすることはできません。
    
- 設置型のプライマリ メールボックスを持つユーザーに対して Exchange ハイブリッド展開でのクラウド ・ ベースのアーカイブ メールボックスには、アーカイブの自動拡張がサポートされています。ただし、クラウド ・ ベースのアーカイブ メールボックスのアーカイブの自動拡張を有効にすると、することはできませんオフボードそのアーカイブ先のメールボックスをオンプレミスの Exchange 組織に戻る。
    
- ユーザーがアーカイブ メールボックスに追加のストレージ領域内の項目にアクセスするために使用できる Outlook クライアントのリストは、[無制限の概要については、Office 365 のアーカイブ](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)で「Outlook の自動展開されたアーカイブ内のアイテムにアクセスするための要件」セクションを参照してください。.
    
- これまで説明すると、10 GB がユーザーのアーカイブをプライマリ メールボックスの記憶域のクォータに追加されます (回復可能なアイテム] フォルダーに、メールボックスが存在する場合を保持) とコマンドを実行する**を有効にするメールボックスの AutoExpandingArchive**です。自動拡張記憶域を準備する (これは最大で 30 日間がかかることができます) になるまで、追加の記憶域を提供します。この追加の記憶域は、組織内のすべてのメールボックスのアーカイブを自動拡張を有効にする**セット OrganizationConfig AutoExpandingArchive**を実行するときに追加されません。アーカイブを組織全体については、自動拡張が有効になって、10 GB の追加の特定のユーザーの記憶域を追加する必要がある場合は、そのメールボックスに**メールボックスが有効にする AutoExpandingArchive**コマンドを実行できます。アーカイブの自動拡張が既に有効になって、ですが、追加のストレージ領域は、メールボックスに追加することを示すエラーが発生することに注意してください。 
