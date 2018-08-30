---
title: Exchange Online に一括インポートの外部の連絡先
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: End User
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 管理者は、Exchange のオンライン PowerShell を使用でき、一括して CSV ファイルは、グローバル アドレス一覧に外部の連絡先をインポートする方法について説明します。
ms.openlocfilehash: 4bde56d49ccf94dc91993df90e1ae693e25c961a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531637"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>Exchange Online に一括インポートの外部の連絡先

**この資料では、管理者用です。連絡先を自分のメールボックスにインポートしようとしていますか。[Outlook に連絡先をインポート](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)を参照してください。**
   
会社は Exchange Online で共有のアドレス帳 (グローバル アドレス一覧とも呼ばれます) に追加する既存のビジネス用連絡先の多くをあるか。場合と同様のユーザーと、社内の配布グループのメンバーとして外部の連絡先を追加しますか。Exchange オンライン PowerShell と一括して CSV (コンマ区切り値) ファイルを使用するため場合、は、Exchange Online に外部の連絡先をインポートします。3 つの手順です。
  
[手順 1: 外部の連絡先に関する情報を含む CSV ファイルを作成します。](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[手順 2: PowerShell での外部の連絡先を作成します。](#step-2-create-the-external-contacts-with-powershell) 

[手順 3: 外部の連絡先のプロパティに情報を追加します。](#step-3-add-information-to-the-properties-of-the-external-contacts)

連絡先をインポートするのには次の手順を完了したら、これらの追加タスクを実行できます。
  
- [その他の外部の連絡先を追加します。](bulk-import-external-contacts.md#AddMore)
  
- [共有のアドレス帳からの外部の連絡先を非表示にします。](bulk-import-external-contacts.md#Hide)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>手順 1: 外部の連絡先に関する情報を含む CSV ファイルを作成します。

最初のステップでは、オンラインの Exchange にインポートする各外部連絡先に関する情報を含む CSV ファイルを作成します。 
  
1. メモ帳でテキスト ファイルに次のテキストをコピーし、デスクトップに保存して、CSV ファイルとして .csv のファイル名のサフィックスを使用して、たとえば、ExternalContacts.csv です。
    
    > [!TIP]
    > 場合は、言語には、UTF-8、またはその他のエンコード方法はメモ帳でファイルを保存するときに CSV ファイルを保存 ( **å** **ä**、およびスウェーデン語の**ö** ) などの特殊文字が含まれています。 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    最初の行、または CSV ファイルのヘッダー行は、オンラインの Exchange にインポートするときに使用できる連絡先のプロパティを一覧表示します。各プロパティ名は、コンマで区切られます。ヘッダー行の下の各行は、1 つの外部連絡先をインポートするためのプロパティの値を表します。 
    
    > [!NOTE]
    > このテキストには、サンプル データ削除することにはが含まれています。削除したり、(ヘッダー) の最初の行を変更しないでください。すべての外部の連絡先のプロパティが含まれています。 
  
2. CSV ファイルを編集するのには Excel を使用する方が簡単であるために、CSV ファイルを編集するのには Microsoft Excel で CSV ファイルを開きます。
    
3. オンラインの Exchange にインポートする連絡先ごとに行を作成します。多くの可能なセルとして設定します。この情報は、各連絡先の共有アドレス帳に表示されます。 
    
    > [!IMPORTANT]
    >  (見出し行の最初の 4 つの項目は、) 次のプロパティは、外部の連絡先を作成する必要があり、CSV ファイルに入力する必要があります: **ExternalEmailAddress**、**名**、**姓**、**姓**です。手順 2 で実行するための PowerShell コマンドは、連絡先を作成するのにこれらのプロパティの値を使用します。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>手順 2: PowerShell での外部の連絡先を作成します。

次の手順は、手順 1 で作成した CSV ファイルを使用して、一括に PowerShell が Exchange Online を CSV ファイルに記載されている外部の連絡先をインポートします。 
  
1.  PowerShell は、オンラインの Exchange 組織に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。オンライン PowerShell を Exchange に接続するときに、Office 365 のグローバル管理者アカウントのユーザー名とパスワードを使用することを確認します。 
    
2. PowerShell を Exchange Online に接続した後は、手順 1 で保存した CSV ファイルのデスクトップ フォルダーに移動します。たとえば`C:\Users\Administrator\desktop`。
    
3. 外部の連絡先を作成するのには、次のコマンドを実行します。

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    インポートする多くの方法によって、新しい連絡先を作成するのにはしばらく時間がかかる場合があります。コマンドが完了するとこれを実行すると、PowerShell が表示されます作成された新しい連絡先の一覧です。 
    
4. 新しい外部の連絡先を表示するには、Exchange 管理センター (EAC) に移動し、**受信者**をクリックし、 \> **の連絡先**です。 
    
    > [!TIP]
    > EAC に接続する方法の詳細については、 [Exchange 管理センター オンラインの Exchange](https://go.microsoft.com/fwlink/p/?LinkId=328197)を参照してください。 
  
5. **更新**] をクリックして、必要に応じて![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif)リストを更新し、インポートされた外部の連絡先を参照してください。 
    
    インポートされた連絡先は、Outlook と Outlook web 上で共有のアドレス帳に表示されます。
    
    > [!NOTE]
    > **ユーザー**に Office 365 の管理ページで、連絡先を表示することも\>**連絡先**です。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>手順 3: 外部の連絡先のプロパティに情報を追加します。

手順 2 でコマンドを実行した後、外部の連絡先が作成されるが、CSV ファイル内のセルのほとんどの情報は、取引先担当者や組織情報が含まれています。必要なプロパティのみを設定する新しい外部の連絡先を作成する場合があるためにです。気にしないですべての情報を CSV ファイルに入力する必要はありません。存在しない、する場合は追加されません。
  
1.  PowerShell は、オンラインの Exchange 組織に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。
    
2. CSV ファイルを手順 1 で保存したデスクトップのフォルダーに移動します。たとえば`C:\Users\Administrator\desktop`。
    
3. 手順 2 で作成した外部の連絡先を CSV ファイルから他のプロパティを追加するのには次の 2 つのコマンドを実行します。
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _マネージャー_のパラメーターは、問題が発生する可能性があります。CSV ファイル内のセルが空白の場合は、エラー メッセージが表示され、プロパティ情報は、連絡先に追加されます。マネージャーを指定する必要はありません場合、だけを削除して` -Manager $_.Manager `以前の PowerShell コマンドからです。 
  
    もう一度、手順 1 でインポートした数に応じて、連絡先を更新するのにはしばらくかかる場合があります。 
    
4. プロパティは、連絡先に追加されたことを確認するには。 
    
1. **受信者**には、EAC で\>**の連絡先**です。
    
2. [連絡先] をクリックし、[**編集**] をクリックして![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)連絡先のプロパティを表示します。 
    
それです！ユーザーは、連絡先と Outlook のアドレス帳に追加の情報および web 上で Outlook に表示されます。
  
## <a name="add-more-external-contacts"></a>その他の外部の連絡先を追加します。

オンライン Exchange で新しい外部の連絡先を追加するのには手順 3 から手順 1 を繰り返します。や社内のユーザーでは、新しい連絡先を CSV ファイルに新しい行を追加できるだけです。作成し、新しい連絡先に情報を追加するには、手順 2 と手順 3 の PowerShell コマンドを実行することができます。
  
> [!NOTE]
> 新しい連絡先を作成するコマンドを実行するときは、既に以前のバージョンで作成された連絡先が存在していることを示すエラーが出るでしょう。ですが、CSV ファイルに追加された新しい連絡先を作成します。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>共有のアドレス帳からの外部の連絡先を非表示にする >

一部の企業は、配布グループのメンバーとして追加できるようにだけ、外部の連絡先を使用できます。このシナリオでは、共有アドレス帳からの外部の連絡先を非表示にする場合があります。ここではどのようにします。
  
1.  PowerShell は、オンラインの Exchange 組織に接続します。手順については、 [Exchange オンライン PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)を参照してください。
    
2. 1 つの外部連絡先を非表示にするには、次のコマンドを実行します。
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    たとえば、Pilar Pinilla 共有アドレス帳から非表示にするには、このコマンドを実行します。

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. 共有のアドレス帳からのすべての外部の連絡先を非表示にするには、このコマンドを実行します。

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

非表示にする、外部の連絡先は、共有アドレス帳に表示されていないが、配布グループのメンバーとして追加することができます。
