---
title: Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる
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
ms.assetid: 5b9a067b-9d2e-4aa5-bb33-99d8c0d0b5d7
description: セキュリティ&amp; /コンプライアンスセンターを使用して、電子情報開示関連のタスクを実行するために必要なアクセス許可を割り当てます。
ms.openlocfilehash: 6b79a15c631fce272c350a826ccd6b371a1672b2
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296400"
---
# <a name="assign-ediscovery-permissions-in-the-office-365-security-amp-compliance-center"></a><span data-ttu-id="8b61b-103">Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8b61b-103">Assign eDiscovery permissions in the Office 365 Security &amp; Compliance Center</span></span>

<span data-ttu-id="8b61b-p101">Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示関連のツールを使用する場合は、適切なアクセス許可をユーザーに割り当てる必要があります。これを行う最も簡単な方法は、Office 365 セキュリティ&amp;コンプライアンスセンターの [**アクセス許可**] ページで該当する役割グループをユーザーに追加することです。このトピックでは、セキュリティ&amp;コンプライアンスセンターを使用して電子情報開示関連のタスクを実行するために必要なアクセス許可について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p101">If you want people to use any of the eDiscovery-related tools in the Office 365 Security &amp; Compliance Center, you have to assign them the appropriate permissions. The easiest way to do this is to add the person the appropriate role group on the **Permissions** page in the Office 365 Security &amp; Compliance Center. This topic describes the permissions required to perform eDiscovery-related tasks using the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="8b61b-p102">セキュリティ&amp; /コンプライアンスセンターにある主要な電子情報開示関連役割グループは、**電子情報開示マネージャー**と呼ばれます。この役割グループ内には、2つのサブグループがあります。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p102">The primary eDiscovery-related role group in Security &amp; Compliance Center is called **eDiscovery Manager**. There are two subgroups within this role group.</span></span> 
  
- <span data-ttu-id="8b61b-p103">**電子情報開示管理者**-電子情報開示管理者は、セキュリティ&amp;コンプライアンスセンターのコンテンツ検索ツールを使用して、組織内のコンテンツの場所を検索し、プレビューやエクスポート検索など、さまざまな検索関連のアクションを実行できます。出力.また、メンバーは、電子情報開示ケースの作成と管理、ケースへのメンバーの追加および削除、ケース保持の作成、ケースに関連付けられたコンテンツ検索の実行、Office 365 Advanced eDiscovery でのサポート案件データへのアクセスも行うことができます。 電子情報開示の管理者は、作成するケースのみにアクセスして管理することができます。他の電子情報開示管理者が作成したケースにアクセスしたり、管理したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p103">**eDiscovery Managers** - An eDiscovery Manager can use the Content Search tool in the Security &amp; Compliance Center to search content locations in the organization, and perform various search-related actions such as preview and export search results. Members can also create and manage eDiscovery cases, add and remove members to a case, create case holds, and run Content Searches associated with a case, and access case data in Office 365 Advanced eDiscovery.  An eDiscovery Managers can only access and manage the cases they create. They can't access or manage cases created by other eDiscovery Managers.</span></span> 
    
- <span data-ttu-id="8b61b-p104">**電子**情報開示管理者-電子情報開示管理者は電子情報開示マネージャーの役割グループのメンバーであり、電子情報開示管理者が実行できるものと同じコンテンツ検索とケース管理に関連するタスクを実行できます。また、電子情報開示管理者は次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p104">**eDiscovery Administrators** - An eDiscovery Administrator is a member of the eDiscovery Manager role group, and can perform the same Content Search and case management-related tasks that an eDiscovery Manager can perform. Additionally, an eDiscovery Administrator can:</span></span> 
    
  - <span data-ttu-id="8b61b-115">セキュリティ&amp; /コンプライアンスセンターの [**電子情報開示ケース**] ページに記載されているすべてのケースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8b61b-115">Access all cases that are listed on the **eDiscovery cases** page in the Security &amp; Compliance Center.</span></span> 

  - <span data-ttu-id="8b61b-116">組織内のあらゆるケースについて、Advanced 電子情報開示のケースデータにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8b61b-116">Access case data in Advanced eDiscovery for any case in the organization.</span></span>
    
  - <span data-ttu-id="8b61b-117">自分自身をケースのメンバーとして追加した後のすべての電子情報開示のケースの管理。</span><span class="sxs-lookup"><span data-stu-id="8b61b-117">Manage any eDiscovery case after they add themself as a member of the case.</span></span>
  
  <span data-ttu-id="8b61b-118">組織の電子情報開示管理者が必要になる理由については、「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-118">See the [More information](#more-information) section for reasons why you might want eDiscovery Administrators in your organization.</span></span> 

