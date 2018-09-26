---
title: スクリプトを使用して、Office 365 のセキュリティで電子的証拠開示の場合は、保留リストにユーザーを追加するのには&amp;コンプライアンス センター
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/23/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
description: メールボックスをすばやく追加するのにはスクリプトを実行し、Office 365 のセキュリティ、電子的証拠開示のケースに関連付けられている新しい保留リストにサイトのビジネスのための OneDrive&amp;コンプライアンス センターです。
ms.openlocfilehash: 2c93deb14bc8c1f89dab7bb054d2e94db06cfbd5
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038260"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a>スクリプトを使用して、Office 365 のセキュリティで電子的証拠開示の場合は、保留リストにユーザーを追加するのには&amp;コンプライアンス センター

Office 365 のセキュリティ&amp;を使用する Windows PowerShell コマンドレットの多くを作成し、電子的証拠開示のサポート案件の管理に関連する、時間のかかるタスクを自動化するコンプライアンス センターが用意されています。現時点では、電子的証拠開示 case ツールを使用してセキュリティの&amp;保留中の多数のコンテンツの場所の管理者を配置するコンプライアンス センターには、時間と準備します。たとえば、保留リストを作成する前にビジネス サイトを保留にするのには、各 OneDrive の URL を収集する必要があります。保留リストに配置する各ユーザーの保留リストに自分のメールボックスとのビジネス サイトの OneDrive を追加する必要があります。セキュリティの将来のリリースで&amp;コンプライアンス センターでは、これは取得を簡単にします。それまでは、このプロセスを自動化するのにこの資料のスクリプトを使用することができます。
  
