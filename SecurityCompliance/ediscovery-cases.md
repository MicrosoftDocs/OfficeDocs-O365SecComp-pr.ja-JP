---
title: セキュリティ & コンプライアンスセンターの電子情報開示ケース
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
ms.assetid: 8dd335ab-29d0-41c3-8dd8-9f7c7481e60c
description: セキュリティ & コンプライアンスセンターを使用して、組織内の電子情報開示ケースを作成して管理します。 ケースにメンバーを割り当てたり、コンテンツの場所を保持に配置したり、ケースに関連付けられたコンテンツ検索を実行したり、検索結果をエクスポートしたりすることができます。 また、高度な電子情報開示に関する詳細な分析のためにケースデータを準備することもできます。
ms.openlocfilehash: 5f31153e70495dc28ee276c36e9edfc67638956e
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32257975"
---
# <a name="ediscovery-cases-in-the-security--compliance-center"></a><span data-ttu-id="09d7d-105">セキュリティ & コンプライアンスセンターの電子情報開示ケース</span><span class="sxs-lookup"><span data-stu-id="09d7d-105">eDiscovery cases in the Security & Compliance Center</span></span>

<span data-ttu-id="09d7d-106">Office 365 および Microsoft 365 のコンプライアンスセンターで電子情報開示ケースを使用して、組織内で電子情報開示ケースを作成、アクセス、および管理できるユーザーを制御することができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-106">You can use eDiscovery cases in the compliance center in Office 365 and Microsoft 365 to control who can create, access, and manage eDiscovery cases in your organization.</span></span> <span data-ttu-id="09d7d-107">組織に office 365 E5 サブスクリプションがある場合は、office 365 Advanced eDiscovery を使用して、電子情報開示ケースを使用して検索結果を分析することもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-107">If your organization has an Office 365 E5 subscription, you can also use eDiscovery cases to analyze search results by using Office 365 Advanced eDiscovery.</span></span>
  
<span data-ttu-id="09d7d-p103">電子情報開示ケースを使用すると、ケースへのメンバーの追加、特定のケース メンバーが実行可能なアクションの種類の制御、訴訟事件に関連のあるコンテンツの場所の保留、複数のコンテンツ検索と 1 つのケースの関連付けを実行できます。また、ケースに関連付けられたコンテンツ検索の結果をエクスポートしたり、Advanced eDiscovery で分析できるように検索結果を準備したりできます。電子情報開示ケースは、組織内の特定の訴訟事件に関するコンテンツ検索と検索結果にアクセスできるユーザーを制限するのに適切な方法です。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p103">An eDiscovery case allows you to add members to a case, control what types of actions that specific case members can perform, place a hold on content locations relevant to a legal case, and associate multiple Content Searches with a single case. You can also export the results of any Content Search that is associated with a case or prepare search results for analysis in Advanced eDiscovery. eDiscovery cases are a good way to limit who has access to Content Searches and search results for a specific legal case in your organization.</span></span>
  
<span data-ttu-id="09d7d-111">次のワークフローを使用して、セキュリティ & コンプライアンスセンターと高度な電子情報開示の電子情報開示ケースを設定および使用します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-111">Use the following workflow to set up and use eDiscovery cases in the Security & Compliance Center and Advanced eDiscovery.</span></span>

