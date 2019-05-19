---
title: Office 365 での特権アクセス管理
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Office 365 での特権アクセス管理の詳細については、このトピックを使用してください。
ms.openlocfilehash: 7547568d6ea2a13de5391d5a827df2921833838c
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157329"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="e4a3b-103">Office 365 での特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="e4a3b-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e4a3b-104">このトピックでは、Office 365 E5 と Advanced コンプライアンス Sku で現在利用可能な機能の展開と構成のガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="e4a3b-105">特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-105">Privileged access management allows granular access control over privileged admin tasks in Office 365.</span></span> <span data-ttu-id="e4a3b-106">これにより、既存の特権のある管理者アカウントを使用して機密性の高いデータにアクセスしたり、重要な構成設定にアクセスしたりすることにより、組織を侵害から保護することができます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-106">It can help protect your organization from breaches that use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="e4a3b-107">特権アクセス管理では、ユーザーはジャストインタイムアクセスを要求して、高度に範囲指定された、時間の制限のある承認ワークフローを通じて、昇格された権限のあるタスクを完了させる必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-107">Privileged access management requires users to request just-in-time access to complete elevated and privileged tasks through a highly scoped and time-bounded approval workflow.</span></span> <span data-ttu-id="e4a3b-108">これにより、機密データや重要な構成設定が危険にさらされることなく、ユーザーにとってすぐにタスクを実行できるだけの余裕が与えられます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-108">This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings.</span></span> <span data-ttu-id="e4a3b-109">Office 365 で特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、管理アクセスの脆弱性に対する防御層を提供できます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-109">Enabling privileged access management in Office 365 allows your organization to operate with zero standing privileges and provide a layer of defense against standing administrative access vulnerabilities.</span></span>

<span data-ttu-id="e4a3b-110">統合された顧客ロックボックスおよび特権アクセス管理ワークフローの簡単な概要については、「 [Office 365 ビデオ」の「customer のロックボックスと特権アクセス管理](https://go.microsoft.com/fwlink/?linkid=2066800)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-110">For a quick overview of the integrated Customer Lockbox and privileged access management workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="e4a3b-111">保護レイヤー</span><span class="sxs-lookup"><span data-stu-id="e4a3b-111">Layers of protection</span></span>

<span data-ttu-id="e4a3b-112">特権アクセス管理は、Office 365 セキュリティアーキテクチャ内の他のデータとアクセス機能の保護を補完します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-112">Privileged access management complements other data and access feature protections within the Office 365 security architecture.</span></span> <span data-ttu-id="e4a3b-113">セキュリティの統合および階層化手法の一部として特権アクセス管理を含めることで、機密情報および Office 365 の構成設定の保護を最大化するセキュリティモデルが提供されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-113">Including privileged access management as part of an integrated and layered approach to security provides a security model that maximizes protection of sensitive information and Office 365 configuration settings.</span></span> <span data-ttu-id="e4a3b-114">図に示されているように、特権アクセス管理は Office 365 データのネイティブ暗号化、および Office 365 サービスの役割ベースのアクセス制御セキュリティモデルで提供される保護に基づいて構築されています。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-114">As shown in the diagram, privileged access management builds on the protection provided with native encryption of Office 365 data and the role-based access control security model of Office 365 services.</span></span> <span data-ttu-id="e4a3b-115">[AZURE AD 特権 Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と共に使用する場合、この2つの機能により、さまざまなスコープでジャストインタイムのアクセスを使用してアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-115">When used with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 の階層型の保護](media/pam-layered-protection.png)

<span data-ttu-id="e4a3b-117">Office 365 での特権アクセス管理は、**タスク**レベルで定義され、スコープが設定されていますが、Azure AD Privileged Identity management は、複数のタスクを実行する機能を使用して、**役割**レベルで保護を適用します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-117">Privileged access management in Office 365 is defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.</span></span> <span data-ttu-id="e4a3b-118">Azure AD 特権 Id 管理は、主に AD の役割および役割グループへのアクセスを管理しますが、Office 365 の特権アクセス管理はタスクレベルでのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-118">Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 applies only at the task level.</span></span>

