---
title: Office 365 で、非アクティブなメールボックスを削除します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/5/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f5caf497-5e8d-4b7a-bfff-d02942f38150
description: Office 365 の非アクティブなメールボックスの内容を保持するために不要になった場合は、保留リストを削除することによって、非アクティブなメールボックスを完全に削除できます。保留リストを削除した後には、非アクティブなメールボックスは削除用にマークされてし、それが処理された後は完全に削除します。
ms.openlocfilehash: 91b73fff6ca319735289abe7ea9351b5fba931a0
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531621"
---
# <a name="delete-an-inactive-mailbox-in-office-365"></a>Office 365 で、非アクティブなメールボックスを削除します。

非アクティブなメールボックスは、彼または彼女が組織を離れた後に、以前の社員の電子メールを保持するために使用されます。非アクティブなメールボックスの内容を保存する必要がなくなった、保留リストを削除することによって、非アクティブなメールボックスを完全に削除できます。また、非アクティブなメールボックスに複数の保留リストを配置することが可能です。などの証拠保全し、埋め込みを保持する 1 つまたは複数、非アクティブなメールボックスを配置する可能性があります。Office 365 保持ポリシーさらに、(Office 365 のセキュリティで作成された&amp;コンプライアンス センター) 非アクティブなメールボックスに適用することがあります。削除する非アクティブなメールボックスからすべての保留リストと Office 365 の保持ポリシーを削除する必要が。保持し、保持ポリシーを削除した後非アクティブなメールボックスは削除用にマークし、それが処理された後は完全に削除します。
  
> [!IMPORTANT]
> 2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。 
  
保留リストが非アクティブなメールボックスから削除された結果の詳細については、「[詳細情報](delete-an-inactive-mailbox.md#moreinfo)」セクションを参照してください。 
  
## <a name="before-you-begin"></a>開始する前に

- 証拠保全を非アクティブなメールボックスから削除するのには Exchange のオンライン PowerShell を使用する必要があります。Exchange 管理センター (EAC) を使用することはできません。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/?linkid=396554)を参照してください。非アクティブなメールボックスから、埋め込みの保持を削除するのには、Exchange オンライン PowerShell または、EAC を使用できます。 
    
- 保留を解除し、非アクティブなメールボックスを削除する前に、非アクティブなメールボックスの内容を別のメールボックスにコピーできます。詳細については、 [Office 365 で、非アクティブなメールボックスの復元](restore-an-inactive-mailbox.md)を参照してください。
    
- 非アクティブなメールボックスから、保留中または Office 365 の保持ポリシーを削除すると、ソフト削除済みメールボックスの保存期間、メールボックスの有効期限が切れて、メールボックスを完全に削除されます。削除は元に戻せません。保留リストを削除する前にメールボックスの内容は必要がなくなったことを確認します。アクティブでないメールボックスを再アクティブ化する場合を回復することができます。詳細については、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。
    
- 非アクティブなメールボックスの詳細については、 [Office 365 でアクティブでないメールボックス](inactive-mailboxes-in-office-365.md)を参照してください。
    
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
> 多くの場所を保持するが非アクティブなメールボックスに配置されている場合、埋め込み保持の Guid のすべてが表示されます。すべての埋め込みを保持の Guid を表示するのには、次のコマンドを実行することができます。`Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox> | Select-Object -ExpandProperty InPlaceHolds`
  
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
  
- **埋め込みを押しながらオブジェクトを削除**非アクティブなメールボックスを完全に削除するが、埋め込みの保持の唯一の元のメールボックスの場合は、埋め込みの保持オブジェクトだけで削除できます。 
    
    > [!NOTE]
    > インプレース ホールド オブジェクトを削除する前に、保留リストを無効にする必要があります。保留リストを有効にしているインプレース ホールド オブジェクトを削除しようとすると、エラー メッセージが表示されます。 
  
- **インプレース ホールドのソース メールボックスとして非アクティブなメールボックスを削除する** インプレース ホールドの他のソース メールボックスを保持する場合は、ソース メールボックスのリストから非アクティブなメールボックスを削除して、インプレース ホールド オブジェクトを保持することができます。 
    
