---
title: 既存の Office 365 テナントにロールアウトされる Azure Information Protection の保護機能
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
description: 情報を保護するための最初の手順を説明するために、2018年7月に、Azure Information Protection の対象となるすべてのテナントに、Azure Information protection の保護機能が既定で有効になります。 以前は Office 365 では、Azure Information Protection の保護機能が Rights Management または Azure RMS と呼ばれていました。 組織に Office E3 service プランまたはより高いサービスプランがある場合は、これらの機能をロールアウトする際に、Azure Information Protection を使用して情報の保護を開始することになります。
ms.openlocfilehash: f7c5126ddf1a15dde147e724ceced34d95eef185
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34152229"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-office-365-tenants"></a><span data-ttu-id="e9e3b-105">既存の Office 365 テナントにロールアウトされる Azure Information Protection の保護機能</span><span class="sxs-lookup"><span data-stu-id="e9e3b-105">Protection features in Azure Information Protection rolling out to existing Office 365 tenants</span></span>

<span data-ttu-id="e9e3b-106">情報を保護するための最初の手順を説明するために、2018年7月に、Azure Information Protection の対象となるすべてのテナントに、Azure Information protection の保護機能が既定で有効になります。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-106">To help with the initial step in protecting your information, starting July 2018 all Azure Information Protection eligible tenants will have the protection features in Azure Information Protection turned on by default.</span></span> <span data-ttu-id="e9e3b-107">以前は Office 365 では、Azure Information Protection の保護機能が Rights Management または Azure RMS と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-107">The protection features in Azure Information Protection were formerly known in Office 365 as Rights Management or Azure RMS.</span></span> <span data-ttu-id="e9e3b-108">組織に Office E3 service プランまたはより高いサービスプランがある場合は、これらの機能をロールアウトする際に、Azure Information Protection を使用して情報の保護を開始することになります。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-108">If your organization has an Office E3 service plan or a higher service plan you will now get a head start protecting information through Azure Information Protection when we roll out these features.</span></span>
  
## <a name="changes-beginning-july-1-2018"></a><span data-ttu-id="e9e3b-109">2018年7月1日以降の変更</span><span class="sxs-lookup"><span data-stu-id="e9e3b-109">Changes beginning July 1, 2018</span></span>

<span data-ttu-id="e9e3b-110">2018年7月1日以降、次のいずれかのサブスクリプションプランを所有しているすべての Office 365 テナントに対して、Azure Information Protection の保護機能が有効になります。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-110">Starting July 1, 2018, Microsoft will enable the protection capability in Azure Information Protection for all Office 365 tenants who have one of the following subscription plans:</span></span>
  
- <span data-ttu-id="e9e3b-111">Office 365 メッセージの暗号化は、Office 365 E3 および E5 の一部として提供されます。 Microsoft E3 and E5、Office 365 A1、A3、A5、および Office 365 G3 および G5。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-111">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5.</span></span> <span data-ttu-id="e9e3b-112">Azure Information Protection によって提供される新しい保護機能を利用するには、追加のライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-112">You do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span> 
    
- <span data-ttu-id="e9e3b-113">また、次のプランに Azure Information Protection Plan 1 を追加して、新しい Office 365 メッセージの暗号化機能を受け取ることができます。 Exchange Online プラン1、Exchange Online プラン2、Office 365 F1、Office 365 Business Essentials、Office 365 Business Premium、またはOffice 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e9e3b-113">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Office 365 Business Essentials, Office 365 Business Premium, or Office 365 Enterprise E1.</span></span>
    
- <span data-ttu-id="e9e3b-114">Office 365 の各ユーザー利点を活用するには、この機能の対象となるライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-114">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>
    
