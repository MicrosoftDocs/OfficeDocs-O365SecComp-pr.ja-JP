---
title: Office 365 のコンテンツ検索を使用した対象コレクション
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: セキュリティ & コンプライアンスセンターでコンテンツ検索を使用して、対象となるコレクションを実行します。 対象となるコレクションは、ケースまたは権限アイテムに応答するアイテムが特定のメールボックスまたはサイトフォルダーにあることを確信していることを意味しています。 この記事に記載されているスクリプトを使用して、検索する特定のメールボックスまたはサイトフォルダーのフォルダー ID またはパスを取得します。
ms.openlocfilehash: 3d9a82926a08b3f7f1f245146e70d79617e7a413
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264020"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a>Office 365 のコンテンツ検索を使用した対象コレクション

Office 365 セキュリティ&amp;コンプライアンスセンターのコンテンツ検索機能では、Exchange メールボックスまたは SharePoint および OneDrive for business サイトの特定のフォルダーを検索するための直接 UI を使用することはできません。 ただし、実際の検索クエリ構文で、サイトの email または path (documentlink) プロパティを指定して、特定のフォルダー (*対象のコレクション*と呼ばれる) を検索することができます。 コンテンツ検索を使用して対象のコレクションを実行することは、特定のメールボックスまたはサイトフォルダーに、訴訟や権限のあるアイテムに応答するアイテムがあることを確信する場合に役立ちます。 この記事に記載されているスクリプトを使用して、SharePoint および OneDrive for business サイト上のフォルダーのメールボックスフォルダーのフォルダー ID またはパス (documentlink) を取得することができます。 その後、検索クエリでフォルダー ID またはパスを使用して、フォルダー内にあるアイテムを返すことができます。

> [!NOTE]
> SharePoint または OneDrive for business サイト内のフォルダーにあるコンテンツを返すには、このトピックのスクリプトで Path プロパティの代わりに documentlink 管理プロパティを使用します。 documentlink プロパティは、フォルダー内のすべてのコンテンツを返すので、path プロパティよりも堅牢ですが、path プロパティはいくつかのメディアファイルを返すわけではありません。

## <a name="before-you-begin"></a>始める前に

