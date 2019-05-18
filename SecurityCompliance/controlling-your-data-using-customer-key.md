---
title: 顧客キーを使用して Office 365 でデータを制御する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
ms.collection:
- M365-security-compliance
description: Exchange Online、Skype for Business、SharePoint Online、OneDrive for business で Office 365 の顧客キーを設定する方法について説明します。 顧客キーを使用して、組織の暗号化キーを制御し、Office 365 を使用して Microsoft のデータセンターで保存されているデータを暗号化するように構成します。
ms.openlocfilehash: 839d0b56b3748e2ab4ccecc30a084447f22131aa
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153719"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="665e1-104">顧客キーを使用して Office 365 でデータを制御する</span><span class="sxs-lookup"><span data-stu-id="665e1-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="665e1-105">顧客キーによって、組織の暗号化キーを制御し、Microsoft のデータ センターにある保存データの暗号化にそれを使用するよう Office 365 を構成できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-105">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers.</span></span> <span data-ttu-id="665e1-106">言い換えると、顧客キーを使用すると、そのキーを使用して、ユーザーに属する暗号化の層を追加することができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-106">In other words, Customer Key allows customers to add a layer of encryption that belongs to them, with their keys.</span></span> <span data-ttu-id="665e1-107">保存データには、メールボックスに保存されている Exchange Online および Skype for Business からのデータと、SharePoint Online および OneDrive for Business に保存されているファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="665e1-107">Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="665e1-108">Office 365 の顧客キーを使用するには、事前に Azure をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-108">You must set up Azure before you can use Customer Key for Office 365.</span></span> <span data-ttu-id="665e1-109">このトピックでは、必要な Azure リソースを作成して構成するために従う必要のある手順について説明し、Office 365 で顧客キーを設定する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="665e1-109">This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365.</span></span> <span data-ttu-id="665e1-110">Azure のセットアップを完了した後、組織内のメールボックスとファイルに割り当てるポリシーとそのためのキーを決定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-110">After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization.</span></span> <span data-ttu-id="665e1-111">ポリシーを割り当てていないメールボックスとファイルでは、Microsoft によって制御および管理されている暗号化ポリシーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-111">Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft.</span></span> <span data-ttu-id="665e1-112">顧客キーの詳細、または一般的な概要については、「 [Office 365 FAQ」の顧客キー](service-encryption-with-customer-key-faq.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-112">For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="665e1-113">このトピックのベストプラクティスに従うことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-113">We strongly recommend that you follow the best practices in this topic.</span></span> <span data-ttu-id="665e1-114">これらは、 **TIP**と**重要**と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="665e1-114">These are called out as **TIP** and **IMPORTANT**.</span></span> <span data-ttu-id="665e1-115">顧客キーを使用すると、組織全体でスコープが大きくなる可能性があるルート暗号化キーを制御できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-115">Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization.</span></span> <span data-ttu-id="665e1-116">このため、これらのキーに誤りが発生しても、サービスが中断したり、データが irrevocable 失われたりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-116">This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="665e1-117">顧客キーの設定を開始する前に</span><span class="sxs-lookup"><span data-stu-id="665e1-117">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="665e1-118"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-118"></span></span>

<span data-ttu-id="665e1-119">開始する前に、組織に適したライセンスを持っていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-119">Before you get started, be sure you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="665e1-120">Office 365 の顧客キーは、Office 365 E5 または Advanced コンプライアンス SKU で提供されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-120">Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="665e1-121">その後、このトピックの概念と手順を理解するには、 [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/)のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-121">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation.</span></span> <span data-ttu-id="665e1-122">また、「[テナント](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)」など、Azure で使用される用語について理解しておいてください。</span><span class="sxs-lookup"><span data-stu-id="665e1-122">Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="665e1-123">ドキュメントなどの顧客キーに関するフィードバックを提供するために、アイデア、提案、視点を customerkeyfeedback@microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="665e1-123">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="665e1-124">Office 365 の顧客キーの設定の概要</span><span class="sxs-lookup"><span data-stu-id="665e1-124">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="665e1-125"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-125"></span></span>

<span data-ttu-id="665e1-126">顧客キーを設定するには、これらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="665e1-126">To set up Customer Key you will complete these tasks.</span></span> <span data-ttu-id="665e1-127">このトピックの残りの部分では、各タスクの詳細な手順を説明します。または、プロセスの各ステップに関する詳細情報へのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-127">The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="665e1-128">**Azure と Microsoft FastTrack の場合:**</span><span class="sxs-lookup"><span data-stu-id="665e1-128">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="665e1-129">これらのタスクのほとんどは、Azure PowerShell にリモートで接続することで完了します。</span><span class="sxs-lookup"><span data-stu-id="665e1-129">You will complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="665e1-130">最良の結果を得るには、Azure PowerShell のバージョン4.4.0 以降を使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-130">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="665e1-131">2つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-131">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="665e1-132">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="665e1-132">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="665e1-133">登録には 1 ~ 5 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="665e1-133">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="665e1-134">Office 365 の顧客キーを有効にするための要求を送信する</span><span class="sxs-lookup"><span data-stu-id="665e1-134">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="665e1-135">2つの新しい Azure サブスクリプションを作成したら、Microsoft FastTrack ポータルでホストされている web フォームに入力して、適切な顧客キー提示要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-135">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal.</span></span> <span data-ttu-id="665e1-136">**FastTrack チームは、顧客キーについてサポートを提供していません。Office では、FastTrack ポータルを使用**してフォームを送信することができます。また、顧客キーの関連する提供を追跡するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="665e1-136">**The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="665e1-137">カスタマーキーオファーを送信すると、Microsoft は要求を確認し、残りのセットアップタスクを続行できる場合に通知します。</span><span class="sxs-lookup"><span data-stu-id="665e1-137">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks.</span></span> <span data-ttu-id="665e1-138">このプロセスには最大5営業日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="665e1-138">This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="665e1-139">各サブスクリプションにプレミアム Azure キーコンテナーを作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-139">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="665e1-140">各キーコンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="665e1-140">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="665e1-141">キーコンテナーでの論理削除を有効にして、確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-141">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="665e1-142">キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="665e1-142">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="665e1-143">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="665e1-143">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="665e1-144">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="665e1-144">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="665e1-145">Azure Key Vault 構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="665e1-145">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="665e1-146">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="665e1-146">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="665e1-147">**Office 365:**</span><span class="sxs-lookup"><span data-stu-id="665e1-147">**In Office 365:**</span></span>
  
<span data-ttu-id="665e1-148">Exchange Online と Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="665e1-148">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="665e1-149">Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-149">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="665e1-150">メールボックスに DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="665e1-150">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="665e1-151">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="665e1-151">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="665e1-152">SharePoint Online と OneDrive for Business:</span><span class="sxs-lookup"><span data-stu-id="665e1-152">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="665e1-153">SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-153">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="665e1-154">グループサイト、チームサイト、および OneDrive for Business の暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="665e1-154">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="665e1-155">Azure Key Vault のタスクを完了し、顧客キーの Microsoft FastTrack を管理する</span><span class="sxs-lookup"><span data-stu-id="665e1-155">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="665e1-156"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-156"></span></span>

<span data-ttu-id="665e1-157">Office 365 の顧客キーを設定するために、Azure Key Vault でこれらのタスクを完了します。</span><span class="sxs-lookup"><span data-stu-id="665e1-157">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365.</span></span> <span data-ttu-id="665e1-158">これらの手順は、Exchange Online と Skype for business、SharePoint Online と OneDrive for business、または Office 365 でサポートされているすべてのサービスに対して、顧客キーを設定するかどうかにかかわらず実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-158">You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="665e1-159">2つの新しい Azure サブスクリプションを作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-159">Create two new Azure subscriptions</span></span>
<span data-ttu-id="665e1-160"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-160"></span></span>

