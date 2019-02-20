---
title: Office 365 での特権アクセス管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Office 365 での特権アクセス管理の詳細については、このトピックを使用してください。
ms.openlocfilehash: 78107ceb497a546ef4d19ba33b8b72ec1406de1b
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090799"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="77885-103">Office 365 での特権アクセス管理</span><span class="sxs-lookup"><span data-stu-id="77885-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77885-104">このトピックでは、Office 365 E5 と Advanced コンプライアンス sku で現在利用可能な機能の展開と構成のガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="77885-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="77885-p101">特権アクセス管理を使用すると、Office 365 の特権のある管理タスクに対して詳細なアクセス制御を行うことができます。機密データへの継続的なアクセス、または重要な構成設定へのアクセスを備えた既存の特権のある管理者アカウントを使用する可能性がある侵害から組織を保護するのに役立ちます。特権アクセス管理を有効にした後、ユーザーは、範囲と時間を制限された承認ワークフローを使用して、昇格された権限のあるタスクを完了するためにジャストインタイムアクセスを要求する必要があります。これにより、機密データや重要な構成設定が危険にさらされることなく、ユーザーにとってすぐにタスクを実行できるだけの余裕が与えられます。Office 365 で特権アクセス管理を有効にすることで、組織はゼロの永続的な権限で運用し、そのような管理アクセスのために発生する脆弱性に対する防御層を提供することができます。</span><span class="sxs-lookup"><span data-stu-id="77885-p101">Privileged access management allows granular access control over privileged admin tasks in Office 365. It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span>

