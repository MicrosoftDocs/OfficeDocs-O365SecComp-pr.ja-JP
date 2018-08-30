---
title: Office 365 Message Encryption 用に Azure Rights Management を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 'Office 365 のメッセージの暗号化は、Microsoft Azure アクセス権の管理 (以前は Windows Azure Active Directory の権限の管理と呼ばれます) によって異なります。 '
ms.openlocfilehash: 99c8de49330cf99545d28d81e0c99c2138797356
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532199"
---
# <a name="set-up-azure-rights-management-for-office-365-message-encryption"></a><span data-ttu-id="be93b-103">Office 365 Message Encryption 用に Azure Rights Management を設定する</span><span class="sxs-lookup"><span data-stu-id="be93b-103">Set up Azure Rights Management for Office 365 Message Encryption</span></span>

<span data-ttu-id="be93b-104">アクティブにしを Azure の権限の管理 (RMS)、Office 365 メッセージの暗号化 (ホーム) を使用して、Azure の情報保護の部分を設定するために以下の必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="be93b-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with Office 365 Message Encryption (OME).</span></span>
  
## <a name="prerequisites-for-using-office-365-message-encryption"></a><span data-ttu-id="be93b-105">Office 365 Message Encryption を使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="be93b-105">Prerequisites for using Office 365 Message Encryption</span></span>
<span data-ttu-id="be93b-106"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="be93b-106"></span></span>

<span data-ttu-id="be93b-p101">Office 365 メッセージの暗号化 (ホーム)、IRM を含むは、Azure アクセス権管理 (Azure RMS) によって異なります。Azure の RMS は、情報保護の Azure で使用される保護技術です。ホームを使用するには、Office 365 の組織は、著作権管理の Azure サブスクリプションが含まれますが、オンライン Exchange または Exchange のオンライン保護のサブスクリプションを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="be93b-p101">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS). Azure RMS is the protection technology used by Azure Information Protection. To use OME, your Office 365 organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="be93b-110">お申し込みの内容のことを確認していない場合は、[メッセージのポリシー、リカバリ、コンプライアンス](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)に関する Exchange Online のサービスの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be93b-110">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>
    
