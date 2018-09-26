---
title: 複数のコンテンツ検索を作成、報告、削除する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: 検索を作成し、Office 365 のセキュリティでは、PowerShell スクリプトを使用してレポートを実行するようにコンテンツの検索タスクを自動化する方法を説明&amp;コンプライアンス センターです。
ms.openlocfilehash: a32c003dfd9a27ea8c38b29b31001b612368bc4a
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038140"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a><span data-ttu-id="2e041-103">複数のコンテンツ検索を作成、報告、削除する</span><span class="sxs-lookup"><span data-stu-id="2e041-103">Create, report on, and delete multiple Content Searches</span></span>

 <span data-ttu-id="2e041-p101">迅速に作成し、検索の報告がよくあります電子的証拠開示や調査の重要な手順については、基になるデータと、豊富な機能と、検索結果の品質とする場合。これを実行するためのセキュリティ&amp;コンプライアンス センターには、時間のかかるコンテンツの検索タスクを自動化する Windows PowerShell コマンドレットのセットが用意されています。これらのスクリプトはの検索の数を作成する迅速で簡単な方法を提供し、対象のデータの量を決定する際に役立つ推定の検索結果のレポートを実行しています。1 つずつ生成結果を比較するのに検索結果の別のバージョンを作成するのにスクリプトを使用することもできます。これらのスクリプトを使用して、迅速かつ効率的には、識別し、選別することができます。</span><span class="sxs-lookup"><span data-stu-id="2e041-p101">Quickly creating and reporting discovery searches is often an important step in eDiscovery and investigations when you're trying to learn about the underlying data, and the richness and quality of your searches. To help you do this, the Security &amp; Compliance Center offers a set of Windows PowerShell cmdlets to automate time-consuming Content Search tasks. These scripts provide a quick and easy way to create a number of searches, and then run reports of the estimated search results that can help you determine the quantity of data in question. You can also use the scripts to create different versions of searches to compare the results each one produces. These scripts can help you to quickly and efficiently identify and cull your data.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="2e041-109">はじめに</span><span class="sxs-lookup"><span data-stu-id="2e041-109">Before you begin</span></span>

- <span data-ttu-id="2e041-110">セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;このトピックに記載されているスクリプトを実行するのにはコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="2e041-110">You have to be a member of the eDiscovery Manager role group in the Security &amp; Compliance Center to run the scripts that are described in this topic.</span></span> 
    
