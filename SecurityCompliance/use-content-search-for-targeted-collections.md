---
title: Office 365 でのコンテンツの検索を使用して、コレクションの対象となります。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: e3cbc79c-5e97-43d3-8371-9fbc398cd92e
description: コンテンツの検索を使用して、Office 365 のセキュリティで&amp;コンプライアンス センターを対象となるコレクションを実行します。対象となるコレクションでは、サポート案件への応答のアイテム、または特権を持つアイテムが特定のメールボックスまたはサイトのフォルダー内にあることを確信していることを意味します。この資料のスクリプトを使用すると、フォルダーの ID を検索する特定のメールボックスまたはサイト フォルダーのパスを取得します。
ms.openlocfilehash: f4bb63a193a11e7467b3b296b2bdfa50657ae65a
ms.sourcegitcommit: 448c5897e44448adfc82e3eaffb774c770c04815
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "25522288"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="29c9e-105">Office 365 でのコンテンツの検索を使用して、コレクションの対象となります。</span><span class="sxs-lookup"><span data-stu-id="29c9e-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="29c9e-p102">コンテンツの検索機能は、Office 365 のセキュリティ&amp;コンプライアンス センターは、ビジネス サイトの Exchange メールボックスまたは SharePoint と OneDrive で特定のフォルダーを検索するのには、UI で直接的な方法を提供していません。ただし、実際の検索クエリの構文では、フォルダー ID またはパスを指定することによって特定のフォルダー (対象となるコレクションと呼ばれます) を検索することができます。コンテンツの検索を使用して、対象のコレクションを実行すると、ケースへの応答のアイテム、または特権を持つアイテムが特定のメールボックスまたはサイトのフォルダー内にあることに間違いない場合に便利です。この資料のスクリプトを使用すると、メールボックス フォルダーのフォルダー ID またはビジネス サイトの SharePoint と OneDrive のフォルダーのパスを取得します。アイテムがフォルダーにあるを取得するのに検索クエリにフォルダー ID またはパスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it is possible to search specific folders (called a targeted collection) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="29c9e-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="29c9e-111">Before you begin</span></span>

