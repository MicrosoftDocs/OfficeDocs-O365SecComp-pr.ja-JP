---
title: コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーの一覧を探す
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: コンテンツ検索とこの記事のスクリプトを使用して、ユーザーのグループのメールボックスと OneDrive for business サイトを検索します。
ms.openlocfilehash: 758c9b9e756f6830f207b76392ad808fc14f0caa
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218887"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="93e74-103">コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーの一覧を探す</span><span class="sxs-lookup"><span data-stu-id="93e74-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="93e74-p101">Office 365 セキュリティ&amp;コンプライアンスセンターでは、時間がかかる電子情報開示に関連するタスクを自動化するための Windows PowerShell コマンドレットが多数提供されています。現時点では、セキュリティ&amp;コンプライアンスセンターでコンテンツ検索を作成して大量の保管担当者コンテンツの場所を検索すると、時間と準備がかかります。検索を作成する前に、各 OneDrive for business サイトの URL を収集し、ビジネスサイト用の各メールボックスと O nedrive を検索に追加する必要があります。今後のリリースでは、これはセキュリティ&amp;コンプライアンスセンターでの操作が簡単になります。その後、この記事のスクリプトを使用してこのプロセスを自動化できます。このスクリプトは、組織の個人用サイトのドメイン名 (たとえば、URL https://contoso-my.sharepoint.com)内の**contoso** 、ユーザーの電子メールアドレスのリスト、新しいコンテンツ検索の名前、使用する検索クエリ) の入力を求めます。このスクリプトは、リスト内の各ユーザーの OneDrive for business URL を取得し、ユーザーが指定した検索クエリを使用して、リスト内の各ユーザーのメールボックスと onedrive for business サイトを検索するコンテンツ検索を作成して開始します。</span><span class="sxs-lookup"><span data-stu-id="93e74-p101">The Office 365 Security &amp; Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks. Currently, creating a Content Search in the Security &amp; Compliance Center to search a large number of custodian content locations takes time and preparation. Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and O neDrive for Business site to the search. In future releases, this will be easier to do in the Security &amp; Compliance Center. Until then, you can use the script in this article to automate this process. This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use. The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="93e74-111">始める前に</span><span class="sxs-lookup"><span data-stu-id="93e74-111">Before you begin</span></span>

- <span data-ttu-id="93e74-112">手順3でスクリプトを実行するには、セキュリティ&amp;コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。また、SharePoint Online のグローバル管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="93e74-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="93e74-p102">手順2で作成したユーザーの一覧と、手順3のスクリプトを同じフォルダーに保存するようにしてください。これにより、スクリプトをより簡単に実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="93e74-p102">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="93e74-p103">スクリプトには、最小限のエラー処理が含まれています。主な目的は、各ユーザーのメールボックスと OneDrive for business サイトをすばやく簡単に検索することです。</span><span class="sxs-lookup"><span data-stu-id="93e74-p103">The script includes minimal error handling. It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="93e74-p104">このトピックに記載されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。サンプルスクリプトは、あらゆる種類の保証なしに提供されています。Microsoft は、すべての[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied 保証を含め、商品性の黙示的な保証または特定の目的に対する適合性を含むすべての保証を放棄します。サンプルのスクリプトとドキュメントの使用によって発生した、またはパフォーマンスを低下させたリスク全体は、そのままになります。いかなる場合でも、Microsoft、その作成者、またはスクリプトの作成、運用、または配信に関係するユーザーは、いかなる損害 (たとえば、損失を含む損害、ビジネスの中断、損失が発生しても含む) に対して責任を負わないものとします。このような損害が発生する可能性が Microsoft から通知されている場合でも、サンプルのスクリプトまたはドキュメントの使用または使用できないことによって発生する、ビジネス情報、またはその他の pecuniary 損失。</span><span class="sxs-lookup"><span data-stu-id="93e74-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="93e74-122">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="93e74-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="93e74-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="93e74-123"></span></span>

<span data-ttu-id="93e74-p105">最初の手順として、SharePoint Online 管理シェルをインストールします。この手順でシェルを使用する必要はありませんが、手順3で実行するスクリプトに必要な前提条件が含まれているためインストールする必要があります。これらの前提条件によって、スクリプトは SharePoint Online と通信して、OneDrive for business サイトの url を取得できます。</span><span class="sxs-lookup"><span data-stu-id="93e74-p105">The first step is to install the SharePoint Online Management Shell. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="93e74-127">「 [sharepoint online 管理シェル Windows PowerShell 環境をセットアップ](https://go.microsoft.com/fwlink/p/?LinkID=286318)する」に移動し、手順1と手順2を実行して、sharepoint online 管理シェルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="93e74-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="93e74-128">手順 2: ユーザーのリストを生成する</span><span class="sxs-lookup"><span data-stu-id="93e74-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="93e74-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="93e74-129"></span></span>

<span data-ttu-id="93e74-p106">手順3のスクリプトは、メールボックスと OneDrive アカウントでユーザーのリストを検索するコンテンツ検索を作成します。テキストファイルに電子メールアドレスを入力することも、Windows PowerShell でコマンドを実行して電子メールアドレスの一覧を取得し、それをファイルに保存することもできます (手順3でスクリプトを保存するのと同じフォルダーに格納されます)。</span><span class="sxs-lookup"><span data-stu-id="93e74-p106">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="93e74-132">次の[Exchange Online の PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)コマンドでは、を実行して、組織内のすべてのユーザーの電子メールアドレスの一覧を取得し、それを`Users.txt`という名前のテキストファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="93e74-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="93e74-p107">このコマンドを実行した後、必ずファイルを開いて、プロパティ名を`PrimarySmtpAddress`含むヘッダーを削除してください。テキストファイルには、電子メールアドレスのリストのみを含める必要があります。それ以外の場合は何も指定しないでください。電子メールアドレスのリストの前または後に空白行がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="93e74-p107">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`. The text file should just contain a list of email addresses, and nothing else. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="93e74-136">手順 3: スクリプトを実行して検索を作成および開始する</span><span class="sxs-lookup"><span data-stu-id="93e74-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="93e74-p108">この手順でスクリプトを実行すると、次の情報を入力するように求めるメッセージが表示されます。スクリプトを実行する前に、この情報を用意しておいてください。</span><span class="sxs-lookup"><span data-stu-id="93e74-p108">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="93e74-139">**ユーザーの資格情報**-スクリプトは、自分の資格情報を使用して SharePoint Online にアクセスして、OneDrive for business の&amp; url を取得し、リモート PowerShell を使用してセキュリティコンプライアンスセンターに接続します。</span><span class="sxs-lookup"><span data-stu-id="93e74-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security &amp; Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="93e74-p109">**個人用サイトのドメインの名前**-個人用サイトのドメインは、組織内のすべての OneDrive for business サイトを含むドメインです。たとえば、個人用サイトのドメインの URL がの場合**https://contoso-my.sharepoint.com**は、スクリプトによっ`contoso`て、個人用サイトのドメインの名前を入力するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="93e74-p109">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="93e74-p110">**手順2のテキストファイルのパス名**。手順2で作成したテキストファイルのパス名。テキストファイルとスクリプトが同じフォルダーにある場合は、テキストファイルの名前を入力します。それ以外の場合は、テキストファイルの完全なパス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="93e74-p110">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2. If the text file and the script are located in the same folder, then enter the name of the text file. Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="93e74-145">**コンテンツ検索の名前**-スクリプトによって作成されるコンテンツ検索の名前。</span><span class="sxs-lookup"><span data-stu-id="93e74-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="93e74-p111">**検索クエリ**-コンテンツ検索と共に使用される検索クエリが作成され、実行されます。検索クエリの詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93e74-p111">**Search query** - The search query that will be used with the Content Search is created and run. For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="93e74-148">**このスクリプトを実行するには、以下の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="93e74-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="93e74-p112">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `SearchEXOOD4B.ps1`のようになります。手順2でユーザーのリストを保存したのと同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="93e74-p112">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`. Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
  ```
  # This PowerShell script will prompt you for the following information:
  #    * Your user credentials 
  #    * The name of your organization's MySite domain                                              
  #    * The pathname for the text file that contains a list of user email addresses
  #    * The name of the Content Search that will be created
  #    * The search query string
  # The script will then:
  #    * Find the OneDrive for Business site for each user in the text file
  #    * Create and start a Content Search using the above information
  # Get user credentials
  if (!$credentials)
  {
      $credentials = Get-Credential
  }
  # Get the user's MySite domain name.  We use this to create the admin URL and root URL for OneDrive for Business
  $mySiteDomain = Read-Host "What is your organization's MySite domain?  For example,  'contoso' for 'https://contoso-my.sharepoint.com'"
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
  # Get other required information
  $inputfile = read-host "Enter the file name of the text file that contains the email addresses for the users you want to search"
  $searchName = Read-Host "Enter the name for the new search"
  $searchQuery = Read-Host "Enter the search query you want to use"
  $emailAddresses = Get-Content $inputfile | where {$_ -ne ""}  | foreach{ $_.Trim() }
  # Connect to Office 365
  if (!$s -or !$a)
  {
      $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
      $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Could not create PowerShell session."
          return;
      }
  }
  # Load the SharePoint assemblies from the SharePoint Online Management Shell
  # To install, go to http://go.microsoft.com/fwlink/p/?LinkId=255251
  if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
  {
      $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
      $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
      $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
      if (!$SharePointClient)
      {
          Write-Error "SharePoint Online Management Shell isn't installed, please install from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then run this script again"
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Add the path of the User Profile Service to the SPO admin URL, then create a new webservice proxy to access it
  $proxyaddr = "$AdminUrl/_vti_bin/UserProfileService.asmx?wsdl"
  $UserProfileService= New-WebServiceProxy -Uri $proxyaddr -UseDefaultCredential False
  $UserProfileService.Credentials = $credentials
  # Take care of auth cookies
  $strAuthCookie = $spCreds.GetAuthenticationCookie($AdminUrl)
  $uri = New-Object System.Uri($AdminUrl)
  $container = New-Object System.Net.CookieContainer
  $container.SetCookies($uri, $strAuthCookie)
  $UserProfileService.CookieContainer = $container
  Write-Host "Getting each user's OneDrive for Business URL"
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
      try
      {
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" } 
          $url = $prop.values[0].value
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "-$emailAddress => $furl"
      }
      catch
      {
          Write-Warning "Could not locate OneDrive for $emailAddress"
      }
  }
  Write-Host "Creating and starting the search"
  $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $emailAddresses -SharePointLocation $urls -ContentMatchQuery $searchQuery
  # Finally, start the search and then display the status
  if($search)
  {
      Start-ComplianceSearch $search.Name
      Get-ComplianceSearch $search.Name
  }
  
  ```

2. <span data-ttu-id="93e74-151">Windows PowerShell を開き、スクリプトを保存したフォルダーおよび手順2でユーザーのリストに移動します。</span><span class="sxs-lookup"><span data-stu-id="93e74-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="93e74-152">スクリプトを開始します。例えば：</span><span class="sxs-lookup"><span data-stu-id="93e74-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="93e74-153">資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="93e74-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="93e74-p113">スクリプトによってプロンプトが表示されたら、次の情報を入力します。各情報を入力し、enter キー \*\*\*\* を押します。</span><span class="sxs-lookup"><span data-stu-id="93e74-p113">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="93e74-156">個人用サイトのドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="93e74-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="93e74-157">ユーザーのリストを含むテキストファイルのパス名。</span><span class="sxs-lookup"><span data-stu-id="93e74-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="93e74-158">コンテンツ検索の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="93e74-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="93e74-159">検索クエリ (空白のままにすると、コンテンツの場所にあるすべてのアイテムが返されます)。</span><span class="sxs-lookup"><span data-stu-id="93e74-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="93e74-p114">このスクリプトは、各 OneDrive for business サイトの url を取得し、検索を作成して開始します。security & コンプライアンスセンターの PowerShell で**new-compliancesearch**コマンドレットを実行して検索の統計情報と結果を表示するか、またはセキュリティ&amp;コンプライアンスセンターの [**コンテンツ検索**] ページに移動して表示することができます。検索に関する情報。</span><span class="sxs-lookup"><span data-stu-id="93e74-p114">The script gets the URLs for each OneDrive for Business site and then creates and starts the search. You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security &amp; Compliance Center to view information about the search.</span></span> 
