---
title: コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーの一覧を探す
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: ユーザーのグループのビジネス サイトのメールボックスと OneDrive を検索するのに、この資料のコンテンツの検索とスクリプトを使用します。
ms.openlocfilehash: cc88f8e81a9883b8d392965db14994691878748d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532006"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a><span data-ttu-id="bc54a-103">コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーの一覧を探す</span><span class="sxs-lookup"><span data-stu-id="bc54a-103">Use Content Search to search the mailbox and OneDrive for Business site for a list of users</span></span>

<span data-ttu-id="bc54a-p101">Office 365 のセキュリティ&amp;コンプライアンス センターには、いくつかの時間がかかる電子的証拠開示に関連するタスクを自動化するための Windows PowerShell コマンドレットが用意されています。現在、コンテンツの検索を作成する、セキュリティで&amp;を検索するコンテンツの場所の管理者の数が多いコンプライアンス センターには、時間と準備します。検索を作成する前に、ビジネス サイトの各 OneDrive の URL を収集し、検索する各メールボックスと O の neDrive のビジネス サイトを追加する必要があります。将来のリリースでは、これが容易になります、セキュリティでは&amp;コンプライアンス センターです。それまでは、このプロセスを自動化するのにこの資料のスクリプトを使用することができます。このスクリプトの入力を求め、組織の個人用サイトのドメインの名前 (たとえば、 **contoso 社**の URL にhttps://contoso-my.sharepoint.com)、一連のユーザーの電子メール アドレスを使用するには、新しいコンテンツの検索、および検索クエリの名前。スクリプトがビジネスの URL の一覧で、ユーザーごとに、OneDrive を取得しを作成し、提供する検索クエリを使用して、ボックスの一覧で各ユーザーのビジネス サイトのメールボックスを検索するコンテンツの検索と OneDrive を開始します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p101">The Office 365 Security &amp; Compliance Center provides a number of Windows PowerShell cmdlets that let you automate time-consuming eDiscovery-related tasks. Currently, creating a Content Search in the Security &amp; Compliance Center to search a large number of custodian content locations takes time and preparation. Before you create a search, you have to collect the URL for each OneDrive for Business site and then add each mailbox and O neDrive for Business site to the search. In future releases, this will be easier to do in the Security &amp; Compliance Center. Until then, you can use the script in this article to automate this process. This script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), a list of user email addresses, the name of the new Content Search, and the search query to use. The script gets the OneDrive for Business URL for each user in the list, and then it creates and starts a Content Search that searches the mailbox and OneDrive for Business site for each user in the list, using the search query that you provide.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="bc54a-111">はじめに</span><span class="sxs-lookup"><span data-stu-id="bc54a-111">Before you begin</span></span>

- <span data-ttu-id="bc54a-112">セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;コンプライアンス センターと SharePoint Online グローバル管理者は、手順 3 でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-112">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3.</span></span>
    
- <span data-ttu-id="bc54a-p102">手順 2 と手順 3 で同じフォルダーにスクリプトで作成したユーザーの一覧を保存しておいてください。容易にできるようにスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p102">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="bc54a-p103">スクリプトには、最低限のエラー処理が含まれています。主な目的は、迅速かつ容易に検索するメールボックスと OneDrive の各ユーザーのビジネス サイトです。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p103">The script includes minimal error handling. It's primary purpose is to quickly and easily search the mailbox and OneDrive for Business site of each user.</span></span>
    
- <span data-ttu-id="bc54a-p104">このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft では、すべてを拒否する[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all i[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="bc54a-122">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="bc54a-122">Step 1: Install the SharePoint Online Management Shell</span></span>
<span data-ttu-id="bc54a-123"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="bc54a-123"></span></span>

<span data-ttu-id="bc54a-p105">最初のステップでは、SharePoint のオンライン管理シェルをインストールします。ここでシェルを使用する必要はありませんが、手順 3 で実行するスクリプトに必要な必須コンポーネントが含まれているために、それをインストールする必要です。これらの前提条件は、SharePoint Online ビジネス サイトの OneDrive の Url を取得すると通信するスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p105">The first step is to install the SharePoint Online Management Shell. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="bc54a-127">[SharePoint のオンライン管理シェル Windows PowerShell 環境の設定](https://go.microsoft.com/fwlink/p/?LinkID=286318)に移動し、SharePoint のオンライン管理シェルをインストールするには、ステップ 1 とステップ 2 を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-127">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell.</span></span>
  
## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="bc54a-128">手順 2: は、ユーザーの一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-128">Step 2: Generate a list of users</span></span>
<span data-ttu-id="bc54a-129"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="bc54a-129"></span></span>

<span data-ttu-id="bc54a-p106">手順 3 でスクリプトは、メールボックスとユーザーの一覧については OneDrive のアカウントを検索するコンテンツの検索を作成します。テキスト ファイル、電子メール アドレスを入力するだけ、または電子メール アドレスの一覧を取得し、(手順 3 でスクリプトを保存するが、同じフォルダーにある) ファイルを保存する Windows PowerShell のコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p106">The script in Step 3 will create a Content Search to search the mailboxes and OneDrive accounts for a list of users. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="bc54a-132">ラントは、組織内のすべてのユーザーの電子メール アドレスのリストを取得し、という名前のテキスト ファイルに保存をすることができます、 [Exchange オンラインの PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)コマンドをここでは`Users.txt`です。</span><span class="sxs-lookup"><span data-stu-id="bc54a-132">Here's an [Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283) command that you can runt to get a list of email addresses for all users in your organization and save it to a text file named `Users.txt`.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

<span data-ttu-id="bc54a-p107">このコマンドを実行した後は、必ずファイルを開き、プロパティの名前を含むヘッダーを削除するのには`PrimarySmtpAddress`です。テキスト ファイルに、電子メール アドレスの一覧と、それ以外のものだけでは。電子メール アドレスの一覧の前後に、空白の行がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p107">After you run this command, be sure to open the file and remove the header that contains the property name,  `PrimarySmtpAddress`. The text file should just contain a list of email addresses, and nothing else. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a><span data-ttu-id="bc54a-136">手順 3: スクリプトを実行して作成し、検索を開始</span><span class="sxs-lookup"><span data-stu-id="bc54a-136">Step 3: Run the script to create and start the search</span></span>

<span data-ttu-id="bc54a-p108">この手順では、スクリプトを実行するときを次の情報を求めます。スクリプトを実行する前にこの情報を準備することを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p108">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="bc54a-139">**ユーザーの資格情報**のスクリプトは、ビジネスの Url の OneDrive を取得し、セキュリティへの接続を SharePoint Online にアクセスする資格情報を使用、&amp;リモート PowerShell でコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="bc54a-139">**Your user credentials** - The script will use your credentials to access SharePoint Online to get the OneDrive for Business URLs and to connect to the Security &amp; Compliance Center with remote PowerShell.</span></span> 
    
- <span data-ttu-id="bc54a-p109">**、個人用サイトのドメインの名前**が [個人用サイトのドメインは、組織内のビジネス ・ サイトのすべての OneDrive が含まれているドメインです。例では、個人用サイトのドメインの URL の場合、**https://contoso-my.sharepoint.com**を入力し、`contoso`とスクリプトの入力を求め、個人用サイトのドメインの名前です。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p109">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="bc54a-p110">**手順 2 からのテキスト ファイルのパス名**を手順 2 で作成したテキスト ファイルのパス名です。同じフォルダーには、テキスト ファイルやスクリプトが存在する場合は、テキスト ファイルの名前を入力します。それ以外の場合、テキスト ファイルの完全パス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p110">**Pathname of the text file from Step 2** - The pathname of the text file that you created in Step 2. If the text file and the script are located in the same folder, then enter the name of the text file. Otherwise, enter the complete pathname for the text file.</span></span> 
    
- <span data-ttu-id="bc54a-145">**コンテンツの検索の名前**のスクリプトによって作成されるコンテンツの検索の名前です。</span><span class="sxs-lookup"><span data-stu-id="bc54a-145">**Name of the Content Search** - The name of the Content Search that will be created by the script.</span></span> 
    
- <span data-ttu-id="bc54a-p111">**検索クエリ**でコンテンツの検索に使用される検索クエリが作成され、実行します。検索クエリの詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p111">**Search query** - The search query that will be used with the Content Search is created and run. For more information about search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>


<span data-ttu-id="bc54a-148">**このスクリプトを実行するには、以下の手順を実行します。**</span><span class="sxs-lookup"><span data-stu-id="bc54a-148">**To run the script:**</span></span>
    
1. <span data-ttu-id="bc54a-p112">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `SearchEXOOD4B.ps1`。手順 2 でユーザーの一覧を保存した同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p112">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchEXOOD4B.ps1`. Save the file to the same folder where you saved the list of users in Step 2.</span></span>
    
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

2. <span data-ttu-id="bc54a-151">Windows PowerShell を開き、手順 2 のスクリプトとユーザーの一覧を保存した場所のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-151">Open Windows PowerShell and go to the folder where you saved the script and the list of users from Step 2.</span></span>
    
3. <span data-ttu-id="bc54a-152">スクリプトを起動します。例えば：</span><span class="sxs-lookup"><span data-stu-id="bc54a-152">Start the script; for example:</span></span>
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. <span data-ttu-id="bc54a-153">資格情報のダイアログ ボックスが表示されたらの電子メール アドレスとパスワードを入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc54a-153">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
    
5. <span data-ttu-id="bc54a-p113">以下のスクリプトによってメッセージが表示されたら、情報を入力します。個々 の情報を入力し、 **Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p113">Enter following information when prompted by the script. Type each piece of information and then press **Enter**.</span></span>
    
    - <span data-ttu-id="bc54a-156">自分の個人用サイトのドメインの名前。</span><span class="sxs-lookup"><span data-stu-id="bc54a-156">The name of your MySite domain.</span></span> 
    
    - <span data-ttu-id="bc54a-157">ユーザーの一覧を含むテキスト ファイルのパス名です。</span><span class="sxs-lookup"><span data-stu-id="bc54a-157">The pathname of the text file that contains the list of users.</span></span>
    
    - <span data-ttu-id="bc54a-158">コンテンツ検索のための名前です。</span><span class="sxs-lookup"><span data-stu-id="bc54a-158">A name for the Content Search.</span></span>
    
    - <span data-ttu-id="bc54a-159">検索クエリ (コンテンツの場所のすべてのアイテムを取得する場合は空白) です。</span><span class="sxs-lookup"><span data-stu-id="bc54a-159">The search query (leave this blank to return all items in the content locations).</span></span>
    
    <span data-ttu-id="bc54a-p114">スクリプトは、ビジネス サイトの各 OneDrive の Url を取得を作成し、検索を開始します。検索の統計情報と、結果を表示するには、セキュリティとコンプライアンス センター PowerShell で**Get ComplianceSearch**コマンドレットを実行することができますか、またはセキュリティの**コンテンツの検索**ページに移動することができます&amp;を表示するのにはコンプライアンス センター検索について説明します。</span><span class="sxs-lookup"><span data-stu-id="bc54a-p114">The script gets the URLs for each OneDrive for Business site and then creates and starts the search. You can either run the **Get-ComplianceSearch** cmdlet in Security & Compliance Center PowerShell to display the search statistics and results, or you can go to the **Content search** page in the Security &amp; Compliance Center to view information about the search.</span></span> 
