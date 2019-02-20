---
title: Office 365 での特権アクセス管理の構成
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
description: Office 365 での特権アクセス管理の構成の詳細については、このトピックを使用してください。
ms.openlocfilehash: 63780da59afb245b35916a1e7a5b2eb780d535a8
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090919"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="f1b75-103">Office 365 での特権アクセス管理の構成</span><span class="sxs-lookup"><span data-stu-id="f1b75-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1b75-104">このトピックでは、Office 365 E5 と Advanced コンプライアンス sku で現在利用可能な機能の展開と構成のガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="f1b75-p101">このトピックでは、Office 365 組織で特権アクセス管理を有効にして構成する方法について説明します。Microsoft 365 管理センターまたは Exchange 管理 PowerShell のいずれかを使用して、特権アクセスを管理および使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="f1b75-107">特権アクセス管理を有効にして構成する</span><span class="sxs-lookup"><span data-stu-id="f1b75-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="f1b75-108">Office 365 組織で特権アクセスをセットアップして使用するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="f1b75-109">手順 1: 承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="f1b75-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="f1b75-p102">特権アクセスの使用を開始する前に、昇格されたタスクと特権タスクへのアクセスのための受信要求に対して、誰がだれに承認権限を付与するかを決定します。承認者グループの一部であるユーザーは、アクセス要求を承認できます。これは、Office 365 でメールが有効なセキュリティグループを作成することによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="f1b75-113">手順 2: 特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="f1b75-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="f1b75-114">既定の承認者グループを使用して Office 365 で特権アクセスを明示的に有効にする必要があります。また、特権アクセス管理アクセス制御から除外する必要があるシステムアカウントのセットを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b75-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="f1b75-115">手順 3: アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f1b75-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="f1b75-p103">承認ポリシーを作成すると、個々のタスクでスコープを設定する特定の承認要件を定義できます。承認の種類のオプションは**自動**または**手動**です。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="f1b75-118">手順 4: 特権アクセス要求を送信/承認する</span><span class="sxs-lookup"><span data-stu-id="f1b75-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="f1b75-p104">有効にした場合、関連付けられた承認ポリシーが定義されているタスクを実行するには、権限のあるアクセス権が必要です。承認ポリシーに含まれるタスクを実行する必要があるユーザーは、タスクを実行するために必要なアクセス許可を付与するために、要求してアクセス承認を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="f1b75-p105">承認が付与されると、要求元のユーザーは目的のタスクを実行できるようになり、特権アクセスはユーザーの代わりにタスクを承認して実行します。承認は、要求された期間 (既定の期間は4時間) に対して有効なままとなり、要求者は目的のタスクを複数回実行できます。このような実行はすべてログに記録され、セキュリティとコンプライアンスの監査に使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="f1b75-p106">exchange 管理 powershell を使用して特権アクセスを有効にし、構成する場合は、「[複数要素認証を使用して exchange online powershell に](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)接続する」の手順に従って、Office 365 を使用して exchange online powershell に接続します。クリデンシャル.Office 365 組織に対して多要素認証を有効にして、Exchange Online PowerShell への接続中に特権アクセスを有効にする手順を使用する必要はありません。多要素認証を使用して接続すると、要求に署名するために特権アクセスで使用される OAuth トークンが作成されます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="f1b75-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="f1b75-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="f1b75-128">手順 1-承認者のグループを作成する</span><span class="sxs-lookup"><span data-stu-id="f1b75-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="f1b75-129">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f1b75-130">管理センターで、[グループ\*\*\*\* > **の追加]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="f1b75-131">メールが**有効なセキュリティグループ**グループの種類を選択し、新しいグループの**名前**、**グループ電子メールアドレス**、および**説明**フィールドを入力します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="f1b75-p107">グループを保存します。グループが完全に構成され、Office 365 管理センターに表示されるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="f1b75-134">新しい承認者のグループを選択し、[**編集**] を選択してグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="f1b75-135">グループを保存します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-135">Save the group.</span></span>

