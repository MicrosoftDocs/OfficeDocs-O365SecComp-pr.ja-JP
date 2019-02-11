---
title: Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 1b45c82f-26c8-44fb-9f3b-b45436fe2271
description: コンプライアンスの境界を使用して、Office 365 組織内で、電子的証拠開示マネージャーが検索できるユーザー コンテンツの場所を制御する論理的な境界を作成します。コンプライアンスの境界を使用して、検索のアクセス許可がどのようなメールボックス、SharePoint サイトを制御する (も呼び出されたコンプライアンス セキュリティ フィルター) をフィルタ リングし、OneDrive アカウントは、特定のユーザーによって検索できます。
ms.openlocfilehash: 23594673e70be4b960c463ae2344c2f4b0fd0cbe
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768018"
---
# <a name="set-up-compliance-boundaries-for-ediscovery-investigations-in-office-365"></a><span data-ttu-id="cad48-104">Office 365 での電子情報開示調査のためにコンプライアンスの境界を設定する</span><span class="sxs-lookup"><span data-stu-id="cad48-104">Set up compliance boundaries for eDiscovery investigations in Office 365</span></span>

<span data-ttu-id="cad48-p102">コンプライアンスの境界では、Office 365 組織内のユーザー コンテンツの場所 (メールボックス、SharePoint サイトでは、OneDrive アカウントなど) 電子的証拠開示マネージャーが検索できるを制御する論理的な境界を作成します。さらに、コンプライアンスの境界管理、法務、人事管理、または組織内の他の調査を管理するために使用される電子的証拠開示の場合にアクセスできるユーザーです。コンプライアンスの境界の必要性は必要なは、地理的な boarders や規制を尊重する必要がある複数の国の企業および政府機関は、さまざまな政府機関は、多くの場合がよくあります。Office 365 に対応できるコンプライアンスの境界のようにこれらの要件を実行すると、コンテンツの検索と電子的証拠開示のサポート案件の管理の調査。</span><span class="sxs-lookup"><span data-stu-id="cad48-p102">Compliance boundaries create logical boundaries within an Office 365 organization that control the user content locations (such as mailboxes, SharePoint sites, and OneDrive accounts) that eDiscovery managers can search. Additionally, compliance boundaries control who can access eDiscovery cases used to manage the legal, human resources, or other investigations within your organization. The need for compliance boundaries is often necessary for multi-nations corporations that have to respect geographical boarders and regulations, and for governments, which are often divided into different agencies. In Office 365, compliance boundaries help you meet these requirements when performing content searches and managing investigations with eDiscovery cases.</span></span>
  
<span data-ttu-id="cad48-109">コンプライアンスの境界がどのように動作するかを説明するのに次の図の例を使用します。</span><span class="sxs-lookup"><span data-stu-id="cad48-109">We'll use the example in the following illustration to explain how compliance boundaries work.</span></span>
  
![コンプライアンスの境界で構成されているアクセス許可の検索フィルターの機関や管理者の役割へのアクセス制御グループの eDisocovery の場合にアクセスを制御すること](media/5c206cc8-a6eb-4d6b-a3a5-21e158791f9a.png)
  
<span data-ttu-id="cad48-p103">この例では、Contoso 社は、Fourth Coffee とコーホー ワイナリーの 2 つの子会社で構成される Office 365 組織です。マネージャーの電子的証拠開示および調査官しか検索 Exchange メールボックス、OneDrive のアカウント、および SharePoint サイトの広告代理店のビジネスが必要です。さらに、電子的証拠開示マネージャーおよび調査官のみを確認できます電子的証拠開示の場合、その機関でのみのメンバーがいる場合をアクセスすることができ、。コンプライアンスの境界がこれらの要件に対応する方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p103">In this example, Contoso LTD is an Office 365 organization that consists of two subsidiaries, Fourth Coffee and Coho Winery. The business requires that eDiscovery mangers and investigators can only search the Exchange mailboxes, OneDrive accounts, and SharePoint sites in their agency. Additionally, eDiscovery managers and investigators can only see eDiscovery cases in the in their agency, and they can only access the cases that they're a member of. Here's how compliance boundaries meet these requirements.</span></span>
  
- <span data-ttu-id="cad48-p104">コンテンツの検索コントロールの機能を電子的証拠開示マネージャーと調査官が検索できるコンテンツの場所にフィルタ リング検索のアクセス許可。これは、電子的証拠開示マネージャーと Fourth Coffee の広告代理店の調査官しか検索コンテンツの場所、Fourth Coffee の子会社のことを意味します。コーホー ワイナリーの関連会社に同じ制限が適用されます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p104">The search permissions filtering functionality in Content Search controls the content locations that eDiscovery managers and investigators can search. This means eDiscovery managers and investigators in the Fourth Coffee agency can only search content locations in the Fourth Coffee subsidiary. The same restriction applies to the Coho Winery subsidiary.</span></span>
    
    <span data-ttu-id="cad48-p105">ロールは、Office 365 のセキュリティで電子的証拠開示の場合を見ることができるコントロールをグループ化&amp;コンプライアンス センターです。これは、電子的証拠開示マネージャーおよび調査官だけを見られる、政府機関で電子的証拠開示の場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p105">Role groups control who can see the eDiscovery cases in the Office 365 Security &amp; Compliance Center. This means that eDiscovery managers and investigators can only see the eDiscovery cases in their agency.</span></span>
    
- <span data-ttu-id="cad48-p106">役割グループ、ユーザー、電子的証拠開示の場合にメンバーを割り当てることができますを制御します。これは、電子的証拠開示マネージャーおよび調査官のみに割り当てることがメンバーのメンバーは、自身の場合を意味します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p106">Role groups also control who can assign members to an eDiscovery case. This means eDiscovery managers and investigators can only assign members to cases that they themselves are a member of.</span></span>
    
<span data-ttu-id="cad48-122">コンプライアンスの境界を設定するためのプロセスを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cad48-122">Here's the process for setting up compliance boundaries:</span></span>
  
