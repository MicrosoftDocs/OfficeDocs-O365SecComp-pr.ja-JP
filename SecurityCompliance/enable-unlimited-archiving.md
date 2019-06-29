---
title: Office 365 で無制限アーカイブを有効にする - 管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: '管理者向け: Exchange Online メールボックスで無制限の記憶領域をユーザーに提供する、Office 365 での自動拡張アーカイブを有効にする方法について説明します。 組織全体に対し、または特定のユーザーだけに対し、自動拡張アーカイブを有効にすることができます。'
ms.openlocfilehash: a6f1e0e43854372b2c7b93c22c1160a7c555a95f
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154749"
---
# <a name="enable-unlimited-archiving-in-office-365---admin-help"></a>Office 365 で無制限アーカイブを有効にする - 管理者向けヘルプ

Office 365 の Exchange Online 自動拡張アーカイブ機能を使用して、アーカイブ メールボックスで無制限の記憶領域を有効化できます。 自動拡張アーカイブが有効になっている場合、ユーザーのアーカイブ メールボックスが容量の上限に近づくと、追加の記憶領域が自動的に追加されます。 無制限のメールボックス記憶容量が提供されます。 組織の全ユーザーに対し、または特定のユーザーだけに対し、自動拡張アーカイブを有効にすることができます。 自動拡張アーカイブの詳細については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。

## <a name="before-you-begin"></a>始める前に

- 組織全体または特定のユーザーの自動拡張アーカイブを有効にするには、Office 365 組織の全体管理者であるか、または Exchange Online 組織の組織管理役割グループのメンバーである必要があります。 または、特定のユーザーに対する自動拡張アーカイブを有効にするには、メール受信者の役割を割り当てられた役割グループのメンバーである必要があります。
    
- 自動拡張アーカイブを有効にする前に、ユーザーのアーカイブ メールボックスを有効にする必要があります。 アーカイブ メールボックスを有効にするには、ユーザーに Exchange Online プラン 2 のライセンスが割り当てられている必要があります。 ユーザーに Exchange Online プラン 1 のライセンスが割り当てられている場合、アーカイブ メールボックスを有効にするには、別の Exchange Online アーカイブ ライセンスを割り当てる必要があります。 「[セキュリティ/コンプライアンス センターでアーカイブ メールボックスを有効にする](enable-archive-mailboxes.md)」を参照してください。
    
