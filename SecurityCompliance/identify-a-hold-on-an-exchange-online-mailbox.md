---
title: Exchange Online メールボックスに保存されている保留の種類を特定する方法
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/22/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6057daa8-6372-4e77-a636-7ea599a76128
description: Office 365 メールボックスに配置できるさまざまな種類の保留リストを識別する方法について説明します。 これらの種類には、訴訟ホールド、電子情報開示の保持、および Office 365 アイテム保持ポリシーが含まれます。 ユーザーが組織全体のアイテム保持ポリシーから除外されているかどうかを確認することもできます。
ms.openlocfilehash: e0c1c54cedfc7494233f12f043bb6d033576eca8
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32253887"
---
# <a name="how-to-identify-the-type-of-hold-placed-on-an-exchange-online-mailbox"></a>Exchange Online メールボックスに保存されている保留の種類を特定する方法

この記事では、Office 365 の Exchange Online メールボックスに配置された保留リストを特定する方法について説明します。

Office 365 には、組織がメールボックスの内容が完全に削除されないようにする方法がいくつか用意されています。 これにより、組織は、コンプライアンス regulars または法的またはその他の種類の調査の期間中に、コンテンツを保持することができます。 Office 365 の保持機能 (*保留*とも呼ばれます) の一覧を以下に示します。

- **訴訟ホールド**-Exchange Online のユーザーメールボックスに適用されるホールド。

- **電子情報開示の保持**-セキュリティ/コンプライアンスセンターの電子情報開示ケースに関連付けられた保留リスト。 電子情報開示の保持は、ユーザーのメールボックス、および対応する Office 365 グループおよび Microsoft Teams のメールボックスに適用できます。

- インプレース**保持**-exchange Online の exchange 管理センターでインプレース電子情報開示 & ホールドツールを使用して、ユーザーのメールボックスに適用されるホールド。

