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
# <a name="sample-script-for-applying-eop-settings-to-multiple-tenants"></a>EOP 設定を複数のテナントに適用するスクリプトのサンプル

以下のサンプル スクリプトにより、複数のテナント (会社) を管理する Microsoft Exchange Online Protection (EOP) 管理者は、Windows PowerShell を使用して構成設定をテナントに適用できます。
  
### <a name="to-run-a-script-or-cmdlet-on-multiple-tenants"></a>複数のテナントでスクリプトまたはコマンドレットを実行するには

1. Excel などのアプリケーションを使用して, .csv ファイル (c:\scripts\inputfile.csv など) を作成します。

2. .csv ファイルで、次の 2 つの列名を指定します。「UserName」および「Cmdlet」。

3. .csv ファイルの各行で、テナントの管理者名を UserName 列に追加し、そのテナントのために実行するコマンドレットを Cmdlet 列に追加します。例えば、admin@contoso.com と Get-AcceptedDomain を使用します。

4. [RunCmdletOnMultipleTenants.ps1](#runcmdletonmultipletenantsps1) スクリプトをメモ帳などのエディターにコピーしてから, .psl ファイルを容易に見つけられる場所 (c:\scripts など) にファイルを保存します。

5. 次の構文を使用して、スクリプトを実行します。

   ```Powershell
   & "<file path>\RunCmdletOnMultipleTenants.ps1" "<file path>\inputfile.csv"
   ```

   次に例を示します。

   ```Powershell
   & "c:\scripts\RunCmdletOnMultipleTenanats.ps1" "c:\scripts\inputfile.csv"
   ```

6. 各テナントへのログオンが行われて、コマンドレットが実行されます。

## <a name="runcmdletonmultipletenantsps1"></a>Runコマンドレット。 ps1

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
