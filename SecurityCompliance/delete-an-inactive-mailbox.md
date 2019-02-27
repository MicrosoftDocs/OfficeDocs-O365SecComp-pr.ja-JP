---
title: Office 365 で非アクティブなメールボックスを削除する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Office 365 の非アクティブなメールボックスの内容を保持する必要がなくなった場合は、保留リストを削除することによって、非アクティブなメールボックスを完全に削除することができます。ホールドを削除すると、非アクティブなメールボックスは削除するようにマークされ、処理された後は完全に削除されます。
ms.openlocfilehash: 6af107face519ac18d5b072d675e76f70dc4c4a6
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295740"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>Office 365 で非アクティブなメールボックスを削除する

非アクティブなメールボックスは、退職後に元従業員の電子メールを保持するために使用されます。非アクティブなメールボックスの内容を保持する必要がなくなった場合は、その保留リストを削除することによって、非アクティブなメールボックスを完全に削除することができます。また、複数の保留リストが非アクティブなメールボックスに配置されている可能性もあります。たとえば、非アクティブなメールボックスを訴訟ホールドの対象にして、1つ以上のインプレース保持に配置することができます。さらに、office 365 のアイテム保持ポリシー (office 365 セキュリティ&amp;コンプライアンスセンターで作成されたもの) は、非アクティブなメールボックスに適用されることがあります。非アクティブなメールボックスからすべてのホールドポリシーと Office 365 アイテム保持ポリシーを削除する必要があります。保留ポリシーとアイテム保持ポリシーを削除すると、非アクティブなメールボックスは削除のマークが付けられ、処理された後は完全に削除されます。
  
> [!IMPORTANT]
> 2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。 
  
保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](delete-an-inactive-mailbox.md#moreinfo)」セクションを参照してください。 
  
## <a name="before-you-begin"></a>開始する前に

- 非アクティブなメールボックスから訴訟ホールドを削除するには、Exchange Online PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)」を参照してください。Exchange Online PowerShell または EAC を使用して、非アクティブなメールボックスからインプレースホールドを削除することができます。 
    
- 保留リストを削除して非アクティブなメールボックスを削除する前に、非アクティブなメールボックスの内容を別のメールボックスにコピーすることができます。詳細については、「 [Office の非アクティブなメールボックスを復元する 365](restore-an-inactive-mailbox.md)」を参照してください。
    
- 非アクティブなメールボックスからホールドまたは Office 365 のアイテム保持ポリシーを削除し、そのメールボックスの回復可能な削除によって削除されたメールボックスの保存期間が切れた場合、そのメールボックスは完全に削除されます。削除すると、回復することはできません。保留リストを削除する前に、メールボックスの内容が不要になっていることを確認してください。非アクティブなメールボックスを再アクティブ化する場合は、回復することができます。詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。
    
- 非アクティブなメールボックスの詳細については、「 [Office 365 の非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)」を参照してください。
    
## <a name="step-1-identify-the-holds-on-an-inactive-mailbox"></a>手順 1: 非アクティブなメールボックスに設定されているホールドを特定する

前述のように、訴訟ホールド、インプレース ホールド、または Office 365 アイテム保持ポリシーが非アクティブなメールボックスに設定されていることがあります。最初の手順として、非アクティブなメールボックスのホールドを識別します。
  
組織内のすべての非アクティブなメールボックスの保留リストの情報を表示するために、次のコマンドを実行します。
  
```
Get-Mailbox -InactiveMailboxOnly | FL DisplayName,Name,IsInactiveMailbox,LitigationHoldEnabled,InPlaceHolds
```

**LitigationHoldEnabled** プロパティの値が **True** になっている場合、非アクティブなメールボックスが訴訟ホールドに設定されていることを示します。インプレース ホールドが非アクティブなメールボックスに設定されていると、保留リストの GUID が **InPlaceHolds** プロパティの値として表示されます。たとえば、2 つの非アクティブなメールボックスの次の結果は、1 つの訴訟ホールドが Ann Beebe に設定され、2 つのインプレース ホールドが Pilar Pinilla に設定されていることを示しています。 
  
```
DisplayName           : Ann Beebe
Name                  : annb
IsInactiveMailbox     : True
LitigationHoldEnabled : True
InPlaceHolds          : {}
...
DisplayName           : Pilar Pinilla
Name                  : pilarp
IsInactiveMailbox     : True
LitigationHoldEnabled : False
InPlaceHolds          : {c0ba3ce811b6432a8751430937152491, ba6f4ba25b62490aaaa253eea27426ab}
```

