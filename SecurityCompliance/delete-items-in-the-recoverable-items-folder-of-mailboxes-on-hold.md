---
title: クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: '管理者の場合: Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除します (法的情報保留に設定されている場合も含む)。 これは、Office 365 に誤ってこぼれたデータを削除する効果的な方法です。'
ms.openlocfilehash: 7badd45f582e4d5fef4cb5708c504573da0aba50
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000080"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>クラウドベースのメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除する-管理者向けヘルプ

Exchange Online メールボックスの回復可能なアイテムフォルダーは、偶発的または悪意のある削除から保護するために存在します。 また、保存されていて、Office 365 コンプライアンス機能 (保留や電子情報開示の検索など) によってアクセスされるアイテムを格納するためにも使用されます。 ただし、状況によっては、削除する必要のある回復可能なアイテムフォルダーに誤って保持されていたデータが組織に存在する可能性があります。 たとえば、ユーザーが気付かないうちに機密情報や情報が含まれる電子メールメッセージを知らずに送信または転送することがあります。 メッセージが完全に削除された場合でも、メールボックスに法的情報保持が設定されているため、無期限に保持される可能性があります。 このシナリオは、データが Office 365 に誤って含まれていたため、データ流出と呼ばれます。 このような状況では、Exchange Online メールボックスのユーザーの回復可能なアイテムフォルダーのアイテムを削除することができます。これは、Office 365 のさまざまな保留機能のいずれかを使用して、そのメールボックスが保持されている場合でも削除できます。 これらの種類には、office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成された訴訟ホールド、インプレースホールド、電子情報開示の保持、および office 365 アイテム保持ポリシーがあります。
  
 この記事では、保留中のクラウドベースのメールボックスの [回復可能なアイテム] フォルダーからアイテムを削除する方法について説明します。 この手順では、メールボックスへのアクセスを無効にし、単一アイテムの回復を無効にし、管理フォルダーアシスタントを無効にして、メールボックスの処理を一時的に解除し、回復可能なアイテムフォルダーからアイテムを削除してから、元に戻す必要があります。メールボックスを以前の構成に設定します。 プロセスは次のとおりです。 
  
