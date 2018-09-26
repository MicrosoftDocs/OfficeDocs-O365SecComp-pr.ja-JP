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
# <a name="use-a-script-to-add-users-to-a-hold-in-an-ediscovery-case-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="fe838-103">スクリプトを使用して、Office 365 のセキュリティで電子的証拠開示の場合は、保留リストにユーザーを追加するのには&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="fe838-103">Use a script to add users to a hold in an eDiscovery case in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="fe838-p101">Office 365 のセキュリティ&amp;を使用する Windows PowerShell コマンドレットの多くを作成し、電子的証拠開示のサポート案件の管理に関連する、時間のかかるタスクを自動化するコンプライアンス センターが用意されています。現時点では、電子的証拠開示 case ツールを使用してセキュリティの&amp;保留中の多数のコンテンツの場所の管理者を配置するコンプライアンス センターには、時間と準備します。たとえば、保留リストを作成する前にビジネス サイトを保留にするのには、各 OneDrive の URL を収集する必要があります。保留リストに配置する各ユーザーの保留リストに自分のメールボックスとのビジネス サイトの OneDrive を追加する必要があります。セキュリティの将来のリリースで&amp;コンプライアンス センターでは、これは取得を簡単にします。それまでは、このプロセスを自動化するのにこの資料のスクリプトを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fe838-p101">The Office 365 Security &amp; Compliance Center provides lots of Windows PowerShell cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases. Currently, using the eDiscovery case tool in the Security &amp; Compliance Center to place a large number of custodian content locations on hold takes time and preparation. For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold. Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold. In future releases of the Security &amp; Compliance Center, this will get easier to do. Until then, you can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="fe838-p102">スクリプトの入力を求め、組織の個人用サイトのドメインの名前 (たとえば、 **contoso 社**の URL にhttps://contoso-my.sharepoint.com)ケースに関連付けられた電子的証拠開示、既存のケースの名前、新しい保留リストの名前を必要なユーザーの電子メール アドレスの一覧保留、およびクエリ ベースの保留リストを作成する場合に使用する検索クエリに配置します。スクリプトは、一覧内の各ユーザーのビジネス サイトの OneDrive の URL を取得し、新しい保留中が作成され、リスト内の各ユーザーのビジネス サイトの保留リストに、メールボックスおよび OneDrive を追加します。スクリプトには、新しい保留リストに関する情報を含むログ ファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="fe838-p102">The script prompts you for the name of your organization's MySite domain (for example, **contoso** in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold. The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold. The script also generates log files that contain information about the new hold.</span></span> 
  
<span data-ttu-id="fe838-113">この作業を行うための手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="fe838-113">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="fe838-114">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="fe838-114">Step 1: Install the SharePoint Online Management Shell</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step1)
  
[<span data-ttu-id="fe838-115">手順 2: は、ユーザーの一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="fe838-115">Step 2: Generate a list of users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step2)
  
