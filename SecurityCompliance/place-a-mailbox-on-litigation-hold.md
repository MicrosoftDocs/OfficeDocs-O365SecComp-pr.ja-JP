---
title: メールボックスを訴訟ホールドの対象にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'メールボックスを訴訟ホールドの対象にすると、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツが保持されます。 '
ms.openlocfilehash: 9c2d5c77a604e4dbe6e1f1db75142d3bf5790618
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002846"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>メールボックスを訴訟ホールドの対象にする
 
メールボックスを訴訟ホールドの対象にすると、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツが保持されます。ユーザーのメールボックスを訴訟ホールドの対象にすると、ユーザーのアーカイブ メールボックス (有効である場合) もホールドの対象になります。削除済みアイテムと変更されたアイテムは、指定した期間またはメールボックスを訴訟ホールドの対象から外すまで、保持されます。[In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) 検索で、このようなメールボックスのすべてのアイテムが返されます。 
  
> [!IMPORTANT]
> 証拠保全は、ユーザーのメールボックスの回復可能なアイテム フォルダー内のアイテムを保持します。番号を削除または変更した項目のサイズによっては、メールボックスの回復可能なアイテム] フォルダーのサイズが簡単に向上します。[回復可能なアイテム] フォルダーは、既定で高いクォータが構成されます。Exchange online では、証拠保全のメールボックスを配置すると、このクォータが自動的に大きくなります。Exchange Server 2013 では、お勧めは、証拠保全、回復可能なアイテムのクォータの制限に到達しないことを確認するのには週単位でのメールボックスを監視すること。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- 予想所要時間: 5 分
    
- 訴訟ホールド設定が有効になるまでに、最長で 60 分かかる場合があります。
    
- [メッセージング ポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) トピック内の この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。 の「インプレース保持」エントリ。 
    
- Exchange Online のメールボックスを配置すると、証拠保全に割り当てる必要があります Exchange Online (プラン 2) ライセンスです。メールボックスが Exchange Online (プラン 1) のライセンスを割り当てられている場合は、上に配置するのには別の Exchange Online Archiving のライセンスを保持してそれを割り当てる必要があります。
    
- 説明したよう、ユーザーのメールボックスに、証拠保全を配置すると、ユーザーのアーカイブ メールボックス内のコンテンツも配置保留状態にされます。Exchange ハイブリッド展開での設置型のプライマリ メールボックスで、証拠保全を配置する場合、クラウド ・ ベースのアーカイブ メールボックスが有効な場合) も保留状態に配置されます。
    
- Exchange online では、回復可能なアイテム フォルダーのクォータが自動的に増加 100 GB に証拠保全のメールボックスを配置すると。このフォルダーの既定のサイズは、30 GB です。
    
- 証拠保全は、削除済みアイテムが保持され、保留が解除されるまで、変更されたアイテムの元のバージョンも保持されます。保持期間] は、指定した期間のメールボックス アイテムが保持されますを指定することができます。保留期間を指定する場合は、メッセージを受け取るか、メールボックスのアイテムが作成された日付から計算されます。指定した条件を満たすアイテムを保持するには、クエリ ベースの保留リストを作成するのには、埋め込みの保持を使用します。詳細については、[作成または埋め込みの保持を削除する](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)を参照してください。
    
- 保留中の Exchange Online のメールボックスを配置するのにはシェルを使用するには、Exchange のオンライン PowerShell を使用する必要です。詳細については、 [Exchange オンラインを使用してリモート PowerShell への接続](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)を参照してください。
    
- パブリック フォルダー メールボックスを訴訟ホールドの対象にすることはサポートされていません。パブリック フォルダーを保持の対象にするには、インプレース ホールドを使用する必要があります。
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>EAC を使用してメールボックスを訴訟ホールドの対象にする
<a name="sectionSection1"> </a>

1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. 、ユーザーのメールボックスの一覧で、証拠保全、上に配置するメールボックスをクリックし、し、[**編集**] をクリックして![[編集] アイコン](media/ITPro-EAC-EditIcon.gif)。
    
