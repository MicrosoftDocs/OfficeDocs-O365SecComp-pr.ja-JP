---
title: 特権にアクセス、Office 365 の管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: 権限に関する詳細については、このトピックを使用して Office 365 の管理のアクセス
ms.openlocfilehash: f3cd5fb263fe3bb83d60a7938f0e22dc38f199e3
ms.sourcegitcommit: b0b0b716718c22779c7c04775b8010d65cd6656b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2019
ms.locfileid: "28723234"
---
# <a name="privileged-access-management-in-office-365"></a><span data-ttu-id="6d1f4-103">特権にアクセス、Office 365 の管理</span><span class="sxs-lookup"><span data-stu-id="6d1f4-103">Privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6d1f4-104">このトピックでは、Office 365 の E5 と高度なコンプライアンスの Sku でのみ現在利用できる機能の展開と構成のガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="6d1f4-p101">管理者アクセス権を Office 365 の管理により、きめ細かなアクセス特権の管理タスクを制御します。機密性の高いデータへのアクセスを位置または重要な構成設定へのアクセス権を持つ既存の権限を持つ管理者アカウントを使用するための侵害から組織を保護するために役立ちます。アクセス権限の管理を有効にすると、ユーザーは、承認のワークフローは、高度なスコープ設定と期限付きでの管理者特権、特権のあるタスクを完了する、ジャスト ・ イン ・ タイムのアクセス権を要求する必要があります。これにより、ユーザーだけからだけアクセスできる機密データや重要な構成設定の露出を危険にさらさず、当面のタスクを実行します。Office 365 にアクセス権限の管理を有効にすると、ゼロ位置の特権で実行され、このような地位の管理アクセスのために起因する脆弱性に対する防御層を提供する組織が有効になります。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p101">Privileged access management allows granular access control over privileged admin tasks in Office 365. It can help protect your organization from breaches that may use existing privileged admin accounts with standing access to sensitive data or access to critical configuration settings. After enabling privileged access management, users will need to request just-in-time access to complete elevated and privileged tasks through an approval workflow that is highly scoped and time-bound. This gives users just-enough-access to perform the task at hand, without risking exposure of sensitive data or critical configuration settings. Enabling privileged access management in Office 365 will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access.</span></span> 

## <a name="layers-of-protection"></a><span data-ttu-id="6d1f4-110">レイヤーの保護</span><span class="sxs-lookup"><span data-stu-id="6d1f4-110">Layers of protection</span></span>

