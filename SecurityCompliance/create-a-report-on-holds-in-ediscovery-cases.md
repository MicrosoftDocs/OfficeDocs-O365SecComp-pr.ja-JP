---
title: Office 365 での電子的証拠開示のケース内の保留に関するレポートを作成します。
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: この資料のスクリプトを使用して、Office 365 のセキュリティで電子的証拠開示のサポート案件に関連付けられているすべての保留に関する情報を含むレポートを生成します&amp;コンプライアンス センターです。
ms.openlocfilehash: 8bc1285f776e2b1aa0c0330c06ccffff8ce4585c
ms.sourcegitcommit: c166964fe14eec69139a2d3d9c10d2c40ab33f91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258645"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>Office 365 での電子的証拠開示のケース内の保留に関するレポートを作成します。
  
この資料のスクリプトにより、管理者は電子的証拠開示や電子的証拠開示マネージャーが Office 365 のセキュリティで電子的証拠開示のサポート案件に関連付けられているすべての保留に関する情報を含むレポートを生成します&amp;コンプライアンス センターです。レポートには、保留リストは、クエリに基づくかどうかと、保留中のケースの名前は、保留リストに配置されているコンテンツの場所に関連付けられているなど、情報が含まれています。保留リストがない場合がある場合、スクリプトを保持せずにケースの一覧に追加のレポートを作成します。

