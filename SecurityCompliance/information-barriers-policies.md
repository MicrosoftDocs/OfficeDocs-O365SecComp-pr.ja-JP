---
title: 情報バリアポリシーの定義
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Microsoft Teams の情報障壁に関するポリシーを定義する方法について説明します。
ms.openlocfilehash: 8d575d0cde4bfec7109cc302f68beaf1040cd894
ms.sourcegitcommit: eeb51470d8996e93fac28d7f12c6117e2aeb0cf0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2019
ms.locfileid: "34935949"
---
# <a name="define-policies-for-information-barriers-preview"></a><span data-ttu-id="9b3a6-103">情報バリアのポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-103">Define policies for information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="9b3a6-104">概要</span><span class="sxs-lookup"><span data-stu-id="9b3a6-104">Overview</span></span>

<span data-ttu-id="9b3a6-105">情報の障壁を使用すると、特定のユーザーセグメントが相互に通信するのを防ぐように設計されたポリシーを定義したり、特定のセグメントのみが特定のセグメントと通信できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-105">With information barriers, you can define policies that are designed to prevent certain segments of users from communicating with each other, or allow specific segments to communicate only with certain other segments.</span></span> <span data-ttu-id="9b3a6-106">情報バリアポリシーは、組織が関連する業界標準および規制に準拠し、潜在的な競合を回避するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-106">Information barrier policies can help your organization maintain compliance with relevant industry standards and regulations, and avoid potential conflicts of interest.</span></span> <span data-ttu-id="9b3a6-107">詳細については、「[情報の障壁 (プレビュー)](information-barriers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-107">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span> 

<span data-ttu-id="9b3a6-108">この記事では、情報バリアポリシーを計画、定義、実装、および管理する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-108">This article describes how to plan, define, implement, and manage information barrier policies.</span></span> <span data-ttu-id="9b3a6-109">いくつかの手順が関係しており、作業フローはいくつかの部分に分かれています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-109">Several steps are involved, and the work flow is divided into several parts.</span></span> <span data-ttu-id="9b3a6-110">情報バリアポリシーの定義 (または編集) を開始する前に、必ず[前提条件](#prerequisites)とプロセス全体に目を通してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-110">Make sure to read through the [prerequisites](#prerequisites) and the entire process before you begin defining (or editing) information barrier policies.</span></span>

> [!TIP]
> <span data-ttu-id="9b3a6-111">この記事には、情報バリアポリシーを計画して定義するのに役立つ、[シナリオの例](#example-contosos-departments-segments-and-policies)とダウンロード可能な[Excel ブック](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-111">This article includes an [example scenario](#example-contosos-departments-segments-and-policies) and a [downloadable Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) to help you plan and define your information barrier policies.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="9b3a6-112">情報バリアポリシーの概念</span><span class="sxs-lookup"><span data-stu-id="9b3a6-112">Concepts of information barrier policies</span></span>

<span data-ttu-id="9b3a6-113">情報バリアポリシーの基礎概念を理解しておくと役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-113">It's helpful to know the underlying concepts of information barrier policies:</span></span>

- <span data-ttu-id="9b3a6-114">**ユーザーアカウントの属性**は、Azure Active Directory (または Exchange Online) で定義されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-114">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="9b3a6-115">これらの属性には、部署、役職、場所、チーム名、その他のジョブプロファイルの詳細を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-115">These attributes can include department, job title, location, team name, and other job profile details.</span></span> 

- <span data-ttu-id="9b3a6-116">**セグメント**とは、Office 365 セキュリティ & コンプライアンスセンターで、選択した**ユーザーアカウント属性**を使用して定義された一連のユーザーのことです。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-116">**Segments** are sets of users that are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**.</span></span> <span data-ttu-id="9b3a6-117">([サポートされている属性の一覧](information-barriers-attributes.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-117">(See the [list of supported attributes](information-barriers-attributes.md).)</span></span> 

- <span data-ttu-id="9b3a6-118">**情報バリアポリシー**では、通信制限または制限を決定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-118">**Information barrier policies** determine communication limits or restrictions.</span></span> <span data-ttu-id="9b3a6-119">情報バリアポリシーを定義するときは、次の2種類のポリシーから選択します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-119">When you define information barrier policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="9b3a6-120">あるセグメントが別のセグメントと通信できないようにする "ブロック" ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-120">"Block" policies that prevent one segment from communicating with another segment</span></span>
    - <span data-ttu-id="9b3a6-121">1つのセグメントのみが特定の他のセグメントと通信できるようにする "許可" ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-121">"Allow" policies that allow one segment to communicate with only certain other segments</span></span>

- <span data-ttu-id="9b3a6-122">**ポリシーアプリケーション**は、すべての情報バリアポリシーが定義された後に実行され、組織に適用する準備が整っています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-122">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="9b3a6-123">作業フローの概要</span><span class="sxs-lookup"><span data-stu-id="9b3a6-123">The work flow at a glance</span></span>

|<span data-ttu-id="9b3a6-124">フェーズ</span><span class="sxs-lookup"><span data-stu-id="9b3a6-124">Phase</span></span>    |<span data-ttu-id="9b3a6-125">関係するもの</span><span class="sxs-lookup"><span data-stu-id="9b3a6-125">What's involved</span></span>  |
|---------|---------|
|[<span data-ttu-id="9b3a6-126">前提条件が満たされていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-126">Make sure prerequisites are met</span></span>](#prerequisites)     |<span data-ttu-id="9b3a6-127">-[必要なライセンスとアクセス許可](information-barriers.md#required-licenses-and-permissions)を持っていることを確認する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-127">- Verify that you have the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions)</span></span><br/><span data-ttu-id="9b3a6-128">-組織のディレクトリに、組織の構造を反映したデータが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-128">- Make sure that your organization's directory includes data that reflects your organization's structure</span></span><br/><span data-ttu-id="9b3a6-129">-Microsoft Teams のスコープ付きディレクトリ検索を有効にする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-129">- Enable scoped directory search for Microsoft Teams</span></span><br/><span data-ttu-id="9b3a6-130">-監査ログが有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-130">- Make sure audit logging is turned on</span></span><br/><span data-ttu-id="9b3a6-131">-PowerShell の使用 (例は提供されています)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-131">- Use PowerShell (examples are provided)</span></span><br/><span data-ttu-id="9b3a6-132">-Microsoft Teams に対する管理者の同意を提供する (手順は含まれています)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-132">- Provide admin consent for Microsoft Teams (steps are included)</span></span>          |
|[<span data-ttu-id="9b3a6-133">パート 1: 組織内のすべてのユーザーのセグメント化</span><span class="sxs-lookup"><span data-stu-id="9b3a6-133">Part 1: Segment all the users in your organization</span></span>](#part-1-segment-users)     |<span data-ttu-id="9b3a6-134">-必要なポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-134">- Determine what policies are needed</span></span><br/><span data-ttu-id="9b3a6-135">-定義するセグメントの一覧を作成する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-135">- Make a list of segments to define</span></span><br/><span data-ttu-id="9b3a6-136">-使用する属性を識別する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-136">- Identify which attributes to use</span></span><br/><span data-ttu-id="9b3a6-137">-ポリシーフィルターの観点からセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-137">- Define segments in terms of policy filters</span></span>        |
|[<span data-ttu-id="9b3a6-138">パート 2: 情報バリアポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-138">Part 2: Define information barrier policies</span></span>](#part-2-define-information-barrier-policies)     |<span data-ttu-id="9b3a6-139">-ポリシーを定義します (まだ適用しない)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-139">- Define your policies (do not apply yet)</span></span><br/><span data-ttu-id="9b3a6-140">-2 つの種類 (ブロックまたは許可) から選択します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-140">- Choose from two kinds (block or allow)</span></span> |
|[<span data-ttu-id="9b3a6-141">パート 3: 情報バリアポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-141">Part 3: Apply information barrier policies</span></span>](#part-3-apply-information-barrier-policies)     |<span data-ttu-id="9b3a6-142">-ポリシーをアクティブな状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-142">- Set policies to active status</span></span><br/><span data-ttu-id="9b3a6-143">-ポリシーアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-143">- Run the policy application</span></span><br/><span data-ttu-id="9b3a6-144">-ポリシーの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-144">- View policy status</span></span>         |
|<span data-ttu-id="9b3a6-145">(必要な場合)[セグメントまたはポリシーを編集する](#edit-a-segment-or-a-policy)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-145">(As needed) [Edit a segment or a policy](#edit-a-segment-or-a-policy)</span></span>     |<span data-ttu-id="9b3a6-146">-セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-146">- Edit a segment</span></span><br/><span data-ttu-id="9b3a6-147">-ポリシーを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-147">- Edit or remove a policy</span></span><br/><span data-ttu-id="9b3a6-148">-ポリシーアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-148">- Run the policy application</span></span><br/><span data-ttu-id="9b3a6-149">-ポリシーの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-149">- View policy status</span></span>         |
|<span data-ttu-id="9b3a6-150">(必要な場合)[トラブルシューティング](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-150">(As needed) [Troubleshooting](information-barriers-troubleshooting.md)</span></span>|<span data-ttu-id="9b3a6-151">-期待どおりに動作しない場合に処理を実行する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-151">- Take action when things are not working as expected</span></span>|

## <a name="prerequisites"></a><span data-ttu-id="9b3a6-152">前提条件</span><span class="sxs-lookup"><span data-stu-id="9b3a6-152">Prerequisites</span></span>

<span data-ttu-id="9b3a6-153">[必要なライセンスとアクセス許可](information-barriers.md#required-licenses-and-permissions)に加えて、次の要件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-153">In addition to the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions), make sure that the following requirements are met:</span></span> 
     
- <span data-ttu-id="9b3a6-154">**ディレクトリデータ**。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-154">**Directory data**.</span></span> <span data-ttu-id="9b3a6-155">組織の構造がディレクトリデータに反映されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-155">Make sure that your organization's structure is reflected in directory data.</span></span> <span data-ttu-id="9b3a6-156">これを行うには、Azure Active Directory (または Exchange Online) に、グループメンバーシップ、部署名などのユーザーアカウント属性が正しく設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-156">To do this, make sure that user account attributes, such as group membership, department name, etc. are populated correctly in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="9b3a6-157">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-157">To learn more, see the following resources:</span></span>
  - [<span data-ttu-id="9b3a6-158">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-158">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)
  - [<span data-ttu-id="9b3a6-159">Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-159">Add or update a user's profile information using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [<span data-ttu-id="9b3a6-160">Office 365 PowerShell でユーザー アカウント プロパティを構成する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-160">Configure user account properties with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- <span data-ttu-id="9b3a6-161">**スコープ付きディレクトリ検索**。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-161">**Scoped directory search**.</span></span> <span data-ttu-id="9b3a6-162">組織の最初の情報バリアポリシーを定義する前に、 [Microsoft Teams でスコープ付きディレクトリ検索を有効](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-162">Before you define your organization's first information barrier policy, you must [enable scoped directory search in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search).</span></span> <span data-ttu-id="9b3a6-163">情報バリアポリシーを設定または定義する前に、スコープ付きディレクトリ検索を有効にした後、少なくとも24時間待機します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-163">Wait at least 24 hours after enabling scoped directory search before you set up or define information barrier policies.</span></span>

- <span data-ttu-id="9b3a6-164">**監査ログ**。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-164">**Audit logging**.</span></span> <span data-ttu-id="9b3a6-165">ポリシーアプリケーションの状態を参照するには、監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-165">In order to look up the status of a policy application, audit logging must be turned on.</span></span> <span data-ttu-id="9b3a6-166">セグメントまたはポリシーの定義を開始する前に、この手順を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-166">We recommend doing this before you begin to define segments or policies.</span></span> <span data-ttu-id="9b3a6-167">詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-167">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="9b3a6-168">**PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-168">**PowerShell**.</span></span> <span data-ttu-id="9b3a6-169">現時点で、情報バリアポリシーは、PowerShell コマンドレットを使用して Office 365 セキュリティ & コンプライアンスセンターで定義および管理されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-169">Currently, information barrier policies are defined and managed in the Office 365 Security & Compliance Center using PowerShell cmdlets.</span></span> <span data-ttu-id="9b3a6-170">この記事ではいくつかの例が示されていますが、PowerShell のコマンドレットとパラメーターについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-170">Although several examples are provided in this article, you'll need to be familiar with PowerShell cmdlets and parameters.</span></span> <span data-ttu-id="9b3a6-171">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-171">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="9b3a6-172">**Microsoft Teams の情報障壁に対する管理者の同意**。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-172">**Admin consent for information barriers in Microsoft Teams**.</span></span> <span data-ttu-id="9b3a6-173">ポリシーが適切に設定されている場合、情報バリアはチャットセッションからユーザーを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-173">When your policies are in place, information barriers can remove people from chat sessions they are not supposed to be in.</span></span> <span data-ttu-id="9b3a6-174">これにより、組織はポリシーと規制に準拠したままになります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-174">This helps ensure your organization remains compliant with policies and regulations.</span></span> <span data-ttu-id="9b3a6-175">次の手順を使用して、Microsoft Teams で情報バリアポリシーが期待どおりに動作するようにします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-175">Use the following procedure to enable information barrier policies to work as expected in Microsoft Teams.</span></span> 

   1. <span data-ttu-id="9b3a6-176">次の PowerShell コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-176">Run the following PowerShell cmdlets:</span></span>

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. <span data-ttu-id="9b3a6-177">メッセージが表示されたら、Office 365 の職場または学校アカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-177">When prompted, sign in using your work or school account for Office 365.</span></span>

   3. <span data-ttu-id="9b3a6-178">[**要求されたアクセス許可**] ダイアログボックスで情報を確認し、[**同意**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-178">In the **Permissions requested** dialog box, review the information, and then choose **Accept**.</span></span>

<span data-ttu-id="9b3a6-179">すべての前提条件が満たされたら、次のセクションに進みます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-179">When all the prerequisites are met, proceed to the next section.</span></span>

> [!TIP]
> <span data-ttu-id="9b3a6-180">プランの準備に役立てるため、この記事にはシナリオの例が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-180">To help you prepare your plan, an example scenario is included in this article.</span></span> <span data-ttu-id="9b3a6-181">[「Contoso 社の部門、セグメント、ポリシー」を参照してください](#example-contosos-departments-segments-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-181">[See Contoso's departments, segments, and policies](#example-contosos-departments-segments-and-policies).</span></span><p><span data-ttu-id="9b3a6-182">また、セグメントとポリシーを計画して定義したり、PowerShell コマンドレットを作成したりするのに役立つダウンロード可能な Excel ブックが用意されています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-182">In addition, a downloadable Excel workbook is available to help you plan and define your segments and policies (and create your PowerShell cmdlets).</span></span> <span data-ttu-id="9b3a6-183">[ブックを取得](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-183">[Get the workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).</span></span> 

## <a name="part-1-segment-users"></a><span data-ttu-id="9b3a6-184">パート 1: セグメントユーザー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-184">Part 1: Segment users</span></span>

<span data-ttu-id="9b3a6-185">このフェーズでは、必要な情報バリアポリシーを決定し、定義するセグメントの一覧を作成して、セグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-185">During this phase, you determine what information barrier policies are needed, make a list of segments to define, and then define your segments.</span></span>

### <a name="determine-what-policies-are-needed"></a><span data-ttu-id="9b3a6-186">必要なポリシーを決定する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-186">Determine what policies are needed</span></span>

<span data-ttu-id="9b3a6-187">法的および業界の規制を考慮しています。組織内で情報の障壁ポリシーを必要とするグループは誰ですか。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-187">Considering legal and industry regulations, who are the groups within your organization who will need information barrier policies?</span></span> <span data-ttu-id="9b3a6-188">リストを作成します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-188">Make a list.</span></span> <span data-ttu-id="9b3a6-189">他のグループとの通信を禁止する必要があるグループはありますか。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-189">Are there any groups who should be prevented from communicating with another group?</span></span> <span data-ttu-id="9b3a6-190">1つまたは2つの他のグループとのみ通信できるようにする必要があるグループはありますか。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-190">Are there any groups that should be allowed to communicate only with one or two other groups?</span></span> <span data-ttu-id="9b3a6-191">次の2つのグループのいずれかに属している必要があるポリシーについて考えます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-191">Think about the policies you need as belonging to one of two groups:</span></span>
- <span data-ttu-id="9b3a6-192">"Block" ポリシーは、あるグループが別のグループと通信できないようにします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-192">"Block" policies prevent one group from communicating with another group.</span></span>
- <span data-ttu-id="9b3a6-193">[許可] ポリシーにより、グループは特定の他の特定のグループのみと通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-193">"Allow" policies allow a group to communicate with only certain other, specific groups.</span></span>

<span data-ttu-id="9b3a6-194">最初にグループとポリシーの一覧を作成したら、次の手順を実行して、必要なセグメントを特定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-194">When you have your initial list of groups and policies, proceed to identify the segments you'll need.</span></span> 

### <a name="identify-segments"></a><span data-ttu-id="9b3a6-195">セグメントを識別する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-195">Identify segments</span></span>

<span data-ttu-id="9b3a6-196">ポリシーの初期リストに加えて、組織のセグメントの一覧を作成します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-196">In addition to your initial list of policies, make a list of segments for your organization.</span></span> <span data-ttu-id="9b3a6-197">組織内のすべてのユーザーはセグメントに属している必要があり、ユーザーは2つ以上のセグメントに所属している必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-197">Every user in your organization should belong to a segment, and no user should belong to two or more segments.</span></span> <span data-ttu-id="9b3a6-198">各セグメントには、1つの情報バリアポリシーのみを適用できます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-198">Each segment can have only one information barrier policy applied.</span></span> 

<span data-ttu-id="9b3a6-199">セグメントを定義するために使用する組織のディレクトリデータの属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-199">Determine which attributes in your organization's directory data you'll use to define segments.</span></span> <span data-ttu-id="9b3a6-200">*Department*、 *MemberOf*、またはサポートされている属性のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-200">You can use *Department*, *MemberOf*, or any of the supported attributes.</span></span> <span data-ttu-id="9b3a6-201">すべてのユーザーに対して選択する属性に値が設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-201">Make sure that you have values in the attribute you select for all users.</span></span> <span data-ttu-id="9b3a6-202">[情報バリア (プレビュー) でサポートされている属性の一覧を参照してください](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-202">[See the list of supported attributes for information barriers (Preview)](information-barriers-attributes.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b3a6-203">**次のセクションに進む前に、セグメントを定義するために使用できる属性の値がディレクトリデータにあることを確認して**ください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-203">**Before you proceed to the next section, make sure your directory data has values for attributes that you can use to define segments**.</span></span> <span data-ttu-id="9b3a6-204">ディレクトリデータに使用する属性の値が含まれていない場合は、情報の障壁を処理する前に、すべてのユーザーアカウントにその情報を含めるように更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-204">If your directory data does not have values for the attributes you want to use, then all user accounts must be updated to include that information before you proceed with information barriers.</span></span> <span data-ttu-id="9b3a6-205">これに関するヘルプを表示するには、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-205">To get help with this, see the following resources:</span></span><br/><span data-ttu-id="9b3a6-206">- [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-206">- [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span></span><br/><span data-ttu-id="9b3a6-207">- [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新する](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-207">- [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span></span>

### <a name="define-segments-using-powershell"></a><span data-ttu-id="9b3a6-208">PowerShell を使用してセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-208">Define segments using PowerShell</span></span>

<span data-ttu-id="9b3a6-209">セグメントを定義しても、ユーザーに影響はありません。情報バリアポリシーが定義され、適用される段階を設定するだけです。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-209">Defining segments does not effect users; it just sets the stage for information barrier policies to be defined and then applied.</span></span>

1. <span data-ttu-id="9b3a6-210">組織セグメントを定義するには、使用する[属性](information-barriers-attributes.md)に対応する**usergroupfilter**パラメーターを指定して、**新しい-組織**セグメントコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-210">To define an organizational segment, use the **New-OrganizationSegment** cmdlet with the **UserGroupFilter** parameter that corresponds to the [attribute](information-barriers-attributes.md) you want to use.</span></span> 

    <span data-ttu-id="9b3a6-211">文`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-211">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="9b3a6-212">例: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-212">Example: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span></span>

    <span data-ttu-id="9b3a6-213">この例では、hr と\*\* いう名前のセグメント\*\* が、Department 属性の値を使用して定義されています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-213">In this example, a segment called *HR* is defined using *HR*, a value in the Department attribute.</span></span>

2. <span data-ttu-id="9b3a6-214">定義するセグメントごとに、手順1を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-214">Repeat step 1 for each segment you want to define.</span></span>

    <span data-ttu-id="9b3a6-215">各コマンドレットを実行すると、新しいセグメントに関する詳細情報の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-215">After you run each cmdlet, you should see a list of details about the new segment.</span></span> <span data-ttu-id="9b3a6-216">詳細には、セグメントの種類、作成者または最終更新日時などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-216">Details include the segment's type, who created or last modified it, and so on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9b3a6-217">**セグメントが重ならないようにして**ください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-217">**Make sure that your segments do not overlap**.</span></span> <span data-ttu-id="9b3a6-218">組織内の各ユーザーは、1つ (1 つの) セグメントに所属している必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-218">Each user in your organization should belong to one (and only one) segment.</span></span> <span data-ttu-id="9b3a6-219">ユーザーは、2つ以上のセグメントに属することはできません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-219">No user should belong to two or more segments.</span></span> <span data-ttu-id="9b3a6-220">セグメントは、組織内のすべてのユーザーに対して定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-220">Segments should be defined for all users in your organization.</span></span> <span data-ttu-id="9b3a6-221">(この記事の「 [Example: Contoso の定義済みセグメント](#contosos-defined-segments)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-221">(See [Example: Contoso's defined segments](#contosos-defined-segments) in this article.)</span></span>

<span data-ttu-id="9b3a6-222">セグメントを定義した後、「情報バリアポリシーを定義する」に進みます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-222">After you have defined your segments, proceed to define information barrier policies.</span></span>

## <a name="part-2-define-information-barrier-policies"></a><span data-ttu-id="9b3a6-223">パート 2: 情報バリアポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-223">Part 2: Define information barrier policies</span></span>

<span data-ttu-id="9b3a6-224">特定のセグメント間の通信を禁止する必要があるか、または特定のセグメントへの通信を制限する必要があるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-224">Determine whether you need to prevent communications between certain segments, or limit communications to certain segments.</span></span> <span data-ttu-id="9b3a6-225">組織が法律上および業界の要件を満たしていることを確認するために、最小限のポリシーを使用することが理想的です。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-225">Ideally, you'll use the minimum number of policies to ensure your organization is compliant with legal and industry requirements.</span></span>

<span data-ttu-id="9b3a6-226">定義するユーザーセグメントと情報バリアポリシーの一覧を使用して、シナリオを選択し、手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-226">With your list of user segments and the information barrier policies you want to define, select a scenario, and then follow the steps.</span></span> 

- [<span data-ttu-id="9b3a6-227">シナリオ 1: セグメント間の通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-227">Scenario 1: Block communications between segments</span></span>](#scenario-1-block-communications-between-segments)
- [<span data-ttu-id="9b3a6-228">シナリオ 2: セグメントが他の1つのセグメントとのみ通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-228">Scenario 2: Allow a segment to communicate only with one other segment</span></span>](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> <span data-ttu-id="9b3a6-229">**ポリシーを定義するときは、1つのセグメントに複数のポリシーを割り当てない**ようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-229">**Make sure that as you define policies, you do not assign more than one policy to a segment**.</span></span> <span data-ttu-id="9b3a6-230">たとえば、 *sales*というセグメントに対して1つのポリシーを定義する場合は、 *sales*に対して追加のポリシーを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-230">For example, if you define one policy for a segment called *Sales*, do not define an additional policy for *Sales*.</span></span><p><span data-ttu-id="9b3a6-231">また、情報バリアポリシーを定義するときには、これらのポリシーを適用する準備ができるまで、非アクティブ状態に設定してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-231">In addition, as you define information barrier policies, make sure to set those policies to inactive status until you are ready to apply them.</span></span> <span data-ttu-id="9b3a6-232">ポリシーを定義 (または編集) すると、それらのポリシーがアクティブな状態に設定された後、ユーザーに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-232">Defining (or editing) policies does not affect users until those policies are set to active status and then applied.</span></span>

<span data-ttu-id="9b3a6-233">(この記事の「 [Example: Contoso の情報バリアポリシー](#contosos-information-barrier-policies) 」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-233">(See [Example: Contoso's information barrier policies](#contosos-information-barrier-policies) in this article.)</span></span>

### <a name="scenario-1-block-communications-between-segments"></a><span data-ttu-id="9b3a6-234">シナリオ 1: セグメント間の通信をブロックする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-234">Scenario 1: Block communications between segments</span></span>

<span data-ttu-id="9b3a6-235">セグメントが相互に通信するのをブロックする場合は、2つのポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-235">When you want to block segments from communicating with each other, you define two policies: one for each direction.</span></span> <span data-ttu-id="9b3a6-236">各ポリシーは、一一の通信のみをブロックします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-236">Each policy blocks communication one way only.</span></span>

<span data-ttu-id="9b3a6-237">たとえば、セグメント A とセグメント B 間の通信をブロックするとします。この場合は、セグメント A からセグメント B と通信することを妨げる1つのポリシーを定義してから、セグメント B とセグメント A との通信を禁止する2番目のポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-237">For example, suppose you want to block communications between Segment A and Segment B. In this case, you define one policy preventing Segment A from communicating with Segment B, and then define a second policy to prevent Segment B from communicating with Segment A.</span></span>

1. <span data-ttu-id="9b3a6-238">最初のブロックポリシーを定義するには、 **InformationBarrierPolicy**コマンドレットを**SegmentsBlocked**パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-238">To define your first blocking policy, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter.</span></span> 

    <span data-ttu-id="9b3a6-239">文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-239">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span></span>

    <span data-ttu-id="9b3a6-240">例: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-240">Example: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span></span>

    <span data-ttu-id="9b3a6-241">この例では、 *sales*というセグメントの*sales Research*というポリシーを定義しました。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-241">In this example, we defined a policy called *Sales-Research* for a segment called *Sales*.</span></span> <span data-ttu-id="9b3a6-242">このポリシーを有効にして適用すると、 *Sales*のユーザーは*Research*というセグメントにあるユーザーと通信できなくなります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-242">When active and applied, this policy prevents people in *Sales* from communicating with people in a segment called *Research*.</span></span>

2. <span data-ttu-id="9b3a6-243">2番目のブロックセグメントを定義するには、 **InformationBarrierPolicy**コマンドレットを**SegmentsBlocked**パラメーターと共に再度使用します。この場合は、セグメントを反転された状態にします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-243">To define your second blocking segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter again, this time with the segments reversed.</span></span>

    <span data-ttu-id="9b3a6-244">例: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-244">Example: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span></span>

    <span data-ttu-id="9b3a6-245">この例では、リサーチという名前のポリシーを定義して、研究*部門*との通信によるコミュニケーションを防止しています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-245">In this example, we defined a policy called *Research-Sales* to prevent Research from communicating with Sales.</span></span>
 
2. <span data-ttu-id="9b3a6-246">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-246">Proceed to one of the following:</span></span>

   - <span data-ttu-id="9b3a6-247">(必要な場合)[セグメントが1つの他のセグメントとのみ通信できるようにするポリシーを定義する](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-247">(If needed) [Define a policy to allow a segment to communicate only with one other segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span></span> 
   - <span data-ttu-id="9b3a6-248">(すべてのポリシーが定義された後)[情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-248">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a><span data-ttu-id="9b3a6-249">シナリオ 2: セグメントが他の1つのセグメントとのみ通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-249">Scenario 2: Allow a segment to communicate only with one other segment</span></span>

1. <span data-ttu-id="9b3a6-250">1つのセグメントが他の1つのセグメントとのみ通信できるようにするには、 **InformationBarrierPolicy**コマンドレットを**SegmentsAllowed**パラメーターと共に使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-250">To allow one segment to communicate with only one other segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsAllowed** parameter.</span></span> 

    <span data-ttu-id="9b3a6-251">文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-251">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span></span>

    <span data-ttu-id="9b3a6-252">例: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-252">Example: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span></span>

    <span data-ttu-id="9b3a6-253">この例では、*製造*と呼ばれるセグメントに対して、*工場*という名前のポリシーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-253">In this example, we defined a policy called *Manufacturing-HR* for a segment called *Manufacturing*.</span></span> <span data-ttu-id="9b3a6-254">このポリシーを有効にして適用すると、*製造*者は*HR*というセグメントにあるユーザーとのみ通信できるようになります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-254">When active and applied, this policy allows people in *Manufacturing* to communicate only with people in a segment called *HR*.</span></span> <span data-ttu-id="9b3a6-255">(この場合、製造は人事の一部ではないユーザーと通信できません)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-255">(In this case, Manufacturing cannot communicate with users who are not part of HR.)</span></span>

    <span data-ttu-id="9b3a6-256">**必要に応じて、次の2つの例に示すように、このコマンドレットで複数のセグメントを指定できます。**</span><span class="sxs-lookup"><span data-stu-id="9b3a6-256">**If needed, you can specify multiple segments with this cmdlet, as shown in the following two examples.**</span></span>

    <span data-ttu-id="9b3a6-257">文`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-257">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span></span>

    <span data-ttu-id="9b3a6-258">**例 1: 複数のセグメントが他の1つのセグメントのみと通信できるようにするポリシーを定義する**</span><span class="sxs-lookup"><span data-stu-id="9b3a6-258">**Example 1: Define a policy to allow multiple segments to communicate with only one other segment**</span></span>

    `New-InformationBarrierPolicy -Name "ResearchManufacturing-HR" -AssignedSegment "Research, Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    <span data-ttu-id="9b3a6-259">この例では、*研究*および*製造*セグメントが*HR*とのみ通信できるようにするポリシーを定義しました。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-259">In this example, we defined a policy that allows the *Research* and *Manufacturing* segments to communicate only with *HR*.</span></span>

    <span data-ttu-id="9b3a6-260">**例 2: 複数のセグメントが特定の他のセグメントのみと通信できるようにするポリシーを定義する**</span><span class="sxs-lookup"><span data-stu-id="9b3a6-260">**Example 2: Define a policy to allow multiple segments to communicate with only certain other segments**</span></span>    

    `New-InformationBarrierPolicy -Name "SalesMarketing-HRManufacturing" -AssignedSegment "Sales, Marketing" -SegmentsAllowed "HR, Manufacturing" -State Inactive`

    <span data-ttu-id="9b3a6-261">この例では、*営業*および*マーケティング*セグメントが*人事*および*製造*のみと通信できるようにするポリシーを定義しました。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-261">In this example, we defined a policy that allows the *Sales* and *Marketing* segments to communicate with only *HR* and *Manufacturing*.</span></span>

    <span data-ttu-id="9b3a6-262">特定のセグメントのみが特定の特定のセグメントと通信できるようにするために定義するポリシーごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-262">Repeat this step for each policy you want to define to allow specific segments to communicate with only certain other specific segments.</span></span>

2. <span data-ttu-id="9b3a6-263">次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-263">Proceed to one of the following:</span></span>

   - <span data-ttu-id="9b3a6-264">(必要な場合)[セグメント間の通信をブロックするポリシーを定義する](#scenario-1-block-communications-between-segments)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-264">(If needed) [Define a policy to block communications between segments](#scenario-1-block-communications-between-segments)</span></span> 
   - <span data-ttu-id="9b3a6-265">(すべてのポリシーが定義された後)[情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-265">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

## <a name="part-3-apply-information-barrier-policies"></a><span data-ttu-id="9b3a6-266">パート 3: 情報バリアポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-266">Part 3: Apply information barrier policies</span></span>

<span data-ttu-id="9b3a6-267">情報バリアポリシーは、アクティブな状態に設定してからポリシーを適用するまで有効になりません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-267">Information barrier policies are not in effect until you set them to active status, and then apply the policies.</span></span>

1. <span data-ttu-id="9b3a6-268">**InformationBarrierPolicy**コマンドレットを使用して、定義されているポリシーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-268">Use the **Get-InformationBarrierPolicy** cmdlet to see a list of policies that have been defined.</span></span> <span data-ttu-id="9b3a6-269">各ポリシーの状態と id (GUID) をメモします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-269">Note the status and identity (GUID) of each policy.</span></span>

    <span data-ttu-id="9b3a6-270">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-270">Syntax: `Get-InformationBarrierPolicy`</span></span>

2. <span data-ttu-id="9b3a6-271">ポリシーをアクティブな状態に設定するには、 **Identity**パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、 **State**パラメーターを**active**に設定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-271">To set a policy to active status, use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and the **State** parameter set to **Active**.</span></span> 

    <span data-ttu-id="9b3a6-272">文`Set-InformationBarrierPolicy -Identity GUID -State Active`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-272">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Active`</span></span>

    <span data-ttu-id="9b3a6-273">例: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-273">Example: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span></span>
    
    <span data-ttu-id="9b3a6-274">この例では、GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*の情報バリアポリシーをアクティブな状態に設定しています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-274">In this example, we set an information barrier policy that has the GUID *43c37853-ea10-4b90-a23d-ab8c93772471* to active status.</span></span>

    <span data-ttu-id="9b3a6-275">各ポリシーに該当する場合は、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-275">Repeat this step as appropriate for each policy.</span></span>

3. <span data-ttu-id="9b3a6-276">情報バリアポリシーのアクティブ状態の設定が終了したら、Office 365 セキュリティ & コンプライアンスセンターで**InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-276">When you have finished setting your information barrier policies to active status, use the **Start-InformationBarrierPoliciesApplication** cmdlet in the Office 365 Security & Compliance Center.</span></span>

    <span data-ttu-id="9b3a6-277">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-277">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9b3a6-278">約30時間後に、組織のポリシーがユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-278">After approximately a half hour, policies are applied, user by user, for your organization.</span></span> <span data-ttu-id="9b3a6-279">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-279">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="9b3a6-280">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-280">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a><span data-ttu-id="9b3a6-281">ユーザーアカウント、セグメント、ポリシー、またはポリシーアプリケーションの状態を表示する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-281">View status of user accounts, segments, policies, or policy application</span></span>

<span data-ttu-id="9b3a6-282">PowerShell を使用すると、次の表に示すように、ユーザーアカウント、セグメント、ポリシー、およびポリシーアプリケーションの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-282">With PowerShell, you can view status of user accounts, segments, policies, and policy application, as listed in the following table.</span></span>

|<span data-ttu-id="9b3a6-283">これを表示するには</span><span class="sxs-lookup"><span data-stu-id="9b3a6-283">To view this</span></span>  |<span data-ttu-id="9b3a6-284">説明</span><span class="sxs-lookup"><span data-stu-id="9b3a6-284">Do this</span></span>  |
|---------|---------|
|<span data-ttu-id="9b3a6-285">ユーザー アカウント</span><span class="sxs-lookup"><span data-stu-id="9b3a6-285">User accounts</span></span>     |<span data-ttu-id="9b3a6-286">Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-286">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <p><span data-ttu-id="9b3a6-287">文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-287">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> <p><span data-ttu-id="9b3a6-288">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-288">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p><span data-ttu-id="9b3a6-289">例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-289">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> <p><span data-ttu-id="9b3a6-290">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-290">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> <p><span data-ttu-id="9b3a6-291">(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます。)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-291">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> <p><span data-ttu-id="9b3a6-292">このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-292">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>|
|<span data-ttu-id="9b3a6-293">多角形</span><span class="sxs-lookup"><span data-stu-id="9b3a6-293">Segments</span></span>     |<span data-ttu-id="9b3a6-294">コマンドレット\*\*\*\* を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-294">Use the **Get-OrganizationSegment** cmdlet.</span></span><p><span data-ttu-id="9b3a6-295">文`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-295">Syntax: `Get-OrganizationSegment`</span></span> <p><span data-ttu-id="9b3a6-296">これにより、組織に定義されているすべてのセグメントの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-296">This will display a list of all segments defined for your organization.</span></span>         |
|<span data-ttu-id="9b3a6-297">情報バリアポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-297">Information barrier policies</span></span>     |<span data-ttu-id="9b3a6-298">**InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-298">Use the **Get-InformationBarrierPolicy** cmdlet.</span></span> <p> <span data-ttu-id="9b3a6-299">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-299">Syntax: `Get-InformationBarrierPolicy`</span></span> <p><span data-ttu-id="9b3a6-300">これにより、定義された情報バリアポリシーの一覧とその状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-300">This will display a list of information barrier policies that were defined, and their status.</span></span>       |
|<span data-ttu-id="9b3a6-301">最新情報バリアポリシーアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9b3a6-301">The most recent information barrier policy application</span></span>     | <span data-ttu-id="9b3a6-302">**InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-302">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span> <p><span data-ttu-id="9b3a6-303">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-303">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span><p>    <span data-ttu-id="9b3a6-304">これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-304">This will display information about whether policy application completed, failed, or is in progress.</span></span>       |
|<span data-ttu-id="9b3a6-305">すべての情報バリアポリシーアプリケーション</span><span class="sxs-lookup"><span data-stu-id="9b3a6-305">All information barrier policy applications</span></span>|<span data-ttu-id="9b3a6-306">使え`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-306">Use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span><p><span data-ttu-id="9b3a6-307">これにより、ポリシーの適用が完了したか、失敗したか、または進行中であるかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-307">This will display information about whether policy application completed, failed, or is in progress.</span></span>|

## <a name="stop-a-policy-application"></a><span data-ttu-id="9b3a6-308">ポリシーアプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-308">Stop a policy application</span></span>

<span data-ttu-id="9b3a6-309">情報バリアポリシーの適用を開始した後で、これらのポリシーの適用を停止するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-309">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="9b3a6-310">プロセスが開始されるまで約30-35 分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-310">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="9b3a6-311">最新の情報バリアポリシーアプリケーションの状態を表示するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-311">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="9b3a6-312">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-312">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="9b3a6-313">アプリケーションの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-313">Note the application's GUID.</span></span>

2. <span data-ttu-id="9b3a6-314">Identity パラメーターを指定して**InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-314">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="9b3a6-315">文`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-315">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="9b3a6-316">例: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-316">Example: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

## <a name="edit-a-segment-or-a-policy"></a><span data-ttu-id="9b3a6-317">セグメントまたはポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-317">Edit a segment or a policy</span></span>

### <a name="edit-a-segment"></a><span data-ttu-id="9b3a6-318">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-318">Edit a segment</span></span>

1. <span data-ttu-id="9b3a6-319">既存のすべてのセグメントを表示するには、コマンドレットの**取得**を使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-319">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="9b3a6-320">文`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-320">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="9b3a6-321">セグメントの種類、UserGroupFilter 値、作成者または最終更新日時、GUID など、セグメントと詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-321">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="9b3a6-322">後で参照するために、セグメントのリストを印刷または保存します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-322">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="9b3a6-323">たとえば、セグメントを編集する場合は、その名前を知っているか、値を識別する必要があります (これは Identity パラメーターと共に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-323">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="9b3a6-324">セグメントを編集するには、 **Identity**パラメーターと関連する詳細情報を使用して、**グループ**化コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-324">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="9b3a6-325">文`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-325">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="9b3a6-326">例: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-326">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="9b3a6-327">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントに対して、部署名を "hrdept" に更新しました。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-327">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="9b3a6-328">組織のセグメントの編集が終了したら、「情報バリアポリシーの[定義](#part-2-define-information-barrier-policies)または[編集](#edit-a-policy)」に進むことができます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-328">When you have finished editing segments for your organization, you can proceed to [define](#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

### <a name="edit-a-policy"></a><span data-ttu-id="9b3a6-329">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-329">Edit a policy</span></span>

1. <span data-ttu-id="9b3a6-330">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-330">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9b3a6-331">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-331">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9b3a6-332">結果の一覧で、変更するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-332">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="9b3a6-333">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-333">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="9b3a6-334">**InformationBarrierPolicy**コマンドレットを**Identity**パラメーターと共に使用して、必要な変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-334">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="9b3a6-335">構文 (セグメントが他のセグメントと通信することをブロックする):</span><span class="sxs-lookup"><span data-stu-id="9b3a6-335">Syntax (blocking segments from communicating with other segments):</span></span> 

    `Set-InformationBarrierPolicy -Identity GUID -SegmentsBlocked "segmentname, segmentname"` 

    <span data-ttu-id="9b3a6-336">構文 (セグメントが特定の他のセグメントとのみ通信できるようにする):</span><span class="sxs-lookup"><span data-stu-id="9b3a6-336">Syntax (enabling segments to communicate only with certain other segments):</span></span>
    
    ``Set-InformationBarrierPolicy -Identity GUID -SegmentsAllowed "segmentname, segmentname"``

    <span data-ttu-id="9b3a6-337">例: 研究をブロックするように定義されたポリシーが、営業およびマーケティングとの通信をブロックしているとします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-337">Example: Suppose a policy was defined to block Research from communicating with Sales and Marketing.</span></span> <span data-ttu-id="9b3a6-338">このポリシーは、このコマンドレットを使用して定義されています。`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-338">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span></span>
    
    <span data-ttu-id="9b3a6-339">研究者が人事内の人とのみ通信できるように変更したいと考えています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-339">Suppose we want to change it so that people in Research can only communicate with people in HR.</span></span> <span data-ttu-id="9b3a6-340">この変更を行うには、次のコマンドレットを使用します。`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-340">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

3. <span data-ttu-id="9b3a6-341">ポリシーの編集が終了したら、変更内容を適用してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-341">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="9b3a6-342">([情報バリアポリシーの適用](#part-3-apply-information-barrier-policies)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-342">(See [Apply information barrier policies](#part-3-apply-information-barrier-policies).)</span></span>

### <a name="remove-a-policy"></a><span data-ttu-id="9b3a6-343">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-343">Remove a policy</span></span>

1. <span data-ttu-id="9b3a6-344">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-344">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9b3a6-345">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-345">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9b3a6-346">結果の一覧で、削除するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-346">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="9b3a6-347">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-347">Note the policy's GUID and name.</span></span> <span data-ttu-id="9b3a6-348">ポリシーが非アクティブの状態に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-348">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="9b3a6-349">Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-349">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="9b3a6-350">文`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-350">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="9b3a6-351">例: GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*のポリシーを削除するとします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-351">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="9b3a6-352">これを行うには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-352">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="9b3a6-353">メッセージが表示されたら、変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-353">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="9b3a6-354">削除するポリシーごとに、手順1-2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-354">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="9b3a6-355">ポリシーの削除が終了したら、変更内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-355">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="9b3a6-356">これを行うには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-356">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="9b3a6-357">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-357">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9b3a6-358">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-358">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="9b3a6-359">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-359">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

### <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="9b3a6-360">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-360">Set a policy to inactive status</span></span>

1. <span data-ttu-id="9b3a6-361">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-361">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9b3a6-362">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-362">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9b3a6-363">結果の一覧で、変更する (または削除する) ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-363">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="9b3a6-364">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-364">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="9b3a6-365">ポリシーの状態を非アクティブに設定するには、Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、State パラメーターを inactive に設定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-365">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="9b3a6-366">文`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-366">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="9b3a6-367">この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247*を非アクティブな状態に設定する情報バリアポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-367">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="9b3a6-368">変更を適用するには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-368">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="9b3a6-369">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9b3a6-369">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9b3a6-370">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-370">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="9b3a6-371">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-371">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="9b3a6-372">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-372">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="9b3a6-373">この時点で、1つまたは複数の情報バリアポリシーが非アクティブ状態に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-373">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="9b3a6-374">ここから、次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-374">From here, you can do any of the following:</span></span>
- <span data-ttu-id="9b3a6-375">そのままにしておきます (非アクティブ状態に設定されたポリシーはユーザーに影響を与えません)。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-375">Leave it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="9b3a6-376">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-376">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="9b3a6-377">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-377">Remove a policy</span></span>](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a><span data-ttu-id="9b3a6-378">例: Contoso 社の部署、セグメント、ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-378">Example: Contoso's departments, segments, and policies</span></span>

<span data-ttu-id="9b3a6-379">組織がセグメントとポリシーを定義する方法を確認するには、次の例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-379">To see how an organization might approach defining segments and policies, consider the following example.</span></span>

### <a name="contosos-departments-and-plan"></a><span data-ttu-id="9b3a6-380">Contoso 社の部門と計画</span><span class="sxs-lookup"><span data-stu-id="9b3a6-380">Contoso's departments and plan</span></span>

<span data-ttu-id="9b3a6-381">Contoso には、人事、営業、マーケティング、研究、製造の5つの部門があります。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-381">Contoso has five departments: HR, Sales, Marketing, Research, and Manufacturing.</span></span> <span data-ttu-id="9b3a6-382">業界の規制に準拠するために、一部の部署のユーザーは、次の表に示すように、他の部署とは通信することは想定されていません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-382">In order to remain compliant with industry regulations, people in some departments are not supposed to communicate with other departments, as listed in the following table:</span></span>

|<span data-ttu-id="9b3a6-383">化</span><span class="sxs-lookup"><span data-stu-id="9b3a6-383">Segment</span></span>  |<span data-ttu-id="9b3a6-384">会話可能</span><span class="sxs-lookup"><span data-stu-id="9b3a6-384">Can talk to</span></span>  |<span data-ttu-id="9b3a6-385">会話できません</span><span class="sxs-lookup"><span data-stu-id="9b3a6-385">Cannot talk to</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9b3a6-386">HR</span><span class="sxs-lookup"><span data-stu-id="9b3a6-386">HR</span></span>     |<span data-ttu-id="9b3a6-387">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-387">Everyone</span></span>         |<span data-ttu-id="9b3a6-388">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-388">(no restrictions)</span></span>         |
|<span data-ttu-id="9b3a6-389">営業</span><span class="sxs-lookup"><span data-stu-id="9b3a6-389">Sales</span></span>     |<span data-ttu-id="9b3a6-390">人事、マーケティング、製造</span><span class="sxs-lookup"><span data-stu-id="9b3a6-390">HR, Marketing, Manufacturing</span></span>         |<span data-ttu-id="9b3a6-391">リサーチ</span><span class="sxs-lookup"><span data-stu-id="9b3a6-391">Research</span></span>         |
|<span data-ttu-id="9b3a6-392">マーケティング</span><span class="sxs-lookup"><span data-stu-id="9b3a6-392">Marketing</span></span>     |<span data-ttu-id="9b3a6-393">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-393">Everyone</span></span>         |<span data-ttu-id="9b3a6-394">(制限なし)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-394">(no restrictions)</span></span>         |
|<span data-ttu-id="9b3a6-395">リサーチ</span><span class="sxs-lookup"><span data-stu-id="9b3a6-395">Research</span></span>     |<span data-ttu-id="9b3a6-396">人事、マーケティング、製造</span><span class="sxs-lookup"><span data-stu-id="9b3a6-396">HR, Marketing, Manufacturing</span></span>        |<span data-ttu-id="9b3a6-397">営業</span><span class="sxs-lookup"><span data-stu-id="9b3a6-397">Sales</span></span>     |
|<span data-ttu-id="9b3a6-398">製造</span><span class="sxs-lookup"><span data-stu-id="9b3a6-398">Manufacturing</span></span> |<span data-ttu-id="9b3a6-399">人事、マーケティング</span><span class="sxs-lookup"><span data-stu-id="9b3a6-399">HR, Marketing</span></span> |<span data-ttu-id="9b3a6-400">人事またはマーケティング以外のすべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-400">Anyone other than HR or Marketing</span></span> |

<span data-ttu-id="9b3a6-401">この点を考慮して、Contoso 社の計画には3つの情報バリアポリシーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-401">With this in mind, Contoso's plan includes three information barrier policies:</span></span>

1. <span data-ttu-id="9b3a6-402">セールスが研究との通信を禁止するように設計されたポリシー (および研究からのセールスとの通信を禁止する別のポリシー)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-402">A policy designed to prevent Sales from communicating with Research (and another policy to prevent Research from communicating with Sales)</span></span>
2. <span data-ttu-id="9b3a6-403">製造に HR および Marketing のみと通信できるように設計されたポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-403">A policy designed to allow Manufacturing to communicate with HR and Marketing only</span></span> 

<span data-ttu-id="9b3a6-404">人事またはマーケティングのポリシーを定義する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-404">It's not necessary to define policies for HR or Marketing.</span></span>

### <a name="contosos-defined-segments"></a><span data-ttu-id="9b3a6-405">Contoso 社が定義したセグメント</span><span class="sxs-lookup"><span data-stu-id="9b3a6-405">Contoso's defined segments</span></span>

<span data-ttu-id="9b3a6-406">Contoso 社は、次のように、Azure Active Directory の Department 属性を使用してセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-406">Contoso will use the Department attribute in Azure Active Directory to define segments, as follows:</span></span>

|<span data-ttu-id="9b3a6-407">部署</span><span class="sxs-lookup"><span data-stu-id="9b3a6-407">Department</span></span>  |<span data-ttu-id="9b3a6-408">セグメント定義</span><span class="sxs-lookup"><span data-stu-id="9b3a6-408">Segment Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="9b3a6-409">HR</span><span class="sxs-lookup"><span data-stu-id="9b3a6-409">HR</span></span>     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|<span data-ttu-id="9b3a6-410">営業</span><span class="sxs-lookup"><span data-stu-id="9b3a6-410">Sales</span></span>     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|<span data-ttu-id="9b3a6-411">マーケティング</span><span class="sxs-lookup"><span data-stu-id="9b3a6-411">Marketing</span></span>     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|<span data-ttu-id="9b3a6-412">リサーチ</span><span class="sxs-lookup"><span data-stu-id="9b3a6-412">Research</span></span>     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|<span data-ttu-id="9b3a6-413">製造</span><span class="sxs-lookup"><span data-stu-id="9b3a6-413">Manufacturing</span></span>     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

<span data-ttu-id="9b3a6-414">セグメントが定義されていると、Contoso はポリシーの定義に進みます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-414">With the segments defined, Contoso proceeds to define policies.</span></span> 

### <a name="contosos-information-barrier-policies"></a><span data-ttu-id="9b3a6-415">Contoso 社の情報バリアポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-415">Contoso's information barrier policies</span></span>

<span data-ttu-id="9b3a6-416">Contoso 社では、次の表に示す3つのポリシーを定義しています。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-416">Contoso defines three polices, as described in the following table:</span></span>

|<span data-ttu-id="9b3a6-417">ポリシー</span><span class="sxs-lookup"><span data-stu-id="9b3a6-417">Policy</span></span>  |<span data-ttu-id="9b3a6-418">ポリシー定義</span><span class="sxs-lookup"><span data-stu-id="9b3a6-418">Policy Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="9b3a6-419">ポリシー 1: Sales がリサーチと通信できないようにする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-419">Policy 1: Prevent Sales from communicating with Research</span></span>     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> <span data-ttu-id="9b3a6-420">この例では、情報バリアポリシーを*Sales Research*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-420">In this example, the information barrier policy is called *Sales-Research*.</span></span> <span data-ttu-id="9b3a6-421">このポリシーがアクティブで適用されている場合は、営業部門のユーザーが Research セグメントのユーザーと通信できないようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-421">When this policy is active and applied, it will help prevent users who are in the Sales segment from communicating with users in the Research segment.</span></span> <span data-ttu-id="9b3a6-422">これは一ウェイのポリシーです。研究からセールスへのコミュニケーションが妨げられることはありません。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-422">This is a one-way policy; it won't prevent Research from communicating with Sales.</span></span> <span data-ttu-id="9b3a6-423">そのためには、ポリシー2が必要です。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-423">For that, Policy 2 is needed.</span></span>      |
|<span data-ttu-id="9b3a6-424">ポリシー 2: リサーチがセールスと通信できないようにする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-424">Policy 2: Prevent Research from communicating with Sales</span></span>     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> <span data-ttu-id="9b3a6-425">この例では、情報バリアポリシーを*Research Sales*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-425">In this example, the information barrier policy is called *Research-Sales*.</span></span> <span data-ttu-id="9b3a6-426">このポリシーがアクティブで適用されている場合は、リサーチセグメントにあるユーザーが営業セグメント内のユーザーと通信できないようにするのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-426">When this policy is active and applied, it will help prevent users who are in the Research segment from communicating with users in the Sales segment.</span></span>       |
|<span data-ttu-id="9b3a6-427">ポリシー 3: 製造に HR と Marketing のみが通信できるようにする</span><span class="sxs-lookup"><span data-stu-id="9b3a6-427">Policy 3: Allow Manufacturing to communicate with HR and Marketing only</span></span>     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR, Marketing" -State Inactive` <p><span data-ttu-id="9b3a6-428">この例では、情報バリアポリシーを*製造-HRMarketing*と呼びます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-428">In this case, the information barrier policy is called *Manufacturing-HRMarketing*.</span></span> <span data-ttu-id="9b3a6-429">このポリシーがアクティブで適用されている場合、製造は人事およびマーケティングとのみ通信できます。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-429">When this policy is active and applied, Manufacturing can communicate only with HR and Marketing.</span></span> <span data-ttu-id="9b3a6-430">人事およびマーケティングは、他のセグメントとの通信に制限されていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-430">Note that HR and Marketing are not restricted from communicating with other segments.</span></span> |

<span data-ttu-id="9b3a6-431">セグメントとポリシーが定義されているので、Contoso は**InformationBarrierPoliciesApplication**コマンドレットを実行してポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-431">With segments and policies defined, Contoso applies the policies by running the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span> 

<span data-ttu-id="9b3a6-432">この処理が完了すると、Contoso は法律および業界の要件に準拠します。</span><span class="sxs-lookup"><span data-stu-id="9b3a6-432">When that finishes, Contoso is compliant with legal and industry requirements.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9b3a6-433">関連記事</span><span class="sxs-lookup"><span data-stu-id="9b3a6-433">Related articles</span></span>

[<span data-ttu-id="9b3a6-434">情報障壁の概要を理解する</span><span class="sxs-lookup"><span data-stu-id="9b3a6-434">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="9b3a6-435">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="9b3a6-435">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="9b3a6-436">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-436">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="9b3a6-437">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9b3a6-437">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
