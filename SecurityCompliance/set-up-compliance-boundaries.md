---
title: Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンスの境界を使用して、電子情報開示マネージャーが検索できるユーザーコンテンツの場所を制御する、Office 365 組織内の論理的な境界を作成します。 コンプライアンス境界では、検索アクセス許可フィルター (コンプライアンスセキュリティフィルターとも呼ばれます) を使用して、特定のユーザーが検索できるメールボックス、SharePoint サイト、および OneDrive アカウントを制御します。
ms.openlocfilehash: ea3c289c63d2ee777e88166a94bd9ed92abcbb26
ms.sourcegitcommit: 1658be51e2c21ed23bc4467a98af74300a45b975
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/26/2019
ms.locfileid: "30862439"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="518d6-104">Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する</span><span class="sxs-lookup"><span data-stu-id="518d6-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="518d6-105">コンプライアンス境界は、電子情報開示マネージャーが検索できるユーザーコンテンツの場所 (メールボックス、SharePoint サイト、OneDrive アカウントなど) を制御する、Office 365 組織内の論理的な境界を作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-105">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search.</span></span> <span data-ttu-id="518d6-106">また、コンプライアンスの境界は、組織内の法律、人的リソース、またはその他の調査を管理するために使用される電子情報開示ケースにアクセスできるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="518d6-106">Additionally, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization.</span></span> <span data-ttu-id="518d6-107">多くの場合、地理的な boarders および規制を遵守する必要がある多民族企業や、多くの場合、さまざまな機関に分けられる政府機関に対して、コンプライアンスの境界が必要になります。</span><span class="sxs-lookup"><span data-stu-id="518d6-107">The need for compliance boundaries is often necessary for multi-nations corporations that have to respect geographical boarders and regulations, and for governments, which are often divided into different agencies.</span></span> <span data-ttu-id="518d6-108">Office 365 では、コンテンツ検索を実行し、電子情報開示ケースを使用して調査を管理する際に、これらの要件を満たすためにコンプライアンスの境界が役立ちます。</span><span class="sxs-lookup"><span data-stu-id="518d6-108">In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="518d6-109">次の図の例を使用して、コンプライアンスの境界がどのように機能するかを説明します。</span><span class="sxs-lookup"><span data-stu-id="518d6-109">We'll use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![コンプライアンス境界は、政府機関へのアクセスを制御する検索アクセス許可フィルターと、edisococo極端なケースへのアクセスを制御する管理役割グループで構成されます。](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="518d6-111">この例では、Contoso ltd. は、2つの子会社、4番目のコーヒー、Coho (コーホーワイナリー) で構成される Office 365 組織です。</span><span class="sxs-lookup"><span data-stu-id="518d6-111">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery.</span></span> <span data-ttu-id="518d6-112">ビジネスでは、電子情報開示 mangers と調査担当者が、エージェンシー内の Exchange メールボックス、OneDrive アカウント、および SharePoint サイトのみを検索できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="518d6-112">The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency.</span></span> <span data-ttu-id="518d6-113">また、電子情報開示の管理者と調査担当者は、エージェンシーの電子情報開示ケースのみを表示でき、メンバーとなっているケースのみにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="518d6-113">Additionally, eDiscovery managers and investigators can only see eDiscovery cases in the in their agency, and they can only access the cases that they're a member of.</span></span> <span data-ttu-id="518d6-114">以下に、コンプライアンスの境界がこれらの要件を満たす方法を示します。</span><span class="sxs-lookup"><span data-stu-id="518d6-114">Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="518d6-115">コンテンツ検索の検索アクセス許可フィルター機能は、電子情報開示の管理者および捜査担当者が検索できるコンテンツの場所を制御します。</span><span class="sxs-lookup"><span data-stu-id="518d6-115">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search.</span></span> <span data-ttu-id="518d6-116">これは、4番目のコーヒーエージェンシーの電子情報開示マネージャーと調査担当者のみが、第4のコーヒー子会社のコンテンツの場所を検索できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="518d6-116">This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary.</span></span> <span data-ttu-id="518d6-117">同じ制限は、Coho の "子会社" にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-117">The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="518d6-118">役割グループは、Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のケースを表示できるユーザーを制御します。</span><span class="sxs-lookup"><span data-stu-id="518d6-118">Role groups control who can see the eDiscovery cases in the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="518d6-119">つまり、電子情報開示の管理者と調査担当者は、エージェンシーの電子情報開示ケースのみを表示できます。</span><span class="sxs-lookup"><span data-stu-id="518d6-119">This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="518d6-120">役割グループは、電子情報開示ケースにメンバーを割り当てることができるユーザーも制御します。</span><span class="sxs-lookup"><span data-stu-id="518d6-120">Role groups also control who can assign members to an eDiscovery case.</span></span> <span data-ttu-id="518d6-121">つまり、電子情報開示マネージャーおよび調査担当者は、自分が自分のメンバーであるケースにのみメンバーを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="518d6-121">This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="518d6-122">コンプライアンスの境界を設定するプロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="518d6-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="518d6-123">手順 1: ユーザー属性を識別して、機関を定義する</span><span class="sxs-lookup"><span data-stu-id="518d6-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="518d6-124">手順 2: Microsoft サポートによる要求をファイル化して、ユーザー属性を OneDrive アカウントに同期させる</span><span class="sxs-lookup"><span data-stu-id="518d6-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="518d6-125">手順 3: 各エージェンシーの役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="518d6-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="518d6-126">手順 4: コンプライアンスの境界を適用するための検索アクセス許可フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="518d6-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="518d6-127">手順 5: エージェンシー内の調査用に電子情報開示ケースを作成する</span><span class="sxs-lookup"><span data-stu-id="518d6-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="518d6-128">手順 1: ユーザー属性を識別して、機関を定義する</span><span class="sxs-lookup"><span data-stu-id="518d6-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="518d6-129">最初の手順として、を使用する Azure Active Directory 属性を選択して、その機関を定義します。</span><span class="sxs-lookup"><span data-stu-id="518d6-129">The first step is to choose an Azure Active Directory attribute to use that will define your agencies.</span></span> <span data-ttu-id="518d6-130">この属性は、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索するように電子情報開示マネージャーを制限する検索アクセス許可フィルターを作成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-130">This attribute will be used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute.</span></span> <span data-ttu-id="518d6-131">たとえば、Contoso 社が**Department**属性の使用を決定したとします。</span><span class="sxs-lookup"><span data-stu-id="518d6-131">For example, let's say Contoso decides to use the **Department** attribute.</span></span> <span data-ttu-id="518d6-132">4番目のコーヒー子会社のユーザーのこの属性の値は`FourthCoffee`となり、Coho のユーザーの値はとなり`CohoWinery`ます。</span><span class="sxs-lookup"><span data-stu-id="518d6-132">The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`.</span></span> <span data-ttu-id="518d6-133">ステップ4では、この`attribute:value`ペア (たとえば、 *Department: 4 thコーヒー* ) を使用して、電子情報開示マネージャーが検索できるユーザーのコンテンツの場所を制限します。</span><span class="sxs-lookup"><span data-stu-id="518d6-133">In Step 4, you'll use this  `attribute:value`  pair (for example,  *Department:FourthCoffee*  ) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="518d6-134">以下は、コンプライアンスの境界に使用できる Azure Active Directory ユーザー属性の一覧です。</span><span class="sxs-lookup"><span data-stu-id="518d6-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="518d6-135">Company</span><span class="sxs-lookup"><span data-stu-id="518d6-135">Company</span></span>
    