スクリプトの入力を求め、組織の個人用サイトのドメインの名前 (たとえば、 **contoso 社**の URL にhttps://contoso-my.sharepoint.com)ケースに関連付けられた電子的証拠開示、既存のケースの名前、新しい保留リストの名前を必要なユーザーの電子メール アドレスの一覧保留、およびクエリ ベースの保留リストを作成する場合に使用する検索クエリに配置します。スクリプトは、一覧内の各ユーザーのビジネス サイトの OneDrive の URL を取得し、新しい保留中が作成され、リスト内の各ユーザーのビジネス サイトの保留リストに、メールボックスおよび OneDrive を追加します。スクリプトには、新しい保留リストに関する情報を含むログ ファイルも生成されます。 
  
この作業を行うための手順を以下に示します。
  
[手順 1: SharePoint Online 管理シェルをインストールする](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[手順 2: は、ユーザーの一覧を生成します。](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[保留リストを作成し、ユーザーを追加するスクリプトを実行する手順 3。](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a>はじめに

- セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;コンプライアンス センターと SharePoint Online グローバル管理者は、手順 3 でスクリプトを実行します。詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。
    
- セキュリティ、電子的証拠開示のケースに関連付けられている保留リストに最大 1,000 個のメールボックスと 100 のサイトを追加することができます&amp;コンプライアンス センターです。保留にするすべてのユーザーは、ビジネス サイトの OneDrive を持っていることと仮定した場合は、この資料のスクリプトを使用して保留リストに最大 100 のユーザーを追加できます。 
    
- 手順 2 と手順 3 で同じフォルダーにスクリプトで作成したユーザーの一覧を保存しておいてください。容易にできるようにスクリプトを実行します。
    
- スクリプトは、既存のサポート案件に関連付けられている新しい保留リストにユーザーの一覧を追加します。スクリプトを実行する前に、大文字と小文字の保留リストに関連付けることが作成されたことを確認します。
    
- スクリプトには、最低限のエラー処理が含まれています。その主な目的は、メールボックスを迅速かつ容易に配置して、上の各ユーザーのビジネス サイトの OneDrive を保持します。
    
- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。

## <a name="step-1-install-the-sharepoint-online-management-shell"></a>手順 1: SharePoint Online 管理シェルをインストールする

最初のステップでは、ローカル コンピューターにまだインストールされていない場合は、SharePoint のオンライン管理シェルをインストールするのには。ここでシェルを使用する必要はありませんが、手順 3 で実行するスクリプトに必要な必須コンポーネントが含まれているために、それをインストールする必要です。これらの前提条件は、SharePoint Online ビジネス サイトの OneDrive の Url を取得すると通信するスクリプトを使用できます。
  
[SharePoint のオンライン管理シェル Windows PowerShell 環境を設定](https://go.microsoft.com/fwlink/p/?LinkID=286318)するのには移動し、ローカル コンピューター上の SharePoint のオンライン管理シェルをインストールするには、手順 1 と手順 2 を実行します。 

## <a name="step-2-generate-a-list-of-users"></a>手順 2: は、ユーザーの一覧を生成します。
<a name="step2"> </a>

手順 3 でスクリプトに関連付けられている、電子的証拠開示の場合と、追加メールボックスおよび OneDrive の保留リストにユーザーの一覧のビジネス サイトの保留リストが作成されます。テキスト ファイル、電子メール アドレスを入力するだけ、または電子メール アドレスの一覧を取得し、(手順 3 でスクリプトを保存するが、同じフォルダーにある) ファイルを保存する Windows PowerShell のコマンドを実行することができます。
  
PowerShell コマンド (つまり、Exchange Online 組織に接続されている、リモート PowerShell を使用して実行するには) は、HoldUsers.txt という名前の組織内のすべてのユーザーの電子メール アドレスのリストを取得し、テキスト ファイルに保存します。
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

後でこのコマンドを実行して、テキスト ファイルを開き、プロパティの名前を含むヘッダーを削除する`PrimarySmtpAddress`。手順 3 で作成する保留リストに追加するユーザーを除くすべての電子メール アドレスを削除します。電子メール アドレスの一覧の前後に、空白の行がないことを確認します。
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a>保留リストを作成し、ユーザーを追加するスクリプトを実行する手順 3。
<a name="step3"> </a>

この手順では、スクリプトを実行するときを次の情報を求めます。スクリプトを実行する前にこの情報を準備することを確認します。
  
- **ユーザーの資格情報**でスクリプトは、セキュリティへの接続に資格情報を使用&amp;リモート PowerShell でコンプライアンス センターです。ビジネスの Url をユーザーの一覧については、OneDrive を取得するのには SharePoint Online にアクセスするのにもこれらの資格情報を使用します。
    
- **、個人用サイトのドメインの名前**が [個人用サイトのドメインは、組織内のビジネス ・ サイトのすべての OneDrive が含まれているドメインです。例では、個人用サイトのドメインの URL の場合、**https://contoso-my.sharepoint.com**を入力し、`contoso`とスクリプトの入力を求め、個人用サイトのドメインの名前です。 
    
- **大文字と小文字の名前**が既存のケースの名前です。スクリプトでは、このサポート案件に関連付けられている新しい保留リストを作成します。
    
- **保留リストの名前**のスクリプトが作成され、指定された大文字と小文字を関連付ける保留リストの名前です。
    
- **クエリ ベースの検索クエリを保持**クエリ ベースの保留リストを作成するには、保留中の指定した検索条件に一致するコンテンツのみが配置されるようにします。保留中のすべてのコンテンツを配置するには、だけで**Enter**キーを押して検索クエリのダイアログ ボックスが表示されたら。 
    
- **保留リストを有効にするかどうか**のスクリプトを作成または有効にせず、保留リストを作成するスクリプトを持つことができますを保留リストを有効にすることができます。保留リストを有効にするスクリプトをお持ちでない場合を有効にできます、セキュリティの&amp;コンプライアンス センターまたは次の PowerShell コマンドを実行することによって。 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- **ユーザーのリストを含むテキスト ファイルの名前**を保留リストに追加するユーザーの一覧が含まれている手順 2 からテキスト ファイルの名前です。このファイルはスクリプトと同じフォルダーにある場合だけ (たとえば、HoldUsers.txt) ファイルの名前を入力します。テキスト ファイルが別のフォルダー内にある場合は、ファイルの完全パス名を入力します。
    
スクリプトは画面を表示する情報を収集した後、最後に、新しい保留リストを作成し、ユーザーを追加するスクリプトを実行します。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `AddUsersToHold.ps1`。
    
  ```
  #script begin
  " " 
  write-host "***********************************************"
  write-host "   Office 365 Security &amp; Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
  write-host "***********************************************"
  " " 
  # Get user credentials &amp; Connect to Office 365 SCC, SPO
  $credentials = Get-Credential -Message "Specify your credentials to connect to the Office 365 Security &amp; Compliance Center and SharePoint Online"
  $s = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://ps.compliance.protection.outlook.com/powershell-liveid" -Credential $credentials -Authentication Basic -AllowRedirection -SessionOption (New-PSSessionOption -SkipCACheck -SkipCNCheck -SkipRevocationCheck)
  $a = Import-PSSession $s -AllowClobber
      if (!$s)
      {
          Write-Error "Couldn't create PowerShell session."
          return;
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
          Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: http://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
          return;
      }
  }
  if (!$spCreds)
  {
      $spCreds = New-Object Microsoft.SharePoint.Client.SharePointOnlineCredentials($credentials.UserName, $credentials.Password)
  }
  # Get the user's MySite domain name. We use this to create the admin URL and root URL for OneDrive for Business
  ""
  $mySiteDomain = Read-Host "Enter the name of your organization's MySite domain. For example, 'contoso' for 'https://contoso-my.sharepoint.com'"
  ""
  # Get other required information
  do{
  $casename = Read-Host "Enter the name of the case"
  $caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
  if($caseexists -ne 'True')
  {""
  write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
  ""}
  }While($caseexists -ne 'True')
  ""
  do{
  $holdName = Read-Host "Enter the name of the new hold"
  $holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
  if($holdexists -eq 'True')
  {""
  write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
  ""}
  }While($holdexists -eq 'True')
  ""
  $holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
  ""
  $holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
  do{
  ""
  $inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
  ""
  $fileexists = test-path -path $inputfile
  if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
  }while($fileexists -ne 'True')
  #Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
      #in the list are unique.
    [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
    [int]$dupl = $emailAddresses.count
    [array]$emailAddresses = $emailAddresses | select-object -unique
    $dupl -= $emailAddresses.count
  #Validate email addresses so the hold creation does not run in to an error.
  if($emailaddresses.count -gt 0){
  write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
  ""
  Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
  ""
  $finallist =@()
  foreach($emailAddress in $emailAddresses)
  {
  if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
  {$finallist += $emailaddress}
  else {"Unable to find the user $emailaddress"
  [array]$excludedlist += $emailaddress}
  }
  ""
  #find user's OneDrive Site URL using email address
  Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow
  ""
  $AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
  $mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
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
  $urls = @()
  foreach($emailAddress in $emailAddresses)
  {
        try{
          $prop = $UserProfileService.GetUserProfileByName("i:0#.f|membership|$emailAddress") | Where-Object { $_.Name -eq "PersonalSpace" }
          $url = $prop.values[0].value
        if($url -ne $null){
          $furl = $mySiteUrlRoot + $url
          $urls += $furl
          Write-Host "- $emailAddress => $furl"
        [array]$ODadded += $furl}
    else{    
          Write-Warning "Couldn't locate OneDrive for $emailAddress"
        [array]$ODExluded += $emailAddress
      }}
    catch { 
    Write-Warning "Could not locate OneDrive for $emailAddress"
    [array]$ODExluded += $emailAddress
    Continue }
  }
  if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
  ""
  Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
  if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
  }
  else{
  New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
  New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
  }
  ""
  }
  else {"No valid locations were identified. Therefore, the hold wasn't created."}
  #write log files (if needed)
  $newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
  $newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
  if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
  {
  Write-Host "Generating output files..." -foregroundColor Yellow
  if($ODAdded.count -gt 0){
  "OneDrive Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
  if($ODExluded.count -gt 0){ 
  "Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
  "================================" | add-content .\LocationsNotOnHold.txt
  $ODExluded | add-content .\LocationsNotOnHold.txt}
  if($finallist.count -gt 0){
  " " | add-content .\LocationsOnHold.txt
  "Exchange Locations" | add-content .\LocationsOnHold.txt
  "==================" | add-content .\LocationsOnHold.txt 
  $newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
  if($excludedlist.count -gt 0){
  " "| add-content .\LocationsNotOnHold.txt
  "Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
  "===============================" | add-content .\LocationsNotOnHold.txt
  $excludedlist | add-content .\LocationsNotOnHold.txt}
  $FormatEnumerationLimit=-1
  if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
  if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
  }
  }
  else {"The hold wasn't created because no valid entries were found in the text file."}
  ""
  Write-host "Script complete!" -foregroundColor Yellow
  ""
  #script end
  ```

2. ローカル コンピューターに Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。
    
3. スクリプトを実行します。例えば：
    
      ```
    .\AddUsersToHold.ps1
      ```

4. スクリプトによってユーザーの情報を入力します。
    
    スクリプトは、セキュリティとコンプライアンス センター PowerShell に接続して電子的証拠開示の場合は、新しい保留リストを作成し、リスト内のユーザーのメールボックスおよびビジネスのための OneDrive を追加します。場合、セキュリティで**電子的証拠開示**のページに進むことができます&amp;、新しい保留リストを表示するのにはコンプライアンス センターです。 
    
スクリプトが終了した後を実行している次のログ ファイルを作成し、スクリプトが格納されているフォルダーに保存します。
  
- **LocationsOnHold.txt** - には、ビジネス サイトに正常に配置スクリプトを保持するためには、メールボックスおよび OneDrive の一覧が含まれています。
    
- **LocationsNotOnHold.txt** - には、保留中のスクリプトが挿入されていないビジネス サイトのメールボックス、および OneDrive の一覧が含まれています。ユーザーが、メールボックスがビジネス サイトの OneDrive ではない場合、ユーザーが保留リストに配置されなかったビジネス サイトの OneDrive の一覧で含まれているは。
    
- **GetCaseHoldPolicy.txt** - には、新しい保留リストを作成した後、スクリプトが実行される新しい保留リストの**取得 CaseHoldPolicy**コマンドレットの出力が含まれています。このコマンドレットによって返される情報には、メールボックスとビジネス サイトの OneDrive が保留と保留リストを有効または無効にするかどうかに配置されたユーザーの一覧が含まれています。 
    
- **GetCaseHoldRule.txt** - には、新しい保留リストを作成した後、スクリプトが実行される新しい保留リストの**取得 CaseHoldRule**コマンドレットの出力が含まれています。このコマンドレットによって返される情報には、クエリ ベースの保留リストを作成するスクリプトを使用する場合、検索クエリが含まれています。 
