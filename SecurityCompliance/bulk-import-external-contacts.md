---
title: 外部連絡先を Exchange Online に一括インポートする
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 管理者が Exchange Online PowerShell と CSV ファイルを使用して外部連絡先をグローバルアドレス一覧に一括インポートする方法について説明します。
ms.openlocfilehash: 08fe7666f03c7fe60555133292be9e27a9ffa413
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152209"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>外部連絡先を Exchange Online に一括インポートする

**この記事は、管理者を対象としています。連絡先を自分のメールボックスにインポートしようとしていますか?「 [Outlook に連絡先をインポートする」を](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)参照してください。**
   
会社は、Exchange Online の共有アドレス帳 (グローバルアドレス一覧とも呼ばれます) に含める必要のある、多数の既存のビジネス用連絡先を所有していますか。 外部の連絡先を、社内のユーザーと同様に、配布グループのメンバーとして追加しますか。 その場合は、Exchange Online の PowerShell と CSV (コンマ区切り値) ファイルを使用して、外部連絡先を Exchange Online に一括インポートすることができます。 次の3つの手順からなるプロセスがあります。
  
[手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[手順 2: PowerShell を使用して外部連絡先を作成する](#step-2-create-the-external-contacts-with-powershell) 

[手順 3: 外部連絡先のプロパティに情報を追加する](#step-3-add-information-to-the-properties-of-the-external-contacts)

連絡先をインポートするための手順を完了したら、次の追加のタスクを実行できます。
  
- [外部連絡先を追加する](#add-more-external-contacts)
  
- [共有アドレス帳から外部連絡先を非表示にする](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>手順 1: 外部連絡先に関する情報を含む CSV ファイルを作成する

最初の手順として、Exchange Online にインポートする各外部連絡先に関する情報を含む CSV ファイルを作成します。 
  
1. 次のテキストをメモ帳のテキストファイルにコピーして、ファイル名サフィックス .csv を使用して、そのファイルを CSV ファイルとしてデスクトップに保存します。たとえば、ExternalContacts。
    
    > [!TIP]
    > 言語に特殊文字 ( **å**、 **ä**、 **ö**など) が含まれている場合は、メモ帳でファイルを保存するときに、CSV ファイルを Utf-8 またはその他の Unicode エンコードで保存します。 
  
    ```
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park 
    ```

    CSV ファイルの最初の行、つまりヘッダー行には、Exchange Online にインポートするときに使用できる連絡先のプロパティが一覧表示されます。 各プロパティ名はコンマで区切ります。 ヘッダー行の下の各行は、1つの外部連絡先をインポートするためのプロパティ値を表します。 
    
    > [!NOTE]
    > このテキストには、サンプルデータが含まれています。これは削除できます。 ただし、最初の (ヘッダー) 行を削除または変更しないでください。 これには、外部連絡先のすべてのプロパティが含まれています。 
  
2. Csv ファイルを編集するには、Excel を使用する方が簡単なため、Microsoft Excel で CSV ファイルを開いて編集してください。
    
3. Exchange Online にインポートする連絡先ごとに行を作成します。 可能な限り多くのセルにデータを設定します。 この情報は、連絡先ごとに共有アドレス帳に表示されます。 
    
    > [!IMPORTANT]
    >  外部連絡先を作成するには、次のプロパティ (見出し行の最初の4つの項目) が必要です。 **ExternalEmailAddress**、 **Name**、 **FIRSTNAME**、 **LastName**という CSV ファイルに設定する必要があります。 手順2で実行した PowerShell コマンドは、これらのプロパティの値を使用して連絡先を作成します。 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>手順 2: PowerShell を使用して外部連絡先を作成する

次の手順では、手順1および PowerShell で作成した CSV ファイルを使用して、CSV ファイルに記載されている外部連絡先を Exchange Online に一括インポートします。 
  
1.  PowerShell を Exchange Online 組織に接続します。 詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。 Exchange Online の PowerShell に接続するときは、必ず Office 365 のグローバル管理者アカウントのユーザー名とパスワードを使用してください。 
    
2. PowerShell を Exchange Online に接続したら、手順1で CSV ファイルを保存したデスクトップフォルダーに移動します。例`C:\Users\Administrator\desktop`を示します。
    
3. 外部連絡先を作成するには、次のコマンドを実行します。

    ```
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    インポートしているユーザーの数によっては、新しい連絡先を作成するのに時間がかかる場合があります。 コマンドの実行が終了すると、作成された新しい連絡先の一覧が PowerShell に表示されます。 
    
4. 新しい外部連絡先を表示するには、Exchange 管理センター (EAC) に移動し、[**受信者** \>の**連絡先**] をクリックします。 
    
    > [!TIP]
    > EAC への接続手順については、「exchange [Online の exchange 管理センター](https://go.microsoft.com/fwlink/p/?LinkId=328197)」を参照してください。 
  
5. 必要に応じて**** ![、[最新](media/O365-MDM-Policy-RefreshIcon.gif)の情報に更新] アイコンをクリックしてリストを更新し、インポートされた外部連絡先を表示します。 
    
    インポートされた連絡先は、Outlook および web 上の Outlook の共有アドレス帳に表示されます。
    
    > [!NOTE]
    > [**ユーザー** \>の**連絡先**] にアクセスして、Microsoft 365 管理センターで連絡先を表示することもできます。 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>手順 3: 外部連絡先のプロパティに情報を追加する

手順2でコマンドを実行した後、外部連絡先は作成されますが、CSV ファイルの大部分のセルからの情報である連絡先または組織の情報は含まれません。 これは、新しい外部連絡先を作成したときに、必要なプロパティだけが設定されるためです。 CSV ファイルに情報が入力されていない場合は、心配しないでください。 含まれていない場合は追加されません。
  
1.  PowerShell を Exchange Online 組織に接続します。 詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。
    
2. 手順1で CSV ファイルを保存したデスクトップフォルダーに移動します。例`C:\Users\Administrator\desktop`を示します。
    
3. 次の2つのコマンドを実行して、CSV ファイルの他のプロパティを手順2で作成した外部連絡先に追加します。
    
    ```
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > _Manager_パラメーターに問題がある可能性があります。 CSV ファイル内のセルが空白の場合は、エラーが発生し、プロパティ情報が連絡先に追加されません。 マネージャーを指定する必要がない場合は、前の` -Manager $_.Manager ` PowerShell コマンドからのみ削除してください。 
  
    手順1でインポートした回数に応じて、連絡先を更新するのに時間がかかる場合があります。 
    
4. プロパティが連絡先に追加されたことを確認するには、次のようにします。 
    
1. EAC で、[**受信者** \>の**連絡先**] に移動します。
    
2. 連絡先をクリックし、[ **** ![編集] 編集](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)アイコンをクリックして、連絡先のプロパティを表示します。 
    
するだけです。 ユーザーは、アドレス帳 Outlook および Outlook on the web の連絡先とその他の情報を表示できます。
  
## <a name="add-more-external-contacts"></a>外部連絡先を追加する

手順1から手順3を繰り返して、Exchange Online に新しい外部連絡先を追加することができます。 会社内のユーザーは、新しい連絡先の CSV ファイルに新しい行を追加するだけで済みます。 その後、手順2と手順3の PowerShell コマンドを実行して、新しい連絡先に情報を作成して追加することができます。
  
> [!NOTE]
> 新しい連絡先を作成するコマンドを実行すると、以前に作成した連絡先が既に存在するというエラーが表示されることがあります。 ただし、CSV ファイルに追加された新しい連絡先は作成されます。 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>共有アドレスから外部連絡先を非表示にする book>

一部の企業では、配布グループのメンバーとして追加できるように外部連絡先のみを使用する場合があります。 このシナリオでは、共有アドレス帳から外部連絡先を非表示にすることができます。 次の操作を実行してください。
  
1.  PowerShell を Exchange Online 組織に接続します。 詳細な手順については、「 [Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?LinkId=396554)」を参照してください。
    
2. 単一の外部連絡先を非表示にするには、次のコマンドを実行します。
    
    ```
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```
 
    たとえば、共有アドレス帳から Pilar Pinilla を非表示にするには、次のコマンドを実行します。

    ```
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```
   
3. 共有アドレス帳からすべての外部連絡先を非表示にするには、次のコマンドを実行します。

    ```
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

非表示にした後も、外部の連絡先は共有アドレス帳に表示されませんが、配布グループのメンバーとして追加できます。