<span data-ttu-id="665e1-161">顧客キーには、2つの Azure サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-161">Two Azure subscriptions are required for Customer Key.</span></span> <span data-ttu-id="665e1-162">ベストプラクティスとして、Microsoft では、顧客キーと共に使用するために新しい Azure サブスクリプションを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-162">As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key.</span></span> <span data-ttu-id="665e1-163">Azure Key Vault キーは、同じ Azure Active Directory (AAD) テナント内のアプリケーションに対してのみ承認できます。この新しいサブスクリプションは、DEPs が割り当てられている Office 365 組織で使用されているものと同じ Azure AD テナントを使用して作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-163">Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned.</span></span> <span data-ttu-id="665e1-164">たとえば、Office 365 組織のグローバル管理者特権を持つ職場または学校のアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-164">For example, using your work or school account that has global administrator privileges in your Office 365 organization.</span></span> <span data-ttu-id="665e1-165">詳細な手順については、「[組織としての Azure へのサインアップ](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-165">For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="665e1-166">顧客キーには、データ暗号化ポリシー (DEP) ごとに2つのキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-166">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="665e1-167">これを実現するためには、2つの Azure サブスクリプションを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-167">In order to achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="665e1-168">ベストプラクティスとして、組織のメンバーごとに、各サブスクリプションで1つのキーを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-168">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="665e1-169">さらに、これらの Azure サブスクリプションは、Office 365 の暗号化キーを管理するためにのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-169">In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365.</span></span> <span data-ttu-id="665e1-170">これにより、オペレーターのいずれかが偶然、故意、または悪意によって削除された場合や、自分が責任を持つキーを誤って管理した場合に、組織が保護されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-170">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span> <br/> <span data-ttu-id="665e1-171">顧客キーで使用するために Azure Key Vault リソースの管理にのみ使用される新しい Azure サブスクリプションをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-171">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key.</span></span> <span data-ttu-id="665e1-172">組織に対して作成できる Azure サブスクリプションの数に実際に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="665e1-172">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="665e1-173">これらのベストプラクティスに従うことで、顧客キーによって使用されるリソースの管理を支援しながら、人的エラーの影響を最小限に抑えることができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-173">Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="665e1-174">Office 365 の顧客キーを有効にするための要求を送信する</span><span class="sxs-lookup"><span data-stu-id="665e1-174">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="665e1-175"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-175"></span></span>

<span data-ttu-id="665e1-176">Azure の手順を完了したら、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)で提供要求を提出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-176">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span> <span data-ttu-id="665e1-177">FastTrack web ポータルを通じて要求を送信すると、Microsoft は、提供された Azure Key Vault 構成データと連絡先情報を検証します。</span><span class="sxs-lookup"><span data-stu-id="665e1-177">Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided.</span></span> <span data-ttu-id="665e1-178">組織の承認済みの担当者に関する提供フォームで行う選択は、重要であり、顧客のキーの登録を完了するために必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-178">The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration.</span></span> <span data-ttu-id="665e1-179">フォームで選択する組織の責任者は、顧客キーデータ暗号化ポリシーで使用されているすべてのキーを取り消して破棄するためのすべての要求の信頼性を確保するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-179">The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy.</span></span> <span data-ttu-id="665e1-180">この手順を1回実行する必要があります。これを行うには、Exchange Online と Skype for business の使用をサポートするための顧客キーを有効にし、SharePoint Online と OneDrive for business の顧客キーを再度アクティブにします。</span><span class="sxs-lookup"><span data-stu-id="665e1-180">You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="665e1-181">顧客キーを有効にするオファーを提出するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-181">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="665e1-182">Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)にログインします。</span><span class="sxs-lookup"><span data-stu-id="665e1-182">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="665e1-183">ログインしたら、**ダッシュボード**を参照します。</span><span class="sxs-lookup"><span data-stu-id="665e1-183">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="665e1-184">[**提供**] を選択し、現在のサービスの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-184">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="665e1-185">適用するオファーの詳細については、「**詳細情報**」を選択します。</span><span class="sxs-lookup"><span data-stu-id="665e1-185">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="665e1-186">**Exchange Online と Skype For business:**「 **Exchange サービスの顧客キー** 」で、[**詳細情報**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="665e1-186">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="665e1-187">**SharePoint Online と OneDrive For business:**「 **SharePoint および OneDrive For business のお客様キー** 」を**参照**してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-187">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="665e1-188">[**提供の詳細**] ページで、[**要求の作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="665e1-188">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="665e1-189">提供フォームで該当するすべての詳細と要求された情報を記入します。</span><span class="sxs-lookup"><span data-stu-id="665e1-189">Fill out all applicable details and requested information on the offer form.</span></span> <span data-ttu-id="665e1-190">暗号化キーとデータを永続的に、元に戻れないように承認する組織の責任者に対して、特定の選択について特に注目してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-190">Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data.</span></span> <span data-ttu-id="665e1-191">フォームが完成したら、[**送信**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="665e1-191">Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="665e1-192">このプロセスは、Microsoft が要求を通知した後、最大5営業日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="665e1-192">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="665e1-193">以下の必須の [保持期間] に進みます。</span><span class="sxs-lookup"><span data-stu-id="665e1-193">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="665e1-194">Azure サブスクリプションを登録して必須の保持期間を使用する</span><span class="sxs-lookup"><span data-stu-id="665e1-194">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="665e1-195"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-195"></span></span>

<span data-ttu-id="665e1-196">ルート暗号化キーが一時的または完全に失われると、非常に破壊的または重大な操作によってデータが失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-196">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="665e1-197">このため、顧客キーで使用されるリソースには強力な保護が必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-197">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="665e1-198">顧客キーと共に使用されるすべての Azure リソースは、既定の構成を超える保護メカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="665e1-198">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="665e1-199">Azure サブスクリプションは、即時および irrevocable のキャンセルを防止するようにタグ付けまたは登録することができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-199">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="665e1-200">これは、必須の保持期間の登録と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="665e1-200">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="665e1-201">必須の保持期間に Azure サブスクリプションを登録するために必要な手順は、Office 365 チームとの共同作業が必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-201">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team.</span></span> <span data-ttu-id="665e1-202">このプロセスには、1 ~ 5 営業日かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="665e1-202">This process can take from one to five business days.</span></span> <span data-ttu-id="665e1-203">以前は、これは「キャンセルしない」と呼ばれることがありました。</span><span class="sxs-lookup"><span data-stu-id="665e1-203">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="665e1-204">Office 365 チームに連絡する前に、顧客キーで使用する各 Azure サブスクリプションに対して次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-204">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="665e1-205">Azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="665e1-205">Log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="665e1-206">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)してログインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-206">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="665e1-207">AzureRmProviderFeature コマンドレットを実行して、必須の保持期間を使用するようにサブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="665e1-207">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="665e1-208">プロセスを完了させるために、Microsoft にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="665e1-208">Contact Microsoft to have the process finalized.</span></span> <span data-ttu-id="665e1-209">SharePoint および OneDrive for Business チームについては、 [spock@microsoft.com](mailto:spock@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="665e1-209">For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com).</span></span> <span data-ttu-id="665e1-210">Exchange Online と Skype for Business の場合は、 [exock@microsoft.com](mailto:exock@microsoft.com)にお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="665e1-210">For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com).</span></span> <span data-ttu-id="665e1-211">このプロセスを完了するためのサービスレベル契約 (SLA) は、Microsoft が事前通知 (および検証) した後で、サブスクリプションを必須の保持期間を使用するように登録した後、5営業日です。</span><span class="sxs-lookup"><span data-stu-id="665e1-211">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="665e1-212">メールに次のものを含めます。</span><span class="sxs-lookup"><span data-stu-id="665e1-212">Include the following in your email:</span></span>
    
    <span data-ttu-id="665e1-213">**件名**: \<*テナントの完全修飾ドメイン名*の顧客キー\></span><span class="sxs-lookup"><span data-stu-id="665e1-213">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="665e1-214">**本文**: 必須の保持期間を最終処理するサブスクリプション id。</span><span class="sxs-lookup"><span data-stu-id="665e1-214">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="665e1-215">登録が完了したことを Microsoft から通知されたら、次のように AzureRmProviderFeature コマンドレットを実行して、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-215">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="665e1-216">AzureRmProviderFeature コマンドレットの**登録状態**プロパティが [**登録済み**] の値を返すことを確認した後、次のコマンドを実行してプロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="665e1-216">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="665e1-217">各サブスクリプションにプレミアム Azure キーコンテナーを作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-217">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="665e1-218"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-218"></span></span>

