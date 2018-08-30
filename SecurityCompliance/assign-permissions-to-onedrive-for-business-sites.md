---
title: OneDrive for Business サイトに対する電子情報開示のアクセス許可を割り当てる
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/27/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 422858ff-917b-46d4-9e5b-3397f60eee4d
description: SharePoint Online の電子情報開示センターを使用するには、特定のキーワード、機密情報、およびその他の検索条件を組織内のビジネス サイトのすべての OneDrive を検索します。組織内の各ユーザーのそれぞれの OneDrive という名前のサイト コレクション内にある、ビジネス サイトの所有者ではhttps://domain-my.sharepoint.comです。既定では、Office 365 のグローバル管理者またはコンプライアンス マネージャーはビジネス サイトの任意の OneDrive を検索するのには SharePoint Online での電子情報開示センターを使用できません。検索するには、ビジネス サイトの管理者またはコンプライアンス担当マネージャー、OneDrive はビジネス サイトには、その OneDrive のサイト コレクションの管理者である必要があります。
ms.openlocfilehash: 48f84dfe21f0f99913ba2c27123d6c0e1f8bc03f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532171"
---
# <a name="assign-ediscovery-permissions-to-onedrive-for-business-sites"></a><span data-ttu-id="16c25-106">OneDrive for Business サイトに対する電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="16c25-106">Assign eDiscovery permissions to OneDrive for Business sites</span></span>

<span data-ttu-id="16c25-p102">SharePoint Online の電子情報開示センターを使用するには、特定のキーワード、機密情報、およびその他の検索条件を組織内のビジネス サイトのすべての OneDrive を検索します。組織内の各ユーザーのそれぞれの OneDrive という名前のサイト コレクション内にある、ビジネス サイトの所有者ではhttps://domain-my.sharepoint.comです。既定では、Office 365 のグローバル管理者またはコンプライアンス マネージャーはビジネス サイトの任意の OneDrive を検索するのには SharePoint Online での電子情報開示センターを使用できません。検索するには、ビジネス サイトの管理者またはコンプライアンス担当マネージャー、OneDrive はビジネス サイトには、その OneDrive のサイト コレクションの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="16c25-p102">You can use the eDiscovery Center in SharePoint Online to search all OneDrive for Business sites in your organization for certain keywords, sensitive information, and other search criteria. Each user in your organization is the owner of their OneDrive for Business site, which is located in the site collection named https://domain-my.sharepoint.com. By default, an Office 365 global administrator or compliance manager can't use the eDiscovery Center in SharePoint Online to search any OneDrive for Business sites. To search a OneDrive for Business site, administrators or compliance managers must be a site collection administrator for that OneDrive for Business site.</span></span> 
  
<span data-ttu-id="16c25-111">この資料では、管理者やコンプライアンス管理者にビジネス サイトのすべての OneDrive のサイト コレクションの管理者、組織内の手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="16c25-111">This article guides you through the steps to make an administrator or compliance manager a site collection administrator for every OneDrive for Business site in your organization.</span></span> 
  
