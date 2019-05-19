---
title: 複数のコンテンツ検索の作成、報告、削除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
ms.assetid: 1d463dda-a3b5-4675-95d4-83db19c9c4a3
description: Office 365 のセキュリティ & コンプライアンスセンターで、PowerShell スクリプトを使用して検索を作成し、レポートを実行するなどのコンテンツ検索タスクを自動化する方法について説明します。
ms.openlocfilehash: 75caf75d576ac4a24779de15f5b05cb7fe8fa724
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151179"
---
# <a name="create-report-on-and-delete-multiple-content-searches"></a>複数のコンテンツ検索の作成、報告、削除

 検索検索を迅速に作成およびレポートすることは、基礎となるデータについて学習しようとしているときに電子情報開示や調査を行う際に重要な手順です。 これを実現するために、Security & コンプライアンスセンター PowerShell では、時間のかかるコンテンツ検索タスクを自動化する一連のコマンドレットを提供しています。 これらのスクリプトを使用すると、多数の検索をすばやく簡単に作成し、予想される検索結果のレポートを実行して、問題のデータ量を判断するのに役立つことができます。 また、これらのスクリプトを使用して、それぞれの結果を比較するさまざまなバージョンの検索を作成することもできます。 これらのスクリプトは、データを迅速かつ効率的に識別してカリングするのに役立ちます。 
  
## <a name="before-you-begin"></a>始める前に

- このトピックで説明するスクリプトを実行するには、Security & コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。 
    
