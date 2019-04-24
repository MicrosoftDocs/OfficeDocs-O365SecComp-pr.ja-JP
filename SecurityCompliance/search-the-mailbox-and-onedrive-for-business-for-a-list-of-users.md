---
title: コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーのリストを探す
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/3/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 5f4f8206-2d6a-4cb2-bbc6-7a0698703cc0
description: コンテンツ検索とこの記事のスクリプトを使用して、ユーザーのグループのメールボックスと OneDrive for business サイトを検索します。
ms.openlocfilehash: 2f0954bf7822ca6c82165ad20b2c732ab0594257
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32260935"
---
# <a name="use-content-search-to-search-the-mailbox-and-onedrive-for-business-site-for-a-list-of-users"></a>コンテンツ検索を使用してメールボックスと OneDrive for Business サイトでユーザーのリストを探す

Security & コンプライアンスセンターでは、時間がかかる電子情報開示関連のタスクを自動化するための Windows PowerShell コマンドレットが多数提供されています。 現時点では、セキュリティ & コンプライアンスセンターでコンテンツ検索を作成して多数の保管担当者コンテンツの場所を検索すると、時間と準備がかかります。 検索を作成する前に、各 OneDrive for business サイトの URL を収集し、ビジネスサイト用の各メールボックスと O nedrive を検索に追加する必要があります。 今後のリリースでは、セキュリティ & コンプライアンスセンターでの作業が容易になります。 その後、この記事のスクリプトを使用してこのプロセスを自動化できます。 このスクリプトは、組織の個人用サイトのドメイン名 (たとえば、URL https://contoso-my.sharepoint.com)内の**contoso** 、ユーザーの電子メールアドレスのリスト、新しいコンテンツ検索の名前、使用する検索クエリ) の入力を求めます。 このスクリプトは、リスト内の各ユーザーの OneDrive for business URL を取得し、ユーザーが指定した検索クエリを使用して、リスト内の各ユーザーのメールボックスと onedrive for business サイトを検索するコンテンツ検索を作成して開始します。 
  
## <a name="before-you-begin"></a>始める前に

- 手順3でスクリプトを実行するには、Security & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。また、SharePoint Online のグローバル管理者である必要があります。
    
- 手順2で作成したユーザーの一覧と、手順3のスクリプトを同じフォルダーに保存するようにしてください。 これにより、スクリプトをより簡単に実行できるようになります。
    
- スクリプトには、最小限のエラー処理が含まれています。 主な目的は、各ユーザーのメールボックスと OneDrive for business サイトをすばやく簡単に検索することです。
    
- このトピックに記載されているサンプルスクリプトは、Microsoft 標準サポートプログラムまたはサービスではサポートされていません。 サンプル スクリプトは現状のまま提供され、いかなる保証も伴いません。 Microsoft は、すべての[https://go.microsoft.com/fwlink/p/?LinkId=517283](https://go.microsoft.com/fwlink/p/?LinkId=517283)mplied 保証を含め、商品性の黙示的な保証または特定の目的に対する適合性を含むすべての保証を放棄します。 サンプル スクリプトおよびドキュメントの使用または実行の結果として生じるリスクはすべてお客様の責任です。 サンプル スクリプトおよびドキュメントを使用したこと、または使用できなかったことに伴って生じるいかなる損害 (業務利益の損失、業務の中断、業務情報の損失、金銭上の損失、その他一切の損害) についても、Microsoft、Microsoft に帰属する作者、スクリプトの作成、製造、または納入に関与したその他のすべての人員は、いかなる場合も責めを負わないものとします。
    
## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする
<a name="step1"> </a>

最初の手順として、SharePoint Online 管理シェルをインストールします。 この手順でシェルを使用する必要はありませんが、手順3で実行するスクリプトに必要な前提条件が含まれているためインストールする必要があります。 これらの前提条件によって、スクリプトは SharePoint Online と通信して、OneDrive for business サイトの url を取得できます。
  
「 [sharepoint online 管理シェル Windows PowerShell 環境をセットアップ](https://go.microsoft.com/fwlink/p/?LinkID=286318)する」に移動し、手順1と手順2を実行して、sharepoint online 管理シェルをインストールします。
  
## <a name="step-2-generate-a-list-of-users"></a>手順 2: ユーザーのリストを生成する
<a name="step2"> </a>

手順3のスクリプトは、メールボックスと OneDrive アカウントでユーザーのリストを検索するコンテンツ検索を作成します。 テキストファイルに電子メールアドレスを入力することも、Windows PowerShell でコマンドを実行して電子メールアドレスの一覧を取得し、それをファイルに保存することもできます (手順3でスクリプトを保存するのと同じフォルダーに格納されます)。
  
次の[Exchange Online の PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=517283)コマンドでは、を実行して、組織内のすべてのユーザーの電子メールアドレスの一覧を取得し、それを`Users.txt`という名前のテキストファイルに保存することができます。 
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > Users.txt
```

このコマンドを実行した後、必ずファイルを開いて、プロパティ名を`PrimarySmtpAddress`含むヘッダーを削除してください。 テキストファイルには、電子メールアドレスのリストのみを含める必要があります。それ以外の場合は何も指定しないでください。 電子メールアドレスのリストの前または後に空白行がないことを確認します。
  
## <a name="step-3-run-the-script-to-create-and-start-the-search"></a>手順 3: スクリプトを実行して検索を作成および開始する

この手順でスクリプトを実行すると、次の情報を入力するように求めるメッセージが表示されます。 スクリプトを実行する前に、この情報を用意しておいてください。
  
- **ユーザーの資格情報**-スクリプトは、自分の資格情報を使用して SharePoint Online にアクセスして、OneDrive for business の url を取得し、リモート PowerShell を使用して Security & コンプライアンスセンターに接続します。 
    
- **個人用サイトのドメインの名前**-個人用サイトのドメインは、組織内のすべての OneDrive for business サイトを含むドメインです。 たとえば、個人用サイトのドメインの URL がの場合**https://contoso-my.sharepoint.com**は、スクリプトによっ`contoso`て、個人用サイトのドメインの名前を入力するように求めるメッセージが表示されます。 
    
- **手順2のテキストファイルのパス名**。手順2で作成したテキストファイルのパス名。 テキストファイルとスクリプトが同じフォルダーにある場合は、テキストファイルの名前を入力します。 それ以外の場合は、テキストファイルの完全なパス名を入力します。 
    
- **コンテンツ検索の名前**-スクリプトによって作成されるコンテンツ検索の名前。 
    
- **検索クエリ**-コンテンツ検索と共に使用される検索クエリが作成され、実行されます。 検索クエリの詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。


**このスクリプトを実行するには、以下の手順を実行します。**
    
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `SearchEXOOD4B.ps1`のようになります。 手順2でユーザーのリストを保存したのと同じフォルダーにファイルを保存します。
    
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

2. Windows PowerShell を開き、スクリプトを保存したフォルダーおよび手順2でユーザーのリストに移動します。
    
3. スクリプトを開始します。例えば：
    
    ```
    .\SearchEXOOD4B.ps1
    ```

4. 資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。 
    
5. スクリプトによってプロンプトが表示されたら、次の情報を入力します。 各情報を入力し、enter キー **** を押します。
    
    - 個人用サイトのドメインの名前。 
    
    - ユーザーのリストを含むテキストファイルのパス名。
    
    - コンテンツ検索の名前を指定します。
    
    - 検索クエリ (空白のままにすると、コンテンツの場所にあるすべてのアイテムが返されます)。
    
    このスクリプトは、各 OneDrive for business サイトの url を取得し、検索を作成して開始します。 security & コンプライアンスセンターの PowerShell で**new-compliancesearch**コマンドレットを実行して、検索の統計情報と結果を表示するか、セキュリティ & コンプライアンスセンターの**コンテンツ検索**ページに移動して情報を表示することができます。検索について。 
