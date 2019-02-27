---
title: Office 365 で非アクティブなメールボックスを復元する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 新しい従業員または別のユーザーが Office 365 の非アクティブなメールボックスのコンテンツにアクセスする必要がある場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (またはマージ) することができます。
ms.openlocfilehash: fa3572ef34a905ae2216672ed42507f0c712accb
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296620"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>Office 365 で非アクティブなメールボックスを復元する

非アクティブなメールボックス (回復可能な削除によって削除されたメールボックスの一種) は、元従業員が組織を離れた後に、その電子メールを保持するために使用されます。別の従業員が退職した従業員の職責を引き継ぐ場合、またはその従業員が組織に復帰する場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。 
  
- **非アクティブなメールボックスを復元する** 退職した従業員の職務を別の従業員が引き継ぐ場合や、非アクティブなメールボックスのコンテンツに別のユーザーがアクセスすることが必要な場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。非アクティブなメールボックスからアーカイブを復元することもできます。復元された後も、非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして保存されます。このトピックでは、非アクティブなメールボックスを復元するための手順について説明します。 
    
- **非アクティブなメールボックスを回復する**退職した従業員が組織に戻った場合、または新しい従業員が退職した従業員の職務に採用された場合は、非アクティブなメールボックスの内容を復元できます。この方法では、非アクティブなメールボックスを、非アクティブなメールボックスのコンテンツが含まれる新しいメールボックスに変換します。回復された後、非アクティブなメールボックスは存在しなくなります。詳細な手順については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。
    
非アクティブなメールボックスの復元と回復の違いの詳細については、この記事の「**詳細情報**」セクションを参照してください。 
  
## <a name="before-you-begin"></a>はじめに

- 非アクティブなメールボックスを復元するには、Exchange Online PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。
    
- Exchange Online PowerShell で次のコマンドを実行して、組織内の非アクティブなメールボックスの id 情報を取得します。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを復元します。
    
- 非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。
    
## <a name="restore-an-inactive-mailbox"></a>非アクティブなメールボックスを復元する

