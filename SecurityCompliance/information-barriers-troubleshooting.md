---
title: 情報の障壁をトラブルシューティングする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: b88f97cd872d4ea3b95bfac049f47cd71dfb2cb2
ms.sourcegitcommit: c603a07d24c4c764bdcf13f9354b3b4b7a76f656
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2019
ms.locfileid: "35131351"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="7fad4-103">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fad4-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="7fad4-104">[情報障壁 (プレビュー)](information-barriers.md)は、組織が法律上の要件や業界の規制に準拠していることを維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-104">[Information barriers (Preview)](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="7fad4-105">たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="7fad4-106">(情報の障壁を設定する方法の詳細については、「 [Define policies for information バリア (Preview)](information-barriers-policies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7fad4-106">(To learn more about how to set up information barriers, see [Define policies for information barriers (Preview)](information-barriers-policies.md).)</span></span>

<span data-ttu-id="7fad4-107">情報の障壁が設定された後に予期しない問題が発生した場合は、それらの問題を解決するために実行できるいくつかの手順があります。</span><span class="sxs-lookup"><span data-stu-id="7fad4-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="7fad4-108">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-108">Use this article as a guide.</span></span>


## <a name="before-you-begin"></a><span data-ttu-id="7fad4-109">開始する前に</span><span class="sxs-lookup"><span data-stu-id="7fad4-109">Before you begin...</span></span>

<span data-ttu-id="7fad4-110">この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fad4-110">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span>
- <span data-ttu-id="7fad4-111">Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7fad4-111">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="7fad4-112">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="7fad4-112">Office 365 Global Administrator</span></span>
- <span data-ttu-id="7fad4-113">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="7fad4-113">Compliance Administrator</span></span>
- <span data-ttu-id="7fad4-114">IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="7fad4-114">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="7fad4-115">情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-115">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span>

<span data-ttu-id="7fad4-116">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-116">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-communications-are-still-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="7fad4-117">問題: Microsoft Teams でブロックする必要があるユーザー間でも、コミュニケーションが可能</span><span class="sxs-lookup"><span data-stu-id="7fad4-117">Issue: Communications are still allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="7fad4-118">この場合、情報バリアは定義、アクティブ、および適用されますが、相互に通信できないようにする必要があるユーザーは、Microsoft Teams でも利用できます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-118">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other still can in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="7fad4-119">行うこと</span><span class="sxs-lookup"><span data-stu-id="7fad4-119">What to do</span></span>

<span data-ttu-id="7fad4-120">該当するユーザーが情報バリアポリシーに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-120">Verify that the users in question are included in an information barrier policy.</span></span> <span data-ttu-id="7fad4-121">Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-121">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

<span data-ttu-id="7fad4-122">文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="7fad4-122">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 

<span data-ttu-id="7fad4-123">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-123">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 

<span data-ttu-id="7fad4-124">例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="7fad4-124">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 

<span data-ttu-id="7fad4-125">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-125">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 

<span data-ttu-id="7fad4-126">(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます)。このコマンドレットは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-126">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`) This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>


|<span data-ttu-id="7fad4-127">結果</span><span class="sxs-lookup"><span data-stu-id="7fad4-127">Results</span></span>  |<span data-ttu-id="7fad4-128">次のステップ</span><span class="sxs-lookup"><span data-stu-id="7fad4-128">Next steps</span></span>  |
|---------|---------|
|<span data-ttu-id="7fad4-129">選択したユーザーのセグメントが表示されません</span><span class="sxs-lookup"><span data-stu-id="7fad4-129">No segments are listed for the selected user(s)</span></span>     |<span data-ttu-id="7fad4-130">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-130">Do one of the following:</span></span><br/><span data-ttu-id="7fad4-131">-Azure Active Directory でユーザープロファイルを編集して、ユーザーを既存のセグメントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="7fad4-131">- Assign users to an existing segment by editing their user profiles in Azure Active Directory</span></span><br/><span data-ttu-id="7fad4-132">-[情報の障壁に対してサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義する</span><span class="sxs-lookup"><span data-stu-id="7fad4-132">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md)</span></span>         |
|<span data-ttu-id="7fad4-133">セグメントは表示されますが、これらのセグメントに情報バリアポリシーが割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="7fad4-133">Segments are listed but no information barrier policies are assigned to those segments</span></span>     |<span data-ttu-id="7fad4-134">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-134">Do one of the following:</span></span><br/><span data-ttu-id="7fad4-135">- 対象のセグメントごとに[情報バリアポリシーを定義する](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="7fad4-135">- [Define an information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span><br/><span data-ttu-id="7fad4-136">- [情報バリアポリシーを編集](information-barriers-policies.md#edit-a-policy)して、適切なセグメントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="7fad4-136">- [Edit an information barrier policy](information-barriers-policies.md#edit-a-policy) and assign it to the correct segment</span></span>         |
|<span data-ttu-id="7fad4-137">セグメントがリストされ、それぞれが情報バリアポリシーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-137">Segments are listed and each is included in an information barrier policy</span></span>     |<span data-ttu-id="7fad4-138">-コマンドレット`Get-InformationBarrierPolicy`を実行して、情報バリアポリシーがアクティブであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-138">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="7fad4-139">- `Get-InformationBarrierPoliciesApplicationStatus`コマンドレットを実行してポリシーが適用されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="7fad4-139">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="7fad4-140">-すべての`Start-InformationBarrierPoliciesApplication`アクティブ情報バリアポリシーを適用するには、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-140">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span>          |


## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="7fad4-141">問題: ユーザーが予期せず Microsoft Teams での通信をブロックされている</span><span class="sxs-lookup"><span data-stu-id="7fad4-141">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="7fad4-142">この場合、ユーザーは Microsoft Teams での予期しない問題を報告しています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-142">In this case, people are reporting unexpected issues communicating in Microsoft Teams.</span></span> <span data-ttu-id="7fad4-143">例:</span><span class="sxs-lookup"><span data-stu-id="7fad4-143">Examples:</span></span>
- <span data-ttu-id="7fad4-144">ユーザーが Microsoft Teams 内の他のユーザーとの間で検索や通信を行うことができません。</span><span class="sxs-lookup"><span data-stu-id="7fad4-144">A user is unable to find or communicate with another user in Microsoft Teams.</span></span>
- <span data-ttu-id="7fad4-145">ユーザーが Microsoft Teams で別のユーザーを表示または選択できません。</span><span class="sxs-lookup"><span data-stu-id="7fad4-145">A user cannot see or select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="7fad4-146">ユーザーは別のユーザーを表示できますが、Microsoft Teams 内の他のユーザーに対してメッセージを選択したり、送信したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="7fad4-146">A user can see another user, but cannot select or send messages to that other user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="7fad4-147">行うこと</span><span class="sxs-lookup"><span data-stu-id="7fad4-147">What to do</span></span>

1. <span data-ttu-id="7fad4-148">ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-148">Determine whether the users are affected by an information barrier policy.</span></span> <span data-ttu-id="7fad4-149">これを行うには、Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-149">To do this, use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="7fad4-150">構文は、`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="7fad4-150">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="7fad4-151">名前、エイリアス、識別名 (DN)、標準 DN、電子メールアドレス、GUID など、各受信者を一意に識別する任意の id 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-151">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="7fad4-152">例: `Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="7fad4-152">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="7fad4-153">この例では、Identity パラメーターに alias (*meガント b*) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-153">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="7fad4-154">このコマンドレットは、ユーザーが情報バリアポリシーの影響を受けているかどうかを示す情報を返します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-154">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="7fad4-155">(\* ExoPolicyId: \<GUID> を検索します。)</span><span class="sxs-lookup"><span data-stu-id="7fad4-155">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="7fad4-156">ユーザーが情報バリアポリシーに含まれていない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-156">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="7fad4-157">それ以外の場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-157">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="7fad4-158">情報バリアポリシーに含まれるセグメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-158">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="7fad4-159">これを行うには、 `Get-InformationBarrierPolicy` Identity パラメーターを指定したコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-159">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="7fad4-160">前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を identity 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-160">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="7fad4-161">例: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="7fad4-161">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="7fad4-162">この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*を持つ情報バリアポリシーに関する詳細情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-162">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="7fad4-163">コマンドレットを実行した後、結果で**AssignedSegment**、 **SegmentsAllowed**、および**SegmentsBlocked**の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-163">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="7fad4-164">例: `Get-InformationBarrierPolicy`コマンドレットを実行した後、結果の一覧で次のように表示されています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-164">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="7fad4-165">この場合、情報バリアポリシーが [営業] および [リサーチ] セグメントにあるユーザーに影響を与えることがわかります。</span><span class="sxs-lookup"><span data-stu-id="7fad4-165">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="7fad4-166">この場合、営業担当者は研究中の人々とコミュニケーションすることができません。</span><span class="sxs-lookup"><span data-stu-id="7fad4-166">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="7fad4-167">これが正しいように思われる場合は、情報バリアが期待どおりに機能しています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-167">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="7fad4-168">それ以外の場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-168">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="7fad4-169">セグメントが正しく定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-169">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="7fad4-170">これを行うには、 `Get-OrganizationSegment`コマンドレットを使用して、結果の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-170">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="7fad4-171">特定のセグメントの詳細を表示するには`Get-OrganizationSegment` 、Identity パラメーターを指定してコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-171">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="7fad4-172">例: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="7fad4-172">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="7fad4-173">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントについての情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="7fad4-173">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="7fad4-174">セグメントの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-174">Review the details for the segment.</span></span> <span data-ttu-id="7fad4-175">必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)してから、 `Start-InformationBarrierPoliciesApplication`コマンドレットを再度使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-175">If necessary, [edit a segment](information-barriers-policies.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="7fad4-176">情報バリアポリシーに問題がある場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-176">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="7fad4-177">問題: 情報バリアアプリケーションプロセスで時間がかかりすぎています</span><span class="sxs-lookup"><span data-stu-id="7fad4-177">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="7fad4-178">**InformationBarrierPoliciesApplication**コマンドレットを実行した後、プロセスが完了するまでに長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="7fad4-178">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="7fad4-179">行うこと</span><span class="sxs-lookup"><span data-stu-id="7fad4-179">What to do</span></span>