詳細については、レポートに含まれる情報の[詳細について](#more-information)はを参照してください。 
  
## <a name="before-you-begin"></a>はじめに

- 組織のすべての電子的証拠開示のサポート案件に関するレポートを生成するには、管理者、組織の電子情報開示をする必要があります。電子的証拠開示マネージャー場合は、レポートはのみにアクセスできる場合についての情報を含まれます。電子的証拠開示の権限の詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。
    
- この資料のスクリプトには、最低限のエラー処理があります。主な目的は、組織で電子的証拠開示のサポート案件に関連付けられている保留リストに関するレポートをすばやく作成するのには。
    
- このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a>手順 1: セキュリティを保護する接続を使用する&amp;リモート PowerShell を使用してコンプライアンス センター

最初の手順は、セキュリティを保護する Windows PowerShell を接続する&amp;、組織のコンプライアンス センターです。
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `ConnectSCC.ps1`。 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. ローカル コンピューターに Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。 
    
3. スクリプトを実行します。例えば：

    ```
    .\ConnectSCC.ps1
    ```
   
4. 資格情報のダイアログ ボックスが表示されたらの電子メール アドレスとパスワードを入力し、し、[ **OK**] をクリックします。 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>手順 2: 実行を報告するスクリプトを保持する電子的証拠開示のサポート案件に関連付けられています。

セキュリティに接続した後&amp;を作成し、組織内の電子的証拠開示のサポート案件に関する情報を収集するスクリプトを実行する次の手順は、リモート PowerShell でコンプライアンス センターです。 
  
1. .Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、CaseHoldsReport.ps1 です。 
    
  ```
#script begin
" " 
write-host "***********************************************"
write-host "   Office 365 Security & Compliance Center   " -foregroundColor yellow -backgroundcolor darkgreen
write-host "        eDiscovery cases - Holds report         " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" " 
#prompt users to specify a path to store the output files
$time=get-date
$Path = Read-Host 'Enter a file path to save the report to a .csv file'
$outputpath=$Path+'\'+'CaseHoldsReport'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
$noholdsfilepath=$Path+'\'+'CaseswithNoHolds'+' '+$time.day+'-'+$time.month+'-'+$time.year+' '+$time.hour+'.'+$time.minute+'.csv'
#add case details to the csv file
function add-tocasereport{
Param([string]$casename,
[String]$casestatus,
[datetime]$casecreatedtime,
[string]$casemembers,
[datetime]$caseClosedDateTime,
[string]$caseclosedby,
[string]$holdname,
[String]$Holdenabled,
[string]$holdcreatedby,
[string]$holdlastmodifiedby,
[string]$ExchangeLocation,
[string]$sharePointlocation,
[string]$ContentMatchQuery,
[datetime]$holdcreatedtime,
[datetime]$holdchangedtime
)
$addRow = New-Object PSObject 
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case name" -Value $casename
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case status" -Value $casestatus
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case members" -Value $casemembers
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case created time" -Value $casecreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed time" -Value $caseClosedDateTime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Case closed by" -Value $caseclosedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold name" -Value $holdname
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold enabled" -Value $Holdenabled
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created by" -Value $holdcreatedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold last changed by" -Value $holdlastmodifiedby
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Exchange locations" -Value  $ExchangeLocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "SharePoint locations" -Value $sharePointlocation
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold query" -Value $ContentMatchQuery
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold created time (UTC)" -Value $holdcreatedtime
Add-Member -InputObject $addRow -MemberType NoteProperty -Name "Hold changed time (UTC)" -Value $holdchangedtime
$allholdreport = $addRow | Select-Object "Case name","Case status","Hold name","Hold enabled","Case members", "Case created time","Case closed time","Case closed by","Exchange locations","SharePoint locations","Hold query","Hold created by","Hold created time (UTC)","Hold last changed by","Hold changed time (UTC)"
$allholdreport | export-csv -path $outputPath -notypeinfo -append -Encoding ascii 
}
#get information on the cases and pass values to the case report function
" "
write-host "Gathering a list of cases and holds..."
" "
$edc =Get-ComplianceCase -ErrorAction SilentlyContinue
foreach($cc in $edc)
{
write-host "Working on case :" $cc.name
if($cc.status -eq 'Closed')
{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
add-tocasereport -casename $cc.name -casestatus $cc.Status -caseclosedby $cc.closedby -caseClosedDateTime $cc.ClosedDateTime -casemembers $cmembers 
}
else{
$cmembers = ((Get-ComplianceCaseMember -Case $cc.name).windowsLiveID)-join ';'
$policies = Get-CaseHoldPolicy -Case $cc.Name | %{ Get-CaseHoldPolicy $_.Name -Case $_.CaseId -DistributionDetail}
if ($policies -ne $NULL)
{
foreach ($policy in $policies)
{
$rule=Get-CaseHoldRule -Policy $policy.name
add-tocasereport -casename $cc.name -casemembers $cmembers -casestatus $cc.Status -casecreatedtime $cc.CreatedDateTime -holdname $policy.name -holdenabled $policy.enabled -holdcreatedby $policy.CreatedBy -holdlastmodifiedby $policy.LastModifiedBy -ExchangeLocation (($policy.exchangelocation.name)-join ';') -SharePointLocation (($policy.sharePointlocation.name)-join ';') -ContentMatchQuery $rule.ContentMatchQuery -holdcreatedtime $policy.WhenCreatedUTC -holdchangedtime $policy.WhenChangedUTC
}
}
else{
write-host "No hold policies found in case:" $cc.name -foregroundColor 'Yellow'
" "
[string]$cc.name | out-file -filepath $noholdsfilepath -append 
}
}
}

" "
Write-host "Script complete! Report files saved to this folder: '$Path'"
" "
#script end
  ```

2. Windows PowerShell セッションのステップ 1 では、スクリプトを保存したフォルダーに移動します。 
    
3. スクリプトを実行します。例えば：

    ```
    .\CaseHoldsReport.ps1
    ```

    スクリプトの対象となるフォルダーにレポートを保存するメッセージが表示されます。 
    
4. 、レポートを保存するフォルダーの完全パス名を入力し、 **Enter**キーを押します。
    
    > [!TIP]
    > スクリプトが配置されている同じフォルダーにレポートを保存するには、ピリオドを入力 ("です。") 対象となるフォルダーのメッセージが表示されたら。レポートを保存して、スクリプトが格納されているフォルダーのサブフォルダーに、単にサブフォルダーの名前を入力します。 
  
    スクリプトは、組織内のすべての電子的証拠開示サポート案件に関する情報を収集するために起動します。スクリプトの実行中に、レポート ファイルにアクセスしません。スクリプトが完了した後、確認のメッセージは、Windows PowerShell セッションに表示されます。このメッセージが表示されたら、手順 4 で指定したフォルダー内のレポートにアクセスできます。レポートのファイル名は`CaseHoldsReport<DateTimeStamp>.csv`です。

    Addtionally、スクリプトのレポートも作成、保留リストがない場合の一覧です。このレポートのファイル名は`CaseswithNoHolds<DateTimeStamp>.csv`です。
    
    ここでは、CaseHoldsReport.ps1 スクリプトを実行した例です。 
    
    ![CaseHoldsReport.ps1 スクリプトの実行後の出力](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>詳細情報

この資料のスクリプトを実行するときに作成されるレポートには、各保留リストに関する次の情報が含まれています大文字と小文字が保持されます。説明したように電子的証拠開示、組織内のすべての保留の情報を取得するには管理者があります。ケースの詳細を保持しているを参照してください[電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md)です。
  
  - 保留と保留リストが関連付けられている電子的証拠開示の場合の名前の名前です。
    
  - かどうか電子的証拠開示は、アクティブまたは終了しました。
    
  - 保留リストが有効か無効かどうか。
    
  - 保留リストが関連付けられている電子的証拠開示の場合のメンバーです。ケースのメンバーでは、表示したり、場合は、それらが割り当てられている電子的証拠開示のアクセス権を管理することができます。
    
  - 大文字と小文字が作成された日付と時刻。
    
  - ケースが閉じている場合と、時間の終了の日付、ある人は閉じられました。
    
  - Exchange メールボックスと SharePoint サイトの保留中の場所です。
    
  - 保留リストのクエリに基づく場合、クエリ構文です。
    
  - 時間と保留リストの作成日と作成した人。
    
  - 時間と保留リストの最終変更日と変更した人。