**New-MailboxRestoreRequest** コマンドレットを  _SourceMailbox_ と  _TargetMailbox_ パラメーターと共に使用して、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。このコマンドレットの使用方法について詳しくは、「 [New-MailboxRestoreRequest](https://go.microsoft.com/fwlink/?linkid=856298)」を参照してください。
  
1. 非アクティブなメールボックスのプロパティを含む変数を作成します。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。 
  
2. 非アクティブなメールボックスのコンテンツを既存のメールボックスに復元します。非アクティブなメールボックス (ソース メールボックス) のコンテンツは、既存のメールボックス (ターゲット メールボックス) の対応するフォルダーにマージされます。
    
    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
    ```
   
   または、非アクティブなメールボックスのコンテンツの復元先として、ターゲット メールボックス内の最上位フォルダーを指定することもできます。指定したターゲット フォルダーまたはターゲット フォルダー構造がターゲット メールボックス内に存在しない場合は、復元処理中に作成されます。 
    
    次の使用例は、非アクティブなメールボックス内のメールボックス アイテムとサブフォルダーを、ターゲット メールボックスの最上位フォルダー構造内にある「Inactive Mailbox」という名前のフォルダーにコピーします。
    
   ```
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```
  
## <a name="restore-the-archive-from-an-inactive-mailbox"></a>非アクティブなメールボックスからアーカイブを復元する

非アクティブなメールボックスにアーカイブ メールボックスがある場合も、それを既存のメールボックスのアーカイブ メールボックスに復元できます。非アクティブなメールボックスからアーカイブを復元するには、 _SourceIsArchive_ と  _TargetIsAchive_ スイッチを、非アクティブなメールボックスの復元に使用するコマンドに追加する必要があります。 
  
1. 非アクティブなメールボックスのプロパティを含む変数を作成します。 
    
    ```
    $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
    ```

    > [!IMPORTANT]
    > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGUID** プロパティの値を使用して非アクティブなメールボックスを識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと非アクティブなメールボックスとでプライマリ SMTP アドレスが等しい可能性があります。 
  
2. アーカイブのコンテンツを、非アクティブなメールボックス (ソース アーカイブ) から既存のメールボックスのアーカイブ (ターゲット アーカイブ) に復元します。この例では、ソース アーカイブのコンテンツが、ターゲット メールボックスのアーカイブ内の「Inactive Mailbox Archive」という名前のフォルダーにコピーされます。

    ```
    New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
    ```

  
## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスの回復と復元の主な違いは何ですか。** 非アクティブなメールボックスを回復する場合、メールボックスは基本的に新しいメールボックスに変換され、非アクティブなメールボックスのコンテンツとフォルダーの構造は保持され、メールボックスは新しいユーザーアカウントにリンクされます。回復後、非アクティブなメールボックスは存在しなくなり、新しいメールボックス内のコンテンツに加えられた変更は、非アクティブなメールボックスで元のまま保持されていたコンテンツに影響します。逆に、非アクティブなメールボックスを復元すると、コンテンツは単に別のメールボックスにコピーされます。非アクティブなメールボックスは保持され、非アクティブなメールボックスとして残ります。ターゲットメールボックス内のコンテンツに加えられた変更は、非アクティブなメールボックスに格納されている元のコンテンツに影響しません。非アクティブなメールボックスは、Office 365 セキュリティ&amp;コンプライアンスセンターの[コンテンツ検索ツール](run-a-content-search-in-the-security-and-compliance-center.md)を使用して検索することも、そのコンテンツを別のメールボックスに復元することも、後で回復または削除することもできます。 
    
- **非アクティブなメールボックスを見つける方法。** 組織内の非アクティブなメールボックスの一覧を取得して、非アクティブなメールボックスを復元するために役立つ情報を表示するには、次のコマンドを実行できます。 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **訴訟ホールドまたは Office 365 アイテム保持ポリシーを使用して非アクティブなメールボックスのコンテンツを保持する。** 非アクティブなメールボックスを復元した後にその状態を保持する場合は、非アクティブなメールボックスを復元する前に、ターゲット メールボックスを [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) に設定するか、または [Office 365 アイテム保持ポリシー](retention-policies.md)を適用することができます。これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。 
    
- **非アクティブなメールボックスを復元する前に、ターゲットメールボックスでの保存機能を有効にします。** 非アクティブなメールボックスからのメールボックスアイテムは古くなっている可能性があるため、非アクティブなメールボックスを復元する前に、ターゲットメールボックスで保存機能を有効にすることを検討してください。メールボックスの保存機能を有効にすると、そのメールボックスに割り当てられているアイテム保持ポリシーは、保存機能が削除されるか、保存期間の期限が切れるまで処理されません。これにより、ターゲットメールボックスの所有者に、非アクティブなメールボックスからの古いメッセージを管理する時間が与えられます。それ以外の場合、アイテム保持ポリシーは、ターゲットメールボックスに対して構成された保持設定に基づいて期限切れになった古いアイテムを削除するか (または、有効になっている場合はアーカイブメールボックスにアイテムを移動する) 可能性があります。詳細については、「 [Exchange Online でメールボックスを保持ホールドの状態にする](https://go.microsoft.com/fwlink/?linkid=856300)」を参照してください。
    
- **AllowLegacyDNMismatch スイッチの機能。** 非アクティブなメールボックスを復元する前述の例では、 **AllowLegacyDNMismatch** スイッチの使用によって、非アクティブなメールボックスを別のターゲット メールボックスに復元できるようになります。一般的な復元シナリオでは、ソース メールボックスとターゲット メールボックスが同じメールボックスのときに、コンテンツを復元することが目標となります。そのため既定では、 **New-MailboxRestoreRequest** コマンドレットにより、ソース メールボックスとターゲット メールボックスの **LegacyExchangeDN** プロパティの値が同じであることが確認されます。これにより、ソース メールボックスが誤って正しくないターゲット メールボックスに復元されることを防止します。 **AllowLegacyDNMismatch** スイッチを使用しないで非アクティブなメールボックスの復元を試行すると、ソース メールボックスとターゲット メールボックスで **LegacyExchangeDN** プロパティの値が異なる場合に、コマンドは失敗する可能性があります。 
    
- **New-MailboxRestoreRequest コマンドレットと共に他のパラメーターを使用して、非アクティブなメールボックスのさまざまな復元シナリオを実装できます。** たとえば、次のコマンドを実行して、非アクティブなメールボックスからターゲット メールボックスのプライマリ メールボックスにアーカイブを復元できます。 
    
  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  また次のコマンドを実行して、非アクティブなプライマリ メールボックスをターゲット メールボックスのアーカイブに復元することもできます。

  ```
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **TargetRootFolder パラメーターの機能。** 前述のように、 **TargetRootFolder** パラメーターを使用して、非アクティブなメールボックスのコンテンツを復元するためにターゲット メールボックス内のフォルダー構造の最上位フォルダー ( ルートとも呼ばれる) を指定できます。このパラメーターを使用しない場合、非アクティブなメールボックスのメールボックス アイテムはターゲット メールボックスの対応する既定のフォルダーにマージされ、カスタム フォルダーがターゲット メールボックスのルートに再作成されます。次の図は、 **TargetRootFolder** パラメーターを使用しない場合と使用する場合の、これらの相違点を強調しています。 
    
    **TargetRootFolder パラメーターを使用しない場合の、ターゲット メールボックス内のフォルダー階層**
    
    ![TargetRootFolder パラメーターを使用していないときのスクリーン ショット](media/76a759af-f483-4d1c-8cc7-243435b5562e.png)
  
    **TargetRootFolder パラメーターを使用する場合の、ターゲット メールボックス内のフォルダー階層**
    
    ![TargetRootFolder パラメーターが使用されているときのスクリーン ショット](media/300da592-7323-48db-b8a4-07012259d113.png)

  

