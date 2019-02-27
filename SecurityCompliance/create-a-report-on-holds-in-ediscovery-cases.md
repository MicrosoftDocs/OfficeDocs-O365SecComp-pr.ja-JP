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
# <a name="create-a-report-on-holds-in-ediscovery-cases-in-office-365"></a><span data-ttu-id="38bb3-103">Office 365 で電子情報開示ケースの保留リストのレポートを作成する</span><span class="sxs-lookup"><span data-stu-id="38bb3-103">Create a report on holds in eDiscovery cases in Office 365</span></span>
  
<span data-ttu-id="38bb3-p101">この記事に記載されているスクリプトを使用すると、電子情報開示管理者と電子情報開示マネージャーは、Office 365 セキュリティ&amp;コンプライアンスセンターの電子情報開示ケースに関連付けられているすべての保留リストに関する情報を含むレポートを生成できます。このレポートには、保留リストが関連付けられているケースの名前、保留になっているコンテンツの場所、保留がクエリベースかどうかなどの情報が含まれています。保持されていないケースがある場合、スクリプトは、保留を行わないケースの一覧を含む追加のレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p101">The script in this article lets eDiscovery administrators and eDiscovery managers generate a report that contains information about all holds that are associated with eDiscovery cases in the Office 365 Security &amp; Compliance Center. The report contains information such as the name of the case a hold is associated with, the content locations that are placed on hold, and whether the hold is query-based. If there are cases that don't have any holds, the script will create an additional report with a list of cases without holds.</span></span>

