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
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="fb8a2-103">Office 365 での電子的証拠開示のケース内の保留に関するレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="fb8a2-p101">この資料のスクリプトにより、管理者は電子的証拠開示や電子的証拠開示マネージャーが Office 365 のセキュリティで電子的証拠開示のサポート案件に関連付けられているすべての保留に関する情報を含むレポートを生成します&amp;コンプライアンス センターです。レポートには、保留リストは、クエリに基づくかどうかと、保留中のケースの名前は、保留リストに配置されているコンテンツの場所に関連付けられているなど、情報が含まれています。保留リストがない場合がある場合、スクリプトを保持せずにケースの一覧に追加のレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p101">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the Office 365 Security &amp; Compliance Center. The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based. If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="fb8a2-107">詳細については、レポートに含まれる情報の[詳細について](#more-information)はを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="fb8a2-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="fb8a2-108">Before you begin</span></span>

- <span data-ttu-id="fb8a2-p102">組織のすべての電子的証拠開示のサポート案件に関するレポートを生成するには、管理者、組織の電子情報開示をする必要があります。電子的証拠開示マネージャー場合は、レポートはのみにアクセスできる場合についての情報を含まれます。電子的証拠開示の権限の詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p102">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization. If you are an eDiscovery Manager, the report will only include information about the cases that you can access. For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="fb8a2-p103">この資料のスクリプトには、最低限のエラー処理があります。主な目的は、組織で電子的証拠開示のサポート案件に関連付けられている保留リストに関するレポートをすばやく作成するのには。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p103">The script in this article has minimal error handling. The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="fb8a2-p104">このトピックで提供されるサンプル スクリプトは、Microsoft の標準サポート プログラムまたはサービスでサポートされていません。サンプル スクリプトは、どのような種類の保証もなく、IS として提供されます。さらに、Microsoft はいかなる黙示の保証を含む、いずれかのもので、商品性または特定目的に対する適合性の。サンプル スクリプトおよびドキュメントのパフォーマンスまたは使用から生じるすべてのリスク負担しなければなりません。いかなる場合においてマイクロソフト、著者、または、作成、生産、またはスクリプトの配信に参加するすべてのユーザーを負いませんいかなる損害に対して損害を含め、制限、ビジネス利益、業務の中断、損失の損失の損害ビジネス情報、またはその他の金銭の損失) マイクロソフトが損害の可能性について知らされていた場合でもに、サンプル スクリプトまたはドキュメントを使用すること、または使用から生じる。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a><span data-ttu-id="fb8a2-119">手順 1: セキュリティを保護する接続を使用する&amp;リモート PowerShell を使用してコンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="fb8a2-119">Step 1: Connect to the Security &amp; Compliance Center using Remote PowerShell</span></span>

<span data-ttu-id="fb8a2-120">最初の手順は、セキュリティを保護する Windows PowerShell を接続する&amp;、組織のコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-120">The first step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="fb8a2-121">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、 `ConnectSCC.ps1`。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="fb8a2-122">ローカル コンピューターに Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="fb8a2-123">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="fb8a2-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="fb8a2-124">資格情報のダイアログ ボックスが表示されたらの電子メール アドレスとパスワードを入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="fb8a2-125">手順 2: 実行を報告するスクリプトを保持する電子的証拠開示のサポート案件に関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="fb8a2-126">セキュリティに接続した後&amp;を作成し、組織内の電子的証拠開示のサポート案件に関する情報を収集するスクリプトを実行する次の手順は、リモート PowerShell でコンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-126">After you've connected to the Security &amp; Compliance Center with remote PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="fb8a2-127">.Ps1 のファイル名サフィックスを使用して Windows PowerShell スクリプト ファイルに次のテキストを保存します。たとえば、CaseHoldsReport.ps1 です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="fb8a2-128">Windows PowerShell セッションのステップ 1 では、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="fb8a2-129">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="fb8a2-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="fb8a2-130">スクリプトの対象となるフォルダーにレポートを保存するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="fb8a2-131">、レポートを保存するフォルダーの完全パス名を入力し、 **Enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="fb8a2-p105">スクリプトが配置されている同じフォルダーにレポートを保存するには、ピリオドを入力 ("です。") 対象となるフォルダーのメッセージが表示されたら。レポートを保存して、スクリプトが格納されているフォルダーのサブフォルダーに、単にサブフォルダーの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p105">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder. To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="fb8a2-p106">スクリプトは、組織内のすべての電子的証拠開示サポート案件に関する情報を収集するために起動します。スクリプトの実行中に、レポート ファイルにアクセスしません。スクリプトが完了した後、確認のメッセージは、Windows PowerShell セッションに表示されます。このメッセージが表示されたら、手順 4 で指定したフォルダー内のレポートにアクセスできます。レポートのファイル名は`CaseHoldsReport<DateTimeStamp>.csv`です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p106">The script starts to collect information about all the eDiscovery cases in your organization. Don't access the report file while the script is running. After the script is complete, a confirmation message is displayed in the Windows PowerShell session. After this message is displayed, you can access the report in the folder that you specified in Step 4. The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="fb8a2-p107">Addtionally、スクリプトのレポートも作成、保留リストがない場合の一覧です。このレポートのファイル名は`CaseswithNoHolds<DateTimeStamp>.csv`です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p107">Addtionally, the script also creates a report with a list of cases that don't have any holds. The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="fb8a2-141">ここでは、CaseHoldsReport.ps1 スクリプトを実行した例です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![CaseHoldsReport.ps1 スクリプトの実行後の出力](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="fb8a2-143">詳細情報</span><span class="sxs-lookup"><span data-stu-id="fb8a2-143">More information</span></span>

<span data-ttu-id="fb8a2-p108">この資料のスクリプトを実行するときに作成されるレポートには、各保留リストに関する次の情報が含まれています大文字と小文字が保持されます。説明したように電子的証拠開示、組織内のすべての保留の情報を取得するには管理者があります。ケースの詳細を保持しているを参照してください[電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md)です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p108">The case holds report that's created when you run the script in this article contains the following information about each hold. As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization. For more information about case holds, see [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="fb8a2-147">保留と保留リストが関連付けられている電子的証拠開示の場合の名前の名前です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="fb8a2-148">かどうか電子的証拠開示は、アクティブまたは終了しました。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="fb8a2-149">保留リストが有効か無効かどうか。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="fb8a2-p109">保留リストが関連付けられている電子的証拠開示の場合のメンバーです。ケースのメンバーでは、表示したり、場合は、それらが割り当てられている電子的証拠開示のアクセス権を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-p109">The members of the eDiscovery case that the hold is associated with. Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="fb8a2-152">大文字と小文字が作成された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="fb8a2-153">ケースが閉じている場合と、時間の終了の日付、ある人は閉じられました。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="fb8a2-154">Exchange メールボックスと SharePoint サイトの保留中の場所です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="fb8a2-155">保留リストのクエリに基づく場合、クエリ構文です。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="fb8a2-156">時間と保留リストの作成日と作成した人。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="fb8a2-157">時間と保留リストの最終変更日と変更した人。</span><span class="sxs-lookup"><span data-stu-id="fb8a2-157">The time and date the hold was last changed and the person who changed it.</span></span>
