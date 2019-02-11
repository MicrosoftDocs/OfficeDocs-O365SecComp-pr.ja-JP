---
title: Office 365 Advanced eDiscovery でユーザーと とケースを設定する
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 60ffd80b-4376-419d-b6e4-a72029b9907c
description: 'ユーザー ロールを構成し、場合を作成し、Office 365 の高度な電子的証拠の開示の場合にユーザーを割り当てる方法について説明します。  '
ms.openlocfilehash: 4c0043b7651cc82272492e19faf01041c6f67932
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29559060"
---
# <a name="set-up-users-and-cases-in-office-365-advanced-ediscovery"></a><span data-ttu-id="fb4f1-103">Office 365 Advanced eDiscovery でユーザーと とケースを設定する</span><span class="sxs-lookup"><span data-stu-id="fb4f1-103">Set up users and cases in Office 365 Advanced eDiscovery</span></span>

<span data-ttu-id="fb4f1-104">このトピックでは、ユーザーと Office 365 の高度な証拠開示のためのケースを設定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-104">This topic describes how to set up users and cases for Office 365 Advanced eDiscovery.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fb4f1-p101">Advanced eDiscovery を使用するには、Advanced Compliance アドオンがインストールされた Office 365 E3 サブスクリプション、または E5 サブスクリプションがお客様の組織で必要になります。このプランを利用しておらず、Advanced eDiscovery をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップ](https://go.microsoft.com/fwlink/p/?LinkID=698279)してください。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
## <a name="prerequisites"></a><span data-ttu-id="fb4f1-107">前提条件</span><span class="sxs-lookup"><span data-stu-id="fb4f1-107">Prerequisites</span></span>

<span data-ttu-id="fb4f1-108">ケースと高度な電子的証拠開示にユーザーを設定する前に、以下が必要です。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-108">Before setting up cases and users in Advanced eDiscovery, the following is required:</span></span>
  
- <span data-ttu-id="fb4f1-p102">高度な電子的証拠開示を使用してユーザーのデータを分析するには、ユーザー (データの保管担当者) 割り当てる必要があります、Office 365 の E5 のライセンスです。または、Office 365 の E1 または E3 のライセンスを持つユーザーが高度な電子的証拠開示のスタンドアロン ライセンスを割り当てることができます。管理者およびコンプライアンス担当者の場合に割り当てられ、データを分析する高度な電子的証拠開示を使用している E5 のライセンスは不要です。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-p102">To analyze a user's data using Advanced eDiscovery, the user (the custodian of the data) must be assigned an Office 365 E5 license. Alternatively, users with an Office 365 E1 or E3 license can be assigned an Advanced eDiscovery standalone license. Administrators and compliance officers who are assigned to cases and use Advanced eDiscovery to analyze data don't need an E5 license.</span></span> 
    
- <span data-ttu-id="fb4f1-p103">Office 365 のセキュリティでは、電子的証拠開示マネージャーの役割グループのメンバーである必要がある&amp;コンプライアンス センターは、電子的証拠開示のサポート案件を作成し、メンバーを追加します。セキュリティでは、電子的証拠開示マネージャーのロール グループに登録するのには&amp;には、Office 365 の組織のグローバル管理者コンプライアンス ・ センターがあります。グローバル管理者でない場合に電子的証拠開示マネージャーの役割グループに追加できるグローバル管理者に依頼する必要があります。詳細についてを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-p103">You have to be a member of the eDiscovery Manager role group in the Office 365 Security &amp; Compliance Center to create an eDiscovery case and add members to it. To add yourself to the eDiscovery Manager role group in Security &amp; Compliance Center, you have to be a global administrator in your Office 365 organization. If you're not a global administrator, you 'll have to ask a global administrator to add you to the eDiscovery Manager role group. For more information, see:</span></span>
    
  - [<span data-ttu-id="fb4f1-116">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="fb4f1-116">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
    
  - [<span data-ttu-id="fb4f1-117">Office 365 のセキュリティ、電子的証拠開示のアクセス許可を割り当てる&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="fb4f1-117">Assign eDiscovery permissions in the Office‍ 365 Security &amp; Compliance Center</span></span>](assign-ediscovery-permissions.md)
    
## <a name="step-1-assign-users-ediscovery-permissions"></a><span data-ttu-id="fb4f1-118">手順 1: 電子的証拠開示のアクセス許可をユーザーに割り当てる</span><span class="sxs-lookup"><span data-stu-id="fb4f1-118">Step 1: Assign users eDiscovery permissions</span></span>

<span data-ttu-id="fb4f1-p104">セキュリティ要件のアクセス許可をユーザーに割り当てるには、まず&amp;コンプライアンス センターの私の電子的証拠開示の場合は、メンバーとして追加できるようにします。ユーザーを追加する場合は、セキュリティでのメンバーとして&amp;コンプライアンス センターで行うことができる高度な電子的証拠開示の場合にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-p104">The first step is to assign users the requirement permissions in the Security &amp; Compliance Center so that they can me added as a member of an eDiscovery case. After a user is added as a member of a case in the Security &amp; Compliance Center, they'll be able to access the case in Advanced eDiscovery.</span></span>
  
<span data-ttu-id="fb4f1-121">電子的証拠開示のサポート案件のメンバーとして追加できるように、必要なアクセス許可、ユーザーを割り当て、手順 1 を参照してください。[電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members)です。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-121">To assign a user the necessary permissions so they can be added as a member of an eDiscovery case, see Step 1 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-1-assign-ediscovery-permissions-to-potential-case-members).</span></span>
  
## <a name="step-2-create-an-ediscovery-case-and-add-members"></a><span data-ttu-id="fb4f1-122">手順 2: 電子的証拠開示のサポート案件を作成し、メンバーを追加</span><span class="sxs-lookup"><span data-stu-id="fb4f1-122">Step 2: Create an eDiscovery case and add members</span></span>

<span data-ttu-id="fb4f1-p105">セキュリティの新しい電子的証拠開示のサポート案件を作成するのには、次の手順&amp;コンプライアンス センター メンバーを追加します。ケースのメンバーは高度な電子的証拠開示の場合にアクセスするのには、できます。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-p105">The next step is to create a new eDiscovery case in the Security &amp; Compliance Center and add members. Members of the case will then be able to access the case in Advanced eDiscovery.</span></span>
  
1. <span data-ttu-id="fb4f1-125">新しい電子的証拠開示のサポート案件を作成するには、手順 2 を参照してください。[電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md#step-2-create-a-new-case)です。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-125">To create a new eDiscovery case, see Step 2 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-2-create-a-new-case).</span></span>
    
2. <span data-ttu-id="fb4f1-126">メンバーを追加する、電子的証拠開示の場合に、手順 3 を参照してください[電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md#step-3-add-members-to-a-case)</span><span class="sxs-lookup"><span data-stu-id="fb4f1-126">To add members to an eDiscovery case, see Step 3 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-3-add-members-to-a-case)</span></span>
    
## <a name="step-3-go-a-case-in-advanced-ediscovery"></a><span data-ttu-id="fb4f1-127">手順 3: 高度な電子的証拠開示のケースを移動します。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-127">Step 3: Go a case in Advanced eDiscovery</span></span>

<span data-ttu-id="fb4f1-p106">電子的証拠開示のサポート案件を作成してメンバーを追加する (または、大文字と小文字の任意のメンバー) は高度な電子的証拠開示に対応する大文字と小文字をアクセスできます。高度な電子的証拠開示のサポート案件を開くには、手順 8 を参照してください。[電子的証拠開示の場合は、Office 365 のセキュリティ&amp;コンプライアンス センター](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery)です。</span><span class="sxs-lookup"><span data-stu-id="fb4f1-p106">After you create an eDiscovery case and add members, you (or any member of the case) can access the corresponding case in Advanced eDiscovery. To access a case in Advanced eDiscovery, see Step 8 in [eDiscovery cases in the Office 365 Security &amp; Compliance Center](ediscovery-cases.md#step-8-go-to-the-case-in-advanced-ediscovery).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fb4f1-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="fb4f1-130">See also</span></span>

[<span data-ttu-id="fb4f1-131">Office 365 Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fb4f1-131">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="fb4f1-132">データの準備</span><span class="sxs-lookup"><span data-stu-id="fb4f1-132">Preparing data</span></span>](prepare-data-for-advanced-ediscovery.md)
 