---
title: Office 365 で非アクティブなメールボックスを作成および管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
description: office 365 で非アクティブなメールボックスを作成するには、ホールドまたは office 365 アイテム保持ポリシーをメールボックスに適用してから、対応する office 365 ユーザーアカウントを削除します。 非アクティブなメールボックス内のアイテムは、非アクティブになる前に適用されていた保留またはアイテム保持ポリシーの期間中保持されます。 非アクティブなメールボックスを完全に削除するには、保持ポリシーまたはアイテム保持ポリシーを削除するだけです。
ms.openlocfilehash: ad874d2f21afaa86fa7fa5a18dc827dfa1b90574
ms.sourcegitcommit: 6c9340e4eb221bf81472ff3f1ae25ae21aaf5297
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/11/2019
ms.locfileid: "31813978"
---
# <a name="create-and-manage-inactive-mailboxes-in-office-365"></a>Office 365 で非アクティブなメールボックスを作成および管理する

Office 365 により、削除済みメールボックスの内容を保持することができます。 この機能は[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)と呼ばれます。 Inactive mailboxes allow you to retain former employees' email after they leave your organization. メールボックスは、対応する office 365 ユーザーアカウントが削除される前に、訴訟ホールドまたは office 365 アイテム保持ポリシー (office 365 または Microsoft 365 のセキュリティ/コンプライアンスセンターで作成されたもの) がメールボックスに適用されると、非アクティブになります。 The contents of an inactive mailbox are retained for the duration of the hold that was placed on the mailbox before it was made inactive. これにより、管理者、コンプライアンス責任者、およびレコード管理者は、コンテンツ検索を使用して、非アクティブなメールボックスのコンテンツを検索してエクスポートすることができます。 Inactive mailboxes can't receive email and aren't displayed in your organization's shared address book or other lists.
  
> [!NOTE]
> 2017 年 7 月 1 日に終了する予定だった、メールボックスを非アクティブにするために新しいインプレース ホールドを作成できる期間を延長しました。しかし、今年の終わりごろまたは来年の初めごろには、新しいインプレース ホールドを Exchange Online 内で作成することはできなくなります。その時点で、非アクティブのメールボックスを作成するために使用できるのは、訴訟ホールドと Office 365 アイテム保持ポリシーだけになります。ただし、インプレース ホールドにある既存の非アクティブなメールボックスは引き続きサポートされます。また、引き続き非アクティブなメールボックスのインプレース ホールドを管理することができます。これには、インプレース ホールドの期間を変更すること、およびそのインプレース ホールドを削除することによって非アクティブなメールボックスを完全に削除することが含まれます。 
  
## <a name="before-you-begin"></a>始める前に

- メールボックスを非アクティブにするには、メールボックスを削除する前に、訴訟ホールドまたは Office 365 のアイテム保持ポリシーをメールボックスに適用できるように、Exchange Online プラン2のライセンスを割り当てる必要があります。 Exchange Online プラン2のライセンスは、Office 365 Enterprise E3 および E5 サブスクリプションの一部です。 メールボックスに exchange online プラン1ライセンス (Office 365 Enterprise E1 サブスクリプションの一部) が割り当てられている場合は、削除する前にメールボックスに保留リストを適用できるように、メールボックスに別の exchange online アーカイブライセンスを割り当てる必要があります。 詳細については、「[Exchange Online Archiving](https://go.microsoft.com/fwlink/p/?LinkId=286153)」をご覧ください。
    
- 削除された Exchange Online メールボックスに関連付けられたライセンスは、対応する Office 365 ユーザー アカウントを削除した後に使用可能になります。 その後、 [Office 365 for business のユーザーにライセンス](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)を別のユーザーに割り当てることができます。 
    
- メールボックスを削除する前に訴訟ホールドまたは Office 365 アイテム保持ポリシーを適用しなかった場合は、メールボックスの内容が保持されず、検索もできません。なお、削除されたメールボックスは、削除後 30 日以内であれば回復できますが、回復されない場合、メールボックスとその内容は 30 日後に完全に削除されます。
    
- For more information about Litigation Hold, see [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). Office 365 アイテム保持ポリシーの詳細については、「[Office 365 のアイテム保持ポリシーの概要」](retention-policies.md)」を参照してください。
  
## <a name="create-an-inactive-mailbox"></a>非アクティブなメールボックスを作成する

メールボックスを非アクティブにするには、2つの手順を実行します。 1) メールボックスを訴訟ホールドの対象にするか、office 365 アイテム保持ポリシーを適用するか、2) メールボックスまたは対応する office 365 ユーザーアカウントを削除します。 メールボックスが非アクティブになると、そのコンテンツは保持ポリシーまたはアイテム保持ポリシーが削除されるまで保持されます。
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-an-office-365-retention-policy"></a>手順 1:メールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用する

