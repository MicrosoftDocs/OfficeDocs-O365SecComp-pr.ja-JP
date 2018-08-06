---
title: オンプレミスの AD RMS サーバーを使用するように IRM を構成する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
ms.audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
description: このトピックでは、AD RMS サーバーを使用するように IRM を構成する方法を示します。
ms.openlocfilehash: 198d7b86b39318361a174395bc460b4a4bd35847
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027374"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a><span data-ttu-id="053a2-103">オンプレミスの AD RMS サーバーを使用するように IRM を構成する</span><span class="sxs-lookup"><span data-stu-id="053a2-103">Configure IRM to use an on-premises AD RMS server</span></span>
  
<span data-ttu-id="053a2-p101">設置型展開で使用するためは、Exchange Online の情報権利管理 (IRM) は、Active Directory Rights Management サービス (AD RMS) と後で Windows Server 2008 では、情報保護の技術を使用します。IRM による保護は、電子メール メッセージに AD RMS 権利ポリシー テンプレートを適用することにより、電子メールに適用されます。権限は、オンラインとオフラインと内部と外部の組織のファイアウォールの保護が行われるように、メッセージ自体に添付されます。</span><span class="sxs-lookup"><span data-stu-id="053a2-p101">For use with on-premises deployments, Information Rights Management (IRM) in Exchange Online uses Active Directory Rights Management Services (AD RMS), an information protection technology in Windows Server 2008 and later. IRM protection is applied to email by applying an AD RMS rights policy template to an email message. Rights are attached to the message itself so that protection occurs online and offline and inside and outside of your organization's firewall.</span></span>
  
