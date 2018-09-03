---
title: 保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 8/22/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a8bdcbdd-9298-462f-b889-df26037a990c
description: 'アーカイブ先のメールボックスを有効にして、Office 365 のメールボックスの回復可能なアイテム] フォルダーのサイズを大きくにはアーカイブの自動拡張を有効にします。 '
ms.openlocfilehash: cd2d07e6ef1637343798ccb71870c8d436f10574
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782094"
---
# <a name="increase-the-recoverable-items-quota-for-mailboxes-on-hold"></a>保持中のメールボックスの [回復可能なアイテム] のクォータを拡大する

デフォルトの保持ポリシー、MRM ポリシーを既定の名前-は Exchange Online のメールボックス新規作成] を自動的に適用されているにはには、名前付きのアイテムの回復可能な 14 日間の移動をアーカイブする保持タグが含まれています。この保持タグは、14 日間の保存期間は、アイテムの有効期限が切れる後アイテムをユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダーから、ユーザーのアーカイブ メールボックスの回復可能なアイテム] フォルダーに移動します。これを実現するには、ユーザーのアーカイブ メールボックスを有効にする必要があります。アーカイブ先のメールボックスが有効でない場合何も起こりません、上のメールボックスのフォルダーを保持する回復可能なアイテムのアイテムは、14 日間の保存期間が終了した後アーカイブ メールボックスに移動されていないことを意味します。保留中のメールボックスからは削除されず、ためことは、回復可能なアイテム] フォルダーの記憶域のクォータを超えた可能性があるユーザーのアーカイブ メールボックスが有効になっていない場合に特に。 
  
この制限を超える可能性を減らすためには、回復可能なアイテム] フォルダーの記憶域のクォータが自動的に増加 30 GB から 100 GB を保留リストに格納されるメールボックス Exchange オンライン。アーカイブ先のメールボックスが有効な場合、アーカイブ メールボックスの回復可能なアイテム フォルダーの記憶域のクォータも増加 30 GB から 100 GB にします。アーカイブの自動拡張機能の Exchange でオンラインになって、ユーザーのアーカイブの回復可能なアイテム フォルダーの記憶域のクォータの制限が解除されます。
  
  [回復可能なアイテム] フォルダーの記憶域クォータを次の表にまとめます。 
  
|**[回復可能なアイテム] フォルダーの場所**|**保持中でないメールボックス**|**保持中のメールボックス**|
|:-----|:-----|:-----|
|プライマリ メールボックス  <br/> |30 GB  <br/> |100 GB  <br/> |
|アーカイブ先のメールボックス<sup>\*</sup> <br/> |無制限  <br/> |無制限  <br/> |
|**[回復可能なアイテム] フォルダーの記憶域クォータの合計** <br/> |無制限  <br/> |無制限  <br/> |
   
> [!NOTE]
> <sup>\*</sup>アーカイブ先のメールボックスの最初の記憶域のクォータでは、100 GB を Exchange Online (プラン 2) のライセンスを持つユーザーです。ただしとアーカイブの自動拡張有効になって保留中のメールボックス、記憶域のクォータの両方に対して、アーカイブ先のメールボックスと、回復可能なアイテム] フォルダーが 110 GB に増加します。追加のアーカイブ ・ ストレージ ・ スペースが必要な場合に準備されますされ、アーカイブ ・ ストレージの無制限の量です。自動拡張の詳細については、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。 
  
保持中のメールボックスのプライマリ メールボックスに含まれる [回復可能なアイテム] フォルダーの記憶域クォータが上限に近づいたら、次の対策を講じることができます。
  
- **アーカイブ先のメールボックスを有効にしてアーカイブの自動拡張を有効にする**だけで、アーカイブ メールボックスを有効にして、Exchange の自動拡張のアーカイブ機能をオンにし、回復可能なアイテム] フォルダーに、無制限のストレージ容量を有効にできますオンライン。これは、結果、110 GB のプライマリ メールボックスとユーザーのアーカイブの回復可能なアイテム フォルダーのストレージ容量の無制限の量で回復可能なアイテムのフォルダーにします。参照してください方法: [Office 365 のセキュリティのアーカイブ メールボックスを有効にする&amp;コンプライアンス センター](enable-archive-mailboxes.md)し、 [Office 365 で無制限のアーカイブを有効に](enable-unlimited-archiving.md)します。
    
    > [!NOTE]
    > 期限切れアイテムが移動されるため、メールボックスを処理するため、アシスタントを手動で開始する管理フォルダー アシスタントを実行する場合、回復可能なアイテム] フォルダーの記憶域のクォータを超えるの近くにあるメールボックスのアーカイブを有効にした後、アーカイブ メールボックスの回復可能なアイテム] フォルダーです。手順については、[手順 4](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)を参照してください。新しいアーカイブ メールボックスにユーザーのメールボックス内のアイテムを移動する場合があることに注意してください。アーカイブ メールボックスを有効にした後、この可能性があります発生することをユーザーに示すことを検討してください。 
  