- <span data-ttu-id="518d6-136">CustomAttribute1-CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="518d6-136">CustomAttribute1 - CustomAttribute15</span></span>
    
- <span data-ttu-id="518d6-137">部署</span><span class="sxs-lookup"><span data-stu-id="518d6-137">Department</span></span>
    
- <span data-ttu-id="518d6-138">事業所</span><span class="sxs-lookup"><span data-stu-id="518d6-138">Office</span></span>
    
<span data-ttu-id="518d6-139">他のユーザー属性も使用できますが (特に Exchange メールボックスの場合)、上記の属性は OneDrive で現在サポートされているものだけです。</span><span class="sxs-lookup"><span data-stu-id="518d6-139">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="518d6-140">手順 2: Microsoft サポートによる要求をファイル化して、ユーザー属性を OneDrive アカウントに同期させる</span><span class="sxs-lookup"><span data-stu-id="518d6-140">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="518d6-141">次の手順では、Microsoft サポートに要求をファイルして、手順1で選択した Azure Active Directory 属性と組織内のすべての OneDrive アカウントを同期させます。</span><span class="sxs-lookup"><span data-stu-id="518d6-141">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization.</span></span> <span data-ttu-id="518d6-142">この同期が行われると、手順1で選択した属性 (およびその値) は、SharePoint の非表示の管理プロパティに`ComplianceAttribute`マップされます。</span><span class="sxs-lookup"><span data-stu-id="518d6-142">After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`.</span></span> <span data-ttu-id="518d6-143">この属性を使用して、手順4で OneDrive の検索アクセス許可フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-143">You'll use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="518d6-144">Microsoft サポートに要求を送信するときに、次の情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="518d6-144">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="518d6-145">Office 365 組織の既定のドメイン名</span><span class="sxs-lookup"><span data-stu-id="518d6-145">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="518d6-146">Azure Active Directory 属性の名前 (手順1から)</span><span class="sxs-lookup"><span data-stu-id="518d6-146">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="518d6-147">サポート要求の目的に関する次のタイトルまたは説明: "コンプライアンスセキュリティフィルターのために Azure Active Directory との OneDrive for business の同期を有効にする"。</span><span class="sxs-lookup"><span data-stu-id="518d6-147">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters".</span></span> <span data-ttu-id="518d6-148">これは、要求を実装する Office 365 eDiscovery エンジニアリングチームに要求をルーティングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="518d6-148">This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span>
    
<span data-ttu-id="518d6-149">エンジニアリングの変更が行われ、属性が OneDrive に同期されると、Microsoft Support は変更が行われたビルド番号と推定展開日を送信します。</span><span class="sxs-lookup"><span data-stu-id="518d6-149">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date.</span></span> <span data-ttu-id="518d6-150">通常、サポート要求を送信した後、展開プロセスは4-6 週間かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-150">Note that the deployment process usually takes 4-6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="518d6-151">**重要:** 変更を展開する前に、手順3から手順5までを完了できます。</span><span class="sxs-lookup"><span data-stu-id="518d6-151">**Important:** You can complete Step 3 through Step 5 before the change is deployed.</span></span> <span data-ttu-id="518d6-152">ただし、コンテンツ検索を実行しても、検索アクセス許可フィルターで指定された OneDrive サイトからのドキュメントは、変更が展開されるまで返されません。</span><span class="sxs-lookup"><span data-stu-id="518d6-152">But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="518d6-153">手順 3: 各エージェンシーの役割グループを作成する</span><span class="sxs-lookup"><span data-stu-id="518d6-153">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="518d6-154">次の手順では、社内の機関と連携する Office 365 &amp;セキュリティコンプライアンスセンターで役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-154">The next step is to create the role groups in the Office 365 Security &amp; Compliance Center that will align with your agencies.</span></span> <span data-ttu-id="518d6-155">組み込みの電子情報開示マネージャーグループをコピーし、適切なメンバーを追加して、ニーズに該当しない可能性がある役割を削除することによって、新しい役割グループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="518d6-155">We recommend that you create a new role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs.</span></span> <span data-ttu-id="518d6-156">電子情報開示関連のロールの詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-156">For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="518d6-157">役割グループを作成するには、セキュリティ&amp; /コンプライアンスセンターの [**アクセス許可**] ページに移動し、コンプライアンスの境界と電子情報開示ケースを使用して調査を管理する各エージェンシーの各チームの役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-157">To create the role groups, go to the **Permissions** page in the Security &amp; Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="518d6-158">Contoso 社のコンプライアンス境界シナリオを使用して、4つの役割グループを作成し、それぞれに適切なメンバーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="518d6-158">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="518d6-159">4番目のコーヒー eDiscovery マネージャー</span><span class="sxs-lookup"><span data-stu-id="518d6-159">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="518d6-160">4番目のコーヒー捜査官</span><span class="sxs-lookup"><span data-stu-id="518d6-160">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="518d6-161">Coho の電子情報開示マネージャー</span><span class="sxs-lookup"><span data-stu-id="518d6-161">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="518d6-162">Coho の捜査官</span><span class="sxs-lookup"><span data-stu-id="518d6-162">Coho Winery Investigators</span></span>
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="518d6-163">手順 4: コンプライアンスの境界を適用するための検索アクセス許可フィルターを作成する</span><span class="sxs-lookup"><span data-stu-id="518d6-163">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>

<span data-ttu-id="518d6-164">各エージェンシーの役割グループを作成したら、次の手順として、各役割グループを特定のエージェンシーに関連付け、コンプライアンス境界自体を定義する検索アクセス許可フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-164">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself.</span></span> <span data-ttu-id="518d6-165">各エージェンシーに対して1つの検索アクセス許可フィルターを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="518d6-165">You need to create one search permissions filter for each agency.</span></span> <span data-ttu-id="518d6-166">セキュリティアクセス許可フィルターの作成の詳細については、「 [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-166">For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="518d6-167">以下は、コンプライアンスの境界に使用される検索アクセス許可フィルターを作成するために使用される構文です。</span><span class="sxs-lookup"><span data-stu-id="518d6-167">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
<span data-ttu-id="518d6-168">コマンドの各パラメーターの説明を次に示します。</span><span class="sxs-lookup"><span data-stu-id="518d6-168">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="518d6-169">`FilterName`-フィルターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-169">`FilterName` - Specifies the name of the filter.</span></span> <span data-ttu-id="518d6-170">フィルターが使用されるエージェンシーを説明または特定する名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="518d6-170">Use a name that describes or identifies the agency that filter will be used in.</span></span> 
    
-  <span data-ttu-id="518d6-171">`Users`-このフィルターを実行するコンテンツ検索アクションに適用される、このフィルターを取得するユーザーまたはグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-171">`Users` - Specifies the users or groups who get this filter applied to the Content Search actions they perform.</span></span> <span data-ttu-id="518d6-172">このパラメーターは、コンプライアンスの境界に対して、フィルターを作成しているエージェンシーの役割グループ (手順3で作成したもの) を指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-172">For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for.</span></span> <span data-ttu-id="518d6-173">メモこれは複数値パラメーターであるため、1つまたは複数の役割グループをコンマで区切って含めることができます。</span><span class="sxs-lookup"><span data-stu-id="518d6-173">Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="518d6-174">`Filters`-フィルターの検索条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-174">`Filters` - Specifies the search criteria for the filter.</span></span> <span data-ttu-id="518d6-175">コンプライアンスの境界については、次のフィルターを定義します。</span><span class="sxs-lookup"><span data-stu-id="518d6-175">For the compliance boundaries, you will define the following filters.</span></span> <span data-ttu-id="518d6-176">それぞれは、ユーザーのコンテンツの場所に適用されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-176">Each one applies to a user content location.</span></span> 
    
  -  <span data-ttu-id="518d6-177">`Mailbox`- `Users`パラメーターで定義されている役割グループが検索できるメールボックスを指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-177">`Mailbox` - Specifies the mailboxes that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="518d6-178">コンプライアンスの境界の場合、 *ComplianceAttribute*は、手順1と属性*値*で指定したものと同じであり、エージェンシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-178">For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency.</span></span> <span data-ttu-id="518d6-179">このフィルターを使用すると、役割グループのメンバーは特定のエージェンシーのメールボックスのみを検索できます。たとえば、 `"Mailbox_Department -eq 'FourthCoffee'"`のようになります。</span><span class="sxs-lookup"><span data-stu-id="518d6-179">This filter allow members of the role group to only search the mailboxes in a specific agency; for example,  `"Mailbox_Department -eq 'FourthCoffee'"` .</span></span> 
    
  -  <span data-ttu-id="518d6-180">`Site`- `Users`パラメーターで定義されている役割グループが検索できる OneDrive アカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-180">`Site` - Specifies the OneDrive accounts that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="518d6-181">OneDrive フィルターの場合は、実際の文字列`ComplianceAttribute`を使用します。これは、手順2で送信したサポート要求の結果として、手順1で識別し、OneDrive アカウントに同期されている属性にマッピングされます。 *attributevalue*はエージェンシーを指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-181">For the OneDrive filter, use the actual string  `ComplianceAttribute`; this will map to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2;  *AttributeValue*  specifies the agency.</span></span> <span data-ttu-id="518d6-182">このフィルターを使用すると、役割グループのメンバーは特定のエージェンシーの OneDrive アカウントのみを検索できます。たとえば、 `"Site_ComplianceAttribute -eq 'FourthCoffee'"`のようになります。</span><span class="sxs-lookup"><span data-stu-id="518d6-182">This filter allow members of the role group to only search the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
  -  <span data-ttu-id="518d6-183">`Site_Path`- `Users`パラメーターで定義されている役割グループが検索できる SharePoint サイトを指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-183">`Site_Path` - Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search.</span></span> <span data-ttu-id="518d6-184">*SharePointURL*は、役割グループのメンバーが検索できる機関内のサイトを指定します。例えば`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span><span class="sxs-lookup"><span data-stu-id="518d6-184">The  *SharePointURL*  specifies the sites in the agency that members of the role group can search; for example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span></span>
    