3. [メールボックスのプロパティ] ページをクリックして **[メールボックスの機能です**。
    
4. **[訴訟ホールド:無効]** で、 **[有効]** をクリックすると、メールボックスが訴訟ホールドの対象になります。 
    
5. **[訴訟ホールド]** ページで、以下のオプション情報を入力します。 
    
  - **訴訟ホールド期間 (日)** このボックスを使用して、メールボックスを訴訟ホールドの対象にするときに、メールボックス アイテムを保持する期間を指定します。期間は、メールボックス アイテムが受信または作成された日から計算されます。このボックスが空白の場合は、アイテムは無期限に、またはその保留が解除されるまで保持されます。日数で期間を指定します。 
    
  - **メモ**証拠保全に自分のメールボックスは、ユーザーに通知するのにには、このボックスを使用します。メモは、Outlook 2010 またはそれ以降を使用している場合、ユーザーのメールボックスに表示されます。 
    
  - **URL**証拠保全の詳細については web サイトをユーザーに指示するのにには、このボックスを使用します。Outlook 2010 以降を使用している場合は、ユーザーのメールボックスにこの URL が表示されます。 
    
6. **[訴訟ホールド]** ページの **[保存]** をクリックして、メールボックスのプロパティ ページにある **[保存]** をクリックします。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>シェルを使用して無期限にメールボックスを訴訟ホールドの対象にする
<a name="sectionSection2"> </a>

この例では、メールボックス bsuneja@contoso.com を訴訟ホールドの対象にします。メールボックス内のアイテムは、無期限にまたは保留が解除されるまで保持されます。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> メールボックスを無期限に訴訟ホールドの対象にする (期間を指定しない) 場合、メールボックスの  _LitigationHoldDuration_ プロパティの値は  `Unlimited` に設定されます。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>シェルを使用してメールボックスを訴訟ホールドの対象にし、指定した期間アイテムを保持する
<a name="sectionSection3"> </a>

この例では、メールボックス bsuneja@contoso.com を訴訟ホールドの対象とし、2555 日間 (約 7 年間) アイテムを保持します。 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>シェルを使用してすべてのメールボックスを指定した期間訴訟ホールドの対象にする
<a name="sectionSection4"> </a>

組織では、すべてのメールボックス データを特定の期間保持しなければならない場合があります。組織内のすべてのメールボックスを訴訟ホールドの対象にする前に、以下の点を考慮します。
  
次の例では、組織内のすべてのユーザー メールボックスを 1 年間 (365 日間) 訴訟ホールドの対象にします。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

この例では、[Get-Mailbox](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx) コマンドレットを使用して組織内のすべてのユーザー メールボックスを取得し、受信者フィルターを使用してすべてのユーザーのメールボックスを含めます。それから、メールボックスの一覧を [Set-Mailbox](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx) コマンドレットにパイプ処理して訴訟ホールドを有効にし、保持期間を指定します。 
  
すべてのユーザー メールボックスを無期限の保持の対象にするには、上記のコマンドを実行しますが、 _LitigationHoldDuration_ パラメーターは含めません。 
  
1 つ以上のメールボックスを含めるまたは除外するフィルターで他の受信者のプロパティを使用する例については、「[詳細情報](#moreinfo.md)」セクションを参照してください。 
  
## <a name="use-the-shell-to-remove-a-mailbox-from-litigation-hold"></a>シェルを使用してメールボックスを訴訟ホールドから削除する
<a name="sectionSection5"> </a>

この例では、メールボックス bsuneja@contoso.com を訴訟ホールドから削除します。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $false
```

P
## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法
<a name="sectionSection6"> </a>

メールボックスが正常に訴訟ホールドの対象となったことを確認するには、次のいずれかを実行します。
  
- EAC で以下を実行します。
    
1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. 、ユーザーのメールボックスの一覧で、証拠保全の設定を確認するメールボックスをクリックし、[**編集**] をクリックして![[編集] アイコン](media/ITPro-EAC-EditIcon.gif)。
    
3. [メールボックスのプロパティ] ページをクリックして **[メールボックスの機能です**。
    
4. **[訴訟ホールド]** の下でそのホールドが有効であることを確認します。
    
5. **[詳細表示]** をクリックして、いつまただれによってメールボックスが訴訟ホールドの対象とされたかを確認します。オプションの **[訴訟ホールド期間 (日)]**、 **[メモ]**、および **[URL]** ボックスの値を確認したり、変更したりすることもできます。 
    
- シェルで、次のいずれかのコマンドを実行します。
    
  ```
  Get-Mailbox <name of mailbox> | FL LitigationHold*
  ```

    または
    
  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | FL Name,LitigationHold*
  ```

    メールボックスが無期限に訴訟ホールドの対象とされた場合、メールボックスの  _LitigationHoldDuration_ プロパティの値は  `Unlimited` に設定されています。
    
## <a name="more-information"></a>詳細情報
<a name="moreinfo"> </a>

- 組織においてすべてのメールボックス データを特定の期間保持する必要がある場合、組織内のすべてのメールボックスを訴訟ホールドの対象にする前に、以下を考慮します。
    
  - 上記のコマンドを使用して、組織内のすべてのメールボックス (または指定した受信者フィルターに一致するメールボックスのサブセット) を保持の対象にすると、コマンドを実行した時点で存在するメールボックスのみが保持の対象になります。後でメールボックスを新規作成する場合は、再度コマンドを実行して、その新しいメールボックスを保持の対象にする必要があります。頻繁にメールボックスを新規作成する場合は、必要な頻度にスケジュールしたタスクとしてコマンドを実行できます。
    
  - 証拠保全上のすべてのメールボックスを配置すると、メールボックスのサイズが大幅に可能性があります。2013 の Exchange Server 組織で、組織の維持の要件を満たすために十分な記憶域を計画します。
    
  - [回復可能なアイテム] フォルダーでは、フォルダー内のアイテムは、メールボックス格納域の制限をカウントしないように、独自の格納域の制限があります。説明したよう時間の長い期間のメールボックスのデータを保持するがユーザーのメールボックスの回復可能なアイテム] フォルダーの増加が発生し、保存します。対応するための増加 Exchange オンライン、回復可能なアイテム] フォルダーのクォータが自動的に増加 30 GB から 100 GB に証拠保全のメールボックスを配置すると。 
    
    Exchange Server 2013 年、回復可能なアイテム] フォルダーの既定の記憶域の制限は、30 GB でもあります。上限に達したことがないことを確認するには、このフォルダーのサイズを定期的に監視することをお勧めします。詳細については、[回復可能なアイテム] フォルダー](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)を参照してください。
    