<span data-ttu-id="7fad4-180">Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-180">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="7fad4-181">ユーザー数が多い場合は、処理に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="7fad4-181">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="7fad4-182">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="7fad4-182">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="7fad4-183">最新のポリシーアプリケーションの状態を確認するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-183">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    <span data-ttu-id="7fad4-184">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="7fad4-184">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="7fad4-185">(*すべて*の情報バリアポリシーアプリケーションの状態を表示するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-185">(To display status for *all* information barrier policy applications, use this cmdlet:</span></span><br/>
    <span data-ttu-id="7fad4-186">`Get-InformationBarrierPoliciesApplicationStatus -All $true`)</span><span class="sxs-lookup"><span data-stu-id="7fad4-186"></span></span>

    <span data-ttu-id="7fad4-187">これにより、ポリシーアプリケーションの完了、失敗、進行中のいずれかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="7fad4-187">This will display information about whether policy application completed, failed, or is in progress..</span></span>

2. <span data-ttu-id="7fad4-188">前の手順の結果に応じて、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-188">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="7fad4-189">状態</span><span class="sxs-lookup"><span data-stu-id="7fad4-189">Status</span></span>  |<span data-ttu-id="7fad4-190">次の手順</span><span class="sxs-lookup"><span data-stu-id="7fad4-190">Next step</span></span>  |
    |---------|---------|
    |<span data-ttu-id="7fad4-191">**未開始**</span><span class="sxs-lookup"><span data-stu-id="7fad4-191">**Not started**</span></span>     |<span data-ttu-id="7fad4-192">**InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを調べて、ポリシー定義にエラーがないかどうか、またはアプリケーションが開始されていない理由を確認してください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-192">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    |<span data-ttu-id="7fad4-193">**失敗**</span><span class="sxs-lookup"><span data-stu-id="7fad4-193">**Failed**</span></span>     |<span data-ttu-id="7fad4-194">アプリケーションに障害が発生した場合は、監査ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-194">If the application has failed, review your audit log.</span></span> <span data-ttu-id="7fad4-195">また、セグメントとポリシーも確認してください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-195">Also review your segments and policies.</span></span> <span data-ttu-id="7fad4-196">複数のセグメントに割り当てられているユーザーはいますか?</span><span class="sxs-lookup"><span data-stu-id="7fad4-196">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="7fad4-197">セグメントに複数の poliicy が割り当てられているかどうか。</span><span class="sxs-lookup"><span data-stu-id="7fad4-197">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="7fad4-198">必要に応じて、[セグメントを編集](information-barriers-policies.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-policies.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-198">If necessary, [edit segments](information-barriers-policies.md#edit-a-segment) and/or [edit policies](information-barriers-policies.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>  |
    |<span data-ttu-id="7fad4-199">**処理中**</span><span class="sxs-lookup"><span data-stu-id="7fad4-199">**In progress**</span></span>     |<span data-ttu-id="7fad4-200">アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="7fad4-200">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="7fad4-201">数日経過した場合は、監査ログを収集し、サポートに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="7fad4-201">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="7fad4-202">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fad4-202">Related topics</span></span>

[<span data-ttu-id="7fad4-203">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fad4-203">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="7fad4-204">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fad4-204">Information barriers (Preview)</span></span>](information-barriers.md)



