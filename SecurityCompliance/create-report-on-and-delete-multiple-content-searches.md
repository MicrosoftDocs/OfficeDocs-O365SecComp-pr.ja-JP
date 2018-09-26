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
# <a name="create-report-on-and-delete-multiple-content-searches"></a>複数のコンテンツ検索を作成、報告、削除する

 迅速に作成し、検索の報告がよくあります電子的証拠開示や調査の重要な手順については、基になるデータと、豊富な機能と、検索結果の品質とする場合。これを実行するためのセキュリティ&amp;コンプライアンス センターには、時間のかかるコンテンツの検索タスクを自動化する Windows PowerShell コマンドレットのセットが用意されています。これらのスクリプトはの検索の数を作成する迅速で簡単な方法を提供し、対象のデータの量を決定する際に役立つ推定の検索結果のレポートを実行しています。1 つずつ生成結果を比較するのに検索結果の別のバージョンを作成するのにスクリプトを使用することもできます。これらのスクリプトを使用して、迅速かつ効率的には、識別し、選別することができます。 
  
## <a name="before-you-begin"></a>はじめに

- セキュリティでは、電子的証拠開示マネージャー ロール グループのメンバーである必要がある&amp;このトピックに記載されているスクリプトを実行するのにはコンプライアンス センターです。 
    
- 手順 1 で CSV ファイルに追加することができる組織内のビジネス サイトの OneDrive の Url の一覧を収集するには、[組織内のすべての OneDrive 場所のリストの作成](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)を参照してください。 
    
- 同じフォルダーに、このトピックで作成したすべてのファイルを保存しておいてください。容易にできるように、スクリプトを実行します。
    
- スクリプトには、最低限のエラー処理が含まれます。主な目的は、簡単に作成、レポート、および複数のコンテンツの検索を削除するのには。
    
- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>手順 1: を実行する、検索に関する情報を含む CSV ファイルを作成します。

この手順で作成したコンマ区切り値 (CSV) ファイルには、検索するユーザーごとに行が含まれています。ユーザーの Exchange Online のメールボックス (アーカイブ先のメールボックスが有効な場合が含まれます) およびビジネスのサイトの OneDrive を検索できます。または、メールボックスだけやビジネス サイトの OneDrive を検索することができます。SharePoint Online 組織内の任意のサイトを検索することもできます。手順 3 で実行するスクリプトでは、CSV ファイルで行ごとに別の検索を作成します。 
  
1. コピーし、次のテキストをメモ帳を使用して .txt ファイルに貼り付けます。ローカル コンピューター上のフォルダーにこのファイルを保存します。このフォルダーに他のスクリプトを保存します。
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    最初の行、または、ファイルのヘッダー行は、新しいコンテンツの検索を作成する (手順 3 でスクリプト) での**新規 ComplianceSearch**コマンドレットで使用するパラメーターを示します。各パラメーター名は、コンマで区切られます。見出し行にスペースがないことを確認します。ヘッダー行の下の各行は、各検索のパラメーター値を表します。CSV ファイル内のプレース ホルダーのデータを実際のデータに置き換えることを確認します。 
    
2. Excel では、.txt ファイルを開くし、各検索の情報を含むファイルを編集するのには次の表に情報を使用します。 
    
    |**パラメーター**|**説明**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |ユーザーのメールボックスの SMTP アドレスです。  <br/> |
    | `SharePointLocation` <br/> |ビジネス サイトのユーザーの OneDrive や、組織内の任意のサイトの URL の URL です。ビジネス サイトの OneDrive の URL の形式を使用して、: ` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `。たとえば、 `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。<br/> |
    | `ContentMatchQuery` <br/> |検索の検索クエリです。検索クエリを作成する方法の詳細については、[キーワード クエリとコンテンツの検索の検索条件](keyword-queries-and-search-conditions.md)を参照してください。<br/> |
    | `StartDate` <br/> |E メール、または、メッセージの後の日付受信者によって受信されたか、送信者によって送信されました。ビジネス サイトの SharePoint または OneDrive 上のドキュメント、ドキュメントの以降の日付が最後に修正されました。  <br/> |
    | `EndDate` <br/> |によって送信された、以前の日付、メッセージ、電子メールのユーザーが送信されます。ビジネス サイトのドキュメントを SharePoint または OneDrive の以前の日付、ドキュメントが最後に修正されました。  <br/> |
   
3. フォルダーに CSV ファイルとして、ローカル コンピューター上の Excel ファイルを保存します。手順 3 で作成したスクリプト情報を使用して、この CSV ファイルで、検索を作成します。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>ステップ 2: 接続セキュリティとコンプライアンス センター PowerShell

次の手順は、セキュリティを保護する Windows PowerShell を接続する&amp;、組織のコンプライアンス センターです。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `ConnectSCC.ps1`。手順 1 で CSV ファイルを保存した同じフォルダーにファイルを保存します。
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. ローカル コンピューターに Windows PowerShell を開く前の手順で作成したスクリプトがある場所のフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>手順 3: スクリプトを実行して作成し、検索を開始

この手順では、スクリプトでは、手順 1 で作成した CSV ファイルで行ごとに独立したコンテンツの検索を作成します。このスクリプトを実行すると 2 つの値にするように求めします。
  
- **グループの ID を検索**: この名前は、CSV ファイルから作成された検索を整理する簡単な方法を提供します。作成される各検索は、検索グループ ID を持つという名前し、検索名に数字が追加されます。などの検索グループ ID の**ContosoCase**を入力する場合、検索はという名前の**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**というようにします。入力した名前が大文字小文字の区別に注意してください。手順 4 と手順 5 での検索のグループ ID を使用して、それを作成したときと同じように、同じ大文字と小文字を使用するのにはあります。 
    
- **CSV ファイル**を手順 1 で作成した CSV ファイルの名前です。使用の完全なファイル名を含めるには、.csv ファイル拡張子を含めることを確認します。たとえば、 `ContosoCase.csv`。
    
このスクリプトを実行するには、以下の手順を実行します。

1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `CreateSearches.ps1`。他のファイルを保存した同じフォルダーにファイルを保存します。
    
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

2. Windows PowerShell では、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\CreateSearches.ps1
    ```