-  <span data-ttu-id="518d6-185">`Action`-フィルターが適用されるコンプライアンス検索アクションの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="518d6-185">`Action` - Specifies the type of Compliance Search action that the filter is applied to.</span></span> <span data-ttu-id="518d6-186">たとえば、は`-Action Search` 、 `Users`パラメーターで定義された役割グループのメンバーがコンテンツ検索を実行するときにのみフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="518d6-186">For example,  `-Action Search` would only apply the filter when members of the role groups defined in the  `Users` parameter runs a content search.</span></span> <span data-ttu-id="518d6-187">この場合、検索結果をエクスポートするときに、フィルターは適用されません。</span><span class="sxs-lookup"><span data-stu-id="518d6-187">In this case, the filter wouldn't be applied when exporting search results.</span></span> <span data-ttu-id="518d6-188">コンプライアンスの境界の場合`-Action All`は、を使用して、すべての検索操作にフィルターが適用されるようにします。</span><span class="sxs-lookup"><span data-stu-id="518d6-188">For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="518d6-189">コンテンツ検索アクションの一覧については、「 [Configure permissions filtering for content search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)」の「new-compliancesecurityfilter」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-189">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>
    
<span data-ttu-id="518d6-190">Contoso 社のコンプライアンス境界シナリオをサポートするために作成される2つの検索アクセス許可フィルターの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="518d6-190">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span>
  
 <span data-ttu-id="518d6-191">**4番目のコーヒー**</span><span class="sxs-lookup"><span data-stu-id="518d6-191">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="518d6-192">**コーホーワイナリー**</span><span class="sxs-lookup"><span data-stu-id="518d6-192">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a><span data-ttu-id="518d6-193">手順 5: エージェンシー内の調査用に電子情報開示ケースを作成する</span><span class="sxs-lookup"><span data-stu-id="518d6-193">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>