<span data-ttu-id="38bb3-107">レポートに含まれる情報の詳細については、「 [More information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38bb3-107">See the [More information](#more-information) section for a detailed description of the information included in the report.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="38bb3-108">はじめに</span><span class="sxs-lookup"><span data-stu-id="38bb3-108">Before you begin</span></span>

- <span data-ttu-id="38bb3-p102">組織内のすべての電子情報開示ケースに関するレポートを生成するには、組織の電子情報開示管理者である必要があります。電子情報開示マネージャーの場合、レポートには、アクセスできるケースに関する情報のみが含まれます。電子情報開示のアクセス許可の詳細については、「 [Office 365 &amp;セキュリティコンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p102">To generate a report on all eDiscovery cases in your organization, you have to be an eDiscovery Administrator in your organization. If you are an eDiscovery Manager, the report will only include information about the cases that you can access. For more information about eDiscovery permissions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="38bb3-p103">この記事のスクリプトには、最小限のエラー処理が含まれています。主な目的は、組織内の電子情報開示ケースに関連付けられている保留リストに関するレポートをすばやく作成することです。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p103">The script in this article has minimal error handling. The primary purpose is to quickly create report about the holds that are associated with the eDiscovery cases in your organization.</span></span>
    
- <span data-ttu-id="38bb3-p104">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
    
## <a name="step-1-connect-to-the-security-amp-compliance-center-using-remote-powershell"></a><span data-ttu-id="38bb3-119">手順 1: リモート PowerShell を使用&amp;してセキュリティコンプライアンスセンターに接続する</span><span class="sxs-lookup"><span data-stu-id="38bb3-119">Step 1: Connect to the Security &amp; Compliance Center using Remote PowerShell</span></span>

<span data-ttu-id="38bb3-120">最初の手順として、Windows PowerShell を組織&amp;のセキュリティコンプライアンスセンターに接続します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-120">The first step is to connect Windows PowerShell to the Security &amp; Compliance Center for your organization.</span></span>
  
1. <span data-ttu-id="38bb3-121">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、 `ConnectSCC.ps1`のようになります。</span><span class="sxs-lookup"><span data-stu-id="38bb3-121">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, `ConnectSCC.ps1`.</span></span> 
    
      ```
      # Get login credentials 
      $UserCredential = Get-Credential 
      $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid -Credential $UserCredential -Authentication Basic -AllowRedirection 
      Import-PSSession $Session -AllowClobber -DisableNameChecking 
      $Host.UI.RawUI.WindowTitle = $UserCredential.UserName + " (Office 365 Security &amp; Compliance Center)" 
    ```

2. <span data-ttu-id="38bb3-122">ローカルコンピューターで、Windows PowerShell を開き、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-122">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="38bb3-123">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="38bb3-123">Run the script; for example:</span></span>

    ```
    .\ConnectSCC.ps1
    ```
   
4. <span data-ttu-id="38bb3-124">資格情報の入力を求められたら、電子メールアドレスとパスワードを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="38bb3-124">When prompted for your credentials, enter your email address and password, and then click **OK**.</span></span> 
  
## <a name="step-2-run-the-script-to-report-on-holds-associated-with-ediscovery-cases"></a><span data-ttu-id="38bb3-125">手順 2: 電子情報開示ケースに関連付けられている保留リストをレポートするスクリプトを実行する</span><span class="sxs-lookup"><span data-stu-id="38bb3-125">Step 2: Run the script to report on holds associated with eDiscovery cases</span></span>

<span data-ttu-id="38bb3-126">リモート PowerShell を使用してセキュリティ&amp;コンプライアンスセンターに接続した後、次の手順では、組織内の電子情報開示ケースに関する情報を収集するスクリプトを作成して実行します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-126">After you've connected to the Security &amp; Compliance Center with remote PowerShell, the next step is to create and run the script that collects information about the eDiscovery cases in your organization.</span></span> 
  
1. <span data-ttu-id="38bb3-127">ファイル名サフィックス. ps1 を使用して、次のテキストを Windows PowerShell スクリプトファイルに保存します。たとえば、CaseHoldsReport のようにします。</span><span class="sxs-lookup"><span data-stu-id="38bb3-127">Save the following text to a Windows PowerShell script file by using a filename suffix of .ps1; for example, CaseHoldsReport.ps1.</span></span> 
    
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

2. <span data-ttu-id="38bb3-128">手順1で開いた Windows PowerShell セッションで、スクリプトを保存したフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-128">In the Windows PowerShell session that opened in Step 1, go to the folder where you saved the script.</span></span> 
    
3. <span data-ttu-id="38bb3-129">スクリプトを実行します。例えば：</span><span class="sxs-lookup"><span data-stu-id="38bb3-129">Run the script; for example:</span></span>

    ```
    .\CaseHoldsReport.ps1
    ```

    <span data-ttu-id="38bb3-130">スクリプトは、レポートを保存するターゲットフォルダーの入力を求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-130">The script will prompt for a target folder to save the report to.</span></span> 
    
4. <span data-ttu-id="38bb3-131">レポートを保存するフォルダーの完全パス名を入力し、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-131">Type the full path name of the folder to save the report to, and then press **Enter**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="38bb3-p105">スクリプトが配置されているのと同じフォルダーにレポートを保存するには、ターゲットフォルダーの入力を求めるメッセージが表示されたら、ピリオド (".") を入力します。スクリプトが配置されているフォルダー内のサブフォルダーにレポートを保存するには、サブフォルダーの名前を入力するだけです。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p105">To save the report in the same folder that the script is located in, type a period (".") when prompted for a target folder. To save the report in a subfolder in the folder where the script is located, just type the name of the subfolder.</span></span> 
  
    <span data-ttu-id="38bb3-p106">このスクリプトは、組織内のすべての電子情報開示ケースに関する情報の収集を開始します。スクリプトの実行中はレポートファイルにアクセスしないでください。スクリプトが完了すると、Windows PowerShell セッションに確認メッセージが表示されます。このメッセージが表示された後、手順4で指定したフォルダー内のレポートにアクセスできます。レポートのファイル名は`CaseHoldsReport<DateTimeStamp>.csv`です。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p106">The script starts to collect information about all the eDiscovery cases in your organization. Don't access the report file while the script is running. After the script is complete, a confirmation message is displayed in the Windows PowerShell session. After this message is displayed, you can access the report in the folder that you specified in Step 4. The file name for the report is `CaseHoldsReport<DateTimeStamp>.csv`.</span></span>

    <span data-ttu-id="38bb3-p107">さらでは、このスクリプトは、保留がないケースの一覧を含むレポートも作成します。このレポートのファイル名は`CaseswithNoHolds<DateTimeStamp>.csv`です。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p107">Addtionally, the script also creates a report with a list of cases that don't have any holds. The file name for this report is `CaseswithNoHolds<DateTimeStamp>.csv`.</span></span>
    
    <span data-ttu-id="38bb3-141">CaseHoldsReport スクリプトを実行する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-141">Here's an example of running the CaseHoldsReport.ps1 script.</span></span> 
    
    ![CaseHoldsReport スクリプトを実行した後の出力](media/7d312ed5-505e-4ec5-8f06-3571e3524a1a.png)
  
## <a name="more-information"></a><span data-ttu-id="38bb3-143">詳細情報</span><span class="sxs-lookup"><span data-stu-id="38bb3-143">More information</span></span>

<span data-ttu-id="38bb3-p108">この記事のスクリプトを実行したときに作成されるケース保持レポートには、各ホールドに関する以下の情報が含まれています。前述のように、組織内のすべての保留リストに関する情報を返すには、電子情報開示管理者でなければなりません。ケース保持の詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターの電子情報開示ケース](ediscovery-cases.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p108">The case holds report that's created when you run the script in this article contains the following information about each hold. As previously explained, you have to be an eDiscovery Administrator to return information for all holds in your organization. For more information about case holds, see [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md).</span></span>
  
  - <span data-ttu-id="38bb3-147">保留の名前と、保留が関連付けられている電子情報開示ケースの名前。</span><span class="sxs-lookup"><span data-stu-id="38bb3-147">The name of the hold and the name of the eDiscovery case that the hold is associated with.</span></span>
    
  - <span data-ttu-id="38bb3-148">電子情報開示ケースがアクティブかクローズかを指定します。</span><span class="sxs-lookup"><span data-stu-id="38bb3-148">Whether or not the eDiscovery case is active or closed.</span></span>
    
  - <span data-ttu-id="38bb3-149">保留が有効であるか無効であるか。</span><span class="sxs-lookup"><span data-stu-id="38bb3-149">Whether or not the hold is enabled or disabled.</span></span>
    
  - <span data-ttu-id="38bb3-p109">保留が関連付けられている電子情報開示ケースのメンバ。ケースメンバーは、割り当てられている電子情報開示のアクセス許可に応じて、ケースを表示または管理できます。</span><span class="sxs-lookup"><span data-stu-id="38bb3-p109">The members of the eDiscovery case that the hold is associated with. Case members can view or manage a case, depending on the eDiscovery permissions they've been assigned.</span></span>
    
  - <span data-ttu-id="38bb3-152">ケースが作成された日時。</span><span class="sxs-lookup"><span data-stu-id="38bb3-152">The time and date the case was created.</span></span>
    
  - <span data-ttu-id="38bb3-153">ケースがクローズされている場合は、そのケースをクローズしたユーザーと、それがクローズされた日時。</span><span class="sxs-lookup"><span data-stu-id="38bb3-153">If a case is closed, the person who closed it and the time and date it was closed.</span></span>
    
  - <span data-ttu-id="38bb3-154">保留中の Exchange メールボックスと SharePoint サイトの場所。</span><span class="sxs-lookup"><span data-stu-id="38bb3-154">The Exchange mailboxes and SharePoint sites locations that are on hold.</span></span>
    
  - <span data-ttu-id="38bb3-155">保留がクエリベースの場合は、クエリ構文。</span><span class="sxs-lookup"><span data-stu-id="38bb3-155">If the hold is query-based, the query syntax.</span></span>
    
  - <span data-ttu-id="38bb3-156">保留が作成された日時と、それを作成したユーザー。</span><span class="sxs-lookup"><span data-stu-id="38bb3-156">The time and date the hold was created and the person who created it.</span></span>
    
  - <span data-ttu-id="38bb3-157">保留が最後に変更された日時と、それを変更したユーザー。</span><span class="sxs-lookup"><span data-stu-id="38bb3-157">The time and date the hold was last changed and the person who changed it.</span></span>
