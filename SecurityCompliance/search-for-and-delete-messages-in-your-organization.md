---
title: Office 365 組織の電子メールメッセージを検索して削除する-管理者向けヘルプ
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Office 365 のセキュリティ & コンプライアンスセンターで検索と削除の機能を使用して、組織内のすべてのメールボックスから電子メールメッセージを検索し、削除します。
ms.openlocfilehash: c6fa0d09852016b918375dbff5a19468886d86b3
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000270"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>Office 365 組織の電子メールメッセージを検索して削除する-管理者向けヘルプ

**この記事は、管理者を対象としています。削除するメールボックス内のアイテムを検索しようとしていますか?「[クイック検索を使用してメッセージまたはアイテムを検索する」を](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)参照してください。**|
   
Office 365 のコンテンツ検索機能を使用して、組織内のすべてのメールボックスから電子メールメッセージを検索し、削除することができます。 これは、次に示す潜在的に有害または高リスクのメールを見つけて削除するのに役立ちます。
  
- 危険な添付ファイルまたはウイルスを含むメッセージ
    
- フィッシング メッセージ
    
- 機密データを含むメッセージ
    
> [!CAUTION]
> 検索と削除は、必要なアクセス許可が割り当てられているユーザーが組織内のメールボックスから電子メールメッセージを削除できるようにするための強力な機能です。 
  
## <a name="before-you-begin"></a>はじめに

- コンテンツ検索を作成して実行するには、**電子情報開示マネージャー**の役割グループのメンバーであるか、または**コンプライアンス検索**管理役割が割り当てられている必要があります。 メッセージを削除するには、**組織の管理**役割グループのメンバーであるか、または**検索と削除**の管理役割が割り当てられている必要があります。 役割グループへのユーザーの追加の詳細については、「[ユーザーにセキュリティ/コンプライアンスセンターへのアクセス権を付与する](grant-access-to-the-security-and-compliance-center.md)」を参照してください。
    
