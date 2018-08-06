---
title: ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 9d64867b-ebdb-4323-8e30-4560d76b4c97
description: ビジネス要件が変化すると、1 つの Microsoft Exchange Online Protection (EOP) 組織 (テナント) を 2 つの別個の組織に分割したり、2 つの組織を 1 つに併合したり、ドメインや EOP の設定を 1 つの組織から別の組織へ移動したりする必要が生じることがあります。
ms.openlocfilehash: 87bf6a4f1e7d0fac1f98255d222693cb4910f1a6
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027664"
---
# <a name="move-domains-and-settings-from-one-eop-organization-to-another-eop-organization"></a><span data-ttu-id="dd360-103">ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する</span><span class="sxs-lookup"><span data-stu-id="dd360-103">Move domains and settings from one EOP organization to another EOP organization</span></span>

<span data-ttu-id="dd360-p101">ビジネス要件が変化すると、1 つの Microsoft Exchange Online Protection (EOP) 組織 (テナント) を 2 つの別個の組織に分割したり、2 つの組織を 1 つに併合したり、ドメインや EOP の設定を 1 つの組織から別の組織へ移動したりする必要が生じることがあります。1 つの EOP 組織から別の EOP 組織へ移動するのは難しい作業ですが、いくつかの基本的なリモート Windows PowerShell スクリプトを用意し、少しの準備作業を行えば、比較的短いメンテナンス期間で完了できます。</span><span class="sxs-lookup"><span data-stu-id="dd360-p101">Changing business requirements can sometimes require splitting one Microsoft Exchange Online Protection (EOP) organization (tenant) into two separate organizations, merging two organizations into one, or moving your domains and EOP settings from one organization to another organization. Moving from one EOP organization to a second EOP organization can be challenging, but with a few basic remote Windows PowerShell scripts and a small amount of preparation, this can be achieved with a relatively small maintenance window.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="dd360-p102">設定を確実に移動できるのは、EOP スタンドアロン (Standard) 組織から別の EOP Standard または Exchange Enterprise CAL with Services (EOP Premium) 組織のいずれかへの移動、または EOP Premium 組織から別の EOP Premium 組織への移動だけです。一部のプレミアム機能は EOP Standard 組織ではサポートされないため、EOP Premium 組織から EOP Premium 組織への移動は成功しないことがあります。 >  この記事の指示は、EOP フィルターのみの組織を対象にしています。1 つの Exchange Online 組織から別の Exchange Online 組織への移動には、追加の考慮事項があります。Exchange Online 組織は、この記事の指示の適用範囲外です。</span><span class="sxs-lookup"><span data-stu-id="dd360-p102">Settings can be reliably moved only from an EOP standalone (Standard) organization to either another EOP Standard or an Exchange Enterprise CAL with Services (EOP Premium) organization, or from an EOP Premium organization to another EOP Premium organization. Because some premium features are not supported in EOP Standard organizations, moves from an EOP Premium organization to an EOP Premium organization might not be successful. >  These instructions are for EOP filtering-only organizations. There are additional considerations in moving from one Exchange Online organization to another Exchange Online organization. Exchange Online organizations are out of scope for these instructions.</span></span> 
  
<span data-ttu-id="dd360-p103">次の例では、Contoso, Ltd. 社を Contoso Suites 社に併合します。次の図は、ドメイン、メール ユーザーとグループ、および設定を、移動元 EOP 組織 (contoso.onmicrosoft.com) から移動先 EOP 組織 (contososuites.onmicrosoft.com) に移動するプロセスを示しています。</span><span class="sxs-lookup"><span data-stu-id="dd360-p103">In the following example, Contoso, Ltd. has merged with Contoso Suites. The following image shows the process of moving domains, mail users and groups, and settings from the source EOP organization (contoso.onmicrosoft.com) to the target EOP organization (contososuites.onmicrosoft.com):</span></span>
  
![EOP ドメインと設定の移動](../media/EOP-Move-domains-and-settings.jpg)
  
<span data-ttu-id="dd360-p104">1 つの組織から別の組織へドメインを移動する際の課題は、検証済みのドメインが 2 つの組織で同時には存在し得ないことです。この記事で説明する手順は、この課題に対処するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="dd360-p104">The challenge in moving domains from one organization to another is that a verified domain can't exist in two organizations at the same time. The following steps help you work through this.</span></span>
      
## <a name="step-1-collect-data-from-the-source-organization"></a><span data-ttu-id="dd360-116">手順 1: 移動元の組織からデータを収集する</span><span class="sxs-lookup"><span data-stu-id="dd360-116">Step 1: Collect data from the source organization</span></span>

<span data-ttu-id="dd360-117">移動元の組織を移動先の組織に再作成するには、移動元の組織について次に挙げる情報を収集して保管してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-117">In order to re-create the source organization in the target organization, make sure that you collect and store the following information about the source organization:</span></span>
  
- <span data-ttu-id="dd360-118">ドメイン</span><span class="sxs-lookup"><span data-stu-id="dd360-118">Domains</span></span>
    
- <span data-ttu-id="dd360-119">メール ユーザー</span><span class="sxs-lookup"><span data-stu-id="dd360-119">Mail users</span></span>
    
- <span data-ttu-id="dd360-120">グループ</span><span class="sxs-lookup"><span data-stu-id="dd360-120">Groups</span></span>
    
- <span data-ttu-id="dd360-121">スパム対策のコンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="dd360-121">Anti-spam content filters</span></span>
    
- <span data-ttu-id="dd360-122">マルウェア対策のコンテンツ フィルター</span><span class="sxs-lookup"><span data-stu-id="dd360-122">Anti-malware content filters</span></span>
    
- <span data-ttu-id="dd360-123">コネクタ</span><span class="sxs-lookup"><span data-stu-id="dd360-123">Connectors</span></span>
    
- <span data-ttu-id="dd360-124">トランスポート ルール</span><span class="sxs-lookup"><span data-stu-id="dd360-124">Transport rules</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dd360-125">トランスポート ルール コレクションのエクスポートとインポートに対するコマンドレット サポートは、現在のところ、EOP Premium サブスクリプション プランだけでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="dd360-125">Cmdlet support for the export and import of the Transport Rule Collection is currently only supported for EOP Premium subscription plans.</span></span> 
  