- 手順1で CSV ファイルに追加できる、組織内の OneDrive for Business サイトの Url の一覧を収集するには、「[組織内のすべての onedrive の場所の一覧を作成](https://support.office.com/article/Create-a-list-of-all-OneDrive-locations-in-your-organization-8e200cb2-c768-49cb-88ec-53493e8ad80a)する」を参照してください。 
    
- このトピックで作成するすべてのファイルを同じフォルダーに保存するようにしてください。 これにより、スクリプトをより簡単に実行できるようになります。
    
- スクリプトには、最小限のエラー処理が含まれています。 その主な目的は、複数のコンテンツ検索をすばやく作成、レポート作成、および削除することです。
    
- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。
    
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-searches-you-want-to-run"></a>手順 1: 実行する検索に関する情報を含む CSV ファイルを作成する

この手順で作成するコンマ区切り値 (CSV) ファイルには、検索するユーザーごとに1つの行が含まれています。 ユーザーの Exchange Online メールボックス (アーカイブメールボックスが有効になっている場合) と OneDrive for Business サイトを検索できます。 または、メールボックスまたは OneDrive for Business サイトのみを検索することもできます。 SharePoint Online 組織の任意のサイトを検索することもできます。 手順3で実行するスクリプトは、CSV ファイルの各行に対して個別に検索を作成します。 
  
1. 次のテキストをコピーして、メモ帳を使用して .txt ファイルに貼り付けます。 このファイルをローカルコンピューター上のフォルダーに保存します。 他のスクリプトもこのフォルダーに保存します。
    
    ```
    ExchangeLocation,SharePointLocation,ContentMatchQuery,StartDate,EndDate
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2000,12/31/2005
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2006,12/31/2010
    sarad@contoso.onmicrosoft.com,https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com,(lawsuit OR legal),1/1/2011,3/21/2016
    ,https://contoso.sharepoint.com/sites/contoso,,,3/21/2016
    ,https://contoso-my.sharepoint.com/personal/davidl_contoso_onmicrosoft_com,,1/1/2015,
    ,https://contoso-my.sharepoint.com/personal/janets_contoso_onmicrosoft_com,,1/1/2015,
    ```

    ファイルの最初の行、つまりヘッダー行には、新しいコンテンツ検索を作成するために、 **new-compliancesearch**コマンドレットで使用するパラメーター (手順3のスクリプト) が表示されます。 パラメーター名とパラメーター名の間はコンマで区切られています。 ヘッダー行にスペースがないことを確認してください。 ヘッダー行の下の各行は、各検索のパラメーター値を表します。 必ず、CSV ファイル内のプレースホルダーデータを実際のデータに置き換えてください。 
    
2. Excel で .txt ファイルを開き、次の表の情報を使用して、各検索の情報でファイルを編集します。 
    
    |**パラメーター**|**説明**|
    |:-----|:-----|
    | `ExchangeLocation` <br/> |ユーザーのメールボックスの SMTP アドレス。  <br/> |
    | `SharePointLocation` <br/> |ユーザーの OneDrive for Business サイトの URL、または組織内のサイトの URL。 OneDrive for Business サイトの URL の場合は、次` https://<your organization>-my.sharepoint.com/personal/<user alias>_<your organization>_onmicrosoft_com `の形式を使用します。 例: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft_com`。  <br/> |
    | `ContentMatchQuery` <br/> |検索の検索クエリ。 検索クエリの作成の詳細については、「[コンテンツ検索のキーワードクエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。  <br/> |
    | `StartDate` <br/> |電子メールの場合、メッセージが受信者によって受信された日付または送信者によって送信された日付。 SharePoint または OneDrive for Business サイトのドキュメントの場合は、ドキュメントが最後に変更された日付またはそれ以降の日付を指定します。  <br/> |
    | `EndDate` <br/> |電子メールの場合、ユーザーによって送信されたメッセージが送信された日付またはそれ以前の日付。 SharePoint または OneDrive for Business サイトのドキュメントの場合、ドキュメントが最後に変更された日付またはそれ以前の日付。  <br/> |
   
3. Excel ファイルを CSV ファイルとして、ローカルコンピューター上のフォルダーに保存します。 手順3で作成したスクリプトでは、この CSV ファイルの情報を使用して検索を作成します。 
  
## <a name="step-2-connect-to-security--compliance-center-powershell"></a>手順 2: Security & コンプライアンスセンター PowerShell に接続する

次の手順では、組織の Security & コンプライアンスセンター PowerShell に接続します。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `ConnectSCC.ps1`のようになります。 手順1で CSV ファイルを保存したのと同じフォルダーにファイルを保存します。
    
    ```
    # Get login credentials 
    $UserCredential = Get-Credential 
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
    Import-PSSession $Session -AllowClobber -DisableNameChecking 
    $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Security & Compliance Center)" 
    ```

2. ローカル コンピューター上で、Windows PowerShell を開き、前の手順で作成したスクリプトが配置されているフォルダーに移動し、スクリプトを実行します。例:
    
    ```
    .\ConnectSCC.ps1
    ```
  
## <a name="step-3-run-the-script-to-create-and-start-the-searches"></a>手順 3: スクリプトを実行して検索を作成および開始する

この手順のスクリプトは、手順1で作成した CSV ファイルの各行に対して個別のコンテンツ検索を作成します。 このスクリプトを実行すると、次の2つの値を入力するように求められます。
  
- **検索グループ ID** -この名前は、CSV ファイルから作成された検索を簡単に整理する方法を提供します。 作成された各検索には、検索グループ ID が付けられ、検索名に数字が追加されます。 たとえば、検索グループ ID に「 **ContosoCase** 」と入力すると、検索には**ContosoCase_1**、 **ContosoCase_2**、 **ContosoCase_3**という名前が付けられます。 入力する名前は大文字と小文字が区別されることに注意してください。 手順4と手順5で検索グループ ID を使用する場合は、作成時と同じケースを使用する必要があります。 
    
- **Csv ファイル**-手順1で作成した csv ファイルの名前。 必ず完全なファイル名を指定してください。ファイル拡張子は .csv にします。たとえば、 `ContosoCase.csv`のようになります。
    
このスクリプトを実行するには、以下の手順を実行します。

1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `CreateSearches.ps1`のようになります。 他のファイルを保存したのと同じフォルダーにファイルを保存します。
    
  ```Powershell
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

2. Windows PowerShell で、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：
    
    ```Powershell
    .\CreateSearches.ps1
    ```

3. [**検索グループ ID** ] プロンプトで、検索グループ名を入力し、enter **** キーを押します。たとえば、 `ContosoCase`のようになります。 この名前は大文字と小文字が区別されるので、以降の手順と同じ方法で入力する必要があることに注意してください。
    
4. [**ソース csv ファイル**] プロンプトで、csv ファイル拡張子を含む csv ファイルの名前を入力します。たとえば、 `ContosoCase.csv`のようになります。
    