[<span data-ttu-id="09d7d-112">手順 1: 潜在的なケースのメンバーに電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="09d7d-112">Step 1: Assign eDiscovery permissions to potential case members</span></span>](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[<span data-ttu-id="09d7d-113">手順 2: 新しいケースを作成する</span><span class="sxs-lookup"><span data-stu-id="09d7d-113">Step 2: Create a new case</span></span>](#step-2-create-a-new-case)

[<span data-ttu-id="09d7d-114">手順 3: ケースにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="09d7d-114">Step 3: Add members to a case</span></span>](#step-3-add-members-to-a-case)

[<span data-ttu-id="09d7d-115">手順 4: コンテンツの場所を保留にする</span><span class="sxs-lookup"><span data-stu-id="09d7d-115">Step 4: Place content locations on hold</span></span>](#step-4-place-content-locations-on-hold)

[<span data-ttu-id="09d7d-116">手順 5: ケースに関連付けられているコンテンツ検索を作成して実行する</span><span class="sxs-lookup"><span data-stu-id="09d7d-116">Step 5: Create and run a Content Search associated with a case</span></span>](#step-5-create-and-run-a-content-search-associated-with-a-case)

[<span data-ttu-id="09d7d-117">手順 6: ケースに関連付けられているコンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="09d7d-117">Step 6: Export the results of a Content Search associated with a case</span></span>](#step-6-export-the-results-of-a-content-search-associated-with-a-case)

[<span data-ttu-id="09d7d-118">手順 7: Advanced eDiscovery 用に検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="09d7d-118">Step 7: Prepare search results for Advanced eDiscovery</span></span>](#step-7-prepare-search-results-for-advanced-ediscovery)

[<span data-ttu-id="09d7d-119">手順 8: Advanced eDiscovery のケースに移動する</span><span class="sxs-lookup"><span data-stu-id="09d7d-119">Step 8: Go to the case in Advanced eDiscovery</span></span>](#step-8-go-to-the-case-in-advanced-ediscovery)

[<span data-ttu-id="09d7d-120">(省略可能) 手順 9: ケースを閉じる</span><span class="sxs-lookup"><span data-stu-id="09d7d-120">(Optional) Step 9: Close a case</span></span>](#optional-step-9-close-a-case)

[<span data-ttu-id="09d7d-121">(省略可能) 手順 10: 閉じたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="09d7d-121">(Optional) Step 10: Re-open a closed case</span></span>](#optional-step-10-re-open-a-closed-case)

[<span data-ttu-id="09d7d-122">詳細情報</span><span class="sxs-lookup"><span data-stu-id="09d7d-122">More information</span></span>](#more-information)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a><span data-ttu-id="09d7d-123">手順 1: 潜在的なケースのメンバーに電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="09d7d-123">Step 1: Assign eDiscovery permissions to potential case members</span></span>

<span data-ttu-id="09d7d-124">最初の手順として、適切な電子情報開示関連のアクセス許可をユーザーに割り当てて、手順2で電子情報開示ケースに追加できるようにします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-124">The first step is to assign the appropriate eDiscovery-related permissions to people so you can add them to an eDiscovery case in Step 2.</span></span> <span data-ttu-id="09d7d-125">電子情報開示のアクセス許可を割り当てるには、セキュリティ & コンプライアンスセンターで、組織の管理役割グループのメンバーであるか (または、役割管理役割が割り当てられている必要があります)。</span><span class="sxs-lookup"><span data-stu-id="09d7d-125">You have to be a member of the Organization Management role group (or be assigned the Role Management role) in the Security & Compliance Center to assign eDiscovery permissions.</span></span> <span data-ttu-id="09d7d-126">次の一覧は、セキュリティ & コンプライアンスセンターの電子情報開示関連の役割グループを示しています。</span><span class="sxs-lookup"><span data-stu-id="09d7d-126">The following list describes the eDiscovery-related role groups in the Security & Compliance Center.</span></span> 
  
- <span data-ttu-id="09d7d-127">**レビュー担当者**-この役割グループには、電子情報開示関連のアクセス許可が最も制限されています。</span><span class="sxs-lookup"><span data-stu-id="09d7d-127">**Reviewer** - This role group has the most restrictive eDiscovery-related permissions.</span></span> <span data-ttu-id="09d7d-128">この役割グループの主な目的は、メンバーが Office 365 Advanced eDiscovery でケースデータの表示とアクセスを行えるようにすることです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-128">The primary purpose of this role group is to allow members to view and access case data in Office 365 Advanced eDiscovery.</span></span> <span data-ttu-id="09d7d-129">このグループのメンバーは、自分がメンバーになっているセキュリティ & コンプライアンスセンターの**電子情報開示**ページでのみ、ケースのリストを表示して開くことができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-129">Members of this group can only see and open the list of the cases on the **eDiscovery** page in the Security & Compliance Center that they are members of.</span></span> <span data-ttu-id="09d7d-130">セキュリティ/コンプライアンスセンターでユーザーがケースにアクセスした後、[ **advanced ediscovery に切り替え**] をクリックすると、高度な電子情報開示でケースデータにアクセスして分析することができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-130">After the user accesses a case in the security and compliance center, they can click **Switch to Advanced eDiscovery** to access and analyze the case data in Advanced eDiscovery.</span></span> <span data-ttu-id="09d7d-131">ケースを作成したり、ケースにメンバーを追加したり、ホールドを作成したり、検索を作成したり、検索結果をプレビューしたり、検索結果をエクスポートしたり、高度な電子情報開示の結果を準備したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-131">They can't create cases, add members to a case, create holds, create searches, preview search results, export search results, or prepare results for Advanced eDiscovery.</span></span> 
    
- <span data-ttu-id="09d7d-p106">**電子情報開示マネージャー** - この役割グループのメンバーは、電子情報開示ケースを作成して管理できます。このメンバーは、ケースへのメンバーの追加と削除、コンテンツの場所の保留、ケースに関連付けられたコンテンツ検索の作成と編集、コンテンツ検索の結果のエクスポート、Advanced eDiscovery で分析するための検索結果の準備ができます。この役割グループには 2 つのサブグループがあります。これらのサブグループの違いは、範囲に基づきます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p106">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases. They can add and remove members, place content locations on hold, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery. There are two sub-groups in this role group. The difference between these subgroups is based on scope.</span></span>
    
  - <span data-ttu-id="09d7d-136">**電子情報開示マネージャー** -自分が作成またはメンバーとなっている電子情報開示ケースを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-136">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="09d7d-137">別の電子情報開示管理者が作成したケースのメンバーとして2番目の電子情報開示マネージャーを追加しなかった場合、2番目の電子情報開示マネージャーは、Security & コンプライアンスセンターの [**電子情報開示**] ページでケースを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-137">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the **eDiscovery** page in the Security & Compliance Center.</span></span> <span data-ttu-id="09d7d-138">電子情報開示マネージャーは、高度な電子情報開示のケースにアクセスして分析タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-138">eDiscovery Managers can also access their cases in Advanced eDiscovery to perform analysis tasks.</span></span> 
    
  - <span data-ttu-id="09d7d-p108">**電子情報開示管理者** - 電子情報開示マネージャーが実行できるすべてのケースの管理タスクを実行できます。さらに、電子情報開示管理者は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p108">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do. Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="09d7d-141">[**電子情報開示**] ページにリストされたすべてのケースを表示する。</span><span class="sxs-lookup"><span data-stu-id="09d7d-141">View all cases that are listed on the **eDiscovery** page.</span></span> 
    
    - <span data-ttu-id="09d7d-142">自分自身をケースのメンバーとして追加した後、組織のすべてのケースを管理する。</span><span class="sxs-lookup"><span data-stu-id="09d7d-142">Manage any case in the organization after they add themself as a member of the case.</span></span>
    
    - <span data-ttu-id="09d7d-143">Advanced eDiscovery で組織内のすべてのケースに関するケース データにアクセスする。</span><span class="sxs-lookup"><span data-stu-id="09d7d-143">Access case data in Advanced eDiscovery for any case in the organization.</span></span>
    
    <span data-ttu-id="09d7d-144">組織に電子情報開示管理者が必要な理由については、「[詳細情報](#more-information)」セクションをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-144">See the [More information](#more-information) section for reasons why you may want an eDiscovery Administrator in your organization.</span></span> 
    
> [!IMPORTANT]
> <span data-ttu-id="09d7d-145">あるユーザーが、これらの電子情報開示関連のどの役割グループのメンバーでもなく、レビュー担当者の役割が割り当てられた役割グループのメンバーでもない場合は、そのユーザーを電子情報開示ケースのメンバーとして追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-145">If a person isn't a member of one of these eDiscovery-related role groups, or isn't a member of a role group that's assigned the Reviewer role, you can't add them as a member of an eDiscovery case.</span></span> 

<span data-ttu-id="09d7d-146">ediscovery アクセス許可の詳細については、「[電子情報開示のアクセス許可を割り当てる](assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-146">For more information about eDiscovery permissions, see [Assign eDiscovery permissions](assign-ediscovery-permissions.md).</span></span>
  
 <span data-ttu-id="09d7d-147">**電子情報開示のアクセス許可を割り当てるには:**</span><span class="sxs-lookup"><span data-stu-id="09d7d-147">**To assign eDiscovery permissions:**</span></span>
  
1. <span data-ttu-id="09d7d-148">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-148">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="09d7d-149">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-149">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="09d7d-150">セキュリティ & コンプライアンスセンターで、[**アクセス許可**] をクリックし、割り当てる電子情報開示のアクセス許可に基づいて次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-150">In the Security & Compliance Center, click **Permissions**, and then do one of the following based on the eDiscovery permissions that you want to assign.</span></span>
    
    - <span data-ttu-id="09d7d-p109">レビュー担当者のアクセス許可を割り当てるには、[**レビュー担当者**] 役割グループを選択し、[**メンバー**] の横にある [**編集**] をクリックします。[**メンバーの選択**]、[**編集**]、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) **追加**] の順にクリックし、レビュー担当者の役割グループに追加するユーザーを選択してから、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p109">To assign Reviewer permissions, select the **Reviewer** role group, and then next to **Members**, click **Edit**. Click **Choose members**, click **Edit**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**, select the user that you want to add to the Reviewer role group, and then click **Add**.</span></span>
    
    - <span data-ttu-id="09d7d-p110">電子情報開示マネージャーのアクセス許可を割り当てるには、[**電子情報開示管理者**] 役割グループを選択し、[**電子情報開示マネージャー**] の横にある [**編集**] をクリックします。[**電子情報開示マネージャーの選択**]、[**編集**]、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) 追加] の順にクリックし、電子情報開示マネージャーとして追加するユーザーを選択してから [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p110">To assign eDiscovery Manager permissions, select the **eDiscovery Manager** role group, and then next to **eDiscovery Manager**, click **Edit**. Click **Choose eDiscovery Manager**, click **Edit**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) \*\* Add \*\*, select the user that you want to add as an eDiscovery Manager, and then click **Add**.</span></span>
    
    - <span data-ttu-id="09d7d-p111">電子情報開示管理者のアクセス許可を割り当てるには、[**電子情報開示マネージャー**] 役割グループを選択し、[**電子情報開示管理者**] の横にある [**編集**] をクリックします。[**電子情報開示管理者の選択**]、[**編集**]、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) **追加**] の順にクリックし、電子情報開示管理者として追加するユーザーを選択してから [**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p111">To assign eDiscovery Administrator permissions, select the **eDiscovery Manager** role group, and then next to **eDiscovery Administrator**, click **Edit**. Click **Choose eDiscovery Administrator**, click **Edit**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**, select the user that you want to add as an eDiscovery Administrator, and then click **Add**.</span></span>
    
4. <span data-ttu-id="09d7d-157">すべてのユーザーを追加した後、[**完了**]、[**保存**] の順にクリックして変更を役割グループに保存してから、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-157">After you've added all the users, click **Done**, click **Save** to save the changes to the role group, and then click **Close**.</span></span>

## <a name="step-2-create-a-new-case"></a><span data-ttu-id="09d7d-158">手順 2: 新しいケースを作成する</span><span class="sxs-lookup"><span data-stu-id="09d7d-158">Step 2: Create a new case</span></span>

<span data-ttu-id="09d7d-159">次の手順では、新しい電子情報開示ケースを作成します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-159">The next step is to create a new eDiscovery case.</span></span> <span data-ttu-id="09d7d-160">電子情報開示のケースを作成するには、電子情報開示マネージャー役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-160">You must be a member of the eDiscovery Managers role group to create eDiscovery cases.</span></span> <span data-ttu-id="09d7d-161">前述のとおり、セキュリティ & コンプライアンスセンターで新しいケースを作成すると、組織に Office 365 E5 サブスクリプションがある場合は、上級電子情報開示でその同じケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-161">As previously explained, after you create a new case in the Security & Compliance Center, you (and other case members) will be able to access that same case in Advanced eDiscovery if your organization has an Office 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="09d7d-162">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-162">Go to [https://protection.office.com](https://protection.office.com).</span></span>
    
2. <span data-ttu-id="09d7d-163">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-163">Sign in to Office 365 using your work or school account.</span></span>
    
3. <span data-ttu-id="09d7d-164">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] ![をクリック](media/ITPro-EAC-AddIcon.gif)し、[追加] アイコンをクリックして**ケースを作成**します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-164">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery**, and then click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Create a case**.</span></span>
    
4. <span data-ttu-id="09d7d-p113">[**新しいケース**] ページで、ケースに名前を付け、オプションで説明を入力し、[**保存**] をクリックします。ケース名は組織内で一意である必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p113">On the **New Case** page, give the case a name, type an optional description, and then click **Save**. Note that the case name must be unique in your organization.</span></span>
    
    ![新しいケースを作成する](media/7f78f83b-1525-4c77-9888-4b6bda1e148d.png)
  
    <span data-ttu-id="09d7d-p114">新しいケースは、[**電子情報開示**] ページのケースのリストに表示されます。なお、ケース名の上にカーソルを置くと、ケースの状態 ([**アクティブ**] または [**閉じる**])、(前述の手順で作成した) ケースの説明、ケースの最終更新日および更新者を含む、ケースの情報を表示できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p114">The new case is displayed in the list of cases on the **eDiscovery** page. Note that you can hover the cursor over a case name to display information about the case, including the status of the case ( **Active** or **Closed**), the description of the case (that was created in the previous step), and when the case was changed last and who changed it.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="09d7d-p115">新しいケースを作成した後に、いつでも名前を変更することができます。[**電子情報開示**] ページのケース名をクリックするだけです。[**このケースの管理**] ポップアップ ページで、[**名前**] のボックスに表示される名前を変更してから、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p115">After you create a new case, you can rename it anytime. Just click the name of the case on the **eDiscovery** page. On the **Manage this case** flyout page, change the name displayed in the box under **Name**, and then save the change.</span></span> 
  
## <a name="step-3-add-members-to-a-case"></a><span data-ttu-id="09d7d-173">手順 3: ケースにメンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="09d7d-173">Step 3: Add members to a case</span></span>

<span data-ttu-id="09d7d-p116">新しいケースを作成したら、次の手順はケースにメンバーを追加することです。前述のように、ケースのメンバーとして追加できるのは、レビュー担当者または電子情報開示マネージャー役割グループのメンバーであるユーザーだけです。なお、ケースを作成した電子情報開示マネージャーは自動的にメンバーとして追加されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p116">After you create a new case, the next step is to add members to the case. As previous explained, only users who are members of the Reviewer or eDiscovery Manager role groups can be added as members of the case. Note that the eDiscovery Manager who created the case is automatically added as a member.</span></span>
  
1. <span data-ttu-id="09d7d-177">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-177">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-178">メンバーを追加するケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-178">Click the name of the case that you want to add members to.</span></span>
    
    <span data-ttu-id="09d7d-179">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-179">The **Manage this case** flyout page is displayed.</span></span> 
    
    ![ケースの管理ポップアップ ページ](media/11f35ceb-6c98-4580-a3bc-ad688e9c7af9.png)
  
3. <span data-ttu-id="09d7d-181">[**メンバーの管理**] で、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) **追加**] をクリックして、ケースにメンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-181">Under **Manage members**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add** to add members to the case.</span></span> 
    
    <span data-ttu-id="09d7d-p117">ケースに役割グループを追加することもできます。[**役割グループの管理**] で、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p117">You can also choose to add a role group to the case. Under **Manage role groups**, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p118">役割グループで、電子情報開示ケースにメンバーを割り当てることができるユーザーが制御されます。つまり、ケースにはメンバーである役割グループのみを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p118">Role groups control who can assign members to an eDiscovery case. That means you can only assign the role groups that you are a member of to a case.</span></span>
    
4. <span data-ttu-id="09d7d-186">ケースのメンバーとして追加できるユーザーまたは役割グループのリストで、追加するユーザーまたは役割グループの名前の横にあるチェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-186">In the list of people or role groups that can be added as members of the case, click the check box next to the names of the people or role groups that you want to add.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="09d7d-187">メンバーとして追加できるユーザーが多数いる場合は、[**検索**] ボックスを使用してリストで特定のユーザーを検索します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-187">If you have a large list of people who can added as members, use the **Search** box to search for a specific person in the list.</span></span> 
  
5. <span data-ttu-id="09d7d-188">グループのメンバーとして追加するユーザーまたは役割グループを選択したら、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-188">After you've selected the people or role groups to add as members of the group, click **Add**.</span></span>
    
    <span data-ttu-id="09d7d-189">[**このケースを管理**] で、[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-189">In **Manage this case**, click **Save** to save the new list of case members.</span></span> 
    
6. <span data-ttu-id="09d7d-190">[**保存**] をクリックして、ケース メンバーの新しいリストを保存します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-190">Click **Save** to save the new list of case members.</span></span> 
  
## <a name="step-4-place-content-locations-on-hold"></a><span data-ttu-id="09d7d-191">手順 4: コンテンツの場所を保留にする</span><span class="sxs-lookup"><span data-stu-id="09d7d-191">Step 4: Place content locations on hold</span></span>

<span data-ttu-id="09d7d-p119">電子情報開示ケースを使用して、ケースに関連する可能性があるコンテンツを保持するための保留を作成できます。ケースのカストディアンであるユーザーのメールボックスと OneDrive for Business サイトを保留にできます。Office 365 グループのグループ メールボックス、SharePoint サイト、および OneDrive for Business サイトも保留にすることができます。同様に、Microsoft Teams と関連付けられているメッセージボックスとサイトを保留にすることができます。コンテンツの場所を保留にすると、コンテンツの場所の保留を解除するか、または保留を削除するまでコンテンツは保持されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p119">You can use an eDiscovery case to create holds to preserve content that might be relevant to the case. You can place a hold on the mailboxes and OneDrive for Business sites of people who are custodians in the case. You can also place a hold on the group mailbox, SharePoint site, and OneDrive for Business site for an Office 365 Group. Similarly, you can place a hold on the mailbox and site that are associated with Microsoft Teams. When you place content locations on hold, content is held until you remove the hold from the content location or until you delete the hold.</span></span>

> [!NOTE]
> <span data-ttu-id="09d7d-197">コンテンツの場所を保留にした後、保留が有効になるまで最大で 24 時間かかります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-197">After you place a content location on hold, it takes up to 24 hours for the hold to take effect.</span></span> 
>   
<span data-ttu-id="09d7d-198">保留リストを作成するときに、指定されたコンテンツの場所に保持されているコンテンツの範囲を指定する場合は、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-198">When you create a hold, you have the following options to scope the content that is held in the specified content locations:</span></span>
  
- <span data-ttu-id="09d7d-p120">すべてのコンテンツが保留にされている場合、無限の保留リストを作成します。また、検索クエリに一致したコンテンツのみが保留にされている場合、クエリ ベースの保留リストも作成できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p120">You create an infinite hold where all content is placed on hold. Alternatively, you can create a query-based hold where only content that matches a search query is placed on hold.</span></span>
    
- <span data-ttu-id="09d7d-p121">日付の範囲を指定して、その日付の範囲内に送信、受信、または作成したコンテンツのみを保留にすることができます。また、コンテンツがいつ送信、受信、作成されたかにかかわらず、すべてのコンテンツを保留にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p121">You can specify a date range to hold only the content that was sent, received, or created within that date range. Alternatively, you can hold all content regardless of when it was sent, received, or created.</span></span>
    
> [!NOTE]
> <span data-ttu-id="09d7d-203">組織内のすべての電子情報開示ケース全体で、最大 10,000 個のポリシーを保留にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-203">You can have a maximum of 10,000 hold policies across all eDiscovery cases in your organization.</span></span> 
  
<span data-ttu-id="09d7d-204">電子情報開示ケースの保留リストを作成するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-204">To create a hold for an eDiscovery case:</span></span>
  
1. <span data-ttu-id="09d7d-205">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-205">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-206">保留リストを作成するケースの横の [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-206">Click **Open** next to the case that you want to create the holds in.</span></span> 
    
3. <span data-ttu-id="09d7d-207">ケースの [**ホーム**] ページで、[**保留**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-207">On the **Home** page for the case, click the **Hold** tab.</span></span> 
    
    ![[保留] タブをクリックする](media/3fef2db4-36de-4517-a34d-82f47b82d9bf.png)
  
4. <span data-ttu-id="09d7d-209">[**保留**] ページで、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) **作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-209">On the **Hold** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Create**.</span></span>
    
5. <span data-ttu-id="09d7d-p122">[**保留リストの名前を設定**] ページで、保留リストに名前を付けます。保留リストの名前は組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p122">On the **Name your hold** page, give the hold a name. The name of the hold must be unique in your organization.</span></span> 
    
    ![保留リストに一意の名前を付ける](media/7e15ea63-abd1-4f14-a29c-7ecfb9571d2c.png)
  
6. <span data-ttu-id="09d7d-213">(省略可能) [\*\*説明 \*\*] ボックスで、保留リストの説明を追加します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-213">(Optional) In the **Description** box, add a description of the hold.</span></span> 
    
7. <span data-ttu-id="09d7d-214">[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-214">Click **Next**.</span></span>
    
8. <span data-ttu-id="09d7d-p123">保留にするコンテンツの場所を選択します。メールボックス、サイト、パブリック フォルダーを保留にできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p123">Choose the content locations that you want to place on hold. You can place mailboxes, sites, and public folders on hold.</span></span>
    
    ![保留にするコンテンツの場所を選択する](media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   <span data-ttu-id="09d7d-p124">a. **Exchange メール** - [**ユーザー、グループ、またはチームの選択**] をクリックし、もう一度 [**ユーザー、グループ、またはチームの選択**] をクリックして保留にするメールボックスを指定します。検索ボックスを使用して、保留にする (グループメンバーのメールボックスを保留にする) ユーザーのメールボックスと配布グループを検索します。Office 365 グループまたは Microsoft チームの関連付けられているメールボックスを保留にすることもできます。ユーザー、グループ、チームのチェック ボックスをオンにし、[**選択**]、[**完了**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p124">a. **Exchange email** - Click **Choose users, groups, or teams** and then click **Choose users, groups, or teams** again. to specify mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups (to place a hold on the mailboxes of group members) to place on hold. You can also place a hold on the associated mailbox for an Office 365 Group or a Microsoft Team. Select the user, group, team check box, click **Choose**, and then click **Done**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p125">[**ユーザー、グループ、またはチームの選択**] をクリックして保留にするメールボックスを指定するときに、表示されるメールボックス ピッカーは空の状態です。これは、パフォーマンスを向上させるための仕様です。このリストにユーザーを追加するには、検索ボックスに名前 (3 文字以上) を入力します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p125">When you click **Choose users, groups, or teams** to specify mailboxes to place on hold, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add people to this list, type a name (a minimum of 3 characters) in the search box.</span></span> 
  
   <span data-ttu-id="09d7d-p126">b. **SharePoint サイト** - [**サイトの選択**] をクリックし、もう一度 [**サイトの選択**] をクリックして保留にする SharePoint および OneDrive for Business サイトを指定します。保留にする各サイトの URL を入力します。Office 365 グループまたは Microsoft チーム用の SharePoint サイトの URL を追加することもできます。[**選択**]、[**完了**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p126">b. **SharePoint Sites** - Click **Choose sites** and then click **Choose sites** again to specify SharePoint and OneDrive for Business sites to place on hold. Type the URL for each site that you want to place on hold. You can also add the URL for the SharePoint site for an Office 365 Group or a Microsoft Team. Click **Choose**, and then click **Done**.</span></span>
    
    <span data-ttu-id="09d7d-232">Office 365 グループと Microsoft Teams を保留にする場合のヒントについては、「[詳細情報](#more-information)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-232">See the [More information](#more-information) section for tips on putting Office 365 Groups and Microsoft Teams on hold.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p127">ユーザーのユーザー プリンパル名 (UPN) が変更されるまれなケースでは、その OneDrive アカウントの URL も新しい UPN を組み込むために変更されます。このような場合は、ユーザーの新しい OneDrive URL を追加し、古いものを削除して、保留リストを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p127">In the rare case that a person's user principal name (UPN) is changed, the URL for their OneDrive account will also be changed to incorporate the new UPN. If this happens, you'll have to modify the hold by adding the user's new OneDrive URL and removing the old one.</span></span> 
  
   <span data-ttu-id="09d7d-p128">**Exchange パブリック フォルダー** - トグル スイッチ ![トグル コントロール](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)を [**すべて**] の位置に移動し、Exchange Online 組織内のパブリック フォルダーをすべて保留にします。保留にする特定のパブリック フォルダーは選択できないことに注意してください。パブリック フォルダーを保留にしない場合は、トグル スイッチを [**なし**] に設定したままにしておいてください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p128">c. **Exchange public folders** - Move the toggle switch ![Toggle control](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) to the **All** position to put all public folders in your Exchange Online organization on hold. Note that you can't choose specific public folders to put on hold. Leave the toggle switch set to **None** if you don't want to put a hold on public folders.</span></span>
    
9. <span data-ttu-id="09d7d-239">保留リストにコンテンツの場所を追加し終わったら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-239">When you're done adding content locations to the hold, click **Next**.</span></span>
    
10. <span data-ttu-id="09d7d-p129">条件付きのクエリ ベースの保留リストを作成するには、次の手順を行います。それ以外の場合は、[**次へ**] をクリックするだけです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p129">To create a query-based hold with conditions, complete the following. Otherwise, just click **Next**</span></span>
    
    ![条件付きのクエリ ベースの保留リストを作成する](media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    
       <span data-ttu-id="09d7d-p130">a. [**キーワード**] の下にあるボックスに、検索条件を満たすコンテンツのみが保留にされるように、検索クエリを入力します。キーワード、メッセージ プロパティ、またはファイル名などのドキュメント プロパティを指定することができます。**AND**、**OR**、または **NOT** などのブール演算子を使用する、より複雑なクエリを使用することもできます。キーワード ボックスを空のままにすると、指定されたコンテンツの場所にあるすべてのコンテンツが保留にされます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p130">a. In the box under **Keywords**, type a search query in the box so that only the content that meets the search criteria is placed on hold. You can specify keywords, message properties, or document properties, such as file names. You can also use more complex queries that use a Boolean operator, such as **AND**, **OR**, or **NOT**. If you leave the keyword box empty, then all content located in the specified content locations will be placed on hold.</span></span>
    
    <span data-ttu-id="09d7d-p131">b. [![追加アイコン](media/ITPro-EAC-AddIcon.gif) **条件の追加**] をクリックして、1 つまたは複数の条件を追加し、保留リストの検索クエリの条件を絞り込みます。保留リストの作成時に、作成され実行される KQL 検索クエリに、条件ごとの句が追加されます。たとえば、指定した日付の範囲内に作成されたメールまたはサイトのドキュメントが保留にされるように、日付の範囲を指定できます。条件は **AND** 演算子によってキーワード クエリ (キーワード ボックスで指定) に論理的に接続されます。つまり、アイテムは、キーワード クエリと保留にする条件の両方を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p131">b. Click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **Add conditions** to add one or more conditions to narrow the search query for the hold. Each condition adds a clause to the KQL search query that is created and run when you create the hold. For example you can specify a date range so that email or site documents that were created within the date ranged are placed on hold. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be placed on hold.</span></span>

    <span data-ttu-id="09d7d-254">検索クエリの作成と条件の使用の詳細については、「[コンテンツ検索のキーワード クエリと検索条件](keyword-queries-and-search-conditions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-254">For more information about creating a search query and using conditions, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
11. <span data-ttu-id="09d7d-255">クエリ ベースの保留リストを構成した後、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-255">After configuring a query-based hold, click **Next**.</span></span>
    
12. <span data-ttu-id="09d7d-256">設定を確認し、[**この保留リストを作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-256">Review your settings, and then click **Create this hold**.</span></span>
    
### <a name="hold-statistics"></a><span data-ttu-id="09d7d-257">保留アイテムの統計情報</span><span class="sxs-lookup"><span data-stu-id="09d7d-257">Hold statistics</span></span>

<span data-ttu-id="09d7d-p132">しばらくすると、選択した保留アイテムの詳細ウィンドウの [**保留リスト**] ページに、新しい保留アイテムに関する情報が表示されます。この情報には、保留中のメッセージボックスとサイトの数、保留にされたコンテンツに関する統計情報 (保留にされたアイテムの合計数とサイズ、保留アイテムの統計情報の最終計算時など) が含まれます。この保留アイテムの統計情報から、電子情報開示ケースに関連するコンテンツがどのくらい保留にされているかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p132">After a while, information about the new hold is displayed in the details pane on the **Holds** page for the selected hold. This information includes the number of mailboxes and sites on hold and statistics about the content that was placed on hold, such as the total number and size of items placed on hold and the last time the hold statistics were calculated. These hold statistics help you identify how much content that's related to the eDiscovery case is being held.</span></span> 
  
![保留アイテムの統計情報](media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
<span data-ttu-id="09d7d-262">保留アイテムの統計情報については、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-262">Keep the following things in mind about hold statistics:</span></span>
  
- <span data-ttu-id="09d7d-p133">保留にされているアイテムの合計数は、すべてのコンテンツ ソースのうち、保留にされているアイテム数を示します。クエリベースの保留リストを作成した場合、この統計情報は、クエリに一致するアイテム数を示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p133">The total number of items on hold indicates the number of items from all content sources that are placed on hold. If you've created a query-based hold, this statistic indicates the number of items that match the query.</span></span>
    
- <span data-ttu-id="09d7d-p134">保留にされているアイテム数には、コンテンツの場所で見つかった、インデックスのないアイテムも含まれます。クエリベースの保留リストを作成した場合、コンテンツの場所にあるインデックスのないすべてのアイテムは保留にされます。これには、クエリベースの保留リストの検索条件と一致しないインデックスのないアイテムと、日付範囲の条件から外れる可能性のあるインデックスのないアイテムが含まれます。これは、コンテンツ検索を実行したときの結果とは異なります。コンテンツ検索の場合、検索クエリと一致しないインデックスのないアイテム、または日付範囲の条件によって除外されるアイテムは、検索結果に含まれません。インデックスのないアイテムの詳細については、「[Office 365 のコンテンツ検索で部分的にインデックスが作成されたアイテム](partially-indexed-items-in-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p134">The number of items on hold also includes unindexed items found in the content locations. Note that if you create a query-based hold, all unindexed items in the content locations are placed on hold. This includes unindexed items that don't match the search criteria of a query-based hold and unindexed items that might fall outside of a date range condition. This is different than what happens when you run a Content Search, in which unindexed items that don't match the search query or are excluded by a date range condition aren't included in the search results. For more information about unindexed items, see [Partially indexed items in Content Search in Office 365](partially-indexed-items-in-content-search.md).</span></span>
    
- <span data-ttu-id="09d7d-p135">最新の保留アイテムの統計情報を取得するには、[**統計を更新**] をクリックし、現在保留にされているアイテム数を計算する検索見積もりを再実行します。必要に応じて、ツール バーの [**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックして、詳細ウィンドウの保留アイテムの統計情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p135">You can get the latest hold statistics by clicking **Update statistics** to re-run a search estimate that calculates the current number of items on hold. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) in the toolbar to update the hold statistics in the details pane.</span></span> 
    
- <span data-ttu-id="09d7d-272">通常、保留にされているアイテム数は時間と共に増えます。これは、メッセージ ボックスまたはサイトが保留にされているユーザーは、一般的に新しいメール メッセージを送受信し、新しい SharePoint および OneDrive for Business ドキュメントを作成するためです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-272">It's normal for the number of items on hold to increase over time because users whose mailbox or site is on hold are typically sending or receiving new email message and creating new SharePoint and OneDrive for Business documents.</span></span>
    
> [!NOTE]
> <span data-ttu-id="09d7d-p136">SharePoint サイトまたは OneDrive アカウントが複数地域環境内の別の領域に移動された場合、そのサイトの統計情報は保留アイテムの統計情報には含まれません。ただし、サイト内のコンテンツは引き続き保留にされます。また、サイトが別の領域に移動された場合、保留リストに表示される URL は更新されません。保留リストを編集し、URL を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p136">If a SharePoint site or OneDrive account is moved to a different region in a multi-geo environment, the statistics for that site won't be included in the hold statistics. However, the content in the site will still be on hold. Also, if a site is moved to a different region the URL that's displayed in the hold will not be updated. You'll have to edit the hold and update the URL.</span></span> 
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a><span data-ttu-id="09d7d-277">手順 5: ケースに関連付けられているコンテンツ検索を作成して実行する</span><span class="sxs-lookup"><span data-stu-id="09d7d-277">Step 5: Create and run a Content Search associated with a case</span></span>

<span data-ttu-id="09d7d-278">電子情報開示のケースを作成し、ケースに関連する管理者にホールドを適用したら、ケースに関連付けられた 1 つ以上のコンテンツ検索を作成して、実行できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-278">After an eDiscovery case is created and any custodians related to the case are placed on hold, you can create and run one or more Content Searches that are associated with the case.</span></span> <span data-ttu-id="09d7d-279">ケースに関連付けられているコンテンツ検索は、セキュリティ & コンプライアンスセンターの [**検索**] ページに表示されません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-279">Content Searches associated with a case aren't listed on the **Search** page in the Security & Compliance Center.</span></span> <span data-ttu-id="09d7d-280">つまり、ケースに関連付けられたコンテンツ検索は、電子情報開示マネージャー役割グループのメンバーを兼ねているケースのメンバーのみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-280">This means that Content Searches associated with a case can only be accessed by case members who are also members of the eDiscovery Manager role group.</span></span> 
  
1. <span data-ttu-id="09d7d-281">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-281">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-282">コンテンツ検索を作成するケースの横の [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-282">Click **Open** next to the case that you want to create a Content Search in.</span></span> 
    
3. <span data-ttu-id="09d7d-283">ケースの [**ホーム**] ページで、[**検索**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-283">On the **Home** page for the case, click the **Search** tab.</span></span> 
    
    ![[検索] タブ](media/2e15fe32-1a2e-4588-ad0b-5d96f77cece9.png)
  
4. <span data-ttu-id="09d7d-285">[**検索**] ページで、[![追加アイコン](media/ITPro-EAC-AddIcon.gif) **新しい検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-285">On the **Search** page, click ![Add Icon](media/ITPro-EAC-AddIcon.gif) **New search**.</span></span> 
    
5. <span data-ttu-id="09d7d-286">[**新しい検索**] ページで、キーワードと条件を追加して検索クエリを作成できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-286">On the **New search** page, you can add keywords and conditions to create the search query.</span></span> 
    
    ![新しい検索](media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
6. <span data-ttu-id="09d7d-p138">キーワード、メッセージのプロパティ (送信日、受信日など)、またはドキュメントのプロパティ (ファイル名、ドキュメントの最終変更日など) を指定できます。**AND**、**OR**、**NOT**、**NEAR**、**ONEAR** などのブール演算子を使用する、より複雑なクエリを使用できます。また、ドキュメント内の機密情報 (社会保障番号など) や、外部で共有されているドキュメントを検索することもできます。キーワード ボックスを空のままにすると、指定したコンテンツの場所にあるすべてのコンテンツが検索結果に含まれます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p138">You can specify keywords, message properties, such as sent and received dates, or document properties, such as file names or the date that a document was last changed. You can use more complex queries that use a Boolean operator, such as **AND**, **OR**, **NOT**, **NEAR**, or **ONEAR**. You can also search for sensitive information (such as social security numbers) in documents, or search for documents that have been shared externally. If you leave the keyword box empty, all content located in the specified content locations will be included in the search results.</span></span> 
    
7. <span data-ttu-id="09d7d-p139">[**キーワード リストの表示**] チェック ボックスをオンにして、各行にキーワードを入力することができます。この操作を行うと、各行のキーワードが、作成された検索クエリの **OR** 演算子で接続されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p139">You can click the **Show keyword list** check box and the type a keyword in each row. If you do this, the keywords on each row are connected by the **OR** operator in the search query that's created.</span></span> 
    
    ![キーワード リスト](media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    <span data-ttu-id="09d7d-p140">キーワード リストを使用するのはなぜですか。各キーワードと一致するアイテム数を示す統計情報を取得することができます。これは、最も有効な (および最も有効でない) キーワードをすばやく識別するのに役立ちます。行で (かっこで囲まれた) キーワード フレーズを使用することもできます。検索統計の詳細については、「[コンテンツ検索結果のキーワード統計の表示](view-keyword-statistics-for-content-search.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p140">Why use the keyword list? You can get statistics that show how many items match each keyword. This can help you quickly identify which keywords are the most (and least) effective. You can also use a keyword phrase (surrounded by parentheses) in a row. For more information about search statistics, see [View keyword statistics for Content Search results](view-keyword-statistics-for-content-search.md).</span></span>
    
    <span data-ttu-id="09d7d-300">キーワード リストの使用の詳細については、「[検索クエリを作成する](content-search.md#building-a-search-query)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-300">For more information about using the keywords list, see [Building a search query](content-search.md#building-a-search-query).</span></span>
    
8. <span data-ttu-id="09d7d-p141">[**条件**] で、検索クエリに条件を追加し、検索を絞り込み、より絞り込まれた結果セットが返されるようにします。各条件によって、句が KQL 検索クエリに追加されます。KQL 検索クエリは、検索の開始時に作成され、実行されます。条件は **AND** 演算子によってキーワード クエリ (キーワード ボックスで指定) に論理的に接続されます。つまり、アイテムは、キーワード クエリと、結果に含める条件の両方を満たす必要があります。このように、条件は結果を絞り込むのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p141">Under **Conditions**, add conditions to a search query to narrow a search and return a more refined set of results. Each condition adds a clause to the KQL search query that is created and run when you start the search. A condition is logically connected to the keyword query (specified in the keyword box) by the **AND** operator. That means that items have to satisfy both the keyword query and the condition to be included in the results. This is how conditions help to narrow your results.</span></span> 
    
    <span data-ttu-id="09d7d-306">検索クエリの作成と条件の使用の詳細については、[コンテンツ検索のキーワード クエリ](keyword-queries-and-search-conditions.md)に関するページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-306">For more information about creating a search query and using conditions, see [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).</span></span>
    
9. <span data-ttu-id="09d7d-p142">[**場所: 保留になっている場所**] で、検索するコンテンツの場所を選択します。同じ検索で、メールボックス、サイト、パブリック フォルダーを検索できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p142">Under **Locations: locations on hold**, choose the content locations that you want to search. You can search mailboxes, sites, and public folders in the same search.</span></span>
    
    ![場所、保留になっている場所](media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - <span data-ttu-id="09d7d-p143">**すべての場所** - 組織内のすべてのコンテンツの場所を検索するには、このオプションを選択します。このオプションを選択すると、すべての Exchange メールボックス (すべての Office 365 グループおよび Microsoft Teams のメールボックスを含む)、すべての SharePoint および OneDrive for Business サイト (すべての Office 365 グループおよび Microsoft Teams のサイトを含む)、およびすべてのパブリック フォルダーを検索することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p143">**All locations** - Select this option to search all content locations in your organization. When you select this option, you can choose to search all Exchange mailboxes (which includes the mailboxes for all Office 365 Groups and Microsoft Teams), all SharePoint and OneDrive for Business sites (which includes the sites for all Office 365 Groups and Microsoft Teams), and all public folders.</span></span>
    
    - <span data-ttu-id="09d7d-p144">**保留になっているすべての場所** - このケースで保留になっているすべてのコンテンツの場所を検索するには、このオプションを選択します。ケースに保留が複数ある場合にこのオプションを選択すると、すべての保留のコンテンツの場所が検索されます。また、コンテンツの場所がクエリによって保留となっている場合、この手順で作成するコンテンツ検索の実行では、保留中のアイテムのみが検索されます。たとえば、特定の日付前に送信または作成されたアイテムを保持するクエリを使用したケースの保留がある場合、コンテンツ検索のその検索基準を使用すると、このようなアイテムのみが検索されます。これは、ケースの保留クエリと、コンテンツ検索クエリを **AND** 演算子で接続して行われます。ケース コンテンツの検索の詳細については、この記事の最後の「[詳細情報](#more-information)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p144">**All locations on hold** - Select this option to search all the content locations that have been placed on hold in the case. If the case contains multiple holds, the content locations from all holds will be searched when you select this option. Additionally, if a content location was placed on a query-based hold, only the items that are on hold will be searched when you run the content search that you're creating in this step. For example, if a user was placed on query-based case hold that preserves items that were sent or created before a specific date, only those items would be searched by using the search criteria of the content search. This is accomplished by connecting the case hold query and the content search query by an **AND** operator. See the [More information](#more-information) section at the end of this article for more details about searching case content.</span></span> 
    
    - <span data-ttu-id="09d7d-p145">**特定の場所** - 検索するメールボックスとサイトを選択するには、このオプションを選択します。このオプションを選択し、[**変更**] をクリックすると、場所のリストが表示されます。ユーザー、グループ、チーム、サイトの場所のいずれかまたはすべてを検索するように選択できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p145">**Specific locations** - Select this option to select the mailboxes and sites that you want to search. When you select this option and click **Modify**, a list of locations appears. You can choose to search any or all users, groups, teams, or site locations.</span></span>
    
      ![特定の場所を選択する](media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
      <span data-ttu-id="09d7d-p146">組織内のすべてのパブリック フォルダーを検索するように選択することもできますが、このオプションを選択して、保留中の任意のコンテンツの場所を検索すると、検索クエリにはクエリを使用したケースが保留となっているケースは適用されません。つまり、クエリを使用したケースの保留によって保持されているコンテンツだけでなく、場所のすべてのコンテンツが検索されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p146">You can also choose to search all public folders in your organization, but if you select this option and search any content location that's on hold, any query from a query-based case hold won't be applied to the search query. In other words, all content in a location is searched, not just the content that is preserved by a query-based case hold.</span></span>
    
      <span data-ttu-id="09d7d-p147">事前に入力したケースのコンテンツの場所を削除するか、新しい場所を追加できます。このオプションを選択すると、特定のサービスのすべてのコンテンツの場所を検索 (すべての Exchange メールボックスを検索するなど) したり、サービスの特定のコンテンツの場所を検索したりすることができ、柔軟性が高まります。また、組織内のパブリック フォルダーを検索するかどうかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p147">You can remove the pre-populated case content locations or add new ones. If you choose this option, you also have flexibility to search all content locations for a specific service (such as searching all Exchange mailboxes) or you can search specific content locations for a service. You can also choose whether or not to search the public folders in your organization.</span></span>
    
      <span data-ttu-id="09d7d-327">検索するコンテンツの場所を追加する場合は、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-327">Keep these things in mind when adding content locations to search:</span></span>
    
      - <span data-ttu-id="09d7d-p148">[**ユーザー、グループ、またはチームの選択**] をクリックして検索するメールボックスを指定するときに、表示されるメールボックス ピッカーは空の状態です。これは、パフォーマンスを向上させるための仕様です。このリストに受信者を追加するには、[**ユーザー、グループ、またはチームの選択**] をクリックし、検索ボックスに名前 (3 文字以上) を入力して、名前の横にあるチェック ボックスをオンにしてから [**選択**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p148">When you click **Choose users, groups, or teams** to specify mailboxes to search, the mailbox picker that's displayed is empty. This is by design to enhance performance. To add recipients to this list, click **Choose users, groups, or teams**, type a name (a minimum of 3 characters) in the search box, select the check box next to the name, and then click **Choose**.</span></span> 
    
      - <span data-ttu-id="09d7d-p149">非アクティブのメールボックス、Office 365 グループ、Microsoft Teams、および配布グループを検索するメールボックスのリストに追加できます。動的配布グループはサポートされません。Office 365 グループまたは Microsoft Teams を追加すると、グループまたはチームのメールボックスが検索されます。グループ メンバーのメールボックスは検索されません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p149">You can add inactive mailboxes, Office 365 Groups, Microsoft Teams, and distribution groups to the list of mailboxes to search. Dynamic distribution groups aren't supported. If you add Office 365 Groups or Microsoft Teams, the group or team mailbox is searched; the mailboxes of the group members aren't searched.</span></span>
    
      - <span data-ttu-id="09d7d-p150">サイトを追加するには、[**サイトの選択**] をクリックし、もう一度 [**サイトの選択**] をクリックしてから、検索する各サイトの URL を入力します。Office 365 グループと Microsoft Teams の SharePoint サイトの URL も追加できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p150">To add sites click **Choose sites**, click **Choose sites** again, and then type the URL for each site that you want to search. You can also add the URL for the SharePoint site for Office 365 Groups and Microsoft Teams.</span></span> 
    
10. <span data-ttu-id="09d7d-336">検索するコンテンツの場所を選択したら、[**完了**]、[**次へ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-336">After you select the content locations to search, click **Done** and then click **Save**.</span></span>
    
11. <span data-ttu-id="09d7d-p151">[**新しい検索**] ページで、[**保存**] をクリックしてから、検索の名前を入力します。ケースに関連付けられたコンテンツ検索の名前は、Office 365 組織内で一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p151">On the **New search** page, click **Save** and then type a name for the search. Content Searches associated with a case must have names that are unique within your Office 365 organization.</span></span> 
    
12. <span data-ttu-id="09d7d-339">[**保存して実行**] をクリックして、検索設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-339">Click **Save &amp; run** to save the search settings.</span></span> 
    
13. <span data-ttu-id="09d7d-340">検索の一意の名前を入力し、[**保存**] をクリックして検索を開始します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-340">Enter a unique name for the search, and click **Save** to start the search.</span></span> 
    
    <span data-ttu-id="09d7d-p152">検索が始まります。しばらくすると、検索結果の見積もりが詳細ウィンドウに表示されます。見積もりには、検索条件と一致したアイテムの合計サイズと数が含まれます。また、検索見積もりには、検索されたコンテンツの場所にあるインデックスのないアイテム数も含まれます。検索条件を満たさないインデックスなしアイテムの数は、詳細ウィンドウに表示される検索の統計情報に含まれます。(他のメッセージまたはドキュメントのプロパティが検索条件と一致するため) インデックスなしアイテムが検索クエリと一致する場合、インデックスなしアイテムの見積もり数には含まれません。検索条件によってインデックスのないアイテムが除外される場合、インデックスのないアイテムの見積もりにも含まれません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p152">The search begins. After a while, an estimate of the search results is displayed in the details pane. The estimate includes the total size and number of items that matched the search criteria. The search estimate also includes the number of unindexed items in the content locations that were searched. The number of unindexed items that don't meet the search criteria will be included in the search statistics displayed in the details pane. If an unindexed item matches the search query (because other message or document properties meet the search criteria), it won't be included in the estimated number of unindexed items. If an unindexed item is excluded by the search criteria, it also won't be included in the estimate of unindexed items.</span></span>
    
  <span data-ttu-id="09d7d-p153">検索が完了した後、検索結果をプレビューすることができます。必要に応じて、[**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックして詳細ウィンドウの情報を更新します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p153">After the search is completed, you can preview the search results. If necessary, click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the information in the details pane.</span></span> 
    
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a><span data-ttu-id="09d7d-350">手順 6: ケースに関連付けられているコンテンツ検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="09d7d-350">Step 6: Export the results of a Content Search associated with a case</span></span>

<span data-ttu-id="09d7d-p154">検索の実行が成功したら、検索結果をエクスポートできます。検索結果をエクスポートすると、メールボックス アイテムが PST ファイルまたは個々のメッセージとしてでダウンロードされます。SharePoint サイトと OneDrive for Business サイトからコンテンツをエクスポートすると、ネイティブ Office ドキュメントとその他のドキュメントのコピーがエクスポートされます。各検索結果に関する情報を含むマニフェスト ファイル (XML 形式) もエクスポートされます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p154">After a search is successfully run, you can export the search results. When you export search results, mailbox items are downloaded in PST files or as individual messages. When you export content from SharePoint and OneDrive for Business sites, copies of native Office documents and other documents are exported. A manifest file (in XML format) that contains information about every search result is also exported.</span></span>
  
<span data-ttu-id="09d7d-355">[ケースに関連付けられている 1 つの検索](#export-the-results-of-a-single-search-associated-with-a-case)の結果をエクスポートすることも、[ケースに関連付けられている複数の検索](#export-the-results-of-multiple-searches-associated-with-a-case)の結果をエクスポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-355">You can export the results of a [single search associated with a case](#export-the-results-of-a-single-search-associated-with-a-case) or you can export the results of [multiple searches associated with a case](#export-the-results-of-multiple-searches-associated-with-a-case).</span></span>
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a><span data-ttu-id="09d7d-356">ケースに関連付けられている 1 つの検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="09d7d-356">Export the results of a single search associated with a case</span></span>

1. <span data-ttu-id="09d7d-357">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-357">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-358">検索をエクスポートするケースの横の [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-358">Click **Open** next to the case that you want to export search from.</span></span> 
    
3. <span data-ttu-id="09d7d-359">ケースの [**ホーム**] ページで [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-359">On the **Home** page for the case, click **Search**.</span></span>
    
4. <span data-ttu-id="09d7d-360">ケースの検索の一覧で、検索結果をエクスポートする検索をクリックし、![検索結果のエクスポート アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) [**詳細**] をクリックしてから、ドロップダウン リストから [**結果のエクスポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-360">In the list of searches for the case, click the search that you want to export search results from, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then select **Export results** from the drop-down list.</span></span> 
    
    <span data-ttu-id="09d7d-361">[**結果のエクスポート**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-361">The **Export results** page is displayed.</span></span> 
    
    ![[結果のエクスポート] ページ](media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    <span data-ttu-id="09d7d-363">ケースに関連付けられているコンテンツの検索の結果をエクスポートするワークフローは、**[コンテンツの検索]** ページで検索の検索結果をエクスポートする場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-363">The workflow to export the results from a Content Search associated with a case is that same as exporting the search results for a search on the **Content search** page.</span></span> <span data-ttu-id="09d7d-364">詳細な手順については、「[コンテンツ検索の結果をエクスポート](export-search-results.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-364">For step-by-step instructions, see [Export Content Search results](export-search-results.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p156">検索されたメールボックスで同じメール メッセージの複数のインスタンスが検出された可能性がある場合でも、検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p156">When you export search results, you have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span> 
  
5. <span data-ttu-id="09d7d-367">[**エクスポート**] タブをクリックすると、そのケースに対して存在するエクスポート ジョブのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-367">Click the **Export** tab to display the list of export jobs that exist for that case.</span></span> 
    
    ![[エクスポート] タブ](media/1b84c45e-4ec9-4ecd-9e07-eaf8fc4cc307.png)
  
    <span data-ttu-id="09d7d-p157">先ほど作成したエクスポート ジョブが表示されるようにするには、[**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックして、エクスポート ジョブのリストを更新することが必要な場合があります。なお、エクスポート ジョブの名前は、対応するコンテンツ検索の名前の末尾に **_Export** が付加されたものとなります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p157">You might have to click **Refresh**![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list of export jobs so that it shows the export job that you just created. Note that export jobs have the same name as the corresponding Content Search with **_Export** appended to the end of search name.</span></span> 
    
6. <span data-ttu-id="09d7d-p158">先ほど作成したエクスポート ジョブをクリックすると、詳細ウィンドウに状態の情報が表示されます。この情報には、Microsoft クラウド内の Azure ストレージ領域に転送されたアイテムの割合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p158">Click the export job that you just created to display status information in the details pane. This information includes the percentage of items that have been transferred to an Azure storage area in the Microsoft cloud.</span></span>
    
    <span data-ttu-id="09d7d-373">すべてのアイテムが転送されたら、[**結果のダウンロード**] をクリックして、検索結果をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-373">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="09d7d-374">詳細については、「[コンテンツ検索の結果をエクスポート](export-search-results.md)する」のステップ2を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-374">For more information, see Step 2 in [Export Content Search results](export-search-results.md)</span></span>
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a><span data-ttu-id="09d7d-375">ケースに関連付けられている複数の検索の結果をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="09d7d-375">Export the results of multiple searches associated with a case</span></span>

<span data-ttu-id="09d7d-p160">ケースに関連付けられている 1 つのコンテンツ検索の結果をエクスポートする代わりに、同じケースの複数の検索の結果を一度にエクスポートすることもできます。1 つずつ検索の結果をエクスポートするより、複数の検索の結果をまとめてエクスポートする方が時間がかからず簡単です。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p160">As an alternative to exporting the results of a single Content Search associated with a case, you can export the results of multiple searches from the same case in a single export. Exporting the results of multiple searches is faster and easier than exporting the results one search at a time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d7d-378">すべての検索結果を検索するように構成されている場合は、複数の検索の結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-378">You can't export the results of multiple searches if one of those searches was configured to search all case content.</span></span> <span data-ttu-id="09d7d-379">電子情報開示ケースに関連付けられている検索の複数の検索結果のみをエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-379">only export the results of multiple searches for searches that are associated with an eDiscovery case.</span></span> <span data-ttu-id="09d7d-380">セキュリティ & コンプライアンスセンターの [**コンテンツ検索**] ページに、複数の検索の結果をエクスポートすることはできません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-380">You can't export the results of multiple searches listed on the **Content search** page in the Security & Compliance Center.</span></span> 
  
1. <span data-ttu-id="09d7d-381">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-381">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-382">検索結果をエクスポートするケースの横の [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-382">Click **Open** next to the case that you want to export search results from.</span></span> 
    
3. <span data-ttu-id="09d7d-383">ケースの [**ホーム**] ページで [**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-383">On the **Home** page for the case, click **Search**.</span></span>
    
4. <span data-ttu-id="09d7d-384">ケースの検索のリストで、検索結果をエクスポートする複数の検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-384">In the list of searches for the case, select two or more searches that you want to export search results from.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p162">複数の検索を選択するには、Ctrl キーを押しながら各検索をクリックします。または、最初の検索をクリックし、Shift キーを押したまま最後の検索をクリックすることで、連続する複数の検索をまとめて選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p162">To select multiple searches, press Ctrl as you click each search. Or you can select multiple adjacent searches by clicking the first search, holding down the Shift key, and then clicking the last search.</span></span> 
  
5. <span data-ttu-id="09d7d-387">検索を選択した後、[**一括操作**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-387">After you select the searches, the **Bulk actions** page appears.</span></span> 
    
    ![[一括操作] ページで、[結果のエクスポート] をクリックする](media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
    
6. <span data-ttu-id="09d7d-389">![検索結果のエクスポート アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) [**結果のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-389">Click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Export results**.</span></span>

7. <span data-ttu-id="09d7d-p163">[**結果のエクスポート**] ページで、エクスポートに一意の名前を付け、出力オプションを選択し、コンテンツのエクスポート方法を選択します。[**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p163">On the **Export results** page, give the export a unique name, select output options, and choose how your content will be exported. Click **Export**.</span></span>
    
    <span data-ttu-id="09d7d-392">ケースに関連付けられている複数のコンテンツ検索から結果をエクスポートするワークフローは、単一の検索の検索結果をエクスポートする場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-392">The workflow to export the results from multiple content searches associated with a case is the same as exporting the search results for a single search.</span></span> <span data-ttu-id="09d7d-393">詳細な手順については、「[コンテンツ検索の結果をエクスポート](export-search-results.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-393">For step-by-step instructions, see [Export Content Search results](export-search-results.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p165">1 つ以上の検索で検索されたメールボックスで同じメッセージの複数のインスタンスが検出された可能性がある場合でも、ケースに関連付けられている複数の検索から検索結果をエクスポートするときに、メール メッセージの 1 つのコピーのみがエクスポートされるようにする重複除去オプションを有効にすることもできます。重複除去および重複したアイテムの特定方法の詳細については、「[電子情報開示検索結果での重複除去](de-duplication-in-ediscovery-search-results.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p165">When you export search results from multiple searches associated with a case, you also have the option to enable de-duplication so that only one copy of an email message is exported even though multiple instances of the same message might have been found in the mailboxes that were searched in one or more of the searches. For more information about de-duplication and how duplicate items are identified, see [De-duplication in eDiscovery search results](de-duplication-in-ediscovery-search-results.md).</span></span> 
  
8. <span data-ttu-id="09d7d-396">エクスポートの開始後、[**エクスポート**] タブをクリックすると、そのケースのエクスポート ジョブのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-396">After you start the export, click the **Export** tab to display the list of export jobs for that case.</span></span> 
    
    ![[エクスポート] タブ、複数の検索](media/b9505e1b-559f-4a8c-96b3-a3f734753926.png)
  
    <span data-ttu-id="09d7d-p166">先ほど作成したエクスポート ジョブを表示するには、[**更新**] ![更新アイコン](media/O365-MDM-Policy-RefreshIcon.gif) をクリックして、エクスポート ジョブを更新することが必要な場合があります。エクスポート ジョブに含まれる検索が [**検索**] 列にリストされることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p166">You might have to click **Refresh** ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) to update the list of export jobs to display the export job that you just created. Note that the searches that were included in the export job are listed in the **Searches** column.</span></span> 
    
8. <span data-ttu-id="09d7d-p167">先ほど作成したエクスポート ジョブをクリックすると、詳細ウィンドウに状態の情報が表示されます。この情報には、Microsoft クラウド内の Azure ストレージ領域に転送されたアイテムの割合が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p167">Click the export job that you just created to display status information in the details pane. This information includes the percentage of items that have been transferred to an Azure storage area in the Microsoft cloud.</span></span>
    
9. <span data-ttu-id="09d7d-402">すべてのアイテムが転送されたら、[**結果のダウンロード**] をクリックして、検索結果をローカルコンピューターにダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-402">After all items have been transferred, click **Download results** to download the search results to your local computer.</span></span> <span data-ttu-id="09d7d-403">詳細については、「[コンテンツ検索結果をエクスポート](export-search-results.md)する」のステップ2を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-403">For more information, see Step 2 in [Export Content Search results](export-search-results.md).</span></span>
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a><span data-ttu-id="09d7d-404">複数の検索の結果のエクスポートに関するその他の情報</span><span class="sxs-lookup"><span data-stu-id="09d7d-404">More information about exporting the results of multiple searches</span></span>

- <span data-ttu-id="09d7d-p169">複数の検索の結果をエクスポートするときは、すべての検索の検索クエリを **OR** 演算子を使用して組み合わせた後、組み合わされた検索が開始されます。組み合わされた検索の予想される結果が、選択したエクスポート ジョブの詳細ウィンドウに表示されます。検索結果は、Microsoft クラウドの Azure ストレージ領域に転送されます。転送のステータスも、詳細ウィンドウに表示されます。前述のとおり、すべての検索結果が転送された後、それらをローカル コンピューターにダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p169">When you export the results of multiple searches, the search queries from all the searches are combined by using **OR** operators, and then the combined search is started. The estimated results of the combined search are displayed in the details pane of the selected export job. The search results are then transferred to the Azure storage area in the Microsoft cloud. The status of the transfer is also displayed in the details pane. As previously stated, after all the search results have been transferred, you can download them to your local computer.</span></span> 
    
- <span data-ttu-id="09d7d-p170">エクスポートするすべての検索の検索クエリのキーワードの最大数は 500 です (これは、1 つのコンテンツ検索の上限と同じです)。これは、エクスポート ジョブで **OR** 演算子を使用して、すべての検索クエリが組み合わされるためです。この上限を超えた場合は、エラーが返されます。その場合は、結果をエクスポートする検索の数を減らすか、またはエクスポートする検索の検索クエリを簡略化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p170">The maximum number of keywords from the search queries for all searches that you want to export is 500. (this is the same limit for a single Content Search). That's because the export job combines all the search queries by using the **OR** operator. If you exceed this limit, an error will be returned. In this case, you'll have to export the results from fewer searches or simplify the search queries of the searches that you want to export.</span></span> 
    
- <span data-ttu-id="09d7d-p171">エクスポートされる検索結果は、アイテムが見つかったコンテンツ ソースごとにまとめられています。つまり、エクスポート結果のコンテンツ ソースのアイテムが異なる検索で返される可能性があります。たとえば、メールボックスごとに 1 つの PST ファイルにメール メッセージをエクスポートする場合、PST ファイルに複数の検索の結果が含まれることがあります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p171">The search results that are exported are organized by the content source the item was found in. That means a content source in the export results might have items returned by different searches. For example, if you chose to export email messages in one PST file for each mailbox, the PST file might have results from multiple searches.</span></span>
    
- <span data-ttu-id="09d7d-418">同じコンテンツの場所の同じメール アイテムまたはドキュメントが、エクスポートする複数の検索によって返される場合、アイテムの 1 つのコピーだけがエクスポートされます。 </span><span class="sxs-lookup"><span data-stu-id="09d7d-418">If the same email item or document from the same content location is returned by more than one of the searches that you export, only one copy of the item will be exported.</span></span>
    
- <span data-ttu-id="09d7d-p172">作成した後で複数の検索のエクスポートを編集することはできません。たとえば、エクスポートの検索を追加または削除することはできません。エクスポートされる検索結果を変更するには、新しいエクスポート ジョブを作成する必要があります。エクスポート ジョブを作成した後で行うことができるのは、コンピューターへの結果のダウンロード、エクスポートの再実行、またはエクスポート ジョブの削除だけです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p172">You can't edit an export for multiple searches after you create it. For example, you can't add or remove searches from the export. You'll have to create a new export job to change which search results are exported. After a export job is created, you only can download the results to a computer, restart the export, or delete the export job.</span></span>
    
- <span data-ttu-id="09d7d-p173">エクスポートを再実行した場合、エクスポート ジョブを構成する検索のクエリに対する変更は、取得される検索結果に影響しません。エクスポートを再実行すると、エクスポート ジョブを作成したときと同じ組み合わせの検索クエリ ジョブが再び実行されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p173">If you restart the export, any changes to the queries of the searches that make up the export job won't affect the search results that will be retrieved. When you restart an export, the same combined search query job that was run when the export job was created will be run again.</span></span>
    
- <span data-ttu-id="09d7d-425">電子情報開示ケースの [**エクスポート**] ページからエクスポートを再実行した場合、Azure ストレージ領域に転送される検索結果で以前の結果が上書きされます。転送された以前の結果はダウンロードできなくなります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-425">If you restart an export from the **Exports** page in an eDiscovery case, the search results that are transferred to the Azure storage area will overwrite the previous results; the previous results there were transferred won't be available to be downloaded.</span></span> 
    
- <span data-ttu-id="09d7d-p174">Advanced eDiscovery での分析に対して複数の検索結果を準備することはできません。Advanced eDiscovery での分析に対して結果を準備できる検索は 1 つだけです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p174">Preparing the results of multiple searches for analysis in Advanced eDiscovery isn't available. You can only prepare the results of a single search for analysis in Advanced eDiscovery.</span></span>

## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a><span data-ttu-id="09d7d-428">手順 7: Advanced eDiscovery 用に検索結果を準備する</span><span class="sxs-lookup"><span data-stu-id="09d7d-428">Step 7: Prepare search results for Advanced eDiscovery</span></span>

<span data-ttu-id="09d7d-p175">組織に Office 365 E5 サブスクリプションがある場合、ケースに関連するコンテンツ検索の結果を Advanced eDiscovery で分析する準備ができます。検索結果を準備したら、Advanced eDiscovery に移動し (「[手順 8: Advanced eDiscovery のケースに移動する](#step-8-go-to-the-case-in-advanced-ediscovery)」を参照)、検索結果のデータを Advanced eDiscovery でさらに分析することができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p175">If your organization has an Office 365 E5 subscription, you can prepare the results of Content Searches associated with a case for analysis in Advanced eDiscovery. After you prepare search results, you can go to Advanced eDiscovery (see [Step 8: Go to the case in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)) and process the search result data for further analysis in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="09d7d-p176">Advanced eDiscovery の検索結果を準備すると、光学式文字認識 (OCR) 機能によって、画像からテキストが自動的に抽出されます。OCR は、圧縮されていないファイル、メールの添付ファイル、および埋め込み画像の場合にサポートされています。画像ファイルの任意のテキストに Advanced eDiscovery のテキスト分析機能 (類似データ、メールのスレッド化、テーマ、プレディクティブ コーディング) を適用できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p176">When you prepare search results for Advanced eDiscovery, optical character recognition (OCR) functionality automatically extracts text from images. OCR is supported for loose files, email attachments, and embedded images. This allows you to apply the text analytic capabilities of Advanced eDiscovery (near-duplicates, email threading, themes, and predictive coding) to any text in image files.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09d7d-p177">Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office365 E5 ライセンスが割り当てられている必要があります。または、Office365 E1 または E3 ライセンスを持つユーザーに Advanced eDiscovery 単体のライセンスを割り当てることもできます。ケースに割り当てられ、Advanced eDiscovery を使用してデータを分析する管理者および法令遵守責任者には E5 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p177">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
  
1. <span data-ttu-id="09d7d-437">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-437">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-438">Advanced eDiscovery で分析するために、検索結果を準備するケースの横の [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-438">Click **Open** next to the case that you want to prepare search results for analysis in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="09d7d-439">ケースの [**ホーム**] ページで [**検索**] をクリックして、検索を選択します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-439">On the **Home** page for the case, click **Search**, and then select the search.</span></span>
    
4. <span data-ttu-id="09d7d-440">詳細ウィンドウで、![検索結果のエクスポート アイコン](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) [**詳細**] をクリックしてから、[**Advanced eDiscovery に対する準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-440">In the details pane, click ![Export search results icon](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **More**, and then click **Prepare for Advanced eDiscovery**.</span></span>
    
    ![Advanced eDiscovery 用に結果を準備する](media/b6548ff0-a6e9-42b1-9ae4-5c15146f5690.png)
  
5. <span data-ttu-id="09d7d-442">[**Advanced eDiscovery に対する準備**] ページで、以下のいずれかを準備するように選択します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-442">On the **Prepare for Advanced eDiscovery** page, choose to prepare one of the following:</span></span> 
    
    - <span data-ttu-id="09d7d-443">形式が認識されていないものを除く、暗号化されている、または他の理由でインデックスが作成されなかったすべてのアイテム。</span><span class="sxs-lookup"><span data-stu-id="09d7d-443">All items, excluding those with unrecognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="09d7d-444">形式が認識されていないものを含む、暗号化されている、または他の理由でインデックスが作成されなかったすべてのアイテム。</span><span class="sxs-lookup"><span data-stu-id="09d7d-444">All items, including those that have unrecognized format, are encrypted, or weren't indexed for other reasons.</span></span>
    
    - <span data-ttu-id="09d7d-445">形式が認識できない、暗号化されている、または他の理由でインデックスが作成されなかったアイテムのみ。</span><span class="sxs-lookup"><span data-stu-id="09d7d-445">Only items that have an unrecognizable format, are encrypted, or weren't indexed for other reasons.</span></span>
    
6. <span data-ttu-id="09d7d-446">(省略可能) [**SharePoint ファイルのバージョンを含めます**] チェック ボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-446">(Optional) Click the **Include versions for SharePoint files** check box.</span></span> 
    
7. <span data-ttu-id="09d7d-447">[**準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-447">Click **Prepare**.</span></span>
    
    <span data-ttu-id="09d7d-448">検索結果が、Advanced eDiscovery を使用して分析するために準備されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-448">The search results are prepared for analysis with Advanced eDiscovery.</span></span>
    
8. <span data-ttu-id="09d7d-449">[**閉じる**] をクリックして、詳細ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-449">Click **Close** to close the details pane.</span></span> 
    
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a><span data-ttu-id="09d7d-450">手順 8: Advanced eDiscovery のケースに移動する</span><span class="sxs-lookup"><span data-stu-id="09d7d-450">Step 8: Go to the case in Advanced eDiscovery</span></span>

<span data-ttu-id="09d7d-451">セキュリティ & コンプライアンスセンターでケースを作成した後は、「Advanced eDiscovery」の同じケースに進むことができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-451">After you create a case in the Security & Compliance Center, you can go to the same case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="09d7d-452">Advanced eDiscovery のケースに移動するには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-452">To go to a case in Advanced eDiscovery:</span></span>
  
1. <span data-ttu-id="09d7d-453">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-453">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-454">Advanced eDiscovery の移動するケースの横の [**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-454">Click **Open** next to the case that you want to go to in Advanced eDiscovery.</span></span> 
    
3. <span data-ttu-id="09d7d-455">ケースの [**ホーム**] ページで、[**Advanced eDiscovery に切り替え**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-455">On the **Home** page for the case, click **Switch to Advanced eDiscovery**.</span></span>
    
    ![[Advanced eDiscovery に切り替え] を選択する](media/d7e31558-e79c-4782-b841-2b735568a576.png)
  
    <span data-ttu-id="09d7d-p178">[**Advanced eDiscovery に接続しています**] の進行状況バーが表示されます。Advanced eDiscovery に接続されると、ページにコンテナーのリストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p178">The **Connecting to Advanced eDiscovery** progress bar is displayed. When you're connected to Advanced eDiscovery, a list of containers is displayed on the page.</span></span> 
    
    ![Advanced eDiscorvery の進行状況バー](media/4a84273d-765b-44b8-9006-c20e810ea393.png)
  
    <span data-ttu-id="09d7d-460">これらのコンテナーは、手順7で高度な電子情報開示で分析するために準備した検索結果を表します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-460">These containers represent the search results that you prepared for analysis in Advanced eDiscovery in Step 7.</span></span> <span data-ttu-id="09d7d-461">セキュリティ & コンプライアンスセンターの場合、コンテナーの名前はコンテンツ検索と同じ名前になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-461">Note that the name of the container has the same name as Content Search in the case in the Security & Compliance Center.</span></span> <span data-ttu-id="09d7d-462">リスト内のコンテナーは、準備したものです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-462">The containers in the list are the ones that you prepared.</span></span> <span data-ttu-id="09d7d-463">上級電子情報開示のために別のユーザーが検索結果を準備している場合、対応するコンテナーはリストに含まれません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-463">If a different user prepared search results for Advanced eDiscovery, the corresponding containers won't be included in the list.</span></span>
    
4. <span data-ttu-id="09d7d-464">コンテナーから Advanced eDiscovery のケースに検索結果データを読み込むには、コンテナーを選択し、[**プロセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-464">To load the search result data from a container to the case in Advanced eDiscovery, select a container and click **Process**.</span></span>
    
    <span data-ttu-id="09d7d-465">コンテナーの処理方法については、「[Office 365 Advanced eDiscovery でプロセス モジュールを実行し、データを読み込む](run-the-process-module-and-load-data-in-advanced-ediscovery.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-465">For information about how to process containers, see [Run the Process module and load data in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).</span></span>
    
> [!TIP]
> <span data-ttu-id="09d7d-466">セキュリティ & コンプライアンスセンターの同じケースに戻るには、[**電子情報開示に切り替え**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-466">Click **Switch to eDiscovery** to go back to the same case in the Security & Compliance Center.</span></span> 
  
## <a name="optional-step-9-close-a-case"></a><span data-ttu-id="09d7d-467">(省略可能) 手順 9: ケースを閉じる</span><span class="sxs-lookup"><span data-stu-id="09d7d-467">(Optional) Step 9: Close a case</span></span>

<span data-ttu-id="09d7d-p180">電子情報開示ケースでサポートされる訴訟や捜査が完了したら、ケースを閉じることができます。ケースを閉じたときの動作を示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p180">When the legal case or investigation supported by an eDiscovery case is completed, you can close the case. Here's what happens when you close a case:</span></span>
  
- <span data-ttu-id="09d7d-p181">ケースに保留中の任意のコンテンツの場所が含まれている場合、これらの保留が無効になります。この結果、ユーザーまたは自動プロセス (削除ポリシーなど) によってコンテンツが完全に削除または消去される場合があります。  </span><span class="sxs-lookup"><span data-stu-id="09d7d-p181">If the case contains any content locations on hold, those holds will be turned off. This might result in content being permanently deleted or purged, either by the user or by an automated process, such as a deletion policy.</span></span>
    
- <span data-ttu-id="09d7d-p182">ケースを閉じると、そのケースに関連付けられている保留だけが無効になります。コンテンツの場所に他の保留 (訴訟ホールド、保持ポリシー、別の電子情報開示ケースからの保留など) がある場合、これらの保留はそのまま保持されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p182">Closing a case only turns off the holds that are associated with that case. If other holds are place on a content location (such as a Litigation Hold. a Preservation Policy, or a hold from a different eDiscovery case) those holds will still be maintained.</span></span>
    
- <span data-ttu-id="09d7d-475">ケースは、セキュリティ & コンプライアンスセンターの [電子情報開示] ページに表示されたままです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-475">The case is still listed on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="09d7d-476">クローズしたケースの詳細、保持、検索、メンバーは保持されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-476">The details, holds, searches, and members of a closed case are retained.</span></span>
    
- <span data-ttu-id="09d7d-p184">ケースは閉じた後でも編集できます。たとえば、メンバーの追加または削除、検索の作成、検索結果のエクスポート、Advanced eDiscovery で分析するための検索結果の準備が行えます。アクティブ ケースと閉じたケースの主な違いは、ケースを閉じると保留が無効になることです。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p184">You can edit a case after it's closed. For example, you can add or removing members, create searches, export search results, and prepare search result for analysis in Advanced eDiscovery. The primary difference between active and closed cases is that holds are turned off when a case is closed.</span></span>
    
<span data-ttu-id="09d7d-480">ケースを閉じるには、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-480">To close a case:</span></span>
  
1. <span data-ttu-id="09d7d-481">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-481">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-482">閉じるケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-482">Click the name of the case that you want to close.</span></span>
    
    <span data-ttu-id="09d7d-483">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-483">The **Manage this case** flyout page is displayed.</span></span> 
    
3. <span data-ttu-id="09d7d-484">[**ケースの状態の管理**] で、![[プレビューの固定を解除] ボタン](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) [**ケースの終了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-484">Under **Manage case status**, click ![Remove the peek button](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) **Close case**.</span></span>
    
    <span data-ttu-id="09d7d-485">ケースに関連付けられた保留が無効になることを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-485">A warning is displayed saying that the holds associated with the case will be turned off.</span></span>
    
4. <span data-ttu-id="09d7d-486">[**はい**] をクリックしてケースを閉じます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-486">Click **Yes** to close the case.</span></span> 
    
    <span data-ttu-id="09d7d-487">[**このケースを管理**] ポップアップ ページの状態が [**アクティブ**] から [**閉じています**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-487">The status on the **Manage this case** flyout page is changed from **Active** to **Closing**.</span></span>
    
5. <span data-ttu-id="09d7d-488">[**このケースを管理**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-488">Close the **Manage this case** page.</span></span> 
    
6. <span data-ttu-id="09d7d-p185">[**電子情報開示**] ページで、![[更新] アイコン](media/O365-MDM-Policy-RefreshIcon.gif) [**更新**] をクリックして、閉じたケースの状態を更新します。閉じるプロセスが完了するまで最大で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p185">On the **eDiscovery** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status of the closed case. It might take up to 60 minutes for the closing process to complete.</span></span> 
    
    <span data-ttu-id="09d7d-p186">プロセスが完了すると、[**電子情報開示**] ページのケースの状態は [**閉じる**] に変わります。もう一度ケース名をクリックして、[**このケースを管理**] ポップアップ ページを表示します。ここには、ケースが閉じられた時刻とケースを閉じたユーザーの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p186">When the process is complete, the status of the case is changed to **Closed** on the **eDiscovery** page. Click the name of the case again to display the **Manage this case** flyout page, which contains information about when the case was closed and who closed it.</span></span> 
     
## <a name="optional-step-10-re-open-a-closed-case"></a><span data-ttu-id="09d7d-493">(省略可能) 手順 10: 閉じたケースを再度開く</span><span class="sxs-lookup"><span data-stu-id="09d7d-493">(Optional) Step 10: Re-open a closed case</span></span>

<span data-ttu-id="09d7d-p187">ケースをもう一度開くと、ケースを閉じたときに有効だった保留を自動的に回復することはできません。ケースをもう一度開いた後に、[**保留**] ページに移動して、以前の保留を有効にする必要があります。保留を有効にするには、詳細ウィンドウで保留を選択し、[**オンにする**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p187">When you reopen a case, any holds that were in place when the case was closed won't be automatically reinstated. After the case is reopened, you'll have to go to the **Hold** page and turn on the previous holds. To turn a hold on, select it and click **Turn it on** in the details pane.</span></span> 
  
1. <span data-ttu-id="09d7d-497">セキュリティ & コンプライアンスセンターで、[**電子情報** \> **開示電子情報開示**] をクリックして、組織内のケースの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-497">In the Security & Compliance Center, click **eDiscovery** \> **eDiscovery** to display the list of cases in your organization.</span></span> 
    
2. <span data-ttu-id="09d7d-498">再度開くケースの名前をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-498">Click the name of the case that you want to reopen.</span></span>
    
    <span data-ttu-id="09d7d-499">[**このケースを管理**] ポップアップ ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-499">The **Manage this case** flyout page is displayed.</span></span> 
    
3. <span data-ttu-id="09d7d-500">[**ケースの状態を管理する**] で、[**ケースを再度開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-500">Under **Manage case status**, click **Reopen case**.</span></span>
    
    <span data-ttu-id="09d7d-501">ケースを閉じたときに関連付けられていた保留は自動的に有効にならないことを示す警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-501">A warning is displayed saying that the holds that were associated with the case when it was closed won't be turned on automatically.</span></span>
    
4. <span data-ttu-id="09d7d-502">[**はい**] をクリックしてケースを再度開きます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-502">Click **Yes** to reopen the case.</span></span> 
    
    <span data-ttu-id="09d7d-503">[**このケースを管理**] ポップアップ ページの状態が [**閉じる**] から [**アクティブ**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-503">The status on the **Manage this case** flyout page is changed from **Closed** to **Active**.</span></span>
    
5. <span data-ttu-id="09d7d-504">[**このケースを管理**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-504">Close the **Manage this case** page.</span></span> 
    
6. <span data-ttu-id="09d7d-p188">[**電子情報開示**] ページで、![[更新] アイコン](media/O365-MDM-Policy-RefreshIcon.gif) [**更新**] をクリックして、再度開いたケースの状態を更新します。再度開くプロセスが完了するまで最大で 60 分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p188">On the **eDiscovery** page, click ![Refresh icon](media/O365-MDM-Policy-RefreshIcon.gif) **Refresh** to update the status of the reopened case. It might take up to 60 minutes for the reopening process to complete.</span></span> 
    
    <span data-ttu-id="09d7d-507">プロセスが完了すると、[**電子情報開示**] ページのケースの状態は [**アクティブ**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-507">When the process is complete, the status of the case is changed to **Active** on the **eDiscovery** page.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="09d7d-508">詳細情報</span><span class="sxs-lookup"><span data-stu-id="09d7d-508">More information</span></span>

- <span data-ttu-id="09d7d-p189">**電子情報開示ケースまたは電子情報開示ケースに関連付けられた保留アイテムに制限はありますか。** 次の表には、電子情報開示ケースとケースの保留に関する制限をまとめています。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p189">**Are there any limits for eDiscovery cases or holds associated with an eDiscovery case?** The following table lists the limits for eDiscovery cases and case holds.</span></span>
    
  |<span data-ttu-id="09d7d-511">**制限の説明**</span><span class="sxs-lookup"><span data-stu-id="09d7d-511">**Description of limit**</span></span>|<span data-ttu-id="09d7d-512">**制限**</span><span class="sxs-lookup"><span data-stu-id="09d7d-512">**Limit**</span></span>|
  |:-----|:-----|
  |<span data-ttu-id="09d7d-513">組織のケースの最大数</span><span class="sxs-lookup"><span data-stu-id="09d7d-513">Maximum number of cases for an organization</span></span>  <br/> |<span data-ttu-id="09d7d-514">制限なし</span><span class="sxs-lookup"><span data-stu-id="09d7d-514">No limit</span></span>  <br/> |
  |<span data-ttu-id="09d7d-515">組織のケース保留の最大数</span><span class="sxs-lookup"><span data-stu-id="09d7d-515">Maximum number of case holds for an organization</span></span>  <br/> |<span data-ttu-id="09d7d-516">10,000</span><span class="sxs-lookup"><span data-stu-id="09d7d-516">10,000</span></span>  <br/> |
  |<span data-ttu-id="09d7d-517">1 つのケース保留のメールボックスの最大数</span><span class="sxs-lookup"><span data-stu-id="09d7d-517">Maximum number of mailboxes in a single case hold</span></span>  <br/> |<span data-ttu-id="09d7d-518">1,000</span><span class="sxs-lookup"><span data-stu-id="09d7d-518">1,000</span></span>  <br/> |
  |<span data-ttu-id="09d7d-519">1 つのケース保留の SharePoint および OneDrive for Business サイトの最大数</span><span class="sxs-lookup"><span data-stu-id="09d7d-519">Maximum number of SharePoint and OneDrive for Business sites in a single case hold</span></span>  <br/> |<span data-ttu-id="09d7d-520">100</span><span class="sxs-lookup"><span data-stu-id="09d7d-520">100</span></span>  <br/> |
   
- <span data-ttu-id="09d7d-521">**Advanced eDiscovery のケース管理ページで作成されたケースについて**</span><span class="sxs-lookup"><span data-stu-id="09d7d-521">**What about cases that were created on the case management page in Advanced eDiscovery?**</span></span> <span data-ttu-id="09d7d-522">セキュリティ & コンプライアンスセンターの [**電子情報開示**] ページの下部にあるリンクをクリックすると、古い高度な電子情報開示ケースのリストにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-522">You can access a list of older Advanced eDiscovery cases by clicking the link at the bottom on the **eDiscovery** page in the Security & Compliance Center.</span></span> <span data-ttu-id="09d7d-523">ただし、以前のケースで作業を行うには、Office 365 サポートに連絡して、セキュリティ & コンプライアンスセンターで、ケースを新しい電子情報開示ケースに移行するよう要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-523">However, to do any work in an older case, you have to contact Office 365 Support and request that the case be moved to a new eDiscovery case in the Security & Compliance Center.</span></span> 
    
- <span data-ttu-id="09d7d-p191">**電子情報開示管理者を作成する理由。** 前述のとおり、電子情報開示管理者は、組織内のすべての電子情報開示ケースを表示したり、これらのケースにアクセスしたりできる、電子情報開示マネージャー役割グループのメンバーです。すべての電子情報開示ケースにアクセスする能力には、2 つの重要な目的があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p191">**Why create an eDiscovery Administrator?** As previously explained, an eDiscovery Administrator is member of the eDiscovery Manager role group who can view and access all eDiscovery cases in your organization. This ability to access all the eDiscovery cases has two important purposes:</span></span>
    
  - <span data-ttu-id="09d7d-527">電子情報開示のケースの唯一のメンバーが組織を退職すると、どのユーザー (組織管理役割グループのメンバー、または電子情報開示マネージャー役割グループの他のメンバーなど) も、ケースのメンバーではないため、その電子情報開示のケースにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-527">If a person who is the only member of an eDiscovery case leaves your organization, no one (including members of the Organization Management role group or another member of the eDiscovery Manager role group) can access that eDiscovery case because they aren't a member of a case.</span></span> <span data-ttu-id="09d7d-528">この状況では、ケースのデータにアクセスする方法はありません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-528">In this situation, there would be no way to access the data in the case.</span></span> <span data-ttu-id="09d7d-529">しかし、電子情報開示管理者は組織内のすべての電子情報開示ケースにアクセスできるため、セキュリティ & コンプライアンスセンターでケースを表示し、そのケースのメンバーとして自分または別の電子情報開示マネージャーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-529">But because an eDiscovery Administrator can access all eDiscovery cases in the organization, they can view the case in the Security & Compliance Center and add themselves or another eDiscovery manager as a member of the case.</span></span>
    
  - <span data-ttu-id="09d7d-p193">電子情報開示管理者は、すべての電子情報開示ケースを表示し、これらのケースにアクセスできるため、すべてのケースと関連するコンテンツ検索の監査と監視を行うことができます。これは、コンテンツ検索または電子情報開示ケースの誤った使い方の防止に役立ちます。さらに、電子情報開示管理者はコンテンツ検索の結果に含まれる潜在的な機密情報にアクセスできるため、電子情報開示管理者となるユーザーの数を制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p193">Because an eDiscovery Administrator can view and access all eDiscovery cases, they can audit and oversee all cases and associated Content Searches. This can help to prevent any misuse of Content Searches or eDiscovery cases. And because eDiscovery Administrators can access potentially sensitive information in the results of a Content Search, you should limit the number of people who are eDiscovery Administrators.</span></span>
    
    <span data-ttu-id="09d7d-533">最後に説明したように、Security & コンプライアンスセンターの電子情報開示管理者は、高度な電子情報開示の管理者として自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-533">Finally, as previous explained, eDiscovery Administrators in the Security & Compliance Center are automatically added as administrators in Advanced eDiscovery.</span></span> <span data-ttu-id="09d7d-534">つまり、電子情報開示管理者であるユーザーは、ユーザーの設定、ケースの作成、ケースへのデータの追加など、高度な電子情報開示で管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-534">That means a person who is an eDiscovery Administrator can perform administrative tasks in Advanced eDiscovery, such as setting up users, creating cases, and adding data to cases.</span></span>
    
- <span data-ttu-id="09d7d-p195">**コンテンツの場所を保留にするには、どのようなライセンスが必要ですか。** 一般に、コンテンツの場所を保留にするには、組織に Office 365 E3 サブスクリプション以上が必要です。メールボックスを保留にするには、保留にするメールボックスの Exchange Online プラン 2 のライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p195">**What are the licensing requirements to place content locations on hold?** In general, organizations require an Office 365 E3 subscription or higher to place content locations on hold. To place mailboxes on hold, an Exchange Online Plan 2 license is required for the mailbox you want to place on hold.</span></span>
    
- <span data-ttu-id="09d7d-p196">**ケースのすべてのコンテンツを検索するのに、手順 5 でその他知っておく必要があることはありますか。** 前述のとおり、ケースで保留となっているコンテンツの場所を検索することができます。これを行うときに、保留の基準と一致するコンテンツのみが検索されます。保留の基準がない場合、すべてのコンテンツが検索されます。コンテンツがクエリで保留になっている場合、(手順 4 で保留となった) 保留の基準と (手順 5 の検索からの) 保留基準が検索結果で返されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p196">**What else should you know about searching all case content in Step 5?** As previously explained, you can search the content locations that have been placed on hold in the case. When you do this, only the content that matches the hold criteria is search. If there is no hold criteria, all content is searched. If contents are on a query-based hold, only the content that matches both hold criteria (from the hold placed in Step 4) and the search criteria (from the search in Step 5) is returned with the search results.</span></span>
    
    <span data-ttu-id="09d7d-543">すべてのケースのコンテンツを検索する場合は、次の点に注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-543">Here are some other things to keep in mind when searching all case content:</span></span>
    
  - <span data-ttu-id="09d7d-p197">同じケース内でコンテンツの場所が複数保留となっている場合、すべてのケースのコンテンツのオプションを使用してコンテンツの場所を検索するときに、保留のクエリは **OR** 演算子によって結合されます。同様に、コンテンツの場所が (1 つはクエリが使用され、もう 1 つはすべてのコンテンツが保留となっている無限の保留である) 2 つの異なる保留の一部である場合、無限の保留のため、すべてのコンテンツが検索されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p197">If a content location is part of multiple holds within the same case, the hold queries are combined by an **OR** operator when you search that content location using the all case content option. Similarly, if a content location is part of two different holds, where one is query-based and the other is an infinite hold (where all content is placed on hold), then all content will be search because of the infinite hold.</span></span> 
    
  - <span data-ttu-id="09d7d-p198">コンテンツ検索があるケース用であり、すべてのケースのコンテンツを検索するように構成し、(コンテンツの場所を追加または削除したり、保留のクエリを変更して) 保留を変更したりした場合、検索構成はそれらの変更で更新されます。ただし、検索結果を更新するには、保留が変更されてから検索を再実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p198">If a content search is for a case and you've configured it to search all case content and then you change a hold (by adding or removing a content location or changing the hold query), the search configuration is updated with those changes. However, you have to re-run the search after the hold is changed to update the search results.</span></span>
    
  - <span data-ttu-id="09d7d-p199">電子情報開示ケースのコンテンツの場所で複数のケースが保留となっており、すべてのケースのコンテンツを検索するように選択した場合、その検索クエリのキーワードの最大数は 500 となります。これは、コンテンツ検索で **OR** 演算子を使用して、クエリによるすべての保留が結合されるためです。結合された保留のクエリとコンテンツ検索クエリのキーワードが 500 を超える場合、クエリを使用したケースの保留と一致するもののみでなく、メールボックスのコンテンツがすべて検索されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p199">If multiple case holds are placed on a content location in an eDiscovery case and you select to search all case content, the maximum number of keywords for that search query is 500. That's because the content search combines all the query-based holds by using the **OR** operator. If there are more than 500 keywords in the combined hold queries and the content search query, then all content in the mailbox is searched, not just that content that matches the any of query-based case holds.</span></span> 
    
  - <span data-ttu-id="09d7d-551">保留のケースの状態が [**有効にしています**] の場合、保留が有効になっている間もケースのコンテンツの場所を検索できます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-551">If a case hold has a status of **Turning on**, you can still search the case content locations while the hold is being turned on.</span></span>
    
  - <span data-ttu-id="09d7d-p200">前述のとおり、検索がすべてのケースのコンテンツを検索するように構成されている場合、複数の検索の結果をエクスポートする場合に、その検索を含めることはできません。検索がケースのすべてのコンテンツを検索するように構成されている場合は、その 1 つの検索の結果をエクスポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p200">As previously stated, if a search is configured to search all case content, then you can't include that search if you want to export the results of multiple searches. If a search is configured to search all case content, then you'll have to export the results of that single search.</span></span>
    
- <span data-ttu-id="09d7d-p201">**保留中のメールボックス、SharePoint サイト、または OneDrive アカウントを複数地域の別の領域に移動する場合でも、保留は適用されますか。** いずれの場合も、メールボックス、サイト、または OneDrive アカウントのコンテンツは引き続き保持されます。ただし、保留アイテムの統計情報には、別の領域に移動されたコンテンツの場所のアイテムが含まれなくなります。移動されたコンテンツの場所に関する保留アイテムの統計情報を含めるには、保留リストを編集し、URL (またはメールボックスの SMTP アドレス) を更新して、コンテンツの場所が保留アイテムの統計情報にもう一度含まれるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p201">**If a mailbox, SharePoint site, or OneDrive account that is on hold is moved to a different region in a multi-geo environment, will the hold still apply?** In all cases, the content in a mailbox, site, or OneDrive account will still be retained. However, the hold statistics will no longer include items from a content location that's been moved to a different region. To include hold statistics for a content location that's been moved, you'll have to edit the hold and update the URL (or SMTP address of a mailbox) so that the content location is once again included in the hold statistics.</span></span> 
    
- <span data-ttu-id="09d7d-p202">**Office 365 グループと Microsoft Teams を保留にする場合はどうですか。** Microsoft Teams は Office 365 グループに組み込まれています。そのため、電子情報開示ケースで保留にする場合とよく似ています。Office 365 グループと Microsoft Teams を保留にするときは、次のことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p202">**What about placing a hold on Office 365 Groups and Microsoft Teams?** Microsoft Teams are built on Office 365 Groups. Therefore, placing them on hold in an eDiscovery case is very similar. Keep the following things in mind when placing Office 365 Groups and Microsoft Teams on hold.</span></span> 
    
  - <span data-ttu-id="09d7d-562">Office 365 グループと Microsoft Teams にあるコンテンツを保留にするには、グループまたはチームに関連付けられているメールボックスと SharePoint サイトを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-562">To place content located in Office 365 Groups and Microsoft Teams on hold, you have to specify the mailbox and SharePoint site that associated with a group or team.</span></span>
    
  - <span data-ttu-id="09d7d-p203">Exchange Online で **Get-UnifiedGroup** コマンドレットを実行し、Office 365 グループまたは Microsoft チームのプロパティを表示します。これは、Office 365 グループまたは Microsoft チームに関連付けられているサイトの URL を取得するのに適した方法です。たとえば、次のコマンドを実行すると、Senior Leadership Team という Office 365 グループの選択したプロパティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p203">Run the **Get-UnifiedGroup** cmdlet in Exchange Online to view properties for an Office 365 Group or Microsoft Team. This is a good way to get the URL for the site that's associated with an Office 365 Group or a Microsoft Team. For example, the following command displays selected properties for an Office 365 Group named Senior Leadership Team:</span></span> 
    
     ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

     DisplayName            : Senior Leadership Team
     Alias                  : seniorleadershipteam
     PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
     SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > <span data-ttu-id="09d7d-566">**Get-UnifiedGroup** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-566">To run the **Get-UnifiedGroup** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="09d7d-p204">ユーザーのメールボックスを検索すると、ユーザーが属している Office 365 グループまたは Microsoft チームは検索されません。同様に、Office 365 グループまたは Microsoft チームを保留にすると、そのグループ メールボックスとグループ サイトのみが保留にされます。保留リストに明示的に追加しない限り、グループ メンバーのメールボックスと OneDrive for Business サイトは保留にされません。そのため、法的な理由から Office 365 グループまたは Microsoft チームを保留にする必要がある場合は、同じ保留リストにグループとチーム メンバーのメールボックスと OneDrive for Business サイトを追加することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p204">When a user's mailbox is searched, any Office 365 Group or Microsoft Team that the user is a member of won't be searched. Similarly, when you place an Office 365 Group or Microsoft Team hold, only the group mailbox and group site are placed on hold; the mailboxes and OneDrive for Business sites of group members aren't placed on hold unless you explicitly add them to the hold. Therefore, if you the need to place an Office 365 Group or Microsoft Team on hold for a legal reasons, consider adding the mailboxes and OneDrive for Business sites for group and team members on the same hold.</span></span>
    
  - <span data-ttu-id="09d7d-570">Office 365 グループまたは microsoft チームのメンバーの一覧を取得するには、microsoft 365 管理センターの [**ホーム\>グループ**] ページでプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="09d7d-570">To get a list of the members of a Office 365 Group or Microsoft Team, you can view the properties on the **Home \> Groups** page in the Microsoft 365 admin center.</span></span> <span data-ttu-id="09d7d-571">または、Exchange Online PowerShell で次のコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="09d7d-571">Alternatively, you can run the following command in Exchange Online PowerShell:</span></span> 
    
      ```
      Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
      ```

    > [!NOTE]
    > <span data-ttu-id="09d7d-572">**Get-UnifiedGroupLinks** コマンドレットを実行するには、Exchange Online で View-Only Recipients という役割が割り当てられているか、View-Only Recipients という役割が割り当てられている役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-572">To run the **Get-UnifiedGroupLinks** cmdlet, you have to be assigned the View-Only Recipients role in Exchange Online or be a member of a role group that's assigned the View-Only Recipients role.</span></span> 
  
  - <span data-ttu-id="09d7d-p206">Microsoft Teams チャネルが含まれる会話は、Microsoft チームに関連付けられているメールボックスに保存されます。同様に、チャネルでチーム メンバーが共有するファイルはチームの SharePoint サイトに保存されます。そのため、チャネル内の会話とファイルを保持するには、Microsoft チーム メールボックスと SharePoint サイトを保留にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p206">Conversations that are part of a Microsoft Teams channel are stored in the mailbox that's associated with the Microsoft Team. Similarly, files that team members share in a channel are stored on the team's SharePoint site. Therefore, you have to place the Microsoft Team mailbox and SharePoint site on hold to retain conversations and files in a channel.</span></span>
    
    <span data-ttu-id="09d7d-p207">または、Microsoft Teams のチャット リストに含まれる会話は、チャットに参加したユーザーのメールボックスに保存されます。チャットの会話でユーザーが共有するファイルは、ファイルを共有するユーザーの OneDrive for Business サイトに保存されます。そのため、チャット リストの会話やファイルを保持するには、個々のユーザーのメールボックスと OneDrive for Business サイトを保留にする必要があります。これが、チームのメールボックス (とサイト) を保留にするだけでなく、Microsoft チームのメンバーのメールボックスを保留にすることをお勧めする理由です。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p207">Alternatively, conversations that are part of the Chat list in Microsoft Teams are stored in the mailbox of the user's who participate in the chat. And files that a user shares in Chat conversations are stored in the OneDrive for Business site of the user who shares the file. Therefore, you have to place the individual user mailboxes and OneDrive for Business sites on hold to retain conversations and files in the Chat list. That's why it's a good idea to place a hold on the mailboxes of members of a Microsoft Team in addition to placing the team mailbox (and site) on hold.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="09d7d-p208">Microsoft Teams のチャット リストに含まれている会話に参加するユーザーは、メールボックスを電子情報開示の保留対象にするときにチャット会話を保持するために、Exchange Online の (クラウド ベースの) メールボックスを持つ必要があります。この理由は、チャット リストに含まれている会話がチャット参加者のクラウドベースのメールボックスに保存されるためです。チャット参加者が Exchange Online のメールボックスを持っていない場合、チャットの会話を保持できなくなります。たとえば、Exchange のハイブリッド展開では、オンプレミスのメールボックスを持つユーザーは Microsoft Teams のチャット リストに含まれている会話に参加できる可能性があります。ただし、この場合はユーザーにクラウドベースのメールボックスがないため、それらの会話の内容を保持できません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p208">Users who participate in conversations that are part of the Chat list in Microsoft Teams must have an Exchange Online (cloud-based) mailbox in order to retain chat conversations when the mailbox is placed on an eDiscovery hold. That's because conversations that are part of the Chat list are stored in the cloud-based mailboxes of the chat participants. If a chat participant doesn't have an Exchange Online mailbox, you won't be able to retain chat conversations. For example, in an Exchange hybrid deployment, users with an on-premises mailbox might be able to participate in conversations that are part of the Chat list in Microsoft Teams. However in this case, content from these conversation can't be retained because the users don't have cloud-based mailboxes.</span></span> 
  
  - <span data-ttu-id="09d7d-p209">各 Microsoft チームまたはチーム チャネルには、メモと共同作業用の Wiki が含まれています。Wiki コンテンツは、.mht 形式のファイルに自動的に保存されます。このファイルは、チームの SharePoint サイトの Teams Wiki データ ドキュメント ライブラリに保存されます。Wiki のコンテンツを保留にするには、チームの SharePoint サイトを保留にします。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p209">Every Microsoft Team or team channel contains a Wiki for note-taking and collaboration. The Wiki content is automatically saved to a file with a .mht format. This file is stored in the Teams Wiki Data document library on the team's SharePoint site. You can place the content in the Wiki on hold by placing the team's SharePoint site on hold.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="09d7d-p210">(チームの SharePoint サイトを保留にするときに) Microsoft チームまたはチーム チャネルの Wiki コンテンツを保持する機能は、2017 年 6 月 22 日にリリースされました。チーム サイトが保留にされると、この日から Wiki コンテンツが保持されます。ただし、チーム サイトが保留にされ、Wiki コンテンツが 2017 年 6 月 22 日よりも前に削除された場合、その Wiki コンテンツは保持されていません。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p210">The capability to retain Wiki content for a Microsoft Team or team channel (when you place the team's SharePoint site on hold) was released on June 22, 2017. If a team site is on hold, the Wiki content will be retained starting on that date. However, if a team site is on hold and the Wiki content was deleted before June 22, 2017, the Wiki content was not retained.</span></span> 
  
- <span data-ttu-id="09d7d-p211">**OneDrive for Business サイトの URL を見つけるにはどうすればよいですか。** 組織内の OneDrive for Business サイトの URL リストを収集して、電子情報開示ケースに関連する保留または検索リストに追加できるようにするには、[組織内のすべての OneDrive の場所のリストの作成](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a)に関する記事を参照してください。この記事のこのスクリプトでは、すべての OneDrive サイトのリストを含むテキスト ファイルが作成されます。このスクリプトを実行するには、SharePoint Online Management Shell をインストールして使用する必要があります。必ず、検索する各 OneDrive サイトに、組織の MySite ドメインの URL を追加してください。これは、すべての OneDrive を含むドメインです。たとえば、`https://contoso-my.sharepoint.com` です。以下に、ユーザーの OneDrive サイトの URL 例を示します。`https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`。</span><span class="sxs-lookup"><span data-stu-id="09d7d-p211">**How do I find the URL for OneDrive for Business sites?** To collect a list of the URLs for the OneDrive for Business sites in your organization so you can add them to a hold or search associated with an eDiscovery case, see [Create a list of all OneDrive locations in your organization](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). This script in this article creates a text file that contains a list of all OneDrive sites. To run this script, you'll have to install and use the SharePoint Online Management Shell. Be sure to append the URL for your organization's MySite domain to each OneDrive site that you want to search. This is the domain that contains all your OneDrive; for example,  `https://contoso-my.sharepoint.com`. Here's an example of a URL for a user's OneDrive site:  `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.</span></span>