<span data-ttu-id="f1b75-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="f1b75-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="f1b75-137">手順 2-特権アクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="f1b75-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-138">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-139">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f1b75-140">管理センターで、[**設定 > セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-141">[**特権アクセス制御の承認を必須**にする] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="f1b75-142">手順1で作成した承認者のグループを**既定の承認者グループ**として割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="f1b75-143">**保存**して**閉じ**ます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-144">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-145">Exchange Online PowerShell で次のコマンドを実行して、特権アクセスを有効にし、承認者のグループを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="f1b75-146">例:</span><span class="sxs-lookup"><span data-stu-id="f1b75-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="f1b75-147">システムアカウント機能を使用して、組織内の特定のオートメーションが特権アクセスに依存せずに機能できるようにすることができます。ただし、このような除外は例外的に行うことをお勧めします。普段は。</span><span class="sxs-lookup"><span data-stu-id="f1b75-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="f1b75-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="f1b75-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="f1b75-149">手順 3-アクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="f1b75-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="f1b75-150">Office 365 組織に対して最大30の特権アクセスポリシーを作成し、構成することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-151">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-152">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f1b75-153">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-154">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f1b75-155">[**ポリシーの構成**] を選択し、[**ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="f1b75-156">ドロップダウンフィールドで、組織に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="f1b75-157">**ポリシーの種類**: タスク、役割、または役割グループ</span><span class="sxs-lookup"><span data-stu-id="f1b75-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="f1b75-158">**ポリシースコープ**: Exchange または Office 365</span><span class="sxs-lookup"><span data-stu-id="f1b75-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="f1b75-159">**ポリシー名**: 使用可能なポリシーから選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="f1b75-160">**承認の種類**: 手動または自動</span><span class="sxs-lookup"><span data-stu-id="f1b75-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="f1b75-161">**承認グループ**: 手順1で作成した承認者グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="f1b75-p108">[**作成**] を選択し、[**閉じる**] をクリックします。ポリシーが完全に構成され、有効になるまでに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-164">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-165">Exchange Online PowerShell で次のコマンドを実行して、承認ポリシーを作成および定義します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="f1b75-166">例:</span><span class="sxs-lookup"><span data-stu-id="f1b75-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="f1b75-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="f1b75-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="f1b75-168">手順 4: 特権アクセス要求を送信/承認する</span><span class="sxs-lookup"><span data-stu-id="f1b75-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="f1b75-169">権限タスクを実行するための昇格承認の要求</span><span class="sxs-lookup"><span data-stu-id="f1b75-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="f1b75-p109">特権アクセスの要求は、要求が送信されてから最大24時間有効です。承認または拒否されていない場合、要求は期限切れになり、アクセスは承認されません。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-172">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-173">資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="f1b75-174">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-175">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f1b75-p110">[**新しい要求**] を選択します。ドロップダウンフィールドで、組織に適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="f1b75-178">**要求の種類**: タスク、役割、または役割グループ</span><span class="sxs-lookup"><span data-stu-id="f1b75-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="f1b75-179">**要求スコープ**: Exchange</span><span class="sxs-lookup"><span data-stu-id="f1b75-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="f1b75-180">**要求**: 使用可能なポリシーから選択します</span><span class="sxs-lookup"><span data-stu-id="f1b75-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="f1b75-p111">**期間 (時間)**: 要求されたアクセスの時間数。要求可能な時間数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="f1b75-183">**comments**: アクセス要求に関連するコメントのテキストフィールド</span><span class="sxs-lookup"><span data-stu-id="f1b75-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="f1b75-p112">[**保存**] を選択し、[**閉じる**] をクリックします。要求は、電子メールを介して承認者のグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-186">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-187">Exchange Online PowerShell で次のコマンドを実行して、承認要求を作成し、承認者のグループに送信します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="f1b75-188">例:</span><span class="sxs-lookup"><span data-stu-id="f1b75-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="f1b75-189">昇格要求の状態を表示する</span><span class="sxs-lookup"><span data-stu-id="f1b75-189">View status of elevation requests</span></span>
<span data-ttu-id="f1b75-190">承認要求が作成されると、昇格要求の状態は、管理センターまたは Exchange 管理 PowerShell で、関連付けられている要求 ID を使用して確認できます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-191">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-192">資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="f1b75-193">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-194">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f1b75-195">[**表示**] を選択して、送信された要求を**保留**、**承認**、**拒否**、または**顧客のロックボックス**の状態でフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-196">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-197">Exchange Online PowerShell で次のコマンドを実行して、特定の要求 ID の承認要求の状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="f1b75-198">例:</span><span class="sxs-lookup"><span data-stu-id="f1b75-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="f1b75-199">昇格認証要求を承認する</span><span class="sxs-lookup"><span data-stu-id="f1b75-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="f1b75-p113">承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知を受信し、要求 ID に関連付けられている要求を承認できます。送信者は、電子メールメッセージを使用して、要求の承認または拒否を通知されます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-202">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-203">資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="f1b75-204">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-205">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f1b75-206">詳細を表示し、要求に対してアクションを実行するには、リストされている要求を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="f1b75-p114">[**承認**] を選択して要求を承認するか、[**拒否**] を選択して要求を拒否します。以前に承認された要求では、 **Revoke**を選択することによってアクセスを取り消すことができます</span><span class="sxs-lookup"><span data-stu-id="f1b75-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-209">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-210">Exchange Online PowerShell で次のコマンドを実行して、昇格認証要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="f1b75-211">例:</span><span class="sxs-lookup"><span data-stu-id="f1b75-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="f1b75-212">Exchange Online PowerShell で次のコマンドを実行して、昇格認証要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="f1b75-213">例:</span><span class="sxs-lookup"><span data-stu-id="f1b75-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="f1b75-214">Office 365 で特権アクセスポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="f1b75-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="f1b75-215">組織で不要になった場合は、特権アクセスポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="f1b75-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-216">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-217">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f1b75-218">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-219">[**アクセスポリシーと要求の管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="f1b75-220">[**構成ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="f1b75-221">削除するポリシーを選択し、[ポリシーの**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="f1b75-222">[**閉じる**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-223">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-224">Exchange Online Powershell で次のコマンドを実行して、特権アクセスポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="f1b75-225">Office 365 で特権アクセスを無効にする</span><span class="sxs-lookup"><span data-stu-id="f1b75-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="f1b75-p115">必要に応じて、組織の特権アクセス管理を無効にすることができます。特権アクセスを無効にしても、関連付けられている承認ポリシーまたは承認グループは削除されません。</span><span class="sxs-lookup"><span data-stu-id="f1b75-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="f1b75-228">Microsoft 365 管理センターの使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="f1b75-229">組織内の管理者アカウントの資格情報を使用して、 [Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="f1b75-230">管理センターで、[**設定** > **セキュリティ & プライバシー** > **特権アクセス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f1b75-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="f1b75-231">[**特権アクセス制御の承認を必須**にする] を有効にします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="f1b75-232">Exchange 管理 PowerShell の使用</span><span class="sxs-lookup"><span data-stu-id="f1b75-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="f1b75-233">Exchange Online Powershell で次のコマンドを実行して、特権アクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="f1b75-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```