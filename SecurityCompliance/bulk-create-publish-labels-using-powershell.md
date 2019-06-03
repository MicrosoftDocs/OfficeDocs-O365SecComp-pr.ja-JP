---
title: PowerShell を使用して保持ラベルを一括で作成および発行する
ms.author: stephow
author: stephow-msft
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Office 365 では、保持ラベルを使って組織の保持スケジュールを実装できます。レコード マネージャーまたは法令遵守責任者は、数百もの保持ラベルを作成して発行する場合があります。これはセキュリティ/コンプライアンス センターの UI を使って行うことができますが、保持ラベルを一度に 1 つずつ作成するのは時間がかかり、非効率です。以下に示す .csv ファイルとスクリプトを使って、保持ラベルと保持ラベル ポリシーを一括作成して発行することができます。まず、Excel で保持ラベルのリストと保持ラベル ポリシーのリストを作成してから、そのリストの保持ラベルと保持ラベル ポリシーを PowerShell を使って一括作成します。これで、保持スケジュールで必要な保持ラベルをすべて一度に簡単に作成して発行できます。
ms.openlocfilehash: 1b6ab634ee0f168392981026367a3b8b2e98f5f8
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590550"
---
# <a name="bulk-create-and-publish-retention-labels-by-using-powershell"></a><span data-ttu-id="d59fc-108">PowerShell を使用して保持ラベルを一括で作成および発行する</span><span class="sxs-lookup"><span data-stu-id="d59fc-108">Bulk create and publish retention labels by using PowerShell</span></span>

<span data-ttu-id="d59fc-p102">Office 365 では、保持ラベルを使用して組織の保持スケジュールを実装できます。レコード マネージャーまたは法令遵守責任者は、作成および発行すべき保持ラベルを何百も持っている可能性があります。セキュリティ &amp; コンプライアンス センターの UI で保持ラベルの作成と発行を行うことができますが、一度に 1 つずつ保持ラベルを作成するのは時間がかかり、非効率です。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p102">In Office 365, you can use labels to implement a retention schedule for your organization. As a record manager or compliance officer, you might have hundreds of labels to create and publish. You can do this through the UI in the Security &amp; Compliance Center, but creating labels one at a time is time-consuming and inefficient.</span></span>
  
<span data-ttu-id="d59fc-p103">以下のスクリプトと .csv ファイルを使用すると、保持ラベルを一括で作成し、保持ラベル ポリシーを発行することができます。まず、保持ラベルのリストと保持ラベル ポリシーのリストを Excel で作成し、PowerShell を使用してそれらのリスト内の保持ラベルと保持ラベル ポリシーを一括作成します。これにより、保持スケジュールに必要なすべての保持ラベルを一度に作成して発行することが容易になります。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p103">By using the script and .csv files provided below, you can bulk create and publish labels and label policies. First you create a list of the labels and a list of the label policies in Excel, and then you bulk create the labels and label policies in those lists by using PowerShell. This makes it easier to create and publish at one time all of the labels that your retention schedule requires.</span></span>
  
