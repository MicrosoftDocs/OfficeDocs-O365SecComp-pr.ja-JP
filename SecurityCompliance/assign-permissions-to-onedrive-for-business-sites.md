---
title: OneDrive for Business サイトに対する電子情報開示のアクセス許可を割り当てる
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: SharePoint Online の電子情報開示センターを使用するには、特定のキーワード、機密情報、およびその他の検索条件を組織内のビジネス サイトのすべての OneDrive を検索します。組織内の各ユーザーのそれぞれの OneDrive という名前のサイト コレクション内にある、ビジネス サイトの所有者ではhttps://domain-my.sharepoint.comです。既定では、Office 365 のグローバル管理者またはコンプライアンス マネージャーはビジネス サイトの任意の OneDrive を検索するのには SharePoint Online での電子情報開示センターを使用できません。検索するには、ビジネス サイトの管理者またはコンプライアンス担当マネージャー、OneDrive はビジネス サイトには、その OneDrive のサイト コレクションの管理者である必要があります。
ms.openlocfilehash: 61f068a03bcce599d9f1b7eb62d7b317b7feab68
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038090"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a>OneDrive for Business サイトに対する電子情報開示のアクセス許可を割り当てる

SharePoint Online の電子情報開示センターを使用するには、特定のキーワード、機密情報、およびその他の検索条件を組織内のビジネス サイトのすべての OneDrive を検索します。組織内の各ユーザーのそれぞれの OneDrive という名前のサイト コレクション内にある、ビジネス サイトの所有者ではhttps://domain-my.sharepoint.comです。既定では、Office 365 のグローバル管理者またはコンプライアンス マネージャーはビジネス サイトの任意の OneDrive を検索するのには SharePoint Online での電子情報開示センターを使用できません。検索するには、ビジネス サイトの管理者またはコンプライアンス担当マネージャー、OneDrive はビジネス サイトには、その OneDrive のサイト コレクションの管理者である必要があります。 
  
この資料では、管理者やコンプライアンス管理者にビジネス サイトのすべての OneDrive のサイト コレクションの管理者、組織内の手順を説明します。 
  
