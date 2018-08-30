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
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーの一覧を探す

Office 365 のセキュリティ&amp;コンプライアンス センターには、いくつかの時間がかかる電子的証拠開示に関連するタスクを自動化するための Windows PowerShell コマンドレットが用意されています。現在、コンテンツの検索を作成する、セキュリティで&amp;を検索するコンテンツの場所の管理者の数が多いコンプライアンス センターには、時間と準備します。検索を作成する前に、ビジネス サイトの各 OneDrive の URL を収集し、検索する各メールボックスと O の neDrive のビジネス サイトを追加する必要があります。将来のリリースでは、これが容易になります、セキュリティでは&amp;コンプライアンス センターです。それまでは、このプロセスを自動化するのにこの資料のスクリプトを使用することができます。このスクリプトの入力を求め、組織の個人用サイトのドメインの名前 (たとえば、 **contoso 社**の URL にhttps://contoso-my.sharepoint.com)、一連のユーザーの電子メール アドレスを使用するには、新しいコンテンツの検索、および検索クエリの名前。スクリプトがビジネスの URL の一覧で、ユーザーごとに、OneDrive を取得しを作成し、提供する検索クエリを使用して、ボックスの一覧で各ユーザーのビジネス サイトのメールボックスを検索するコンテンツの検索と OneDrive を開始します。 
  
## <a name="before-you-begin"></a>はじめに

- セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;コンプライアンス センターと SharePoint Online グローバル管理者は、手順 3 でスクリプトを実行します。
    
- 手順 2 と手順 3 で同じフォルダーにスクリプトで作成したユーザーの一覧を保存しておいてください。容易にできるようにスクリプトを実行します。
    
- スクリプトには、最低限のエラー処理が含まれています。主な目的は、迅速かつ容易に検索するメールボックスと OneDrive の各ユーザーのビジネス サイトです。
    
- このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft では、すべてを拒否する[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする
<a name="step1"> </a>

最初のステップでは、SharePoint のオンライン管理シェルをインストールします。ここでシェルを使用する必要はありませんが、手順 3 で実行するスクリプトに必要な必須コンポーネントが含まれているために、それをインストールする必要です。これらの前提条件は、SharePoint Online ビジネス サイトの OneDrive の Url を取得すると通信するスクリプトを使用できます。
  
[SharePoint のオンライン管理シェル Windows PowerShell 環境の設定](https://go.microsoft.com/fwlink/p/?LinkID=286318)に移動し、SharePoint のオンライン管理シェルをインストールするには、ステップ 1 とステップ 2 を実行します。
  
## <a name="step-2-generate-a-list-of-users"></a>手順 2: は、ユーザーの一覧を生成します。
<a name="step2"> </a>

手順 3 でスクリプトは、メールボックスとユーザーの一覧については OneDrive のアカウントを検索するコンテンツの検索を作成します。テキスト ファイル、電子メール アドレスを入力するだけ、または電子メール アドレスの一覧を取得し、(手順 3 でスクリプトを保存するが、同じフォルダーにある) ファイルを保存する Windows PowerShell のコマンドを実行することができます。
  
ラントは、組織内のすべてのユーザーの電子メール アドレスのリストを取得し、という名前のテキスト ファイルに保存をすることができます、 [Exchange オンラインの PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)コマンドをここでは`Users.txt`です。 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

このコマンドを実行した後は、必ずファイルを開き、プロパティの名前を含むヘッダーを削除するのには`PrimarySmtpAddress`です。テキスト ファイルに、電子メール アドレスの一覧と、それ以外のものだけでは。電子メール アドレスの一覧の前後に、空白の行がないことを確認します。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>手順 3: スクリプトを実行して作成し、検索を開始

この手順では、スクリプトを実行するときを次の情報を求めます。スクリプトを実行する前にこの情報を準備することを確認します。
  
- **ユーザーの資格情報**のスクリプトは、ビジネスの Url の OneDrive を取得し、セキュリティへの接続を SharePoint Online にアクセスする資格情報を使用、&amp;リモート PowerShell でコンプライアンス センターです。 
    
- **、個人用サイトのドメインの名前**が [個人用サイトのドメインは、組織内のビジネス ・ サイトのすべての OneDrive が含まれているドメインです。例では、個人用サイトのドメインの URL の場合、**https://contoso-my.sharepoint.com**を入力し、`contoso`とスクリプトの入力を求め、個人用サイトのドメインの名前です。 
    
- **手順 2 からのテキスト ファイルのパス名**を手順 2 で作成したテキスト ファイルのパス名です。同じフォルダーには、テキスト ファイルやスクリプトが存在する場合は、テキスト ファイルの名前を入力します。それ以外の場合、テキスト ファイルの完全パス名を入力します。 
    
- **コンテンツの検索の名前**のスクリプトによって作成されるコンテンツの検索の名前です。 
    
- **検索クエリ**でコンテンツの検索に使用される検索クエリが作成され、実行します。検索クエリの詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。


**このスクリプトを実行するには、以下の手順を実行します。**
    
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `SearchEXOOD4B.ps1`。手順 2 でユーザーの一覧を保存した同じフォルダーにファイルを保存します。
    
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

2. Windows PowerShell を開き、手順 2 のスクリプトとユーザーの一覧を保存した場所のフォルダーに移動します。
    
3. スクリプトを起動します。例えば：
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. 資格情報のダイアログ ボックスが表示されたらの電子メール アドレスとパスワードを入力し、し、[ **OK**] をクリックします。 
    
5. 以下のスクリプトによってメッセージが表示されたら、情報を入力します。個々 の情報を入力し、 **Enter**キーを押します。
    
    - 自分の個人用サイトのドメインの名前。 
    
    - ユーザーの一覧を含むテキスト ファイルのパス名です。
    
    - コンテンツ検索のための名前です。
    
    - 検索クエリ (コンテンツの場所のすべてのアイテムを取得する場合は空白) です。
    
    スクリプトは、ビジネス サイトの各 OneDrive の Url を取得を作成し、検索を開始します。検索の統計情報と、結果を表示するには、セキュリティとコンプライアンス センター PowerShell で**Get ComplianceSearch**コマンドレットを実行することができますか、またはセキュリティの**コンテンツの検索**ページに移動することができます&amp;を表示するのにはコンプライアンス センター検索について説明します。 