- <span data-ttu-id="29c9e-p103">セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;ステップ 1 でスクリプトを実行するコンプライアンス センターです。詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="29c9e-p104">さらに、Exchange Online 組織内の差し込み印刷の宛先役割を割り当てる必要があります。これは、ステップ 1 でスクリプトに含まれる**Get MailboxFolderStatistics**コマンドレットを実行する必要です。既定では、メール受信者の役割が割り当てられている組織の管理と受信者の管理役割グループに Exchange オンライン。Exchange のオンラインでのアクセス許可の割り当ての詳細については、[管理役割グループのメンバー](https://go.microsoft.com/fwlink/p/?linkid=692102)を参照してください。カスタムの役割グループを作成し、メール受信者の役割を割り当てる、ステップ 1 でスクリプトを実行する必要があるメンバーを追加します。詳細については、[役割グループの管理](https://go.microsoft.com/fwlink/p/?linkid=730688)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="29c9e-p105">手順 1 で、スクリプトを実行するたびに、新しいリモート PowerShell セッションが作成されます。などをすべてリモート PowerShell セッションを使用するを使用できます。これが発生しないようにするには、作業中のリモート PowerShell セッションを切断するのには次のコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="29c9e-123">詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29c9e-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="29c9e-p106">スクリプトには、最低限のエラー処理が含まれています。スクリプトの主な目的は、すばやくメールボックス フォルダー Id の一覧を表示したり、サイトの対象となるコレクションを実行するコンテンツの検索の検索クエリの構文で使用できるパスには。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="29c9e-p107">このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="29c9e-131">手順 1: スクリプトを実行するメールボックスまたはサイトのフォルダーの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="29c9e-p108">最初の手順を実行するスクリプトは、メールボックスのフォルダーの一覧または SharePoint ビジネス フォルダーでは、OneDrive と対応するフォルダーの ID または各フォルダーへのパスに戻ります。このスクリプトを実行する場合を次の情報を求めます。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="29c9e-p109">**アドレスまたはサイトの URL を電子メールで送信**Exchange メールボックス フォルダーのリストを返し、Id を 2 つ折りに管理者の電子メール アドレスを入力します。または指定したサイトのパスの一覧を取得するには、SharePoint サイトの URL またはビジネス サイトの OneDrive を入力します。いくつかの例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and fold IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="29c9e-137">**Exchange** - stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="29c9e-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="29c9e-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="29c9e-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="29c9e-139">**ビジネスの OneDrive** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="29c9e-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="29c9e-p110">**ユーザーの資格情報**でスクリプトは Exchange Online とセキュリティへの接続に資格情報を使用&amp;リモート PowerShell でコンプライアンス センターです。説明したようには、正常にこのスクリプトを実行する適切なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="29c9e-142">メールボックス フォルダーの一覧を表示またはサイトのパス名。</span><span class="sxs-lookup"><span data-stu-id="29c9e-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="29c9e-143">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `GetFolderSearchParameters.ps1`。</span><span class="sxs-lookup"><span data-stu-id="29c9e-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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
          # Create a Complinace Search Action and wait for it to complete. The folders will be listed in the .Results parameter
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

2. <span data-ttu-id="29c9e-144">ローカル コンピューターに Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="29c9e-145">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="29c9e-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="29c9e-146">スクリプトによってユーザーの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="29c9e-p111">スクリプトには、メールボックスのフォルダーまたは指定したユーザーのサイト フォルダーの一覧が表示されます。このウィンドウを開き、フォルダー ID またはパス名をコピーして手順 2 で検索クエリを貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="29c9e-p112">コンピューターの画面には、フォルダーの一覧を表示するのではなく、テキスト ファイルにスクリプトの出力を再指示できます。このファイルは、スクリプトが格納されているフォルダーに保存されます。たとえば、スクリプトのテキスト ファイルに出力をリダイレクトするのには手順 3 で次のコマンドを実行:`.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`検索クエリで使用するファイルからフォルダー ID またはパスをコピーすることができますし、します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="29c9e-152">メールボックス フォルダーのスクリプトの出力</span><span class="sxs-lookup"><span data-stu-id="29c9e-152">Script output for mailbox folders</span></span>

<span data-ttu-id="29c9e-p113">メールボックス フォルダー Id がある場合、スクリプトはリモート PowerShell を使用して Exchange Online に接続**Get MailboxFolderStatisics**コマンドレットを実行し、指定したメールボックスからフォルダーの一覧が表示されます。メールボックス内のすべてのフォルダーには、スクリプトは、 **FolderPath**列と**FolderQuery**列にフォルダー ID で、フォルダーの名前を表示します。さらに、スクリプトはフォルダー ID に**フォルダー Id** (これは、メールボックスのプロパティの名前) のプレフィックスを追加します。**フォルダー id**のプロパティが検索可能なプロパティであるためを使用します`folderid:<folderid>`フォルダーを検索する手順 2 で検索クエリにします。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="29c9e-157">ここでは、メールボックス フォルダーのスクリプトによって返される出力の例です。</span><span class="sxs-lookup"><span data-stu-id="29c9e-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![メールボックスのフォルダーとフォルダーのスクリプトによって返される Id の一覧の例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="29c9e-159">ステップ 2 の例では、ユーザーの回復可能なアイテム] フォルダーで、[パージ] サブフォルダーを検索に使用するクエリを示します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="29c9e-160">サイト フォルダーのスクリプトの出力</span><span class="sxs-lookup"><span data-stu-id="29c9e-160">Script output for site folders</span></span>

<span data-ttu-id="29c9e-p114">スクリプトが接続セキュリティを保護する場合は、ビジネス サイトの SharePoint または OneDrive からのパスを取得している、 &amp; 、新しいコンテンツの検索フォルダーは、サイトを検索し、フォルダーの一覧が表示されますを作成するリモート PowerShell を使用してコンプライアンス センター指定したサイト内にあります。スクリプトは、各フォルダーの名前を表示し、フォルダーの URL に (つまり、サイトのプロパティの名前)**のパス**のプレフィックスを追加します。使用する**path**プロパティが検索可能なプロパティであるため、`path:<path>`フォルダーを検索する手順 2 で検索クエリにします。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="29c9e-164">ここでは、サイト フォルダーのスクリプトによって返される出力の例です。</span><span class="sxs-lookup"><span data-stu-id="29c9e-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![スクリプトによって返されるサイトのフォルダーのパス名のリストの例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="29c9e-166">ステップ 2: 対象となるコレクションを実行するのにフォルダーの ID またはパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="29c9e-p115">セキュリティに移動するの次のステップまたは特定のユーザーのパスのフォルダー Id の一覧を収集するスクリプトを実行すると後、&amp;コンプライアンス センターと、特定のフォルダーを検索するのには新しいコンテンツの検索を作成します。使用して、`folderid:<folderid>`または`path:<path>`、コンテンツの検索キーワード] ボックスで (または**新規 ComplianceSearch**コマンドレットを使用する場合は、 *ContentMatchQuery*パラメーターの値) に構成した検索クエリのプロパティです。組み合わせることができます、`folderid`または`path`その他のプロパティのパラメーターを検索するか、検索条件を定義します。のみを指定した場合、`folderid`または`path`クエリで、検索が返されるすべての項目を指定したフォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="29c9e-171">使用して、 `path` OneDrive の場所を検索するプロパティが検索結果に、.png、.tiff、または .wav ファイルなどのメディア ファイルを返しません。</span><span class="sxs-lookup"><span data-stu-id="29c9e-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="29c9e-172">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="29c9e-173">アカウントとステップ 1 でスクリプトを実行するために使用する資格情報を使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="29c9e-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="29c9e-174">セキュリティの左側のウィンドウで&amp;コンプライアンス センター] をクリックして**検索&amp;調査** \> **コンテンツの検索**、し、[**新規**] をクリックし、![追加アイコン](media/O365-MDM-CreatePolicy-AddIcon.gif)。</span><span class="sxs-lookup"><span data-stu-id="29c9e-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="29c9e-p116">**[新規検索]** ページで、コンテンツ検索の名前を入力します。この名前は、組織内で固有である必要があります。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="29c9e-177">**場所を指定して検索できるため**、次のいずれかの操作に基づいてかどうか、メールボックスのフォルダーまたはサイトのフォルダーに検索します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-177">Under **Where do you want us to look**, do one of the following, based on whether your searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="29c9e-178">**検索する特定のメールボックスを選択**をクリックし、手順 1 でスクリプトを実行するときに指定したのと同じメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="29c9e-179">または</span><span class="sxs-lookup"><span data-stu-id="29c9e-179">Or</span></span>
    
    - <span data-ttu-id="29c9e-180">検索し、手順 1 でスクリプトを実行したときに指定したサイトの URL を追加し、**検索する特定のサイトを選択してください**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c9e-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="29c9e-181">[ **次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c9e-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="29c9e-182">**何か探すようになりました**] ページで [キーワード] ボックスに貼り付け、`folderid:<folderid>`または`path:<path>`ステップ 1 でスクリプトによって返された値です。</span><span class="sxs-lookup"><span data-stu-id="29c9e-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="29c9e-183">ユーザーの回復可能なアイテム] フォルダー内のサブフォルダーに削除の項目の次のスクリーン ショットでは、クエリを検索するたとえば、(の値、`folderid`のステップ 1 のスクリーン ショットでパージ サブフォルダーのプロパティが表示されている)。</span><span class="sxs-lookup"><span data-stu-id="29c9e-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![フォルダー id または検索クエリの [キーワード] ボックスにパスをペーストします。](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="29c9e-185">対象となるコレクションの検索を開始する**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="29c9e-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="29c9e-186">コレクションの対象となる検索クエリの例</span><span class="sxs-lookup"><span data-stu-id="29c9e-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="29c9e-p117">使用するいくつかの例をここでは、`folderid`と`path`で、対象のコレクションを実行する検索クエリのプロパティです。用のプレース ホルダーを使用することに注意してください`folderid:<folderid>`と`path:<path>`領域を節約します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="29c9e-p118">この例では、3 つの別のメールボックス フォルダーを検索します。ユーザーの回復可能なアイテム] フォルダー内の非表示のフォルダーを検索するのに同様のクエリ構文を使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="29c9e-191">この例では、完全一致のフレーズを含むアイテムのメールボックス フォルダーを検索します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="29c9e-192">次の使用例は、タイトルに「機密保持契約」の文字含むドキュメントをサイト フォルダーとサブフォルダー) を検索します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="29c9e-193">次の使用例は、日付の範囲内にあるドキュメントが変更されたために、サイト フォルダーとすべてのサブフォルダー) を検索します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="29c9e-194">詳細情報</span><span class="sxs-lookup"><span data-stu-id="29c9e-194">More information</span></span>

