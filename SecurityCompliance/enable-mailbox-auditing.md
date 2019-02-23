---
title: Office 365 でメールボックスの監査を有効にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: Office 365 では、メールボックス監査ログを有効にして、メールボックスの所有者、代理人、および管理者によるメールボックスへのアクセスをログに記録できます。既定では、Office 365 のメールボックスの監査は有効になっていません。メールボックスのメールボックス監査ログを有効にした後、メールボックスに対して実行されたアクティビティの Office 365 監査ログを検索することができます。
ms.openlocfilehash: bb110e95d27feb8ae82b62803d218a2b38528692
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214607"
---
# <a name="enable-mailbox-auditing-in-office-365"></a>Office 365 でメールボックスの監査を有効にする
  
Office 365 では、メールボックス監査ログを有効にして、メールボックスの所有者、代理人、および管理者によるメールボックスへのアクセスをログに記録できます。既定では、Office 365 のメールボックスの監査は有効になっていません。これは、Office 365 監査ログでメールボックスアクティビティを検索したときに、メールボックス監査イベントが結果に表示されないことを意味します。ただし、ユーザーメールボックスのメールボックス監査ログを有効にした後は、メールボックスアクティビティの監査ログを検索することができます。さらに、メールボックス監査ログが有効になっている場合、管理者、代理人、および所有者によって実行される操作の中には、既定で記録されるものがあります。その他の操作をログに記録して検索するには、「手順3」を参照してください。

## <a name="before-you-begin"></a>始める前に
  
- メールボックス監査ログを有効にするには、Exchange Online PowerShell を使用する必要があります。Office 365 セキュリティ&amp;コンプライアンスセンターまたは Exchange 管理センターを使用することはできません。
    
- Office 365 グループまたは Microsoft Teams のチームに関連付けられているメールボックスのメールボックス監査ログを有効にすることはできません。
    
- ユーザーのメールボックスに対するフル アクセスのアクセス許可を割り当てられた管理者が代理人ユーザーと見なされます。
  
## <a name="step-1-connect-to-exchange-online-powershell"></a>手順 1: Exchange Online PowerShell に接続する

1. ローカル コンピューターで、Windows PowerShell を開き、次のコマンドを実行します。
   
    ```
    $UserCredential = Get-Credential
    ```

