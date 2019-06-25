---
title: 情報バリアポリシーを編集または削除する
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
description: 情報バリアのポリシーを編集または削除する方法について説明します。
ms.openlocfilehash: e6bed4df2329d426f86bd4cde07bdc7d1a2792cd
ms.sourcegitcommit: 7c48ce016fa9f45a3813467f7c5a2fd72f9b8f49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2019
ms.locfileid: "35215650"
---
# <a name="edit-or-remove-information-barrier-policies-preview"></a><span data-ttu-id="9383b-103">情報バリアポリシーの編集または削除 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9383b-103">Edit or remove information barrier policies (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="9383b-104">概要</span><span class="sxs-lookup"><span data-stu-id="9383b-104">Overview</span></span>

<span data-ttu-id="9383b-105">[情報バリアポリシーを定義](information-barriers-policies.md)した後、[トラブルシューティング](information-barriers-troubleshooting.md)の一環として、または定期的な保守の一環として、これらのポリシーまたはユーザーセグメントに変更を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="9383b-105">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="9383b-106">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-106">Use this article as a guide.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9383b-107">この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9383b-107">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="9383b-108">-Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="9383b-108">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="9383b-109">-Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="9383b-109">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="9383b-110">-コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="9383b-110">- Compliance Administrator</span></span><br/><span data-ttu-id="9383b-111">-IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="9383b-111">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="9383b-112">情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9383b-112">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="9383b-113">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="9383b-113">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="9383b-114">ユーザーアカウントの属性を編集する</span><span class="sxs-lookup"><span data-stu-id="9383b-114">Edit user account attributes</span></span>

<span data-ttu-id="9383b-115">ユーザーのセグメント化に使用される属性を編集するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-115">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="9383b-116">たとえば、Department 属性を使用していて、1つまたは複数のユーザーアカウントで Department の値がリストされていない場合は、それらのユーザーアカウントを編集して部署情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="9383b-116">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="9383b-117">ユーザーアカウント属性は、情報バリアポリシーを割り当てることができるように、セグメントを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="9383b-117">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="9383b-118">属性値、割り当てられたセグメントなど、特定のユーザーアカウントの詳細を表示するには、Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-118">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

   <span data-ttu-id="9383b-119">文`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="9383b-119">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> 
    
   <span data-ttu-id="9383b-120">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9383b-120">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> 
    
   <span data-ttu-id="9383b-121">例: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="9383b-121">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> 
    
   <span data-ttu-id="9383b-122">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="9383b-122">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> 
    
   <span data-ttu-id="9383b-123">(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます。)</span><span class="sxs-lookup"><span data-stu-id="9383b-123">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> 
    
2. <span data-ttu-id="9383b-124">ユーザーアカウントプロファイルに対してどの属性を編集するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-124">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="9383b-125">詳細については、 [「情報バリアポリシーの属性 (プレビュー)](information-barriers-attributes.md) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9383b-125">Refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="9383b-126">1つ以上のユーザーアカウントを編集して、前の手順で選択した属性の値を含めます。</span><span class="sxs-lookup"><span data-stu-id="9383b-126">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="9383b-127">これを行うには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-127">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="9383b-128">単一のアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9383b-128">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="9383b-129">複数のアカウントを編集する (または PowerShell を使用して1つのアカウントを編集する) には、「 [Office 365 powershell でユーザーアカウントのプロパティを構成](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9383b-129">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="9383b-130">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="9383b-130">Edit a segment</span></span>

<span data-ttu-id="9383b-131">この手順を使用して、ユーザーセグメントの定義を編集します。</span><span class="sxs-lookup"><span data-stu-id="9383b-131">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="9383b-132">たとえば、セグメントの名前を変更したり、セグメントに含まれている人物を特定するために使用するフィルターを変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="9383b-132">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="9383b-133">既存のすべてのセグメントを表示するには、コマンドレットの**取得**を使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-133">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="9383b-134">文`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="9383b-134">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="9383b-135">セグメントの種類、UserGroupFilter 値、作成者または最終更新日時、GUID など、セグメントと詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9383b-135">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="9383b-136">後で参照するために、セグメントのリストを印刷または保存します。</span><span class="sxs-lookup"><span data-stu-id="9383b-136">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="9383b-137">たとえば、セグメントを編集する場合は、その名前を知っているか、値を識別する必要があります (これは Identity パラメーターと共に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="9383b-137">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="9383b-138">セグメントを編集するには、 **Identity**パラメーターと関連する詳細情報を使用して、**グループ**化コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-138">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="9383b-139">文`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="9383b-139">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="9383b-140">例: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="9383b-140">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="9383b-141">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントに対して、部署名を "hrdept" に更新しました。</span><span class="sxs-lookup"><span data-stu-id="9383b-141">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="9383b-142">組織のセグメントの編集が終了したら、情報バリアポリシーの[定義](information-barriers-policies.md#part-2-define-information-barrier-policies)または[編集](#edit-a-policy)を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9383b-142">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="9383b-143">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="9383b-143">Edit a policy</span></span>

1. <span data-ttu-id="9383b-144">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-144">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9383b-145">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9383b-145">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9383b-146">結果の一覧で、変更するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-146">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="9383b-147">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="9383b-147">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="9383b-148">**InformationBarrierPolicy**コマンドレットを**Identity**パラメーターと共に使用して、必要な変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-148">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="9383b-149">例: ポリシーが定義されていて、*リサーチ*セグメントが*販売*および*マーケティング*セグメントとの通信をブロックするとします。</span><span class="sxs-lookup"><span data-stu-id="9383b-149">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="9383b-150">このポリシーは、このコマンドレットを使用して定義されています。`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="9383b-150">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="9383b-151">*研究*セグメント内のユーザーが*HR*セグメント内のユーザーとのみ通信できるように変更するとします。</span><span class="sxs-lookup"><span data-stu-id="9383b-151">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="9383b-152">この変更を行うには、次のコマンドレットを使用します。`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="9383b-152">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="9383b-153">この例では、"SegmentsBlocked" を "SegmentsAllowed" に変更し、 *HR*セグメントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="9383b-153">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="9383b-154">ポリシーの編集が終了したら、変更内容を適用してください。</span><span class="sxs-lookup"><span data-stu-id="9383b-154">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="9383b-155">([情報バリアポリシーの適用](information-barriers-policies.md#part-3-apply-information-barrier-policies)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9383b-155">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="9383b-156">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="9383b-156">Set a policy to inactive status</span></span>

1. <span data-ttu-id="9383b-157">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-157">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9383b-158">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9383b-158">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9383b-159">結果の一覧で、変更する (または削除する) ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-159">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="9383b-160">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="9383b-160">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="9383b-161">ポリシーの状態を非アクティブに設定するには、Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、State パラメーターを inactive に設定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-161">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="9383b-162">文`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="9383b-162">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="9383b-163">この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247*を非アクティブな状態に設定する情報バリアポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-163">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="9383b-164">変更を適用するには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-164">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="9383b-165">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9383b-165">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9383b-166">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9383b-166">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="9383b-167">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9383b-167">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="9383b-168">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="9383b-168">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="9383b-169">この時点で、1つまたは複数の情報バリアポリシーが非アクティブ状態に設定されます。</span><span class="sxs-lookup"><span data-stu-id="9383b-169">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="9383b-170">ここから、次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="9383b-170">From here, you can do any of the following:</span></span>
- <span data-ttu-id="9383b-171">そのまま保持する (非アクティブな状態に設定されたポリシーはユーザーに影響しません)</span><span class="sxs-lookup"><span data-stu-id="9383b-171">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="9383b-172">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="9383b-172">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="9383b-173">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="9383b-173">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="9383b-174">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="9383b-174">Remove a policy</span></span>

