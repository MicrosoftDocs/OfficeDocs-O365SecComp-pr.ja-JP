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
description: Office 365 セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を使用して、対象となるコレクションを実行します。対象となるコレクションは、ケースまたは権限アイテムに応答するアイテムが特定のメールボックスまたはサイトフォルダーにあることを確信していることを意味しています。この記事に記載されているスクリプトを使用して、検索する特定のメールボックスまたはサイトフォルダーのフォルダー ID またはパスを取得します。
ms.openlocfilehash: c6e837e2f95b4f2ae3e32344f966f096407e360e
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296930"
---
# <a name="use-content-search-in-office-365-for-targeted-collections"></a><span data-ttu-id="3e168-105">Office 365 のコンテンツ検索を使用した対象コレクション</span><span class="sxs-lookup"><span data-stu-id="3e168-105">Use Content Search in Office 365 for targeted collections</span></span>

<span data-ttu-id="3e168-p102">Office 365 セキュリティ&amp;コンプライアンスセンターのコンテンツ検索機能では、Exchange メールボックスまたは SharePoint および OneDrive for business サイトの特定のフォルダーを検索するための直接 UI を使用することはできません。ただし、実際の検索クエリ構文でフォルダー ID またはパスを指定すると、特定のフォルダー (*対象となるコレクション*と呼ばれる) を検索することができます。コンテンツ検索を使用して対象のコレクションを実行することは、特定のメールボックスまたはサイトフォルダーに、訴訟や権限のあるアイテムに応答するアイテムがあることを確信する場合に役立ちます。この記事に記載されているスクリプトを使用して、メールボックスフォルダーのフォルダー ID、または SharePoint および OneDrive for business サイト上のフォルダーのパスを取得できます。その後、検索クエリでフォルダー ID またはパスを使用して、フォルダー内にあるアイテムを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="3e168-p102">The Content Search feature in the Office 365 Security &amp; Compliance Center doesn't provide a direct way in the UI to search specific folders in Exchange mailboxes or SharePoint and OneDrive for Business sites. However, it's possible to search specific folders (called a *targeted collection*) by specifying the folder ID or path in the actual search query syntax. Using Content Search to perform a targeted collection is useful when you're confident that items responsive to a case or privileged items are located in a specific mailbox or site folder. You can use the script in this article to obtain the folder ID for mailbox folders or the path for folders on a SharePoint and OneDrive for Business site. Then you can use the folder ID or path in a search query to return items located in the folder.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="3e168-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="3e168-111">Before you begin</span></span>

