---
title: 情報の障壁をトラブルシューティングする
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/24/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報の障壁をトラブルシューティングするためのガイドとして使用してください。
ms.openlocfilehash: e8750358aaa7788c85f0ab656b30f5b5149d898c
ms.sourcegitcommit: 044003455eb36071806c9f008ac631d54c64dde6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/24/2019
ms.locfileid: "35199515"
---
# <a name="troubleshooting-information-barriers-preview"></a><span data-ttu-id="e8f02-103">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e8f02-103">Troubleshooting information barriers (Preview)</span></span>

<span data-ttu-id="e8f02-104">[情報障壁 (プレビュー)](information-barriers.md)は、組織が法律上の要件や業界の規制に準拠していることを維持するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-104">[Information barriers (Preview)](information-barriers.md) can help your organization remain compliant with legal requirements and industry regulations.</span></span> <span data-ttu-id="e8f02-105">たとえば、情報バリアを使用すると、特定のユーザーグループ間の通信を制限して、利息やその他の問題の競合を回避できます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-105">For example, with information barriers, you can restrict communication between specific groups of users to avoid a conflict of interest or other issues.</span></span> <span data-ttu-id="e8f02-106">(情報の障壁を設定する方法の詳細については、「 [Define policies for information バリア (Preview)](information-barriers-policies.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e8f02-106">(To learn more about how to set up information barriers, see [Define policies for information barriers (Preview)](information-barriers-policies.md).)</span></span>

<span data-ttu-id="e8f02-107">情報の障壁が設定された後に予期しない問題が発生した場合は、それらの問題を解決するために実行できるいくつかの手順があります。</span><span class="sxs-lookup"><span data-stu-id="e8f02-107">In the event that people run into unexpected issues after information barriers are in place, there are some steps you can take to resolve those issues.</span></span> <span data-ttu-id="e8f02-108">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-108">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e8f02-109">この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8f02-109">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="e8f02-110">-Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e8f02-110">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="e8f02-111">-Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e8f02-111">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="e8f02-112">-コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="e8f02-112">- Compliance Administrator</span></span><br/><span data-ttu-id="e8f02-113">-IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="e8f02-113">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="e8f02-114">情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-114">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="e8f02-115">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-115">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a><span data-ttu-id="e8f02-116">問題: Microsoft Teams でブロックする必要があるユーザー間で通信が許可されている</span><span class="sxs-lookup"><span data-stu-id="e8f02-116">Issue: Communications are allowed between users who should be blocked in Microsoft Teams</span></span>

<span data-ttu-id="e8f02-117">この場合、情報の障壁が定義され、アクティブ化されており、適用されていますが、相互に通信できないようにする必要があるユーザーは、Microsoft Teams で何らかの方法で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-117">In this case, although information barriers are defined, active, and applied, people who should be prevented from communicating with each other are somehow able to in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="e8f02-118">行うこと</span><span class="sxs-lookup"><span data-stu-id="e8f02-118">What to do</span></span>

<span data-ttu-id="e8f02-119">該当するユーザーが情報バリアポリシーに含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-119">Verify that the users in question are included in an information barrier policy.</span></span> 

1. <span data-ttu-id="e8f02-120">Identity パラメーターを使用して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-120">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span>

    <span data-ttu-id="e8f02-121">文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="e8f02-121">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 

    <span data-ttu-id="e8f02-122">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-122">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 

    <span data-ttu-id="e8f02-123">例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="e8f02-123">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 

    <span data-ttu-id="e8f02-124">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-124">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="e8f02-125">1人のユーザーに対してこのコマンドレットを使用することもできます。`Get-InformationBarrierRecipientStatus -Identity <value>`</span><span class="sxs-lookup"><span data-stu-id="e8f02-125">You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`</span></span>
    
2. <span data-ttu-id="e8f02-126">結果を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-126">Review the findings.</span></span> <span data-ttu-id="e8f02-127">**InformationBarrierRecipientStatus**コマンドレットでは、属性値、適用されている情報バリアポリシーなど、ユーザーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-127">The **Get-InformationBarrierRecipientStatus** cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span> 

    <span data-ttu-id="e8f02-128">結果を確認し、次の表に示すように、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-128">Review the results, and then take your next steps, as described in the following table:</span></span>
    
    |<span data-ttu-id="e8f02-129">結果</span><span class="sxs-lookup"><span data-stu-id="e8f02-129">Results</span></span>  |<span data-ttu-id="e8f02-130">次のステップ</span><span class="sxs-lookup"><span data-stu-id="e8f02-130">Next steps</span></span>  |
    |---------|---------|
    |<span data-ttu-id="e8f02-131">選択したユーザーのセグメントが表示されません</span><span class="sxs-lookup"><span data-stu-id="e8f02-131">No segments are listed for the selected user(s)</span></span>     |<span data-ttu-id="e8f02-132">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-132">Do one of the following:</span></span><br/><span data-ttu-id="e8f02-133">-Azure Active Directory でユーザープロファイルを編集して、ユーザーを既存のセグメントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-133">- Assign users to an existing segment by editing their user profiles in Azure Active Directory.</span></span> <span data-ttu-id="e8f02-134">(「 [Office 365 PowerShell を使用してユーザーアカウントのプロパティを構成する」を](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e8f02-134">(See [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).)</span></span><br/><span data-ttu-id="e8f02-135">-[情報バリアに対してサポートされている属性](information-barriers-attributes.md)を使用してセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-135">- Define a segment using a [supported attribute for information barriers](information-barriers-attributes.md).</span></span> <span data-ttu-id="e8f02-136">次に、[新しいポリシーを定義](information-barriers-policies.md#part-2-define-information-barrier-policies)するか、[既存のポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)してそのセグメントを含めます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-136">Then, either [define a new policy](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit an existing policy](information-barriers-edit-segments-policies.md.md#edit-a-policy) to include that segment.</span></span>  |
    |<span data-ttu-id="e8f02-137">セグメントは表示されますが、これらのセグメントに情報バリアポリシーが割り当てられていません</span><span class="sxs-lookup"><span data-stu-id="e8f02-137">Segments are listed but no information barrier policies are assigned to those segments</span></span>     |<span data-ttu-id="e8f02-138">次のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-138">Do one of the following:</span></span><br/><span data-ttu-id="e8f02-139">- 対象のセグメントごとに[新しい情報バリアポリシーを定義する](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="e8f02-139">- [Define a new information barrier policy](information-barriers-policies.md#part-2-define-information-barrier-policies) for each segment in question</span></span><br/><span data-ttu-id="e8f02-140">- [既存の情報バリアポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)して正しいセグメントに割り当てる</span><span class="sxs-lookup"><span data-stu-id="e8f02-140">- [Edit an existing information barrier policy](information-barriers-edit-segments-policies.md.md#edit-a-policy) to assign it to the correct segment</span></span>         |
    |<span data-ttu-id="e8f02-141">セグメントがリストされ、それぞれが情報バリアポリシーに含まれています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-141">Segments are listed and each is included in an information barrier policy</span></span>     |<span data-ttu-id="e8f02-142">-コマンドレット`Get-InformationBarrierPolicy`を実行して、情報バリアポリシーがアクティブであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-142">- Run the `Get-InformationBarrierPolicy` cmdlet to verify that information barrier policies are active</span></span><br/><span data-ttu-id="e8f02-143">- `Get-InformationBarrierPoliciesApplicationStatus`コマンドレットを実行してポリシーが適用されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="e8f02-143">- Run the `Get-InformationBarrierPoliciesApplicationStatus` cmdlet to confirm the policies are applied</span></span><br/><span data-ttu-id="e8f02-144">-すべての`Start-InformationBarrierPoliciesApplication`アクティブ情報バリアポリシーを適用するには、コマンドレットを実行します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-144">- Run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies</span></span>          |
    

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a><span data-ttu-id="e8f02-145">問題: ユーザーが予期せず Microsoft Teams での通信をブロックされている</span><span class="sxs-lookup"><span data-stu-id="e8f02-145">Issue: People are unexpectedly blocked from communicating in Microsoft Teams</span></span> 

<span data-ttu-id="e8f02-146">この場合、ユーザーは、Microsoft Teams の他のユーザーとの間で予期しない問題を報告しています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-146">In this case, people are reporting unexpected issues communicating with others in Microsoft Teams.</span></span> <span data-ttu-id="e8f02-147">例:</span><span class="sxs-lookup"><span data-stu-id="e8f02-147">Examples:</span></span>
- <span data-ttu-id="e8f02-148">ユーザーが Microsoft Teams で別のユーザーを見つけることができません。</span><span class="sxs-lookup"><span data-stu-id="e8f02-148">A user is unable to find another user in Microsoft Teams.</span></span>
- <span data-ttu-id="e8f02-149">ユーザーが Microsoft Teams で別のユーザーを選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8f02-149">A user cannot select another user in Microsoft Teams.</span></span>
- <span data-ttu-id="e8f02-150">ユーザーは別のユーザーを表示できますが、Microsoft Teams 内の他のユーザーに対してメッセージを選択したり、送信したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e8f02-150">A user can see another user, but cannot select or send messages to that other user in Microsoft Teams.</span></span>
- <span data-ttu-id="e8f02-151">ユーザーは別のユーザーを表示して選択できますが、Microsoft Teams でそのユーザーと通信することはできません。</span><span class="sxs-lookup"><span data-stu-id="e8f02-151">A user can see and select another user, but cannot communicate with that user in Microsoft Teams.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="e8f02-152">行うこと</span><span class="sxs-lookup"><span data-stu-id="e8f02-152">What to do</span></span>

<span data-ttu-id="e8f02-153">ユーザーが情報バリアポリシーの影響を受けているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-153">Determine whether the users are affected by an information barrier policy.</span></span>

1. <span data-ttu-id="e8f02-154">Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-154">Use the **Get-InformationBarrierRecipientStatus** cmdlet with the Identity parameter.</span></span> 

    <span data-ttu-id="e8f02-155">構文は、`Get-InformationBarrierRecipientStatus -Identity`</span><span class="sxs-lookup"><span data-stu-id="e8f02-155">The syntax is `Get-InformationBarrierRecipientStatus -Identity`</span></span>

    <span data-ttu-id="e8f02-156">名前、エイリアス、識別名 (DN)、標準 DN、電子メールアドレス、GUID など、各受信者を一意に識別する任意の id 値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-156">You can use any identity value that uniquely identifies each recipient, such as Name, Alias, Distinguished name (DN), Canonical DN, Email address, or GUID.</span></span>

    <span data-ttu-id="e8f02-157">例: `Get-InformationBarrierRecipientStatus -Identity meganb`</span><span class="sxs-lookup"><span data-stu-id="e8f02-157">Example: `Get-InformationBarrierRecipientStatus -Identity meganb`</span></span>

    <span data-ttu-id="e8f02-158">この例では、Identity パラメーターに alias (*meガント b*) を使用しています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-158">In this example, we are using an alias (*meganb*) for the Identity parameter.</span></span> <span data-ttu-id="e8f02-159">このコマンドレットは、ユーザーが情報バリアポリシーの影響を受けているかどうかを示す情報を返します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-159">This cmdlet will return information that indicates whether the user is affected by an information barrier policy.</span></span> <span data-ttu-id="e8f02-160">(\* ExoPolicyId: \<GUID> を検索します。)</span><span class="sxs-lookup"><span data-stu-id="e8f02-160">(Look for \*ExoPolicyId: \<GUID>.)</span></span>

    <span data-ttu-id="e8f02-161">ユーザーが情報バリアポリシーに含まれていない場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-161">If the users are not included in information barrier policies, contact support.</span></span> <span data-ttu-id="e8f02-162">それ以外の場合は、次の手順に進んでください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-162">Otherwise, proceed to the next step.</span></span>

2. <span data-ttu-id="e8f02-163">情報バリアポリシーに含まれるセグメントを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-163">Find out which segments are included in an information barrier policy.</span></span> <span data-ttu-id="e8f02-164">これを行うには、 `Get-InformationBarrierPolicy` Identity パラメーターを指定したコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-164">To do this, use the `Get-InformationBarrierPolicy` cmdlet with the Identity parameter.</span></span> <span data-ttu-id="e8f02-165">前の手順で受信したポリシー GUID (ExoPolicyId) などの詳細を identity 値として使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-165">Use details, such as the policy GUID (ExoPolicyId) you received during the previous step, as an identity value.</span></span>

    <span data-ttu-id="e8f02-166">例: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span><span class="sxs-lookup"><span data-stu-id="e8f02-166">Example: `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`</span></span>

    <span data-ttu-id="e8f02-167">この例では、ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*を持つ情報バリアポリシーに関する詳細情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-167">In this example, we are getting detailed information about the information barrier policy that has ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*.</span></span>
    
    <span data-ttu-id="e8f02-168">コマンドレットを実行した後、結果で**AssignedSegment**、 **SegmentsAllowed**、および**SegmentsBlocked**の値を検索します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-168">After you run the cmdlet, in the results, look for **AssignedSegment**, **SegmentsAllowed**, and **SegmentsBlocked** values.</span></span>

    <span data-ttu-id="e8f02-169">例: `Get-InformationBarrierPolicy`コマンドレットを実行した後、結果の一覧で次のように表示されています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-169">Example: After running the `Get-InformationBarrierPolicy` cmdlet, we saw the following in our list of results:</span></span>

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    <span data-ttu-id="e8f02-170">この場合、情報バリアポリシーが [営業] および [リサーチ] セグメントにあるユーザーに影響を与えることがわかります。</span><span class="sxs-lookup"><span data-stu-id="e8f02-170">In this case, we can see that an information barrier policy affects people who are in the Sales and Research segments.</span></span> <span data-ttu-id="e8f02-171">この場合、営業担当者は研究中の人々とコミュニケーションすることができません。</span><span class="sxs-lookup"><span data-stu-id="e8f02-171">In this case, people in Sales are prevented from communicating with people in Research.</span></span> <span data-ttu-id="e8f02-172">これが正しいように思われる場合は、情報バリアが期待どおりに機能しています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-172">If this seems correct, then information barriers are working as expected.</span></span> <span data-ttu-id="e8f02-173">それ以外の場合は、次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-173">If not, proceed to the next step.</span></span>

4. <span data-ttu-id="e8f02-174">セグメントが正しく定義されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-174">Make sure your segments are defined correctly.</span></span> <span data-ttu-id="e8f02-175">これを行うには、 `Get-OrganizationSegment`コマンドレットを使用して、結果の一覧を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-175">To do this, use the `Get-OrganizationSegment` cmdlet, and review the list of results.</span></span> 

    <span data-ttu-id="e8f02-176">特定のセグメントの詳細を表示するには`Get-OrganizationSegment` 、Identity パラメーターを指定してコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-176">To view details for a specific segment, use the `Get-OrganizationSegment` cmdlet with an Identity parameter.</span></span> 

    <span data-ttu-id="e8f02-177">例: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span><span class="sxs-lookup"><span data-stu-id="e8f02-177">Example: `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`</span></span>

    <span data-ttu-id="e8f02-178">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントについての情報を取得しています。</span><span class="sxs-lookup"><span data-stu-id="e8f02-178">In this example, we are getting information about the segment that has GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*.</span></span>

    <span data-ttu-id="e8f02-179">セグメントの詳細を確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-179">Review the details for the segment.</span></span> <span data-ttu-id="e8f02-180">必要に応じて、[セグメントを編集](information-barriers-edit-segments-policies.md.md#edit-a-segment)してから、 `Start-InformationBarrierPoliciesApplication`コマンドレットを再度使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-180">If necessary, [edit a segment](information-barriers-edit-segments-policies.md.md#edit-a-segment), and then re-use the `Start-InformationBarrierPoliciesApplication` cmdlet.</span></span>

    <span data-ttu-id="e8f02-181">情報バリアポリシーに問題がある場合は、サポートにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-181">If you are still having issues with your information barrier policy, contact support.</span></span>
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a><span data-ttu-id="e8f02-182">問題: 情報バリアアプリケーションプロセスで時間がかかりすぎています</span><span class="sxs-lookup"><span data-stu-id="e8f02-182">Issue: The information barrier application process is taking too long</span></span>

<span data-ttu-id="e8f02-183">**InformationBarrierPoliciesApplication**コマンドレットを実行した後、プロセスが完了するまでに長い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e8f02-183">After running the **Start-InformationBarrierPoliciesApplication** cmdlet, the process is taking a really long time to finish.</span></span>

### <a name="what-to-do"></a><span data-ttu-id="e8f02-184">行うこと</span><span class="sxs-lookup"><span data-stu-id="e8f02-184">What to do</span></span>

<span data-ttu-id="e8f02-185">Policy application コマンドレットを実行すると、組織内のすべてのアカウントについて、情報バリアポリシーがユーザーごとに適用 (または削除) されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-185">Keep in mind that when you run the policy application cmdlet, information barrier policies are being applied (or removed), user by user, for all accounts in your organization.</span></span> <span data-ttu-id="e8f02-186">ユーザー数が多い場合は、処理に時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="e8f02-186">If you have a lot of users, it will take a while to process.</span></span> <span data-ttu-id="e8f02-187">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="e8f02-187">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

1. <span data-ttu-id="e8f02-188">最新のポリシーアプリケーションの状態を確認するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-188">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet to verify status of the most recent policy application.</span></span>

    <span data-ttu-id="e8f02-189">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="e8f02-189">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="e8f02-190">(*すべて*の情報バリアポリシーアプリケーションの状態を表示するには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-190">(To display status for *all* information barrier policy applications, use this cmdlet:</span></span><br/>
    <span data-ttu-id="e8f02-191">`Get-InformationBarrierPoliciesApplicationStatus -All $true`)</span><span class="sxs-lookup"><span data-stu-id="e8f02-191"></span></span>

    <span data-ttu-id="e8f02-192">これにより、ポリシーアプリケーションの完了、失敗、進行中のいずれかに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e8f02-192">This will display information about whether policy application completed, failed, or is in progress..</span></span>

2. <span data-ttu-id="e8f02-193">前の手順の結果に応じて、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-193">Depending on the results of the previous step, take one of the following steps:</span></span>
  
    |<span data-ttu-id="e8f02-194">状態</span><span class="sxs-lookup"><span data-stu-id="e8f02-194">Status</span></span>  |<span data-ttu-id="e8f02-195">次の手順</span><span class="sxs-lookup"><span data-stu-id="e8f02-195">Next step</span></span>  |
    |---------|---------|
    |<span data-ttu-id="e8f02-196">**未開始**</span><span class="sxs-lookup"><span data-stu-id="e8f02-196">**Not started**</span></span>     |<span data-ttu-id="e8f02-197">**InformationBarrierPoliciesApplication**コマンドレットが実行されてから45分以上経過している場合は、監査ログを調べて、ポリシー定義にエラーがないかどうか、またはアプリケーションが開始されていない理由を確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-197">If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started.</span></span> |
    |<span data-ttu-id="e8f02-198">**失敗**</span><span class="sxs-lookup"><span data-stu-id="e8f02-198">**Failed**</span></span>     |<span data-ttu-id="e8f02-199">アプリケーションに障害が発生した場合は、監査ログを確認します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-199">If the application has failed, review your audit log.</span></span> <span data-ttu-id="e8f02-200">また、セグメントとポリシーも確認してください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-200">Also review your segments and policies.</span></span> <span data-ttu-id="e8f02-201">複数のセグメントに割り当てられているユーザーはいますか?</span><span class="sxs-lookup"><span data-stu-id="e8f02-201">Are any users assigned to more than one segment?</span></span> <span data-ttu-id="e8f02-202">セグメントに複数の poliicy が割り当てられているかどうか。</span><span class="sxs-lookup"><span data-stu-id="e8f02-202">Are any segments assigned more than one poliicy?</span></span> <span data-ttu-id="e8f02-203">必要に応じて、[セグメントを編集](information-barriers-edit-segments-policies.md.md#edit-a-segment)するか、または[ポリシーを編集](information-barriers-edit-segments-policies.md.md#edit-a-policy)してから、 **InformationBarrierPoliciesApplication**コマンドレットを再度実行します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-203">If necessary, [edit segments](information-barriers-edit-segments-policies.md.md#edit-a-segment) and/or [edit policies](information-barriers-edit-segments-policies.md.md#edit-a-policy), and then run the **Start-InformationBarrierPoliciesApplication** cmdlet again.</span></span>  |
    |<span data-ttu-id="e8f02-204">**処理中**</span><span class="sxs-lookup"><span data-stu-id="e8f02-204">**In progress**</span></span>     |<span data-ttu-id="e8f02-205">アプリケーションがまだ進行中の場合は、完了するのに時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="e8f02-205">If the application is still in progress, allow more time for it to complete.</span></span> <span data-ttu-id="e8f02-206">数日経過した場合は、監査ログを収集し、サポートに連絡してください。</span><span class="sxs-lookup"><span data-stu-id="e8f02-206">If it has been several days, gather your audit logs, and then contact support.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="e8f02-207">関連項目</span><span class="sxs-lookup"><span data-stu-id="e8f02-207">Related topics</span></span>

[<span data-ttu-id="e8f02-208">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e8f02-208">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="e8f02-209">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="e8f02-209">Information barriers (Preview)</span></span>](information-barriers.md)



