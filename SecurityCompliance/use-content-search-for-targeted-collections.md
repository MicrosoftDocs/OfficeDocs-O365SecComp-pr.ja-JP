---
title: Office 365 でのコンテンツの検索を使用して、コレクションの対象となります。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: コンテンツの検索を使用して、Office 365 のセキュリティで&amp;コンプライアンス センターを対象となるコレクションを実行します。対象となるコレクションでは、サポート案件への応答のアイテム、または特権を持つアイテムが特定のメールボックスまたはサイトのフォルダー内にあることを確信していることを意味します。この資料のスクリプトを使用すると、フォルダーの ID を検索する特定のメールボックスまたはサイト フォルダーのパスを取得します。
ms.openlocfilehash: 094fa4de4b8de9782a9bafb2eb8fb6ef3c52b46b
ms.sourcegitcommit: 06ae71741875f604bcc7a4e01b0b62cc768cbe97
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/13/2018
ms.locfileid: "27245064"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Office 365 でのコンテンツの検索を使用して、コレクションの対象となります。

コンテンツの検索機能は、Office 365 のセキュリティ&amp;コンプライアンス センターは、ビジネス サイトの Exchange メールボックスまたは SharePoint と OneDrive で特定のフォルダーを検索するのには、UI で直接的な方法を提供していません。ただし、実際の検索クエリの構文では、フォルダー ID またはパスを指定することによって特定のフォルダー (*コレクションをターゲットと*呼ばれます) を検索することができます。コンテンツの検索を使用して、対象のコレクションを実行すると、ケースへの応答のアイテム、または特権を持つアイテムが特定のメールボックスまたはサイトのフォルダー内にあることに間違いない場合に便利です。この資料のスクリプトを使用すると、メールボックス フォルダーのフォルダー ID またはビジネス サイトの SharePoint と OneDrive のフォルダーのパスを取得します。アイテムがフォルダーにあるを取得するのに検索クエリにフォルダー ID またはパスを使用できます。
  
## <a name="before-you-begin"></a>はじめに

- セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;ステップ 1 でスクリプトを実行するコンプライアンス センターです。詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。
    
    さらに、Exchange Online 組織内の差し込み印刷の宛先役割を割り当てる必要があります。これは、ステップ 1 でスクリプトに含まれる**Get MailboxFolderStatistics**コマンドレットを実行する必要です。既定では、メール受信者の役割が割り当てられている組織の管理と受信者の管理役割グループに Exchange オンライン。Exchange のオンラインでのアクセス許可の割り当ての詳細については、[管理役割グループのメンバー](https://go.microsoft.com/fwlink/p/?linkid=692102)を参照してください。カスタムの役割グループを作成し、メール受信者の役割を割り当てる、ステップ 1 でスクリプトを実行する必要があるメンバーを追加します。詳細については、[役割グループの管理](https://go.microsoft.com/fwlink/p/?linkid=730688)を参照してください。
    
- 手順 1 で、スクリプトを実行するたびに、新しいリモート PowerShell セッションが作成されます。などをすべてリモート PowerShell セッションを使用するを使用できます。これが発生しないようにするには、作業中のリモート PowerShell セッションを切断するのには次のコマンドを実行できます。
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
- スクリプトには、最低限のエラー処理が含まれています。スクリプトの主な目的は、すばやくメールボックス フォルダー Id の一覧を表示したり、サイトの対象となるコレクションを実行するコンテンツの検索の検索クエリの構文で使用できるパスには。
    
- このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>手順 1: スクリプトを実行するメールボックスまたはサイトのフォルダーの一覧を取得します。

最初の手順を実行するスクリプトは、メールボックスのフォルダーの一覧または SharePoint ビジネス フォルダーでは、OneDrive と対応するフォルダーの ID または各フォルダーへのパスに戻ります。このスクリプトを実行する場合を次の情報を求めます。
  
- **アドレスまたはサイトの URL を電子メールで送信**Exchange のメールボックスのフォルダーとフォルダー Id のリストを取得するのには管理者の電子メール アドレスを入力します。または指定したサイトのパスの一覧を取得するには、SharePoint サイトの URL またはビジネス サイトの OneDrive を入力します。いくつかの例を以下に示します。 
    
  - **Exchange** - stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **ビジネスの OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **ユーザーの資格情報**でスクリプトは Exchange Online とセキュリティへの接続に資格情報を使用&amp;リモート PowerShell でコンプライアンス センターです。説明したようには、正常にこのスクリプトを実行する適切なアクセス許可を割り当てる必要があります。
    
メールボックス フォルダーの一覧を表示またはサイトのパス名。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `GetFolderSearchParameters.ps1`。
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security &amp; Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the folder paths for the site. #
  #    * In both cases, the script supplies the correct search properties (folderid: or path:)      #
  #      appended to the folder ID or path ID to use in a Content Search.               #
  # Notes:                                              #
  #    * For SharePoint and OneDrive for Business, the paths are searched recursively; this means the   #
  #      the current folder and all sub-folders are searched.                       #
  #    * For Exchange, only the specified folder will be searched; this means sub-folders in the folder #
  #      will not be searched.  To search sub-folders, you need to use the specify the folder ID for    #
  #      each sub-folder that you want to search.                               #
  #    * For Exchange, only folders in the user's primary mailbox will be returned by the script.       #
  #########################################################################################################
  # Collect the target email address or SharePoint Url
  $addressOrSite = Read-Host "Enter an email address or a URL for a SharePoint or OneDrive for Business site"
  # Authenticate with Exchange Online and the Security &amp; Compliance Center (Exchange Online Protection - EOP)
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  if ($addressOrSite.IndexOf("@") -ige 0)
  {
      # List the folder Ids for the target mailbox
      $emailAddress = $addressOrSite
      # Authenticate with Exchange Online
      if (!$ExoSession)
      {
          $ExoSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell-liveid/ -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $ExoSession -AllowClobber -DisableNameChecking
      }
      $folderQueries = @()
      $folderStatistics = Get-MailboxFolderStatistics $emailAddress
      foreach ($folderStatistic in $folderStatistics)
      {
          $folderId = $folderStatistic.FolderId;
          $folderPath = $folderStatistic.FolderPath;
          $encoding= [System.Text.Encoding]::GetEncoding("us-ascii")
          $nibbler= $encoding.GetBytes("0123456789ABCDEF");
          $folderIdBytes = [Convert]::FromBase64String($folderId);
          $indexIdBytes = New-Object byte[] 48;
          $indexIdIdx=0;
          $folderIdBytes | select -skip 23 -First 24 | %{$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -shr 4];$indexIdBytes[$indexIdIdx++]=$nibbler[$_ -band 0xF]}
          $folderQuery = "folderid:$($encoding.GetString($indexIdBytes))";
          $folderStat = New-Object PSObject
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderPath -Value $folderPath
          Add-Member -InputObject $folderStat -MemberType NoteProperty -Name FolderQuery -Value $folderQuery
          $folderQueries += $folderStat
      }
      Write-Host "-----Exchange Folders-----"
      $folderQueries |ft
  }
  elseif ($addressOrSite.IndexOf("http") -ige 0)
  {
      $searchName = "SPFoldersSearch"
      $searchActionName = "SPFoldersSearch_Preview"
      # List the folders for the SharePoint or OneDrive for Business Site
      $siteUrl = $addressOrSite
      # Authenticate with the Security &amp; Compliance Center
      if (!$SccSession)
      {
          $SccSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $credentials -Authentication Basic -AllowRedirection
          Import-PSSession $SccSession -AllowClobber -DisableNameChecking
      }
      # Clean-up, if the script was aborted, the search we created might not have been deleted.  Try to do so now.
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
      # Create a Content Search against the SharePoint Site or OneDrive for Business site and only search for folders; wait for the search to complete
      $complianceSearch = New-ComplianceSearch -Name $searchName -ContentMatchQuery "contenttype:folder" -SharePointLocation $siteUrl
      Start-ComplianceSearch $searchName
      do{
          Write-host "Waiting for search to complete..."
          Start-Sleep -s 5
          $complianceSearch = Get-ComplianceSearch $searchName
      }while ($complianceSearch.Status -ne 'Completed')
      if ($complianceSearch.Items -gt 0)
      {
          # Create a Compliance Search Action and wait for it to complete. The folders will be listed in the .Results parameter
          $complianceSearchAction = New-ComplianceSearchAction -SearchName $searchName -Preview
          do
          {
              Write-host "Waiting for search action to complete..."
              Start-Sleep -s 5
              $complianceSearchAction = Get-ComplianceSearchAction $searchActionName
          }while ($complianceSearchAction.Status -ne 'Completed')
          # Get the results and print out the folders
          $results = $complianceSearchAction.Results
          $matches = Select-String "Data Link:.+[,}]" -Input $results -AllMatches
          foreach ($match in $matches.Matches)
          {
              $rawUrl = $match.Value
              $rawUrl = $rawUrl -replace "Data Link: " -replace "," -replace "}"
              Write-Host "path:""$rawUrl"""
          }
      }
      else
      {
          Write-Host "No folders were found for $siteUrl"
      }
      Remove-ComplianceSearch $searchName -Confirm:$false -ErrorAction 'SilentlyContinue'
  }
  else
  {
      Write-Error "Couldn't recognize $addressOrSite as an email address or a site URL"
  }
  ```

2. ローカル コンピューターに Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。
    
3. スクリプトを実行します。例えば：
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. スクリプトによってユーザーの情報を入力します。
    
    スクリプトには、メールボックスのフォルダーまたは指定したユーザーのサイト フォルダーの一覧が表示されます。このウィンドウを開き、フォルダー ID またはパス名をコピーして手順 2 で検索クエリを貼り付けます。
    
    > [!TIP]
    > コンピューターの画面には、フォルダーの一覧を表示するのではなく、テキスト ファイルにスクリプトの出力を再指示できます。このファイルは、スクリプトが格納されているフォルダーに保存されます。たとえば、スクリプトのテキスト ファイルに出力をリダイレクトするのには手順 3 で次のコマンドを実行:`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`検索クエリで使用するファイルからフォルダー ID またはパスをコピーすることができますし、します。
  
### <a name="script-output-for-mailbox-folders"></a>メールボックス フォルダーのスクリプトの出力

メールボックス フォルダー Id がある場合、スクリプトはリモート PowerShell を使用して Exchange Online に接続**Get MailboxFolderStatisics**コマンドレットを実行し、指定したメールボックスからフォルダーの一覧が表示されます。メールボックス内のすべてのフォルダーには、スクリプトは、 **FolderPath**列と**FolderQuery**列にフォルダー ID で、フォルダーの名前を表示します。さらに、スクリプトはフォルダー ID に**フォルダー Id** (これは、メールボックスのプロパティの名前) のプレフィックスを追加します。**フォルダー id**のプロパティが検索可能なプロパティであるためを使用します`folderid:<folderid>`フォルダーを検索する手順 2 で検索クエリにします。 
  
ここでは、メールボックス フォルダーのスクリプトによって返される出力の例です。
  
![メールボックスのフォルダーとフォルダーのスクリプトによって返される Id の一覧の例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
ステップ 2 の例では、ユーザーの回復可能なアイテム] フォルダーで、[パージ] サブフォルダーを検索に使用するクエリを示します。
  
### <a name="script-output-for-site-folders"></a>サイト フォルダーのスクリプトの出力

スクリプトが接続セキュリティを保護する場合は、ビジネス サイトの SharePoint または OneDrive からのパスを取得している、 &amp; 、新しいコンテンツの検索フォルダーは、サイトを検索し、フォルダーの一覧が表示されますを作成するリモート PowerShell を使用してコンプライアンス センター指定したサイト内にあります。スクリプトは、各フォルダーの名前を表示し、フォルダーの URL に (つまり、サイトのプロパティの名前)**のパス**のプレフィックスを追加します。使用する**path**プロパティが検索可能なプロパティであるため、`path:<path>`フォルダーを検索する手順 2 で検索クエリにします。 
  
ここでは、サイト フォルダーのスクリプトによって返される出力の例です。
  
![スクリプトによって返されるサイトのフォルダーのパス名のリストの例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a>ステップ 2: 対象となるコレクションを実行するのにフォルダーの ID またはパスを使用します。

セキュリティに移動するの次のステップまたは特定のユーザーのパスのフォルダー Id の一覧を収集するスクリプトを実行すると後、&amp;コンプライアンス センターと、特定のフォルダーを検索するのには新しいコンテンツの検索を作成します。使用して、`folderid:<folderid>`または`path:<path>`、コンテンツの検索キーワード] ボックスで (または**新規 ComplianceSearch**コマンドレットを使用する場合は、 *ContentMatchQuery*パラメーターの値) に構成した検索クエリのプロパティです。組み合わせることができます、`folderid`または`path`その他のプロパティのパラメーターを検索するか、検索条件を定義します。のみを指定した場合、`folderid`または`path`クエリで、検索が返されるすべての項目を指定したフォルダー内にあります。 
  
> [!NOTE]
> 使用して、 `path` OneDrive の場所を検索するプロパティが検索結果に、.png、.tiff、または .wav ファイルなどのメディア ファイルを返しません。 
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. アカウントとステップ 1 でスクリプトを実行するために使用する資格情報を使用して Office 365 にサインインします。
    
3. セキュリティの左側のウィンドウで&amp;コンプライアンス センター] をクリックして**検索&amp;調査** \> **コンテンツの検索**、し、[**新規**] をクリックし、![追加アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)。
    
4. **[新規検索]** ページで、コンテンツ検索の名前を入力します。この名前は、組織内で固有である必要があります。 
    
5. **場所を指定して検索できるため**、次のいずれかの操作に基づいてメールボックスのフォルダーまたはサイトのフォルダーを検索しているかどうか。
    
    - **検索する特定のメールボックスを選択**をクリックし、手順 1 でスクリプトを実行するときに指定したのと同じメールボックスを追加します。 
    
      または
    
    - 検索し、手順 1 でスクリプトを実行したときに指定したサイトの URL を追加し、**検索する特定のサイトを選択してください**] をクリックします。 
    
6. [ **次へ**] をクリックします。
    
7. **何か探すようになりました**] ページで [キーワード] ボックスに貼り付け、`folderid:<folderid>`または`path:<path>`ステップ 1 でスクリプトによって返された値です。 
    
    ユーザーの回復可能なアイテム] フォルダー内のサブフォルダーに削除の項目の次のスクリーン ショットでは、クエリを検索するたとえば、(の値、`folderid`のステップ 1 のスクリーン ショットでパージ サブフォルダーのプロパティが表示されている)。
    
    ![フォルダー id または検索クエリの [キーワード] ボックスにパスをペーストします。](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. 対象となるコレクションの検索を開始する**検索**] をクリックします。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>コレクションの対象となる検索クエリの例

使用するいくつかの例をここでは、`folderid`と`path`で、対象のコレクションを実行する検索クエリのプロパティです。用のプレース ホルダーを使用することに注意してください`folderid:<folderid>`と`path:<path>`領域を節約します。 
  
- この例では、3 つの別のメールボックス フォルダーを検索します。ユーザーの回復可能なアイテム] フォルダー内の非表示のフォルダーを検索するのに同様のクエリ構文を使用する可能性があります。
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- この例では、完全一致のフレーズを含むアイテムのメールボックス フォルダーを検索します。
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- 次の使用例は、タイトルに「機密保持契約」の文字含むドキュメントをサイト フォルダーとサブフォルダー) を検索します。
    
  ```
  path:<path> AND filename:nda
  ```

- 次の使用例は、日付の範囲内にあるドキュメントが変更されたために、サイト フォルダーとすべてのサブフォルダー) を検索します。
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>詳細情報

この資料で対象となるコレクションを実行するスクリプトを使用する場合、次の点に注意してください。
  
- スクリプトは、結果から、任意のフォルダーを削除されません。いくつかのフォルダーが表示されるように、結果可能性があります検索できない (または 0 個のアイテムを返す) システムによって生成されたコンテンツが含まれているためです。
    
- このスクリプトは、ユーザーのプライマリ メールボックスのフォルダー情報だけを返します。ユーザーのアーカイブ メールボックス内のフォルダーに関する情報を返さない。
    
- フォルダーでは、指定したフォルダーのみを検索するとき (によって識別される、`folderid`プロパティ) が検索されます。サブフォルダーは検索されません。フォルダーにサブフォルダーを検索するには、検索するサブ フォルダーのフォルダー ID を使用する必要があります。 
    
- サイト フォルダー、フォルダーを検索するとき (によって識別される、`path`プロパティ) と、すべてのサブフォルダーが検索されます。 
    
- 前述したように、使うことはできません`path`.png、.tiff、.wav ファイルなどのメディア ファイルを検索するプロパティが OneDrive の場所に配置します。OneDrive フォルダー内のメディア ファイルを検索するには、別の[サイトのプロパティ](keyword-queries-and-search-conditions.md#searchable-site-properties)を使用します。 

- 場合のみが指定されている検索結果をエクスポートするとき、 `folderid` 、検索クエリのプロパティを選択できます最初のエクスポートのオプション」を認識できない形式を持つものを除く、すべてのアイテムは暗号化されているまたは他の理由によりインデックスが作成されませんでした」。フォルダー ID は常にインデックスを作成するため、フォルダー内のすべてのアイテムは常に、インデックス作成の状態に関係なくエクスポートされます。
