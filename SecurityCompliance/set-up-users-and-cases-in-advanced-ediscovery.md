---
title: Office 365 の高度な電子情報開示でユーザーとケースをセットアップする
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'Office 365 Advanced eDiscovery でユーザーの役割を構成し、ケースを作成して、ケースにユーザーを割り当てる方法について説明します。  '
ms.openlocfilehash: 5a22e0683e49ebdaf8391e092aeb101386e0636b
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999270"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="7913a-103">Office 365 の高度な電子情報開示でユーザーとケースをセットアップする</span><span class="sxs-lookup"><span data-stu-id="7913a-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="7913a-104">このトピックでは、Office 365 Advanced eDiscovery のユーザーおよびケースをセットアップする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="7913a-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7913a-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="7913a-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="7913a-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="7913a-107">Prerequisites</span></span>

<span data-ttu-id="7913a-108">Advanced eDiscovery でケースとユーザーを設定する前に、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="7913a-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="7913a-p102">Advanced eDiscovery を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) に Office365 E5 ライセンスが割り当てられている必要があります。または、Office365 E1 または E3 ライセンスを持つユーザーに Advanced eDiscovery 単体のライセンスを割り当てることもできます。ケースに割り当てられ、Advanced eDiscovery を使用してデータを分析する管理者および法令遵守責任者には E5 ライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="7913a-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="7913a-112">電子情報開示ケースを作成してメンバーを追加するには、Office 365 &amp;セキュリティコンプライアンスセンターの電子情報開示マネージャーの役割グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="7913a-112">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it.</span></span> <span data-ttu-id="7913a-113">セキュリティ&amp; /コンプライアンスセンターの電子情報開示マネージャーの役割グループに自分を追加するには、Office 365 組織の全体管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7913a-113">To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization.</span></span> <span data-ttu-id="7913a-114">全体管理者ではない場合は、電子情報開示マネージャーの役割グループに追加するように全体管理者に依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7913a-114">If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group.</span></span> <span data-ttu-id="7913a-115">詳細については、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7913a-115">For more information, see:</span></span>
    
  - [<span data-ttu-id="7913a-116">Microsoft 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="7913a-116">Permissions in the Microsoft 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="7913a-117">Microsoft 365 セキュリティ&amp;コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="7913a-117">Assign eDiscovery permissions in the Microsoft‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="7913a-118">手順 1: ユーザーに電子情報開示のアクセス許可を割り当てる</span><span class="sxs-lookup"><span data-stu-id="7913a-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="7913a-119">最初の手順は、ユーザーが電子情報開示ケースのメンバー &amp;として追加できるように、セキュリティコンプライアンスセンターで必要なアクセス許可をユーザーに割り当てることです。</span><span class="sxs-lookup"><span data-stu-id="7913a-119">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case.</span></span> <span data-ttu-id="7913a-120">セキュリティ&amp; /コンプライアンスセンターでユーザーをケースのメンバーとして追加すると、上級電子情報開示のケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7913a-120">After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="7913a-121">電子情報開示ケースのメンバーとして追加できるように、必要なアクセス許可をユーザーに割り当てるには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報開示のケース](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)」のステップ1を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7913a-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="7913a-122">手順 2: 電子情報開示ケースを作成し、メンバーを追加する</span><span class="sxs-lookup"><span data-stu-id="7913a-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="7913a-123">次の手順では、セキュリティ&amp;コンプライアンスセンターで新しい電子情報開示ケースを作成し、メンバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7913a-123">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members.</span></span> <span data-ttu-id="7913a-124">そのケースのメンバーは、高度な電子情報開示のケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7913a-124">Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="7913a-125">新しい電子情報開示ケースを作成するには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報](ediscovery-cases.md#step-2-create-a-new-case)開示のケース」のステップ2を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7913a-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="7913a-126">電子情報開示ケースにメンバーを追加するには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報開示ケース](ediscovery-cases.md#step-3-add-members-to-a-case)のステップ3」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7913a-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="7913a-127">手順 3: 高度な電子情報開示でケースを進める</span><span class="sxs-lookup"><span data-stu-id="7913a-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="7913a-128">電子情報開示ケースを作成してメンバーを追加すると、そのユーザー (またはケースのメンバー) は、高度な電子情報開示で対応するケースにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="7913a-128">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery.</span></span> <span data-ttu-id="7913a-129">高度な電子情報開示のケースにアクセスするには、 [Microsoft 365 セキュリティ&amp;コンプライアンスセンターの「電子情報](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)開示のケース」の手順8を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7913a-129">To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Microsoft 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7913a-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="7913a-130">See also</span></span>

[<span data-ttu-id="7913a-131">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="7913a-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="7913a-132">データの準備</span><span class="sxs-lookup"><span data-stu-id="7913a-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 