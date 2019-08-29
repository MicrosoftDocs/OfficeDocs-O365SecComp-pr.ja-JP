---
title: メールボックスの監査を管理する
ms.author: chrisda
author: chrisda
manager: dansimp
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
ms.assetid: aaca8987-5b62-458b-9882-c28476a66918
description: メールボックス監査ログは、既定では Office 365 で有効になっています (既定では、既定のメールボックスの監査またはメールボックスの監査とも呼ばれます)。 これは、メールボックスの所有者、代理人、および管理者によって実行される特定のアクションがメールボックス監査ログに自動的に記録されることを意味します。このログでは、メールボックスに対して実行されたアクティビティを検索できます。
ms.openlocfilehash: 049b9fe79ae3389e09fb07017fd2deb810640f35
ms.sourcegitcommit: 3962de88a143f0eb416b5cfdfd777d731f560ec8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2019
ms.locfileid: "36649912"
---
# <a name="manage-mailbox-auditing"></a>メールボックスの監査を管理する

2019年1月以降、Microsoft は、すべての Office 365 組織に対してメールボックス監査ログを既定で有効にしています。 これは、メールボックスの所有者、代理人、および管理者によって実行される特定のアクションが自動的にログに記録されることを意味します。メールボックス監査ログで検索すると、対応するメールボックス監査レコードが使用できるようになります。 既定でメールボックス監査を有効にする前に、組織内のすべてのユーザーメールボックスに対して手動で有効にする必要がありました。

既定では、メールボックスの監査の利点は次のとおりです。

- 新しいメールボックスを作成すると、監査が自動的に有効になります。 新規ユーザーに対して手動で有効にする必要はありません。

- 監査対象のメールボックスアクションを管理する必要はありません。 事前に定義された一連のメールボックスアクションは、既定では、各ログオンの種類 (管理者、代理人、および所有者) に対して監査されます。

- Microsoft が新しいメールボックスアクションをリリースした場合 (特に組織を保護し、フォレンジック調査を支援するためのアクション)、既定で監査されるメールボックスの操作の一覧に、このアクションが自動的に追加されます。 これは、メールボックスに新しいアクションを追加することを監視する必要がないことを意味します。

- 組織全体で一貫したメールボックスの監査ポリシーを使用している (すべてのメールボックスに対して同じアクションを監査しているため)。

> [!NOTE]
>•既定でのメールボックス監査のリリースに関する重要な点は、次のとおりです。メールボックスの監査を管理するために何もする必要はありません。 ただし、詳細については、このトピックで説明されているように、既定の設定からメールボックスの監査をカスタマイズするか、または完全に無効にすることをお勧めします。 <br><br>•既定でメールボックスの監査が有効になっている場合でも、一部のユーザーのメールボックス監査イベントが、セキュリティ & コンプライアンスセンターまたは Office 365 Management Activity API を介して監査ログの検索に含まれていないことがあります。 詳細については、このトピックの「[詳細情報](#more-information)」を参照してください。

## <a name="verify-mailbox-auditing-on-by-default-is-turned-on"></a>既定で [メールボックスの監査を有効にする] がオンになっていることを確認する

組織のメールボックス監査が既定でオンになっていることを確認するには、 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)で次のコマンドを実行します。

```
Get-OrganizationConfig | Format-List AuditDisabled
```

値が**False**の場合、既定でオンになっているメールボックスの監査が組織に対して有効になっていることを示します。 これは既定の組織値によって、特定のメールボックスのメールボックスの監査設定より優先されます。 たとえば、メールボックスのメールボックスの監査が無効になっている場合 (メールボックスで*Auditenabled*プロパティが**False**になっている場合)、既定のメールボックスの操作はメールボックスで引き続き監査されます。機関.

