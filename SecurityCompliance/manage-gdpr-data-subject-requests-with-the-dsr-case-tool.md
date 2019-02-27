---
title: Office 365 セキュリティ&amp; /コンプライアンスセンターの DSR ケースツールを使用して GDPR データ主体要求を管理する
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 5/25/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: ce9eb942-3589-42cb-88fd-1576ecb09c5c
description: GDPR は、個人データに対して、特定の権限を (データの対象と呼ばれる) EU 市民に提供します。これらの権限には、そのファイルのコピーの取得、変更の要求、ファイルの処理の制限、削除、または電子形式での受信などが含まれます。個人データに対してアクションを実行するデータ主体による正式な要求は、データ主体要求または DSR と呼ばれます。Office 365 セキュリティ&amp;コンプライアンスセンターで dsr ケースを使用して、組織の dsr 調査を管理することができます。
ms.openlocfilehash: fe702ab9050e76b6b8f00fbc8d2670505a030756
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296590"
---
# <a name="manage-gdpr-data-subject-requests-with-the-dsr-case-tool-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="bfe7d-105">Office 365 セキュリティ&amp; /コンプライアンスセンターの DSR ケースツールを使用して GDPR データ主体要求を管理する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-105">Manage GDPR data subject requests with the DSR case tool in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="bfe7d-p102">eu 一般データ保護規則 (GDPR) は、欧州連合 (EU) 内部で個人のプライバシー権を保護し、有効にすることについてのものです。GDPR は、欧州連合 (データ対象者と呼ばれます) の各ユーザーに、個人データのアクセス、取得、修正、消去、および制限を行う権限を付与します。GDPR の [個人データ] は、特定されたまたは特定の自然な人物に関する情報を意味します。個人データに対するアクションを実行するために組織に対する正式な要求は、データ主体要求または DSR と呼ばれます。office 365 でのデータの dsrs への対応の詳細については、「 [office 365 データ主体要求ガイド](https://go.microsoft.com/fwlink/?linkid=871169 )」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p102">The EU General Data Protection Regulation (GDPR) is about protecting and enabling individuals' privacy rights inside the European Union (EU). The GDPR gives individuals in the European Union (known as data subjects) the right to access, retrieve, correct, erase, and restrict processing of their personal data. Under the GDPR, personal data means any information relating to an identified or identifiable natural person. A formal request by a person to their organization to take an action on their personal data is called a Data Subject Request or DSR. For detailed information about responding to DSRs for data in Office 365, see [Office 365 Data Subject Request Guide](https://go.microsoft.com/fwlink/?linkid=871169 ).</span></span>
  
<span data-ttu-id="bfe7d-111">組織内のユーザーが送信した dsr に応答して調査を管理するには、Office 365 セキュリティ&amp;コンプライアンスセンターの dsr ケースツールを使用して、に格納されているコンテンツを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-111">To manage investigations in response to a DSR submitted by a person in your organization, you can use the DSR case tool in the Office 365 Security &amp; Compliance Center to find content stored in:</span></span>
  
- <span data-ttu-id="bfe7d-p103">組織内の任意のユーザーメールボックス。これには、Microsoft Teams での Skype for business の会話と1対1のチャットが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p103">Any user mailbox in your organization. This includes Skype for Business conversations and one-to-one chats in Microsoft Teams</span></span>
    
- <span data-ttu-id="bfe7d-114">Office 365 グループに関連付けられているすべてのメールボックスと、Microsoft Teams 内のすべてのチームメールボックス</span><span class="sxs-lookup"><span data-stu-id="bfe7d-114">All mailboxes associated with an Office 365 Group and all team mailboxes in Microsoft Teams</span></span>
    
- <span data-ttu-id="bfe7d-115">組織内のすべての SharePoint サイトおよび OneDrive for Business アカウント</span><span class="sxs-lookup"><span data-stu-id="bfe7d-115">All SharePoint Online sites and OneDrive for Business accounts in your organization</span></span>
    
- <span data-ttu-id="bfe7d-116">組織内のすべての Teams サイトと Office 365 グループサイト</span><span class="sxs-lookup"><span data-stu-id="bfe7d-116">All Teams sites and Office 365 Group sites in your organization</span></span>
    
- <span data-ttu-id="bfe7d-117">Exchange Online のすべてのパブリック フォルダー</span><span class="sxs-lookup"><span data-stu-id="bfe7d-117">All public folders in Exchange Online</span></span>
    
<span data-ttu-id="bfe7d-118">DSR ケースツールを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-118">Using the DSR case tool you can:</span></span>
  
- <span data-ttu-id="bfe7d-119">DSR 調査ごとに個別のケースを作成する。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-119">Create a separate case for each DSR investigation.</span></span>
    
- <span data-ttu-id="bfe7d-p104">ユーザーをケースのメンバーとして追加することによって、DSR ケースにアクセスできるユーザーを制御します。セキュリティ&amp; /コンプライアンスセンターの [ **DSR ケース**] ページのケースの一覧では、メンバーのみがケースにアクセスでき、ケースは表示できます。さらに、同じケースの異なるメンバーに異なるアクセス許可を割り当てることができます。たとえば、一部のメンバーに対して、ケースおよび検索結果の表示のみを許可し、他のメンバーが検索を作成して検索結果をエクスポートできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p104">Control who has access to the DSR case by adding people as members of the case; only members can access the case and can only see their cases in the list of cases on the **DSR cases** page in the Security &amp; Compliance Center. Additionally, you can assign different permissions to different members of the same case. For example, you can allow some members to only view the case and search results and allow other members to create searches and export search results.</span></span> 
    
- <span data-ttu-id="bfe7d-123">組み込み検索を使用して、特定のデータ主体によって作成またはアップロードされたすべてのコンテンツを検索します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-123">Use the built-in search to search for all content created or uploaded by a specific data subject.</span></span>
    
- <span data-ttu-id="bfe7d-124">必要に応じて、組み込みの検索クエリを修正し、検索を再実行して検索結果を絞り込みます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-124">Optionally revise the built-in search query and re-run the search to narrow the search results.</span></span>
    
- <span data-ttu-id="bfe7d-p105">DSR ケースに関連付けられている追加のコンテンツ検索を追加します。これには、分析および Office ローミングサービスから、部分的にインデックス付けされたアイテムとシステム生成ログを返す検索を作成することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p105">Add additional content searches associated with the DSR case. This includes creating searches that return partially indexed items and system-generated logs from My Analytics and the Office Roaming Service.</span></span>
    
- <span data-ttu-id="bfe7d-127">DSR へのアクセスまたはエクスポート要求に対する応答としてデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-127">Export data in response to a DSR access or export request.</span></span>
    
- <span data-ttu-id="bfe7d-128">DSR 調査プロセスが完了したら、ケースを削除します。これにより、ケースに関連付けられたすべての検索とエクスポートジョブが削除されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-128">Delete cases when the DSR investigation process is complete; this will remove all searches and export jobs associated with the case.</span></span>
    
<span data-ttu-id="bfe7d-129">dsr ケースツールを使用して dsr 調査を管理するための大まかなプロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-129">Here's the high-level process for using the DSR case tool to manage DSR investigations:</span></span>
  
