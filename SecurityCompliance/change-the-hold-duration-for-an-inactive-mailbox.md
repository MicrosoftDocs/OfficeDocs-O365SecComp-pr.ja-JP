---
title: Office 365 での非アクティブなメールボックスの保持期間を変更します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/29/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: bdee24ed-b8cf-4dd0-92ae-b86ec4661e6b
description: Office 365 のメールボックスを無効になりましたが後、は、保留中または非アクティブなメールボックスに割り当てられている Office 365 の保持ポリシーの期間を変更できます。保留期間は、[回復可能なアイテムのフォルダーが保持されているどのくらいの時間の項目を定義します。
ms.openlocfilehash: 22bd9f9294b625a38d243f6235097d1aee437121
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532185"
---
# <a name="change-the-hold-duration-for-an-inactive-mailbox-in-office-365"></a>Office 365 での非アクティブなメールボックスの保持期間を変更します。

非アクティブなメールボックスは、退職して組織を離れた元従業員の電子メールを保持するために使用します。訴訟ホールド、インプレース ホールド、Office 365 アイテム保持ポリシー、または電子情報開示ケースと関連付けられているホールドがメールボックスに設定され、それに対応する Office 365 ユーザー アカウントが削除されると、そのメールボックスは非アクティブになります。非アクティブなメールボックスのコンテンツは、非アクティブになる前にメールボックスに設定された保持期間の間、保持されます。保持期間は、[回復可能なアイテム] フォルダー内のアイテムを保持する期間を定義します。[回復可能なアイテム] フォルダー内のアイテムの保持期間が過ぎると、アイテムは非アクティブなメールボックスから完全に削除 (消去) されます。メールボックスが非アクティブになった後でも、非アクティブなメールボックスに割り当てられているホールドや Office 365 アイテム保持ポリシーの期間を変更できます。
  
> [!IMPORTANT]
> 2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。 
  
## <a name="before-you-begin"></a>はじめに

- 証拠保全を非アクティブなメールボックスの保持期間を変更するのには Exchange のオンライン PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。ですが、埋め込みの保持の保持期間を変更するのには Exchange オンライン PowerShell または、EAC を使用することができます。Office 365 のセキュリティを使用することができます&amp;センターのコンプライアンスやセキュリティ&amp;コンプライアンス センターの PowerShell Office 365 の保持ポリシーの保持期間を変更します。
    
- Exchange オンライン PowerShell またはセキュリティに接続する&amp;コンプライアンス センター PowerShell、次のトピックのいずれかを参照してください。
    
  - [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
  - [Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=799771)
    
- 電子情報開示ケースに関連付けられているホールドは無限ホールド、つまり変更できるホールド期間がない点にご注意ください。アイテムは、ホールドが削除されて非アクティブなメールボックスが削除されるまで無限に保持されます。
    
- 非アクティブなメールボックスの詳細については、 [Office 365 でアクティブでないメールボックス](inactive-mailboxes-in-office-365.md)を参照してください。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

異なる種類のホールドや 1 つ以上の Office 365 アイテム保持ポリシーが非アクティブなメールボックスにある可能性があるため、最初の手順では、非アクティブなメールボックスにあるホールドを特定します。
  
Exchange Online PowerShell で次のコマンドを実行して、組織内のすべての非アクティブなメールボックスのホールドの情報を表示します。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,LitigationHoldDuration,InPlaceHolds
```
   
**True**の場合、 **LitigationHoldEnabled**プロパティの値は、証拠保全が非アクティブなメールボックスであることを示します。埋め込みを保持する、電子的証拠開示、または Office 365 のリテンション ・ ポリシーがアクティブでないメールボックスに配置されます、 **InPlaceHolds**プロパティの値として保持、または保持ポリシーの GUID が表示されます。たとえば、次に示します 5 の非アクティブなメールボックスの結果。 
  
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
|Mario Necaise  <br/> |セキュリティで Office 365 保持ポリシーを組織全体にわたる&amp;コンプライアンス センター  <br/> |*InPlaceHolds*プロパティは空です。これは、非アクティブなメールボックスを 1 つまたは複数の組織全体または (全体で Exchange) Office 365 の保存のポリシーを適用することを示します。この例では、実行することができます、' Get OrganizationConfig | 選択オブジェクト-ExpandProperty InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies that are applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> <br/>To identity the Office 365 retention policy that's applied to the inactive mailbox, run the following command in Security &amp; Compliance Center PowerShell.  <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名 '<br/><br/>
|Carol Olson  <br/> |セキュリティの保持ポリシーを office 365&amp;コンプライアンス センターは、特定のメールボックスに適用  <br/> |*InPlaceHolds*  プロパティに、非アクティブなメールボックスに適用されている Office 365 アイテム保持ポリシーの GUID が含まれています。GUID が  `mbx` プレフィックスで始まっているため、これは特定のメールボックスに適用されたアイテム保持ポリシーであることがわかります。非アクティブなメールボックスに適用されている保持ポリシーの GUID が  `skp` プレフィックスで始まる場合、保持ポリシーが Skype for Business の会話に適用されることを示していることに注意してください。  <br/><br/> セキュリティの次のコマンドを実行する非アクティブなメールボックスに適用されている保持ポリシーを Office 365 の id、&amp;コンプライアンス センター PowerShell。<br/><br/> ' Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名` <br/><br/>Be sure to remove the  `mbx` or  `skp' このコマンドを実行するときにプレフィックスです。  <br/> |
|Abraham McMahon  <br/> |電子的証拠開示の場合は、セキュリティの保持&amp;コンプライアンス センター  <br/> |*InPlaceHolds*  プロパティに、非アクティブなメールボックスに設定されている電子情報開示ケース ホールドの GUID が含まれています。GUID が  `UniH` プレフィックスで始まっているため、これは電子情報開示ケース ホールドであることがわかります。  <br/> 使用することができます、`Get-CaseHoldPolicy`セキュリティのコマンドレット&amp;コンプライアンス センターの PowerShell に非アクティブなメールボックスの保留リストが関連付けられている場合は電子的証拠開示に関する情報を取得します。コマンドを実行することができますたとえば、' Get CaseHoldPolicy<hold GUID without prefix> | FL 名` to display the name of the case hold that's on the inactive mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the inactive mailbox is associated with, run the following commands.  <br/><br/> `$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/> `Get ComplianceCase $CaseHold.CaseId | FL 名 '<br/><br/><br/> **注:** 非アクティブなメールボックスを保持している電子的証拠開示を使用してお勧めしません。電子的証拠開示の場合は、法的な問題に関連する場合は、特定の期限付きにするためです。いくつかの時点では、訴訟事件を終了可能性がありますが、サポート案件に関連付けられている保留リストを削除して電子的証拠開示の場合を閉じる (または削除) します。実際には、非アクティブなメールボックスに配置されている保留リストは、電子的証拠開示のサポート案件に関連付けられていると保留を解除、または電子的証拠開示のケースが閉じられるか、削除、非アクティブなメールボックス完全に削除されます。 

Office 365 のリテンション ・ ポリシーの詳細については、[保存ポリシーの概要](retention-policies.md)を参照してください。
  
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

1. 変更する埋め込みのままの名前がわかっている場合は、次の手順に進みます。それ以外の場合、非アクティブなメールボックスに配置されている埋め込みのままの名前を取得するのには次のコマンドを実行します。埋め込み保持[手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得した GUID を使用します。

    ```
    Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
    ```

2. **コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。
    
3. 埋め込みの保留、変更する] を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. **インプレース電子情報開示&amp;を保持**プロパティ] ページで、**場所に保持**] をクリックします。 
    
5. 現在の保持期間に基づいて、次のいずれかの操作を実行します。
    
1. 無制限にアイテムを保持する場合は、 **[無期限に保持]** をクリックします。 
    
2. 特定の期間のアイテムを保持するために **、受信した日を基準にして項目を保持する日数を指定してください**] をクリックします。項目を保持する日数を入力します。 
    
    ![インプレース ホールド期間の変更に関するスクリーン ショット](media/cfcfd92a-9d65-40c0-90ef-ab72697b0166.png)
  
6. **[保存]** をクリックします。
    
#### <a name="use-exchange-online-powershell-to-change-the-hold-duration"></a>Exchange Online PowerShell を使用して保持期間を変更する

1. 変更する埋め込みのままの名前がわかっている場合は、次の手順に進みます。それ以外の場合、非アクティブなメールボックスに配置されている埋め込みのままの名前を取得するのには次のコマンドを実行します。埋め込み保持[手順 1](#step-1-identify-the-holds-on-an-inactive-mailbox)で取得した GUID を使用します。

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
