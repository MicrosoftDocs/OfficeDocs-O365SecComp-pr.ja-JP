---
title: 検索し、Office 365 の組織の管理のヘルプで電子メール メッセージを削除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 4/25/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 検索を使用し、Office 365 のセキュリティの機能を削除&amp;コンプライアンス ・ センターを検索し、組織内のすべてのメールボックスから電子メール メッセージを削除します。
ms.openlocfilehash: 8bba4be473977afc229f64dfba6fd1514b86ecd2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531954"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a>検索し、Office 365 の組織の管理のヘルプで電子メール メッセージを削除

**この資料では、管理者用です。削除するメールボックスのアイテムを検索しようとしていますか。[メッセージまたはインスタント検索を使用してアイテムを検索](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)を参照してください。**|
   
Office 365 のコンテンツの検索機能を使用するにを検索し、組織内のすべてのメールボックスから電子メール メッセージを削除します。これを検索して、次のように、有害なまたは危険度の高い電子メールを削除することができます。
  
- 危険性のある添付ファイルやウイルスを含むメッセージ
    
- フィッシング メッセージ
    
- 機密データを含むメッセージ
    
> [!CAUTION]
> 検索と削除は、強力な機能により、すべてのユーザーを組織内のメールボックスから電子メール メッセージを削除するのには必要なアクセス許可が割り当てられているです。 
  
## <a name="before-you-begin"></a>はじめに

- 作成し、コンテンツの検索を実行するには、**電子的証拠開示マネージャー**の役割グループのメンバーであるか、**コンプライアンス検索**の管理役割を割り当てる必要があります。メッセージを削除するには、**組織の管理**役割グループのメンバーであるか、**検索および削除**の管理役割を割り当てる必要があります。ユーザーを役割グループに追加する方法の詳細についてを参照してください[Office 365 のセキュリティにアクセスできるように&amp;コンプライアンス センター](grant-access-to-the-security-and-compliance-center.md)です。
    