ビジネス サイトのサイト コレクションの管理者として OneDrive からのユーザーを削除するのには手順 3 でスクリプトの修正を含む、この資料のスクリプトの使用に関するヒントの[詳細について](#more-information)はを参照してください。 
  
## <a name="before-you-begin"></a>はじめに

- SharePoint Online 管理シェルをインストールします。詳細については、「[SharePoint Online 管理シェル Windows PowerShell 環境を設定する](https://go.microsoft.com/fwlink/p/?LinkID=286318)」を参照してください。
    
- ユーザーに割り当てる、サイト コレクションの管理者として、組織内のビジネス ・ サイトの任意の OneDrive をするたびに手順 3 でスクリプトを実行します。 
    
    > [!IMPORTANT]
    > 管理者またはコンプライアンス ビジネス サイトがビジネス ドキュメント ライブラリのユーザーの OneDrive を開くし、所有者と同じタスクを実行する OneDrive のサイト コレクションの管理者であるマネージャーです。割り当てられているアクセス許可の電子的証拠開示 OneDrive、組織内のビジネス サイトのユーザーを監視し、コントロールが重要です。 
  
- この資料に記載されているサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a>手順 1: ビジネス サイトのすべての OneDrive の一覧を収集します。

最初のステップでは、組織のビジネス サイトのすべての OneDrive のリストを作成します。手順については、[組織内のすべての OneDrive 場所のリストの作成](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)を参照してください。この資料では、このスクリプトは、OneDrive のすべてのサイトの一覧を含むテキスト ファイルを作成します。手順 3 で実行するスクリプトは、この手順で作成したテキスト ファイルに記載されているビジネス サイトの各 OneDrive に、サイト コレクションの管理者として指定したユーザーを割り当てます。次のテキストには、このファイル内のサイトのリストを書式設定する方法の例が用意されています。必要に応じて、このファイルからサイトを削除できます。

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a>手順 2: SharePoint のオンライン管理シェルを組織に接続します。

1. ローカル コンピューターで、SharePoint Online 管理シェルを開き、次のコマンドを実行します。

    ```
    $credentials = Get-Credential
    ```

2. **[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、Office 365 グローバル管理者アカウントのユーザー名とパスワードを入力してから、 **[OK]** をクリックします。
    
3. 次のコマンドを実行して、シェルを SharePoint Online 組織に接続します。
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. SharePoint Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのサイトのリストを取得します。
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a>手順 3: ユーザーを OneDrive for Business サイトのサイト コレクション管理者として割り当てる

次の手順では、サイト コレクション管理者は、組織内のビジネス サイトのすべての OneDrive で指定されたユーザーを割り当てるスクリプトを実行します。このスクリプトは、手順 1 で作成したビジネス サイトの OneDrive のリストを使用します。前述したように、ビジネス サイトのサイト コレクションの管理者として OneDrive にユーザーを割り当てるには使用するたびにこのスクリプトを実行する必要です。
  
1. 次のテキストをテキスト ファイルに保存します。たとえば、OD4BAssignSCA.txt という名前のファイルに保存することができます。

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. スクリプト ファイルの先頭に次の変数を編集し、組織に固有の情報を使用します。次の例では、組織のドメイン名が contoso.onmicrosoft.com であると見なします。二重引用符で変数の値を囲むことを確認する ("")。
    
    - **$AdminURI** - これの URI を指定、SharePoint Online の管理サービス、たとえば、 `"https://contoso-admin.sharepoint.com"`。
    
    - **$AdminAccount**のグローバル管理者アカウントで指定 Office 365 組織では、たとえば、 `"admin@contoso.onmicrosoft.com"`。
    
    - **$eDiscoveryUser** - 管理者のユーザー アカウントを指定またはコンプライアンス マネージャーに割り当てられるサイト コレクション管理者は、組織内のビジネス サイトのすべての OneDrive の例では、 `"annb@contoso.onmicrosoft.com"`。
    
      > [!NOTE]
      > **$EDiscoveryUser**変数で指定されたユーザー アカウントを変更し、サイト コレクションの管理者として **$MySiteListFile**変数で指定されているビジネス サイトの OneDrive に別のユーザーを割り当てるには、スクリプトを再実行します。 
  
    - **$MySitePrefix**これは、組織の個人用サイトのドメインの URL を指定します。これは、たとえば、ビジネスのサイト、組織内のすべての OneDrive が含まれるドメイン`"https://contoso-my.sharepoint.com"`。
    
    - **$MySiteListFile**手順 1 で作成したテキスト ファイルの完全パスを指定します。たとえば、このファイルに、組織内のビジネス サイトの OneDrive の一覧が含まれています`'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`。単一引用符では、この変数の値を囲むようにしてください (' ')。手順 1 でテキスト ファイルを保存する場所を指定する必要があることに注意してください。
    
3. このテキスト ファイルを PowerShell スクリプト ファイルとして保存するために、ファイル名サフィックスを .ps1 に変更します。たとえば、ファイル OD4BAssignSCA.txt を OD4BAssignSCA.ps1 として保存します。
    
4. SharePoint Online 管理シェルで、前のステップで作成した PowerShell スクリプトの入ったフォルダーに移動して、スクリプトを実行します。たとえば、次のように入力します。
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    スクリプトで指定した管理者アカウントのパスワードを入力するように促されます。スクリプトは、メッセージでは、正常に動作している場合`"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` **$MySiteListFile**で指定された入力ファイルに記載されているビジネス サイトの各 OneDrive に表示されます。

## <a name="more-information"></a>詳細情報

- 手順 3 で実行したスクリプトは、 **$MySiteListFile**変数で指定されたファイルに記載されているビジネスのすべての OneDrive に、サイト コレクションの管理者として指定したユーザーを割り当てるには、**セット SPOUser**コマンドレットを使用します。、数千のユーザーに非常に大規模な組織がある場合は、電子的証拠開示のアクセス許可の割り当てを管理しやすくには以下の手順を検討します。 
    
  - ユーザーは、作業中の訴訟の対象となるサイトのみが含まれるようにビジネス サイトの OneDrive の一覧が含まれている手順 1 で作成したファイルを編集します。
    
  - 2,500 を超えるの OneDrive の 1 日のビジネス サイトにアクセス許可を割り当てます。たとえば、組織のビジネス サイトの 10,000 の OneDrive があるとします。すべてのサイトを収集するために手順 1 でリストを作成します。2,500 ユーザーがそれぞれ含まれている 4 つのファイルを作成するのにはそのファイルを使用する可能性があります。最初の日では、ビジネス サイトの最初の 2,500 の OneDrive にアクセス許可を割り当てるには、手順 3 でスクリプトを実行するとします。第 2 日目はビジネス サイトでは、次に 2,500 の OneDrive のスクリプトを実行したりします。
    
- 電子的証拠開示の権限と、サイト コレクションの管理者として割り当てられているユーザーに割り当てられたビジネス サイトの OneDrive の記録を保持します。などのアクセス許可を割り当てると後、は、ビジネス サイトの OneDrive の一覧を含むテキスト ファイルを保存し、行を追加するサイト コレクションの管理者として割り当てられているユーザーを識別します。
    
- ユーザーは、ビジネス サイトの OneDrive のサイト コレクション管理者は、自分のリストを表示できます。ユーザーは独自の OneDrive のビジネス サイトのサイト コレクションの管理者であるため、サイト コレクションの管理者を削除することができます。ビジネス サイトの OneDrive に電子的証拠開示のアクセス許可を割り当てられているユーザーを削除してしまう可能性を軽減するために以下の手順を検討してください。
    
  - 電子的証拠開示とコンプライアンスのために、法令遵守責任者割り当てられているサイト コレクションの管理者として OneDrive を組織内のビジネス サイトのユーザーに連絡します。
    
  - 再 OneDrive のビジネスのサイトのサイト コレクションの管理者として、ユーザーを再割り当てするのには、必要な場合は、手順 3 で、スクリプトを実行します。
    
- 手順 3 で実行したスクリプトを使用することも、サイト コレクションの管理者として、ビジネスのサイトの OneDrive からユーザーを削除します。ユーザーを削除するサイト コレクションの管理者としてからの (スクリプトの終了) の近くには、次のコマンドを変更する必要。 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    次のように変更します。
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    さらに、スクリプトの次の行を

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    次のように変更します。
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    これらの変更を実行した後は、OD4BRemoveSCA.ps1 などの別の名前でスクリプトを保存しを使用して、サイト コレクションの管理者としてビジネス サイトの OneDrive のグループからユーザーを削除します。