3. プロンプトで、**グループの ID を検索**、検索、グループ名を入力し、 **Enter**キーを押しますたとえば、 `ContosoCase`。この名前が大文字小文字を区別、後続の手順で同じ方法を入力する必要があるありますので注意してください。
    
4. **ソース CSV ファイル**プロンプトでは、.csv ファイル拡張子を含む CSV ファイルの名前を入力しますたとえば、 `ContosoCase.csv`。
    
5. スクリプトの実行を続行するのには enter キーを**入力**します。 
    
    スクリプトを作成し、検索を実行中の進行状況を表示します。スクリプトが完了すると、プロンプトに戻ります。 
    
    ![複数のコンプライアンス検索を作成するスクリプトを実行した場合の出力例](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>手順 4: を実行する検索を報告するスクリプトを推定します。

検索を作成した後は、手順 3 で作成した検索の検索のヒット数の単純なレポートを表示するスクリプトを実行します。レポートには、検索、およびヒット数の合計数とすべての検索の合計サイズの結果のサイズも含まれています。レポート ・ スクリプトを実行すると、するが必要、検索グループ ID、および CSV ファイル名のレポートを CSV ファイルに保存する場合。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `SearchReport.ps1`。他のファイルを保存した同じフォルダーにファイルを保存します。
    
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

2. Windows PowerShell では、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\SearchReport.ps1
    ```

3. プロンプトで、**グループの ID を検索**、検索、グループ名を入力し、 **Enter**キーを押しますたとえば`ContosoCase`。この名前は大文字小文字を区別、それを入力する必要があるありますのでと同じ方法で使用した手順 3 でスクリプトを実行するときのことを覚えておいてください。
    
4. **ファイル パス、レポートを CSV ファイル (未入力にレポートを表示する) を保存する**プロンプトで、レポートを CSV ファイルに保存する場合は、(.csv ファイルの拡張子を含む) 完全なファイル名のパスのファイル名を入力します。.csv ファイル拡張子を含む CSV ファイルの名前です。たとえば、入力`ContosoCaseReport.csv`または現在のディレクトリに保存するには入力`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`別のフォルダーに保存します。ことができますも空白のままに、プロンプトにレポートを表示しますが、ファイルに保存されません。 
    
5. **Enter**キーを押します。
    
    スクリプトを作成し、検索を実行中の進行状況を表示します。スクリプトが完了すると、レポートが表示されます。 
    
    ![検索レポートを実行して検索グループの推定値を表示する](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 同じメールボックス ストアまたはサイトを検索グループ内の 1 つ以上の検索でのコンテンツの場所として指定する場合 (両方の項目の数と合計サイズ) のレポートの結果の合計見積には、同じ項目の結果が含まれます。同じ電子メール メッセージやドキュメントが複数の 1 回カウントされる検索グループの別の検索クエリと一致する場合があるためにです。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>手順 5: スクリプトを実行して、サーチを削除

多くの検索を作成する場合ため、この最後のスクリプトだけで、簡単迅速に手順 3 で作成した検索を削除するのには。他のスクリプトと同じようにこの 1 つもの入力を求める検索グループの id。検索名で検索のグループ ID を持つすべての検索は、このスクリプトを実行するときに削除されます。 
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `DeleteSearches.ps1`。他のファイルを保存した同じフォルダーにファイルを保存します。
    
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

2. Windows PowerShell では、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行し、例えば：
    
    ```
    .\DeleteSearches.ps1
    ```

3. **グループ ID の検索**プロンプトで、削除する検索の検索グループ名を入力し、 **Enter**キーを押しますたとえば、 `ContosoCase`。この名前は大文字小文字を区別、それを入力する必要があるありますのでと同じ方法で使用した手順 3 でスクリプトを実行するときのことを覚えておいてください。
    
    スクリプトには、削除された各検索の名前が表示されます。
    
    ![検索グループ内の検索を削除するスクリプトを実行する](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
