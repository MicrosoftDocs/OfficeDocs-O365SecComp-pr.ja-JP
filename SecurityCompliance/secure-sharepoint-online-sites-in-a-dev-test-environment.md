---
title: 開発/テスト環境の SharePoint Online サイトをセキュリティで保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/18/2019
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 06af70f3-e7dc-4ee2-a385-fb4d61a5e93b
description: '概要: 開発/テスト環境で、パブリック、プライベート、機密、および高機密の SharePoint Online チーム サイトを作成します。'
ms.openlocfilehash: 148db19c8902735829a5849901723b5f2f200b74
ms.sourcegitcommit: 3ffd188a7fd547ae343ccf14361c1e4300f88de0
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/18/2019
ms.locfileid: "35059545"
---
# <a name="secure-sharepoint-online-sites-in-a-devtest-environment"></a><span data-ttu-id="040ca-103">開発/テスト環境の SharePoint Online サイトをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="040ca-103">Secure SharePoint Online sites in a dev/test environment</span></span>

 <span data-ttu-id="040ca-104">**概要:** 開発/テスト環境で、パブリック、プライベート、機密、および高機密の SharePoint Online チーム サイトを作成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-104">**Summary:** Create public, private, sensitive, and highly confidential SharePoint Online team sites in a dev/test environment.</span></span>
  
<span data-ttu-id="040ca-105">この記事では、4 つの異なるタイプの SharePoint Online チーム サイトを含む開発/テスト環境を [SharePoint Online サイトとファイルをセキュリティで保護する](secure-sharepoint-online-sites-and-files.md) ソリューション用に作成する手順を順を追って説明します。</span><span class="sxs-lookup"><span data-stu-id="040ca-105">This article provides step-by-step instructions to create a dev/test environment that includes the four different types of SharePoint Online team sites for the [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) solution.</span></span>
  