[<span data-ttu-id="cad48-123">ステップ 1: 政府機関を定義するのにはユーザーの属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="cad48-123">Step 1: Identify a user attribute to define your agencies</span></span>](#step-1-identify-a-user-attribute-to-define-your-agencies)

[<span data-ttu-id="cad48-124">手順 2: ファイルの OneDrive アカウントにユーザーの属性を同期するには、マイクロソフトのサポートと要求</span><span class="sxs-lookup"><span data-stu-id="cad48-124">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>](#step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts)

[<span data-ttu-id="cad48-125">手順 3: 各機関の役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-125">Step 3: Create a role group for each agency</span></span>](#step-3-create-a-role-group-for-each-agency)

[<span data-ttu-id="cad48-126">手順 4: コンプライアンスの境界を適用する検索のアクセス許可フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-126">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>](#step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary)

[<span data-ttu-id="cad48-127">機関内の調査の電子的証拠開示のケースを作成する手順 5。</span><span class="sxs-lookup"><span data-stu-id="cad48-127">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>](#step-5-create-an-ediscovery-case-for-an-intra-agency-investigations)
  
## <a name="step-1-identify-a-user-attribute-to-define-your-agencies"></a><span data-ttu-id="cad48-128">ステップ 1: 政府機関を定義するのにはユーザーの属性を識別します。</span><span class="sxs-lookup"><span data-stu-id="cad48-128">Step 1: Identify a user attribute to define your agencies</span></span>

<span data-ttu-id="cad48-p107">最初のステップでは、Azure Active Directory 属性を使用するを選択するのには、政府機関を定義します。電子情報開示を制限する検索のアクセス許可フィルターを作成するには、この属性に特定の値が割り当てられているユーザーのコンテンツの場所のみを検索するにはマネージャーには、この属性が使用されます。たとえば、contoso 社**所属**の属性を使用することを決定したとします。Fourth Coffee の関連会社内のユーザーに対しては、この属性の値になります`FourthCoffee`「コーホーワイナリー」と関連会社でユーザー値なると`CohoWinery`。手順 4 で、これを使用します`attribute:value`ユーザーを制限するための組み合わせ (たとえば、*部門: FourthCoffee* ) コンテンツの電子的証拠開示マネージャーが検索できる場所です。</span><span class="sxs-lookup"><span data-stu-id="cad48-p107">The first step is to choose an Azure Active Directory attribute to use that will define your agencies. This attribute will be used to create the search permissions filter that limits an eDiscovery manager to search only the content locations of users who are assigned a specific value for this attribute. For example, let's say Contoso decides to use the **Department** attribute. The value for this attribute for users in the Fourth Coffee subsidiary would be  `FourthCoffee`  and the value for users in Coho Winery subsidiary would be `CohoWinery`. In Step 4, you'll use this  `attribute:value`  pair (for example,  *Department:FourthCoffee*  ) to limit the user content locations that eDiscovery managers can search.</span></span> 
  
<span data-ttu-id="cad48-134">境界を遵守するために使用できる Azure Active Directory ユーザー属性の一覧を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cad48-134">Here's a list of Azure Active Directory user attributes that you can use for compliance boundaries:</span></span>
  
- <span data-ttu-id="cad48-135">Company</span><span class="sxs-lookup"><span data-stu-id="cad48-135">Company</span></span>
    
- <span data-ttu-id="cad48-136">CustomAttribute1 - CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="cad48-136">CustomAttribute1 - CustomAttribute15</span></span>
    
- <span data-ttu-id="cad48-137">部署</span><span class="sxs-lookup"><span data-stu-id="cad48-137">Department</span></span>
    
- <span data-ttu-id="cad48-138">事業所</span><span class="sxs-lookup"><span data-stu-id="cad48-138">Office</span></span>
    
<span data-ttu-id="cad48-139">多くのユーザー属性は、メールボックスで使用できる、特に Exchange が、上記の属性は、OneDrive で現在サポートされているだけのものです。</span><span class="sxs-lookup"><span data-stu-id="cad48-139">Although more user attributes are available, particularly for Exchange mailboxes, the attributes listed above are the only ones currently supported by OneDrive.</span></span>
  
## <a name="step-2-file-a-request-with-microsoft-support-to-synchronize-the-user-attribute-to-onedrive-accounts"></a><span data-ttu-id="cad48-140">手順 2: ファイルの OneDrive アカウントにユーザーの属性を同期するには、マイクロソフトのサポートと要求</span><span class="sxs-lookup"><span data-stu-id="cad48-140">Step 2: File a request with Microsoft Support to synchronize the user attribute to OneDrive accounts</span></span>

<span data-ttu-id="cad48-p108">組織の OneDrive のすべてのアカウントに手順 1 で選択した Azure Active Directory 属性を同期するのにはマイクロソフトのサポートの要求をファイルには、次の手順です。この同期が発生した場合、属性とその値) という名前の SharePoint で非表示の管理プロパティにマップする手順 1 で選択した`ComplianceAttribute`。手順 4 で OneDrive の検索のアクセス許可フィルターを作成するのには、この属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p108">The next step is to file a request with Microsoft Support to synchronize the Azure Active Directory attribute that you chose in Step 1 to all OneDrive accounts in your organization. After this synchronization occurs, the attribute (and its value) that you chose in Step 1 will be mapped to a hidden managed property in SharePoint named  `ComplianceAttribute`. You'll use this attribute to create the search permissions filter for OneDrive in Step 4.</span></span>
  
<span data-ttu-id="cad48-144">マイクロソフトのサポート要求を送信する場合については、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cad48-144">Include the following information when you submit the request to Microsoft support:</span></span>
  
- <span data-ttu-id="cad48-145">Office 365 組織の既定のドメイン名</span><span class="sxs-lookup"><span data-stu-id="cad48-145">The default domain name of your Office 365 organization</span></span>
    
- <span data-ttu-id="cad48-146">(手順 1) から Azure Active Directory 属性の名前</span><span class="sxs-lookup"><span data-stu-id="cad48-146">The name of the Azure Active Directory attribute (from Step 1)</span></span>
    
- <span data-ttu-id="cad48-p109">次のタイトルまたはサポート要求の目的の説明:」を有効にする OneDrive のビジネス同期と Azure アクティブ ディレクトリのコンプライアンス セキュリティ フィルター」です。要求を実装する Office 365 電子的証拠開示エンジニア リング チームに要求をルーティングするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p109">The following title or description of the purpose of the support request: "Enable OneDrive for Business Synchronization with Azure Active Directory for Compliance Security Filters". This will help route the request to the Office 365 eDiscovery engineering team who will implement the request.</span></span>
    
<span data-ttu-id="cad48-p110">エンジニア リングの変更が加えられるし、属性が OneDrive に同期されている、マイクロソフトのサポート送信するとビルド番号に変更が加えられたと展開の予定日です。展開プロセスは、サポート リクエストを送信した後、4 ~ 6 週間を通常は注意してください。</span><span class="sxs-lookup"><span data-stu-id="cad48-p110">After the engineering change is made and the attribute is synchronized to OneDrive, Microsoft Support will send you the build number that the change was made in and an estimated deployment date. Note that the deployment process usually takes 4-6 weeks after you submit the support request.</span></span>
  
 <span data-ttu-id="cad48-p111">**重要な:** 変更を展開する前に、手順 5 から手順 3 を完了できます。変更が配置された後まで検索のアクセス許可のフィルターで指定されている OneDrive のサイトからドキュメントを返すコンテンツの検索を実行しているされません。</span><span class="sxs-lookup"><span data-stu-id="cad48-p111">**Important:** You can complete Step 3 through Step 5 before the change is deployed. But running content searches won't return documents from OneDrive sites specified in the search permissions filter until after the change is deployed.</span></span> 
  
## <a name="step-3-create-a-role-group-for-each-agency"></a><span data-ttu-id="cad48-153">手順 3: 各機関の役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-153">Step 3: Create a role group for each agency</span></span>

<span data-ttu-id="cad48-p112">次の手順は、Office 365 のセキュリティの役割グループを作成する&amp;、政府機関の連携はコンプライアンス センターです。コピーして、組み込みの電子的証拠開示マネージャー グループ、メンバーの追加、適切なお客様のニーズに該当することができない可能性があるロールを削除する新しい役割グループを作成することをお勧めします。電子的証拠開示に関連する役割の詳細についてを参照してください[Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター](assign-ediscovery-permissions.md)です。</span><span class="sxs-lookup"><span data-stu-id="cad48-p112">The next step is to create the role groups in the Office 365 Security &amp; Compliance Center that will align with your agencies. We recommend that you create a new role group by copying the built-in eDiscovery Managers group, adding the appropriate members, and removing roles that may not be applicable to your needs. For more information about eDiscovery-related roles, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
<span data-ttu-id="cad48-157">役割グループを作成するには、セキュリティの**アクセス許可**] ページに移動&amp;コンプライアンス センター調査を管理するためにコンプライアンスの境界および電子的証拠開示のサポート案件を使用する各省庁の各チームの役割グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-157">To create the role groups, go to the **Permissions** page in the Security &amp; Compliance Center and create a role group for each team in each agency that will use compliance boundaries and eDiscovery cases to manage investigations.</span></span> 
  
<span data-ttu-id="cad48-158">Contoso のコンプライアンスの境界を使用すると、4 つの役割グループを作成する必要があるし、それぞれに適切なメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="cad48-158">Using the Contoso compliance boundaries scenario, four role groups need to be created and the appropriate members added to each one.</span></span>
  
- <span data-ttu-id="cad48-159">4 番目のコーヒーの電子的証拠開示マネージャー</span><span class="sxs-lookup"><span data-stu-id="cad48-159">Fourth Coffee eDiscovery Managers</span></span>
    
- <span data-ttu-id="cad48-160">コーヒー 4 つ目の調査官</span><span class="sxs-lookup"><span data-stu-id="cad48-160">Fourth Coffee Investigators</span></span>
    
- <span data-ttu-id="cad48-161">Coho Winery 電子的証拠開示マネージャー</span><span class="sxs-lookup"><span data-stu-id="cad48-161">Coho Winery eDiscovery Managers</span></span>
    
- <span data-ttu-id="cad48-162">Coho Winery 調査官</span><span class="sxs-lookup"><span data-stu-id="cad48-162">Coho Winery Investigators</span></span>
    

  
## <a name="step-4-create-a-search-permissions-filter-to-enforce-the-compliance-boundary"></a><span data-ttu-id="cad48-163">手順 4: コンプライアンスの境界を適用する検索のアクセス許可フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-163">Step 4: Create a search permissions filter to enforce the compliance boundary</span></span>
<span data-ttu-id="cad48-164"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="cad48-164"></span></span>

<span data-ttu-id="cad48-p113">各機関の役割グループを作成したら、次の手順はその特定の機関にそれぞれの役割グループに関連付ける検索のアクセス許可フィルターを作成するのには、し、コンプライアンスの境界を定義します。各機関の 1 つの検索のアクセス許可のフィルターを作成する必要があります。セキュリティ アクセス許可のフィルターを作成する方法の詳細については、[アクセス許可を構成するコンテンツの検索のフィルター処理](permissions-filtering-for-content-search.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad48-p113">After you've created role groups for each agency, the next step is to create the search permissions filters that associate each role group to its specific agency and defines the compliance boundary itself. You need to create one search permissions filter for each agency. For more information about creating security permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
  
<span data-ttu-id="cad48-168">ここでは、境界を遵守するために使用される検索のアクセス許可フィルターを作成するために使用される構文です。</span><span class="sxs-lookup"><span data-stu-id="cad48-168">Here's the syntax that's used to create a search permissions filter used for compliance boundaries.</span></span>

```
New-ComplianceSecurityFilter -FilterName <name of filter> -Users <role groups> -Filters "Mailbox_<Compliance attribute from Step 1>  -eq '<AttributeVale> '", "Site_ComplianceAttribute  -eq <AttributeValue>' -or Site_Path -like <SharePointURL> *'" -Action <Action >
```
  
<span data-ttu-id="cad48-169">コマンドの各パラメーターの説明を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="cad48-169">Here's a description of each parameter in the command:</span></span>
  
-  <span data-ttu-id="cad48-p114">`FilterName`-フィルターの名前を指定します。使用について説明またはフィルターを適用する代理店を識別する名前が使用されます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p114">`FilterName` - Specifies the name of the filter. Use a name that describes or identifies the agency that filter will be used in.</span></span> 
    
-  <span data-ttu-id="cad48-p115">`Users`-ユーザーまたはグループを実行するコンテンツの検索操作に適用されるフィルターを取得するユーザーを指定します。コンプライアンスの境界の代理店のためのフィルターを作成することで、ロール グループ (手順 3 で作成した場合) を指定します。複数値パラメーターは、コンマで区切られた 1 つまたは複数の役割グループを含めることができますので注意してください。</span><span class="sxs-lookup"><span data-stu-id="cad48-p115">`Users` - Specifies the users or groups who get this filter applied to the Content Search actions they perform. For compliance boundaries, this parameter specifies the role groups (that you created in Step 3) in the agency that you're creating the filter for. Note this is a multi-value parameter so you can include one or more role groups, separated by commas.</span></span> 
    
-  <span data-ttu-id="cad48-p116">`Filters`-フィルターの検索条件を指定します。コンプライアンスの境界は、次のフィルターを定義します。各 1 つは、ユーザーのコンテンツの場所に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p116">`Filters` - Specifies the search criteria for the filter. For the compliance boundaries, you will define the following filters. Each one applies to a user content location.</span></span> 
    
  -  <span data-ttu-id="cad48-p117">`Mailbox`-の役割グループが定義されているメールボックスを指定する、`Users`のパラメーターを検索できます。コンプライアンスの境界の*ComplianceAttribute*は、手順 1 で特定したのと同じ属性および*AttributeValue*機関を指定します。このフィルターは特定の政府機関にのみメールボックスを検索するロール グループのメンバーを許可します。たとえば、 `"Mailbox_Department -eq 'FourthCoffee'"` 。</span><span class="sxs-lookup"><span data-stu-id="cad48-p117">`Mailbox` - Specifies the mailboxes that the role groups defined in the  `Users` parameter can search. For compliance boundaries,  *ComplianceAttribute*  is the same attribute that you identified in Step 1 and  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the mailboxes in a specific agency; for example,  `"Mailbox_Department -eq 'FourthCoffee'"` .</span></span> 
    
  -  <span data-ttu-id="cad48-p118">`Site`-の役割グループが定義されている OneDrive のアカウントを指定する、`Users`のパラメーターを検索できます。OneDrive フィルターは、実際の文字列を使用して、 `ComplianceAttribute`。手順 1 で特定した、手順 2 で送信したサポート ・ リクエストの結果として OneDrive のアカウントに同期するのと同じ属性にマッピングします。 *AttributeValue*は、機関を指定します。このフィルターは特定の政府機関でのみ OneDrive のアカウントを検索するロール グループのメンバーを許可します。たとえば、 `"Site_ComplianceAttribute -eq 'FourthCoffee'"`。</span><span class="sxs-lookup"><span data-stu-id="cad48-p118">`Site` - Specifies the OneDrive accounts that the role groups defined in the  `Users` parameter can search. For the OneDrive filter, use the actual string  `ComplianceAttribute`; this will map to the same attribute that you identified in Step 1 and that's synchronized to OneDrive accounts as a result of the support request that you submitted in Step 2;  *AttributeValue*  specifies the agency. This filter allow members of the role group to only search the OneDrive accounts in a specific agency; for example,  `"Site_ComplianceAttribute -eq 'FourthCoffee'"`.</span></span>
    
  -  <span data-ttu-id="cad48-p119">`Site_Path`-の役割グループが定義されている SharePoint サイトを指定する、`Users`のパラメーターを検索できます。*SharePointURL*では、サイトを指定の機関の役割グループのメンバーを検索できます。例えば`"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span><span class="sxs-lookup"><span data-stu-id="cad48-p119">`Site_Path` - Specifies the SharePoint sites that the role groups defined in the  `Users` parameter can search. The  *SharePointURL*  specifies the sites in the agency that members of the role group can search; for example,  `"Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'"`</span></span>
    
-  <span data-ttu-id="cad48-p120">`Action`-フィルターを適用するコンプライアンスの検索動作の種類を指定します。たとえば、`-Action Search`だけに適用、フィルターの役割グループのメンバーが定義されている場合、`Users`パラメーターは、コンテンツの検索を実行します。この例では、検索結果をエクスポートするときは、フィルターを適用しません。コンプライアンスの境界を使用して`-Action All`ため、すべてのアクションを検索するフィルターが適用されます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p120">`Action` - Specifies the type of Compliance Search action that the filter is applied to. For example,  `-Action Search` would only apply the filter when members of the role groups defined in the  `Users` parameter runs a content search. In this case, the filter wouldn't be applied when exporting search results. For compliance boundaries, use  `-Action All` so the filter applies to all search actions.</span></span> 
    
    <span data-ttu-id="cad48-190">コンテンツの検索操作のリストは、[アクセス許可を構成するコンテンツの検索をフィルタ リング](permissions-filtering-for-content-search.md#new-compliancesecurityfilter)で「新規 ComplianceSecurityFilter」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cad48-190">For a list of the Content Search actions, see the "New-ComplianceSecurityFilter" section in [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md#new-compliancesecurityfilter).</span></span>
    
<span data-ttu-id="cad48-191">Contoso 社のコンプライアンスの境界のシナリオをサポートするために作成される 2 つの検索のアクセス許可のフィルターの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="cad48-191">Here are examples of the two search permissions filters that would be created to support the Contoso compliance boundaries scenario.</span></span>
  
 <span data-ttu-id="cad48-192">**コーヒーハウス**</span><span class="sxs-lookup"><span data-stu-id="cad48-192">**Fourth Coffee**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_ComplianceAttribute -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL
```
   
 <span data-ttu-id="cad48-193">**コーホー ワイナリー**</span><span class="sxs-lookup"><span data-stu-id="cad48-193">**Coho Winery**</span></span>

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_ComplianceAttribute -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL
```

## <a name="step-5-create-an-ediscovery-case-for-an-intra-agency-investigations"></a><span data-ttu-id="cad48-194">機関内の調査の電子的証拠開示のケースを作成する手順 5。</span><span class="sxs-lookup"><span data-stu-id="cad48-194">Step 5: Create an eDiscovery case for an intra-agency investigations</span></span>

<span data-ttu-id="cad48-p121">最後の手順は、セキュリティの新しい電子的証拠開示のサポート案件を作成するのには、&amp;コンプライアンス センター、役割グループに追加し、手順 3 で作成した-大文字と小文字のメンバーとして。これは、コンプライアンスの境界を使用する場合の 2 つの重要な特性が得られます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p121">The final step is to create a new eDiscovery case in the Security &amp; Compliance Center and then add the role group—that you created in Step 3—as a member of the case. This results in two important characteristics of using compliance boundaries:</span></span>
  
- <span data-ttu-id="cad48-p122">表示して、セキュリティの場合にアクセスできる場合に追加の役割グループのメンバーのみ&amp;コンプライアンス センターです。たとえば、4 つ目のコーヒーの調査官の役割グループが、大文字と小文字の唯一のメンバーである場合は、し、Fourth Coffee の電子的証拠開示マネージャー ロールのグループ (または、他の役割グループのメンバー) のメンバーことはできませんを参照するか、大文字と小文字をアクセスします。</span><span class="sxs-lookup"><span data-stu-id="cad48-p122">Only members of the role group added to the case will be able to see and access the case in the Security &amp; Compliance Center. For example, if the Fourth Coffee Investigators role group is the only member of a case, then members of the Fourth Coffee eDiscovery Managers role group (or members of any other role group) won't be able to see or access the case.</span></span>
    
- <span data-ttu-id="cad48-199">サポート案件に割り当てられた役割グループのメンバーは、サポート案件に関連付けられている検索を実行するときにのみできるようになります (で定義されている手順 4 で作成した検索のアクセス許可のフィルターします。)、機関内でのコンテンツの場所を検索</span><span class="sxs-lookup"><span data-stu-id="cad48-199">When a member of the role group assigned to a case runs a search associated with the case, they will only be able to search the content locations within their agency (which is defined by the search permissions filter that you created in Step 4.)</span></span>


<span data-ttu-id="cad48-200">新しいケースを作成し、メンバーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="cad48-200">To create a new case and assign members:</span></span>
    
1. <span data-ttu-id="cad48-201">セキュリティで**電子的証拠開示**のページに&amp;コンプライアンス センターと新しいケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-201">Go to the **eDiscovery** page in the Security &amp; Compliance Center and create a new case.</span></span> 
    
2. <span data-ttu-id="cad48-202">電子的証拠開示のサポート案件の一覧で、作成した、大文字と小文字の名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad48-202">In the list of eDiscovery cases, click the name of the case you just created.</span></span>
    
3. <span data-ttu-id="cad48-203">**管理ここ**フライアウト] ページで、**役割グループの管理**] の下でをクリックして![の追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)**追加**します。</span><span class="sxs-lookup"><span data-stu-id="cad48-203">In the **Manage this case** flyout page, under **Mange role groups**, click ![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **Add**.</span></span>
    
    ![電子的証拠開示のサポート案件のメンバーとしての役割グループを追加します。](media/f8b4b557-01b9-4388-85be-b5b5ab7c5629.png)
  
4. <span data-ttu-id="cad48-205">役割グループの一覧で手順 3 で作成した役割グループのいずれかを選択し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad48-205">In the list of role groups, select one of the role groups that you created in Step 3, and click **Add**.</span></span>
    
5. <span data-ttu-id="cad48-206">変更を保存するのには**このサポート案件の管理**のフライアウトで [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cad48-206">Click **Save** on the **Manage this case** flyout to save the change.</span></span> 

## <a name="compliance-boundary-limitations"></a><span data-ttu-id="cad48-207">境界の制限事項を遵守</span><span class="sxs-lookup"><span data-stu-id="cad48-207">Compliance boundary limitations</span></span>

<span data-ttu-id="cad48-208">場合は電子的証拠開示およびコンプライアンスの境界の調査を使用する管理する場合は、次の制限事項に留意してください。</span><span class="sxs-lookup"><span data-stu-id="cad48-208">Keep the following limitations in mind when managing eDiscovery cases and investigations that use of compliance boundaries.</span></span>
  
- <span data-ttu-id="cad48-p123">作成すると、コンテンツの検索を実行している、政府機関が外部にあるコンテンツの場所を選択できます。ただし、検索のアクセス許可のフィルターがあるためは、これらの場所からコンテンツを検索結果に含まれません。</span><span class="sxs-lookup"><span data-stu-id="cad48-p123">When creating and running a Content Search, you can select content locations that are outside of your agency. However, because of the search permissions filter, content from those locations won't be included in the search results.</span></span>
    
- <span data-ttu-id="cad48-p124">コンプライアンスの境界は、電子的証拠開示の場合の保留を適用しないでください。1 つの機関で、電子的証拠開示マネージャーは、保留中のさまざまな機関でユーザーを追加できることを意味します。ただし、コンプライアンスの境界は、電子的証拠開示マネージャーが配置された保留中のユーザーのコンテンツの場所を検索する場合に適用されます。つまり、電子的証拠開示マネージャーはユーザーのコンテンツの場所が検索をする、いても、それらのユーザーを配置することを保持はありません。</span><span class="sxs-lookup"><span data-stu-id="cad48-p124">Compliance boundaries don't apply to holds in eDiscovery cases. That means an eDiscovery manager in one agency can place a user in a different agency on hold. However, the compliance boundary will be enforced if the eDiscovery manager searches the content locations of the user who was placed on hold. That means the eDiscovery manager won't be able search the user's content locations, even though they were able to place the user on hold.</span></span>
    
    <span data-ttu-id="cad48-215">また、統計情報は、機関内のコンテンツの場所にのみ適用されますを保持します。</span><span class="sxs-lookup"><span data-stu-id="cad48-215">Additionally, hold statistics will only apply to content locations in the agency.</span></span>
    
- <span data-ttu-id="cad48-216">Exchange パブリック フォルダーへのアクセス許可の検索フィルターが適用されません。</span><span class="sxs-lookup"><span data-stu-id="cad48-216">Search permissions filters aren't applied to Exchange public folders.</span></span>

## <a name="searching-and-exporting-content-in-multi-geo-environments"></a><span data-ttu-id="cad48-217">検索や、複数地域の環境でのコンテンツをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cad48-217">Searching and exporting content in Multi-Geo environments</span></span>

<span data-ttu-id="cad48-218">検索のアクセス許可のフィルターでは、エクスポート用のコンテンツがルーティングされ、 [SharePoint の複数の地域の環境](https://go.microsoft.com/fwlink/?linkid=860840)での SharePoint サイトおよび OneDrive のアカウントを検索する場合、どのデータ ・ センターを検索できるを制御することもできます。</span><span class="sxs-lookup"><span data-stu-id="cad48-218">Search permissions filters also let you control where content is routed for export and which datacenter can be searched when searching SharePoint sites and OneDrive accounts in a [SharePoint Multi-Geo environment](https://go.microsoft.com/fwlink/?linkid=860840):</span></span>
  
- <span data-ttu-id="cad48-p125">特定のデータ ・ センターから検索結果をエクスポートします。つまり、データ ・ センターの場所から結果をエクスポートする検索を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p125">Export search results from a specific data center. This means that you can specify the data center location that search results will be exported from.</span></span>
    
- <span data-ttu-id="cad48-p126">SharePoint サイトおよび衛星データ ・ センターに OneDrive のアカウントのルートを検索します。つまり、検索を実行可能なデータ センターの場所を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p126">Route searches of SharePoint sites and OneDrive accounts to a satellite data center. This means you can specify the data center location where searches will be run.</span></span>
    
<span data-ttu-id="cad48-223">**新規 ComplianceSecurityFilter**または**セット ComplianceSecurityFilter**コマンドレットの作成またはエクスポートを経由するデータ ・ センターを変更する**地域**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="cad48-223">Use the **Region** parameter for **New-ComplianceSecurityFilter** or **Set-ComplianceSecurityFilter** cmdlets to create or change which datacenter the export will be routed through.</span></span>
  
|<span data-ttu-id="cad48-224">**パラメーターの値**</span><span class="sxs-lookup"><span data-stu-id="cad48-224">**Parameter value**</span></span>|<span data-ttu-id="cad48-225">**データ センターの場所**</span><span class="sxs-lookup"><span data-stu-id="cad48-225">**Data center location**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cad48-226">NAM</span><span class="sxs-lookup"><span data-stu-id="cad48-226">NAM</span></span>  <br/> |<span data-ttu-id="cad48-227">北アメリカ (実際のデータ ・ センターは、米国では)</span><span class="sxs-lookup"><span data-stu-id="cad48-227">North American (actual data centers are in the US)</span></span>  <br/> |
|<span data-ttu-id="cad48-228">EUR</span><span class="sxs-lookup"><span data-stu-id="cad48-228">EUR</span></span>  <br/> |<span data-ttu-id="cad48-229">ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="cad48-229">Europe</span></span>  <br/> |
|<span data-ttu-id="cad48-230">APC</span><span class="sxs-lookup"><span data-stu-id="cad48-230">APC</span></span>  <br/> |<span data-ttu-id="cad48-231">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="cad48-231">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="cad48-232">CAN</span><span class="sxs-lookup"><span data-stu-id="cad48-232">CAN</span></span> <br/> |<span data-ttu-id="cad48-233">カナダ</span><span class="sxs-lookup"><span data-stu-id="cad48-233">Canada</span></span>
   
<span data-ttu-id="cad48-p127">同様に、SharePoint と OneDrive の場所を検索するときにコンテンツの検索を実行するどのデータ ・ センターを制御するのに**領域**のパラメーター値を次の値を使用できます。次の表は、エクスポートを経由するデータ ・ センターも表示に注意してください。</span><span class="sxs-lookup"><span data-stu-id="cad48-p127">Similarly, you can use the following values for the **Region** parameter values to control which data center that Content Searches will run in when searching SharePoint and OneDrive locations. Note that the following table also shows which data center exports will be routed through.</span></span> 
  
|<span data-ttu-id="cad48-236">**パラメーターの値**</span><span class="sxs-lookup"><span data-stu-id="cad48-236">**Parameter value**</span></span>|<span data-ttu-id="cad48-237">**データ ・ センターのエクスポート用のルーティングの場所**</span><span class="sxs-lookup"><span data-stu-id="cad48-237">**Data center routing locations for export**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cad48-238">NAM</span><span class="sxs-lookup"><span data-stu-id="cad48-238">NAM</span></span>  <br/> |<span data-ttu-id="cad48-239">US</span><span class="sxs-lookup"><span data-stu-id="cad48-239">US</span></span>  <br/> |
|<span data-ttu-id="cad48-240">EUR</span><span class="sxs-lookup"><span data-stu-id="cad48-240">EUR</span></span>  <br/> |<span data-ttu-id="cad48-241">ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="cad48-241">Europe</span></span>  <br/> |
|<span data-ttu-id="cad48-242">APC</span><span class="sxs-lookup"><span data-stu-id="cad48-242">APC</span></span>  <br/> |<span data-ttu-id="cad48-243">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="cad48-243">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="cad48-244">CAN</span><span class="sxs-lookup"><span data-stu-id="cad48-244">CAN</span></span>  <br/> |<span data-ttu-id="cad48-245">US</span><span class="sxs-lookup"><span data-stu-id="cad48-245">US</span></span>  <br/> |
|<span data-ttu-id="cad48-246">AUS</span><span class="sxs-lookup"><span data-stu-id="cad48-246">AUS</span></span>  <br/> |<span data-ttu-id="cad48-247">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="cad48-247">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="cad48-248">KOR</span><span class="sxs-lookup"><span data-stu-id="cad48-248">KOR</span></span>  <br/> |<span data-ttu-id="cad48-249">組織の既定のデータ センター</span><span class="sxs-lookup"><span data-stu-id="cad48-249">The organization's default data center</span></span>  <br/> |
|<span data-ttu-id="cad48-250">GBR</span><span class="sxs-lookup"><span data-stu-id="cad48-250">GBR</span></span>  <br/> |<span data-ttu-id="cad48-251">ヨーロッパ</span><span class="sxs-lookup"><span data-stu-id="cad48-251">Europe</span></span>  <br/> |
|<span data-ttu-id="cad48-252">JPN</span><span class="sxs-lookup"><span data-stu-id="cad48-252">JPN</span></span>  <br/> |<span data-ttu-id="cad48-253">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="cad48-253">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="cad48-254">IND</span><span class="sxs-lookup"><span data-stu-id="cad48-254">IND</span></span>  <br/> |<span data-ttu-id="cad48-255">アジア太平洋地域</span><span class="sxs-lookup"><span data-stu-id="cad48-255">Asia Pacific</span></span>  <br/> |
|<span data-ttu-id="cad48-256">LAM</span><span class="sxs-lookup"><span data-stu-id="cad48-256">LAM</span></span>  <br/> |<span data-ttu-id="cad48-257">US</span><span class="sxs-lookup"><span data-stu-id="cad48-257">US</span></span>  <br/> |
   
 <span data-ttu-id="cad48-258">**注:** 検索のアクセス許可のフィルターの領域のパラメーターを指定しない場合の組織の既定の SharePoint 地域が検索されますし、検索結果は、最も近いデータ ・ センターにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="cad48-258">**Note:** If you don't specify the Region parameter for a search permissions filter, the organizations default SharePoint region will be searched, then search results are exported to the closest data center.</span></span> 
  
<span data-ttu-id="cad48-p128">使用例をここでは、 **-地域**境界を遵守するための検索許可フィルターを作成するときのパラメーターです。これは、Fourth Coffee の関連会社が北アメリカであることと、Coho Winery が、ヨーロッパにあると仮定します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p128">Here are examples of using the **-Region** parameter when creating search permission filters for compliance boundaries. This assumes that the Fourth Coffee subsidiary is located in North America and that Coho Winery is in Europe.</span></span> 
  
```
New-ComplianceSecurityFilter -FilterName "Fourth Coffee Security Filter" -Users "Fourth Coffee eDiscovery Managers", "Fourth Coffee Investigators" -Filters "Mailbox_Department -eq 'FourthCoffee'", "Site_Department -eq 'FourthCoffee' -or Site_Path -like 'https://contoso.sharepoint.com/sites/FourthCoffee*'" -Action ALL -Region NAM
```

```
New-ComplianceSecurityFilter -FilterName "Coho Winery Security Filter" -Users "Coho Winery eDiscovery Managers", "Coho Winery Investigators" -Filters "Mailbox_Department -eq 'CohoWinery'", "Site_Department -eq 'CohoWinery' -or Site_Path -like 'https://contoso.sharepoint.com/sites/CohoWinery*'" -Action ALL -Region EUR
```
   
<span data-ttu-id="cad48-261">複数地域の環境でコンテンツを検索するときの注意、およびエクスポートするのには、次のことを維持します。</span><span class="sxs-lookup"><span data-stu-id="cad48-261">Keep the following things in mind when searching and exporting content in multi-geo environments.</span></span>
  
- <span data-ttu-id="cad48-p129">**領域**パラメーターは、Exchange メールボックスの検索を制御しません。メールボックスを検索すると、すべてのデータ ・ センターが検索されます。どの Exchange のメールボックスを検索できる検索範囲を限定するには、**フィルター**パラメーターを作成または検索のアクセス許可のフィルターを変更するときに使用します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p129">The **Region** parameter doesn't control searches of Exchange mailboxes; all data centers will be searched when you search mailboxes. To limit the scope of which Exchange mailboxes can be searched, use the **Filters** parameter when creating or changing a search permissions filter.</span></span> 
    
- <span data-ttu-id="cad48-264">代替領域を指定する検索のアクセス許可のフィルターで使用できるマネージャーその証拠開示のための別のユーザー アカウントを作成する必要があります電子的証拠開示マネージャーが複数の SharePoint の領域全体を検索するために必要な場合は、場所、SharePoint サイトまたは OneDrive アカウントは、配置されます。</span><span class="sxs-lookup"><span data-stu-id="cad48-264">If it's necessary for an eDiscovery Manager to search across multiple SharePoint regions, you'll need to create a different user account for that eDiscovery manager that can be used in the search permissions filter to specify the alternate region where the SharePoint sites or OneDrive accounts are located.</span></span>
    
- <span data-ttu-id="cad48-p130">SharePoint および OneDrive のコンテンツを検索する**領域**のパラメーターを指示したか、メインの検索や、電子的証拠開示マネージャーが電子的証拠開示の調査を実施する場所の場所の衛星。電子的証拠開示マネージャーは、SharePoint サイトと OneDrive サイトの検索のアクセス許可のフィルターで指定されている領域の外を検索する場合は、検索結果は返されません。</span><span class="sxs-lookup"><span data-stu-id="cad48-p130">When searching for content in SharePoint and OneDrive, the **Region** parameter directs searches to either the main or satellite location where the eDiscovery manager will conduct eDiscovery investigations. If an eDiscovery manager searches SharePoint and OneDrive sites outside of the region that's specified in the search permissions filter, no search results will be returned.</span></span> 
    
- <span data-ttu-id="cad48-p131">(Exchange、Skype をビジネスでは、SharePoint では、OneDrive のコンテンツの検索ツールを使用して検索できるその他の Office 365 サービスを含む) すべてのコンテンツの場所からコンテンツで Azure ストレージの場所にアップロードする検索結果をエクスポートするとき、**領域**パラメーターで指定されているデータ ・ センターです。これにより、組織内でのコンプライアンスの対象となるコントロールの境界線の間でコンテンツを許可しないことによってです。検索のアクセス許可のフィルターで地域を指定しない場合は、組織の既定の領域にコンテンツがアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p131">When exporting search results, content from all content locations (including Exchange, Skype for Business, SharePoint, OneDrive and other Office 365 services that you can search by using the Content Search tool) will be uploaded to the Azure storage location in the data center that's specified by the **Region** parameter. This helps organizations stay within compliance by not allowing content to be exported across controlled borders. If no region is specified in the search permissions filter, content is uploaded to the organization's default region.</span></span> 
    
- <span data-ttu-id="cad48-270">追加または次のコマンドを実行することによって、地域を変更する既存の検索のアクセス許可フィルターを編集できます。</span><span class="sxs-lookup"><span data-stu-id="cad48-270">You can edit an existing search permissions filter to add or change the region by running the following command:</span></span>

    ```
    Set-ComplianceSecurityFilter -FilterName <Filter name>  -Region <Region>
    ```
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="cad48-271">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="cad48-271">Frequently asked questions</span></span>

 <span data-ttu-id="cad48-272">**ユーザーを作成および管理 (新規 ComplianceSecurityFilter とセット ComplianceSecurityFilter コマンドレットを使用して) 検索のアクセス許可のフィルターでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-272">**Who can create and manage search permissions filters (using New-ComplianceSecurityFilter and Set-ComplianceSecurityFilter cmdlets )?**</span></span>
  
<span data-ttu-id="cad48-273">作成するに表示し、検索のアクセス許可のフィルターを変更、セキュリティで組織の管理役割グループのメンバーである必要がある&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="cad48-273">To create, view and modify search permissions filters, you have to be a member of the Organization Management role group in the Security &amp; Compliance Center.</span></span>
  
 <span data-ttu-id="cad48-274">**電子的証拠開示マネージャーが複数の機関にまたがる複数の役割グループに割り当てられている場合、検索する方法を 1 つの機関内のコンテンツやその他のでしょうか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-274">**If an eDiscovery manager is assigned to more than one role group that spans multiple agencies, how do they search for content in one agency or the other?**</span></span>
  
<span data-ttu-id="cad48-p132">電子的証拠開示マネージャーは、検索の範囲を特定の機関に制限は、検索クエリにパラメーターを追加できます。たとえば、組織が政府機関を区別するために**CustomAttribute10**プロパティを指定した場合に追加できます次特定機関でメールボックスおよび OneDrive のアカウントを検索するには、その検索クエリ: `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`。</span><span class="sxs-lookup"><span data-stu-id="cad48-p132">The eDiscovery manager can add parameters to their search query that will restrict the search to a specific agency. For example, if an organization has specified the **CustomAttribute10** property to differentiate agencies, they can append the following to their search query to search mailboxes and OneDrive accounts in a specific agency:  `CustomAttribute10:<value> AND Site_ComplianceAttribute:<value>`.</span></span>
  
 <span data-ttu-id="cad48-277">**コンプライアンス属性検索のアクセス許可のフィルターとして使用される属性の値を変更するとどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-277">**What happens if the value of the attribute that's used as the compliance attribute in a search permissions filter is changed?**</span></span>
  
<span data-ttu-id="cad48-p133">コンプライアンスの境界を適用するフィルターで使用されている属性の値が変更された場合に検索のアクセス許可のフィルターには、最大で 3 日かかります。たとえば、contoso 社のシナリオと Fourth Coffee の代理店のユーザーが Coho Winery 代行業者に転送されます。その結果、ユーザー オブジェクトに**所属**の属性の値は、 *FourthCoffee*から*CohoWinery*に変更します。このような場合は、Fourth Coffee の電子的証拠開示、投資家検索結果を取得、属性が変更された後、3 日間をそのユーザー用です。同様に、Coho Winery 電子的証拠開示マネージャーの前に最大 3 日かかるし、調査官は、ユーザーの検索結果を取得します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p133">It takes up to 3 days for a search permissions filter to enforce the compliance boundary if the value of the attribute that's used in the filter is changed. For example, in the Contoso scenario let's say that a user in the Fourth Coffee agency is transferred to the Coho Winery agency. As a result, the value of the **Department** attribute on the user object is changed from  *FourthCoffee*  to  *CohoWinery*  . In this situation, Fourth Coffee eDiscovery and investors will get search results for that user for up 3 days after the attribute is changed. Similarly, it will take up to 3 days before Coho Winery eDiscovery managers and investigators will get search results for the user.</span></span> 
  
 <span data-ttu-id="cad48-283">**電子的証拠開示マネージャーは 2 つの独立したコンプライアンスの境界からのコンテンツを表示できますか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-283">**Can an eDiscovery manager see content from two separate compliance boundaries?**</span></span>
  
<span data-ttu-id="cad48-p134">うん。これは、両方の機関からの可視性を持っている役割グループにユーザーを追加することによって実行できます。</span><span class="sxs-lookup"><span data-stu-id="cad48-p134">Yes. This can be done by adding the user to role groups that have visibility to both agencies.</span></span>
  
 <span data-ttu-id="cad48-286">**電子的証拠開示のサポート ・ リクエストの保留、Office 365 の保持ポリシー、または DLP のフィルター機能のアクセス許可を検索しますか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-286">**Do search permissions filters work for eDiscovery case holds, Office 365 retention policies, or DLP?**</span></span>
  
<span data-ttu-id="cad48-287">いいえ、現時点ではありません。</span><span class="sxs-lookup"><span data-stu-id="cad48-287">No, not at this time</span></span>
  
 <span data-ttu-id="cad48-288">**コンテンツをエクスポートすると、SharePoint の組織がその地域でないコントロールに領域を指定した場合でも検索する SharePoint でしょうか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-288">**If I specify a region to control where content is exported, but I don't have a SharePoint organization in that region, can I still search SharePoint?**</span></span>
  
<span data-ttu-id="cad48-289">組織の検索のアクセス許可のフィルターで指定された領域が存在しない場合は、既定の領域が検索されます。</span><span class="sxs-lookup"><span data-stu-id="cad48-289">If the region specified in the search permissions filter doesn't exist in your organization, the default region will be searched.</span></span>
  
 <span data-ttu-id="cad48-290">**組織で作成することができます検索のアクセス許可のフィルターの最大数とは何ですか。**</span><span class="sxs-lookup"><span data-stu-id="cad48-290">**What is the maximum number of search permissions filters that can be created in an organization?**</span></span>
  
<span data-ttu-id="cad48-p135">組織で作成することができます検索のアクセス許可のフィルターの数に制限はありません。ただし、100 以上の検索のアクセス許可のフィルターがある場合に検索のパフォーマンスが低下します。できるだけ小さく、組織内のアクセス許可の検索フィルターの数を保持するには、可能な限り 1 つの検索のアクセス許可のフィルターに交換、SharePoint、および OneDrive の規則を結合するためのフィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="cad48-p135">There is no limit to the number of search permissions filters that can be created in an organization. However, search performance will be impacted when there are more than 100 search permissions filters. To keep the number of search permissions filters in your organization as small as possible, create filters that combine rules for Exchange, SharePoint, and OneDrive into a single search permissions filter whenever possible.</span></span>