#### <a name="use-the-eac-to-delete-an-in-place-hold"></a>EAC を使用してインプレース ホールドを削除する

1. 削除するインプレース ホールドの名前が分かっている場合は、次の手順に進むことができます。そうでない場合は、次のコマンドを実行して、完全に削除する非アクティブなメールボックスに設定されているインプレース ホールドの名前を取得します。[手順 1: 非アクティブなメールボックスに設定されているホールドを特定する](delete-an-inactive-mailbox.md#step1) で取得したインプレース ホールドの GUID を使用します。
    
```
  Get-MailboxSearch -InPlaceHoldIdentity <In-Place Hold GUID> | FL Name
```

2. **コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。
    
<<<<<<< 見出し
3. 埋め込みの保留を削除する] を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
=======
3. 埋め込みの保留を削除する] を選択し、[**編集**] をクリックして![アイコンを編集](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)します。
>>>>>>> markjjo 変換
    
4. **、インプレース電子情報開示&amp;を保持**プロパティ ページで、**場所に保持**] をクリックして**で選択したメールボックスの検索クエリに一致する場所のコンテンツを保持する**] ボックスをオフにし、[**保存**] をクリックします。
    
5. **埋め込み電子的証拠開示&amp;を保持**ページで、埋め込みの保持をもう一度選択し、[**削除**] をクリックし、![削除アイコン](media/87565fbb-5147-4f22-9ed7-1c18ce664392.png)。
    
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

2. **コンプライアンス管理**には、EAC で\>**インプレース電子情報開示&amp;を保持**。
    
3. 非アクティブなメールボックスを配置する埋め込みの保留] を選択し、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)。
    
4. **、インプレース電子情報開示&amp;を保持**プロパティ] ページで、[**ソース**] をクリックします。
    
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

   **注:** 埋め込み保持の*ソース*のプロパティは、ユーザーの*LegacyExchangeDN*プロパティの移行元のメールボックスを識別します。このプロパティは、アクティブでないメールボックスを一意に識別ため、埋め込みの保持から*のソース*プロパティを使用して防ぐ間違ったメールボックスを削除します。これは、同じエイリアスまたは SMTP アドレスに 2 つのメールボックスがある場合は、問題を回避するのにも役立ちます。 
   
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
    
- **ソフト削除されたメールボックスの保存期間が非アクティブなメールボックスに影響しますか?** ソフト削除、非アクティブなメールボックスの日付が、保留が削除された日付より前に 30 日以上の場合は、メールボックスが完全に削除のマークされます。ですが、アクティブでないメールボックスには、過去 30 日以内のソフト削除された日付、保留を解除する場合は、ソフト削除済みメールボックスの保存期間の期限が切れるまで、メールボックスを回復できます。詳細については、[削除するかオンライン Exchange ユーザーのメールボックスの復元](https://go.microsoft.com/fwlink/?linkid=856835)を参照してください。ソフト削除されたメールボックスの保存期間を過ぎると、非アクティブなメールボックスを回復する手順を実行します。詳細については、 [Office 365 で、非アクティブなメールボックスのリカバリ](recover-an-inactive-mailbox.md)を参照してください。
    
- **表示するには、非アクティブなメールボックスに関する情報の保持を削除した後ですか?** 保留リストが削除され、非アクティブなメールボックスは、ソフト削除されたメールボックスに戻されますが後は、、 **Get**コマンドレットの*InactiveMailboxOnly*パラメーターを使用して返されません。**Get メールボックス SoftDeletedMailbox**コマンドを使用してメールボックスに関する情報を表示することができます。例えば： 
    
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
  
上の例では、 *WhenSoftDeleted*プロパティは、ソフト削除された日付であるこの例では 2014 年 10 月 30 日を識別します。このソフト削除されたメールボックスが、以前に、保留中の削除対象の非アクティブなメールボックスであった場合は完全に削除されてから 30 日後、 *WhenSoftDeleted*プロパティの値があります。この例では、2014 年 11 月 30 日後、メールボックスを完全に削除します。