![セキュリティで保護された SharePoint Online の開発/テスト環境の 4 つすべてのチーム サイト。](media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
<span data-ttu-id="040ca-107">SharePoint Online チーム サイトを運用環境に展開する前に、この開発/テスト環境を使用して情報保護の動作を試し、特定の必要に応じて設定を微調整します。</span><span class="sxs-lookup"><span data-stu-id="040ca-107">Use this dev/test environment to experiment with the information protection behaviors and fine-tune settings for your specific needs before deploying SharePoint Online team sites in production.</span></span>
  
## <a name="phase-1-create-your-devtest-environment"></a><span data-ttu-id="040ca-108">フェーズ 1: 開発/テスト環境を作成する</span><span class="sxs-lookup"><span data-stu-id="040ca-108">Phase 1: Create your dev/test environment</span></span>

<span data-ttu-id="040ca-109">このフェーズでは、架空の組織用に Office 365 と Enterprise Mobility + Security (EMS) の試用版サブスクリプションを取得します。</span><span class="sxs-lookup"><span data-stu-id="040ca-109">In this phase, you obtain trial subscriptions for Office 365 and Enterprise Mobility + Security (EMS) for a fictional organization.</span></span>
  
<span data-ttu-id="040ca-110">まず、「[Office 365 開発/テスト環境](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment)」の**フェーズ 2**に記されている手順を実行します</span><span class="sxs-lookup"><span data-stu-id="040ca-110">First, follow the instructions in **Phase 2** of the [Office 365 dev/test environment](https://docs.microsoft.com/office365/enterprise/office-365-dev-test-environment).</span></span>
  
<span data-ttu-id="040ca-111">次に、EMS 試用版サブスクリプションにサインアップして、Office 365 試用版サブスクリプションと同じ組織に追加します。</span><span class="sxs-lookup"><span data-stu-id="040ca-111">Next, sign up for the EMS trial subscription and add it to the same organization as your Office 365 trial subscription.</span></span>
  
1. <span data-ttu-id="040ca-112">必要に応じて、試用版サブスクリプション用の全体管理者アカウントの資格情報で [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-112">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="040ca-113">左側のナビゲーションで **[請求]、[サービスを購入する]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-113">In the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="040ca-p101">**[サービスを購入]** ページで、 **[Enterprise Mobility + Security E5]** 項目を探します。その項目の上にマウス ポインターを移動させ、 **[無料試用版を起動する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-p101">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>
    
4. <span data-ttu-id="040ca-116">**[注文の確認]** ページで、 **[今すぐ実行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-116">On the **Confirm your order** page, click **Try now**.</span></span>
    
5. <span data-ttu-id="040ca-117">**[注文の受領書]** ページで、**[続行]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-117">On the **Order receipt** page, click **Continue**.</span></span>
    
<span data-ttu-id="040ca-118">次に、全体管理者アカウントの Enterprise Mobility + Security E5 ライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="040ca-118">Next, enable the Enterprise Mobility + Security E5 license for your global administrator account.</span></span>
  
1. <span data-ttu-id="040ca-119">ブラウザーの **[Microsoft 365 管理センター]** タブの左側のナビゲーションで **[ユーザー] > [アクティブなユーザー]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-119">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>
    
2. <span data-ttu-id="040ca-120">全体管理者アカウントをクリックしてから、 **[製品ライセンス]** で **[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-120">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>
    
3. <span data-ttu-id="040ca-121">**[製品ライセンス]** ウィンドウで、 **Enterprise Mobility + Security E5** の製品ライセンスを **[オン]** にして、 **[保存]** をクリックしてから、 **[閉じる]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-121">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>
    
## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups-and-users"></a><span data-ttu-id="040ca-122">フェーズ 2: Azure Active Directory (AD) グループとユーザーを作成して構成する</span><span class="sxs-lookup"><span data-stu-id="040ca-122">Phase 2: Create and configure your Azure Active Directory (AD) groups and users</span></span>

<span data-ttu-id="040ca-123">このフェーズでは、架空の組織用の Azure AD のグループとユーザーを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-123">In this phase, you create and configure the Azure AD groups and users for your fictional organization.</span></span>
  
<span data-ttu-id="040ca-124">最初に、Azure Portal で一般的な組織のグループのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-124">First, create a set of groups for a typical organization with the Azure portal.</span></span>
  
1. <span data-ttu-id="040ca-p102">ブラウザーで別のタブを作成し、Azure portal ([https://portal.azure.com](https://portal.azure.com)) に移動します。必要に応じて、Office 365 E5 の試用版サブスクリプション用の全体管理者アカウントの資格情報でサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-p102">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com). If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>
    
2. <span data-ttu-id="040ca-127">Azure Portal で **[Azure Active Directory] > [グループ]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-127">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="040ca-128">**[グループ] - [すべてのグループ]** ブレードで、**[+ 新しいグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-128">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="040ca-129">**[グループ]** ブレードでの手順:</span><span class="sxs-lookup"><span data-stu-id="040ca-129">On the **Group** blade:</span></span>
    
  - <span data-ttu-id="040ca-130">**[グループの種類]** で **[Office 365]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="040ca-130">Select **Office 365** in **Group type**.</span></span>
    
  - <span data-ttu-id="040ca-131">**[名前]** に「**C スイート**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-131">Type **C-Suite** in **Name**.</span></span>
    
  - <span data-ttu-id="040ca-132">**[メンバーシップの種類]** で **[割り当て済み]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="040ca-132">Select **Assigned** in **Membership type**.</span></span>
      
5. <span data-ttu-id="040ca-133">**[作成]** をクリックして、 **[グループ]** ブレードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="040ca-133">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="040ca-134">次のグループ名について手順 3 から 5 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="040ca-134">Repeat steps 3-5 for the following group names:</span></span>
    
  - <span data-ttu-id="040ca-135">IT staff (IT スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-135">IT staff</span></span>
    
  - <span data-ttu-id="040ca-136">Research staff (研究スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-136">Research staff</span></span>
    
  - <span data-ttu-id="040ca-137">Regular staff (正規スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-137">Regular staff</span></span>
    
  - <span data-ttu-id="040ca-138">Marketing staff (マーケティング スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-138">Marketing staff</span></span>
    
  - <span data-ttu-id="040ca-139">Sales staff (営業スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-139">Sales staff</span></span>
    
7. <span data-ttu-id="040ca-140">ブラウザーの [Azure Portal] タブを開いたままにします。</span><span class="sxs-lookup"><span data-stu-id="040ca-140">Keep the Azure portal tab in your browser open.</span></span>
    
<span data-ttu-id="040ca-141">次に、グループのメンバーが、Office 365 と EMS のサブスクリプションのライセンスを自動的に割り当てられるように、自動ライセンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-141">Next, you configure automatic licensing so that members of your groups are automatically assigned licenses for your Office 365 and EMS subscriptions.</span></span>
  
1. <span data-ttu-id="040ca-142">Azure Portal で **[Azure Active Directory] > [ライセンス] > [すべての製品]** の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-142">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>
    
2. <span data-ttu-id="040ca-143">一覧で、 **[Enterprise Mobility + Security E5]** と **[Office 365 Enterprise E5]** を選択し、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-143">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
    
3. <span data-ttu-id="040ca-144">**[ライセンスの割り当て]** ブレードで、 **[ユーザーとグループ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-144">In the **Assign license** blade, click **Users and groups**.</span></span>
    
4. <span data-ttu-id="040ca-145">グループの一覧で、以下を選択します。</span><span class="sxs-lookup"><span data-stu-id="040ca-145">In the list of groups, select the following:</span></span>
    
  - <span data-ttu-id="040ca-146">C-Suite (C スイート)</span><span class="sxs-lookup"><span data-stu-id="040ca-146">C-Suite</span></span>
    
  - <span data-ttu-id="040ca-147">IT staff (IT スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-147">IT staff</span></span>
    
  - <span data-ttu-id="040ca-148">Research staff (研究スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-148">Research staff</span></span>
    
  - <span data-ttu-id="040ca-149">Regular staff (正規スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-149">Regular staff</span></span>
    
  - <span data-ttu-id="040ca-150">Marketing staff (マーケティング スタッフ)</span><span class="sxs-lookup"><span data-stu-id="040ca-150">Marketing staff</span></span>
    
  - <span data-ttu-id="040ca-151">営業スタッフ</span><span class="sxs-lookup"><span data-stu-id="040ca-151">Sales staff</span></span>
    
5. <span data-ttu-id="040ca-152">**[選択]** をクリックし、 **[割り当て]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-152">Click **Select**, and then click **Assign**.</span></span>
    
6. <span data-ttu-id="040ca-153">ブラウザーの [Azure Portal] タブを閉じます。</span><span class="sxs-lookup"><span data-stu-id="040ca-153">Close the Azure portal tab in your browser.</span></span>
    
<span data-ttu-id="040ca-154">次に、[Graph 用 Azure Active Directory PowerShell モジュールに接続](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)します。</span><span class="sxs-lookup"><span data-stu-id="040ca-154">Next, you [Connect with the Azure Active Directory PowerShell for Graph module ](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="040ca-155">組織名、場所、および共通のパスワードを入力し、PowerShell コマンド プロンプトまたは Integrated Script Environment (ISE) からこれらのコマンドを実行し、ユーザー アカウントを作成し、それぞれのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="040ca-155">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create user accounts and add them to their groups:</span></span>
  
```
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Research staff"
$userNames=@("Researcher1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Regular staff"
$userNames=@("Regular1", "Regular2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Marketing staff"
$userNames=@("Marketing1", "Marketing2") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
$groupName="Sales staff"
$userNames=@("SalesPerson1") 
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){ 
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location 
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="040ca-156">ここで共通のパスワードを使用することで、自動化と、開発/テスト環境の構成を容易にします。</span><span class="sxs-lookup"><span data-stu-id="040ca-156">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="040ca-157">運用環境のサブスクリプションは避けるように強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="040ca-157">Obviously, this is highly discouraged for production subscriptions.</span></span> 
  
<span data-ttu-id="040ca-158">次の手順を使用して、グループ ベースのライセンスが正しく機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="040ca-158">Use these steps to verify that group-based licensing is working correctly.</span></span>
  
1. <span data-ttu-id="040ca-159">ブラウザーの **[Microsoft Office Home]** タブで、 **[管理者]** タイルをクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-159">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>
    
2. <span data-ttu-id="040ca-160">ブラウザーの新しい **Office 管理センター**のタブで、**[ユーザー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-160">From the new **Office Admin center** tab of your browser, click **Users**.</span></span>
    
3. <span data-ttu-id="040ca-161">ユーザーの一覧で、**[CEO]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-161">In the list of users, click **CEO**.</span></span>
    
4. <span data-ttu-id="040ca-162">**CEO** ユーザー アカウントのプロパティが一覧表示されているウィンドウで、(**[Product licenses]\(製品ライセンス\)** の) **Enterprise Mobility + Security E5** および **Office 365 Enterprise E5** のライセンスが割り当てられていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="040ca-162">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>
    
## <a name="phase-3-create-office-365-retention-labels"></a><span data-ttu-id="040ca-163">フェーズ 3: Office 365 保持ラベルを作成する</span><span class="sxs-lookup"><span data-stu-id="040ca-163">Phase 3: Create Office 365 retention labels</span></span>

<span data-ttu-id="040ca-164">このフェーズでは、SharePoint Online チーム サイトのドキュメント フォルダーに対してさまざまなセキュリティ レベルの保持ラベルを作成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-164">In this phase, you create the retention labels for the different levels of security for SharePoint Online team site documents folders.</span></span>


1. <span data-ttu-id="040ca-165">全体管理者アカウントで、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-165">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="040ca-166">ブラウザーの **[ホーム - Microsoft 365 コンプライアンス]** タブで、**[分類] > [ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-166">From the **Home - Microsoft 365 compliance** tab of your browser, click **Classifications > Labels**.</span></span>
    
3. <span data-ttu-id="040ca-167">**[保持ラベル] > [ラベルの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-167">Click **Retention labels > Create a label**.</span></span>
    
4. <span data-ttu-id="040ca-168">**[ラベルに名前をつける]** ウィンドウで、**[ラベルに名前をつける]** のところに「**内部パブリック**」と入力してから、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-168">On the **Name your label** pane, type **Internal Public** in **Name your label**, and then click **Next**.</span></span>

5. <span data-ttu-id="040ca-169">**[ファイル計画記述子]** ウィンドウで **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-169">On the **File plan descriptors** pane, click **Next**.</span></span>
    
6. <span data-ttu-id="040ca-170">**[ラベルの設定]** ウィンドウで、必要に応じて **[保持]** を **[オン]** にして **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-170">On the **Label settings** pane, if needed, set **Retention** to **On**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="040ca-171">**[設定の確認]** ウィンドウで、**[ラベルを作成する]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-171">On the **Review your settings** pane, click **Create the label**.</span></span>
    
8. <span data-ttu-id="040ca-172">次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="040ca-172">Repeat steps 3-7 for additional labels with these names:</span></span>
    
  - <span data-ttu-id="040ca-173">プライベート</span><span class="sxs-lookup"><span data-stu-id="040ca-173">Private</span></span>
    
  - <span data-ttu-id="040ca-174">機密</span><span class="sxs-lookup"><span data-stu-id="040ca-174">Sensitive</span></span>
    
  - <span data-ttu-id="040ca-175">非常に機密性の高い社外秘</span><span class="sxs-lookup"><span data-stu-id="040ca-175">Highly Confidential</span></span>
  
9. <span data-ttu-id="040ca-176">**[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-176">From the **Home > Labels** pane, click **Publish labels**.</span></span>
    
10. <span data-ttu-id="040ca-177">**[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-177">On the **Choose labels to publish** pane, click **Choose labels to publish**.</span></span>
    
11. <span data-ttu-id="040ca-178">**[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。</span><span class="sxs-lookup"><span data-stu-id="040ca-178">On the **Choose labels** pane, click **Add** and select all four labels.</span></span>
    
12. <span data-ttu-id="040ca-179">[ **完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-179">Click **Done**.</span></span>
    
13. <span data-ttu-id="040ca-180">**[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-180">On the **Choose labels to publish** pane, click **Next**.</span></span>
    
14. <span data-ttu-id="040ca-181">**[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-181">On the **Choose locations** pane, click **Next**.</span></span>
    
15. <span data-ttu-id="040ca-182">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-182">On the **Name your policy** pane, type **Example organization** in **Name**, and then click **Next**.</span></span>
    
16. <span data-ttu-id="040ca-183">**[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-183">On the **Review your settings** pane, click **Publish labels**, and then click **Close**.</span></span>
    
## <a name="phase-4-create-your-sharepoint-online-team-sites"></a><span data-ttu-id="040ca-184">フェーズ 4: SharePoint Online チーム サイトを作成する</span><span class="sxs-lookup"><span data-stu-id="040ca-184">Phase 4: Create your SharePoint Online team sites</span></span>

<span data-ttu-id="040ca-185">このフェーズでは、例の組織に 4 種類の SharePoint Online チーム サイトを作成して構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-185">In this phase, you create and configure the four types of SharePoint Online team sites for your example organization.</span></span>
  
### <a name="organization-wide-team-site"></a><span data-ttu-id="040ca-186">Organization wide チーム サイト</span><span class="sxs-lookup"><span data-stu-id="040ca-186">Organization wide team site</span></span>

<span data-ttu-id="040ca-187">ベースラインのパブリック SharePoint Online チーム サイトを作成するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="040ca-187">To create a baseline public SharePoint Online team site, do the following:</span></span>
  
1. <span data-ttu-id="040ca-188">必要な場合は、試用版サブスクリプションの全体管理者アカウントの資格情報で [Office 365 ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-188">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="040ca-189">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-189">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="040ca-190">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-190">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="040ca-191">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-191">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="040ca-192">**[サイト名]** に「**組織全体**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-192">In **Site name**, type **Organization wide**.</span></span> 
    
6. <span data-ttu-id="040ca-193">**[チーム サイトの説明]** に、「 **組織全体の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-193">In **Team site description**, type **SharePoint site for the entire organization**.</span></span>
    
7. <span data-ttu-id="040ca-194">**[プライバシー設定]** で、 **[パブリック - 組織の全ユーザーがこのサイトにアクセス可能]** を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-194">In **Privacy settings**, select **Public - anyone in the organization can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="040ca-195">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-195">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="040ca-196">次に、組織全体のチーム サイトのドキュメント フォルダーを [内部パブリック] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-196">Next, configure the documents folder of the Organization wide team site for the Internal Public label.</span></span>
  
1. <span data-ttu-id="040ca-197">ブラウザーの **[組織全体 - ホーム]** タブで、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-197">In the **Organization wide-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="040ca-198">[設定] アイコンをクリックしてから、 **[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-198">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="040ca-199">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-199">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="040ca-200">**[設定 - ラベルの適用]** で **[内部パブリック]** をクリックし、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-200">In **Settings-Apply Label**, select **Internal Public**, and then click **Save**.</span></span>
    
### <a name="project-1-team-site"></a><span data-ttu-id="040ca-201">プロジェクト 1 チーム サイト</span><span class="sxs-lookup"><span data-stu-id="040ca-201">Project 1 team site</span></span>

<span data-ttu-id="040ca-202">組織内のプロジェクト用にベースラインのプライベート SharePoint Online チーム サイトを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="040ca-202">To create a baseline private SharePoint Online team site for a project within the organization, do the following:</span></span>
  
1. <span data-ttu-id="040ca-203">必要な場合は、試用版サブスクリプションの全体管理者アカウントの資格情報で [Office 365 ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-203">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="040ca-204">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-204">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="040ca-205">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-205">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="040ca-206">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-206">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="040ca-207">**[サイト名]** に、「 **プロジェクト 1**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-207">In **Site name**, type **Project 1**.</span></span> 
    
6. <span data-ttu-id="040ca-208">**[チーム サイトの説明]** に、「 **プロジェクト 1 の SharePoint サイト**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-208">In **Team site description,** type **SharePoint site for Project 1**.</span></span>
    
7. <span data-ttu-id="040ca-209">**[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-209">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="040ca-210">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-210">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
<span data-ttu-id="040ca-211">次に、プライベート ラベル用に Project 1 チーム サイトのドキュメント フォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-211">Next, configure the documents folder of the Project 1 team site for the Private label.</span></span>
  
1. <span data-ttu-id="040ca-212">ブラウザーの **[プロジェクト 1 - ホーム]** タブで、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-212">In the **Project 1-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="040ca-213">[設定] アイコンをクリックしてから、 **[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-213">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="040ca-214">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-214">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="040ca-215">**[設定 - ラベルの適用]** で **[プライベート]** をクリックし、**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-215">In **Settings-Apply Label**, select **Private**, and then click **Save**.</span></span>
    
### <a name="marketing-campaigns-team-site"></a><span data-ttu-id="040ca-216">マーケティング キャンペーン チーム サイト</span><span class="sxs-lookup"><span data-stu-id="040ca-216">Marketing campaigns team site</span></span>

<span data-ttu-id="040ca-217">マーケティング キャンペーン リソース用の機密レベルの分離した SharePoint Online チーム サイトを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="040ca-217">To create a sensitive-level isolated SharePoint Online team site for marketing campaign resources, do the following:</span></span>

 
1. <span data-ttu-id="040ca-218">必要な場合は、試用版サブスクリプションの全体管理者アカウントの資格情報で [Office 365 ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-218">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="040ca-219">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-219">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="040ca-220">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-220">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="040ca-221">**[サイトの作成]** ページで、**[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-221">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="040ca-222">**[Team site name]\(チーム サイト名\)** に、「**Marketing campaigns**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-222">In **Team site name**, type **Marketing campaigns**.</span></span>
    
6. <span data-ttu-id="040ca-223">**[チーム サイトの説明]** に、「 **マーケティング キャンペーン リソースの SharePoint サイト (機密)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-223">In **Team site description**, type **SharePoint site for marketing campaign resources (sensitive)**.</span></span>
    
7.  <span data-ttu-id="040ca-224">**[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-224">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="040ca-225">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-225">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="040ca-226">ブラウザーの新しい **[マーケティング キャンペーン]** タブのツール バーで、設定アイコンをクリックしてから、 **[サイトのアクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-226">On the new **Marketing campaigns** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="040ca-227">**[サイトの権限]** ウィンドウで、 **[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-227">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="040ca-228">ブラウザーの新しい **[アクセス許可]** タブで、**[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-228">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="040ca-229">**[アクセス要求の設定]** ダイアログ ボックスで、**[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可します]** および **[メンバーが、他のユーザーをサイト メンバー グループに招待することを許可します]** チェック ボックスをクリアし、**[すべてのアクセス要求を送信する]** に「**ITAdmin1@**\<組織名>**.onmicrosoft.com**」と入力し、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-229">In the **Access Request Settings** dialog box, clear the **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** check boxes, type **ITAdmin1@**\<your organization name>**.onmicrosoft.com** in **Send all requests for access**, and then click **OK**.</span></span>
    
13. <span data-ttu-id="040ca-230">一覧にある **[マーケティング キャンペーン メンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-230">Click **Marketing campaigns Members** in the list.</span></span>
    
14. <span data-ttu-id="040ca-231">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-231">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="040ca-232">**[共有]** ダイアログ ボックスで、「 **マーケティング スタッフ**」と入力し、それを選択してから、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-232">In the **Share** dialog box, type **Marketing staff**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="040ca-233">**Researcher1** ユーザー アカウントに対して手順 14 と 15 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="040ca-233">Repeat steps 14 and 15 for the **Researcher1** user account.</span></span>
    
17. <span data-ttu-id="040ca-234">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-234">Click the back button on your browser.</span></span>
    
18. <span data-ttu-id="040ca-235">一覧にある **[マーケティング キャンペーン所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-235">Click **Marketing campaigns Owners** in the list.</span></span>
    
19. <span data-ttu-id="040ca-236">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-236">On the **People and Groups** page, click **New**.</span></span>
    
20. <span data-ttu-id="040ca-237">**[共有]** ダイアログ ボックスに「 **IT スタッフ**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-237">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
21. <span data-ttu-id="040ca-238">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-238">Click the back button on your browser.</span></span>
    
22. <span data-ttu-id="040ca-239">ブラウザーの **[ユーザーとグループ]** タブを閉じて、ブラウザーの **[マーケティング キャンペーン - ホーム]** タブをクリックしてから、 **[サイトのアクセス許可]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="040ca-239">Close the **People and Groups** tab in your browser, click the **Marketing campaigns-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="040ca-240">権限を構成した結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="040ca-240">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="040ca-241">**Marketing campaigns - メンバー** SharePoint グループには、**Marketing campaigns** グループ (全体管理者ユーザー アカウントを含む)、**Marketing staff (マーケティング スタッフ)** グループ (Marketing1 および Marketing2 のユーザー アカウントを含む)、および **Researcher1** ユーザー アカウントのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="040ca-241">The **Marketing campaigns-Members** SharePoint group contains only the **Marketing campaigns** group (which contains the global administrator user account), the **Marketing staff** group (which contains the Marketing1 and Marketing2 user accounts), and the **Researcher1** user account.</span></span>
    
- <span data-ttu-id="040ca-242">**Marketing campaigns - 所有者** SharePoint グループには、**IT staff (IT スタッフ)** グループ (ITAdmin1 および ITAdmin2 のユーザー アカウントのみを含む) のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="040ca-242">The **Marketing campaigns-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="040ca-243">**Marketing campaigns - 閲覧者** SharePoint グループには、グループまたはユーザー アカウントは含まれません。</span><span class="sxs-lookup"><span data-stu-id="040ca-243">The **Marketing campaigns-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="040ca-244">メンバーは、サイト レベルのアクセス許可を変更できません (これを実行できるのは、 **[マーケティング キャンペーン - 所有者]** グループのメンバーだけです)。</span><span class="sxs-lookup"><span data-stu-id="040ca-244">Members cannot modify site-level permissions (this can only be done by members of the **Marketing campaigns-Owners** group).</span></span>
    
- <span data-ttu-id="040ca-245">他のユーザー アカウントは、サイトやそのリソースにアクセスできませんが、サイトへのアクセスを要求することができます。これにより、ITAdmin1 ユーザー アカウントのメールボックスに電子メールが送信されます。</span><span class="sxs-lookup"><span data-stu-id="040ca-245">Other user accounts cannot access the site or its resources, but can request access to the site, which will send an email to the ITAdmin1 user account mailbox.</span></span>
    
<span data-ttu-id="040ca-246">次に、マーケティング キャンペーン チーム サイトのドキュメント フォルダーを [機密] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-246">Next, configure the documents folder of the Marketing campaigns team site for the Sensitive label.</span></span>
  
1. <span data-ttu-id="040ca-247">ブラウザーの **[マーケティング キャンペーン - ホーム]** タブで、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-247">In the **Marketing campaigns-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="040ca-248">[設定] アイコンをクリックしてから、 **[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-248">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="040ca-249">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-249">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="040ca-250">**[設定 - ラベルの適用]** で **[機密]** をクリックし、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-250">In **Settings-Apply Label**, select **Sensitive**, and then click **Save**.</span></span>
    
<span data-ttu-id="040ca-251">次に、機密ラベルのある SharePoint Online チーム サイト上のドキュメントを共有しようとしているユーザーに通知を行うデータ損失防止 (DLP) ポリシーを構成します。このチーム サイトには、組織外部のマーケティング キャンペーン サイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="040ca-251">Next, configure a data loss prevention (DLP) policy that notifies users when they share a document on a SharePoint Online team site with the Sensitive label, which includes the Marketing campaigns site, outside the organization.</span></span>

1. <span data-ttu-id="040ca-252">全体管理者アカウントで、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-252">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin account.</span></span>
    
2. <span data-ttu-id="040ca-253">ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-253">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="040ca-254">**[ホーム] > [データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-254">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="040ca-255">**[テンプレートを利用するか、カスタム ポリシーを作成します]** ウィンドウで、**[カスタム]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-255">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="040ca-256">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **機密ラベル SharePoint Online チーム サイト**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-256">In the **Name your policy** pane, type **Sensitive label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="040ca-257">**[場所の選択]** ウィンドウで、**[特定の場所を選択]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-257">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="040ca-258">場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-258">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="040ca-259">**[保護するコンテンツの種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-259">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="040ca-260">**[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-260">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="040ca-261">**[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-261">In the **Retention labels** pane, click **Add**, select the **Sensitive** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="040ca-262">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-262">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="040ca-263">**保護するコンテンツの種類をカスタマイズする** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-263">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="040ca-264">**機密性の高い情報が検出された場合に実行する操作** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-264">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="040ca-265">**[ポリシー ヒントと電子メール通知をカスタマイズする]** ウィンドウで、**[ポリシー ヒント テキストをカスタマイズする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-265">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="040ca-266">機密性の高いファイルを保護するために Azure Information Protection を実装したかどうかに応じて、テキスト ボックスに、次のいずれかのヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="040ca-266">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="040ca-p104">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="040ca-p104">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="040ca-270">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-270">Click **OK**.</span></span>
    
17. <span data-ttu-id="040ca-271">**[機密性の高い情報が検出された場合に実行する操作]** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-271">In the **What do you want to do if we detect sensitive info?** pane, click **Next**.</span></span>
    
18. <span data-ttu-id="040ca-272">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-272">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="040ca-273">**[設定の確認]** ウィンドウで、**[作成]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-273">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
  
### <a name="company-strategy-team-site"></a><span data-ttu-id="040ca-274">会社戦略のチーム サイト</span><span class="sxs-lookup"><span data-stu-id="040ca-274">Company strategy team site</span></span>

<span data-ttu-id="040ca-275">組織の最高責任者の戦略上の会社のリソース用に高機密レベルで分離した SharePoint Online チーム サイトを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="040ca-275">To create an isolated SharePoint Online team site at the highly confidential level for strategic company resources of the chief executives of the organization, do the following:</span></span>
  
1. <span data-ttu-id="040ca-276">必要な場合は、試用版サブスクリプションの全体管理者アカウントの資格情報で [Office 365 ポータル](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-276">If needed, sign in to the [Office 365 portal](https://portal.office.com) with the credentials of the global administrator account of your trial subscription.</span></span>
    
2. <span data-ttu-id="040ca-277">タイルのリストで、**[SharePoint]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-277">In the list of tiles, click **SharePoint**.</span></span>
    
3. <span data-ttu-id="040ca-278">ブラウザーの新しい **SharePoint** タブで、**[+ サイトの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-278">On the new **SharePoint** tab in your browser, click **+ Create site**.</span></span>
    
4. <span data-ttu-id="040ca-279">**[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-279">On the **Create a site** page, click **Team site**.</span></span>
    
5. <span data-ttu-id="040ca-280">**[Team site name]\(チーム サイト名\)** に「**Company strategy**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-280">In **Team site name**, type **Company strategy**.</span></span>
    
6. <span data-ttu-id="040ca-281">**[チーム サイトの説明]** に、「 **会社戦略の SharePoint サイト (高機密)**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-281">In **Team site description**, type **SharePoint site for company strategy (highly confidential)**.</span></span>
    
7.  <span data-ttu-id="040ca-282">**[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-282">In **Privacy settings**, select **Private - only members can access this site**, and then click **Next**.</span></span>
    
8. <span data-ttu-id="040ca-283">**[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-283">On the **Who do you want to add?** pane, click **Finish**.</span></span>
    
9. <span data-ttu-id="040ca-284">ブラウザーの新しい **[会社戦略]** タブのツール バーで、設定アイコンをクリックしてから、 **[サイトのアクセス許可]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-284">On the new **Company strategy** tab in your browser, in the tool bar, click the settings icon, and then click **Site permissions**.</span></span>
    
10. <span data-ttu-id="040ca-285">**[サイトの権限]** ウィンドウで、 **[高度な権限の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-285">In the **Site permissions** pane, click **Advanced permissions settings**.</span></span>
    
11. <span data-ttu-id="040ca-286">ブラウザーの新しい **[アクセス許可]** タブで、 **[アクセス要求の設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-286">In the new **Permissions** tab in your browser, click **Access Request Settings**.</span></span>
    
12. <span data-ttu-id="040ca-287">**[アクセス要求の設定]** ダイアログ ボックスの **[サイトと個別のファイルおよびフォルダーの共有をメンバーに許可します]** と **[メンバーが、他のユーザーをサイト メンバー グループに招待することを許可します]** をクリアし (これによって、3 つのチェック ボックスがすべてクリアされる)、 **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-287">In the **Access Request Settings** dialog box, clear **Allow members to share the site and individual files and folders** and **Allow members to invite others to the site members group** (so that all three check boxes are cleared), and then click **OK**.</span></span>
    
13. <span data-ttu-id="040ca-288">一覧にある **[会社戦略メンバー]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-288">Click **Company strategy Members** in the list.</span></span>
    
14. <span data-ttu-id="040ca-289">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-289">On the **People and Groups** page, click **New**.</span></span>
    
15. <span data-ttu-id="040ca-290">**[共有]** ダイアログ ボックスで、「 **C スイート**」と入力し、それを選択してから、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-290">In the **Share** dialog box, type **C-Suite**, select it, and then click **Share**.</span></span>
    
16. <span data-ttu-id="040ca-291">一覧にある **[会社戦略所有者]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-291">Click **Company strategy Owners** in the list.</span></span>
    
17. <span data-ttu-id="040ca-292">**[ユーザーとグループ]** ページで、 **[新規]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-292">On the **People and Groups** page, click **New**.</span></span>
    
18. <span data-ttu-id="040ca-293">**[共有]** ダイアログ ボックスに「 **IT スタッフ**」と入力し、それを選択して、 **[共有]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-293">In the **Share** dialog box, type **IT staff**, select it, and then click **Share**.</span></span>
    
19. <span data-ttu-id="040ca-294">ブラウザーの戻るボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-294">Click the back button on your browser.</span></span>
    
20. <span data-ttu-id="040ca-295">ブラウザーの **[ユーザーとグループ]** タブを閉じて、ブラウザーの **[会社戦略 - ホーム]** タブをクリックしてから、 **[サイトのアクセス許可]** ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="040ca-295">Close the **People and Groups** tab in your browser, click the **Company strategy-Home** tab in your browser, and then close the **Site permissions** pane.</span></span>
    
<span data-ttu-id="040ca-296">権限を構成した結果を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="040ca-296">Here are the results of configuring permissions:</span></span>
  
- <span data-ttu-id="040ca-297">**[会社戦略 - メンバー]** SharePoint グループには、 **[C スイート]** グループ (CEO、CFO、および CIO ユーザー アカウントのみを含む) と **[会社戦略]** グループ (全体管理者ユーザー アカウントのみを含む) のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="040ca-297">The **Company strategy-Members** SharePoint group contains only the **C-Suite** group (which contains only the CEO, CFO, and CIO user accounts) and the **Company strategy** group (which contains only the global administrator user account).</span></span>
    
- <span data-ttu-id="040ca-298">**[会社戦略 - 所有者]** SharePoint グループには、 **[IT スタッフ]** グループ (ITAdmin1 ユーザー アカウントと ITAdmin2 ユーザー アカウントのみを含む) のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="040ca-298">The **Company strategy-Owners** SharePoint group contains only the **IT staff** group (which contains only the ITAdmin1 and ITAdmin2 user accounts).</span></span>
    
- <span data-ttu-id="040ca-299">**[会社戦略 - 訪問者]** SharePoint グループには、グループまたはユーザー アカウントは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="040ca-299">The **Company strategy-Visitors** SharePoint group contains no groups or user accounts.</span></span>
    
- <span data-ttu-id="040ca-300">メンバーはサイト レベルのアクセス許可を変更できません (これを実行できるのは、 **[会社戦略 - 所有者]** グループのメンバーだけです)。</span><span class="sxs-lookup"><span data-stu-id="040ca-300">Members cannot modify site-level permissions (this can only be done by members of the **Company strategy-Owners** group).</span></span>
    
- <span data-ttu-id="040ca-p105">その他のユーザー アカウントは、サイトやそのリソースにアクセスすることも、そのサイトへのアクセスを要求することもできません。サイトへの追加のアクセス許可は、全体管理者または **[会社戦略 - 所有者]** グループのメンバーが行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="040ca-p105">Other user accounts cannot access the site or its resources or request access to the site. Additional permissions to the site must be done by the global administrator or by a member of the **Company strategy-Owners** group.</span></span>
    
<span data-ttu-id="040ca-303">次に、会社戦略チーム サイトのドキュメント フォルダーを [高機密] ラベル用に構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-303">Next, configure the documents folder of the Company strategy team site for the Highly Confidential label.</span></span>
  
1. <span data-ttu-id="040ca-304">ブラウザーの **[会社戦略 - ホーム]** タブで、 **[ドキュメント]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-304">In the **Company strategy-Home** tab of your browser, click **Documents**.</span></span>
    
2. <span data-ttu-id="040ca-305">[設定] アイコンをクリックしてから、 **[ライブラリの設定]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-305">Click the settings icon, and then click **Library settings**.</span></span>
    
3. <span data-ttu-id="040ca-306">**[権限と管理]** をクリックして、 **[このライブラリ内の項目にラベルを適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-306">Under **Permissions and Management**, click **Apply label to items in this library**.</span></span>
    
4. <span data-ttu-id="040ca-307">**[設定 - ラベルの適用]** で **[高機密]** をクリックし、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-307">In **Settings-Apply Label**, select **Highly Confidential**, and then click **Save**.</span></span>
    
<span data-ttu-id="040ca-308">次に、高機密ラベルのある SharePoint Online チーム サイト上のドキュメントをユーザーが共有するのをブロックする DLP ポリシーを構成します。このチーム サイトには、組織外部の会社戦略サイトが含まれます。</span><span class="sxs-lookup"><span data-stu-id="040ca-308">Next, configure a DLP policy that blocks users when they share a document on a SharePoint Online team site with the Highly Confidential label, which includes the Company strategy site, outside the organization.</span></span>
  
1. <span data-ttu-id="040ca-309">全体管理者で、[Microsoft 365 コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-309">Sign in to the [Microsoft 365 compliance portal](https://compliance.microsoft.com/) with your global admin.</span></span>
    
2. <span data-ttu-id="040ca-310">ブラウザーの新しい **[Microsoft 365 コンプライアンス]** タブで、**[ポリシー] > [データ損失防止]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-310">On the new **Microsoft 365 compliance** tab in your browser, click **Policies > Data loss prevention**.</span></span>
    
3. <span data-ttu-id="040ca-311">**[ホーム] > [データ損失防止]** ウィンドウで、**[ポリシーの作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-311">In the **Home > Data loss prevention** pane, click **Create a policy**.</span></span>
    
4. <span data-ttu-id="040ca-312">**[テンプレートを利用するか、カスタム ポリシーを作成します]** ウィンドウで、**[カスタム]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-312">In the **Start with a template or create a custom policy** pane, click **Custom**, and then click **Next**.</span></span>
    
5. <span data-ttu-id="040ca-313">**[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **高機密ラベル SharePoint Online チーム サイト**」と入力してから、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-313">In the **Name your policy** pane, type **Highly Confidential label SharePoint Online team sites** in **Name**, and then click **Next**.</span></span>
    
6. <span data-ttu-id="040ca-314">**[場所の選択]** ウィンドウで、**[特定の場所を選択]** をクリックしてから **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-314">In the **Choose locations** pane, click **Let me choose specific locations**, and then click **Next**.</span></span>
    
7. <span data-ttu-id="040ca-315">場所の一覧で、**[Exchange メール]**、**[OneDrive アカウント]**、および **[Teams のチャットとチャネルのメッセージ]** の場所を無効にして、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-315">In the list of locations, disable the **Exchange email**, **OneDrive accounts**, and **Teams chat and channel messages** locations, and then click **Next**.</span></span>
    
8. <span data-ttu-id="040ca-316">**[保護するコンテンツの種類をカスタマイズする]** ウィンドウで、**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-316">In the **Customize the type of content you want to protect** pane, click **Edit**.</span></span>
    
9. <span data-ttu-id="040ca-317">**[保護するコンテンツの種類を選ぶ]** ウィンドウのドロップダウン ボックスで **[追加]** をクリックしてから、**[保持ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-317">In the **Choose the types of content to protect** pane, click **Add** in the drop-down box, and then click **Retention labels**.</span></span>
    
10. <span data-ttu-id="040ca-318">**[保持ラベル]** ウィンドウで、**[追加]** をクリックして **[高機密]** ラベルを選択し、**[追加]** をクリックしてから **[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-318">In the **Retention labels** pane, click **Add**, select the **Highly Confidential** label, click **Add**, and then click **Done**.</span></span>
    
11. <span data-ttu-id="040ca-319">**[保護するコンテンツの種類を選択する]** ウィンドウで、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-319">In the **Choose the types of content to protect** pane, click **Save**.</span></span>
    
12. <span data-ttu-id="040ca-320">**保護するコンテンツの種類をカスタマイズする** ウィンドウで、**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-320">In the **Customize the type of content you want to protect** pane, click **Next**.</span></span>

13. <span data-ttu-id="040ca-321">**機密性の高い情報が検出された場合に実行する操作** ウィンドウで、**ヒントと電子メールをカスタマイズする** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-321">In the **What do you want to do if we detect sensitive info?** pane, click **Customize the tip and email**.</span></span>
    
14. <span data-ttu-id="040ca-322">**[ポリシー ヒントと電子メール通知をカスタマイズする]** ウィンドウで、**[ポリシー ヒント テキストをカスタマイズする]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-322">In the **Customize policy tips and email notifications** pane, click **Customize the policy tip text**.</span></span>
    
15. <span data-ttu-id="040ca-323">機密性の高いファイルを保護するために Azure Information Protection を実装したかどうかに応じて、テキスト ボックスに、次のいずれかのヒントを入力するか、貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="040ca-323">In the text box, type or paste in one of the following tips, depending on if you implemented Azure Information Protection to protect highly confidential files:</span></span>
    
  - <span data-ttu-id="040ca-p106">組織外のユーザーと共有するには、ファイルをダウンロードしてから開きます。[ファイル]、[文書の保護]、[パスワードを使用して暗号化] の順にクリックし、強力なパスワードを指定します。別の電子メールまたはその他の通信手段でパスワードを送信します。</span><span class="sxs-lookup"><span data-stu-id="040ca-p106">To share with a user outside the organization, download the file and then open it. Click File, then Protect Document, and then Encrypt with Password, and then specify a strong password. Send the password in a separate email or other means of communication.</span></span>
    
16. <span data-ttu-id="040ca-327">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-327">Click **OK**.</span></span>
    
17. <span data-ttu-id="040ca-328">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-328">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>

18. <span data-ttu-id="040ca-329">**[ポリシーを有効にしますか、または最初にテストしますか?]** ウィンドウで、 **[すぐ有効にします]** をクリックし、 **[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-329">In the **Do you want to turn on the policy or test things out first?** pane, click **Yes, turn it on right away**, and then click **Next**.</span></span>
    
19. <span data-ttu-id="040ca-330">**[設定の確認]** ウィンドウで、 **[作成]** をクリックしてから **[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-330">In the **Review your settings** pane, click **Create**, and then click **Close**.</span></span>
   
    
<span data-ttu-id="040ca-331">次に、「[Microsoft 365 管理センターから Azure Rights Management をアクティブ化する方法](https://docs.microsoft.com/information-protection/deploy-use/activate-office365)」にある指示に従います。</span><span class="sxs-lookup"><span data-stu-id="040ca-331">Next, follow the instructions in [Activate Azure RMS with the Microsoft 365 admin center](https://docs.microsoft.com/information-protection/deploy-use/activate-office365).</span></span>
  
<span data-ttu-id="040ca-332">次に、以下の手順に従い、保護とアクセス許可用に C-Suite グループを対象とした新しいポリシーとサブラベルを使用して、Azure Information Protection を構成します。</span><span class="sxs-lookup"><span data-stu-id="040ca-332">Next, configure Azure Information Protection with a new policy and sub-label scoped for the C-Suite group for protection and permissions with the following steps:</span></span>
  
1. <span data-ttu-id="040ca-333">必要に応じて、全体管理者アカウントを使用して、[Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="040ca-333">If needed, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global admin account.</span></span>
    
2. <span data-ttu-id="040ca-334">ブラウザーで別のタブを開き、Azure portal ([https://portal.azure.com](https://portal.azure.com)) に移動します。</span><span class="sxs-lookup"><span data-stu-id="040ca-334">In a separate tab of your browser, go to the Azure portal ([https://portal.azure.com](https://portal.azure.com)).</span></span>
    
3. <span data-ttu-id="040ca-335">初めて Azure Information Protection を構成する場合は、これらの[手順](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="040ca-335">If this is the first time you are configuring Azure Information Protection, see these [instructions](https://docs.microsoft.com/information-protection/deploy-use/configure-policy#to-access-the-azure-information-protection-blade-for-the-first-time).</span></span>
    
4. <span data-ttu-id="040ca-336">リスト ウィンドウで、**[すべてのサービス]** をクリックして、「**information**」と入力し、**[Azure Information Protection]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-336">In the list pane, click **All services**, type **information**, and then click **Azure Information Protection**.</span></span>

5. <span data-ttu-id="040ca-337">**[ラベル]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-337">Click **Labels**.</span></span>
    
6. <span data-ttu-id="040ca-338">**[非常に機密性の高い社外秘]** ラベルを右クリックしてから、**[サブラベルの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-338">Right-click the **Highly Confidential** label, and then click **Add a sub-label**.</span></span>
    
7. <span data-ttu-id="040ca-339">**[名前]** と **[説明]** に「**C-Suite members**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-339">Type **C-Suite members** in **Name** and **Description**.</span></span>
    
8. <span data-ttu-id="040ca-340">**[このラベルを含むドキュメントやメールに対するアクセス許可の設定]** で、**[保護]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-340">In **Set permissions for documents and emails containing this label**, click **Protect**.</span></span>
    
9. <span data-ttu-id="040ca-341">**[保護]** セクションで **[Azure (クラウド キー)]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-341">In the **Protection** section, click **Azure (cloud key)**.</span></span>
    
10. <span data-ttu-id="040ca-342">**[保護]** ブレードで **[保護設定]** の **[+ アクセス許可の追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-342">On the **Protection** blade, under **Protection settings**, click **+ Add permissions**.</span></span>
    
11. <span data-ttu-id="040ca-343">**[アクセス許可を追加する]** ブレードの **[ユーザーとグループの指定]** で、 **[+ ディレクトリを参照]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-343">On the **Add permissions** blade, under **Specify users and groups**, click **+ Browse directory**.</span></span>
    
12. <span data-ttu-id="040ca-344">**[AAD ユーザーとグループ]** ウィンドウで、**[C スイート]** を選択してから、**[選択]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-344">On the **AAD Users and Groups** pane, select **C-Suite**, and then click **Select**.</span></span>
    
13. <span data-ttu-id="040ca-345">**[事前設定またはカスタムの設定からアクセス許可を選択する]** の **[カスタム]** をクリックし、次に **[権限の表示]**、**[コンテンツの編集]**、**[保存]**、**[返信]**、**[全員へ返信]** の各チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="040ca-345">Under **Choose permissions from the preset or set custom**, click **Custom**, and then click the **View Rights**, **Edit Content**, **Save**, **Reply**, and **Reply all** check boxes.</span></span>
    
14. <span data-ttu-id="040ca-346">**[OK]** を 2 回クリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-346">Click **OK** twice.</span></span>
    
15. <span data-ttu-id="040ca-347">**[サブラベル]** ブレードで **[保存]** をクリックし、次に **[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-347">On the **Sub-label** blade, click **Save**, and then click **OK**.</span></span>

16. <span data-ttu-id="040ca-348">**[Azure Information Protection]** ブレードで **[ポリシー] > [+ 新しいポリシーの追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-348">On the **Azure Information protection** blade, click **Policies > + Add a new policy**.</span></span>
    
17. <span data-ttu-id="040ca-349">**[ポリシー名]** に「**CompanyStrategy**」と入力し、**[説明]** に「**会社戦略チーム サイトのドキュメント**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="040ca-349">Type **CompanyStrategy** in **Policy name** and **Documents in the Company strategy team site** in **Description**.</span></span>
    
18. <span data-ttu-id="040ca-350">**[このポリシーを取得するユーザーまたはグループを選択してください] > [ユーザー/グループ]** をクリックし、 **[C スイート]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="040ca-350">Click **Select which users or groups get this policy > User/Groups**, and then select **C-Suite**.</span></span>
    
19. <span data-ttu-id="040ca-351">**[選択] > [OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-351">Click **Select > OK**.</span></span>

20. <span data-ttu-id="040ca-p107">**[ラベルの追加または削除]** をクリックします。**[ポリシー: ラベルの追加または削除]** ペインで **[C-Suite]** をクリックしてから、**[OK]** をクリックます。</span><span class="sxs-lookup"><span data-stu-id="040ca-p107">Click **Add or remove labels**. In the **Policy: Add or remove labels** pane, click **C-Suite**, and then click **OK**.</span></span>   

21. <span data-ttu-id="040ca-354">**[保存]** をクリックし、**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="040ca-354">Click **Save**, and then click **OK**.</span></span>
    
<span data-ttu-id="040ca-355">Azure Information Protection とこの新しいラベルでドキュメントを保護するには、テスト マシンに [Azure Information Protection クライアントをインストール](https://docs.microsoft.com/information-protection/rms-client/install-client-app)し、管理センターから Office をインストールしてから、試用版サブスクリプションの **[C スイート]** グループのアカウントを使用して Microsoft Word からサインインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="040ca-355">To protect a document with Azure Information Protection and this new label, you must [install the Azure Information Protection client](https://docs.microsoft.com/information-protection/rms-client/install-client-app) on a test machine, install Office from the admin center, and then sign in from Microsoft Word with an account in the **C-Suite** group of your trial subscription.</span></span>
  
<span data-ttu-id="040ca-356">これら 4 つのサイトでドキュメントを作成し、試用版サブスクリプションでさまざまなユーザー アカウントを使用して、それらへのアクセスをテストする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="040ca-356">You are now ready to create documents in these four sites and test access to them with various user accounts in your trial subscription.</span></span>
  
<span data-ttu-id="040ca-357">ここに 4 つの SharePoint Online チーム サイト全体の構成を示します。</span><span class="sxs-lookup"><span data-stu-id="040ca-357">Here is the overall configuration for all four SharePoint Online team sites.</span></span>
  
![セキュリティで保護された SharePoint Online の開発/テスト環境の 4 つすべてのチーム サイト。](media/b0fea489-359c-4c85-a0ad-e4efb4a1e47f.png)
  
## <a name="next-step"></a><span data-ttu-id="040ca-359">次の手順</span><span class="sxs-lookup"><span data-stu-id="040ca-359">Next step</span></span>

<span data-ttu-id="040ca-360">セキュリティで保護された SharePoint Online サイトの本番展開の準備が整ったら、「[SharePoint Online サイトとファイルをセキュリティで保護する](secure-sharepoint-online-sites-and-files.md)」を参照して、詳細情報と、展開を順を追って説明した記事へのリンクをご確認ください。</span><span class="sxs-lookup"><span data-stu-id="040ca-360">When you are ready for production deployment of secure SharePoint Online sites, see [Secure SharePoint Online sites and files](secure-sharepoint-online-sites-and-files.md) for detailed information and links to step-by-step deployment articles.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="040ca-361">関連項目</span><span class="sxs-lookup"><span data-stu-id="040ca-361">See Also</span></span>

[<span data-ttu-id="040ca-362">SharePoint Online サイトとファイルをセキュリティで保護する</span><span class="sxs-lookup"><span data-stu-id="040ca-362">Secure SharePoint Online sites and files</span></span>](secure-sharepoint-online-sites-and-files.md)
  
[<span data-ttu-id="040ca-363">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="040ca-363">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
  
[<span data-ttu-id="040ca-364">選挙運動、非営利組織、およびその他のアジャイル組織のための Microsoft Security ガイダンス</span><span class="sxs-lookup"><span data-stu-id="040ca-364">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)