[手順 1: メールボックスに関する情報を収集する](#step-1-collect-information-about-the-mailbox)

[手順 2: メールボックスを準備する](#step-2-prepare-the-mailbox)

[手順 3: メールボックスからすべての保留リストを削除する](#step-3-remove-all-holds-from-the-mailbox)

[手順 4: メールボックスから遅延保持を削除する](#step-4-remove-the-delay-hold-from-the-mailbox)

[手順 5: 回復可能なアイテムフォルダーのアイテムを削除する](#step-5-delete-items-in-the-recoverable-items-folder)

[手順 6: メールボックスを以前の状態に戻す](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> この記事に記載されている手順により、Exchange Online メールボックスからデータが完全に削除 (パージ) されます。 これは、回復可能なアイテムフォルダーから削除されたメッセージを回復できず、法的証拠開示やその他の法令遵守のために利用できないことを意味します。 セキュリティ/コンプライアンスセンターで作成された訴訟ホールド、インプレースホールド、電子情報開示のホールド、または Office 365 アイテム保持ポリシーの一部として保留になっているメールボックスからメッセージを削除する場合は、レコード管理または法務部門に確認してください。保留リストを削除する前。 組織には、保留中のメールボックスとデータ流出インシデントのどちらを優先するかを定義するポリシーがあります。 
  
## <a name="before-you-begin"></a>はじめに

- 手順5で [回復可能なアイテム] フォルダーからメッセージを検索して削除するには、Exchange Online の次の両方の管理役割を割り当てられている必要があります。
    
  - **メールボックス検索**-この役割を使用すると、組織内のメールボックスを検索できます。 既定では、Exchange 管理者はこの役割を割り当てられていません。 この役割を自分自身に割り当てるには、Exchange Online の "Discovery Management/検出の管理" 役割グループのメンバーとして自分自身を追加します。 
    
  - **メールボックスインポートエクスポート**-この役割を使用すると、ユーザーのメールボックスからメッセージを削除することができます。 既定では、この役割はどの役割グループにも割り当てられていません。 ユーザーのメールボックスからメッセージを削除するには、Exchange Online の組織の管理役割グループに、メールボックスのインポートの役割を追加します。 
    
- この記事で説明する手順は、非アクティブなメールボックスではサポートされていません。 これは、削除した後、非アクティブなメールボックスに保留 (または Office 365 アイテム保持ポリシー) を再適用できないためです。 非アクティブなメールボックスからホールドを削除すると、その保留中のメールボックスは通常の回復可能な削除によって削除され、管理フォルダーアシスタントによる処理後は組織から完全に削除されます。
    
- 保持ロックでロックされている Office 365 アイテム保持ポリシーに割り当てられているメールボックスに対して、この手順を実行することはできません。 これは、保持ロックによって、Office 365 アイテム保持ポリシーからメールボックスを削除または除外したり、メールボックス上の管理フォルダーアシスタントを無効にしたりすることができないためです。 保持ポリシーのロックの詳細については、「[アイテム保持ポリシーのロック](retention-policies.md#locking-a-retention-policy)」を参照してください。
    
- メールボックスが保持されていない (または単一アイテムの回復が有効になっていない) 場合は、単に回復可能なアイテムフォルダーからアイテムを削除することができます。 これを行う方法の詳細については、「[メッセージを検索して削除](https://go.microsoft.com/fwlink/?linkid=852453)する」を参照してください。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>手順 1: メールボックスに関する情報を収集する

最初の手順では、この手順に影響する、ターゲットメールボックスから選択したプロパティを収集します。 これらのプロパティの一部を変更し、[回復可能なアイテム] フォルダーからアイテムを削除した後に、手順6で元の値に戻すことができるように、これらの設定を書き留めておくか、テキストファイルに保存してください。 収集する必要があるメールボックスのプロパティの一覧を次に示します。
  
-  *singleitemrecoveryenabled*および*RetainDeletedItemsFor* ;必要に応じて、1回の回復を無効にして、手順3で削除済みアイテムの保存期間を延長します。 
    
-  *LitigationHoldEnabled*および*InPlaceHolds* ;手順3で一時的に削除できるように、メールボックスに配置されているすべての保留リストを識別する必要があります。 メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。 
    
また、この手順の実行中に所有者 (または他のユーザー) がメールボックスにアクセスできないように、メールボックスクライアントアクセスの設定を取得する必要があります。 最後に、[回復可能なアイテム] フォルダー内のアイテムの現在のサイズと数を取得することができます。 手順5で [回復可能なアイテム] フォルダー内のアイテムを削除した後、この情報を使用してアイテムが実際に削除されたことを確認します。
  
1. [Exchange Online PowerShell に接続します](https://go.microsoft.com/fwlink/?linkid=396554)。 Exchange Online で適切な管理役割が割り当てられている管理者アカウントには、必ずユーザー名とパスワードを使用してください。 
    
2. 単一アイテムの回復と削除済みアイテムの保存期間に関する情報を取得するには、次のコマンドを実行します。

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   単一アイテムの回復が有効になっている場合は、手順2で無効にする必要があります。 削除済みアイテムの保存期間が30日間 (Exchange Online の最大値) に設定されていない場合は、手順2で増やすことができます。 
    
3. 次のコマンドを実行して、メールボックスのメールボックスアクセス設定を取得します。 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   手順2では、これらのアクセス方法をすべて無効にします。
    
4. 次のコマンドを実行して、メールボックスに適用されている保留リストと Office 365 アイテム保持ポリシーに関する情報を取得します。
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > *InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。 
  
5. 組織全体の Office 365 保持ポリシーに関する情報を取得するには、次のコマンドを実行します。 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   組織全体で Office 365 のアイテム保持ポリシーを使用している場合は、手順3でこれらのポリシーからメールボックスを除外する必要があります。

   > [!TIP]
    > *InPlaceHolds*プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行してそれぞれの値を別々の行に表示することができます。 
  
6. 次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   ユーザーのアーカイブメールボックスが有効になっている場合は、次のコマンドを実行して、アーカイブメールボックス内の [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   手順5でアイテムを削除する場合、ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムを削除するか、削除するかを選択できます。 メールボックスに対して自動拡張アーカイブが有効になっている場合、補助アーカイブメールボックス内のアイテムは削除されないことに注意してください。
  
## <a name="step-2-prepare-the-mailbox"></a>手順 2: メールボックスを準備する

メールボックスに関する情報を収集して保存した後、次の手順では、次のタスクを実行してメールボックスを準備します。 
  
- メールボックス**へのクライアントアクセスを無効**にして、メールボックスの所有者がメールボックスにアクセスできないようにして、この手順の実行中にメールボックスデータを変更しないようにします。 
    
- **削除済みアイテムの保存期間**を30日間 (Exchange Online の最大値) に増やして、手順5でアイテムを回復可能なアイテムフォルダーから削除されないようにします。 
    
- 手順5で [回復可能なアイテム] フォルダーからアイテムを削除した後に、アイテムが保持されないように、**単一アイテムの回復を無効**にします (削除済みアイテムの保存期間中)。 
    
- **管理フォルダーアシスタントを無効**にして、メールボックスが処理されず、手順5で削除されたアイテムを保持するようにします。 
    
Exchange Online PowerShell で次の手順を実行します。
  
1. 次のコマンドを実行して、メールボックスへのすべてのクライアントアクセスを無効にします。 コマンド構文では、すべてのクライアントアクセスメソッドがメールボックスで有効になっていることを前提としています。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > メールボックスへのすべてのクライアントアクセス方法を無効にするには、最大60分かかる場合があります。 これらのアクセス方法を無効にしても、現在サインインしているメールボックスの所有者が切断されることに注意してください。 所有者がサインインしていない場合、これらのアクセス方法を無効にした後はメールボックスにアクセスできなくなります。 
  
2. 次のコマンドを実行して、削除済みアイテムの保存期間を最大で30日に増やします。 これは、現在の設定が30日未満であることを前提としています。 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 次のコマンドを実行して、単一アイテムの回復を無効にします。
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 単一アイテムの回復を無効にするには、最大60分かかる場合があります。 この期間が経過するまで、[回復可能なアイテム] フォルダー内のアイテムを削除しないでください。 
  
4. 管理フォルダーアシスタントがメールボックスを処理できないようにするには、次のコマンドを実行します。 前述したように、保持ロックが設定された Office 365 アイテム保持ポリシーがメールボックスに適用されていない場合にのみ、管理フォルダーアシスタントを無効にすることができます。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>手順 3: メールボックスからすべての保留リストを削除する

回復可能なアイテムフォルダーからアイテムを削除する前の最後の手順は、メールボックスに配置されたすべてのホールド (手順1で特定した) を削除することです。 [回復可能なアイテム] フォルダーからアイテムを削除した後は、アイテムが保持されないように、すべての保留リストを削除する必要があります。 次のセクションでは、メールボックスにさまざまな種類の保留リストを削除する方法について説明します。 メールボックスに配置される可能性のある型保持を特定する方法については、「[詳細情報](#more-information)」セクションを参照してください。 詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。
  
> [!CAUTION]
> 前述したように、メールボックスから保留リストを削除する前に、レコード管理または法務部門に確認してください。 
  
 ### <a name="litigation-hold"></a>訴訟ホールド
  
Exchange Online PowerShell で次のコマンドを実行して、メールボックスから訴訟ホールドを削除します。

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> クライアントアクセス方法と単一アイテムの回復を無効にする場合と同様に、訴訟ホールドを削除するには最大60分かかる場合があります。 この期間が経過するまで、[回復可能なアイテム] フォルダーからアイテムを削除しないでください。 
  
 ### <a name="in-place-hold"></a>インプレース ホールド
  
Exchange Online PowerShell で次のコマンドを実行して、メールボックスに配置されているインプレースホールドを識別します。 手順1で特定したインプレースホールドの GUID を使用します。 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
インプレースホールドを識別した後、exchange 管理センター (EAC) または exchange Online PowerShell を使用して、保留リストからメールボックスを削除できます。 詳細については、「[インプレース保持を作成または削除する](https://go.microsoft.com/fwlink/?linkid=852668)」を参照してください。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>特定のメールボックスに適用される Office 365 アイテム保持ポリシー
  
[Security & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用されている Office 365 アイテム保持ポリシーを特定します。 手順1で特定したアイテム`mbx`保持`skp`ポリシーの GUID (またはプレフィックスを含まない) を使用します。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
アイテム保持ポリシーを識別した後、Security & コンプライアンスセンターの [**ガバナンス** \> **** の日付に関するページ] に移動し、前の手順で識別したアイテム保持ポリシーを編集して、そのメールボックスを一覧からアイテム保持ポリシーに含まれている受信者。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>組織全体の Office 365 のアイテム保持ポリシー
  
組織全体および Exchange 全体の Office 365 保持ポリシーは、組織内のすべてのメールボックスに適用されます。 これらは、(メールボックスレベルではなく) 組織レベルで適用され、手順1で取得した組織レベルの**config**コマンドレットを実行したときに返されます。 [Security & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、組織全体の Office 365 アイテム保持ポリシーを特定します。 手順1で特定した組織`mbx`全体のアイテム保持ポリシーの GUID (プレフィックスを含まない) を使用します。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

組織全体の Office 365 アイテム保持ポリシーを特定した後、Security & コンプライアンスセンターの [**ガバナンス** \> **** の日付] ページに移動して、組織全体のアイテム保持ポリシーを編集します。前の手順を実行し、除外された受信者のリストにメールボックスを追加します。 この操作を行うと、ユーザーのメールボックスがアイテム保持ポリシーから削除されます。 

### <a name="office-365-retention-labels"></a>Office 365 保持ラベル

ユーザーがコンテンツを保持するように設定されているラベルを適用するか、メールボックス内のフォルダーまたはアイテムを保持した後にコンテンツを削除すると、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。 このような場合、メールボックスは、訴訟ホールドの対象として、または Office 365 アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。

*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

フォルダーまたはアイテムに保持ラベルが適用されているためにメールボックスが保留になっていることを確認したら、セキュリティ/コンプライアンスセンターのコンテンツ検索ツールを使用して、ComplianceTag の検索条件を使用してラベル付きアイテムを検索できます。 詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)」の「検索条件」セクションを参照してください。

ラベルの詳細については、「 [Office 365 ラベルの概要](labels.md)」を参照してください。

 ### <a name="ediscovery-case-holds"></a>電子情報開示ケースの保持
  
[Security & コンプライアンスセンターの PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)で次のコマンドを実行して、メールボックスに適用される電子情報開示ケースに関連付けられている保留リストを識別します。 手順1で特定した電子`UniH`情報開示ホールドの GUID (プレフィックスを含まない) を使用します。 2番目のコマンドには、保留が関連付けられている電子情報開示ケースの名前が表示されることに注意してください。3番目のコマンドは、保留の名前を表示します。 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

電子情報開示のケースとホールドの名前を特定したら、コンプライアンスセンターの [**電子情報** \> **開示電子情報開示**] ページに移動し、ケースを開き、保留リストからメールボックスを削除します。 詳細については、「[電子情報開示ケース](ediscovery-cases.md)」を参照してください。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>手順 4: メールボックスから遅延保持を削除する

メールボックスから何らかの種類の保留が解除されると、 *DelayHoldApplied* mailbox プロパティの値は**True**に設定されます。 これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。 これは*遅延ホールド*と呼ばれ、データがメールボックスから完全に削除されないようにするために、保留リストの実際の削除が30日間延期されることを意味します。 (遅延保持の目的は、保留が解除された後に削除されるメールボックスアイテムを、管理者が検索または復旧する機会を管理者に提供することです)。 メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。 30日後、遅延保持が有効期限切れになり、Office 365 は遅延保持を自動的に削除します ( *DelayHoldApplied*プロパティを**False**に設定する)。保留が実際に削除されるようにします。 

手順5でアイテムを削除する前に、メールボックスから遅延ホールドを削除する必要があります。 最初に、Exchange Online PowerShell で次のコマンドを実行して、遅延保持がメールボックスに適用されているかどうかを判断します。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

*DelayHoldApplied*プロパティの値が**False**に設定されている場合、遅延保持はメールボックスに配置されていません。 [回復可能なアイテム] フォルダー内のアイテムを削除するには、手順5に進みます。

*DelayHoldApplied*プロパティの値が**True**に設定されている場合は、次のコマンドを実行して遅延保持を削除します。

```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
*RemoveDelayHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があることに注意してください。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>手順 5: 回復可能なアイテムフォルダーのアイテムを削除する

これで、Exchange Online の PowerShell で[検索-メールボックス](https://go.microsoft.com/fwlink/?linkid=852595)コマンドレットを使用して、回復可能なアイテムフォルダーのアイテムを実際に削除する準備ができました。 **検索-メールボックス**コマンドレットを実行すると、次の3つのオプションがあります。 
  
- アイテムを削除する前に、対象のメールボックスにコピーしてから、必要に応じて削除する前にアイテムを確認できるようにします。
    
- アイテムをターゲットメールボックスにコピーし、同じコマンドで削除します。
    
- ターゲットメールボックスにコピーせずにアイテムを削除します。 
    
ユーザーのプライマリアーカイブメールボックスの [回復可能なアイテム] フォルダー内のアイテムは、**検索-メールボックス**コマンドレットを実行したときにも削除されることに注意してください。 これを防ぐために、  *DoNotIncludeArchive*  スイッチを含めることができます。 前述したように、メールボックスの自動拡張アーカイブが有効になっている場合、* * 検索-メールボックス * * コマンドレットは補助アーカイブメールボックス内のアイテムを削除しません。 自動拡張アーカイブの詳細については、「 [Office 365 の無制限アーカイブの概要](unlimited-archiving.md)」を参照してください。
  
> [!NOTE]
> ( *SearchQuery*  パラメーターを使用していて) 検索クエリが含まれている場合、 **Search-Mailbox** コマンドレットは、検索結果で最大 10,000 個のアイテムを返します。したがって、検索クエリを含める場合は、 **Search-Mailbox** コマンドを複数回実行して 10,000 を超えるアイテムを削除する必要があるかもしれません。 
  
次の例は、これらの各オプションのコマンド構文を示しています。 これらの例で`-SearchQuery size>0`は、パラメーター値を使用して、回復可能なアイテムフォルダー内のすべてのサブフォルダーからすべてのアイテムを削除します。 特定の条件に一致するアイテムのみを削除する必要がある場合は、 *searchquery*パラメーターを使用して、メッセージの件名、日付の範囲など、他の条件を指定することもできます。 [その他の searchquery パラメーターの使用例](#other-examples-of-using-the-searchquery-parameter)を参照してください。 
  
### <a name="example-1"></a>例 1

この例では、ユーザーの回復可能なアイテムフォルダー内のすべてのアイテムを組織の探索検索メールボックス内のフォルダーにコピーします。 これにより、アイテムを完全に削除する前に確認することができます。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

前の例では、アイテムを探索検索メールボックスにコピーする必要はありません。 任意のターゲットメールボックスにメッセージをコピーできます。 ただし、機密性の高いメールボックスデータにアクセスできないようにするには、権限のある人物にアクセスが制限されたメールボックスにメッセージをコピーすることをお勧めします。 既定では、既定の探索検索メールボックスへのアクセスは、Exchange Online の "discovery Management/検出の管理" 役割グループのメンバーに制限されています。 
  
### <a name="example-2"></a>例 2

この例では、ユーザーの回復可能なアイテムフォルダー内のすべてのアイテムを組織の探索検索メールボックス内のフォルダーにコピーし、ユーザーの回復可能なアイテムフォルダーからアイテムを削除します。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>例 3

この例では、ユーザーの回復可能なアイテムフォルダー内のすべてのアイテムをターゲットメールボックスにコピーせずに削除します。 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>searchquery パラメーターを使用する他の例

次に、 *searchquery*パラメーターを使用して特定のメッセージを検索する例をいくつか示します。 *searchquery*パラメーターを使用して特定のアイテムを検索する場合は、検索結果を確認し、必要に応じてクエリを修正してから検索結果を削除することができるように、検索結果をターゲットメールボックスにコピーすることを検討してください。 
  
この例では、[件名] フィールドに特定の語句が含まれるメッセージを返します。
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

この例では、指定した日付範囲内に送信されたメッセージを返します。
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
この例では、指定したユーザーに送信されたメッセージを返します。

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>アイテムが削除されたことを確認する

メールボックスの [回復可能なアイテム] フォルダーからアイテムが正常に削除されたことを確認するには、Exchange Online PowerShell で**get-mailboxfolderstatistics**コマンドレットを使用して、回復可能なアイテムフォルダー内のアイテムのサイズと数を確認します。 これらの統計情報は、手順1で収集したものと比較できます。 
  
で次のコマンドを実行して、ユーザーのプライマリメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムの現在のサイズと合計数を取得します。 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
次のコマンドを実行して、ユーザーのアーカイブメールボックスの [回復可能なアイテム] フォルダー内のフォルダーとサブフォルダー内のアイテムのサイズと合計数を取得します。 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>手順 6: メールボックスを以前の状態に戻す

最後の手順では、メールボックスを以前の構成に戻します。 これは、手順2で変更したプロパティをリセットし、手順3で削除した保留リストを再適用することを意味します。 これには以下が含まれます。
  
- 削除済みアイテムの保存期間を以前の値に戻します。 または、Exchange Online の最大値の30日間に設定しておくこともできます。
    
- 単一アイテムの回復を再び有効にします。
    
- 所有者が自分のメールボックスにアクセスできるように、クライアントアクセス方法を再度有効にします。
    
- 削除した保留リストと Office 365 アイテム保持ポリシーを再適用します。
    
- 管理フォルダーアシスタントを再度有効にして、メールボックスを処理します。
    
> [!IMPORTANT]
> 管理フォルダーアシスタントを再度有効にしてメールボックスを処理する前に、保持ポリシーまたは Office 365 アイテム保持ポリシーを再適用してから24時間待機することをお勧めします。 
  
Exchange Online PowerShell で次の手順を実行します (指定された順序で)。
  
1. 削除済みアイテムの保存期間を元の値に戻すには、次のコマンドを実行します。 これは、前の設定が30日未満であることを前提としています。たとえば、14日間。 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. 単一アイテムの回復を再び有効にするには、次のコマンドを実行します。
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. 次のコマンドを実行して、すべてのクライアントアクセス方法をメールボックスに再び有効にします。
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. 手順3で削除した保留を再度適用します。 保留の種類に応じて、次のいずれかの手順を使用します。
    
    **訴訟ホールド**
    
    メールボックスの訴訟ホールドを再び有効にするには、次のコマンドを実行します。
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    EAC (または Exchange Online PowerShell) を使用して、メールボックスをインプレース保持に戻します。 
    
    **特定のメールボックスに適用される Office 365 アイテム保持ポリシー**
    
    セキュリティ & コンプライアンスセンターを使用して、メールボックスをアイテム保持ポリシーに戻します。 セキュリティ & コンプライアンスセンターの [**ガバナンス** \> **保持期間**] ページに移動し、アイテム保持ポリシーを編集して、アイテム保持ポリシーが適用されている受信者のリストにメールボックスを追加し直します。 
    
    **組織全体の Office 365 のアイテム保持ポリシー**
    
    組織全体または Exchange 全体のアイテム保持ポリシーをポリシーから除外して削除した場合は、Security & コンプライアンスセンターを使用して、除外するユーザーのリストからメールボックスを削除します。 セキュリティ & コンプライアンスセンターの [**ガバナンス** \> **期間**の日付] ページに移動し、組織全体のアイテム保持ポリシーを編集して、除外された受信者のリストからメールボックスを削除します。 これを行うと、ユーザーのメールボックスにアイテム保持ポリシーが再適用されます。 
    
    **電子情報開示ケースの保持**
    
    セキュリティ & コンプライアンスセンターを使用して、電子情報開示ケースに関連付けられている保留リストにメールボックスを追加します。 [**電子情報** \> **開示電子情報開示**] ページに移動し、ケースを開いて、メールボックスを保持に戻します。 
    
5. 管理フォルダーアシスタントがメールボックスを再度処理できるようにするには、次のコマンドを実行します。 前述したように、管理フォルダーアシスタントを再度有効にする前に、保留リストまたは Office 365 アイテム保持ポリシーを再適用してから24時間待ってから再開することをお勧めします。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. メールボックスが以前の構成に戻されたことを確認するには、次のコマンドを実行し、設定を手順1で収集したものと比較します。

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>詳細情報

次の表は、 *InPlaceHolds*プロパティの値に基づいて、**メールボックスの取得**または取得、または**取得-組織の構成**のコマンドレットを実行した場合に、さまざまな種類の保留を識別する方法を示しています。 詳細については、「 [Exchange Online メールボックスに配置されたホールドの種類を特定する方法](identify-a-hold-on-an-exchange-online-mailbox.md)」を参照してください。

前述のとおり、[回復可能なアイテム] フォルダー内のアイテムを正常に削除する前に、すべてのホールドポリシーと Office 365 アイテム保持ポリシーをメールボックスから削除する必要があります。 
  
|**ホールドの種類**|**値の例**|**保留リストを識別する方法**|
|:-----|:-----|:-----|
|訴訟ホールド  <br/> | `True` <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|インプレース ホールド  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。 GUID はプレフィックスで始まっていないため、これはインプレースホールドであることを伝えることができます。  <br/> Exchange Online の PowerShell `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL`でコマンドを使用して、メールボックスのインプレース保持に関する情報を取得できます。  <br/> |
| 特定のメールボックスに適用されるセキュリティ & コンプライアンスセンターの Office 365 アイテム保持ポリシー  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> or  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |**メールボックスの取得**コマンドレットを実行すると、 *InPlaceHolds*プロパティには、メールボックスに適用されている Office 365 アイテム保持ポリシーの guid も含まれます。 GUID が`mbx`プレフィックスで始まっているため、アイテム保持ポリシーを識別できます。 アイテム保持ポリシーの GUID が`skp`プレフィックスで始まっている場合は、アイテム保持ポリシーが Skype for business の会話に適用されることを示すことに注意してください。  <br/> メールボックスに適用されている Office 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。 <br/> <br/>`Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|セキュリティ & コンプライアンスセンターの組織全体にわたる Office 365 のアイテム保持ポリシー  <br/> |値なし  <br/> or  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(メールボックスが組織全体のポリシーから除外されていることを示します)  <br/> |InPlaceHolds コマンドレットの実行時に** プロパティが空**** の場合でも、メールボックスに適用されている組織全体の Office 365 保持ポリシーが1つ以上存在する可能性があります。  <br/> このことを確認するには、 `Get-OrganizationConfig | FL InPlaceHolds` Exchange Online PowerShell でコマンドを実行して、組織全体の Office 365 アイテム保持ポリシーの guid の一覧を取得します。 Exchange メールボックスに適用される組織全体のアイテム保持ポリシーの GUID `mbx`は、接頭辞で始まります。例`mbxa3056bb15562480fadb46ce523ff7b02`を示します。  <br/> メールボックスに適用されている組織全体の Office 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。 <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>メールボックスが組織全体の Office 365 アイテム保持ポリシーから除外されている場合は、**メールボックス取得**コマンドレットを実行すると、ユーザーのメールボックスの*InPlaceHolds*プロパティにアイテム保持ポリシーの GUID が表示されることに注意してください。プレフィックス`-mbx`によって識別されます。例えば`-mbxe9b52bf7ab3b46a286308ecb29624696` <br/> |
|セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*プロパティには、メールボックスに配置される可能性のある Security & コンプライアンスセンターの電子情報開示ケースに関連付けられている保留の GUID も含まれています。 GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> Security & コンプライアンスセンター `Get-CaseHoldPolicy` PowerShell のコマンドレットを使用して、メールボックスの保留リストに関連付けられている電子情報開示ケースに関する情報を取得できます。 たとえば、コマンド`Get-CaseHoldPolicy <hold GUID without prefix> | FL Name`を実行して、メールボックスにあるケースホールドの名前を表示できます。 Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> メールボックスの保留リストが関連付けられている電子情報開示ケースを識別するには、次のコマンドを実行します。<br/><br/>`$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/>`Get-ComplianceCase $CaseHold.CaseId | FL Name`


