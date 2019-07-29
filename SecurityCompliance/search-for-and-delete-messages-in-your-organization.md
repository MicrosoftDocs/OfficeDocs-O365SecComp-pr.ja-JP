---
title: Office 365 組織でメール メッセージの検索と削除を行う - 管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Office 365 セキュリティ/コンプライアンス センターの検索と消去機能を使って、組織のすべてのメールボックスからメール メッセージを検索し、削除できます。
ms.openlocfilehash: 318a7deeedb6bd4875a7a2ca0f5e33b764bdbac3
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854631"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>Office 365 組織でメール メッセージの検索と削除を行う - 管理者向けヘルプ

**この記事は管理者向けです。メールボックスで削除するアイテムを探している場合は、「[クイック検索を使ってメッセージまたはアイテムを検索する](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)」を参照してください。**|
   
Office 365 のコンテンツ検索機能を使って、組織のすべてのメールボックスにあるメール メッセージを検索し削除できます。 この機能を使用して、次のように有害な、またはリスクが高い可能性があるメールを検索し、削除することができます。
  
- 危険性のある添付ファイルやウイルスを含むメッセージ
    
- フィッシング メッセージ
    
- 機密データを含むメッセージ
    
> [!CAUTION]
> 検索と消去は、必要なアクセス許可が割り当てられていれば、誰でも組織のメールボックスからメール メッセージを削除できる強力な機能です。 
  
## <a name="before-you-begin"></a>始める前に

