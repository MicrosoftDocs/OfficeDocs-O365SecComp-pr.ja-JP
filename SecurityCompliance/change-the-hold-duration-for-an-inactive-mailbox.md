---
title: Office 365 の非アクティブなメールボックスの保持期間を変更する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 メールボックスが非アクティブになった後は、非アクティブなメールボックスに割り当てられているホールドまたは office 365 アイテム保持ポリシーの期間を変更できます。 保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。
ms.openlocfilehash: 57b4bda5bda49785b752646174620101f8441135
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999600"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>Office 365 の非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。訴訟ホールド、インプレース ホールド、Office 365 アイテム保持ポリシー、または電子情報開示ケースと関連付けられているホールドがメールボックスに設定され、それに対応する Office 365 ユーザー アカウントが削除されると、そのメールボックスは非アクティブになります。非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間、保持されます。保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。[回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。メールボックスが非アクティブになった後でも、非アクティブなメールボックスに割り当てられているホールドや Office 365 アイテム保持ポリシーの期間を変更できます。
  
> [!IMPORTANT]
> 2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。 
  
## <a name="before-you-begin"></a>はじめに

- You have to use Exchange Online PowerShell to change the hold duration for a Litigation Hold on an inactive mailbox. You can't use the Exchange admin center (EAC). But you can use Exchange Online PowerShell or the EAC to change the hold duration for an In-Place Hold. セキュリティ/コンプライアンスセンターまたは security & コンプライアンスセンター PowerShell を使用して、Office 365 アイテム保持ポリシーの保持期間を変更できます。
    
- Exchange Online powershell または Security & コンプライアンスセンター powershell に接続するには、次のいずれかのトピックを参照してください。
    
  - [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Office 365 Security& コンプライアンスセンター PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 電子情報開示ケースに関連付けられているホールドは無限ホールド、つまり変更できるホールド期間がない点にご注意ください。アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。
    
- 非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

異なる種類のホールドや 1 つ以上の Office 365 アイテム保持ポリシーが非アクティブなメールボックスにある可能性があるため、最初の手順では、非アクティブなメールボックスにあるホールドを特定します。
  
Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスは訴訟ホールド中ということになります。 非アクティブなメールボックスにインプレース ホールド、電子情報開示ホールド、または Office 365 アイテム保持ポリシーが設定されているときは、このホールドまたはアイテム保持ポリシーの GUID が **InPlaceHolds** プロパティの値として表示されます。 たとえば、以下は5つの非アクティブなメールボックスの結果を示しています。 
  
||
|:-----|
|
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
LitigationHoldDuration: 365.00:00:00
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491}
...
DisplayName           : Mario Necaise
Name                  : marion
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {}
...
DisplayName           : Carol Olson
Name                  : carolo
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {mbxcdbbb86ce60342489bff371876e7f224}
...
DisplayName           : Abraham McMahon
Name                  : abrahamm
IsInactiveMailbox     : True
LitigationHoldEnabled : False
LitigationHoldDuration: Unlimited
InPlaceHolds          : {UniH7d895d48-7e23-4a8d-8346-533c3beac15d}
```
   
次の表は、各メールボックスを非アクティブにするのに使用された 5 つの異なる種類のホールドを示しています。
  
|**非アクティブなメールボックス**|**ホールドの種類**|**非アクティブなメールボックスのホールドを識別する方法**|
|:-----|:-----|:-----|
|Ann Beebe  <br/> |訴訟ホールド  <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|Pilar Pinilla  <br/> |インプレース ホールド  <br/> |*InPlaceHolds*  プロパティには非アクティブなメールボックスに設定されたインプレース ホールドの GUID が含まれています。ID がプレフィックスから始まっていないため、これはインプレース ホールドだとわかります。  <br/> Exchange Online PowerShell で  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL` コマンドを使用して、非アクティブのメールボックスのインプレース ホールドについての情報を取得できます。  <br/> |
|Mario Necaise  <br/> |セキュリティ & コンプライアンスセンターの組織全体にわたる Office 365 アイテム保持ポリシー  <br/> |*InPlaceHolds*  プロパティが空になっています。 これは、1 つ以上の組織全体 (または Exchange 全体) の Office 365 アイテム保持ポリシーが非アクティブなメールボックスに適用されていることを示します。 この場合は、Exchange Online PowerShell で  `Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02` プレフィックスで始まります。  <br/> <br/>非アクティブなメールボックスに適用されている Office 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。  <br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name`<br/><br/>
|Carol Olson  <br/> |特定のメールボックスに適用されるセキュリティ & コンプライアンスセンターの Office 365 アイテム保持ポリシー  <br/> |*InPlaceHolds*  プロパティに、非アクティブなメールボックスに適用されている Office 365 アイテム保持ポリシーの GUID が含まれています。GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。非アクティブなメールボックスに適用されている保持ポリシーの GUID が  `skp` プレフィックスで始まる場合、保持ポリシーが Skype for Business の会話に適用されることを示していることに注意してください。  <br/><br/> 非アクティブなメールボックスに適用されている Office 365 アイテム保持ポリシーを識別するには、Security & コンプライアンスセンターの PowerShell で次のコマンドを実行します。<br/><br/> `Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name` <br/><br/>このコマンドを実行する場合は、必ず、 `mbx` または  `skp` プレフィックスを削除してください。  <br/> |
|Abraham McMahon  <br/> |セキュリティ & コンプライアンスセンターにおける電子情報開示ケースホールド  <br/> |*InPlaceHolds*  プロパティに、非アクティブなメールボックスに設定されている電子情報開示ケース ホールドの GUID が含まれています。GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> Security & コンプライアンスセンター `Get-CaseHoldPolicy` PowerShell のコマンドレットを使用して、非アクティブなメールボックスの保留リストが関連付けられている電子情報開示ケースに関する情報を取得できます。 For example, you can run the command  `Get-CaseHoldPolicy <hold GUID without prefix> | FL Name` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` プレフィックスを削除してください。  <br/><br/> 非アクティブなメールボックスのホールドが関連付けられている電子情報開示ケースを特定するには、次のコマンドを実行します。  <br/><br/> `$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>`<br/><br/> `Get-ComplianceCase $CaseHold.CaseId | FL Name`<br/><br/><br/> **注:** 非アクティブなメールボックスに対して電子情報開示保持を使用することはお勧めしません。 That's because eDiscovery cases are intended for specific, time-bound cases related to a legal issue. いずれかの時点で、訴訟ケースが終了し、ケースに関連付けられている保留リストが削除され、電子情報開示ケースがクローズされる (または削除される) 場合があります。 実際には、非アクティブなメールボックスに配置されたホールドが電子情報開示ケースに関連付けられていて、保留が解除されるか、または電子情報開示ケースが閉じられるか削除されると、非アクティブなメールボックスは完全に削除されます。 