> [!NOTE]
> <span data-ttu-id="8b61b-p105">Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office 365 E5 ライセンスが割り当てられている必要があります。または、Office 365 E1 または E3 ライセンスを持つユーザーに、Advanced eDiscovery スタンドアロンライセンスを割り当てることができます。ケースに割り当てられ、高度な電子情報開示を使用してデータを分析する管理者とコンプライアンス責任者は、E5 ライセンスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p105">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="8b61b-122">はじめに</span><span class="sxs-lookup"><span data-stu-id="8b61b-122">Before you begin</span></span>

- <span data-ttu-id="8b61b-123">セキュリティ&amp; /コンプライアンスセンターで電子情報開示のアクセス許可を割り当てるには、組織の管理役割グループのメンバーであるか、または役割管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b61b-123">You have to be a member of the Organization Management role group (or be assigned the Role Management role) to assign eDiscovery permissions in the Security &amp; Compliance Center.</span></span>
    
- <span data-ttu-id="8b61b-p106">セキュリティ&amp;コンプライアンスセンターの PowerShell で[add-rolegroupmember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx)コマンドレットを使用して、メールが有効なセキュリティグループを電子情報開示マネージャーの役割グループの電子情報開示マネージャーサブグループのメンバーとして追加できます。ただし、メールが有効なセキュリティグループを電子情報開示管理者サブグループに追加することはできません。詳細については、「 [more information](#more-information) 」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p106">You can use the [Add-RoleGroupMember](https://technet.microsoft.com/en-us/library/dd638207%28v=exchg.160%29.aspx) cmdlet in Security &amp; Compliance Center PowerShell to add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group. However, you can't add a mail-enabled security group to the eDiscovery Administrators subgroup. See the [More information](#more-information) section for more details.</span></span> 
    
## <a name="assign-ediscovery-permissions-in-the-security-amp-compliance-center"></a><span data-ttu-id="8b61b-127">セキュリティ&amp; /コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="8b61b-127">Assign eDiscovery permissions in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="8b61b-128">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="8b61b-128">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="8b61b-129">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="8b61b-129">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="8b61b-130">セキュリティ&amp; /コンプライアンスセンターの左側のウィンドウで、[**アクセス許可**] をクリックし、[**電子情報開示マネージャー**] の横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="8b61b-130">In the left pane of the Security &amp; Compliance Center, click **Permissions**, and then click the checkbox next to **eDiscovery Manager**.</span></span>
    
4. <span data-ttu-id="8b61b-131">[**電子情報開示マネージャー**のポップアップ] ページで、割り当てる電子情報開示のアクセス許可に基づいて、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8b61b-131">On the **eDiscovery Manager** flyout page, do one of the following based on the eDiscovery permissions that you want to assign.</span></span> 
    
  - <span data-ttu-id="8b61b-p107">**ユーザーに電子情報開示マネージャーを設定するに**は[**電子情報開示マネージャー**] の横にある [**編集**] をクリックします。[**選択した電子情報開示マネージャー**] の [ ![**編集**]](media/ITPro-EAC-AddIcon.gif) \*\*\*\* をクリックし、[追加] アイコンをクリックします。電子情報開示管理者として追加するユーザー (複数のユーザー) を選択し、[**追加**] をクリックします。ユーザーの追加が完了したら、[**完了**] をクリックします。その後、[**編集] [電子情報開示マネージャー**のポップアップの選択] ページで、[**保存**] をクリックして、電子情報開示マネージャーのメンバーシップへの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p107">**To make a user an eDiscovery Manager** Next to **eDiscovery Manager**, click **Edit**. Under **Selected eDiscovery Managers**, click **Edit**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery manager, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Manager** flyout page, click **Save** to save the changes to the eDiscovery Manager membership.</span></span> 
    
  - <span data-ttu-id="8b61b-p108">**ユーザーに電子情報開示管理者を作成するに**は[**電子情報開示管理者**] の横にある [**編集**] をクリックします。[**選択した電子情報開示管理者**] で![[**編集**] をクリックし、[追加] アイコン](media/ITPro-EAC-AddIcon.gif) **追加**をクリックします。電子情報開示管理者として追加するユーザー (複数のユーザー) を選択し、[**追加**] をクリックします。ユーザーの追加が完了したら、[**完了**] をクリックします。その後、[**編集] [電子情報開示管理者**のポップアップの選択] ページで、[**保存**] をクリックして、電子情報開示管理者のメンバーシップに対する変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p108">**To make a user an eDiscovery Administrator** Next to **eDiscovery Administrator**, click **Edit**. Under **Selected eDiscovery Administrators**, click **Edit**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**. Select the user (or users) you want to add as an eDiscovery Administrator, and then click **Add**. When you're finished adding users, click **Done**. Then, on the **Editing Choose eDiscovery Administrator** flyout page, click **Save** to save the changes to the eDiscovery Administrator membership.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="8b61b-p109">また、 **Add-ediscoverycaseadmin**コマンドレットを使用して、ユーザーを電子情報開示管理者にすることもできます。ただし、このコマンドレットを使用して電子情報開示管理者にするには、ユーザーにケース管理役割が割り当てられている必要があります。詳細については、「 [Add-ediscoverycaseadmin](https://go.microsoft.com/fwlink/p/?LinkID=798217)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p109">You can also use the **Add-eDiscoveryCaseAdmin** cmdlet to make a user an eDiscovery Administrator. However, the user must be assigned the Case Management role before you can use this cmdlet to make them an eDiscovery Administrator. For more information, see [Add-eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkID=798217).</span></span> 
  
<span data-ttu-id="8b61b-p110">セキュリティ&amp; /コンプライアンスセンターの [**アクセス許可**] ページで、[コンプライアンス管理者]、[組織の管理]、および [レビューアー] の役割グループにユーザーを追加することによって、電子情報開示に関連するアクセス許可をユーザーに割り当てることもできます。これらの各役割グループに割り当てられている電子情報開示関連の rbac の役割の説明については、「[電子情報開示に関連する rbac の役割](#rbac-roles-related-to-ediscovery)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p110">On the **Permissions** page in the Security &amp; Compliance Center, you can also assign users eDiscovery-related permissions, by adding them to the Compliance Administrator, Organization Management, and Reviewer role groups. For a description of the eDiscovery-related RBAC roles assigned to each of these role groups, see the [RBAC roles related to eDiscovery](#rbac-roles-related-to-ediscovery) section.</span></span> 

## <a name="rbac-roles-related-to-ediscovery"></a><span data-ttu-id="8b61b-147">電子情報開示に関連する RBAC の役割</span><span class="sxs-lookup"><span data-stu-id="8b61b-147">RBAC roles related to eDiscovery</span></span>

<span data-ttu-id="8b61b-148">次の表に、セキュリティ & コンプライアンスセンターの電子情報開示関連の RBAC の役割を示します。既定では、各役割に割り当てられている組み込みの役割グループを示しています。</span><span class="sxs-lookup"><span data-stu-id="8b61b-148">The following table lists the eDiscovery-related RBAC roles in the Security & Compliance Center, and indicates the built-in role groups that each role is assigned to by default.</span></span> 
    
|<span data-ttu-id="8b61b-149">**役割**</span><span class="sxs-lookup"><span data-stu-id="8b61b-149">**Role**</span></span>|<span data-ttu-id="8b61b-150">**コンプライアンス管理者**</span><span class="sxs-lookup"><span data-stu-id="8b61b-150">**Compliance Administrator**</span></span>|<span data-ttu-id="8b61b-151">**電子情報開示マネージャー & 管理者**</span><span class="sxs-lookup"><span data-stu-id="8b61b-151">**eDiscovery Manager & Administrator**</span></span>|<span data-ttu-id="8b61b-152">**組織の管理**</span><span class="sxs-lookup"><span data-stu-id="8b61b-152">**Organization Management**</span></span>|<span data-ttu-id="8b61b-153">**レビュー担当者**</span><span class="sxs-lookup"><span data-stu-id="8b61b-153">**Reviewer**</span></span>|
|:-----|:-----:|:-----:|:-----:|:-----:|
|<span data-ttu-id="8b61b-154">ケース管理</span><span class="sxs-lookup"><span data-stu-id="8b61b-154">Case Management</span></span> <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="8b61b-158">コンプライアンス検索</span><span class="sxs-lookup"><span data-stu-id="8b61b-158">Compliance Search</span></span> <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="8b61b-162">エクスポート</span><span class="sxs-lookup"><span data-stu-id="8b61b-162">Export</span></span> <br/> | <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|<span data-ttu-id="8b61b-164">保留</span><span class="sxs-lookup"><span data-stu-id="8b61b-164">Hold</span></span> <br/>  |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |
|<span data-ttu-id="8b61b-168">プレビュー</span><span class="sxs-lookup"><span data-stu-id="8b61b-168">Preview</span></span> <br/>  | <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> | <br/> |
|<span data-ttu-id="8b61b-170">確認</span><span class="sxs-lookup"><span data-stu-id="8b61b-170">Review</span></span> <br/>  | <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> | <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |
|<span data-ttu-id="8b61b-173">RMS の復号化</span><span class="sxs-lookup"><span data-stu-id="8b61b-173">RMS Decrypt</span></span> <br/>  ||![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png) <br/> |||
|<span data-ttu-id="8b61b-175">検索と削除</span><span class="sxs-lookup"><span data-stu-id="8b61b-175">Search And Purge</span></span> <br/> | <br/> | <br/> |![チェック マーク](media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)           <br/> | <br/> | 
||||
  
<span data-ttu-id="8b61b-177">次のセクションでは、前の表に示した電子情報開示関連の各 RBAC の役割について説明します。</span><span class="sxs-lookup"><span data-stu-id="8b61b-177">The following sections describe each of the eDiscovery-related RBAC roles listed in the previous table.</span></span>

### <a name="case-management"></a><span data-ttu-id="8b61b-178">ケース管理</span><span class="sxs-lookup"><span data-stu-id="8b61b-178">Case Management</span></span>

<span data-ttu-id="8b61b-p111">この役割により、ユーザーはセキュリティ & コンプライアンスセンターで電子情報開示ケースへのアクセスを作成、編集、削除、制御することができます。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のケースを管理する](manage-ediscovery-cases.md)」を参照してください。前述したように、ユーザーにはケース管理の役割が割り当てられて\*\*\*\* いる必要があります。その前に、ユーザーに対して電子情報開示管理者を作成するために、このコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p111">This role lets users create, edit, delete, and control access to eDiscovery cases in the Security & Compliance Center. For more information, see [Manage eDiscovery cases in the Office 365 Security &amp; Compliance Center](manage-ediscovery-cases.md). As previously explained, a user must be assigned the Case Management role before you can use the **Add-eDiscoveryCaseAdmin** cmdlet to make them an eDiscovery Administrator.</span></span> 

### <a name="compliance-search"></a><span data-ttu-id="8b61b-182">コンプライアンス検索</span><span class="sxs-lookup"><span data-stu-id="8b61b-182">Compliance Search</span></span>

<span data-ttu-id="8b61b-p112">この役割により、ユーザーは、Security & コンプライアンスセンターでコンテンツ検索ツールを実行して、メールボックスとパブリックフォルダー、SharePoint Online サイト、OneDrive for business サイト、Skype for business の会話、Office 365 グループ、および Microsoft Teams を検索できます。この役割によって、ユーザーは検索結果の推定を取得し、エクスポートレポートを作成できますが、検索結果のプレビュー、エクスポート、削除などのコンテンツ検索アクションを開始するには、追加のロールが必要です。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p112">This role lets users run the Content Search tool in the Security & Compliance Center to search mailboxes and public folders, SharePoint Online sites, OneDrive for Business sites, Skype for Business conversations, Office 365 Groups, and Microsoft Teams. This role allows a user to get an estimate of the search results and create export reports, but additional roles are needed to initiate content search actions such as previewing, exporting, or deleting search results.</span></span>

<span data-ttu-id="8b61b-p113">ユーザーがコンプライアンス検索の役割を割り当てているが、プレビューの役割を持っていない場合は、プレビューの役割が割り当てられているユーザーによってプレビューアクションが開始されたことを示す検索結果をプレビューできないことに注意してください。プレビューの役割を持たないユーザーは、最初のプレビュー操作が作成されてから最大2週間後に結果をプレビューできます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p113">Note that users assigned the Compliance Search role but don't have the Preview role can preview the results of a search in which the preview action has been initiated by a user that's assigned the Preview role. The user without the Preview role can preview results for up to 2 weeks after the initial preview action was created.</span></span>

<span data-ttu-id="8b61b-p114">同様に、コンプライアンス検索の役割を割り当てられているユーザーは、エクスポートの役割が割り当てられていないユーザーによってエクスポートアクションが開始された検索の結果をダウンロードすることもできます。エクスポートの役割を持たないユーザーは、最初のエクスポート操作が作成されてから最大2週間後に検索の結果をダウンロードできます。その後、エクスポートの役割を持つユーザーがエクスポートを再開しない限り、結果をダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p114">Similarly, users assigned the Compliance Search role but don't have the Export role can download the results of a search in which the export action has initiated by a user that's assigned the Export role. The user without the Export role can download the results of a search for up to 2 weeks after the initial export action was created. After that they won’t be able to download the results unless someone with the Export role restarts the export.</span></span>

<span data-ttu-id="8b61b-190">詳細については、「 [Office 365 のコンテンツ検索](content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-190">For more information, see [Content Search in Office 365](content-search.md).</span></span> 

### <a name="export"></a><span data-ttu-id="8b61b-191">エクスポート</span><span class="sxs-lookup"><span data-stu-id="8b61b-191">Export</span></span>

<span data-ttu-id="8b61b-p115">役割を使用すると、ユーザーはコンテンツ検索の結果をローカルコンピューターにエクスポートできます。また、高度な電子情報開示で分析のための検索結果を準備することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p115">The role lets users export the results of a Content Search to a local computer. It also lets them prepare search results for analysis in Advanced eDiscovery.</span></span> 

<span data-ttu-id="8b61b-194">検索結果のエクスポートの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターの検索結果をエクスポートする](export-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-194">For more information about exporting search results, see [Export search results from the Office 365 Security & Compliance Center](export-search-results.md).</span></span>

### <a name="hold"></a><span data-ttu-id="8b61b-195">保留</span><span class="sxs-lookup"><span data-stu-id="8b61b-195">Hold</span></span>

<span data-ttu-id="8b61b-p116">この役割を使用すると、ユーザーはメールボックス、パブリックフォルダー、サイト、Skype for business の会話、および Office 365 グループにコンテンツを格納できます。コンテンツが保持されている場合でも、コンテンツ所有者は元のコンテンツを変更または削除できますが、保持が削除されるか保持期間が経過するまで、コンテンツは保持されます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p116">This role lets users place content in mailboxes, public folders, sites, Skype for Business conversations, and Office 365 groups on hold. When content is on hold, content owners will still be able to modify or delete the original content, but the content will be preserved until the hold is removed or until the hold duration expires.</span></span> 

<span data-ttu-id="8b61b-198">保留の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-198">For more information about holds, see:</span></span>

- [<span data-ttu-id="8b61b-199">Office 365 Security & コンプライアンスセンターの電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="8b61b-199">eDiscovery cases in the Office 365 Security & Compliance Center</span></span>](ediscovery-cases.md) 
- [<span data-ttu-id="8b61b-200">アイテム保持ポリシーの概要</span><span class="sxs-lookup"><span data-stu-id="8b61b-200">Overview of retention policies</span></span>](retention-policies.md)

### <a name="preview"></a><span data-ttu-id="8b61b-201">プレビュー</span><span class="sxs-lookup"><span data-stu-id="8b61b-201">Preview</span></span>

<span data-ttu-id="8b61b-p117">この役割により、ユーザーはコンテンツ検索から返されたアイテムの一覧を表示できます。また、リストから各アイテムを開いて表示し、コンテンツを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p117">This role lets users view a list of items that were returned from a Content Search. They'll also be able to open and view each item from the list to view its contents.</span></span>

### <a name="review"></a><span data-ttu-id="8b61b-204">確認</span><span class="sxs-lookup"><span data-stu-id="8b61b-204">Review</span></span>

<span data-ttu-id="8b61b-p118">この役割により、ユーザーは Office 365 の高度な電子情報開示のケースデータにアクセスできるようになります。この役割の主な目的は、ユーザーが高度な電子情報開示にアクセスできるようにすることです。この役割を割り当てられたユーザーは、自分がメンバーになっているセキュリティ & コンプライアンスセンターの電子情報開示ページで、ケースの一覧を表示して開くことができます。セキュリティ & コンプライアンスセンターでユーザーがケースにアクセスした後、[ **advanced ediscovery に切り替え**] をクリックすると、advanced ediscovery でケースデータにアクセスして分析することができます。この役割では、ユーザーは、ケースに関連付けられたコンテンツ検索の結果をプレビューしたり、その他のコンテンツ検索やケース管理タスクを実行したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p118">This role lets users access case data in Office 365 Advanced eDiscovery. The primary purpose of this role is to give users access to Advanced eDiscovery. Users who are assigned this role can see and open the list of cases on the eDiscovery page in the Security & Compliance Center that they are members of. After the user accesses a case in the Security & Compliance Center, they can click **Switch to Advanced eDiscovery** to access and analyze the case data in Advanced eDiscovery. This role doesn't allow the user to preview the results of a content search that's associated with the case or to perform other content search or case management tasks.</span></span>

### <a name="rms-decrypt"></a><span data-ttu-id="8b61b-210">RMS の復号化</span><span class="sxs-lookup"><span data-stu-id="8b61b-210">RMS Decrypt</span></span>

<span data-ttu-id="8b61b-p119">この役割により、ユーザーは検索結果をエクスポートするとき、または高度な電子情報開示で分析のために検索結果を準備するときに、RMS で暗号化された電子メールメッセージを解読エクスポート中の検索結果の復号化の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターの検索結果をエクスポートする](export-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p119">This role lets users decrypt RMS-encrypted email messages when exporting search results or preparing search results for analysis in Advanced eDiscovery. For more information about decrypting search results during export, see [Export search results from the Office 365 Security & Compliance Center](export-search-results.md).</span></span>

### <a name="search-and-purge"></a><span data-ttu-id="8b61b-213">検索と削除</span><span class="sxs-lookup"><span data-stu-id="8b61b-213">Search And Purge</span></span>

<span data-ttu-id="8b61b-p120">この役割により、ユーザーはコンテンツ検索の条件に一致するデータを一括で削除することができます。詳細については、「 [Office 365 組織の電子メールメッセージの検索と削除](search-for-and-delete-messages-in-your-organization.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p120">This role lets users perform bulk removal of data matching the criteria of a content search. For more information, see [Search for and delete email messages in your Office 365 organization](search-for-and-delete-messages-in-your-organization.md).</span></span> 


## <a name="more-information"></a><span data-ttu-id="8b61b-216">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8b61b-216">More information</span></span>

- <span data-ttu-id="8b61b-p121">**電子情報開示管理者を作成する理由**前述したように、電子情報開示管理者は、組織内のすべての電子情報開示ケースを表示してアクセスできる電子情報開示マネージャーの役割グループのメンバーです。すべての電子情報開示ケースにアクセスする機能には、次の2つの重要な目的があります。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p121">**Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes:</span></span> 
    
  - <span data-ttu-id="8b61b-p122">電子情報開示ケースの唯一のメンバーであるユーザーが組織を離れた場合、(組織の管理役割グループのメンバーまたは電子情報開示マネージャーの役割グループのメンバーを含む) は、その電子情報開示ケースにアクセスできるのはメンバーではないためです。ケースの。このような状況では、ケース内のデータにアクセスする方法はありません。しかし、電子情報開示管理者は組織内のすべての電子情報開示ケースにアクセスできるため、 &amp;セキュリティコンプライアンスセンターでケースを表示し、自分または別の電子情報開示マネージャーをケースのメンバーとして追加することができます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p122">If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case. In this situation, there would be no way to access the data in the case. But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security &amp; Compliance Center and add themselves or another eDiscovery manager as a member of the case.</span></span>
    
  - <span data-ttu-id="8b61b-p123">電子情報開示管理者はすべての電子情報開示ケースを表示してアクセスできるため、すべてのケースと関連するコンプライアンス検索を監査して監視することができます。これにより、コンプライアンス検索や電子情報開示ケースの悪用を防ぐことができます。また、電子情報開示管理者は、コンプライアンス検索の結果に含まれる潜在的な機密情報にアクセスできるため、電子情報開示管理者の人数を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p123">Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated compliance searches. This can help to prevent any misuse of compliance searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a compliance search, you should limit the number of people who are eDiscovery Administrators.</span></span>
    
    <span data-ttu-id="8b61b-p124">また、セキュリティ&amp;コンプライアンスセンターの電子情報開示管理者は、高度な電子情報開示の管理者として自動的に追加されます。つまり、ユーザーの設定、ケースの作成、ケースへのデータのインポートなど、上級電子情報開示で管理タスクを実行するために、電子情報開示管理者であることが必要です。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p124">Also, eDiscovery Administrators in the Security &amp; Compliance Center are automatically added as administrators in Advanced eDiscovery. That means a person must be an eDiscovery Administrator to perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and importing data in to a case.</span></span>
    
- <span data-ttu-id="8b61b-p125">**セキュリティ&amp; /コンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーとしてグループを追加できますか。** 前述のとおり、セキュリティ&amp;コンプライアンスセンターの PowerShell で**add-rolegroupmember**コマンドレットを使用して、メールが有効なセキュリティグループを電子情報開示マネージャーの役割グループのメンバーとして追加できます。たとえば、次のコマンドを実行して、メールが有効なセキュリティグループを電子情報開示マネージャーの役割グループに追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p125">**Can I add a group as a member of the eDiscovery Manager role group in the Security &amp; Compliance Center?** As previously explained, you can add a mail-enabled security group as a member of the eDiscovery Managers subgroup in the eDiscovery Manager role group by using the **Add-RoleGroupMember** cmdlet in Security &amp; Compliance Center PowerShell. For example, you can run the following command to add a mail-enabled security group to the eDiscovery Manager role group.</span></span> 
    
  ```
  Add-RoleGroupMember "eDiscovery Manager" -Member <name of security group>
  ```

    <span data-ttu-id="8b61b-p126">Exchange 配布グループまたは Office 365 グループがサポートされていないことに注意してください。Exchange Online PowerShell で` New-DistributionGroup -Type Security `コマンドを使用して作成できる、メールが有効なセキュリティグループを使用する必要があります。また、Exchange 管理センターまたは Office 365 管理センターで、メールが有効なセキュリティグループ (およびメンバーを追加する) を作成することもできます。新しいメールが有効なセキュリティが電子情報開示マネージャーの役割グループに追加されるようになるまで、最大で60分かかる場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p126">Note that an Exchange distribution group or an Office 365 group aren't supported. You must use a mail-enabled security group, which you can create in Exchange Online PowerShell by using the ` New-DistributionGroup -Type Security ` command. You can also create a mail-enabled security group (and add members) in the Exchange admin center or in the Office 365 admin center. Note that it might take up to 60 minutes after you create it for a new mail-enabled security to be available to add to the eDiscovery Managers role group.</span></span> 
    
    <span data-ttu-id="8b61b-p127">また、前述したように、セキュリティ&amp;コンプライアンスセンターの PowerShell で**アドオン**コマンドレットを使用して、メールが有効なセキュリティグループを電子情報開示管理者にすることはできません。個人ユーザーは、電子情報開示管理者としてのみ追加できます。</span><span class="sxs-lookup"><span data-stu-id="8b61b-p127">Also as previously stated, you can't make a mail-enabled security group an eDiscovery Administrator by using the **Add-eDiscoveryCaseAdmin** cmdlet in Security &amp; Compliance Center PowerShell. You can only add individual users as eDiscovery Administrators.</span></span> 
    
    <span data-ttu-id="8b61b-237">メールが有効なセキュリティグループをケースのメンバーとして追加することもできないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="8b61b-237">Note that you also can't add a mail-enabled security group as a member of a case.</span></span>