- <span data-ttu-id="e4a3b-119">**Office 365 で特権アクセス管理を有効にしていますが、既に AZURE AD 特権 Id 管理を使用しています。** Office 365 で特権アクセス管理を追加すると、Office 365 データへの特権アクセスのための、より詳細な保護および監査機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="e4a3b-120">**Office 365 で既に特権アクセス管理を使用しているときに、AZURE AD 特権 Id 管理を有効にする:** Office 365 で Azure AD 特権 Id 管理を特権アクセス管理に追加すると、主にユーザーロールまたは id によって定義された Office 365 外部のデータへの特権アクセスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by user roles or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="e4a3b-121">特権アクセス管理アーキテクチャとプロセスフロー</span><span class="sxs-lookup"><span data-stu-id="e4a3b-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="e4a3b-122">次の各プロセスフローは、特権アクセスのアーキテクチャと、それが Office 365 のサブストレート、Office 365 監査、および Exchange 管理実行空間と対話する方法の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-122">Each of the following process flows outline the architecture of privileged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configure-a-privileged-access-policy"></a><span data-ttu-id="e4a3b-123">手順 1: 特権アクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="e4a3b-123">Step 1: Configure a privileged access policy</span></span>

<span data-ttu-id="e4a3b-124">[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して、特権アクセスポリシーを構成する場合は、ポリシーおよび特権アクセス機能のプロセスと、Office 365 のサブポリシーの属性を定義します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-124">When you configure a privileged access policy with the [Microsoft 365 admin center](https://admin.microsoft.com) or the Exchange Management PowerShell, you define the policy and the privileged access feature processes and the policy attributes in the Office 365 substrate.</span></span> <span data-ttu-id="e4a3b-125">アクティビティは、Office 365 セキュリティ/コンプライアンスセンターに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-125">The activities are logged in the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="e4a3b-126">これで、ポリシーが有効になり、承認のための受信要求を処理する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-126">The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![手順 1: ポリシーの作成](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="e4a3b-128">手順 2: アクセス要求</span><span class="sxs-lookup"><span data-stu-id="e4a3b-128">Step 2: Access request</span></span>

<span data-ttu-id="e4a3b-129">[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して、ユーザーは昇格されたタスクまたは権限のあるタスクへのアクセスを要求できます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-129">In the [Microsoft 365 admin center](https://admin.microsoft.com) or with the Exchange Management PowerShell, users can request access to elevated or privileged tasks.</span></span> <span data-ttu-id="e4a3b-130">特権アクセス機能は、構成された特権アクセスポリシーに対して処理するために、Office 365 サブストレートに要求を送信し、Office 365 セキュリティおよびコンプライアンスセンターのログにアクティビティを記録します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-130">The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the Activity in the Office 365 Security and Compliance Center logs.</span></span>

![手順 2: アクセス要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="e4a3b-132">手順 3: アクセスの承認</span><span class="sxs-lookup"><span data-stu-id="e4a3b-132">Step 3: Access approval</span></span>

<span data-ttu-id="e4a3b-133">承認要求が生成され、保留中の要求通知が承認者に電子メールで送信されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-133">An approval request is generated and the pending request notification is emailed to approvers.</span></span> <span data-ttu-id="e4a3b-134">承認された場合、特権アクセス要求は承認として処理され、タスクが完了できる状態になります。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-134">If approved, the privileged access request is processed as an approval and the task is ready to be completed.</span></span> <span data-ttu-id="e4a3b-135">拒否された場合、タスクはブロックされ、リクエスターへのアクセスは許可されません。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-135">If denied, the task is blocked and no access is granted to the requestor.</span></span> <span data-ttu-id="e4a3b-136">送信者は、電子メールメッセージを使用して、要求の承認または拒否を通知されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-136">The requestor is notified of the request approval or denial via email message.</span></span>

![手順 3: アクセスの承認](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="e4a3b-138">手順 4: Access の処理</span><span class="sxs-lookup"><span data-stu-id="e4a3b-138">Step 4: Access processing</span></span>

<span data-ttu-id="e4a3b-139">承認済みの要求の場合、タスクは Exchange 管理実行空間によって処理されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-139">For an approved request, the task is processed by the Exchange Management runspace.</span></span> <span data-ttu-id="e4a3b-140">承認は、特権アクセスポリシーに照らしてチェックされ、Office 365 のサブストレートによって処理されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-140">The approval is checked against the privileged access policy and processed by the Office 365 substrate.</span></span> <span data-ttu-id="e4a3b-141">タスクのすべてのアクティビティは、Office 365 セキュリティ/コンプライアンスセンターに記録されます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-141">All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![手順 4: Access の処理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="e4a3b-143">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="e4a3b-143">Frequently asked questions</span></span>

### <a name="what-skus-can-use-privileged-access-in-office-365"></a><span data-ttu-id="e4a3b-144">Office 365 では、どの Sku で特権アクセスを使用できますか?</span><span class="sxs-lookup"><span data-stu-id="e4a3b-144">What SKUs can use privileged access in Office 365?</span></span>
<span data-ttu-id="e4a3b-145">特権アクセス管理は、Office 365 E5 および高度なコンプライアンス Sku を使用しているお客様が利用できます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-145">Privileged access management is available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a><span data-ttu-id="e4a3b-146">特権アクセスが Exchange を超えて Office 365 ワークロードをサポートするのはいつですか?</span><span class="sxs-lookup"><span data-stu-id="e4a3b-146">When will privileged access support Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="e4a3b-147">権限のあるアクセス管理は、近日中に他の Office 365 ワークロードで利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-147">Privileged access management will be available in other Office 365 workloads soon.</span></span> <span data-ttu-id="e4a3b-148">詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-148">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) for more details.</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a><span data-ttu-id="e4a3b-149">自分の組織では30以上の特権アクセスポリシーが必要ですが、この制限は増加しますか?</span><span class="sxs-lookup"><span data-stu-id="e4a3b-149">My organization needs more than 30 privileged access policies, will this limit be increased?</span></span>
<span data-ttu-id="e4a3b-150">はい。 Office 365 組織あたりの特権アクセスポリシーの現在の制限は、機能ロードマップにあります。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-150">Yes, raising the current limit of 30 privileged access policies per Office 365 organization is on the feature roadmap.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="e4a3b-151">Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-151">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="e4a3b-152">いいえ。 Office 365 で特権アクセスを管理するアカウントには、Exchange 役割管理役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-152">No, you need the Exchange Role Management role assigned to accounts that manage privileged access in Office 365.</span></span> <span data-ttu-id="e4a3b-153">役割管理役割をスタンドアロンのアカウントアクセス許可として構成しない場合は、グローバル管理者の役割に既定でこの役割が含まれ、特権アクセスを管理できます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-153">If you don’t want to configure the Role Management role as a stand-alone account permission, the Global Administrator role includes this role by default and can manage privileged access.</span></span> <span data-ttu-id="e4a3b-154">承認者のグループに含まれているユーザーは、グローバル管理者である必要がありません。または、要求を確認して承認するための役割管理役割が割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-154">Users included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span>

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="e4a3b-155">お客様のロックボックスに関連する Office 365 での特権アクセス管理について</span><span class="sxs-lookup"><span data-stu-id="e4a3b-155">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="e4a3b-156">[カスタマーロックボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)Microsoft がデータにアクセスするときに、組織に対してレベルのアクセス制御を許可します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-156">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations when Microsoft accesses data.</span></span> <span data-ttu-id="e4a3b-157">Office 365 の特権アクセス管理を使用すると、すべての Office 365 特権タスクに対して、組織内で詳細なアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-157">Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>

## <a name="ready-to-get-started"></a><span data-ttu-id="e4a3b-158">始める準備はいいですか。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-158">Ready to get started?</span></span>

<span data-ttu-id="e4a3b-159">[権限のあるアクセス管理の組織の構成を](privileged-access-management-configuration.md)開始します。</span><span class="sxs-lookup"><span data-stu-id="e4a3b-159">Start [configuring your organization for privileged access management](privileged-access-management-configuration.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="e4a3b-160">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e4a3b-160">Learn more</span></span>

[<span data-ttu-id="e4a3b-161">対話型ガイド: 特権アクセス管理を使用して管理者タスクを監視および制御する</span><span class="sxs-lookup"><span data-stu-id="e4a3b-161">Interactive guide: Monitor and control administrator tasks with privileged access management</span></span>](https://content.cloudguides.com/en-us/guides/Privileged%20Access%20Management)