2. **[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、Office 365 のグローバル管理者アカウントのユーザー名とパスワードを入力し、 **[OK]** をクリックします。
    
3. 次のコマンドを実行します。
    
    ```
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    ```

3. 次のコマンドを実行します。

    ```
    Import-PSSession $Session
    ```
   
4. Exchange Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのメールボックスのリストを取得します。
    
    ```
    Get-Mailbox
    ```
  
詳細については、または Exchange Online 組織への接続に関する問題がある場合は、「[リモート PowerShell による Exchange への接続](https://go.microsoft.com/fwlink/p/?LinkId=517283)」を参照してください。
  
## <a name="step-2-enable-mailbox-audit-logging"></a>手順 2: メールボックス監査ログを有効にする

Exchange Online 組織に接続した後、PowerShell を使用してメールボックスのメールボックス監査ログを有効にします。または、組織内のすべてのメールボックスに対してメールボックスの監査を有効にすることもできます。
  
この例では、Pilar Pinilla のメールボックスのメールボックス監査ログを有効にします。
  
```
Set-Mailbox -Identity "Pilar Pinilla" -AuditEnabled $true
```

この例では、組織内のすべてのユーザー メールボックスに対して、メールボックス監査ログを有効にしています。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditEnabled $true
```
  
## <a name="step-3-specify-owner-actions-to-audit"></a>手順 3: 監査する所有者の操作を指定する

メールボックスの監査を有効にすると、メールボックスの所有者によって実行される操作の一部が既定で監査されます。監査する他の所有者アクションを指定する必要があります。既定でログに記録される所有者操作の一覧と、監査可能なその他の操作については、「 [Mailbox auditing actions](#mailbox-auditing-actions) 」セクションの表を参照してください。 
  
この例では、Pilar Pinilla のメールボックスのメールボックス監査に、 **MailboxLogin**および**ハード削除**の所有者アクションを追加します。この例では、メールボックスの監査がこのメールボックスで既に有効になっていることを前提としています。 

```
Set-Mailbox "Pilar Pinilla" -AuditOwner @{Add="MailboxLogin","HardDelete"}
```

この例では、Don Hall のメールボックスのメールボックス監査ログを有効にし、メールボックスの所有者によって実行された**MailboxLogin**アクションのみがログに記録されるように指定します。この例では、既定の updatefolderpermissions アクションを上書きすることに注意してください。 
  
```
Set-Mailbox "Don Hall" -AuditEnabled $true -AuditOwner MailboxLogin
```
   
この例では、組織内のすべてのメールボックスに**MailboxLogin**、**ハード削除**、および**softdelete** owner アクションを追加します。この例では、メールボックスの監査がすべてのメールボックスに対して既に有効になっていると仮定します。 
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -AuditOwner @{Add="MailboxLogin","HardDelete","SoftDelete"}
```
  
## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

あるメールボックスに対してメールボックス監査ログが正常に有効にされたかを確認するには、**Get-Mailbox** コマンドレットを実行して、そのメールボックスの監査設定を取得します。 
  
この例では、Pilar Pinilla の監査設定を取得しています。

```
Get-Mailbox "Pilar Pinilla"| FL Audit*
```
   
この例では、組織内のすべてのユーザー メールボックスの監査設定を取得しています。

```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,Audit*
```
   
**auditenabled**プロパティの値を**True**に設定すると、メールボックス監査ログが有効になっていることが確認されます。 
    
## <a name="mailbox-auditing-actions"></a>メールボックス監査アクション
  
次の表に、メールボックス監査ログによって記録できるアクションを示します。表には、さまざまなユーザーログオンの種類に対してログに記録できるアクションが記載されています。表の [**いいえ**] は、そのログオンの種類に対してアクションをログに記録できないことを示します。アスタリスク ( **\*** ) は、メールボックスのメールボックス監査ログが有効になっている場合に、アクションが既定でログに記録されることを示します。 
  
|**操作**|**説明**|**管理者**|**代理人\*\*\***|**所有者**|
|:-----|:-----|:-----|:-----|:-----|
|**コピーする** <br/> |メッセージが別のフォルダーにコピーされました。  <br/> |はい  <br/> |×  <br/> |いいえ  <br/> |
|**Create** <br/> |メールボックスの予定表、連絡先、メモ、または仕事フォルダーでアイテムが作成されます。たとえば、新しい会議出席依頼が作成されます。メッセージの作成、送信、または受信は監査されないことにご注意ください。また、メールボックス フォルダーの作成も監視されません。  <br/> |はい\*  <br/> |はい\*  <br/> |はい  <br/> |
|**FolderBind** <br/> |メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。  <br/> |はい  <br/> |はい\*\*  <br/> |いいえ  <br/> |
|**HardDelete** <br/> |メッセージが [回復可能なアイテム] フォルダーから削除されました。  <br/> |はい\*  <br/> |はい\*  <br/> |はい  <br/> |
|**MailboxLogin** <br/> |ユーザーが自分のメールボックスにサインインしました。  <br/> |いいえ  <br/> |いいえ  <br/> |はい  <br/> |
|**messagebind** <br/> |メッセージがプレビュー ウィンドウに表示されました (または開かれました)。  <br/> |はい  <br/> |×  <br/> |いいえ  <br/> |
|**移動する** <br/> |メッセージが別のフォルダーに移動されました。  <br/> |はい  <br/> |はい  <br/> |はい  <br/> |
|**MoveToDeletedItems** <br/> |メッセージが削除され、削除済みアイテム フォルダーに移動されました。  <br/> |はい\*  <br/> |はい\*  <br/> |はい  <br/> |
|**SendAs** <br/> |メッセージが、メールボックス所有者として送信するアクセス許可を使用して送信されました。これは、メールボックスの所有者から送信されているかのように、別のユーザーがメッセージを送信したことを意味します。  <br/> |はい\*  <br/> |はい\*  <br/> |いいえ  <br/> |
|**SendOnBehalf** <br/> |SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。  <br/> |はい\*  <br/> |はい\*  <br/> |いいえ  <br/> |
|**SoftDelete** <br/> |メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。  <br/> |はい\*  <br/> |はい\*  <br/> |はい  <br/> |
|**更新する** <br/> |メッセージまたはそのプロパティが変更されました。  <br/> |はい\*  <br/> |はい\*  <br/> |はい  <br/> |
|**UpdateCalendarDelegation** <br/> |メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。  <br/> |はい\*  <br/> |いいえ  <br/> |はい\*  <br/> |
|**UpdateFolderPermissions** <br/> |フォルダーのアクセス許可が変更されました。フォルダーのアクセス許可は、組織内のどのユーザーがメールボックス内のフォルダーにアクセスできるか、およびそれらのフォルダーに格納されているメッセージを制御します。  <br/> |はい\*  <br/> |はい\*  <br/> |はい\*  <br/> |
|**UpdateInboxRules** <br/> |受信トレイ ルールが、追加、削除、または変更されました。受信トレイ ルールを使用して、指定された条件に基づいて受信ボックス内のメッセージを処理し、ルールの条件と一致した場合は、指定されたフォルダーへのメッセージの移動やメッセージの削除などのアクションを実行します。  <br/> |はい\*  <br/> |はい\*  <br/> |はい\*  <br/> |
   
> [!NOTE]
> <sup>\*</sup>メールボックスの監査が有効になっている場合は、既定で監査されます。<br/><br/>  <sup>\*\*</sup>代理人が実行したフォルダーバインド操作のエントリは統合されます。24時間の期間内の個々のフォルダーへのアクセスに対して1つのログエントリが生成されます。<br/><br/><sup>\*\*\*</sup>ユーザーのメールボックスに対するフルアクセスのアクセス許可を割り当てられた管理者は、代理人ユーザーと見なされます。 
  
特定の種類のメールボックスの操作を監査する必要がなくなった場合は、メールボックスの監査ログ構成を変更して、それらの操作を無効にする必要があります。監査ログエントリの保持期限に達するまで、既存のログエントリは削除されません。監査ログエントリの保持期間の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md#before-you-begin)」の「開始する前に」セクションを参照してください。
  
## <a name="more-infotab"></a>[詳細](#tab/)
  
- Office 365 監査ログを使用して、ログに記録されたメールボックスアクティビティを検索します。特定のユーザーメールボックスのアクティビティを検索できます。次のスクリーンショットは、Office 365 監査ログで検索できるメールボックスアクティビティの一覧を示しています。これらのアクティビティは、このトピックの「Mailbox auditing actions」セクションで説明されている操作と同じです。
    
    ![[アクティビティ] ドロップダウンリストで [Exchange メールボックスのアクティビティ] を選択することによって、メールボックス監査アクションの Office 365 監査ログを検索できます。](media/fadc34f8-9de2-4688-8b1a-bc5540e69a23.png)
  
    次の表は、検索できる各メールボックスのアクティビティと、対応するメールボックスの監査アクションを示しています。
    
    |**監査ログでのアクティビティ**|**メールボックスの監査アクション**|
    |:-----|:-----|
    |メールボックス アイテムの作成  <br/> |Create  <br/> |
    |別のフォルダーへのメッセージのコピー  <br/> |Copy  <br/> |
    |メールボックスへのユーザーのサインイン  <br/> |MailboxLogin  <br/> |
    |代理送信権限を使ったメッセージの送信  <br/> |SendOnBehalf  <br/> |
    |メールボックスからのメッセージの消去  <br/> |HardDelete  <br/> |
    |削除済みアイテム フォルダーへのメッセージの移動  <br/> |MoveToDeletedItems  <br/> |
    |別のフォルダーへのメッセージの移動  <br/> |Move  <br/> |
    |送信者権限を使ったメッセージの送信  <br/> |SendAs  <br/> |
    |メッセージの更新  <br/> |Update  <br/> |
    |削除済みアイテム フォルダーからのメッセージの削除  <br/> |SoftDelete  <br/> |
    |フォルダーにアクセス許可を追加しました  <br/> |UpdateFolderPermissions  <br/> |
    |フォルダーの変更された権限  <br/> |UpdateFolderPermissions  <br/> |
    |フォルダーから権限を削除しました  <br/> |UpdateFolderPermissions  <br/> |
    |予定表フォルダーへの代理人アクセス権を持つユーザーを追加または削除しました  <br/> |UpdateCalendarDelegation  <br/> |
   
    前のスクリーンショットに示されている**代理メールボックス**のアクセス許可を追加したり、**代理人メールボックスのアクセス許可を削除**したりしても、メールボックスの監査アクションとは関係ありません。これらは、管理者が fullaccess メールボックスのアクセス許可を割り当てたり削除したりしたかどうかを示します。 
    
    office 365 監査ログの詳細については、「 [office 365 セキュリティ&amp;コンプライアンスセンターでの監査ログの検索](search-the-audit-log-in-security-and-compliance.md)」を参照してください。
    
- 以下のシナリオでは、メールボックスに管理者のみがアクセスするものと見なしています。
    
  - メールボックスを検索するには、Exchange Online のインプレース電子情報開示または Office 365 のコンテンツ検索を使用します。
    
  - [Microsoft Exchange Server MAPI エディター](https://go.microsoft.com/fwlink/p/?linkId=204086)を使用してメールボックスにアクセスする。 
    
- メールボックスの監査ログを有効にすると、ログオンの種類 (管理者、代理人、または所有者) ごとにログに記録するユーザー操作 (メッセージへのアクセス、移動、削除など) も指定できます。 
    
- メールボックス監査ログを無効にするには、次のコマンドを実行します。

  ```
  Set-Mailbox -Identity <identity of mailbox> -AuditEnabled $false
   ```

- 各種類のユーザーに対して監査されるアクションは、**メールボックスの取得**コマンドレットを実行しても表示されません。ただし、次のコマンドを実行すると、特定のユーザーログオンの種類に関するすべての監査操作を表示できます。 

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditAdmin
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditDelegate
    ```

    ```
    Get-Mailbox <identity of mailbox> | Select-Object -ExpandProperty AuditOwner
    ```

- メールボックス監査ログをエクスポートして、1人以上のユーザーに含めるエントリを指定することもできます。レポートおよび監査ログの各エントリには、アクションを実行したユーザーと、アクションが実行された日時、およびアクションが成功したかどうかに関する情報が含まれています。詳細については、「[メールボックス監査ログのエクスポート](https://go.microsoft.com/fwlink/p/?LinkID=404104)」を参照してください。
