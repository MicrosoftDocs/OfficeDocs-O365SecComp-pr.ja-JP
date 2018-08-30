---
title: Office 365 で、非アクティブなメールボックスを復元します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/28/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: 新入社員や他のユーザーは、Office 365 で、非アクティブなメールボックスの内容へのアクセスを必要とする場合することができます復元 (またはマージ) 使用頻度の低い既存のメールボックスにメールボックスの内容です。
ms.openlocfilehash: e0add2b63a48edc27795143324c83153b15dcf8c
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531624"
---
# <a name="restore-an-inactive-mailbox-in-office-365"></a>Office 365 で、非アクティブなメールボックスを復元します。

非アクティブなメールボックス (回復可能な削除によって削除されたメールボックスの一種) は、元従業員が組織を離れた後に、その電子メールを保持するために使用されます。別の従業員が退職した従業員の職責を引き継ぐ場合、またはその従業員が組織に復帰する場合には、非アクティブなメールボックスのコンテンツをユーザーが使用できるようにする 2 つの方法があります。 
  
- **非アクティブなメールボックスを復元する** 退職した従業員の職務を別の従業員が引き継ぐ場合や、非アクティブなメールボックスのコンテンツに別のユーザーがアクセスすることが必要な場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (または マージ) できます。非アクティブなメールボックスからアーカイブを復元することもできます。復元された後も、非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして保存されます。このトピックでは、非アクティブなメールボックスを復元するための手順について説明します。 
    
- **非アクティブなメールボックスのリカバリ**組織では、ゲーム終了者の従業員が返された場合、またはゲーム終了者の従業員の業務上の責任で実行する新しい従業員が採用された場合は、非アクティブなメールボックスの内容を回復できます。このメソッドは、アクティブでないメールボックスを非アクティブなメールボックスの内容を含む新しいメールボックスに変換します。を修復した後、非アクティブなメールボックスは存在しません。ステップ バイ ステップの手順では、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。
    
復元して、アクティブでないメールボックスを回復するとの違いの詳細については、この資料の**詳細について**はを参照してください。 
  
## <a name="before-you-begin"></a>はじめに

- アクティブでないメールボックスを復元する Exchange のオンライン PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)を参照してください。
    
- 次のコマンドを実行 Exchange オンライン組織内の非アクティブなメールボックスの id 情報を取得する PowerShell。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly | FL Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
    ```

     このコマンドによって返される情報を使用して、特定の非アクティブなメールボックスを復元します。
    
- 非アクティブなメールボックスの詳細については、 [Office 365 でアクティブでないメールボックス](inactive-mailboxes-in-office-365.md)を参照してください。
    
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

- **をリカバリして、アクティブでないメールボックスを復元するには大きな違いは何ですか?** 非アクティブなメールボックスをリカバリする場合は、メールボックスを新しいメールボックスに変換されます基本的と内容と非アクティブなメールボックスのフォルダー構造は保持されますが、メールボックスを新しいユーザー アカウントにリンクします。リカバリ後、非アクティブなメールボックスが存在しない、新しいメールボックスの内容に加えられた変更がコンテンツに接続されていたことに影響を与える非アクティブなメールボックスに保持します。逆に、非アクティブなメールボックスを復元する場合、別のメールボックスには、内容はコピーだけで。非アクティブなメールボックスは保持され、非アクティブなメールボックスのまま。移動先のメールボックス内のコンテンツに加えられた変更は、非アクティブなメールボックスに保持されている元のコンテンツに影響しません。非アクティブなメールボックスを Office 365 のセキュリティ[コンテンツの検索ツール](run-a-content-search-in-the-security-and-compliance-center.md)を使用して検索もできる&amp;コンプライアンス センターでは、別のメールボックスにその内容を復元することができますまたは回復または後で削除できます。 
    
- **非アクティブなメールボックスを見つける方法。** 組織内の非アクティブなメールボックスの一覧を取得して、非アクティブなメールボックスを復元するために役立つ情報を表示するには、次のコマンドを実行できます。 

  ```
  Get-Mailbox -InactiveMailboxOnly | FL Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **訴訟ホールドまたは Office 365 アイテム保持ポリシーを使用して非アクティブなメールボックスのコンテンツを保持する。** 非アクティブなメールボックスを復元した後にその状態を保持する場合は、非アクティブなメールボックスを復元する前に、ターゲット メールボックスを [Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286) に設定するか、または [Office 365 アイテム保持ポリシー](retention-policies.md)を適用することができます。これにより、非アクティブなメールボックスのアイテムがターゲット メールボックスに復元された後に、完全に削除されることがなくなります。 
    
- **、アクティブでないメールボックスを復元する前に移動先のメールボックスの保存を有効にするを保持します**。非アクティブなメールボックスからメールボックスのアイテムが古い可能性があります、ため、非アクティブなメールボックスを復元する前に、移動先のメールボックスに保持を有効にすることを検討する可能性があります。配置すると、保存上のメールボックスを保持、リテンション ・ ポリシーに割り当てられているは、保持を削除または保存管理機能を保持するまでには、期間が満了するまで処理されません。ターゲット メールボックス時間の非アクティブなメールボックスから古いメッセージを管理するための所有者を示します。それ以外の場合、リテンション ・ ポリシーがあります古いアイテムを削除 (または有効になっている場合は、アーカイブ メールボックスにアイテムを移動) 移動先のメールボックスに対して構成されている保存期間の設定に基づいて期限切れです。詳細については、 [Exchange オンラインを保持保持上のメールボックスの場所](https://go.microsoft.com/fwlink/?linkid=856300)を参照してください。
    
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

  