<span data-ttu-id="053a2-p102">このトピックでは、AD RMS サーバーを使用して IRM を構成する方法を示します。Azure Active Directory と Azure のアクセス権の管理と Office 365 のメッセージの暗号化の新しい機能の使用方法の詳細については、 [Office 365 のメッセージの暗号化の FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-p102">This topic shows you how to configure IRM to use an AD RMS server. For information about using the new capabilities for Office 365 Message Encryption with Azure Active Directory and Azure Rights Management, see the [Office 365 Message Encryption FAQ](https://support.office.com/article/0432dce9-d9b6-4e73-8a13-4a932eb0081e).</span></span>
  
<span data-ttu-id="053a2-109">Exchange Online の IRM については、「[Exchange Online での Information Rights Management](information-rights-management-in-exchange-online.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-109">To learn more about IRM in Exchange Online, see [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md).</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="053a2-110">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="053a2-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="053a2-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="053a2-111"></span></span>

- <span data-ttu-id="053a2-112">このタスクの予想所要時間:30 分</span><span class="sxs-lookup"><span data-stu-id="053a2-112">Estimated time to complete this task: 30 minutes</span></span>
    
- <span data-ttu-id="053a2-p103">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。 「[Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx)」の「Information Rights Management」。</span><span class="sxs-lookup"><span data-stu-id="053a2-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Information Rights Management" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic.</span></span> 
    
- <span data-ttu-id="053a2-p104">AD RMS サーバーは、Windows Server 2008 以降を実行している必要があります。AD RMS を展開する方法については、「[AD RMS クラスターのインストール](https://go.microsoft.com/fwlink/?LinkId=210873)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-p104">The AD RMS server must be running Windows Server 2008 or later. For details about how to deploy AD RMS, see [Installing an AD RMS Cluster](https://go.microsoft.com/fwlink/?LinkId=210873).</span></span>
    
- <span data-ttu-id="053a2-117">Windows PowerShell のインストール方法と構成方法、およびサービスへの接続方法については、「[リモート PowerShell による Exchange への接続](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-117">For details about how to install and configure Windows PowerShell and connect to the service, see [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/c8bea338-6c1a-4bdf-8de0-7895d427ee5b.aspx).</span></span>
    
- <span data-ttu-id="053a2-118">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-118">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="053a2-p105">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="053a2-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="053a2-122">実行方法</span><span class="sxs-lookup"><span data-stu-id="053a2-122">How do you do this?</span></span>
<span data-ttu-id="053a2-123"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="053a2-123"></span></span>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a><span data-ttu-id="053a2-124">手順 1:AD RMS コンソールを使用して、AD RMS サーバーから信頼された発行ドメイン (TPD) をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="053a2-124">Step 1: Use the AD RMS console to export a trusted publishing domain (TPD) from an AD RMS server</span></span>

<span data-ttu-id="053a2-p106">まず、信頼された発行ドメイン (TPD) を社内 AD RMS サーバーから XML ファイルにエクスポートします。TPD には RMS 機能を使用するために必要な以下の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="053a2-p106">The first step is to export a trusted publishing domain (TPD) from the on-premises AD RMS server to an XML file. The TPD contains the following settings needed to use RMS features:</span></span> 
  
- <span data-ttu-id="053a2-127">証明書とライセンスの署名と暗号化に使用されるサーバー ライセンサー証明書 (SLC)</span><span class="sxs-lookup"><span data-stu-id="053a2-127">The server licensor certificate (SLC) used for signing and encrypting certificates and licenses</span></span>
    
- <span data-ttu-id="053a2-128">ライセンスと発行に使用される URL</span><span class="sxs-lookup"><span data-stu-id="053a2-128">The URLs used for licensing and publishing</span></span>
    
- <span data-ttu-id="053a2-129">TPD に固有の SLC を使用して作成された AD RMS 権利ポリシー テンプレート</span><span class="sxs-lookup"><span data-stu-id="053a2-129">The AD RMS rights policy templates that were created with the specific SLC for that TPD</span></span>
    
<span data-ttu-id="053a2-130">TPD をインポートすると、Exchange Online に保存され、保護されます。</span><span class="sxs-lookup"><span data-stu-id="053a2-130">When you import the TPD, it's stored and protected in Exchange Online.</span></span>
  
1. <span data-ttu-id="053a2-131">Active Directory Rights Management サービスのコンソールを開いて、AD RMS クラスターを展開します。</span><span class="sxs-lookup"><span data-stu-id="053a2-131">Open the Active Directory Rights Management Services console, and then expand the AD RMS cluster.</span></span>
    
2. <span data-ttu-id="053a2-132">コンソール ツリーで、 **[信頼ポリシー]** を展開してから、 **[信頼された発行ドメイン]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="053a2-132">In the console tree, expand **Trust Policies**, and then click **Trusted Publishing Domains**.</span></span>
    
3. <span data-ttu-id="053a2-133">結果ウィンドウで、エクスポートするドメインの証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="053a2-133">In the results pane, select the certificate for the domain you want to export.</span></span>
    
4. <span data-ttu-id="053a2-134">**[操作]** ウィンドウで、 **[信頼された発行ドメインのエクスポート]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="053a2-134">In the **Actions** pane, click **Export Trusted Publishing Domain**.</span></span>
    
5. <span data-ttu-id="053a2-p107">**[発行ドメイン ファイル]** の **[名前を付けて保存]** をクリックして、ローカル コンピューター上の特定の場所にファイルを保存します。ファイル名を入力して、  `.xml` ファイル名拡張子を指定してから、 **[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="053a2-p107">In the **Publishing domain file** box, click **Save As** to save the file to a specific location on the local computer. Type a file name, making sure to specify the  `.xml` file name extension, and then click **Save**.</span></span>
    
6. <span data-ttu-id="053a2-p108">**[パスワード]** ボックスと **[パスワードの確認入力]** ボックスに、信頼された発行ドメイン ファイルの暗号化に使用する強力なパスワードを入力します。このパスワードは、クラウドベースの電子メール組織に TPD をインポートするときに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="053a2-p108">In the **Password** and **Confirm Password** boxes, type a strong password that will be used to encrypt the trusted publishing domain file. You will have to specify this password when you import the TPD to your cloud-based email organization.</span></span> 
    
### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a><span data-ttu-id="053a2-139">手順 2: Exchange 管理シェル を使用して TPD を Exchange Online にインポートする</span><span class="sxs-lookup"><span data-stu-id="053a2-139">Step 2: Use the Exchange Management Shell to import the TPD to Exchange Online</span></span>

<span data-ttu-id="053a2-p109">TPD を XML ファイルにエクスポートした後は、TPD を Exchange Online にインポートする必要があります。TPD をインポートすると、組織の AD RM テンプレートもインポートされます。最初の TPD をインポートすると、それがクラウドベース組織の既定の TPD になります。別の TPD をインポートする場合は、 **Default** スイッチを使用してこの TPD を既定の TPD にし、ユーザーが使用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="053a2-p109">After the TPD is exported to an XML file, you have to import it to Exchange Online. When a TPD is imported, your organization's AD RMS templates are also imported. When the first TPD is imported, it becomes the default TPD for your cloud-based organization. If you import another TPD, you can use the **Default** switch to make it the default TPD that is available to users.</span></span> 
  
<span data-ttu-id="053a2-144">TPD をインポートするには、Windows PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="053a2-144">To import the TPD, run the following command in Windows PowerShell:</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

<span data-ttu-id="053a2-p110">_ExtranetLicensingUrl_ パラメーターと  _IntranetLicensingUrl_ パラメーターの値は、Active Directory Rights Management サービスのコンソールで取得できます。コンソール ツリーで AD RMS クラスターを選択します。ライセンスの URL が結果ウィンドウに表示されます。コンテンツを復号化する必要がある場合と使用する TPD を Exchange Online で決定する必要がある場合は、これらの URL が電子メール クライアントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="053a2-p110">You can obtain the values for the  _ExtranetLicensingUrl_ and  _IntranetLicensingUrl_ parameters in the Active Directory Rights Management Services console. Select the AD RMS cluster in the console tree. The licensing URLs are displayed in the results pane. These URLs are used by email clients when content has to be decrypted and when Exchange Online needs to determine which TPD to use.</span></span> 
  
<span data-ttu-id="053a2-p111">このコマンドを実行すると、パスワードの入力を求めるプロンプトが表示されます。TPD を AD RMS サーバーからエクスポートしたときに指定したパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="053a2-p111">When you run this command, you'll be prompted for a password. Enter the password that you specified when you exported the TPD from your AD RMS server.</span></span>
  
<span data-ttu-id="053a2-p112">たとえば、次のコマンドは、AD RMS サーバーからエクスポートして管理者アカウントのデスクトップに保存された XML ファイルを使用して、Exported TPD という名前の TPD をインポートします。Name パラメーターは TPD の名前を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="053a2-p112">For example, the following command imports the TPD named Exported TPD using the XML file that you exported from your AD RMS server and saved to the desktop of the Administrator account. The Name parameter is used to specify a name to the TPD.</span></span>
  
```
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

<span data-ttu-id="053a2-153">構文およびパラメーターの詳細については、「[Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-153">For detailed syntax and parameter information, see [Import-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/7c5e7a0f-9c9d-4863-bab8-bcc729cc16a6.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="053a2-154">このステップの検証方法</span><span class="sxs-lookup"><span data-stu-id="053a2-154">How do you know this step worked?</span></span>

<span data-ttu-id="053a2-p113">TPD が正常にインポートされたことを確認するには、 **Get-RMSTrustedPublishingDomain** コマンドレットを実行して Exchange Online 組織の TPD を取得します。詳細については、「 [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx)」内の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-p113">To verify that you have successfully imported the TPD, run the **Get-RMSTrustedPublishingDomain** cmdlet to retrieve TPDs in your Exchange Online organization. For details, see the examples in [Get-RMSTrustedPublishingDomain](http://technet.microsoft.com/library/69499195-f08f-41bd-b0ed-443688410b12.aspx).</span></span>
  
### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a><span data-ttu-id="053a2-157">手順 3: Exchange 管理シェル を使用して AD RMS 権利ポリシー テンプレートを配布する</span><span class="sxs-lookup"><span data-stu-id="053a2-157">Step 3: Use the Exchange Management Shell to distribute an AD RMS rights policy template</span></span>

<span data-ttu-id="053a2-p114">TPD をインポートしたら、AD RMS 権利ポリシー テンプレートが配布されていることを確認する必要があります。配布済みテンプレートは Outlook Web App ユーザーに対して表示され、電子メール メッセージに適用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="053a2-p114">After you import the TPD, you must make sure an AD RMS rights policy template is distributed. A distributed template is visible to Outlook Web App users, who can then apply the templates to an email message.</span></span>
  
<span data-ttu-id="053a2-160">既定の TPD に含まれているすべてのテンプレートの一覧を取得するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="053a2-160">To return a list of all templates contained in the default TPD, run the following command:</span></span>
  
```
Get-RMSTemplate -Type All | fl
```

<span data-ttu-id="053a2-p115">_Type_ パラメーターの値が  `Archived` の場合は、テンプレートがユーザーに対して表示されません。既定の TPD に含まれている配布済みテンプレートだけを Outlook Web App で使用できます。</span><span class="sxs-lookup"><span data-stu-id="053a2-p115">If the value of the  _Type_ parameter is  `Archived`, the template isn't visible to users. Only distributed templates in the default TPD are available in Outlook Web App.</span></span>
  
<span data-ttu-id="053a2-163">テンプレートを配布するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="053a2-163">To distribute a template, run the following command:</span></span>
  
```
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

<span data-ttu-id="053a2-164">たとえば、次のコマンドは、Company Confidential テンプレートをインポートします。</span><span class="sxs-lookup"><span data-stu-id="053a2-164">For example, the following command imports the Company Confidential template.</span></span>
  
```
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

<span data-ttu-id="053a2-165">構文とパラメーターの詳細については、「[Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)」と「[Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-165">For detailed syntax and parameter information, see [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx) and [Set-RMSTemplate](http://technet.microsoft.com/library/4637f6b8-751a-4f5e-8869-428250230382.aspx).</span></span>
  
 <span data-ttu-id="053a2-166">**転送不可テンプレート**</span><span class="sxs-lookup"><span data-stu-id="053a2-166">**The Do Not Forward template**</span></span>
  
<span data-ttu-id="053a2-p116">既定の TPD を社内組織から Exchange Online にインポートすると、 **Do Not Forward** という名前の AD RMS 権利ポリシー テンプレートが 1 つインポートされます。既定で、このテンプレートは、既定の TPD をインポートしたときに配布されます。 **Set-RMSTemplate** コマンドレットを使用して **Do Not Forward** テンプレートを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="053a2-p116">When you import the default TPD from your on-premises organization into Exchange Online, one AD RMS rights policy template named **Do Not Forward** is imported. By default, this template is distributed when you import the default TPD. You can't use the **Set-RMSTemplate** cmdlet to modify the **Do Not Forward** template.</span></span> 
  
<span data-ttu-id="053a2-p117">**Do Not Forward** テンプレートがメッセージに適用されている場合は、メッセージにアドレスが指定された受信者のみがメッセージを読むことができます。受信者が次の操作を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="053a2-p117">When the **Do Not Forward** template is applied to a message, only the recipients addressed in the message can read the message. Additionally, recipients can't do the following:</span></span> 
  
- <span data-ttu-id="053a2-172">メッセージを別のユーザーに転送する。</span><span class="sxs-lookup"><span data-stu-id="053a2-172">Forward the message to another person.</span></span>
    
- <span data-ttu-id="053a2-173">メッセージの内容をコピーする。</span><span class="sxs-lookup"><span data-stu-id="053a2-173">Copy content from the message.</span></span>
    
- <span data-ttu-id="053a2-174">メッセージを印刷する。</span><span class="sxs-lookup"><span data-stu-id="053a2-174">Print the message.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="053a2-175">**Do Not Forward** テンプレートは、サードパーティのスクリーン キャプチャ プログラムやカメラを使用してメッセージ内の情報がコピーされたり、ユーザーによって情報が書き写されるのを防げるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="053a2-175">The **Do Not Forward** template can't prevent information in a message from being copied with third-party screen capture programs, cameras, or users manually transcribing the information</span></span> 
  
<span data-ttu-id="053a2-p118">IRM 保護要件に合わせて、社内組織内の AD RMS サーバー上に追加の AD RMS 権利ポリシー テンプレートを作成できます。追加の AD RMS 権利ポリシー テンプレートを作成する場合は、TPD を社内 AD RMS サーバーから再びエクスポートして、クラウドベースの電子メール組織の TPD を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="053a2-p118">You can create additional AD RMS rights policy templates on the AD RMS server in your on-premises organization to meet your IRM protection requirements. If you create additional AD RMS rights policy templates, you have to export the TPD from the on-premises AD RMS server again and refresh the TPD in the cloud-based email organization.</span></span> 
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="053a2-178">このステップの検証方法</span><span class="sxs-lookup"><span data-stu-id="053a2-178">How do you know this step worked?</span></span>

<span data-ttu-id="053a2-p119">AD RMS 権利ポリシー テンプレートが正常に配布されたことを確認するには、 **Get-RMSTemplate** コマンドレットを実行してテンプレートのプロパティをチェックします。詳細については、「 [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx)」内の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-p119">To verify that you have successfully distributed and AD RMS rights policy template, run the **Get-RMSTemplate** cmdlet to check the template's properties. For details, see the examples in [Get-RMSTemplate](http://technet.microsoft.com/library/4a5066e8-b770-4aa2-b464-0d2190914f71.aspx).</span></span>
  
### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a><span data-ttu-id="053a2-181">手順 4: Exchange 管理シェル を使用して IRM を有効にする</span><span class="sxs-lookup"><span data-stu-id="053a2-181">Step 4: Use the Exchange Management Shell to enable IRM</span></span>

<span data-ttu-id="053a2-182">TPD をインポートして AD RMS 権利ポリシー テンプレートを配布したら、次のコマンドを実行して、クラウドベースの電子メール組織に対して IRM を有効にします。</span><span class="sxs-lookup"><span data-stu-id="053a2-182">After you import the TPD and distribute an AD RMS rights policy template, run the following command to enable IRM for your cloud-based email organization.</span></span>
  
```
Set-IRMConfiguration -InternalLicensingEnabled $true
```

<span data-ttu-id="053a2-183">構文およびパラメーターの詳細については、「[Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-183">For detailed syntax and parameter information, see [Set-IRMConfiguration](http://technet.microsoft.com/library/5df0b56a-7bcc-4be2-b4b8-4de16720476c.aspx).</span></span>
  
#### <a name="how-do-you-know-this-step-worked"></a><span data-ttu-id="053a2-184">このステップの検証方法</span><span class="sxs-lookup"><span data-stu-id="053a2-184">How do you know this step worked?</span></span>

<span data-ttu-id="053a2-185">IRM が正常に有効になったことを確認するには、[Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) コマンドレットを実行して、Exchange Online 組織内の IRM 構成をチェックします。</span><span class="sxs-lookup"><span data-stu-id="053a2-185">To verify that you have successfully enabled IRM, run the [Get-IRMConfiguration](http://technet.microsoft.com/library/e1821219-fe18-4642-a9c2-58eb0aadd61a.aspx) cmdlet to check IRM configuration in the Exchange Online organization.</span></span> 
  
## <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="053a2-186">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="053a2-186">How do you know this task worked?</span></span>
<span data-ttu-id="053a2-187"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="053a2-187"></span></span>

<span data-ttu-id="053a2-188">TPD が正常にインポートされ、IRM が有効になったことを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="053a2-188">To verify that you have successfully imported the TPD and enabled IRM, do the following:</span></span>
  
- <span data-ttu-id="053a2-p120">IRM の機能をテストするには、 **Test-IRMConfiguration** コマンドレットを使用します。詳細については、「 [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx)」の「例 1」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="053a2-p120">Use the **Test-IRMConfiguration** cmdlet to test IRM functionality. For details, see "Example 1" in [Test-IRMConfiguration](http://technet.microsoft.com/library/a730e7ff-a67f-4360-b5ff-70d171bb5e1d.aspx).</span></span>
    
- <span data-ttu-id="053a2-191">Outlook Web App で新しいメッセージを作成し、拡張メニュー (****[その他のオプション] アイコン![) で ](media/ITPro-EAC-MoreOptionsIcon.png) オプションを選択して、そのメッセージを IRM で保護します。</span><span class="sxs-lookup"><span data-stu-id="053a2-191">Compose a new message in Outlook Web App and IRM-protect it by selecting **Set permissions** option from the extended menu ( ![More Options Icon](media/ITPro-EAC-MoreOptionsIcon.png)).</span></span>
    

