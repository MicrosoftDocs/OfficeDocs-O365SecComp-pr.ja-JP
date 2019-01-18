---
title: 顧客キーを使用して Office 365 でデータを制御する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/1/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f2cd475a-e592-46cf-80a3-1bfb0fa17697
description: ビジネス、SharePoint Online では、およびビジネスのための OneDrive の Exchange Online、Skype の Office 365 用の顧客のキーを設定する方法について説明します。顧客のキーを使用して、組織の暗号キーを制御し、マイクロソフトのデータ センターの残りの部分でデータの暗号化を使用する Office 365 を構成し、します。
ms.openlocfilehash: c4a59af49efad3bb8539b6c83b9ad9fd1c2d1f43
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723254"
---
# <a name="controlling-your-data-in-office-365-using-customer-key"></a><span data-ttu-id="fd9b8-104">顧客キーを使用して Office 365 でデータを制御する</span><span class="sxs-lookup"><span data-stu-id="fd9b8-104">Controlling your data in Office 365 using Customer Key</span></span>

<span data-ttu-id="fd9b8-p102">顧客のキーを使用して、組織の暗号キーを制御し、マイクロソフトのデータ ・ センターの残りの部分でデータの暗号化を使用する Office 365 を構成し、します。不使用時のデータには、Exchange のオンラインと、メールボックス、および SharePoint Online に保存されているファイルに格納されているビジネス用の Skype とビジネスの OneDrive からのデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p102">With Customer Key, you control your organization's encryption keys and then configure Office 365 to use them to encrypt your data at rest in Microsoft's data centers. Data at rest includes data from Exchange Online and Skype for Business that is stored in mailboxes and files that are stored in SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="fd9b8-p103">Office 365 の顧客のキーを使用する前に、Azure を設定する必要があります。このトピックでは、作成し、必要な Azure リソースを構成するために必要な手順を説明し、Office 365 の顧客のキーを設定するための手順を提供します。Azure のセットアップが完了したら後、は、どのポリシーでは、およびそのため、メールボックス、および組織内のファイルに割り当てるには、どのキーを決定します。メールボックスと対象のポリシーを割り当てていないファイルの管理方法と Microsoft によって管理されている暗号化のポリシーを使用します。顧客のキーの詳細については、一般的な概要については、 [Office 365 のよく寄せられる質問の顧客のキー](service-encryption-with-customer-key-faq.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p103">You must set up Azure before you can use Customer Key for Office 365. This topic describes the steps you need to follow to create and configure the required Azure resources and then provides the steps for setting up Customer Key in Office 365. After you have completed Azure setup, you determine which policy, and therefore, which keys, to assign to mailboxes and files in your organization. Mailboxes and files for which you don't assign a policy will use encryption policies that are controlled and managed by Microsoft. For more information about Customer Key, or for a general overview, see the [Customer Key for Office 365 FAQ](service-encryption-with-customer-key-faq.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fd9b8-p104">ここでのベスト プラクティスに従うことを強くお勧めします。これらは、**ヒント**、**重要**とと呼びます。ルートの暗号化キーを持つスコープを制御するキーにより、顧客は、組織全体と同じ大きさにすることはできます。つまり、これらのキーの間違いが広範な影響を与えることができ、サービスの中断やデータの損失を取り消し不可能な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p104">We strongly recommend that you follow the best practices in this topic. These are called out as **TIP** and **IMPORTANT**. Customer Key gives you control over root encryption keys whose scope can be as large as your entire organization. This means that mistakes made with these keys can have a broad impact and may result in service interruptions or irrevocable loss of your data.</span></span> 
  
## <a name="before-you-begin-setting-up-customer-key"></a><span data-ttu-id="fd9b8-116">顧客キーの設定を開始する前に</span><span class="sxs-lookup"><span data-stu-id="fd9b8-116">Before you begin setting up Customer Key</span></span>
<span data-ttu-id="fd9b8-117"><a name="Beforeyoustart"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-117"></span></span>

<span data-ttu-id="fd9b8-p105">作業を開始する前に、組織の適切なライセンスがあることを確認します。Office 365 の顧客のキーは、Office 365 の E5 や高度なコンプライアンス SKU で提供されています。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p105">Before you get started, be sure you have the appropriate licensing for your organization. Customer Key in Office 365 is offered in Office 365 E5 or the Advanced Compliance SKU.</span></span>
  