- PowerShell を使って、アーカイブ メールボックスを有効にすることもできます。 組織内のすべてのユーザーのアーカイブ メールボックスを有効するために使用できる PowerShell コマンドの例については、「[詳細情報](#more-information)」セクションを参照してください。 
    
- アーカイブの自動拡張では、共有メールボックスもサポートされます。 共有メールボックスのアーカイブを有効にするには、Exchange Online プラン 2 のライセンス、または Exchange Online Archiving のライセンスの付いた Exchange Online プラン 1 のライセンスが必要です。
    
- Exchange 管理センターまたはセキュリティ/コンプライアンスセンターを使用して自動拡張アーカイブを有効にすることはできません。 Exchange Online PowerShell を使用する必要があります。 リモート PowerShell を使って Exchange Online 組織に接続する方法については、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>自動拡張アーカイブを組織全体で有効にする

組織全体の自動拡張アーカイブを有効にすることができます。 いったん有効にすると、既存ユーザーのメールボックスと、作成される新規ユーザーのメールボックスに対し、自動拡張アーカイブが有効になります。 新しいユーザー メールボックスを作成するときは、自動拡張アーカイブ機能が新しいユーザー メールボックスで機能するように、ユーザーのメイン アーカイブ メールボックスを有効にする必要があります。
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 自動拡張アーカイブを組織全体で有効にするには、Exchange Online PowerShell で次のコマンドを実行します。

    ```
    Set-OrganizationConfig -AutoExpandingArchive
    ```
  
## <a name="enable-auto-expanding-archiving-for-specific-users"></a>自動拡張アーカイブを特定のユーザーに対して有効にする

組織内のすべてのユーザーの自動拡張アーカイブを有効にするのではなく、特定のユーザーについてだけ有効にできます。 大容量のアーカイブ記憶領域を必要とするのが一部のユーザーのみの場合に、この方法を使用します。
  
特定のユーザーに対して自動拡張アーカイブを有効にした場合で、ユーザーのメールボックスが保留中であるか Office 365 保持ポリシーに割り当てられている場合、次の 2 つの構成変更が行われます。
  
- ユーザーのプライマリ アーカイブ メールボックスの記憶領域のクォータが 10 GB 増加します (100 GB から 110 GB へ)。 また、アーカイブの警告クォータも 10 GB 増加します (90 GB から 100 GB へ)。
    
- ユーザーのプライマリ メールボックスの [回復可能なアイテム] フォルダーの記憶領域のクォータは、10 GB 増加します (100 GB から 110 GB へ)。 回復可能なアイテムの警告クォータも、10 GB 増加します (90 GB から 100 GB へ)。 これらの変更は、メールボックスが保留中の場合、または Office 365 のアイテム保持ポリシーに割り当てられている場合にのみ適用されます。
    
この追加容量は、自動拡張アーカイブのプロビジョニングが行われる前に発生する可能性がある記憶領域の問題を防ぐために追加されるものです。 前のセクションで説明したように、自動拡張アーカイブを組織全体に対して有効にする場合は、追加記憶領域は追加*されない*ことに注意してください。 
  
1. [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. 自動拡張アーカイブを特定のユーザーに対して有効にするには、次の PowerShell コマンドを実行します。 前述のように、ユーザーの自動拡張アーカイブを有効にする前に、そのユーザーのアーカイブ メールボックス (メイン アーカイブ) を有効にしておく必要があります。
    
    ```
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> Exchange ハイブリッド展開では、ユーザーのプライマリメールボックスがオンプレミスにあり、かつアーカイブ メールボックスがクラウド ベースの特定のユーザーについては、**Enable-Mailbox -AutoExpandingArchive** コマンドを使用して自動拡張アーカイブを有効にすることはできません。 クラウド ベースのアーカイブ メールボックスの自動拡張アーカイブを Exchange ハイブリッド展開で有効にするには、Exchange Online PowerShell で **Set-OrganizationConfig -AutoExpandingArchive** コマンドを実行して、組織全体に対して自動拡張アーカイブを有効にする必要があります。 ユーザーのプライマリ メールボックスとアーカイブ メールボックスが両方ともクラウド ベースの場合は、**Enable-Mailbox -AutoExpandingArchive** コマンドを使用してそのユーザーに対して自動拡張アーカイブを有効にできます。 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>自動拡張アーカイブが有効になっていることを確認する

自動拡張アーカイブが組織に対して有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。

```
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

値 `True` は、自動拡張アーカイブが組織に対して有効になっていることを示します。 
  
自動拡張アーカイブが特定のユーザーに対して有効になっていることを確認するには、Exchange Online PowerShell で次のコマンドを実行します。
  
```
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```
値 `True` は、自動拡張アーカイブがそのユーザーに対して有効になっていることを示します。 
  
自動拡張アーカイブを有効にした後は、次の点に注意してください。
  
- **Set-OrganizationConfig -AutoExpandingArchive** コマンドを実行して自動拡張アーカイブを組織に対して有効化する場合は、個々のメールボックスに対して **Enable-Mailbox -AutoExpandingArchive** を実行する必要はありません。 **Set-OrganizationConfig** コマンドレットを実行して組織の自動拡張アーカイブを有効にしても、ユーザー メールボックスの *AutoExpandingArchiveEnabled* プロパティは `True` に変わらないことにご注意ください。
    
- 同様に、自動拡張アーカイブを有効にしても、メールボックスの *ArchiveQuota* プロパティと *ArchiveWarningQuota* プロパティの値も変更されません。 実際、ユーザー メールボックスの自動拡張アーカイブを有効にして、*AutoExpandingArchiveEnabled* プロパティを `True` に設定している場合、*ArchiveQuota* プロパティと *ArchiveWarningQuota* プロパティは無視されます。 ユーザーのメールボックスの自動拡張アーカイブを有効にした後のこれらのメールボックス プロパティの例を示します。 
    
    ![自動拡張アーカイブを有効にした後、ArchiveQuota と ArchiveWarningQuota プロパティは無視されます。](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>詳細情報

- PowerShell を使って、アーカイブ メールボックスを有効にすることもできます。 たとえば、Exchange Online PowerShell で次のコマンドを実行して、アーカイブ メールボックスがまだ有効になっていないすべてのユーザーのアーカイブ メールボックスを有効にできます。

    ```
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- 組織または特定のユーザーに対して自動拡張アーカイブを有効にした後、アーカイブ メールボックス ([回復可能なアイテム] フォルダーを含む) が 90 GB に達すると、アーカイブ メールボックスは自動拡張アーカイブに変換されます。 追加記憶領域がプロビジョニングされるには、最大 30 日かかります。
    
- 自動拡張アーカイブを有効にした後は、無効にすることはできません。
    
- 自動拡張アーカイブは、オンプレミスのプライマリメールボックスを持つユーザーについて、Exchange ハイブリッド展開のクラウド ベースのアーカイブ メールボックスでサポートされています。 ただし、クラウド ベースのアーカイブ メールボックスに対して自動拡張アーカイブを有効にした後は、そのアーカイブ メールボックスをオフボードしてオンプレミスの Exchange 組織に戻すことはできません。 Exchange Server 2010 のオンプレミスのメールボックスでは、自動拡張アーカイブはサポートされていません。
    
- アーカイブ メールボックスの追加記憶領域内のアイテムにアクセスするためにユーザーが使用できる Outlook クライアントの一覧については、「[Office 365 での無制限アーカイブの概要](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)」の「自動拡張アーカイブ内のアイテムにアクセスするための Outlook の要件」セクションをご覧ください。
    
- 前述のように、**Enable-Mailbox -AutoExpandingArchive** コマンドを実行すると、ユーザーのプライマリ アーカイブ メールボックス (および、メールボックスが保留中の場合は、[回復可能なアイテム] フォルダー) の記憶領域のクォータ に 10 GB が追加されます。 これにより、自動拡張記憶領域がプロビジョニングされるまで (最大で30 日間かかります)、追加の記憶領域が提供されます。 **Set-OrganizationConfig -AutoExpandingArchive** を実行して組織のすべてのメールボックスに対して自動拡張アーカイブを有効化した場合は、追加記憶領域は追加されません。 自動拡張アーカイブを組織全体に対して有効化した場合でも、特定のユーザーの記憶領域に 10 GB を追加する必要がある場合は、そのメールボックスに対して **Enable-Mailbox -AutoExpandingArchive** コマンドを実行できます。 自動拡張アーカイブが既に有効化されているというエラー メッセージが表示されますが、メールボックスには追加記憶領域が追加されます。 

- 管理者は、記憶領域のクォータを調整できません。

> [!IMPORTANT]
> 自動拡張アーカイブがサポートされているのは、個々のユーザーのメールボックスまたは 1 日あたりの成長率が 1 GB 未満の共有メールボックスのみです。 アーカイブ目的のために、ジャーナリング、トランスポート ルール、または自動転送ルールを使用してメッセージをアーカイブ メールボックスにコピーすることは許可されていません。 ユーザーのアーカイブ メールボックスは、そのユーザー専用です。 Microsoft は、ユーザーのアーカイブ メールボックスを使用して他のユーザーのアーカイブ データを格納する、インスタンスでの無制限アーカイブを拒否する権利を有します。