<span data-ttu-id="518d6-194">最後の手順として、セキュリティ&amp;コンプライアンスセンターで新しい電子情報開示ケースを作成し、次に、手順3で作成した役割グループをケースのメンバーとして追加します。</span><span class="sxs-lookup"><span data-stu-id="518d6-194">The final step is to create a new eDiscovery case in the Security &amp; Compliance Center and then add the role group—that you created in Step 3—as a member of the case.</span></span> <span data-ttu-id="518d6-195">これにより、コンプライアンスの境界を使用する2つの重要な特徴が得られるようになります。</span><span class="sxs-lookup"><span data-stu-id="518d6-195">This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="518d6-196">ケースに追加された役割グループのメンバーのみが、セキュリティ&amp; /コンプライアンスセンターでそのケースを参照してアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="518d6-196">Only members of the role group added to the case will be able to see and access the case in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="518d6-197">たとえば、4番目のコーヒーの捜査官の役割グループがケースの唯一のメンバーである場合、その4番目のコーヒー eDiscovery Managers 役割グループ (または他の任意の役割グループのメンバー) のメンバーは、ケースを表示またはアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="518d6-197">For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="518d6-198">ケースに割り当てられた役割グループのメンバーが、そのケースに関連付けられている検索を実行すると、それらは、手順4で作成した検索アクセス許可フィルターによって定義された、エージェンシー内のコンテンツの場所のみを検索できます。</span><span class="sxs-lookup"><span data-stu-id="518d6-198">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>


