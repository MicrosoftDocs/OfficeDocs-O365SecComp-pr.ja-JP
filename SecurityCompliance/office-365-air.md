---
title: Office 365 で脅威に自動的に調査して応答する
keywords: AIR、自動赤外線、ATP、自動化、調査、応答、修復、脅威、高度、脅威、保護
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Office 365 Advanced Threat Protection プラン2の自動調査および応答機能の使用を開始します。
ms.openlocfilehash: c2c2b9a0409c472c99b07293a002f9bdbf6c5090
ms.sourcegitcommit: e6c0d9aea3172a5ccc6c7943625d69144ba20aca
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2019
ms.locfileid: "36790931"
---
# <a name="automatically-investigate-and-respond-to-threats-in-office-365"></a><span data-ttu-id="fc5bd-104">Office 365 で脅威に自動的に調査して応答する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-104">Automatically investigate and respond to threats in Office 365</span></span>

## <a name="overview"></a><span data-ttu-id="fc5bd-105">概要</span><span class="sxs-lookup"><span data-stu-id="fc5bd-105">Overview</span></span>

<span data-ttu-id="fc5bd-106">[Office 365 Advanced Threat Protection](office-365-atp.md)プラン2には自動調査と応答 (AIR) 機能が含まれており、セキュリティ運用チームの時間と、アラートと脅威を処理するための労力を節約できます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-106">[Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2 includes automated investigation and response (AIR) capabilities that can save your security operations team time and effort in dealing with alerts and threats.</span></span> <span data-ttu-id="fc5bd-107">Office 365 の機能の使用を開始するには、この記事をお読みください。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-107">Read this article to get started using AIR capabilities in Office 365.</span></span> <span data-ttu-id="fc5bd-108">空気のしくみの詳細については、「 [Office 365 での自動調査と応答 (AIR)](automated-investigation-response-office.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-108">To learn more about how AIR works, see [Automated Investigation and Response (AIR) with Office 365](automated-investigation-response-office.md).</span></span>

<span data-ttu-id="fc5bd-109">AIR を使用すると、特定のアラートがトリガーされ、1つ以上のセキュリティプレイブックが開始され、自動調査が開始します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-109">With AIR, when certain alerts are triggered, one or more security playbooks initiate, and automated investigation begins.</span></span> <span data-ttu-id="fc5bd-110">自動化された調査プロセスの最中および実行後に、管理者およびセキュリティ運用チームは次のことを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-110">During and after an automated investigation process, your administrators and security operations team can:</span></span>

- [<span data-ttu-id="fc5bd-111">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-111">View the details of an investigation</span></span>](#view-details-of-an-investigation)

- [<span data-ttu-id="fc5bd-112">調査の結果としてアクションを確認して承認する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-112">Review and approve actions as a result of an investigation</span></span>](#review-and-approve-actions) 

- [<span data-ttu-id="fc5bd-113">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-113">View details about an alert related to an investigation</span></span>](#view-details-about-an-alert-related-to-an-investigation)

> [!NOTE]
> <span data-ttu-id="fc5bd-114">この記事で説明されているタスクを実行するには、全体管理者、セキュリティ管理者、セキュリティオペレーター、またはセキュリティリーダーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-114">You must be a global administrator, security administrator, security operator, or security reader to perform the tasks described in this article.</span></span> <span data-ttu-id="fc5bd-115">詳細については、「 [Microsoft 365 セキュリティセンター: 役割とアクセス許可](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-115">To learn more, see [Microsoft 365 security center: roles and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

## <a name="view-details-of-an-investigation"></a><span data-ttu-id="fc5bd-116">調査の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-116">View details of an investigation</span></span>

1. <span data-ttu-id="fc5bd-117">Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-117">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="fc5bd-118">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-118">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="fc5bd-119">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-119">Do one of the following:</span></span>

    - <span data-ttu-id="fc5bd-120">[**脅威管理** > ]**ダッシュボード**に移動します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-120">Go to **Threat management** > **Dashboard**.</span></span> <span data-ttu-id="fc5bd-121">これにより、[セキュリティダッシュボード](security-dashboard.md)が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-121">This takes you to the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="fc5bd-122">エアウィジェットは、[セキュリティダッシュボード](security-dashboard.md)の上部に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-122">Your AIR widgets appear across the top of the [Security Dashboard](security-dashboard.md).</span></span> <span data-ttu-id="fc5bd-123">**調査の概要**などのウィジェットを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-123">Select a widget, such as **Investigations summary**.</span></span>

    - <span data-ttu-id="fc5bd-124">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-124">Go to **Threat management** > **Investigations**.</span></span> 

    <span data-ttu-id="fc5bd-125">どちらの方法でも、調査の一覧を取得できます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-125">Either method takes you to a list of investigations.</span></span>

    ![エアのメイン調査ページ](media/air-maininvestigationpage.png) 

3. <span data-ttu-id="fc5bd-127">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-127">In the list of investigations, select an item in the **ID** column.</span></span> <span data-ttu-id="fc5bd-128">これにより、調査の詳細ページが表示され、調査のグラフが開始されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-128">This opens investigation details page, starting with the investigation graph.</span></span>

    ![AIR 調査グラフページ](media/air-investigationgraphpage.png)

4. <span data-ttu-id="fc5bd-130">調査の詳細については、さまざまなタブを使用してください。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-130">Use the various tabs to learn more about the investigation.</span></span>

## <a name="review-and-approve-actions"></a><span data-ttu-id="fc5bd-131">アクションの確認と承認</span><span class="sxs-lookup"><span data-stu-id="fc5bd-131">Review and approve actions</span></span>

<span data-ttu-id="fc5bd-132">Office 365 では、通常、自動調査は1つまたは複数の推奨されるアクションになります。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-132">In Office 365, automated investigations typically result in one or more recommended actions.</span></span> <span data-ttu-id="fc5bd-133">ただし、セキュリティ運用チームによって承認されるまで、アクションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-133">However, no actions are taken until they are approved by your security operations team.</span></span> <span data-ttu-id="fc5bd-134">アクションを確認して承認するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-134">Use the following procedure to review and approve actions.</span></span>

1. <span data-ttu-id="fc5bd-135">Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-135">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> 

2. <span data-ttu-id="fc5bd-136">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-136">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="fc5bd-137">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-137">In the list of investigations, select an item in the **ID** column.</span></span> 

3. <span data-ttu-id="fc5bd-138">調査の詳細ビューで、[**操作**] タブを選択します。承認待ちのすべてのアクションがここに表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-138">On the investigation details view, select the **Actions** tab. Any actions that are pending approval are listed here.</span></span>

4. <span data-ttu-id="fc5bd-139">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-139">Select an item in the list.</span></span>

5. <span data-ttu-id="fc5bd-140">推奨されるアクションを実行する場合は [**承認**] を選択します (アクションを行わずに調査を終了する場合は**拒否**)。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-140">Select **Approve** to take the recommended action (or **Reject** to close the investigation without taking action).</span></span>

## <a name="view-details-about-an-alert-related-to-an-investigation"></a><span data-ttu-id="fc5bd-141">調査に関連する通知の詳細を表示する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-141">View details about an alert related to an investigation</span></span>

<span data-ttu-id="fc5bd-142">特定の種類の通知では、Office 365 で自動調査がトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-142">Certain kinds of alerts trigger automated investigation in Office 365.</span></span> <span data-ttu-id="fc5bd-143">詳細については、「 [Alerts](automated-investigation-response-office.md#alerts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-143">To learn more, see [Alerts](automated-investigation-response-office.md#alerts).</span></span> <span data-ttu-id="fc5bd-144">次の手順を使用して、自動調査に関連付けられている通知の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-144">Use the following procedure to view details about an alert that is associated with an automated investigation.</span></span>

1. <span data-ttu-id="fc5bd-145">Office 365 の全体管理者、セキュリティ管理者、またはセキュリティ閲覧者[https://protection.office.com](https://protection.office.com)として、に移動して、サインインします。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-145">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="fc5bd-146">これにより、セキュリティ & コンプライアンスセンターに移動できます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-146">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="fc5bd-147">[**脅威管理** > の**調査**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-147">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="fc5bd-148">調査の一覧で、[ **ID** ] 列のアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-148">In the list of investigations, select an item in the **ID** column.</span></span> 

4. <span data-ttu-id="fc5bd-149">調査の詳細を開いた状態で、[**通知**] タブを選択します。調査をトリガーしたアラートが一覧表示されています。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-149">With details of an investigation open, select the **Alerts** tab. Any alerts that triggered the investigation are listed here.</span></span>

5. <span data-ttu-id="fc5bd-150">リストからアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-150">Select an item in the list.</span></span> <span data-ttu-id="fc5bd-151">ポップアップが開き、通知に関する詳細と追加情報およびアクションへのリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-151">A flyout opens, with details about the alert and links to additional information and actions.</span></span>

6. <span data-ttu-id="fc5bd-152">ポップアップの情報を確認し、特定の通知に応じて、ユーザーの**解決**、**抑制**、または**通知**などのアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-152">Review the information on the flyout, and, depending on the particular alert, take an action, such as **Resolve**, **Suppress**, or **Notify users**.</span></span> 

    - <span data-ttu-id="fc5bd-153">**解決**は通知を閉じることと同じです。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-153">**Resolve** is equivalent to closing an alert</span></span>
    
    - <span data-ttu-id="fc5bd-154">**抑制**すると、指定した期間、ポリシーがアラートをトリガーしなくなります。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-154">**Suppress** causes a policy to not trigger alerts for a specified period of time</span></span>
    
    - <span data-ttu-id="fc5bd-155">**通知**ユーザーに既に入力されたユーザーのメールアドレスを使用してメールを開始し、セキュリティ運用チームがそれらのユーザーにメッセージを入力できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-155">**Notify users** starts an email with users' email addresses already entered, and enables your security operations team to type a message to those users.</span></span> <span data-ttu-id="fc5bd-156">(これは、[脅威エクスプローラー](threat-explorer.md)を使用してメッセージを受信者に送信するのと似ています。)</span><span class="sxs-lookup"><span data-stu-id="fc5bd-156">(This is similar to sending a message to recipients using [Threat Explorer](threat-explorer.md).)</span></span>  

## <a name="use-the-office-365-management-activity-api-for-custom-or-third-party-reporting-solutions"></a><span data-ttu-id="fc5bd-157">カスタムまたはサードパーティのレポートソリューションに Office 365 Management Activity API を使用する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-157">Use the Office 365 Management Activity API for custom or third-party reporting solutions</span></span>

<span data-ttu-id="fc5bd-158">組織でカスタムレポートソリューションを使用している場合、またはサードパーティのレポートソリューションを使用している場合は、Office 365 Management Activity API を使用して、そのソリューションの自動化された調査に関する情報を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-158">If your organization is using a custom reporting solution, or a third-party reporting solution, you can view information about automated investigations in that solution by using the Office 365 Management Activity API.</span></span>

<span data-ttu-id="fc5bd-159">これを設定するには、次のリソースを使用します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-159">Use the following resources to set this up:</span></span>

|<span data-ttu-id="fc5bd-160">リソース</span><span class="sxs-lookup"><span data-stu-id="fc5bd-160">Resource</span></span>  |<span data-ttu-id="fc5bd-161">説明</span><span class="sxs-lookup"><span data-stu-id="fc5bd-161">Description</span></span>  |
|---------|---------|
|[<span data-ttu-id="fc5bd-162">Office 365 管理 API の概要</span><span class="sxs-lookup"><span data-stu-id="fc5bd-162">Office 365 Management APIs overview</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)     |<span data-ttu-id="fc5bd-163">Office 365 管理アクティビティ API は、Office 365 と Azure Active Directory のアクティビティ ログからの、ユーザー、管理者、システム、およびポリシー アクションとポリシー イベントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-163">The Office 365 Management Activity API provides information about various user, admin, system, and policy actions and events from Office 365 and Azure Active Directory activity logs.</span></span>         |
|[<span data-ttu-id="fc5bd-164">Office 365 管理 API の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-164">Get started with Office 365 Management APIs</span></span>](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)     |<span data-ttu-id="fc5bd-165">Office 365 管理 API は、Azure AD を使用して、アプリケーションが Office 365 データにアクセスするための認証サービスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-165">The Office 365 Management API uses Azure AD to provide authentication services for your application to access Office 365 data.</span></span> <span data-ttu-id="fc5bd-166">これを設定するには、この記事の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-166">Follow the steps in this article to set this up.</span></span>          |
|[<span data-ttu-id="fc5bd-167">Office 365 管理アクティビティ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="fc5bd-167">Office 365 Management Activity API reference</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)     |<span data-ttu-id="fc5bd-168">Office 365 Management Activity API を使用して、Office 365 および Azure AD のアクティビティログから、ユーザー、管理者、システム、およびポリシーのアクションとイベントに関する情報を取得することができます。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-168">You can use the Office 365 Management Activity API to retrieve information about user, admin, system, and policy actions and events from Office 365 and Azure AD activity logs.</span></span> <span data-ttu-id="fc5bd-169">この機能の詳細については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-169">Read this article to learn more about how this works.</span></span>        |
|[<span data-ttu-id="fc5bd-170">Office 365 管理アクティビティ API のスキーマ</span><span class="sxs-lookup"><span data-stu-id="fc5bd-170">Office 365 Management Activity API schema</span></span>](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)     |<span data-ttu-id="fc5bd-171">Office 365 Management Activity API を通じて使用できる特定の種類のデータについて理解するために、[共通スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema)と[OFFICE 365 の ATP および脅威の調査および応答スキーマ](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)の概要を説明します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-171">Get an overview of the [Common schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#common-schema) and the [Office 365 ATP and threat investigation and response schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) to learn about specific kinds of data available through the Office 365 Management Activity API.</span></span>         |

## <a name="next-steps"></a><span data-ttu-id="fc5bd-172">次のステップ</span><span class="sxs-lookup"><span data-stu-id="fc5bd-172">Next steps</span></span>

[<span data-ttu-id="fc5bd-173">通知の詳細情報</span><span class="sxs-lookup"><span data-stu-id="fc5bd-173">Learn more about alerts</span></span>](alert-policies.md)

[<span data-ttu-id="fc5bd-174">Office 365 で配信された悪意のある電子メールを手動で検索して調査する</span><span class="sxs-lookup"><span data-stu-id="fc5bd-174">Manually find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)

[<span data-ttu-id="fc5bd-175">Microsoft Defender ATP のエアダスターの詳細</span><span class="sxs-lookup"><span data-stu-id="fc5bd-175">Learn about AIR in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

[<span data-ttu-id="fc5bd-176">Microsoft 365 ロードマップを参照して、近日中およびロールアウトされているものを確認します。</span><span class="sxs-lookup"><span data-stu-id="fc5bd-176">Visit the Microsoft 365 Roadmap to see what's coming soon and rolling out</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=)