- コンテンツ検索を作成して実行するには、**電子情報開示管理者**役割グループのメンバーであるか、**コンプライアンス検索**の管理役割が割り当てられている必要があります。 メッセージを削除するには、**Organization Management** 役割グループのメンバーであるか、**検索と消去**の管理役割が割り当てられている必要があります。 ユーザーを役割グループに追加する方法の詳細については、「[ユーザーにセキュリティ/コンプライアンス センターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」をご覧ください。
    
- メッセージを削除するには、セキュリティ/コンプライアンス センターの PowerShell を使用する必要があります。 接続方法については、「[手順 2](#step-2-connect-to-security--compliance-center-powershell)」を参照してください。
    
- メールボックスごとに最大 10 個のアイテムを一度に削除できます。 メッセージを検索し削除するための機能はインシデント対応ツールを意図したものなので、この制限により、メールボックスからすばやくかつ確実にメッセージを削除できます。 これは、ユーザーのメールボックスをクリーンアップするための機能ではありません。 10 個を超えるアイテムを削除する場合は、Exchange Online の PowerShell で **Search-Mailbox -DeleteContent** コマンドを使用できます。 「[メッセージを検索して削除する - 管理者向けヘルプ](search-for-and-delete-messagesadmin-help.md)」を参照してください。
    
- コンテンツ検索で検索と削除アクションを実行してアイテムを削除できるメールボックスの最大数は 50,000 個です。 コンテンツ検索 ([手順 1](#step-1-create-a-content-search-to-find-the-message-to-delete) で作成) に 50,000 を超えるソース メールボックスが含まれる場合、削除アクション (手順 3 で作成) は失敗します。 50,000 を超えるメールボックスに対して検索と削除の操作を実行するためのヒントについては、「[詳細情報](#more-information)」セクションを参照してください。 
    
- この記事の手順は、Exchange Online のメールボックスとパブリック フォルダーにあるアイテムを削除する場合にのみ使用できます。 SharePoint や OneDrive for Business のサイトからコンテンツを削除する場合には使用できません。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>手順 1: コンテンツ検索を作成して、削除するメッセージを探す

最初の手順は、組織のメールボックスから削除するメッセージを見つけるコンテンツ検索を作成し、実行することです。 セキュリティ/コンプライアンス センターを使用するか、**New-ComplianceSearch** コマンドレットと **Start-ComplianceSearch** コマンドレットを実行すると、検索を作成できます。 [手順 3](#step-3-delete-the-message) で **New-ComplianceSearchAction -Purge** コマンドを実行すると、この検索のクエリに一致するメッセージは削除されます。 コンテンツ検索を作成し、検索クエリを構成する方法については、次のトピックを参照してください。 
  
- [Office 365 のコンテンツ検索](content-search.md)
    
- [コンテンツ検索のキーワード クエリ](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> この手順で作成するコンテンツ検索で検索されるコンテンツの場所に、SharePoint や OneDrive for Business のサイトを含めることはできません。 メール メッセージに使われるコンテンツ検索には、メールボックスとパブリック フォルダーのみを含めることができます。 コンテンツ検索にサイトが含まれる場合、**New-ComplianceSearchAction** コマンドレットを実行すると、手順 3 でエラーが発生します。 
  
### <a name="tips-for-finding-messages-to-remove"></a>削除するメッセージを見つけるためのヒント

検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。
  
- メッセージの件名に使われているテキストまたはフレーズを正確に記憶している場合は、検索クエリの **Subject** プロパティをご利用ください。 
    
- メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。 
    
- メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。 
    
- 検索結果をプレビューして、検索が、削除を希望するメッセージだけを返したことを確認します。
    
- 検索見積もりの統計情報 (セキュリティ/コンプライアンス センターの検索の詳細ウィンドウや、[Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) コマンドレットを使用して表示される情報) を使用して、結果の合計数のカウントを取得します。 
    
不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。
  
- このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>手順 2: セキュリティ/コンプライアンス センターの PowerShell に接続する

次に、組織のセキュリティ/コンプライアンス センターの PowerShell に接続します。 詳細な手順については、「[セキュリティ/コンプライアンス センターの PowerShell への接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。
  
Office 365 アカウントで多要素認証 (MFA) やフェデレーション認証を使用する場合、次のトピックの手順ではセキュリティ/コンプライアンス センターの PowerShell に接続できません。 代わりに、「[多要素認証を使用してセキュリティ/コンプライアンス センターの PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)」の手順を参照してください。
  
## <a name="step-3-delete-the-message"></a>手順 3:メッセージを削除する

削除するメッセージを返すコンテンツ検索を作成して検索条件を絞り、セキュリティ/コンプライアンス センターの PowerShell に接続したら、最後に **New-ComplianceSearchAction** コマンドレットを実行して、メッセージを削除します。 メッセージは、論理的に削除することも、物理的に削除することもできます。 論理的に削除したアイテムは、ユーザーの [回復可能なアイテム] フォルダーに移動され、削除済みアイテムの保持期間が切れるまで保持されます。 物理的に削除したメッセージは、メールボックスから完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に完全に削除されます。 そのメールボックスで単一アイテムの回復が有効になっている場合、物理的に削除したアイテムは、削除済みアイテムの保持期間が切れると完全に削除されます。 メールボックスが保留中になっている場合は、削除したメッセージは、そのアイテムの保留期間が切れるか、その保留がメールボックスから削除されるまで保持されます。
  
次の例では、"Remove Phishing Message"(フィッシング メッセージの削除) という名前のコンテンツ検索によって返された検索結果がコマンドによって論理的に削除されます。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

Remove Phishing Message コンテンツ検索によって返されたアイテムを物理的に削除するには、次のコマンドを実行します。

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

前のコマンドを実行してメッセージを論理的または物理的に削除する場合、*SearchName* パラメーターで指定される検索は、手順 1 で作成したコンテンツ検索になります。 
  
詳細については、「[New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)」を参照してください。

## <a name="more-information"></a>詳細情報

- **検索と削除の操作の状態を取得するにはどうすればよいですか?**

    **Get-ComplianceSearchAction** を実行すると、その削除操作の状態を取得できます。 **New-ComplianceSearchAction** コマンドレットを実行したときに作成されるオブジェクトは、`<name of Content Search>_Purge` という形式で名前付けされます。 
    
- **メッセージを削除するとどうなりますか?**

   `New-ComplianceSearchAction -Purge -PurgeType HardDelete` コマンドを使用して削除されたメッセージは、Purges フォルダーに移動され、ユーザーはアクセスできなくなります。 Purges フォルダーに移動されたメッセージは、そのメールボックスで単一アイテムの回復が有効になっている場合、削除済みアイテムの保持期間が切れるまで保持されます。 (Office 365 では、新しいメールボックスを作成すると、既定で単一アイテムの回復が有効になります)。削除済みアイテムの保持期間を過ぎると、そのメッセージは完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に Office 365 から消去されます。 

   `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` コマンドを使用すると、メッセージは、ユーザーの回復可能なアイテム フォルダーの Deletions フォルダーに移動されます。 Office 365 から直ちに削除されることはありません。 ユーザーは、メールボックスに構成されている削除したアイテムの保持期間に基づき、その期間は削除済みアイテム フォルダーのメッセージを復元できます。 この保持期間を過ぎるか、過ぎる前にユーザーがメッセージを消去すると、メッセージは Purges フォルダーに移動され、ユーザーはアクセスできなくなります。 Purges フォルダーに移動されたメッセージは、そのメールボックスで単一アイテムの回復が有効になっている場合、メールボックスに構成されている削除済みアイテムの保持期間が切れるまで保持されます。 (Office 365 では、新しいメールボックスを作成すると、既定で単一アイテムの回復が有効になります)。削除済みアイテムの保持期間を過ぎると、そのメッセージは完全に削除するようにマークされ、管理フォルダー用アシスタントによって次回そのメールボックスが処理される際に Office 365 から消去されます。 
    
- **50,000 を超えるメールボックスからメッセージを削除するにはどうすればよいですか?**

    前述のとおり、検索と削除の操作を実行できるメールボックスの上限は 50,000 です。 50,000 を超えるメールボックスに対して検索と削除の操作を実行する必要がある場合は、検索対象となるメールボックスの数を 50,000 未満に減らす一時的な検索権限フィルターを作成することをご検討ください。 たとえば、異なる部署、都道府県、国のメールボックスが組織内にある場合、そのようなメールボックスのプロパティのいずれかを基にメールボックスの検索権限フィルターを作成して、組織のメールボックスのサブセットを検索できます。 検索権限フィルターを作成したら、検索を作成 (手順 1 を参照) し、メッセージを削除 (手順 3 を参照) します。 その後、フィルターを編集し、別のメールボックスのセット内のメッセージを検索して削除できます。 検索権限フィルターの作成の詳細については、「[コンテンツ検索用にアクセス許可フィルターを設定する](permissions-filtering-for-content-search.md)」を参照してください。
    
- **検索結果に含まれるインデックスのないアイテムも削除されますか?**

    いいえ。`New-ComplianceSearchAction -Purge コマンドでは、インデックスのないアイテムは削除されません。 
    
- **メッセージが、インプレース ホールドまたは訴訟ホールドが設定されたメールボックスから削除されたり、Office 365 の保持ポリシーに割り当てられたりするとどうなりますか?**

    消去されて Purges フォルダーに移動されたメッセージは、保持期間が切れるまで保持されます。 保持期間が無期限である場合は、ホールドが解除されるか、または保持期間が変更されるまで、アイテムは保持されます。
    
- **検索と削除のワークフローが、セキュリティ/コンプライアンス センターのさまざまな役割グループに分けられているのはなぜですか?**

    前述したように、メールボックスを検索するには、電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理の役割が割り当てられている必要があります。 メッセージを削除するには、組織管理役割グループのメンバーであるか、検索と消去の管理の役割が割り当てられている必要があります。 この制限によって、組織のメールボックスを検索できるユーザーとメッセージを削除できるユーザーを制御できます。 