- <span data-ttu-id="3e168-p103">手順1でスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e168-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the script in Step 1. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
    <span data-ttu-id="3e168-p104">さらに、Exchange Online 組織内のメール受信者の役割を割り当てる必要があります。これは、手順1でスクリプトに含まれている**get-mailboxfolderstatistics**コマンドレットを実行するために必要です。既定では、メール受信者の役割は、Exchange Online の [組織の管理] および [受信者の管理] 役割グループに割り当てられます。Exchange Online でのアクセス許可の割り当ての詳細については、「[役割グループのメンバーの管理](https://go.microsoft.com/fwlink/p/?linkid=692102)」を参照してください。また、カスタム役割グループを作成し、メール受信者の役割を割り当ててから、手順1でスクリプトを実行する必要があるメンバーを追加することもできます。詳細については、「[役割グループの管理](https://go.microsoft.com/fwlink/p/?linkid=730688)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e168-p104">Additionally, you have to be assigned the Mail Recipients role in your Exchange Online organization. This is required to run the **Get-MailboxFolderStatistics** cmdlet, which is included in the script in Step 1. By default, the Mail Recipients role is assigned to the Organization Management and Recipient Management role groups in Exchange Online. For more information about assigning permissions in Exchange Online, see [Manage role group members](https://go.microsoft.com/fwlink/p/?linkid=692102). You could also create a custom role group, assign the Mail Recipients role to it, and then add the members who need to run the script in Step 1. For more information, see [Manage role groups](https://go.microsoft.com/fwlink/p/?linkid=730688).</span></span>
    
- <span data-ttu-id="3e168-p105">手順1でスクリプトを実行するたびに、新しいリモート PowerShell セッションが作成されます。そのため、使用可能なすべてのリモート PowerShell セッションを使用できます。この問題が発生しないようにするには、次のコマンドを実行して、アクティブなリモート PowerShell セッションを切断します。</span><span class="sxs-lookup"><span data-stu-id="3e168-p105">Each time you run the script in Step 1, a new remote PowerShell session is created. So you could use up all the remote PowerShell sessions available to you. To prevent this from happening, you can run the following command to disconnect your active remote PowerShell sessions.</span></span>
    
  ```
  Get-PSSession | Remove-PSSession
  ```

    <span data-ttu-id="3e168-123">詳細については、「[Exchange Online PowerShell への接続](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e168-123">For more information, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
    
- <span data-ttu-id="3e168-p106">スクリプトには、最小限のエラー処理が含まれています。このスクリプトの主な目的は、コンテンツ検索の検索クエリ構文で対象のコレクションを実行するために使用できるメールボックスフォルダー id またはサイトパスの一覧をすばやく表示することです。</span><span class="sxs-lookup"><span data-stu-id="3e168-p106">The script includes minimal error handling. The primary purpose of the script is to quickly display a list of mailbox folder IDs or site paths that can be used in the search query syntax of a Content Search to perform a targeted collection.</span></span>
    
- <span data-ttu-id="3e168-p107">このトピックで提供されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。このサンプルスクリプトは、あらゆる種類の保証なしに提供されています。さらに、Microsoft は、商品性、または特定の目的に対する適合性を明示的に保証することを含め、すべての黙示の保証を放棄します。サンプルスクリプトおよびドキュメントの使用によって発生した、またはパフォーマンスの低下によって生じるリスク全体は、そのままになります。いかなる場合でも、Microsoft、その作成者、またはスクリプトの作成、運用、または配信に関係するユーザーは、いかなる損害 (たとえば、損失を含む損害、ビジネスの中断、損失が発生しても含む) に対して責任を負わないものとします。このような損害が発生する可能性が Microsoft から通知されている場合でも、サンプルのスクリプトまたはドキュメントの使用または使用できないことによって発生する、ビジネス情報、またはその他の pecuniary 損失。</span><span class="sxs-lookup"><span data-stu-id="3e168-p107">The sample script provided in this topic isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-run-the-script-to-get-a-list-of-folders-for-a-mailbox-or-site"></a><span data-ttu-id="3e168-131">手順 1: スクリプトを実行して、メールボックスまたはサイトのフォルダーの一覧を取得する</span><span class="sxs-lookup"><span data-stu-id="3e168-131">Step 1: Run the script to get a list of folders for a mailbox or site</span></span>

<span data-ttu-id="3e168-p108">この最初の手順で実行するスクリプトは、メールボックスフォルダーまたは SharePoint または OneDrive for business フォルダーの一覧、および各フォルダーの対応するフォルダー ID またはパスを返します。このスクリプトを実行すると、次の情報を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3e168-p108">The script that you run in this first step will return a list of mailbox folders or SharePoint or OneDrive for Business folders, and the corresponding folder ID or path for each folder. When you run this script, it will prompt you for the following information.</span></span>
  
- <span data-ttu-id="3e168-p109">**電子メールアドレスまたはサイトの URL**Exchange メールボックスフォルダーとフォルダー id の一覧を返すには、保管担当者の電子メールアドレスを入力します。または、指定したサイトのパスの一覧を返すには、SharePoint サイトまたは OneDrive for business サイトの URL を入力します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="3e168-p109">**Email address or site URL** Type an email address of the custodian to return a list of Exchange mailbox folders and folder IDs. Or type the URL for a SharePoint site or a OneDrive for Business site to return a list of paths for the specified site. Here are some examples:</span></span> 
    
  - <span data-ttu-id="3e168-137">**Exchange** -stacig@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="3e168-137">**Exchange** - stacig@contoso.onmicrosoft.com</span></span> 
    
  - <span data-ttu-id="3e168-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span><span class="sxs-lookup"><span data-stu-id="3e168-138">**SharePoint** - https://contoso.sharepoint.com/sites/marketing</span></span> 
    
  - <span data-ttu-id="3e168-139">**OneDrive for business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span><span class="sxs-lookup"><span data-stu-id="3e168-139">**OneDrive for Business** - https://contoso-my.sharepoint.com/personal/stacig_contoso_onmicrosoft_com</span></span> 
    
- <span data-ttu-id="3e168-p110">**ユーザーの資格情報**-スクリプトは、資格情報を使用して Exchange Online に接続&amp;し、リモート PowerShell を使用してセキュリティ/コンプライアンスセンターに接続します。前述のように、このスクリプトを正常に実行するには、適切なアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e168-p110">**Your user credentials** - The script will use your credentials to connect to Exchange Online and the Security &amp; Compliance Center with remote PowerShell. As previously explained, you have to assigned the appropriate permissions to successfully run this script.</span></span>
    
<span data-ttu-id="3e168-142">メールボックスフォルダーまたはサイトパス名の一覧を表示するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="3e168-142">To display a list of mailbox folders or site path names:</span></span>
  
1. <span data-ttu-id="3e168-143">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `GetFolderSearchParameters.ps1`のようになります。</span><span class="sxs-lookup"><span data-stu-id="3e168-143">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `GetFolderSearchParameters.ps1`.</span></span>
    
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

2. <span data-ttu-id="3e168-144">ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="3e168-144">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="3e168-145">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="3e168-145">Run the script; for example:</span></span>
    
      ```
      .\GetFolderSearchParameters.ps1
      ```

4. <span data-ttu-id="3e168-146">スクリプトによってプロンプトが表示される情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="3e168-146">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="3e168-p111">スクリプトによって、指定したユーザーのメールボックスフォルダーまたはサイトフォルダーの一覧が表示されます。フォルダー ID またはパス名をコピーして、手順2で検索クエリに貼り付けることができるように、このウィンドウを開いておきます。</span><span class="sxs-lookup"><span data-stu-id="3e168-p111">The script displays a list of mailbox folders or site folder for the specified user. Let this window open so that you can copy a folder ID or path name and paste it in to a search query in Step 2.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="3e168-p112">コンピューター画面にフォルダーの一覧を表示する代わりに、スクリプトの出力をテキストファイルにリダイレクトすることができます。このファイルは、スクリプトが配置されているフォルダーに保存されます。たとえば、スクリプトの出力をテキストファイルにリダイレクトするには、手順 3 `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt`で次のコマンドを実行します。次に、ファイルからフォルダー ID またはパスをコピーして、検索クエリで使用できます。</span><span class="sxs-lookup"><span data-stu-id="3e168-p112">Instead of displaying a list of folders on the computer screen, you can re-direct the output of the script to a text file. This file will be saved to the folder where the script is located. For example, to redirect the script output to a text file, run the following command in Step 3:  `.\GetFolderSearchParameters.ps1 > StacigFolderIds.txt` Then you can copy a folder ID or path from the file to use in a search query.</span></span>
  
### <a name="script-output-for-mailbox-folders"></a><span data-ttu-id="3e168-152">メールボックスフォルダーのスクリプト出力</span><span class="sxs-lookup"><span data-stu-id="3e168-152">Script output for mailbox folders</span></span>

<span data-ttu-id="3e168-p113">メールボックスフォルダー id を取得している場合、スクリプトはリモート PowerShell を使用して Exchange Online に接続し、 **MailboxFolderStatisics**コマンドレットを実行して、指定したメールボックスのフォルダーの一覧を表示します。メールボックス内のすべてのフォルダーについて、スクリプトによって、 **FolderPath**列にフォルダーの名前と、フォルダー ID が**folderquery**列に表示されます。また、スクリプトは**folderId** (メールボックスプロパティの名前) のプレフィックスをフォルダー ID に追加します。**folderid**プロパティは検索可能なプロパティであるため、手順`folderid:<folderid>` 2 の検索クエリでそのフォルダーを検索するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3e168-p113">If you're getting mailbox folder IDs, the script connects to Exchange Online by using remote PowerShell, runs the **Get-MailboxFolderStatisics** cmdlet, and then displays the list of the folders from the specified mailbox. For every folder in the mailbox, the script displays the name of the folder in the **FolderPath** column and the folder ID in the **FolderQuery** column. Additionally, the script adds the prefix of **folderId** (which is the name of the mailbox property) to the folder ID. Because the **folderid** property is a searchable property, you'll use  `folderid:<folderid>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="3e168-157">メールボックスフォルダーのスクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3e168-157">Here's an example of the output returned by the script for mailbox folders.</span></span>
  
![スクリプトによって返されるメールボックスフォルダーとフォルダー id のリストの例](media/cd739207-eb84-4ebf-a03d-703f3d3a797d.png)
  
<span data-ttu-id="3e168-159">手順2の例は、ユーザーの [回復可能なアイテム] フォルダー内の [削除] サブフォルダーを検索するために使用されるクエリを示しています。</span><span class="sxs-lookup"><span data-stu-id="3e168-159">The example in Step 2 shows the query used to search the Purges subfolder in the user's Recoverable Items folder.</span></span>
  
### <a name="script-output-for-site-folders"></a><span data-ttu-id="3e168-160">サイトフォルダーのスクリプト出力</span><span class="sxs-lookup"><span data-stu-id="3e168-160">Script output for site folders</span></span>

<span data-ttu-id="3e168-p114">SharePoint または OneDrive for business サイトからパスを取得している場合、スクリプトはリモート&amp; PowerShell を使用してセキュリティコンプライアンスセンターに接続し、サイトを検索する新しいコンテンツ検索を作成し、フォルダーの一覧を表示します。指定したサイトにあります。このスクリプトは、各フォルダーの名前を表示し、**パス**のプレフィックス (サイトプロパティの名前) をフォルダーの URL に追加します。**path**プロパティは検索可能なプロパティであるため、手順`path:<path>` 2 の検索クエリでそのフォルダーを検索するために使用します。</span><span class="sxs-lookup"><span data-stu-id="3e168-p114">If you're getting paths from SharePoint or OneDrive for Business sites, the script connects to the Security &amp; Compliance Center using remote PowerShell, creates a new Content Search that searches the site for folders, and then displays a list of the folders located in the specified site. The script displays the name of each folder and adds the prefix of **path** (which is the name of the site property) to the folder URL. Because the **path** property is a searchable property, you'll use  `path:<path>` in a search query in Step 2 to search that folder.</span></span> 
  
<span data-ttu-id="3e168-164">サイトフォルダーのスクリプトによって返される出力の例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="3e168-164">Here's an example of the output returned by the script for site folders.</span></span>
  
![スクリプトによって返されるサイトフォルダーのパス名の一覧の例](media/519e8347-7365-4067-af78-96c465dc3d15.png)
  
## <a name="step-2-use-a-folder-id-or-path-to-perform-a-targeted-collection"></a><span data-ttu-id="3e168-166">手順 2: フォルダー ID またはパスを使用して対象のコレクションを実行する</span><span class="sxs-lookup"><span data-stu-id="3e168-166">Step 2: Use a folder ID or path to perform a targeted collection</span></span>

<span data-ttu-id="3e168-p115">特定のユーザーのフォルダー id またはパスの一覧を収集するスクリプトを実行した後、次の手順では、セキュリティ&amp;コンプライアンスセンターに移動して、特定のフォルダーを検索する新しいコンテンツ検索を作成します。`folderid:<folderid>`または、コンテンツ検索`path:<path>`キーワードボックスで構成した検索クエリで or プロパティを使用します (または、 **new-compliancesearch**コマンドレットを使用する場合は、 *contentmatchquery*パラメーターの値として指定します)。`folderid`または`path`プロパティを他の検索パラメーターまたは検索条件と組み合わせることができます。`folderid`または`path`プロパティのみをクエリに含める場合、検索では指定したフォルダーにあるすべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="3e168-p115">After you've run the script to collect a list of folder IDs or paths for a specific user, the next step to go to the Security &amp; Compliance Center and create a new Content Search to search a specific folder. You'll use the  `folderid:<folderid>` or  `path:<path>` property in the search query that you configure in the Content Search keyword box (or as the value for the  *ContentMatchQuery*  parameter if you use the **New-ComplianceSearch** cmdlet). You can combine the  `folderid` or  `path` property with other search parameters or search conditions. If you only include the  `folderid` or  `path` property in the query, the search will return all items located in the specified folder.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3e168-171">OneDrive の`path`場所を検索するためにプロパティを使用しても、検索結果には .png, tiff ファイル、.wav ファイルなどのメディアファイルは返されません。</span><span class="sxs-lookup"><span data-stu-id="3e168-171">Using the  `path` property to search OneDrive locations won't return media files, such as .png, .tiff, or .wav files, in the search results.</span></span> 
  
1. <span data-ttu-id="3e168-172">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="3e168-172">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="3e168-173">手順1でスクリプトの実行に使用したアカウントと資格情報を使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3e168-173">Sign in to Office 365 using the account and credentials that you used to run the script in Step 1.</span></span>
    
3. <span data-ttu-id="3e168-174">セキュリティ&amp; /コンプライアンスセンターの左側のウィンドウで、[**検索&amp;調査** \> **コンテンツ検索**] をクリックし\*\*\*\* ![、[新規](media/O365-MDM-CreatePolicy-AddIcon.gif)追加] アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e168-174">In the left pane of the Security &amp; Compliance Center, click **Search &amp; investigation** \> **Content search**, and then click **New** ![Add icon](media/O365-MDM-CreatePolicy-AddIcon.gif).</span></span>
    
4. <span data-ttu-id="3e168-p116">**[新規検索]** ページで、コンテンツ検索の名前を入力します。この名前は、組織内で固有である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e168-p116">On the **New search** page, type a name for the Content Search. This name has to be unique in your organization.</span></span> 
    
5. <span data-ttu-id="3e168-177">[検索する**場所**] で、次のいずれかの操作を行います。メールボックスフォルダーまたはサイトフォルダーのどちらを検索しているかによって決まります。</span><span class="sxs-lookup"><span data-stu-id="3e168-177">Under **Where do you want us to look**, do one of the following, based on whether you're searching a mailbox folder or a site folder:</span></span>
    
    - <span data-ttu-id="3e168-178">[**検索する特定のメールボックスを選択する**] をクリックし、手順1でスクリプトを実行したときに指定したものと同じメールボックスを追加します。</span><span class="sxs-lookup"><span data-stu-id="3e168-178">Click **Choose specific mailboxes to search** and then add the same mailbox that you specified when you ran the script in Step 1.</span></span> 
    
      <span data-ttu-id="3e168-179">または</span><span class="sxs-lookup"><span data-stu-id="3e168-179">Or</span></span>
    
    - <span data-ttu-id="3e168-180">[検索する**特定のサイトを選択する**] をクリックし、手順1でスクリプトを実行したときに指定したものと同じサイト URL を追加します。</span><span class="sxs-lookup"><span data-stu-id="3e168-180">Click **Choose specific sites to search** to search and then add the same site URL that you specified when you ran the script in Step 1.</span></span> 
    
6. <span data-ttu-id="3e168-181">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e168-181">Click **Next**.</span></span>
    
7. <span data-ttu-id="3e168-182">[**検索する内容を選択**してください] ページの [キーワード] ボックスに、 `folderid:<folderid>`手順`path:<path>` 1 でスクリプトによって返された値を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="3e168-182">In the keyword box on the **What do you want us to look for** page, paste the  `folderid:<folderid>` or  `path:<path>` value that was returned by the script in Step 1.</span></span> 
    
    <span data-ttu-id="3e168-183">たとえば、次のスクリーンショットのクエリは、ユーザーの回復可能なアイテムフォルダーのパージサブフォルダー内のアイテムを検索します (パージ`folderid`サブフォルダーのプロパティの値は、手順1のスクリーンショットに示されています)。</span><span class="sxs-lookup"><span data-stu-id="3e168-183">For example, the query in the following screenshot will search for any item in the Purges subfolder in the user's Recoverable Items folder (the value of the `folderid` property for the Purges subfolder is shown in the screenshot in Step 1):</span></span>
    
    ![folderid またはパスを検索クエリのキーワードボックスに貼り付けます。](media/84057516-b663-48a4-a78f-8032a8f8da80.png)
  
8. <span data-ttu-id="3e168-185">[**検索**] をクリックして、対象となるコレクション検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="3e168-185">Click **Search** to start the targeted collection search.</span></span> 
  
### <a name="examples-of-search-queries-for-targeted-collections"></a><span data-ttu-id="3e168-186">対象となるコレクションの検索クエリの例</span><span class="sxs-lookup"><span data-stu-id="3e168-186">Examples of search queries for targeted collections</span></span>

<span data-ttu-id="3e168-p117">ここでは、 `folderid`検索クエリで and `path`プロパティを使用して対象となるコレクションを実行する例をいくつか示します。プレースホルダーは、スペースを節約`folderid:<folderid>`する`path:<path>`ために使用されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e168-p117">Here are some examples of using the  `folderid` and  `path` properties in a search query to perform a targeted collection. Note that placeholders are used for  `folderid:<folderid>` and  `path:<path>` to save space.</span></span> 
  
- <span data-ttu-id="3e168-p118">この例では、3つの異なるメールボックスフォルダーを検索します。同じようなクエリ構文を使用して、ユーザーの回復可能なアイテムフォルダー内の隠しフォルダーを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="3e168-p118">This example searches three different mailbox folders. You could use similar query syntax to search the hidden folders in a user's Recoverable Items folder.</span></span>
    
  ```
  folderid:<folderid> OR folderid:<folderid> OR folderid:<folderid>
  ```

- <span data-ttu-id="3e168-191">この例では、完全に一致する語句を含むアイテムをメールボックスフォルダーから検索します。</span><span class="sxs-lookup"><span data-stu-id="3e168-191">This example searches a mailbox folder for items that contain an exact phrase.</span></span>
    
  ```
  folderid:<folderid> AND "Contoso financial results"
  ```

- <span data-ttu-id="3e168-192">次の使用例は、タイトルに "NDA" という文字が含まれるドキュメントのサイトフォルダー (およびすべてのサブフォルダー) を検索します。</span><span class="sxs-lookup"><span data-stu-id="3e168-192">This example searches a site folder (and any subfolders) for documents that contain the letters "NDA" in the title.</span></span>
    
  ```
  path:<path> AND filename:nda
  ```

- <span data-ttu-id="3e168-193">この例では、日付の範囲内で変更されたドキュメントのサイトフォルダー (およびすべてのサブフォルダー) を検索します。</span><span class="sxs-lookup"><span data-stu-id="3e168-193">This example searches a site folder (and any subfolder) for documents there were changed within a date range.</span></span>
    
  ```
  path:<path> AND (lastmodifiedtime>=01/01/2017 AND lastmodifiedtime<=01/21/2017)
  ```
  
## <a name="more-information"></a><span data-ttu-id="3e168-194">詳細情報</span><span class="sxs-lookup"><span data-stu-id="3e168-194">More information</span></span>

<span data-ttu-id="3e168-195">この記事に記載されているスクリプトを使用して対象のコレクションを実行する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="3e168-195">Keep the following things in mind when using the script in this article to perform targeted collections.</span></span>
  
- <span data-ttu-id="3e168-p119">このスクリプトでは、結果からフォルダーは削除されません。そのため、検索結果に表示される一部のフォルダーには、システムによって生成されるコンテンツが含まれているため、検索できない (または、0個のアイテムを返します) 場合が</span><span class="sxs-lookup"><span data-stu-id="3e168-p119">The script doesn't remove any folders from the results. So some folders listed in the results might be unsearchable (or return zero items) because they contain system-generated content.</span></span>
    
- <span data-ttu-id="3e168-p120">このスクリプトは、ユーザーのプライマリメールボックスのフォルダー情報のみを返します。ユーザーのアーカイブメールボックス内のフォルダーに関する情報は返されません。</span><span class="sxs-lookup"><span data-stu-id="3e168-p120">This script only returns folder information for the user's primary mailbox. It doesn't return information about folders in the user's archive mailbox.</span></span>
    
- <span data-ttu-id="3e168-p121">メールボックスフォルダーを検索する場合、指定されたフォルダー `folderid` (そのプロパティで識別される) のみが検索されます。サブフォルダーは検索されません。サブフォルダーを検索するには、検索するサブフォルダーのフォルダー ID を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3e168-p121">When searching mailbox folders, only the specified folder (identified by its  `folderid` property) will be searched. Subfolders won't be searched. To search sub-folders, you need to use the  folder ID for the sub-folder that you want to search.</span></span> 
    
- <span data-ttu-id="3e168-203">サイトフォルダーを検索すると、その`path`フォルダー (プロパティによって識別される) とすべてのサブフォルダーが検索されます。</span><span class="sxs-lookup"><span data-stu-id="3e168-203">When searching site folders, the folder (identified by its  `path` property) and all sub-folders will be searched.</span></span> 
    
- <span data-ttu-id="3e168-p122">前述したように、プロパティ`path`を使用して、.png、tiff、.wav ファイルなどのメディアファイルを OneDrive の場所に配置することはできません。OneDrive フォルダーのメディアファイルを検索するには、別の[サイトプロパティ](keyword-queries-and-search-conditions.md#searchable-site-properties)を使用します。</span><span class="sxs-lookup"><span data-stu-id="3e168-p122">As previously stated, you can't use  `path` property to search for media files, such as .png, .tiff, or .wav files, located in OneDrive locations. Use a different [site property](keyword-queries-and-search-conditions.md#searchable-site-properties) to search for media files in OneDrive folders.</span></span> 

- <span data-ttu-id="3e168-p123">検索クエリで指定した`folderid`プロパティのみを使用した検索の結果をエクスポートする場合は、[最初のエクスポート] オプションを選択できます。「すべてのアイテム、認識できない形式のすべてのアイテム、暗号化されている、またはその他の理由でインデックスが作成されていません」というオプションがあります。フォルダー内のすべてのアイテムは、常にインデックス作成の状態にかかわらずエクスポートされます。フォルダー ID には常にインデックスが付けられています。</span><span class="sxs-lookup"><span data-stu-id="3e168-p123">When exporting the results of a search in which you only specified the `folderid` property in the search query, you can choose the first export option, "All items, excluding ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons." All items in the folder will always be exported regardless of their indexing status because the folder ID is always indexed.</span></span>