- 手順1でスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。
    
    さらに、Exchange Online 組織内のメール受信者の役割を割り当てる必要があります。 これは、手順1でスクリプトに含まれている**get-mailboxfolderstatistics**コマンドレットを実行するために必要です。 既定では、メール受信者の役割は、Exchange Online の [組織の管理] および [受信者の管理] 役割グループに割り当てられます。 Exchange Online でのアクセス許可の割り当ての詳細については、「[役割グループのメンバーの管理](https://go.microsoft.com/fwlink/p/?linkid=692102)」を参照してください。 また、カスタム役割グループを作成し、メール受信者の役割を割り当ててから、手順1でスクリプトを実行する必要があるメンバーを追加することもできます。 詳細については、「[役割グループの管理](https://go.microsoft.com/fwlink/p/?linkid=730688)」を参照してください。
    
- 手順1でスクリプトを実行するたびに、新しいリモート PowerShell セッションが作成されます。 そのため、使用可能なすべてのリモート PowerShell セッションを使用できます。 この問題が発生しないようにするには、次のコマンドを実行して、アクティブなリモート PowerShell セッションを切断します。
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。
    
- スクリプトには、最小限のエラー処理が含まれています。 このスクリプトの主な目的は、コンテンツ検索の検索クエリ構文で対象のコレクションを実行するために使用できるメールボックスフォルダー id またはサイトパスの一覧をすばやく表示することです。
    
- このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。 このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。 Microsoft は、商品性の保証および特定目的への適合性の保証を含むいかなる明示もしくは黙示の保証責任を負いません。 サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a>手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得する

この最初の手順で実行するスクリプトは、メールボックスフォルダーまたは SharePoint と OneDrive for business フォルダーの一覧と、各フォルダーの対応するフォルダー ID またはパスを返します。 このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。
  
- **電子メールアドレスまたはサイトの URL**Exchange メールボックスフォルダーとフォルダー id の一覧を返すには、保管担当者の電子メールアドレスを入力します。 または、指定したサイトのパスの一覧を返すには、SharePoint サイトまたは OneDrive for business サイトの URL を入力します。 次に例を示します。 
    
  - **Exchange** -stacig@contoso.onmicrosoft.com 
    
  - **SharePoint** - https://contoso.sharepoint.com/sites/marketing 
    
  - **OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com 
    
- **ユーザーの資格情報**-スクリプトは、資格情報を使用して Exchange Online およびセキュリティ & コンプライアンスセンターとリモート PowerShell に接続します。 前述のように、このスクリプトを正常に実行するには、適切なアクセス許可を割り当てる必要があります。
    
メールボックスフォルダーまたはサイト documentlink (path) 名の一覧を表示するには、次のようにします。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `GetFolderSearchParameters.ps1`のようになります。
    
  ```
  #########################################################################################################
  # This PowerShell script will prompt you for:                             #
  #    * Admin credentials for a user who can run the Get-MailboxFolderStatistics cmdlet in Exchange    #
  #      Online and who is an eDiscovery Manager in the Security & Compliance Center.           #
  # The script will then:                                           #
  #    * If an email address is supplied: list the folders for the target mailbox.          #
  #    * If a SharePoint or OneDrive for Business site is supplied: list the documentlinks (folder paths) #
  #    * for the site.                                                                                  #
  #    * In both cases, the script supplies the correct search properties (folderid: or documentlink:)  #
  #      appended to the folder ID or documentlink to use in a Content Search.              #
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
  # Authenticate with Exchange Online and the Security & Compliance Center (Exchange Online Protection - EOP)
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
      # Authenticate with the Security & Compliance Center
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
              Write-Host "DocumentLink:""$rawUrl"""
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

2. ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。
    
3. スクリプトを実行します。例えば：
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. スクリプトによってプロンプトが表示される情報を入力します。
    
    スクリプトによって、指定したユーザーのメールボックスフォルダーまたはサイトフォルダーの一覧が表示されます。 フォルダー ID または documentlink の名前をコピーして、手順2で検索クエリに貼り付けることができるように、このウィンドウを開いておきます。
    
    > [!TIP]
    > コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキストファイルにリダイレクトすることができます。 このファイルは、スクリプトが配置されているフォルダーに保存されます。 たとえば、スクリプトの出力をテキストファイルにリダイレクトするには、手順3で次のコマンドを`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`実行します。次に、ファイルからフォルダー ID または documentlink をコピーして、検索クエリで使用できます。
  
### <a name="script-output-for-mailbox-folders"></a>メールボックスフォルダーのスクリプト出力

メールボックスフォルダー id を取得している場合、スクリプトはリモート PowerShell を使用して Exchange Online に接続し、 **MailboxFolderStatisics**コマンドレットを実行して、指定したメールボックスのフォルダーの一覧を表示します。 メールボックス内のすべてのフォルダーについて、スクリプトによって、 **FolderPath**列にフォルダーの名前と、フォルダー ID が**folderquery**列に表示されます。 また、スクリプトは**folderId** (メールボックスプロパティの名前) のプレフィックスをフォルダー ID に追加します。 **folderid**プロパティは検索可能なプロパティであるため、手順`folderid:<folderid>` 2 の検索クエリでそのフォルダーを検索するために使用します。 

> [!IMPORTANT]
> この記事のスクリプトには、 **get-mailboxfolderstatistics**によって返される64文字のフォルダー Id 値を、検索用にインデックス付けされたものと同じ48文字形式に変換するためのエンコードロジックが含まれています。 PowerShell で**get-mailboxfolderstatistics**コマンドレットを実行してフォルダー id を取得した場合 (この記事のスクリプトを実行するのではなく)、そのフォルダー id 値を使用する検索クエリは失敗します。 コンテンツ検索で使用できる正しい形式のフォルダー id を取得するには、スクリプトを実行する必要があります。
  
メールボックスフォルダーのスクリプトによって返される出力の例を次に示します。
  
![スクリプトによって返されるメールボックスフォルダーとフォルダー id のリストの例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
手順2の例は、ユーザーの [回復可能なアイテム] フォルダー内の [削除] サブフォルダーを検索するために使用されるクエリを示しています。
  
### <a name="script-output-for-site-folders"></a>サイトフォルダーのスクリプト出力

SharePoint または OneDrive for business サイトから**documentlink**プロパティのパスを取得している場合、スクリプトはリモート PowerShell を使用して Security & コンプライアンスセンターに接続し、サイトを検索する新しいコンテンツ検索を作成します。指定したサイトにあるフォルダーの一覧を表示します。 このスクリプトは、各フォルダーの名前を表示し、" **documentlink of ドキュメント**" というプレフィックスをフォルダーの URL に追加します。 **documentlink**プロパティは検索可能なプロパティであるため、手順`documentlink:<path>` 2 の検索クエリで [プロパティ: 値のペア] を使用して、そのフォルダーを検索します。 
  
サイトフォルダーのスクリプトによって返される出力の例を次に示します。
  
![スクリプトによって返されるサイトフォルダーのドキュメントリンク名のリストの例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-documentlink-to-perform-a-targeted-collection"></a>手順 2: フォルダー ID または documentlink を使用して対象のコレクションを実行する

特定のユーザーのフォルダー id または documentlinks の一覧を収集するスクリプトを実行した後、次の手順では、Security & コンプライアンスセンターに移動し、新しいコンテンツ検索を作成して特定のフォルダーを検索します。 コンテンツ検索キーワードボックス`folderid:<folderid>`で`documentlink:<path>`構成した検索クエリで、またはプロパティ: 値のペアを使用します (または、 **new-compliancesearch**コマンドレットを使用する場合は、 *contentmatchquery*パラメーターの値として指定します)。 `folderid`または`documentlink`プロパティを他の検索パラメーターまたは検索条件と組み合わせることができます。 `folderid`または`documentlink`プロパティのみをクエリに含める場合、検索では指定したフォルダーにあるすべてのアイテムが返されます。 
  
1. [https://protection.office.com](https://protection.office.com) に移動します。
    
2. 手順1でスクリプトの実行に使用したアカウントと資格情報を使用して、Office 365 にサインインします。
    
3. セキュリティ & コンプライアンスセンターの左側のウィンドウで、[**検索** \> **コンテンツの検索**] をクリックし、[**新規作成** ![] [追加] アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)をクリックします。
    
4. **[新規検索]** ページで、コンテンツ検索の名前を入力します。 この名前は、組織内で固有である必要があります。 
    
5. [検索する**場所**] で、次のいずれかの操作を行います。メールボックスフォルダーまたはサイトフォルダーのどちらを検索しているかによって決まります。
    
    - [**検索する特定のメールボックスを選択する**] をクリックし、手順1でスクリプトを実行したときに指定したものと同じメールボックスを追加します。 
    
      または
    
    - [検索する**特定のサイトを選択する**] をクリックし、手順1でスクリプトを実行したときに指定したものと同じサイト URL を追加します。 
    
6. **[次へ]** をクリックします。
    
7. [**検索する内容を選択**してください] ページの [キーワード] ボックスに、 `folderid:<folderid>`手順`documentlink:<path>` 1 でスクリプトによって返された値を貼り付けます。 
    
    たとえば、次のスクリーンショットのクエリは、ユーザーの回復可能なアイテムフォルダーのパージサブフォルダー内のアイテムを検索します (パージ`folderid`サブフォルダーのプロパティの値は、手順1のスクリーンショットに示されています)。
    
    ![検索クエリのキーワードボックスに folderid または documentlink を貼り付ける](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. [**検索**] をクリックして、対象となるコレクション検索を開始します。 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a>対象となるコレクションの検索クエリの例

ここでは、 `folderid`検索クエリで and `documentlink`プロパティを使用して対象となるコレクションを実行する例をいくつか示します。 プレースホルダーは、スペースを節約`folderid:<folderid>`する`documentlink:<path>`ために使用されることに注意してください。 
  
- この例では、3つの異なるメールボックスフォルダーを検索します。 同じようなクエリ構文を使用して、ユーザーの回復可能なアイテムフォルダー内の隠しフォルダーを検索することができます。
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- この例では、完全に一致する語句を含むアイテムをメールボックスフォルダーから検索します。
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- 次の使用例は、タイトルに "NDA" という文字が含まれるドキュメントのサイトフォルダー (およびすべてのサブフォルダー) を検索します。
    
  ```
  documentlink:<path> AND filename:nda
  ```

- この例では、日付の範囲内で変更されたドキュメントのサイトフォルダー (およびすべてのサブフォルダー) を検索します。
    
  ```
  documentlink:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a>詳細情報

この記事に記載されているスクリプトを使用して対象のコレクションを実行する場合は、次の点に注意してください。
  
- このスクリプトでは、結果からフォルダーは削除されません。 そのため、検索結果に表示される一部のフォルダーには、システムによって生成されるコンテンツが含まれているため、検索できない (または、0個のアイテムを返します) 場合が
    
- このスクリプトは、ユーザーのプライマリメールボックスのフォルダー情報のみを返します。 ユーザーのアーカイブメールボックス内のフォルダーに関する情報は返されません。
    
- メールボックスフォルダーを検索する場合、指定されたフォルダー `folderid` (そのプロパティで識別される) のみが検索されます。サブフォルダーは検索されません。 サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使用する必要があります。 
    
- サイトフォルダーを検索すると、その`documentlink`フォルダー (プロパティによって識別される) とすべてのサブフォルダーが検索されます。 
    
- 検索クエリで指定した`folderid`プロパティのみを使用した検索の結果をエクスポートする場合は、[最初のエクスポート] オプションを選択できます。「すべてのアイテム、認識できない形式のすべてのアイテム、暗号化されている、またはその他の理由でインデックスが作成されていません」というオプションがあります。 フォルダー内のすべてのアイテムは、常にインデックス作成の状態にかかわらずエクスポートされます。フォルダー ID には常にインデックスが付けられています。