- セキュリティを使用する必要が&amp;メッセージを削除するのにはセンター PowerShell を遵守します。接続する方法について、[手順 2](#step-2-connect-to-security-amp-compliance-center-powershell)を参照してください。
    
- メールボックスあたり 10 個のアイテムの最大値を同時に削除できます。検索してメッセージを削除する機能は、インシデント対応ツールになるようとしているためこの制限により、メールボックスからメッセージが削除されます簡単にできます。この機能は、ユーザーのメールボックスをクリーンアップするのにはありません。10 個を超えるアイテムを削除するには、Exchange オンライン PowerShell で**検索メールボックス DeleteContent**コマンドを使用できます。[検索して削除するメッセージの管理のヘルプ](search-for-and-delete-messagesadmin-help.md)を参照してください。
    
- コンテンツの検索を使用している内の項目を削除するには、検索を行うとアクションを削除することでメールボックスの最大数は、50,000 です。([手順 1](#step-1-create-a-content-search-to-find-the-message-to-delete)で作成) をコンテンツの検索には、50,000 以上のソース メールボックスがある、(手順 3 で作成する場合) を削除操作が失敗します。検索を実行する方法についてのヒントの[詳細について](#more-information)はを参照してくださいし、50,000 以上のメールボックスでの操作を削除します。 
    
- この資料の手順は、Exchange Online のメールボックスおよびパブリック フォルダー内のアイテムを削除するのにのみ使用できます。SharePoint または OneDrive からビジネス サイトのコンテンツを削除するのには使用できません。
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a>手順 1: コンテンツ検索を作成して、削除するメッセージを探す

作成し、組織内のメールボックスから削除するメッセージを検索するコンテンツの検索を実行するのには、まず。セキュリティを使用して検索を作成することができます&amp;コンプライアンス センターか**新規 ComplianceSearch**および**開始 ComplianceSearch**コマンドレットを実行しています。この検索のクエリに一致するメッセージは、[手順 3](#step-3-delete-the-message)で**新規 ComplianceSearchAction**コマンドレットを実行することによって削除されます。コンテンツの検索を作成して、検索クエリを構成する方法については、次のトピックを参照してください。 
  
- [Office 365 でのコンテンツの検索](content-search.md)
    
- [コンテンツ検索用のキーワード クエリ](keyword-queries-and-search-conditions.md)
    
- [New-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [Start-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> この手順で作成したコンテンツの検索に検索対象となるコンテンツの場所は、ビジネス サイトの SharePoint または OneDrive を含めることはできません。電子メール メッセージに使用されるコンテンツの検索では、メールボックスとパブリック フォルダーのみを含めることができます。コンテンツの検索には、サイトが含まれている場合、エラーが返さステップ 3 で**新規 ComplianceSearchAction**コマンドレットを実行するとします。 
  
### <a name="tips-for-finding-messages-to-remove"></a>削除するメッセージの検索に関するヒント

検索クエリの目標は、削除するメッセージだけに検索結果を絞り込むことです。次にヒントを示します。
  
- 正確な語句、メッセージの件名行で使用されている場合は、検索クエリの**Subject**プロパティを使用します。 
    
- メッセージの正確な日付 (または期間) がわかる場合は、検索クエリに **Received** プロパティを含めます。 
    
- メッセージの送信者がわかる場合は、検索クエリに **From** プロパティを含めます。 
    
- 検索に、メッセージ (またはメッセージ) のみが返されることを確認するのには検索結果をプレビュー表示を削除します。
    
- 見積もり、検索の統計を使用して (セキュリティでの検索の詳細ウィンドウに表示されている&amp;コンプライアンス センターまたは[Get ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934)コマンドレットを使用して) 結果の合計数のカウントを取得します。 
    
不審な電子メール メッセージを検索するクエリの 2 つの例を次に示します。
  
- このクエリは、2016 年 4 月 13 日から 2016 年 4 月 14 日までの間にユーザーが受信し、単語 "action" と "required" が件名に含まれるメッセージを返します。
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- このクエリは、chatsuwloginsset12345@outlook.com から送信され、完全に一致する語句 "Update your account information" (アカウント情報を更新してください) が件名に含まれているメッセージを返します。
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security-amp-compliance-center-powershell"></a>ステップ 2: 接続セキュリティ&amp;コンプライアンス センター PowerShell

セキュリティへの接続を次の手順は、 &amp; 、組織のコンプライアンス センターの PowerShell。手順についてを参照してください[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
Office 365 アカウントでは、多要素認証 (MFA) またはフェデレーション認証を使用する場合セキュリティへの接続の前のトピックでの手順を使うことはできません&amp;コンプライアンス センター PowerShell。代わりに、トピックの指示を参照してください[Office 365 のセキュリティへの接続&amp;コンプライアンス センター PowerShell の多要素認証を使用して](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)。
  
## <a name="step-3-delete-the-message"></a>ステップ 3: メッセージを削除します。

作成しを削除するのにはセキュリティに接続しているメッセージが返されるコンテンツの検索を改良した後&amp;コンプライアンス センター PowerShell では、最後に、メッセージを削除するのには**新規 ComplianceSearchAction**コマンドレットを実行します。削除されたメッセージは、ユーザーの回復可能なアイテム] フォルダーに移動されます。 
  
次の例では、"Remove Phishing Message"(フィッシング メッセージの削除) という名前のコンテンツ検索によって返された検索結果がコマンドによって削除されます。 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```
  
*SearchName*パラメーターで指定された検索では、手順 1 で作成したコンテンツの検索がされます。 
  
詳細については、[新規 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)を参照してください。
  

## <a name="more-information"></a>詳細情報

- **検索のステータスを取得および操作を削除する方法**

    削除操作の状態を取得する**Get ComplianceSearchAction**を実行します。この形式を使用して**新規 ComplianceSearchAction**コマンドレットを実行するときに作成されるオブジェクトの名前はことに注意してください: `<name of Content Search>_Purge`。 
    
- **メッセージを削除した後はどうなるか**

    使用して削除されたメッセージ、`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドは、ユーザーの回復可能なアイテム] フォルダーの削除フォルダーに移動します。されていない、Office 365 から直ちにパージされます。ユーザーは、メールボックスに対して構成されている削除済みアイテムの保持期間に基づいて、期間の削除済みアイテム フォルダー内のメッセージを回復できます。この保存期間の有効期限が切れた (または期限が切れたユーザーの前にメッセージを削除する場合)、メッセージは削除フォルダーに移動され、ユーザーが再びアクセスすることができます。1 回パージ] フォルダーでメッセージもう一度は保持されます、メールボックスの単一アイテムの回復が有効になっている場合は、メールボックスの構成されている削除済みアイテムの保存期間に基づいて、期間の。(、Office 365 で単一アイテムの回復は既定で有効に新しいメールボックスが作成されるときです。)削除済みアイテムの保存期間を過ぎると、メッセージが完全に削除のマークされているし、次のように、メールボックスが管理フォルダー アシスタントによって処理されたときに Office 365 からパージされます。 
    
- **すればメッセージが削除され、ユーザーの回復可能な項目] フォルダーに移動しますか。**

    メッセージを削除した後、同じコンテンツの検索を実行する場合は、同じ数の検索結果が表示されますが、ユーザーのメールボックスからメッセージが削除されていないことを考えるかもしれませんが、)。これは、コンテンツの検索は、[回復可能な項目] フォルダーを検索するため、削除されたメッセージの移動先を実行した後は、`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドです。回復可能な項目] フォルダーに移動する場合にメッセージを確認するには、探索メールボックスに (とを使用して同じソース メールボックス検索条件として、コンテンツの検索は、手順 1 で作成)、埋め込み電子的証拠開示検索と検索結果のコピーを実行できます。検出メールボックスに検索結果を表示し、メッセージが回復可能なアイテム] フォルダーに移動されたことを確認できます。元のメールボックスおよびコンテンツの検索からの検索クエリのリストを使用する埋め込みの電子的証拠開示検索を作成する方法については[、電子的証拠開示ワークフロー内のコンテンツの検索を使用](use-content-search-in-ediscovery.md)を参照してください。 
    
- **ある場合は 50,000 人を超えるメールボックスからメッセージを削除しますか。**

    前述したように、検索を実行し、最大 50,000 のメールボックスでの操作を削除できます。検索を実行し、50,000 を超えるメールボックスでの操作を削除する必要がある場合は、50,000 未満のメールボックスを検索するメールボックスの数を削減する一時的な検索のアクセス許可フィルターを作成することを検討します。などの組織では、さまざまな部門、状態、または国でのメールボックスが含まれている場合は、組織内のメールボックスのサブセットを検索するのにはこれらのメールボックスのプロパティのいずれかに基づいて、メールボックス検索のアクセス許可のフィルターを作成できます。検索のアクセス許可フィルターを作成した後 (手順 1 で説明した) 検索を作成し、(手順 3 で説明した) メッセージを削除します。検索し、別の一連のメールボックスにメッセージを削除するフィルターを編集できます。検索のアクセス許可のフィルターを作成する方法の詳細については、[アクセス許可を構成するコンテンツの検索のフィルター処理](permissions-filtering-for-content-search.md)を参照してください。
    
- **検索結果に含まれるインデックスの項目は削除されます。**

    残念ですが、`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`コマンドは、インデックスを持たないアイテムを削除しません。 
    
- **インプレース保持または訴訟を保持していますか、Office 365 のリテンション ・ ポリシーに割り当てられているメールボックスからメッセージを削除するとどうなりますか。**

    (ユーザー、または削除済みアイテムの保存期間が終了した後)、メッセージがパージされると、保留期間が経過するまで、メッセージが保持されます。保留期間が制限されている場合は、保留リストを削除または保持期間を変更するまで、アイテムは保持されます。
    
- **理由検索と削除のワークフローに分割されている別のセキュリティ&amp;コンプライアンス センターの役割のグループですか。**

    説明したように電子的証拠開示マネージャーの役割グループのメンバーであるか、メールボックスを検索するのには、コンプライアンス検索管理の役割を割り当てられる人があります。人にメッセージを削除するには、組織の管理役割グループのメンバーであるか、検索および削除の管理役割を割り当てるには。これにより、管理する組織内のメールボックスを検索することができ、メッセージを削除することができます。 
