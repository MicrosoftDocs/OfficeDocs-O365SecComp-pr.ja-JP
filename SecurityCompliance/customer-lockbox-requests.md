---
title: Office 365 カスタマー ロックボックス要求
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
search.appverid:
- BCS160
- MET150
- MOE150
description: 問題が発生したときに Microsoft サポートエンジニアがデータにアクセスする方法を制御するための、カスタマーロックボックス要求について説明します。
ms.openlocfilehash: 3a86f3333114f3015b85d8066298f9834737f127
ms.sourcegitcommit: 000548aa269ad775f20af5acd6aa726ac340c793
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "33661423"
---
# <a name="customer-lockbox-in-office-365"></a><span data-ttu-id="3f7c6-103">Office 365 のカスタマーロックボックス</span><span class="sxs-lookup"><span data-stu-id="3f7c6-103">Customer Lockbox in Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="3f7c6-104">この記事では、現在使用可能な機能の展開と構成に関するガイダンスを提供します。この機能は、Microsoft 365 E5、Office 365 E5、情報の保護とコンプライアンス、または高度なコンプライアンスアドオンサブスクリプションを持つ組織でのみ利用できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-104">This article provides deployment and configuration guidance for a feature that is currently available only for organizations that have a Microsoft 365 E5, Office 365 E5, Information Protection and Compliance, or Advanced Compliance add-on subscription.</span></span>

<span data-ttu-id="3f7c6-105">カスタマーロックボックスを使用すると、明示的な承認なしにサービス操作を実行するために、Microsoft がコンテンツにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-105">Customer Lockbox ensures that Microsoft cannot access your content to perform a service operation without your explicit approval.</span></span> <span data-ttu-id="3f7c6-106">お客様のロックボックスによって、コンテンツにアクセスする要求の承認ワークフローに入ります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-106">Customer Lockbox brings you into the approval workflow for requests to access your content.</span></span>

<span data-ttu-id="3f7c6-107">Microsoft のエンジニアは、サポートプロセスでお客様から報告された問題のトラブルシューティングと修正に役立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-107">Occasionally, Microsoft engineers help troubleshoot and fix customer reported issues in the support process.</span></span> <span data-ttu-id="3f7c6-108">通常、問題は広範なテレメトリおよびデバッグツールによって Microsoft がサービスに適用されています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-108">Usually, issues are fixed through extensive telemetry and debugging tools Microsoft has in place for its services.</span></span> <span data-ttu-id="3f7c6-109">ただし、場合によっては、Microsoft のエンジニアにお客様のコンテンツにアクセスして、根本的な原因を特定し、問題を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-109">However, some cases require a Microsoft engineer to access customer content to determine the root cause and fix the issue.</span></span> <span data-ttu-id="3f7c6-110">お客様のロックボックスには、エンジニアが承認ワークフローの最後の手順として顧客からのアクセスを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-110">Customer Lockbox requires the engineer to request access from the customer as a final step in the approval workflow.</span></span> <span data-ttu-id="3f7c6-111">これにより、組織は、これらの要求を承認または拒否したり、顧客への直接アクセス制御を提供したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-111">This gives organizations the option to approve or deny these requests, and provide direct access control to the customer.</span></span>

### <a name="customer-lockbox-overview-video"></a><span data-ttu-id="3f7c6-112">顧客ロックボックスの概要ビデオ</span><span class="sxs-lookup"><span data-stu-id="3f7c6-112">Customer Lockbox overview video</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/8fecf10b-1f03-4849-8b67-76d3d2a43f26?autoplay=false]

