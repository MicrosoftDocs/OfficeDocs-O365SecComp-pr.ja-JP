---
title: 高度な電子情報開示で通信を操作する (プレビュー)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 916691e1f2470ef9e9e54d9dfe06c5277a92ba53
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241254"
---
# <a name="work-with-communications-in-advanced-ediscovery-preview"></a><span data-ttu-id="8ccef-102">高度な電子情報開示で通信を操作する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="8ccef-102">Work with communications in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="8ccef-103">Advanced eDiscovery (プレビュー) を使用すると、法務部門は法的情報保留通知の追跡と配布に関してプロセスを簡素化できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-103">Advanced eDiscovery (Preview) allows legal departments to simplify their processes around tracking and distributing legal hold notifications.</span></span> <span data-ttu-id="8ccef-104">保管担当者の通信機能を使用すると、法律部門は、通知、アラーム、およびエスカレーションからすべてを1つの場所で管理および自動化できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-104">The custodian communications feature enables legal departments to manage and automate their entire legal hold processes--from notifications, reminders, and escalations--all in one place.</span></span>

## <a name="what-is-a-legal-hold-notification"></a><span data-ttu-id="8ccef-105">法的情報保留通知とは</span><span class="sxs-lookup"><span data-stu-id="8ccef-105">What is a legal hold notification?</span></span>

<span data-ttu-id="8ccef-106">法的情報保留 (*訴訟ホールド*とも呼ばれます) 通知は、組織の法務部門から従業員、臨時スタッフ、またはその他のデータ保管担当者に送信される通知です。</span><span class="sxs-lookup"><span data-stu-id="8ccef-106">A legal hold (also known as a *litigation hold*) notice is a notification sent from an organization’s legal department to employees, contingent staff, or other data custodians.</span></span> <span data-ttu-id="8ccef-107">これらの通知では、電子的に保存された情報 (ESI) と、法的な法的事項に関連する可能性があるあらゆる材料を保持するように保管担当者に指示します。</span><span class="sxs-lookup"><span data-stu-id="8ccef-107">These notifications instruct custodians to preserve electronically stored information (ESI) as well as any material that may be relevant to an active or imminent legal matter.</span></span> <span data-ttu-id="8ccef-108">法務部門のチームは、それぞれの保管担当者が受信、読み取り、理解され、特定の手順に準拠することを知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ccef-108">Legal teams must know that each custodian has received, read, and understood, and agreed to comply with the given instructions.</span></span>

## <a name="the-legal-hold-notification-process"></a><span data-ttu-id="8ccef-109">法的情報保留通知プロセス</span><span class="sxs-lookup"><span data-stu-id="8ccef-109">The legal hold notification process</span></span>

<span data-ttu-id="8ccef-110">組織には、訴訟や規制に関する調査について学習したときに、関連する情報を保持するための職務があります。</span><span class="sxs-lookup"><span data-stu-id="8ccef-110">An organization has a duty to preserve relevant information when it learns about an impending litigation or regulatory investigation.</span></span> <span data-ttu-id="8ccef-111">保持要件に準拠するために、組織はすぐに、必要な情報を保持するために、自分の責務に関する保管担当者の潜在的な通知にすぐに通知する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ccef-111">In order to comply with its preservation requirements, the organization should immediately inform potential custodians about their duty to preserve relevant information.</span></span> 

<span data-ttu-id="8ccef-112">Advanced eDiscovery (プレビュー) を使用すると、法務部門は法的情報保留通知ワークフローを作成およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-112">With Advanced eDiscovery (Preview), legal teams can create and customize their legal hold notification workflow.</span></span> <span data-ttu-id="8ccef-113">保管担当者の通信機能を使用すると、法務部門のチームが以下の通知とワークフローを構成できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-113">The Custodian Communications feature allows legal teams to configure the following notices and workflows:</span></span>

