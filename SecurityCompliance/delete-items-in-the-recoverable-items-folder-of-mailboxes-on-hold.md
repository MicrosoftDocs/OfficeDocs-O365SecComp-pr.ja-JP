---
title: 管理者ヘルプの保留中のクラウド ベースのメールボックスの回復可能なアイテム] フォルダー内の項目を削除します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: a85e1c87-a48e-4715-bfa9-d5275cde67b0
description: '管理者: 法的保存要件にそのメールボックスが配置された場合でも、Exchange Online のメールボックスに対するユーザーの回復可能なアイテム] フォルダー内の項目を削除します。これは、データが誤ってこぼした Office 365 にするを削除するのには効果的な方法です。'
ms.openlocfilehash: 9174e953ebdd7f0032f411b99a814aeacd880a1e
ms.sourcegitcommit: dd58ed6fd424272e361bc3c109ecd6d63d673048
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/15/2018
ms.locfileid: "25566888"
---
# <a name="delete-items-in-the-recoverable-items-folder-of-cloud-based-mailboxes-on-hold---admin-help"></a>管理者ヘルプの保留中のクラウド ベースのメールボックスの回復可能なアイテム] フォルダー内の項目を削除します。

過失または悪意による削除から保護するために Exchange Online のメールボックスの [回復可能な項目] フォルダーが存在しています。保持される、検索を保留リストと電子情報開示など、Office 365 のコンプライアンス機能によってアクセスされるアイテムを保存するにも使用します。ただし、状況によっては、組織はそれらを削除する必要がありますが回復可能なアイテム] フォルダーに誤って保持されているデータがあります。ユーザーが知らないうちに送信など、機密情報や企業が深刻な影響の可能性がある情報を含む電子メール メッセージを転送します。場合でも、メッセージが完全に削除されると、それが無期限に保持され法的差し押さえがメールボックスに格納されているためです。このシナリオは、データが誤ってこぼした Office 365 にあるために、データのこぼしたと呼ばれます。このような場合は、Office 365 の保留中のさまざまな機能の 1 つの保留中のメールボックスが配置された場合でも、Exchange Online のメールボックスに対するユーザーの回復可能なアイテム] フォルダー内の項目を削除できます。保留のこれらの種類には、証拠保全、インプレースを保持して、電子的証拠開示の保留、および Office 365 のセキュリティで作成した Office 365 の保持ポリシーが含まれます&amp;コンプライアンス センターです。 
  
 この資料では、保留中では、クラウド ベースのメールボックスの回復可能なアイテム] フォルダーからアイテムを削除する方法について説明します。この手順は、メールボックスへのアクセスを無効にして、単一アイテムの回復、管理フォルダー アシスタントからメールボックスを処理、保留リストを一時的に削除する、回復可能なアイテム] フォルダーからアイテムを削除して、[元に戻すを無効にするを無効にする必要があります。以前の構成のためのメールボックス。プロセスを以下に示します。 
  
[手順 1: メールボックス情報を収集します。](#step-1-collect-information-about-the-mailbox)

[手順 2: メールボックスを準備します。](#step-2-prepare-the-mailbox)

[手順 3: メールボックスからすべての保留を削除します。](#step-3-remove-all-holds-from-the-mailbox)

[ステップ 4: メールボックスからの遅延の保留中を削除します。](#step-4-remove-the-delay-hold-from-the-mailbox)

[手順 5: 回復可能なアイテム] フォルダー内のアイテムを削除します。](#step-5-delete-items-in-the-recoverable-items-folder)

[手順 6: 以前の状態のためのメールボックスを元に戻す](#step-6-revert-the-mailbox-to-its-previous-state)
  
> [!CAUTION]
> この資料に記載された手順と、データは完全に削除 (パージ)、Exchange Online のメールボックスから。つまり、回復可能なアイテム] フォルダーから削除したメッセージは、回復できないので、法的証拠開示やその他のコンプライアンスのために使用できることはできません。証拠保全、インプレース保持の一部として保留中に配置されているメールボックスからメッセージを削除する場合は、電子的証拠開示、または保持ポリシーを Office 365 は、Office 365 のセキュリティで作成された&amp;コンプライアンス センターでは、レコード管理または法的にチェック保留リストを削除する前に部門です。上にメールボックスを保持するかどうかを定義するポリシーを持つ組織もあります。 またはデータのこぼしたインシデントが優先します。 
  
## <a name="before-you-begin"></a>はじめに

- 割り当てられる次の管理役割の両方の Exchange オンラインを検索し、手順 5 で回復可能なアイテム] フォルダーからメッセージを削除する必要があります。
    
  - **メールボックスの検索**- この役割では、組織内のメールボックスを検索することができます。Exchange 管理者は、既定でこの役割を割り当てられない。自分にこの役割を割り当てるには、自分で検出の管理役割グループのメンバーとして Exchange オンライン追加します。 
    
  - **メールボックスのインポートのエクスポート**- このロールには、ユーザーのメールボックスからメッセージを削除することができます。既定では、このロールはない任意の役割グループに割り当てられます。ユーザーのメールボックスからメッセージを削除するには、ことが役割を追加するメールボックスのインポート エクスポートの組織の管理役割グループに Exchange オンライン。 
    
- この資料で説明する手順は、非アクティブなメールボックスに対してサポートされていません。です保留中 (または Office 365 のリテンション ・ ポリシー) を適用することはできません再、非アクティブなメールボックスを削除した後。非アクティブなメールボックスから保留を解除するときは通常のソフト削除されたメールボックスに変更しは完全に削除、組織内の管理フォルダー アシスタントによって処理された後。
    
- 保持ロックでロックされている Office 365 の保持ポリシーに割り当てられているメールボックスに対してこの手順を実行することはできません。削除するか、管理フォルダー アシスタントでメールボックスを無効にして、Office 365 の保持ポリシーからメールボックスを除外することはできません保持ロックするためです。リテンション ・ ポリシーのロックの詳細については、[リテンション ・ ポリシーのロック](retention-policies.md#locking-a-retention-policy)を参照してください。
    
- メールボックス保留リストに配置されていない (または単一アイテムの回復が有効になっているがない) 場合は、回復可能なアイテム] フォルダーからだけでアイテムを削除できます。これを行う方法の詳細については、[検索および削除するメッセージ](https://go.microsoft.com/fwlink/?linkid=852453)を参照してください。
  
## <a name="step-1-collect-information-about-the-mailbox"></a>手順 1: メールボックス情報を収集します。

この最初の手順は、次の手順に影響を与える対象のメールボックスから選択したプロパティを収集するためです。これらの設定を記録したり、これらのプロパティの一部を変更し、回復可能なアイテム] フォルダーからアイテムを削除した後に手順 6 では、元の値に戻すことがあるためテキスト ファイルに保存することを確認します。ここでは、収集する必要がありますメールボックスのプロパティの一覧です。
  
-  *SingleItemRecoveryEnabled*と*RetainDeletedItemsFor*です。必要に応じて、1 つのリカバリを無効にして、手順 3 で削除済みアイテムの保存期間を変更します。 
    
-  *LitigationHoldEnabled*と*InPlaceHolds*です。手順 3 で一時的に削除することができるように、メールボックスにすべての保留リストを識別する必要があります。メールボックスに配置する場合があります型保留リストを識別する方法に関するヒントについては、[詳細について](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#moreinfo)はを参照してください。 
    
またを一時的に無効にできますので、この処理中にメールボックスにアクセスできません、所有者 (または他のユーザー) があるために、メールボックスのクライアント アクセスの設定を取得する必要があります。最後に、回復可能なアイテム] フォルダーには、現在のサイズとアイテム数を取得できます。手順 5 で [回復可能な項目] フォルダー内の項目を削除した後は、項目が実際に削除されることを確認するのにはこの情報を使用します。
  
1. [オンライン PowerShell を Exchange に接続](https://go.microsoft.com/fwlink/?linkid=396554)します。Exchange Online 内の適切な管理ロールに割り当てられている管理者アカウントのユーザー名とパスワードを使用することを確認します。 
    
2. 1 つのアイテムを復元し、削除済みアイテムの保存期間に関する情報を取得するのには次のコマンドを実行します。

    ```
    Get-Mailbox <username> | FL SingleItemRecoveryEnabled,RetainDeletedItemsFor
    ```

   単一アイテムの回復が有効な場合は、手順 2 で無効にする必要があります。30 日の削除済みアイテムの保存期間が設定されていないかどうか (Exchange Online の最大の値)、手順 2 で増やすことができますし、します。 
    
3. メールボックス、メールボックスのアクセスの設定を取得する次のコマンドを実行します。 
    
    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```

   手順 2 では、これらのアクセス方法のすべてを無効にします。
    
4. 保持し、Office 365 のメールボックスに適用されるリテンション ・ ポリシーに関する情報を取得するのには次のコマンドを実行します。
    
    ```
    Get-Mailbox <username> | FL LitigationHoldEnabled,InPlaceHolds
    ```


   > [!TIP]
    > 実行することができる場合は、 *InPlaceHolds*プロパティの値が多すぎますがあり、それらのすべてが表示されます、`Get-Mailbox <username> | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各値を表示します。 
  
5. 組織全体の Office 365 リテンション ・ ポリシーに関する情報を取得するのには次のコマンドを実行します。 

    ```
    Get-OrganizationConfig | FL InPlaceHolds
    ```
   組織に、組織全体の Office 365 の保持ポリシーがある場合は、手順 3 で、これらのポリシーからメールボックスを除外する必要があります。

   > [!TIP]
    > 実行することができる場合は、 *InPlaceHolds*プロパティの値が多すぎますがあり、それらのすべてが表示されます、`Get-OrganizationConfig | Select-Object -ExpandProperty InPlaceHolds`コマンドを別の行に各値を表示します。 
  
6. フォルダーおよびユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダー内のサブフォルダーの現在のサイズとアイテムの合計数を取得する次のコマンドを実行します。 

    ```
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   ユーザーのアーカイブ メールボックスが有効な場合は、フォルダーとユーザーのアーカイブ メールボックスの回復可能なアイテム フォルダー内のサブフォルダーのサイズとアイテムの合計数を取得する次のコマンドを実行します。 

    ```s
    Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
    ```

   手順 5 でアイテムを削除すると、削除するか、ユーザーの主なアーカイブ メールボックスの回復可能なアイテム] フォルダーにアイテムを削除することもできます。メールボックスのアーカイブの自動拡張が有効になっている場合、補助のアーカイブ メールボックス内のアイテムも削除されることに注意してください。
  
## <a name="step-2-prepare-the-mailbox"></a>手順 2: メールボックスを準備します。

収集すると、メールボックスに関する情報を保存、次の手順は次のタスクを実行してメールボックスを準備するのにです。 
  
- **メールボックスへのクライアント アクセスを無効にする**メールボックスの所有者は自分のメールボックスにアクセスできず、この処理中にメールボックスのデータを変更できるようにします。 
    
- 30 日後に**削除済みアイテム保存期間を延長**を (Exchange のオンラインでの最大値) それらを削除するには手順 5 の前に、回復可能なアイテム] フォルダーからアイテムが削除されないようにします。 
    
- 手順 5 で回復可能なアイテム] フォルダーからそれらを削除した後 (削除済みアイテムの保存期間の期間) のため、アイテムを**1 つのアイテムの復元を無効にする**には保持されません。 
    
- **管理フォルダー アシスタントを無効にする**ことは、メールボックスの処理し、手順 5 で削除したアイテムを保持しないようにします。 
    
Exchange オンライン PowerShell で次の手順を実行します。
  
1. クライアントからのすべてのメールボックスへのアクセスを無効にするのには、次のコマンドを実行します。コマンドの構文では、メールボックスのすべてのクライアント アクセスの方法が有効であると仮定しています。

    ```   
    Set-CASMailbox <username> -EwsEnabled $false -ActiveSyncEnabled $false -MAPIEnabled $false -OWAEnabled $false -ImapEnabled $false -PopEnabled $false
    ```
   
   > [!NOTE]
    > メールボックスにすべてのクライアント アクセスの方法を無効にするのには、最大 60 分かかる場合があります。これらのアクセス方法を無効にすることで現在サインインしたメールボックスの所有者を切断しないことに注意してください。所有者署名されていない場合、ことはできませんこれらのアクセス方法が無効にした後のメールボックスにアクセスします。 
  
2. 削除済みアイテムの保持期間の 30 日間の最大値を増やすには、次のコマンドを実行します。これは、現在の設定は、30 日以内であると仮定します。 

    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 30
    ```

3. 単一アイテムの回復を無効にするのには、次のコマンドを実行します。
    
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $false
    ```

   > [!NOTE]
    > 単一アイテムの回復を無効にするのには、最大 60 分かかる場合があります。この期間が経過するまで、回復可能なアイテム フォルダー内のアイテムを削除しないでください。 
  
4. 管理フォルダー アシスタントがメールボックスを処理を防ぐために次のコマンドを実行します。説明したようを無効にできます、管理フォルダー アシスタントのみ保持ロックで、Office 365 の保持ポリシーはメールボックスには適用されません。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $true
    ```

## <a name="step-3-remove-all-holds-from-the-mailbox"></a>手順 3: メールボックスからすべての保留を削除します。

回復可能なアイテム] フォルダーからアイテムを削除する前に最後のステップでは、すべての保留をするは、手順 1 で識別される)、メールボックスの配置を削除します。アイテムは、回復可能なアイテム] フォルダーからそれらを削除した後は保持されませんように、すべての保留を削除してください。次のセクションには、さまざまな種類のメールボックスの保留を削除することに関する情報が含まれます。メールボックスに配置する場合があります型保留リストを識別する方法に関するヒントについては、[詳細について](#more-information)はを参照してください。詳細については、 [Exchange Online のメールボックスに配置されているの種類を識別する方法を保持](identify-a-hold-on-an-exchange-online-mailbox.md)を参照してください。
  
> [!CAUTION]
> 前述したように、保留リストをメールボックスから削除する前に、レコード管理または法務部門に確認してください。 
  
 ### <a name="litigation-hold"></a>訴訟ホールド
  
次のコマンドを実行 Exchange オンライン PowerShell、証拠保全をメールボックスから削除するのには。

```
Set-Mailbox <username> -LitigationHoldEnabled $false
```

   
> [!NOTE]
> クライアント アクセスの方法と 1 つのアイテムの復元を無効にすることと同様に、かかることがあります、証拠保全を削除するのには最大 60 分までです。この期間が経過するまで、回復可能なアイテム] フォルダーからアイテムを削除しません。 
  
 ### <a name="in-place-hold"></a>インプレース保持
  
次のコマンドを実行 Exchange オンライン メールボックスに配置されている埋め込みの保持を識別する PowerShell。手順 1 で特定した埋め込み保持の GUID を使用します。 

```
Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL Name
```
   
埋め込みの保持を識別した後、保留リストからメールボックスを削除するのには、Exchange 管理センター (EAC) または Exchange のオンライン PowerShell を使用できます。詳細については、[作成または削除する、埋め込みの保持](https://go.microsoft.com/fwlink/?linkid=852668)を参照してください。
  
 ### <a name="office-365-retention-policies-applied-to-specific-mailboxes"></a>Office 365 の保持ポリシーが特定のメールボックスに適用されます。
  
次のコマンドを実行[Office 365 のセキュリティ&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)メールボックスに適用されている Office 365 の保持ポリシーを識別します。GUID を使用して (を除いて、`mbx`または`skp`プレフィックス) 手順 1 で特定したリテンション ・ ポリシーの。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```
   
リテンション ・ ポリシーを特定した後に、**日付のガバナンス ・** \> **の保存**] ページのセキュリティで&amp;コンプライアンス センターでは、前の手順では、リテンション ・ ポリシーを編集しの一覧からメールボックスを削除します。リテンション ・ ポリシーに含まれる受信者を指定します。 
  
 ### <a name="organization-wide-office-365-retention-policies"></a>Office 365 の保持ポリシーを組織全体にわたる
  
組織全体および Exchange 全体の Office 365 のリテンション ・ ポリシーは、組織内のすべてのメールボックスに適用されます。組織レベル (メールボックス レベルではなく) の適用は、手順 1 で**取得 OrganizationConfig**コマンドレットを実行する場合に返されます。次のコマンドを実行[セキュリティ&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)組織の Office 365 のリテンション ・ ポリシーを識別します。GUID を使用して (を除いて、`mbx`プレフィックス) 手順 1 で特定した組織全体の保存ポリシーのです。 

```
Get-RetentionCompliancePolicy <retention policy GUID without prefix> | FL Name
```

組織の Office 365 のリテンション ・ ポリシーを特定した後に、**日付のガバナンス**\>セキュリティでの**保存期間**] ページ&amp;コンプライアンス センターで特定した各組織全体の保存ポリシーの編集、前ステップ、およびメールボックスを除外されている受信者の一覧に追加します。この操作を行うと、リテンション ・ ポリシーからユーザーのメールボックスが削除されます。 

### <a name="office-365-retention-labels"></a>Office 365 保存ラベル

ユーザーが構成されているコンテンツを保持または保持し、任意のフォルダーまたはメールボックス内のアイテムにコンテンツを削除するラベルを適用するたびに、 *ComplianceTagHoldApplied*のメールボックスのプロパティが**True**に設定します。このような場合、メールボックスは、保留中の場合と同様に証拠保全がまたは Office 365 のリテンション ・ ポリシーに割り当てられていると見なされます。

*ComplianceTagHoldApplied*プロパティの値を表示するには、Exchange オンライン PowerShell で次のコマンドを実行します。

```
Get-Mailbox <username> |FL ComplianceTagHoldApplied
```

上のメールボックスを特定したら、保存ラベルは、フォルダーまたはアイテムに適用されます、コンテンツの検索ツールを使用するには、セキュリティとコンプライアンス ・ センターを検索するというラベルの付いた項目 ComplianceTag の検索条件を使用しているためにを保持します。詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md#conditions-for-common-properties)で「検索条件」のセクションを参照してください。

ラベルの詳細については、 [Office 365 の概要のラベル](labels.md)を参照してください。

 ### <a name="ediscovery-case-holds"></a>電子的証拠開示のケースを保持します。
  
次のコマンドを実行[セキュリティ&amp;コンプライアンス センター PowerShell](https://go.microsoft.com/fwlink/?linkid=627084)メールボックスに適用されている電子的証拠開示のサポート案件に関連付けられている保留リストを識別します。GUID を使用して (を除いて、`UniH`プレフィックス)、電子的証拠開示の手順 1 で識別することを保持します。2 番目のコマンドが保留リストに関連付けられては電子的証拠開示のケースの名前を表示することに注意してください。3 番目のコマンドは、保留リストの名前を表示します。 
  
```
$CaseHold = Get-CaseHoldPolicy <hold GUID without prefix>
```

```
Get-ComplianceCase $CaseHold.CaseId | FL Name
```

```
$CaseHold.Name
```

電子的証拠開示の場合、保留リストの名前を特定した後に、**検索&amp;調査**\>セキュリティで**電子的証拠開示**のページ&amp;コンプライアンス センター、ケースを開けるし、保留リストからメールボックスを削除します。詳細についてを参照してください[電子的証拠開示の場合は、Office 365 のセキュリティを管理する&amp;コンプライアンス センター](manage-ediscovery-cases.md)です。
  
## <a name="step-4-remove-the-delay-hold-from-the-mailbox"></a>ステップ 4: メールボックスからの遅延の保留中を削除します。

保留中の任意の種類がメールボックスから削除されると、 *DelayHoldApplied*のメールボックスのプロパティの値が**True**に設定します。これは、*遅延の保持*と呼ばれ、データが完全に削除されることを防止するのには 30 日間、保留中の実際の削除を延期することを意味メールボックスからには、(削除) します。  遅延ホールドがメールボックスに配置されると、メールボックスと見なされます上にある、無制限の期間の保持と証拠保全上にメールボックスがあったかどうか。(遅延保持の目的を検索するか、保留が削除された後にパージされるメールボックス アイテムを回復する機会を管理者に提供するが)。後 30 日間の遅延が含まれている Noe の期限が切れるし、Office 365 は、( *DelayHoldApplied*プロパティを**False**に設定) によって遅延保持を削除するのには自動的に試みます保留リストが実際に削除されるようにします。 

手順 5 でアイテムを削除するには、メールボックスから遅延保持を削除する必要があります。次のコマンドを実行 Exchange オンライン PowerShell 遅延保持を削除するのには。 
 
```
Set-Mailbox <username> -RemoveDelayHoldApplied
```
する必要があります法的保持義務の役割を割り当てる Exchange オンライン*RemoveDelayHoldApplied*パラメーターを使用するのには注意してください。

遅延の保留が削除されたことを確認するには、次のコマンドを実行します。

```
Get-Mailbox <username> | FL DelayHoldApplied
```

*DelayHoldApplied*プロパティの値が**False**のでは、遅延時間が削除されたことを示します。

## <a name="step-5-delete-items-in-the-recoverable-items-folder"></a>手順 5: 回復可能なアイテム] フォルダー内のアイテムを削除します。

PowerShell を使用して[検索メールボックス](https://go.microsoft.com/fwlink/?linkid=852595)コマンドレットでは、Exchange オンラインで実際には、回復可能なアイテム] フォルダー内のアイテムを削除する準備が整いました。**検索用メールボックス**のコマンドレットを実行するとき、3 つのオプションがあります。 
  
- それらを削除する前に、この項目では、必要に応じてを確認することができますそれらを削除する前に、アイテムを移動先のメールボックスにコピーします。
    
- アイテムを移動先のメールボックスにコピーし、同じコマンドを削除することです。
    
- 移動先のメールボックスにコピーすることのないアイテムを削除します。 
    
ユーザーの主なアーカイブ メールボックスの回復可能なアイテム フォルダー内のアイテムをも削除を実行すると、* * 検索メールボックス * * コマンドレットです。これを防止するには、 *DoNotIncludeArchive*スイッチを含めることができます。前述したように場合は、アーカイブの自動拡張が有効なメールボックスの * * 検索メールボックス * * コマンドレットは、補助のアーカイブ メールボックス内のアイテムを削除しません。自動拡張の詳細については、アーカイブ、 [Office 365 で無制限のアーカイブの概要](unlimited-archiving.md)を参照してください。
  
> [!NOTE]
> ( *SearchQuery*  パラメーターを使用していて) 検索クエリが含まれている場合、 **Search-Mailbox** コマンドレットは、検索結果で最大 10,000 個のアイテムを返します。したがって、検索クエリを含める場合は、 **Search-Mailbox** コマンドを複数回実行して 10,000 を超えるアイテムを削除する必要があるかもしれません。 
  
次の例では、これらのオプションのコマンドの構文を表示します。これらの例を使用して、`-SearchQuery size>0`パラメーターの値は、回復可能なアイテム] フォルダー内のすべてのサブフォルダーからすべてのアイテムを削除します。特定の条件に一致するアイテムのみを削除する場合は、または日付範囲のメッセージの件名など、他の条件を指定するのには、 *SearchQuery*パラメーターを使用することができますも。次の[SearchQuery パラメーターを使用するには、他の例](#other-examples-of-using-the-searchquery-parameter)を参照してください。 
  
### <a name="example-1"></a>例 1

この例では、組織の探索検索メールボックス内のフォルダーに、ユーザーの回復可能なアイテム] フォルダー内のすべての項目をコピーします。項目を完全に削除する前に確認できます。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>"
```

前の例では、探索検索メールボックスにアイテムをコピーする必要はありません。移動先のメールボックスにメッセージをコピーすることができます。ただし、可能性のある機密性の高いメールボックス データへのアクセスを防ぐため、お勧めアクセス権限のある担当者に制限のあるメールボックスにメッセージをコピーします。既定では、既定の探索検索メールボックスへのアクセスが制限されている探索管理役割グループのメンバーに Exchange オンライン。 
  
### <a name="example-2"></a>例 2

この例では、組織の探索検索メールボックス内のフォルダーにユーザーの回復可能なアイテム] フォルダー内のすべての項目をコピーし、ユーザーの回復可能なアイテム] フォルダーからアイテムが削除されます。

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -TargetMailbox "Discovery Search Mailbox" -TargetFolder "<foldername>" -DeleteContent
```
 
### <a name="example-3"></a>例 3

この例では、移動先のメールボックスにコピーすることがなくユーザーの回復可能なアイテム] フォルダー内のすべての項目を削除します。 

```
Search-Mailbox <username> -SearchQuery size>0 -SearchDumpsterOnly -DeleteContent
```

### <a name="other-examples-of-using-the-searchquery-parameter"></a>SearchQuery パラメーターを使用するには、他の例

*SearchQuery*パラメーターを使用して特定のメッセージを検索するがいくつかの例を次に示します。*SearchQuery*パラメーターを使用して特定の項目を検索する場合は、移動先のメールボックスに検索結果をコピーできるように、検索結果を確認して、クエリを変更に応じて、検索結果を削除する前に検討してください。 
  
この例では、[件名] フィールドで特定の語句を含むメッセージを返します。
  
```
SearchQuery 'subject:"MAIL_BOX VALIDATION/UPGRADE!!!"' 
```

この例では、指定した日付範囲内で送信されたメッセージを返します。
  
```
SearchQuery 'sent>=06/01/2016 AND sent<=09/01/2016'
```
 
この例では、指定したユーザーに送信されたメッセージを返します。

```
SearchQuery 'to:garthf@alpinehouse.com'
```
   
### <a name="verify-that-items-were-deleted"></a>アイテムが削除されたことを確認します。

メールボックスの回復可能なアイテム] フォルダーからアイテムを正常に削除したことを確認するには、PowerShell を使用**Get MailboxFolderStatistics**コマンドレット Exchange オンライン回復可能なアイテム] フォルダー内のアイテムの数とサイズを確認します。ステップ 1 で収集したもので、これらの統計を比較することができます。 
  
フォルダーおよびユーザーのプライマリ メールボックスの回復可能なアイテム] フォルダー内のサブフォルダーの現在のサイズとアイテムの合計数を取得する次のコマンドを実行します。 
  
```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
   
フォルダーおよびユーザーのアーカイブ メールボックスの回復可能なアイテム] フォルダー内のサブフォルダーのサイズとアイテムの合計数を取得する次のコマンドを実行します。 