- **上のメールボックスのユーザー設定の保持ポリシーの保持を作成する**のに加えて、アーカイブ メールボックスを有効にして、証拠保全や場所に置くと、上のメールボックスのアーカイブの自動拡張することも上のメールボックスのカスタムのリテンション ・ ポリシーを作成するには保持します。これは、みましょうする保持ポリシーを適用する保留リストに登録されていないメールボックスに適用される既定の MRM ポリシーとは異なる保留中のメールボックスに。これにより、保留中のメールボックス用に設計された保持タグを適用することができます。[回復可能なアイテム] フォルダーに新しい保持タグの作成が含まれます。 
    
このトピックの残りの部分では、保持中のメールボックスのカスタム保存ポリシーを作成する手順について説明します。
  
[手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する](#step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder)

[[手順 2: 保留中のメールボックスの新しい保存ポリシーを作成する](#step-2-create-a-new-retention-policy-for-mailboxes-on-hold)

[手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する](#step-3-apply-the-new-retention-policy-to-mailboxes-on-hold)

[(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する](#optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings)
  
## <a name="step-1-create-a-custom-retention-tag-for-the-recoverable-items-folder"></a>手順 1:[回復可能なアイテム] フォルダーのカスタム保持タグを作成する

最初のステップでは、回復可能なアイテム] フォルダーのカスタム保持期間タグ (RPT の保持ポリシー タグと呼ばれます) を作成します。説明したようは、この RPT は、ユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダーからアイテムをユーザーのアーカイブ メールボックスの回復可能なアイテム] フォルダーに移動します。[回復可能なアイテム] フォルダーに RPT を作成する PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。 
  
1. [Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)
    
2. [回復可能なアイテム] フォルダーの新しい RPT を作成するには、次のコマンドを実行します。  
    
    ```
    New-RetentionPolicyTag -Name <Name of RPT> -Type RecoverableItems -AgeLimitForRetention <Number of days> -RetentionAction MoveToArchive
    ```

    たとえば、次のコマンドを実行すると、[回復可能なアイテム] フォルダー用に "Recoverable Items 30 days for mailboxes on hold" という名前の RPT が作成され、保持期間が 30 日間に設定されます。これは、アイテムが [回復可能なアイテム] フォルダーに移動されてから 30 日後に、そのアイテムがユーザーのアーカイブ メールボックス内の [回復可能なアイテム] フォルダーに移動されるということです。
    
    ```
    New-RetentionPolicyTag -Name "Recoverable Items 30 days for mailboxes on hold" -Type RecoverableItems -AgeLimitForRetention 30 -RetentionAction MoveToArchive
    ```

    > [!TIP]
    > 回復可能なアイテム RPT の保存期間 ( _AgeLimitForRetention_パラメーターで定義されている) が RPT を適用するメールボックスの削除済みアイテムの保存期間と同じことをお勧めします。これにより、ユーザー全体の削除済みアイテムの保持期間、アーカイブ メールボックスに移動する前に削除済みアイテムを回復します。前の例では、保存期間は、メールボックスの削除済みアイテムの保存期間は 30 日でもあるという前提に基づいて、30 日に設定されました。既定の 14 日間は、削除済みアイテムを保持する Exchange Online のメールボックスを構成するとします。最大 30 日以内にこの設定を変更することができます。詳細については、 [Exchange オンラインのメールボックスの削除済みアイテムの保存期間の変更](https://go.microsoft.com/fwlink/p/?LinkId=286940)を参照してください。 
  
## <a name="step-2-create-a-new-retention-policy-for-mailboxes-on-hold"></a>手順 2: 保持中のメールボックスの新しいアイテム保持ポリシーを作成する

次の手順では、新しいアイテム保持ポリシーを作成し、そのポリシーに保持タグ (手順 1 で作成した回復可能なアイテムの RPT を含む) を追加します。この新しいポリシーは、次の手順で保持中のメールボックスに適用します。  
  
新しいアイテム保持ポリシーを作成する前に、追加する保持タグを決定します。Default MRM Policy に追加されている保持タグの一覧、および新しい保持タグを作成する方法については、以下を参照してください。
  
- [既定の保持ポリシーでは、Exchange オンライン](https://go.microsoft.com/fwlink/p/?LinkId=746954)
    
- [アイテム保持ポリシー タグをサポートする既定のフォルダー](https://go.microsoft.com/fwlink/p/?LinkId=746957)
    
- [保持ポリシーの作成](https://go.microsoft.com/fwlink/p/?LinkId=404422)」の「保持タグを作成する」セクションです。
    
EAC または Exchange のオンライン PowerShell を使用すると、保持ポリシーを作成します。
  
### <a name="use-the-eac-to-create-a-retention-policy"></a>EAC を使用してアイテム保持ポリシーを作成する
  
1. EAC では、**コンプライアンスの管理**に移動\> **・ リテンション ・ ポリシー**の**追加**] をクリックし、![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。
    
2. **[新しい保持ポリシー]** ページの **[名前]** に、アイテム保持ポリシーの目的を説明する名前 (例: **MRM Policy for Mailboxes on Hold**) を入力します。  
    
3. **保持タグ**では、下の [**追加**] をクリックします![アイコンの追加](media/ITPro-EAC-AddIcon.gif)。
    
4. 保持タグの一覧で、手順 1 で作成した回復可能なアイテムの RPT を選択し、**[追加]** をクリックします。
    
    ![カスタムの [回復可能なアイテム] 保持タグを選択する](media/eb49866b-bdef-4fcd-a6d9-01607c01249b.png)
  
5. アイテム保持ポリシーに追加する保持タグを選択します。たとえば、Default MRM Policy に含まれているのと同じタグを追加します。
    
6. 保持タグの追加が完了したら、**[OK]** をクリックします。
    
7. **[保存]** をクリックして新しいアイテム保持ポリシーを作成します。 
    
    アイテム保持ポリシーにリンクされている保持タグが詳細ウィンドウに表示されることに注目してください。
    
    ![アイテム保持ポリシーにリンクした保持タグが詳細ウィンドウに表示される](media/dad1c8f4-9928-4d6d-991a-6f6c5194eceb.png)
  
### <a name="use-exchange-online-powershell-to-create-a-retention-policy"></a>Exchange オンライン PowerShell を使用して、保持ポリシーを作成するには
  
保持中のメールボックスの新しいアイテム保持ポリシーを作成するには、次のコマンドを実行します。  
  
```
New-RetentionPolicy <Name of retention policy>  -RetentionPolicyTagLinks <list of retention tags>

```

たとえば次のコマンドを実行すると、前の図に示されているアイテム保持ポリシーとそれにリンクされている保持タグが作成されます。
  
```
New-RetentionPolicy "MRM Policy for Mailboxes on Hold"  -RetentionPolicyTagLinks "Recoverable Items 30 days for mailboxes on hold","1 Month Delete","1 Week Delete","1 Year Delete","5 Year Delete","6 Month Delete","Default 2 year move to archive","Junk Email","Never Delete","Personal 1 year move to archive","Personal 5 year move to archive"
```
  
## <a name="step-3-apply-the-new-retention-policy-to-mailboxes-on-hold"></a>手順 3:保持中のメールボックスに新しいアイテム保持ポリシーを適用する

最後のステップでは、組織内で保留中のメールボックスに手順 2 で作成した新しい保持ポリシーを適用します。EAC または Exchange のオンライン PowerShell を使用するには、メールボックスを 1 つまたは複数のメールボックスに保持ポリシーを適用します。 
  
### <a name="use-the-eac-to-apply-the-new-retention-policy"></a>EAC を使用して新しい保持ポリシーを適用する
  
1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. リスト ビューで、リテンション ・ ポリシーを適用するメールボックスを選択し、し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
3. **[ユーザー メールボックス]** ページで、**[メールボックスの機能]** をクリックします。
    
4. **[アイテム保持ポリシー]** から、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。
    
EAC を使用して、アイテム保持ポリシーを複数のメールボックスに適用することもできます。
  
1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. リスト ビューで、Shift キーまたは Ctrl キーを使用して複数のメールボックスを選択します。
    
3. 詳細ウィンドウで、 **[その他のオプション]** をクリックします。
    
4. **[アイテム保持ポリシー]** 下で **[更新]** をクリックします。
    
5. **[アイテム保持ポリシーの一括割り当て]** ページで、手順 2 で作成したアイテム保持ポリシーを選択し、**[保存]** をクリックします。  
    
### <a name="use-exchange-online-powershell-to-apply-the-new-retention-policy"></a>Exchange オンライン PowerShell を使用して、新しい保持ポリシーを適用するのには
  
Exchange オンライン PowerShell を使用すると、1 つのメールボックスに新しいアイテム保持ポリシーを適用します。PowerShell の真の力を使えること、1 つのコマンドで、インプレース保持、または証拠保全は、すべてのメールボックスへの新しい保存ポリシーを適用する組織内のメールボックスを保持するすべてを迅速に特定します。Exchange PowerShell を使用する 1 つまたは複数のメールボックスに保持ポリシーを適用するいくつかの例を次に示します。すべての例は、手順 2 で作成した保持ポリシーを適用します。
  
この例では、Pilar Pinilla のメールボックスに新しいアイテム保持ポリシーを適用します。
  
```
Set-Mailbox "Pilar Pinilla" -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

この例では、組織内の訴訟ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。
  
```
$LitigationHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'}
```

```
$LitigationHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

この例では、組織内のインプレース ホールド中のすべてのメールボックスに新しいアイテム保持ポリシーを適用します。
  
```
$InPlaceHolds = Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null}
```

```
$InPlaceHolds.DistinguishedName | Set-Mailbox -RetentionPolicy "MRM Policy for Mailboxes on Hold"
```

**Get-Mailbox** コマンドレットを使用すると、新しいアイテム保持ポリシーが適用されたことを確認できます。 
  
以下は、前の例で実行したコマンドを使用して、"MRM Policy for Mailboxes on Hold" というアイテム保持ポリシーが、訴訟ホールド中のメールボックスとインプレース ホールド中のメールボックスに適用されたことを確認する例です。
  
```
Get-Mailbox "Pilar Pinilla" | Select RetentionPolicy
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.LitigationHoldEnabled -eq 'True'} | FT DisplayName,RetentionPolicy -Auto
```

```
Get-Mailbox -ResultSize unlimited | Where-Object {$_.InPlaceHolds -ne $null} | FT DisplayName,RetentionPolicy -Auto
```
  
## <a name="optional-step-4-run-the-managed-folder-assistant-to-apply-the-new-retention-settings"></a>(省略可能) 手順 4:管理フォルダー アシスタントを実行して、新しい保持設定を適用する

保留中のメールボックスを新しい保存ポリシーを適用すると、かかることが最大 7 日間 Exchange オンライン管理フォルダー アシスタントの新しい保存ポリシーの設定を使用してこれらのメールボックスを処理します。待たず、管理フォルダー アシスタントを実行するのに新しい保持ポリシーを適用したメールボックスを処理するのには、アシスタントを手動で開始するのに**開始 ManagedFolderAssistant**コマンドレットを使用することができます。 
  
Pilar Pinilla のメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。
  
```
Start-ManagedFolderAssistant "Pilar Pinilla"
```

保持中のすべてのメールボックスに対して管理フォルダー アシスタントを開始するには、次のコマンドを実行します。
  
```
$MailboxesOnHold = Get-Mailbox -ResultSize unlimited | Where-Object {($_.InPlaceHolds -ne $null) -or ($_.LitigationHoldEnabled -eq "True")}
```

```
$MailboxesOnHold.DistinguishedName | Start-ManagedFolderAssistant
```

## <a name="more-information"></a>詳細情報

- ユーザーのアーカイブ メールボックスを有効にした後は、(回復可能なアイテム] フォルダー内だけでなくアイテム) は、自分のメールボックス内のアイテムをアーカイブ メールボックスに移動する可能性があることをユーザーに示すことを検討します。これは、Exchange Online のメールボックスに割り当てられている既定の MRM ポリシーには、アイテムがメールボックスに配信されるかによって作成された日付より後の 2 年間アーカイブ メールボックスにアイテムを移動する保持タグ (名前付きの既定の 2 年間は、アーカイブに移動) が含まれているため、ユーザーです。詳細については、 [Exchange のオンラインでの保持ポリシーの既定値](https://go.microsoft.com/fwlink/p/?LinkId=746954)を参照してください。
    
- ユーザーのアーカイブ メールボックスを有効にした後は、回復できることをユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムを削除するも伝えることがあります。Outlook のアーカイブ先のメールボックスの**削除済みアイテム**フォルダーを選択し、[**ホーム**] タブの [**サーバーから削除済みアイテムの回復**では、ことができます。削除済みアイテムの回復の詳細については、[回復は、Outlook のウィンドウ内の項目を削除](https://go.microsoft.com/fwlink/p/?LinkId=624829)を参照してください。 