- <span data-ttu-id="be93b-111">RMS の Azure サブスクリプションのオンラインの Exchange または Exchange のオンライン保護をお持ちでない場合は、サブスクリプションを購入および最初に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be93b-111">If you don't have an Azure RMS subscription for Exchange Online or Exchange Online Protection, you must purchase a subscription and activate it first.</span></span>
    
    <span data-ttu-id="be93b-p102">Azure アクセス権の管理へのサブスクリプションの購入方法の詳細については、 [Azure アクセス権の管理](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT)を参照してください。次のセクションでは、Azure の権限管理のアクティブ化についての情報を示します。</span><span class="sxs-lookup"><span data-stu-id="be93b-p102">For information about purchasing a subscription to Azure Rights Management, see [Azure Rights Management](https://portal.office.com/Signup/MainSignUp15.aspx?&amp;OfferId=9DF77AF9-DAAE-4d51-8E0E-EEEADD4866B8&amp;dl=RIGHTSMANAGEMENT). The next section gives you information about activating Azure Rights Management.</span></span>
    
- <span data-ttu-id="be93b-114">Azure アクセス権の管理を有効にする方法について説明 Azure アクセス権の管理がある場合は、Exchange Online または Exchange のオンライン保護設定されていないし、Azure アクセス権の管理に使用するホームを設定する最善の方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="be93b-114">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>
    
- <span data-ttu-id="be93b-p103">既に設定したホームで使用する Azure アクセス権管理オンライン Exchange または Exchange のオンライン保護を設定する方法によって場合は、ホームおよびその新機能をすぐに使用を開始する準備が完了する必要があります。この資料では、かどうかしたホームを正しくセットアップすることを確認する方法、設定を変更する必要がある場合の対処方法と、設定を変更しないように選択する場合の対処について説明します。などの新機能を使用するためには、ホームで Azure RMS を使用する必要があります。オンプレミス Active ディレクトリ RMS では、新しい機能を使用できません。</span><span class="sxs-lookup"><span data-stu-id="be93b-p103">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away. This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup. For example, in order to use the new capabilities, you must use Azure RMS with OME. You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>
    
## <a name="activate-azure-rights-management-for-ome-in-office-365"></a><span data-ttu-id="be93b-119">Office 365 でホームの Azure の著作権管理を有効化します。</span><span class="sxs-lookup"><span data-stu-id="be93b-119">Activate Azure Rights Management for OME in Office 365</span></span>
<span data-ttu-id="be93b-120"><a name="activatewarm"> </a></span><span class="sxs-lookup"><span data-stu-id="be93b-120"></span></span>

<span data-ttu-id="be93b-p104">Azure アクセス権の管理を有効に、組織内のユーザーがメッセージを送信すると、情報の保護を適用し、メッセージと Azure の権利管理サービスによって保護されているファイルを開くようにする必要があります。手順については、 [Azure アクセス権の管理をアクティブにする](https://go.microsoft.com/fwlink/p/?LinkId=525775)を参照してください。ライセンス認証の手続きが完了したら、ここを返し、この資料内のタスクを続行します。</span><span class="sxs-lookup"><span data-stu-id="be93b-p104">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service. For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="be93b-124">信頼された発行ドメイン (TPDs) をインポートすると、Azure の RMS を使用するホームを設定します。</span><span class="sxs-lookup"><span data-stu-id="be93b-124">Set up OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>
<span data-ttu-id="be93b-125"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="be93b-125"></span></span>

<span data-ttu-id="be93b-p105">TPD は、組織の権限の管理の設定に関する情報を含む XML ファイルです。など、TPD には、署名と証明書とライセンスの暗号化に使用されるサーバー ライセンサー証明書 (SLC) に関する情報が含まれている、Url のライセンスおよび発行を使用しています。Office 365 の組織に、TPD をインポートするには、Windows PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="be93b-p105">A TPD is an XML file that contains information about your organization's rights management settings. For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on. You import the TPD into your Office 365 organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="be93b-p106">以前は、Active Directory の権限管理サービス (AD RMS) から TPDs を Office 365 の組織にインポートすることもできます。ただし、これを行う新しいホーム機能を使用するを防止する、お勧めできません。組織は、現在、Office 365 では、このような方法を構成する場合は、オンプレミスの Active ディレクトリ RMS から Azure クラウド ・ ベース情報の保護に移行する計画を作成することをお勧めします。詳細については、 [Azure の情報保護に AD RMS からの移行](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)を参照してください。Azure の情報保護への移行が完了するまでは、ホームの新機能を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="be93b-p106">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your Office 365 organization. However, doing so will prevent you from using the new OME capabilities and is not recommended. If your Office 365 organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection. For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span> 
  
 <span data-ttu-id="be93b-134">**TPDs を Azure の RMS からインポートするのには**</span><span class="sxs-lookup"><span data-stu-id="be93b-134">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="be93b-135">[オンライン リモート PowerShell を使用して Exchange に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="be93b-135">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="be93b-136">Office 365 組織の地理的な場所に対応するキーの共有 URL を選択します。</span><span class="sxs-lookup"><span data-stu-id="be93b-136">Choose the key-sharing URL that corresponds to your Office 365 organization's geographic location:</span></span>
    
|<span data-ttu-id="be93b-137">**場所**</span><span class="sxs-lookup"><span data-stu-id="be93b-137">**Location**</span></span>|<span data-ttu-id="be93b-138">**キーの場所の URL を共有します。**</span><span class="sxs-lookup"><span data-stu-id="be93b-138">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be93b-139">北アメリカ</span><span class="sxs-lookup"><span data-stu-id="be93b-139">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="be93b-140">欧州連合</span><span class="sxs-lookup"><span data-stu-id="be93b-140">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="be93b-141">アジア</span><span class="sxs-lookup"><span data-stu-id="be93b-141">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="be93b-142">南アメリカ</span><span class="sxs-lookup"><span data-stu-id="be93b-142">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="be93b-143">行政機関向け Office 365 (行政機関のコミュニティ クラウド)</span><span class="sxs-lookup"><span data-stu-id="be93b-143">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="be93b-144">この RMS キーを共有の場所は、政府の Sku の Office 365 が購入されたお客様に予約されています。</span><span class="sxs-lookup"><span data-stu-id="be93b-144">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
   
3. <span data-ttu-id="be93b-145">次のように[セット IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx)コマンドレットを実行してキーを共有の場所を構成します。</span><span class="sxs-lookup"><span data-stu-id="be93b-145">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
  ```

    <span data-ttu-id="be93b-146">たとえば、北米では、組織がある場合、場所を共有キーを構成するとします。</span><span class="sxs-lookup"><span data-stu-id="be93b-146">For example, to configure the key sharing location if your organization is located in North America:</span></span>
    
  ```
  Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
  ```

4. <span data-ttu-id="be93b-147">Azure アクセス権の管理から、TPD をインポートするのには-RMSOnline スイッチを使用して[インポート RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be93b-147">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 
    
  ```
  Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
  ```

    <span data-ttu-id="be93b-p107">*TPDName*は、名前、TPD を使用します。たとえば、「Contoso 北米 TPD」。</span><span class="sxs-lookup"><span data-stu-id="be93b-p107">Where  *TPDName*  is the name you want to use for the TPD. For example, "Contoso North American TPD".</span></span> 
    
5. <span data-ttu-id="be93b-150">Azure の権限の管理サービスを使用する Office 365 の組織が正常に構成されていることを確認するには、次のように-RMSOnline スイッチを使用して[テスト IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be93b-150">To verify that you successfully configured your Office 365 organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span> 
    
  ```
  Test-IRMConfiguration -RMSOnline
  ```

    <span data-ttu-id="be93b-151">などでは、このコマンドレット Azure の権限の管理サービスとの接続を確認、TPD をダウンロード、その有効性を確認します。</span><span class="sxs-lookup"><span data-stu-id="be93b-151">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>
    
6. <span data-ttu-id="be93b-152">Outlook と web 上の Outlook で使用できなくなっている Azure アクセス権の管理テンプレートを無効にするには、次のように[セット IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be93b-152">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 
    
  ```
  Set-IRMConfiguration -ClientAccessServerEnabled $false
  ```

7. <span data-ttu-id="be93b-153">クラウド ベースの電子メール組織の Azure アクセス権の管理を有効にして、Azure のアクセス権の管理を使用して、Office 365 のメッセージの暗号化を構成する次のように[セット IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="be93b-153">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span> 
    
  ```
  Set-IRMConfiguration -InternalLicensingEnabled $true
  ```

8. <span data-ttu-id="be93b-p108">正常に、TPD をインポートしている Azure アクセス権の管理を有効になっていることを確認するには、Azure の著作権管理の機能をテストするのには、テスト IRMConfiguration コマンドレットを使用します。詳細については、[テスト ・ IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)の「例 1」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be93b-p108">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality. For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>
    
## <a name="i-have-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="be93b-156">ホームが Active Directory の権限管理 Azure の情報保護しないと設定があると、行うことは何ですか?</span><span class="sxs-lookup"><span data-stu-id="be93b-156">I have OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="be93b-157"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="be93b-157"></span></span>

<span data-ttu-id="be93b-p109">Active Directory の権限管理で、既存の Office 365 のメッセージの暗号化メール フロー ルールを使用する続行することができますが、構成またはホームの新機能を使用することはできません。代わりに、情報の保護を Azure に移行する必要があります。移行し、これにより、組織の詳細については、 [Azure の情報保護に AD RMS からの移行](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be93b-p109">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities. Instead, you need to migrate to Azure Information Protection. For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="be93b-161">次の手順</span><span class="sxs-lookup"><span data-stu-id="be93b-161">Next steps</span></span>
<span data-ttu-id="be93b-162"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="be93b-162"></span></span>

<span data-ttu-id="be93b-163">ホームの新機能を有効にするを参照してくださいする場合は Azure アクセス権の管理のセットアップが完了したら[情報の保護を Azure 上に構築された、新しい Office 365 のメッセージの暗号化機能を設定します](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)。</span><span class="sxs-lookup"><span data-stu-id="be93b-163">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e)</span></span>
  
<span data-ttu-id="be93b-164">ホームの新機能を使用する組織を設定したら後、は、[ホームの新機能を持つ電子メール メッセージを保護するためにメール フロー ルールを定義](define-mail-flow-rules-to-encrypt-email.md)する準備が整ったら。</span><span class="sxs-lookup"><span data-stu-id="be93b-164">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="be93b-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="be93b-165">Related topics</span></span>
<span data-ttu-id="be93b-166"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="be93b-166"></span></span>

[<span data-ttu-id="be93b-167">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="be93b-167">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="be93b-168">Office 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="be93b-168">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="be93b-169">Azure アクセス権の管理とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="be93b-169">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
  

