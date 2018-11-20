---
title: Exchange Online メールボックスに適用されている保留の種類を特定する方法
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Office 365 のメールボックスに配置できる保留中のさまざまな種類を識別する方法を説明します。保留のこれらの種類には、証拠保全、電子的証拠開示の保留、および Office 365 のリテンション ・ ポリシーが含まれます。ユーザーが組織全体の保持ポリシーから除外されているかどうかを確認することも
ms.openlocfilehash: 1572b34d3f9abef2fb922fc9b01d1f5a27fcdf7b
ms.sourcegitcommit: e4ebef6aaf756eefb86c9f3a602cf75f5d344271
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026514"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Exchange Online メールボックスに適用されている保留の種類を特定する方法

この資料では、Office 365 のオンラインの Exchange メールボックスに配置する保留リストを識別する方法について説明します。

Office 365 には、いくつかの組織が完全に削除されるからメールボックスの内容を妨げる可能性が方法が用意されています。これにより、コンプライアンスの常連を満たすためにコンテンツを保持する組織、法的または他の種類の調査の間。Office 365 の保存機能 (も呼び出されたを*保持している*) の一覧を以下に示します。

- **証拠保全**の Exchange Online のユーザーのメールボックスに適用されているを保持します。

- **電子的証拠開示を保持**・ セキュリティとコンプライアンスの中心で、電子的証拠開示のケースに関連付けられているを保持します。電子的証拠開示の保留リストは、Office 365 のグループとマイクロソフトのチームのユーザーのメールボックスと対応するメールボックスに適用できます。

- **埋め込み保持**- 埋め込み電子的証拠開示と保持のツールを使用して Exchange 管理ツールで、ユーザーのメールボックスに適用される保留リストを中央揃え Exchange オンライン。

- **保持ポリシーを office 365**の Office 365 のグループとマイクロソフトのチームの Exchange Online と対応するメールボックスのユーザーのメールボックス内のコンテンツを保持します。保持を作成するポリシーは、ユーザーのメールボックスに格納されている、ビジネス会話の Skype を保持します。

  メールボックスに割り当てることができる Office 365 の保持ポリシーの 2 種類があります。

    - **保存ポリシーの特定の場所**- これらは、特定のユーザーのコンテンツの場所に割り当てられているポリシーです。Exchange オンライン PowerShell で特定のメールボックスに割り当てられているリテンション ・ ポリシーに関する情報を取得するのに**Get メールボックス**コマンドレットを使用するとします。

    - **組織全体の保存ポリシー** - これらは、組織内のすべてのコンテンツの場所に割り当てられているポリシーです。Exchange オンライン PowerShell で組織全体の保存ポリシーに関する情報を取得するのに**Get OrganizationConfig**コマンドレットを使用するとします。詳細については、 [Office 365 の概要の保存ポリシー](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)で「組織全体または特定の場所に保持ポリシーを適用する」セクションを参照してください。