- メッセージを削除するには、Security & コンプライアンスセンター PowerShell を使用する必要があります。 接続方法については、[手順 2](#step-2-connect-to-security--compliance-center-powershell)を参照してください。
    
- 一度に削除できるアイテムは、メールボックスごとに10個までです。 メッセージを検索し削除するための機能はインシデント対応ツールを意図したものなので、この制限により、メールボックスからすばやくかつ確実にメッセージを削除できます。 この機能は、ユーザーのメールボックスをクリーンアップするためのものではありません。 10を超えるアイテムを削除するには、Exchange Online PowerShell で**DeleteContent**コマンドを使用します。 「[メッセージを検索して削除する-管理者ヘルプ](search-for-and-delete-messagesadmin-help.md)」を参照してください。
    
- 検索と削除の操作を実行して、コンテンツ検索でアイテムを削除できる最大メールボックス数は5万です。 [手順 1](#step-1-create-a-content-search-to-find-the-message-to-delete)で作成したコンテンツ検索に5万個を超えるソースメールボックスがある場合、削除アクション (手順3で作成したもの) は失敗します。 5万を超えるメールボックスで検索と削除の操作を実行する際のヒントについては、「 [More information](#more-information) 」セクションを参照してください。 
    
- この記事の手順は、Exchange Online メールボックスおよびパブリックフォルダー内のアイテムを削除する場合にのみ使用できます。 これを使用して SharePoint または OneDrive for business サイトからコンテンツを削除することはできません。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>手順 1: コンテンツ検索を作成して、削除するメッセージを探す

最初に、コンテンツ検索を作成して実行し、組織のメールボックスから削除するメッセージを見つけます。 セキュリティ & コンプライアンスセンターを使用するか、 **new-compliancesearch**コマンドレットと**new-compliancesearch**コマンドレットを実行することによって、検索を作成できます。 この検索のクエリに一致するメッセージは、[手順 3](#step-3-delete-the-message)で**new-compliancesearchaction-Purge**コマンドを実行することによって削除されます。 コンテンツ検索の作成と、検索クエリの構成の詳細については、以下のトピックをご覧ください。 
  
- [Office 365 のコンテンツ検索](content-search.md)
    
- [コンテンツ検索のキーワードクエリ](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> この手順で作成するコンテンツ検索で検索されるコンテンツの場所には、SharePoint または OneDrive for business サイトを含めることはできません。 電子メールメッセージに使用するコンテンツ検索には、メールボックスとパブリックフォルダーのみを含めることができます。 コンテンツ検索にサイトが含まれている場合、 **new-compliancesearchaction**コマンドレットを実行すると、手順3でエラーが表示されます。 
  
### <a name="tips-for-finding-messages-to-remove"></a>削除するメッセージを検索するためのヒント

検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。
  
- メッセージの件名に使用されているテキストまたは語句が正確にわかっている場合は、検索クエリの**subject**プロパティを使用します。 
    
- メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。 
    
- メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。 
    
- 検索結果をプレビューして、削除するメッセージのみが検索によって返されたことを確認します。
    
- 検索の推定統計 (セキュリティ & コンプライアンスセンターでの検索の詳細ウィンドウ、または[new-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)コマンドレットを使用) を使用して、結果の合計数のカウントを取得します。 
    
不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。
  
- このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a>手順 2: Security & コンプライアンスセンター PowerShell に接続する

次の手順では、組織の Security & コンプライアンスセンター PowerShell に接続します。 詳細な手順については、「 [Connect to Security & コンプライアンスセンター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)」を参照してください。
  
Office 365 アカウントで多要素認証 (MFA) またはフェデレーション認証を使用している場合は、「Security & コンプライアンスセンター PowerShell への接続」に記載されている前のトピックの手順を使用することはできません。 代わりに、「[多要素認証を使用してセキュリティ & コンプライアンスセンター PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)」の手順を参照してください。
  
## <a name="step-3-delete-the-message"></a>手順 3: メッセージを削除する

削除してセキュリティ & コンプライアンスセンター PowerShell に接続されているメッセージを返すようにコンテンツ検索を作成して調整した後、最後の手順として、 **new-compliancesearchaction**コマンドレットを実行してメッセージを削除します。 メッセージをソフトまたはハード削除することができます。 回復可能な削除によって削除されたメッセージは、ユーザーの回復可能なアイテムフォルダーに移動され、削除済みアイテムの保存期間が経過するまで保持されます。 物理的に削除されたメッセージは、メールボックスから完全に削除するようマークが付けられ、管理フォルダーアシスタントによって次回メールボックスが処理されるときに完全に削除されます。 メールボックスの単一アイテムの回復が有効になっている場合は、削除済みアイテムの保存期間の期限が切れた後、完全に削除されたアイテムが完全に削除されます。 メールボックスがホールドの対象になっている場合、削除されたメッセージは、アイテムの保持期間が満了するか、保持がメールボックスから削除されるまで保持されます。
  
次の例では、"フィッシング詐欺メッセージの削除" という名前のコンテンツ検索によって返された検索結果がコマンドによって削除されます。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

"フィッシングメッセージの削除" コンテンツ検索によって返されるアイテムを物理的に削除するには、次のコマンドを実行します。

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

前のコマンドを実行してメッセージをソフトまたは物理的に削除すると、 *searchname*パラメーターで指定された検索は、手順1で作成したコンテンツ検索になることに注意してください。 
  
詳細については、「 [new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)」を参照してください。

## <a name="more-information"></a>詳細情報

- **検索と削除の操作の状態を取得するには、どうすればよいですか。**

    **Get-ComplianceSearchAction** を実行して、削除操作の状態を取得します。 **new-compliancesearchaction**コマンドレットを実行するときに作成されるオブジェクトは、次`<name of Content Search>_Purge`の形式を使用して指定されていることに注意してください。 
    
- **メッセージを削除した後はどうなりますか。**

   `New-ComplianceSearchAction -Purge -PurgeType HardDelete`コマンドを使用して削除されたメッセージは、削除フォルダーに移動され、ユーザーがアクセスすることはできません。 メッセージが [削除] フォルダーに移動された後、メールボックスに対して単一アイテムの回復が有効になっている場合は、削除済みアイテムの保存期間中はメッセージが保持されます。 (Office 365 では、新しいメールボックスが作成されるときに、単一アイテムの回復が既定で有効になっています。)削除済みアイテムの保存期間の期限が切れると、メッセージは永続的な削除のマークが付けられ、次回メールボックスが管理フォルダーアシスタントによって処理されたときに Office 365 から削除されます。 

   `New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドを使用すると、メッセージはユーザーの回復可能なアイテムフォルダーの削除フォルダーに移動されます。 Office 365 からすぐに削除されることはありません。 ユーザーは、メールボックスに対して構成された削除済みアイテムの保存期間に基づいて、削除済みアイテムフォルダー内のメッセージを復元することができます。 この保存期間が過ぎると (または、ユーザーが期限切れになる前にメッセージを削除すると)、メッセージはパージフォルダーに移動され、ユーザーがアクセスできなくなります。 [削除] フォルダーで、メールボックスに対して単一アイテムの回復が有効になっている場合に、メールボックスに対して構成された削除済みアイテムの保存期間に基づいて、メッセージは保持期間中保持されます。 (Office 365 では、新しいメールボックスが作成されるときに、単一アイテムの回復が既定で有効になっています。)削除済みアイテムの保存期間の期限が切れると、メッセージは永続的な削除のマークが付けられ、次回メールボックスが管理フォルダーアシスタントによって処理されたときに Office 365 から削除されます。 
    
- **5万を超えるメールボックスからメッセージを削除する必要がある場合はどうなりますか。**

    前述したように、最大5万のメールボックスで検索と削除の操作を実行できます。 5万を超えるメールボックスで検索と削除の操作を実行する必要がある場合は、検索対象のメールボックスの数が5万未満になるようにするための、一時検索アクセス許可フィルターを作成することを検討してください。 たとえば、組織のメールボックスが異なる部署、都道府県、または国に含まれている場合は、これらのいずれかのメールボックスのプロパティに基づいてメールボックス検索アクセス許可フィルターを作成し、組織内のメールボックスのサブセットを検索することができます。 検索アクセス許可フィルターを作成したら、手順1で説明した検索を作成し、メッセージを削除します (手順3を参照)。 その後、フィルターを編集して、別のメールボックスのセット内のメッセージを検索し、削除することができます。 検索アクセス許可フィルターの作成の詳細については、「 [Configure permissions filtering for Content search](permissions-filtering-for-content-search.md)」を参照してください。
    
- **検索結果に含まれるインデックスのないアイテムは削除されますか。**

    いいえ。 ' new-compliancesearchaction-削除コマンドは、インデックスが作成されていないアイテムを削除しません。 
    
- **インプレース保持または訴訟ホールドの対象となっているメールボックスから、または Office 365 アイテム保持ポリシーに割り当てられているメッセージが削除された場合はどうなりますか?**

    メッセージが削除されて、[削除] フォルダーに移動されると、保持期間が経過するまで、メッセージは保持されます。 保持期間が無期限である場合は、ホールドが解除されるか、または保持期間が変更されるまで、アイテムは保持されます。
    
- **検索と削除のワークフローが異なるセキュリティ/コンプライアンスセンターの役割グループに分けられるのはなぜですか?**

    前述のとおり、メールボックスを検索するには、ユーザーは電子情報開示管理者役割グループのメンバーであるか、コンプライアンス検索の管理役割が割り当てられている必要があります。 メッセージを削除するには、Organization Management 役割グループのメンバーであるか、検索と消去の管理役割が割り当てられている必要があります。 これにより、組織内でメールボックスを検索できる人と、メッセージを削除できる人とを制御できます。 