1. <span data-ttu-id="8ccef-114">**発行通知**: 法務部門からの通知によって法的情報保留通知が発行 (または開始) され、保管担当者がケースに関する関連情報を持っている可能性があることを示します。</span><span class="sxs-lookup"><span data-stu-id="8ccef-114">**Issuance notice**: A legal hold notice is issued (or initiated) by a notification from the legal department to custodians who might have relevant information about the case matter.</span></span> <span data-ttu-id="8ccef-115">この通知は、検出に必要なすべての情報を保持するように保管担当者に指示します。</span><span class="sxs-lookup"><span data-stu-id="8ccef-115">This notice instructs those custodians to preserve any information that might be needed for discovery.</span></span> 
   
2.  <span data-ttu-id="8ccef-116">**再発行の通知**: ケースでは、以前に指示された情報よりも多くの情報を保持するために、保管担当者が必要になる場合があります。</span><span class="sxs-lookup"><span data-stu-id="8ccef-116">**Re-Issuance notice**: During a case, custodians may be required to preserve additional or less information than was previously instructed.</span></span> <span data-ttu-id="8ccef-117">このシナリオでは、既存の保留通知を更新して、保管担当者に再発行することができます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-117">For this scenario, you can update the existing hold notice and re-issue it to your custodians.</span></span>

3.  <span data-ttu-id="8ccef-118">**リリース通知**: 1 つの問題が解決され、保管担当者が保持義務の対象ではなくなると、不要になった場合に情報が保持されないように、保管担当者を解放することができます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-118">**Release notice**: Once a matter is resolved and the custodian is no longer subject to a preservation duty, the custodian can be released so that information is no longer retained if not needed.</span></span> <span data-ttu-id="8ccef-119">また、保管担当者には、保持義務がなくなり、アクティビティを再開する方法についての未処理の指示があることが通知されます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-119">In addition, your custodian will be notified that they are no longer under preservation duty and with outstanding instructions on how to resume their activity.</span></span>

4. <span data-ttu-id="8ccef-120">**アラームとエスカレーション**: 一部のインスタンスでは、法的証拠開示の要件を満たすために十分ではないことを通知するだけです。</span><span class="sxs-lookup"><span data-stu-id="8ccef-120">**Reminders and escalations**: In some instances, just issuing a notice is not enough to satisfy legal discovery requirements.</span></span> <span data-ttu-id="8ccef-121">各通知で、法務部門は、応答のない保管担当者で自動的にフォローアップする一連のアラームおよびエスカレーションワークフローをスケジュールすることができます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-121">With each notification, legal teams can schedule a set of reminder and escalation workflows to automatically follow-up with unresponsive custodians.</span></span>

    - <span data-ttu-id="8ccef-122">**事前通知**: 法的情報保留通知が発行された後、または保管担当者のセットに再発行されると、組織は応答のない保管担当者に通知するように通知を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-122">**Reminders**:  After a legal hold notice has been issued or re-issued to a set of custodians, an organization may set up reminders to alert unresponsive custodians.</span></span> 

    - <span data-ttu-id="8ccef-123">**エスカレーション**: 通知のセットの後でも保管担当者が応答しない場合、法務部門は保管担当者とその上司に通知するエスカレーションワークフローを設定できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-123">**Escalations**: In some cases, if a custodian remains unresponsive even after a set of reminders, the legal team can set up an escalation workflow to notify the custodian and his/her manager.</span></span>

## <a name="role-groups-and-permissions"></a><span data-ttu-id="8ccef-124">役割グループとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="8ccef-124">Role groups and permissions</span></span> 

<span data-ttu-id="8ccef-125">法的チームは、セキュリティ & コンプライアンスセンターで、電子情報開示関連の役割グループとアクセス許可を使用して、ケースアクティビティを制御し、セグメント化することができます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-125">Legal teams can control and segment their case activity using eDiscovery-related role groups and permissions in the Security & Compliance Center.</span></span> 

<span data-ttu-id="8ccef-126">法的情報保留通知を作成および管理するには、ユーザーが次の役割グループに属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ccef-126">To create and manage legal hold notifications, a user must be part of the following role groups:</span></span>

