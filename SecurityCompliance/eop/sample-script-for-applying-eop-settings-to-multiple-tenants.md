---
title: EOP 設定を複数のテナントに適用するスクリプトのサンプル
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e87e84e1-7be0-44bf-a414-d91d60ed8817
description: 以下のサンプル スクリプトにより、複数のテナント (会社) を管理する Microsoft Exchange Online Protection (EOP) 管理者は、Windows PowerShell を使用して構成設定をテナントに適用できます。
ms.openlocfilehash: 2886d2c1dd4dc2f324e8cc21babc3a9f4bf51e5f
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699205"
---
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a><span data-ttu-id="0b71d-103">EOP 設定を複数のテナントに適用するスクリプトのサンプル</span><span class="sxs-lookup"><span data-stu-id="0b71d-103">Sample script for applying EOP settings to multiple tenants</span></span>

<span data-ttu-id="0b71d-104">以下のサンプル スクリプトにより、複数のテナント (会社) を管理する Microsoft Exchange Online Protection (EOP) 管理者は、Windows PowerShell を使用して構成設定をテナントに適用できます。</span><span class="sxs-lookup"><span data-stu-id="0b71d-104">The following sample script lets Microsoft Exchange Online Protection (EOP) admins who manage multiple tenants (companies) use Windows PowerShell to apply configuration settings to their tenants.</span></span>
  
### <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a><span data-ttu-id="0b71d-105">複数のテナントでスクリプトまたはコマンドレットを実行するには</span><span class="sxs-lookup"><span data-stu-id="0b71d-105">To run a script or cmdlet on multiple tenants</span></span>

1. <span data-ttu-id="0b71d-106">Excel などのアプリケーションを使用して, .csv ファイル (c:\scripts\inputfile.csv など) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0b71d-106">Using an application such as Excel, create a .csv file (for example, c:\scripts\inputfile.csv):</span></span>

2. <span data-ttu-id="0b71d-107">.csv ファイルで、次の 2 つの列名を指定します。「UserName」および「Cmdlet」。</span><span class="sxs-lookup"><span data-stu-id="0b71d-107">In the .csv file, specify two column names: UserName and Cmdlet.</span></span>

3. <span data-ttu-id="0b71d-p101">.csv ファイルの各行で、テナントの管理者名を UserName 列に追加し、そのテナントのために実行するコマンドレットを Cmdlet 列に追加します。例えば、admin@contoso.com と Get-AcceptedDomain を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b71d-p101">For each row in the .csv file, add the tenant's admin name in the UserName column and the cmdlet to run for that tenant in the Cmdlet column. For example, use admin@contoso.com and Get-AcceptedDomain.</span></span>

4. <span data-ttu-id="0b71d-110">[RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) スクリプトをメモ帳などのエディターにコピーしてから, .psl ファイルを容易に見つけられる場所 (c:\scripts など) にファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="0b71d-110">Copy the [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) script to an editor like Notepad, and then save the file to a location (like c:\scripts) that makes .ps1 files easy to find.</span></span>

5. <span data-ttu-id="0b71d-111">次の構文を使用して、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b71d-111">Run the script by using the following syntax:</span></span>

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   <span data-ttu-id="0b71d-112">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="0b71d-112">Here's an example.</span></span>

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. <span data-ttu-id="0b71d-113">各テナントへのログオンが行われて、コマンドレットが実行されます。</span><span class="sxs-lookup"><span data-stu-id="0b71d-113">Each tenant will be logged on to, and the cmdlet will be run.</span></span>

## <a name="runcmdletonmultipletenantsps1"></a><span data-ttu-id="0b71d-114">Runコマンドレット。 ps1</span><span class="sxs-lookup"><span data-stu-id="0b71d-114">RunCmdletOnMultipleTenants.ps1</span></span>

```Powershell
# This script runs Windows PowerShell cmdlets on multiple tenants.
# Usage: RunCmdletOnMultipleTenants.ps1 inputfile.csv
#  
# .csv input file sample:
# UserName,Cmdlet
# admin@contoso.com,Get-AcceptedDomain | ft Name
# URI for connecting to remote Windows PowerShell
$URI = "https://ps.protection.outlook.com/powershell-liveid/"
# Get the .csv file name as an argument to this script.
$FilePath = $args[0]
# Import the UserName and Cmdlet values from the .csv file.
$CompanyList = Import-CSV $FilePath
# Loop through each entry from the .csv file.
ForEach ($Company in $CompanyList) {
# Get the current entry's UserName.
$UserName = $Company.UserName
# Get the current entry's Cmdlet.
$Cmdlet = $Company.Cmdlet
# Create a PowerShell credential object by using the current entry's UserName. Prompt for the password.
$UserCredential = Get-Credential -username $UserName
# Log on to a new Windows PowerShell session.
$Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri $URI -Credential $UserCredential -Authentication Basic -AllowRedirection
Import-PSSession $Session
# Here's where the script to be run on the tenant goes.
# In this example, the cmdlet in the .csv file runs.
Invoke-Expression $Cmdlet
# End the current PowerShell session.
Remove-PsSession -Session $Session
}
```
