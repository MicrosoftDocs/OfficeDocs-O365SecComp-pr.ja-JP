---
title: Office 365 で電子情報開示ケースの保留リストのレポートを作成する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 9/11/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: cca08d26-6fbf-4b2c-b102-b226e4cd7381
description: この記事のスクリプトを使用して、Office 365 セキュリティ&amp;コンプライアンスセンターの電子情報開示ケースに関連付けられているすべての保留リストに関する情報を含むレポートを生成します。
ms.openlocfilehash: 95a960e8f76c672185e10d5b6be2a7ff2538a34b
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297000"
---
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a>Office 365 で電子情報開示ケースの保留リストのレポートを作成する
  
この記事に記載されているスクリプトを使用すると、電子情報開示管理者と電子情報開示マネージャーは、Office 365 セキュリティ&amp;コンプライアンスセンターの電子情報開示ケースに関連付けられているすべての保留リストに関する情報を含むレポートを生成できます。このレポートには、保留リストが関連付けられているケースの名前、保留になっているコンテンツの場所、保留がクエリベースかどうかなどの情報が含まれています。保持されていないケースがある場合、スクリプトは、保留を行わないケースの一覧を含む追加のレポートを作成します。

レポートに含まれる情報の詳細については、「 [More information](#more-information) 」セクションを参照してください。 
  
## <a name="before-you-begin"></a>はじめに

- 組織内のすべての電子情報開示ケースに関するレポートを生成するには、組織の電子情報開示管理者である必要があります。電子情報開示マネージャーの場合、レポートには、アクセスできるケースに関する情報のみが含まれます。電子情報開示のアクセス許可の詳細については、「 [Office 365 &amp;セキュリティコンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。
    
- この記事のスクリプトには、最小限のエラー処理が含まれています。主な目的は、組織内の電子情報開示ケースに関連付けられている保留リストに関するレポートをすばやく作成することです。
    
- このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a>手順 1: リモート PowerShell を使用&amp;してセキュリティコンプライアンスセンターに接続する

最初の手順として、Windows PowerShell を組織&amp;のセキュリティコンプライアンスセンターに接続します。
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `ConnectSCC.ps1`のようになります。 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。 
    
3. スクリプトを実行します。例えば：

    ```
    .\ConnectSCC.ps1
    ```
   
4. 資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a>手順 2: 電子情報開示ケースに関連付けられている保留リストをレポートするスクリプトを実行する

リモート PowerShell を使用してセキュリティ&amp;コンプライアンスセンターに接続した後、次の手順では、組織内の電子情報開示ケースに関する情報を収集するスクリプトを作成して実行します。 
  
1. ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、CaseHoldsReport のようにします。 
    
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

2. 手順1で開いた Windows PowerShell セッションで、スクリプトを保存したフォルダーに移動します。 
    
3. スクリプトを実行します。例えば：

    ```
    .\CaseHoldsReport.ps1
    ```

    スクリプトは、レポートを保存するターゲットフォルダーの入力を求めるメッセージを表示します。 
    
4. レポートを保存するフォルダーの完全パス名を入力し、 **enter**キーを押します。
    
    > [!TIP]
    > スクリプトが配置されているのと同じフォルダーにレポートを保存するには、ターゲットフォルダーの入力を求めるメッセージが表示されたら、ピリオド (".") を入力します。スクリプトが配置されているフォルダー内のサブフォルダーにレポートを保存するには、サブフォルダーの名前を入力するだけです。 
  
    このスクリプトは、組織内のすべての電子情報開示ケースに関する情報の収集を開始します。スクリプトの実行中はレポートファイルにアクセスしないでください。スクリプトが完了すると、Windows PowerShell セッションに確認メッセージが表示されます。このメッセージが表示された後、手順4で指定したフォルダー内のレポートにアクセスできます。レポートのファイル名は`CaseHoldsReport<DateTimeStamp>.csv`です。

    さらでは、このスクリプトは、保留がないケースの一覧を含むレポートも作成します。このレポートのファイル名は`CaseswithNoHolds<DateTimeStamp>.csv`です。
    
    CaseHoldsReport スクリプトを実行する例を次に示します。 
    
    ![CaseHoldsReport スクリプトを実行した後の出力](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a>詳細情報

この記事のスクリプトを実行したときに作成されるケース保持レポートには、各ホールドに関する以下の情報が含まれています。前述のように、組織内のすべての保留リストに関する情報を返すには、電子情報開示管理者でなければなりません。ケース保持の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターの電子情報開示ケース](ediscovery-cases.md)」を参照してください。
  
  - 保留の名前と、保留が関連付けられている電子情報開示ケースの名前。
    
  - 電子情報開示ケースがアクティブかクローズかを指定します。
    
  - 保留が有効であるか無効であるか。
    
  - 保留が関連付けられている電子情報開示ケースのメンバ。ケースメンバーは、割り当てられている電子情報開示のアクセス許可に応じて、ケースを表示または管理できます。
    
  - ケースが作成された日時。
    
  - ケースがクローズされている場合は、そのケースをクローズしたユーザーと、それがクローズされた日時。
    
  - 保留中の Exchange メールボックスと SharePoint サイトの場所。
    
  - 保留がクエリベースの場合は、クエリ構文。
    
  - 保留が作成された日時と、それを作成したユーザー。
    
  - 保留が最後に変更された日時と、それを変更したユーザー。