[<span data-ttu-id="bfe7d-130">手順 1: 潜在的なケースのメンバーに電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bfe7d-130">Step 1: Assign eDiscovery permissions to potential case members</span></span>](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[<span data-ttu-id="bfe7d-131">手順 2: DSR ケースを作成してメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-131">Step 2: Create a DSR case and add members</span></span>](#step-2-create-a-dsr-case-and-add-members)

[<span data-ttu-id="bfe7d-132">手順 3: 検索クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-132">Step 3: Run the search query</span></span>](#step-3-run-the-search-query)

[<span data-ttu-id="bfe7d-133">手順 4: データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bfe7d-133">Step 4: Export the data</span></span>](#step-4-export-the-data)

[<span data-ttu-id="bfe7d-134">オプション手順 5: 組み込みの検索クエリを変更する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-134">(Optional) Step 5: Revise the built-in search query</span></span>](#optional-step-5-revise-the-built-in-search-query)

[<span data-ttu-id="bfe7d-135">DSR ケースツールの使用に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="bfe7d-135">More information about using the DSR case tool</span></span>](#more-information-about-using-the-dsr-case-tool)
  
> [!IMPORTANT]
> <span data-ttu-id="bfe7d-p106">ツールを使用すると、管理者は dsr のアクセスまたはエクスポート要求を実行できるようになります。これにより、dsr ケースツールに含まれる組み込みの検索とエクスポートの機能を利用できるようになります。このツールは、データ主体によって送信された DSR 要求に関連するデータをエクスポートするためのベストエフォート方式を促進するのに役立ちます。ただし、検索結果は、アイテムがエクスポート目的で "個人データ" と見なされるかどうかに影響を与える可能性のあるデータ主体または管理者のアクションによって異なる可能性があることに注意することが重要です。たとえば、データの件名が、作成していないファイルを最後に変更したユーザーである場合、そのファイルは検索結果に返されないことがあります。同様に、管理者は、部分的にインデックス付けされたアイテムや SharePoint ドキュメントのすべてのバージョンを含めずにデータをエクスポートすることもできます。そのため、提供されているツールを使用すると、データ要求へのアクセスとエクスポートが容易になります。ただし、結果は特定の管理者およびデータ主体の使用シナリオの対象となります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p106">Our tools can help admins perform DSR access or export requests by enabling them to utilize the built-in search and export functionality found in the DSR case tool. The tool helps to facilitate a best-effort method to export data that's relevant to a DSR request submitted by a data subject. However, it's important to note that search results can vary based on the data subject or the admin actions taken that may impact whether or not an item would be deemed as "personal data" for export purposes. For example, if the data subject was the last person to modify a file they didn't create, the file might not be returned in the search results. Similarly, an admin could export data without including partially indexed items or all versions of SharePoint documents. Therefore, the tools provided can help facilitate accessing and exporting data requests; however, the results are subject to specific admin and data subject usage scenarios.</span></span> 
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a><span data-ttu-id="bfe7d-142">手順 1: 潜在的なケースのメンバーに電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="bfe7d-142">Step 1: Assign eDiscovery permissions to potential case members</span></span>

<span data-ttu-id="bfe7d-p107">既定では、Office 365 グローバル管理者は、セキュリティ&amp;コンプライアンスセンターの DSR ケースツールにアクセスできます。設計上、データプライバシー責任者、人事マネージャー、または dsr 調査に関わる他のユーザーは、dsr ケースツールへのアクセス権を持ちません。また、ツールにアクセスするための適切なアクセス許可を割り当てる必要があります。これを行う最も簡単な方法は、セキュリティ&amp;コンプライアンスセンターの [**アクセス許可**] ページに移動して、電子情報開示マネージャーの役割グループにユーザーを追加することです。なお、手順2で作成した DSR ケースのメンバーとして追加できるように、これらのアクセス許可を割り当てる必要もあります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p107">By default, an Office 365 global administrator can access the DSR case tool in the Security &amp; Compliance Center. By design, other users such as a data privacy officer, a human resources manager, or other people involved in DSR investigations don't have access to the DSR case tool and will have to be assigned the appropriate permissions to access the tool. The easiest way to do this is to go to the **Permissions** page in the Security &amp; Compliance Center and add users to the eDiscovery Manager role group. Note that you also have to assign these permissions so you can add them as members of the DSR case that you create in Step 2.</span></span> 
  
<span data-ttu-id="bfe7d-147">詳細な手順については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-147">For step-by-step instructions, see [Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center](assign-ediscovery-permissions.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfe7d-p108">既定では、Office 365 のグローバル管理者 (またはセキュリティ&amp; /コンプライアンスセンターの [組織の管理] 役割グループの他のメンバーには、コンテンツ検索結果をエクスポートするために必要なアクセス許可がありません (この記事の手順4を参照)。これを解決するために、管理者は自分自身を電子情報開示マネージャーの役割グループのメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p108">By default, an Office 365 global administrator (or other members of the Organization Management role group in the Security &amp; Compliance Center don't have the necessary permissions to export Content Search results (see Step 4 in this article). To address this, an admin can add themselves as a member of the eDiscovery Manager role group.</span></span> 
  
## <a name="step-2-create-a-dsr-case-and-add-members"></a><span data-ttu-id="bfe7d-150">手順 2: DSR ケースを作成してメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-150">Step 2: Create a DSR case and add members</span></span>

<span data-ttu-id="bfe7d-p109">次の手順では、DSR ケースを作成します。ケースを作成する場合、組み込み検索を開始するか、検索を開始せずにケースを作成するかを選択できます。次の手順では、検索を開始せずにケースを作成し、ケースにメンバーを追加する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p109">The next step is to create a DSR case. When you create a case, you can choose to start the built-in search or you can create the case without starting the search. The following procedure will instruct you to create the case without starting the search and then show you how to add members to the case.</span></span>
  
1. <span data-ttu-id="bfe7d-154">に[https://protection.office.com](https://protection.office.com)移動して、職場または学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-154">Go to [https://protection.office.com](https://protection.office.com) and sign in to Office 365 using your work or school account.</span></span> 
    
2. <span data-ttu-id="bfe7d-155">&amp;セキュリティ/コンプライアンスセンターで、[**データプライバシー** \> **データの件名の要求**] を![クリックし](media/ITPro-EAC-AddIcon.gif) 、[追加] アイコン [**新しい DSR ケース**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-155">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New DSR case**.</span></span>
    
3. <span data-ttu-id="bfe7d-p110">[**新しい DSR ケース**のポップアップ] ページで、ケースに名前を付け、オプションの説明を入力して、[**次へ**] をクリックします。ケースの名前は、組織内で一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p110">On the **New DSR case** flyout page, give the case a name, type an optional description, and then click **Next**. Note that the name of the case must be unique in your organization.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bfe7d-p111">調査している DSR 要求を送信したユーザーの名前を、新しいケースの名前や説明に追加することを検討してください。このケース (および電子情報開示管理者) のメンバーのみが、[**データ主体要求**] ページのケースの一覧でケースを表示できることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p111">Consider adding the name of the person who submitted the DSR request that you're investigating in the name and/or description of the new case. Note that only members of this case (and eDiscovery Administrators) will be able to see the case in the list of cases on the **Data subject requests** page.</span></span> 
  
4. <span data-ttu-id="bfe7d-160">[**要求の詳細**] ページの [**データの件名 (この要求を提出したユーザー)**] で、データを検索してエクスポートするユーザーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-160">On the **Request details** page, under **Data subject (the person who filed this request)**, select the person that you want to find and export data for and then click **Next**.</span></span>
    
5. <span data-ttu-id="bfe7d-p112">[**ケースの設定の確認**] ページで、ケースの名前と説明を変更し、別のデータ主体を選択できます。それ以外の場合は、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p112">On the **Confirm your case settings** page, you can change the case name and description, and select a different data subject. Otherwise, just click **Save**.</span></span>
    
    <span data-ttu-id="bfe7d-163">新しい DSR ケースが作成されたことを確認するページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-163">A page is displayed that confirms the new DSR case has been created.</span></span>
    
    ![検索を開始するか、[新しい DSR ケース] ページを閉じる](media/b5e62c2c-cafe-4a8d-a38c-789ed9f9ccbd.png)
  
    <span data-ttu-id="bfe7d-165">この時点で、次の2つの操作のいずれかを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-165">At this point, you can do one of two things:</span></span>
    
    <span data-ttu-id="bfe7d-p113">a [**検索結果の表示]** をクリックすると、検索が開始されます。これは既定の選択です。このオプションを選択したときに実行される組み込み検索は、手順3で説明されています。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p113">a. Clicking **Show me search results** starts the search. This is the default selection. The built-in search that is run when you select this option and the results that are returned are discussed in Step 3.</span></span>
    
    <span data-ttu-id="bfe7d-p114">b. [**完了**] をクリックすると、組み込み検索を開始せずに新しい DSR ケースが閉じられます。このオプションを選択すると、新しい DSR ケースが [**データ主体要求**] ページに表示されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p114">b. Clicking **Finish** closes the new DSR case without starting the built-in search. When you select this option, the new DSR case is displayed on the **Data subject requests** page.</span></span>
    
6. <span data-ttu-id="bfe7d-173">[**完了**] をクリックして、新しい DSR ケースに移動して、メンバーを追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-173">Click **Finish** so that you can go in to the new DSR case and add members to it.</span></span> 
    
7. <span data-ttu-id="bfe7d-174">[**データ主体要求**] ページで、先ほど作成した DSR のケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-174">On the **Data subject requests** page, click the name of the DSR case that you just created.</span></span> 
    
8. <span data-ttu-id="bfe7d-175">[**このケースの管理**] ページの [**メンバーの管理**] で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-175">On the **Manage this case** flyout page, under **Manage members**, click **Add**.</span></span> 
    
    <span data-ttu-id="bfe7d-p115">[**ユーザー**] の下に、適切な電子情報開示のアクセス許可が割り当てられているユーザーの一覧が表示されます。手順1で電子情報開示のアクセス許可を割り当てたユーザーがこの一覧に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p115">Under **Users**, a list of people that have been assigned the appropriate eDiscovery permissions is displayed. Note that the people you assigned eDiscovery permissions to in Step 1 will be displayed in this list.</span></span> 
    
9. <span data-ttu-id="bfe7d-178">DSR ケースのメンバーとして追加するユーザーを選択し、[**追加**] をクリックして、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-178">Select the people to add as members of the DSR case, click **Add**, and then save your changes.</span></span>
    
    <span data-ttu-id="bfe7d-179">「 **Manage role groups**」の下にある [**追加**] をクリックして、DSR のメンバーとして役割グループを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-179">Note that you can also add role groups as members of DSR case by clicking **Add** under **Manage role groups**.</span></span> 
    
## <a name="step-3-run-the-search-query"></a><span data-ttu-id="bfe7d-180">手順 3: 検索クエリを実行する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-180">Step 3: Run the search query</span></span>

<span data-ttu-id="bfe7d-p116">DSR ケースを作成してメンバーを追加した後、次の手順では、ケースに関連付けられている組み込み検索を実行します。この既定の検索クエリでは、次の処理が行われます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p116">After you create a DSR case and add members, the next step is to run the built-in search that's associated with the case. This default search query does the following:</span></span>
  
- <span data-ttu-id="bfe7d-p117">組織内のすべてのメールボックスで、データ主体によって送受信されたすべての電子メールアイテムを検索します。これは、*参加者*の電子メールプロパティを使用して実行されます。このプロパティは、電子メールメッセージ内のすべての人物フィールドのデータ主体を検索します。このプロパティは、データの件名が**From**、 **To**、 **CC**、および**BCC**の各フィールドに含まれるアイテムを返します。Exchange Online のパブリックフォルダーも、データ主体によって送受信されたメッセージを検索します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p117">Searches all mailboxes in your organization for all email items that were sent or received by the data subject. This is accomplished by using the  *Participants*  email property, which searches for the data subject in all the people fields in an email message. This property returns items in which the data subject is in the **From**, **To**, **CC**, and **BCC** fields. Public folders in Exchange Online are also searched for messages sent or received by the data subject.</span></span> 
    
- <span data-ttu-id="bfe7d-p118">組織内のすべてのサイトで、データ主体によって作成またはアップロードされたドキュメントとアイテムを検索します。これは、次のサイトプロパティを使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p118">Searches all sites in your organization for documents and items that were created or uploaded by the data subject. This is accomplished by using the following site properties:</span></span>
    
  - <span data-ttu-id="bfe7d-p119">*author*プロパティは、Office ドキュメントの author フィールドにデータの件名が表示されているアイテムを返します。この値は、ドキュメントが他のユーザーによってコピーおよびアップロードされた場合でも保持されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p119">The  *Author*  property returns items where the data subject is listed in the author field in Office documents. This value persists, even if the document is copied and uploaded by someone else.</span></span> 
    
  - <span data-ttu-id="bfe7d-191">*CreatedBy*プロパティは、データ主体によって作成またはアップロードされたアイテムを返します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-191">The  *CreatedBy*  property returns items that were created or uploaded by the data subject.</span></span> 
    
<span data-ttu-id="bfe7d-192">DSR ケースの作成時に自動的に作成される、組み込み検索のキーワードクエリは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-192">Here's what the keyword query looks like for the built-in search that gets automatically created when you create a DSR case.</span></span>
  
```
participants:"<email address>" OR author:"<display name>" OR createdby:"<display name>"
```

<span data-ttu-id="bfe7d-193">たとえば、データの件名の名前が Leonte の場合、キーワードクエリは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-193">For example, if the name of the data subject is Ina Leonte, the keyword query would look like this:</span></span>
  
```
participants:"ina@contoso.com" OR author:"Ina Leonte" OR createdby:"Ina Leonte"
```

 <span data-ttu-id="bfe7d-194">**DSR ケースの組み込み検索を実行するには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="bfe7d-194">**To run the built-in search for a DSR case:**</span></span>
  
1. <span data-ttu-id="bfe7d-195">セキュリティ&amp; /コンプライアンスセンターで、[**データプライバシー** \> **データのサブジェクト要求**] をクリックし、手順2で作成した DSR ケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-195">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case that you created in Step 2.</span></span> 
    
    <span data-ttu-id="bfe7d-p120">ページの上部にある [**検索**] タブをクリックし、新しい DSR ケースを作成したときに作成された組み込み検索の横にあるチェックボックスをオンにします。メモこの検索には、DSR ケースと同じ名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p120">Click the **Search** tab at the top of the page, and then click the checkbox next to the built-in search that was created when you created the new DSR case. Note the search has the same name as the DSR case.</span></span> 
    
2. <span data-ttu-id="bfe7d-198">[検索] ポップアップページで、[**クエリを開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-198">In the search flyout page, click **Open query**.</span></span>
    
    <span data-ttu-id="bfe7d-199">クエリを開くと、検索が開始され、しばらくして完了します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-199">When you open the query, the search is started and will complete in a few moments.</span></span> 
    
3. <span data-ttu-id="bfe7d-p121">検索が完了したら、[**結果のプレビュー** ] をクリックして検索結果をプレビューします。詳細については、「[検索結果のプレビュー](content-search.md#preview-search-results)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p121">When the search is complete, click **Preview results** to preview the search results. For more information, see [Preview search results](content-search.md#preview-search-results).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="bfe7d-p122">検索クエリの統計を表示して、検索によって返されるメールボックスおよびサイトアイテムの数と、検索クエリに一致するアイテムを含む上位のコンテンツの場所を確認することもできます。詳細については、「[検索に関する情報と統計情報を表示する](content-search.md#view-information-and-statistics-about-a-search)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p122">You can also view the search query statistics to see the number of mailbox and site items that are returned by the search, and the top content locations that contain items that match the search query. For more information see, [View information and statistics about a search](content-search.md#view-information-and-statistics-about-a-search).</span></span> 
  
<span data-ttu-id="bfe7d-p123">組み込みの検索クエリを編集し、検索するコンテンツの場所を変更して、検索を再度実行します。詳細については、「 [Step 5](#optional-step-5-revise-the-built-in-search-query) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p123">You can edit the built-in search query, change the content locations that are searched, and then re-run the search. See [Step 5](#optional-step-5-revise-the-built-in-search-query) for more information.</span></span> 
  
## <a name="step-4-export-the-data"></a><span data-ttu-id="bfe7d-206">手順 4: データをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bfe7d-206">Step 4: Export the data</span></span>

<span data-ttu-id="bfe7d-p124">組み込み検索を実行した後、検索結果をエクスポートすることができます。または、データをエクスポートする前に、クエリを変更して検索結果の数を減らす必要がある場合があります。検索結果の絞り込みの詳細については、手順5を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p124">After you run the built-in search, you can export the search results. Alternatively, before you export the data, you may want to revise the query to reduce the number of search results. See Step 5 for more information about narrowing the search results.</span></span>
  
<span data-ttu-id="bfe7d-p125">検索結果をエクスポートすると、メールボックスアイテムを PST ファイルまたは個別のメッセージとしてダウンロードできます。SharePoint と OneDrive のアカウントからコンテンツをエクスポートすると、ネイティブの Office ドキュメントとその他のドキュメントのコピーがエクスポートされます。エクスポートされたすべてのアイテムに関する情報を含む結果ファイルも検索結果に含まれています。エクスポートの詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターからコンテンツ検索の結果をエクスポートする](export-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p125">When you export search results, mailbox items can be downloaded in PST files or as individual messages. When you export content from SharePoint and OneDrive accounts, copies of native Office documents and other documents are exported. A results file that contains information about every item that is exported is also included with the search results. For more detailed information about exporting, see [Export Content Search results from the Office 365 Security &amp; Compliance Center](export-search-results.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="bfe7d-p126">既定では、Office 365 のグローバル管理者 (またはセキュリティ&amp;コンプライアンスセンターの [組織の管理] 役割グループの他のメンバー) は、コンテンツ検索の結果をエクスポートするために必要なアクセス許可を持っていません。これを解決するために、管理者は自分自身を電子情報開示マネージャーの役割グループのメンバーとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p126">By default, an Office 365 global administrator (or other members of the Organization Management role group in the Security &amp; Compliance Center) don't have the necessary permissions to export Content Search results. To address this, an admin can add themselves as a member of the eDiscovery Manager role group.</span></span> 
  
<span data-ttu-id="bfe7d-216">データのエクスポートに使用するコンピューターは、次のシステム要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-216">The computer you use to export data has to meet the following system requirements:</span></span>
  
- <span data-ttu-id="bfe7d-217">32 ビットおよび 64 ビット バージョンの Windows 7 およびそれ以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="bfe7d-217">32- or 64-bit versions of Windows 7 and later versions</span></span>
    
- <span data-ttu-id="bfe7d-218">Microsoft .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="bfe7d-218">Microsoft .NET Framework 4.7</span></span>
    
- <span data-ttu-id="bfe7d-219">サポートされているブラウザー:</span><span class="sxs-lookup"><span data-stu-id="bfe7d-219">A supported browser:</span></span>
    
  - <span data-ttu-id="bfe7d-220">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bfe7d-220">Microsoft Edge</span></span>
    
    <span data-ttu-id="bfe7d-221">または</span><span class="sxs-lookup"><span data-stu-id="bfe7d-221">Or</span></span>
    
  - <span data-ttu-id="bfe7d-222">Microsoft Internet Explorer 10 以降のバージョン</span><span class="sxs-lookup"><span data-stu-id="bfe7d-222">Microsoft Internet Explorer 10 and later versions</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bfe7d-p127">Microsoft は、ClickOnce アプリケーションのサードパーティの拡張機能またはアドオンを製造していません。サポートされていないブラウザーを使用して、サードパーティの内線番号またはアドオンと共にデータをエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p127">Microsoft doesn't manufacture third-party extensions or add-ons for ClickOnce applications. Exporting data using an unsupported browser with third-party extensions or add-ons isn't supported.</span></span> 
  
 <span data-ttu-id="bfe7d-225">**DSR ケースの組み込み検索からデータをエクスポートするには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="bfe7d-225">**To export data from the built-in search in a DSR case:**</span></span>
  
1. <span data-ttu-id="bfe7d-226">セキュリティ&amp; /コンプライアンスセンターで、[**データプライバシー** \> **データの件名の要求**] をクリックし、データのエクスポート元となる DSR ケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-226">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case that you want to export data from.</span></span> 
    
2. <span data-ttu-id="bfe7d-p128">ページの上部にある [**検索**] タブをクリックし、DSR ケースを作成したときに作成された組み込み検索の横にあるチェックボックスをオンにします。または、別の検索をクリックして、その検索からデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p128">Click the **Search** tab at the top of the page, and then click the checkbox next to the built-in search that was created when you created the DSR case. Or click another search to export data from that search.</span></span> 
    
3. <span data-ttu-id="bfe7d-229">検索ポップアップページで、[検索![結果アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \*\*\*\* のエクスポート] をクリックし、ドロップダウンリストから [**結果のエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-229">On the search flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="bfe7d-230">[**結果のエクスポート**] ページで、DSR エクスポート要求に対して次の推奨オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-230">On the **Export results** page, select the following recommended options for DSR export requests.</span></span> 
    
    ![エクスポート設定を構成する](media/25416b79-57da-46a1-ae07-e640602a8fa4.png)
  
    <span data-ttu-id="bfe7d-p129">[**出力オプション**] で、最初のオプション (**認識できない形式のアイテム、暗号化されていない、またはその他の理由でインデックスが付けられ**ていないものを除く) を選択して、インデックス付きのアイテムのみをエクスポートします。組み込み検索から、部分的にインデックス付けされたアイテムをエクスポートしない理由は、他のユーザーからの部分的なインデックス付きアイテムがエクスポートされるためです。データ主体に対して、部分的にインデックスが作成されたアイテムのみをエクスポートするには、別の検索を作成することをお勧めします。詳細については、「DSR ケースツールの使用に関する詳細情報」の「インデックスが作成された[アイテムをエクスポート](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exportunindexeditems)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p129">a. Under **Output options**, select the first option ( **All items, excluding ones that have ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export indexed items only. The reason you don't want to export partially indexed items from the built-in search is because partially indexed items from other users will be exported. To export only the partially indexed items for the data subject, we recommend that you create a separate search. For more information, see [Exporting partially indexed items](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#exportunindexeditems) in the "More information about using the DSR case tool" section.</span></span>
    
    <span data-ttu-id="bfe7d-p130">b. [ **Exchange コンテンツのエクスポート**] で、1つの**フォルダー内のすべてのメッセージを含む1つの PST ファイル**を選択し、3番目のオプションを選択します。一部の結果は、別のユーザーのメールボックスに含まれるアイテムによって異なることがあるので、このオプションを使用すると、実際のメールボックスを示さずに1つのフォルダー内のアイテムを一覧表示することができます。また、次のアイテムに推奨されたとおりに結果を除外する場合に最適なオプションです。.また、このオプションを使用すると、アイテムごとに元のメールボックスフォルダー構造を移動しなくても、データの件名が日付順に表示されます (アイテムは送信日で並べ替えられます)。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p130">b. Under **Export Exchange content as**, select the third option, **One PST file containing all messages in a single folder**. Because some of the results may be for items that originated in another user's mailbox, this option just lists the item in a single folder without indicating the actual mailbox and is the best option to use when you de-duplicate the results as recommended in the next item. This option also lets the data subject review items in chronological order (items are sorted by sent date) without having to navigate the original mailbox folder structure for each item.</span></span>
    
    <span data-ttu-id="bfe7d-p131">c. [重複**除外を有効**にする] オプションを選択して、重複した電子メールメッセージを除外します。組み込みの検索では、組織内のすべてのメールボックスを検索するため、このオプションをお勧めします。そのため、同じメッセージの複数のコピーが検索されたメールボックス内にある場合、このオプションは、メッセージのコピーが1つだけエクスポートされることを意味します。このオプションを使用すると、1つのフォルダー内の1つの PST ファイル内のメッセージを1つのフォルダーにエクスポートすることで、DSR のエクスポート要求に対する最良のユーザー環境を得ることができます。結果の .csv エクスポートレポートには、重複メッセージが見つかったすべての場所が一覧表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p131">c. Select **Enable de-duplication** option to excludes duplicate email messages. We recommend this option because the built-in search searches all mailboxes in your organization. So if multiple copies of the same message are found in the mailboxes that were searched, this option means only one copy of a message will be exported. This option, together will exporting messages in one PST file in a single folder results in the best user experience for DSR export requests. Note that the Results.csv export report will list all locations where duplicate messages were found.</span></span>
    
    <span data-ttu-id="bfe7d-p132">必要に応じて、[sharepoint**ドキュメントにバージョンを含める**] オプションを選択して、sharepoint および OneDrive ドキュメントのすべてのバージョンをエクスポートすることもできます。そのためには、ドキュメントライブラリに対してバージョン管理が有効になっている必要があります。このオプションを使用すると、関連するすべてのデータを確実にエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p132">Optionally, you can select **Include versions for SharePoint documents** option to export all versions of SharePoint and OneDrive documents. This requires that versioning is turned on for document libraries. This option helps to ensure that all relevant data is exported.</span></span>
    
5. <span data-ttu-id="bfe7d-250">エクスポート設定を選択したら、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-250">After you choose the export settings, click **Export**.</span></span>
    
    <span data-ttu-id="bfe7d-p133">検索結果はダウンロード用に準備されています。これは、Microsoft クラウドの組織の Azure ストレージ領域にアップロードされることを意味します。次の手順では、このデータをローカルコンピューターにダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p133">The search results are prepared for downloading, which means they're uploaded to the Azure storage area for your organization in the Microsoft cloud. The next steps show you how to download this data to your local computer.</span></span>
    
6. <span data-ttu-id="bfe7d-p134">[**エクスポート**] タブをクリックして、先ほど作成したエクスポートジョブを表示します。エクスポートジョブには、検索名の末尾に**export**を追加した対応する検索と同じ名前が付いていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p134">Click the **Export** tab to display the export job you just created. Note that export jobs have the same name as the corresponding search with **_Export** appended to the end of search name.</span></span> 
    
7. <span data-ttu-id="bfe7d-p135">作成したエクスポートジョブをクリックして、[エクスポート] フライアウトページを表示します。このページには、エクスポートされるアイテムのサイズと合計数、および Azure ストレージ領域に転送されたアイテムの割合など、検索に関する情報が表示されます。[**更新**] をクリックして、アップロードの状態情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p135">Click the export job that you just created to display the export flyout page. This page shows information about the search, such as the size and total number of items to be exported, and the percentage of the items that have been transferred to an Azure storage area. Click **Refresh** to update the upload status information.</span></span> 
    
8. <span data-ttu-id="bfe7d-p136">[**キーのエクスポート**] で、[**クリップボードにコピー] を**クリックします。検索結果をダウンロードするには、手順11でこのキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p136">Under **Export key**, click **Copy to clipboard**. You will use this key in step 11 to download the search results.</span></span>
    
9. <span data-ttu-id="bfe7d-260">[ ![エクスポート] ポップアップページ](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)の上部にある [検索結果のアイコンを**ダウンロード**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-260">Click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Download results** at the top of the export flyout page.</span></span> 
    
10. <span data-ttu-id="bfe7d-p137">ページの下部にあるポップアップウィンドウで、[**開く**] をクリックして**Microsoft Office 365 eDiscovery エクスポートツール**を開きます。**電子情報開示エクスポートツール**は、最初に検索結果をダウンロードするときにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p137">In the pop-up window at the bottom of the page, click **Open** to open the **Microsoft Office 365 eDiscovery Export Tool**. The **eDiscovery Export Tool** will be installed the first time you download search results.</span></span> 
    
11. <span data-ttu-id="bfe7d-263">**電子情報開示エクスポートツール**で、手順8でコピーしたエクスポートキーを適切なボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-263">In the **eDiscovery Export Tool**, paste the export key that you copied in step 8 in the appropriate box.</span></span>
    
12. <span data-ttu-id="bfe7d-264">**[参照]** をクリックして、検索結果のファイルをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-264">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bfe7d-265">ディスクアクティビティが大量に (読み取りおよび書き込み) あるため、検索結果をローカルディスクドライブにダウンロードする必要があります。マップされたネットワークドライブまたは他のネットワークの場所にはダウンロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-265">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
13. <span data-ttu-id="bfe7d-266">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-266">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="bfe7d-p138">**電子情報開示エクスポートツール**は、エクスポート処理に関する状態情報を表示します。これには、ダウンロードする残りのアイテムの数 (およびサイズ) の推定値が含まれます。エクスポートプロセスが完了すると、ダウンロードされた場所にあるファイルにアクセスできます。コンテンツ検索の結果をダウンロードするときに含まれるレポートの詳細については、「Office 365 セキュリティ&amp;コンプライアンスセンターからコンテンツ検索の結果をエクスポートする」の「[詳細情報](export-search-results.md#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p138">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can access the files in the location where they were downloaded. For more information about the reports that included when you download Content Search results, see the [More information](export-search-results.md#more-information) section in "Export Content Search results from the Office 365 Security &amp; Compliance Center".</span></span> 
    
<span data-ttu-id="bfe7d-p139">データをエクスポートした後、検索結果とエクスポートレポートは、DSR ケースと同じ名前のフォルダーに配置されます。メールボックスアイテムを含む PST ファイルは、 **Exchange**という名前のサブフォルダーに配置されます。サイトのドキュメントやその他のアイテムは、 **SharePoint**という名前のサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p139">After the data is exported, the search results and export reports are located in a folder that has the same name as the DSR case. The PST files that contain mailbox items are located in a subfolder named **Exchange**. Documents and other items from sites are located in a subfolder named **SharePoint**.</span></span> 
  
## <a name="optional-step-5-revise-the-built-in-search-query"></a><span data-ttu-id="bfe7d-273">オプション手順 5: 組み込みの検索クエリを変更する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-273">(Optional) Step 5: Revise the built-in search query</span></span>

<span data-ttu-id="bfe7d-p140">組み込みの検索を実行した後で、検索結果を減らすために範囲を絞り込むように変更できます。これを行うには、クエリに条件を追加します。条件は、 **and**演算子によって、キーワードクエリに論理的に接続されています。これは、検索結果で返されることを意味するため、アイテムはキーワードクエリと追加の条件の両方を満たす必要があります。このようにすると、条件によって結果を絞り込むことができます。検索クエリに2つ以上の一意の条件を追加すると、それらの条件は**and**演算子によって論理的に接続されます。つまり、キーワードクエリに加えて、すべての条件を満たすアイテムのみが返されます。複数の値をコンマまたはセミコロンで区切って1つの条件に追加すると、それらの値は**or**演算子によって接続されます。これは、条件内のプロパティに指定された値が含まれている場合に、アイテムが返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p140">After you run the built-in search, you can revise it to narrow the scope to return fewer search results. You can do this by adding conditions to the query. A condition is logically connected to the keyword query by the **AND** operator. That means to be returned in the search results, items must satisfy both the keyword query and any conditions you add. This is how conditions help to narrow the results. If you add two or more unique conditions to a search query (conditions that specify different properties), those conditions are logically connected by the **AND** operator. That means only items that satisfy all the conditions (in addition to the keyword query) are returned. If you add multiple values (separated by commas or semi-colons) to a single condition, those values are connected by the **OR** operator. That means items are returned if they contain any of the specified values for the property in the condition.</span></span> 
  
<span data-ttu-id="bfe7d-p141">DSR ケースの組み込み検索クエリに追加できる条件の例を次に示します。検索クエリで使用される実際のプロパティの名前は、かっこで囲まれています。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p141">Here are some examples of the conditions that you can add to the built-in search query of a DSR case. The name of the actual property used in a search query is shown parentheses.</span></span>
  
- <span data-ttu-id="bfe7d-p142">**ファイルの種類`filetype`()** -ドキュメントまたはファイルの拡張子を指定します。特定の Office アプリケーション (Word、Excel、OneNote など) によって作成されたドキュメントやファイルを検索するには、この条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p142">**File type ( `filetype`)** - Specifies the extension of a document or file. Use this condition to search for documents and files created by specific Office applications, such as Word, Excel, and OneNote.</span></span> 
    
- <span data-ttu-id="bfe7d-p143">**Message type ( `kind`)** -検索する電子メールアイテムの種類を指定します。たとえば、Microsoft Teams では、この`kind:email OR kind:im`構文を使用して、電子メールメッセージと Skype for business の会話または1対1のチャットのみを返すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p143">**Message type ( `kind`)** - Specifies the type of email item to search for. For example, you can use the syntax  `kind:email OR kind:im` to return only email messages and Skype for Business conversations or one-to-one chats in Microsoft Teams.</span></span> 
    
- <span data-ttu-id="bfe7d-p144">**コンプライアンスタグ (`compliancetag`)** -電子メールメッセージまたはドキュメントに割り当てられたラベルを指定します。この条件は、特定のラベルに分類されたアイテムを返します。ラベルは、データガバナンスのために電子メールとドキュメントを分類し、ラベルで定義された分類に基づいて保持ルールを適用するために使用されます。これは、組織がデータのプライバシーに関連するコンテンツを分類するためにラベルを使用しているか、個人データや機密情報が含まれている場合があるため、これは DSR 調査にとって便利な条件です。この条件の値については、完全なラベル名またはラベル名の最初の部分をワイルドカードで使用します。詳細については、「 [Office 365 のラベルの概要](labels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p144">**Compliance tag (`compliancetag`)** - Specifies a label assigned to an email message or a document. This condition will return items that are classified with a specific label. Labels are used to classify email and documents for data governance and enforce retention rules based on the classification defined by the label. This is a useful condition for DSR investigations because your organization may be using labels to classify content related to data privacy or that contains personal data or sensitive information. For the value of this condition, use the complete label name or the first part of the label name with a wildcard. For more information, see [Overview of labels in Office 365](labels.md).</span></span>
    
<span data-ttu-id="bfe7d-295">DSR ケースツールで使用可能なすべての条件の一覧と説明については、記事「キーワードクエリと検索条件のコンテンツ検索」の「[検索条件](keyword-queries-and-search-conditions.md#search-conditions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-295">For a list and description of all the conditions available in the DSR case tool, see [Search conditions](keyword-queries-and-search-conditions.md#search-conditions) in the "Keyword queries and search conditions for Content Search" article.</span></span> 
  
### <a name="changing-the-content-locations-that-are-searched"></a><span data-ttu-id="bfe7d-296">検索するコンテンツの場所を変更する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-296">Changing the content locations that are searched</span></span>

<span data-ttu-id="bfe7d-p145">DSR ケースの組み込み検索を改訂するだけでなく、検索するコンテンツの場所を変更することもできます。前述のように、組み込みの検索では、組織内のすべてのメールボックスとサイト、および Exchange Online のパブリックフォルダーが検索されます。たとえば、検索を絞り込んで、データ主体のメールボックスと OneDrive アカウント、および選択した SharePoint サイトのみを検索することができます。特定のサイトを検索することを選択した場合は、検索する各サイトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p145">In addition to revising the built-in search for a DSR case, you can also change the content locations that are searched. As previously explained, the built-in search searches every mailbox and site in the organization, and any Exchange Online public folders. For example, you could narrow the search to only search the data subject's mailbox and OneDrive account and selected SharePoint sites. If you choose to search specific sites, you'll have to add each site that you want to search.</span></span>
  
<span data-ttu-id="bfe7d-301">検索するコンテンツの場所を変更するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-301">To modify the content locations to search:</span></span>
  
1. <span data-ttu-id="bfe7d-302">のコンテンツの場所を変更する組み込みの検索を開きます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-302">Open the built-in search that you want to change the content locations for.</span></span>
    
2. <span data-ttu-id="bfe7d-303">検索クエリの [**場所**] で、[**特定の場所**] オプションの横にある [**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-303">In the search query, under **Locations**, click **Modify** next to the **Specific locations** option.</span></span> 
    
    ![組み込み検索クエリのコンテンツの場所を変更するには、[変更] をクリックします。](media/d66f7ba7-b71f-4ff5-a030-460ff02e3123.png)
  
    <span data-ttu-id="bfe7d-p146">[**場所の変更**] ポップアップページが表示されます。ここでは、組み込み検索でのコンテンツの場所と、検索する場所の変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p146">The **Modify locations** flyout page is displayed. Here's a description of the content locations in the built-in search and some information about modifying the locations that are searched.</span></span> 
    
    ![場所のポップアップページの変更](media/56c033f6-6735-46ba-abb2-a263a2b79836.png)
  
    <span data-ttu-id="bfe7d-p147">。ポップアップページの上部にある [メールボックス内の**すべてを選択**] セクションの下にあるトグルは、すべてのメールボックスを検索することを示す、選択されています。検索範囲を絞るには、[トグル] をクリックして選択を解除し、[**ユーザー、グループ、またはチームの選択**] をクリックして、検索する特定のメールボックスを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p147">a. The toggle under **Select all** in mailbox section at the top of the flyout page is selected, which indicates that all mailboxes are searched. To narrow the scope of the search, click the toggle to unselect it, and then click **Choose users, groups, or teams** and choose specific mailboxes to search.</span></span>
    
    <span data-ttu-id="bfe7d-p148">b. フライアウトページの中央にある [サイト] セクションの [**すべて選択]** の下にある切り替えが選択されています。これは、すべてのサイトが検索されることを示します。選択したサイトに対して検索を絞り込むには、切り替えの選択を解除してから、[**サイトの選択**] をクリックします。検索する特定のサイト (データサブジェクトの OneDrive アカウントを含む) を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p148">b. The toggle under **Select all** in the sites section in the middle of the flyout page is selected, which indicates that all sites are searched. To narrow the search to selected sites, you would unselect the toggle and then click **Choose sites**. You'll have to add each specific site that you want to search, including the data subject's OneDrive account.</span></span>
    
    <span data-ttu-id="bfe7d-p149">c. [exchange パブリックフォルダーの切り替え] セクションが選択されています。これは、すべての exchange パブリックフォルダーが検索されることを意味します。すべての Exchange パブリックフォルダーのみを検索できることに注意してください。検索に特定のものを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p149">c. The toggle in the Exchange public folders section is selected, which means all Exchange public folders are searched. Note that you can only search all Exchange public folders or none of them. You can't choose specific ones to search.</span></span>
    
3. <span data-ttu-id="bfe7d-319">組み込みの検索でコンテンツの場所を変更する場合は、[ **Save &amp; run** ] をクリックして検索を再開します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-319">If you modify the content locations in the built-in search, click **Save &amp; run** to re-start the search.</span></span> 
  
## <a name="more-information-about-using-the-dsr-case-tool"></a><span data-ttu-id="bfe7d-320">DSR ケースツールの使用に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="bfe7d-320">More information about using the DSR case tool</span></span>

<span data-ttu-id="bfe7d-321">次のセクションでは、dsr のケースツールを使用して dsr エクスポート要求に応答する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-321">The following sections contain more information about using the DSR case tool to respond to DSR export requests.</span></span>
  
[<span data-ttu-id="bfe7d-322">myanalytics と Office ローミングサービスからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="bfe7d-322">Exporting data from MyAnalytics and the Office Roaming Service</span></span>](#exporting-data-from-myanalytics-and-the-office-roaming-service)

[<span data-ttu-id="bfe7d-323">部分的にインデックスが作成されたアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bfe7d-323">Exporting partially indexed items</span></span>](#exporting-partially-indexed-items)

[<span data-ttu-id="bfe7d-324">Microsoft Teams および Office 365 グループからのデータの検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="bfe7d-324">Searching and exporting data from Microsoft Teams and Office 365 Groups</span></span>](#searching-and-exporting-data-from-microsoft-teams-and-office-365-groups)

[<span data-ttu-id="bfe7d-325">Exchange パブリックフォルダーの検索</span><span class="sxs-lookup"><span data-stu-id="bfe7d-325">Searching Exchange public folders</span></span>](#searching-exchange-public-folders)
  
### <a name="exporting-data-from-myanalytics-and-the-office-roaming-service"></a><span data-ttu-id="bfe7d-326">myanalytics と Office ローミングサービスからのデータのエクスポート</span><span class="sxs-lookup"><span data-stu-id="bfe7d-326">Exporting data from MyAnalytics and the Office Roaming Service</span></span>

<span data-ttu-id="bfe7d-p150">DSR ケースツールを使用すると、myanalytics および Office ローミングサービスによって生成された利用状況データを検索してエクスポートすることができます。これらのサービスの機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p150">You can use the DSR case tool to search for and export usage data that's generated by MyAnalytics and the Office Roaming Service. Here's a description of what these services do:</span></span>
  
- <span data-ttu-id="bfe7d-p151">**myanalytics** -メールボックス内のメールおよび予定表のデータに基づいて時間を費やす方法に関する洞察をユーザーに提供します。すべての myanalytics insights は、ユーザーのメールボックス内の電子メールと会議のヘッダーから派生します。myanalytics ライセンスを割り当てられているユーザーは、Office 365 にサインインし、myanalytics ダッシュボードに移動して、自分の時間をどのように過ごしたかについての洞察を表示することができます。(DSR アクセス要求に応じて、ユーザーはこれらの洞察のスクリーンショットを表示できます)。DSR ケースの組み込み検索は、myanalytics insights の生成に使用されるデータをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p151">**MyAnalytics** - Provides users with insights about how they spend their time based on the mail and calendar data in their mailbox. All MyAnalytics insights are derived from email and meeting headers in the user's mailbox. Users that are assigned a MyAnalytics license can sign in to Office 365 and go to the MyAnalytics dashboard to view the insights about how they spend their time. (Users can screen shots of these insights in response to a DSR access request). The built-in search in a DSR case will export the data that's used to generate MyAnalytics insights.</span></span> 
    
- <span data-ttu-id="bfe7d-334">**office ローミングサービス**-ローミングは、office テーマ、ユーザー辞書、言語設定、開発者モード、自動修正など、office 関連の設定を保存するサービスです。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-334">**Office Roaming Service** - Roaming is a service that stores Office-related settings, such as Office theme, custom dictionary, language settings, developer mode, and auto correct.</span></span> 
    
<span data-ttu-id="bfe7d-p152">myanalytics と Office ローミングサービスからのデータは、データ主体のメールボックスに、Exchange Online メールボックスの非個人情報サブツリー (IPM 以外) にある隠しフォルダーに格納されます。これは、ユーザーが Outlook または他のメールクライアントを使用して自分のメールボックスにアクセスするときに、ユーザーの表示からデータが非表示になることを意味します。隠しフォルダーの詳細については、「 [MAPI の非表示フォルダー](https://go.microsoft.com/fwlink/?linkid=872758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p152">The data from MyAnalytics and the Office Roaming service is stored in a data subject's mailbox in hidden folders located in a non-interpersonal message (non-IPM) subtree of Exchange Online mailboxes. This means the data is hidden from the user's view when they use Outlook or other mail clients to access their mailbox. For more information about hidden folders, see [MAPI Hidden Folders](https://go.microsoft.com/fwlink/?linkid=872758).</span></span>
  
<span data-ttu-id="bfe7d-p153">データの [情報カテゴリ] メールボックス内の myanalytics および Office ローミングサービスの使用状況データを返す個別のコンテンツ検索を作成し、DSR ケースに関連付けることができます。このデータは検索統計に含まれていないため、プレビューでは使用できません。ただし、DSR エクスポート要求に対する応答として、エクスポートしてからデータ主体に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p153">You can create a separate content search (and associate it with a DSR case) that returns the MyAnalytics and the Office Roaming Service usage data in the data's subjects mailbox. This data isn't included in the search statistics and it won't be available for preview. But you can export it and then give it to the data subject in response to a DSR export request.</span></span>
  
<span data-ttu-id="bfe7d-p154">myanalytics および Office ローミングサービスからデータをエクスポートすると、データは、データ主体の電子メールアドレスを持つ名前のフォルダーの下にある、 **applicationdataroot**フォルダーにあるアプリケーションごとに個別のフォルダーに保存されます。このデータは JSON ファイルとしてエクスポートされます。これは、電子メールメッセージに添付された XML または TXT ファイルに似た、人間が判読できるテキストファイルです。現在、これらのフォルダーには、myanalytics と Office ローミングサービスに割り当てられているグローバル一意識別子 (GUID) が付けられ、次の表に記載されています。DSR ケースツールの今後のバージョンでは、GUID が実際のアプリケーションの名前に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p154">When you export data from MyAnalytics and the Office Roaming Service, the data is saved to a separate folder for each application that's located in the **ApplicationDataRoot** folder, which is under a folder that is name with the data subject's email address. This data is exported as JSON files, which are human-readable text files similar to XML or TXT files, that are attached to email messages. Currently, these folders are named with a globally unique identifier (GUID) that's assigned to MyAnalytics and the Office Roaming Service, which are listed in the following table. In future versions of the DSR case tool, the GUID will be replaced with the name of the actual application.</span></span> 
  
|<span data-ttu-id="bfe7d-345">**アプリケーション**</span><span class="sxs-lookup"><span data-stu-id="bfe7d-345">**Application**</span></span>|<span data-ttu-id="bfe7d-346">**GUID/フォルダー名**</span><span class="sxs-lookup"><span data-stu-id="bfe7d-346">**GUID/folder name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bfe7d-347">MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="bfe7d-347">MyAnalytics</span></span>  <br/> |<span data-ttu-id="bfe7d-348">3c896ded-22c5-450f-91f6-3d1ef0848f6e</span><span class="sxs-lookup"><span data-stu-id="bfe7d-348">3c896ded-22c5-450f-91f6-3d1ef0848f6e</span></span>  <br/> |
|<span data-ttu-id="bfe7d-349">Office ローミング サービス</span><span class="sxs-lookup"><span data-stu-id="bfe7d-349">Office Roaming Service</span></span>  <br/> |<span data-ttu-id="bfe7d-350">1caee58f-eb14-4a6b-9339-1fe2ddf6692b</span><span class="sxs-lookup"><span data-stu-id="bfe7d-350">1caee58f-eb14-4a6b-9339-1fe2ddf6692b</span></span>  <br/> |
   
 <span data-ttu-id="bfe7d-351">**myanalytics および Office ローミングサービスデータを検索してエクスポートするには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="bfe7d-351">**To search for and export MyAnalytics and Office Roaming Service data:**</span></span>
  
1. <span data-ttu-id="bfe7d-352">セキュリティ&amp; /コンプライアンスセンターで、[**データプライバシー** \> **データの件名の要求**] をクリックし、使用状況データをエクスポートするデータ主体の DSR ケースの横にある [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-352">In the Security &amp; Compliance Center, click **Data privacy** \> **Data subject requests**, and then click **Open** next to the DSR case for the data subject that you want to export usage data for.</span></span> 
    
2. <span data-ttu-id="bfe7d-353">ページの上部にある [**検索**] タブをクリックし、[ ![](media/ITPro-EAC-AddIcon.gif) **ガイド付き検索**の追加] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-353">Click the **Search** tab at the top of the page, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Guided search**.</span></span>
    
3. <span data-ttu-id="bfe7d-354">[**検索に名前**をつける] ページで [**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-354">Click **Cancel** on the **Name your search** page.</span></span> 
    
4. <span data-ttu-id="bfe7d-355">[**検索クエリ**] の [**種類**] 条件で、[ **myanalytics**および**Office ローミングサービス**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-355">Under **Search query**, in the **Type** condition, select the check boxes next to **MyAnalytics** and **Office Roaming Service**.</span></span> 
    
    ![利用状況データをエクスポートするには、[myanalytics および Office ローミングサービス] チェックボックスをオンにします。](media/3dacbc7a-c314-492c-828c-6757fda84963.png)
  
    <span data-ttu-id="bfe7d-p155">検索クエリでは、**型**の条件 (電子メールメッセージクラス) が唯一のアイテムである必要があることに注意してください。[**キーワード**] ボックスを削除するか、空白のままにしておくことができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p155">Note that the **Type** condition (which are email message classes) should be the only item in the search query. You can delete the **Keywords** box or leave it blank.</span></span> 
    
5. <span data-ttu-id="bfe7d-359">[**場所**] で**特定の場所**が選択されていることを確認し、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-359">Under **Locations**, make sure **Specific locations** is selected and then click **Modify**.</span></span>
    
6. <span data-ttu-id="bfe7d-360">[**場所の変更**] ポップアップページ ([メールボックス] セクション) の上部にある [**ユーザー、グループ、またはチームの選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-360">On top part of the **Modify locations** flyout page (the mailbox section), click **Choose users, groups, or teams**.</span></span>
    
7. <span data-ttu-id="bfe7d-361">[**場所の編集**] ページで、[**ユーザー、グループ、またはチームの選択**] をクリックし、データ主体のメールボックスを選択して、選択内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-361">On the **Edit locations** page, click **Choose users, groups, or teams**, choose the data subject's mailbox, and then save your selection.</span></span> 
    
8. <span data-ttu-id="bfe7d-362">[\*\*保存&amp; \*\*] をクリックして、検索に名前を付けて保存します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-362">Click **Save &amp; run**, and then name the search and save it.</span></span>
    
    <span data-ttu-id="bfe7d-363">検索が開始されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-363">The search is started.</span></span>
    
 <span data-ttu-id="bfe7d-364">**myanalytics および Office ローミングサービスデータをエクスポートするには、次のようにします。**</span><span class="sxs-lookup"><span data-stu-id="bfe7d-364">**To export MyAnalytics and Office Roaming Service data:**</span></span>
  
1. <span data-ttu-id="bfe7d-p156">前の手順で作成した検索が完了したら、ページの上部にある [**検索**] タブをクリックし、検索の横にあるチェックボックスをオンにします。[最新の情報に![更新](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) \*\*\*\* ] をクリックして検索を表示することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p156">When the search that you created in the previous step is complete, click the **Search** tab at the top of the page, and then click the checkbox next to the search. You may have to click ![refresh](media/165fb3ad-38a8-4dd9-9e76-296aefd96334.png) **Refresh** to display the search.</span></span> 
    
2. <span data-ttu-id="bfe7d-367">検索ポップアップページで、[検索![結果アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) \*\*\*\* のエクスポート] をクリックし、ドロップダウンリストから [**結果のエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-367">On the search flyout page, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="bfe7d-368">[**結果のエクスポート**] ページで、利用状況データをエクスポートするために推奨される次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-368">On the **Export results** page, select the these recommended options to export usage data.</span></span> 
    
    ![myanalytics および Office ローミングサービスの使用状況データをエクスポートするときのエクスポートオプション](media/470a7d1e-eeae-4b42-95aa-15cb82ce2f68.png)
  
    <span data-ttu-id="bfe7d-p157">[**出力オプション**] で、最初のオプション (**認識できない形式のアイテム、暗号化されていない、またはその他の理由でインデックスが付けられ**ていないものを除く) を選択して、インデックス付きのアイテムのみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p157">a. Under **Output options**, select the first option ( **All items, excluding ones that have ones that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export indexed items only.</span></span>
    
    <span data-ttu-id="bfe7d-p158">b. [ **Exchange コンテンツのエクスポート**] で、2番目のオプションで**ある、すべてのメッセージを含む1つの PST ファイル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p158">b. Under **Export Exchange content as**, select the second option, **One PST file containing all messages**.</span></span>
    
    <span data-ttu-id="bfe7d-p159">c. 残りのエクスポートオプションを選択解除したままにします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p159">c. Leave the remaining export options unselected.</span></span>
    
4. <span data-ttu-id="bfe7d-376">エクスポート設定を選択したら、[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-376">After you choose the export settings, click **Export**.</span></span>
    
    <span data-ttu-id="bfe7d-p160">検索結果はダウンロード用に準備されています。これは、Microsoft クラウドの組織の Azure ストレージ領域にアップロードされることを意味します。次の手順では、このデータをローカルコンピューターにダウンロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p160">The search results are prepared for downloading, which means they're uploaded to the Azure storage area for your organization in the Microsoft cloud. The next steps show you how to download this data to your local computer.</span></span>
    
5. <span data-ttu-id="bfe7d-p161">[**エクスポート**] タブをクリックして、先ほど作成したエクスポートジョブを表示します。エクスポートジョブには、検索名の末尾に**export**を追加した対応する検索と同じ名前が付いていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p161">Click the **Export** tab to display the export job you just created. Note that export jobs have the same name as the corresponding search with **_Export** appended to the end of search name.</span></span> 
    
6. <span data-ttu-id="bfe7d-381">作成したエクスポートジョブをクリックして、[エクスポート] フライアウトページを表示します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-381">Click the export job that you just created to display the export flyout page.</span></span> 
    
7. <span data-ttu-id="bfe7d-p162">[**キーのエクスポート**] で、[**クリップボードにコピー] を**クリックします。検索結果をダウンロードするには、手順10でこのキーを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p162">Under **Export key**, click **Copy to clipboard**. You will use this key in step 10 to download the search results.</span></span>
    
8. <span data-ttu-id="bfe7d-384">[ ![エクスポート] ポップアップページ](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)の上部にある [検索結果のアイコンを**ダウンロード**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-384">Click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Download results** at the top of the export flyout page.</span></span> 
    
9. <span data-ttu-id="bfe7d-p163">ページの下部にあるポップアップウィンドウで、[**開く**] をクリックして**Microsoft Office 365 eDiscovery エクスポートツール**を開きます。**電子情報開示エクスポートツール**は、最初に検索結果をダウンロードするときにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p163">In the pop-up window at the bottom of the page, click **Open** to open the **Microsoft Office 365 eDiscovery Export Tool**. The **eDiscovery Export Tool** will be installed the first time you download search results.</span></span> 
    
10. <span data-ttu-id="bfe7d-387">**電子情報開示エクスポート ツール**で、手順 7 でコピーしたエクスポート キーを該当するボックスに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-387">In the **eDiscovery Export Tool**, paste the export key that you copied in step 7 in the appropriate box.</span></span>
    
11. <span data-ttu-id="bfe7d-388">**[参照]** をクリックして、検索結果のファイルをダウンロードする場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-388">Click **Browse** to specify the location where you want to download the search result files.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="bfe7d-389">ディスクアクティビティが大量に (読み取りおよび書き込み) あるため、検索結果をローカルディスクドライブにダウンロードする必要があります。マップされたネットワークドライブまたは他のネットワークの場所にはダウンロードしないでください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-389">Due to the high amount of disk activity (reads and writes), you should download search results to a local disk drive; don't download them to a mapped network drive or other network location.</span></span> 
  
12. <span data-ttu-id="bfe7d-390">**[開始]** をクリックして、検索結果をコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-390">Click **Start** to download the search results to your computer.</span></span> 
    
    <span data-ttu-id="bfe7d-p164">**電子情報開示エクスポートツール**は、エクスポート処理に関する状態情報を表示します。これには、ダウンロードする残りのアイテムの数 (およびサイズ) の推定値が含まれます。エクスポートプロセスが完了すると、Outlook で Exchange PST ファイルを開いて、 **applicationdataroot**フォルダーに移動して、myanalytics およびローミングサービスへのサブフォルダーにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p164">The **eDiscovery Export Tool** displays status information about the export process, including an estimate of the number (and size) of the remaining items to be downloaded. When the export process is complete, you can open the Exchange PST file in Outlook and then go to the **ApplicationDataRoot** folder to access the subfolders to MyAnalytics and Roaming service.</span></span> 
    
    <span data-ttu-id="bfe7d-p165">前述したように、利用状況データを含む JSON ファイルはメッセージに添付されます。json ファイルを表示するには、メッセージをクリックして、添付されている json ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p165">As previously explained, the JSON files that contains usage data are attached to messages. To view a JSON file, click a message and then open the attached JSON file.</span></span> 
  
### <a name="exporting-partially-indexed-items"></a><span data-ttu-id="bfe7d-395">部分的にインデックスが作成されたアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bfe7d-395">Exporting partially indexed items</span></span>

<span data-ttu-id="bfe7d-p166">新しい DSR ケースを作成するときに作成される組み込み検索から、部分的にインデックスが作成されたアイテム (インデックスなしのアイテムとも呼ばれます) をエクスポートしないことをお勧めします。これは、検索結果には、組織内の他のユーザーについて部分的にインデックス付けされたアイテムが含まれる可能性が高く、データの件名の一部のインデックスアイテムだけではないためです。代わりに、データ主体に関連する、部分的にインデックスが作成されたアイテムのみをエクスポートするように設計された DSR ケースに関連付けられた個別のコンテンツ検索を作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p166">We recommend that you don't export partially indexed items (also called unindexed items) from the built-in search that's created when you create a new DSR case. That's because the search results will more than likely include partially indexed items for other users in your organization, and not just partially indexed items for the data subject). Instead, we recommend that you create a separate Content Search that's associated with the DSR case that's designed to export only the partially indexed items related to the data subject.</span></span> 
  
<span data-ttu-id="bfe7d-p167">以下に、部分的にインデックスが作成されたアイテムをエクスポートするための大まかな手順を示します。エクスポートした後で、アイテムが DSR アクセスまたはエクスポート要求に応答しているかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p167">Here's a high-level process to export partially indexed items. After they're export, you can review them to determine if an items is responsive to a DSR access or export request.</span></span>
  
1. <span data-ttu-id="bfe7d-401">DSR ケースを開き、[**検索**] ページで新しい検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-401">Open the DSR case and create a new search on the **Search** page.</span></span> 
    
2. <span data-ttu-id="bfe7d-402">検索クエリと検索するコンテンツの場所を構成するには、次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-402">Use the following criteria for configuring the search query and the content locations to search:</span></span>
    
    - <span data-ttu-id="bfe7d-p168">空の/空白のキーワードクエリを使用します。これにより、検索されるコンテンツの場所にあるすべてのアイテムが返されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p168">Use an empty/blank keyword query. This will return all items in the content locations that are searched.</span></span>
    
    - <span data-ttu-id="bfe7d-405">データ主体の Exchange Online メールボックスとその OneDrive アカウントのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-405">Search only the data subject's Exchange Online mailbox and their OneDrive account.</span></span>
    
3. <span data-ttu-id="bfe7d-p169">検索を実行して完了した後、検索結果をエクスポートしてダウンロードできます ([手順 4](#step-4-export-the-data)で説明)。次の設定を使用して、部分的にインデックスが作成されたアイテムをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p169">After you run the search and it completes, you can export and download the search results (as described in [Step 4](#step-4-export-the-data)). Use the following settings to export partially indexed items.</span></span> 
    
    - <span data-ttu-id="bfe7d-408">[**出力オプション**] で、3番目のオプション (**認識できない形式のアイテムのみ、暗号化されているか、またはその他の理由でインデックスが作成されなかったアイテムのみ**) を選択して、部分的にインデックスが作成されたアイテムのみをエクスポート</span><span class="sxs-lookup"><span data-stu-id="bfe7d-408">Under **Output options**, select the third option ( **Only items that have an unrecognized format, are encrypted, or weren't indexed for other reasons**) to export partially indexed items only.</span></span>
    
    - <span data-ttu-id="bfe7d-409">[ **Exchange コンテンツのエクスポート**] で、ユーザーの設定に基づいて任意のオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-409">Under **Export Exchange content as**, you can select any option based on your preferences.</span></span> 
    
    - <span data-ttu-id="bfe7d-410">[ **SharePoint ドキュメントにバージョンを含める**] オプションを選択すると、バージョンが部分的にインデックス付けされている場合、ドキュメントのバージョンがエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-410">Selecting the **Include versions for SharePoint documents** option will export versions of documents if a version is partially indexed.</span></span> 
    
<span data-ttu-id="bfe7d-411">部分的にインデックスが作成されたアイテムの詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-411">For more information about partially indexed items, see:</span></span> 
  
- [<span data-ttu-id="bfe7d-412">Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム</span><span class="sxs-lookup"><span data-stu-id="bfe7d-412">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="bfe7d-413">部分的にインデックスが作成されたアイテムをエクスポートする</span><span class="sxs-lookup"><span data-stu-id="bfe7d-413">Exporting partially indexed items</span></span>](export-search-results.md#exporting-partially-indexed-items)
    
### <a name="searching-and-exporting-data-from-microsoft-teams-and-office-365-groups"></a><span data-ttu-id="bfe7d-414">Microsoft Teams および Office 365 グループからのデータの検索とエクスポート</span><span class="sxs-lookup"><span data-stu-id="bfe7d-414">Searching and exporting data from Microsoft Teams and Office 365 Groups</span></span>

<span data-ttu-id="bfe7d-p170">Microsoft Teams のチャットリスト (チームチャットまたは1対1のチャットと呼ばれる) に含まれる会話は、チャットに参加しているユーザーの Exchange Online メールボックスに格納されます。また、1対1のチャットでユーザーが共有するファイルは、そのファイルを共有しているユーザーの OneDrive アカウントに保存されます。組み込みの検索では、組織内のすべてのメールボックスと OneDrive アカウントが検索されるので、チャットセッションで共有されているチームのチャットとドキュメント (作成またはアップロードされたデータサブジェクト) は、DSR ケースの組み込み検索によって返されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p170">Conversations that are part of the Chat list in Microsoft Teams (called Team chats or one-to-one chats) are stored in the Exchange Online mailbox of the users who participate in the chats. Also, the files a person shares in a one-to-one chat are stored in the OneDrive account of the person who shares the file. Because the built-in search searches all mailboxes and OneDrive accounts in the organization, team chats and documents shared in a chat session (that the data subject created or uploaded) will be returned by built-in search in a DSR case.</span></span>
  
<span data-ttu-id="bfe7d-p171">または、Teams チャネル (チャネルメッセージとも呼ばれます) の一部である会話は、チームに関連付けられているメールボックスに格納されます。Microsoft Teams に関連付けられたすべてのメールボックスが検索されるため、データサブジェクトが参加した会話の種類は、組み込みの検索によっても返されます。また、データ主体が Teams チャネルで共有している可能性があるタイルは、チームの SharePoint サイトに格納されます。作成または uploadedby のファイルは、Microsoft Teams に関連付けられているサイトが検索に含まれるため、DSR ケースでは組み込み検索によって返されます。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p171">Alternatively, conversations that are part of a Teams channel (also called channel messages) are stored in the mailbox that's associated with a team. These types of conversations that the data subject participated in are also returned by the built-in search because all mailboxes associated with Microsoft Teams are searched. Additionally, tiles that a data subject might have shared in a Teams channel are stored on the team's SharePoint site. Files created or uploadedby the data subject will be returned by the built-in search in a DSR case because sites associated with Microsoft Teams are included in the search.</span></span>
  
<span data-ttu-id="bfe7d-p172">同様に、Office 365 グループに対応するメールボックスと SharePoint サイトも、組み込み検索に含まれています。これは、データの件名で送受信された電子メールメッセージと、データ主体によって作成またはアップロードされたファイルが返されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p172">Similarly, mailboxes and SharePoint sites that correspond to an Office 365 Group are also included in the built-in search. This means that email messages that where sent or received by the data subject and files created or uploaded by the data subject will be returned.</span></span> 
  
<span data-ttu-id="bfe7d-424">コンテンツ検索を使用して Microsoft Teams および office 365 グループ内のアイテムを検索する方法、またはメンバーの一覧を取得する方法については、「 [Office 365 のコンテンツ検索](content-search.md#searching-microsoft-teams-and-office-365-groups)」の「microsoft teams および office 365 グループを検索する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-424">For more information about using Content Search to search for items in Microsoft Teams and Office 365 Groups or to see how to get a list of a members, see the "Searching Microsoft Teams and Office 365 Groups" section in [Content Search in Office 365](content-search.md#searching-microsoft-teams-and-office-365-groups).</span></span> 
  
### <a name="searching-exchange-public-folders"></a><span data-ttu-id="bfe7d-425">Exchange パブリックフォルダーの検索</span><span class="sxs-lookup"><span data-stu-id="bfe7d-425">Searching Exchange public folders</span></span>

<span data-ttu-id="bfe7d-p173">DSR ケースの組み込み検索は、メールが有効なパブリックフォルダーに送信された電子メールメッセージ、または他のユーザーがパブリックフォルダーに送信し、データ主体もコピーしたメッセージのみを返します。データの件名がパブリックフォルダーに投稿された可能性があるというメッセージは返されません。データ主体がパブリックフォルダーに投稿したアイテムを検索するには、別のコンテンツ検索を作成して、データ主体によってパブリックフォルダーに投稿されたアイテムを検索します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p173">The built-in search in a DSR case will only return email messages that the data subject sent to a mail-enabled public folder or messages that someone else sent to a public folder and also copied the data subject . It will not return message that the data subject might have posted to a public folder. To search for items that the data subject posted to a public folder, you can create a separate create a separate Content Search that searches for any item posted to a public folder by the data subject.</span></span>
  
<span data-ttu-id="bfe7d-429">ここでは、データの件名がパブリックフォルダーに投稿されている可能性があるアイテムを検索するための大まかなプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-429">Here's a high-level process to search for items that the data subject might have posted to a public folder.</span></span> 
  
1. <span data-ttu-id="bfe7d-430">DSR ケースを開き、[**検索**] ページで新しい検索を作成します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-430">Open the DSR case and create a new search on the **Search** page.</span></span> 
    
2. <span data-ttu-id="bfe7d-431">検索クエリと検索するコンテンツの場所を構成するには、次の条件を使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-431">Use the following criteria for configuring the search query and the content locations to search:</span></span>
    
  - <span data-ttu-id="bfe7d-432">[**キーワード**] ボックスで、次の検索クエリを使用します。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-432">In the **Keywords** box, use the following search query:</span></span> 
    
    ```
    itemclass:ipm.post AND "<email address of the data subject>"
    ```

  - <span data-ttu-id="bfe7d-433">すべての Exchange パブリックフォルダーを検索する</span><span class="sxs-lookup"><span data-stu-id="bfe7d-433">Search all Exchange public folders</span></span>
    
  - <span data-ttu-id="bfe7d-p174">検索を実行して完了した後、検索結果をエクスポートしてダウンロードできます ([手順 4](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#step4)で説明)。次の設定を使用して、部分的にインデックスが作成されたアイテムをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="bfe7d-p174">After you run the search and it completes, you can export and download the search results (as described in [Step 4](manage-gdpr-data-subject-requests-with-the-dsr-case-tool.md#step4)). Use the following settings to export partially indexed items.</span></span> 