> [!TIP]
> 非アクティブなメールボックスに多数のインプレースホールドが設定されている場合は、インプレースホールドのすべての guid が表示されるわけではありません。すべてのインプレースホールド guid を表示するには、次のコマンドを実行します。`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
## <a name="step-2-remove-a-hold-from-an-inactive-mailbox"></a>手順 2:非アクティブなメールボックスから保留リストを削除する

非アクティブなメールボックスにどの種類の保留リストが設定されているか (および複数の保留リストがあるかどうか) を特定したら、次の手順ではメールボックスの保留リストを削除します。前述のように、非アクティブなメールボックスを完全に削除するには、すべての保留リストを削除する必要があります。 
  
### <a name="remove-a-litigation-hold"></a>訴訟ホールドを削除する

前述のように、非アクティブなメールボックスから訴訟ホールドを削除するには、Windows PowerShell を使用する必要があります。EAC は使用できません。次のコマンドを実行して、訴訟ホールドを削除します。
  
```
Set-Mailbox -InactiveMailbox -Identity <identity of inactive mailbox> -LitigationHoldEnabled $false
```

> [!TIP]
> 非アクティブなメールボックスを特定するには、識別名または Exchange GUID 値を使用するのが最適です。これらの値のいずれかを使用すると、正しくないメールボックスを誤って指定することを回避できます。 
  
### <a name="remove-in-place-holds"></a>インプレース ホールドを削除する

 非アクティブなメールボックスからインプレース ホールドを削除する方法は 2 つあります。 
  
- **インプレースホールドオブジェクトを削除する**完全に削除する非アクティブなメールボックスが、インプレースホールドの唯一のソースメールボックスである場合は、インプレース保持オブジェクトを削除するだけです。 
    
    > [!NOTE]
    > インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。 
  
- **インプレース ホールドのソース メールボックスとして非アクティブなメールボックスを削除する** インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>EAC を使用してインプレース ホールドを削除する

1. 削除するインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、完全に削除する非アクティブなメールボックスに設定されているインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース ホールドの GUID を使用します。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. EAC で、[**コンプライアンス管理** \> ]**の [インプレース電子情報&amp;開示の保留**] に移動します。
    
3. 削除するインプレースホールドを選択し、[編集] **** ![編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)をクリックします。
    
4. [**インプレースの電子情報開示&amp;保持**のプロパティ] ページで、[**インプレースホールド**] をクリックし、[**選択したメールボックス内の検索クエリに一致**したコンテンツを保持する] ボックスをオフにして、[**保存**] をクリックします。
    
5. [**インプレースの電子情報開示&amp;保持**] ページで、インプレースホールドをもう一度選択し、[ ****![削除] アイコン](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)をクリックします。
    
6. 警告が表示されたら、 **[はい]** をクリックして、インプレース保持を削除します。 
    
#### <a name="use-exchange-online-powershell-to-delete-an-in-place-hold"></a>Exchange Online PowerShell を使用してインプレース ホールドを削除する

1. 削除するインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース保持の GUID を使用します。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. インプレース ホールドの保留リストを無効にします。
    
```
  Set-MailboxSearch $InPlaceHold.Name -InPlaceHoldEnabled $false
```

3. インプレース ホールドを削除します。
    
```
  Remove-MailboxSearch $InPlaceHold.Name
```

#### <a name="use-the-eac-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>EAC を使用してインプレース ホールドから非アクティブなメールボックスを削除する

1. 非アクティブなメールボックスに設定されたインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、メールボックスに設定されたインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース ホールドの GUID を使用します。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. EAC で、[**コンプライアンス管理** \> ]**の [インプレース電子情報&amp;開示の保留**] に移動します。
    
3. 非アクティブなメールボックスに配置されたインプレースホールドを選択し、[ **** ![編集アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)の編集] をクリックします。
    
4. [**インプレースの電子情報開示&amp;保持**のプロパティ] ページで、[**ソース**] をクリックします。
    
5. ソース メールボックスのリストで、削除する非アクティブなメールボックスの名前をクリックして、 **[削除]**![[削除] アイコン](media/adf01106-cc79-475c-8673-065371c1897b.gif)をクリックします。
    
6. **[保存]** をクリックして変更を保存します。操作が正常に完了したことを示すメッセージが表示されます。 
    
7. 手順 1 から手順 6 を繰り返して、非アクティブなメールボックスに設定された他のインプレース保持を削除します。
    
#### <a name="use-exchange-online-powershell-to-remove-an-inactive-mailbox-from-an-in-place-hold"></a>Exchange Online PowerShell を使用してインプレース保持から非アクティブなメールボックスを削除する

インプレース ホールドに多数のソース メールボックスが含まれている場合、EAC の **[ソース]** ページに非アクティブなメールボックスがリストされないことがあります。インプレース ホールドを編集する場合、 **[ソース]** ページに最大 3,000 のメールボックスが表示されます。非アクティブなメールボックスが **[ソース]** ページにリストされない場合は、Exchange Online PowerShell を使用してインプレース ホールドから削除できます。 
  
1. 非アクティブなメールボックスに設定されたインプレース保持のプロパティを含む変数を作成します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース保持の GUID を使用します。
    
```
  $InPlaceHold = Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID>
```

2. 非アクティブなメールボックスがインプレース ホールドのソース メールボックスとしてリストされていることを確認します。 
    
```
  $InPlaceHold.Sources
