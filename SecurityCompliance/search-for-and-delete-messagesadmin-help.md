---
title: メッセージを検索して削除する - 管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 管理者は Search-Mailbox コマンドレットを使って、ユーザーのメールボックスを検索し、メールボックスからメッセージを削除できます。
ms.openlocfilehash: 718a23f649843420ccfd924be72752a99278da4c
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297130"
---
# <a name="search-for-and-delete-messages---admin-help"></a>メッセージを検索して削除する - 管理者向けヘルプ
  
管理者は **Search-Mailbox** コマンドレットを使って、ユーザーのメールボックスを検索し、メールボックスからメッセージを削除できます。 
  
1 回の手順でメッセージを検索して削除するには、 **Search-Mailbox** コマンドレットに  _DeleteContent_ スイッチを指定して実行します。ただし、これを実行する場合、検索によって返される結果をプレビューしたり、メッセージのログを生成したりすることはできないため、削除するつもりのないメッセージを誤って削除してしまう可能性があります。メッセージが削除される前に、検索で見つかったメッセージのログをプレビューするには、 **Search-Mailbox** コマンドレットに  _LogOnly_ スイッチを指定して実行します。 
  
追加の予防手段として、 _TargetMailbox_ および  _TargetFolder_ パラメーターを使用して、最初にメッセージを別のメールボックスにコピーすることができます。これにより、削除されたメッセージに再度アクセスすることが必要になる場合のために、削除されたメッセージのコピーを保持できます。 
  
## <a name="before-you-begin"></a>はじめに

- 予想所要時間 : 10 分。実際の時間は、メールボックスのサイズと検索クエリによって異なる場合があります。
    
- Exchange 管理センター (EAC) を使用して、これらの手順を実行することはできません。シェルを使用する必要があります。
    
- ユーザーのメールボックスにあるメッセージを検索し、削除するためには、次の両方の管理役割を割り当てられる必要があります。
    
  - **メールボックスの検索**-この役割を使用すると、組織内の複数のメールボックス間でメッセージを検索することができます。既定では、管理者はこの役割を割り当てられていません。メールボックスを検索できるようにこの役割を自分自身に割り当てるには、自分自身を Discovery Management 役割グループのメンバーとして追加します。「[ユーザーを Discovery Management 役割グループに追加する」を](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)参照してください。
    
  - **メールボックスインポートエクスポート**-この役割を使用すると、ユーザーのメールボックスからメッセージを削除することができます。既定では、この役割はどの役割グループにも割り当てられていません。ユーザーのメールボックスからメッセージを削除するには、"Organization Management/組織の管理" 役割グループに [メールボックスのインポートのエクスポート] 役割を追加します。詳細については、「 [Manage role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) 」の「役割グループに役割を追加する」セクションを参照してください。 
    
- メッセージの削除を行うメールボックスで単一アイテムの回復が有効になっている場合は、最初にその機能を無効にする必要があります。詳細については、「[メールボックスの単一アイテムの回復を有効または無効にする](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)」を参照してください。
    
- メッセージを削除するメールボックスが保留になっている場合は、保留リストを削除してメールボックスの内容を削除する前に、レコード管理または法務部門に確認することをお勧めします。承認を得た後、「[回復可能なアイテム」フォルダーをクリーンアップ](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)するトピックに記載されている手順に従います。
    