- すべてのメールボックスを保持の対象にする上記のコマンドでは、すべてのユーザーのメールボックスを返す受信者フィルターが使用されます。特定のメールボックスを訴訟ホールドの対象とするために、その他の受信者プロパティを使用して、 **Set-Mailbox** コマンドレットにパイプ処理できるそれらのメールボックスの一覧を返すことができます。 
    
    以下に、 **Get-Mailbox** コマンドレットと **Get-Recipient** コマンドレットを使用して、共通のユーザー属性またはメールボックス属性に基づいてメールボックスのサブセットを返す例を示します。これらの例では、関連するメールボックスのプロパティ (  _CustomAttributeN_ や  _Department_ など) が入力されていることを想定しています。
    
  ```
  Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'CustomAttribute15 -eq "OneYearLitigationHold"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'Department -eq "HR"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'PostalCode -eq "98052"'
  ```

  ```
  Get-Recipient -RecipientTypeDetails UserMailbox -ResultSize unlimited -Filter 'StateOrProvince -eq "WA"'
  ```

  ```
  Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -ne "DiscoveryMailbox"}
  ```

    フィルターで他のユーザーのメールボックス プロパティを使用して、メールボックスを含めたり、除外したりすることができます。詳細については、「[Filterable Properties for the -Filter Parameter](http://technet.microsoft.com/library/b02b0005-2fb6-4bc2-8815-305259fa5432.aspx)」を参照してください。
    