5. **Enter**キーを押して、スクリプトの実行を続行します。 
    
    スクリプトには、検索の作成と実行の進行状況が表示されます。 スクリプトが完了すると、プロンプトに戻ります。 
    
    ![複数のコンプライアンス検索を作成するスクリプトを実行した場合の出力例](media/37d59b0d-5f89-4dbc-9e2d-0e88e2ed7b4c.png)
  
## <a name="step-4-run-the-script-to-report-the-search-estimates"></a>手順 4: 検索結果を報告するスクリプトを実行する

検索を作成した後、手順3で作成した各検索の検索ヒット数の簡単なレポートを表示するスクリプトを実行します。 レポートには、各検索の結果のサイズと、ヒットの合計数とすべての検索の合計サイズも含まれます。 レポートスクリプトを実行すると、検索グループ ID の入力を求められます。また、レポートを CSV ファイルに保存する場合は、CSV ファイル名を指定する必要があります。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `SearchReport.ps1`のようになります。 他のファイルを保存したのと同じフォルダーにファイルを保存します。
    
  ```Powershell
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

2. Windows PowerShell で、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：
    
    ```Powershell
    .\SearchReport.ps1
    ```

3. [**検索グループ ID** ] プロンプトで、検索グループ名を入力し、enter **** キーを押します。例`ContosoCase`を示します。 この名前は大文字と小文字が区別されるので、手順3でスクリプトを実行したときと同じ方法で入力する必要があります。
    
4. レポートを csv ファイルに保存するための**ファイルパス (空白のままに**してレポートを表示します) を入力します。レポートを csv ファイルに保存する場合は、完全なファイル名パス (.csv ファイル拡張子を含む) のファイル名を入力します。 csv ファイル拡張子を含む CSV ファイルの名前。 たとえば、現在のディレクトリに`ContosoCaseReport.csv`保存するか、別のフォルダーに保存`C:\Users\admin\OneDrive for Business\ContosoCase\ContosoCaseReport.csv`するように入力することができます。 また、メッセージを空白のままにしてレポートを表示することもできますが、ファイルに保存することはできません。 
    
5. **[Enter]** キーを押します。
    
    スクリプトには、検索の作成と実行の進行状況が表示されます。 スクリプトが完了すると、レポートが表示されます。 
    
    ![検索レポートを実行して検索グループの推定値を表示する](media/3b5f2595-71d5-4a14-9214-fad156c981f8.png)
  
> [!NOTE]
> 同じメールボックスまたはサイトが検索グループ内の複数の検索でコンテンツの場所として指定されている場合、レポート内の合計結果の推定 (アイテム数と合計サイズの両方) に同じアイテムに対する結果が含まれる可能性があります。 これは、同じ電子メールメッセージまたはドキュメントが検索グループ内のさまざまな検索のクエリに一致する場合に、複数回カウントされるためです。 
  
## <a name="step-5-run-the-script-to-delete-the-searches"></a>手順 5: 検索を削除するスクリプトを実行する

多数の検索を作成している可能性があるため、この最後のスクリプトにより、手順3で作成した検索を簡単に削除できるようになります。 他のスクリプトと同様に、この1つは検索グループ ID の入力も求められます。 このスクリプトを実行すると、検索グループ ID が指定されている検索はすべて削除されます。 
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `DeleteSearches.ps1`のようになります。 他のファイルを保存したのと同じフォルダーにファイルを保存します。
    
  ```Powershell
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

2. Windows PowerShell で、前の手順でスクリプトを保存したフォルダーに移動し、スクリプトを実行します。例えば：
    
    ```Powershell
    .\DeleteSearches.ps1
    ```

3. [**検索グループ ID** ] プロンプトで、削除する検索の検索グループ名を入力し、enter キーを押します****。たとえば、 `ContosoCase`のようになります。 この名前は大文字と小文字が区別されるので、手順3でスクリプトを実行したときと同じ方法で入力する必要があります。
    
    スクリプトは、削除された各検索の名前を表示します。
    
    ![検索グループ内の検索を削除するスクリプトを実行する](media/9d97b9d6-a539-4d9b-a4e4-e99989144ec7.png)