<span data-ttu-id="6d1f4-p102">管理者アクセス権の管理は、Office 365 のセキュリティ ・ アーキテクチャ内で他のデータとアクセスの機能保護を補完するものです。セキュリティに統合されたアプローチの一部としてのアクセス権限の管理を有効にすると、組織を保護、機密性の高い情報と Office 365 の構成設定の保護を最大化する階層型のセキュリティ モデルを使用できます。特権を有効にする、次の図に示すように Office 365 のデータのネイティブの暗号化と Office 365 サービスの役割に基づいたアクセス制御のセキュリティ モデルで提供される保護のアクセス管理の支援を構築します。[Azure AD 管理者の Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と連携して使用する場合、これら 2 つの機能は、さまざまなスコープでジャスト ・ イン ・ タイムのアクセスとアクセス制御を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p102">Privileged access management complements other data and access feature protections within the Office 365 security architecture. By enabling privileged access management as part of an integrated approach to security and protecting your organization, a layered security model can be used to maximize protection of sensitive information and Office 365 configuration settings. As shown in the diagram below, enabling privileged access management helps builds on the protection provided with native encryption of Office 365 data and the role based access control security model of Office 365 services. When used in conjunction with [Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure), these two features provide access control with just-in-time access at different scopes.</span></span>

![Office 365 の階層型の保護](media/pam-layered-protection.png)

<span data-ttu-id="6d1f4-p103">管理者アクセス権を Office 365 の管理を定義し、Azure AD 管理者の Id 管理が複数のタスクを実行する機能を持つ**ロール**レベルでの保護を適用中に、**タスク**レベルのスコープです。 Azure AD 特権 Id 管理主に AD の役割と役割グループのアクセスを管理する、タスク レベルでのみ Office 365 の管理が適用される権限にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p103">Privileged access management in Office 365 can be defined and scoped at the **task** level, while Azure AD Privileged Identity Management applies protection at the **role** level with the ability to execute multiple tasks.  Azure AD Privileged Identity Management primarily allows managing accesses for AD roles and role groups, while privileged access management in Office 365 is applied only at the task level.</span></span>

- <span data-ttu-id="6d1f4-118">**特権を有効にする既に Azure AD 管理者の Id 管理を使用しているときに Office 365 の管理のアクセス:** Office 365 にアクセス権限の管理を追加する別の Office 365 のデータへのアクセス権限の保護と監査の機能の細分化された層を提供します。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-118">**Enabling privileged access management in Office 365 while already using Azure AD Privileged Identity Management:** Adding privileged access management in Office 365 provides another granular layer of protection and audit capabilities for privileged access to Office 365 data.</span></span>

- <span data-ttu-id="6d1f4-119">**を既に使用しているときに、Azure AD の特権の有効にすると Id 管理特権を Office 365 にアクセス管理:** Azure AD 管理者の Id 管理を追加する特権を Office 365 でのアクセス管理は、Office 365 ユーザーのロールまたは id によって主に定義されている外部データへのアクセス権限を拡張できます。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-119">**Enabling Azure AD Privileged Identity Management while already using privileged access management in Office 365:**  Adding Azure AD Privileged Identity Management to privileged access management in Office 365 can extend privileged access to data outside of Office 365 that’s primarily defined by a user’s role or identity.</span></span>  

## <a name="privileged-access-management-architecture-and-process-flow"></a><span data-ttu-id="6d1f4-120">アクセス権限管理のアーキテクチャとプロセスのフロー</span><span class="sxs-lookup"><span data-stu-id="6d1f4-120">Privileged access management architecture and process flow</span></span>

<span data-ttu-id="6d1f4-121">次のプロセス ・ フローの各権限の少ないアクセスし、Office 365 の基板、Office 365 は、次の監査、および Exchange の管理の実行空間との対話方法のアーキテクチャの概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-121">Each of the following process flows outline the architecture of priveleged access and how it interacts with the Office 365 substrate, Office 365 auditing, and the Exchange Management runspace.</span></span>

### <a name="step-1-configuring-a-privileged-access-policy"></a><span data-ttu-id="6d1f4-122">手順 1: 管理者のアクセス ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="6d1f4-122">Step 1: Configuring a privileged access policy</span></span>

<span data-ttu-id="6d1f4-p104">特権アクセス機能は、Office 365 の基板とログのポリシーの属性を処理および作成し、ポリシーを定義する、Office 365 管理者センターまたは Exchange 管理の PowerShell を使用してアクセス権限ポリシーを構成するとき、Office 365 のセキュリティとコンプライアンス センターでの活動です。ポリシーが有効になりますし、承認のための着信要求を処理する準備ができています。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p104">When configuring a privileged access policy using either the Office 365 Admin Center or Exchange Management PowerShell, you create and define the policy and the privileged access feature processes the policy attributes in the Office 365 substrate and logs the activity in the Office 365 Security and Compliance Center. The policy is now enabled and ready to handle incoming requests for approvals.</span></span>

![ステップ 1 - ポリシーの作成](media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a><span data-ttu-id="6d1f4-126">手順 2: アクセス権の要求</span><span class="sxs-lookup"><span data-stu-id="6d1f4-126">Step 2: Access request</span></span>

<span data-ttu-id="6d1f4-p105">Office 365 管理センターまたは Exchange 管理 PowerShell を使用すると、ユーザーは管理者特権または管理者のタスクへのアクセスを要求できます。特権アクセス機能は、Office 365 基板に対して構成されている特権のアクセス ポリシーの処理のために要求を送信し、Office 365 のセキュリティでは、sctivity を記録し、コンプライアンス センターをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p105">Using the Office 365 Admin Center or Exchange Management PowerShell, users can request access to elevated or privileged tasks. The privileged access feature sends the request to the Office 365 substrate for processing against the configured privilege access policy and records the sctivity in the Office 365 Security and Compliance Center logs.</span></span>

![ステップ 2 - アクセス権の要求](media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a><span data-ttu-id="6d1f4-130">手順 3: アクセスの承認</span><span class="sxs-lookup"><span data-stu-id="6d1f4-130">Step 3: Access approval</span></span>

<span data-ttu-id="6d1f4-p106">承認要求が生成され、承認グループに保留中の要求の電子メールで通知されます。承認が付与される場合は、承認とアクセス権限要求を処理し、タスクを完了する準備ができました。要求が拒否された場合は、タスクがブロックされているし、reqeustor へのアクセスは許可されません。要求者の要求の承認または拒否メッセージを電子メール経由で通知されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p106">An approval request is generated and the approval group is notified by email of the pending request. If approval is granted, the privileged access request is processed as an approval and the task is ready to be completed. If the request is denied, task is blocked and no access is granted to the reqeustor. The requestor will be notified of the request approval or denial via email message.</span></span>

![ステップ 3 - アクセスの承認](media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a><span data-ttu-id="6d1f4-136">手順 4: アクセスの処理</span><span class="sxs-lookup"><span data-stu-id="6d1f4-136">Step 4: Access processing</span></span>

<span data-ttu-id="6d1f4-p107">承認された要求は、Exchange の管理の実行空間で、タスクが処理されます。承認はアクセス権限ポリシーに照らしてチェックや、Office 365 の基板で処理します。Office 365 のセキュリティとコンプライアンスのセンターでは、タスクのすべてのアクティビティが記録されます。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p107">For approved requests, the task is processed by the Exchange Management runspace. The approval is checked against the privileged access policy and processed by the Office 365 substrate. All activity for the task is logged in the Office 365 Security and Compliance Center.</span></span>

![ステップ 4 - アクセスの処理](media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a><span data-ttu-id="6d1f4-141">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="6d1f4-141">Frequently asked questions</span></span>

### <a name="what-skus-do-i-need-to-use-privileged-access-in-office-365"></a><span data-ttu-id="6d1f4-142">Office 365 にアクセス権限を使用する必要があるどのような Sku をしますか。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-142">What SKUs do I need to use privileged access in Office 365?</span></span>
<span data-ttu-id="6d1f4-143">管理者アクセス権管理は、現在のみ向け Office 365 の E5 と高度なコンプライアンスの Sku を使用します。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-143">Privileged access management is currently only available for customers with Office 365 E5 and Advanced Compliance SKUs.</span></span>

### <a name="when-will-privileged-access-be-available-for-office-365-workloads-beyond-exchange"></a><span data-ttu-id="6d1f4-144">特権を持つアクセス可能になります Exchange 以外の Office 365 の作業負荷でしょうか。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-144">When will privileged access be available for Office 365 workloads beyond Exchange?</span></span>
<span data-ttu-id="6d1f4-p108">その他の Office 365 のワークロードでは、この機能をすぐに提供する予定です。タイムラインを共有する準備ができました、 [365 のロードマップを Microsoft](https://www.microsoft.com/microsoft-365/roadmap)から利用可能ながあります。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p108">We plan to offer this feature in other Office 365 workloads soon. When we’re ready to share a timeline, it will be available through the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap).</span></span>

### <a name="my-organization-needs-more-than-30-privileged-access-polices-will-this-limit-be-increased"></a><span data-ttu-id="6d1f4-147">ポリシーを自分の組織のニーズが 30 のアクセス権限よりも、この制限値は増加するでしょうか。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-147">My organization needs more than 30 privileged access polices, will this limit be increased?</span></span>

<span data-ttu-id="6d1f4-148">すぐに Office 365 の組織ごとの 30 のアクセス権限ポリシーの現在の制限値を大きくには計画されています。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-148">We're planning to increase the current limit of 30 privileged access policies per Office 365 organization soon.</span></span>

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a><span data-ttu-id="6d1f4-149">Office 365 の管理者のアクセスを管理するためのグローバル管理者である必要がありますか。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-149">Do I need to be a Global Admin to manage privileged access in Office 365?</span></span>
<span data-ttu-id="6d1f4-p109">残念ですが、Office 365 の管理者のアクセスを管理するアカウントに割り当てられている Exchange の役割の管理役割を持っている必要があります。ただし、グローバル管理者ロールは既定でこのロールが含まれていて、スタンドアロンのアカウントのアクセス許可と役割の管理役割を構成したくない場合は、アクセス権限を管理するために使用することができます。承認者のグループに含まれるユーザーをグローバル管理者であるかを確認し、要求の承認に割り当てられている役割の管理役割を持っている必要はありません。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p109">No, you need to have the Exchange Role Management role assigned to accounts that will manage privileged access in Office 365. However, the Global Administrator role includes this role by default and can be used to manage privileged access if you don’t want to configure the Role Management role as a stand-alone account permission. Users who are included in an approvers’ group don't need to be a Global Admin or have the Role Management role assigned to review and approve requests.</span></span> 

### <a name="how-is-privileged-access-management-in-office-365-related-to-customer-lockbox"></a><span data-ttu-id="6d1f4-153">ロック ボックスの顧客に関連する Office 365 にアクセス権限の管理ですか。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-153">How is privileged access management in Office 365 related to Customer Lockbox?</span></span>
<span data-ttu-id="6d1f4-p110">[お客様のロック ボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests)は、組織では、サービス プロバイダー、つまり Microsoft によってデータにアクセスするためのアクセス制御のレベルを使用できます。管理者アクセス権をすべての Office 365 の管理者権限を持って作業を組織内で、きめ細かなアクセス制御により、Office 365 の管理。</span><span class="sxs-lookup"><span data-stu-id="6d1f4-p110">[Customer Lockbox](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) allows a level of access control for organizations for access to to data by their service provider, i.e. Microsoft. Privileged access management in Office 365 allows granular access control within an organization for all Office 365 privileged tasks.</span></span>