```
Get-MailboxFolderStatistics <username> -FolderScope RecoverableItems -Archive | FL Name,FolderAndSubfolderSize,ItemsInFolderAndSubfolders
```
  
## <a name="step-6-revert-the-mailbox-to-its-previous-state"></a>手順 6: 以前の状態のためのメールボックスを元に戻す

最後の手順は、メールボックスを以前の構成を元に戻すには。これは、手順 2 で変更したプロパティをリセットして、手順 3 で削除する保留リストを再適用することを意味します。これが含まれています。
  
- 削除済みアイテムの保持期間を変更する前の値にバックアップを作成します。または、することができますだけオンラインのままに Exchange で 30 日、最大値に設定。
    
- 1 つのアイテムの復元を再度有効にします。
    
- 所有者が自分のメールボックスにアクセスできるように、クライアント アクセスの方法を再度有効にします。
    
- 保持し、削除する保持ポリシーを Office 365 を再適用します。
    
- 管理フォルダー アシスタントにメールボックスの処理を再度有効にします。
    
> [!IMPORTANT]
> 保留中または Office 365 を再適用した後 24 時間を待機することをお勧めします。 保存ポリシーとそれが適用されていることを確認する) を再度有効にする、管理フォルダー アシスタントのメールボックスを処理する前にします。 
  
