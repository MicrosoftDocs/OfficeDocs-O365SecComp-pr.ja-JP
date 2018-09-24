---
title: Office 365 でモバイル デバイス管理 (MDM) を管理するデバイスの詳細を表示します。
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 6/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MBS150
- MET150
ms.assetid: 5602963c-a1f2-4c21-afb9-f66cd7dca1f0
description: この資料では、Windows PowerShell を使用して、Office 365 でモバイル デバイスの管理を設定すること、組織内のデバイスに関する詳細情報を取得する方法を示します。
ms.openlocfilehash: 90ee59c5afed1cd260e13134299a7cb4f17dc5bc
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972319"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a>Office 365 でモバイル デバイス管理 (MDM) を管理するデバイスの詳細を表示します。

この資料では、Windows PowerShell を使用して、Office 365 でモバイル デバイスの管理を設定すること、組織内のデバイスに関する詳細情報を取得する方法を示します。 
  
## <a name="what-device-details-can-i-get"></a>どのようなデバイスの詳細情報を入手できますか。

内訳を次に示します。
  
|**詳細**|**PowerShell で検索するのにはどのような**|
|:-----|:-----|
|[Office 365 の MDM に登録されている](enroll-your-mobile-device.md)デバイスは、します。 <br/> |*IsManaged*パラメーターの値は次のとおりです。  <br/> **True** = デバイスを登録します。  <br/> **False** = デバイスが登録されていません。  <br/> |
|デバイスは、[デバイスのセキュリティ ポリシー](https://go.microsoft.com/fwlink/?linkid=615144)に準拠して <br/> |*IsCompliant*パラメーターの値は次のとおりです。  <br/> **True** = デバイスは、ポリシーに準拠しています。  <br/> **False** = デバイスがポリシーに準拠していません。  <br/> |
   
![フローのデバイスが登録されているかどうかと苦情を AAD シェルのパラメーター値を表示します。](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> コマンドおよびスクリプトをこの資料にも[Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune)によって管理されているすべてのデバイスに関する詳細情報を返します。 
  
## <a name="before-you-begin"></a>はじめに

いくつかの点をする必要がありますように設定するのにはこの資料のコマンドと記載されているスクリプトを実行します。
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a>手順 1: をダウンロードして、Azure Active Directory モジュールを Windows PowerShell をインストールします。

これらの手順の詳細については、 [Office 365 の PowerShell への接続](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell)を参照してください。
  
1. [Microsoft オンライン サービス サインイン アシスタントの IT プロフェッショナル向けの RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950)に移動し、Microsoft オンライン サービス サインイン アシスタントの [**ダウンロード**] をクリックします。 
    
2. 以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。
    
    1. 管理者レベルの PowerShell コマンド プロンプトを開きます。
        
    2. 実行、`Install-Module MSOnline`コマンドです。
        
    3. NuGet のプロバイダーをインストールするように求められたら、入力`Y`し、ENTER キーを押します。
        
    4. PSGallery からモジュールをインストールするように求められたら、入力`Y`し、ENTER キーを押します。
        
    5. インストール後、PowerShell コマンド ウィンドウを閉じます。
    
### <a name="step-2-connect-to-your-office-365-subscription"></a>手順 2: Office 365 サブスクリプションに接続する

1. Windows Azure Active ディレクトリ モジュールを Windows PowerShell では、次のコマンドを実行します。<br/>  
  `$UserCredential = Get-Credential`

2. **Windows PowerShell の資格情報の要求**] ダイアログ ボックスで、Office 365 のグローバル管理者アカウントのパスワードとユーザー名を入力し、し、[ **OK**] をクリックします。
    
3. 次のコマンドを実行します。<br/>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a>手順 3: PowerShell スクリプトを実行することを確認します。

> [!NOTE]
> PowerShell スクリプトを実行するのには既に設定されている場合は、この手順を省略できます。 
  
**Get MsolUserDeviceComplianceStatus.ps1**スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。 
  
1. Windows デスクトップで [**開始**] をクリックし、Windows PowerShell を入力し。**Windows PowerShell**では、右クリックし、[**管理者として実行**] をクリックします。
    
2. 次のコマンドを実行します。<br/>
  `Set-ExecutionPolicy RemoteSigned`

3. ダイアログ ボックスが表示されたら、入力`Y`し、Enter キーを押します。 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a>組織内のすべてのデバイスの詳細を表示するのには、Get MsolDevice コマンドレットを実行します。

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. 次のコマンドを実行します。<br/>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

例については、 [Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)を参照してください。
  
## <a name="run-a-script-to-get-device-details"></a>デバイスの詳細情報を取得するためのスクリプトを実行します。

### <a name="first-save-the-script-to-your-computer"></a>最初に、スクリプトをお使いのコンピューターに保存します。

1. コピーし、次のテキストをメモ帳に貼り付けます。<br/> 
  ```
  param (
      [PSObject[]]$users = @(),
      [Switch]$export,
      [String]$exportFileName = "UserDeviceComplianceStatus_" + (Get-Date -Format "yyMMdd_HHMMss") + ".csv",
      [String]$exportPath = [Environment]::GetFolderPath("Desktop")
   )
  [System.Collections.IDictionary]$script:schema = @{
      
      DeviceId = ''
      DeviceOSType = ''
      DeviceOSVersion = ''
      DeviceTrustLevel = ''
      DisplayName = ''
      IsCompliant = ''
      IsManaged = ''
      ApproximateLastLogonTimestamp = ''
      DeviceObjectId = ''    
      RegisteredOwnerUpn = ''
      RegisteredOwnerObjectId = ''
      RegisteredOwnerDisplayName = ''
  }
  function createResultObject
  {
      [PSObject]$resultObject = New-Object -TypeName PSObject -Property $script:schema
      return $resultObject
  }
  If ($users.Count -eq 0)
  {
      $users = Get-MsolUser
  }
  [PSObject[]]$result = foreach ($u in $users)
  {
      
      [PSObject]$devices = get-msoldevice -RegisteredOwnerUpn $u.UserPrincipalName
      foreach ($d in $devices)
      {
          [PSObject]$deviceResult = createResultObject
          $deviceResult.DeviceId = $d.DeviceId 
          $deviceResult.DeviceOSType = $d.DeviceOSType 
          $deviceResult.DeviceOSVersion = $d.DeviceOSVersion 
          $deviceResult.DeviceTrustLevel = $d.DeviceTrustLevel
          $deviceResult.DisplayName = $d.DisplayName
          $deviceResult.IsCompliant = $d.GraphDeviceObject.IsCompliant
          $deviceResult.IsManaged = $d.GraphDeviceObject.IsManaged
          $deviceResult.DeviceObjectId = $d.ObjectId
          $deviceResult.RegisteredOwnerUpn = $u.UserPrincipalName
          $deviceResult.RegisteredOwnerObjectId = $u.ObjectId
          $deviceResult.RegisteredOwnerDisplayName = $u.DisplayName
          $deviceResult.ApproximateLastLogonTimestamp = $d.ApproximateLastLogonTimestamp
          $deviceResult
      }
  }
  If ($export)
  {
      $result | Export-Csv -path ($exportPath + "\" + $exportFileName) -NoTypeInformation
  }
  Else
  {
      $result
  }
  
  ```

2. ファイル拡張子 **.ps1**を使用して Windows PowerShell スクリプト ファイルとして保存します。 <br/>例:<br/> `Get-MsolUserDeviceComplianceStatus.ps1`.
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a>単一のユーザー アカウント用のデバイス情報を取得するスクリプトを実行します。

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。などの C:\PS-Scripts に保存する場合は、次のコマンドを実行するとします。<br/>
    `cd C:\PS-Scripts`

3. デバイスの詳細を取得するユーザーを識別する次のコマンドを実行します。次の使用例は、bar@example.com の詳細を取得します。<br/>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. スクリプトを開始するのには次のコマンドを実行します。<br/>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

情報は、CSV ファイルとしてデスクトップにエクスポートされます。CSV のパスとファイル名を指定するのには、追加のパラメーターを使用できます。
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a>スクリプトを実行するユーザーのグループのデバイス情報を取得します。

1. Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。
    
2. スクリプトを保存したフォルダーに移動します。などの C:\PS-Scripts に保存する場合は、次のコマンドを実行するとします。<br/>
  `cd C:\PS-Scripts`

3. デバイスの詳細を取得するグループを識別する次のコマンドを実行します。この例では、FinanceStaff グループのユーザーの詳細を取得します。<br/>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. スクリプトを開始するのには次のコマンドを実行します。<br/>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

情報は、CSV ファイルとしてデスクトップにエクスポートされます。CSV のパスとファイル名を指定するのには、追加のパラメーターを使用できます。
  
## <a name="more-info"></a>詳細情報

[Office 365 の MDM の概要](overview-of-mdm.md)
  
[Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)
  