メールボックスを訴訟ホールドの対象にするか、Office 365 アイテム保持ポリシーを適用すると、メールボックスが削除される前に、その中のすべての内容が保持されます。どちらの種類の保持も、削除済みアイテムや変更されたアイテムの元のバージョンなど、すべてのメールボックスのコンテンツを保持します。削除または変更されたアイテムは、指定された期間、または非アクティブなメールボックスに適用されているホールドまたは保持ポリシーを除去することによって完全に非アクティブなメールボックスを削除するまで、非アクティブなメールボックスに保持されます。
  
メールボックスが既にホールドの対象になっている場合や、Office 365 アイテム保持ポリシーがメールボックスに既に適用されている場合に行う必要があるのは、手順 2 で説明されているように、対応する Office 365 ユーザー アカウントを削除することだけです。
  
メールボックスを訴訟ホールドの対象にするため、または Office 365 アイテム保持ポリシーを適用するためのステップごとの手順については、以下を参照してください。
  
- [メールボックスを訴訟ホールドの対象にする](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [アイテム保持ポリシーの概要](retention-policies.md)
    
> [!NOTE]
> 訴訟ホールドと Office 365 アイテム保持ポリシーでは、無期限のホールドまたは時間ベースのホールドを作成できます。無期限のホールドでは、非アクティブなメールボックスの内容が永久に保持されるか、またはそのホールドが除去されるかホールド期間が変更されるまで保持されます。ホールドまたはアイテム保持ポリシーを解除すると、非アクティブなメールボックスは完全な削除対象としてマークされ、メールボックスの内容は保持されなくなり、検索もできなくなります (メールボックスは 30 日より前に削除されていることを前提とします)。時間ベースのホールドまたは Office 365 アイテム保持ポリシーでは、ホールド期間を指定します。この期間は、アイテム ベースで、メールボックス アイテムが受信または作成された日から計算されます。メールボックス アイテムのホールド期間が切れると、そのアイテムが非アクティブなメールボックスの [回復可能なアイテム] フォルダーにあるかそこに移動された場合、そのアイテムは削除済みアイテム保持期間が切れた後に非アクティブなメールボックスから完全に削除されます。 
  
### <a name="step-2-delete-the-mailbox"></a>手順 2:メールボックスを削除する

メールボックスをホールドの対象にするか、Office 365 アイテム保持ポリシーをそれに適用したら、次の手順としてそのメールボックスを削除します。 メールボックスを削除する最善の方法は、Microsoft 365 管理センターで対応する Office 365 ユーザーアカウントを削除することです。 Office 365 ユーザーアカウントの削除の詳細については、「[組織からユーザーを削除する](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e)」を参照してください。
  
> [!NOTE]
> Exchange Online PowerShell で **Remove-Mailbox** コマンドレットを使用してメールボックスを削除することもできます。 詳細については、「 [Exchange Online でユーザーメールボックスを削除または復元](https://go.microsoft.com/fwlink/?linkid=856287)する」を参照してください。 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>非アクティブなメールボックスの一覧を表示する

組織内の非アクティブなメールボックスの一覧を表示するには、次のようにします。
  
1. に[https://protection.office.com](https://protection.office.com)移動し、Office 365 組織の管理者アカウントの資格情報を使用してサインインします。 
    
2. [**データガバナンス** > の**保持**] をクリックします。
    
3. [**保持**] ページで、[**その他**![の](media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)ナビゲーションバーの省略記号] をクリックし、[**非アクティブなメールボックス**] をクリックします。
    
    ![[保持] ページで、[詳細]、[非アクティブなメールボックス] の順にクリックして、非アクティブなメールボックスの一覧を表示します。](media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    [**非アクティブなメールボックス**] ページが表示されます。 注: 組織内の非アクティブなメールボックスの合計数が表示されます。 
    
    ![組織内のすべての非アクティブなメールボックスの一覧が表示されます。](media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
または、Exchange Online PowerShell で次のコマンドを実行して、非アクティブなメールボックスの一覧を表示することもできます。

```
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

[検索結果![のエクスポート] アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **エクスポート**をクリックして、組織内の非アクティブなメールボックスに関する追加情報を含む CSV ファイルを表示またはダウンロードできます。 
  
また、次のコマンドを実行して、非アクティブなメールボックスとその他の情報の一覧を CSV ファイルにエクスポートすることもできます。 この例では、CSV ファイルが現在のディレクトリに作成されます。

```
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```
   
> [!NOTE]
> 非アクティブなメールボックスは、アクティブなユーザーメールボックスと同じ SMTP アドレスを持つことができます。 この場合は、 **DistinguishedName**または**exchangeguid**プロパティの値を使用して、非アクティブなメールボックスを一意に識別することができます。 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>非アクティブなメールボックスのコンテンツを検索し、エクスポートする

セキュリティ & コンプライアンスセンターのコンテンツ検索ツールを使用して、非アクティブなメールボックスのコンテンツにアクセスできます。 When you search an inactive mailbox, you can create a keyword search query to search for specific items or you can return the entire contents of the inactive mailbox. You can preview the search results or export the search results to an Outlook Data (PST) file or as individual email messages. For step-by-step procedures for searching mailboxes and exporting search results, see the following topics:
  
- [Office 365 のコンテンツ検索](content-search.md)
    
- [コンテンツ検索の結果をエクスポートする](export-search-results.md)
    
次に示しているのは、非アクティブなメールボックスを検索するときの留意点です。
  
- コンテンツ検索にユーザー メールボックスを含めた後に、そのメールボックスが非アクティブになった場合、非アクティブになってから検索を再実行すると、コンテンツ検索は非アクティブなメールボックスの検索を続行します。
    
- 場合によっては、ユーザーは同じ SMTP アドレスを持つアクティブなメールボックスおよび非アクティブなメールボックスを所有している可能性があります。この場合、コンテンツ検索の場所として選択した特定のメールボックスのみが検索されます。つまり、検索にユーザーのメールボックスを追加する場合に、アクティブなメールボックスと非アクティブなメールボックスの両方が検索されることは想定できません。検索に明示的に追加したメールボックスのみが検索されます。
    
- 同じ SMTP アドレスを持つアクティブなメールボックスと非アクティブなメールボックスを使用しないことを強くお勧めします。 非アクティブなメールボックスに現在割り当てられている SMTP アドレスを再利用する必要がある場合は、非アクティブなメールボックスを回復するか、非アクティブなメールボックスのコンテンツをアクティブなメールボックス (またはアクティブなメールボックスのアーカイブ) に復元することをお勧めします。非アクティブなメールボックス。
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>非アクティブなメールボックスの保持期間を変更する

メールボックスが非アクティブになった後は、非アクティブなメールボックスに適用されているホールドまたは Office 365 アイテム保持ポリシーの期間を変更できます。 詳細な手順については、「 [Office 365 の非アクティブなメールボックスの保持期間を変更](change-the-hold-duration-for-an-inactive-mailbox.md)する」を参照してください。
  
## <a name="recover-an-inactive-mailbox"></a>非アクティブなメールボックスを回復する

元従業員が組織に復帰する場合、または新しい従業員が退職した従業員の職責を引き継ぐ場合には、非アクティブなメールボックスのコンテンツを回復できます。 非アクティブなメールボックスを回復すると、そのメールボックスは新しいメールボックスに変換され、非アクティブなメールボックスのコンテンツとフォルダー構造が保持されて、メールボックスが新しいユーザー アカウントにリンクされます。 回復された後、非アクティブなメールボックスは存在しなくなります。 ステップごとの手順、および非アクティブなメールボックスを回復するときの処理に関する詳細については、「 [Office 365 の非アクティブなメールボックスを回復](recover-an-inactive-mailbox.md)する」を参照してください。
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>非アクティブなメールボックスのコンテンツを別のメールボックスに復元する

別の従業員が元従業員の職責を引き継ぐ場合、または別のユーザーが非アクティブなメールボックスのコンテンツにアクセスする必要がある場合は、非アクティブなメールボックスのコンテンツを既存のメールボックスに復元 (またはマージ) できます。 非アクティブなメールボックスを復元すると、そのコンテンツは別のメールボックスにコピーされます。 非アクティブなメールボックスは保持されて、非アクティブなメールボックスとして残ります。 非アクティブなメールボックスは、電子情報開示を使用して検索すること、そのコンテンツを別のメールボックスに復元すること、それを後に回復したり削除したりすることが引き続き可能です。 詳細な手順については、「 [Office 365 の非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)」を参照してください。
  
## <a name="delete-an-inactive-mailbox"></a>非アクティブなメールボックスを削除する

非アクティブなメールボックスの内容を保持する必要がなくなった場合、ホールドを解除することにより、または非アクティブなメールボックスに適用された Office 365 アイテム保持ポリシーを除去することにより、非アクティブなメールボックスを完全に削除できます。 メールボックスを削除してから 30 日が経過すると、そのメールボックスは保持の解除後に完全な削除対象としてマークされ、メールボックスが回復不能になります。 メールボックスを過去 30 日以内に削除した場合、ホールドまたはアイテム保持ポリシーを削除した後もメールボックスを回復することができます。 非アクティブなメールボックスを完全に削除するための、ホールドまたは Office 365 のアイテム保持ポリシーを削除するための詳細な手順については、「 [Office の非アクティブなメールボックスを削除する 365](delete-an-inactive-mailbox.md)」を参照してください。