```

   **注:** インプレースホールドの*Sources*プロパティは、 *LegacyExchangeDN*プロパティによってソースメールボックスを識別します。このプロパティは、非アクティブなメールボックスを一意に識別するので、インプレース保持の*Sources*プロパティを使用すると、間違ったメールボックスが削除されないようにすることができます。これにより、2つのメールボックスが同じエイリアスまたは SMTP アドレスを持つ場合に問題が発生しないようにすることもできます。 
   
3. 変数のソース メールボックスのリストから非アクティブなメールボックスを削除します。前の手順のコマンドで返された非アクティブなメールボックスの **LegacyExchangeDN** を必ず使用してください。 
    
```
  $InPlaceHold.Sources.Remove("<LegacyExchangeDN of the inactive mailbox>")
```

    For example, the following command removes the inactive mailbox for Pilar Pinilla.
    
  ```
  $InPlaceHold.Sources.Remove("/o=contoso/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=9c8dfff651ec4908950f5df60cbbda06-pilarp")
  ```

4. 変数のソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。
    
```
  $InPlaceHold.Sources
```

5. 非アクティブなメールボックスを含まないソース メールボックスの更新されたリストで、インプレース ホールドを変更します。
    
```
  Set-MailboxSearch $InPlaceHold.Name -SourceMailboxes $InPlaceHold.Sources
```

6. インプレース ホールドのソース メールボックスのリストから非アクティブなメールボックスが削除されていることを確認します。
    
```
  Get-MailboxSearch $InPlaceHold.Name | FL Sources
```

## <a name="more-information"></a>詳細情報

- **非アクティブなメールボックスは、回復可能な削除によって削除されたメールボックスの一種です。** Exchange Onlineで、回復可能な削除によって削除されたメールボックスは、メールボックスが削除されてはいるものの、特定の保持期間内であれば回復することができます。Exchange Online で回復可能な削除によって削除されたメールボックスの保存期間は 30 日です。つまり、回復可能な削除によって削除されてから 30 日以内なら、メールボックスを復元できます。30 日が経過すると、回復可能な削除によって削除されたメールボックスは完全削除のマークが付けられ、回復できなくなります。 
    
- **非アクティブなメールボックスに対する保留リストを削除した後はどうなりますか。** 非アクティブなメールボックスは、他の回復可能な削除によって削除されたメールボックスと同様に扱われ、回復可能な削除によって削除されたメールボックスの保持期間である 30 日が経過した後に完全削除のマークが付けられます。この保存期間は、メールボックスが最初に非アクティブになった日から始まります。この日付は、回復可能な削除によって削除された日付と呼ばれ、対応する Office 365 ユーザー アカウントが削除された日、またはExchange Online メールボックスが **Remove-Mailbox** コマンドレットを使用して削除された日になります。回復可能な削除によって削除された日は、保留リストを削除した日ではありません。 
    
- **ホールドを解除した直後に、非アクティブなメールボックスは完全に削除されますか。** 非アクティブなメールボックスが回復可能な削除によって削除された日付が 30 日より前であっても、ホールドを解除するとすぐにメールボックスが完全に削除されるということはありません。メールボックスに完全に削除するようマークが付けられ、次に処理されるときに削除されます。 
    
- **削除済みメールボックスの保持期間は非アクティブなメールボックスにどのように影響しますか?** 非アクティブなメールボックスの回復可能な削除によって、保持期間が削除されてから30日が経過すると、そのメールボックスは完全削除のマークが付けられます。ただし、非アクティブなメールボックスに過去30日間以内に削除された削除済みの日付がある場合は、削除済みメールボックスの保持期間が経過するまでメールボックスを回復することができます。詳細については、「 [Exchange Online でユーザーメールボックスを削除または復元](https://go.microsoft.com/fwlink/?linkid=856835)する」を参照してください。回復可能な削除によって削除されたメールボックスの保持期間が経過すると、非アクティブなメールボックスを回復するための手順に従います。詳細については、「 [Office 365 の非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)」を参照してください。
    
- **保留が解除された後、非アクティブなメールボックスに関する情報をどのように表示しますか。** 保持が削除され、非アクティブなメールボックスが回復可能な削除によって削除されたメールボックスに戻された後は、**メールボックスの取得**コマンドレットで*inactivemailboxonly*パラメーターを使用して返されることはありません。ただし、 **SoftDeletedMailbox**コマンドを使用して、メールボックスに関する情報を表示することができます。例えば： 
    
```
  Get-Mailbox -SoftDeletedMailbox -Identity pilarp | FL Name,Identity,LitigationHoldEnabled,In
  Placeholds,WhenSoftDeleted,IsInactiveMailbox
  Name                   : pilarp
  Identity               : Soft Deleted Objects\pilarp
  LitigationHoldEnabled  : False
  InPlaceHolds           : {}
  WhenSoftDeleted        : 10/30/2014 1:19:04 AM
  IsInactiveMailbox      : False
```
  
上記の例では、 *whensoftdeleted*プロパティは、回復可能な削除によって削除された日付 (この例では、2014年10月30日) を示しています。この回復可能な削除によって削除されたメールボックスが以前は、保留が削除された非アクティブなメールボックスであった場合、 *whensoftdeleted*プロパティの値の30日後に完全に削除されます。この場合、2014年11月30日以降、メールボックスは完全に削除されます。

