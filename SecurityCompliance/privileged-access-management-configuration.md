---
title: Office 365 にアクセス権限の管理を構成します。
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
description: このトピックを使用して、Office 365 にアクセス権限の管理を構成する方法の詳細については、
ms.openlocfilehash: 47cae93a41b0fd60645021f6f299645777a9a2e1
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25011843"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="08ddf-103">Office 365 にアクセス権限の管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08ddf-104">このトピックでは、Office 365 の E5 と高度なコンプライアンスの Sku でのみ現在利用できる機能の展開と構成のガイダンスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="08ddf-p101">このトピックでは有効にし、Office 365 の組織内のアクセス権限の管理について説明します。いずれかの方法を使用することができます、管理者アクセス権を管理および使用するには、365 の管理窓口または Exchange 管理 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="08ddf-107">有効にして、アクセス権限の管理を構成します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="08ddf-108">設定し、Office 365 の組織内のアクセス権限を使用してこれらの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="08ddf-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="08ddf-109">手順 1: 承認者のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="08ddf-p102">特権アクセスの使用を開始する前に、管理者特権、特権を持つタスクにアクセスするための着信方向の要求の承認権限を持ってことを確認します。承認者グループの一部になっているユーザーはアクセス権の要求を承認することになります。これは、Office 365 のメールが有効なセキュリティ グループを作成することによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="08ddf-113">手順 2: アクセス権限を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="08ddf-114">アクセス権限を明示的にオンにする Office 365 の既定の承認者グループとアクセス権限の管理アクセスの制御から除外することがシステム アカウントのセットを含む必要があります。</span><span class="sxs-lookup"><span data-stu-id="08ddf-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="08ddf-115">アクセス ポリシーを作成する手順 3。</span><span class="sxs-lookup"><span data-stu-id="08ddf-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="08ddf-p103">承認ポリシーを作成すると、個々 のタスクのスコープの特定の承認要件を定義できます。承認の種類のオプションは、**自動**または**手動**です。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="08ddf-118">ステップ 4: 送信とアクセス権限の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="08ddf-p104">いったん有効に、特権を持つアクセスでは、定義されている関連する承認ポリシーを持つ任意のタスクを実行するための承認が必要です。含まれているタスクを実行するために必要とするユーザーの承認ポリシーが要求する必要があり、タスクを実行するために必要なアクセス許可を持つために、アクセスの承認を付与します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="08ddf-p105">承認を付与すると、要求元のユーザーは、目的のタスクを実行できるとアクセス権限は承認され、ユーザーの代わりにタスクを実行します。承認は、要求の有効期間 (既定の期間は、4 時間) 中に、依頼者が目的のタスクを複数回実行します。このようなすべての実行はログに記録したり、セキュリティとコンプライアンスの監査に使用可能です。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="08ddf-p106">Exchange 管理 PowerShell を使用して、有効にしてアクセス権限を構成する場合は、以下の[Exchange オンライン PowerShell への接続は、多要素認証を使用して](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)Office 365 のオンライン PowerShell を Exchange に接続するための手順資格情報です。オンライン PowerShell を Exchange に接続中にアクセス権限を有効にする手順を使用する Office 365 の組織の多要素認証を有効にする必要はありません。多要素認証で接続する、要求に署名するためのアクセス権限で使用される、OAuth トークンを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="08ddf-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="08ddf-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="08ddf-128">手順 1 - 承認者のグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="08ddf-129">組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="08ddf-130">**グループ**には、管理センターで、 > **グループを追加**します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="08ddf-131">**メールが有効なセキュリティ グループ**のグループの種類を選択し、し、新しいグループの**名前**、**グループの電子メール アドレス**、および**説明**のフィールドを完了します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="08ddf-p107">グループを保存します。グループを完全に構成して、Office 365 の管理ページに表示するのに数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="08ddf-134">新しい承認者のグループを選択し、グループにユーザーを追加するのには**編集**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="08ddf-135">グループを保存します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-135">Save the group.</span></span>