1. <span data-ttu-id="9383b-175">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-175">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="9383b-176">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="9383b-176">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="9383b-177">結果の一覧で、削除するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="9383b-177">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="9383b-178">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="9383b-178">Note the policy's GUID and name.</span></span> <span data-ttu-id="9383b-179">ポリシーが非アクティブの状態に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9383b-179">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="9383b-180">Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-180">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="9383b-181">文`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="9383b-181">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="9383b-182">例: GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*のポリシーを削除するとします。</span><span class="sxs-lookup"><span data-stu-id="9383b-182">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="9383b-183">これを行うには、次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-183">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="9383b-184">メッセージが表示されたら、変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="9383b-184">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="9383b-185">削除するポリシーごとに、手順1-2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="9383b-185">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="9383b-186">ポリシーの削除が終了したら、変更内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-186">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="9383b-187">これを行うには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-187">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="9383b-188">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="9383b-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="9383b-189">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="9383b-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="9383b-190">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9383b-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="9383b-191">ポリシーアプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="9383b-191">Stop a policy application</span></span>

<span data-ttu-id="9383b-192">情報バリアポリシーの適用を開始した後で、これらのポリシーの適用を停止するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-192">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="9383b-193">プロセスが開始されるまで約30-35 分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9383b-193">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="9383b-194">最新の情報バリアポリシーアプリケーションの状態を表示するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-194">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="9383b-195">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="9383b-195">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="9383b-196">アプリケーションの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="9383b-196">Note the application's GUID.</span></span>

2. <span data-ttu-id="9383b-197">Identity パラメーターを指定して**InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="9383b-197">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="9383b-198">文`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="9383b-198">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="9383b-199">例: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="9383b-199">Example: `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

    <span data-ttu-id="9383b-200">この例では、情報バリアポリシーの適用を停止しています。</span><span class="sxs-lookup"><span data-stu-id="9383b-200">In this example, we are stopping information barrier policies from being applied.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9383b-201">関連記事</span><span class="sxs-lookup"><span data-stu-id="9383b-201">Related articles</span></span>

[<span data-ttu-id="9383b-202">情報障壁の概要を理解する</span><span class="sxs-lookup"><span data-stu-id="9383b-202">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="9383b-203">情報バリアのポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9383b-203">Define policies for information barriers (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="9383b-204">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="9383b-204">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="9383b-205">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9383b-205">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="9383b-206">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="9383b-206">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