- **office 365 アイテム保持ポリシー** -Exchange Online のユーザーメールボックスおよび office 365 グループと Microsoft Teams の対応するメールボックスにコンテンツを保持します。 アイテム保持ポリシーを作成すると、ユーザーのメールボックスに格納されている Skype for business 会話が保持されます。

  メールボックスに割り当てることができる Office 365 のアイテム保持ポリシーには、2種類あります。

    - **特定の場所の保持ポリシー** -特定のユーザーのコンテンツの場所に割り当てられているポリシーです。 Exchange Online の PowerShell で、**メールボックスの取得**コマンドレットを使用して、特定のメールボックスに割り当てられているアイテム保持ポリシーに関する情報を取得します。

    - **組織全体のアイテム保持ポリシー** -組織内のすべてのコンテンツの場所に割り当てられているポリシーです。 組織全体のアイテム保持ポリシーについての情報を取得するには、Exchange Online の PowerShell で、" **get-help/** 組織全体の構成" コマンドレットを使用します。
  詳細については、「 [Office 365 アイテム保持ポリシーの概要](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」の「組織全体または特定の場所にアイテム保持ポリシーを適用する」セクションを参照してください。

- **office 365 の保持ラベル**-ユーザーが自分のメールボックス内の*任意*のフォルダーまたはアイテムに office 365 の保持ラベル (コンテンツを保持するように構成されている、またはコンテンツを保持してから削除するように構成されている) を適用すると、メールボックスがメールボックスの場合と同じように保持されます。訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーに割り当てられます。 詳細については、この記事の「[フォルダーまたはアイテムに保持ラベルが適用されているため、保留中のメールボックスを識別](#identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item)する」を参照してください。

保留中のメールボックスを管理するには、保持期間の変更、一時的または完全に保持を削除する、または Office 365 アイテム保持ポリシーからメールボックスを除外するなどのタスクを実行できるように、メールボックスに設定されているホールドの種類を特定する必要がある場合があります。 このような場合は、最初の手順として、メールボックスに設定されている保留の種類を特定します。 また、複数のホールド (および異なる種類の保留リスト) を単一のメールボックスに配置することができるため、そのような保留リストを削除または変更する場合は、メールボックスに設定されているすべての保留リストを特定する必要があります。

## <a name="step-1-obtaining-the-guid-for-holds-placed-on-a-mailbox"></a>手順 1: メールボックスに配置された保留リストの GUID を取得する

Exchange Online PowerShell で次の2つのコマンドレットを実行して、メールボックスに配置されている保留リストの GUID を取得できます。 GUID を取得した後、それを使用して、手順2で特定のホールドを識別します。 訴訟ホールドは GUID で識別されないことに注意してください。 訴訟ホールドは、メールボックスに対して有効または無効のどちらかになります。

- **Get メールボックス**-メールボックスに対して訴訟ホールドが有効になっているかどうかを確認し、メールボックスに割り当てられている電子情報開示の保持ポリシー、インプレースホールド、および Office 365 アイテム保持ポリシーの guid を取得するには、このコマンドレットを使用します。 このコマンドレットの出力は、メールボックスが組織全体のアイテム保持ポリシーから明示的に除外されているかどうかも示します。

- **get-help config** -組織全体のアイテム保持ポリシーの guid を取得するには、このコマンドレットを使用します。

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)」を参照してください。

### <a name="get-mailbox"></a>Get-Mailbox

次のコマンドを実行して、メールボックスに適用されている保留リストと Office 365 アイテム保持ポリシーに関する情報を取得します。

```
Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行して各 GUID を別々の行に表示することができます。

次の表は、InPlaceHolds コマンドレットを実行するときに、 ** プロパティの値に基づいてさまざまな**** 種類の保留リストを識別する方法を示しています。


|ホールドの種類  |値の例  |保留リストを識別する方法  |
|---------|---------|---------|
|訴訟ホールド     |    `True`     |     *LitigationHoldEnabled*プロパティがに`True`設定されている場合、メールボックスに対して訴訟ホールドが有効になります。    |
|電子情報開示の保留     |  `UniH7d895d48-7e23-4a8d-8346-533c3beac15d`       |   *InPlaceHolds プロパティ*には、セキュリティ/コンプライアンスセンターの電子情報開示ケースに関連付けられている保留リストの GUID が含まれています。 GUID は`UniH`プレフィックス (統合された保持を示す) で始まっているため、これが電子情報開示の保留であることを伝えることができます。      |
|インプレース ホールド     |     `c0ba3ce811b6432a8751430937152491` <br/> or <br/> `cld9c0a984ca74b457fbe4504bf7d3e00de`  |     *InPlaceHolds*プロパティには、メールボックスに配置されたインプレースホールドの GUID が含まれています。 GUID がプレフィックスで始まっていないか、 `cld`プレフィックスで始まっていないため、これはインプレースホールドであると判断できます。     |
|特にメールボックスに適用される Office 365 アイテム保持ポリシー     |    `mbxcdbbb86ce60342489bff371876e7f224:1` <br/> or <br/> `skp127d7cf1076947929bf136b7a2a8c36f:3`     |     InPlaceHolds プロパティには、メールボックスに適用される特定の場所保持ポリシーの guid が含まれています。 GUID は`mbx`または`skp`プレフィックスで始まっているため、アイテム保持ポリシーを識別できます。 プレフィックス`skp`は、アイテム保持ポリシーがユーザーのメールボックス内の Skype for business の会話に適用されることを示します。    |
|組織全体の Office 365 アイテム保持ポリシーから除外されます。     |   `-mbxe9b52bf7ab3b46a286308ecb29624696`      |     メールボックスが組織全体の Office 365 アイテム保持ポリシーから除外されている場合、メールボックスが除外されるアイテム保持ポリシーの GUID は InPlaceHolds プロパティに表示され`-mbx` 、プレフィックスで識別されます。    |

### <a name="get-organizationconfig"></a>Get-OrganizationConfig
**メールボックスの取得**コマンドレットを実行したときに*InPlaceHolds*プロパティが空の場合、依然として、1つ以上の組織全体の Office 365 アイテム保持ポリシーがメールボックスに適用されている可能性があります。 Exchange Online PowerShell で次のコマンドを実行して、組織全体の Office 365 保持ポリシーの guid の一覧を取得します。

```
Get-OrganizationConfig | FL InPlaceHolds
```

> [!TIP]
> InPlaceHolds プロパティに含まれる値が多すぎて、一部が表示されていない場合は、 `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを実行して各 GUID を別々の行に表示することができます。

次の表では、組織全体のさまざまな種類と、InPlaceHolds コマンドレットを実行するときに、 ** プロパティに含まれている**** guid に基づいて各種類を識別する方法について説明します。


|ホールドの種類  |値の例  |説明  |
|---------|---------|---------|
|exchange メールボックス、exchange パブリックフォルダー、およびチームチャットに適用される Office 365 アイテム保持ポリシー    |      `mbx7cfb30345d454ac0a989ab3041051209:2`   |   exchange メールボックス、exchange パブリックフォルダー、および Microsoft Teams の1xn チャットに適用される組織全体のアイテム保持ポリシーは、 `mbx`プレフィックスで始まる guid によって識別されます。 1xn チャットは、個々のチャット参加者のメールボックスに格納されることに注意してください。      |
|office 365 グループおよび Teams チャネルメッセージに適用される office 365 アイテム保持ポリシー     |   `grp1a0a132ee8944501a4bb6a452ec31171:3`      |    Office 365 グループに適用される組織全体のアイテム保持ポリシーと、Microsoft Teams のチャネルメッセージは、 `grp`プレフィックスで始まる guid によって識別されます。 チャネルメッセージは、Microsoft teams に関連付けられているグループメールボックスに格納されていることに注意してください。     |

Microsoft teams に適用される詳細なアイテム保持ポリシーについては、「[アイテム保持ポリシーの概要](retention-policies.md#applying-a-retention-policy-to-an-entire-organization-or-specific-locations)」の「teams の場所」セクションを参照してください。

### <a name="understanding-the-format-of-the-inplaceholds-value-for-retention-policies"></a>保持ポリシーの InPlaceHolds 値の形式について

Office 365 アイテム保持ポリシーとして InPlaceHolds プロパティのアイテムを識別するプレフィックス (、skp、または grp) に加えて、この値には、ポリシーに対して構成されている保持アクションの種類を識別するサフィックスも含まれています。 たとえば、次の例では、アクションのサフィックスが太字で強調表示されています。

   `skp127d7cf1076947929bf136b7a2a8c36f`**: 1**

   `mbx7cfb30345d454ac0a989ab3041051209`**: 2**

   `grp1a0a132ee8944501a4bb6a452ec31171`**: 3**

次の表では、3つの保持アクションを定義します。

|値  |説明  |
|---------|---------|
|**1**     | アイテムを削除するようにアイテム保持ポリシーが構成されていることを示します。ポリシーはアイテムを保持しません。        |
|**2**    |    アイテム保持ポリシーがアイテムを保持するように構成されていることを示します。保持期間が経過すると、ポリシーによってアイテムが削除されることはありません。     |
|**3**     |   アイテム保持ポリシーがアイテムを保持するように構成されていて、保存期間が経過した後にアイテムを削除することを示します。      |

保持アクションの詳細については、「[アイテム保持ポリシーの概要](retention-policies.md#retaining-content-for-a-specific-period-of-time)」の「特定の期間だけコンテンツを保持する」を参照してください。
   
## <a name="step-2-using-the-guid-to-identify-the-hold"></a>手順 2: GUID を使用して保留リストを識別する

メールボックスに適用されている保留リストの guid を取得した後、次の手順として、その guid を使用して保留リストを識別します。 次のセクションでは、ホールド GUID を使用して、保留 (およびその他の情報) の名前を識別する方法を示します。

### <a name="ediscovery-holds"></a>電子情報開示の保持

Security & コンプライアンスセンターの PowerShell で次のコマンドを実行して、メールボックスに適用されている電子情報開示ホールドを識別します。 手順1で特定した電子情報開示の保留リストの GUID (unih プレフィックスを含まない) を使用します。 最初のコマンドは、ホールドに関する情報を含む変数を作成します。この変数は、他のコマンドで使用されます。 2番目のコマンドは、保留が関連付けられている電子情報開示ケースの名前を表示します。 3番目のコマンドは、保留リストの名前と、保留が適用されるメールボックスのリストを表示します。

```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold | FL Name,ExchangeLocation
```

security & コンプライアンスセンター powershell に接続するには、「 [connect to security & コンプライアンスセンター powershell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)」を参照してください。

### <a name="in-place-holds"></a>インプレース保持

Exchange Online PowerShell で次のコマンドを実行して、メールボックスに適用されているインプレースホールドを識別します。 手順1で特定したインプレースホールドの GUID を使用します。 このコマンドは、保留リストの名前と、保留が適用されるメールボックスのリストを表示します。

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name,SourceMailboxes
```
インプレース保持の GUID が`cld`プレフィックスで始まる場合は、前のコマンドを実行するときに必ずプレフィックスを含めるようにしてください。

### <a name="office-365-retention-policies"></a>Office 365 のアイテム保持ポリシー

Security & コンプライアンスセンターの PowerShell で次のコマンドを実行して、メールボックスに適用されている Office 365 アイテム保持ポリシー (組織全体または特定の場所) を識別します。 手順1で特定した GUID を使用します (この場合は、[説明]、[skp]、[grp prefix] または [action サフィックス] は含まれません)。

```
Get-RetentionCompliancePolicy <hold GUID without prefix or suffix> -DistributionDetail  | FL Name,*Location
```

## <a name="identifying-mailboxes-on-hold-because-a-retention-label-has-been-applied-to-a-folder-or-item"></a>フォルダーまたはアイテムに保持ラベルが適用されているため、保留中のメールボックスを識別する

コンテンツを保持するように構成されている、またはメールボックス内の任意のフォルダーまたはアイテムにコンテンツを削除するように、ユーザーが保持ラベルを適用するときには、 *ComplianceTagHoldApplied* mailbox プロパティが**True**に設定されます。 このような場合、メールボックスは、訴訟ホールドの対象として、または Office 365 アイテム保持ポリシーに割り当てられているかのように、保留中であると見なされます。 *ComplianceTagHoldApplied*プロパティが**True**に設定されている場合は、次のような状況が発生することがあります。

- メールボックスまたはユーザーの Office 365 ユーザーアカウントが削除されると、メールボックスは[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)になります。
- メールボックス (プライマリメールボックスまたはアーカイブメールボックスが有効になっている場合) を無効にすることはできません。
- メールボックス内のアイテムが予想よりも長く保持されている可能性があります。 これは、メールボックスが保持されているため、完全に削除 (パージ) されるアイテムがないためです。

*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

保持ラベルの詳細については、「 [Office 365 の保持ラベルの概要](labels.md)」を参照してください。

## <a name="managing-mailboxes-on-delay-hold"></a>遅延保持時のメールボックスの管理

メールボックスから何らかの種類の保留が解除されると、 *DelayHoldApplied* mailbox プロパティの値は**True**に設定されます。 これは、管理フォルダーアシスタントが次回メールボックスを処理し、ホールドが削除されたことを検出したときに発生します。 これは*遅延ホールド*と呼ばれ、保留を実際に削除すると、メールボックスからデータが完全に削除 (パージ) されないようにするために30日間は遅延することになります。 これにより、管理者は、保留が実際に削除された後に削除されるメールボックスアイテムを検索したり、回復したりする機会を得ることができます。 メールボックスに遅延保持が設定されている場合でも、メールボックスが訴訟ホールドの対象であったかのように、無期限に保持されていると見なされます。 30日後、遅延保持が有効期限切れになり、Office 365 は遅延保持を自動的に削除します ( *DelayHoldApplied*プロパティを**False**に設定する)。これにより、ホールドが実際に削除されます。 *DelayHoldApplied*プロパティの値を**False**に設定すると、削除がマークされているアイテムは、次回メールボックスが管理フォルダーアシスタントによって処理されたときに削除されます。

メールボックスの*DelayHoldApplied*プロパティの値を表示するには、Exchange Online PowerShell で次のコマンドを実行します。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

遅延が期限切れになるまでの遅延を削除するには、Exchange Online PowerShell で次のコマンドを実行します。 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
*RemoveDelayHoldApplied*パラメーターを使用するには、Exchange Online で法的情報保留の役割が割り当てられている必要があることに注意してください。 

非アクティブなメールボックスの遅延ホールドを削除するには、Exchange Online PowerShell で次のコマンドを実行します。

```
Set-Mailbox <DN or Exchange GUID> -InactiveMailbox -RemoveDelayHoldApplied
```

> [!TIP]
> 以前のコマンドで非アクティブなメールボックスを指定するには、その識別名または Exchange GUID 値を使用するのが最善の方法です。 これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。 

## <a name="next-steps"></a>次のステップ

メールボックスに適用されている保留リストを識別した後、保留の期間の変更、一時的または完全に保持の削除、または Office 365 のアイテム保持ポリシーの場合は、ポリシーからの非アクティブなメールボックスを除外するなどのタスクを実行できます。 保留に関連するタスクの実行の詳細については、以下のいずれかのトピックを参照してください。

- セキュリティ & コンプライアンスセンターの PowerShell で[ \<new-retentioncompliancepolicy-addexchangelocationexception user mailbox>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/Set-RetentionCompliancePolicy?view=exchange-ps)コマンドを実行して、組織全体の Office 365 アイテム保持ポリシーからメールボックスを除外します。 このコマンドは、 *exchangelocation*プロパティの値がと等しい`All`アイテム保持ポリシーにのみ使用できることに注意してください。

- Exchange Online PowerShell で[プレフィックスまたは\<suffix> コマンドを指定せずに ExcludeFromOrgHolds hold GUID](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox?view=exchange-ps)を実行して、組織全体の Office 365 アイテム保持ポリシーから非アクティブなメールボックスを除外します。

- [Office 365 の非アクティブなメールボックスの保持期間を変更する](change-the-hold-duration-for-an-inactive-mailbox.md)

- [Office 365 の非アクティブなメールボックスを削除する](delete-an-inactive-mailbox.md)

- [保留中のクラウド ベースのメールボックスの [回復可能なアイテム] フォルダーのアイテムを削除する](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md)