<span data-ttu-id="fd9b8-p106">次に、このトピックの手順と概念を理解するのに[Azure キー ヴォールト](https://azure.microsoft.com/en-us/documentation/services/key-vault/)のマニュアルを確認します。また、Azure では、[テナント](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant)などで使われる用語に精通のようになります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p106">Then, to understand the concepts and procedures in this topic, you should review the [Azure Key Vault](https://azure.microsoft.com/en-us/documentation/services/key-vault/) documentation. Also, become familiar with the terms used in Azure, for example, [tenant](https://msdn.microsoft.com/library/azure/jj573650.aspx#BKMK_WhatIsAnAzureADTenant).</span></span>
  
<span data-ttu-id="fd9b8-122">顧客キーを文書などに関するフィードバックを提供するには、customerkeyfeedback@microsoft.com に、アイデア、提案、分析視点を送信します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-122">To provide feedback on Customer Key, including the documentation, send your ideas, suggestions and perspectives to customerkeyfeedback@microsoft.com.</span></span>
  
## <a name="overview-of-setting-up-customer-key-for-office-365"></a><span data-ttu-id="fd9b8-123">Office 365 の顧客のキーの設定の概要</span><span class="sxs-lookup"><span data-stu-id="fd9b8-123">Overview of setting up Customer Key for Office 365</span></span>
<span data-ttu-id="fd9b8-124"><a name="Overview"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-124"></span></span>

<span data-ttu-id="fd9b8-p107">顧客キーを設定するには、これらのタスクを完了します。このトピックの残りの部分には、各タスクまたはプロセスの各手順の詳細についてをリンクする詳細な手順が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p107">To set up Customer Key you will complete these tasks. The rest of this topic provides detailed instructions for each task, or links out to more information for each step in the process.</span></span>
  
<span data-ttu-id="fd9b8-127">**Azure および Microsoft FastTrack。**</span><span class="sxs-lookup"><span data-stu-id="fd9b8-127">**In Azure and Microsoft FastTrack:**</span></span>
  
<span data-ttu-id="fd9b8-p108">Azure PowerShell にリモートで接続することによって、これらのタスクのほとんどを完了します。最良の結果を使用してバージョン 4.4.0 や Azure PowerShell の後で。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p108">You will complete most of these tasks by remotely connecting to Azure PowerShell. For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>
  
- [<span data-ttu-id="fd9b8-130">2 つの新しい Azure サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-130">Create two new Azure subscriptions</span></span>](controlling-your-data-using-customer-key.md#Create2newsubs)
    
- [<span data-ttu-id="fd9b8-131">必須の保持期間を使用するのには Azure サブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-131">Register Azure subscriptions to use a mandatory retention period</span></span>](controlling-your-data-using-customer-key.md#RegisterSubsforMRP)
    
    <span data-ttu-id="fd9b8-132">登録は、1 ~ 5 営業日かかります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-132">Registration can take from one to five business days.</span></span>
    
- [<span data-ttu-id="fd9b8-133">Office 365 の顧客のキーをアクティブ化する要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-133">Submit a request to activate Customer Key for Office 365</span></span>](controlling-your-data-using-customer-key.md#FastTrack)
    
    <span data-ttu-id="fd9b8-p109">2 つの新しい Azure サブスクリプションを作成した後は、適切な顧客キーの提供要求を送信するには、Microsoft FastTrack ポータルでホストされている web フォームに入力する必要があります。**、Fasttrack というチームは、お客様のキーを使用して支援を提供していません。Office だけを使用して、FastTrack ポータルを使用すると、フォームを送信して、顧客キーに関連するサービスを追跡するために**。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p109">Once you've created the two new Azure subscriptions, you'll need to submit the appropriate Customer Key offer request by completing a web form that is hosted in the Microsoft FastTrack portal. **The FastTrack team doesn't provide assistance with Customer Key. Office simply uses the FastTrack portal to allow you to submit the form and to help us track the relevant offers for Customer Key**.</span></span>
  
<span data-ttu-id="fd9b8-p110">顧客キーの提供を送信すると、Microsoft は、要求をレビューし、セットアップ タスクの残りの部分を行うときに通知します。最大 5 営業日をかかることができます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p110">Once you have submitted a Customer Key offer, Microsoft reviews your request and notifies you when you can proceed with the rest of the setup tasks. This process can take up to five business days.</span></span>
    
- [<span data-ttu-id="fd9b8-138">サブスクリプションごとにプレミアムの Azure キー ヴォールトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-138">Create a premium Azure Key Vault in each subscription</span></span>](controlling-your-data-using-customer-key.md#CreateKeyVault)
    
- [<span data-ttu-id="fd9b8-139">各キーのボルトにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fd9b8-139">Assign permissions to each key vault</span></span>](controlling-your-data-using-customer-key.md#KeyVaultPerms)
    
- [<span data-ttu-id="fd9b8-140">有効にして、キー、ボルトのソフトの削除を確認</span><span class="sxs-lookup"><span data-stu-id="fd9b8-140">Enable and then confirm soft delete on your key vaults</span></span>](controlling-your-data-using-customer-key.md#SoftDelete)
    
- [<span data-ttu-id="fd9b8-141">各キーのボルトにするか、作成またはキーをインポートすることでキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-141">Add a key to each key vault either by creating or importing a key</span></span>](controlling-your-data-using-customer-key.md#AddKeystoKeyVault)
    
- [<span data-ttu-id="fd9b8-142">キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-142">Check the recovery level of your keys</span></span>](controlling-your-data-using-customer-key.md#CheckKeyRecoveryLevel)
    
- [<span data-ttu-id="fd9b8-143">Azure キー ヴォールトをバックアップ</span><span class="sxs-lookup"><span data-stu-id="fd9b8-143">Backup Azure Key Vault</span></span>](controlling-your-data-using-customer-key.md#BackupAzureKeyVaultkeys)
    
- [<span data-ttu-id="fd9b8-144">Azure キーの格納域の構成の設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-144">Validate Azure Key Vault configuration settings</span></span>](controlling-your-data-using-customer-key.md#Validateconfiguration)
    
- [<span data-ttu-id="fd9b8-145">各 Azure キー ヴォールト ・ キーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-145">Obtain the URI for each Azure Key Vault key</span></span>](controlling-your-data-using-customer-key.md#GetKeyURI)
    
<span data-ttu-id="fd9b8-146">**Office 365:**</span><span class="sxs-lookup"><span data-stu-id="fd9b8-146">**In Office 365:**</span></span>
  
<span data-ttu-id="fd9b8-147">Exchange のオンライン ビジネスの Skype.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-147">Exchange Online and Skype for Business:</span></span>
  
- [<span data-ttu-id="fd9b8-148">ビジネスの Exchange Online と Skype を使用するためのデータ暗号化のポリシー (DEP) の作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-148">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4EXOSkype)
    
- [<span data-ttu-id="fd9b8-149">DEP をメールボックスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="fd9b8-149">Assign a DEP to a mailbox</span></span>](controlling-your-data-using-customer-key.md#assignDEPtomailbox)
    
- [<span data-ttu-id="fd9b8-150">メールボックスの暗号化を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-150">Validate mailbox encryption</span></span>](controlling-your-data-using-customer-key.md#validatemailboxencryption)
    
<span data-ttu-id="fd9b8-151">SharePoint のオンライン ビジネスのための OneDrive.</span><span class="sxs-lookup"><span data-stu-id="fd9b8-151">SharePoint Online and OneDrive for Business:</span></span>
  
- [<span data-ttu-id="fd9b8-152">各 SharePoint Online および OneDrive のビジネス地域のデータの暗号化ポリシー (DEP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-152">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>](controlling-your-data-using-customer-key.md#CreateDEP4SPOODfB)
    
- [<span data-ttu-id="fd9b8-153">グループ サイト、チーム サイト、およびビジネスのための OneDrive の暗号化を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-153">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>](controlling-your-data-using-customer-key.md#validateencryptionSPO)
    
## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a><span data-ttu-id="fd9b8-154">Azure キー ヴォールトおよび顧客キー用の Microsoft FastTrack でタスクを完了</span><span class="sxs-lookup"><span data-stu-id="fd9b8-154">Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key</span></span>
<span data-ttu-id="fd9b8-155"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-155"></span></span>

<span data-ttu-id="fd9b8-p111">Office 365 の顧客のキーを設定するのには、Azure のキーの保管場所にこれらのタスクを完了します。かどうかを設定する顧客のキーを Exchange Online と Skype のビジネスまたは SharePoint Online と OneDrive のビジネスのまたは Office 365 のサポートされているすべてのサービスに関係なく、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p111">Complete these tasks in Azure Key Vault in order to set up Customer Key for Office 365. You will need to complete these steps regardless of whether you intend to set up Customer Key for Exchange Online and Skype for Business or SharePoint Online and OneDrive for Business or for all supported services in Office 365.</span></span>
  
### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="fd9b8-158">2 つの新しい Azure サブスクリプションを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-158">Create two new Azure subscriptions</span></span>
<span data-ttu-id="fd9b8-159"><a name="Create2newsubs"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-159"></span></span>

<span data-ttu-id="fd9b8-p112">Azure の 2 つのサブスクリプションは、お客様のキーの必要があります。最善の方法としては、顧客のキーを使用するための新しい Azure サブスクリプションを作成することをお勧めします。Azure のキーのヴォールト ・ キーは同じ Azure Active Directory (AAD) テナントのアプリケーションの承認のみことができます、DEPs を割り当てられる Office 365 の組織で使用される同じ Azure AD テナントを使用して新しいサブスクリプションを作成する必要があります。たとえば、職場、学校、Office 365 の組織のグローバル管理者特権を持つアカウントを使用しています。詳細な手順は、[組織としての Azure にサインアップする](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p112">Two Azure subscriptions are required for Customer Key. As a best practice, Microsoft recommends that you create new Azure subscriptions for use with Customer Key. Azure Key Vault keys can only be authorized for applications in the same Azure Active Directory (AAD) tenant, you must create the new subscriptions using the same Azure AD tenant used with your Office 365 organization where the DEPs will be assigned. For example, using your work or school account that has global administrator privileges in your Office 365 organization. For detailed steps, see [Sign up for Azure as an organization](https://azure.microsoft.com/en-us/documentation/articles/sign-up-organization/).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fd9b8-p113">顧客キーには、ポリシーごとにデータの暗号化 (DEP) の 2 つのキーが必要です。これを行うには、Azure サブスクリプションの 2 つを作成する必要があります。最善の方法としては、サブスクリプションごとに 1 つのキーを構成する組織の別のメンバーがあることをお勧めします。さらに、これら Azure サブスクリプションは、Office 365 の暗号化キーの管理にのみ使用してください。誤って、意図的に、または悪意のある削除、またはそれ以外の場合、担当するキーを mismanages、演算子のいずれかの場合に、組織を保護します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p113">Customer Key requires two keys for each data encryption policy (DEP). In order to achieve this, you must create two Azure subscriptions. As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription. In addition, these Azure subscriptions should only be used to administer encryption keys for Office 365. This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible. </span></span><br/> <span data-ttu-id="fd9b8-p114">顧客キーを使用してキー ヴォールトの Azure リソースを管理するためだけに使用されている新しい Azure サブスクリプションを設定することをお勧めします。組織の作成することができます Azure サブスクリプションの数には事実上制限はありません。これらのベスト プラクティスに従うと、顧客キーによって使用されるリソースを管理しながらヒューマン エラーの影響を最小限は。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p114">We recommend that you set up new Azure subscriptions that are solely used for managing Azure Key Vault resources for use with Customer Key. There is no practical limit to the number of Azure subscriptions that you can create for your organization. Following these best practices will minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span> 
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a><span data-ttu-id="fd9b8-173">Office 365 の顧客のキーをアクティブ化する要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-173">Submit a request to activate Customer Key for Office 365</span></span>
<span data-ttu-id="fd9b8-174"><a name="FastTrack"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-174"></span></span>

<span data-ttu-id="fd9b8-p115">Azure の手順を完了したら、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)のサービス リクエストを送信する必要があります。FastTrack web ポータルを通じて要求を送信した後マイクロソフトが提供した Azure キー ヴォールトの構成データおよび連絡先情報を確認します。組織の権限のある役員に関する提案フォームでの選択は重要な顧客キー登録の完了に必要です。フォームで選択した組織の責任者は失効し、顧客のキー データの暗号化ポリシーで使用されるすべてのキーを破棄するための要求の信頼性を保証するために使用されます。Exchange Online と Skype ビジネスと 2 回目の SharePoint Online およびビジネスのための OneDrive の顧客のキーをアクティブにするのには顧客のキーをアクティブにするのには、この手順を 1 回する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p115">Once you've completed the Azure steps, you'll need to submit an offer request in the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/). Once you have submitted a request through the FastTrack web portal, Microsoft verifies the Azure Key Vault configuration data and contact information you provided. The selections that you make in the offer form regarding the authorized officers of your organization is critical and necessary for completion of Customer Key registration. The officers of your organization that you select in the form will be the used to ensure the authenticity of any request to revoke and destroy all keys used with a Customer Key data encryption policy. You'll need to do this step once to activate Customer Key for Exchange Online and Skype for Business coverage and a second time to activate Customer Key for SharePoint Online and OneDrive for Business.</span></span>
  
<span data-ttu-id="fd9b8-180">顧客キーをアクティブにするという申し出を送信するには、この手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-180">To submit an offer to activate Customer Key, complete these steps:</span></span>
  
1. <span data-ttu-id="fd9b8-181">大域管理者アクセス許可を持つ、Office 365 の組織で、職場、学校のアカウントを使用すると、 [Microsoft FastTrack ポータル](https://fasttrack.microsoft.com/)にログインします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-181">Using a work or school account that has global administrator permissions in your Office 365 organization, log in to the [Microsoft FastTrack portal](https://fasttrack.microsoft.com/).</span></span>
    
2. <span data-ttu-id="fd9b8-182">ログオンしていることと**ダッシュ ボード**を参照します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-182">Once you're logged in, browse to the **Dashboard**.</span></span>
    
3. <span data-ttu-id="fd9b8-183">**用意されています**が、選択し、現在のサービスの一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-183">Choose **Offers**, and review the list of current offers.</span></span>
    
4. <span data-ttu-id="fd9b8-184">該当する提供サービスの**詳細**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-184">Choose **Learn More** for the offer that applies to you:</span></span> 
    
  - <span data-ttu-id="fd9b8-185">**オンラインの Exchange およびビジネス用の Skype:\*\*\*\*Exchange の顧客のキー**の提供の**詳細**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-185">**Exchange Online and Skype for Business:** Choose **Learn More** on the **Customer Key for Exchange** offer.</span></span> 
    
  - <span data-ttu-id="fd9b8-186">**オンラインの SharePoint とビジネスの OneDrive:\*\*\*\*SharePoint およびビジネスのための OneDrive の顧客のキー**の提供の**詳細**を選択しました。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-186">**SharePoint Online and OneDrive for Business:** Chose **Learn More** on the **Customer Key for SharePoint and OneDrive for Business** offer.</span></span> 
    
5. <span data-ttu-id="fd9b8-187">**特別提供の詳細**] ページで、**要求の作成**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-187">On the **Offer details** page, choose **Create Request**.</span></span>
    
6. <span data-ttu-id="fd9b8-p116">すべての該当する詳細情報と必要な情報提供のフォームに記入します。暗号化キーとデータの元に戻すこと、永続的な破壊を承認する承認する、選択した項目にする責任者の組織の特定の注意を払います。フォームが完了したら、**送信**を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p116">Fill out all applicable details and requested information on the offer form. Pay particular attention to your selections for which officers of your organization you want to authorize to approve the permanent and irreversible destruction of encryption keys and data. Once you've completed the form, choose **Submit**.</span></span>
    
    <span data-ttu-id="fd9b8-191">処理が完了するまでの 5 営業日後、Microsoft は、要求が通知されています。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-191">This process can take up to five business days once Microsoft has been notified of your request.</span></span>
    
7. <span data-ttu-id="fd9b8-192">必須の保持期間以下のセクションに進みます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-192">Continue on to the mandatory retention period section below.</span></span>
    
### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="fd9b8-193">必須の保持期間を使用するのには Azure サブスクリプションを登録します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-193">Register Azure subscriptions to use a mandatory retention period</span></span>
<span data-ttu-id="fd9b8-194"><a name="RegisterSubsforMRP"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-194"></span></span>

<span data-ttu-id="fd9b8-p117">暗号化キーのルートの一時的または永続的な損失は、支障をきたすまたはサービスの操作にも壊滅的なことができ、データの損失が発生することができます。このため、顧客のキーで使用するリソースには、強力な保護が必要があります。顧客キーで使用されているすべての Azure リソースは、既定の構成以外の保護メカニズムを提供します。Azure サブスクリプションは、タグ付けまたは即時かつ取消不能なキャンセルを回避する方法で登録できます。これは必須の保持期間の登録と呼ばれます。必須の保持期間の Azure サブスクリプションを登録するための手順には、Office 365 チームとの共同作業が必要です。このプロセスは、1 ~ 5 営業日かかることができます。以前は、これとも呼ば [キャンセルの操作を行います] です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p117">The temporary or permanent loss of root encryption keys can be very disruptive or even catastrophic to service operation and can result in data loss. For this reason, the resources used with Customer Key require strong protection. All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration. Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation. This is referred to as registering for a mandatory retention period. The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Office 365 team. This process can take from one to five business days. Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="fd9b8-203">Office 365 チームに問い合わせる前に顧客のキーを使用する Azure サブスクリプションごとに次の手順を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-203">Before contacting the Office 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key:</span></span>
  
1. <span data-ttu-id="fd9b8-p118">Azure PowerShell で Azure サービスにログインします。手順については、 [Azure の PowerShell を使用してログイン](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p118">Log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
2. <span data-ttu-id="fd9b8-206">必須の保持期間を使用するのには、サブスクリプションを登録するのにはレジスタ AzureRmProviderFeature コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-206">Run the Register-AzureRmProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span>
    
  ```
  Register-AzureRmProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
  ```

3. <span data-ttu-id="fd9b8-p119">プロセスを終了するのには Microsoft に問い合わせてください。SharePoint およびビジネスのチームの OneDrive は、 [spock@microsoft.com](mailto:spock@microsoft.com)をにお問い合わせください。Exchange Online は、ビジネスの Skype [exock@microsoft.com](mailto:exock@microsoft.com)をにお問い合わせください。サービス レベル契約 (SLA) 必須の保持期間を使用するのには、サブスクリプションを登録するこのプロセスの完了には、マイクロソフトが通知を受け取る (および検証された) した後、5 営業日以内にします。電子メールに次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p119">Contact Microsoft to have the process finalized. For the SharePoint and OneDrive for Business team, contact [spock@microsoft.com](mailto:spock@microsoft.com). For Exchange Online and Skype for Business, contact [exock@microsoft.com](mailto:exock@microsoft.com). The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period. Include the following in your email:</span></span>
    
    <span data-ttu-id="fd9b8-212">**件名**: 顧客のキーの\< *、テナントの完全修飾ドメイン名*\></span><span class="sxs-lookup"><span data-stu-id="fd9b8-212">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span> 
    
    <span data-ttu-id="fd9b8-213">**本文**: 必須の保持期間の終了するサブスクリプションの Id です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-213">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span> 
    
4. <span data-ttu-id="fd9b8-214">登録が完了しているマイクロソフトからの通知が表示されたら、次のように Get AzureRmProviderFeature コマンドレットを実行することによって、登録の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-214">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzureRmProviderFeature cmdlet as follows:</span></span>
    
  ```
  Get-AzureRmProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
  ```

5. <span data-ttu-id="fd9b8-215">Get AzureRmProviderFeature コマンドレットの**登録の状態**プロパティが**登録されている**の値を返すことを確認した後、プロセスを完了するのには次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-215">After verifying that the **Registration State** property from the Get-AzureRmProviderFeature cmdlet returns a value of **Registered**, run the following command to complete the process:</span></span>
    
  ```
  Register-AzureRmResourceProvider -ProviderNamespace "Microsoft.KeyVault"
  ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="fd9b8-216">サブスクリプションごとにプレミアムの Azure キー ヴォールトを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-216">Create a premium Azure Key Vault in each subscription</span></span>
<span data-ttu-id="fd9b8-217"><a name="CreateKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-217"></span></span>

<span data-ttu-id="fd9b8-218">キーのボルトを作成する手順は、 [Azure のキーのボルトを使うにあたって](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)をインストールして Azure PowerShell を起動する、Azure サブスクリプションに接続する、リソース グループを作成するおよび主要ボルトを作成することでに記載されていますリソース グループです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-218">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="fd9b8-p120">SKU を選択する必要があります主要ボルトを作成する場合: 標準またはプレミアムのいずれかです。標準の SKU のハードウェア セキュリティ モジュール (HSM) キーの保護はありません - ソフトウェアで保護する Azure キー ヴォールト ・ キーを使うと、プレミアム SKU キー ヴォールト ・ キーの保護に Hsm を使用できます。プレミアム SKU のみを使用することを強くお勧めしているにもかかわらず、顧客キーはいずれかの SKU を使用するキーのボルトを受け入れます。いずれかの種類のキー操作のコストは、コストの唯一の違いが HSM で保護されたキーはごとに 1 か月あたりのコストであるためです。詳細については、[キーのボルトの価格](https://azure.microsoft.com/pricing/details/key-vault/)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p120">When you create a key vault, you must choose a SKU: either Standard or Premium. The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys. Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU. The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key. See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="fd9b8-224">プレミアム SKU キー ボルトと HSM で保護されたキーを使用して、本番データとだけ標準的な SKU キー ボルトとキーを使用して、テストと検証のために。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-224">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span> 
  
<span data-ttu-id="fd9b8-p121">顧客キーを使用すると、Office 365 サービスごとに作成した 2 つの Azure サブスクリプションの各主要ボルトを作成します。たとえば、Exchange Online とはビジネスのみまたは SharePoint Online の Skype とビジネスだけの OneDrive、ボルトの 1 つだけのペアを作成します。Exchange Online と SharePoint Online の両方の顧客のキーを有効にするのには、キーの貯蔵庫の 2 つのペアを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p121">For each Office 365 service with which you will use Customer Key, create a key vault in each of the two Azure subscriptions that you created. For example, for Exchange Online and Skype for Business only or SharePoint Online and OneDrive for Business only, you will create only one pair of vaults. To enable Customer Key for both Exchange Online and SharePoint Online, you will create two pairs of key vaults.</span></span>
  
<span data-ttu-id="fd9b8-p122">関連付けるボルト DEP の使用目的を表すキーのボルトの名前付け規則を使用します。命名規則に関する推奨事項はベスト ・ プラクティスの項を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p122">Use a naming convention for key vaults that reflects the intended use of the DEP with which you will associate the vaults. See the Best Practices section below for naming convention recommendations.</span></span>
  
<span data-ttu-id="fd9b8-p123">1 組の独立した一連のデータの暗号化ポリシーごとにボルトを作成します。オンラインの Exchange のメールボックスにポリシーを割り当てるとしてデータの暗号化ポリシーのスコープが選択されます。メールボックスが割り当てられている 1 つだけのポリシーを持つことができ、50 台までのポリシーを作成することができます。SharePoint Online には、ポリシーのスコープは、地理的位置、または地域で組織内のデータのすべてです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p123">Create a separate, paired set of vaults for each data encryption policy. For Exchange Online, the scope of a data encryption policy is chosen by you when you assign the policy to mailbox. A mailbox can have only one policy assigned, and you can create up to fifty policies. For SharePoint Online the scope of a policy is all of the data within an organization in a geographic location, or geo.</span></span>
  
<span data-ttu-id="fd9b8-p124">ボルトのキーの作成は、(ただし、非常に小さい)、キーのボルトがストレージ容量を必要し、ログイン、キーのボルトが有効な場合も生成保存されているデータなので、Azure のリソース グループの作成が必要です。ベスト プラクティスとしては、一連の関連するすべての顧客キー リソースを管理する管理者の配置の管理と、各リソース グループを管理するために個別の管理者を使用してをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p124">The creation of key vaults also requires the creation of Azure resource groups, since key vaults need storage capacity (though very small) and Key Vault logging, if enabled, also generates stored data. As a best practice Microsoft recommends using separate administrators to manage each resource group, with the administration aligned with the set of administrators that will manage all related Customer Key resources.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fd9b8-p125">可用性を最大化するのには、Office 365 サービスに近い地域でキー、ボルトがあります。たとえば、Exchange Online 組織は、北アメリカでは、北米でのキー、ボルトを配置します。Exchange Online 組織は、ヨーロッパでは場合、は、ヨーロッパのキー、ボルトを配置します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p125">To maximize availability, your key vaults should be in regions close to your Office 365 service. For example, if your Exchange Online organization is in North America, place your key vaults in North America. If your Exchange Online organization is in Europe, place your key vaults in Europe.</span></span><br/><span data-ttu-id="fd9b8-p126">キーのボルトに共通のプレフィックスを使用し、使用の省略形およびボルトのキーとキーの範囲が含まれます (contoso 社の SharePoint サービスが可能な 1 組の名前の北米でのボルトの位置は、Contoso O365SP NA VaultA1 用など、Contoso O365SP-「na」と VaultA2。ボルトの名前は、目的の名前は既に Azure の他の顧客が要求している場合に、目的の名前のバリエーションを実行する必要がありますので、Azure 内のグローバル一意識別の文字列です。2017年 7 月年ヴォールト ・名前は変更できません、ため、セットアップを記述した計画があり、プランが正しく実行されたことを確認するのには 2 番目のユーザーを使用するが最適です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p126">Use a common prefix for key vaults, and include an abbreviation of the use and scope of the key vault and keys (e.g., for the Contoso SharePoint service where the vaults will be located in North America, a possible pair of names is Contoso-O365SP-NA-VaultA1 and Contoso-O365SP-NA-VaultA2. Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers. As of July 2017 vault names cannot be changed, so a best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span><br/><span data-ttu-id="fd9b8-p127">可能な場合は、ペアになっていない地域で、ボルトを作成します。Azure の一対の領域は、サービスの障害ドメイン間で高可用性を提供します。したがって、地域のペアは互いのバックアップ領域として。これは、1 つの領域に配置される Azure のリソースが自動的にペアリングされている地域によってフォールト トレランスを獲得することを意味します。このため、場所、地域では、ペアは、可用性の 2 つの領域の合計のみを使用していることを意味する DEP で使用される 2 つのボルトの領域を選択します。ほとんどの地域では、まだ非対応の地域を選択することがないために 2 つの領域をあるだけです。可能な場合、dep が原因で使用される 2 つのボルトの 2 つのペアになっていない領域を選択します。可用性の 4 つの領域の合計からこれを利用できます。詳細についてを参照してください[ビジネス継続性/災害復旧 (BCDR): Azure 対応の地域](https://docs.microsoft.com/azure/best-practices-availability-paired-regions)の地域のペアの現在のリストです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p127">If possible, create your vaults in non-paired regions. Paired Azure regions provide high availability across service failure domains. Therefore, regional pairs can be thought of as each other's backup region. This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region. For this reason, choosing regions for two vaults used in a DEP where the regions are paired means that only a total of two regions of availability are in use. Most geographies only have two regions, so it's not yet possible to select non-paired regions. If possible, choose two non-paired regions for the two vaults used with a DEP. This benefits from a total of four regions of availability. For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span> 
  
### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="fd9b8-251">各キーのボルトにアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="fd9b8-251">Assign permissions to each key vault</span></span>
<span data-ttu-id="fd9b8-252"><a name="KeyVaultPerms"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-252"></span></span>

<span data-ttu-id="fd9b8-p128">各キーのボルトの実装によって、お客様のキーのアクセス許可の 3 つの異なるセットを定義する必要があります。たとえば、次の各アクセス許可の 1 つのセットを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p128">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation. For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="fd9b8-p129">組織のキー、ボルトの日常的な管理を実行する**キー ヴォールトの管理者**です。これらのタスクのバックアップ、作成、取得、] ボックスの一覧をインポートします。 および復元します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p129">**Key vault administrators** that will perform day-to-day management of your key vault for your organization. These tasks include backup, create, get, import, list, and restore.</span></span> 
    
    > [!IMPORTANT]
    > <span data-ttu-id="fd9b8-p130">キー ヴォールトの管理者に割り当てられたアクセス許可のセットでは、キーを削除するアクセス許可は含まれません。これは意図的なものと、重要なプラクティスです。暗号化キーを削除する通常行わないと、データが破壊されるため永続的に行うためです。最善の方法としてはこのアクセス権を付与キー ヴォールトの管理者に既定でします。キー ヴォールトの貢献者にこれを予約し、のみに割り当てることを短期的に管理者の影響を明確に理解を理解するとします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p130">The set of permissions assigned to key vault administrators does not include the permission to delete keys. This is intentional and an important practice. Deleting encryption keys is not typically done, since doing so permanently destroys data. As a best practice, do not grant this permission to key vault administrators by default. Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span> 
  
    <span data-ttu-id="fd9b8-p131">Office 365 組織内のユーザーにこれらのアクセス許可を割り当てるには Azure PowerShell で Azure サービスにログインします。手順については、 [Azure の PowerShell を使用してログイン](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p131">To assign these permissions to a user in your Office 365 organization, log in to your Azure subscription with Azure PowerShell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps?view=azurermps-4.3.1).</span></span>
    
- <span data-ttu-id="fd9b8-264">必要なアクセス許可を割り当てるセット AzureRmKeyVaultAccessPolicy コマンドレットを実行するには。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-264">Run the Set-AzureRmKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
  -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
  ```

  <span data-ttu-id="fd9b8-265">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-265">For example:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
  ```

- <span data-ttu-id="fd9b8-p132">自体ように Azure キー ボルトへのアクセス許可が変更可能な**キーのボルトの貢献者**。従業員のままにして、チームに参加、または非常にまれな状況で、キーのヴォールティング管理者正当に必要があることを削除するか、キーを復元するためのアクセス許可と、これらのアクセス許可を変更する必要があります。この一連のキー ヴォールト ・投稿者のニーズがキー、ボルト、**寄稿者**の役割を与えられます。Azure のリソース マネージャーを使用して、このロールを割り当てることができます。詳細な手順は、 [Use Role-Based、Azure サブスクリプションのリソースへのアクセスを管理するためのアクセス制御](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure)を参照してください。サブスクリプションを作成した管理者は、寄稿者の役割を他の管理者を割り当てる機能だけでなく暗黙的に、このアクセス権を持ちます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p132">**Key vault contributors** that can change permissions on the Azure Key Vault itself. You'll need to change these permissions as employees leave or join your team, or in the extremely rare situation that the key vault administrators legitimately need permission to delete or restore a key. This set of key vault contributors needs to be granted the **Contributor** role on your key vault. You can assign this role by using Azure Resource Manager. For detailed steps, see [Use Role-Based Access Control to manage access to your Azure subscription resources](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure). The administrator who creates a subscription has this access implicitly, as well as the ability to assign other administrators to the Contributor role.</span></span>
    
- <span data-ttu-id="fd9b8-p133">Exchange Online と Skype をビジネスの顧客キーを使用する場合は、Exchange Online と Skype のためのキーのボルトを使用して、ビジネスのために Office 365 にアクセス権を付与する必要があります。同様に、SharePoint Online および OneDrive とビジネスの顧客キーを使用する場合は、SharePoint Online と OneDrive のためのキーのボルトを使用して、ビジネスのために Office 365 にアクセス許可を追加する必要があります。Office 365 にアクセス許可を与える、次の構文を使用して**セット AzureRmKeyVaultAccessPolicy**コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p133">If you intend to use Customer Key with Exchange Online and Skype for Business, you need to give permission to Office 365 to use the key vault on behalf of Exchange Online and Skype for Business. Likewise, if you intend to use Customer Key with SharePoint Online and OneDrive for Business, you need to add permission for the Office 365 to use the key vault on behalf of SharePoint Online and OneDrive for Business. To give permission to Office 365, run the **Set-AzureRmKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span> 
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
  ```

    <span data-ttu-id="fd9b8-275">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-275">Where:</span></span>
    
  - <span data-ttu-id="fd9b8-276">*vaultname*は、作成したキーのボルトの名前です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-276">*vaultname* is the name of the key vault you created.</span></span> 
    
  - <span data-ttu-id="fd9b8-277">Exchange Online は、ビジネスの Skype と*Office 365 の appID*が置き換えられること`00000002-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="fd9b8-277">For Exchange Online and Skype for Business, replace  *Office 365 appID* with `00000002-0000-0ff1-ce00-000000000000`</span></span>
    
  - <span data-ttu-id="fd9b8-278">SharePoint Online をビジネスのための OneDrive と*Office 365 の appID*が置き換えられる`00000003-0000-0ff1-ce00-000000000000`</span><span class="sxs-lookup"><span data-stu-id="fd9b8-278">For SharePoint Online and OneDrive for Business, replace  *Office 365 appID* with `00000003-0000-0ff1-ce00-000000000000`</span></span>
    
  <span data-ttu-id="fd9b8-279">例: は、Exchange のオンラインおよびビジネス用の Skype のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-279">Example: Setting permissions for Exchange Online and Skype for Business:</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
  ```

  <span data-ttu-id="fd9b8-280">例: SharePoint Online およびビジネスのための OneDrive のアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-280">Example: Setting permissions for SharePoint Online and OneDrive for Business</span></span>
    
  ```
  Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
  -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="fd9b8-281">有効にして、キー、ボルトのソフトの削除を確認</span><span class="sxs-lookup"><span data-stu-id="fd9b8-281">Enable and then confirm soft delete on your key vaults</span></span>
<span data-ttu-id="fd9b8-282"><a name="SoftDelete"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-282"></span></span>

<span data-ttu-id="fd9b8-p134">キーをすばやく回復できますが、ときに、誤ってまたは悪意のある削除されたキーのための拡張サービス障害が発生する可能性は低くしています。呼ばれるソフト削除では、お客様のキーを使用して、キーを使用する前に、この構成を有効にする必要があります。ソフト削除の有効化を使用すると、削除の 90 日以内にバックアップから復元することがなくキーまたはボルトを回復します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p134">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys. You need to enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key. Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="fd9b8-286">キー、ボルトのソフトの削除を有効にするには、これらの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-286">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="fd9b8-p135">Windows Powershell で Azure サービスにログインします。手順については、 [Azure の PowerShell を使用してログイン](https://docs.microsoft.com/powershell/azure/authenticate-azureps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p135">Log in to your Azure subscription with Windows Powershell. For instructions, see [Log in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>
    
2. <span data-ttu-id="fd9b8-p136">[Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault)コマンドレットを実行します。この例では、 *vaultname*は、ソフトの削除を有効にするキーのボルトの名です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p136">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/azurerm.keyvault/get-azurermkeyvault) cmdlet. In this example, *vaultname* is the name of the key vault for which you are enabling soft delete:</span></span> 
    
   ```
   $v = Get-AzureRmKeyVault -VaultName <vaultname>
   $r = Get-AzureRmResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzureRmResource -ResourceId $r.ResourceId -Properties $r.Properties
   ``` 
    
3. <span data-ttu-id="fd9b8-p137">ソフト削除は**Get AzureRmKeyVault**コマンドレットを実行してキーのボルトの構成を確認します。ソフトの削除が正しく設定されてキーのボルトの場合、ソフトは有効を削除しますか。プロパティは、 **True**の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p137">Confirm soft delete is configured for the key vault by running the **Get-AzureRmKeyVault** cmdlet. If soft delete is configured properly for the key vault, then the  Soft Delete Enabled? property returns a value of **True**:</span></span> 
    
   ```
   Get-AzureRmKeyVault -VaultName <vaultname> | fl
   ```

   
    
### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="fd9b8-293">各キーのボルトにするか、作成またはキーをインポートすることでキーを追加します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-293">Add a key to each key vault either by creating or importing a key</span></span>
<span data-ttu-id="fd9b8-294"><a name="AddKeystoKeyVault"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-294"></span></span>

<span data-ttu-id="fd9b8-p138">Azure キーのボルトにキーを追加するのには 2 つの方法があります。キーを作成するにはキーのボルトで直接、またはキーをインポートすることができます。キーの保管場所に直接キーを作成する方が、簡単なキーを生成する方法を完全に制御を提供するキーをインポートするときに。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p138">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key. Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span>
  
<span data-ttu-id="fd9b8-297">キーをボルトに直接キーを作成するには、次のように[追加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-297">To create a key directly in your key vault, run the [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Add-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="fd9b8-298">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-298">Where:</span></span>
  
-  <span data-ttu-id="fd9b8-299">*vaultname*は、主キーを作成するボルトの名前です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-299">*vaultname*  is the name of the key vault in which you want to create the key.</span></span> 
    
-  <span data-ttu-id="fd9b8-300">*キー名*は、新しいキーを指定する名前です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-300">*keyname*  is the name you want to give the new key.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="fd9b8-p139">前述のキーの貯蔵庫のような名前付け規則を使用して、キーの名前を指定します。この方法では、キーの名前のみを表示するツールでは、文字列は、自己言及的な。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p139">Name keys using a similar naming convention as described above for key vaults. This way, in tools that show only the key name, the string is self-describing.</span></span> 
  
- <span data-ttu-id="fd9b8-303">HSM にキーを保護する場合は、**ソフトウェア**を指定することは、 **HSM**を_コピー先_のパラメーターの値として指定を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-303">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the  _Destination_ parameter, otherwise, specify **Software**.</span></span>
    
<span data-ttu-id="fd9b8-304">たとえば、次のように使用します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-304">For example,</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="fd9b8-305">キーをボルトに直接には、キーをインポートするには、Thales nShield ハードウェア セキュリティ モジュールがある必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-305">To import a key directly into your key vault, you need to have a Thales nShield Hardware Security Module.</span></span>
  
<span data-ttu-id="fd9b8-306">組織によっては、キーと、この provenance を確立するには、このアプローチを選択する方法には、次も用意されています。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-306">Some organizations prefer this approach to establish the provenance of their keys, and the this method also provides the following:</span></span>
  
- <span data-ttu-id="fd9b8-307">インポートに使用するツールセットは、Thales を生成するキーの暗号化に使用されるキー交換キー (KEK) がエクスポート可能ではないことの証明が含まれています、Thales によって製造された正規品である HSM 内で生成されるが。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-307">The toolset used for import includes attestation from Thales that the Key Exchange Key (KEK) that is used to encrypt the key you generate is not exportable and is generated inside a genuine HSM that was manufactured by Thales.</span></span>
    
- <span data-ttu-id="fd9b8-p140">ツールセットには、Thales の Thales 製の正規品である HSM にキー ヴォールトの Azure のセキュリティ環境が生成されたもの証明が含まれています。この証明は、マイクロソフトが本物である Thales のハードウェアを使用しても自分に証明します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p140">The toolset includes attestation from Thales that the Azure Key Vault security world was also generated on a genuine HSM manufactured by Thales. This attestation proves to you that Microsoft is also using genuine Thales hardware.</span></span>
    
<span data-ttu-id="fd9b8-p141">上記の attestations が必要なかどうかを決定するセキュリティ グループを確認します。キーの設置型を作成し、キー、ボルトにインポートする手順の詳細を[生成し、Azure キー ヴォールト用の HSM で保護されたキーを転送する方法](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)を参照してください。各キーの保管場所にキーを作成するのにには、Azure の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p141">Check with your security group to determine if the above attestations are required. For detailed steps to create a key on-premises and import it into your key vault, see [How to generate and transfer HSM-protected keys for Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/). Use the Azure instructions to create a key in each key vault.</span></span>
  
### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="fd9b8-313">キーの回復レベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-313">Check the recovery level of your keys</span></span>
<span data-ttu-id="fd9b8-314"><a name="CheckKeyRecoveryLevel"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-314"></span></span>

<span data-ttu-id="fd9b8-p142">Office 365 では、キー ヴォールトの Azure サブスクリプションをキャンセルしないでに設定されていると、お客様のキーに使用するキーがあるソフトの削除が有効になっている必要があります。これを確認するには、キーの回復レベルを見る。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p142">Office 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled. You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="fd9b8-317">Azure の PowerShell で、キーの回復レベルを確認するのには次のように Get AzureKeyVaultKey コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-317">To check the recovery level of a key, in Azure PowerShell, run the Get-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname>).Attributes 
```

<span data-ttu-id="fd9b8-318">_リカバリ ・ レベル_のプロパティには、**回復可能な + ProtectedSubscription**の値以外の値が返された場合は、このトピックを参照し、すべてのサブスクリプションをキャンセルしないでリストに配置する手順を従っていることを確認する必要があり、あるソフト削除の各キー、ボルトの上を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-318">If the  _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this topic and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you have soft delete enabled on each of your key vaults.</span></span>
  
### <a name="backup-azure-key-vault"></a><span data-ttu-id="fd9b8-319">Azure キー ヴォールトをバックアップ</span><span class="sxs-lookup"><span data-stu-id="fd9b8-319">Backup Azure Key Vault</span></span>
<span data-ttu-id="fd9b8-320"><a name="BackupAzureKeyVaultkeys"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-320"></span></span>

<span data-ttu-id="fd9b8-p143">すぐ後に作成または変更しても、キーをバックアップを実行し、バックアップ、オンラインとオフラインの両方のコピーを格納します。オフライン コピーする必要があります接続されていないネットワークなど、安全または商用ストレージの物理的な施設にします。バックアップのコピーを少なくとも 1 つは、災害発生時にアクセスできる場所に格納されている必要があります。バックアップの blob は、キーのヴォールト ・ キーまたはする必要が完全に破棄しなくなる場合それ以外の場合、キー マテリアルを復元する唯一の手段です。Azure キー ボルトの外部に、Azure のキーのボルトにインポートされたキーの対象とならないバックアップとして外部キーを使用して顧客のキー、キーを使用するのに必要なメタデータが存在しないためです。顧客キーを使用して、リストア ・ オペレーションの Azure キー ヴォールトから作成されたバックアップのみを使用できます。したがって、キーをアップロードまたは作成したら、Azure キー ヴォールトのバックアップが行われることが重要です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p143">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline. Offline copies should not be connected to any network, such as in a physical safe or commercial storage facility. At least one copy of the backup should be stored in a location that will be accessible in the event of a disaster. The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable. Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key. Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key. Therefore, it is essential that a backup of Azure Key Vault be made once a key is uploaded or created.</span></span>
  
<span data-ttu-id="fd9b8-328">Azure キー ヴォールト ・ キーのバックアップを作成するには、次のように[バックアップ AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-328">To create a backup of an Azure Key Vault key, run the [Backup-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Backup-AzureKeyVaultKey) cmdlet as follows:</span></span>
```
Backup-AzureKeyVaultKey -VaultName <vaultname> -Name <keyname> 
-OutputFile <filename .backup>

```

<span data-ttu-id="fd9b8-329">出力ファイルがサフィックスを使用することを確認`.backup`。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-329">Ensure that your output file uses the suffix  `.backup`.</span></span>
  
<span data-ttu-id="fd9b8-p144">このコマンドレットの結果の出力ファイルは暗号化されており、Azure キー ヴォールト以外では使用できません。バックアップは、バックアップが行われた Azure サブスクリプションにのみ復元できます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p144">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault. The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
> [!TIP]
> <span data-ttu-id="fd9b8-p145">出力ファイルでは、ボルトの名前とキーの名前の組み合わせを選択します。これにより、ファイル名は自己記述形式します。それも使用すれば、バックアップ ファイル名が競合していないこと。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p145">For the output file, choose a combination of your vault name and key name. This will make the file name self-describing. It will also ensure that backup file names do not collide.</span></span> 
  
<span data-ttu-id="fd9b8-335">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-335">For example:</span></span>
  
```
Backup-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="fd9b8-336">Azure キーの格納域の構成の設定を検証します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-336">Validate Azure Key Vault configuration settings</span></span>
<span data-ttu-id="fd9b8-337"><a name="Validateconfiguration"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-337"></span></span>

<span data-ttu-id="fd9b8-p146">キーを使用して、DEP で前に検証を実行することはオプションですが、強くお勧めです。具体的には、このトピックで説明されていないその他のキーとボルトを設定する手順を使用する場合、顧客のキーを構成する前に、Azure キー ヴォールト ・ リソースの稼働状態を検証する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p146">Performing validation before using keys in a DEP is optional, but highly recommended. In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="fd9b8-340">キーがある、wrapKey、および unwrapKey の操作が有効になっていることを確認するには。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-340">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="fd9b8-341">次のように、 [Get AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-341">Run the [Get-AzureRmKeyVault](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureRmKeyVault) cmdlet as follows:</span></span> 
  
```
Get-AzureRMKeyVault -VaultName <vaultname>
```

<span data-ttu-id="fd9b8-p147">出力では、適切なアクセス ポリシーおよび Exchange のオンライン id (GUID) または SharePoint Online id (GUID) を確認します。上のアクセス許可の 3 つのすべてはする必要がありますキーを [アクセス許可表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p147">In the output, look for the Access Policy and for the Exchange Online identity (GUID) or the SharePoint Online identity (GUID) as appropriate. All three of the above permissions must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="fd9b8-344">アクセス ポリシーの構成が正しくない場合、次のようにセット AzureRmKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-344">If the access policy configuration is incorrect, run the Set-AzureRmKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

<span data-ttu-id="fd9b8-345">たとえば、Exchange Online とビジネス用の Skype。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-345">For example, for Exchange Online and Skype for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="fd9b8-346">たとえば、SharePoint Online およびビジネスのための OneDrive。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-346">For example, for SharePoint Online and OneDrive for Business:</span></span>
  
```
Set-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName TBD
```

<span data-ttu-id="fd9b8-347">次のように、 [Get AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey)コマンドレットを実行する、キーの有効期限が設定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-347">To verify that an expiration date is not set for your keys run the [Get-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Get-AzureKeyVaultKey) cmdlet as follows:</span></span> 
  
```
Get-AzureKeyVaultKey -VaultName <vaultname> 
```

<span data-ttu-id="fd9b8-p148">顧客キーで、有効期限の切れたキーを使用することはできませんし、有効期限の切れたキーを使用して実行しようとする操作は失敗し、サービスの停止が発生する可能性があります。顧客キーに使用されるキーに有効期限がないことを強くお勧めします。有効期限の日付、セット、削除することはできませんが、別の日付に変更することができます。キーを使用する有効期限を設定する場合は、12/31/9999 に有効期限の値を変更します。有効期限の日付を使用してキーは、12/31/9999 が Office 365 の検証を通過しない以外の日付に設定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p148">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail, and possibly result in a service outage. We strongly recommend that keys used with Customer Key do not have an expiration date. An expiration date, once set, cannot be removed, but can be changed to a different date. If a key must be used that has an expiration date set, change the expiration value to 12/31/9999. Keys with an expiration date set to a date other than 12/31/9999 will not pass Office 365 validation.</span></span>
  
<span data-ttu-id="fd9b8-353">12/31/9999 以外の値に設定されている有効期限の日付を変更するには、次のように[セット AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-353">To change an expiration date that has been set to any value other than 12/31/9999, run the [Set-AzureKeyVaultKeyAttribute](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Set-AzureKeyVaultKeyAttribute) cmdlet as follows:</span></span> 
  
```
Set-AzureKeyVaultKeyAttribute -VaultName <vaultname> -Name <keyname> 
-Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> <span data-ttu-id="fd9b8-354">顧客キーで使用する暗号化キーの有効期限を設定しません。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-354">Don't set expiration dates on encryption keys you use with Customer Key.</span></span> 
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="fd9b8-355">各 Azure キー ヴォールト ・ キーの URI を取得します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-355">Obtain the URI for each Azure Key Vault key</span></span>
<span data-ttu-id="fd9b8-356"><a name="GetKeyURI"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-356"></span></span>

<span data-ttu-id="fd9b8-p149">キー、ボルトを設定するのには Azure 内のすべての手順を完了すると、キーを追加、各キーの保管場所にキーの URI を取得するのには次のコマンドを実行します。これらを使用する必要があります。 Uri を作成して後で、それぞれの DEP を割り当てるときは、安全な場所でこの情報を保存するようにします。各キーのボルトには、このコマンドを実行することを忘れないでください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p149">Once you have completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault. You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place. Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="fd9b8-360">Azure PowerShell: の</span><span class="sxs-lookup"><span data-stu-id="fd9b8-360">In Azure PowerShell:</span></span>
  
```
(Get-AzureKeyVaultKey -VaultName <vaultname>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="fd9b8-361">Office 365: Exchange のオンラインであり、ビジネス用の Skype の顧客のキーを設定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-361">Office 365: Setting up Customer Key for Exchange Online and Skype for Business</span></span>
<span data-ttu-id="fd9b8-362"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-362"></span></span>

<span data-ttu-id="fd9b8-p150">作業を開始する前に、Azure キー ヴォールトを設定するために必要なタスクを完了したことを確認します。については、 [Azure キー ヴォールトおよび顧客キー用の Microsoft FastTrack でタスクの実行](controlling-your-data-using-customer-key.md#AzureSteps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p150">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="fd9b8-365">Exchange オンラインであり、ビジネスの Skype の顧客のキーを設定するには、Windows PowerShell を Exchange Online にリモートで接続して、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-365">To set up Customer Key for Exchange Online and Skype for Business, you will need to perform these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a><span data-ttu-id="fd9b8-366">ビジネスの Exchange Online と Skype を使用するためのデータ暗号化のポリシー (DEP) の作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-366">Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business</span></span>
<span data-ttu-id="fd9b8-367"><a name="CreateDEP4EXOSkype"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-367"></span></span>

<span data-ttu-id="fd9b8-p151">DEP は、Azure のキーの保管場所に保存されているキーのセットに関連付けられます。DEP は、Office 365 にメールボックスを割り当てます。Office 365 メールボックスを暗号化するために、ポリシーで指定されたキーが使用されます。DEP を作成するには、キーのボルトの Uri が以前のバージョンを取得する必要があります。手順については、[各 Azure キー ヴォールト ・ キーの URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p151">A DEP is associated with a set of keys stored in Azure Key Vault. You assign a DEP to a mailbox in Office 365. Office 365 will then use the keys identified in the policy to encrypt the mailbox. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="fd9b8-p152">忘れないでください!DEP を作成するときは、2 つの異なる Azure キー ヴォールト内に存在する 2 つのキーを指定します。これらのキーは、geo の冗長性を確保するのには 2 つの独立した Azure 領域に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p152">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="fd9b8-376">DEP を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-376">To create the DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="fd9b8-377">職場または学校のアカウントを Office 365 組織で Windows PowerShell を開き、次のコマンドを実行している[Exchange のオンライン PowerShell への接続](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx)をグローバル管理者のアクセス許可を持つを使用して、ローカル コンピューター上です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-377">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [connect to Exchange Online PowerShell](https://technet.microsoft.com/en-us/library/jj984289%28v=exchg.160%29.aspx) by opening Windows PowerShell and running the following command.</span></span> 
    
   ```
   $UserCredential = Get-Credential
   ```

2. <span data-ttu-id="fd9b8-378">Windows PowerShell の資格情報の要求] ダイアログ ボックスで、作業時間を入力またはアカウント情報の学校 **[ok]** を次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-378">In the Windows PowerShell Credential Request dialog box, enter your work or school account information, click **OK**, and then enter the following command.</span></span> 
    
   ```
   $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
   ```

3. <span data-ttu-id="fd9b8-379">次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-379">Run the following command.</span></span>
    
   ```
   Import-PSSession $Session
   ```

4. <span data-ttu-id="fd9b8-380">DEP を作成するには、次のコマンドを入力して新規 DataEncryptionPolicy コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-380">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>
    
   ```
   New-DataEncryptionPolicy -Name <PolicyName> -Description "PolicyDescription " -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="fd9b8-381">詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-381">Where:</span></span>
    
   -  <span data-ttu-id="fd9b8-p153">*グループ*は、ポリシーを使用する名前です。名は、スペースを含めることはできません。たとえば、USA_mailboxes です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p153">*PolicyName*  is the name you want to use for the policy. Names cannot contain spaces. For example, USA_mailboxes.</span></span> 
    
   -  <span data-ttu-id="fd9b8-p154">*許可*を忘れないように、ポリシーのポリシーのユーザー フレンドリな説明です。説明にスペースを含めることができます。たとえば、アメリカ合衆国およびその領土内のメールボックス用のキーをルートします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p154">*PolicyDescription*  is a user friendly description of the policy that will help you remember what the policy is for. You can include spaces in the description. For example, Root key for mailboxes in USA and its territories.</span></span> 
    
   -  <span data-ttu-id="fd9b8-p155">*KeyVaultURI1*は、URI のポリシーでは、最初のキーです。たとえば、 https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p155">*KeyVaultURI1*  is the URI for the first key in the policy. For example, https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01.</span></span> 
    
   -  <span data-ttu-id="fd9b8-p156">*KeyVaultURI2*は、ポリシーでは、2 番目のキーの URI です。たとえば、 https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02。コンマとスペース 2 つの Uri を分離します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p156">*KeyVaultURI2*  is the URI for the second key in the policy. For example, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02. Separate the two URIs by a comma and a space.</span></span> 
    
   <span data-ttu-id="fd9b8-393">例:</span><span class="sxs-lookup"><span data-stu-id="fd9b8-393">Example:</span></span>
  
   ```
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="fd9b8-394">DEP をメールボックスに割り当てる</span><span class="sxs-lookup"><span data-stu-id="fd9b8-394">Assign a DEP to a mailbox</span></span>
<span data-ttu-id="fd9b8-395"><a name="assignDEPtomailbox"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-395"></span></span>

<span data-ttu-id="fd9b8-p157">セット-メールボックス コマンドレットを使用して、DEP をメールボックスに割り当てます。ポリシーを割り当てると、Office 365 が、DEP. で指定したキーを使用してメールボックスを暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p157">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet. Once you assign the policy, Office 365 can encrypt the mailbox with the key designated in the DEP.</span></span>
  
```
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="fd9b8-p158">場所*MailboxIdParameter*は、メールボックスを指定します。セット-メールボックス コマンドレットの詳細については、[一連のメールボックス](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p158">Where *MailboxIdParameter* specifies a mailbox. For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](https://technet.microsoft.com/library/bb123981%28v=exchg.160%29.aspx).</span></span>
  
### <a name="validate-mailbox-encryption"></a><span data-ttu-id="fd9b8-400">メールボックスの暗号化を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-400">Validate mailbox encryption</span></span>
<span data-ttu-id="fd9b8-401"><a name="validatemailboxencryption"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-401"></span></span>

<span data-ttu-id="fd9b8-p159">メールボックスを暗号化すると、時間がかかることができます。時間ポリシーの割り当て、最初のメールボックスする必要がありますも移動を完了 1 つのデータベースから別にサービスが、メールボックスを暗号化する前にします。DEP を変更するか、最初の時間を割り当てる、DEP のメールボックスに、暗号化を検証しようとする前に、72 時間を待機することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p159">Encrypting a mailbox can take some time. For first time policy assignment, the mailbox must also complete the move from one database to another before the service can encrypt the mailbox. We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="fd9b8-405">Get MailboxStatistics コマンドレットを使用すると、メールボックスが暗号化されているかを判断できます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-405">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="fd9b8-406">暗号化されたチャレンジ プロパティは、メールボックスが暗号化されていない場合の値**は true**メールボックスが暗号化されている場合と**false**の値を返します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-406">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span> 

<span data-ttu-id="fd9b8-p160">メールボックスの移動を完了するには、メールボックスのサイズと同様に、最初に、DEP を割り当てるためのメールボックスの数によって異なります。DEP が割り当てられた時間から 1 週間後、メールボックスが暗号化されていない場合、新規 MoveRequest コマンドレットを使用して暗号化されていないメールボックスに対するメールボックスの移動を開始します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p160">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, as well as the size of the mailboxes. If the mailboxes have not been encrypted after a week from the time you assigned the DEP, initiate a mailbox move for the unencrypted mailboxes by using the New-MoveRequest cmdlet.</span></span>

```
New-MoveRequest <mailbox alias>
``` 

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="fd9b8-409">Office 365: SharePoint Online およびビジネスのための OneDrive の顧客のキーを設定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-409">Office 365: Setting up Customer Key for SharePoint Online and OneDrive for Business</span></span>
<span data-ttu-id="fd9b8-410"><a name="AzureSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-410"></span></span>

<span data-ttu-id="fd9b8-p161">作業を開始する前に、Azure キー ヴォールトを設定するために必要なタスクを完了したことを確認します。については、 [Azure キー ヴォールトおよび顧客キー用の Microsoft FastTrack でタスクの実行](controlling-your-data-using-customer-key.md#AzureSteps)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p161">Before you begin, ensure that you have completed the tasks required to set up Azure Key Vault. See [Complete tasks in Azure Key Vault and Microsoft FastTrack for Customer Key](controlling-your-data-using-customer-key.md#AzureSteps) for information.</span></span> 
  
<span data-ttu-id="fd9b8-413">SharePoint Online およびビジネスのための OneDrive の顧客のキーを設定するには、SharePoint Online では、Windows PowerShell にリモートで接続することによって、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-413">To set up Customer Key for SharePoint Online and OneDrive for Business, you will need to perform these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a><span data-ttu-id="fd9b8-414">各 SharePoint Online および OneDrive のビジネス地域のデータの暗号化ポリシー (DEP) を作成します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-414">Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo</span></span>
<span data-ttu-id="fd9b8-415"><a name="CreateDEP4SPOODfB"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-415"></span></span>

<span data-ttu-id="fd9b8-p162">DEP は、Azure のキーの保管場所に保存されているキーのセットに関連付けられます。地域とも呼ばれる 1 つの地理的位置にあるデータのすべてに、DEP を適用するとします。(プレビュー) では現在、複数地域の機能 Office 365 を使用する場合は、地域ごとの 1 つの DEP を作成できます。複数地域を使用していない場合は、ビジネスの SharePoint Online と OneDrive を使用する Office 365 の DEP の 1 つを作成できます。Office 365 は、その地域のデータを暗号化するのには、DEP で識別されるキーが使用されます。DEP を作成するには、キーのボルトの Uri が以前のバージョンを取得する必要があります。手順については、[各 Azure キー ヴォールト ・ キーの URI を取得](controlling-your-data-using-customer-key.md#GetKeyURI)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p162">A DEP is associated with a set of keys stored in Azure Key Vault. You apply a DEP to all of your data in one geographic location, also called a geo. If you use the multi-geo feature of Office 365 (currently in Preview), you can create one DEP per geo. If you are not using multi-geo, you can create one DEP in Office 365 for use with SharePoint Online and OneDrive for Business. Office 365 will then use the keys identified in the DEP to encrypt your data in that geo. To create the DEP, you need the Key Vault URIs you obtained earlier. See [Obtain the URI for each Azure Key Vault key](controlling-your-data-using-customer-key.md#GetKeyURI) for instructions.</span></span> 
  
<span data-ttu-id="fd9b8-p163">忘れないでください!DEP を作成するときは、2 つの異なる Azure キー ヴォールト内に存在する 2 つのキーを指定します。これらのキーは、geo の冗長性を確保するのには 2 つの独立した Azure 領域に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p163">Remember! When you create a DEP, you specify two keys that reside in two different Azure Key Vaults. Ensure that these keys are located in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="fd9b8-426">DEP を作成するには、Windows PowerShell を使用して、SharePoint Online にリモートで接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-426">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="fd9b8-427">ローカル コンピューター上には、グローバル管理者アクセス許可を持つ[SharePoint オンライン Powershell への接続](https://technet.microsoft.com/library/fp161372.aspx)、Office 365 の組織で職場または学校のアカウントを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-427">On your local computer, using a work or school account that has global administrator permissions in your Office 365 organization, [Connect to SharePoint Online Powershell](https://technet.microsoft.com/library/fp161372.aspx).</span></span>
    
2. <span data-ttu-id="fd9b8-428">Microsoft SharePoint オンライン管理シェルで次のように[レジスタ SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx)コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-428">In the Microsoft SharePoint Online Management Shell, run the [Register-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843950.aspx) cmdlet as follows:</span></span> 
    
   ```
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="fd9b8-p164">DEP を登録する場合、地域内のデータの暗号化を開始します。これにより、時間がかかることができます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p164">When you register the DEP, encryption begins on the data in the geo. This can take some time.</span></span>
    
### <a name="validate-encryption-of-group-sites-team-sites-and-onedrive-for-business"></a><span data-ttu-id="fd9b8-431">グループ サイト、チーム サイト、およびビジネスのための OneDrive の暗号化を確認します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-431">Validate encryption of Group Sites, Team Sites, and OneDrive for Business</span></span>
<span data-ttu-id="fd9b8-432"><a name="validateencryptionSPO"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-432"></span></span>

<span data-ttu-id="fd9b8-433">次のように Get SPODataEncryptionPolicy コマンドレットを実行して、暗号化の状態をチェックできます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-433">You can check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="fd9b8-434">このコマンドレットからの出力は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-434">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="fd9b8-435">プライマリ ・ キーの URI。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-435">The URI of the primary key.</span></span>
    
- <span data-ttu-id="fd9b8-436">セカンダリ ・ キーの URI。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-436">The URI of the secondary key.</span></span>
    
- <span data-ttu-id="fd9b8-p165">Geo の暗号化の状態です。可能な状態は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p165">The encryption status for the geo. Possible states include:</span></span>
    
  - <span data-ttu-id="fd9b8-439">**未登録:** 顧客キー暗号方式はまだ適用されていません。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-439">**Unregistered:** Customer Key encryption has not yet been applied.</span></span> 
    
  - <span data-ttu-id="fd9b8-p166">**の登録:** 顧客キーの暗号化が適用されているし、ファイルが暗号化されています。地域がこの状態である場合も表示されます情報を地域内のサイトの割合は、完全な暗号化の進行状況を監視することができます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p166">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted. If your geo is in this state, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span> 
    
  - <span data-ttu-id="fd9b8-442">**登録:** 顧客キーの暗号化が適用されている、およびすべてのサイト内のすべてのファイルが暗号化されています。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-442">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span> 
    
  - <span data-ttu-id="fd9b8-p167">**ローリング:** キーのロールは、実行中です。地域がこの状態である場合も表示されます情報のサイトの何パーセント完了キー操作の進行状況を監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p167">**Rolling:** A key roll is in progress. If your geo is in this state, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span> 
    
## <a name="managing-customer-key-for-office-365"></a><span data-ttu-id="fd9b8-445">Office 365 の顧客のキーを管理します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-445">Managing Customer Key for Office 365</span></span>
<span data-ttu-id="fd9b8-446"><a name="ManageCustomerKey"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-446"></span></span>

<span data-ttu-id="fd9b8-447">Office 365 の顧客のキーを設定したら後、は、これらの余分な管理作業を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-447">After you've set up Customer Key for Office 365, you can perform these additional management tasks.</span></span>
  
- [<span data-ttu-id="fd9b8-448">Azure キー ヴォールト ・ キーを復元します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-448">Restore Azure Key Vault keys</span></span>](controlling-your-data-using-customer-key.md#RestoreAzureKeyVaultKeys)
    
- [<span data-ttu-id="fd9b8-449">ロールまたは顧客のキーを使用した Azure キーの保管場所にキーを回転させる</span><span class="sxs-lookup"><span data-stu-id="fd9b8-449">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>](controlling-your-data-using-customer-key.md#RollCKkey)
    
- [<span data-ttu-id="fd9b8-450">ヴォールトのキーのアクセス許可を管理します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-450">Manage key vault permissions</span></span>](controlling-your-data-using-customer-key.md#Managekeyvaultperms)
    
- [<span data-ttu-id="fd9b8-451">DEP のメールボックスに割り当てられているを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-451">Determine the DEP assigned to a mailbox</span></span>](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)
    
### <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="fd9b8-452">Azure キー ヴォールト ・ キーを復元します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-452">Restore Azure Key Vault keys</span></span>
<span data-ttu-id="fd9b8-453"><a name="RestoreAzureKeyVaultKeys"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-453"></span></span>

<span data-ttu-id="fd9b8-p168">リストアを実行する前に、ソフトの削除が提供するリカバリ機能を使用します。顧客キーで使用されるすべてのキーは、ソフトの削除を有効にする必要があります。ソフトの削除、ごみ箱のように動作でき、回復を 90 日間を復元する必要はありません。復元は、極端なまたは異常な状況は、たとえば、キーまたはキーのボルトが失われた場合にのみ必要する必要があります。顧客のキーを使用するキーを復元する必要がある場合 Azure の PowerShell のコマンドレットを実行、復元 AzureKeyVaultKey 次のように。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p168">Before performing a restore, use the recovery capabilities provided by soft delete. All keys that are used with Customer Key are required to have soft delete enabled. Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore. Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost. If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName <vaultname> -InputFile <filename>
```

<span data-ttu-id="fd9b8-459">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-459">For example:</span></span>
  
```
Restore-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="fd9b8-p169">キーの保管場所に同じ名前のキーが既に存在する場合、復元操作は失敗します。復元 AzureKeyVaultKey は、キーのすべてのバージョンおよびキーの名前を含むキーのすべてのメタデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p169">If a key with the same name already exists in the key vault, the restore operation will fail. Restore-AzureKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
### <a name="rolling-or-rotating-a-key-in-azure-key-vault-that-you-use-with-customer-key"></a><span data-ttu-id="fd9b8-462">ロールまたは顧客のキーを使用した Azure キーの保管場所にキーを回転させる</span><span class="sxs-lookup"><span data-stu-id="fd9b8-462">Rolling or rotating a key in Azure Key Vault that you use with Customer Key</span></span>
<span data-ttu-id="fd9b8-463"><a name="RollCKkey"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-463"></span></span>

<span data-ttu-id="fd9b8-p170">キーのロールでは、いずれかの Azure キー ヴォールト、顧客キーは必要ありません。さらに、HSM で保護されているキーは侵害することは事実上不可能ではありません。ルート キーが悪意のあるアクターに所持されていた場合でも、Office 365 のコードのみを使用する方法を知っているので、データを復号化に使用する際の実現可能な対策はありません。ただし、キーのローリングでは顧客のキーです。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p170">Rolling keys is not required by either Azure Key Vault or by Customer Key. In addition, keys that are protected with an HSM are virtually impossible to compromise. Even if a root key were in the possession of a malicious actor there is no feasible means of using it to decrypt data, since only Office 365 code knows how to use it. However, rolling a key is supported by Customer Key.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="fd9b8-p171">チェック ボックスをオフに技術的な理由が存在するか、規則の遵守要件の規定があるか、キーを展開するときに、お客様のキーを使用してに使用する暗号化キーのロールのみです。さらに、またはポリシーに関連付けられていたすべてのキーを削除できません。ありますが、キーをロールバックすると、コンテンツは暗号化以前のキーで。などのアクティブなメールボックス再暗号化される多くの場合、非アクティブなときにメールボックスが切断された場合、および無効になっている可能性がありますまだ暗号化以前のキーで。SharePoint のオンライン ・ バックアップを実行コンテンツの復元と回復のためにアーカイブされたコンテンツが古いキーを使用してありますので。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p171">Only roll an encryption key that you use with Customer Key when a clear technical reason exists or a compliance requirement dictates that you have to roll the key. In addition, do not delete any keys that are or were associated with policies. When you roll your keys, there will be content encrypted with the previous keys. For example, while active mailboxes will be re-encrypted frequently, inactive, disconnected, and disabled mailboxes may still be encrypted with the previous keys. SharePoint Online performs backup of content for restore and recovery purposes, so there may still be archived content using older keys. </span></span><br/> <span data-ttu-id="fd9b8-p172">データの安全を確保するには、SharePoint Online は操作を許可する複数のキーのロールを同時に実行されています。キーのロールの最初の操作が待機する必要がありますキーの両方をキーの保管場所にロールバックする場合は、完全に完了します。推奨は、さまざまな間隔で、キーのロールの操作をずらすようにこれは問題ではありません。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p172">To ensure the safety of your data, SharePoint Online will allow no more than one Key Roll operation to be in progress at a time. If you want to roll both of the keys in a key vault, you'll need to wait for the first key roll operation to fully complete. Our recommendation is to stagger your key roll operations at different intervals, so that this is not an issue.</span></span> 
  
<span data-ttu-id="fd9b8-p173">キーをロールバックするときは、既存のキーの新しいバージョンを要求しています。既存のキーの新しいバージョンを要求するために、まずキーの作成に使用した同じ構文を使用して[追加 AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey)、同じコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p173">When you roll a key, you are requesting a new version of an existing key. In order to request a new version of an existing key, you use the same cmdlet, [Add-AzureKeyVaultKey](https://docs.microsoft.com/powershell/module/AzureRM.KeyVault/Add-AzureKeyVaultKey), with the same syntax that you used to create the key in the first place.</span></span>
  
<span data-ttu-id="fd9b8-478">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-478">For example:</span></span>
  
```
Add-AzureKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
```

<span data-ttu-id="fd9b8-p174">この例では、 **Contoso O365EX NA VaultA1** vault の**contoso 社の O365EX-ナ-VaultA1-Key001**を既にという名前のキーが存在するため、新しいキー バージョン作成されます。操作は、新しいキー バージョンを追加します。以前にそのキーで暗号化されたデータが暗号化を解除できるように、この操作は、以前のキー、キーのバージョン履歴では、バージョンを保持します。DEP に関連付けられている任意のキーのローリングを完了すると、顧客キーは新しいキーの使用を開始することを確認するのには追加のコマンドレットを実行してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p174">In this example, since a key named **Contoso-O365EX-NA-VaultA1-Key001** already exists in the **Contoso-O365EX-NA-VaultA1** vault, a new key version will be created. The operation adds a new key version. This operation preserves the previous key versions in the key's version history, so that data previously encrypted with that key can still be decrypted. Once you have completed rolling any key that is associated with a DEP, you must then run an additional cmdlet to ensure Customer Key begins using the new key.</span></span> 
  
#### <a name="enable-exchange-online-and-skype-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="fd9b8-483">Exchange オンラインで Skype のビジネス ロールまたは Azure キーの保管場所にキーを回転した後、新しいキーを使用するを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-483">Enable Exchange Online and Skype for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="fd9b8-484">いずれかに移動すると、DEP に関連付けられている Azure キー ヴォールトのキーを使用と、Exchange オンライン Skype ビジネス、DEP を更新し、新しいキーを使用する Office 365 を有効にするには、次のコマンドを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-484">When you roll either of the Azure Key Vault keys associated with a DEP used with Exchange Online and Skype for Business, you must run the following command to update the DEP and enable Office 365 to start using the new key.</span></span>
  
<span data-ttu-id="fd9b8-485">顧客キーを暗号化するために新しいキーを使用するように指示するのには、Office 365 のメールボックスは、セット DataEncryptionPolicy コマンドレットをとおり実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-485">To instruct Customer Key to use the new key to encrypt mailboxes in Office 365 run the Set-DataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Set-DataEncryptionPolicy <policyname> -Refresh 
```

<span data-ttu-id="fd9b8-p175">48 時間以内は、このポリシーを使用して暗号化のアクティブなメールボックスが更新されたキーに関連付けられているになります。メールボックスの DataEncryptionPolicyID プロパティの値を確認するのには[特定のメールボックスに割り当てられている DEP](controlling-your-data-using-customer-key.md#DeterminemailboxDEP)で手順を使用します。更新キーが適用された後、このプロパティの値が変更されます。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p175">Within 48 hours, the active mailboxes encrypted using this policy will become associated with the updated key. Use the steps in [Determine the DEP assigned to a mailbox](controlling-your-data-using-customer-key.md#DeterminemailboxDEP) to check the value for the DataEncryptionPolicyID property for the mailbox. The value for this property will change once the updated key has been applied.</span></span> 
  
#### <a name="enable-sharepoint-online-and-onedrive-for-business-to-use-a-new-key-after-you-roll-or-rotate-keys-in-azure-key-vault"></a><span data-ttu-id="fd9b8-489">SharePoint Online およびビジネスのための OneDrive ロールまたは Azure キーの保管場所にキーを回転した後、新しいキーを使用するを有効にします。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-489">Enable SharePoint Online and OneDrive for Business to use a new key after you roll or rotate keys in Azure Key Vault</span></span>

<span data-ttu-id="fd9b8-490">いずれかに移動すると、DEP に関連付けられている Azure キー ヴォールトのキーを使用し、OneDrive、SharePoint Online でビジネス、DEP を更新し、新しいキーを使用する Office 365 を有効にする[更新プログラム SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx)コマンドレットを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-490">When you roll either of the Azure Key Vault keys associated with a DEP used with SharePoint Online and OneDrive for Business, you must run the [Update-SPODataEncryptionPolicy](https://technet.microsoft.com/library/mt843948.aspx) cmdlet to update the DEP and enable Office 365 to start using the new key.</span></span> 
  
```
Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
```

<span data-ttu-id="fd9b8-p176">SharePoint Online およびビジネスのための OneDrive のキー操作を開始します。この操作は即時ではありません。キーの操作をロールバックの進行状況を表示するには、次のように、Get SPODataEncryptionPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p176">This will start the key roll operation for SharePoint Online and OneDrive for Business. This action is not immediate. To see the progress of the key roll operation, run the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>
  
```
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

### <a name="manage-key-vault-permissions"></a><span data-ttu-id="fd9b8-494">ヴォールトのキーのアクセス許可を管理します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-494">Manage key vault permissions</span></span>
<span data-ttu-id="fd9b8-495"><a name="Managekeyvaultperms"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-495"></span></span>

<span data-ttu-id="fd9b8-p177">利用できるいくつかのコマンドレットを表示し、必要であれば、ボルトのキーのアクセス許可を削除することができます。従業員がチームを離れたときなど、アクセス許可を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p177">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions. You might need to remove permissions, for example, when an employee leaves the team.</span></span>
  
<span data-ttu-id="fd9b8-498">ヴォールトのキーのアクセス許可を表示するには、Get AzureRmKeyVault コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-498">To view key vault permissions, run the Get-AzureRmKeyVault cmdlet:</span></span>
  
```
Get-AzureRmKeyVault -VaultName <vaultname>
```

<span data-ttu-id="fd9b8-499">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-499">For example:</span></span>
  
```
Get-AzureRmKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="fd9b8-500">管理者のアクセス許可を削除するには、削除 AzureRmKeyVaultAccessPolicy コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-500">To remove an administrator's permissions, run the Remove-AzureRmKeyVaultAccessPolicy cmdlet:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName <vaultname> 
-UserPrincipalName <UPN of user>
```

<span data-ttu-id="fd9b8-501">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-501">For example:</span></span>
  
```
Remove-AzureRmKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-UserPrincipalName alice@contoso.com
```

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="fd9b8-502">DEP のメールボックスに割り当てられているを決定します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-502">Determine the DEP assigned to a mailbox</span></span>
<span data-ttu-id="fd9b8-503"><a name="DeterminemailboxDEP"> </a></span><span class="sxs-lookup"><span data-stu-id="fd9b8-503"></span></span>

<span data-ttu-id="fd9b8-p178">DEP のメールボックスに割り当てられているを確認するのには、Get MailboxStatistics コマンドレットを使用します。コマンドレットでは、一意の識別子 (GUID) を返します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p178">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet. The cmdlet returns a unique identifier (GUID).</span></span>
  
```
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
```

<span data-ttu-id="fd9b8-p179">場所*GeneralMailboxOrMailUserIdParameter*は、メールボックスを指定します。Get MailboxStatistics コマンドレットの詳細については、 [Get MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-p179">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox. For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://technet.microsoft.com/library/bb124612%28v=exchg.160%29.aspx).</span></span>
  
<span data-ttu-id="fd9b8-508">メールボックス割り当てられている次のコマンドレットを実行して、DEP のフレンドリ名を検索するのには、GUID を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-508">Use the GUID to find out the friendly name of the DEP to which the mailbox is assigned by running the following cmdlet.</span></span>
  
```
Get-DataEncryptionPolicy <GUID>
```

<span data-ttu-id="fd9b8-509">*GUID*は、前の手順で Get MailboxStatistics コマンドレットによって返される GUID です。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-509">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span> 
  