- <span data-ttu-id="8ccef-127">**電子情報開示マネージャー** -この役割グループのメンバーは、電子情報開示ケースを作成および管理できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-127">**eDiscovery Manager** - Members of this role group can create and manage eDiscovery cases.</span></span> <span data-ttu-id="8ccef-128">メンバーを追加および削除したり、保管担当者とコンテンツの場所を保持に配置したり、訴訟ホールドの通知を管理したり、ケースに関連付けられたコンテンツ検索を作成および編集したり、コンテンツ検索の結果をエクスポートしたり、詳細に分析するための検索結果を準備したりすることができます。電子情報開示 (プレビュー)。</span><span class="sxs-lookup"><span data-stu-id="8ccef-128">They can add and remove members, place custodians and content locations on hold, manage legal hold notifications, create and edit Content Searches associated with a case, export the results of a Content Search, and prepare search results for analysis in Advanced eDiscovery (Preview).</span></span> <span data-ttu-id="8ccef-129">この役割グループには、2 つのサブグループがあります。</span><span class="sxs-lookup"><span data-stu-id="8ccef-129">There are two sub-groups in this role group.</span></span> <span data-ttu-id="8ccef-130">これらのサブグループの違いは、スコープに基づきます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-130">The difference between these subgroups is based on scope.</span></span>

  - <span data-ttu-id="8ccef-131">**電子情報開示マネージャー** -自分が作成またはメンバーとなっている電子情報開示ケースを表示および管理できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-131">**eDiscovery Manager** - Can view and manage the eDiscovery cases they create or are a member of.</span></span> <span data-ttu-id="8ccef-132">別の電子情報開示管理者が作成したケースのメンバーとして2番目の電子情報開示マネージャーを追加しなかった場合、2番目の電子情報開示マネージャーは、Security & コンプライアンスセンターの [電子情報開示] ページでケースを表示または開くことができません。</span><span class="sxs-lookup"><span data-stu-id="8ccef-132">If another eDiscovery Manager creates a case but doesn't add a second eDiscovery Manager as a member of that case, the second eDiscovery Manager won't be able to view or open the case on the eDiscovery page in the Security & Compliance Center.</span></span> <span data-ttu-id="8ccef-133">また、電子情報開示管理者は、高度な電子情報開示 (プレビュー) でケースにアクセスして、分析タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-133">eDiscovery Managers can also access their cases in Advanced eDiscovery (Preview) to perform analysis tasks.</span></span>

  - <span data-ttu-id="8ccef-134">**電子情報開示管理者**は、電子情報開示マネージャーが実行できるすべてのケース管理タスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-134">**eDiscovery Administrator** - Can perform all case management tasks that an eDiscovery Manager can do.</span></span> <span data-ttu-id="8ccef-135">さらに、電子情報開示管理者は、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="8ccef-135">Additionally, an eDiscovery Administrator can:</span></span>
    
    - <span data-ttu-id="8ccef-136">[電子情報開示] ページにリストされたすべてのケースを表示する。</span><span class="sxs-lookup"><span data-stu-id="8ccef-136">View all cases that are listed on the eDiscovery page.</span></span>
    - <span data-ttu-id="8ccef-137">ケースのメンバーとして自身を追加した後、組織内のケースを管理します。</span><span class="sxs-lookup"><span data-stu-id="8ccef-137">Manage any case in the organization after they add themselves as a member of the case.</span></span>
    - <span data-ttu-id="8ccef-138">組織内のすべてのケースについて、Advanced eDiscovery (プレビュー) のサポート案件データにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="8ccef-138">Access case data in Advanced eDiscovery (Preview) for any case in the organization.</span></span>

<span data-ttu-id="8ccef-139">詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターで電子情報開示のアクセス許可を割り当てる](../assign-ediscovery-permissions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ccef-139">For more information, see [Assign eDiscovery permissions in the Office 365 Security & Compliance Center](../assign-ediscovery-permissions.md).</span></span>