- <span data-ttu-id="2e041-111">手順 1 で CSV ファイルに追加することができる組織内のビジネス サイトの OneDrive の Url の一覧を収集するには、[組織内のすべての OneDrive 場所のリストの作成](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e041-111">To collect a list of the URLs for the OneDrive for Business sites in your organization that you can add to the CSV file in Step 1, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a).</span></span> 
    
- <span data-ttu-id="2e041-p102">同じフォルダーに、このトピックで作成したすべてのファイルを保存しておいてください。容易にできるように、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p102">Be sure to save all the files that you create in this topic to the same folder. That will make it easier to run the scripts.</span></span>
    
- <span data-ttu-id="2e041-p103">スクリプトには、最低限のエラー処理が含まれます。主な目的は、簡単に作成、レポート、および複数のコンテンツの検索を削除するのには。</span><span class="sxs-lookup"><span data-stu-id="2e041-p103">The scripts include minimal error handling. Their primary purpose is to quickly create, report on, and delete multiple Content Searches.</span></span>
    
- <span data-ttu-id="2e041-p104">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="2e041-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a><span data-ttu-id="2e041-121">手順 1: を実行する、検索に関する情報を含む CSV ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="2e041-121">Step 1: Create a CSV file that contains information about the searches you want to run</span></span>

<span data-ttu-id="2e041-p105">この手順で作成したコンマ区切り値 (CSV) ファイルには、検索するユーザーごとに行が含まれています。ユーザーの Exchange Online のメールボックス (アーカイブ先のメールボックスが有効な場合が含まれます) およびビジネスのサイトの OneDrive を検索できます。または、メールボックスだけやビジネス サイトの OneDrive を検索することができます。SharePoint Online 組織内の任意のサイトを検索することもできます。手順 3 で実行するスクリプトでは、CSV ファイルで行ごとに別の検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p105">The comma separated value (CSV) file that you create in this step contains a row for each user that want to search. You can search the user's Exchange Online mailbox (which includes the archive mailbox, if it's enabled) and their OneDrive for Business site. Or you can search just the mailbox or the OneDrive for Business site. You can also search any site in your SharePoint Online organization. The script that you run in Step 3 will create a separate search for each row in the CSV file.</span></span> 
  
1. <span data-ttu-id="2e041-p106">コピーし、次のテキストをメモ帳を使用して .txt ファイルに貼り付けます。ローカル コンピューター上のフォルダーにこのファイルを保存します。このフォルダーに他のスクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p106">Copy and paste the following text into a .txt file using NotePad. Save this file to a folder on your local computer. You'll save the other scripts to this folder as well.</span></span>
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    <span data-ttu-id="2e041-p107">最初の行、または、ファイルのヘッダー行は、新しいコンテンツの検索を作成する (手順 3 でスクリプト) での**新規 ComplianceSearch**コマンドレットで使用するパラメーターを示します。各パラメーター名は、コンマで区切られます。見出し行にスペースがないことを確認します。ヘッダー行の下の各行は、各検索のパラメーター値を表します。CSV ファイル内のプレース ホルダーのデータを実際のデータに置き換えることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p107">The first row, or header row, of the file lists the parameters that will be used by **New-ComplianceSearch** cmdlet (in the script in Step 3) to create a new Content Searches. Each parameter name is separated by a comma. Make sure there aren't any spaces in the header row. Each row under the header row represents the parameter values for each search. Be sure to replace the placeholder data in the CSV file with your actual data.</span></span> 
    
2. <span data-ttu-id="2e041-135">Excel では、.txt ファイルを開くし、各検索の情報を含むファイルを編集するのには次の表に情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e041-135">Open the .txt file in Excel, and then use the information in the following table to edit the file with information for each search.</span></span> 
    
    |<span data-ttu-id="2e041-136">**パラメーター**</span><span class="sxs-lookup"><span data-stu-id="2e041-136">**Parameter**</span></span>|<span data-ttu-id="2e041-137">**説明**</span><span class="sxs-lookup"><span data-stu-id="2e041-137">**Description**</span></span>|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |<span data-ttu-id="2e041-138">ユーザーのメールボックスの SMTP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="2e041-138">The SMTP address of the user's mailbox.</span></span>  <br/> |
    | `SharePointLocation` <br/> |<span data-ttu-id="2e041-p108">ビジネス サイトのユーザーの OneDrive や、組織内の任意のサイトの URL の URL です。ビジネス サイトの OneDrive の URL の形式を使用して、: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。たとえば、 `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。</span><span class="sxs-lookup"><span data-stu-id="2e041-p108">The URL for the user's OneDrive for Business site or the URL for any site in your organization. For the URL for OneDrive for Business sites, use this format: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `. For example,  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`.  </span></span><br/> |
    | `ContentMatchQuery` <br/> |<span data-ttu-id="2e041-p109">検索の検索クエリです。検索クエリを作成する方法の詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e041-p109">The search query for the search. For more information about creating a search query, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).  </span></span><br/> |
    | `StartDate` <br/> |<span data-ttu-id="2e041-p110">E メール、または、メッセージの後の日付受信者によって受信されたか、送信者によって送信されました。ビジネス サイトの SharePoint または OneDrive 上のドキュメント、ドキュメントの以降の日付が最後に修正されました。</span><span class="sxs-lookup"><span data-stu-id="2e041-p110">For email, the date on or after a message was received by a recipient or sent by the sender. For documents on SharePoint or OneDrive for Business sites, the date on or after a document was last modified.</span></span>  <br/> |
    | `EndDate` <br/> |<span data-ttu-id="2e041-p111">によって送信された、以前の日付、メッセージ、電子メールのユーザーが送信されます。ビジネス サイトのドキュメントを SharePoint または OneDrive の以前の日付、ドキュメントが最後に修正されました。</span><span class="sxs-lookup"><span data-stu-id="2e041-p111">For email, the date on or before a message was sent by a sent by the user. For documents on SharePoint or OneDrive for Business sites, the date on or before a document was last modified.</span></span>  <br/> |
   
3. <span data-ttu-id="2e041-p112">フォルダーに CSV ファイルとして、ローカル コンピューター上の Excel ファイルを保存します。手順 3 で作成したスクリプト情報を使用して、この CSV ファイルで、検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p112">Save the Excel file as a CSV file to a folder on your local computer. The script that you create in Step 3 will use the information in this CSV file to create the searches.</span></span> 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="2e041-150">ステップ 2: 接続セキュリティとコンプライアンス センター PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e041-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="2e041-151">次の手順は、セキュリティを保護する Windows PowerShell を接続する&amp;、組織のコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="2e041-151">The next step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="2e041-p113">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `ConnectSCC.ps1`。手順 1 で CSV ファイルを保存した同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p113">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`. Save the file to the same folder that you saved the CSV file to in Step 1.</span></span>
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="2e041-154">ローカル コンピューターに Windows PowerShell を開く前の手順で作成したスクリプトがある場所のフォルダーに移動し、スクリプトを実行し、例えば：</span><span class="sxs-lookup"><span data-stu-id="2e041-154">On your local computer, open Windows PowerShell, go to the folder where the script that you created in the previous step is located, and then run the script; for example:</span></span>
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a><span data-ttu-id="2e041-155">手順 3: スクリプトを実行して作成し、検索を開始</span><span class="sxs-lookup"><span data-stu-id="2e041-155">Step 3: Run the script to create and start the searches</span></span>

<span data-ttu-id="2e041-p114">この手順では、スクリプトでは、手順 1 で作成した CSV ファイルで行ごとに独立したコンテンツの検索を作成します。このスクリプトを実行すると 2 つの値にするように求めします。</span><span class="sxs-lookup"><span data-stu-id="2e041-p114">The script in this step will create a separate Content Search for each row in the CSV file that you created in Step 1. When you run this script, you'll be prompted for two values:</span></span>
  
- <span data-ttu-id="2e041-p115">**グループの ID を検索**: この名前は、CSV ファイルから作成された検索を整理する簡単な方法を提供します。作成される各検索は、検索グループ ID を持つという名前し、検索名に数字が追加されます。などの検索グループ ID の**ContosoCase**を入力する場合、検索はという名前の**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**というようにします。入力した名前が大文字小文字の区別に注意してください。手順 4 と手順 5 での検索のグループ ID を使用して、それを作成したときと同じように、同じ大文字と小文字を使用するのにはあります。</span><span class="sxs-lookup"><span data-stu-id="2e041-p115">**Search Group ID** - This name provides an easy way to organize the searches that are created from the CSV file. Each search that's created is named with the Search Group ID, and then a number is appended to the search name. For example, if you enter **ContosoCase** for the Search Group ID, then the searches are named **ContosoCase_1**, **ContosoCase_2**, **ContosoCase_3**, and so on. Note that the name you type is case sensitive. When you use the Search Group ID in Step 4 and Step 5, you have to use the same case as you did when you created it.</span></span> 
    
- <span data-ttu-id="2e041-p116">**CSV ファイル**を手順 1 で作成した CSV ファイルの名前です。使用の完全なファイル名を含めるには、.csv ファイル拡張子を含めることを確認します。たとえば、 `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="2e041-p116">**CSV file** - The name of the CSV file that you created in Step 1. Be sure to include the use the full filename, include the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
<span data-ttu-id="2e041-165">このスクリプトを実行するには、以下の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2e041-165">To run the script:</span></span>

1. <span data-ttu-id="2e041-p117">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `CreateSearches.ps1`。他のファイルを保存した同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p117">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `CreateSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
  ```
  # Get the Search Group ID and the location of the CSV input file
  $searchGroup = Read-Host 'Search Group ID'
  $csvFile = Read-Host 'Source CSV file'
    
  # Do a quick check to make sure our group name will not collide with other searches
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    $searchName = $searchGroup +'_' + $searchCounter
    $search = Get-ComplianceSearch $searchName -EA SilentlyContinue
    if ($search)
    {
        Write-Error "The Search Group ID conflicts with existing searches.  Please choose a search group name and restart the script."
        return
    }
    $searchCounter++
  }
    
  $searchCounter = 1
  import-csv $csvFile |
    ForEach-Object{
    
    # Create the query
    $query = $_.ContentMatchQuery
    if(($_.StartDate -or $_.EndDate))
    {
          # Add the appropriate date restrictions.  NOTE: Using the Date condition property here because it works across Exchange, SharePoint, and OneDrive for Business.
          # For Exchange, the Date condition property maps to the Sent and Received dates; for SharePoint and OneDrive for Business, it maps to Created and Modified dates.
          if($query)
          {
              $query += " AND"
          }
          $query += " ("
          if($_.StartDate)
          {
              $query += "Date >= " + $_.StartDate
          }
          if($_.EndDate)
          {
              if($_.StartDate)
              {
                  $query += " AND "
              }
              $query += "Date <= " + $_.EndDate
          }
          $query += ")"
    }
      
      # -ExchangeLocation can't be set to an empty string, set to null if there's no location.
      $exchangeLocation = $null
      if ( $_.ExchangeLocation)
      {
           $exchangeLocation = $_.ExchangeLocation
      }
    
    # Create and run the search        
    $searchName = $searchGroup +'_' + $searchCounter
    Write-Host "Creating and running search: " $searchName -NoNewline
    $search = New-ComplianceSearch -Name $searchName -ExchangeLocation $exchangeLocation -SharePointLocation $_.SharePointLocation -ContentMatchQuery $query
    
    # Start and wait for each search to complete
    Start-ComplianceSearch $search.Name
    while ((Get-ComplianceSearch $search.Name).Status -ne "Completed")
    {
        Write-Host " ." -NoNewline
        Start-Sleep -s 3
    }
    Write-Host ""
    
    $searchCounter++
  }
  ```

2. <span data-ttu-id="2e041-168">Windows PowerShell では、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行し、例えば：</span><span class="sxs-lookup"><span data-stu-id="2e041-168">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\CreateSearches.ps1
    ```

3. <span data-ttu-id="2e041-p118">プロンプトで、**グループの ID を検索**、検索、グループ名を入力し、 **Enter**キーを押しますたとえば、 `ContosoCase`。この名前が大文字小文字を区別、後続の手順で同じ方法を入力する必要があるありますので注意してください。</span><span class="sxs-lookup"><span data-stu-id="2e041-p118">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way in the subsequent steps.</span></span>
    
4. <span data-ttu-id="2e041-171">**ソース CSV ファイル**プロンプトでは、.csv ファイル拡張子を含む CSV ファイルの名前を入力しますたとえば、 `ContosoCase.csv`。</span><span class="sxs-lookup"><span data-stu-id="2e041-171">At the **Source CSV file** prompt, type the name of the CSV file, including the .csv file extension; for example,  `ContosoCase.csv`.</span></span>
    
5. <span data-ttu-id="2e041-172">スクリプトの実行を続行するのには enter キーを**入力**します。</span><span class="sxs-lookup"><span data-stu-id="2e041-172">Press **Enter** to continue running the script.</span></span> 
    
    <span data-ttu-id="2e041-p119">スクリプトを作成し、検索を実行中の進行状況を表示します。スクリプトが完了すると、プロンプトに戻ります。</span><span class="sxs-lookup"><span data-stu-id="2e041-p119">The script displays the progress of creating and running the searches. When the script is complete, it returns to the prompt.</span></span> 
    
    ![複数のコンプライアンス検索を作成するスクリプトを実行した場合の出力例](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a><span data-ttu-id="2e041-176">手順 4: を実行する検索を報告するスクリプトを推定します。</span><span class="sxs-lookup"><span data-stu-id="2e041-176">Step 4: Run the script to report the search estimates</span></span>

<span data-ttu-id="2e041-p120">検索を作成した後は、手順 3 で作成した検索の検索のヒット数の単純なレポートを表示するスクリプトを実行します。レポートには、検索、およびヒット数の合計数とすべての検索の合計サイズの結果のサイズも含まれています。レポート ・ スクリプトを実行すると、するが必要、検索グループ ID、および CSV ファイル名のレポートを CSV ファイルに保存する場合。</span><span class="sxs-lookup"><span data-stu-id="2e041-p120">After you create the searches, the next step is to run a script that displays a simple report of the number of search hits for each search that was created in Step 3. The report also includes the size of results for each search, and the total number of hits and total size of all searches. When you run the reporting script, you'll be prompted for the Search Group ID, and a CSV filename if you want to save the report to a CSV file.</span></span>
  
1. <span data-ttu-id="2e041-p121">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `SearchReport.ps1`。他のファイルを保存した同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `SearchReport.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
  ```
  $searchGroup = Read-Host 'Search Group ID'
  $outputFile = Read-Host 'Enter a file name or file path to save the report to a .csv file. Leave blank to only display the report'
  $searches = Get-ComplianceSearch | ?{$_.Name -clike $searchGroup + "_*"}
  $allSearchStats = @()
  foreach ($partialObj in $searches)
  {
      $search = Get-ComplianceSearch $partialObj.Name
      $sizeMB = [System.Math]::Round($search.Size / 1MB, 2)
      $searchStatus = $search.Status
      if($search.Errors)
      {
          $searchStatus = "Failed"
      }elseif($search.NumFailedSources -gt 0)
      {
          $searchStatus = "Failed Sources"
      }
      $searchStats = New-Object PSObject
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Name -Value $search.Name
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name ContentMatchQuery -Value $search.ContentMatchQuery
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Status -Value $searchStatus
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name Items -Value $search.Items
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size" -Value $search.Size
      Add-Member -InputObject $searchStats -MemberType NoteProperty -Name "Size(MB)" -Value $sizeMB
      $allSearchStats += $searchStats
  }
  # Calculate the totals
  $allItems = ($allSearchStats | Measure-Object Items -Sum).Sum
  # Convert the total size to MB and round to the nearst 100th
  $allSize = ($allSearchStats | Measure-Object 'Size' -Sum).Sum
  $allSizeMB = [System.Math]::Round($allSize  / 1MB, 2)
  # Get the total successful searches and total of all searches
  $allSuccessCount = ($allSearchStats |?{$_.Status -eq "Completed"}).Count
  $allCount = $allSearchStats.Count
  $allStatus = [string]$allSuccessCount + " of " + [string]$allCount
  # Totals Row
  $totalSearchStats = New-Object PSObject
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Name -Value "Total"
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Status -Value $allStatus
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name Items -Value $allItems
  Add-Member -InputObject $totalSearchStats -MemberType NoteProperty -Name "Size(MB)" -Value $allSizeMB
  $allSearchStats += $totalSearchStats
  # Just get the columns we're interested in showing
  $allSearchStatsPrime = $allSearchStats | Select-Object Name, Status, Items, "Size(MB)", ContentMatchQuery
  # Print the results to the screen
  $allSearchStatsPrime |ft -AutoSize -Wrap
  # Save the results to a CSV file
  if ($outputFile)
  {
      $allSearchStatsPrime | Export-Csv -Path $outputFile -NoTypeInformation
  }
  ```

2. <span data-ttu-id="2e041-182">Windows PowerShell では、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行し、例えば：</span><span class="sxs-lookup"><span data-stu-id="2e041-182">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\SearchReport.ps1
    ```

3. <span data-ttu-id="2e041-p122">プロンプトで、**グループの ID を検索**、検索、グループ名を入力し、 **Enter**キーを押しますたとえば`ContosoCase`。この名前は大文字小文字を区別、それを入力する必要があるありますのでと同じ方法で使用した手順 3 でスクリプトを実行するときのことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="2e041-p122">At the **Search Group ID** prompt, type a search group name, and then press **Enter**; for example  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
4. <span data-ttu-id="2e041-p123">**ファイル パス、レポートを CSV ファイル (未入力にレポートを表示する) を保存する**プロンプトで、レポートを CSV ファイルに保存する場合は、(.csv ファイルの拡張子を含む) 完全なファイル名のパスのファイル名を入力します。.csv ファイル拡張子を含む CSV ファイルの名前です。たとえば、入力`ContosoCaseReport.csv`または現在のディレクトリに保存するには入力`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`別のフォルダーに保存します。ことができますも空白のままに、プロンプトにレポートを表示しますが、ファイルに保存されません。</span><span class="sxs-lookup"><span data-stu-id="2e041-p123">At the **File path to save the report to a CSV file (leave blank to just display the report)** prompt, type a file name of complete filename path (including the .csv file extension) if you want to save the report to a CSV file. name of the CSV file, including the .csv file extension. For example, you could type  `ContosoCaseReport.csv` to save it to the current directory or you could type  `C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv` to save it to a different folder. You can also leave the prompt blank to display the report but not save it to a file.</span></span> 
    
5. <span data-ttu-id="2e041-189">**Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2e041-189">Press **Enter**.</span></span>
    
    <span data-ttu-id="2e041-p124">スクリプトを作成し、検索を実行中の進行状況を表示します。スクリプトが完了すると、レポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e041-p124">The script displays the progress of creating and running the searches. When the script is complete, the report is displayed.</span></span> 
    
    ![検索レポートを実行して検索グループの推定値を表示する](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> <span data-ttu-id="2e041-p125">同じメールボックス ストアまたはサイトを検索グループ内の 1 つ以上の検索でのコンテンツの場所として指定する場合 (両方の項目の数と合計サイズ) のレポートの結果の合計見積には、同じ項目の結果が含まれます。同じ電子メール メッセージやドキュメントが複数の 1 回カウントされる検索グループの別の検索クエリと一致する場合があるためにです。</span><span class="sxs-lookup"><span data-stu-id="2e041-p125">If the same mailbox or site is specified as a content location in more than one search in a search group, the total results estimate in the report (for both the number of items and the total size) might include results for the same items. That's because the same email message or document will be counted more than once if it matches the query for different searches in the search group.</span></span> 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a><span data-ttu-id="2e041-195">手順 5: スクリプトを実行して、サーチを削除</span><span class="sxs-lookup"><span data-stu-id="2e041-195">Step 5: Run the script to delete the searches</span></span>

<span data-ttu-id="2e041-p126">多くの検索を作成する場合ため、この最後のスクリプトだけで、簡単迅速に手順 3 で作成した検索を削除するのには。他のスクリプトと同じようにこの 1 つもの入力を求める検索グループの id。検索名で検索のグループ ID を持つすべての検索は、このスクリプトを実行するときに削除されます。</span><span class="sxs-lookup"><span data-stu-id="2e041-p126">Because you might be creating a lot of searches, this last script just makes it easy to quickly delete the searches you created in Step 3. Like the other scripts, this one also prompts you for the Search Group ID. All searches with the Search Group ID in the search name will be deleted when you run this script.</span></span> 
  
1. <span data-ttu-id="2e041-p127">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `DeleteSearches.ps1`。他のファイルを保存した同じフォルダーにファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="2e041-p127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `DeleteSearches.ps1`. Save the file to the same folder where you saved the other files.</span></span>
    
  ```
  # Delete all searches in a search group
  $searchGroup = Read-Host 'Search Group ID'
  Get-ComplianceSearch |
      ForEach-Object{
      # If the name matches the search group name pattern (case sensitive), delete the search
      if ($_.Name -cmatch $searchGroup + "_\d+")
      {
          Write-Host "Deleting search: " $_.Name
          Remove-ComplianceSearch $_.Name -Confirm:$false
      }
  }
  ```

2. <span data-ttu-id="2e041-201">Windows PowerShell では、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行し、例えば：</span><span class="sxs-lookup"><span data-stu-id="2e041-201">In Windows PowerShell, go to the folder where you saved the script in the previous step, and then run the script; for example:</span></span>
    
    ```
    .\DeleteSearches.ps1
    ```

3. <span data-ttu-id="2e041-p128">**グループ ID の検索**プロンプトで、削除する検索の検索グループ名を入力し、 **Enter**キーを押しますたとえば、 `ContosoCase`。この名前は大文字小文字を区別、それを入力する必要があるありますのでと同じ方法で使用した手順 3 でスクリプトを実行するときのことを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="2e041-p128">At the **Search Group ID** prompt, type a search group name for the searches that you want to delete, and then press **Enter**; for example,  `ContosoCase`. Remember that this name is case sensitive, so you'll have to type it the same way you did when you ran the script in Step 3.</span></span>
    
    <span data-ttu-id="2e041-204">スクリプトには、削除された各検索の名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e041-204">The script displays the name of each search that's deleted.</span></span>
    
    ![検索グループ内の検索を削除するスクリプトを実行する](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