特定のメールボックスに対してメールボックスの監査を無効にするには、メールボックスの所有者とメールボックスへのアクセスが委任されている他のユーザーに対してメールボックス監査バイパスを構成します。 詳細については、このトピックの「[メールボックス監査ログをバイパス](#bypass-mailbox-audit-logging)する」を参照してください。

> [!NOTE]
> 組織のメールボックス監査が既定で有効になっている場合は、影響を受けるメールボックスの*Auditenabled*プロパティが**False**から**True**に変更されません。 言い換えると、メールボックスの監査が既定でオンになっている場合、メールボックスの*auditenabled*プロパティは無視されます。

## <a name="supported-mailbox-types"></a>サポートされるメールボックスの種類

次の表は、既定では、メールボックスの監査で現在サポートされているメールボックスの種類を示しています。

|**メールボックスの種類**|**サポートされている**|**サポートされていない**|
|:---------|:---------:|:---------:|
|ユーザー メールボックス|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|共有メールボックス|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|Office 365 グループメールボックス|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|リソース メールボックス||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|パブリック フォルダー メールボックス||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|

## <a name="logon-types-and-mailbox-actions"></a>ログオンの種類とメールボックスの操作

ログオンの種類は、監査対象のアクションを実行したユーザーをメールボックスに分類します。 次の一覧では、メールボックス監査ログで使用されるログオンの種類について説明します。

- **Owner**: メールボックスの所有者 (メールボックスに関連付けられているアカウント)。

- **デリゲート**:

  - 別のメールボックスへの SendAs、SendOnBehalf 人、または FullAccess のアクセス許可が割り当てられているユーザー。

  - ユーザーのメールボックスに対する FullAccess アクセス許可が割り当てられている管理者。

- **管理者**:

  - メールボックスは、次のいずれかの Microsoft eDiscovery ツールで検索されます。

    - コンプライアンスセンターでのコンテンツ検索。

    - コンプライアンスセンターでの電子情報開示または高度な電子情報開示。

    - Exchange Online のインプレース電子情報開示。

  - メールボックスは、 [Microsoft Exchange SERVER MAPI エディター](https://go.microsoft.com/fwlink/p/?linkId=204086)を使用してアクセスします。

### <a name="mailbox-actions-for-user-mailboxes-and-shared-mailboxes"></a>ユーザーメールボックスと共有メールボックスのメールボックスアクション

次の表では、ユーザーメールボックスと共有メールボックスのメールボックス監査ログで使用できるメールボックスアクションについて説明します。

- チェックマーク ( ![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)) メールボックスの操作をログオンの種類に対してログに記録できることを示します (すべてのログオンの種類で使用できるすべてのアクションがあるわけではありません)。

- チェックマークの<sup>\*</sup>後のアスタリスク () は、ログオンの種類に対して既定でメールボックスのアクションが記録されることを示します。

- メールボックスに対するフルアクセスのアクセス許可を持つ管理者は、代理人と見なされることに注意してください。

|**メールボックスアクション**|**説明**|**管理者**|**代理人**|**所有者**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**AddFolderPermissions**|**注**: この値はメールボックスアクションとして受け入れられますが、既に**updatefolderpermissions**アクションに含まれており、個別に監査されていません。 言い換えると、この値は使用しないでください。||||
|**ApplyRecord**|アイテムには、レコードとしてラベルが付けられます。|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**コピーする**|メッセージが別のフォルダーにコピーされました。|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**Create**|メールボックス内の予定表、連絡先、メモ、または仕事フォルダーにアイテムが作成されました (たとえば、新しい会議出席依頼が作成された場合)。 メッセージの作成、送信、または受信が監査されないことに注意してください。 また、メールボックスフォルダーの作成は監査されません。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**FolderBind**|メールボックス フォルダーがアクセスされました。この操作は、管理者または委任されたユーザーがメールボックスを開いたときにも記録されます。<br/><br/> **注**: 代理人によって実行されたフォルダーバインド操作の監査レコードは統合されます。 1つの監査レコードは、24時間以内に個々のフォルダーへのアクセスに対して生成されます。|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MailboxLogin**|ユーザーが自分のメールボックスにサインインしている。 |||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MessageBind**|メッセージがプレビュー ウィンドウに表示されました (または開かれました)。|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|**ModifyFolderPermissions**|**注**: この値はメールボックスアクションとして受け入れられますが、既に**updatefolderpermissions**アクションに含まれており、個別に監査されていません。 言い換えると、この値は使用しないでください。||||
|**移動する**|メッセージが別のフォルダーに移動されました。|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**RecordDelete**|レコードとしてラベル付けされたアイテムは、回復可能な削除 (回復可能なアイテムフォルダーに移動) されました。 レコードとしてラベル付けされたアイテムを完全に削除することはできません (回復可能なアイテムフォルダーから削除されます)。|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**RemoveFolderPermissions**|**注**: この値はメールボックスアクションとして受け入れられますが、既に**updatefolderpermissions**アクションに含まれており、個別に監査されていません。 言い換えると、この値は使用しないでください。||||
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者を装ってメッセージを送信しました)。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました (他のユーザーがこのメールボックスの所有者の代理人としてメッセージを送信しました)。この場合は、メッセージの名目上の送信者と実際の送信者が受信者に示されます。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|メッセージまたはそのプロパティが変更されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateCalendarDelegation**|メールボックスに予定表の委任が割り当てられました。予定表の委任により、同じ組織の他のユーザーに、メールボックス所有者の予定表を管理する権限が付与されます。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateFolderPermissions**|フォルダーのアクセス許可が変更されました。 フォルダーのアクセス許可は、組織内のどのユーザーがメールボックス内のフォルダーにアクセスできるか、およびそれらのフォルダーに格納されているメッセージを制御します。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**UpdateInboxRules**|受信トレイルールが追加、削除、または変更されました。 受信トレイルールは、指定された条件に基づいてユーザーの受信トレイ内のメッセージを処理し、指定されたフォルダーにメッセージを移動したり、メッセージを削除したりするなど、ルールの条件が満たされたときにアクションを実行するために使用されます。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

> [!IMPORTANT]
> 組織内で既定でオンになっているメールボックスの監査を有効にする*前*に、任意のログオンの種類を監査するようにメールボックスのアクションをカスタマイズした場合、カスタマイズした設定はメールボックスに保持され、既定のメールボックスアクションによって上書きされません。このセクションで説明します。 監査メールボックスアクションを既定値に戻すには (いつでも可能)、このトピックで後述する「[既定のメールボックスアクションを復元](#restore-the-default-mailbox-actions)する」セクションを参照してください。

### <a name="mailbox-actions-for-office-365-group-mailboxes"></a>Office 365 グループメールボックスのメールボックスアクション

既定でのメールボックス監査メールボックス監査ログを Office 365 グループメールボックスに取り込みますが、ログ記録される内容をカスタマイズすることはできません (ログオンの種類に対して記録されるメールボックスアクションを追加または削除することはできません)。

次の表では、Office 365 グループメールボックスのログオンの種類ごとに既定で記録されるメールボックスの操作について説明します。

Office 365 グループメールボックスへのフルアクセスのアクセス許可を持つ管理者は、代理人と見なされることに注意してください。

|**メールボックスアクション**|**説明**|**管理者**|**代理人**|**所有者**|
|:---------|:---------|:---------:|:---------:|:---------:|
|**Create**|予定表アイテムの作成。 メッセージの作成、送信、または受信が監査されないことに注意してください。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**HardDelete**|メッセージが [回復可能なアイテム] フォルダーから削除されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**MoveToDeletedItems**|メッセージが削除され、[削除済みアイテム] フォルダーに移動されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**SendAs**|SendAs アクセス許可を使用してメッセージが送信されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SendOnBehalf**|SendOnBehalf アクセス許可を使用してメッセージが送信されました。 |![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>||
|**SoftDelete**|メッセージが完全に削除された、つまり [削除済みアイテム] フォルダーから削除されました。削除済み (回復可能) アイテムは、回復可能なアイテム フォルダーに移動されます。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|
|**Update**|メッセージまたはそのプロパティが変更されました。|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|![チェックマーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)<sup>\*</sup>|

### <a name="verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type"></a>ログオンの種類ごとに既定のメールボックスアクションがログに記録されていることを確認する

既定でのメールボックスの監査すべてのメールボックスに新しい*Defaultauditset*プロパティを追加します。 このプロパティの値は、メールボックスの既定のメールボックスの操作 (Microsoft が管理する) が監査されているかどうかを示します。

ユーザーメールボックスまたは共有メールボックスに値を表示\<する\>には、MailboxIdentity をメールボックスの名前、エイリアス、電子メールアドレス、またはユーザープリンシパル名 (ユーザー名) に置き換えて、Exchange Online PowerShell で次のコマンドを実行します。

```
Get-Mailbox -Identity <MailboxIdentity> | Format-List DefaultAuditSet
```

Office 365 のグループメールボックスに値を表示する\<に\>は、MailboxIdentity を共有メールボックスの名前、エイリアス、または電子メールアドレスに置き換え、Exchange Online PowerShell で次のコマンドを実行します。

```
Get-Mailbox -Identity <MailboxIdentity> -GroupMailbox | Format-List DefaultAuditSet
```

値は`Admin, Delegate, Owner`次の値を示します。

- 3つのすべてのログオンの種類に対する既定のメールボックスアクションが監査されます。 これは、Office 365 グループメールボックスに表示される唯一の値であることに注意してください。

- 管理者は、ユーザーのメールボックスまたは共有メールボックスのすべてのログオンの種類について、監査されたメールボックスの操作を変更し*ていません*。 注これは、既定でオンになっているメールボックスの監査後の既定の状態が組織内で最初に有効になっていることを示しています。

管理者が、ログオンの種類に対して監査されるメールボックスの操作 ( *Auditadmin*、 *auditadmin*、または*AuditOwner*コマンドレットのパラメーター **** を使用して) を変更した場合、プロパティ値は異なります。

たとえば、ユーザーメールボックス`Owner`または共有メールボックスの*defaultauditset*プロパティの値は次のように示されます。

- メールボックスの所有者に対する既定のメールボックスアクションが監査されている。

- `Delegate`および`Admin`ログオンの種類に対して監査されたメールボックスアクションが既定のアクションから変更されました。

*Defaultauditset*プロパティの空白値は、ユーザーのメールボックスまたは共有メールボックスで3種類のすべてのログオンの種類に対するメールボックスの操作が変更されたことを示します。

詳細については、このトピックの「[既定でログメールボックスのアクションを変更または復元](#change-or-restore-mailbox-actions-logged-by-default)する」セクションを参照してください。

### <a name="display-the-mailbox-actions-that-are-being-logged-on-mailboxes"></a>メールボックスにログオンしているメールボックスのアクションを表示する

ユーザーのメールボックスまたは共有メールボックスに現在ログオンしているメールボックスの\<操作\>を表示するには、MailboxIdentity をメールボックスの名前、エイリアス、電子メールアドレス、またはユーザープリンシパル名 (username) に置き換えて、次の1つ以上を実行します。Exchange Online の PowerShell のコマンド。

> [!NOTE]
> Office 365 のグループメール`-GroupMailbox`ボックスの次の**メールボックス**コマンドにスイッチを追加することはできますが、表示される値を信じないでください。 Office 365 グループメールボックスに対して監査される既定および静的メールボックスのアクションについては、このトピックで前述した「 [office 365 グループメールボックスのメールボックスアクション](#mailbox-actions-for-office-365-group-mailboxes)」セクションを参照してください。

#### <a name="owner-actions"></a>所有者のアクション

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditOwner
```

#### <a name="delegate-actions"></a>デリゲートアクション

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditDelegate
```

#### <a name="admin-actions"></a>管理者アクション

```
Get-Mailbox -Identity <MailboxIdentity> | Select-Object -ExpandProperty AuditAdmin
```

## <a name="change-or-restore-mailbox-actions-logged-by-default"></a>既定でログに記録されるメールボックスアクションを変更または復元する

前述のように、既定でメールボックス監査をオンにすることの主な利点の1つとして、監査対象のメールボックスアクションを管理する必要はありません。 Microsoft は、これをユーザーに対して自動的に追加し、リリースされたときに既定で監査される新しいメールボックスアクションを自動的に追加します。

ただし、組織では、ユーザーメールボックスと共有メールボックスのメールボックスアクションの異なるセットを監査する必要がある場合があります。 このセクションの手順では、各ログオンの種類に対して監査されるメールボックスの操作を変更する方法と、Microsoft が管理する既定のアクションに戻す方法について説明します。

> [!IMPORTANT]
> 次の手順を使用して、ユーザーのメールボックスまたは共有メールボックスにログオンしたメールボックスの操作をカスタマイズすると、Microsoft によってリリースされた新しい既定のメールボックスのアクションは、それらのメールボックスで自動的には監査されません。 カスタマイズしたアクションのリストに、新しいメールボックスアクションを手動で追加する必要があります。

### <a name="change-the-mailbox-actions-to-audit"></a>メールボックスのアクションを監査に変更する

ユーザーメールボックスと共有メールボックスについて監査されるメールボックス**** の操作を変更するには、AuditOwner コマンドレットで*auditadmin*、 *Auditadmin*、または** パラメーターを使用できます (Office 365 グループの監査対象アクション)メールボックスをカスタマイズすることはできません)。

メールボックスのアクションを指定するには、2つの異なる方法を使用できます。

- *Replace*(上書きする) 次の構文`action1,action2,...actionN`を使用して、既存のメールボックスアクションを上書きします。

- この構文を使用して、他の既存の値に影響を`@{Add="action1","action2",..."actionN"}`与え`@{Remove="action1","action2",..."actionN"}`ずに、メールボックスアクションを*追加または削除*します。または。

この例では、"Gabriela Laureano" という名前のメールボックスの管理メールボックスのアクションを変更します。これにより、既定の操作を SoftDelete およびハード Delete で上書きします。

```
Set-Mailbox -Identity "Gabriela Laureano" -AuditAdmin HardDelete,SoftDelete
```

この例では、MailboxLogin owner アクションをメールボックス laura@contoso.onmicrosoft.com に追加します。

```
Set-Mailbox -Identity laura@contoso.onmicrosoft.com -AuditOwner @{Add="MailboxLogin"}
```

この例では、チームディスカッションメールボックスの MoveToDeletedItems delegate アクションを削除します。

```
Set-Mailbox -Identity "Team Discussion" -AuditDelegate @{Remove="MoveToDeletedItems"}
```

使用する方法に関係なく、ユーザーのメールボックスまたは共有メールボックスで監査されたメールボックスの操作をカスタマイズすると、次の結果が得られます。

- カスタマイズしたログオンの種類については、監査されたメールボックスの操作が Microsoft によって管理されなくなりました。

- カスタマイズしたログオンの種類は、[前述](#verify-that-default-mailbox-actions-are-being-logged-for-each-logon-type)したように、メールボックスの*defaultauditset*プロパティ値に表示されなくなりました。

### <a name="restore-the-default-mailbox-actions"></a>既定のメールボックスアクションを復元する

ユーザーメールボックスまたは共有メールボックスで監査されるメールボックスの操作をカスタマイズした場合は、次の構文を使用して、1つまたはすべてのログオンの種類に対する既定のメールボックスアクションを復元できます。

```
Set-Mailbox -Identity <MailboxIdentity> -DefaultAuditSet <Admin | Delegate | Owner>
```

複数の*Defaultauditset*値をコンマで区切って指定できます。

**注**: 以下の手順は、Office 365 のグループメールボックスには適用されません ([ここで](#mailbox-actions-for-office-365-group-mailboxes)説明している既定の操作に制限されます)。

この例では、メールボックス mark@contoso.onmicrosoft.com 上のすべてのログオンの種類について、既定の監査済みメールボックスアクションを復元します。

```
Set-Mailbox -Identity mark@contoso.onmicrosoft.com -DefaultAuditSet Admin,Delegate,Owner
```

この例では、メールボックス chris@contoso.onmicrosoft.com の管理者のログオンの種類に対する既定の監査済みメールボックスアクションを復元します。ただし、委任および所有者のログオンの種類に対してカスタマイズされた監査メールボックスアクションを残します。

```
Set-Mailbox -Identity chris@contoso.onmicrosoft.com -DefaultAuditSet Admin
```

既定の監査済みメールボックスのログオンの種類のアクションには、次のような結果があります。

- メールボックスアクションの現在のリストは、ログオンの種類に対する既定のメールボックスアクションに置き換えられます。

- Microsoft によってリリースされた新しいメールボックスのアクションは、そのログオンの種類に対する監査対象のアクションの一覧に自動的に追加されます。

- メールボックスの*Defaultauditset*プロパティの値は、復元されたログオンの種類を含むように更新されます。

## <a name="turn-off-mailbox-auditing-on-by-default-for-your-organization"></a>組織に対して既定でメールボックスの監査を無効にする

Exchange Online PowerShell で次のコマンドを実行することによって、組織全体のメールボックスの監査を既定で無効にすることができます。

```
Set-OrganizationConfig -AuditDisabled $true
```

既定でメールボックス監査を無効にすると、次の結果が得られます。

- 組織のメールボックスの監査が無効になっています。

- 既定では、メールボックスの監査を無効にしたときに、メールボックスの監査が有効になっている場合でも、メールボックスの操作は監査されません (メールボックスの*Auditenabled*プロパティが**True**に設定されている場合)。

- 新しいメールボックスに対してメールボックスの監査が有効になっておらず、新規または既存のメールボックスの*Auditenabled*プロパティが**True**に設定されている場合は無視されます。

- メールボックス監査バイパスの関連付け設定 ( **set-mailboxauditbypassassociation**コマンドレットを使用して構成) は無視されます。

- 既存のメールボックス監査レコードは、レコードの監査ログの有効期限が切れるまで保持されます。

### <a name="turn-on-mailbox-auditing-on-by-default"></a>既定でメールボックス監査をオンにする

組織のメールボックスの監査を再び有効にするには、Exchange Online PowerShell で次のコマンドを実行します。

```
Set-OrganizationConfig -AuditDisabled $false
```

## <a name="bypass-mailbox-audit-logging"></a>メールボックス監査ログをバイパスする

現在、組織内のメールボックスの監査が既定でオンになっている場合、特定のメールボックスのメールボックス監査を無効にすることはできません。 たとえば、 *Auditenabled* mailbox プロパティを**False**に設定することは無視されます。

ただし、Exchange Online PowerShell で**set-mailboxauditbypassassociation**コマンドレットを使用して、アクションが発生した場所に関係なく、指定されたユーザーによる*すべて*のメールボックスの操作をログに記録しないようにすることができます。 次に例を示します。

- バイパスユーザーが実行したメールボックスの所有者のアクションは記録されません。

- 他のユーザーのメールボックス (共有メールボックスを含む) で、バイパスされたユーザーによって実行される代理アクションは記録されません。

- バイパスユーザーによって実行された管理操作は記録されません。

特定のユーザーのメールボックス監査ログをバイパスする\<に\>は、MailboxIdentity をユーザーの名前、電子メールアドレス、エイリアス、またはユーザープリンシパル名 (ユーザー名) に置き換えて、次のコマンドを実行します。

```
Set-MailboxAuditBypassAssociation -Identity <MailboxIdentity> -AuditByPassEnabled $true
```

指定したユーザーの監査がバイパスされていることを確認するには、次のコマンドを実行します。

```
Get-MailboxAuditBypassAssociation -Identity <MailboxIdentity> | Format-List AuditByPassEnabled
```

値**True**は、ユーザーのメールボックス監査ログがバイパスされることを示します。

## <a name="more-information"></a>詳細情報

- E5 ライセンスまたはメールボックスを管理者によって手動で有効にしたメールボックスを持つユーザーのみが、セキュリティ & コンプライアンスセンターまたは Office 365 Management Activity API を介して監査ログの検索でメールボックス監査ログイベントを返します。

  E5 ライセンスを持たないユーザーのメールボックス監査ログエントリを取得するには、次のことを行います。

  - Exchange Online PowerShell で次のコマンドレットを使用します。

    - [「Search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)を使用して、特定のユーザーのメールボックス監査ログを検索します。

    - [「New-mailboxauditlogsearch」](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/new-mailboxauditlogsearch)を使用して、特定のユーザーのメールボックス監査ログを検索し、結果を指定された受信者に電子メール経由で送信します。

  - Exchange Online の Exchange 管理センター (EAC) を使用して、次の操作を行います。

    - [メールボックス監査ログのエクスポート](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/export-mailbox-audit-logs)

    - [所有者以外のメールボックス アクセスのレポートの実行](https://docs.microsoft.com/Exchange/security-and-compliance/exchange-auditing-reports/non-owner-mailbox-access-report)

- 既定では、メールボックス監査ログレコードは、削除されるまでは90日間保持されます。 監査ログレコードの有効期限を変更するには、Exchange Online PowerShell の**メールボックスの設定**コマンドレットで、 *auditlogagelimit*パラメーターを使用します。 ただし、この値を大きくしても、Office 365 監査ログで90日より前のイベントを検索することはできません。

  保存期間を延長した場合は、Exchange Online PowerShell で[「search-mailboxauditlog](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog)コマンドレットを使用して、ユーザーのメールボックス監査ログで90日より前のレコードを検索する必要があります。

- メールボックスの監査を有効にする前にメールボックスの*Auditlogagelimit*プロパティを変更した場合、既定では、組織では、メールボックスの既存の監査ログの有効期限は変更されません。 言い換えると、既定でオンになっているメールボックス監査は、メールボックス監査レコードの現在の保存期間制限に影響しません。

- Office 365 グループメールボックスの*Auditlogagelimit*値を変更するには、この`-GroupMailbox`スイッチを**mailbox**コマンドに含める必要があります。

- メールボックス監査ログレコードは、各ユーザーのメールボックスの [回復可能なアイテム] フォルダーにあるサブフォルダー (*監査*という名前) に格納されます。 メールボックス監査レコードと回復可能なアイテムフォルダーについては、次の点に注意してください。

  - メールボックス監査レコードは、回復可能なアイテムフォルダーの記憶域のクォータに対してカウントされます。これは既定で30GB ます (警告クォータは 20 GB です)。 ストレージクォータは、次の場合に自動的に 100 GB に増加します (90 GB の警告クォータがあります)。

    - メールボックスにホールドが適用されます。

    - メールボックスは、コンプライアンスセンターのアイテム保持ポリシーに割り当てられます。

  - メールボックス監査レコードは[、回復可能なアイテムフォルダーのフォルダー制限](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#mailbox-folder-limits)にもカウントされます。 監査サブフォルダーには、最大300万個のアイテム (監査レコード) を格納できます。

    > [!NOTE]
    > 既定では、メールボックスの監査が、回復可能なアイテムフォルダーの記憶域のクォータまたはフォルダーの制限に影響を与える可能性はほとんどありません。

    - Exchange Online の PowerShell で次のコマンドを実行すると、回復可能なアイテムフォルダーの監査サブフォルダー内のアイテムのサイズと数を表示できます。

      ```
      Get-MailboxFolderStatistics -Identity <MailboxIdentity> -FolderScope RecoverableItems | Where-Object {$_.Name -eq 'Audits'} | Format-List FolderPath,FolderSize,ItemsInFolder
      ```

    - [回復可能なアイテム] フォルダー内の監査ログレコードに直接アクセスすることはできません。代わりに、 **「search-mailboxauditlog**コマンドレットを使用するか、Office 365 監査ログを検索して、メールボックス監査レコードを検索して表示します。

- メールボックスが保留になっている場合、またはコンプライアンスセンターでアイテム保持ポリシーに割り当てられている場合、メールボックスの*Auditlogagelimit*プロパティによって定義されている期間 (既定では90日間) の監査ログレコードが引き続き保持されます。 保留中のメールボックスの監査ログレコードを長期間保持するには、メールボックスの*Auditlogagelimit*の値を増やす必要があります。