<span data-ttu-id="dd360-p105">これらの設定をすべて収集する最も簡単な方法は、リモート Windows PowerShell を使用する方法です。リモート Windows PowerShell を使用して EOP に接続する方法については、「[リモート PowerShell を使用して Exchange Online Protection に接続する](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p105">The easiest way to collect all of your settings is to use remote Windows PowerShell. To connect to EOP by using remote Windows PowerShell, see [Connect to Exchange Online Protection Using Remote PowerShell](http://technet.microsoft.com/library/054e0fd7-d465-4572-93f8-a00a9136e4d1.aspx).</span></span>
  
<span data-ttu-id="dd360-p106">次に、すべての設定を収集し、それらを .xml ファイルにエクスポートし、そのファイルを移動先のテナントにインポートします。一般に、各設定の **Get** コマンドレットの出力を **Export-Clixml** コマンドレットにパイプ処理することにより、設定を .xml ファイルに保存できます。この後のコード例に示すとおりです。</span><span class="sxs-lookup"><span data-stu-id="dd360-p106">Next, you can collect all your settings and export them to an .xml file to be imported into the target tenant. In general, you can pipe the output of the **Get** cmdlet for each setting to the **Export-Clixml** cmdlet to save the settings in .xml files, as shown in the following code sample.</span></span> 
  
<span data-ttu-id="dd360-p107">リモート Windows PowerShell に接続した後、見つけやすい場所に Export というディレクトリを作成し、そのディレクトリに移動します。次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="dd360-p107">After you've connected to remote Windows PowerShell, create a directory called Export in a location that's easy to find and change to that directory. For example:</span></span>
  
```
mkdir C:\EOP\Export
```

```
cd C:\EOP\Export
```

<span data-ttu-id="dd360-p108">次のスクリプトは、移動元の組織のすべてのメール ユーザー、グループ、スパム対策の設定、マルウェア対策の設定、コネクター、およびトランスポート ルールを収集するために使用できます。次のテキストをコピーしてメモ帳などのテキスト エディターに貼り付け、それを先ほど作成した Export ディレクトリに Source_EOP_Settings.ps1 という名前で保存し、次のコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p108">The following script can be used to collect all the mail users, groups, anti-spam settings, anti-malware settings, connectors, and transport rules in the source organization. Copy and paste the following text into a text editor like Notepad, save the file as Source_EOP_Settings.ps1 in the Export directory you just created, and run the following command:</span></span>
  
```
&amp; "C:\EOP\Export\Source_EOP_Settings.ps1"

```

```
#****************************************************************************
# Export Domains
#*****************************************************************************
Get-AcceptedDomain | Export-Clixml Domains.xml
#****************************************************************************
# Export mail users
#
#****************************************************************************
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUser | Export-Clixml MailUsers.xml
#****************************************************************************
# Groups
#
# If you're using directory synchronization, you can skip this step and 
# simply sync to the target 
# tenant.
# First, you need to capture information about the distribution groups.
#****************************************************************************
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUniversalDistributionGroup | Export-Clixml DistributionGroups.xml
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUniversalSecurityGroup | Export-Clixml SecurityGroups.xml 
#****************************************************************************
# And then we'll use that output to loop through each group and get the 
# members.
#****************************************************************************
$DGs = Import-Clixml .\DistributionGroups.xml
ForEach ($dg in $DGs) {Get-DistributionGroupMember -Identity $dg.name | Export-Clixml $dg.ExternalDirectoryObjectId}
$SGs = Import-Clixml .\SecurityGroups.xml
ForEach ($sg in $SGs) {Get-DistributionGroupMember -Identity $sg.name | Export-Clixml $sg.ExternalDirectoryObjectId} 
#*****************************************************************************
# Export dynamic distribution groups - EOP Premium Only
#
# If you're using directory synchronization, then you can skip this step and simply 
# sync to the target tenant.
#*****************************************************************************
Get-DynamicDistributionGroup -ResultSize unlimited | Export-Clixml DynamicDistributionGroups.xml
#*****************************************************************************
# Export mail contacts - EOP Premium Only
#
# If you're using directory synchronization, then you can skip this step and simply 
# sync to the target tenant.
#*****************************************************************************
Get-MailContact -ResultSize unlimited -RecipientTypeDetails MailContact | Export-Clixml MailContacts.xml
#****************************************************************************
# Anti-spam
#****************************************************************************
Get-HostedConnectionFilterPolicy | Export-Clixml HostedConnectionFilterPolicy.xml
Get-HostedContentFilterPolicy | Export-Clixml HostedContentFilterPolicy.xml
Get-HostedContentFilterRule | Export-Clixml HostedContentFilterRule.xml
Get-HostedOutboundSpamFilterPolicy | Export-Clixml HostedOutboundSpamFilterPolicy.xml
#****************************************************************************
# Anti-malware content filters
#****************************************************************************
Get-MalwareFilterPolicy | Export-Clixml MalwareFilterPolicy.xml
Get-MalwareFilterRule | Export-Clixml MalwareFilterRule.xml
#****************************************************************************
# Connectors
#****************************************************************************
Get-InboundConnector | Export-Clixml InboundConnector.xml
Get-OutboundConnector | Export-Clixml OutboundConnector.xml
#****************************************************************************
# Exchange transport rules
#****************************************************************************
$file = Export-TransportRuleCollection
Set-Content -Path ".TransportRules.xml" -Value $file.FileData -Encoding Byte

```

<span data-ttu-id="dd360-p109">次のコマンドを Export ディレクトリから実行して、移動先の組織の .xml ファイルを更新します。contoso.onmicrosoft.com と contososuites.onmicrosoft.com は、実際の移動元および移動先の組織の名前に置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p109">Run the following commands from the Export directory to update the .xml files with the target organization. Replace contoso.onmicrosoft.com and contososuites.onmicrosoft.com with your source and target organization names.</span></span>
  
```
$files = ls
ForEach ($file in $files) { (Get-Content $file.Name) | Foreach-Object {$_ -replace 'contoso.onmicrosoft.com', 'contososuites.onmicrosoft.com'} | Set-Content $file.Name}
```

## <a name="step-2-add-domains-to-the-target-organization"></a><span data-ttu-id="dd360-136">手順 2: 移動先の組織にドメインを追加する</span><span class="sxs-lookup"><span data-stu-id="dd360-136">Step 2: Add domains to the target organization</span></span>

<span data-ttu-id="dd360-p110">次のスクリプトを使用して、移動先の組織にドメインを追加します。テキストをコピーしてメモ帳などのテキスト エディターに貼り付け、スクリプトを C:\EOP\Export\Add_Domains.ps1 として保存し、次のコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p110">Add domains to the target organization by using the following script. Copy and paste the text into a text editor like Notepad, save the script as C:\EOP\Export\Add_Domains.ps1, and run the following command:</span></span>
  
```
&amp; "C:\EOP\Export\Add_Domains.ps1"
```

<span data-ttu-id="dd360-139">これらのドメインは検証されず、メールのルーティングには使用できませんが、ドメインを追加した後、ドメインを検証するために必要な情報を収集し、最終的には新しいテナントに合わせて MX レコードを更新できます。</span><span class="sxs-lookup"><span data-stu-id="dd360-139">These domains won't be verified and can't be used to route mail, but after the domains are added, you can collect the information needed to verify the domains and eventually update your MX records for the new tenant.</span></span>
  
```
#***********************************************************************
# Login to Azure Active Directory
#*****************************************************************************
$msolcred = Get-Credential
connect-msolservice -credential $msolcred
#****************************************************************************
# Add domains
#****************************************************************************
$Domains = Import-Clixml ".\Domains.xml"
Foreach ($domain in $Domains) {
    New-MsolDomain -Name $domain.Name
} 

```

<span data-ttu-id="dd360-140">この時点で、移動先の組織の Office 365 管理センターからの情報を検討して収集し、タイミングを見計らってドメインを手早く検証することができます。</span><span class="sxs-lookup"><span data-stu-id="dd360-140">Now, you can review and collect the information from the Office 365 admin center of your target organization so that you can quickly verify your domains when the time comes:</span></span>
  
1. <span data-ttu-id="dd360-141">[https://portal.office.com](https://portal.office.com) の Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dd360-141">Sign in to the Office 365 admin center at [https://portal.office.com](https://portal.office.com).</span></span>
    
2. <span data-ttu-id="dd360-142">**[ドメイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd360-142">Click **Domains**.</span></span>
    
3. <span data-ttu-id="dd360-143">それぞれの **[セットアップの開始]** リンクをクリックした後、セットアップ ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="dd360-143">Click each **Start setup** link, and then proceed through the setup wizard.</span></span> 
    
4. <span data-ttu-id="dd360-144">**[所有者の確認]** ページで、 **[次のレジストラーを使用してこの操作を実行するためのステップ バイ ステップの手順を確認します]** に対して **[一般的な手順]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="dd360-144">On the **Confirm ownership** page, for **See step-by-step instructions for performing this step with**, select **General instructions**.</span></span>
    
5. <span data-ttu-id="dd360-145">ドメインの検証に使用する MX レコードまたは TXT レコードを記録し、セットアップ ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="dd360-145">Record the MX record or TXT record that you'll use to verify your domain, and finish the setup wizard.</span></span>
    
6. <span data-ttu-id="dd360-p111">検証 TXT レコードを DNS レコードに追加します。これにより、移動元の組織からドメインを削除した後、移動先の組織でドメインを迅速に検証できます。DNS の構成の詳細については、「[Office 365 の DNS レコードを作成する](https://go.microsoft.com/fwlink/p/?LinkId=304219)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p111">Add the verification TXT records to your DNS records. This will let you more quickly verify the domains in the source organization after they're removed from the target organization. For more information about configuring DNS, see [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).</span></span>
    
## <a name="step-3-force-senders-to-queue-mail"></a><span data-ttu-id="dd360-149">手順 3: 送信者がメールをキューに格納するように強制する</span><span class="sxs-lookup"><span data-stu-id="dd360-149">Step 3: Force senders to queue mail</span></span>

<span data-ttu-id="dd360-p112">ドメインを 1 つのテナントから別のテナントへ移動している間は、移動元の組織からドメインを削除し、その後、移動先の組織でドメインを検証する必要があります。この作業の間は、EOP を介してメールをルーティングすることができません。</span><span class="sxs-lookup"><span data-stu-id="dd360-p112">While moving your domains from one tenant to another, you'll need to delete the domains from the source organization and then verify them in your target organization. During this time, you won't be able to route mail through EOP.</span></span>
  
<span data-ttu-id="dd360-152">送信者がメールをキューに格納するように強制する 1 つの方法は、MX レコードを更新して、社内のメール サーバーを直接ポイントするようにする方法です。</span><span class="sxs-lookup"><span data-stu-id="dd360-152">One option to force senders to queue mail is to update your MX records to point directly to your on-premises mail server.</span></span>
  
<span data-ttu-id="dd360-p113">別の方法として、自分のドメインに対する DNS レコードが保持されている各ドメイン (DNS ホスティング サービスとも呼ばれる) に無効な MX レコード置く方法もあります。このようにすると、送信元ではメールをキューに格納し、再試行します (通常は 48 時間にわたって再試行しますが、プロバイダーによって異なります)。無効な MX 宛先としては、invalid.outlook.com を使用できます。MX レコードの有効時間 (TTL) 値を 5 分に短縮すれば、変更が各 DNS プロバイダーに伝達されるまでの時間を短縮できます。</span><span class="sxs-lookup"><span data-stu-id="dd360-p113">Another option is to put an invalid MX record in each domain where the DNS records for your domain are kept (also known as your DNS hosting service). This will cause the sender to queue your mail and retry (typical retry attempts are for 48 hours, but this might vary from provider to provider). You can use invalid.outlook.com as an invalid MX target. Lowering the Time to Live (TTL) value to five minutes on the MX record will help the change propagate to DNS providers more quickly.</span></span>
  
<span data-ttu-id="dd360-157">DNS の構成の詳細については、「[Office 365 の DNS レコードを作成する](https://go.microsoft.com/fwlink/p/?LinkId=304219)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-157">For more information about configuring DNS, see [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dd360-p114">メールをキューに保持する時間はプロバイダーごとに異なります。キューに格納する時間が満了して送信者に配信不能レポート (NDR) が送信されるのを避けるため、新しいテナントを迅速に設定し、DNS 設定を元に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd360-p114">Different providers queue mail for different periods of time. You'll need to set up your new tenant quickly and revert your DNS settings to avoid non-delivery reports (NDRs) from being sent to the sender if the queuing time expires.</span></span> 
  
## <a name="step-4-remove-users-groups-and-domains-from-the-source-organization"></a><span data-ttu-id="dd360-160">手順 4: 移動元の組織からユーザー、グループ、およびドメインを削除する</span><span class="sxs-lookup"><span data-stu-id="dd360-160">Step 4: Remove users, groups, and domains from the source organization</span></span>

<span data-ttu-id="dd360-p115">次のスクリプトでは、Azure Active Directory のリモート Windows PowerShell を使用して、移動元のテナントからユーザー、グループ、およびドメインを削除します。次のテキストをコピーしてメモ帳などのテキスト エディターに貼り付け、ファイルを C:\EOP\Export\Remove_Users_and_Groups.ps1 として保存し、次のコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p115">The following script removes users, groups, and domains from the source tenant by using Azure Active Directory remote Windows PowerShell. Copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Remove_Users_and_Groups.ps1, and run the following command:</span></span>
  
```
&amp; "C:\EOP\Export\Remove_Users_and_Groups.ps1"
```

```
#*****************************************************************************
# Login to Azure Active Directory
#*****************************************************************************
$msolcred= Get-Credential
connect-msolservice -credential $msolcred
#*****************************************************************************
# Remove users
#*****************************************************************************
$Users = Get-MSOLUser -All | sort UserPrincipalName
$user_count = $Users.count
write-host "Removing $user_count users."
Foreach ($User in $Users) {
write-host $User.UserPrincipalName
$User | Remove-MSOLUser -Force
}
#*****************************************************************************
# Remove groups
#*****************************************************************************
Get-MSOLGroup | Remove-MSOLGroup -Force
#*****************************************************************************
# Remove domains
# Note: Your onmicrosoft.com domain should be the default domain
#*****************************************************************************
$Domains = Get-MsolDomain
$Domain_count = $Domains.count
write-host "Removing $Domain_count domains."
Foreach ($Domain in $Domains) {
write-host $Domain.Name
Remove-MsolDomain -DomainName $Domain.Name -Force
} 

```

## <a name="step-5-verify-domains-for-the-target-organization"></a><span data-ttu-id="dd360-163">手順 5: 移動先の組織のドメインを検証する</span><span class="sxs-lookup"><span data-stu-id="dd360-163">Step 5: Verify domains for the target organization</span></span>

1. <span data-ttu-id="dd360-164">[https://portal.office.com](https://portal.office.com) の Office 365 管理センターにサインインします。</span><span class="sxs-lookup"><span data-stu-id="dd360-164">Sign in to the Office 365 admin center at [https://portal.office.com](https://portal.office.com).</span></span>
    
2. <span data-ttu-id="dd360-165">**[ドメイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dd360-165">Click **Domains**.</span></span>
    
3. <span data-ttu-id="dd360-166">移動先のドメインの各 **[セットアップの開始]** リンクをクリックし、セットアップ ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="dd360-166">Click each **Start setup** link for the target domain and proceed through the setup wizard.</span></span> 
    
## <a name="step-6-add-mail-users-and-groups-to-the-target-organization"></a><span data-ttu-id="dd360-167">手順 6: 移動先の組織にメール ユーザーとグループを追加する</span><span class="sxs-lookup"><span data-stu-id="dd360-167">Step 6: Add mail users and groups to the target organization</span></span>

<span data-ttu-id="dd360-p116">EOP の場合のベスト プラクティスは、Azure Active Directory を使用して社内の Active Directory と移動先のテナントで同期をとる方法です。これを行う方法の詳細については、「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」の「ディレクトリの同期を使用してメール ユーザーを管理する」セクションを参照してください。別の方法として、次のスクリプトを使用して移動元のテナントからユーザーとグループを再作成することもできます。メモ:ユーザーのパスワードは移動できません。新しいユーザー パスワードが作成され、UsersAndGroups.ps1 という名前のファイルに保存されます。(パスワード再設定の詳細については、「[ユーザーのパスワードを再設定する](https://office.microsoft.com/en-us/office365-suite-help/reset-a-user-s-password-HA102816058.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p116">A best practice for EOP is to use Azure Active Directory to sync your on-premises Active Directory to your target tenant. For more information about how to do this, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](manage-mail-users-in-eop.md). You can also use the following script to recreate your users and groups from your source tenant. Note: User passwords cannot be moved. New user passwords are created and saved in the file named UsersAndGroups.ps1. (For more information about resetting your password, see [Reset a user's password](https://office.microsoft.com/en-us/office365-suite-help/reset-a-user-s-password-HA102816058.aspx).)</span></span>
  
<span data-ttu-id="dd360-174">スクリプトを使用するには、次のテキストをコピーしてメモ帳などのテキスト エディターに貼り付け、ファイルを C:\EOP\Export\Add_Users_and_Groups.ps1 として保存し、次のコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-174">To use the script, copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Add_Users_and_Groups.ps1, and run the following command:</span></span>
  
```
&amp; "C:\EOP\Export\Add_Users_and_Groups.ps1"
```

```
#***********************************************************************
# makeparam helper function
#****************************************************************************
function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam       
 } 
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\UsersAndGroups.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# Add mail users
#****************************************************************************
$rand = New-Object System.Random -ArgumentList (get-date).millisecond
$MailUsers = Import-Clixml ".\MailUsers.xml"
$MailUsersCount = $MailUsers.Name.Count
if($MailUsersCount -gt 0){
    Write-Host "Importing $MailUsersCount Mail Users"
    ForEach ($MailUser in $MailUsers) {
        $MailUsersCmdlet = "New-MailUser"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPMailUser"
        }
        $MailUsersCmdlet += makeparam "LastName" $MailUser.LastName
        $MailUsersCmdlet += makeparam "FirstName" $MailUser.FirstName
        $MailUsersCmdlet += makeparam "DisplayName" $MailUser.DisplayName
        $MailUsersCmdlet += makeparam "Name" $MailUser.Name
        $MailUsersCmdlet += makeparam "Alias" $MailUser.Alias
        $MailUsersCmdlet += makeparam "MicrosoftOnlineServicesID" $MailUser.MicrosoftOnlineServicesID
        $MailUsersCmdlet += makeparam "ExternalEmailAddress" $MailUser.ExternalEmailAddress
        
        # Generate a new 10 character password
        $NewPassword = ""
        1..10 | ForEach { $NewPassword = $NewPassword + [char]$rand.next(40,127) }
        
        $MailUsersCmdlet += " -Password (ConvertTo-SecureString -String '$NewPassword' -AsPlainText -Force)"
        Add-Content $outfile "`n$MailUsersCmdlet"
    }
}
#****************************************************************************
# Add distribution groups
#****************************************************************************
$DistributionGroups = Import-Clixml ".\DistributionGroups.xml"
$DistributionGroupsCount = $DistributionGroups.Name.Count
if($DistributionGroupsCount -gt 0){
    Write-Host "Importing $DistributionGroupsCount Distribution Groups"
    ForEach ($DistributionGroup in $DistributionGroups) {
        $DistributionGroupsCmdlet = "New-DistributionGroup"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPDistributionGroup"
        }
        $DistributionGroupsCmdlet += makeparam "Name" $DistributionGroup.Name
        $DistributionGroupsCmdlet += makeparam "Alias" $DistributionGroup.Alias
        $DistributionGroupsCmdlet += makeparam "DisplayName" $DistributionGroup.DisplayName
        $DistributionGroupsCmdlet += makeparam "ManagedBy" $DistributionGroup.ManagedBy
        
        $DistributionGroupsCmdlet += makeparam "Notes" $DistributionGroup.Notes
        $DistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DistributionGroup.PrimarySmtpAddress
        $DistributionGroupsCmdlet += makeparam "Type" $DistributionGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $DistributionGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$DistributionGroupsCmdlet"
}
#****************************************************************************
# Add security groups
#****************************************************************************
$SecurityGroups = Import-Clixml ".\SecurityGroups.xml"
$SecurityGroupsCount = $SecurityGroups.Name.Count
if($SecurityGroupsCount -gt 0){
    Write-Host "Importing $SecurityGroupsCount Security Groups"
    ForEach ($SecurityGroup in $SecurityGroups) {
        $SecurityGroupsCmdlet = "New-SecurityGroup"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPSecurityGroup"
        }
        $SecurityGroupsCmdlet += makeparam "Name" $SecurityGroup.Name
        $SecurityGroupsCmdlet += makeparam "Alias" $SecurityGroup.Alias
        $SecurityGroupsCmdlet += makeparam "DisplayName" $SecurityGroup.DisplayName
        $SecurityGroupsCmdlet += makeparam "ManagedBy" $SecurityGroup.ManagedBy
        
        $SecurityGroupsCmdlet += makeparam "Notes" $SecurityGroup.Notes
        $SecurityGroupsCmdlet += makeparam "PrimarySmtpAddress" $SecurityGroup.PrimarySmtpAddress
        $SecurityGroupsCmdlet += makeparam "Type" $SecurityGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $SecurityGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$SecurityGroupsCmdlet"
}
#****************************************************************************
# Add Dynamic Distribution Groups
#****************************************************************************
If((Get-PSSession).ComputerName.Contains("ps.protection")) {
    write-Host "No Synamic Distribution Groups for EOP Standard organizations."
}else{
    $DynamicDistributionGroups = Import-Clixml ".\DynamicDistributionGroups.xml"
    $DynamicDistributionGroupsCount = $DynamicDistributionGroups.Name.Count
    if($DynamicDistributionGroupsCount -gt 0){
        Write-Host "Importing $DynamicDistributionGroupsCount Dynamic Distribution Groups"
        foreach ($DynamicDistributionGroup in $DynamicDistributionGroups) {
            $DynamicDistributionGroupsCmdlet = "New-DynamicDistributionGroup" 
            $DynamicDistributionGroupsCmdlet += " -Confirm:`$False"
            $DynamicDistributionGroupsCmdlet += makeparam "DisplayName" $DynamicDistributionGroup.DisplayName 
            $DynamicDistributionGroupsCmdlet += makeparam "ModeratedBy" $DynamicDistributionGroup.ModeratedBy 
            $DynamicDistributionGroupsCmdlet += makeparam "ModerationEnabled" $DynamicDistributionGroup.ModerationEnabled 
            $DynamicDistributionGroupsCmdlet += makeparam "Name" $DynamicDistributionGroup.Name 
            $DynamicDistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DynamicDistributionGroup.PrimarySmtpAddress 
            $DynamicDistributionGroupsCmdlet += makeparam "RecipientContainer" $DynamicDistributionGroup.RecipientContainer
            $RecipientFilterParam =  makeparam "RecipientFilter" $DynamicDistributionGroup.RecipientFilter
            $RecipientFilterParam = " -RecipientFilter {" + $RecipientFilterParam.Substring(19)
            $RecipientFilterParam = $RecipientFilterParam.Substring(0,$RecipientFilterParam.Length-1)
            $RecipientFilterParam += "}"
            $DynamicDistributionGroupsCmdlet +=  $RecipientFilterParam
            $DynamicDistributionGroupsCmdlet += makeparam "SendModerationNotifications" $DynamicDistributionGroup.SendModerationNotifications 
            Add-Content $outfile "`n$DynamicDistributionGroupsCmdlet"
        }
    
    }else{ 
        Write-Host "No Dynamic Distribution Groups to add."
    }
} 
#****************************************************************************
# Add Mail Contacts
#****************************************************************************
If((Get-PSSession).ComputerName.Contains("ps.protection")) {
    write-Host "No Mail Contact for EOP Standard organizations."
}else{
    $MailContacts = Import-Clixml ".\MailContacts.xml"
    $MailContactsCount = $MailContacts.Name.Count
    if($MailContactsCount -gt 0){
        Write-Host "Importing $MailContactsCount Dynamic Distribution Groups"
        foreach ($MailContact in $MailContacts) {
            $MailContactsCmdlet = "New-MailContact" 
            $MailContactsCmdlet += makeparam "UsePreferMessageFormat" $MailContact.UsePreferMessageFormat
            $MailContactsCmdlet += makeparam "DisplayName" $MailContact.DisplayName
            $MailContactsCmdlet += makeparam "ModeratedBy" $MailContact.ModeratedBy
            $MailContactsCmdlet += makeparam "Name" $MailContact.Name
            $MailContactsCmdlet += makeparam "MessageBodyFormat" $MailContact.MessageBodyFormat
            $MailContactsCmdlet += makeparam "OrganizationalUnit" $MailContact.OrganizationalUnit
            $MailContactsCmdlet += makeparam "Initials" $MailContact.Initials
            $MailContactsCmdlet += makeparam "MessageFormat" $MailContact.MessageFormat
            $MailContactsCmdlet += makeparam "ModerationEnabled" $MailContact.ModerationEnabled
            $MailContactsCmdlet += makeparam "MacAttachmentFormat" $MailContact.MacAttachmentFormat
            $MailContactsCmdlet += makeparam "SendModerationNotifications" $MailContact.SendModerationNotifications
            $MailContactsCmdlet += " -Confirm:`$False"
            $MailContactsCmdlet += makeparam "ExternalEmailAddress" $MailContact.ExternalEmailAddress
            $MailContactsCmdlet += makeparam "FirstName" $MailContact.FirstName
            $MailContactsCmdlet += makeparam "Alias" $MailContact.Alias
            Add-Content $outfile "`n$MailContactsCmdlet"
        }
    
    }else{ 
        Write-Host "No Mail Contacts to add."
    }
}
#***********************************************************************
# makeparam helper function
#************************************************************************
 function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam       
 } 
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\UsersAndGroups.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# Add mail users
#****************************************************************************
$rand = New-Object System.Random -ArgumentList (get-date).millisecond
$MailUsers = Import-Clixml ".\MailUsers.xml"
$MailUsersCount = $MailUsers.Name.Count
if($MailUsersCount -gt 0){
    Write-Host "Importing $MailUsersCount Mail Users"
    ForEach ($MailUser in $MailUsers) {
        $MailUsersCmdlet = "New-EOPMailUser"
        $MailUsersCmdlet += makeparam "LastName" $MailUser.LastName
        $MailUsersCmdlet += makeparam "FirstName" $MailUser.FirstName
        $MailUsersCmdlet += makeparam "DisplayName" $MailUser.DisplayName
        $MailUsersCmdlet += makeparam "Name" $MailUser.Name
        $MailUsersCmdlet += makeparam "Alias" $MailUser.Alias
        $MailUsersCmdlet += makeparam "MicrosoftOnlineServicesID" $MailUser.MicrosoftOnlineServicesID
        $MailUsersCmdlet += makeparam "ExternalEmailAddress" $MailUser.ExternalEmailAddress
        
        # Generate a new 10 character password
        $NewPassword = ""
        1..10 | ForEach { $NewPassword = $NewPassword + [char]$rand.next(40,127) }
        
        $MailUsersCmdlet += " -Password (ConvertTo-SecureString -String '$NewPassword' -AsPlainText -Force)"
        Add-Content $outfile "`n$MailUsersCmdlet"
    }
}
#****************************************************************************
# Add distribution groups
#****************************************************************************
$DistributionGroups = Import-Clixml ".\DistributionGroups.xml"
$DistributionGroupsCount = $DistributionGroups.Name.Count
if($DistributionGroupsCount -gt 0){
    Write-Host "Importing $DistributionGroupsCount Distribution Groups"
    ForEach ($DistributionGroup in $DistributionGroups) {
        $DistributionGroupsCmdlet = "New-EOPDistributionGroup"
        $DistributionGroupsCmdlet += makeparam "Name" $DistributionGroup.Name
        $DistributionGroupsCmdlet += makeparam "Alias" $DistributionGroup.Alias
        $DistributionGroupsCmdlet += makeparam "DisplayName" $DistributionGroup.DisplayName
        $DistributionGroupsCmdlet += makeparam "ManagedBy" $DistributionGroup.ManagedBy
        
        $DistributionGroupsCmdlet += makeparam "Notes" $DistributionGroup.Notes
        $DistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DistributionGroup.PrimarySmtpAddress
        $DistributionGroupsCmdlet += makeparam "Type" $DistributionGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $DistributionGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$DistributionGroupsCmdlet"
}
#****************************************************************************
# Add security groups
#****************************************************************************
$SecurityGroups = Import-Clixml ".\SecurityGroups.xml"
$SecurityGroupsCount = $SecurityGroups.Name.Count
if($SecurityGroupsCount -gt 0){
    Write-Host "Importing $SecurityGroupsCount Security Groups"
    ForEach ($SecurityGroup in $SecurityGroups) {
        $SecurityGroupsCmdlet = "New-EOPSecurityGroup"
        $SecurityGroupsCmdlet += makeparam "Name" $SecurityGroup.Name
        $SecurityGroupsCmdlet += makeparam "Alias" $SecurityGroup.Alias
        $SecurityGroupsCmdlet += makeparam "DisplayName" $SecurityGroup.DisplayName
        $SecurityGroupsCmdlet += makeparam "ManagedBy" $SecurityGroup.ManagedBy
        
        $SecurityGroupsCmdlet += makeparam "Notes" $SecurityGroup.Notes
        $SecurityGroupsCmdlet += makeparam "PrimarySmtpAddress" $SecurityGroup.PrimarySmtpAddress
        $SecurityGroupsCmdlet += makeparam "Type" $SecurityGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $SecurityGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$SecurityGroupsCmdlet"
}
#****************************************************************************
# Add Dynamic Distribution Groups
#****************************************************************************
$DynamicDistributionGroups = Import-Clixml ".\DynamicDistributionGroups.xml"
$DynamicDistributionGroupsCount = $DynamicDistributionGroups.Name.Count
if($DynamicDistributionGroupsCount -gt 0){
    Write-Host "Importing $DynamicDistributionGroupsCount Dynamic Distribution Groups"
    foreach ($DynamicDistributionGroup in $DynamicDistributionGroups) {
        $DynamicDistributionGroupsCmdlet = "New-DynamicDistributionGroup" 
        $DynamicDistributionGroupsCmdlet += " -Confirm:`$False"
        $DynamicDistributionGroupsCmdlet += makeparam "DisplayName" $DynamicDistributionGroup.DisplayName 
        $DynamicDistributionGroupsCmdlet += makeparam "ModeratedBy" $DynamicDistributionGroup.ModeratedBy 
        $DynamicDistributionGroupsCmdlet += makeparam "ModerationEnabled" $DynamicDistributionGroup.ModerationEnabled 
        $DynamicDistributionGroupsCmdlet += makeparam "Name" $DynamicDistributionGroup.Name 
        $DynamicDistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DynamicDistributionGroup.PrimarySmtpAddress 
        $DynamicDistributionGroupsCmdlet += makeparam "RecipientContainer" $DynamicDistributionGroup.RecipientContainer
        $RecipientFilterParam =  makeparam "RecipientFilter" $DynamicDistributionGroup.RecipientFilter
        $RecipientFilterParam = " -RecipientFilter {" + $RecipientFilterParam.Substring(19)
        $RecipientFilterParam = $RecipientFilterParam.Substring(0,$RecipientFilterParam.Length-1)
        $RecipientFilterParam += "}"
        $DynamicDistributionGroupsCmdlet +=  $RecipientFilterParam
        $DynamicDistributionGroupsCmdlet += makeparam "SendModerationNotifications" $DynamicDistributionGroup.SendModerationNotifications 
        Add-Content $outfile "`n$DynamicDistributionGroupsCmdlet"
    }
    
}else{ 
    Write-Host "No Dynamic Distribution Groups to add."
} 
#****************************************************************************
# Add Mail Contacts
#****************************************************************************
$MailContacts = Import-Clixml ".\MailContacts.xml"
$MailContactsCount = $MailContacts.Name.Count
if($MailContactsCount -gt 0){
    Write-Host "Importing $MailContactsCount Dynamic Distribution Groups"
    foreach ($MailContact in $MailContacts) {
        $MailContactsCmdlet = "New-MailContact" 
        $MailContactsCmdlet += makeparam "UsePreferMessageFormat" $MailContact.UsePreferMessageFormat
        $MailContactsCmdlet += makeparam "DisplayName" $MailContact.DisplayName
        $MailContactsCmdlet += makeparam "ModeratedBy" $MailContact.ModeratedBy
        $MailContactsCmdlet += makeparam "Name" $MailContact.Name
        $MailContactsCmdlet += makeparam "MessageBodyFormat" $MailContact.MessageBodyFormat
        $MailContactsCmdlet += makeparam "OrganizationalUnit" $MailContact.OrganizationalUnit
        $MailContactsCmdlet += makeparam "Initials" $MailContact.Initials
        $MailContactsCmdlet += makeparam "MessageFormat" $MailContact.MessageFormat
        $MailContactsCmdlet += makeparam "ModerationEnabled" $MailContact.ModerationEnabled
        $MailContactsCmdlet += makeparam "MacAttachmentFormat" $MailContact.MacAttachmentFormat
        $MailContactsCmdlet += makeparam "SendModerationNotifications" $MailContact.SendModerationNotifications
        $MailContactsCmdlet += " -Confirm:`$False"
        $MailContactsCmdlet += makeparam "ExternalEmailAddress" $MailContact.ExternalEmailAddress
        $MailContactsCmdlet += makeparam "FirstName" $MailContact.FirstName
        $MailContactsCmdlet += makeparam "Alias" $MailContact.Alias
        Add-Content $outfile "`n$MailContactsCmdlet"
    }
    
}else{ 
    Write-Host "No Mail Contacts to add."
} 

```

## <a name="step-7-add-protection-settings-to-the-target-organization"></a><span data-ttu-id="dd360-175">手順 7: 移動先の組織に保護設定を追加する</span><span class="sxs-lookup"><span data-stu-id="dd360-175">Step 7: Add protection settings to the target organization</span></span>

<span data-ttu-id="dd360-176">移動先の組織にログインしている間に、次のスクリプトを Export ディレクトリから実行することにより、以前に移動元の組織から .xml ファイルにエクスポートした設定を再作成します。</span><span class="sxs-lookup"><span data-stu-id="dd360-176">You can run the following script from the Export directory while logged in to your target organization to recreate the settings exported to .xml files earlier from the source organization.</span></span>
  
<span data-ttu-id="dd360-177">次のテキストをコピーしてメモ帳などのテキスト エディターに貼り付け、ファイルを C:\EOP\Export\Import_Settings.ps1 として保存し、次のコマンドを実行してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-177">Copy and paste the script text into a text editor like Notepad, save the file as C:\EOP\Export\Import_Settings.ps1, and run the following command:</span></span>
  
```
&amp; "C:\EOP\Export\Import_Settings.ps1"
```

<span data-ttu-id="dd360-178">このスクリプトでは, .xml ファイルをインポートして Settings.ps1 という Windows PowerShell スクリプトが作成されます。作成されたスクリプトを検討し編集してから実行し、保護とメール フローの設定を再作成してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-178">This script imports the .xml files and create a Windows PowerShell script file called Settings.ps1 that you can review, edit, and then run to recreate your protection and mail-flow settings.</span></span>
  
```
#***********************************************************************
# makeparam helper function
#****************************************************************************
 function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam       
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\Settings.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# HostedContentFilterPolicy
#****************************************************************************
$HostedContentFilterPolicys = Import-Clixml ".\HostedContentFilterPolicy.xml"
$HostedContentFilterPolicyCount = $HostedContentFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterPolicyCount Inbound Connectors"
    ForEach ($HostedContentFilterPolicy in $HostedContentFilterPolicys) {
        $HostedContentFilterPolicyCmdlet = "New-HostedContentFilterPolicy"
        if($HostedContentFilterPolicy.Name -eq "Default") {$HostedContentFilterPolicyCmdlet = "Set-HostedContentFilterPolicy -Identity Default"}
        else {
        $HostedContentFilterPolicyCmdlet += makeparam "Name" $HostedContentFilterPolicy.Name
        }
        $HostedContentFilterPolicyCmdlet += makeparam "AddXHeaderValue" $HostedContentFilterPolicy.AddXHeaderValue 
        $HostedContentFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedContentFilterPolicy.AdminDisplayName
        $HostedContentFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedContentFilterPolicyCmdlet += makeparam "DownloadLink" $HostedContentFilterPolicy.DownloadLink 
        $HostedContentFilterPolicyCmdlet += makeparam "EnableEndUserSpamNotifications" $HostedContentFilterPolicy.EnableEndUserSpamNotifications 
        $HostedContentFilterPolicyCmdlet += makeparam "EnableLanguageBlockList" $HostedContentFilterPolicy.EnableLanguageBlockList 
        $HostedContentFilterPolicyCmdlet += makeparam "EnableRegionBlockList" $HostedContentFilterPolicy.EnableRegionBlockList
        if($HostedContentFilterPolicy.EndUserSpamNotificationCustomFromAddress.Length -gt 0)
        {
            $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomFromAddress" $HostedContentFilterPolicy.EndUserSpamNotificationCustomFromAddress
        }
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomFromName" $HostedContentFilterPolicy.EndUserSpamNotificationCustomFromName 
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomSubject" $HostedContentFilterPolicy.EndUserSpamNotificationCustomSubject 
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationFrequency" $HostedContentFilterPolicy.EndUserSpamNotificationFrequency 
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationLanguage" $HostedContentFilterPolicy.EndUserSpamNotificationLanguage
        $HostedContentFilterPolicyCmdlet += makeparam "LanguageBlockList" $HostedContentFilterPolicy.LanguageBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamBulkMail" $HostedContentFilterPolicy.MarkAsSpamBulkMail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamEmbedTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamEmbedTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamEmptyMessages" $HostedContentFilterPolicy.MarkAsSpamEmptyMessages
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFormTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamFormTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFramesInHtml" $HostedContentFilterPolicy.MarkAsSpamFramesInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFromAddressAuthFail" $HostedContentFilterPolicy.MarkAsSpamFromAddressAuthFail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamJavaScriptInHtml" $HostedContentFilterPolicy.MarkAsSpamJavaScriptInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamNdrBackscatter" $HostedContentFilterPolicy.MarkAsSpamNdrBackscatter
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamObjectTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamObjectTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamSensitiveWordList" $HostedContentFilterPolicy.MarkAsSpamSensitiveWordList
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamSpfRecordHardFail" $HostedContentFilterPolicy.MarkAsSpamSpfRecordHardFail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamWebBugsInHtml" $HostedContentFilterPolicy.MarkAsSpamWebBugsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "ModifySubjectValue" $HostedContentFilterPolicy.ModifySubjectValue
        $HostedContentFilterPolicyCmdlet += makeparam "Organization" $HostedContentFilterPolicy.Organization
        $HostedContentFilterPolicyCmdlet += makeparam "QuarantineRetentionPeriod" $HostedContentFilterPolicy.QuarantineRetentionPeriod
        $HostedContentFilterPolicyCmdlet += makeparam "RedirectToRecipients" $HostedContentFilterPolicy.RedirectToRecipients
        $HostedContentFilterPolicyCmdlet += makeparam "RegionBlockList" $HostedContentFilterPolicy.RegionBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "SpamAction" $HostedContentFilterPolicy.SpamAction
        $HostedContentFilterPolicyCmdlet += makeparam "TestModeBccToRecipients" $HostedContentFilterPolicy.TestModeBccToRecipients
        Add-Content $outfile "`n$HostedContentFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Content Policy Filters to add."
 }
#****************************************************************************
# HostedContentFilterRule
#****************************************************************************
$HostedContentFilterRules = Import-Clixml ".\HostedContentFilterRule.xml"
$HostedContentFilterRuleCount = $HostedContentFilterRules.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterRuleCount Hosted Content Filter Rules"
    ForEach ($HostedContentFilterRule in $HostedContentFilterRules) {
        $HostedContentFilterRuleCmdlet = "New-HostedContentFilterRule"
        if($HostedContentFilterRule.Name -eq "Default") {$HostedContentFilterRuleCmdlet = "Set-HostedContentFilterRule Default"}
        $HostedContentFilterRuleCmdlet += makeparam "Name" $HostedContentFilterRule.Name
        $HostedContentFilterRuleCmdlet  += makeparam "HostedContentFilterPolicy" $HostedContentFilterRule.HostedContentFilterPolicy
        $HostedContentFilterRuleCmdlet += makeparam "Comments" $HostedContentFilterRule.Comments
        $HostedContentFilterRuleCmdlet += " -Confirm:`$False"
        $HostedContentFilterRuleCmdlet += makeparam "Enabled" $HostedContentFilterRule.Enabled
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfRecipientDomainIs" $HostedContentFilterRule.ExceptIfRecipientDomainIs
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfSentTo" $HostedContentFilterRule.ExceptIfSentTo
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfSentToMemberOf" $HostedContentFilterRule.ExceptIfSentToMemberOf
        $HostedContentFilterRuleCmdlet += makeparam "Priority" $HostedContentFilterRule.Priority
        $HostedContentFilterRuleCmdlet += makeparam "RecipientDomainIs" $HostedContentFilterRule.RecipientDomainIs
        $HostedContentFilterRuleCmdlet += makeparam "SentTo" $HostedContentFilterRule.SentTo
        $HostedContentFilterRuleCmdlet += makeparam "SentToMemberOf" $HostedContentFilterRule.SentToMemberOf        
        Add-Content $outfile "`n$HostedContentFilterRuleCmdlet"
    }
 }else{
    Write-Host "No Hosted Content Filter Rules to add."
 }
#****************************************************************************
# HostedOutboundSpamFilterPolicy
#****************************************************************************
$HostedOutboundSpamFilterPolicys = Import-Clixml ".\HostedOutboundSpamFilterPolicy.xml"
$HostedOutboundSpamFilterPolicyCount = $HostedOutboundSpamFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedOutboundSpamFilterPolicyCount Hosted Outbound Spam Filter Policies"
    ForEach ($HostedOutboundSpamFilterPolicy in $HostedOutboundSpamFilterPolicys) {
        $HostedOutboundSpamFilterPolicyCmdlet = "Set-HostedOutboundSpamFilterPolicy Default"
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedOutboundSpamFilterPolicy.AdminDisplayName
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "BccSuspiciousOutboundAdditionalRecipients" $HostedOutboundSpamFilterPolicy.BccSuspiciousOutboundAdditionalRecipients 
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "BccSuspiciousOutboundMail" $HostedOutboundSpamFilterPolicy.BccSuspiciousOutboundMail
        $HostedOutboundSpamFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "NotifyOutboundSpam" $HostedOutboundSpamFilterPolicy.NotifyOutboundSpam
        $NotifyOutboundSpamRecipients  += makeparam "NotifyOutboundSpamRecipients" $HostedOutboundSpamFilterPolicy.NotifyOutboundSpamRecipients
        Add-Content $outfile "`n$HostedOutboundSpamFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Outbound Spam Filter Policies to add."
 }
#****************************************************************************
# HostedConnectionFilterPolicy
#****************************************************************************
$HostedConnectionFilterPolicys = Import-Clixml ".\HostedConnectionFilterPolicy.xml"
$HostedConnectionFilterPolicyCount = $HostedConnectionFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedConnectionFilterPolicyCount Hosted Connection Filter Policies"
    ForEach ($HostedConnectionFilterPolicy in $HostedConnectionFilterPolicys) {
        $HostedConnectionFilterPolicyCmdlet = "Set-HostedConnectionFilterPolicy"
        $HostedConnectionFilterPolicyCmdlet += makeparam "Identity" $HostedConnectionFilterPolicy.Name
        $HostedConnectionFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedConnectionFilterPolicy.AdminDisplayName
        $HostedConnectionFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedConnectionFilterPolicyCmdlet += makeparam "EnableSafeList" $HostedConnectionFilterPolicy.EnableSafeList
        $HostedConnectionFilterPolicyCmdlet += makeparam "IPAllowList" $HostedConnectionFilterPolicy.IPAllowList
        $HostedConnectionFilterPolicyCmdlet += makeparam "IPBlockList" $HostedConnectionFilterPolicy.IPBlockList
        
        Add-Content $outfile "`n$HostedConnectionFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Connection Filter Policies to add."
 }
#****************************************************************************
# MalwareFilterPolicy
#****************************************************************************
$MalwareFilterPolicys = Import-Clixml ".\MalwareFilterPolicy.xml"
$MalwareFilterPolicyCount = $MalwareFilterPolicys.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterPolicyCount Malware Filter Policies"
    ForEach ($MalwareFilterPolicy in $MalwareFilterPolicys) {
        $MalwareFilterPolicyCmdlet = "New-MalwareFilterPolicy"
        if($MalwareFilterPolicy.Name -eq "Default") {$MalwareFilterPolicyCmdlet = "Set-MalwareFilterPolicy Default"}
        else {
        $MalwareFilterPolicyCmdlet += makeparam "Name" $MalwareFilterPolicy.Name
        }
        $MalwareFilterPolicyCmdlet += makeparam "Action" $MalwareFilterPolicy.Action
        $MalwareFilterPolicyCmdlet += makeparam "DeleteAttachmentAndUseDefaultAlertText" $MalwareFilterPolicy.DeleteAttachmentAndUseDefaultAlertText
        $MalwareFilterPolicyCmdlet += makeparam "DeleteAttachmentAndUseCustomAlertText" $MalwareFilterPolicy.DeleteAttachmentAndUseCustomAlertText
        $MalwareFilterPolicyCmdlet += makeparam "AdminDisplayName" $MalwareFilterPolicy.AdminDisplayName
        $MalwareFilterPolicyCmdlet += " -Confirm:`$False"
        $MalwareFilterPolicyCmdlet += makeparam "CustomAlertText" $MalwareFilterPolicy.CustomAlertText
        $MalwareFilterPolicyCmdlet += makeparam "CustomExternalBody" $MalwareFilterPolicy.CustomExternalBody
        $MalwareFilterPolicyCmdlet += makeparam "CustomExternalSubject" $MalwareFilterPolicy.CustomExternalSubject
        if($MalwareFilterPolicy.CustomFromAddress.Length -gt 0) {
            $MalwareFilterPolicyCmdlet += makeparam "CustomFromAddress" $MalwareFilterPolicy.CustomFromAddress
        }
        $MalwareFilterPolicyCmdlet += makeparam "CustomFromName" $MalwareFilterPolicy.CustomFromName
        $MalwareFilterPolicyCmdlet += makeparam "CustomInternalBody" $MalwareFilterPolicy.CustomInternalBody
        $MalwareFilterPolicyCmdlet += makeparam "CustomInternalSubject" $MalwareFilterPolicy.CustomInternalSubject
        $MalwareFilterPolicyCmdlet += makeparam "CustomNotifications" $MalwareFilterPolicy.CustomNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableExternalSenderAdminNotifications" $MalwareFilterPolicy.EnableExternalSenderAdminNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableExternalSenderNotifications" $MalwareFilterPolicy.EnableExternalSenderNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableInternalSenderAdminNotifications" $MalwareFilterPolicy.EnableInternalSenderAdminNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableInternalSenderNotifications" $MalwareFilterPolicy.EnableInternalSenderNotifications
        if($MalwareFilterPolicy.ExternalSenderAdminAddress.Length -gt 0) {
        $MalwareFilterPolicyCmdlet += makeparam "ExternalSenderAdminAddress" $MalwareFilterPolicy.ExternalSenderAdminAddress
        }
        if($MalwareFilterPolicy.InternalSenderAdminAddress.Length -gt 0) {
        $MalwareFilterPolicyCmdlet += makeparam "InternalSenderAdminAddress" $MalwareFilterPolicy.InternalSenderAdminAddress
        }
        Add-Content $outfile "`n$MalwareFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Malware Filter Policies to add."
 }
#****************************************************************************
# MalwareFilterRule
#****************************************************************************
$MalwareFilterRules = Import-Clixml ".\MalwareFilterRule.xml"
$MalwareFilterRuleCount = $MalwareFilterRules.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterRuleCount Malware Filter Rules"
    ForEach ($MalwareFilterRule in $MalwareFilterRules) {
        $MalwareFilterRuleCmdlet = "New-MalwareFilterRule"
        if($MalwareFilterRule.Name -eq "Default") {$MalwareFilterRuleCmdlet = "Set-MalwareFilterPolicy Default"}
        $MalwareFilterRuleCmdlet += makeparam "Name" $MalwareFilterRule.Name
        $MalwareFilterRuleCmdlet += makeparam "MalwareFilterPolicy" $MalwareFilterRule.MalwareFilterPolicy
        $MalwareFilterRuleCmdlet += makeparam "Comments" $MalwareFilterRule.Comments
        $MalwareFilterRuleCmdlet += " -Confirm:`$False"
        $MalwareFilterRuleCmdlet += makeparam "Enabled" $MalwareFilterRule.Enabled
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfRecipientDomainIs" $MalwareFilterRule.ExceptIfRecipientDomainIs
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfSentTo" $MalwareFilterRule.ExceptIfSentTo
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfSentToMemberOf" $MalwareFilterRule.ExceptIfSentToMemberOf
        $MalwareFilterRuleCmdlet += makeparam "RecipientDomainIs" $MalwareFilterRule.RecipientDomainIs
        $MalwareFilterRuleCmdlet += makeparam "SentTo" $MalwareFilterRule.SentTo
        $MalwareFilterRuleCmdlet += makeparam "SentToMemberOf" $MalwareFilterRule.SentToMemberOf       
        Add-Content $outfile "`n$MalwareFilterRuleCmdlet"
    }
 }else{
    Write-Host "No Malware Filter Rules to add."
 }
#****************************************************************************
# InboundConnectors
#****************************************************************************
$InboundConnectors = Import-Clixml ".\InboundConnector.xml"
$InboundConnectorCount = $InboundConnectors.Name.Count
if($InboundConnectorCount -gt 0){
    Write-Host "Importing $InboundConnectorCount Inbound Connectors"
    ForEach ($InboundConnector in $InboundConnectors) {
        $InboundConnectorCmdlet = "New-InboundConnector"
        $InboundConnectorCmdlet += makeparam "Name" $InboundConnector.Name
        $InboundConnectorCmdlet += makeparam "SenderDomains" $InboundConnector.SenderDomains
        
        If($InboundConnector.AssociatedAcceptedDomains.Count -gt 0) {
            If($InboundConnector.AssociatedAcceptedDomains[0].Contains("/")) {
                # This connector was created in an EOP Standard tenant
                # Strip out just the domain name
                $InboundConnectorCmdlet += " -AssociatedAcceptedDomains "
                ForEach  ($accepteddomain in $InboundConnectors.AssociatedAcceptedDomains) {
                    $accepteddomain = $accepteddomain.SubString($accepteddomain.LastIndexOf("/")+1)
                    $InboundConnectorCmdlet += "`"$accepteddomain`","
                }
                $InboundConnectorCmdlet = $InboundConnectorCmdlet.TrimEnd(",")
            }else{
                $InboundConnectorCmdlet += makeparam "AssociatedAcceptedDomains" $InboundConnector.AssociatedAcceptedDomains
            }
        }
        
        $InboundConnectorCmdlet += makeparam "CloudServicesMailEnabled" $InboundConnector.CloudServicesMailEnabled 
        $InboundConnectorCmdlet += makeparam "Comment" $InboundConnector.Comment 
        $InboundConnectorCmdlet += " -Confirm:`$False"
        $InboundConnectorCmdlet += makeparam "ConnectorSource" $InboundConnector.ConnectorSource
        $InboundConnectorCmdlet += makeparam "ConnectorType" $InboundConnector.ConnectorType
        $InboundConnectorCmdlet += makeparam "Enabled" $InboundConnector.Enabled
        $InboundConnectorCmdlet += makeparam "RequireTls" $InboundConnector.RequireTls 
        $InboundConnectorCmdlet += makeparam "RestrictDomainsToCertificate" $InboundConnector.RestrictDomainsToCertificate
        $InboundConnectorCmdlet += makeparam "RestrictDomainsToIPAddresses" $InboundConnector.RestrictDomainsToIPAddresses
        $InboundConnectorCmdlet += makeparam "SenderIPAddresses" $InboundConnector.SenderIPAddresses
        $InboundConnectorCmdlet += makeparam "TlsSenderCertificateName" $InboundConnector.TlsSenderCertificateName
        Add-Content $outfile "`n$InboundConnectorCmdlet"
     }
}else{
    Write-Host "No Inbound Connectors to add."
 }
#****************************************************************************
# OutboundConnector
#****************************************************************************
$OutboundConnectors = Import-Clixml ".\OutboundConnector.xml"
$OutboundConnectorCount = $OutboundConnectors.Name.Count
if($OutboundConnectorCount -gt 0){
    Write-Host "Importing $OutboundConnectorCount Outbound Connectors"
    ForEach ($OutboundConnector in $OutboundConnectors) {
        $OutboundConnectorCmdlet = "New-OutboundConnector"
        $OutboundConnectorCmdlet += makeparam "Name" $OutboundConnector.Name
        $OutboundConnectorCmdlet += makeparam "AllAcceptedDomains" $OutboundConnector.AllAcceptedDomains
        $OutboundConnectorCmdlet += makeparam "BypassValidation" $OutboundConnector.BypassValidation
        $OutboundConnectorCmdlet += makeparam "CloudServicesMailEnabled" $OutboundConnector.CloudServicesMailEnabled
        $OutboundConnectorCmdlet += makeparam "Comment" $OutboundConnector.Comment
        $OutboundConnectorCmdlet += " -Confirm:`$False"
        $OutboundConnectorCmdlet += makeparam "ConnectorSource" $OutboundConnector.ConnectorSource
        $OutboundConnectorCmdlet += makeparam "ConnectorType" $OutboundConnector.ConnectorType
        $OutboundConnectorCmdlet += makeparam "IsTransportRuleScoped" $OutboundConnector.IsTransportRuleScoped
        $OutboundConnectorCmdlet += makeparam "RecipientDomains" $OutboundConnector.RecipientDomains
        $OutboundConnectorCmdlet += makeparam "RouteAllMessagesViaOnPremises" $OutboundConnector.RouteAllMessagesViaOnPremises
        $OutboundConnectorCmdlet += makeparam "SmartHosts" $OutboundConnector.SmartHosts
        $OutboundConnectorCmdlet += makeparam "TlsDomain" $OutboundConnector.TlsDomain
        $OutboundConnectorCmdlet += makeparam "TlsSettings" $OutboundConnector.TlsSettings
        $OutboundConnectorCmdlet += makeparam "UseMXRecord" $OutboundConnector.UseMXRecord
        Add-Content $outfile "`n$OutboundConnectorCmdlet"
    }
 }else{
    Write-Host "No Outbound Connectors to add."
 }
#*****************************************************************************
# TransportRule
#*****************************************************************************
Add-Content $outfile "`n[Byte[]]$Data = Get-Content -Path `".TransportRules.xml`" -Encoding Byte -ReadCount 0"
Add-Content $outfile "`nImport-TransportRuleCollection -FileData $Data"
#****************************************************************************
# Domain Type
#****************************************************************************
$Domains = Import-Clixml ".\Domains.xml"
$DomainCount = $Domains.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $DomainCount Domains"
    ForEach ($Domain in $Domains) {
        $DomainCmdlet = "Set-AcceptedDomain"
        $DomainCmdlet += makeparam "Identity" $Domain.Name
        $DomainCmdlet += makeparam "DomainType" $Domain.DomainType
        Add-Content $outfile "`n$DomainCmdlet"
    }
 }else{
    Write-Host "No Domains to add."
 } 
 
```

## <a name="step-8-revert-your-dns-settings-to-stop-mail-queuing"></a><span data-ttu-id="dd360-179">手順 8: DNS 設定を元に戻し、メールをキューに格納する処置を停止する</span><span class="sxs-lookup"><span data-stu-id="dd360-179">Step 8: Revert your DNS settings to stop mail queuing</span></span>

<span data-ttu-id="dd360-p117">移行中に送信者がメールをキューに格納するようにするために MX レコードに無効なアドレスを設定した場合は、その設定を、[Office 365 管理センター](https://portal.office.com) で指定した正しい値に戻す必要があります。DNS の構成の詳細については、「 [Office 365 の DNS レコードを作成する](https://go.microsoft.com/fwlink/p/?LinkId=304219)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd360-p117">If you chose to set your MX records to an invalid address to cause the senders to queue mail during your transition, you'll need to set them back to the correct value as specified in the [Office 365 admin center](https://portal.office.com). For more information about configuring DNS, see [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).</span></span>
  