<span data-ttu-id="665e1-219">キーコンテナーを作成する手順については、「azure[キーコンテナー](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)の概要」で説明されています。このガイドでは、azure PowerShell のインストールと起動、azure サブスクリプションへの接続、リソースグループの作成、およびその場所でのキーコンテナーの作成を実行する方法について説明します。リソースグループ。</span><span class="sxs-lookup"><span data-stu-id="665e1-219">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="665e1-220">キーコンテナーを作成する場合、SKU: Standard または Premium のどちらかを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-220">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="665e1-221">標準 SKU を使用すると、Azure Key Vault キーがソフトウェアで保護されます。ハードウェアセキュリティモジュール (HSM) キー保護はありません。また、Premium SKU では、重要な資格情報のキーを保護するために Hsm を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-221">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="665e1-222">顧客キーは、いずれかの SKU を使用するキーコンテナーを受け入れますが、Microsoft は Premium SKU のみを使用することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-222">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="665e1-223">どちらの種類のキーを使用する操作のコストも同じであるため、コストの唯一の違いは、各 HSM で保護されたキーの月ごとのコストです。</span><span class="sxs-lookup"><span data-stu-id="665e1-223">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="665e1-224">詳細については、「[主要な資格情報](https://azure.microsoft.com/pricing/details/key-vault/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-224">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="665e1-225">プレミアム SKU キーコンテナーおよび HSM で保護された、運用データ用のキーを使用して、テストおよび検証の目的で標準的な SKU キーボルトとキーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-225">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="665e1-226">顧客キーを使用する Office 365 サービスごとに、作成した2つの Azure サブスクリプションのそれぞれにキーコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="665e1-226">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created.</span></span> <span data-ttu-id="665e1-227">たとえば、Exchange Online と Skype for business のみ、または SharePoint Online と OneDrive for business の場合のみ、ボルトのペアを1つだけ作成します。</span><span class="sxs-lookup"><span data-stu-id="665e1-227">For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults.</span></span> <span data-ttu-id="665e1-228">Exchange Online と SharePoint Online の両方で顧客キーを有効にするには、キーコンテナーの2つのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="665e1-228">To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="665e1-229">資格を与えるために使用する DEP の使用目的を反映する、キーコンテナーの名前付け規則を使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-229">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults.</span></span> <span data-ttu-id="665e1-230">命名規則の推奨事項については、以下の「ベストプラクティス」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-230">See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="665e1-231">各データ暗号化ポリシーに対して、独立したコンテナーのセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="665e1-231">Create a separate, paired set of vaults for each data encryption policy.</span></span> <span data-ttu-id="665e1-232">Exchange Online の場合、データ暗号化ポリシーの範囲は、そのポリシーをメールボックスに割り当てるときに選択されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-232">For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox.</span></span> <span data-ttu-id="665e1-233">メールボックスに割り当てることのできるポリシーは1つだけで、最大50のポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-233">A mailbox can have only one policy assigned, and you can create up to fifty policies.</span></span> <span data-ttu-id="665e1-234">SharePoint Online では、ポリシーの範囲として、組織内のすべてのデータが地理的な場所または geo に含まれます。</span><span class="sxs-lookup"><span data-stu-id="665e1-234">For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="665e1-235">キーコンテナーの作成には、Azure リソースグループの作成も必要です。これは、キーコンテナーにはストレージ容量が必要です (非常に小さい)。また、キーヴォールトログが有効になっている場合は、保存されたデータも生成します。</span><span class="sxs-lookup"><span data-stu-id="665e1-235">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data.</span></span> <span data-ttu-id="665e1-236">ベストプラクティスとして、Microsoft では、個別の管理者を使用して各リソースグループを管理することをお勧めします。管理者は、関連するすべての顧客キーリソースを管理する一連の管理者と連携しています。</span><span class="sxs-lookup"><span data-stu-id="665e1-236">As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="665e1-237">可用性を最大限にするには、Office 365 サービスの近くにある地域にキーコンテナーが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-237">To maximize availability, your key vaults should be in regions close to your Office 365 service.</span></span> <span data-ttu-id="665e1-238">たとえば、北米に Exchange Online 組織がある場合は、北アメリカにキーコンテナーを配置します。</span><span class="sxs-lookup"><span data-stu-id="665e1-238">For example, if your Exchange Online organization is in North America, place your key vaults in North America.</span></span> <span data-ttu-id="665e1-239">Exchange Online 組織がヨーロッパの場合は、重要な資格を欧州に配置します。</span><span class="sxs-lookup"><span data-stu-id="665e1-239">If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="665e1-240">キーコンテナーに共通のプレフィックスを使用します。また、重要な資格情報の使用およびスコープの省略形を含めることもできます (たとえば、コンテナーが北米に配置される Contoso SharePoint サービスの場合は、名前のペアが O365SP-NA-VaultA1 となり、Contoso-O365SP-VaultA2。</span><span class="sxs-lookup"><span data-stu-id="665e1-240">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2.</span></span> <span data-ttu-id="665e1-241">コンテナー名は Azure 内のグローバルに一意の文字列なので、目的の名前が他の Azure のお客様によって既に要求されている場合は、目的の名前のバリエーションを試す必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-241">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="665e1-242">2017年7月の資格情報を変更することはできません。そのため、セットアップに関する計画を作成し、2番目のユーザーを使用して計画が正常に実行されることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-242">As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="665e1-243">可能な場合は、ペアになっていない地域にコンテナーを作成します。</span><span class="sxs-lookup"><span data-stu-id="665e1-243">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="665e1-244">ペアになっている Azure 領域は、サービス障害ドメイン間で高可用性を提供します。</span><span class="sxs-lookup"><span data-stu-id="665e1-244">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="665e1-245">そのため、地域のペアは、互いのバックアップ地域と考えることができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-245">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="665e1-246">これは、1つの領域に配置されている Azure リソースが、ペア化された領域を通じて自動的にフォールトトレランスを獲得することを意味します。</span><span class="sxs-lookup"><span data-stu-id="665e1-246">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="665e1-247">このため、地域がペアになっている場合に、DEP で使用される2つの資格情報領域を選択することは、2つの空き領域が使用されていることを意味します。</span><span class="sxs-lookup"><span data-stu-id="665e1-247">For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="665e1-248">ほとんどの地域には2つの地域があるため、ペアになっていない地域を選択することはまだできません。</span><span class="sxs-lookup"><span data-stu-id="665e1-248">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="665e1-249">可能であれば、DEP で使用する2つのコンテナーに対して2つのペアでない地域を選択します。</span><span class="sxs-lookup"><span data-stu-id="665e1-249">If possible, choose two non-paired regions for the two vaults used with a DEP.</span></span> <span data-ttu-id="665e1-250">これは、合計4つの可用性の領域からメリットを得られます。</span><span class="sxs-lookup"><span data-stu-id="665e1-250">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="665e1-251">詳細については、「 [Business 継続性と障害復旧 (BCDR)](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 」を参照してください。現在の地域のペアの一覧については、「Azure ペアリング領域」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-251">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="665e1-252">各キーコンテナーにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="665e1-252">Assign permissions to each key vault</span></span>
<span data-ttu-id="665e1-253"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-253"></span></span>

<span data-ttu-id="665e1-254">各キーコンテナーについて、お客様の実装に応じて、顧客キーに対して3つの個別のアクセス許可セットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-254">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="665e1-255">たとえば、次のいずれかのアクセス許可のセットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-255">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="665e1-256">組織のために主要な資格情報コンテナーの日常の管理を実行する**主要な資格情報コンテナー管理者**。</span><span class="sxs-lookup"><span data-stu-id="665e1-256">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="665e1-257">これらのタスクには、backup、create、get、import、list、restore があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-257">These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="665e1-258">キーコンテナー管理者に割り当てられているアクセス許可のセットには、キーを削除するためのアクセス許可は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="665e1-258">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="665e1-259">これは意図的で重要な手法です。</span><span class="sxs-lookup"><span data-stu-id="665e1-259">This is intentional and an important practice.</span></span> <span data-ttu-id="665e1-260">暗号化キーの削除は、通常、データを完全に破棄するため、通常は行われません。</span><span class="sxs-lookup"><span data-stu-id="665e1-260">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="665e1-261">ベストプラクティスとして、既定では、このアクセス許可を主要な資格情報管理者に付与しないでください。</span><span class="sxs-lookup"><span data-stu-id="665e1-261">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="665e1-262">その代わりに、主要な資格情報投稿者に対してこれを予約し、その結果を明確に理解した後に、短い期間のみ管理者に割り当てるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="665e1-262">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="665e1-263">Office 365 組織のユーザーにこれらのアクセス許可を割り当てるには、azure PowerShell を使用して Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="665e1-263">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="665e1-264">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)してログインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-264">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="665e1-265">必要なアクセス許可を割り当てるには、AzureRmKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-265">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="665e1-266">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-266">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="665e1-267">Azure Key Vault 自体に対する権限を変更できる**重要な資格情報投稿**者。</span><span class="sxs-lookup"><span data-stu-id="665e1-267">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="665e1-268">これらのアクセス許可を変更する必要があるのは、従業員がチームを脱退するか、チームに参加するか、重要な資格情報管理者がキーを削除または復元するためのアクセス許可を必要とする非常にまれな状況です。</span><span class="sxs-lookup"><span data-stu-id="665e1-268">You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="665e1-269">この一連の主要なコンテナー投稿者は、キーコンテナーに対して**投稿者**の役割を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-269">This set of key vault contributors needs to be granted the **Contributor** role on your key vault.</span></span> <span data-ttu-id="665e1-270">この役割は、Azure リソースマネージャーを使用して割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-270">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="665e1-271">詳細な手順については、「[役割ベースのアクセス制御を使用して Azure サブスクリプションリソースへのアクセスを管理する](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-271">For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure).</span></span> <span data-ttu-id="665e1-272">サブスクリプションを作成する管理者は、このアクセス権と、他の管理者を共同作成者の役割に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-272">The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="665e1-273">Exchange Online と Skype for business で顧客キーを使用する場合は、Office 365 に Exchange Online と Skype for business の代わりにキーヴォールトを使用するためのアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-273">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business.</span></span> <span data-ttu-id="665e1-274">同様に、SharePoint Online と OneDrive for business で顧客キーを使用する場合は、SharePoint Online と OneDrive for business の代わりにキーコンテナーを使用するために Office 365 にアクセス許可を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-274">Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="665e1-275">Office 365 にアクセス許可を付与するには、次の構文を使用して**AzureRmKeyVaultAccessPolicy**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-275">To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="665e1-276">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="665e1-276">Where:</span></span>
    
  - <span data-ttu-id="665e1-277">*vaultname*は、作成したキーのコンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="665e1-277">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="665e1-278">Exchange Online と Skype for Business の場合は、 *Office 365 appID*をに置き換えます。`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="665e1-278">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="665e1-279">SharePoint Online と OneDrive for business の場合は、 *Office 365 appID*をに置き換えます。`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="665e1-279">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="665e1-280">例: Exchange Online と Skype for Business のアクセス許可を設定する:</span><span class="sxs-lookup"><span data-stu-id="665e1-280">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="665e1-281">例: SharePoint Online と OneDrive for business の権限を設定する</span><span class="sxs-lookup"><span data-stu-id="665e1-281">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="665e1-282">キーコンテナーでの論理削除を有効にして、確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-282">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="665e1-283"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-283"></span></span>

<span data-ttu-id="665e1-284">キーをすばやく回復できると、偶然または悪意によって削除されたキーによってサービスの停止が発生する可能性が低くなります。</span><span class="sxs-lookup"><span data-stu-id="665e1-284">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="665e1-285">ユーザーキーでキーを使用する前に、この構成を (ソフト削除と呼ばれる) 有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-285">You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="665e1-286">ソフト削除を有効にすると、バックアップからの復元を行わずに、削除から90日以内にキーまたは資格を回復できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-286">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="665e1-287">キーコンテナーでの論理削除を有効にするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-287">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="665e1-288">Windows Powershell を使用して、Azure サブスクリプションにログインします。</span><span class="sxs-lookup"><span data-stu-id="665e1-288">Log in to your Azure subscription with Windows Powershell.</span></span> <span data-ttu-id="665e1-289">手順については、「 [Azure PowerShell を使用](https://docs.microsoft.com/powershell/azure/authenticate-azureps)してログインする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-289">For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="665e1-290">[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-290">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet.</span></span> <span data-ttu-id="665e1-291">この例では、 *vaultname*は、回復可能な削除を有効にするキーコンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="665e1-291">In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="665e1-292">**AzureRmKeyVault**コマンドレットを実行して、重要なコンテナーに対して論理削除が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-292">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet.</span></span> <span data-ttu-id="665e1-293">重要な資格情報コンテナーに対して論理削除が適切に構成されている場合は、回復可能な削除を有効にしますか。プロパティは**True**の値を返します。</span><span class="sxs-lookup"><span data-stu-id="665e1-293">If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="665e1-294">キーを作成またはインポートすることによって、各キーコンテナーにキーを追加する</span><span class="sxs-lookup"><span data-stu-id="665e1-294">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="665e1-295"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-295"></span></span>

<span data-ttu-id="665e1-296">Azure Key Vault にキーを追加するには、2つの方法があります。キーを直接キーコンテナーに作成することも、キーをインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="665e1-296">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="665e1-297">キーコンテナーに直接キーを作成することは、より単純な方法ですが、キーのインポートでは、キーの生成方法を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-297">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="665e1-298">キーコンテナーに直接キーを作成するには、次のように[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-298">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="665e1-299">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="665e1-299">Where:</span></span>
  
-  <span data-ttu-id="665e1-300">*vaultname*は、キーを作成するキーコンテナーの名前です。</span><span class="sxs-lookup"><span data-stu-id="665e1-300">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="665e1-301">*keyname*は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="665e1-301">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="665e1-302">キーコンテナーの場合と同様の命名規則を使用して、名前付きキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-302">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="665e1-303">このようにすると、キー名のみを表示するツールでは、文字列が自己記述されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-303">This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="665e1-304">キーを HSM で保護する場合は、 _Destination_パラメーターの値として**hsm**を指定する必要があります。そうでない場合は、**ソフトウェア**を指定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-304">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="665e1-305">For example,</span><span class="sxs-lookup"><span data-stu-id="665e1-305">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="665e1-306">キーを直接キーコンテナーにインポートするには、Thales nShield ハードウェアセキュリティモジュールを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-306">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="665e1-307">一部の組織では、キーの機能を確立するためにこの方法をお勧めします。また、この方法では、次の機能も提供されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-307">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="665e1-308">インポートに使用されるツールセットには、Thales からの構成証明が含まれています。生成するキー交換キー (KEK) はエクスポート可能ではないため、Thales によって製造された正規の HSM の内部で生成されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-308">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="665e1-309">ツールセットには、Thales からの構成証明が含まれています。これは、Azure Key Vault セキュリティ world が Thales で製造された正規の HSM でも生成されたことです。</span><span class="sxs-lookup"><span data-stu-id="665e1-309">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales.</span></span> <span data-ttu-id="665e1-310">この構成証明は、Microsoft が正規の Thales ハードウェアを使用していることを証明します。</span><span class="sxs-lookup"><span data-stu-id="665e1-310">This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="665e1-311">セキュリティグループに確認して、上記の attestations が必要かどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-311">Check with your security group to determine if the above attestations are required.</span></span> <span data-ttu-id="665e1-312">オンプレミスのキーを作成してキーコンテナーにインポートする詳細な手順については、「 [Azure Key vault 用に HSM で保護されたキーを生成して転送する方法](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-312">For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/).</span></span> <span data-ttu-id="665e1-313">各キーコンテナーにキーを作成するには、Azure の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-313">Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="665e1-314">キーの回復レベルを確認する</span><span class="sxs-lookup"><span data-stu-id="665e1-314">Check the recovery level of your keys</span></span>
<span data-ttu-id="665e1-315"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-315"></span></span>

<span data-ttu-id="665e1-316">Office 365 では、Azure Key Vault サブスクリプションがキャンセルされないように設定されている必要があります。また、顧客キーで使用されるキーには、ソフト削除が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="665e1-316">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="665e1-317">このことを確認するには、キーの回復レベルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-317">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="665e1-318">キーの復旧レベルを確認するには、Azure PowerShell で、次のように AzureKeyVaultKey コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-318">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="665e1-319">_回復レベル_プロパティが、回復**可能 + ProtectedSubscription**以外の値を返す場合は、このトピックを確認して、サブスクリプションをキャンセル不可リストに追加するすべての手順を実行していることを確認してください。各キーボルトに対して、ソフト削除が有効になっていること。</span><span class="sxs-lookup"><span data-stu-id="665e1-319">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="665e1-320">Azure Key Vault のバックアップ</span><span class="sxs-lookup"><span data-stu-id="665e1-320">Backup Azure Key Vault</span></span>
<span data-ttu-id="665e1-321"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-321"></span></span>

<span data-ttu-id="665e1-322">作成またはキーへの変更の直後に、バックアップを実行し、オンラインとオフラインの両方でバックアップとストアのコピーを行います。</span><span class="sxs-lookup"><span data-stu-id="665e1-322">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="665e1-323">オフラインコピーは、物理的な安全または商用ストレージ機能などのネットワークに接続することはできません。</span><span class="sxs-lookup"><span data-stu-id="665e1-323">Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="665e1-324">バックアップの少なくとも1つは、障害が発生した場合にアクセスできる場所に格納する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-324">At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster.</span></span> <span data-ttu-id="665e1-325">バックアップ blob はキーマテリアルを復元するための唯一の手段です。キーコンテナーキーを完全に破棄するか、またはその他の方法で操作できないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-325">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="665e1-326">Azure key vault の外部にあるキーは、キーを使用するために必要なメタデータが外部キーに存在しないため、バックアップとして認定されません。</span><span class="sxs-lookup"><span data-stu-id="665e1-326">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="665e1-327">顧客キーを使用した復元操作には、Azure Key Vault から取得したバックアップのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-327">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="665e1-328">したがって、キーをアップロードまたは作成した後に、Azure Key Vault のバックアップを作成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-328">Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="665e1-329">Azure Key Vault キーのバックアップを作成するには、次のように[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-329">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="665e1-330">出力ファイルがサフィックス`.backup`を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-330">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="665e1-331">このコマンドレットから得られる出力ファイルは暗号化されており、Azure Key Vault の外部では使用できません。</span><span class="sxs-lookup"><span data-stu-id="665e1-331">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="665e1-332">バックアップは、バックアップが実行された Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-332">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="665e1-333">出力ファイルに対して、コンテナー名とキー名の組み合わせを選択します。</span><span class="sxs-lookup"><span data-stu-id="665e1-333">For the output file, choose a combination of your vault name and key name.</span></span> <span data-ttu-id="665e1-334">これにより、ファイル名が自己記述されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-334">This will make the file name self-describing.</span></span> <span data-ttu-id="665e1-335">バックアップファイルの名前が競合しないようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="665e1-335">It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="665e1-336">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-336">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="665e1-337">Azure Key Vault 構成設定を検証する</span><span class="sxs-lookup"><span data-stu-id="665e1-337">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="665e1-338"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-338"></span></span>

<span data-ttu-id="665e1-339">DEP でキーを使用する前に検証を実行することはオプションですが、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-339">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="665e1-340">特に、手順を使用して、このトピックで説明されているもの以外のキーとボルトを設定する場合は、顧客キーを構成する前に、Azure Key Vault のリソースの状態を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-340">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="665e1-341">キーに get、wrapKey、および unwrapKey 操作が有効になっていることを確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="665e1-341">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="665e1-342">[AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-342">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="665e1-343">出力で、必要に応じて、アクセスポリシーと Exchange Online id (GUID) または SharePoint Online id (GUID) を探します。</span><span class="sxs-lookup"><span data-stu-id="665e1-343">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate.</span></span> <span data-ttu-id="665e1-344">上記の3つのアクセス許可のすべてを [キーへのアクセス許可] の下に表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-344">All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="665e1-345">アクセスポリシーの構成が正しくない場合は、次のように AzureRmKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-345">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="665e1-346">たとえば、Exchange Online と Skype for Business の場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="665e1-346">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="665e1-347">たとえば、SharePoint Online と OneDrive for business の場合は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="665e1-347">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="665e1-348">キーの有効期限が設定されていないことを確認するには、 [AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-348">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="665e1-349">期限切れのキーを顧客キーで使用することはできず、期限切れのキーを使用して実行しようとした操作は失敗し、サービスが停止する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-349">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage.</span></span> <span data-ttu-id="665e1-350">顧客キーと一緒に使用するキーに有効期限がないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-350">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="665e1-351">有効期限日を設定すると、削除することはできませんが、別の日付に変更することができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-351">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="665e1-352">有効期限日が設定されているキーを使用する必要がある場合は、有効期限の値を12/31/9999 に変更します。</span><span class="sxs-lookup"><span data-stu-id="665e1-352">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="665e1-353">有効期限が12/31/9999 以外の日付に設定されているキーは、Office 365 検証に合格しません。</span><span class="sxs-lookup"><span data-stu-id="665e1-353">Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="665e1-354">12/31/9999 以外の値に設定されている有効期限を変更するには、 [AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-354">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="665e1-355">顧客キーで使用する暗号化キーに有効期限を設定しないようにします。</span><span class="sxs-lookup"><span data-stu-id="665e1-355">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="665e1-356">各 Azure Key Vault キーの URI を取得する</span><span class="sxs-lookup"><span data-stu-id="665e1-356">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="665e1-357"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-357"></span></span>

<span data-ttu-id="665e1-358">キーコンテナーを設定してキーを追加するために Azure のすべての手順を完了したら、次のコマンドを実行して、各キーコンテナーのキーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="665e1-358">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="665e1-359">後で各 DEP を作成して割り当てるときにこれらの Uri を使用する必要があるので、この情報は安全な場所に保存しておいてください。</span><span class="sxs-lookup"><span data-stu-id="665e1-359">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="665e1-360">このコマンドは、キーヴォールトごとに1回実行してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-360">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="665e1-361">Azure PowerShell の場合:</span><span class="sxs-lookup"><span data-stu-id="665e1-361">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="665e1-362">Office 365: Exchange Online と Skype for Business の顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="665e1-362">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="665e1-363"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-363"></span></span>

<span data-ttu-id="665e1-364">開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-364">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="665e1-365">詳細については[、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](controlling-your-data-using-customer-key.md#AzureSteps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-365">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="665e1-366">Exchange Online と Skype for Business の顧客キーを設定するには、Windows PowerShell を使用して Exchange Online にリモートで接続することにより、これらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-366">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="665e1-367">Exchange Online と Skype for Business で使用するデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-367">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="665e1-368"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-368"></span></span>

<span data-ttu-id="665e1-369">DEP は、Azure Key Vault に格納されているキーのセットに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="665e1-369">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="665e1-370">Office 365 で、メールボックスに DEP を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="665e1-370">You assign a DEP to a mailbox in Office 365.</span></span> <span data-ttu-id="665e1-371">Office 365 は、ポリシーで識別されたキーを使用して、メールボックスを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="665e1-371">Office 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="665e1-372">DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-372">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="665e1-373">手順については[、「Azure Key Vault キーごとに URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-373">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="665e1-374">念頭!</span><span class="sxs-lookup"><span data-stu-id="665e1-374">Remember!</span></span> <span data-ttu-id="665e1-375">DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-375">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="665e1-376">これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-376">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="665e1-377">DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-377">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="665e1-378">ローカルコンピューターで、Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、Windows PowerShell を開いて次のコマンドを実行して、 [Exchange Online powershell に接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="665e1-378">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="665e1-379">[Windows PowerShell 資格情報の要求] ダイアログボックスで、職場または学校のアカウント情報を入力し、[ **OK**] をクリックして、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="665e1-379">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="665e1-380">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-380">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="665e1-381">DEP を作成するには、次のコマンドを入力して、新しい-DataEncryptionPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-381">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="665e1-382">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="665e1-382">Where:</span></span>
    
   -  <span data-ttu-id="665e1-383">*PolicyName*は、ポリシーに使用する名前です。</span><span class="sxs-lookup"><span data-stu-id="665e1-383">*PolicyName*  is the name you want to use for the policy.</span></span> <span data-ttu-id="665e1-384">名前にスペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="665e1-384">Names cannot contain spaces.</span></span> <span data-ttu-id="665e1-385">たとえば、USA_mailboxes のようになります。</span><span class="sxs-lookup"><span data-stu-id="665e1-385">For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="665e1-386">*PolicyDescription*は、ポリシーの目的を記憶するのに役立つユーザーフレンドリな説明です。</span><span class="sxs-lookup"><span data-stu-id="665e1-386">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="665e1-387">説明にはスペースを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-387">You can include spaces in the description.</span></span> <span data-ttu-id="665e1-388">たとえば、USA およびその領土のメールボックスのルートキー。</span><span class="sxs-lookup"><span data-stu-id="665e1-388">For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="665e1-389">*KeyVaultURI1*は、ポリシー内の最初のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="665e1-389">*KeyVaultURI1*  is the URI for the first key in the policy.</span></span> <span data-ttu-id="665e1-390">たとえば、https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01 などです。</span><span class="sxs-lookup"><span data-stu-id="665e1-390">For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="665e1-391">*KeyVaultURI2*は、ポリシーの2番目のキーの URI です。</span><span class="sxs-lookup"><span data-stu-id="665e1-391">*KeyVaultURI2*  is the URI for the second key in the policy.</span></span> <span data-ttu-id="665e1-392">たとえば、https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02 などです。</span><span class="sxs-lookup"><span data-stu-id="665e1-392">For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02.</span></span> <span data-ttu-id="665e1-393">2つの Uri をコンマとスペースで区切ります。</span><span class="sxs-lookup"><span data-stu-id="665e1-393">Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="665e1-394">例:</span><span class="sxs-lookup"><span data-stu-id="665e1-394">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="665e1-395">メールボックスに DEP を割り当てる</span><span class="sxs-lookup"><span data-stu-id="665e1-395">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="665e1-396"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-396"></span></span>

<span data-ttu-id="665e1-397">メールボックスの設定コマンドレットを使用して、メールボックスに DEP を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="665e1-397">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="665e1-398">ポリシーを割り当てた後、Office 365 は DEP で指定されたキーを使用してメールボックスを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-398">Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="665e1-399">ここで、 *MailboxIdParameter*はメールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-399">Where *MailboxIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="665e1-400">メールボックスの設定コマンドレットの詳細については、「[メールボックスの設定](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-400">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="665e1-401">メールボックスの暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="665e1-401">Validate mailbox encryption</span></span>
<span data-ttu-id="665e1-402"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-402"></span></span>

<span data-ttu-id="665e1-403">メールボックスを暗号化するには、しばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="665e1-403">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="665e1-404">最初にポリシーを割り当てる場合、メールボックスは、サービスがメールボックスを暗号化する前に、あるデータベースから別のデータベースへの移動も完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-404">For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox.</span></span> <span data-ttu-id="665e1-405">DEP を変更した後、または初めてメールボックスに DEP を割り当てるときに、暗号化の検証を試行する前に、72時間待つことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-405">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="665e1-406">メールボックスが暗号化されているかどうかを確認するには、Get-mailboxstatistics コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-406">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="665e1-407">IsEncrypted プロパティは、メールボックスが暗号化されている場合は**true**の値を返し、メールボックスが暗号化されていない場合は**false**の値を返します。</span><span class="sxs-lookup"><span data-stu-id="665e1-407">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="665e1-408">メールボックスの移動が完了するまでの時間は、最初に DEP を割り当てるメールボックスの数、およびメールボックスのサイズによって異なります。</span><span class="sxs-lookup"><span data-stu-id="665e1-408">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes.</span></span> <span data-ttu-id="665e1-409">DEP を割り当てたときから1週間後にメールボックスが暗号化されていない場合は、New-moverequest コマンドレットを使用して、暗号化されていないメールボックスのメールボックスの移動を開始します。</span><span class="sxs-lookup"><span data-stu-id="665e1-409">If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="665e1-410">Office 365: SharePoint Online と OneDrive for business の顧客キーの設定</span><span class="sxs-lookup"><span data-stu-id="665e1-410">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="665e1-411"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-411"></span></span>

<span data-ttu-id="665e1-412">開始する前に、Azure Key Vault をセットアップするために必要なタスクを完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-412">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="665e1-413">詳細については[、「Azure Key Vault でタスクを完了する」および「Microsoft FastTrack For Customer key](controlling-your-data-using-customer-key.md#AzureSteps) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-413">See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="665e1-414">SharePoint Online と OneDrive for business の顧客キーを設定するには、Windows PowerShell を使用して SharePoint Online にリモートで接続することにより、これらの手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-414">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="665e1-415">SharePoint Online と OneDrive for business の各 geo にデータ暗号化ポリシー (DEP) を作成する</span><span class="sxs-lookup"><span data-stu-id="665e1-415">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="665e1-416"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-416"></span></span>

<span data-ttu-id="665e1-417">DEP は、Azure Key Vault に格納されているキーのセットに関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="665e1-417">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="665e1-418">1つの地理的な場所 (geo とも呼ばれます) 内のすべてのデータに DEP を適用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-418">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="665e1-419">Office 365 の複数地域機能を使用している場合 (現在プレビュー中)、geo ごとに1つの DEP を作成できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-419">If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo.</span></span> <span data-ttu-id="665e1-420">複数地域を使用していない場合は、SharePoint Online と OneDrive for business で使用するために、1つの DEP を Office 365 で作成できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-420">If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="665e1-421">Office 365 は、DEP で識別されたキーを使用して、その地域のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="665e1-421">Office 365 will then use the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="665e1-422">DEP を作成するには、前の手順で取得したキーの資格情報 Uri が必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-422">To create the DEP, you need the Key Vault URIs you obtained earlier.</span></span> <span data-ttu-id="665e1-423">手順については[、「Azure Key Vault キーごとに URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-423">See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="665e1-424">念頭!</span><span class="sxs-lookup"><span data-stu-id="665e1-424">Remember!</span></span> <span data-ttu-id="665e1-425">DEP を作成するときには、2つの異なる Azure キーボルトに存在する2つのキーを指定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-425">When you create a DEP, you specify two keys that reside in two different Azure Key Vaults.</span></span> <span data-ttu-id="665e1-426">これらのキーが、地理的冗長性を確保するために2つの独立した Azure 領域に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-426">Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="665e1-427">DEP を作成するには、Windows PowerShell を使用して SharePoint Online にリモートで接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-427">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="665e1-428">ローカルコンピューターで、Office 365 組織のグローバル管理者のアクセス許可を持つ職場または学校のアカウントを使用して、 [SharePoint Online Powershell に接続](https://technet.microsoft.com/library/fp161372.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="665e1-428">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="665e1-429">Microsoft SharePoint Online 管理シェルで、 [get-spodataencryptionpolicy](https://technet.microsoft.com/library/mt843950.aspx)コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-429">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="665e1-430">DEP を登録すると、暗号化は geo のデータに対して開始されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-430">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="665e1-431">これには、しばらく時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="665e1-431">This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="665e1-432">グループサイト、チームサイト、および OneDrive for Business の暗号化を検証する</span><span class="sxs-lookup"><span data-stu-id="665e1-432">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="665e1-433"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-433"></span></span>

<span data-ttu-id="665e1-434">Get-spodataencryptionpolicy コマンドレットを次のように実行して、暗号化の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-434">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="665e1-435">このコマンドレットの出力には次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="665e1-435">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="665e1-436">主キーの URI。</span><span class="sxs-lookup"><span data-stu-id="665e1-436">The URI of the primary key.</span></span>
    
- <span data-ttu-id="665e1-437">セカンダリキーの URI。</span><span class="sxs-lookup"><span data-stu-id="665e1-437">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="665e1-438">Geo の暗号化の状態。</span><span class="sxs-lookup"><span data-stu-id="665e1-438">The encryption status for the geo.</span></span> <span data-ttu-id="665e1-439">次の状態が考えられます。</span><span class="sxs-lookup"><span data-stu-id="665e1-439">Possible states include:</span></span>
    
  - <span data-ttu-id="665e1-440">**未登録:** 顧客キーの暗号化はまだ適用されていません。</span><span class="sxs-lookup"><span data-stu-id="665e1-440">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="665e1-441">**登録:** 顧客キーの暗号化が適用され、ファイルが暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="665e1-441">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="665e1-442">Geo がこの状態にある場合は、暗号化の進行状況を監視できるように、地域内のサイトの割合がどれだけ完了しているかに関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-442">If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="665e1-443">**登録済み:** 顧客キーの暗号化が適用され、すべてのサイトのすべてのファイルが暗号化されました。</span><span class="sxs-lookup"><span data-stu-id="665e1-443">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="665e1-444">**ローリング:** キーロールが進行中です。</span><span class="sxs-lookup"><span data-stu-id="665e1-444">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="665e1-445">Geo がこの状態にある場合は、進行状況を監視できるように、キーロール操作を完了したサイトの割合に関する情報も表示されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-445">If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="665e1-446">Office 用の顧客キーの管理365</span><span class="sxs-lookup"><span data-stu-id="665e1-446">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="665e1-447"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-447"></span></span>

<span data-ttu-id="665e1-448">Office 365 の顧客キーを設定した後、これらの追加の管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-448">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="665e1-449">Azure Key Vault キーを復元する</span><span class="sxs-lookup"><span data-stu-id="665e1-449">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="665e1-450">顧客キーと共に使用する Azure Key Vault でキーをローリングまたは回転する</span><span class="sxs-lookup"><span data-stu-id="665e1-450">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="665e1-451">キーコンテナーのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="665e1-451">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="665e1-452">メールボックスに割り当てられた DEP を決定する</span><span class="sxs-lookup"><span data-stu-id="665e1-452">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="665e1-453">Azure Key Vault キーを復元する</span><span class="sxs-lookup"><span data-stu-id="665e1-453">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="665e1-454"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-454"></span></span>

<span data-ttu-id="665e1-455">復元を実行する前に、ソフト削除で提供される回復機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-455">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="665e1-456">ユーザーキーで使用されるすべてのキーは、ソフト削除を有効にするために必要です。</span><span class="sxs-lookup"><span data-stu-id="665e1-456">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="665e1-457">ソフト削除は、ごみ箱と同じように動作し、復元する必要がなくても最大90日の復旧が可能です。</span><span class="sxs-lookup"><span data-stu-id="665e1-457">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="665e1-458">復元は、キーまたはキーの保管が失われた場合など、極端または異常な状況でのみ必要になります。</span><span class="sxs-lookup"><span data-stu-id="665e1-458">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="665e1-459">顧客キーと一緒に使用するためにキーを復元する必要がある場合は、Azure PowerShell で、AzureKeyVaultKey コマンドレットを次のように実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-459">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="665e1-460">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-460">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="665e1-461">同じ名前を持つキーがキーコンテナーに既に存在する場合、復元操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="665e1-461">If a key with the same name already exists in the key vault, the restore operation will fail.</span></span> <span data-ttu-id="665e1-462">AzureKeyVaultKey は、キーの名前を含むキーのすべてのキーバージョンとすべてのメタデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="665e1-462">Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="665e1-463">顧客キーと共に使用する Azure Key Vault でキーをローリングまたは回転する</span><span class="sxs-lookup"><span data-stu-id="665e1-463">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="665e1-464"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-464"></span></span>

<span data-ttu-id="665e1-465">キーのローリングは、Azure Key Vault または顧客キーでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="665e1-465">Rolling keys is not required by either Azure Key Vault or by Customer Key.</span></span> <span data-ttu-id="665e1-466">さらに、HSM で保護されているキーは、実質的には危険にさらすことは不可能です。</span><span class="sxs-lookup"><span data-stu-id="665e1-466">In addition, keys that are protected with an HSM are virtually impossible to compromise.</span></span> <span data-ttu-id="665e1-467">ルートキーが悪意のある出演者に所有されている場合でも、Office 365 コードのみがその使用方法を認識しているため、これを使用してデータの暗号化を解除することはできません。</span><span class="sxs-lookup"><span data-stu-id="665e1-467">Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it.</span></span> <span data-ttu-id="665e1-468">ただし、キーのロールは顧客キーでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="665e1-468">However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="665e1-469">お客様キーと一緒に使用する暗号化キーをロールするのは、明確な技術的理由が存在するか、コンプライアンスの要件によってキーをロールする必要がある場合のみにしてください。</span><span class="sxs-lookup"><span data-stu-id="665e1-469">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key.</span></span> <span data-ttu-id="665e1-470">また、ポリシーに関連付けられている、またはポリシーに関連付けられていたキーは削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="665e1-470">In addition, do not delete any keys that are or were associated with policies.</span></span> <span data-ttu-id="665e1-471">キーをロールすると、以前のキーを使用してコンテンツが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-471">When you roll your keys, there will be content encrypted with the previous keys.</span></span> <span data-ttu-id="665e1-472">たとえば、アクティブなメールボックスは頻繁に再暗号化されますが、非アクティブ、切断済み、および無効になったメールボックスは、以前のキーで暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="665e1-472">For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys.</span></span> <span data-ttu-id="665e1-473">SharePoint Online は復元と回復のためにコンテンツのバックアップを実行するので、古いキーを使用してアーカイブされたコンテンツが残っている場合があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-473">SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys.</span></span> <br/> <span data-ttu-id="665e1-474">データの安全性を確保するために、SharePoint Online では一度に1つのキーロール操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="665e1-474">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time.</span></span> <span data-ttu-id="665e1-475">キーコンテナーで両方のキーをロールバックする場合は、最初のキーロール操作が完全に完了するまで待機する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-475">If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete.</span></span> <span data-ttu-id="665e1-476">重要な役割の操作をさまざまな間隔でずらして、これが問題にならないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="665e1-476">Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="665e1-477">キーをロールすると、既存のキーの新しいバージョンが要求されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-477">When you roll a key, you are requesting a new version of an existing key.</span></span> <span data-ttu-id="665e1-478">既存のキーの新しいバージョンを要求するために、最初にキーを作成したときと同じ構文を使用して、同じコマンドレット[AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)を使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-478">In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="665e1-479">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-479">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="665e1-480">この例では、 **VaultA1-Key001**という名前のキーが O365EX に既に存在して\*\*\*\* いるため、新しいキーバージョンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-480">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created.</span></span> <span data-ttu-id="665e1-481">操作によって新しいキーバージョンが追加されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-481">The operation adds a new key version.</span></span> <span data-ttu-id="665e1-482">この操作では、以前のキーバージョンがキーのバージョン履歴で保持されるため、以前にキーを使用して暗号化されたデータを復号化することができます。</span><span class="sxs-lookup"><span data-stu-id="665e1-482">This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted.</span></span> <span data-ttu-id="665e1-483">DEP に関連付けられているキーのすべてのロールアウトを完了したら、追加のコマンドレットを実行して、顧客キーが新しいキーを使用するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-483">Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="665e1-484">Azure Key Vault でキーをロールまたは回転した後、Exchange Online と Skype for Business が新しいキーを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="665e1-484">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="665e1-485">Exchange Online と Skype for Business で使用される DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールバックする場合は、次のコマンドを実行して DEP を更新し、Office 365 を有効にして新しいキーの使用を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-485">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="665e1-486">Office 365 でメールボックスを暗号化するために新しいキーを使用するよう顧客キーに指示するには、次のように、Set-DataEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-486">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="665e1-487">48時間以内に、このポリシーを使用して暗号化されたアクティブなメールボックスは、更新されたキーに関連付けられます。</span><span class="sxs-lookup"><span data-stu-id="665e1-487">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key.</span></span> <span data-ttu-id="665e1-488">「[メールボックスに対して DEP が割り当てられているかどうかを判断](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)する」の手順を使用して、メールボックスの DataEncryptionPolicyID プロパティの値を確認します。</span><span class="sxs-lookup"><span data-stu-id="665e1-488">Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox.</span></span> <span data-ttu-id="665e1-489">更新したキーが適用されると、このプロパティの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-489">The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="665e1-490">Azure Key Vault でキーをロールまたは回転した後、SharePoint Online と OneDrive for Business で新しいキーを使用できるようにする</span><span class="sxs-lookup"><span data-stu-id="665e1-490">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="665e1-491">SharePoint Online と OneDrive for business で使用される DEP に関連付けられている Azure キーヴォールトキーのいずれかをロールする場合は、 [get-spodataencryptionpolicy](https://technet.microsoft.com/library/mt843948.aspx)コマンドレットを実行して dep を更新し、Office 365 を有効にして新しいキーの使用を開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-491">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="665e1-492">これにより、SharePoint Online と OneDrive for business のキーロール操作が開始されます。</span><span class="sxs-lookup"><span data-stu-id="665e1-492">This will start the key roll operation for SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="665e1-493">このアクションは、すぐには実行されません。</span><span class="sxs-lookup"><span data-stu-id="665e1-493">This action is not immediate.</span></span> <span data-ttu-id="665e1-494">キーロール操作の進行状況を確認するには、次のように Get-spodataencryptionpolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-494">To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="665e1-495">キーコンテナーのアクセス許可を管理する</span><span class="sxs-lookup"><span data-stu-id="665e1-495">Manage key vault permissions</span></span>
<span data-ttu-id="665e1-496"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-496"></span></span>

<span data-ttu-id="665e1-497">いくつかのコマンドレットを使用して、重要な資格情報のアクセス許可を表示および削除できます。</span><span class="sxs-lookup"><span data-stu-id="665e1-497">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="665e1-498">たとえば、従業員がチームを離れるときにアクセス許可を削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="665e1-498">You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="665e1-499">重要な資格情報コンテナーのアクセス許可を表示するには、AzureRmKeyVault コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-499">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="665e1-500">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-500">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="665e1-501">管理者のアクセス許可を削除するには、AzureRmKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="665e1-501">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="665e1-502">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="665e1-502">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="665e1-503">メールボックスに割り当てられた DEP を決定する</span><span class="sxs-lookup"><span data-stu-id="665e1-503">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="665e1-504"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="665e1-504"></span></span>

<span data-ttu-id="665e1-505">メールボックスに割り当てられている DEP を特定するには、Get-mailboxstatistics コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="665e1-505">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="665e1-506">コマンドレットは、一意の識別子 (GUID) を返します。</span><span class="sxs-lookup"><span data-stu-id="665e1-506">The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="665e1-507">ここで、 *GeneralMailboxOrMailUserIdParameter*はメールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="665e1-507">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox.</span></span> <span data-ttu-id="665e1-508">Get-mailboxstatistics コマンドレットの詳細については、「 [get-mailboxstatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="665e1-508">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="665e1-509">GUID を使用して、次のコマンドレットを実行して、メールボックスが割り当てられている DEP のフレンドリ名を検索します。</span><span class="sxs-lookup"><span data-stu-id="665e1-509">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="665e1-510">ここで、 *guid*は、前の手順で get-mailboxstatistics コマンドレットによって返される guid です。</span><span class="sxs-lookup"><span data-stu-id="665e1-510">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