Exchange オンライン PowerShell では、(、指定した順序で) 次の手順を実行します。
  
1. 削除済みアイテムの保持期間を変更するのには次のコマンドが元の値にバックアップを実行します。以前の設定には、30 日以内にこれを前提としていますたとえば 14 日間です。 
    
    ```
    Set-Mailbox <username> -RetainDeletedItemsFor 14
    ```
   
2. 1 つのアイテムの復元を再度有効にするのには次のコマンドを実行します。
   
    ```
    Set-Mailbox <username> -SingleItemRecoveryEnabled $true
    ```

3. メールボックスにすべてのクライアント アクセスの方法を再度有効にするのには次のコマンドを実行します。
    
    ```
    Set-CASMailbox <username> -EwsEnabled $true -ActiveSyncEnabled $true -MAPIEnabled $true -OWAEnabled $true -ImapEnabled $true -PopEnabled $true
    ```
   
4. 手順 3 で削除する保留リストを再適用します。、保留リストの種類に応じて、次の手順のいずれかを使用します。
    
    **訴訟ホールド**
    
    メールボックスの証拠の保全を再度有効にするには、次のコマンドを実行します。
    
    ```
    Set-Mailbox <username> -LitigationHoldEnabled $true
    ```

    **In-Place Hold**
    
    埋め込みの保持にメールボックスを追加するのには、EAC (または Exchange オンライン PowerShell) を使用します。 
    
    **Office 365 の保持ポリシーが特定のメールボックスに適用されます。**
    
    セキュリティを使用して、 &amp; 、メールボックスを Office 365 のリテンション ・ ポリシーに追加するコンプライアンス センターです。**日付のガバナンス**に\>**の保存**] ページのセキュリティで&amp;コンプライアンス センターでは、リテンション ・ ポリシーを編集し、リテンション ・ ポリシーが適用される受信者のリストに戻る、メールボックスを追加します。 
    
    **Office 365 の保持ポリシーを組織全体にわたる**
    
    ポリシーから除外することによって、組織全体または Exchange 全体の保持ポリシーを削除する場合は、セキュリティを使用して&amp;の一覧からメールボックスを削除するのにはコンプライアンス センターは、ユーザーを除外します。**日ガバナンス**に\>**の保存**] ページのセキュリティで&amp;コンプライアンス センターでは、組織全体のリテンション ・ ポリシーを編集し、除外されている受信者の一覧からメールボックスを削除します。これは再、保持ポリシーの適用ユーザーのメールボックスにします。 
    
    **電子的証拠開示のケースを保持します。**
    
    セキュリティを使用して、 &amp; 、メールボックスを追加するのにはコンプライアンス センター電子的証拠開示のサポート案件に関連付けられている保留中のバックアップします。移動、**検索&amp;調査**\>セキュリティで**電子的証拠開示**ページ&amp;コンプライアンス ・ センター、ケースを開けるし、メールボックスを保留リストに追加します。 
    