[<span data-ttu-id="fe838-116">保留リストを作成し、ユーザーを追加するスクリプトを実行する手順 3。</span><span class="sxs-lookup"><span data-stu-id="fe838-116">Step 3: Run the script to create a hold and add users</span></span>](use-a-script-to-add-users-to-a-hold-in-ediscovery.md#step3)
  
## <a name="before-you-begin"></a><span data-ttu-id="fe838-117">はじめに</span><span class="sxs-lookup"><span data-stu-id="fe838-117">Before you begin</span></span>

- <span data-ttu-id="fe838-p103">セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;コンプライアンス センターと SharePoint Online グローバル管理者は、手順 3 でスクリプトを実行します。詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="fe838-p103">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center and a SharePoint Online global administrator to run the script in Step 3. For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="fe838-p104">セキュリティ、電子的証拠開示のケースに関連付けられている保留リストに最大 1,000 個のメールボックスと 100 のサイトを追加することができます&amp;コンプライアンス センターです。保留にするすべてのユーザーは、ビジネス サイトの OneDrive を持っていることと仮定した場合は、この資料のスクリプトを使用して保留リストに最大 100 のユーザーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="fe838-p104">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security &amp; Compliance Center. Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span> 
    
- <span data-ttu-id="fe838-p105">手順 2 と手順 3 で同じフォルダーにスクリプトで作成したユーザーの一覧を保存しておいてください。容易にできるようにスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p105">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder. That will make it easier to run the script.</span></span>
    
- <span data-ttu-id="fe838-p106">スクリプトは、既存のサポート案件に関連付けられている新しい保留リストにユーザーの一覧を追加します。スクリプトを実行する前に、大文字と小文字の保留リストに関連付けることが作成されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p106">The script adds the list of users to a new hold that is associated with an existing case. Be sure the case that you want to associate the hold with is created before you run the script.</span></span>
    
- <span data-ttu-id="fe838-p107">スクリプトには、最低限のエラー処理が含まれています。その主な目的は、メールボックスを迅速かつ容易に配置して、上の各ユーザーのビジネス サイトの OneDrive を保持します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p107">The script includes minimal error handling. Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>
    
- <span data-ttu-id="fe838-p108">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="fe838-p108">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="fe838-133">手順 1: SharePoint Online 管理シェルをインストールする</span><span class="sxs-lookup"><span data-stu-id="fe838-133">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="fe838-p109">最初のステップでは、ローカル コンピューターにまだインストールされていない場合は、SharePoint のオンライン管理シェルをインストールするのには。ここでシェルを使用する必要はありませんが、手順 3 で実行するスクリプトに必要な必須コンポーネントが含まれているために、それをインストールする必要です。これらの前提条件は、SharePoint Online ビジネス サイトの OneDrive の Url を取得すると通信するスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe838-p109">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer. You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3. These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="fe838-137">[SharePoint のオンライン管理シェル Windows PowerShell 環境を設定](https://go.microsoft.com/fwlink/p/?LinkID=286318)するのには移動し、ローカル コンピューター上の SharePoint のオンライン管理シェルをインストールするには、手順 1 と手順 2 を実行します。</span><span class="sxs-lookup"><span data-stu-id="fe838-137">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span> 

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="fe838-138">手順 2: は、ユーザーの一覧を生成します。</span><span class="sxs-lookup"><span data-stu-id="fe838-138">Step 2: Generate a list of users</span></span>
<span data-ttu-id="fe838-139"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="fe838-139"></span></span>

<span data-ttu-id="fe838-p110">手順 3 でスクリプトに関連付けられている、電子的証拠開示の場合と、追加メールボックスおよび OneDrive の保留リストにユーザーの一覧のビジネス サイトの保留リストが作成されます。テキスト ファイル、電子メール アドレスを入力するだけ、または電子メール アドレスの一覧を取得し、(手順 3 でスクリプトを保存するが、同じフォルダーにある) ファイルを保存する Windows PowerShell のコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="fe838-p110">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold. You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="fe838-142">PowerShell コマンド (つまり、Exchange Online 組織に接続されている、リモート PowerShell を使用して実行するには) は、HoldUsers.txt という名前の組織内のすべてのユーザーの電子メール アドレスのリストを取得し、テキスト ファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="fe838-142">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="fe838-p111">後でこのコマンドを実行して、テキスト ファイルを開き、プロパティの名前を含むヘッダーを削除する`PrimarySmtpAddress`。手順 3 で作成する保留リストに追加するユーザーを除くすべての電子メール アドレスを削除します。電子メール アドレスの一覧の前後に、空白の行がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p111">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`. Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3. Make sure there are no blank rows before or after the list of email addresses.</span></span>
  

  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="fe838-146">保留リストを作成し、ユーザーを追加するスクリプトを実行する手順 3。</span><span class="sxs-lookup"><span data-stu-id="fe838-146">Step 3: Run the script to create a hold and add users</span></span>
<span data-ttu-id="fe838-147"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="fe838-147"></span></span>

<span data-ttu-id="fe838-p112">この手順では、スクリプトを実行するときを次の情報を求めます。スクリプトを実行する前にこの情報を準備することを確認します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p112">When you run the script in this step, it will prompt you for the following information. Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="fe838-p113">**ユーザーの資格情報**でスクリプトは、セキュリティへの接続に資格情報を使用&amp;リモート PowerShell でコンプライアンス センターです。ビジネスの Url をユーザーの一覧については、OneDrive を取得するのには SharePoint Online にアクセスするのにもこれらの資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p113">**Your user credentials** - The script will use your credentials to connect to the Security &amp; Compliance Center with remote PowerShell. It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>
    
- <span data-ttu-id="fe838-p114">**、個人用サイトのドメインの名前**が [個人用サイトのドメインは、組織内のビジネス ・ サイトのすべての OneDrive が含まれているドメインです。例では、個人用サイトのドメインの URL の場合、**https://contoso-my.sharepoint.com**を入力し、`contoso`とスクリプトの入力を求め、個人用サイトのドメインの名前です。</span><span class="sxs-lookup"><span data-stu-id="fe838-p114">**Name of your MySite domain** - The MySite domain is the domain that contains all the OneDrive for Business sites in your organization. For example, if the URL for your MySite domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your MySite domain.</span></span> 
    
- <span data-ttu-id="fe838-p115">**大文字と小文字の名前**が既存のケースの名前です。スクリプトでは、このサポート案件に関連付けられている新しい保留リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p115">**Name of the case** - The name of an existing case. The script will create a new hold that is associated with this case.</span></span>
    
- <span data-ttu-id="fe838-156">**保留リストの名前**のスクリプトが作成され、指定された大文字と小文字を関連付ける保留リストの名前です。</span><span class="sxs-lookup"><span data-stu-id="fe838-156">**Name of the hold** - The name of the hold the script will create and associate with the specified case.</span></span>
    
- <span data-ttu-id="fe838-p116">**クエリ ベースの検索クエリを保持**クエリ ベースの保留リストを作成するには、保留中の指定した検索条件に一致するコンテンツのみが配置されるようにします。保留中のすべてのコンテンツを配置するには、だけで**Enter**キーを押して検索クエリのダイアログ ボックスが表示されたら。</span><span class="sxs-lookup"><span data-stu-id="fe838-p116">**Search query for a query-based hold** - You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold. To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span> 
    
- <span data-ttu-id="fe838-p117">**保留リストを有効にするかどうか**のスクリプトを作成または有効にせず、保留リストを作成するスクリプトを持つことができますを保留リストを有効にすることができます。保留リストを有効にするスクリプトをお持ちでない場合を有効にできます、セキュリティの&amp;コンプライアンス センターまたは次の PowerShell コマンドを実行することによって。</span><span class="sxs-lookup"><span data-stu-id="fe838-p117">**Whether or not to turn the hold on** - You can have the script turn the hold on after it's created or you can have the script create the hold without enabling it. If you don't have the script turn on the hold, you can turn it on later in the Security &amp; Compliance Center or by running the following PowerShell commands:</span></span> 
    
  ```
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="fe838-p118">**ユーザーのリストを含むテキスト ファイルの名前**を保留リストに追加するユーザーの一覧が含まれている手順 2 からテキスト ファイルの名前です。このファイルはスクリプトと同じフォルダーにある場合だけ (たとえば、HoldUsers.txt) ファイルの名前を入力します。テキスト ファイルが別のフォルダー内にある場合は、ファイルの完全パス名を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe838-p118">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold. If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt). If the text file is in another folder, type the full pathname of the file.</span></span>
    
<span data-ttu-id="fe838-164">スクリプトは画面を表示する情報を収集した後、最後に、新しい保留リストを作成し、ユーザーを追加するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fe838-164">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="fe838-165">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `AddUsersToHold.ps1`。</span><span class="sxs-lookup"><span data-stu-id="fe838-165">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `AddUsersToHold.ps1`.</span></span>
    
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

2. <span data-ttu-id="fe838-166">ローカル コンピューターに Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fe838-166">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>
    
3. <span data-ttu-id="fe838-167">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="fe838-167">Run the script; for example:</span></span>
    
      ```
    .\AddUsersToHold.ps1
      ```

4. <span data-ttu-id="fe838-168">スクリプトによってユーザーの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fe838-168">Enter the information that the script prompts you for.</span></span>
    
    <span data-ttu-id="fe838-p119">スクリプトは、セキュリティとコンプライアンス センター PowerShell に接続して電子的証拠開示の場合は、新しい保留リストを作成し、リスト内のユーザーのメールボックスおよびビジネスのための OneDrive を追加します。場合、セキュリティで**電子的証拠開示**のページに進むことができます&amp;、新しい保留リストを表示するのにはコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="fe838-p119">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list. You can go to the case on the **eDiscovery** page in the Security &amp; Compliance Center to view the new hold.</span></span> 
    
<span data-ttu-id="fe838-171">スクリプトが終了した後を実行している次のログ ファイルを作成し、スクリプトが格納されているフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="fe838-171">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="fe838-172">**LocationsOnHold.txt** - には、ビジネス サイトに正常に配置スクリプトを保持するためには、メールボックスおよび OneDrive の一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe838-172">**LocationsOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>
    
- <span data-ttu-id="fe838-p120">**LocationsNotOnHold.txt** - には、保留中のスクリプトが挿入されていないビジネス サイトのメールボックス、および OneDrive の一覧が含まれています。ユーザーが、メールボックスがビジネス サイトの OneDrive ではない場合、ユーザーが保留リストに配置されなかったビジネス サイトの OneDrive の一覧で含まれているは。</span><span class="sxs-lookup"><span data-stu-id="fe838-p120">**LocationsNotOnHold.txt** - Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold. If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>
    
- <span data-ttu-id="fe838-p121">**GetCaseHoldPolicy.txt** - には、新しい保留リストを作成した後、スクリプトが実行される新しい保留リストの**取得 CaseHoldPolicy**コマンドレットの出力が含まれています。このコマンドレットによって返される情報には、メールボックスとビジネス サイトの OneDrive が保留と保留リストを有効または無効にするかどうかに配置されたユーザーの一覧が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe838-p121">**GetCaseHoldPolicy.txt** - Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold. The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 
    
- <span data-ttu-id="fe838-p122">**GetCaseHoldRule.txt** - には、新しい保留リストを作成した後、スクリプトが実行される新しい保留リストの**取得 CaseHoldRule**コマンドレットの出力が含まれています。このコマンドレットによって返される情報には、クエリ ベースの保留リストを作成するスクリプトを使用する場合、検索クエリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe838-p122">**GetCaseHoldRule.txt** - Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold. The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span> 
