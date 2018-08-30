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
ms.openlocfilehash: 2e406d3583e7892531b7c74bef0db374672956c7
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272532"
---
# <a name="get-details-about-devices-managed-by-mobile-device-management-mdm-for-office-365"></a><span data-ttu-id="ad377-103">Office 365 でモバイル デバイス管理 (MDM) を管理するデバイスの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="ad377-103">Get details about devices managed by Mobile Device Management (MDM) for Office 365</span></span>

<span data-ttu-id="ad377-104">この資料では、Windows PowerShell を使用して、Office 365 でモバイル デバイスの管理を設定すること、組織内のデバイスに関する詳細情報を取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ad377-104">This article shows you how to use Windows PowerShell to get details about the devices in your organization that you set up for Mobile Device Management for Office 365.</span></span> 
  
## <a name="what-device-details-can-i-get"></a><span data-ttu-id="ad377-105">どのようなデバイスの詳細情報を入手できますか。</span><span class="sxs-lookup"><span data-stu-id="ad377-105">What device details can I get?</span></span>

<span data-ttu-id="ad377-106">内訳を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ad377-106">Here's a breakdown.</span></span>
  
|<span data-ttu-id="ad377-107">**詳細**</span><span class="sxs-lookup"><span data-stu-id="ad377-107">**Detail**</span></span>|<span data-ttu-id="ad377-108">**PowerShell で検索するのにはどのような**</span><span class="sxs-lookup"><span data-stu-id="ad377-108">**What to look for in PowerShell**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ad377-109">[Office 365 の MDM に登録されている](enroll-your-mobile-device.md)デバイスは、します。</span><span class="sxs-lookup"><span data-stu-id="ad377-109">Device is [enrolled in MDM for Office 365](enroll-your-mobile-device.md)</span></span> <br/> |<span data-ttu-id="ad377-110">*IsManaged*パラメーターの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad377-110">The value of the  *isManaged*  parameter is:</span></span>  <br/> <span data-ttu-id="ad377-111">**True** = デバイスを登録します。</span><span class="sxs-lookup"><span data-stu-id="ad377-111">**True** = device is enrolled.</span></span>  <br/> <span data-ttu-id="ad377-112">**False** = デバイスが登録されていません。</span><span class="sxs-lookup"><span data-stu-id="ad377-112">**False** = device is not enrolled.</span></span>  <br/> |
|<span data-ttu-id="ad377-113">デバイスは、[デバイスのセキュリティ ポリシー](https://go.microsoft.com/fwlink/?linkid=615144)に準拠して</span><span class="sxs-lookup"><span data-stu-id="ad377-113">Device is compliant with your [device security policies](https://go.microsoft.com/fwlink/?linkid=615144)</span></span> <br/> |<span data-ttu-id="ad377-114">*IsCompliant*パラメーターの値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="ad377-114">The value of the  *isCompliant*  parameter is:</span></span>  <br/> <span data-ttu-id="ad377-115">**True** = デバイスは、ポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="ad377-115">**True** = device is compliant with policies.</span></span>  <br/> <span data-ttu-id="ad377-116">**False** = デバイスがポリシーに準拠していません。</span><span class="sxs-lookup"><span data-stu-id="ad377-116">**False** = device is not compliant with policies.</span></span>  <br/> |
   
![フローのデバイスが登録されているかどうかと苦情を AAD シェルのパラメーター値を表示します。](media/647b70f4-f886-41ef-8bff-04773a1da278.png)
  
> [!NOTE]
> <span data-ttu-id="ad377-118">コマンドおよびスクリプトをこの資料にも[Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune)によって管理されているすべてのデバイスに関する詳細情報を返します。</span><span class="sxs-lookup"><span data-stu-id="ad377-118">The commands and scripts in this article will also return details about any devices that are managed by [Microsoft Intune](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="ad377-119">はじめに</span><span class="sxs-lookup"><span data-stu-id="ad377-119">Before you begin</span></span>

<span data-ttu-id="ad377-120">いくつかの点をする必要がありますように設定するのにはこの資料のコマンドと記載されているスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-120">There are a few things you'll need to set up to run the commands and scripts described in this article.</span></span>
  
### <a name="step-1-download-and-install-the-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="ad377-121">手順 1: をダウンロードして、Azure Active Directory モジュールを Windows PowerShell をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad377-121">Step 1: Download and install the Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="ad377-122">これらの手順の詳細については、 [Office 365 の PowerShell への接続](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad377-122">For more info on these steps, see [Connect to Office 365 PowerShell](https://docs.microsoft.com/Office365/enterprise/powershell/connect-to-office-365-powershell).</span></span>
  
1. <span data-ttu-id="ad377-123">[Microsoft オンライン サービス サインイン アシスタントの IT プロフェッショナル向けの RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950)に移動し、Microsoft オンライン サービス サインイン アシスタントの [**ダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad377-123">Go to [Microsoft Online Services Sign-In Assistant for IT Professionals RTWl](https://www.microsoft.com/en-us/download/details.aspx?id=41950) and click **Download** for Microsoft Online Services Sign-in Assistant.</span></span> 
    
2. <span data-ttu-id="ad377-124">以下の手順に従って、Windows PowerShell の Microsoft Azure Active Directory モジュールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ad377-124">Install the Microsoft Azure Active Directory Module for Windows PowerShell with these steps:</span></span>
    
    1. <span data-ttu-id="ad377-125">管理者レベルの PowerShell コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad377-125">Open an administrator-level PowerShell command prompt.</span></span>
        
    2. <span data-ttu-id="ad377-126">実行、`Install-Module MSOnline`コマンドです。</span><span class="sxs-lookup"><span data-stu-id="ad377-126">Run the `Install-Module MSOnline` command.</span></span>
        
    3. <span data-ttu-id="ad377-127">NuGet のプロバイダーをインストールするように求められたら、入力`Y`し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad377-127">If prompted to install the NuGet provider, type `Y` and press ENTER.</span></span>
        
    4. <span data-ttu-id="ad377-128">PSGallery からモジュールをインストールするように求められたら、入力`Y`し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad377-128">If prompted to install the module from PSGallery, type `Y` and press ENTER.</span></span>
        
    5. <span data-ttu-id="ad377-129">インストール後、PowerShell コマンド ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ad377-129">After installation, close the PowerShell command window.</span></span>
    
### <a name="step-2-connect-to-your-office-365-subscription"></a><span data-ttu-id="ad377-130">手順 2: Office 365 サブスクリプションに接続する</span><span class="sxs-lookup"><span data-stu-id="ad377-130">Step 2: Connect to your Office 365 subscription</span></span>

1. <span data-ttu-id="ad377-131">Windows Azure Active ディレクトリ モジュールを Windows PowerShell では、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-131">In the Windows Azure Active Directory Module for Windows PowerShell, run the following command.</span></span></br>  
  `$UserCredential = Get-Credential`

2. <span data-ttu-id="ad377-132">**Windows PowerShell の資格情報の要求**] ダイアログ ボックスで、Office 365 のグローバル管理者アカウントのパスワードとユーザー名を入力し、し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad377-132">In the **Windows PowerShell Credential Request** dialog box, type the user name and password for your Office 365 global admin account, and then click **OK**.</span></span>
    
3. <span data-ttu-id="ad377-133">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-133">Run the following command.</span></span></br>
    `
  Connect-MsolService -Credential $UserCredential
  `

### <a name="step-3-make-sure-youre-able-to-run-powershell-scripts"></a><span data-ttu-id="ad377-134">手順 3: PowerShell スクリプトを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="ad377-134">Step 3: Make sure you're able to run PowerShell scripts</span></span>

> [!NOTE]
> <span data-ttu-id="ad377-135">PowerShell スクリプトを実行するのには既に設定されている場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="ad377-135">You can skip this step if you're already set up to run PowerShell scripts.</span></span> 
  
<span data-ttu-id="ad377-136">**Get MsolUserDeviceComplianceStatus.ps1**スクリプトを実行するには、PowerShell スクリプトの実行を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad377-136">To run the **Get-MsolUserDeviceComplianceStatus.ps1** script, you need to enable the running of PowerShell scripts.</span></span> 
  
1. <span data-ttu-id="ad377-p101">Windows デスクトップで [**開始**] をクリックし、Windows PowerShell を入力し。**Windows PowerShell**では、右クリックし、[**管理者として実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad377-p101">From your Windows Desktop, click **Start**, and then type Windows PowerShell. Right click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="ad377-139">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-139">Run the following command.</span></span></br>
  `Set-ExecutionPolicy RemoteSigned`

3. <span data-ttu-id="ad377-140">ダイアログ ボックスが表示されたら、入力`Y`し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ad377-140">When prompted, type `Y` and then press Enter.</span></span> 
    
## <a name="run-the-get-msoldevice-cmdlet-to-display-details-for-all-devices-in-your-organization"></a><span data-ttu-id="ad377-141">組織内のすべてのデバイスの詳細を表示するのには、Get MsolDevice コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-141">Run the Get-MsolDevice cmdlet to display details for all devices in your organization</span></span>

1. <span data-ttu-id="ad377-142">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad377-142">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ad377-143">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-143">Run the following command.</span></span></br>
  ```
  Get-MsolDevice -All -ReturnRegisteredOwners | Where-Object {$_.RegisteredOwners.Count -gt 0}
  ```

<span data-ttu-id="ad377-144">例については、 [Get MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad377-144">For more examples, see [Get-MsolDevice](https://go.microsoft.com/fwlink/?linkid=841721).</span></span>
  
## <a name="run-a-script-to-get-device-details"></a><span data-ttu-id="ad377-145">デバイスの詳細情報を取得するためのスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-145">Run a script to get device details</span></span>

### <a name="first-save-the-script-to-your-computer"></a><span data-ttu-id="ad377-146">最初に、スクリプトをお使いのコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="ad377-146">First, save the script to your computer</span></span>

1. <span data-ttu-id="ad377-147">コピーし、次のテキストをメモ帳に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="ad377-147">Copy and paste the following text into Notepad.</span></span></br> 
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

2. <span data-ttu-id="ad377-148">ファイル拡張子 **.ps1**を使用して Windows PowerShell スクリプト ファイルとして保存します。</span><span class="sxs-lookup"><span data-stu-id="ad377-148">Save it as a Windows PowerShell script file by using the file extension **.ps1**.</span></span> </br><span data-ttu-id="ad377-149">例:</span><span class="sxs-lookup"><span data-stu-id="ad377-149">Example:</span></span></br> <span data-ttu-id="ad377-150">`Get-MsolUserDeviceComplianceStatus.ps1`.</span><span class="sxs-lookup"><span data-stu-id="ad377-150"></span></span>
    
### <a name="run-the-script-to-get-device-information-for-a-single-user-account"></a><span data-ttu-id="ad377-151">単一のユーザー アカウント用のデバイス情報を取得するスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-151">Run the script to get device information for a single user account</span></span>

1. <span data-ttu-id="ad377-152">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad377-152">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ad377-p102">スクリプトを保存したフォルダーに移動します。などの C:\PS-Scripts に保存する場合は、次のコマンドを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="ad377-p102">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span></br>
    `cd C:\PS-Scripts`

3. <span data-ttu-id="ad377-p103">デバイスの詳細を取得するユーザーを識別する次のコマンドを実行します。次の使用例は、bar@example.com の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad377-p103">Run the following command to identify the user you want to get device details for. This example gets details for bar@example.com.</span></span></br>
  ```
  $u = Get-MsolUser -UserPrincipalName bar@example.com
  ```

4. <span data-ttu-id="ad377-157">スクリプトを開始するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-157">Run the following command to initiate the script.</span></span></br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="ad377-p104">情報は、CSV ファイルとしてデスクトップにエクスポートされます。CSV のパスとファイル名を指定するのには、追加のパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad377-p104">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
### <a name="run-the-script-to-get-device-information-for-a-group-of-users"></a><span data-ttu-id="ad377-160">スクリプトを実行するユーザーのグループのデバイス情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad377-160">Run the script to get device information for a group of users</span></span>

1. <span data-ttu-id="ad377-161">Windows PowerShell 用 Microsoft Azure Active Directory モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="ad377-161">Open the Microsoft Azure Active Directory Module for Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ad377-p105">スクリプトを保存したフォルダーに移動します。などの C:\PS-Scripts に保存する場合は、次のコマンドを実行するとします。</span><span class="sxs-lookup"><span data-stu-id="ad377-p105">Navigate to the folder where you saved the script. For example, if you saved it to C:\PS-Scripts, you'd run the following command.</span></span></br>
  `cd C:\PS-Scripts`

3. <span data-ttu-id="ad377-p106">デバイスの詳細を取得するグループを識別する次のコマンドを実行します。この例では、FinanceStaff グループのユーザーの詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="ad377-p106">Run the following command to identify the group you want to get device details for. This example gets details for users in the FinanceStaff group.</span></span></br>
  ```
  $u = Get-MsolGroupMember -SearchString "FinanceStaff" | % { Get-MsolUser -ObjectId $_.ObjectId }
  ```

4. <span data-ttu-id="ad377-166">スクリプトを開始するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="ad377-166">Run the following command to initiate the script.</span></span></br>
  ```
  .\Get-MsolUserDeviceComplianceStatus.ps1 -User $u -Export
  ```

<span data-ttu-id="ad377-p107">情報は、CSV ファイルとしてデスクトップにエクスポートされます。CSV のパスとファイル名を指定するのには、追加のパラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad377-p107">The information is exported to your Windows Desktop as a CSV file. You can use additional parameters to specify the file name and path of the CSV.</span></span>
  
## <a name="more-info"></a><span data-ttu-id="ad377-169">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ad377-169">More info</span></span>

[<span data-ttu-id="ad377-170">Office 365 の MDM の概要</span><span class="sxs-lookup"><span data-stu-id="ad377-170">Overview of MDM for Office 365</span></span>](overview-of-mdm.md)
  
[<span data-ttu-id="ad377-171">Get MsolDevice</span><span class="sxs-lookup"><span data-stu-id="ad377-171">Get-MsolDevice</span></span>](https://go.microsoft.com/fwlink/?linkid=841721)
  