> [!NOTE]
> <span data-ttu-id="3f7c6-113">Customer ロックボックスは、Exchange Online、SharePoint Online、OneDrive for business のデータにアクセスするための要求をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-113">Customer Lockbox supports requests to access data in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="3f7c6-114">他の Office 365 サービスのサポートを推奨するには、 [office 365 UserVoice](https://office365.uservoice.com/)で要求を送信してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-114">To recommend support for other Office 365 services, please submit a request at [Office 365 UserVoice](https://office365.uservoice.com/).</span></span>

## <a name="customer-lockbox-workflow"></a><span data-ttu-id="3f7c6-115">顧客ロックボックスのワークフロー</span><span class="sxs-lookup"><span data-stu-id="3f7c6-115">Customer Lockbox workflow</span></span>

<span data-ttu-id="3f7c6-116">次の手順では、Microsoft のエンジニアからカスタマーロックボックス要求が開始されたときの一般的なワークフローの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-116">The following steps outline the typical workflow when a Customer Lockbox request is initiated by a Microsoft engineer:</span></span>

1. <span data-ttu-id="3f7c6-117">組織内の誰かが Office 365 メールボックスに問題を持っている。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-117">Someone at an organization has an issue with their Office 365 mailbox.</span></span>

2. <span data-ttu-id="3f7c6-118">ユーザーが問題のトラブルシューティングを行った後、問題を修正できない場合は、Microsoft サポートにサポートリクエストを開きます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-118">After the user troubleshoots the issue, but can't fix it, they open a support request with Microsoft Support.</span></span>

3. <span data-ttu-id="3f7c6-119">サポートエンジニアがサービス要求を確認し、問題を修復するためにお客様の Exchange Online コンテンツにアクセスする必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-119">A support engineer reviews the service request and determines a need to access customer’s Exchange Online content to repair the issue.</span></span>

4. <span data-ttu-id="3f7c6-120">サポートエンジニアは、Customer のロックボックス要求ツールにログインし、顧客のテナント名、サービス要求番号、およびデータへのアクセスが必要な見積もり期間を指定して、データアクセス要求を行います。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-120">The support engineer logs into the Customer Lockbox request tool and makes a data access request by specifying the customer's tenant name, service request number, and the estimated duration for which access to the data is needed.</span></span>

5. <span data-ttu-id="3f7c6-121">Microsoft サポートマネージャーが要求を承認した後、顧客のロックボックスは、Microsoft からの保留中のアクセス要求に関する電子メール通知をお客様の組織で指定された承認者に送信します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-121">After a Microsoft Support manager approves the request, Customer Lockbox sends the designated approver at the customer's organization an email notification about the pending access request from Microsoft.</span></span>

    ![顧客のロックボックス電子メール通知の例](media/CustomerLockbox1.png)

   > [!NOTE]
   > <span data-ttu-id="3f7c6-123">Microsoft 365 管理センターで[カスタマーロックボックスアクセス承認](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)者の役割を割り当てられたすべてのユーザーは、顧客ロックボックス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-123">Anyone who is assigned the [Customer Lockbox access approver](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) admin role in Microsoft 365 admin center can approve Customer Lockbox requests.</span></span>

7. <span data-ttu-id="3f7c6-124">承認者は、Microsoft 365 管理センターにサインインし、要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-124">The approver signs in to the Microsoft 365 admin center and approves the request.</span></span> <span data-ttu-id="3f7c6-125">この手順では、Office 365 監査ログの検索によって使用可能な監査レコードの作成が開始されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-125">This step triggers the creation of an audit record available by searching the Office 365 audit log.</span></span> <span data-ttu-id="3f7c6-126">詳細については、「[ユーザーのロックボックス要求の監査](#auditing-customer-lockbox-requests)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-126">For more information, see the [Auditing Customer Lockbox requests](#auditing-customer-lockbox-requests) section.</span></span>

   <span data-ttu-id="3f7c6-127">顧客が要求を拒否した場合、または要求が12時間以内に承認されなかった場合、要求は有効期限が切れ、Microsoft のエンジニアにはアクセス権が与えられません。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-127">If the customer rejects the request or the request isn’t approved within 12 hours, the request expires and no access is granted to the Microsoft engineer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="3f7c6-128">Microsoft では、Office 365 にサインインする必要がある、カスタマーロックボックスの電子メール通知にリンクは含まれていません。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-128">Microsoft does not include any links in Customer Lockbox email notifications requiring you to sign in to Office 365.</span></span>

8. <span data-ttu-id="3f7c6-129">お客様が要求を承認した後、Microsoft エンジニアは承認メッセージを受け取り、Exchange Online にログインし、お客様の問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-129">After the customer approves the request, the Microsoft engineer receives the approval message, logs into Exchange Online, and fixes the customer's issue.</span></span> <span data-ttu-id="3f7c6-130">Microsoft のエンジニアは、要求された期間に、アクセスが自動的に取り消される前に問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-130">Microsoft engineers have the requested duration to fix the issue after which the access is automatically revoked.</span></span>

> [!NOTE]
> <span data-ttu-id="3f7c6-131">Microsoft のエンジニアによって実行されるすべての操作は、Office 365 監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-131">All actions performed by a Microsoft engineer are logged in the Office 365 audit log.</span></span> <span data-ttu-id="3f7c6-132">これらの監査レコードを検索して確認し、検索して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-132">You can search for and review these audit record and can be searched for and reviewed.</span></span>

## <a name="turn-customer-lockbox-requests-on-or-off"></a><span data-ttu-id="3f7c6-133">カスタマーロックボックス要求を有効または無効にする</span><span class="sxs-lookup"><span data-stu-id="3f7c6-133">Turn Customer Lockbox requests on or off</span></span>

<span data-ttu-id="3f7c6-134">Office 365 管理者は、Microsoft 365 管理センターでカスタマーロックボックスコントロールをオンにすることができます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-134">An Office 365 administrator can turn on Customer Lockbox controls in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3f7c6-135">カスタマーロックボックスがオンになっている場合は、そのコンテンツにアクセスする前に、組織の承認を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-135">When Customer Lockbox is turned on, Microsoft is required to obtain an organization’s approval before accessing any of their content.</span></span>

> [!NOTE]
> <span data-ttu-id="3f7c6-136">次の手順を実行するには、Microsoft 365 または Office 365 組織の全体管理者であるか、**カスタマーロックボックスアクセス許可**の管理者ロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-136">To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.</span></span>

1. <span data-ttu-id="3f7c6-137">[https://admin.microsoft.com](https://admin.microsoft.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-137">Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="3f7c6-138">[**設定 _GT_ Security & Privacy**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-138">Click **Settings > Security & privacy**.</span></span>

    ![管理センターでカスタマーロックボックスの設定を編集する](media/CustomerLockbox2.png)

3. <span data-ttu-id="3f7c6-140">[**顧客ロックボックス**] タイルで、[**編集**] をクリックし、トグルを **[オン**] または [**オフ**] に移動して、機能をオンまたはオフにします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-140">On the **Customer Lockbox** tile, click **Edit**, and then move the toggle to **On** or **Off** to turn the feature on or off.</span></span>

    ![Require approval for Customer Lockbox](media/CustomerLockbox4.png)

## <a name="approve-or-deny-a-customer-lockbox-request"></a><span data-ttu-id="3f7c6-142">カスタマーロックボックス要求を承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="3f7c6-142">Approve or deny a Customer Lockbox request</span></span>

> [!NOTE]
> <span data-ttu-id="3f7c6-143">次の手順を実行するには、Microsoft 365 または Office 365 組織の全体管理者であるか、**カスタマーロックボックスアクセス許可**の管理者ロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-143">To perform the following procedure, you must be a global administrator in your Microsoft 365 or Office 365 organization, or be assigned the **Customer Lockbox access approver** admin role.</span></span>

1. <span data-ttu-id="3f7c6-144">[https://admin.microsoft.com](https://admin.microsoft.com) に移動し、職場または学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-144">Go to [https://admin.microsoft.com](https://admin.microsoft.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="3f7c6-145">[ **Support _GT_ Customer のロックボックス要求**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-145">Click **Support > Customer Lockbox Requests**.</span></span>

    ![[サポート] をクリックし、[カスタマーロックボックス要求] をクリックします。](media/CustomerLockbox5.png)

    <span data-ttu-id="3f7c6-147">顧客のロックボックス要求の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-147">A list of Customer Lockbox requests is displayed.</span></span>

    ![顧客ロックボックス要求の一覧](media/CustomerLockbox6.png)

3. <span data-ttu-id="3f7c6-149">顧客のロックボックス要求を選択し、[**承認**] または [**拒否**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-149">Select a Customer Lockbox request, and then click **Approve** or **Deny**.</span></span>

    ![カスタマーロックボックス要求を承認または拒否する](media/CustomerLockbox7.png)

    <span data-ttu-id="3f7c6-151">カスタマーロックボックス要求の承認に関する確認メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-151">A confirmation message about the approval of the Customer Lockbox request is displayed.</span></span>

    ![カスタマーロックボックス要求を承認または拒否する](media/CustomerLockbox8.png)

## <a name="auditing-customer-lockbox-requests"></a><span data-ttu-id="3f7c6-153">顧客ロックボックス要求の監査</span><span class="sxs-lookup"><span data-stu-id="3f7c6-153">Auditing Customer Lockbox requests</span></span> 

<span data-ttu-id="3f7c6-154">カスタマーロックボックス要求に対応する監査レコードは、Office 365 監査ログに記録され、Office 365 Security & コンプライアンスセンターの[監査ログ検索ツール](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance)を使用してアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-154">Audit records that correspond to the Customer Lockbox requests are logged in the Office 365 audit log and can be accessed by using the [Audit log search tool](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance) in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3f7c6-155">顧客に関連するアクション (アクセス要求が承認された場合に、Microsoft のエンジニアによって実行された操作) を承諾または拒否すると、Office 365 監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-155">Actions related to a customer accepting or denying a Customer Lockbox request and actions performed by Microsoft engineers (when access requests are approved) are logged in the Office 365 audit log.</span></span> <span data-ttu-id="3f7c6-156">これらの監査レコードを検索して確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-156">You can search for and review these audit records.</span></span>

> [!NOTE]
> <span data-ttu-id="3f7c6-157">Office 365 監査ログを検索するには、Exchange Online で [表示のみの監査ログまたは監査ログの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-157">You have to be assigned the View-Only Audit Logs or Audit Logs role in Exchange Online to search the Office 365 audit log.</span></span> <span data-ttu-id="3f7c6-158">詳細については、「[Office 365 セキュリティ/コンプライアンス センターで監査ログを検索する](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-158">For more information, see [Search the audit log in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#before-you-begin).</span></span>

### <a name="search-the-audit-log-for-activity-related-to-customer-lockbox-requests"></a><span data-ttu-id="3f7c6-159">カスタマーロックボックス要求に関連するアクティビティの監査ログを検索する</span><span class="sxs-lookup"><span data-stu-id="3f7c6-159">Search the audit log for activity related to Customer Lockbox requests</span></span>

<span data-ttu-id="3f7c6-160">次に、監査ログ検索クエリを作成して、顧客ロックボックスに関連する監査レコードを取得する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-160">Here's how to create an audit log search query to return audit records related to Customer Lockbox:</span></span>

1. <span data-ttu-id="3f7c6-161">[https://protection.office.com](https://protection.office.com) に移動します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-161">Go to [https://protection.office.com](https://protection.office.com).</span></span>
  
2. <span data-ttu-id="3f7c6-162">職場または学校のアカウントを使用して、Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-162">Sign in to Office 365 using your work or school account.</span></span>

3. <span data-ttu-id="3f7c6-163">セキュリティ センターとコンプライアンス センターの左側のウィンドウで、[**検索と調査**]  >  [**監査ログの検索**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-163">In the left pane of the Security & Compliance Center, click **Search & investigation** > **Audit log search**.</span></span>

    <span data-ttu-id="3f7c6-164">[**監査ログの検索**] ページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-164">The **Audit log search** page is displayed.</span></span>

    ![監査ログの検索ページ](media/auditlogsearch1.png)
  
4. <span data-ttu-id="3f7c6-166">次の検索条件を設定します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-166">Configure the following search criteria:</span></span>

    <span data-ttu-id="3f7c6-167">a.</span><span class="sxs-lookup"><span data-stu-id="3f7c6-167">a.</span></span> <span data-ttu-id="3f7c6-168">**アクティビティ**-検索ですべてのアクティビティの監査レコードが返されるようにするには、このフィールドを空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-168">**Activities** - Leave this field blank so that the search returns audit records for all activities.</span></span> <span data-ttu-id="3f7c6-169">これは、カスタマーロックボックス要求と、Microsoft のエンジニアによって実行される対応するアクティビティに関連する監査レコードを返すために必要です。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-169">This is necessary to return any audit records related to Customer Lockbox requests and corresponding activity performed by Microsoft engineers.</span></span>

    <span data-ttu-id="3f7c6-170">b.</span><span class="sxs-lookup"><span data-stu-id="3f7c6-170">b.</span></span> <span data-ttu-id="3f7c6-171">**開始**日と**終了日**-その期間内に発生したイベントを表示する日付と時刻の範囲を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-171">**Start date** and **End date** - Select a date and time range to display the events that occurred within that period.</span></span>

    <span data-ttu-id="3f7c6-172">c.</span><span class="sxs-lookup"><span data-stu-id="3f7c6-172">c.</span></span> <span data-ttu-id="3f7c6-173">**ユーザー** -このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-173">**Users** - Leave this field blank.</span></span>

    <span data-ttu-id="3f7c6-174">d.</span><span class="sxs-lookup"><span data-stu-id="3f7c6-174">d.</span></span> <span data-ttu-id="3f7c6-175">**ファイル、フォルダー、またはサイト** - このフィールドは空白のままにします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-175">**File, folder, or site** - Leave this field blank.</span></span>

5. <span data-ttu-id="3f7c6-176">[**検索**] をクリックして、設定した検索条件で検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-176">Click **Search** to run the search using your search criteria.</span></span> 

    <span data-ttu-id="3f7c6-177">検索結果が読み込まれ、しばらくすると、[**監査ログの検索**] ページの [**結果**] の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-177">The search results are loaded, and after a few moments they are displayed under **Results** on the **Audit log search** page.</span></span>

6. <span data-ttu-id="3f7c6-178">[検索結果] ページで [**結果のフィルター処理**] をクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-178">Click **Filter results** on the search results page, and do one of the following things:</span></span>

   - <span data-ttu-id="3f7c6-179">組織内の承認者に関連する監査レコードを表示するには、顧客のロックボックス要求を承認または拒否します。 [**アクティビティ**] 列の下のボックスに「 **AccessToCustomerDataRequest**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-179">To display audit records related to an approver in your organization approving or denying a Customer Lockbox request: In the box under the **Activity** column, type **Set-AccessToCustomerDataRequest**.</span></span>

   - <span data-ttu-id="3f7c6-180">Microsoft のエンジニアに関連する監査レコードを表示するには、承認された顧客ロックボックス要求に対する処理を実行します。 [**ユーザー** ] 列の下のボックスに、「 **Microsoft Operator**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-180">To display audit records related to a Microsoft engineer performing actions in response to an approved Customer Lockbox request: In the box under the **User** column, type **Microsoft Operator**.</span></span> <span data-ttu-id="3f7c6-181">エンジニアによって実行されるアクションが [**アクティビティ**] 列に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-181">Note that the action performed by the engineer is displayed int the **Activity** column.</span></span>

      ![監査レコードを表示するには、"Microsoft Operator" のフィルターを適用します。](media/CustomerLockbox10.png)

7. <span data-ttu-id="3f7c6-183">結果の一覧で、監査レコードをクリックして表示します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-183">In the list of results, click an audit record to display it.</span></span>

### <a name="audit-record-for-a-customer-lockbox-access-request"></a><span data-ttu-id="3f7c6-184">カスタマーロックボックスのアクセス要求の監査レコード</span><span class="sxs-lookup"><span data-stu-id="3f7c6-184">Audit record for a Customer Lockbox access request</span></span>

<span data-ttu-id="3f7c6-185">組織内のユーザーがカスタマーロックボックス要求を承認または拒否すると、監査レコードが Office 365 監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-185">When a person in your organization approves or denies a Customer Lockbox request, an audit record is logged in the Office 365 audit log.</span></span> <span data-ttu-id="3f7c6-186">このレコードには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-186">This record contains the following information.</span></span> 

| <span data-ttu-id="3f7c6-187">Audit record プロパティ</span><span class="sxs-lookup"><span data-stu-id="3f7c6-187">Audit record property</span></span>| <span data-ttu-id="3f7c6-188">説明</span><span class="sxs-lookup"><span data-stu-id="3f7c6-188">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="3f7c6-189">日付</span><span class="sxs-lookup"><span data-stu-id="3f7c6-189">Date</span></span>       | <span data-ttu-id="3f7c6-190">顧客のロックボックス要求が承認または拒否された日時。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-190">The date and time when the Customer Lockbox request was approved or denied.</span></span>
| <span data-ttu-id="3f7c6-191">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f7c6-191">IP address</span></span> | <span data-ttu-id="3f7c6-192">承認者が要求を承認または拒否するために使用したコンピューターの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-192">The IP address of the machine the approver used to approve or deny a request.</span></span> |
| <span data-ttu-id="3f7c6-193">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3f7c6-193">User</span></span>       | <span data-ttu-id="3f7c6-194">サービスアカウント BOXServiceAccount @\[\]prod.outlook.com。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-194">The service account BOXServiceAccount@\[customerforest\].prod.outlook.com.</span></span>            |
| <span data-ttu-id="3f7c6-195">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3f7c6-195">Activity</span></span>   | <span data-ttu-id="3f7c6-196">AccessToCustomerDataRequest;これは、顧客のロックボックス要求を承認または拒否するときに記録される監査アクティビティです。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-196">Set-AccessToCustomerDataRequest; this is the auditing activity that is logged when you approve or deny a Customer Lockbox request.</span></span>                                |
| <span data-ttu-id="3f7c6-197">項目</span><span class="sxs-lookup"><span data-stu-id="3f7c6-197">Item</span></span>       | <span data-ttu-id="3f7c6-198">顧客のロックボックス要求の Guid</span><span class="sxs-lookup"><span data-stu-id="3f7c6-198">The Guid of the Customer Lockbox request</span></span>                             |

<span data-ttu-id="3f7c6-199">次のスクリーンショットは、承認された顧客ロックボックス要求に対応する監査ログレコードの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-199">The following screenshot shows an example of an audit log record that corresponds to an approved Customer Lockbox request.</span></span> <span data-ttu-id="3f7c6-200">顧客のロックボックス要求が拒否された場合、 **Approvaldecision**パラメーターの値は**Deny**になります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-200">If a Customer Lockbox request was denied, then the value of **ApprovalDecision** parameter would be **Deny**.</span></span>

![承認された顧客ロックボックス要求の監査レコード](media/CustomerLockbox9.png)

> [!TIP]
> <span data-ttu-id="3f7c6-202">監査レコードに詳細情報を表示するには、[**詳細情報**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-202">To display more detailed information in an audit record, click **More information**.</span></span>

### <a name="audit-record-for-an-action-performed-by-a-microsoft-engineer"></a><span data-ttu-id="3f7c6-203">Microsoft のエンジニアによって実行されたアクションの監査レコード</span><span class="sxs-lookup"><span data-stu-id="3f7c6-203">Audit record for an action performed by a Microsoft engineer</span></span>

<span data-ttu-id="3f7c6-204">前述のように、お客様のロックボックス要求が承認された後に Microsoft のエンジニアが実行した操作 (およびお客様のコンテンツへのアクセスが発生する可能性があります) は、監査ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-204">As previously explained, the actions performed by a Microsoft engineer after a Customer Lockbox request is approved (and that may result in accessing customer content) are logged in the audit log.</span></span> <span data-ttu-id="3f7c6-205">これらのレコードには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-205">These records contain the following information.</span></span>

| <span data-ttu-id="3f7c6-206">Audit record プロパティ</span><span class="sxs-lookup"><span data-stu-id="3f7c6-206">Audit record property</span></span>| <span data-ttu-id="3f7c6-207">説明</span><span class="sxs-lookup"><span data-stu-id="3f7c6-207">Description</span></span>|
|:---------- |:----------|
| <span data-ttu-id="3f7c6-208">日付</span><span class="sxs-lookup"><span data-stu-id="3f7c6-208">Date</span></span>       | <span data-ttu-id="3f7c6-209">アクションが実行された日時。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-209">Date time when the action was performed.</span></span> <span data-ttu-id="3f7c6-210">この操作が実行された時間は、顧客のロックボックス要求が承認された4時間以内になることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-210">Note that the time that this action was performed will be within 4 hours of when the Customer Lockbox request was approved.</span></span>              |
| <span data-ttu-id="3f7c6-211">IP アドレス</span><span class="sxs-lookup"><span data-stu-id="3f7c6-211">IP address</span></span> | <span data-ttu-id="3f7c6-212">Microsoft エンジニアが使用したコンピューターの IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-212">The IP Address of the machine Microsoft engineer used.</span></span> |
| <span data-ttu-id="3f7c6-213">ユーザー</span><span class="sxs-lookup"><span data-stu-id="3f7c6-213">User</span></span>       | <span data-ttu-id="3f7c6-214">Microsoft Operator;この値は、このレコードが顧客のロックボックス要求に関連付けられていることを示します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-214">Microsoft Operator; this value indicates that this record is related to a Customer Lockbox request.</span></span>                                  |
| <span data-ttu-id="3f7c6-215">アクティビティ</span><span class="sxs-lookup"><span data-stu-id="3f7c6-215">Activity</span></span>   | <span data-ttu-id="3f7c6-216">Microsoft エンジニアによって実行されたアクティビティの名前。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-216">Name of the activity performed by the Microsoft engineer.</span></span>|
| <span data-ttu-id="3f7c6-217">項目</span><span class="sxs-lookup"><span data-stu-id="3f7c6-217">Item</span></span>       | <span data-ttu-id="3f7c6-218">\<必須\></span><span class="sxs-lookup"><span data-stu-id="3f7c6-218">\<empty\></span></span>                                             |


## <a name="frequently-asked-questions"></a><span data-ttu-id="3f7c6-219">よく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="3f7c6-219">Frequently asked questions</span></span>

#### <a name="which-office-365-services-does-customer-lockbox-apply-to"></a><span data-ttu-id="3f7c6-220">どの Office 365 サービスが顧客ロックボックスに適用されますか。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-220">Which Office 365 services does Customer Lockbox apply to?</span></span>

<span data-ttu-id="3f7c6-221">お客様のロックボックスは現在、Exchange Online、SharePoint Online、OneDrive for business でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-221">Customer Lockbox is currently supported in Exchange Online, SharePoint Online, and OneDrive for Business.</span></span>

#### <a name="is-customer-lockbox-available-to-all-office-365-customers"></a><span data-ttu-id="3f7c6-222">お客様のロックボックスは、すべての Office 365 のお客様が利用できますか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-222">Is Customer Lockbox available to all Office 365 customers?</span></span>

<span data-ttu-id="3f7c6-223">カスタマーロックボックスは、Microsoft 365 または Office 365 E5 サブスクリプションに含まれており、情報の保護とコンプライアンス、または高度なコンプライアンスアドオンサブスクリプションを使用して他のプランに追加できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-223">Customer Lockbox is included with the Microsoft 365 or Office 365 E5 subscriptions and can be added to other plans with an Information Protection and Compliance or an Advanced Compliance add-on subscription.</span></span> <span data-ttu-id="3f7c6-224">詳細については [、「プランと価格](https://products.office.com/business/office-365-enterprise-e5-business-software) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-224">Please see [Plans and pricing](https://products.office.com/business/office-365-enterprise-e5-business-software) for more information.</span></span>

#### <a name="what-is-customer-content"></a><span data-ttu-id="3f7c6-225">顧客コンテンツとは</span><span class="sxs-lookup"><span data-stu-id="3f7c6-225">What is customer content?</span></span>

<span data-ttu-id="3f7c6-226">顧客コンテンツは、Office 365 サービスおよびアプリケーションのユーザーによって作成されたデータです。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-226">Customer content is the data created by users of Office 365 services and applications.</span></span> <span data-ttu-id="3f7c6-227">顧客コンテンツの例は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-227">Examples of customer content include:</span></span>

- <span data-ttu-id="3f7c6-228">電子メール本文またはメールの添付ファイル</span><span class="sxs-lookup"><span data-stu-id="3f7c6-228">Email body or email attachments</span></span>

- <span data-ttu-id="3f7c6-229">SharePoint サイトのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="3f7c6-229">SharePoint site contents</span></span>

- <span data-ttu-id="3f7c6-230">SharePoint ファイルの本文に含まれる情報</span><span class="sxs-lookup"><span data-stu-id="3f7c6-230">Information in the body of a SharePoint file</span></span>

- <span data-ttu-id="3f7c6-231">Skype for Business プレゼンテーションファイルの本文</span><span class="sxs-lookup"><span data-stu-id="3f7c6-231">Skype for Business presentation file body</span></span>

- <span data-ttu-id="3f7c6-232">インスタントメッセージ (IM) または音声会話</span><span class="sxs-lookup"><span data-stu-id="3f7c6-232">Instant messages (IM) or voice conversations</span></span>

- <span data-ttu-id="3f7c6-233">ユーザーが生成した blob または構造化ストレージデータ (SQL コンテナーなど)</span><span class="sxs-lookup"><span data-stu-id="3f7c6-233">Customer-generated blob or structured storage data (for example, SQL Containers)</span></span>

- <span data-ttu-id="3f7c6-234">顧客が所有するセキュリティ情報 (証明書、暗号化キー、パスワードなど)</span><span class="sxs-lookup"><span data-stu-id="3f7c6-234">Customer-owned security information (for example, certificates, encryption keys, and passwords)</span></span>

- <span data-ttu-id="3f7c6-235">お客様のコンテンツが残っている場合の推論、以降のすべての推論</span><span class="sxs-lookup"><span data-stu-id="3f7c6-235">Inferences, and all subsequent inferences, if customer content remains</span></span>

<span data-ttu-id="3f7c6-236">Office 365 の顧客コンテンツの詳細については、「 [office 365 のセキュリティセンター](https://products.office.com/en-US/business/office-365-trust-center-privacy/)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-236">For additional information about customer content in Office 365, see the [Office 365 Trust Center](https://products.office.com/en-US/business/office-365-trust-center-privacy/).</span></span>

#### <a name="who-is-notified-when-there-is-a-request-to-access-my-content"></a><span data-ttu-id="3f7c6-237">自分のコンテンツへのアクセスを要求された場合、だれに通知されますか。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-237">Who is notified when there is a request to access my content?</span></span>

<span data-ttu-id="3f7c6-238">グローバル管理者と、カスタマーロックボックスアクセス許可管理者役割に割り当てられているユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-238">Global administrators and anyone assigned the Customer Lockbox access approver admin role are notified.</span></span> <span data-ttu-id="3f7c6-239">これらのユーザーは、顧客のロックボックス要求の承認を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-239">These are also the same users who can approve for Customer Lockbox requests.</span></span>

#### <a name="who-can-approve-or-reject-these-requests-in-my-organization"></a><span data-ttu-id="3f7c6-240">組織内でこれらの要求を承認または拒否できるユーザー</span><span class="sxs-lookup"><span data-stu-id="3f7c6-240">Who can approve or reject these requests in my organization?</span></span>

<span data-ttu-id="3f7c6-241">グローバル管理者と顧客ロックボックスアクセス許可管理者ロールに割り当てられたユーザーは、顧客ロックボックス要求を承認できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-241">Global administrators and anyone assigned the Customer Lockbox access approver admin role can approve Customer Lockbox requests.</span></span> <span data-ttu-id="3f7c6-242">お客様は、組織内でこれらの役割の割り当てを制御します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-242">Customers control these role assignments in their organizations.</span></span>

#### <a name="how-do-i-opt-in-to-customer-lockbox"></a><span data-ttu-id="3f7c6-243">カスタマーロックボックスにオプトインするにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-243">How do I opt-in to Customer Lockbox?</span></span>

<span data-ttu-id="3f7c6-244">グローバル管理者は、Microsoft 365 または Microsoft 365 管理センターでカスタマーロックボックスを有効にして構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-244">A global administrator can enable and configure Customer Lockbox in the Microsoft 365 or Microsoft 365 admin center.</span></span>

#### <a name="if-i-approve-a-customer-lockbox-request-what-can-the-engineer-do-and-how-will-i-know-what-the-microsoft-engineer-did"></a><span data-ttu-id="3f7c6-245">カスタマーロックボックス要求を承認した場合、エンジニアは何をすることができますか。また、Microsoft のエンジニアが何をしたかを知る方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-245">If I approve a Customer Lockbox request, what can the engineer do and how will I know what the Microsoft engineer did?</span></span>

<span data-ttu-id="3f7c6-246">カスタマーロックボックス要求を承認した後、Microsoft のエンジニアは、事前承認済みコマンドレットを使用して、お客様のコンテンツにアクセスするためにこれらの必要な権限を付与しました。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-246">After you approve a Customer Lockbox request, the Microsoft engineer granted these necessary privileges to access customer content by using pre-approved cmdlets.</span></span> <span data-ttu-id="3f7c6-247">カスタマーロックボックスの要求に対応して Microsoft のエンジニアが実行するアクションは、Office 365 Security & コンプライアンスセンターの監査ログに記録され、アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-247">Actions taken by Microsoft engineers in response to Customer Lockbox requests are logged and accessible in the audit log in the Office 365 Security & Compliance Center.</span></span>

#### <a name="how-do-i-know-that-microsoft-follows-the-approval-process"></a><span data-ttu-id="3f7c6-248">Microsoft が承認プロセスに従うことをどのように確認できますか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-248">How do I know that Microsoft follows the approval process?</span></span>

<span data-ttu-id="3f7c6-249">組織内の管理者および承認者に送信される電子メールの承認通知は、Microsoft 365 管理センターのカスタマーロックボックス要求の履歴と相互参照できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-249">You can cross-reference the email approval notifications sent to admins and approvers in your organization with the Customer Lockbox request history in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="3f7c6-250">お客様のロックボックスは、最新の[SOC 1 SSAE 16 監査レポート](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-250">Customer Lockbox is included in the latest [SOC 1 SSAE 16 audit report](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span> <span data-ttu-id="3f7c6-251">詳細については、 [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports)の最新レポートを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-251">For more details, you can find the latest reports in the [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=91592749-e86a-43ac-801e-121382614681&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_SOC%20%2F%20SSAE%2016%20Reports).</span></span>

#### <a name="can-microsoft-modify-the-list-of-approvers-for-my-tenant-if-not-how-is-it-prevented"></a><span data-ttu-id="3f7c6-252">Microsoft は、自分のテナントの承認者の一覧を変更できますか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-252">Can Microsoft modify the list of approvers for my tenant?</span></span> <span data-ttu-id="3f7c6-253">そうでない場合は、どのような方法で回避できますか。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-253">If not, how is it prevented?</span></span>

<span data-ttu-id="3f7c6-254">顧客のロックボックス要求を承認できるユーザーを指定できるのは、組織内のグローバル管理者のみです。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-254">Only a global administrator in your organization can specify who can approve Customer Lockbox requests.</span></span> <span data-ttu-id="3f7c6-255">これは、Azure Active Directory の全体管理者グループのメンバーのみが、要求を承認できるユーザーを指定できることを意味します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-255">That means only the members of the Global administrator group in Azure Active Directory can specify who can approve request.</span></span> <span data-ttu-id="3f7c6-256">Azure Active Directory の全体管理者グループのメンバーシップは、組織によってのみ管理されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-256">Membership of the Global administrator group in Azure Active Directory is managed only by your organization.</span></span>

#### <a name="what-if-i-need-more-information-about-a-content-access-request-to-approve-it"></a><span data-ttu-id="3f7c6-257">承認のためにコンテンツアクセス要求に関する詳細情報が必要な場合は、どうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-257">What if I need more information about a content access request to approve it?</span></span>

<span data-ttu-id="3f7c6-258">各顧客のロックボックス要求には、Office 365 サービスの要求番号が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-258">Each Customer Lockbox request contains an Office 365 service request number.</span></span> <span data-ttu-id="3f7c6-259">要求に関する詳細情報を取得するには、Microsoft サポートに連絡して、このサービス番号を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-259">You can contact Microsoft Support and reference this service number to get more information about the request.</span></span>

#### <a name="when-a-customer-lockbox-request-is-approved-how-long-are-the-permissions-valid"></a><span data-ttu-id="3f7c6-260">顧客のロックボックス要求が承認されると、アクセス許可はどのくらいの期間有効になりますか。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-260">When a Customer Lockbox request is approved, how long are the permissions valid?</span></span>

<span data-ttu-id="3f7c6-261">現時点では、Microsoft のエンジニアに付与されるアクセス許可の最大期間は4時間です。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-261">Currently, the maximum period for the access permissions granted to the Microsoft engineer is 4 hours.</span></span> <span data-ttu-id="3f7c6-262">Microsoft のエンジニアは、短い期間を要求することもできます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-262">The Microsoft engineer can also request a shorter period.</span></span>

#### <a name="how-can-i-get-a-history-of-all-customer-lockbox-requests"></a><span data-ttu-id="3f7c6-263">すべてのカスタマーロックボックス要求の履歴を取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-263">How can I get a history of all Customer Lockbox requests?</span></span>

<span data-ttu-id="3f7c6-264">すべてのカスタマーロックボックス要求は、Microsoft 365 管理センターで表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-264">All Customer Lockbox requests are viewed in the Microsoft 365 admin center.</span></span>

#### <a name="how-do-i-correlate-the-content-access-requests-with-the-related-audit-logs"></a><span data-ttu-id="3f7c6-265">コンテンツアクセス要求を関連する監査ログと関連付けるにはどうすればよいですか。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-265">How do I correlate the content access requests with the related audit logs?</span></span>

<span data-ttu-id="3f7c6-266">コンプライアンスセンターのアクティビティフィードには、顧客ロックボックスのログアクティビティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-266">The Compliance Center Activity Feed contains log activities of Customer Lockbox.</span></span> <span data-ttu-id="3f7c6-267">顧客は、受信した電子メール要求に対して、顧客のロックボックスログアクティビティをアクティビティフィードから相互参照できます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-267">Customers can cross-reference the Customer Lockbox log activities from the activity feed against the email request they receive.</span></span>

#### <a name="what-happens-when-a-customer-doesnt-respond-to-a-customer-lockbox-request"></a><span data-ttu-id="3f7c6-268">お客様がお客様のロックボックス要求に応答しない場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-268">What happens when a customer doesn't respond to a Customer Lockbox request?</span></span>

<span data-ttu-id="3f7c6-269">顧客のロックボックス要求の既定の期間は12時間です。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-269">Customer Lockbox requests have a default duration of 12 hours.</span></span> <span data-ttu-id="3f7c6-270">12時間以内に要求に応答しない場合、要求は有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-270">If you don't respond to a request within 12 hour, the request expires.</span></span>

#### <a name="what-does-microsoft-when-a-customer-rejects-a-customer-lockbox-request"></a><span data-ttu-id="3f7c6-271">お客様が顧客のロックボックス要求を拒否した場合、Microsoft は何ができますか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-271">What does Microsoft when a customer rejects a Customer Lockbox request?</span></span>

<span data-ttu-id="3f7c6-272">顧客が顧客のロックボックス要求を拒否した場合、顧客コンテンツへのアクセスは行われません。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-272">If a customer rejects a Customer Lockbox request, no access to customer content occurs.</span></span> <span data-ttu-id="3f7c6-273">この問題を解決するために Microsoft がお客様のコンテンツにアクセスする必要があるというサービスの問題が組織内のユーザーから引き続き発生する場合、サービスの問題が持続する可能性があり、Microsoft はそのことをユーザーに通知します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-273">If a user in your organization continues to experience a service issue requiring Microsoft to access customer content to resolve the issue, then the service issue might persist and Microsoft will inform the user about this.</span></span>

#### <a name="does-customer-lockbox-protect-against-data-requests-from-law-enforcement-agencies-or-other-third-parties"></a><span data-ttu-id="3f7c6-274">カスタマーロックボックスは、法律執行機関または他のサードパーティからのデータ要求に対して保護されるものですか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-274">Does Customer Lockbox protect against data requests from law enforcement agencies or other third parties?</span></span>

<span data-ttu-id="3f7c6-275">いいえ。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-275">No.</span></span> <span data-ttu-id="3f7c6-276">Microsoft は、お客様のデータに関するサードパーティの要求を真剣に引き受けます。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-276">Microsoft takes third-party requests for customer data seriously.</span></span> <span data-ttu-id="3f7c6-277">クラウドサービスプロバイダーとして、Microsoft はお客様のデータのプライバシーを常に重視しています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-277">As a cloud service provider, Microsoft always advocates for the privacy of customer data.</span></span> <span data-ttu-id="3f7c6-278">召喚を受け取った場合、Microsoft は常にお客様に情報を取得するためにサードパーティのリダイレクトを試行します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-278">In the event we get a subpoena, Microsoft always attempts to redirect the third party to the customer to obtain the information.</span></span> <span data-ttu-id="3f7c6-279">(行政スミスのブログ:[政府からのお客様データの保護](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/))。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-279">(Read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)).</span></span> <span data-ttu-id="3f7c6-280">Microsoft が受け取る法的執行機関の要求に関する[詳細情報](https://www.microsoft.com/en-us/corporate-responsibility/lerr)を定期的に公開しています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-280">We periodically publish [detailed information](https://www.microsoft.com/en-us/corporate-responsibility/lerr) about the law enforcement requests that Microsoft receives.</span></span>

<span data-ttu-id="3f7c6-281">詳細については、「[オンラインサービス用語](https://www.microsoft.com/Licensing/product-licensing/products.aspx)」の「サードパーティのデータ要求に関する[Microsoft セキュリティセンター](https://www.microsoft.com/en-us/trustcenter/default.aspx) 」と「顧客データの開示」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-281">See the [Microsoft Trust Center](https://www.microsoft.com/en-us/trustcenter/default.aspx) regarding third-party data requests and the "Disclosure of Customer Data" section in the [Online Services Terms](https://www.microsoft.com/Licensing/product-licensing/products.aspx) for more information.</span></span>

#### <a name="how-does-microsoft-ensure-that-a-member-of-its-staff-doesnt-have-standing-access-to-customer-content-in-office-365-applications"></a><span data-ttu-id="3f7c6-282">Microsoft では、Office 365 アプリケーションの顧客コンテンツへの継続的なアクセス権を、スタッフのメンバーが持っているかどうかを確認する方法を教えてください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-282">How does Microsoft ensure that a member of its staff doesn't have standing access to customer content in Office 365 applications?</span></span>

<span data-ttu-id="3f7c6-283">Microsoft は、アクセス制御システムを使用して広範な予防措置を実装しており、これらのアクセス制御システムを回避する試みを識別して対処するための検出対策を行います。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-283">Microsoft implements extensive preventive measures through access control systems, and detective measures to identify and address attempts to circumvent these access control systems.</span></span> <span data-ttu-id="3f7c6-284">Office 365 は、最小限の特権とジャストインタイムアクセスの原則を使用して操作します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-284">Office 365 operates with the principles of least privilege and just-in-time access.</span></span> <span data-ttu-id="3f7c6-285">そのため、Microsoft の担当者は、継続的にお客様のコンテンツにアクセスするためのアクセス許可を持っていません。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-285">Therefore, no Microsoft personnel have permission to access customer content on an ongoing basis.</span></span> <span data-ttu-id="3f7c6-286">アクセス許可が付与されている場合は、期間に制限があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-286">If permission is granted, it is for a limited duration.</span></span> 

<span data-ttu-id="3f7c6-287">Office 365 は、*ロックボックス*と呼ばれるアクセス制御システムを使用して、サービス内で運用および管理機能を実行する機能を付与するアクセス許可に対する要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-287">Office 365 uses an access control system called *Lockbox* to process requests for permissions that grant the ability to perform operational and administrative functions within the service.</span></span> <span data-ttu-id="3f7c6-288">オペレーターは、ロックボックスを使用してユーザーのコンテンツへのアクセスを要求する必要があります。その後、アクセス許可が付与される前に、要求に対してアクションを実行する (たとえば、承認する) 必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-288">An operator must request access to customer content using Lockbox, which then requires a second person to take action on the request (e.g., approve it) before access is granted.</span></span> <span data-ttu-id="3f7c6-289">この2番目のユーザーはリクエスターになることができず、顧客コンテンツへのアクセスを承認するように指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-289">That second person can't be the requestor and must be designated to approve access to customer content.</span></span> <span data-ttu-id="3f7c6-290">要求が承認された場合にのみ、オペレーターは顧客コンテンツへの一時的なアクセス権を取得します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-290">Only if the request is approved does the operator acquire temporary access to customer content.</span></span> <span data-ttu-id="3f7c6-291">昇格期間が過ぎると、ロックボックスはアクセスを取り消します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-291">After the elevation period expires, Lockbox revokes access.</span></span>

<span data-ttu-id="3f7c6-292">Microsoft の一般的なセキュリティ対策の詳細については、[オンラインサービス](https://www.microsoft.com/licensing/product-licensing/products)の使用条件を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-292">Please refer to the [Online Services Terms](https://www.microsoft.com/licensing/product-licensing/products) for more details about Microsoft general security practices.</span></span>

#### <a name="under-what-circumstances-do-microsoft-engineers-need-access-to-my-content"></a><span data-ttu-id="3f7c6-293">Microsoft のエンジニアがコンテンツにアクセスする必要があるのはどのような状況ですか。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-293">Under what circumstances do Microsoft engineers need access to my content?</span></span>

<span data-ttu-id="3f7c6-294">Microsoft のエンジニアがお客様のコンテンツへのアクセスを必要とする最も一般的なシナリオは、お客様がトラブルシューティングのためのアクセス権を必要とするサポート要求を行った場合です。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-294">The most common scenario where Microsoft engineers need access customer content is when the customer makes a support request requiring access for troubleshooting.</span></span> <span data-ttu-id="3f7c6-295">Office 365 の基本原則は、お客様のコンテンツに Microsoft がアクセスせずにサービスを運用することです。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-295">A foundational principle of Office 365 is that the service operates without Microsoft access to customer content.</span></span> <span data-ttu-id="3f7c6-296">Microsoft によって実行されるほとんどすべてのサービス操作は完全に自動化されており、人的関与はユーザーのコンテンツによって高度に制御および抽象化されています。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-296">Nearly all service operations performed by Microsoft are fully automated and human involvement is highly controlled and abstracted away from customer content.</span></span> <span data-ttu-id="3f7c6-297">Office 365 の目標は、お客様が Microsoft access の特定の要求を承認するまで、サービスをサポートするためにお客様のコンテンツにアクセスすることです。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-297">The goal for Office 365 is access to customer content to support the service isn't needed until the customer approves a specific request for Microsoft access.</span></span>

#### <a name="i-already-thought-my-data-was-secure-with-the-microsoft-cloud-so-why-do-i-need-customer-lockbox"></a><span data-ttu-id="3f7c6-298">Microsoft クラウドでデータをセキュリティで保護したことが既に考えられていますが、なぜお客様のロックボックスが必要ですか?</span><span class="sxs-lookup"><span data-stu-id="3f7c6-298">I already thought my data was secure with the Microsoft cloud, so why do I need Customer Lockbox?</span></span>

<span data-ttu-id="3f7c6-299">カスタマーロックボックスは、サービス操作の明示的なアクセス承認を提供する機能をお客様に提供することによって、特別な制御層を提供します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-299">Customer Lockbox provides an extra layer of control by offering customers the ability to give explicit access authorization for service operations.</span></span> <span data-ttu-id="3f7c6-300">明示的なデータアクセス承認のためにプロシージャが配置されていることを示すことにより、お客様のロックボックスは、顧客が HIPAA、FEDRAMP などの特定のコンプライアンス義務を満たすのを支援します。</span><span class="sxs-lookup"><span data-stu-id="3f7c6-300">By demonstrating that procedures are in place for explicit data access authorization, Customer Lockbox also helps customers meet certain compliance obligations such as HIPAA and FEDRAMP.</span></span>