<span data-ttu-id="d59fc-115">保持ラベルの詳細については、「[ラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d59fc-115">For more information about labels, see [Overview of labels](labels.md).</span></span>
  
## <a name="disclaimer"></a><span data-ttu-id="d59fc-116">免責事項</span><span class="sxs-lookup"><span data-stu-id="d59fc-116">Disclaimer</span></span>

<span data-ttu-id="d59fc-p104">このトピックで提供されているサンプル スクリプトは、いかなる Microsoft 標準サポート プログラムまたはサービスでもサポートされていません。サンプル スクリプトは、いかなる保証もありません。これらのサンプルに対しては、Microsoft 社は商品またはその他の何らかの目的を持つものに付随すると考えられている暗黙の責任も一切認めません。これらのサンプルは、完全にユーザーの責任において使用してください。いかなる場合でも、Microsoft 社および販売店は、これらのサンプルを使用した結果発生した損害およびこれらのサンプルを使用できなかったことによる損害に対して、商業的損失、業務の中断、企業情報の喪失、およびその他の金銭的損失等を含め、何ら制限も設けることなく一切の責任を認めません。これは、たとえ Microsoft 社がそのような損害の可能性について通知を受けていた場合でも同じです。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p104">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>
  
## <a name="step-1-create-a-csv-file-for-creating-the-retention-labels"></a><span data-ttu-id="d59fc-122">手順 1: 保持ラベルを作成するための .csv ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d59fc-122">Step 1: Create a .csv file for creating the labels</span></span>

<span data-ttu-id="d59fc-p105">まず、設定を持つ保持ラベルのリストを含む .csv ファイルを作成します。下のサンプルを Excel にコピーしてテンプレートとして使用し、テキストを列に変換します (Excel で \>**[データ]** タブ\>**[区切り位置]**\>**[コンマやタブなどの区切り文字によってフィールドごとに区切られたデータ]**\>**[コンマ]**\>**[一般]** を選択します)。次にワークシートを見つけやすい場所に .csv ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p105">First you create a .csv file that contains a list of your labels with their retention settings. You can use the sample below as a template by copying it into Excel, converting the text to columns (in Excel \> **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**), and then saving the worksheet as a .csv file in a location that's easy to find.</span></span>
  
<span data-ttu-id="d59fc-125">このコマンドレットのパラメーター値の詳細については、「[New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d59fc-125">For more information about the parameter values for this cmdlet, see [New-ComplianceTag](https://go.microsoft.com/fwlink/?linkid=866511).</span></span>
  
<span data-ttu-id="d59fc-126">注:</span><span class="sxs-lookup"><span data-stu-id="d59fc-126">Notes:</span></span>
  
- <span data-ttu-id="d59fc-127">保持ラベルを作成するためのソース ファイルを指定しない場合、スクリプトは進行し、保持ラベルを発行するためのソース ファイルを要求してきます (次のセクションを参照)。スクリプトは既存の保持ラベルのみを発行します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-127">If you don't provide a source file for creating labels, the script moves on and prompts you for the source file for publishing labels (see the next section), and the script will publish only existing labels.</span></span>
    
- <span data-ttu-id="d59fc-p106">既に存在するものと同じ名前の保持ラベルが .csv ファイルに含まれている場合、スクリプトはその保持ラベルの作成をスキップします。重複する保持ラベルは作成されません。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p106">If the .csv file contains a label with the same name as one that already exists, the script skips creating that label. No duplicate labels are created.</span></span>
    
- <span data-ttu-id="d59fc-p107">列見出しを変更したり、名前を変更したりすると、スクリプトは失敗します。このスクリプトでは、ここに示す形式の .csv ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p107">If you change or rename the column headers, the script will fail. The script requires a .csv file in the format provided here.</span></span>
    
### <a name="sample-csv-file"></a><span data-ttu-id="d59fc-132">CSV ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="d59fc-132">Sample .csv file</span></span>

```
Name (Required),Comment (Optional),IsRecordLabel (Required),RetentionAction (Optional),RetentionDuration (Optional),RetentionType (Optional),ReviewerEmail (Optional)
LabelName_t_1,Record - keep and delete - 2 years,$true,KeepAndDelete,730,CreationAgeInDays,
LabelName_t_2,Keep and delete tag - 7 years,$false,KeepAndDelete,2555,ModificationAgeInDays,
LabelName_t_3,5 year delete,$false,Delete,1825,TaggedAgeInDays,
LabelName_t_4,Record label tag - financial,$true,Keep,730,CreationAgeInDays,
```

## <a name="step-2-create-a-csv-file-for-publishing-the-labels"></a><span data-ttu-id="d59fc-133">手順 2: ラベルを発行するための .csv ファイルを作成する</span><span class="sxs-lookup"><span data-stu-id="d59fc-133">Step 2: Create a .csv file for publishing the labels</span></span>

<span data-ttu-id="d59fc-p108">次に、場所とその他の設定を持つ保持ラベル ポリシーのリストを含む .csv ファイルを作成します。下のサンプルを Excel にコピーしてテンプレートとして使用し、テキストを列に変換します (Excel で \>**[データ]** タブ\>**[区切り位置]**\>**[コンマやタブなどの区切り文字によってフィールドごとに区切られたデータ]**\>**[コンマ]**\>**[一般]** を選択します)。次にワークシートを見つけやすい場所に .csv ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p108">Next you create a .csv file that contains a list of label policies with their locations and other settings. You can use the sample below as a template by copying it into Excel, converting the text to columns (in Excel \> **Data** tab \> **Text to Columns** \> **Delimited** \> **Comma** \> **General**), and then saving the worksheet as a .csv file in a location that's easy to find.</span></span>
  
<span data-ttu-id="d59fc-136">このコマンドレットのパラメーター値の詳細については、「[New-RetentionCompliancePolicy](https://go.microsoft.com/fwlink/?linkid=866512)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d59fc-136">For more information about the parameter values for this cmdlet, see [New-RetentionCompliancePolicy](https://go.microsoft.com/fwlink/?linkid=866512).</span></span>
  
<span data-ttu-id="d59fc-137">注:</span><span class="sxs-lookup"><span data-stu-id="d59fc-137">Notes:</span></span>
  
- <span data-ttu-id="d59fc-138">保持ラベルを発行するためのソース ファイルを指定していない場合、スクリプトで保持ラベルは作成されますが (前のセクションを参照)、発行されません。</span><span class="sxs-lookup"><span data-stu-id="d59fc-138">If you don't provide a source file for publishing labels, the script creates labels (see the previous section) but does not publish them.</span></span>
    
- <span data-ttu-id="d59fc-p109">既に存在するものと同じ名前の保持ラベル ポリシーが .csv ファイルに含まれている場合、スクリプトはその保持ラベル ポリシーの作成をスキップします。重複する保持ラベル ポリシーは作成されません。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p109">If the .csv file contains a label policy with the same name as one that already exists, the script skips creating that label policy. No duplicate label policies are created.</span></span>
    
- <span data-ttu-id="d59fc-p110">スクリプトは、コンテンツに手動で適用される保持ラベルのみを発行します。また、コンテンツに自動で適用される保持ラベルはサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p110">The script publishes only labels that are applied manually to content. This script does not support labels that are auto-applied to content.</span></span>
    
- <span data-ttu-id="d59fc-p111">列見出しを変更したり、名前を変更したりすると、スクリプトは失敗します。このスクリプトでは、ここに示す形式の .csv ファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p111">If you change or rename the column headers, the script will fail. The script requires a .csv file in the format provided here.</span></span>
    
### <a name="sample-csv-file"></a><span data-ttu-id="d59fc-145">CSV ファイルのサンプル</span><span class="sxs-lookup"><span data-stu-id="d59fc-145">Sample .csv file</span></span>

```
Policy Name (Required),PublishComplianceTag (Required),Comment (Optional),Enabled (Required),ExchangeLocation (Optional),ExchangeLocationException (Optional),ModernGroupLocation (Optional),ModernGroupLocationException (Optional),OneDriveLocation (Optional),OneDriveLocationException (Optional),PublicFolderLocation (Optional),SharePointLocation (Optional),SharePointLocationException (Optional),SkypeLocation (Optional),SkypeLocationException (Optional)
Publishing Policy Red1,"LabelName_t_1, LabelName_t_2, LabelName_t_3, LabelName_t_4",N/A,$true,All,,All,,All,,,All,,,
Publishing Policy Orange1,"LabelName_t_1, LabelName_t_2",N/A,$true,All,,,,,,,,,,
Publishing Policy Yellow1,"LabelName_t_3, LabelName_t_4",N/A,$false,All,,,,,,,,,,
```

## <a name="step-3-create-the-powershell-script"></a><span data-ttu-id="d59fc-146">手順 3: PowerShell スクリプトを作成する</span><span class="sxs-lookup"><span data-stu-id="d59fc-146">Step 3: Create the PowerShell script</span></span>

<span data-ttu-id="d59fc-p112">以下の PowerShell スクリプトをコピーしてメモ帳に貼り付けます。\<path\>CreateRetentionSchedule.ps1 のように、ファイル名にサフィックス .ps1 を使用して、簡単に見つけやすい場所にファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p112">Copy and paste the below PowerShell script into Notepad. Save the file by using a filename suffix of .ps1 in a location that's easy to find -- for example, \<path\>CreateRetentionSchedule.ps1.</span></span>
  
### <a name="powershell-script"></a><span data-ttu-id="d59fc-149">PowerShell スクリプト</span><span class="sxs-lookup"><span data-stu-id="d59fc-149">PowerShell script</span></span>

```
<#
. Steps: Import and Publish Compliance Tag
    ○ Load compliance tag csv file 
    ○ Validate csv file input
    ○ Create compliance tag
    ○ Create compliance policy
    ○ Publish compliance tag for the policy
    ○ Generate the log for tags creation
    ○ Generate the csv result for the tags created and published
. Syntax
    .\Publish-ComplianceTag.ps1 [-LabelListCSV <string>] [-PolicyListCSV <string>] 
. Detailed Description
    1) [-LabelListCSV <string>]
    -LabelListCSV ".\SampleInputFile_LabelList.csv"
    Load compliance tag for creation.
    2) [-PolicyListCSV <string>]
    -PolicyListCSV ".\SampleInputFile_PolicyList.csv"
    Load compliance tag for creation.
#>
param (
    [Parameter(Mandatory = $true)]
    [string]$LabelListCSV = "",
    [Parameter(Mandatory = $true)]
    [string]$PolicyListCSV = "",
    [Switch]$ResultCSV
)
# -------------------
# File operation
# -------------------
Function FileExist
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath,
        [Switch]$Warning
    )
    $inputFileExist = Test-Path $FilePath
    if (!$inputFileExist)
    {
        if ($Warning -eq $false) 
        { 
            WriteToLog -Type "Failed" -Message "[File: $FilePath] The file doesn't exist"
            throw 
        }
        else 
        { 
            WriteToLog -Type "Warning" -Message "[File: $FilePath] The file doesn't exist"
        }
    }
    else
    {
        WriteToLog -Type "Succeed" -Message "[File: $FilePath] The file is found"
    }
}
# -------------------
# Log operation
# -------------------
Function WriteToLog
{
    Param(
        # Message want to write to log file
        [Parameter(Mandatory = $true)]
        [String]$Message,
        # "Succeed" or "Faild"
        [String]$Type = "Message"
    )
    $date = Get-Date -Format 'HH:mm:ss'
    $logInfo = $date + " - [$Type] " + $Message
    $logInfo | Out-File -FilePath $logfilePath -Append
    if ($Type -eq "Succeed") { Write-Host $logInfo -ForegroundColor Green }
    elseif ($Type -eq "Failed") { Write-Host $logInfo -ForegroundColor Red }
    elseif ($Type -eq "Warning") { Write-Host $logInfo -ForegroundColor Yellow }
    elseif ($Type -eq "Start") { Write-Host $logInfo -ForegroundColor Cyan }
    else { Write-Verbose $logInfo }
}
Function Create-Log
{
    Param(
        # Log folder Root
        [Parameter(Mandatory = $true)]
        [String]$LogFolderRoot,
        # The function Log file for
        [Parameter(Mandatory = $true)]
        [String]$LogFunction
    )
    $logFolderPath = "$LogFolderRoot\logfiles"
    $folderExist = Test-Path "$logFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$logFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $logfilePath = "$logFolderPath\Log_{0}_{1}.txt" -f $LogFunction, $date
    Write-Verbose "Log file is writen to: $logfilePath"
    $logfile = New-Item $logfilePath  -type file
    return $logfilePath
}
Function Create-ResultCSV
{
    Param(
        # Result folder Root
        [Parameter(Mandatory = $true)]
        [String]$ResultFolderRoot,
        # The function Result file for
        [Parameter(Mandatory = $true)]
        [String]$ResultFunction
    )
    $retFolderPath = "$ResultFolderRoot\logfiles"
    $folderExist = Test-Path "$retFolderPath"
    if (!$folderExist)
    {
        $folder = New-Item "$retFolderPath" -type directory
    }
    $date = Get-Date -Format 'MMddyyyy_HHmmss'
    $retfilePath = "$retFolderPath\Result_{0}_{1}.csv" -f $ResultFunction, $date
    Write-Verbose "Result file is writen to: $retfilePath"
    $retfile = New-Item $retfilePath  -type file
    return $retfilePath
}
# -------------------
# Prepare Log File
# -------------------
$scriptPath = '.\'
$logfilePath = Create-Log -LogFolderRoot $scriptPath -LogFunction "Publish_Compliance_Tag"
if ($ResultCSV)
{
    $tagRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Creation"
    $tagPubRetFile = Create-ResultCSV -ResultFolderRoot $scriptPath -ResultFunction "Tag_Publish"
}
# -------------------
# Invoke Powershell cmdlet
# -------------------
Function InvokePowerShellCmdlet
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$CmdLet
    )
    try
    {
        WriteToLog -Type "Start" -Message "Execute Cmdlet : '$CmdLet'" 
        return Invoke-Expression $CmdLet -ErrorAction SilentlyContinue
    }
    catch
    {
        WriteToLog -Type "Failed" "Failed to execute cmdlet!"
        WriteToLog -Type "Failed" $error[0]
        return $null
    }
}
# -------------------
# Create Compliance Tag
# -------------------
Function CreateComplianceTag
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to create Compliance Tag"
    FileExist $FilePath
    
    # TODO Validate CSV file for the Header
    try
    {
        # Import csv
        $labels = Import-Csv $FilePath
        # Retrieve existing compliance tags
        $tags = InvokePowerShellCmdlet "Get-ComplianceTag"
        foreach($lab in $labels)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $cmdlet = 'New-ComplianceTag'
            if ([String]::IsNullOrEmpty($lab.'Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $name = $lab.'Name (Required)'
                $cmdlet += " -Name '" + $name + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'Comment (Optional)'))
            {
                $para = $lab.'Comment (Optional)'
                $cmdlet += " -Comment '" + $para + "'"
            }
            if (![String]::IsNullOrEmpty($lab.'IsRecordLabel (Required)'))
            {
                $para = $lab.'IsRecordLabel (Required)'
                $cmdlet += " -IsRecordLabel " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionAction (Optional)'))
            {
                $para = $lab.'RetentionAction (Optional)'
                $cmdlet += " -RetentionAction " + $para 
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionDuration (Optional)'))
            {
                $para = $lab.'RetentionDuration (Optional)'
                $cmdlet += " -RetentionDuration " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'RetentionType (Optional)'))
            {
                $para = $lab.'RetentionType (Optional)'
                $cmdlet += " -RetentionType " + $para
            }
            if (![String]::IsNullOrEmpty($lab.'ReviewerEmail (Optional)'))
            {
                $emails = $lab.'ReviewerEmail (Optional)'.Split(",") | ForEach-Object { $_.Trim() }
                if (($emails -ne $null) -and ($emails.Count -ne 0))
                {
                    $eml = '@('
                    foreach($email in $emails)
                    {
                        $eml += "'{0}'," -f $email
                    }
                    $eml = $eml.Substring(0, $eml.Length - 1) + ')'
                    
                    $cmdlet += " -ReviewerEmail " + $eml
                }
            }
            # If the tag already exists, skip for creation
            if (($tags -eq $null) -or ($tags | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create compliance tag
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
                
                $ret = InvokePowerShellCmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The tag '$name' already exists! Skip for creation!"
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Create Retention Compliance Policy
# -------------------
Function CreateRetentionCompliancePolicy
{
    Param(
        # File path needed to check
        [Parameter(Mandatory = $true)]
        [String]$FilePath
    )
    
    WriteToLog -Type "Start" "Start to Create Retention Policy"
    FileExist $FilePath
    try
    {
        # Import csv
        $list = Import-Csv -Path $FilePath
        # Retrieve existing retention compliance policy
        $policies = InvokePowerShellCmdlet "Get-RetentionCompliancePolicy"
        foreach($rp in $list)
        {
            # Cmdlet parameters
            $para = [String]::Empty;
            $name = [String]::Empty;
            $rpid = [String]::Empty;
            $cmdlet = 'New-RetentionCompliancePolicy'
            if ([String]::IsNullOrEmpty($rp.'Policy Name (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
               $name = $rp.'Policy Name (Required)'
               $cmdlet += " -Name '" + $name + "'"
            }
            if ([String]::IsNullOrEmpty($rp.'Enabled (Required)'))
            {
                WriteToLog -Type "Failed" -Message "Could not acquire table for writing."
                throw;
            }
            else
            {
                $enabled = $rp.'Enabled (Required)'
                $cmdlet += " -Enabled " + $enabled
            }
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocation (Optional)'))
            {
                $para = $rp.'ExchangeLocation (Optional)'
                $cmdlet += " -ExchangeLocation " + $para
            }
         
            if (![String]::IsNullOrEmpty($rp.'ExchangeLocationException (Optional)'))
            {
                $para = $rp.'ExchangeLocationException (Optional)'
                $cmdlet += " -ExchangeLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocation (Optional)'))
            {
                $para = $rp.'ModernGroupLocation (Optional)'
                $cmdlet += " -ModernGroupLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'ModernGroupLocationException (Optional)'))
            {
                $para = $rp.'ModernGroupLocationException (Optional)'
                $cmdlet += " -ModernGroupLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocation (Optional)'))
            {
                $para = $rp.'OneDriveLocation (Optional)'
                $cmdlet += " -OneDriveLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'OneDriveLocationException (Optional)'))
            {
                $para = $rp.'OneDriveLocationException (Optional)'
                $cmdlet += " -OneDriveLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocation (Optional)'))
            {
                $para = $rp.'SharePointLocation (Optional)'
                $cmdlet += " -SharePointLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SharePointLocationException (Optional)'))
            {
                $para = $rp.'SharePointLocationException (Optional)'
                $cmdlet += " -SharePointLocationException " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'PublicFolderLocation (Optional)'))
            {
                $para = $rp.'PublicFolderLocation (Optional)'
                $cmdlet += " -PublicFolderLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocation (Optional)'))
            {
                $para = $rp.'SkypeLocation (Optional)'
                $cmdlet += " -SkypeLocation " + $para
            }
            if (![String]::IsNullOrEmpty($rp.'SkypeLocationException (Optional)'))
            {
                $para = $rp.'SkypeLocationException (Optional)'
                $cmdlet += " -SkypeLocationException " + $para
            }
            # If the policy already exists, skip for creation
            if (($policies -eq $null) -or ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }) -eq $null)
            {
                # Create retention compliance policy
                $msg = "Execute Cmdlet : {0}" -f $cmdlet
            
                $ret = invokepowershellcmdlet $cmdlet
            
                if ($ret -eq $null)
                {
                    WriteToLog -Type "Failed" $error[0]
                    break;
                }
                $rpid = $ret.Guid
            }
            else
            {
                WriteToLog -Type "Warning" -Message "The policy '$name' already exists! Skip for creation!"
                $rpid = ($policies | ? { $_.Name.ToLower() -eq $name.ToLower() }).Guid
            }
                        
            # Retrieve tag name for publishing
            $ts = $rp.'PublishComplianceTag (Required)'
            $tagList = $ts.Split(",") | ForEach-Object { $_.Trim() }
            
            WriteToLog -Type "Message" -Message "Publish Tags : '$ts'" 
            
            PublishComplianceTag -PolicyGuid $rpid -TagName $tagList
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Publish Compliance Tag
# -------------------
Function PublishComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$PolicyGuid,
        [Parameter(Mandatory = $true)]
        [String[]]$TagNames
    )
    
    WriteToLog -Type "Start" "Start to Publish Compliance Tag"
    try
    {
        # Retrieve existing rule related to the given compliance policy
        $rule = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $PolicyGuid)
        $tagGuids = New-Object System.Collections.ArrayList
        
        foreach ($tn in $TagNames)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag {0}" -f $tn)
            $tagGuids.Add($t.Guid) | Out-Null
        }
        if ($rule -ne $null)
        {
            foreach ($r in $rule)
            {
                if ([String]::IsNullOrEmpty($r.PublishComplianceTag))
                {
                    continue;
                }
                else
                {
                    $tl = $r.PublishComplianceTag.Split(",")
                    if ($tagGuids.Contains([GUID]$tl[0]))
                    {
                        $tagGuids.Remove([GUID]$tl[0]);
                    }
                }
            }
        }
        
        foreach($t in $tagGuids)
        {
            # Publish compliance tag
            $cmdlet = "New-RetentionComplianceRule -Policy {0} -PublishComplianceTag {1}" -f $PolicyGuid, $t
            $ret = InvokePowerShellCmdlet $cmdlet
            
            if ($ret -eq $null)
            {
                WriteToLog -Type "Failed" $error[0]
                break;
            }
        }
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in input"
    }
}
# -------------------
# Export All Labels Created in The Process
# -------------------
Function ExportCreatedComplianceTag
{
    Param(
        [Parameter(Mandatory = $true)]
        [String]$LabelFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Compliance Tag Created"
    try
    {
        # Import input csv
        $labels = Import-Csv $LabelFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn Name,([string])
        $col2 = New-Object system.Data.DataColumn Comment,([string])
        $col3 = New-Object system.Data.DataColumn IsRecordLabel,([string])
        $col4 = New-Object system.Data.DataColumn RetentionAction,([string])
        $col5 = New-Object system.Data.DataColumn RetentionDuration,([string])
        $col6 = New-Object system.Data.DataColumn RetentionType,([string])
        $col7 = New-Object system.Data.DataColumn ReviewerEmail,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        foreach($lab in $labels)
        {
            $t = InvokePowerShellCmdlet ("Get-ComplianceTag '{0}' " -f $lab.'Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Name'] = $t.Name
            $row['Comment'] = $t.Comment
            $row['IsRecordLabel'] = $t.IsRecordLabel
            $row['RetentionAction'] = $t.RetentionAction
            $row['RetentionDuration'] = $t.RetentionDuration
            $row['RetentionType'] = $t.RetentionType
            $row['ReviewerEmail'] = $t.ReviewerEmail
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# -------------------
# Export All Published Labels and Policies in The Process
# -------------------
Function ExportPublishedComplianceTagAndPolicy
{
    Param(
        [Parameter(Mandatory = $true)]
        [String[]]$PolicyFilePath
    )
    
    WriteToLog -Type "Start" "Start to Export Published Compliance Tag and Policy"
    try
    {
        # Import input csv
        $policies = Import-Csv $PolicyFilePath
        # Create result table
        $tabName = "ResultTable"
        $table = New-Object system.Data.DataTable "$tabName"
        $col1 = New-Object system.Data.DataColumn 'Policy Name',([string])
        $col2 = New-Object system.Data.DataColumn PublishComplianceTag,([string])
        $col3 = New-Object system.Data.DataColumn Comment,([string])
        $col4 = New-Object system.Data.DataColumn Enabled,([string])
        $col5 = New-Object system.Data.DataColumn ExchangeLocation,([string])
        $col6 = New-Object system.Data.DataColumn ExchangeLocationException,([string])
        $col7 = New-Object system.Data.DataColumn ModernGroupLocation,([string])
        $col8 = New-Object system.Data.DataColumn ModernGroupLocationException,([string])
        $col9 = New-Object system.Data.DataColumn OneDriveLocation,([string])
        $col10 = New-Object system.Data.DataColumn OneDriveLocationException,([string])
        $col11 = New-Object system.Data.DataColumn PublicFolderLocation,([string])
        $col12 = New-Object system.Data.DataColumn SharePointLocation,([string])
        $col13 = New-Object system.Data.DataColumn SharePointLocationException,([string])
        $col14 = New-Object system.Data.DataColumn SkypeLocation,([string])
        $col15 = New-Object system.Data.DataColumn SkypeLocationException,([string])
        
        # Add the Columns
        $table.columns.add($col1)
        $table.columns.add($col2)
        $table.columns.add($col3)
        $table.columns.add($col4)
        $table.columns.add($col5)
        $table.columns.add($col6)
        $table.columns.add($col7)
        $table.columns.add($col8)
        $table.columns.add($col9)
        $table.columns.add($col10)
        $table.columns.add($col11)
        $table.columns.add($col12)
        $table.columns.add($col13)
        $table.columns.add($col14)
        $table.columns.add($col15)
        foreach($policy in $policies)
        {
            $t = InvokePowerShellCmdlet ("Get-RetentionCompliancePolicy '{0}' -DistributionDetail" -f $policy.'Policy Name (Required)')
            
            # Create a result row
            $row = $table.NewRow()
            $row['Policy Name'] = $t.Name
            
            $rules = InvokePowerShellCmdlet ("Get-RetentionComplianceRule -Policy {0}" -f $t.Guid)
            $tagList = [String]::Empty
            foreach($rule in $rules)
            {
                if ([String]::IsNullOrEmpty($rule.PublishComplianceTag) -eq $False)
                {
                    $tName = $rule.PublishComplianceTag.Split(',')[1]
                    $tagList = [String]::Concat($tagList, $tName, ",")
                }
            }
            if (![String]::IsNullOrEmpty($tagList))
            {
                $tagList = $tagList.Substring(0, $tagList.LastIndexOf(','))
            }
            $row['PublishComplianceTag'] = $tagList
            $row['Comment'] = $t.Comment
            $row['Enabled'] = $t.Enabled
            $row['ExchangeLocation'] = $t.ExchangeLocation
            $row['ExchangeLocationException'] = $t.ExchangeLocationException
            $row['ModernGroupLocation'] = $t.ModernGroupLocation
            $row['ModernGroupLocationException'] = $t.ModernGroupLocationException
            $row['OneDriveLocation'] = $t.OneDriveLocation
            $row['OneDriveLocationException'] = $t.OneDriveLocationException
            $row['PublicFolderLocation'] = $t.PublicFolderLocation
            $row['SharePointLocation'] = $t.SharePointLocation
            $row['SharePointLocationException'] = $t.SharePointLocationException
            $row['SkypeLocation'] = $t.SkypeLocation
            $row['SkypeLocationException'] = $t.SkypeLocationException
            
            # Add the row to the table
            $table.Rows.Add($row)
        }
        $table | Export-Csv $tagPubRetFile -NoTypeInformation
    }
    catch
    {
        WriteToLog -Type "Failed" "Error in exporting results."
    }
}
# Create compliance tag
CreateComplianceTag -FilePath $LabelListCSV
# Create retention policy and publish compliance tag with the policy
CreateRetentionCompliancePolicy -FilePath $PolicyListCSV
# Export to result csv
if ($ResultCSV)
{
    ExportCreatedComplianceTag -LabelFilePath $LabelListCSV
    ExportPublishedComplianceTagAndPolicy -PolicyFilePath $PolicyListCSV 
}

```

## <a name="step-4-connect-to-security-amp-compliance-center-powershell"></a><span data-ttu-id="d59fc-150">手順 4: セキュリティ&amp;コンプライアンス センター PowerShell に接続する</span><span class="sxs-lookup"><span data-stu-id="d59fc-150">Step 4: Connect to Security &amp; Compliance Center PowerShell</span></span>

<span data-ttu-id="d59fc-151">以下の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d59fc-151">Follow the steps here:</span></span>
  
- [<span data-ttu-id="d59fc-152">Office 365 セキュリティ&amp;コンプライアンス センター PowerShell への接続</span><span class="sxs-lookup"><span data-stu-id="d59fc-152">Connect to Office 365 Security &amp; Compliance Center PowerShell</span></span>](https://go.microsoft.com/fwlink/?linkid=799771)
    
## <a name="step-5-run-the-powershell-script-to-create-and-publish-the-retention-labels"></a><span data-ttu-id="d59fc-153">手順 5: PowerShell スクリプトを実行して保持ラベルを作成および発行する</span><span class="sxs-lookup"><span data-stu-id="d59fc-153">Step 5: Run the PowerShell script to create and publish the labels</span></span>

<span data-ttu-id="d59fc-154">セキュリティ&amp;コンプライアンス センター PowerShell に接続したら、次に、保持ラベルを作成して発行するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-154">After you've connected to Security &amp; Compliance Center PowerShell, next you run the script that creates and publishes the labels.</span></span>
  
1. <span data-ttu-id="d59fc-155">セキュリティ&amp;コンプライアンス PowerShell セッションでパスを入力し、その後ろに文字「.\」とスクリプトのファイル名を入力し、ENTER キーを押してスクリプトを実行します。例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-155">In the Security &amp; Compliance PowerShell session, enter the path, followed by the characters .\ and file name of the script, and then press ENTER to run the script - for example:</span></span>
    
  ```
  <path>.\CreateRetentionSchedule.ps1
  ```

    <span data-ttu-id="d59fc-156">スクリプトは、上で作成した .csv ファイルの場所を要求するダイアログを表示します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-156">The script will prompt you for the locations of the .csv files that you created above.</span></span>
    
2. <span data-ttu-id="d59fc-157">パスを入力し、その後ろに文字「.\」と .csv ファイルの名前を入力し、ENTER キーを押します。例を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="d59fc-157">Enter the path, followed by the characters .\ and file name of the .csv file, and then press ENTER - for example:</span></span>
    
  ```
  <path>.\LabelsToCreate.csv
  ```

## <a name="step-6-view-the-log-file-with-the-results"></a><span data-ttu-id="d59fc-158">手順 6: 結果を含むログ ファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="d59fc-158">Step 6: View the log file with the results</span></span>

<span data-ttu-id="d59fc-p113">スクリプトを実行すると、実行された各アクションと、アクションが成功したか失敗したかを記録するログ ファイルが生成されます。ログ ファイルには、作成された保持ラベルと発行された保持ラベルに関するすべてのメタデータが含まれています。ログ ファイルはこの場所で見つけられます。ファイル名の数字は異なることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="d59fc-p113">When you run the script, it generates a log file that records each action it took and whether the action succeeded or failed. The log file includes all metadata about what labels were created and what labels were published. You can find the log file at this location -- note that the digits in the file name vary.</span></span>
  
```
<path>.\Log_Publish_Compliance_Tag_01112018_151239.txt
```