Office 365 アイテム保持ポリシーの詳細については、「[アイテム保持ポリシーの概要](retention-policies.md)」を参照してください。
  
## <a name="step-2-change-the-hold-duration-for-an-inactive-mailbox"></a>手順 2: 非アクティブなメールボックスの保持期間を変更する

非アクティブなメールボックスに設定されているホールドの種類 (および複数のホールドがあるかどうか) を特定したら、次は、保持期間を変更します。 
  
### <a name="change-the-duration-for-a-litigation-hold"></a>訴訟ホールドの期間を変更する

Exchange Online PowerShell を使用して、非アクティブなメールボックスに配置されている訴訟ホールドの保持期間を変更する方法を次に示します。EAC を使用することはできません。保持期間を変更するには、次のコマンドを実行します。この例では、保持期間を無期限に変更しています。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldDuration unlimited
```

結果として、非アクティブなメールボックス内のアイテムは、無期限に、あるいは、ホールドが削除されるか保持期間が別の値に変更されるまで、保持されます。
  
> [!TIP]
> 非アクティブなメールボックスを特定する最もよい方法は、 **Distinguished Name** または **Exchange GUID** の値を使用することです。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを避けられます。 
  
### <a name="change-the-duration-for-an-in-place-hold"></a>インプレース ホールドの期間を変更する

 インプレース ホールドの保持期間の変更は、EAC か Exchange Online PowerShell を使用して行うことができます。 
  
#### <a name="use-the-eac-to-change-the-hold-duration"></a>EAC を使用して保持期間を変更する

1. 変更するインプレース ホールドの名前が分かっている場合は、次の手順に進みます。 そうでない場合は、次のコマンドを実行して、非アクティブなメールボックスに設定されたインプレース ホールドの名前を取得します。 [手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得したインプレースホールドの GUID を使用します。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. In the EAC, go to **Compliance management** \> **In-Place eDiscovery &amp; Hold**.
    
3. 変更するインプレースホールドを選択し、[編集] **** ![編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)をクリックします。
    
4. On the **In-Place eDiscovery &amp; Hold** properties page, click **In-Place Hold**. 
    
5. 現在の保持期間に基づいて、次のいずれかの操作を実行します。
    
1. 無制限にアイテムを保持する場合は、 **[無期限に保持]** をクリックします。 
    
2. 特定の期間のアイテムを保持するために **、[受信日を基準**としてアイテムを保持する日数を指定する] をクリックします。 Type the number of days that you want to hold items for. 
    
    ![インプレース ホールド期間の変更に関するスクリーン ショット](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. **[保存]** をクリックします。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Exchange Online PowerShell を使用して保持期間を変更する

1. 変更するインプレース ホールドの名前が分かっている場合は、次の手順に進みます。 そうでない場合は、次のコマンドを実行して、非アクティブなメールボックスに設定されたインプレース ホールドの名前を取得します。 [手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得したインプレースホールドの GUID を使用します。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. 保持期間を変更するには、次のコマンドを実行します。この例では、ホールド期間を 2,555 日 (約 7 年間) に変更します。 
    
    ```
    Set-MailboxSearch <identity of In-Place Hold> -ItemHoldPeriod 2555
    ```

     保持期間を無制限の期間に変更するには、 _-ItemHoldPeriod unlimited_ を使用します。
  
## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックス内のアイテムの保持期間はどのように計算されますか。** 保持期間は、メールボックス アイテムを受信または作成した最初の日付から計算されます。 
    
- **保持期間を過ぎるとどうなりますか。**[回復可能なアイテム] フォルダー内のアイテムの保持期間を過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。非アクティブなメールボックスに設定されたホールドの保持期間が指定されていない場合、(非アクティブなメールボックスの保持期間が変更されない限り) [回復可能なアイテム] フォルダー内のアイテムは削除されません。 
    
- **Exchange アイテム保持ポリシーの処理は、非アクティブなメールボックスに対しても継続されますか。** メールボックスが非アクティブになったときにメールボックスに Exchange アイテム保持ポリシー (Exchange Online の機能であるメッセージング レコード管理 (MRM)) が適用されていた場合は、その非アクティブなメールボックスに対して削除ポリシー ( **Delete** 保持アクションが設定された保持タグ) の処理が継続されます。つまり、保持期間を過ぎると、削除ポリシーのタグが付けられたアイテムは [回復可能なアイテム] フォルダーに移動されます。その後、保持期間を過ぎると、それらのアイテムは非アクティブなメールボックスから消去されます。 
    
    逆に、非アクティブなメールボックスに割り当てられた保持ポリシーにアーカイブ ポリシー ( **MoveToArchive** 保持アクションが設定された保持タグ) が含まれている場合、それらはすべて無視されます。つまり、非アクティブなメールボックス内のアーカイブ ポリシーのタグが付けられたアイテムは、保持期間を過ぎてもプライマリ メールボックスに残ります。それらのアイテムは、アーカイブ メールボックスやアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されません。ユーザーは非アクティブなメールボックスにサインインできないので、アーカイブ ポリシーを処理するためにデータセンターのリソースを消費する理由はありません。 
    
- **新しい保持期間を確認するには、次のコマンドのいずれかを実行します。** 最初のコマンドは訴訟ホールド用で、2 番目はインプレース ホールド用です。 

    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | FL LitigationHoldDuration
    ```

    ```
    Get-MailboxSearch <identity of In-Place Hold> | FL ItemHoldPeriod
    ```

- **通常のメールボックスのように、管理フォルダー アシスタント (MFA) は非アクティブなメールボックスも処理します。** Exchange Online の場合、MFA は約 7 日に 1 度メールボックスを処理します。非アクティブなメールボックスの保持期間を変更したなら、 **Start-ManagedFolderAssistant** コマンドレットを使用して、非アクティブなメールボックスの新しい保持期間の処理を直ちに開始します。次のコマンドを実行します。 

    ```
    Start-ManagedFolderAssistant -InactiveMailbox <identity of inactive mailbox>
    ```
   
- **非アクティブなメールボックスに対して多数のホールドが設定されている場合、一部のホールドの GUID は表示されません。** 非アクティブなメールボックスに設定されているすべてのホールド (訴訟ホールドを除く) の GUID を表示するには、次のコマンドを実行します。 
    
    ```
    Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds
    ```