<span data-ttu-id="518d6-199">新しいケースを作成し、メンバーを割り当てるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="518d6-199">To create a new case and assign members:</span></span>
    
1. <span data-ttu-id="518d6-200">セキュリティ&amp; /コンプライアンスセンターの [**電子情報開示**] ページに移動し、新しいケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-200">Go to the **eDiscovery** page in the Security &amp; Compliance Center and create a new case.</span></span> 
    
2. <span data-ttu-id="518d6-201">電子情報開示ケースの一覧で、作成したケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="518d6-201">In the list of eDiscovery cases, click the name of the case you just created.</span></span>
    
3. <span data-ttu-id="518d6-202">[**このケースの管理**] ページの [**役割グループ**の管理] ![で、](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) \*\*\*\*[追加] アイコン [追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="518d6-202">In the **Manage this case** flyout page, under **Mange role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![電子情報開示ケースのメンバーとして役割グループを追加する](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="518d6-204">役割グループの一覧で、手順3で作成した役割グループの1つを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="518d6-204">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="518d6-205">[**このケースの管理**] ポップアップで [**保存**] をクリックして変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="518d6-205">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="518d6-206">コンプライアンス境界の制限</span><span class="sxs-lookup"><span data-stu-id="518d6-206">Compliance boundary limitations</span></span>

<span data-ttu-id="518d6-207">電子情報開示ケースを管理する場合、およびコンプライアンスの境界を使用する調査を行う場合は、次の制限事項に注意してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-207">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="518d6-208">コンテンツ検索を作成して実行するときは、エージェンシーの外部にあるコンテンツの場所を選択できます。</span><span class="sxs-lookup"><span data-stu-id="518d6-208">When creating and running a Content Search, you can select content locations that are outside of your agency.</span></span> <span data-ttu-id="518d6-209">ただし、検索アクセス許可フィルターのため、これらの場所からのコンテンツは検索結果に含まれません。</span><span class="sxs-lookup"><span data-stu-id="518d6-209">However, because of the search permissions filter, content from those locations won't be included in the search results.</span></span>
    
- <span data-ttu-id="518d6-210">コンプライアンスの境界は、電子情報開示ケースの保留リストには適用されません。</span><span class="sxs-lookup"><span data-stu-id="518d6-210">Compliance boundaries don't apply to holds in eDiscovery cases.</span></span> <span data-ttu-id="518d6-211">つまり、あるエージェンシーの電子情報開示管理者は、ユーザーを保留中の異なるエージェンシーに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="518d6-211">That means an eDiscovery manager in one agency can place a user in a different agency on hold.</span></span> <span data-ttu-id="518d6-212">ただし、電子情報開示マネージャーが保留中のユーザーのコンテンツの場所を検索する場合は、コンプライアンスの境界が適用されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-212">However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold.</span></span> <span data-ttu-id="518d6-213">つまり、電子情報開示マネージャーは、ユーザーを保留にすることができた場合でも、ユーザーのコンテンツの場所を検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="518d6-213">That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="518d6-214">また、保留の統計情報はエージェンシーのコンテンツの場所にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-214">Additionally, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="518d6-215">検索アクセス許可のフィルターは、Exchange のパブリックフォルダーには適用されません。</span><span class="sxs-lookup"><span data-stu-id="518d6-215">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="518d6-216">複数地域環境でのコンテンツの検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="518d6-216">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="518d6-217">また、検索アクセス許可フィルターを使用すると、エクスポート用にコンテンツをルーティングする場所を制御したり、 [SharePoint 複数地域環境](https://go.microsoft.com/fwlink/?linkid=860840)でコンテンツの場所を検索するときに検索できるデータセンターを制御したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="518d6-217">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching content locations in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840).</span></span>
  
- <span data-ttu-id="518d6-218">**検索結果をエクスポート**する-特定のデータセンターから Exchange メールボックス、SharePoint サイト、および OneDrive アカウントから検索結果をエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="518d6-218">**Export search results** - You can export the search results from Exchange mailboxes, SharePoint sites, and OneDrive accounts from a specific datacenter.</span></span> <span data-ttu-id="518d6-219">これは、検索結果のエクスポート元となるデータセンターの場所を指定できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="518d6-219">This means that you can specify the datacenter location that search results will be exported from.</span></span>

    <span data-ttu-id="518d6-220">**new-compliancesecurityfilter**または**new-compliancesecurityfilter**コマンドレットに**Region**パラメーターを使用して、エクスポートがルーティングされるデータセンターを作成または変更します。</span><span class="sxs-lookup"><span data-stu-id="518d6-220">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
    |<span data-ttu-id="518d6-221">**パラメーターの値**</span><span class="sxs-lookup"><span data-stu-id="518d6-221">**Parameter value**</span></span>|<span data-ttu-id="518d6-222">**データセンターの場所**</span><span class="sxs-lookup"><span data-stu-id="518d6-222">**Datacenter location**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="518d6-223">NAM</span><span class="sxs-lookup"><span data-stu-id="518d6-223">NAM</span></span>  <br/> |<span data-ttu-id="518d6-224">北アメリカ (実際のデータセンターは米国にあります)</span><span class="sxs-lookup"><span data-stu-id="518d6-224">North American (actual datacenters are in the US)</span></span>  <br/> |
    |<span data-ttu-id="518d6-225">EUR</span><span class="sxs-lookup"><span data-stu-id="518d6-225">EUR</span></span>  <br/> |<span data-ttu-id="518d6-226">地区</span><span class="sxs-lookup"><span data-stu-id="518d6-226">Europe</span></span>  <br/> |
    |<span data-ttu-id="518d6-227">APC</span><span class="sxs-lookup"><span data-stu-id="518d6-227">APC</span></span>  <br/> |<span data-ttu-id="518d6-228">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="518d6-228">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="518d6-229">CAN</span><span class="sxs-lookup"><span data-stu-id="518d6-229">CAN</span></span> <br/> |<span data-ttu-id="518d6-230">カナダ</span><span class="sxs-lookup"><span data-stu-id="518d6-230">Canada</span></span>
    
- <span data-ttu-id="518d6-231">**コンテンツ検索をルーティング**する-SharePoint サイトと OneDrive アカウントのコンテンツ検索をサテライトデータセンターにルーティングできます。</span><span class="sxs-lookup"><span data-stu-id="518d6-231">**Route content searches** - You can route the content searches of SharePoint sites and OneDrive accounts to a satellite data center.</span></span> <span data-ttu-id="518d6-232">これは、検索を実行するデータセンターの場所を指定できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="518d6-232">This means you can specify the datacenter location where searches will be run.</span></span>
    
    <span data-ttu-id="518d6-233">次の値を**Region**パラメーター値として使用して、SharePoint サイトと OneDrive の場所を検索するときにコンテンツ検索が実行するデータセンターを制御します。</span><span class="sxs-lookup"><span data-stu-id="518d6-233">Use the following values for the **Region** parameter values to control which datacenter that Content Searches will run in when searching SharePoint sites and OneDrive locations.</span></span> <span data-ttu-id="518d6-234">また、次の表に、によってルーティングされるデータセンターのエクスポートも表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-234">Note that the following table also shows which datacenter exports will be routed through.</span></span> 
  
    |<span data-ttu-id="518d6-235">**パラメーターの値**</span><span class="sxs-lookup"><span data-stu-id="518d6-235">**Parameter value**</span></span>|<span data-ttu-id="518d6-236">**エクスポート用のデータセンタールーティング場所**</span><span class="sxs-lookup"><span data-stu-id="518d6-236">**Datacenter routing locations for export**</span></span>|
    |:-----|:-----|
    |<span data-ttu-id="518d6-237">NAM</span><span class="sxs-lookup"><span data-stu-id="518d6-237">NAM</span></span>  <br/> |<span data-ttu-id="518d6-238">電源</span><span class="sxs-lookup"><span data-stu-id="518d6-238">US</span></span>  <br/> |
    |<span data-ttu-id="518d6-239">EUR</span><span class="sxs-lookup"><span data-stu-id="518d6-239">EUR</span></span>  <br/> |<span data-ttu-id="518d6-240">地区</span><span class="sxs-lookup"><span data-stu-id="518d6-240">Europe</span></span>  <br/> |
    |<span data-ttu-id="518d6-241">APC</span><span class="sxs-lookup"><span data-stu-id="518d6-241">APC</span></span>  <br/> |<span data-ttu-id="518d6-242">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="518d6-242">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="518d6-243">CAN</span><span class="sxs-lookup"><span data-stu-id="518d6-243">CAN</span></span>  <br/> |<span data-ttu-id="518d6-244">電源</span><span class="sxs-lookup"><span data-stu-id="518d6-244">US</span></span>  <br/> |
    |<span data-ttu-id="518d6-245">AUS</span><span class="sxs-lookup"><span data-stu-id="518d6-245">AUS</span></span>  <br/> |<span data-ttu-id="518d6-246">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="518d6-246">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="518d6-247">KOR</span><span class="sxs-lookup"><span data-stu-id="518d6-247">KOR</span></span>  <br/> |<span data-ttu-id="518d6-248">組織の既定のデータセンター</span><span class="sxs-lookup"><span data-stu-id="518d6-248">The organization's default data center</span></span>  <br/> |
    |<span data-ttu-id="518d6-249">GBR</span><span class="sxs-lookup"><span data-stu-id="518d6-249">GBR</span></span>  <br/> |<span data-ttu-id="518d6-250">地区</span><span class="sxs-lookup"><span data-stu-id="518d6-250">Europe</span></span>  <br/> |
    |<span data-ttu-id="518d6-251">JPN</span><span class="sxs-lookup"><span data-stu-id="518d6-251">JPN</span></span>  <br/> |<span data-ttu-id="518d6-252">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="518d6-252">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="518d6-253">IND</span><span class="sxs-lookup"><span data-stu-id="518d6-253">IND</span></span>  <br/> |<span data-ttu-id="518d6-254">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="518d6-254">Asia Pacific</span></span>  <br/> |
    |<span data-ttu-id="518d6-255">語頭</span><span class="sxs-lookup"><span data-stu-id="518d6-255">LAM</span></span>  <br/> |<span data-ttu-id="518d6-256">電源</span><span class="sxs-lookup"><span data-stu-id="518d6-256">US</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="518d6-257">検索アクセス許可フィルターに**Region**パラメーターを指定しない場合、組織の既定の SharePoint 地域が検索され、検索結果が最も近いデータセンターにエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="518d6-257">If you don't specify the **Region** parameter for a search permissions filter, the organizations default SharePoint region will be searched, then search results are exported to the closest datacenter.</span></span> 
  
<span data-ttu-id="518d6-258">ここでは、コンプライアンスの境界に対して検索アクセス許可のフィルターを作成するときに**Region**パラメーターを使用する例を示します。</span><span class="sxs-lookup"><span data-stu-id="518d6-258">Here are examples of using the **Region** parameter when creating search permission filters for compliance boundaries.</span></span> <span data-ttu-id="518d6-259">この場合は、4つ目のコーヒー子会社が北米に配置されており、Coho がヨーロッパにあることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="518d6-259">This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="518d6-260">複数地域環境でコンテンツを検索してエクスポートする場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="518d6-260">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="518d6-261">**Region**パラメーターは、Exchange メールボックスの検索を制御しません。メールボックスを検索すると、すべてのデータセンターが検索されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-261">The **Region** parameter doesn't control searches of Exchange mailboxes; all data centers will be searched when you search mailboxes.</span></span> <span data-ttu-id="518d6-262">検索アクセス許可フィルターを作成または変更するときに、検索できる Exchange メールボックスの範囲を制限するには、 **Filters**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="518d6-262">To limit the scope of which Exchange mailboxes can be searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="518d6-263">電子情報開示管理者が複数の SharePoint 地域を検索する必要がある場合は、その電子情報開示マネージャーに対して別のユーザーアカウントを作成する必要があります。これを検索権限フィルターで使用して、SharePoint サイトまたは OneDrive アカウントが配置されている。</span><span class="sxs-lookup"><span data-stu-id="518d6-263">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you'll need to create a different user account for that eDiscovery manager that can be used in the search permissions filter to specify the alternate region where the SharePoint sites or OneDrive accounts are located.</span></span>
    
- <span data-ttu-id="518d6-264">SharePoint および OneDrive でコンテンツを検索する場合、 **Region**パラメーターは、電子情報開示マネージャーが電子情報開示の調査を行うメインまたはサテライトの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="518d6-264">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations.</span></span> <span data-ttu-id="518d6-265">電子情報開示マネージャーが、検索アクセス許可フィルターで指定されている地域外の SharePoint および OneDrive サイトを検索すると、検索結果は返されません。</span><span class="sxs-lookup"><span data-stu-id="518d6-265">If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results will be returned.</span></span> 
    
- <span data-ttu-id="518d6-266">検索結果をエクスポートすると、すべてのコンテンツの場所 (Exchange、Skype for business、SharePoint、OneDrive、およびコンテンツ検索ツールを使用して検索できる他の Office 365 サービスを含む) からのコンテンツが、**Region**パラメーターで指定されたデータセンター。</span><span class="sxs-lookup"><span data-stu-id="518d6-266">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive and other Office 365 services that you can search by using the Content Search tool) will be uploaded to the Azure storage location in the data center that's specified by the **Region** parameter.</span></span> <span data-ttu-id="518d6-267">これにより、管理された境界を越えてコンテンツをエクスポートすることを許可しないことで、組織のコンプライアンスを実現できます。</span><span class="sxs-lookup"><span data-stu-id="518d6-267">This helps organizations stay within compliance by not allowing content to be exported across controlled borders.</span></span> <span data-ttu-id="518d6-268">検索アクセス許可フィルターで地域が指定されていない場合、コンテンツは組織の既定の地域にアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="518d6-268">If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="518d6-269">既存の検索アクセス許可フィルターを編集して、次のコマンドを実行し、地域を追加または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="518d6-269">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="518d6-270">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="518d6-270">Frequently asked questions</span></span>

 <span data-ttu-id="518d6-271">**検索アクセス許可フィルターを作成および管理できるユーザー (new-compliancesecurityfilter および new-compliancesecurityfilter コマンドレットを使用)**</span><span class="sxs-lookup"><span data-stu-id="518d6-271">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets )?**</span></span>
  
