---
title: 情報の障壁をトラブルシューティングする
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
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668317"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="3ede3-103">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3ede3-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="3ede3-104">情報バリアは、組織が法的な要件や業界の規制に準拠していることを支援します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-104">Information barriers can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="3ede3-105">たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="3ede3-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="3ede3-106">詳細については、「[情報の障壁 (プレビュー)](information-barriers.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-106">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span>

<span data-ttu-id="3ede3-107">この記事では、情報の障壁に関する質問に回答したり、発生する可能性のある問題を解決したりするために使用できるガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-107">This article provides guidance you can use to get answers to questions or resolve issues that may arise with information barriers.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="3ede3-108">開始する前に</span><span class="sxs-lookup"><span data-stu-id="3ede3-108">Before you begin...</span></span>

<span data-ttu-id="3ede3-109">この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ede3-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="3ede3-110">Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="3ede3-110">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="3ede3-111">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="3ede3-111">Office 365 Global Administrator</span></span>
- <span data-ttu-id="3ede3-112">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="3ede3-112">Compliance Administrator</span></span>
- <span data-ttu-id="3ede3-113">IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="3ede3-113">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="3ede3-114">役割とアクセス許可の詳細については、「 [Office 365 セキュリティ & コンプライアンスセンター」の「アクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-114">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="3ede3-115">情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="3ede3-116">また、 [Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-116">Also, make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="3ede3-117">問題: ユーザーが予期せず Microsoft Teams での通信をブロックされている</span><span class="sxs-lookup"><span data-stu-id="3ede3-117">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="3ede3-118">この場合、ユーザーは Microsoft Teams での予期しない問題を報告しています。</span><span class="sxs-lookup"><span data-stu-id="3ede3-118">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="3ede3-119">例:</span><span class="sxs-lookup"><span data-stu-id="3ede3-119">Examples:</span></span>
- <span data-ttu-id="3ede3-120">ユーザーが Microsoft Teams 内の他のユーザーとの間で検索や通信を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="3ede3-120">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="3ede3-121">ユーザーが Microsoft Teams で別のユーザーを表示または選択できません。</span><span class="sxs-lookup"><span data-stu-id="3ede3-121">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="3ede3-122">ユーザーは、Microsoft Teams の他のユーザーにメッセージを表示することはできますが、メッセージを送信することはできません。</span><span class="sxs-lookup"><span data-stu-id="3ede3-122">A user can see, but cannot send messages to, another user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="3ede3-123">行うこと</span><span class="sxs-lookup"><span data-stu-id="3ede3-123">What to do</span></span>

1. <span data-ttu-id="3ede3-124">ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-124">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="3ede3-125">これを行うには、Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-125">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="3ede3-126">構文は、`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="3ede3-126">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="3ede3-127">名前、エイリアス、識別名 (DN)、標準 DN、電子メールアドレス、GUID など、各受信者を一意に識別する任意の id 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ede3-127">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="3ede3-128">例: `Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="3ede3-128">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="3ede3-129">この例では、Identity パラメーターに alias (*meガント b*) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="3ede3-129">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="3ede3-130">このコマンドレットは、ユーザーが情報バリアポリシーの影響を受けているかどうかを示す情報を返します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-130">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="3ede3-131">(\* ExoPolicyId: \<GUID> を検索します。)</span><span class="sxs-lookup"><span data-stu-id="3ede3-131">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="3ede3-132">ユーザーが情報バリアポリシーに含まれていない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-132">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="3ede3-133">それ以外の場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-133">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="3ede3-134">情報バリアポリシーに含まれるセグメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-134">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="3ede3-135">これを行うには、 `Get-InformationBarrierPolicy` Identity パラメーターを指定したコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-135">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="3ede3-136">前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を identity 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-136">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="3ede3-137">例: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="3ede3-137">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="3ede3-138">この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*を持つ情報バリアポリシーに関する詳細情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="3ede3-138">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="3ede3-139">コマンドレットを実行した後、結果で**AssignedSegment**、 **SegmentsAllowed**、および**SegmentsBlocked**の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-139">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="3ede3-140">例: `Get-InformationBarrierPolicy`コマンドレットを実行した後、結果の一覧で次のように表示されています。</span><span class="sxs-lookup"><span data-stu-id="3ede3-140">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="3ede3-141">この場合、情報バリアポリシーが [営業] および [リサーチ] セグメントにあるユーザーに影響を与えることがわかります。</span><span class="sxs-lookup"><span data-stu-id="3ede3-141">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="3ede3-142">この場合、営業担当者は研究中の人々とコミュニケーションすることができません。</span><span class="sxs-lookup"><span data-stu-id="3ede3-142">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="3ede3-143">これが正しいように思われる場合は、情報バリアが期待どおりに機能しています。</span><span class="sxs-lookup"><span data-stu-id="3ede3-143">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="3ede3-144">それ以外の場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="3ede3-144">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="3ede3-145">セグメントが正しく定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-145">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="3ede3-146">これを行うには、 `Get-OrganizationSegment`コマンドレットを使用して、結果の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-146">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="3ede3-147">特定のセグメントの詳細を表示するには`Get-OrganizationSegment` 、Identity パラメーターを指定してコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-147">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="3ede3-148">例: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="3ede3-148">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="3ede3-149">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントについての情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="3ede3-149">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="3ede3-150">セグメントの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-150">Review the details for the segment.</span></span> <span data-ttu-id="3ede3-151">必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)してから、 `Start-InformationBarrierPoliciesApplication`コマンドレットを再度使用します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-151">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="3ede3-152">情報バリアポリシーに問題がある場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-152">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="3ede3-153">問題: 情報バリアアプリケーションプロセスで時間がかかりすぎています</span><span class="sxs-lookup"><span data-stu-id="3ede3-153">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="3ede3-154">**InformationBarrierPoliciesApplication**コマンドレットを実行した後、プロセスが完了するまでに長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="3ede3-154">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="3ede3-155">行うこと</span><span class="sxs-lookup"><span data-stu-id="3ede3-155">What to do</span></span>

1. <span data-ttu-id="3ede3-156">Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-156">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="3ede3-157">ユーザー数が多い場合は、処理に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="3ede3-157">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="3ede3-158">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="3ede3-158">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span> 

2. <span data-ttu-id="3ede3-159">状態を確認するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-159">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status.</span></span>

    <span data-ttu-id="3ede3-160">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="3ede3-160">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="3ede3-161">すべての情報バリアポリシーアプリケーションの状態を表示するには、を使用します。`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="3ede3-161">To display status for all information barrier policy applications, use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span>

    <span data-ttu-id="3ede3-162">これにより、ポリシーアプリケーションの完了、失敗、進行中のいずれかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="3ede3-162">This will display information about whether policy application completed, failed, or is in progress..</span></span>

3. <span data-ttu-id="3ede3-163">手順2の結果に応じて、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-163">Depending on the results of step 2, take one of the following steps:</span></span>

    - <span data-ttu-id="3ede3-164">アプリケーションが開始されておらず、 **InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを確認してポリシー定義にエラーがないかどうか、またはその他の理由でアプリケーションが開始されていません。</span><span class="sxs-lookup"><span data-stu-id="3ede3-164">If the application has not started, and it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span>

    - <span data-ttu-id="3ede3-165">アプリケーションに障害が発生した場合は、セグメントとポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-165">If the application has failed, review your segments and policies.</span></span> <span data-ttu-id="3ede3-166">必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-policies.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-166">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>

    - <span data-ttu-id="3ede3-167">アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="3ede3-167">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="3ede3-168">数日かかる場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="3ede3-168">If it has been several days, contact support.</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ede3-169">関連項目</span><span class="sxs-lookup"><span data-stu-id="3ede3-169">Related topics</span></span>

[<span data-ttu-id="3ede3-170">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3ede3-170">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="3ede3-171">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="3ede3-171">Information barriers (Preview)</span></span>](information-barriers.md)