<span data-ttu-id="29c9e-195">この資料のスクリプトを使用して、コレクションを対象としたときは、次の点に注意をしてください。</span><span class="sxs-lookup"><span data-stu-id="29c9e-195">Keep the following things in mind when using the script in this article and performing targeted collections.</span></span>
  
- <span data-ttu-id="29c9e-p119">スクリプトは、結果から、任意のフォルダーを削除されません。いくつかのフォルダーが表示されるように、結果可能性があります検索できない (または 0 個のアイテムを返す) システムによって生成されたコンテンツが含まれているためです。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="29c9e-p120">このスクリプトは、ユーザーのプライマリ メールボックスのフォルダー情報だけを返します。ユーザーのアーカイブ メールボックス内のフォルダーに関する情報を返さない。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="29c9e-p121">フォルダーでは、指定したフォルダーのみを検索するとき (によって識別される、`folderid`プロパティ) が検索されます。サブフォルダーは検索されません。フォルダーにサブフォルダーを検索するには、使用する必要があります、 `folderid` 、サブ フォルダーを検索するのです。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  `folderid` for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="29c9e-203">サイト フォルダー、フォルダーを検索するとき (によって識別される、`path`プロパティ) と、すべてのサブフォルダーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="29c9e-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="29c9e-p122">前述したように、使うことはできません`path`.png、.tiff、.wav ファイルなどのメディア ファイルを検索するプロパティが OneDrive の場所に配置します。OneDrive フォルダー内のメディア ファイルを検索するには、別の[サイトのプロパティ](keyword-queries-and-search-conditions.md#searchable-site-properties)を使用します。</span><span class="sxs-lookup"><span data-stu-id="29c9e-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 