<span data-ttu-id="16c25-112">ビジネス サイトのサイト コレクションの管理者として OneDrive からのユーザーを削除するのには手順 3 でスクリプトの修正を含む、この資料のスクリプトの使用に関するヒントの[詳細について](#more-information)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="16c25-112">See the [More information](#more-information) section for tips about using the script in this article, including revising the script in Step 3 to remove a user as a site collection administrator from OneDrive for Business sites.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="16c25-113">はじめに</span><span class="sxs-lookup"><span data-stu-id="16c25-113">Before you begin</span></span>

- <span data-ttu-id="16c25-p103">SharePoint Online 管理シェルをインストールします。詳細については、「[SharePoint Online 管理シェル Windows PowerShell 環境を設定する](https://go.microsoft.com/fwlink/p/?LinkID=286318)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16c25-p103">Install the SharePoint Online Management Shell. For information, see [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318).</span></span>
    
- <span data-ttu-id="16c25-116">ユーザーに割り当てる、サイト コレクションの管理者として、組織内のビジネス ・ サイトの任意の OneDrive をするたびに手順 3 でスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="16c25-116">Run the script in Step 3 each time you want to assign a user as a site collection administrator to any OneDrive for Business sites in your organization.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="16c25-p104">管理者またはコンプライアンス ビジネス サイトがビジネス ドキュメント ライブラリのユーザーの OneDrive を開くし、所有者と同じタスクを実行する OneDrive のサイト コレクションの管理者であるマネージャーです。割り当てられているアクセス許可の電子的証拠開示 OneDrive、組織内のビジネス サイトのユーザーを監視し、コントロールが重要です。</span><span class="sxs-lookup"><span data-stu-id="16c25-p104">An administrator or compliance manager who is a site collection administrator for OneDrive for Business sites can open users' OneDrive for Business document libraries and perform the same tasks as the owner. It's important to control and monitor who has been assigned eDiscovery permissions to OneDrive for Business sites in your organization.</span></span> 
  
- <span data-ttu-id="16c25-p105">この資料に記載されているサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。</span><span class="sxs-lookup"><span data-stu-id="16c25-p105">The sample script provided in this article isn't supported under any Microsoft standard support program or service. The sample script is provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample script and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the script be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample script or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-collect-a-list-of-all-onedrive-for-business-sites"></a><span data-ttu-id="16c25-124">手順 1: ビジネス サイトのすべての OneDrive の一覧を収集します。</span><span class="sxs-lookup"><span data-stu-id="16c25-124">Step 1: Collect a list of all OneDrive for Business sites</span></span>

<span data-ttu-id="16c25-p106">最初のステップでは、組織のビジネス サイトのすべての OneDrive のリストを作成します。手順については、[組織内のすべての OneDrive 場所のリストの作成](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)を参照してください。この資料では、このスクリプトは、OneDrive のすべてのサイトの一覧を含むテキスト ファイルを作成します。手順 3 で実行するスクリプトは、この手順で作成したテキスト ファイルに記載されているビジネス サイトの各 OneDrive に、サイト コレクションの管理者として指定したユーザーを割り当てます。次のテキストには、このファイル内のサイトのリストを書式設定する方法の例が用意されています。必要に応じて、このファイルからサイトを削除できます。</span><span class="sxs-lookup"><span data-stu-id="16c25-p106">The first step is to create a list of all OneDrive for Business sites in your organization. For instructions, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. The script that you run in Step 3 assigns a specified user as a site collection administrator to each OneDrive for Business site listed in the text file that's created in this step. The following text provides an example of how the list of sites in this file should be formatted. You can remove sites from this file if necessary.</span></span>

```
/personal/annb_contoso_onmicrosoft_com/
/personal/carolt_contoso_onmicrosoft_com/
/personal/esterv_contoso_onmicrosoft_com/
/personal/hollyh_contoso_onmicrosoft_com/
/personal/jeffl_contoso_onmicrosoft_com/
/personal/joeh_contoso_onmicrosoft_com/
/personal/kaia_contoso_onmicrosoft_com/
```

## <a name="step-2-connect-sharepoint-online-management-shell-to-your-organization"></a><span data-ttu-id="16c25-131">手順 2: SharePoint のオンライン管理シェルを組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="16c25-131">Step 2: Connect SharePoint Online Management Shell to your organization</span></span>

1. <span data-ttu-id="16c25-132">ローカル コンピューターで、SharePoint Online 管理シェルを開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="16c25-132">On your local computer, open the SharePoint Online Management Shell, and run the following command:</span></span>

    ```
    $credentials = Get-Credential
    ```

2. <span data-ttu-id="16c25-133">**[Windows PowerShell 資格情報の要求]** ダイアログ ボックスで、Office 365 グローバル管理者アカウントのユーザー名とパスワードを入力してから、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="16c25-133">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global administrator account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="16c25-134">次のコマンドを実行して、シェルを SharePoint Online 組織に接続します。</span><span class="sxs-lookup"><span data-stu-id="16c25-134">Run the following command to connect the Shell to your SharePoint Online organization:</span></span>
    
    ```
    Connect-SPOService -Url https://<your organization name>-admin.sharepoint.com -credential $credentials
    ```
   
4. <span data-ttu-id="16c25-135">SharePoint Online 組織に接続されたことを検証するために、次のコマンドを実行して、組織内のすべてのサイトのリストを取得します。</span><span class="sxs-lookup"><span data-stu-id="16c25-135">To verify that you are connected to your SharePoint Online organization, run the following command to get a list of all the sites in your organization:</span></span>
    
    ```
    Get-SPOSite
    ```

## <a name="step-3-assign-a-user-as-a-site-collection-administrator-to-onedrive-for-business-sites"></a><span data-ttu-id="16c25-136">手順 3: ユーザーを OneDrive for Business サイトのサイト コレクション管理者として割り当てる</span><span class="sxs-lookup"><span data-stu-id="16c25-136">Step 3: Assign a user as a site collection administrator to OneDrive for Business sites</span></span>

<span data-ttu-id="16c25-p107">次の手順では、サイト コレクション管理者は、組織内のビジネス サイトのすべての OneDrive で指定されたユーザーを割り当てるスクリプトを実行します。このスクリプトは、手順 1 で作成したビジネス サイトの OneDrive のリストを使用します。前述したように、ビジネス サイトのサイト コレクションの管理者として OneDrive にユーザーを割り当てるには使用するたびにこのスクリプトを実行する必要です。</span><span class="sxs-lookup"><span data-stu-id="16c25-p107">The next step is to run a script that assigns a specified user as a site collection administrator in every OneDrive for Business site in your organization. This script uses the list of OneDrive for Business sites that you created in Step 1. As previously stated, you have to run this script each time that you want to assign a user as a site collection administrator to OneDrive for Business sites.</span></span>
  
1. <span data-ttu-id="16c25-p108">次のテキストをテキスト ファイルに保存します。たとえば、OD4BAssignSCA.txt という名前のファイルに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="16c25-p108">Save the following text to a text file. For example, you could save it to a file named OD4BAssignSCA.txt.</span></span>

    ```
    # Start logging, so if this script fails, you can look at the last successful change,
    # remove any OneDrive for Business paths that worked it from the input file, and then rerun the script.

    Start-Transcript

    # URL for your organization's SPO admin service

    $AdminURI = "https://<your organization name>-admin.sharepoint.com"

    # User account for an Office 365 global admin in your organization

    $AdminAccount = "<global admin account>"

    # Compliance manager to be made site collection admin on each MySite

    $eDiscoveryUser = "<eDiscovery user account>"

    # URL for your tenant's MySite domain

    $MySitePrefix = "https://<your organization name>-my.sharepoint.com"

    # Where should we read the list of MySites?
    # This file should contain partial MySite paths formatted as follows, one per line; for example
    # /personal/junminh_contoso_onmicrosoft_com/

    $MySiteListFile = 'C:\Users\<youralias>\Desktop\ListOfMysites.txt'

    # Begin by connecting to the service
    Connect-SPOService -Url $AdminURI -Credential $AdminAccount

    # Make a reader for our list of MySites

    $reader = [System.IO.File]::OpenText($MySiteListFile)

    try {
      for(;;) {

    # Read a line
          $line = $reader.ReadLine()
    # Stop if it doesn't exist
          if ($line -eq $null) { break }

    # Turn the line into a complete SharePoint site path by merging $MySitePrefix
    # Formatted like this: "https://contoso-my.sharepoint.com"
    # ...with each partial MySite path in the file, formatted like this:
    # "/personal/junminh_contoso_onmicrosoft_com/"

          $fullsitepath = "$MySitePrefix$line"

    Write-Host "Operating on $fullsitepath "

    # We need to remove the last "/" to work around an issue.
    # "/personal/junminh_contoso_onmicrosoft_com/"
    # becomes "/personal/junminh_contoso_onmicrosoft_com"

    $fullsitepath = $fullsitepath.trimend("/")

    # Make the specified eDiscovery user a site collection admin on the OneDrive for Business site
    Write-Host "Making $eDiscoveryUser a Site Collection Admin"
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
      }
    }
    finally {
      $reader.Close()
    }
    Write-Host "Done!"
    Stop-Transcript
    Write-Host "Log written."
    ```

2. <span data-ttu-id="16c25-p109">スクリプト ファイルの先頭に次の変数を編集し、組織に固有の情報を使用します。次の例では、組織のドメイン名が contoso.onmicrosoft.com であると見なします。二重引用符で変数の値を囲むことを確認する ("")。</span><span class="sxs-lookup"><span data-stu-id="16c25-p109">Edit the following variables in the beginning of the script file, and use information that's specific to your organization. The following examples assume that the domain name of your organization is contoso.onmicrosoft.com. Be sure to surround the values for the variables with double-quotation marks (" ").</span></span>
    
    - <span data-ttu-id="16c25-145">**$AdminURI** - これの URI を指定、SharePoint Online の管理サービス、たとえば、 `"https://contoso-admin.sharepoint.com"`。</span><span class="sxs-lookup"><span data-stu-id="16c25-145">**$AdminURI** - This specifies the URI for your SharePoint Online admin service, for example,  `"https://contoso-admin.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="16c25-146">**$AdminAccount**のグローバル管理者アカウントで指定 Office 365 組織では、たとえば、 `"admin@contoso.onmicrosoft.com"`。</span><span class="sxs-lookup"><span data-stu-id="16c25-146">**$AdminAccount** - This specifies a global administrator account in your Office 365 organization, for example,  `"admin@contoso.onmicrosoft.com"`.</span></span>
    
    - <span data-ttu-id="16c25-147">**$eDiscoveryUser** - 管理者のユーザー アカウントを指定またはコンプライアンス マネージャーに割り当てられるサイト コレクション管理者は、組織内のビジネス サイトのすべての OneDrive の例では、 `"annb@contoso.onmicrosoft.com"`。</span><span class="sxs-lookup"><span data-stu-id="16c25-147">**$eDiscoveryUser** - This specifies the user account of an administrator or compliance manager who will be assigned as a site collection administrator for every OneDrive for Business site in your organization, for example,  `"annb@contoso.onmicrosoft.com"`.</span></span>
    
      > [!NOTE]
      > <span data-ttu-id="16c25-148">**$EDiscoveryUser**変数で指定されたユーザー アカウントを変更し、サイト コレクションの管理者として **$MySiteListFile**変数で指定されているビジネス サイトの OneDrive に別のユーザーを割り当てるには、スクリプトを再実行します。</span><span class="sxs-lookup"><span data-stu-id="16c25-148">Change the user account specified by the **$eDiscoveryUser** variable and re-run the script to assign a different user as a site collection administrator to the OneDrive for Business sites that are specified by the **$MySiteListFile** variable.</span></span> 
  
    - <span data-ttu-id="16c25-p110">**$MySitePrefix**これは、組織の個人用サイトのドメインの URL を指定します。これは、たとえば、ビジネスのサイト、組織内のすべての OneDrive が含まれるドメイン`"https://contoso-my.sharepoint.com"`。</span><span class="sxs-lookup"><span data-stu-id="16c25-p110">**$MySitePrefix**This specifies the URL for your organization's MySite domain. This is the domain that contains all the OneDrive for Business sites in your organization, for example,  `"https://contoso-my.sharepoint.com"`.</span></span>
    
    - <span data-ttu-id="16c25-p111">**$MySiteListFile**手順 1 で作成したテキスト ファイルの完全パスを指定します。たとえば、このファイルに、組織内のビジネス サイトの OneDrive の一覧が含まれています`'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`。単一引用符では、この変数の値を囲むようにしてください (' ')。手順 1 でテキスト ファイルを保存する場所を指定する必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="16c25-p111">**$MySiteListFile**This specifies the full path of the text file that you created in Step 1. This file contains a list of OneDrive for Business sites in your organization, for example,  `'C:\Users\<youralias>\Desktop\ListOfMysites.txt'`. Be sure to surround the value for this variable with single-quotation marks (' '). Note that you should specify the location that you saved the text file to in Step 1.</span></span>
    
3. <span data-ttu-id="16c25-p112">このテキスト ファイルを PowerShell スクリプト ファイルとして保存するために、ファイル名サフィックスを .ps1 に変更します。たとえば、ファイル OD4BAssignSCA.txt を OD4BAssignSCA.ps1 として保存します。</span><span class="sxs-lookup"><span data-stu-id="16c25-p112">Save the text file as a PowerShell script file by changing the file name suffix to .ps1. For example, save the file OD4BAssignSCA.txt as OD4BAssignSCA.ps1.</span></span>
    
4. <span data-ttu-id="16c25-157">SharePoint Online 管理シェルで、前のステップで作成した PowerShell スクリプトの入ったフォルダーに移動して、スクリプトを実行します。たとえば、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="16c25-157">In SharePoint Online Management Shell, go to the folder that contains the PowerShell script that you created in the previous step, and then run the script, for example:</span></span>
    
    ```
    .\OD4BAssignSCA.ps1
    ```

    <span data-ttu-id="16c25-p113">スクリプトで指定した管理者アカウントのパスワードを入力するように促されます。スクリプトは、メッセージでは、正常に動作している場合`"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` **$MySiteListFile**で指定された入力ファイルに記載されているビジネス サイトの各 OneDrive に表示されます。</span><span class="sxs-lookup"><span data-stu-id="16c25-p113">You will be prompted to enter the password for the administrator account that you specified in the script. If the script runs successfully, the message `"Making  _\<user specified by $eDiscoveryUser\>_ a Site Collection Admin"` is displayed for each OneDrive for Business site that's listed in the input file specified by **$MySiteListFile**.</span></span>

## <a name="more-information"></a><span data-ttu-id="16c25-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="16c25-160">More information</span></span>

- <span data-ttu-id="16c25-p114">手順 3 で実行したスクリプトは、 **$MySiteListFile**変数で指定されたファイルに記載されているビジネスのすべての OneDrive に、サイト コレクションの管理者として指定したユーザーを割り当てるには、**セット SPOUser**コマンドレットを使用します。、数千のユーザーに非常に大規模な組織がある場合は、電子的証拠開示のアクセス許可の割り当てを管理しやすくには以下の手順を検討します。</span><span class="sxs-lookup"><span data-stu-id="16c25-p114">The script that you ran in Step 3 uses the **Set-SPOUser** cmdlet to assign the specified user as a site collection administrator to every OneDrive for Business that's listed in the file specified by the **$MySiteListFile** variable. If you have a very large organization with thousands of users, consider doing the following to make it easier to manage assigning eDiscovery permissions.</span></span> 
    
  - <span data-ttu-id="16c25-163">ユーザーは、作業中の訴訟の対象となるサイトのみが含まれるようにビジネス サイトの OneDrive の一覧が含まれている手順 1 で作成したファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="16c25-163">Edit the file that you created in Step 1 that contains the list of OneDrive for Business sites so that it includes only the sites for users are that are involved in active legal cases.</span></span>
    
  - <span data-ttu-id="16c25-p115">2,500 を超えるの OneDrive の 1 日のビジネス サイトにアクセス許可を割り当てます。たとえば、組織のビジネス サイトの 10,000 の OneDrive があるとします。すべてのサイトを収集するために手順 1 でリストを作成します。2,500 ユーザーがそれぞれ含まれている 4 つのファイルを作成するのにはそのファイルを使用する可能性があります。最初の日では、ビジネス サイトの最初の 2,500 の OneDrive にアクセス許可を割り当てるには、手順 3 でスクリプトを実行するとします。第 2 日目はビジネス サイトでは、次に 2,500 の OneDrive のスクリプトを実行したりします。</span><span class="sxs-lookup"><span data-stu-id="16c25-p115">Assign permissions to no more than 2,500 OneDrive for Business sites per day. For example, let's say you have 10,000 OneDrive for Business sites in your organization. You could create the list in Step 1 to collect all the sites. Then you could use that file to create four files that each contain 2,500 users. On the first day, you would run the script in Step 3 to assign permissions to the first 2,500 OneDrive for Business sites. On the second day, you would run the script for the next 2,500 OneDrive for Business sites, and so on.</span></span>
    
- <span data-ttu-id="16c25-p116">電子的証拠開示の権限と、サイト コレクションの管理者として割り当てられているユーザーに割り当てられたビジネス サイトの OneDrive の記録を保持します。などのアクセス許可を割り当てると後、は、ビジネス サイトの OneDrive の一覧を含むテキスト ファイルを保存し、行を追加するサイト コレクションの管理者として割り当てられているユーザーを識別します。</span><span class="sxs-lookup"><span data-stu-id="16c25-p116">Keep a record of the OneDrive for Business sites that were assigned eDiscovery permissions and the user who is assigned as the site collection administrator. For example, after you assign permissions, you can save the text file that contains the list of OneDrive for Business sites and add a line to it that identifies the user who is assigned as the site collection administrator.</span></span>
    
- <span data-ttu-id="16c25-p117">ユーザーは、ビジネス サイトの OneDrive のサイト コレクション管理者は、自分のリストを表示できます。ユーザーは独自の OneDrive のビジネス サイトのサイト コレクションの管理者であるため、サイト コレクションの管理者を削除することができます。ビジネス サイトの OneDrive に電子的証拠開示のアクセス許可を割り当てられているユーザーを削除してしまう可能性を軽減するために以下の手順を検討してください。</span><span class="sxs-lookup"><span data-stu-id="16c25-p117">Users can view the list of site collection administators for their OneDrive for Business site. Because users are site collection administrator for their own OneDrive for Business site, they can remove site collection administrators. Consider doing the following to mitigate the chance of users removing the user who is assigned eDiscovery permissions to OneDrive for Business sites.</span></span>
    
  - <span data-ttu-id="16c25-175">電子的証拠開示とコンプライアンスのために、法令遵守責任者割り当てられているサイト コレクションの管理者として OneDrive を組織内のビジネス サイトのユーザーに連絡します。</span><span class="sxs-lookup"><span data-stu-id="16c25-175">Communicate to users that for eDiscovery and compliance purposes, a compliance officer has been assigned as a site collection administrator to OneDrive for Business sites in your organization.</span></span>
    
  - <span data-ttu-id="16c25-176">再 OneDrive のビジネスのサイトのサイト コレクションの管理者として、ユーザーを再割り当てするのには、必要な場合は、手順 3 で、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="16c25-176">Re-run the script in Step 3, if necessary, to re-assign a user as the site collection administrator for OneDrive for Business sites.</span></span>
    
- <span data-ttu-id="16c25-p118">手順 3 で実行したスクリプトを使用することも、サイト コレクションの管理者として、ビジネスのサイトの OneDrive からユーザーを削除します。ユーザーを削除するサイト コレクションの管理者としてからの (スクリプトの終了) の近くには、次のコマンドを変更する必要。</span><span class="sxs-lookup"><span data-stu-id="16c25-p118">You can also use the script that you ran in Step 3 to remove a user as the site collection administrator from OneDrive for Business sites. To remove a user as a site collection administrator, you have to change the following command (near the end of the script) from:</span></span> 

    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $true
    ```

    <span data-ttu-id="16c25-179">次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="16c25-179">to:</span></span>
    
    ```
    Set-SPOUser -Site $fullsitepath -LoginName $eDiscoveryUser -IsSiteCollectionAdmin $false
    ```

    <span data-ttu-id="16c25-180">さらに、スクリプトの次の行を</span><span class="sxs-lookup"><span data-stu-id="16c25-180">You can also change the following line in the script from:</span></span>

    ```
    "Making $eDiscoveryUser a Site Collection Admin"
    ```

    <span data-ttu-id="16c25-181">次のように変更します。</span><span class="sxs-lookup"><span data-stu-id="16c25-181">to:</span></span>
    
    ```
    "Removing $eDiscoveryUser as a Site Collection Admin"
    ```

    <span data-ttu-id="16c25-182">これらの変更を実行した後は、OD4BRemoveSCA.ps1 などの別の名前でスクリプトを保存しを使用して、サイト コレクションの管理者としてビジネス サイトの OneDrive のグループからユーザーを削除します。</span><span class="sxs-lookup"><span data-stu-id="16c25-182">After you make these changes, save the script with a different name, such as OD4BRemoveSCA.ps1, and then use it to remove a user as a site collection administrator from a group of OneDrive for Business sites.</span></span>
