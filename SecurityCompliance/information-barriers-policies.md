---
title: 情報バリアポリシーの定義
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Microsoft Teams の情報障壁に関するポリシーを定義する方法について説明します。
ms.openlocfilehash: 3ec9d89f22456f00104135013ee6009e8e4824df
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668318"
---
# <a name="define-policies-for-information-barriers-preview"></a><span data-ttu-id="51bc3-103">情報バリアのポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="51bc3-103">Define policies for information barriers (Preview)</span></span>

<span data-ttu-id="51bc3-104">情報の障壁を使用すると、特定のユーザーセグメントが相互に通信するのを防ぐように設計されたポリシーを定義したり、特定のセグメントのみが特定のセグメントと通信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-104">With information barriers, you can define policies that are designed to prevent certain segments of users from communicating with each other, or allow specific segments to communicate only with certain other segments.</span></span> <span data-ttu-id="51bc3-105">情報バリアポリシーは、組織が関連する業界標準および規制に準拠し、潜在的な競合を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-105">Information barrier policies can help your organization maintain compliance with relevant industry standards and regulations, and avoid potential conflicts of interest.</span></span> <span data-ttu-id="51bc3-106">詳細については、「[情報の障壁 (プレビュー)](information-barriers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-106">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="51bc3-107">この記事では、情報バリアポリシーを計画、定義、実装、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-107">This article describes how to plan, define, implement, and manage information barrier policies.</span></span> <span data-ttu-id="51bc3-108">いくつかの手順が関係しており、作業フローはいくつかの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-108">Several steps are involved, and the work flow is divided into several parts.</span></span> <span data-ttu-id="51bc3-109">情報バリアポリシーの定義 (または編集) を開始する前に、必ず[前提条件](#prerequisites)とプロセス全体に目を通してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-109">Make sure to read through the [prerequisites](#prerequisites) and the entire process before you begin defining (or editing) information barrier policies.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="51bc3-110">情報バリアポリシーの概念</span><span class="sxs-lookup"><span data-stu-id="51bc3-110">Concepts of information barrier policies</span></span>

<span data-ttu-id="51bc3-111">情報バリアポリシーを計画、定義、および実装する前に、基になる概念を理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-111">Before you plan, define, and implement information barrier policies, get to know the underlying concepts.</span></span> <span data-ttu-id="51bc3-112">情報の障壁を使用して、この記事で説明されているユーザーアカウントの属性、セグメント、情報バリアポリシー、およびポリシーアプリケーションプロセスを操作できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-112">With information barriers, you'll work with user account attributes, segments, information barrier policies, and a policy application process described in this article.</span></span> 

- <span data-ttu-id="51bc3-113">**ユーザーアカウントの属性**は、Azure Active Directory (または Exchange Online) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-113">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="51bc3-114">これらの属性には、部署、役職、場所、チーム名などを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-114">These attributes can include department, job title, location, team name, etc.</span></span> 

- <span data-ttu-id="51bc3-115">**セグメント**は、Office 365 セキュリティ & コンプライアンスセンターで、部署、役職、場所、チーム名、[サポートさ](information-barriers-attributes.md)れている任意の属性など、選択された**ユーザーアカウント属性**を使用して定義されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-115">**Segments** are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**, such as department, job title, location, team name, or any [supported attribute](information-barriers-attributes.md).</span></span> <span data-ttu-id="51bc3-116">セグメントを定義しても、ユーザーに影響はありません。情報バリアポリシーが定義され、適用される段階を設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="51bc3-116">Defining segments does not effect users; it just sets the stage for information barrier policies to be defined and then applied.</span></span>

- <span data-ttu-id="51bc3-117">**情報バリアポリシー**は、個々の**セグメント**に定義され、割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-117">**Information barrier policies** are defined and assigned to individual **Segments**.</span></span> <span data-ttu-id="51bc3-118">すべてのセグメントにポリシーが割り当てられるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-118">Not all segments will have a policy assigned.</span></span> <span data-ttu-id="51bc3-119">また、1つのセグメントに複数のポリシーを割り当てることはできません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-119">In addition, no single segment can be assigned more than one policy.</span></span> <span data-ttu-id="51bc3-120">ポリシーを定義するときは、次の2種類のポリシーから選択します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-120">When you define policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="51bc3-121">1つのセグメントが別のセグメントと通信できないようにするポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-121">Policies that prevent one segment from communicating with another segment</span></span>
    - <span data-ttu-id="51bc3-122">1つのセグメントのみが特定の他のセグメントと通信できるようにするポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-122">Policies that allow one segment to communicate with only certain other segments</span></span>

    <span data-ttu-id="51bc3-123">組織が法律上および業界の要件を満たしていることを確認するために、最小限のポリシーを使用することが理想的です。</span><span class="sxs-lookup"><span data-stu-id="51bc3-123">Ideally, you'll use the minimum number of policies to ensure your organization is compliant with legal and industry requirements.</span></span>

- <span data-ttu-id="51bc3-124">**ポリシーアプリケーション**は、すべての情報バリアポリシーが定義された後に実行され、組織に適用する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-124">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="51bc3-125">作業フローの概要</span><span class="sxs-lookup"><span data-stu-id="51bc3-125">The work flow at a glance</span></span>

|<span data-ttu-id="51bc3-126">フェーズ</span><span class="sxs-lookup"><span data-stu-id="51bc3-126">Phase</span></span>    |<span data-ttu-id="51bc3-127">関係するもの</span><span class="sxs-lookup"><span data-stu-id="51bc3-127">What's involved</span></span>  |
|---------|---------|
|[<span data-ttu-id="51bc3-128">前提条件が満たされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="51bc3-128">Make sure prerequisites are met</span></span>](#prerequisites)     |<span data-ttu-id="51bc3-129">-サブスクリプションに情報の障壁が含まれていることを確認する</span><span class="sxs-lookup"><span data-stu-id="51bc3-129">- Confirm that your subscription includes information barriers</span></span><br/><span data-ttu-id="51bc3-130">-セグメントとポリシーの定義/編集に必要なアクセス許可を持っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="51bc3-130">- Verify that you have the necessary permissions to define/edit segments and policies</span></span><br/><span data-ttu-id="51bc3-131">-ディレクトリデータが組織の構造を反映していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-131">- Make sure that your directory data reflects your organization's structure</span></span><br/><span data-ttu-id="51bc3-132">-スコープ付きディレクトリ検索が Microsoft Teams で有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-132">- Make sure that scoped directory search is enabled in Microsoft Teams</span></span><br/><span data-ttu-id="51bc3-133">-監査ログが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-133">- Make sure audit logging is turned on</span></span><br/><span data-ttu-id="51bc3-134">-PowerShell を使用してこの記事のタスクを実行します (コマンドレットの例を示します)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-134">- Use PowerShell to perform the tasks in this article (example cmdlets are provided)</span></span><br/><span data-ttu-id="51bc3-135">-Microsoft Teams の情報障壁に対する管理者の同意を提供します (手順は含まれています)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-135">- Provide admin consent for information barriers in Microsoft Teams (steps are included)</span></span>          |
|[<span data-ttu-id="51bc3-136">パート 1: 組織内のすべてのユーザーのセグメント化</span><span class="sxs-lookup"><span data-stu-id="51bc3-136">Part 1: Segment all the users in your organization</span></span>](#part-1-segment-users)     |<span data-ttu-id="51bc3-137">-必要なポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="51bc3-137">- Determine what policies are needed</span></span><br/><span data-ttu-id="51bc3-138">-定義するセグメントの一覧を作成する</span><span class="sxs-lookup"><span data-stu-id="51bc3-138">- Make a list of segments to define</span></span><br/><span data-ttu-id="51bc3-139">-使用する属性を識別する</span><span class="sxs-lookup"><span data-stu-id="51bc3-139">- Identify which attributes to use</span></span><br/><span data-ttu-id="51bc3-140">-ポリシーフィルターの観点からセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="51bc3-140">- Define segments in terms of policy filters</span></span>        |
|[<span data-ttu-id="51bc3-141">パート 2: 情報バリアポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="51bc3-141">Part 2: Define information barrier policies</span></span>](#part-2-define-information-barrier-policies)     |<span data-ttu-id="51bc3-142">-ポリシーを定義します (まだ適用しない)</span><span class="sxs-lookup"><span data-stu-id="51bc3-142">- Define your policies (do not apply yet)</span></span><br/><span data-ttu-id="51bc3-143">-2 つの種類 (ブロックまたは許可) から選択します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-143">- Choose from two kinds (block or allow)</span></span> |
|[<span data-ttu-id="51bc3-144">パート 3: 情報バリアポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="51bc3-144">Part 3: Apply information barrier policies</span></span>](#part-3-apply-information-barrier-policies)     |<span data-ttu-id="51bc3-145">-ポリシーをアクティブな状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-145">- Set policies to active status</span></span><br/><span data-ttu-id="51bc3-146">-ポリシーアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="51bc3-146">- Run the policy application</span></span><br/><span data-ttu-id="51bc3-147">-ポリシーの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="51bc3-147">- Verify policy status</span></span>         |
|<span data-ttu-id="51bc3-148">(必要な場合)[セグメントまたはポリシーを編集する](#edit-a-segment-or-a-policy)</span><span class="sxs-lookup"><span data-stu-id="51bc3-148">(As needed) [Edit a segment or a policy](#edit-a-segment-or-a-policy)</span></span>     |<span data-ttu-id="51bc3-149">-セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="51bc3-149">- Edit a segment</span></span><br/><span data-ttu-id="51bc3-150">-ポリシーを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="51bc3-150">- Edit or remove a policy</span></span><br/><span data-ttu-id="51bc3-151">-ポリシーアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="51bc3-151">- Run the policy application</span></span><br/><span data-ttu-id="51bc3-152">-ポリシーの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="51bc3-152">- Verify policy status</span></span>         |
|<span data-ttu-id="51bc3-153">(必要な場合)[トラブルシューティング](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="51bc3-153">(As needed) [Troubleshooting](information-barriers-troubleshooting.md)</span></span>|<span data-ttu-id="51bc3-154">-ポリシーが期待どおりに機能していない場合に処理を実行する</span><span class="sxs-lookup"><span data-stu-id="51bc3-154">- Take action when policies are not working as expected</span></span>|

## <a name="prerequisites"></a><span data-ttu-id="51bc3-155">前提条件</span><span class="sxs-lookup"><span data-stu-id="51bc3-155">Prerequisites</span></span>

<span data-ttu-id="51bc3-156">**現時点では、情報バリア機能はプライベートプレビューに**あります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-156">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="51bc3-157">これらの機能が一般公開されると、次のようなサブスクリプションに含まれます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-157">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="51bc3-158">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="51bc3-158">Microsoft 365 E5</span></span>
- <span data-ttu-id="51bc3-159">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="51bc3-159">Office 365 E5</span></span>
- <span data-ttu-id="51bc3-160">Office 365 Advanced Compliance</span><span class="sxs-lookup"><span data-stu-id="51bc3-160">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="51bc3-161">Microsoft 365 E5 情報の保護とコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="51bc3-161">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="51bc3-162">詳細については、「[コンプライアンスソリューション](https://products.office.com/business/security-and-compliance/compliance-solutions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-162">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

### <a name="permissions"></a><span data-ttu-id="51bc3-163">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="51bc3-163">Permissions</span></span>

<span data-ttu-id="51bc3-164">情報バリアポリシーを定義または編集するには、次のいずれかのような**適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-164">To define or edit information barrier policies, **you must be assigned an appropriate role**, such as one of the following:</span></span>
- <span data-ttu-id="51bc3-165">Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="51bc3-165">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="51bc3-166">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="51bc3-166">Office 365 Global Administrator</span></span>
- <span data-ttu-id="51bc3-167">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="51bc3-167">Compliance Administrator</span></span>
- <span data-ttu-id="51bc3-168">IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="51bc3-168">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="51bc3-169">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-169">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
       
### <a name="directory-data"></a><span data-ttu-id="51bc3-170">ディレクトリデータ</span><span class="sxs-lookup"><span data-stu-id="51bc3-170">Directory data</span></span>

<span data-ttu-id="51bc3-171">**組織の構造がディレクトリデータに反映されていることを確認し**ます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-171">**Make sure that your organization's structure is reflected in directory data**.</span></span> <span data-ttu-id="51bc3-172">これを行うには、Azure Active Directory (または Exchange Online) に、グループメンバーシップ、部署名などのユーザーアカウント属性が正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-172">To do this, make sure that user account attributes, such as group membership, department name, etc. are populated correctly in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="51bc3-173">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-173">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="51bc3-174">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="51bc3-174">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="51bc3-175">Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する</span><span class="sxs-lookup"><span data-stu-id="51bc3-175">Add or update a user's profile information using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
- [<span data-ttu-id="51bc3-176">Office 365 PowerShell でユーザー アカウント プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="51bc3-176">Configure user account properties with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

### <a name="scoped-directory-search"></a><span data-ttu-id="51bc3-177">スコープ付きディレクトリ検索</span><span class="sxs-lookup"><span data-stu-id="51bc3-177">Scoped directory search</span></span>

<span data-ttu-id="51bc3-178">**組織の最初の情報バリアポリシーを定義する前に、 [Microsoft Teams でスコープ付きディレクトリ検索を有効](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)にする必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-178">**Before you define your organization's first information barrier policy, you must [enable scoped directory search in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)**.</span></span> <span data-ttu-id="51bc3-179">情報バリアポリシーを設定または定義する前に、スコープ付きディレクトリ検索を有効にした後、少なくとも24時間待機します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-179">Wait at least 24 hours after enabling scoped directory search before you set up or define information barrier policies.</span></span>

### <a name="audit-logging"></a><span data-ttu-id="51bc3-180">監査ログ</span><span class="sxs-lookup"><span data-stu-id="51bc3-180">Audit logging</span></span>

<span data-ttu-id="51bc3-181">ポリシーアプリケーションの状態を参照するには、監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-181">In order to look up the status of a policy application, audit logging must be turned on.</span></span> <span data-ttu-id="51bc3-182">セグメントまたはポリシーの定義を開始する前に、この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-182">We recommend doing this before you begin to define segments or policies.</span></span> <span data-ttu-id="51bc3-183">詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-183">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

### <a name="powershell"></a><span data-ttu-id="51bc3-184">PowerShell</span><span class="sxs-lookup"><span data-stu-id="51bc3-184">PowerShell</span></span>

<span data-ttu-id="51bc3-185">**現時点で、情報バリアポリシーは、PowerShell コマンドレットを使用して Office 365 セキュリティ & コンプライアンスセンターで定義および管理され**ます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-185">**Currently, information barrier policies are defined and managed in the Office 365 Security & Compliance Center using PowerShell cmdlets**.</span></span> <span data-ttu-id="51bc3-186">この記事では、いくつかのシナリオと例が提供されていますが、PowerShell のコマンドレットとパラメーターについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-186">Although several scenarios and examples are provided in this article, you'll need to be familiar with PowerShell cmdlets and parameters.</span></span> 

<span data-ttu-id="51bc3-187">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-187">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="provide-admin-consent-for-information-barriers-in-microsoft-teams"></a><span data-ttu-id="51bc3-188">Microsoft Teams の情報障壁に対する管理者の同意を提供する</span><span class="sxs-lookup"><span data-stu-id="51bc3-188">Provide admin consent for information barriers in Microsoft Teams</span></span>

<span data-ttu-id="51bc3-189">次の手順を使用して、Microsoft Teams で情報バリアポリシーが期待どおりに動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-189">Use the following procedure to enable information barrier policies to work as expected in Microsoft Teams.</span></span> 

<span data-ttu-id="51bc3-190">たとえば、ポリシーが適切に設定されている場合、情報障壁によって、チャットセッションからユーザーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-190">For example, when your policies are in place, information barriers can remove people from chat sessions they are not supposed to be in.</span></span> <span data-ttu-id="51bc3-191">これにより、組織はポリシーと規制に準拠したままになります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-191">This helps ensure your organization remains compliant with policies and regulations.</span></span> 

1. <span data-ttu-id="51bc3-192">次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-192">Run the following PowerShell cmdlets:</span></span>

    ```
    Login-AzureRmAccount 
    $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
    $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
    if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
    Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
    ```

2. <span data-ttu-id="51bc3-193">メッセージが表示されたら、Office 365 の職場または学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-193">When prompted, sign in using your work or school account for Office 365.</span></span>

3. <span data-ttu-id="51bc3-194">[**要求されたアクセス許可**] ダイアログボックスで情報を確認し、[**同意**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-194">In the **Permissions requested** dialog box, review the information, and then choose **Accept**.</span></span>

## <a name="part-1-segment-users"></a><span data-ttu-id="51bc3-195">パート 1: セグメントユーザー</span><span class="sxs-lookup"><span data-stu-id="51bc3-195">Part 1: Segment users</span></span>

<span data-ttu-id="51bc3-196">このフェーズでは、必要なポリシーを決定し、定義するセグメントの一覧を作成して、セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-196">During this phase, you determine what policies are needed, make a list of segments to define, and then define your segments.</span></span>

### <a name="determine-what-policies-are-needed"></a><span data-ttu-id="51bc3-197">必要なポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="51bc3-197">Determine what policies are needed</span></span>

<span data-ttu-id="51bc3-198">法的および業界の規制を考慮しています。組織内で情報の障壁ポリシーを必要とするグループは誰ですか。</span><span class="sxs-lookup"><span data-stu-id="51bc3-198">Considering legal and industry regulations, who are the groups within your organization who will need information barrier policies?</span></span> <span data-ttu-id="51bc3-199">リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-199">Make a list.</span></span> <span data-ttu-id="51bc3-200">他のグループとの通信を禁止する必要があるグループはありますか。</span><span class="sxs-lookup"><span data-stu-id="51bc3-200">Are there any groups who should be prevented from communicating with another group?</span></span> <span data-ttu-id="51bc3-201">1つまたは2つの他のグループとのみ通信できるようにする必要があるグループはありますか。</span><span class="sxs-lookup"><span data-stu-id="51bc3-201">Are there any groups that should be allowed to communicate only with one or two other groups?</span></span> <span data-ttu-id="51bc3-202">次の2つのグループのいずれかに属している必要があるポリシーについて考えます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-202">Think about the policies you need as belonging to one of two groups:</span></span>
- <span data-ttu-id="51bc3-203">あるグループが別のグループと通信できないようにする**ポリシーをブロック**する</span><span class="sxs-lookup"><span data-stu-id="51bc3-203">**Blocking policies** that prevent one group from communicating with another group</span></span>
- <span data-ttu-id="51bc3-204">特定のグループだけが特定の他のグループと通信できるようにする**ポリシーを許可**します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-204">**Allow policies** that allow certain groups to communicate with only certain other groups.</span></span>

<span data-ttu-id="51bc3-205">最初にグループとポリシーの一覧を作成したら、次の手順を実行して、必要なセグメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-205">When you have your initial list of groups and policies, proceed to identify the segments you'll need.</span></span>

<span data-ttu-id="51bc3-206">(この記事の「 [Example: Contoso 社の部署と計画](#contosos-departments-and-plan)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-206">(See [Example: Contoso's departments and plan](#contosos-departments-and-plan) in this article.)</span></span>

### <a name="identify-segments"></a><span data-ttu-id="51bc3-207">セグメントを識別する</span><span class="sxs-lookup"><span data-stu-id="51bc3-207">Identify segments</span></span>

<span data-ttu-id="51bc3-208">ポリシーの初期リストに加えて、組織のセグメントの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-208">In addition to your initial list of policies, make a list of segments for your organization.</span></span> <span data-ttu-id="51bc3-209">組織内のすべてのユーザーはセグメントに属している必要があり、ユーザーは2つ以上のセグメントに所属している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-209">Every user in your organization should belong to a segment, and no user should belong to two or more segments.</span></span> <span data-ttu-id="51bc3-210">各セグメントには、1つの情報バリアポリシーのみを適用できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-210">Each segment can have only one information barrier policy applied.</span></span> 

<span data-ttu-id="51bc3-211">セグメントを定義するために使用する組織のディレクトリデータの属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-211">Determine which attributes in your organization's directory data you'll use to define segments.</span></span> <span data-ttu-id="51bc3-212">*Department*、 *MemberOf*、またはサポートされている属性のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-212">You can use *Department*, *MemberOf*, or any of the supported attributes.</span></span> <span data-ttu-id="51bc3-213">すべてのユーザーに対して選択する属性に値が設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-213">Make sure that you have values in the attribute you select for all users.</span></span> <span data-ttu-id="51bc3-214">サポートされている属性の一覧を表示するには、「[情報バリアポリシーの属性 (プレビュー)](information-barriers-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-214">To see a list of supported attributes, refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51bc3-215">**次のセクションに進む前に、セグメントを定義するために使用できる属性の値がディレクトリデータにあることを確認して**ください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-215">**Before you proceed to the next section, make sure your directory data has values for attributes that you can use to define segments**.</span></span> <span data-ttu-id="51bc3-216">ディレクトリデータに使用する属性の値が含まれていない場合は、情報の障壁を処理する前に、すべてのユーザーアカウントにその情報を含めるように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-216">If your directory data does not have values for the attributes you want to use, then all user accounts must be updated to include that information before you proceed with information barriers.</span></span> <span data-ttu-id="51bc3-217">これに関するヘルプを表示するには、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-217">To get help with this, see the following resources:</span></span><br/><span data-ttu-id="51bc3-218">- [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="51bc3-218">- [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span></span><br/><span data-ttu-id="51bc3-219">- [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="51bc3-219">- [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span></span>

### <a name="define-segments-using-powershell"></a><span data-ttu-id="51bc3-220">PowerShell を使用してセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="51bc3-220">Define segments using PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51bc3-221">**セグメントが重ならないようにして**ください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-221">**Make sure that your segments do not overlap**.</span></span> <span data-ttu-id="51bc3-222">組織内の各ユーザーは、1つ (1 つの) セグメントに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-222">Each user in your organization should belong to one (and only one) segment.</span></span> <span data-ttu-id="51bc3-223">ユーザーは、2つ以上のセグメントに属することはできません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-223">No user should belong to two or more segments.</span></span> <span data-ttu-id="51bc3-224">セグメントは、組織内のすべてのユーザーに対して定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-224">Segments should be defined for all users in your organization.</span></span> <span data-ttu-id="51bc3-225">(この記事の「 [Example: Contoso の定義済みセグメント](#contosos-defined-segments)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-225">(See [Example: Contoso's defined segments](#contosos-defined-segments) in this article.)</span></span>

1. <span data-ttu-id="51bc3-226">組織セグメントを定義するには、使用する[属性](information-barriers-attributes.md)に対応する**usergroupfilter**パラメーターを指定して、**新しい-組織**セグメントコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-226">To define an organizational segment, use the **New-OrganizationSegment** cmdlet with the **UserGroupFilter** parameter that corresponds to the [attribute](information-barriers-attributes.md) you want to use.</span></span> 

    <span data-ttu-id="51bc3-227">文`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-227">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="51bc3-228">例: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-228">Example: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span></span>

    <span data-ttu-id="51bc3-229">この例では、hr と\*\* いう名前のセグメント\*\* が、Department 属性の値を使用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-229">In this example, a segment called *HR* is defined using *HR*, a value in the Department attribute.</span></span>

2. <span data-ttu-id="51bc3-230">定義するセグメントごとに、手順1を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-230">Repeat step 1 for each segment you want to define.</span></span>

    <span data-ttu-id="51bc3-231">各コマンドレットを実行すると、新しいセグメントに関する詳細情報の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-231">After you run each cmdlet, you should see a list of details about the new segment.</span></span> <span data-ttu-id="51bc3-232">詳細には、セグメントの種類、作成者または最終更新日時などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-232">Details include the segment's type, who created or last modified it, and so on.</span></span> 

<span data-ttu-id="51bc3-233">セグメントを定義した後、「情報バリアポリシーを定義する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-233">After you have defined your segments, proceed to define information barrier policies.</span></span>

## <a name="part-2-define-information-barrier-policies"></a><span data-ttu-id="51bc3-234">パート 2: 情報バリアポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="51bc3-234">Part 2: Define information barrier policies</span></span>

<span data-ttu-id="51bc3-235">定義するユーザーセグメントと情報バリアポリシーの一覧を使用して、シナリオを選択し、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-235">With your list of user segments and the information barrier policies you want to define, select a scenario, and then follow the steps.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="51bc3-236">**ポリシーを定義するときは、1つのセグメントに複数のポリシーを割り当てない**ようにしてください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-236">**Make sure that as you define policies, you do not assign more than one policy to a segment**.</span></span> <span data-ttu-id="51bc3-237">たとえば、 *sales*というセグメントに対して1つのポリシーを定義する場合は、 *sales*に対して追加のポリシーを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-237">For example, if you define one policy for a segment called *Sales*, do not define an additional policy for *Sales*.</span></span> 

<span data-ttu-id="51bc3-238">特定のセグメント間の通信を禁止する必要があるか、または特定のセグメントへの通信を制限する必要があるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-238">Determine whether you need to prevent communications between certain segments, or limit communications to certain segments.</span></span> <span data-ttu-id="51bc3-239">次のシナリオのいずれかを選択してポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-239">Choose between the scenarios below to define your policies.</span></span>

- [<span data-ttu-id="51bc3-240">シナリオ 1: セグメント間の通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="51bc3-240">Scenario 1: Block communications between segments</span></span>](#scenario-1-block-communications-between-segments)
- [<span data-ttu-id="51bc3-241">シナリオ 2: セグメントが他の1つのセグメントとのみ通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="51bc3-241">Scenario 2: Allow a segment to communicate only with one other segment</span></span>](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!NOTE]
> <span data-ttu-id="51bc3-242">情報バリアポリシーを定義するときには、それらのポリシーを適用する準備ができるまで、非アクティブ状態に設定してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-242">As you define information barrier policies, make sure to set those policies to inactive status until you are ready to apply them.</span></span> <span data-ttu-id="51bc3-243">ポリシーを定義 (または編集) すると、それらのポリシーがアクティブな状態に設定された後、ユーザーに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-243">Defining (or editing) policies does not affect users until those policies are set to active status and then applied.</span></span>

<span data-ttu-id="51bc3-244">(この記事の「 [Example: Contoso の情報バリアポリシー](#contosos-information-barrier-policies) 」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-244">(See [Example: Contoso's information barrier policies](#contosos-information-barrier-policies) in this article.)</span></span>

### <a name="scenario-1-block-communications-between-segments"></a><span data-ttu-id="51bc3-245">シナリオ 1: セグメント間の通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="51bc3-245">Scenario 1: Block communications between segments</span></span>

<span data-ttu-id="51bc3-246">セグメントが相互に通信するのをブロックする場合は、2つのポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-246">When you want to block segments from communicating with each other, you define two policies: one for each direction.</span></span> <span data-ttu-id="51bc3-247">各ポリシーは、一一の通信のみをブロックします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-247">Each policy blocks communication one way only.</span></span>

<span data-ttu-id="51bc3-248">たとえば、セグメント A とセグメント B 間の通信をブロックするとします。この場合は、セグメント A からセグメント B と通信することを妨げる1つのポリシーを定義してから、セグメント B とセグメント A との通信を禁止する2番目のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-248">For example, suppose you want to block communications between Segment A and Segment B. In this case, you define one policy preventing Segment A from communicating with Segment B, and then define a second policy to prevent Segment B from communicating with Segment A.</span></span>

1. <span data-ttu-id="51bc3-249">最初のブロックポリシーを定義するには、 **InformationBarrierPolicy**コマンドレットを**SegmentsBlocked**パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-249">To define your first blocking policy, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter.</span></span> 

    <span data-ttu-id="51bc3-250">文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-250">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span></span>

    <span data-ttu-id="51bc3-251">例: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="51bc3-251">Example: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span></span>

    <span data-ttu-id="51bc3-252">この例では、 *sales*というセグメントの*sales Research*というポリシーを定義しました。</span><span class="sxs-lookup"><span data-stu-id="51bc3-252">In this example, we defined a policy called *Sales-Research* for a segment called *Sales*.</span></span> <span data-ttu-id="51bc3-253">このポリシーを有効にして適用すると、 *Sales*のユーザーは*Research*というセグメントにあるユーザーと通信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-253">When active and applied, this policy prevents people in *Sales* from communicating with people in a segment called *Research*.</span></span>

2. <span data-ttu-id="51bc3-254">2番目のブロックセグメントを定義するには、 **InformationBarrierPolicy**コマンドレットを**SegmentsBlocked**パラメーターと共に再度使用します。この場合は、セグメントを反転された状態にします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-254">To define your second blocking segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter again, this time with the segments reversed.</span></span>

    <span data-ttu-id="51bc3-255">例: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="51bc3-255">Example: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span></span>

    <span data-ttu-id="51bc3-256">この例では、リサーチという名前のポリシーを定義して、研究*部門*との通信によるコミュニケーションを防止しています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-256">In this example, we defined a policy called *Research-Sales* to prevent Research from communicating with Sales.</span></span>
 
2. <span data-ttu-id="51bc3-257">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-257">Proceed to one of the following:</span></span>

   - <span data-ttu-id="51bc3-258">(必要な場合)[セグメントが1つの他のセグメントとのみ通信できるようにするポリシーを定義する](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span><span class="sxs-lookup"><span data-stu-id="51bc3-258">(If needed) [Define a policy to allow a segment to communicate only with one other segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span></span> 
   - <span data-ttu-id="51bc3-259">(すべてのポリシーが定義された後)[情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="51bc3-259">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a><span data-ttu-id="51bc3-260">シナリオ 2: セグメントが他の1つのセグメントとのみ通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="51bc3-260">Scenario 2: Allow a segment to communicate only with one other segment</span></span>

1. <span data-ttu-id="51bc3-261">1つのセグメントが他の1つのセグメントとのみ通信できるようにするには、 **InformationBarrierPolicy**コマンドレットを**SegmentsAllowed**パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-261">To allow one segment to communicate with only one other segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsAllowed** parameter.</span></span> 

    <span data-ttu-id="51bc3-262">文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-262">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span></span>

    <span data-ttu-id="51bc3-263">例: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="51bc3-263">Example: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span></span>

    <span data-ttu-id="51bc3-264">この例では、*製造*と呼ばれるセグメントに対して、*工場*という名前のポリシーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-264">In this example, we defined a policy called *Manufacturing-HR* for a segment called *Manufacturing*.</span></span> <span data-ttu-id="51bc3-265">このポリシーを有効にして適用すると、*製造*者は*HR*というセグメントにあるユーザーとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-265">When active and applied, this policy allows people in *Manufacturing* to communicate only with people in a segment called *HR*.</span></span> <span data-ttu-id="51bc3-266">(この場合、製造は人事の一部ではないユーザーと通信できません)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-266">(In this case, Manufacturing cannot communicate with users who are not part of HR.)</span></span>

    <span data-ttu-id="51bc3-267">**必要に応じて、次の2つの例に示すように、このコマンドレットで複数のセグメントを指定できます。**</span><span class="sxs-lookup"><span data-stu-id="51bc3-267">**If needed, you can specify multiple segments with this cmdlet, as shown in the following two examples.**</span></span>

    <span data-ttu-id="51bc3-268">文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-268">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span></span>

    <span data-ttu-id="51bc3-269">**例 1: 複数のセグメントが他の1つのセグメントのみと通信できるようにするポリシーを定義する**</span><span class="sxs-lookup"><span data-stu-id="51bc3-269">**Example 1: Define a policy to allow multiple segments to communicate with only one other segment**</span></span>

    `New-InformationBarrierPolicy -Name "ResearchManufacturing-HR" -AssignedSegment "Research, Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    <span data-ttu-id="51bc3-270">この例では、*研究*および*製造*セグメントが*HR*とのみ通信できるようにするポリシーを定義しました。</span><span class="sxs-lookup"><span data-stu-id="51bc3-270">In this example, we defined a policy that allows the *Research* and *Manufacturing* segments to communicate only with *HR*.</span></span>

    <span data-ttu-id="51bc3-271">**例 2: 複数のセグメントが特定の他のセグメントのみと通信できるようにするポリシーを定義する**</span><span class="sxs-lookup"><span data-stu-id="51bc3-271">**Example 2: Define a policy to allow multiple segments to communicate with only certain other segments**</span></span>    

    `New-InformationBarrierPolicy -Name "SalesMarketing-HRManufacturing" -AssignedSegment "Sales, Marketing" -SegmentsAllowed "HR, Manufacturing" -State Inactive`

    <span data-ttu-id="51bc3-272">この例では、*営業*および*マーケティング*セグメントが*人事*および*製造*のみと通信できるようにするポリシーを定義しました。</span><span class="sxs-lookup"><span data-stu-id="51bc3-272">In this example, we defined a policy that allows the *Sales* and *Marketing* segments to communicate with only *HR* and *Manufacturing*.</span></span>

    <span data-ttu-id="51bc3-273">特定のセグメントのみが特定の特定のセグメントと通信できるようにするために定義するポリシーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-273">Repeat this step for each policy you want to define to allow specific segments to communicate with only certain other specific segments.</span></span>

2. <span data-ttu-id="51bc3-274">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-274">Proceed to one of the following:</span></span>

   - <span data-ttu-id="51bc3-275">(必要な場合)[セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments)</span><span class="sxs-lookup"><span data-stu-id="51bc3-275">(If needed) [Define a policy to block communications between segments](#scenario-1-block-communications-between-segments)</span></span> 
   - <span data-ttu-id="51bc3-276">(すべてのポリシーが定義された後)[情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="51bc3-276">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

## <a name="part-3-apply-information-barrier-policies"></a><span data-ttu-id="51bc3-277">パート 3: 情報バリアポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="51bc3-277">Part 3: Apply information barrier policies</span></span>

<span data-ttu-id="51bc3-278">情報バリアポリシーは、アクティブな状態に設定してからポリシーを適用するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-278">Information barrier policies are not in effect until you set them to active status, and then apply the policies.</span></span>

1. <span data-ttu-id="51bc3-279">**InformationBarrierPolicy**コマンドレットを使用して、定義されているポリシーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-279">Use the **Get-InformationBarrierPolicy** cmdlet to see a list of policies that have been defined.</span></span> <span data-ttu-id="51bc3-280">各ポリシーの状態と id (GUID) をメモします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-280">Note the status and identity (GUID) of each policy.</span></span>

    <span data-ttu-id="51bc3-281">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="51bc3-281">Syntax: `Get-InformationBarrierPolicy`</span></span>

2. <span data-ttu-id="51bc3-282">ポリシーをアクティブな状態に設定するには、 **Identity**パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、 **State**パラメーターを**active**に設定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-282">To set a policy to active status, use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and the **State** parameter set to **Active**.</span></span> 

    <span data-ttu-id="51bc3-283">文`Set-InformationBarrierPolicy -Identity GUID -State Active`</span><span class="sxs-lookup"><span data-stu-id="51bc3-283">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Active`</span></span>

    <span data-ttu-id="51bc3-284">例: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span><span class="sxs-lookup"><span data-stu-id="51bc3-284">Example: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span></span>
    
    <span data-ttu-id="51bc3-285">この例では、GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*の情報バリアポリシーをアクティブな状態に設定しています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-285">In this example, we set an information barrier policy that has the GUID *43c37853-ea10-4b90-a23d-ab8c93772471* to active status.</span></span>

    <span data-ttu-id="51bc3-286">各ポリシーに該当する場合は、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-286">Repeat this step as appropriate for each policy.</span></span>

3. <span data-ttu-id="51bc3-287">情報バリアポリシーのアクティブ状態の設定が終了したら、Office 365 セキュリティ & コンプライアンスセンターで**InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-287">When you have finished setting your information barrier policies to active status, use the **Start-InformationBarrierPoliciesApplication** cmdlet in the Office 365 Security & Compliance Center.</span></span>

    <span data-ttu-id="51bc3-288">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="51bc3-288">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="51bc3-289">約30時間後に、組織のポリシーがユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-289">After approximately a half hour, policies are applied, user by user, for your organization.</span></span> <span data-ttu-id="51bc3-290">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-290">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="51bc3-291">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-291">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

## <a name="verify-status-of-user-accounts-segments-policies-or-policy-application"></a><span data-ttu-id="51bc3-292">ユーザーアカウント、セグメント、ポリシー、またはポリシーアプリケーションの状態を確認する</span><span class="sxs-lookup"><span data-stu-id="51bc3-292">Verify status of user accounts, segments, policies, or policy application</span></span>

<span data-ttu-id="51bc3-293">PowerShell を使用すると、次の表に示すように、ユーザーアカウント、セグメント、ポリシー、およびポリシーアプリケーションの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-293">Using PowerShell, you can verify status of user accounts, segments, policies, and policy application, as listed in the following table.</span></span>

|<span data-ttu-id="51bc3-294">これを確認するには</span><span class="sxs-lookup"><span data-stu-id="51bc3-294">To verify this</span></span>  |<span data-ttu-id="51bc3-295">説明</span><span class="sxs-lookup"><span data-stu-id="51bc3-295">Do this</span></span>  |
|---------|---------|
|<span data-ttu-id="51bc3-296">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="51bc3-296">User accounts</span></span>     |<span data-ttu-id="51bc3-297">Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-297">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <p><span data-ttu-id="51bc3-298">文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="51bc3-298">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> <p><span data-ttu-id="51bc3-299">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-299">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p><span data-ttu-id="51bc3-300">例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="51bc3-300">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> <p><span data-ttu-id="51bc3-301">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-301">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> <p><span data-ttu-id="51bc3-302">(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます。)</span><span class="sxs-lookup"><span data-stu-id="51bc3-302">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> <p><span data-ttu-id="51bc3-303">このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-303">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>|
|<span data-ttu-id="51bc3-304">多角形</span><span class="sxs-lookup"><span data-stu-id="51bc3-304">Segments</span></span>     |<span data-ttu-id="51bc3-305">コマンドレット\*\*\*\* を使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-305">Use the **Get-OrganizationSegment** cmdlet.</span></span><p><span data-ttu-id="51bc3-306">文`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="51bc3-306">Syntax: `Get-OrganizationSegment`</span></span> <p><span data-ttu-id="51bc3-307">これにより、組織に定義されているすべてのセグメントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-307">This will display a list of all segments defined for your organization.</span></span>         |
|<span data-ttu-id="51bc3-308">情報バリアポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-308">Information barrier policies</span></span>     |<span data-ttu-id="51bc3-309">**InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-309">Use the **Get-InformationBarrierPolicy** cmdlet.</span></span> <p> <span data-ttu-id="51bc3-310">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="51bc3-310">Syntax: `Get-InformationBarrierPolicy`</span></span> <p><span data-ttu-id="51bc3-311">これにより、定義された情報バリアポリシーの一覧とその状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-311">This will display a list of information barrier policies that were defined, and their status.</span></span>       |
|<span data-ttu-id="51bc3-312">最新情報バリアポリシーアプリケーション</span><span class="sxs-lookup"><span data-stu-id="51bc3-312">The most recent information barrier policy application</span></span>     | <span data-ttu-id="51bc3-313">**InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-313">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span> <p><span data-ttu-id="51bc3-314">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="51bc3-314">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span><p>    <span data-ttu-id="51bc3-315">これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-315">This will display information about whether policy application completed, failed, or is in progress.</span></span>       |
|<span data-ttu-id="51bc3-316">すべての情報バリアポリシーアプリケーション</span><span class="sxs-lookup"><span data-stu-id="51bc3-316">All information barrier policy applications</span></span>|<span data-ttu-id="51bc3-317">使え`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="51bc3-317">Use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span><p><span data-ttu-id="51bc3-318">これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-318">This will display information about whether policy application completed, failed, or is in progress.</span></span>|

## <a name="stop-a-policy-application"></a><span data-ttu-id="51bc3-319">ポリシーアプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="51bc3-319">Stop a policy application</span></span>

<span data-ttu-id="51bc3-320">情報バリアポリシーの適用を開始した後で、これらのポリシーの適用を停止するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-320">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="51bc3-321">プロセスが開始されるまで約30-35 分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-321">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="51bc3-322">最新の情報バリアポリシーアプリケーションの状態を表示するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-322">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="51bc3-323">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="51bc3-323">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="51bc3-324">アプリケーションの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-324">Note the application's GUID.</span></span>

2. <span data-ttu-id="51bc3-325">Identity パラメーターを指定して**InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-325">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="51bc3-326">文`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="51bc3-326">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="51bc3-327">例: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="51bc3-327">Example: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

## <a name="edit-a-segment-or-a-policy"></a><span data-ttu-id="51bc3-328">セグメントまたはポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="51bc3-328">Edit a segment or a policy</span></span>

### <a name="edit-a-segment"></a><span data-ttu-id="51bc3-329">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="51bc3-329">Edit a segment</span></span>

1. <span data-ttu-id="51bc3-330">既存のすべてのセグメントを表示するには、コマンドレットの**取得**を使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-330">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="51bc3-331">文`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="51bc3-331">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="51bc3-332">セグメントの種類、UserGroupFilter 値、作成者または最終更新日時、GUID など、セグメントと詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-332">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="51bc3-333">後で参照するために、セグメントのリストを印刷または保存します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-333">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="51bc3-334">たとえば、セグメントを編集する場合は、その名前を知っているか、値を識別する必要があります (これは Identity パラメーターと共に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-334">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="51bc3-335">セグメントを編集するには、 **Identity**パラメーターと関連する詳細情報を使用して、**グループ**化コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-335">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="51bc3-336">文`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-336">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="51bc3-337">例: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-337">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="51bc3-338">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントに対して、部署名を "hrdept" に更新しました。</span><span class="sxs-lookup"><span data-stu-id="51bc3-338">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="51bc3-339">組織のセグメントの編集が終了したら、「情報バリアポリシーの[定義](#part-2-define-information-barrier-policies)または[編集](#edit-a-policy)」に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-339">When you have finished editing segments for your organization, you can proceed to [define](#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

### <a name="edit-a-policy"></a><span data-ttu-id="51bc3-340">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="51bc3-340">Edit a policy</span></span>

1. <span data-ttu-id="51bc3-341">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-341">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="51bc3-342">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="51bc3-342">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="51bc3-343">結果の一覧で、変更するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-343">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="51bc3-344">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-344">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="51bc3-345">**InformationBarrierPolicy**コマンドレットを**Identity**パラメーターと共に使用して、必要な変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-345">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="51bc3-346">構文 (セグメントが他のセグメントと通信することをブロックする):</span><span class="sxs-lookup"><span data-stu-id="51bc3-346">Syntax (blocking segments from communicating with other segments):</span></span> 

    `Set-InformationBarrierPolicy -Identity GUID -SegmentsBlocked "segmentname, segmentname"` 

    <span data-ttu-id="51bc3-347">構文 (セグメントが特定の他のセグメントとのみ通信できるようにする):</span><span class="sxs-lookup"><span data-stu-id="51bc3-347">Syntax (enabling segments to communicate only with certain other segments):</span></span>
    
    ``Set-InformationBarrierPolicy -Identity GUID -SegmentsAllowed "segmentname, segmentname"``

    <span data-ttu-id="51bc3-348">例: 研究をブロックするように定義されたポリシーが、営業およびマーケティングとの通信をブロックしているとします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-348">Example: Suppose a policy was defined to block Research from communicating with Sales and Marketing.</span></span> <span data-ttu-id="51bc3-349">このポリシーは、このコマンドレットを使用して定義されています。`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-349">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span></span>
    
    <span data-ttu-id="51bc3-350">研究者が人事内の人とのみ通信できるように変更したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-350">Suppose we want to change it so that people in Research can only communicate with people in HR.</span></span> <span data-ttu-id="51bc3-351">この変更を行うには、次のコマンドレットを使用します。`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="51bc3-351">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

3. <span data-ttu-id="51bc3-352">ポリシーの編集が終了したら、変更内容を適用してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-352">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="51bc3-353">([情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-353">(See [Apply information barrier policies](#part-3-apply-information-barrier-policies).)</span></span>

### <a name="remove-a-policy"></a><span data-ttu-id="51bc3-354">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="51bc3-354">Remove a policy</span></span>

1. <span data-ttu-id="51bc3-355">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-355">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="51bc3-356">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="51bc3-356">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="51bc3-357">結果の一覧で、削除するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-357">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="51bc3-358">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-358">Note the policy's GUID and name.</span></span> <span data-ttu-id="51bc3-359">ポリシーが非アクティブの状態に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-359">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="51bc3-360">Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-360">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="51bc3-361">文`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="51bc3-361">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="51bc3-362">例: GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*のポリシーを削除するとします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-362">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="51bc3-363">これを行うには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-363">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="51bc3-364">メッセージが表示されたら、変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-364">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="51bc3-365">削除するポリシーごとに、手順1-2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-365">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="51bc3-366">ポリシーの削除が終了したら、変更内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-366">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="51bc3-367">これを行うには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-367">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="51bc3-368">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="51bc3-368">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="51bc3-369">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-369">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="51bc3-370">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-370">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

### <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="51bc3-371">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="51bc3-371">Set a policy to inactive status</span></span>

1. <span data-ttu-id="51bc3-372">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-372">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="51bc3-373">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="51bc3-373">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="51bc3-374">結果の一覧で、変更する (または削除する) ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-374">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="51bc3-375">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="51bc3-375">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="51bc3-376">ポリシーの状態を非アクティブに設定するには、Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、State パラメーターを inactive に設定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-376">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="51bc3-377">文`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="51bc3-377">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="51bc3-378">この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247*を非アクティブな状態に設定する情報バリアポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-378">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="51bc3-379">変更を適用するには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-379">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="51bc3-380">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="51bc3-380">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="51bc3-381">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-381">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="51bc3-382">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-382">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="51bc3-383">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-383">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="51bc3-384">この時点で、1つまたは複数の情報バリアポリシーが非アクティブ状態に設定されます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-384">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="51bc3-385">ここから、次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-385">From here, you can do any of the following:</span></span>
- <span data-ttu-id="51bc3-386">そのままにしておきます (非アクティブ状態に設定されたポリシーはユーザーに影響を与えません)。</span><span class="sxs-lookup"><span data-stu-id="51bc3-386">Leave it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="51bc3-387">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="51bc3-387">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="51bc3-388">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="51bc3-388">Remove a policy</span></span>](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a><span data-ttu-id="51bc3-389">例: Contoso 社の部署、セグメント、ポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-389">Example: Contoso's departments, segments, and policies</span></span>

<span data-ttu-id="51bc3-390">組織がセグメントとポリシーを定義する方法を確認するには、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-390">To see how an organization might approach defining segments and policies, consider the following example.</span></span>

### <a name="contosos-departments-and-plan"></a><span data-ttu-id="51bc3-391">Contoso 社の部門と計画</span><span class="sxs-lookup"><span data-stu-id="51bc3-391">Contoso's departments and plan</span></span>

<span data-ttu-id="51bc3-392">Contoso には、人事、営業、マーケティング、研究、製造の5つの部門があります。</span><span class="sxs-lookup"><span data-stu-id="51bc3-392">Contoso has five departments: HR, Sales, Marketing, Research, and Manufacturing.</span></span> <span data-ttu-id="51bc3-393">業界の規制に準拠するために、一部の部署のユーザーは、次の表に示すように、他の部署とは通信することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-393">In order to remain compliant with industry regulations, people in some departments are not supposed to communicate with other departments, as listed in the following table:</span></span>

|<span data-ttu-id="51bc3-394">化</span><span class="sxs-lookup"><span data-stu-id="51bc3-394">Segment</span></span>  |<span data-ttu-id="51bc3-395">会話可能</span><span class="sxs-lookup"><span data-stu-id="51bc3-395">Can talk to</span></span>  |<span data-ttu-id="51bc3-396">会話できません</span><span class="sxs-lookup"><span data-stu-id="51bc3-396">Cannot talk to</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="51bc3-397">HR</span><span class="sxs-lookup"><span data-stu-id="51bc3-397">HR</span></span>     |<span data-ttu-id="51bc3-398">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="51bc3-398">Everyone</span></span>         |<span data-ttu-id="51bc3-399">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="51bc3-399">(no restrictions)</span></span>         |
|<span data-ttu-id="51bc3-400">営業</span><span class="sxs-lookup"><span data-stu-id="51bc3-400">Sales</span></span>     |<span data-ttu-id="51bc3-401">人事、マーケティング、製造</span><span class="sxs-lookup"><span data-stu-id="51bc3-401">HR, Marketing, Manufacturing</span></span>         |<span data-ttu-id="51bc3-402">リサーチ</span><span class="sxs-lookup"><span data-stu-id="51bc3-402">Research</span></span>         |
|<span data-ttu-id="51bc3-403">マーケティング</span><span class="sxs-lookup"><span data-stu-id="51bc3-403">Marketing</span></span>     |<span data-ttu-id="51bc3-404">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="51bc3-404">Everyone</span></span>         |<span data-ttu-id="51bc3-405">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="51bc3-405">(no restrictions)</span></span>         |
|<span data-ttu-id="51bc3-406">リサーチ</span><span class="sxs-lookup"><span data-stu-id="51bc3-406">Research</span></span>     |<span data-ttu-id="51bc3-407">人事、マーケティング、製造</span><span class="sxs-lookup"><span data-stu-id="51bc3-407">HR, Marketing, Manufacturing</span></span>        |<span data-ttu-id="51bc3-408">営業</span><span class="sxs-lookup"><span data-stu-id="51bc3-408">Sales</span></span>     |
|<span data-ttu-id="51bc3-409">製造</span><span class="sxs-lookup"><span data-stu-id="51bc3-409">Manufacturing</span></span> |<span data-ttu-id="51bc3-410">人事、マーケティング</span><span class="sxs-lookup"><span data-stu-id="51bc3-410">HR, Marketing</span></span> |<span data-ttu-id="51bc3-411">人事またはマーケティング以外のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="51bc3-411">Anyone other than HR or Marketing</span></span> |

<span data-ttu-id="51bc3-412">この点を考慮して、Contoso 社の計画には3つの情報バリアポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-412">With this in mind, Contoso's plan includes three information barrier policies:</span></span>

1. <span data-ttu-id="51bc3-413">セールスが研究との通信を禁止するように設計されたポリシー (および研究からのセールスとの通信を禁止する別のポリシー)</span><span class="sxs-lookup"><span data-stu-id="51bc3-413">A policy designed to prevent Sales from communicating with Research (and another policy to prevent Research from communicating with Sales)</span></span>
2. <span data-ttu-id="51bc3-414">製造に HR および Marketing のみと通信できるように設計されたポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-414">A policy designed to allow Manufacturing to communicate with HR and Marketing only</span></span> 

<span data-ttu-id="51bc3-415">人事またはマーケティングのポリシーを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-415">It's not necessary to define policies for HR or Marketing.</span></span>

### <a name="contosos-defined-segments"></a><span data-ttu-id="51bc3-416">Contoso 社が定義したセグメント</span><span class="sxs-lookup"><span data-stu-id="51bc3-416">Contoso's defined segments</span></span>

<span data-ttu-id="51bc3-417">Contoso 社は、次のように、Azure Active Directory の Department 属性を使用してセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-417">Contoso will use the Department attribute in Azure Active Directory to define segments, as follows:</span></span>

|<span data-ttu-id="51bc3-418">部署</span><span class="sxs-lookup"><span data-stu-id="51bc3-418">Department</span></span>  |<span data-ttu-id="51bc3-419">セグメント定義</span><span class="sxs-lookup"><span data-stu-id="51bc3-419">Segment Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="51bc3-420">HR</span><span class="sxs-lookup"><span data-stu-id="51bc3-420">HR</span></span>     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|<span data-ttu-id="51bc3-421">営業</span><span class="sxs-lookup"><span data-stu-id="51bc3-421">Sales</span></span>     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|<span data-ttu-id="51bc3-422">マーケティング</span><span class="sxs-lookup"><span data-stu-id="51bc3-422">Marketing</span></span>     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|<span data-ttu-id="51bc3-423">リサーチ</span><span class="sxs-lookup"><span data-stu-id="51bc3-423">Research</span></span>     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|<span data-ttu-id="51bc3-424">製造</span><span class="sxs-lookup"><span data-stu-id="51bc3-424">Manufacturing</span></span>     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

<span data-ttu-id="51bc3-425">セグメントが定義されていると、Contoso はポリシーの定義に進みます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-425">With the segments defined, Contoso proceeds to define policies.</span></span> 

### <a name="contosos-information-barrier-policies"></a><span data-ttu-id="51bc3-426">Contoso 社の情報バリアポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-426">Contoso's information barrier policies</span></span>

<span data-ttu-id="51bc3-427">Contoso 社では、次の表に示す3つのポリシーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="51bc3-427">Contoso defines three polices, as described in the following table:</span></span>

|<span data-ttu-id="51bc3-428">ポリシー</span><span class="sxs-lookup"><span data-stu-id="51bc3-428">Policy</span></span>  |<span data-ttu-id="51bc3-429">ポリシー定義</span><span class="sxs-lookup"><span data-stu-id="51bc3-429">Policy Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="51bc3-430">ポリシー 1: Sales がリサーチと通信できないようにする</span><span class="sxs-lookup"><span data-stu-id="51bc3-430">Policy 1: Prevent Sales from communicating with Research</span></span>     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> <span data-ttu-id="51bc3-431">この例では、情報バリアポリシーを*Sales Research*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-431">In this example, the information barrier policy is called *Sales-Research*.</span></span> <span data-ttu-id="51bc3-432">このポリシーがアクティブで適用されている場合は、営業部門のユーザーが Research セグメントのユーザーと通信できないようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-432">When this policy is active and applied, it will help prevent users who are in the Sales segment from communicating with users in the Research segment.</span></span> <span data-ttu-id="51bc3-433">これは一ウェイのポリシーです。研究からセールスへのコミュニケーションが妨げられることはありません。</span><span class="sxs-lookup"><span data-stu-id="51bc3-433">This is a one-way policy; it won't prevent Research from communicating with Sales.</span></span> <span data-ttu-id="51bc3-434">そのためには、ポリシー2が必要です。</span><span class="sxs-lookup"><span data-stu-id="51bc3-434">For that, Policy 2 is needed.</span></span>      |
|<span data-ttu-id="51bc3-435">ポリシー 2: リサーチがセールスと通信できないようにする</span><span class="sxs-lookup"><span data-stu-id="51bc3-435">Policy 2: Prevent Research from communicating with Sales</span></span>     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> <span data-ttu-id="51bc3-436">この例では、情報バリアポリシーを*Research Sales*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-436">In this example, the information barrier policy is called *Research-Sales*.</span></span> <span data-ttu-id="51bc3-437">このポリシーがアクティブで適用されている場合は、リサーチセグメントにあるユーザーが営業セグメント内のユーザーと通信できないようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-437">When this policy is active and applied, it will help prevent users who are in the Research segment from communicating with users in the Sales segment.</span></span>       |
|<span data-ttu-id="51bc3-438">ポリシー 3: 製造に HR と Marketing のみが通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="51bc3-438">Policy 3: Allow Manufacturing to communicate with HR and Marketing only</span></span>     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR, Marketing" -State Inactive` <p><span data-ttu-id="51bc3-439">この例では、情報バリアポリシーを*製造-HRMarketing*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-439">In this case, the information barrier policy is called *Manufacturing-HRMarketing*.</span></span> <span data-ttu-id="51bc3-440">このポリシーがアクティブで適用されている場合、製造は人事およびマーケティングとのみ通信できます。</span><span class="sxs-lookup"><span data-stu-id="51bc3-440">When this policy is active and applied, Manufacturing can communicate only with HR and Marketing.</span></span> <span data-ttu-id="51bc3-441">人事およびマーケティングは、他のセグメントとの通信に制限されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="51bc3-441">Note that HR and Marketing are not restricted from communicating with other segments.</span></span> |

<span data-ttu-id="51bc3-442">セグメントとポリシーが定義されているので、Contoso は**InformationBarrierPoliciesApplication**コマンドレットを実行してポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-442">With segments and policies defined, Contoso applies the policies by running the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span> 

<span data-ttu-id="51bc3-443">この処理が完了すると、Contoso は法律および業界の要件に準拠します。</span><span class="sxs-lookup"><span data-stu-id="51bc3-443">When that finishes, Contoso is compliant with legal and industry requirements.</span></span>

## <a name="related-articles"></a><span data-ttu-id="51bc3-444">関連記事</span><span class="sxs-lookup"><span data-stu-id="51bc3-444">Related articles</span></span>

[<span data-ttu-id="51bc3-445">情報障壁の概要を理解する</span><span class="sxs-lookup"><span data-stu-id="51bc3-445">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="51bc3-446">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="51bc3-446">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="51bc3-447">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="51bc3-447">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="51bc3-448">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="51bc3-448">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