- **Search-Mailbox** コマンドレットを使用して、最大 10,000 個のメールボックスを検索できます。10,000 以上のメールボックスを持つ Exchange Online 組織の場合は、コンプライアンス検索機能 (または対応する **New-ComplianceSearch** コマンドレット) を使用して無制限の数のメールボックスを検索できます。その後、 **New-ComplianceSearchAction** コマンドレットを使用して、コンプライアンス検索によって返されたメッセージを削除できます。詳細については、「 [Office 365 組織でメール メッセージの検索と削除を行う - 管理者向けヘルプ](https://go.microsoft.com/fwlink/p/?LinkId=786856)」を参照してください。
    
- ( *SearchQuery*  パラメーターを使用していて) 検索クエリが含まれている場合、 **Search-Mailbox** コマンドレットは、検索結果で最大 10,000 個のアイテムを返します。したがって、検索クエリを含める場合は、 **Search-Mailbox** コマンドを複数回実行して 10,000 を超えるアイテムを削除する必要があるかもしれません。 
    
- **検索-メールボックス**コマンドレットを実行すると、ユーザーのアーカイブメールボックスも検索されます。同様に、 _DeleteContent_スイッチを指定して**Search メールボックス**コマンドレットを使用すると、プライマリアーカイブメールボックス内のアイテムが削除されます。これを防止するには、「 ** 」と表示されているスイッチを含めることができます。また、予期しないデータ損失が発生する可能性があるため、自動拡張アーカイブが有効になっている Exchange Online メールボックス内のメッセージを削除する場合は、 _DeleteContent_スイッチを使用しないことをお勧めします。 
    
## <a name="search-messages-and-log-the-search-results"></a>メッセージを検索し、検索結果をログに記録する

この例は、April Stewart のメールボックスに対し、件名フィールドに「Your bank statement」という語句が含まれるメッセージを検索し、その結果を、管理者のメールボックスの SearchAndDeleteLog フォルダーに記録します。メッセージは、対象のメールボックスにコピーまたは対象のメールボックスから削除されません。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

次の使用例は、組織内の全メールボックスでファイル名に「Trojan」という言葉が含まれるあらゆる種類の添付ファイルが付いたメッセージを検索し、管理者のメールボックスにログ メッセージを送信します。
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

構文およびパラメーターの詳細については、「[Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)」を参照してください。
  
 
## <a name="search-and-delete-messages"></a>メッセージを検索して削除する

この例は、April Stewart のメールボックスに対し、件名フィールドに「Your bank statement」という語句が含まれるメッセージを検索し、検索結果を別のフォルダーにコピーせずに、そのメッセージをソース メールボックスから削除します。前述のように、ユーザーのメールボックスからメッセージを削除するためには、"Mailbox Import Export" 役割を割り当てられている必要があります。
  
> [!IMPORTANT]
> **Search-Mailbox** コマンドレットに  _DeleteContent_ スイッチを指定して使用すると、メッセージはソース メールボックスから完全に削除されます。メッセージを完全に削除する前に、  _LogOnly_ スイッチを使用して検索で見つかったメッセージが削除される前にログを生成するか、またはメッセージがソース メールボックスから削除される前に別のメールボックスにコピーするかのいずれかを推奨します。 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

この例は、April Stewart のメールボックスに対し、件名フィールドに「Your bank statement」という語句が含まれるメッセージを検索し、その結果をメールボックス BackupMailbox の AprilStewart-DeletedMessages フォルダーにコピーして、そのメッセージを April のメールボックスから削除します。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

次の使用例は、組織内の全メールボックスで件名が「このファイルをダウンロード」というメッセージを検索してから、完全に削除します。 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

構文およびパラメーターの詳細については、「[Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)」を参照してください。

## <a name="using-the--loglevel-full-parameter"></a>-LogLevel Full パラメーターを使用する

前のいくつかの例では、 _Search-Mailbox_ コマンドレットによって返された結果に関する詳細情報をログ記録するため、  `Full` 値を指定した  **LogLevel** パラメーターを使用しています。 このパラメーターを含めると、メール メッセージが作成され、  _TargetMailbox_ パラメーターによって指定されたメールボックスに送信されます。ログ ファイル (Search Results.csv という名前の CSV 形式のファイル) はこのメール メッセージに添付され、  _TargetFolder_ パラメーターによって指定されたフォルダーに配置されます。ログ ファイルには、 **Search-Mailbox** コマンドレットを実行すると、検索結果に含まれる各メッセージの行が含まれています。 
