---
title: メールボックスを訴訟ホールドの対象にする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2016
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: ''
ms.assetid: adee4621-3626-4aec-aa53-00b35ff0d0b0
description: 'メールボックスを訴訟ホールドの対象にすると、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツが保持されます。 '
ms.openlocfilehash: a4d0939ffed32a8442b4b705bd15804b9f3eb7ea
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693126"
---
# <a name="place-a-mailbox-on-litigation-hold"></a>メールボックスを訴訟ホールドの対象にする
 
メールボックスを訴訟ホールドの対象にすると、削除済みアイテムと変更されたアイテムの元のバージョンを含む、すべてのメールボックスのコンテンツが保持されます。 ユーザーのメールボックスを訴訟ホールドの対象にすると、ユーザーのアーカイブメールボックス内のコンテンツ (有効になっている場合) も保持に配置されます。 削除および変更されたアイテムは、指定した期間、またはメールボックスを訴訟ホールドの対象から外すまで保持されます。 [In-Place eDiscovery](http://technet.microsoft.com/library/6377cb7a-3416-4e15-8571-c45d2160fc6f.aspx) 検索で、このようなメールボックスのすべてのアイテムが返されます。 
  
> [!IMPORTANT]
> 訴訟ホールドによって、ユーザーのメールボックスにある [回復可能なアイテム] フォルダー内のアイテムを保持します。 削除または変更するアイテムの数およびサイズによっては、メールボックスの [回復可能なアイテム] フォルダーのサイズが急に増加する可能性があります。 既定では、[回復可能なアイテム] フォルダーは高いクォータで構成されています。 Exchange Online では、メールボックスを訴訟ホールドの対象にすると、このクォータは自動的に増加します。 Exchange Server 2013 では、訴訟ホールドの対象となっているメールボックスを週単位で監視して、回復可能なアイテムのクォータの制限に到達しないようにすることをお勧めします。 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報
<a name="sectionSection0"> </a>

- 予想所要時間 : 5 分
    
- 訴訟ホールド設定が有効になるまでに、最長で 60 分かかる場合があります。
    
- [メッセージング ポリシーとコンプライアンスのアクセス許可](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) トピック内の この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。 の「インプレース保持」エントリ。 
    
- exchange online メールボックスを訴訟ホールドの対象にするには、exchange online (Plan 2) ライセンスが割り当てられている必要があります。 メールボックスに Exchange Online (プラン 1) ライセンスが割り当てられている場合は、別の Exchange Online Archiving ライセンスに割り当て、メールボックスを保持の対象にする必要があります。
    
- 前述したように、ユーザーのメールボックスに訴訟ホールドを配置すると、ユーザーのアーカイブメールボックス内のコンテンツも保持に配置されます。 Exchange ハイブリッド展開のオンプレミスのプライマリメールボックスに訴訟ホールドを配置すると、クラウドベースのアーカイブメールボックス (有効な場合) もホールドの対象になります。
    
- Exchange Online では、メールボックスを訴訟ホールドの対象にすると、回復可能なアイテムフォルダーのクォータは自動的に 100 GB に増加します。 このフォルダーの既定のサイズは 30 GB です。
    
- 訴訟ホールドは、削除済みアイテムを保持し、保留が解除されるまで、変更されたアイテムの元のバージョンを保持します。 必要に応じて保持期間を指定することもできます (指定した期間中、メールボックスのアイテムが保持されます)。 保持期間を指定する場合は、メッセージが受信された、またはメールボックス アイテムが作成された日付から計算されます。 指定した条件に一致するアイテムを保持するには、インプレース保持を使用してクエリベースの保留リストを作成します。 詳細については、「[インプレース保持を作成または削除する](http://technet.microsoft.com/library/9d5d8d37-a053-4830-9cb1-6e1ede25e963.aspx)」を参照してください。
    
- シェルを使用して exchange online メールボックスを保持するには、exchange online PowerShell を使用する必要があります。 詳細については、「[リモート PowerShell による Exchange への接続](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)」を参照してください。
    
- パブリックフォルダーメールボックスに訴訟ホールドを配置することはサポートされていません。 パブリックフォルダーを保持するには、インプレース保持を使用する必要があります。
    
## <a name="use-the-eac-to-place-a-mailbox-on-litigation-hold"></a>EAC を使用してメールボックスを訴訟ホールドの対象にする
<a name="sectionSection1"> </a>

1. **[受信者]** \> **[メールボックス]** に移動します。
    
2. ユーザーメールボックスの一覧で、訴訟ホールドの対象となるメールボックスをクリックし、[編集] **** ![編集アイコン](media/ITPro-EAC-EditIcon.gif)をクリックします。
    
3. メールボックスのプロパティページで、[**メールボックスの機能**] をクリックします。
    
4. **[訴訟ホールド:無効]** で、 **[有効]** をクリックすると、メールボックスが訴訟ホールドの対象になります。 
    
5. **[訴訟ホールド]** ページで、以下のオプション情報を入力します。 
    
  - **訴訟ホールド期間 (日)** このボックスを使用して、メールボックスを訴訟ホールドの対象にするときに、メールボックス アイテムを保持する期間を指定します。期間は、メールボックス アイテムが受信または作成された日から計算されます。このボックスが空白の場合は、アイテムは無期限に、またはその保留が解除されるまで保持されます。日数で期間を指定します。 
    
  - **注** このボックスを使用して、メールボックスが訴訟ホールドの対象であることをユーザーに通知します。 メモは、Outlook 2010 以降を使用している場合に、ユーザーのメールボックスに表示されます。 
    
  - **URL** このボックスを使用して、訴訟ホールドに関する詳細については Web サイトを参照するようにユーザーに指示します。 この URL は、Outlook 2010 以降を使用している場合に、ユーザーのメールボックスに表示されます。 
    
6. **[訴訟ホールド]** ページの **[保存]** をクリックして、メールボックスのプロパティ ページにある **[保存]** をクリックします。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-indefinitely"></a>シェルを使用してメールボックスを無期限に訴訟ホールドに配置する
<a name="sectionSection2"> </a>

この例では、メールボックス bsuneja@contoso.com を訴訟ホールドの対象にします。メールボックス内のアイテムは、無期限にまたは保留が解除されるまで保持されます。
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true
```

> [!NOTE]
> メールボックスを無期限に訴訟ホールドの対象にする (期間を指定しない) 場合、メールボックスの  _LitigationHoldDuration_ プロパティの値は  `Unlimited` に設定されます。 
  
## <a name="use-the-shell-to-place-a-mailbox-on-litigation-hold-and-preserve-items-for-a-specified-duration"></a>シェルを使用してメールボックスを訴訟ホールドの対象にし、指定した期間だけアイテムを保持する
<a name="sectionSection3"> </a>

この例では、メールボックス bsuneja@contoso.com を訴訟ホールドの対象とし、2555 日間 (約 7 年間) アイテムを保持します。 
  
```
Set-Mailbox bsuneja@contoso.com -LitigationHoldEnabled $true -LitigationHoldDuration 2555
```

## <a name="use-the-shell-to-place-all-mailboxes-on-litigation-hold-for-a-specified-duration"></a>シェルを使用して、指定した期間にすべてのメールボックスを訴訟ホールドの対象にする
<a name="sectionSection4"> </a>

組織では、すべてのメールボックスのデータを一定の期間保持することが必要な場合があります。 組織内のすべてのメールボックスを訴訟ホールドに配置する前に、次の点を考慮してください。
  
この例では、組織内のすべてのユーザーメールボックスを1年間 (365 日) の訴訟ホールドに配置します。
  
```
Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"} | Set-Mailbox -LitigationHoldEnabled $true -LitigationHoldDuration 365
```

この例では、[メールボックス取得](http://technet.microsoft.com/library/8a5a6eb9-4a75-47f9-ae3b-a3ba251cf9a8.aspx)コマンドレットを使用して組織内のすべてのメールボックスを取得し、すべてのユーザーメールボックスを含める受信者フィルターを指定して、メールボックスのリストをメールボックスの[セット](http://technet.microsoft.com/library/a0d413b9-d949-4df6-ba96-ac0906dedae2.aspx)にパイプ処理して訴訟ホールドを有効にし、保持期間。 
  
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
    
2. ユーザーメールボックスの一覧で、訴訟ホールドの設定を確認するメールボックスをクリックし、[編集アイコン**** ![](media/ITPro-EAC-EditIcon.gif)の編集] をクリックします。
    
3. メールボックスのプロパティページで、[**メールボックスの機能**] をクリックします。
    
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
    
  - すべてのメールボックスを訴訟ホールドの対象にすると、メールボックスのサイズに大きな影響を与える可能性があります。 Exchange Server 2013 組織では、組織の保持要件を満たすのに十分なストレージを計画します。
    
  - [回復可能なアイテム] フォルダーには独自の格納域の制限があるため、このフォルダー内のアイテムはメールボックスの格納域の制限にカウントされません。 上記の説明のとおり、メールボックスのデータを長期間保持すると、ユーザーのメールボックスとアーカイブにある [回復可能なアイテム] フォルダーのサイズが増大します。 Exchange Online のこの増加に対応するために、メールボックスを訴訟ホールドの対象にすると、回復可能なアイテムフォルダーのクォータは自動的に 30 gb から 100 GB に増加します。 
    
    Exchange Server 2013 では、回復可能なアイテムフォルダーの既定の格納域の制限も 30 GB です。 [回復可能なアイテム] フォルダーが制限に達していないことを確認するため、フォルダーのサイズを定期的に監視することをお勧めします。 詳細については、「[回復可能なアイテムフォルダー](http://technet.microsoft.com/library/efc48fb4-2ed8-4d05-93af-f3505fbc389d.aspx)」を参照してください。
    
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
    