5. 管理フォルダー アシスタント メールボックスをもう一度処理を許可するのには、次のコマンドを実行します。述べたように、保留中または Office 365 を再適用した後 24 時間を待機することをお勧めします。 保存ポリシーとそれが適用されていることを確認する) 前に、再度有効にする、管理フォルダー アシスタントです。 

    ```
    Set-Mailbox <username> -ElcProcessingDisabled $false
    ```
   
6. 以前の状態に戻します、メールボックスが元に戻されたことを確認するには、次のコマンドを実行し、手順 1 で収集したものに設定を比較し、できます。

    ```
    Get-Mailbox <username> | FL ElcProcessingDisabled,InPlaceHolds,LitigationHoldEnabled,RetainDeletedItemsFor,SingleItemRecoveryEnabled
    ```

    ```
    Get-CASMailbox <username> | FL EwsEnabled,ActiveSyncEnabled,MAPIEnabled,OWAEnabled,ImapEnabled,PopEnabled
    ```
  
## <a name="more-information"></a>詳細情報

ここでは、 **Get メールボックス**または**Get OrganizationConfig**コマンドレットを実行すると、 *InPlaceHolds*プロパティの値に基づいて保留の種類を識別する方法を説明した表です。詳細については、[の種類を識別する方法を Exchange Online のメールボックスに配置されている保持](identify-a-hold-on-an-exchange-online-mailbox.md)を参照してください。