- **保存期間のラベルを office 365**のユーザーは、フォルダー *、* または自分のメールボックスでは、保留リストにアイテムを (1 つのコンテンツを保持または保持し、コンテンツを削除し、構成されている)、Office 365 の保存のラベルを適用する場合は、場合と同様、メールボックスがメールボックスに配置されます。証拠保全に配置または Office 365 のリテンション ・ ポリシーに割り当てられています。詳細については、この資料の[特定のメールボックス フォルダーまたはアイテムに保存期間のラベルが適用されているためにの保持](#identifying-mailboxes-on-hold-because-a-label-has-been-applied-to-a-folder-or-item)」を参照してください。

保留中のメールボックスを管理するには、保留中の変更、一時的または恒久的に、保留リストを削除するまたは Office 365 のリテンション ・ ポリシーからメールボックスを除外するなどのタスクを実行できるように、メールボックスに配置されている保留リストの種類を識別する必要があります。これらの場合、最初に、メールボックスに配置する保留リストの種類を識別します。複数の保留などさまざまな種類の保留の 1 つのメールボックスを配置するためすべての保留が削除または変更するそれらを保持する場合、メールボックスの配置を特定する必要があります。

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>手順 1: は、メールボックスに保留リストの GUID を取得します。

メールボックスに配置されている保留リストの GUID を取得するのには、Exchange オンライン PowerShell では、次の 2 つのコマンドレットを実行できます。GUID を取得した後は、手順 2 で特定の保留リストを識別するのに使用します。訴訟を保持していない識別される GUID で注意してください。証拠保全が有効またはメールボックスを無効にします。

- **Get メールボックス**- を保持するメールボックスの証拠保全が有効かどうかを判断するのには、電子的証拠開示の Guid を取得するのには、このコマンドレットを使用して、インプレースを保持している、Office 365 保存ポリシーのメールボックスに明示的に割り当てられています。このコマンドレットの出力は、メールボックスは、組織全体のリテンション ・ ポリシーから明示的に除外されているかどうかも表示されます。

- **Get OrganizationConfig** - このコマンドレットを使用して、組織全体の保存ポリシーの Guid を取得します。

オンライン PowerShell を Exchange に接続するには、 [Exchange オンライン PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)を参照してください。

### <a name="get-mailbox"></a>Get-Mailbox

保持し、Office 365 のメールボックスに適用されるリテンション ・ ポリシーに関する情報を取得するのには次のコマンドを実行します。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティの値が多すぎますがあり、それらのすべてが表示されます、実行できます、`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各 GUID を表示します。

次の表では、 **Get メールボックス**コマンドレットを実行すると、 *InPlaceHolds*プロパティの値に基づいて保留の種類を識別する方法について説明します。


|ホールドの種類  |値の例  |保留リストを識別する方法  |
|---------|---------|---------|
|訴訟ホールド     |    `True`     |     証拠保全が有効になっているメールボックスの*LitigationHoldEnabled*プロパティに設定されている場合`True`。    |
|電子的証拠開示の保留中     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds プロパティ*には、セキュリティとコンプライアンスの中心で電子的証拠開示のサポート案件に関連付けられている保留状態の GUID が含まれています。これは、GUID が始まるためにの電子的証拠開示の保留リストを確認できます、 `UniH` (統一保持を示します) をプレフィックスします。      |
|インプレース保持     |     `c0ba3ce811b6432a8751430937152491` <br/> または <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*プロパティには、メールボックスに配置されている埋め込みの保持の GUID が含まれています。これは、埋め込みを保持するため、GUID は、プレフィックスを持つ起動しないか、または最初にことがわかります、`cld`のプレフィックスです。     |
|Office 365 のメールボックスに適用される具体的にはリテンション ・ ポリシー     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> または <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds プロパティには、メールボックスに適用されている任意の特定の場所の保存ポリシーの Guid が含まれています。リテンション ・ ポリシーを識別するには、GUID が始まるため、`mbx`または`skp`のプレフィックスです。`skp`プレフィックスは、ユーザーのメールボックス内のビジネス会話を Skype にリテンション ・ ポリシーが適用されることを示します。    |
|組織の Office 365 のリテンション ・ ポリシーから除外     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     メールボックスが除外されているリテンション ・ ポリシーの GUID が InPlaceHolds のプロパティに表示され、によって識別されるメールボックスが組織全体にわたる Office 365 のリテンション ・ ポリシーから除外されている場合、`-mbx`のプレフィックスです。    |

### <a name="get-organizationconfig"></a>Get OrganizationConfig
**Get メールボックス**コマンドレットを実行するときに*InPlaceHolds*プロパティが空の場合もある可能性があります 1 つまたは複数のメールボックスに適用される組織の Office 365 リテンション ・ ポリシーです。次のコマンドを実行 Exchange オンライン組織全体の Office 365 の保存ポリシーの Guid の一覧を取得する PowerShell。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティの値が多すぎますがあり、それらのすべてが表示されます、実行できます、`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各 GUID を表示します。

次の表では、組織全体を保持し、 **Get OrganizationConfig**コマンドレットを実行するときに、 *InPlaceHolds*プロパティに含まれている Guid に基づいて、それぞれの種類を識別する方法のさまざまな種類について説明します。


|ホールドの種類  |値の例  |説明  |
|---------|---------|---------|
|Office 365 のリテンション ・ ポリシーでは、チャットを Exchange メールボックス、Exchange のパブリック フォルダー、およびチームに適用    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   Exchange メールボックス、Exchange のパブリック フォルダーを組織全体の保存ポリシーが適用され、マイクロソフトのチームでの 1xN チャットで始まる Guid によって識別される、`mbx`のプレフィックスです。1xN チャットが個別のチャット参加者のメールボックスに格納されている注意してください。      |
|Office 365 の保持ポリシーが Office 365 のグループやチームのチャネル メッセージに適用     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    組織全体の保存ポリシーを Office 365 のグループとマイクロソフトのチームでのチャネルのメッセージに適用されるで始まる Guid によって識別される、`grp`のプレフィックスです。マイクロソフト チームに関連付けられているグループのメールボックスにチャネルのメッセージが格納されることに注意してください。     |

詳細情報保存ポリシーがマイクロソフトのチームに適用される、チームの場所」セクション[の保存ポリシーの概要](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)を参照してください。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>リテンション ・ ポリシーの InPlaceHolds の値の形式を理解します。

だけでなく、mbx、skp、(グループ) を識別するプレフィックスとして Office 365 のリテンション ・ ポリシーの InPlaceHolds プロパティ内の項目、値には、ポリシーに構成されている保存操作の種類を識別するサフィックスも含まれています。たとえば、アクションのサフィックスは次の例で太字で強調表示されます。

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

次の表には、3 つの保存期間のアクションが定義されています。

|値  |説明  |
|---------|---------|
|**1**     | 項目を削除するのには、リテンション ・ ポリシーが構成されていることを示します。ポリシーは、アイテムを保持しません。        |
|**2**    |    項目を保持するためにリテンション ・ ポリシーが構成されていることを示します。ポリシーは、保存期間が終了した後、アイテムを削除しません。     |
|**3**     |   項目を保持し、保存期間が終了した後それらを削除する保持ポリシーが構成されていることを示します。      |

保存アクションの詳細については、[リテンション ・ ポリシーの](retention-policies.md#retaining-content-for-a-specific-period-of-time)概要」を参照する土留め内容] 特定の期間を参照してください。
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>手順 2: 保留リストを識別する GUID を使用してください。

メールボックスに適用される保留リストの GUID を取得したら、次に、その GUID を使用して保留リストを特定します。次のセクションでは、保留リストの GUID を使用して保留リスト (およびその他の情報) の名前を識別する方法を示します。

### <a name="ediscovery-holds"></a>電子的証拠開示を保持します。

メールボックスに適用されている電子的証拠開示の保留リストを識別するには、セキュリティとコンプライアンス センター PowerShell では、次のコマンドを実行します。(UniH プレフィックス) などではない GUID を使用して、電子的証拠開示には、手順 1 で識別することを保持します。最初のコマンドは、保留リストに関する情報を含む変数を作成します。この変数は、他のコマンドで使用されます。2 番目のコマンドは、保留リストに関連付けられて、電子的証拠開示大文字と小文字の名前を表示します。3 番目のコマンドは、保留リストの名前と保留リストに適用するメールボックスの一覧を表示します。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

セキュリティとコンプライアンス センター PowerShell に接続するには、 [Office 365 のセキュリティとコンプライアンス センター PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)を参照してください。

### <a name="in-place-holds"></a>インプレース ホールド

メールボックスに適用されている埋め込みの保持を識別する、Exchange オンライン PowerShell では、次のコマンドを実行します。手順 1 で特定した埋め込み保持の GUID を使用します。コマンドには、保留リストの名前と保留リストに適用するメールボックスの一覧が表示されます。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
始まる埋め込み保持の場合はその GUID を控えておきます、`cld`プレフィックスを前のコマンドを実行するときにプレフィックスを含めるようにしてください。

### <a name="office-365-retention-policies"></a>Office 365 のリテンション ・ ポリシー

次のコマンドを実行セキュリティとコンプライアンス センター PowerShell で id に、メールボックスに適用されている Office 365 の保持ポリシー (組織全体または特定の場所)。(Mbx、skp、またはグループのプレフィックスまたはサフィックスの操作) などではない、ステップ 1 で特定した GUID を使用します。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>上の特定のメールボックス フォルダーまたはアイテムに保存期間のラベルが適用されているためにの保持します。

ユーザーがコンテンツを保持または保持のフォルダーまたはメールボックス内のアイテムのコンテンツを削除し、構成されている保存期間のラベルを適用するたびに、 *ComplianceTagHoldApplied*のメールボックスのプロパティが**True**に設定します。このような場合、メールボックスは、保留中の場合と同様に証拠保全がまたは Office 365 のリテンション ・ ポリシーに割り当てられていると見なされます。*ComplianceTagHoldApplied*プロパティを**True**に設定すると、次の項目が表示される場合があります。

- メールボックスまたはユーザーの Office 365 のユーザー アカウントを削除すると、メールボックス、[メールボックスを非アクティブ](inactive-mailboxes-in-office-365.md)になります。
- (プライマリ メールボックスまたはアーカイブ メールボックスを有効になっている場合) のメールボックスを無効にすることはできません。
- メールボックス内のアイテムは、予想以上に長く保持することがあります。これは、保留中のメールボックスがあり、したがってアイテムを削除しないため (パージ) します。

*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange オンライン PowerShell で次のコマンドを実行します。

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

保存ラベルの詳細については、 [Office 365 の概要の保存期間のラベル](labels.md)を参照してください。

## <a name="managing-mailboxes-on-delay-hold"></a>遅延を管理するメールボックスを保持します。

保留中の任意の種類がメールボックスから削除されると、 *DelayHoldApplied*のメールボックスのプロパティの値が**True**に設定します。次に管理フォルダー アシスタントのメールボックスを処理し、保留リストが削除されたことを検出したとき発生します。これは、*遅延の保持*と呼ばれ、データが完全に削除されることを防止するのには 30 日間、保留中の実際の削除を延期することを意味メールボックスからには、(削除) します。これは、管理者を検索したり、保留リストが実際に削除された後にパージされるメールボックス アイテムをリカバリできます。遅延ホールドがメールボックスに配置されると、メールボックスと見なされます上にある、無制限の期間の保持と証拠保全上にメールボックスがあったかどうか。30 日間、遅延の保持期限が切れる、および Office 365 は、( *DelayHoldApplied*プロパティを**False**に設定) によって遅延保持を削除するのには自動的に試みます保留リストが実際に削除されるようにします。*DelayHoldApplied*プロパティを**False**には後の削除のマークされているアイテムが削除されます、メールボックスの管理フォルダー アシスタントによって処理される次の時間。

メールボックスの*DelayHoldApplied*プロパティの値を表示するには、Exchange オンライン PowerShell で次のコマンドを実行します。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

期限が切れる前に、遅延の保留リストを削除するには、Exchange オンライン PowerShell で次のコマンドを実行できます。 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
する必要があります法的保持義務の役割を割り当てる Exchange オンライン、 *RemoveDelayHoldApplied*パラメーターを使用するに注意してください。 

遅延の保持を非アクティブなメールボックスを削除するには、Exchange オンライン PowerShell で次のコマンドを実行します。

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> 前のコマンドで、アクティブでないメールボックスを指定する最良の方法では、その識別名、または Exchange の GUID 値を使用します。これらの値のいずれかの方法とは、誤って正しくないメールボックスを指定することを防止できます。 

## <a name="next-steps"></a>次の手順

メールボックスに適用される保留リストを識別した後、非アクティブなメールボックスのポリシーから除外、一時的に、保留リストの期間の変更など、保留リストを完全に削除、または Office 365 のリテンション ・ ポリシーの場合にタスクを実行できます。保留リストに関連するタスクを実行する方法の詳細については、次のトピックのいずれかを参照してください。

- 実行、[セット RetentionCompliancePolicy AddExchangeLocationException\<ユーザー メールボックス >](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)で組織全体にわたる Office 365 のリテンション ・ ポリシーからメールボックスを除外するには、セキュリティとコンプライアンス センター PowerShell コマンドです。このコマンドのみ使えること・ リテンション ・ ポリシーの*ExchangeLocation*プロパティの値に注意してください`All`。

- 実行、[セット-メールボックス ExcludeFromOrgHolds\<プレフィックスまたはサフィックスのない GUID を保持する >](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)組織全体にわたる Office 365 のリテンション ・ ポリシーからがアクティブでないメールボックスを除外するのには、Exchange オンライン PowerShell のコマンドです。

- [Office 365 での非アクティブなメールボックスの保持期間を変更します。](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Office 365 で、非アクティブなメールボックスを削除します。](delete-an-inactive-mailbox.md)

- [保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