- <span data-ttu-id="e9e3b-115">完全なリストについては、「 [Exchange Online サービスの説明](https://technet.microsoft.com/library/exchange-online-service-description.aspx)」の「Office 365 Message Encryption」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-115">For the full list see the [Exchange Online service descriptions](https://technet.microsoft.com/library/exchange-online-service-description.aspx) for Office 365 Message Encryption.</span></span> 
    
<span data-ttu-id="e9e3b-116">テナント管理者は、Office 365 管理者ポータルで保護の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-116">Tenant administrators can check the protection status in the Office 365 administrator portal.</span></span> 
  
![Office 365 の権限管理がアクティブ化されたことを示すスクリーンショット。](media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)
  
## <a name="why-are-we-making-this-change"></a><span data-ttu-id="e9e3b-118">この変更を行う理由</span><span class="sxs-lookup"><span data-stu-id="e9e3b-118">Why are we making this change?</span></span>

<span data-ttu-id="e9e3b-119">Office 365 Message Encryption では、Azure Information Protection の保護機能を活用しています。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-119">Office 365 Message Encryption leverages the protection capabilities in Azure Information Protection.</span></span> <span data-ttu-id="e9e3b-120">最近の Office 365 メッセージ暗号化の機能強化と、Microsoft 365 における情報保護への幅広い投資に加えて、組織では、以前のように保護機能を有効にして使用することが容易になりました。暗号化テクノロジはセットアップが困難です。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-120">At the heart of the recent improvements to Office 365 Message Encryption and our broader investments to information protection in Microsoft 365, we are making it easier for organizations to turn on and use our protection capabilities, as historically, encryption technologies have been difficult to set up.</span></span> <span data-ttu-id="e9e3b-121">Azure Information Protection の保護機能を既定で有効にすることにより、機密データの保護をすばやく始めることができます。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-121">By turning on the protection features in Azure Information Protection by default, you can quickly get started to protect your sensitive data.</span></span>
  
## <a name="does-this-impact-me"></a><span data-ttu-id="e9e3b-122">影響はありますか?</span><span class="sxs-lookup"><span data-stu-id="e9e3b-122">Does this impact me?</span></span>

<span data-ttu-id="e9e3b-123">Office 365 組織が適格な Office 365 ライセンスを購入している場合、テナントはこの変更によって影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-123">If your Office 365 organization has purchased an eligible Office 365 license, then your tenant will be impacted by this change.</span></span>
  
 <span data-ttu-id="e9e3b-124">**大事な！**</span><span class="sxs-lookup"><span data-stu-id="e9e3b-124">**IMPORTANT!**</span></span> <span data-ttu-id="e9e3b-125">オンプレミス環境で Active Directory Rights Management サービス (AD RMS) を使用している場合は、この変更をすぐにオプトアウトするか、または Azure Information Protection に移行してから、今後30日間以内にこの変更を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-125">If you're using Active Directory Rights Management Services (AD RMS) in your on-premises environment, you must either opt-out of this change immediately or migrate to Azure Information Protection before we roll out this change within the next 30 days.</span></span> <span data-ttu-id="e9e3b-126">オプトアウトの詳細については、「AD RMS を使用して、どのようにオプトアウトしますか?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-126">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="e9e3b-127">」で説明する手順に従ってローカライズされたファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-127">later in this article.</span></span> <span data-ttu-id="e9e3b-128">移行を希望する場合は、「 [AD RMS から Azure Information Protection への移行](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-128">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>
  
## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a><span data-ttu-id="e9e3b-129">Active Directory Rights Management サービス (AD RMS) で Azure Information Protection を使用できますか?</span><span class="sxs-lookup"><span data-stu-id="e9e3b-129">Can I use Azure Information Protection with Active Directory Rights Management Services (AD RMS)?</span></span>

<span data-ttu-id="e9e3b-130">いいえ。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-130">No.</span></span> <span data-ttu-id="e9e3b-131">これは、サポートされている展開シナリオではありません。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-131">This is not a supported deployment scenario.</span></span> <span data-ttu-id="e9e3b-132">追加の脱退手順を行わないと、一部のコンピューターでは、Azure Rights Management サービスの使用が自動的に開始され、AD RMS クラスターにも接続される場合があります。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-132">Without taking the additional opt-out steps, some computers might automatically start using the Azure Rights Management service and also connect to your AD RMS cluster.</span></span> <span data-ttu-id="e9e3b-133">このシナリオはサポートされておらず、信頼できない結果があるため、これらの新機能を展開する前に、今後30日以内にこの変更を行わないことが重要です。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-133">This scenario isn't supported and has unreliable results, so it's important that you opt out of this change within the next 30 days before we roll out these new features.</span></span> <span data-ttu-id="e9e3b-134">オプトアウトの詳細については、「AD RMS を使用して、どのようにオプトアウトしますか?」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-134">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="e9e3b-135">」で説明する手順に従ってローカライズされたファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-135">later in this article.</span></span> <span data-ttu-id="e9e3b-136">移行を希望する場合は、「 [AD RMS から Azure Information Protection への移行](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-136">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>
  
## <a name="how-do-i-know-if-im-using-ad-rms"></a><span data-ttu-id="e9e3b-137">AD RMS を使用しているかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="e9e3b-137">How do I know if I'm using AD RMS?</span></span>

<span data-ttu-id="e9e3b-138">[Active Directory Rights Management サービス (AD rms)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms)を使用して ad rms が展開されているかどうかを確認するときは、次の手順を使用して Azure Rights management の環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-138">Use these instructions from [Preparing the environment for Azure Rights Management when you also have Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) to check if you have deployed AD RMS:</span></span> 
  
1. <span data-ttu-id="e9e3b-139">ほとんどの AD RMS 展開はオプションですが、ドメインコンピューターが AD RMS クラスターを検出できるように、サービス接続ポイント (SCP) を Active Directory に公開します。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-139">Although optional, most AD RMS deployments publish the service connection point (SCP) to Active Directory so that domain computers can discover the AD RMS cluster.</span></span> 
  
<span data-ttu-id="e9e3b-140">ADSI Edit を使用して、Active Directory で発行された SCP があるかどうかを確認します。 CN = Configuration [サーバー名], CN = Services, CN = RightsManagementServices, CN = SCP</span><span class="sxs-lookup"><span data-stu-id="e9e3b-140">Use ADSI Edit to see whether you have an SCP published in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span></span>
    
2. <span data-ttu-id="e9e3b-141">SCP を使用していない場合は、AD RMS クラスターに接続する Windows コンピューターを、Windows レジストリ: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation または HKEY_ を使用して、クライアント側サービスの検出またはライセンスのリダイレクト用に構成する必要があります。LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation</span><span class="sxs-lookup"><span data-stu-id="e9e3b-141">If you are not using an SCP, Windows computers that connect to an AD RMS cluster must be configured for client-side service discovery or licensing redirection by using the Windows registry: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation</span></span> 
  
<span data-ttu-id="e9e3b-142">これらのレジストリ構成の詳細については、「 [Windows レジストリを使用して](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry)[ライセンスサーバーのトラフィックをリダイレクト](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-142">For more information about these registry configurations, see [Enabling client-side service discovery by using the Windows registry](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).</span></span>
    
## <a name="i-use-ad-rms-how-do-i-opt-out"></a><span data-ttu-id="e9e3b-143">AD RMS を使用していますが、どのようにオプトアウトすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="e9e3b-143">I use AD RMS, how do I opt out?</span></span>

<span data-ttu-id="e9e3b-144">今後の変更を中止するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-144">To opt out of the upcoming change, complete these steps:</span></span>
  
1. <span data-ttu-id="e9e3b-145">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell セッションを開始し、Exchange Online に接続します。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-145">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="e9e3b-146">手順については、「 [Exchange Online PowerShell への接続](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-146">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
    
2. <span data-ttu-id="e9e3b-147">次の構文を使用して、Set-IRMConfiguration コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-147">Run the Set-IRMConfiguration cmdlet using the following syntax:</span></span>
    
  ```
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false 
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a><span data-ttu-id="e9e3b-148">この変更を行った後に予想されることは何ですか。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-148">What can I expect after this change has been made?</span></span>

<span data-ttu-id="e9e3b-149">これを有効にしていない場合は、 [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801)で発表された新しいバージョンの Office 365 Message Encryption の使用を開始して、Azure 情報の暗号化および保護機能を活用することができます。保護.</span><span class="sxs-lookup"><span data-stu-id="e9e3b-149">Once this is enabled, provided you haven't opted out, you can start using the new version of Office 365 Message Encryption which was announced at [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) and leverages the encryption and protection capabilities of Azure Information Protection.</span></span> 
  
![Web 上の Outlook で OME 保護されたメッセージを示すスクリーンショット。](media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)
  
<span data-ttu-id="e9e3b-151">新しい機能の詳細については、「 [Office 365 Message Encryption](ome.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e9e3b-151">For more information about the new enhancements, see [Office 365 Message Encryption](ome.md).</span></span>
  