前に説明すると、すべての保留を削除するのにがありする前にメールボックスから保存ポリシーを Office 365 は、回復可能なアイテム] フォルダー内の項目を正常に削除できます。 
  
|**ホールドの種類**|**値の例**|**保留リストを識別する方法**|
|:-----|:-----|:-----|
|訴訟ホールド  <br/> | `True` <br/> |*LitigationHoldEnabled*  プロパティが  `True` に設定されています。  <br/> |
|インプレース保持  <br/> | `c0ba3ce811b6432a8751430937152491` <br/> |*InPlaceHolds*プロパティには、メールボックスに配置されている埋め込みの保持の GUID が含まれています。これは、埋め込みを保持するためプレフィックスを持つ GUID が起動しないことがわかります。<br/> Exchange Online PowerShell で  `Get-MailboxSearch -InPlaceHoldIdentity <hold GUID> | FL' のメールボックス上の埋め込みの保持に関する情報を取得する Exchange のオンライン PowerShell コマンドです。  <br/> |
| セキュリティで保存ポリシーを office 365&amp;コンプライアンス センターは、特定のメールボックスに適用  <br/> | `mbxcdbbb86ce60342489bff371876e7f224` <br/> または  <br/>  `skp127d7cf1076947929bf136b7a2a8c36f` <br/> |**Get メールボックス**コマンドレットを実行すると Office 365 の Guid の保存ポリシーが、メールボックスに適用されるは、 *InPlaceHolds*プロパティも含まれます。リテンション ・ ポリシーを識別するには、GUID が始まるため、`mbx`のプレフィックスです。リテンション ・ ポリシーの GUID で始まる場合、 `skp` 、ビジネス会話を Skype にリテンション ・ ポリシーが適用されることを示すプレフィックスです。<br/> セキュリティの次のコマンドを実行するメールボックスに適用されている保持ポリシーを Office 365 の id、&amp;コンプライアンス センター PowerShell: <br/> <br/>' Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名`<br/><br/>Be sure to remove the  `mbx` or  `skp' このコマンドを実行するときにプレフィックスです。  <br/> |
|セキュリティで Office 365 保存ポリシーを組織全体にわたる&amp;コンプライアンス センター  <br/> |値なし  <br/> または  <br/>  `-mbxe9b52bf7ab3b46a286308ecb29624696`(メールボックスが組織全体にわたるポリシーから除外されていることを示します)  <br/> |**Get メールボックス**コマンドレットを実行する*InPlaceHolds*プロパティが空であってもある可能性があります 1 つまたは複数のメールボックスに適用される組織の Office 365 リテンション ・ ポリシーです。  <br/> 実行することができますこれを確認するのには、' Get OrganizationConfig | FL InPlaceHolds` command in Exchange Online PowerShell to get a list of the GUIDs for organization-wide Office 365 retention policies. The GUID for organization-wide retention policies applied to Exchange mailboxes start with the  `mbx` prefix; for example  `mbxa3056bb15562480fadb46ce523ff7b02`.  <br/> To identity the organization-wide Office 365 retention policy that's applied to the mailbox, run the following command in Security &amp; Compliance Center PowerShell: <br/><br/> `Get RetentionCompliancePolicy<retention policy GUID without prefix> | FL 名`<br/><br/>Note that if a mailbox is excluded from an organization-wide Office 365 retention policy, the GUID for the retention policy is displayed in the  *InPlaceHolds*  property of the user's mailbox when you run the **Get-Mailbox** cmdlet; it's identified by the prefix  `・ mbx`; for example,  `-mbxe9b52bf7ab3b46a286308ecb29624696' <br/> |
|電子的証拠開示の場合は、セキュリティの保持&amp;コンプライアンス センター  <br/> | `UniH7d895d48-7e23-4a8d-8346-533c3beac15d` <br/> |*InPlaceHolds*プロパティには、セキュリティ、電子的証拠開示のケースに関連付けられている保留状態の GUID も含まれています&amp;コンプライアンス センター メールボックスに配置する可能性があります。これは、GUID が始まるためにの電子的証拠開示サポート ・ リクエストの保留がわかる、`UniH`のプレフィックスです。<br/> 使用することができます、`Get-CaseHoldPolicy`セキュリティのコマンドレット&amp;コンプライアンス センターの PowerShell のメールボックスの保留リストが関連付けられている電子的証拠開示のサポート案件に関する情報を取得します。コマンドを実行することができますたとえば、' Get CaseHoldPolicy<hold GUID without prefix> | FL 名` to display the name of the case hold that's on the mailbox. Be sure to remove the  `UniH` prefix when you run this command.  <br/><br/> To identity the eDiscovery case that the hold on the mailbox is associated with, run the following commands:<br/><br/>`$CaseHold = Get CaseHoldPolicy <hold GUID without prefix> `<br/><br/>`Get ComplianceCase $CaseHold.CaseId | FL 名 '