<span data-ttu-id="08ddf-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="08ddf-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="08ddf-137">手順 2 - アクセス権限を有効にします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-138">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-139">組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="08ddf-140">移動、管理センターで、**の設定 > セキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-141">**アクセス権限の承認を必要とする**コントロールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="08ddf-142">の**既定の承認者グループ**に手順 1 で作成した承認者のグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="08ddf-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="08ddf-143">**保存**して**閉じます**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-144">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-145">アクセス権限を有効にして、承認者のグループを割り当てるには、Exchange オンライン PowerShell で次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="08ddf-146">例:</span><span class="sxs-lookup"><span data-stu-id="08ddf-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="08ddf-147">システム アカウントの機能は、組織内の特定の自動化を確実に使用可能になりますが、アクセス権限の依存関係を持たない作業できますを推奨するこのような除外される例外的な許可承認および監査する必要があります。普段は。</span><span class="sxs-lookup"><span data-stu-id="08ddf-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="08ddf-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="08ddf-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="08ddf-149">手順 3 - アクセス ポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="08ddf-150">作成し、Office 365 の組織に最大 30 個までの特権のアクセス ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="08ddf-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-151">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-152">組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="08ddf-153">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-154">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="08ddf-155">**ポリシーを構成する**を選択し、[**ポリシーの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="08ddf-156">ドロップ ダウン フィールドから、組織の適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="08ddf-157">**ポリシーの種類**: タスク、ロール、またはロールのグループ</span><span class="sxs-lookup"><span data-stu-id="08ddf-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="08ddf-158">**ポリシーのスコープ**: Exchange または Office 365</span><span class="sxs-lookup"><span data-stu-id="08ddf-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="08ddf-159">**ポリシー名**: 使用可能なポリシーから選択</span><span class="sxs-lookup"><span data-stu-id="08ddf-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="08ddf-160">**承認タイプ**: 手動または自動</span><span class="sxs-lookup"><span data-stu-id="08ddf-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="08ddf-161">**承認グループ**: ステップ 1 で作成した承認者のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="08ddf-p108">**作成**し、[**閉じる**を選択します。ポリシーを完全に構成し、有効にするのには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-164">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-165">次のコマンドを実行 Exchange オンライン PowerShell を作成し、承認ポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="08ddf-166">例:</span><span class="sxs-lookup"><span data-stu-id="08ddf-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="08ddf-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="08ddf-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="08ddf-168">ステップ 4: 送信とアクセス権限の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="08ddf-169">特権付きタスクを実行する昇格の承認を要求します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="08ddf-p109">アクセス権限の要求は、要求の送信後 24 時間まで有効です。要求の有効期限が切れる場合はありませんが承認または拒否、およびアクセスが承認されていません。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-172">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-173">ユーザーの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="08ddf-174">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-175">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="08ddf-p110">**新しい要求**を選択します。ドロップ ダウン フィールドから、組織の適切な値を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="08ddf-178">**要求の種類**: タスク、ロール、またはロールのグループ</span><span class="sxs-lookup"><span data-stu-id="08ddf-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="08ddf-179">**要求スコープ**: Exchange</span><span class="sxs-lookup"><span data-stu-id="08ddf-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="08ddf-180">**要求**: 使用可能なポリシーから選択</span><span class="sxs-lookup"><span data-stu-id="08ddf-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="08ddf-p111">**期間 (時間)**: 要求されたアクセスの時間数。要求できる時間数に制限はありません。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="08ddf-183">**コメント**: コメントのテキスト フィールドは、アクセス権の要求に関連します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="08ddf-p112">**保存**し、**閉じる**を選択します。要求は、電子メールでの承認者のグループに送信されます。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-186">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-187">次のコマンドを実行 Exchange オンライン PowerShell を作成し、承認者のグループに承認依頼を送信します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="08ddf-188">例:</span><span class="sxs-lookup"><span data-stu-id="08ddf-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="08ddf-189">昇格の要求のステータスを表示</span><span class="sxs-lookup"><span data-stu-id="08ddf-189">View status of elevation requests</span></span>
<span data-ttu-id="08ddf-190">承認要求が作成されると、管理センターには、昇格の要求の状態を確認できますか、Exchange 管理の PowerShell で使用する、関連付けられている要求の id。</span><span class="sxs-lookup"><span data-stu-id="08ddf-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-191">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-192">ユーザーの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="08ddf-193">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-194">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="08ddf-195">**保留中**の、**承認**、**拒否**、または**お客様のロック ボックス**の状態で送信された要求をフィルター処理する**ビュー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-196">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-197">次のコマンドを実行 Exchange オンライン PowerShell は、特定の要求 ID の承認の要求の状態を表示するのには。</span><span class="sxs-lookup"><span data-stu-id="08ddf-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="08ddf-198">例:</span><span class="sxs-lookup"><span data-stu-id="08ddf-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="08ddf-199">昇格の承認要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="08ddf-p113">承認要求が作成されると、関連する承認者グループのメンバーは電子メール通知が表示され、要求 ID に関連付けられている要求を承認することができます。要求者の要求の承認または拒否メッセージを電子メール経由で通知されます。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-202">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-203">ユーザーの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="08ddf-204">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-205">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="08ddf-206">一覧表示されている要求の詳細を表示するのには、要求の操作を実行するを選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="08ddf-p114">要求を承認するか要求を拒否する**拒否**を選択するのには、**承認**を選択します。以前承認された要求は、失効**を取り消す**かを選択してアクセスを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-209">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-210">次のコマンドを実行 Exchange オンラインの昇格の承認要求を承認する PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08ddf-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="08ddf-211">例:</span><span class="sxs-lookup"><span data-stu-id="08ddf-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="08ddf-212">次のコマンドを実行 Exchange オンラインの昇格の承認要求を拒否する PowerShell:</span><span class="sxs-lookup"><span data-stu-id="08ddf-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="08ddf-213">例:</span><span class="sxs-lookup"><span data-stu-id="08ddf-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="08ddf-214">Office 365 の管理者のアクセス ポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="08ddf-215">アクセス権限ポリシーを削除するには、それが組織で不要になった場合。</span><span class="sxs-lookup"><span data-stu-id="08ddf-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-216">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-217">組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="08ddf-218">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-219">**アクセス ポリシーを管理し要求**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="08ddf-220">**ポリシーを構成する**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="08ddf-221">削除するポリシーを選択し、**削除するポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="08ddf-222">**閉じる**を選択します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-223">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-224">次のコマンドを実行 Exchange オンライン アクセス権限ポリシーを削除する Powershell:</span><span class="sxs-lookup"><span data-stu-id="08ddf-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="08ddf-225">Office 365 の管理者のアクセスを無効にします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="08ddf-p115">必要な場合、組織のアクセス権限の管理を無効にできます。特権を無効にするとアクセスは削除されません、関連付けられている承認ポリシーや承認者のグループです。</span><span class="sxs-lookup"><span data-stu-id="08ddf-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="08ddf-228">Microsoft 365 管理センターを使用してください。</span><span class="sxs-lookup"><span data-stu-id="08ddf-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="08ddf-229">組織の管理者アカウントの資格情報を使用して[Microsoft 365 管理センター](https://portal.office.com)にサインインします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="08ddf-230">**設定**に移動し、管理センターで、 > **のセキュリティとプライバシー** > **のアクセス権限**。</span><span class="sxs-lookup"><span data-stu-id="08ddf-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="08ddf-231">**アクセス権限の承認を必要とする**コントロールを有効にします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="08ddf-232">Exchange 管理 PowerShell を使用します。</span><span class="sxs-lookup"><span data-stu-id="08ddf-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="08ddf-233">次のコマンドを実行 Exchange オンライン Powershell へのアクセス権限を無効にします。</span><span class="sxs-lookup"><span data-stu-id="08ddf-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```