<span data-ttu-id="77885-110">統合された顧客のロックボックスおよび特権アクセス管理のエンドツーエンドのワークフローの概要については、「 [Office 365 ビデオ」の「customer のロックボックスと特権アクセス管理](https://go.microsoft.com/fwlink/?linkid=2066800)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="77885-110">For a quick overview of the integrated Customer Lockbox and privileged access management end-to-end workflow, see this [Customer Lockbox and privileged access management in Office 365 video](https://go.microsoft.com/fwlink/?linkid=2066800).</span></span>

## <a name="layers-of-protection"></a><span data-ttu-id="77885-111">保護レイヤー</span><span class="sxs-lookup"><span data-stu-id="77885-111">Layers of protection</span></span>

<span data-ttu-id="77885-p102">特権アクセス管理は、Office 365 セキュリティアーキテクチャ内の他のデータとアクセス機能の保護を補完します。セキュリティに対する統合アプローチの一部として特権アクセス管理を有効にし、組織を保護することにより、階層型セキュリティモデルを使用して、機密情報および Office 365 の構成設定の保護を最大化することができます。次の図に示すように、特権アクセス管理を有効にすると、office 365 データのネイティブ暗号化、および office 365 サービスのロールベースのアクセス制御セキュリティモデルで提供される保護に基づいて構築できます。[Azure AD 特権 id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と共に使用する場合、この2つの機能により、さまざまなスコープでのジャストインタイムアクセスを備えたアクセス制御が提供されます。</span><span class="sxs-lookup"><span data-stu-id="77885-p102">Privileged access management complements other data and access feature protections within the Office 365 security architecture. By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings. As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services. When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 の階層型の保護](media/pam-layered-protection.png)

<span data-ttu-id="77885-p103">Office 365 での特権アクセス管理は、**タスク**レベルで定義およびスコープ設定できますが、Azure AD 特権 id 管理は、複数のタスクを実行する機能を使用して、**役割**レベルで保護を適用します。 Azure ad の特権 id 管理は、主に AD の役割および役割グループへのアクセスを管理し、Office 365 での特権アクセス管理はタスクレベルでのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="77885-p103">Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.</span></span>

- <span data-ttu-id="77885-119">**Office 365 で特権アクセス管理を有効にしていますが、既に Azure AD 特権 id 管理を使用しています。** office 365 で特権アクセス管理を追加すると、office 365 データへの特権アクセスのための、より詳細な保護および監査機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="77885-119">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="77885-120">**Office 365 で既に特権アクセス管理を使用しているときに、Azure AD 特権 id 管理を有効にする:** office 365 で Azure AD 特権 id 管理を特権アクセス管理に追加すると、主にユーザーのロールまたは id によって定義された office 365 外部のデータへの特権アクセスを拡張できます。</span><span class="sxs-lookup"><span data-stu-id="77885-120">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="77885-121">特権アクセス管理アーキテクチャとプロセスフロー</span><span class="sxs-lookup"><span data-stu-id="77885-121">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="77885-122">次の各プロセスフローは、priveleged アクセスのアーキテクチャと、それが office 365 のサブストレート、office 365 監査、および Exchange 管理実行空間と対話する方法の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="77885-122">Each of the following process flows outline the architecture of priveleged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configuring-a-privileged-access-policy"></a><span data-ttu-id="77885-123">手順 1: 特権アクセスポリシーを構成する</span><span class="sxs-lookup"><span data-stu-id="77885-123">Step 1: Configuring a privileged access policy</span></span>

<span data-ttu-id="77885-p104">office 365 管理センターまたは Exchange 管理 PowerShell のいずれかを使用して特権アクセスポリシーを構成する場合は、ポリシーを作成して定義し、特権アクセス機能が office 365 サブのポリシー属性を処理して、Office 365 セキュリティ/コンプライアンスセンターのアクティビティ。これで、ポリシーが有効になり、承認のための受信要求を処理する準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="77885-p104">When configuring a privileged access policy using either the Office 365 Admin Center or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center. The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![手順 1-ポリシーの作成](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="77885-127">手順 2: アクセス要求</span><span class="sxs-lookup"><span data-stu-id="77885-127">Step 2: Access request</span></span>

<span data-ttu-id="77885-p105">ユーザーは、Office 365 管理センターまたは Exchange 管理 PowerShell を使用して、昇格したタスクまたは権限のあるタスクへのアクセスを要求できます。特権アクセス機能は、構成された特権アクセスポリシーに対して処理するために、office 365 サブストレートに要求を送信し、office 365 のセキュリティおよびコンプライアンスセンターのログに sctivity を記録します。</span><span class="sxs-lookup"><span data-stu-id="77885-p105">Using the Office 365 Admin Center or Exchange Management PowerShell, users can request access to elevated or privileged tasks. The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the sctivity in the Office 365 Security and Compliance Center logs.</span></span>

![手順 2-アクセス要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="77885-131">手順 3: アクセスの承認</span><span class="sxs-lookup"><span data-stu-id="77885-131">Step 3: Access approval</span></span>

<span data-ttu-id="77885-p106">承認要求が生成され、保留中の要求の電子メールによって承認グループに通知されます。承認が付与されている場合、特権アクセス要求は承認として処理され、タスクを完了する準備ができています。要求が拒否された場合、タスクはブロックされ、reqeustor へのアクセスは許可されません。送信者は、電子メールメッセージを使用して、要求の承認または拒否を通知されます。</span><span class="sxs-lookup"><span data-stu-id="77885-p106">An approval request is generated and the approval group is notified by email of the pending request. If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed. If the request is denied, task is blocked and no access is granted to the reqeustor. The requestor will be notified of the request approval or denial via email message.</span></span>

![ステップ 3-アクセス承認](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="77885-137">手順 4: Access の処理</span><span class="sxs-lookup"><span data-stu-id="77885-137">Step 4: Access processing</span></span>

<span data-ttu-id="77885-p107">承認済みの要求の場合、タスクは Exchange 管理実行空間によって処理されます。承認は、特権アクセスポリシーに照らしてチェックされ、Office 365 のサブストレートによって処理されます。タスクのすべてのアクティビティは、Office 365 セキュリティ/コンプライアンスセンターに記録されます。</span><span class="sxs-lookup"><span data-stu-id="77885-p107">For approved requests, the task is processed by the Exchange Management runspace. The approval is checked against the privileged access policy and processed by the Office 365 substrate. All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![ステップ 4-アクセス処理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="77885-142">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="77885-142">Frequently asked questions</span></span>

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a><span data-ttu-id="77885-143">Office 365 で特権アクセスを使用するために必要な sku</span><span class="sxs-lookup"><span data-stu-id="77885-143">What SKUs do I need to use privileged access in Office 365?</span></span>
<span data-ttu-id="77885-144">特権アクセス管理は、現在、Office 365 E5 および高度なコンプライアンス sku を使用しているお客様のみが利用できます。</span><span class="sxs-lookup"><span data-stu-id="77885-144">Privileged access management is currently only available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a><span data-ttu-id="77885-145">Exchange を超えて Office 365 ワークロードで特権アクセスを使用できるようになるのはいつですか?</span><span class="sxs-lookup"><span data-stu-id="77885-145">When will privileged access be available for Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="77885-p108">この機能は、近日中に他の Office 365 ワークロードに提供する予定です。タイムラインを共有する準備ができたら、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="77885-p108">We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a><span data-ttu-id="77885-148">自分の組織では、30以上の特権アクセスポリシーが必要ですが、この制限は増加しますか?</span><span class="sxs-lookup"><span data-stu-id="77885-148">My organization needs more than 30 privileged access polices, will this limit be increased?</span></span>

<span data-ttu-id="77885-149">現時点では、Office 365 組織あたり30の特権アクセスポリシーの現在の制限をさらに増加する予定です。</span><span class="sxs-lookup"><span data-stu-id="77885-149">We're planning to increase the current limit of 30 privileged access policies per Office 365 organization soon.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="77885-150">Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="77885-150">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="77885-p109">いいえ。 Office 365 で特権アクセスを管理するアカウントには、Exchange の役割管理の役割を割り当てる必要があります。ただし、グローバル管理者の役割にはこの役割が既定で含まれており、役割管理の役割をスタンドアロンのアカウントのアクセス許可として構成しない場合に、特権アクセスを管理するために使用できます。承認者のグループに含まれているユーザーは、グローバル管理者である必要がありません。または、要求を確認して承認するための役割管理役割を割り当てられている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="77885-p109">No, you need to have the Exchange Role Management role assigned to accounts that will manage privileged access in Office 365. However, the Global Administrator role includes this role by default and can be used to manage privileged access if you don’t want to configure the Role Management role as a stand-alone account permission. Users who are included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span> 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="77885-154">お客様のロックボックスに関連する Office 365 での特権アクセス管理について</span><span class="sxs-lookup"><span data-stu-id="77885-154">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="77885-p110">[カスタマーロックボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)を使用すると、組織がサービスプロバイダー (Microsoft など) からデータにアクセスするためのレベルのアクセス制御を行うことができます。office 365 の特権アクセス管理を使用すると、すべての office 365 特権タスクに対して、組織内で詳細なアクセス制御を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="77885-p110">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>