<span data-ttu-id="518d6-272">検索アクセス許可のフィルターを作成、表示、および変更するには、セキュリティ&amp;コンプライアンスセンターで、組織の管理役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="518d6-272">To create, view and modify search permissions filters, you have to be a member of the Organization Management role group in the Security &amp; Compliance Center.</span></span>
  
 <span data-ttu-id="518d6-273">**電子情報開示マネージャーが複数の機関にまたがる複数の役割グループに割り当てられている場合、どのようにして1つのエージェンシーでコンテンツを検索しますか?**</span><span class="sxs-lookup"><span data-stu-id="518d6-273">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="518d6-274">電子情報開示マネージャーは、検索を特定のエージェンシーに制限するパラメーターを検索クエリに追加できます。</span><span class="sxs-lookup"><span data-stu-id="518d6-274">The eDiscovery manager can add parameters to their search query that will restrict the search to a specific agency.</span></span> <span data-ttu-id="518d6-275">たとえば、組織で**CustomAttribute10**プロパティを指定してエージェンシーを区別する場合、次のものを検索クエリに追加して、特定のエージェンシーのメールボックスと OneDrive `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`アカウントを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="518d6-275">For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="518d6-276">**検索アクセス許可フィルターでコンプライアンス属性として使用されている属性の値が変更された場合はどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="518d6-276">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="518d6-277">検索アクセス許可フィルターで使用される属性の値が変更された場合に、コンプライアンスの境界を適用するには最大3日間かかります。</span><span class="sxs-lookup"><span data-stu-id="518d6-277">It takes up to 3 days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed.</span></span> <span data-ttu-id="518d6-278">たとえば、Contoso 社のシナリオでは、第4のコーヒーエージェンシーのユーザーが Coho (コーホーワイナリー) エージェンシーに転送されるとします。</span><span class="sxs-lookup"><span data-stu-id="518d6-278">For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency.</span></span> <span data-ttu-id="518d6-279">その結果、ユーザーオブジェクトの**Department**属性の値が、"4 *thコーヒー* " から " *cohowinery* " に変更されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-279">As a result, the value of the **Department** attribute on the user object is changed from  *FourthCoffee*  to  *CohoWinery*  .</span></span> <span data-ttu-id="518d6-280">このような状況では、4番目のコーヒー eDiscovery および投資家が、属性が変更されてから3日後にそのユーザーの検索結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="518d6-280">In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up 3 days after the attribute is changed.</span></span> <span data-ttu-id="518d6-281">同様に、Coho の電子情報開示マネージャーおよび調査担当者がユーザーの検索結果を取得するまで最大3日間かかります。</span><span class="sxs-lookup"><span data-stu-id="518d6-281">Similarly, it will take up to 3 days before Coho Winery eDiscovery managers and investigators will get search results for the user.</span></span> 
  
 <span data-ttu-id="518d6-282">**電子情報開示マネージャーは、2つの異なるコンプライアンス境界からのコンテンツを表示できますか。**</span><span class="sxs-lookup"><span data-stu-id="518d6-282">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="518d6-283">はい。</span><span class="sxs-lookup"><span data-stu-id="518d6-283">Yes.</span></span> <span data-ttu-id="518d6-284">この操作を行うには、両方のエージェンシーに対して可視性を持つ役割グループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="518d6-284">This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="518d6-285">**検索アクセス許可フィルターは、電子情報開示のケースホールド、Office 365 アイテム保持ポリシー、DLP のいずれかに対して機能しますか?**</span><span class="sxs-lookup"><span data-stu-id="518d6-285">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="518d6-286">いいえ (現時点では不可)</span><span class="sxs-lookup"><span data-stu-id="518d6-286">No, not at this time</span></span>
  
 <span data-ttu-id="518d6-287">**コンテンツのエクスポート先を制御する地域を指定したが、その地域に sharepoint 組織が存在しない場合、sharepoint を検索することはできますか?**</span><span class="sxs-lookup"><span data-stu-id="518d6-287">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="518d6-288">検索アクセス許可フィルターで指定されている地域が組織内に存在しない場合は、既定の地域が検索されます。</span><span class="sxs-lookup"><span data-stu-id="518d6-288">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="518d6-289">**組織内で作成できる検索アクセス許可のフィルターの最大数はいくつですか。**</span><span class="sxs-lookup"><span data-stu-id="518d6-289">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="518d6-290">組織内で作成できる検索アクセス許可フィルターの数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="518d6-290">There is no limit to the number of search permissions filters that can be created in an organization.</span></span> <span data-ttu-id="518d6-291">ただし、100を超える検索アクセス許可フィルターがある場合は、検索のパフォーマンスが影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="518d6-291">However, search performance will be impacted when there are more than 100 search permissions filters.</span></span> <span data-ttu-id="518d6-292">組織内の検索アクセス許可フィルターの数を可能な限り小さくするには、Exchange、SharePoint、および OneDrive のルールを可能な限り1つの検索アクセス許可フィルターにまとめるフィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="518d6-292">To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
