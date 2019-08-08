---
title: 情報バリアポリシーの編集
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 情報バリアのポリシーを編集または削除する方法について説明します。
ms.openlocfilehash: 20a1dd62fa80469a7a31db9b5541064ae16b4e02
ms.sourcegitcommit: 7a0cb7e1da39fc485fc29e7325b843d16b9808af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36230591"
---
# <a name="edit-or-remove-information-barrier-policies"></a><span data-ttu-id="18679-103">情報バリアポリシーの編集 (または削除)</span><span class="sxs-lookup"><span data-stu-id="18679-103">Edit (or remove) information barrier policies</span></span>

<span data-ttu-id="18679-104">[情報バリアポリシーを定義](information-barriers-policies.md)した後、[トラブルシューティング](information-barriers-troubleshooting.md)の一環として、または定期的な保守の一環として、これらのポリシーまたはユーザーセグメントに変更を加える必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="18679-104">After you have [defined information barrier policies](information-barriers-policies.md), you might need to make changes to those policies or to your user segments, as part of [troubleshooting](information-barriers-troubleshooting.md) or as regular maintenance.</span></span> <span data-ttu-id="18679-105">この記事をガイドとして使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-105">Use this article as a guide.</span></span>

## <a name="what-do-you-want-to-do"></a><span data-ttu-id="18679-106">目的に合ったトピックをクリックしてください</span><span class="sxs-lookup"><span data-stu-id="18679-106">What do you want to do?</span></span>

|<span data-ttu-id="18679-107">アクション</span><span class="sxs-lookup"><span data-stu-id="18679-107">Action</span></span>  |<span data-ttu-id="18679-108">説明</span><span class="sxs-lookup"><span data-stu-id="18679-108">Description</span></span> |
|---------|---------|
|[<span data-ttu-id="18679-109">ユーザーアカウントの属性を編集する</span><span class="sxs-lookup"><span data-stu-id="18679-109">Edit user account attributes</span></span>](#edit-user-account-attributes)     |<span data-ttu-id="18679-110">セグメントを定義するために使用できる Azure Active Directory の属性を入力します。</span><span class="sxs-lookup"><span data-stu-id="18679-110">Fill in attributes in Azure Active Directory that can be used to define segments.</span></span><br/><span data-ttu-id="18679-111">ユーザーアカウントの属性を編集して、ユーザーがセグメントに含まれていない場合、ユーザーが所属するセグメントを変更したり、異なる属性を使用してセグメントを定義したりする場合。</span><span class="sxs-lookup"><span data-stu-id="18679-111">Edit user account attributes when users are not included in segments they should be, to change which segments users are in, or to define segments using different attributes.</span></span>         |
|[<span data-ttu-id="18679-112">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="18679-112">Edit a segment</span></span>](#edit-a-segment)     |<span data-ttu-id="18679-113">セグメントの定義方法を変更する場合は、セグメントを編集します。</span><span class="sxs-lookup"><span data-stu-id="18679-113">Edit segments when you want to change how a segment is defined.</span></span> <br/><span data-ttu-id="18679-114">たとえば、最初に*Department*を使用してセグメントを定義していて、その他の属性 ( *MemberOf*など) を使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="18679-114">For example, you might have originally defined segments using *Department* and now want to use another attribute, such as *MemberOf*.</span></span>         |
|[<span data-ttu-id="18679-115">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="18679-115">Edit a policy</span></span>](#edit-a-policy)     |<span data-ttu-id="18679-116">ポリシーの動作を変更する場合は、情報バリアポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="18679-116">Edit an information barrier policy when you want to change how a policy works.</span></span><br/><span data-ttu-id="18679-117">たとえば、2つのセグメント間の通信をブロックするのではなく、特定のセグメント間でのみ通信が行われるようにすることを決定する場合があります。</span><span class="sxs-lookup"><span data-stu-id="18679-117">For example, instead of blocking communications between two segments, you might decide you want to allow communications to occur only between certain segments.</span></span>         |
|[<span data-ttu-id="18679-118">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="18679-118">Set a policy to inactive status</span></span>](#set-a-policy-to-inactive-status)     |<span data-ttu-id="18679-119">ポリシーを変更する場合、またはポリシーを有効にしない場合は、ポリシーを非アクティブ状態に設定します。</span><span class="sxs-lookup"><span data-stu-id="18679-119">Set a policy to inactive status when you want to make changes to a policy, or when you don't want a policy to be in effect.</span></span>         |
|[<span data-ttu-id="18679-120">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="18679-120">Remove a policy</span></span>](#remove-a-policy)     |<span data-ttu-id="18679-121">特定のポリシーが不要になった場合に、情報バリアポリシーを削除します。</span><span class="sxs-lookup"><span data-stu-id="18679-121">Remove an information barrier policy when you no longer need a particular policy in place.</span></span>         |
|[<span data-ttu-id="18679-122">ポリシーアプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="18679-122">Stop a policy application</span></span>](#stop-a-policy-application)     |<span data-ttu-id="18679-123">情報バリアポリシーの適用プロセスを停止する場合は、この手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="18679-123">Do this when you want to stop the process of applying information barrier policies.</span></span><br/><span data-ttu-id="18679-124">ポリシーアプリケーションを停止しても、ユーザーに既に適用されているポリシーは元に戻すことができないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="18679-124">Note that stopping a policy application is not instant, and it does not undo policies that are already applied to users.</span></span>         |
|[<span data-ttu-id="18679-125">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="18679-125">Define policies for information barriers</span></span>](information-barriers-policies.md)     |<span data-ttu-id="18679-126">このようなポリシーがまだ適用されていない場合に情報バリアポリシーを定義します。また、特定のユーザーグループ間の通信を制限または制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18679-126">Define an information barrier policy when you do not already have such policies in place, and you must restrict or limit communications between specific groups of users.</span></span>         |
|[<span data-ttu-id="18679-127">情報の障壁をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="18679-127">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)     |<span data-ttu-id="18679-128">情報バリアを使用して予期しない問題が発生した場合は、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18679-128">Refer to this article when you run into unexpected issues with information barriers.</span></span>         |

> [!IMPORTANT]
> <span data-ttu-id="18679-129">この記事で説明されているタスクを実行するには、次のいずれかのような適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="18679-129">To perform the tasks described in this article, you must be assigned an appropriate role, such as one of the following:</span></span><br/><span data-ttu-id="18679-130">-Microsoft 365 エンタープライズグローバル管理者</span><span class="sxs-lookup"><span data-stu-id="18679-130">- Microsoft 365 Enterprise Global Administrator</span></span><br/><span data-ttu-id="18679-131">-Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="18679-131">- Office 365 Global Administrator</span></span><br/><span data-ttu-id="18679-132">-コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="18679-132">- Compliance Administrator</span></span><br/><span data-ttu-id="18679-133">-IB コンプライアンス管理 (新しい役割)</span><span class="sxs-lookup"><span data-stu-id="18679-133">- IB Compliance Management (this is a new role!)</span></span><p><span data-ttu-id="18679-134">情報障壁の前提条件の詳細については、「[必須コンポーネント (情報バリアポリシー)](information-barriers-policies.md#prerequisites)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18679-134">To learn more about prerequisites for information barriers, see [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).</span></span><p><span data-ttu-id="18679-135">[Office 365 セキュリティ & コンプライアンスセンター PowerShell に接続](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)するようにしてください。</span><span class="sxs-lookup"><span data-stu-id="18679-135">Make sure to [connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

## <a name="edit-user-account-attributes"></a><span data-ttu-id="18679-136">ユーザーアカウントの属性を編集する</span><span class="sxs-lookup"><span data-stu-id="18679-136">Edit user account attributes</span></span>

<span data-ttu-id="18679-137">ユーザーのセグメント化に使用される属性を編集するには、以下の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-137">Use this procedure to edit attributes that are used for segmenting users.</span></span> 

<span data-ttu-id="18679-138">たとえば、Department 属性を使用していて、1つまたは複数のユーザーアカウントで Department の値がリストされていない場合は、それらのユーザーアカウントを編集して部署情報を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="18679-138">For example, if you are using a Department attribute, and one or more user accounts do not currently have any values listed for Department, you must edit those user accounts to include Department information.</span></span> 

<span data-ttu-id="18679-139">ユーザーアカウント属性は、情報バリアポリシーを割り当てることができるように、セグメントを定義するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="18679-139">User account attributes are used for defining segments so that information barrier policies can be assigned.</span></span>

1. <span data-ttu-id="18679-140">属性値、割り当てられたセグメントなど、特定のユーザーアカウントの詳細を表示するには、Identity パラメーターを指定して**InformationBarrierRecipientStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-140">To view details for a specific user account, such as attribute values and assigned segment(s), use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> 

    |<span data-ttu-id="18679-141">構文</span><span class="sxs-lookup"><span data-stu-id="18679-141">Syntax</span></span>  |<span data-ttu-id="18679-142">例</span><span class="sxs-lookup"><span data-stu-id="18679-142">Example</span></span>  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   <span data-ttu-id="18679-143">名前、エイリアス、識別名、標準ドメイン名、電子メールアドレス、GUID など、各ユーザーを一意に識別する任意の値を使用できます。</span><span class="sxs-lookup"><span data-stu-id="18679-143">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p>   <span data-ttu-id="18679-144">(1 人のユーザーに対してこのコマンドレットを`Get-InformationBarrierRecipientStatus -Identity <value>`使用することもできます。)</span><span class="sxs-lookup"><span data-stu-id="18679-144">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span>      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   <span data-ttu-id="18679-145">この例では、Office 365 の2つのユーザーアカウント ( *Megan*の場合は*Meガント b* 、 *Alex*の場合は*alexw* ) を参照しています。</span><span class="sxs-lookup"><span data-stu-id="18679-145">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span>         |

2. <span data-ttu-id="18679-146">ユーザーアカウントプロファイルに対してどの属性を編集するかを決定します。</span><span class="sxs-lookup"><span data-stu-id="18679-146">Determine which attribute you want to edit for your user account profile(s).</span></span> <span data-ttu-id="18679-147">詳細については、「[情報バリアポリシーの属性](information-barriers-attributes.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18679-147">Refer to [Attributes for information barrier policies](information-barriers-attributes.md) for more details.</span></span> 

3. <span data-ttu-id="18679-148">1つ以上のユーザーアカウントを編集して、前の手順で選択した属性の値を含めます。</span><span class="sxs-lookup"><span data-stu-id="18679-148">Edit one or more user accounts to include values for the attribute you selected in the previous step.</span></span> <span data-ttu-id="18679-149">これを行うには、次のいずれかの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-149">To do this, use one of the following procedures:</span></span>

    - <span data-ttu-id="18679-150">単一のアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18679-150">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

    - <span data-ttu-id="18679-151">複数のアカウントを編集する (または PowerShell を使用して1つのアカウントを編集する) には、「 [Office 365 powershell でユーザーアカウントのプロパティを構成](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18679-151">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

## <a name="edit-a-segment"></a><span data-ttu-id="18679-152">セグメントを編集する</span><span class="sxs-lookup"><span data-stu-id="18679-152">Edit a segment</span></span>

<span data-ttu-id="18679-153">この手順を使用して、ユーザーセグメントの定義を編集します。</span><span class="sxs-lookup"><span data-stu-id="18679-153">Use this procedure edit the definition of a user segment.</span></span> <span data-ttu-id="18679-154">たとえば、セグメントの名前を変更したり、セグメントに含まれている人物を特定するために使用するフィルターを変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="18679-154">For example, you might change the name of a segment, or the filter that is used to determine who's included in the segment.</span></span>

1. <span data-ttu-id="18679-155">既存のすべてのセグメントを表示するには、コマンドレットの**取得**を使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-155">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="18679-156">文`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="18679-156">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="18679-157">セグメントの種類、UserGroupFilter 値、作成者または最終更新日時、GUID など、セグメントと詳細の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="18679-157">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="18679-158">後で参照するために、セグメントのリストを印刷または保存します。</span><span class="sxs-lookup"><span data-stu-id="18679-158">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="18679-159">たとえば、セグメントを編集する場合は、その名前を知っているか、値を識別する必要があります (これは Identity パラメーターと共に使用されます)。</span><span class="sxs-lookup"><span data-stu-id="18679-159">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="18679-160">セグメントを編集するには、 **Identity**パラメーターと関連する詳細情報を使用して、**グループ**化コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-160">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    |<span data-ttu-id="18679-161">構文</span><span class="sxs-lookup"><span data-stu-id="18679-161">Syntax</span></span>  |<span data-ttu-id="18679-162">例</span><span class="sxs-lookup"><span data-stu-id="18679-162">Example</span></span>  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p><span data-ttu-id="18679-163">この例では、GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*を持つセグメントに対して、部署名を "hrdept" に更新しました。</span><span class="sxs-lookup"><span data-stu-id="18679-163">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>         |

<span data-ttu-id="18679-164">組織のセグメントの編集が終了したら、情報バリアポリシーの[定義](information-barriers-policies.md#part-2-define-information-barrier-policies)または[編集](#edit-a-policy)を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="18679-164">When you have finished editing segments for your organization, you can either [define](information-barriers-policies.md#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

## <a name="edit-a-policy"></a><span data-ttu-id="18679-165">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="18679-165">Edit a policy</span></span>

1. <span data-ttu-id="18679-166">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-166">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="18679-167">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="18679-167">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="18679-168">結果の一覧で、変更するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="18679-168">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="18679-169">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="18679-169">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="18679-170">**InformationBarrierPolicy**コマンドレットを**Identity**パラメーターと共に使用して、必要な変更を指定します。</span><span class="sxs-lookup"><span data-stu-id="18679-170">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="18679-171">例: ポリシーが定義されていて、*リサーチ*セグメントが*販売*および*マーケティング*セグメントとの通信をブロックするとします。</span><span class="sxs-lookup"><span data-stu-id="18679-171">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="18679-172">このポリシーは、このコマンドレットを使用して定義されています。`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="18679-172">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="18679-173">*研究*セグメント内のユーザーが*HR*セグメント内のユーザーとのみ通信できるように変更するとします。</span><span class="sxs-lookup"><span data-stu-id="18679-173">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="18679-174">この変更を行うには、次のコマンドレットを使用します。`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="18679-174">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="18679-175">この例では、"SegmentsBlocked" を "SegmentsAllowed" に変更し、 *HR*セグメントを指定しました。</span><span class="sxs-lookup"><span data-stu-id="18679-175">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="18679-176">ポリシーの編集が終了したら、変更内容を適用してください。</span><span class="sxs-lookup"><span data-stu-id="18679-176">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="18679-177">([情報バリアポリシーの適用](information-barriers-policies.md#part-3-apply-information-barrier-policies)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="18679-177">(See [Apply information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)</span></span>

## <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="18679-178">ポリシーを非アクティブな状態に設定する</span><span class="sxs-lookup"><span data-stu-id="18679-178">Set a policy to inactive status</span></span>

1. <span data-ttu-id="18679-179">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-179">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="18679-180">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="18679-180">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="18679-181">結果の一覧で、変更する (または削除する) ポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="18679-181">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="18679-182">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="18679-182">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="18679-183">ポリシーの状態を非アクティブに設定するには、Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用し、State パラメーターを inactive に設定します。</span><span class="sxs-lookup"><span data-stu-id="18679-183">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    |<span data-ttu-id="18679-184">構文</span><span class="sxs-lookup"><span data-stu-id="18679-184">Syntax</span></span>  |<span data-ttu-id="18679-185">例</span><span class="sxs-lookup"><span data-stu-id="18679-185">Example</span></span>  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p><span data-ttu-id="18679-186">この例では、GUID *43c37853-ea10-4b90-a23d-ab8c9377247*を非アクティブな状態に設定する情報バリアポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="18679-186">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>         |

3. <span data-ttu-id="18679-187">変更を適用するには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-187">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="18679-188">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="18679-188">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="18679-189">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="18679-189">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="18679-190">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="18679-190">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="18679-191">(一般的なガイドラインとして、5000のユーザーアカウントを処理するのには1時間かかります)。</span><span class="sxs-lookup"><span data-stu-id="18679-191">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="18679-192">この時点で、1つまたは複数の情報バリアポリシーが非アクティブ状態に設定されます。</span><span class="sxs-lookup"><span data-stu-id="18679-192">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="18679-193">ここから、次のいずれかの操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="18679-193">From here, you can do any of the following:</span></span>
- <span data-ttu-id="18679-194">そのまま保持する (非アクティブな状態に設定されたポリシーはユーザーに影響しません)</span><span class="sxs-lookup"><span data-stu-id="18679-194">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="18679-195">ポリシーを編集する</span><span class="sxs-lookup"><span data-stu-id="18679-195">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="18679-196">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="18679-196">Remove a policy</span></span>](#remove-a-policy)

## <a name="remove-a-policy"></a><span data-ttu-id="18679-197">ポリシーを削除する</span><span class="sxs-lookup"><span data-stu-id="18679-197">Remove a policy</span></span>

1. <span data-ttu-id="18679-198">現在の情報バリアポリシーの一覧を表示するには、 **InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-198">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="18679-199">文`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="18679-199">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="18679-200">結果の一覧で、削除するポリシーを特定します。</span><span class="sxs-lookup"><span data-stu-id="18679-200">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="18679-201">ポリシーの GUID と名前をメモします。</span><span class="sxs-lookup"><span data-stu-id="18679-201">Note the policy's GUID and name.</span></span> <span data-ttu-id="18679-202">ポリシーが非アクティブの状態に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="18679-202">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="18679-203">Identity パラメーターを指定して**InformationBarrierPolicy**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-203">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="18679-204">構文</span><span class="sxs-lookup"><span data-stu-id="18679-204">Syntax</span></span>  |<span data-ttu-id="18679-205">例</span><span class="sxs-lookup"><span data-stu-id="18679-205">Example</span></span>  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p><span data-ttu-id="18679-206">この例では、GUID が*43c37853-ea10-4b90-a23d-ab8c93772471*のポリシーを削除しています。</span><span class="sxs-lookup"><span data-stu-id="18679-206">In this example, we are removing the policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span>          |

    <span data-ttu-id="18679-207">メッセージが表示されたら、変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="18679-207">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="18679-208">削除するポリシーごとに、手順1-2 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="18679-208">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="18679-209">ポリシーの削除が終了したら、変更内容を適用します。</span><span class="sxs-lookup"><span data-stu-id="18679-209">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="18679-210">これを行うには、 **InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-210">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="18679-211">文`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="18679-211">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="18679-212">組織の変更がユーザーごとに適用されます。</span><span class="sxs-lookup"><span data-stu-id="18679-212">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="18679-213">組織の規模が大きい場合、このプロセスが完了するまでに24時間以上かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="18679-213">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

## <a name="stop-a-policy-application"></a><span data-ttu-id="18679-214">ポリシーアプリケーションを停止する</span><span class="sxs-lookup"><span data-stu-id="18679-214">Stop a policy application</span></span>

<span data-ttu-id="18679-215">情報バリアポリシーの適用を開始した後で、これらのポリシーの適用を停止するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-215">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="18679-216">プロセスが開始されるまで約30-35 分かかることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="18679-216">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="18679-217">最新の情報バリアポリシーアプリケーションの状態を表示するには、 **InformationBarrierPoliciesApplicationStatus**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-217">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="18679-218">文`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="18679-218">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="18679-219">アプリケーションの GUID をメモします。</span><span class="sxs-lookup"><span data-stu-id="18679-219">Note the application's GUID.</span></span>

2. <span data-ttu-id="18679-220">Identity パラメーターを指定して**InformationBarrierPoliciesApplication**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="18679-220">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    |<span data-ttu-id="18679-221">構文</span><span class="sxs-lookup"><span data-stu-id="18679-221">Syntax</span></span>  |<span data-ttu-id="18679-222">例</span><span class="sxs-lookup"><span data-stu-id="18679-222">Example</span></span>  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p><span data-ttu-id="18679-223">この例では、情報バリアポリシーの適用を停止しています。</span><span class="sxs-lookup"><span data-stu-id="18679-223">In this example, we are stopping information barrier policies from being applied.</span></span>         |

## <a name="related-articles"></a><span data-ttu-id="18679-224">関連記事</span><span class="sxs-lookup"><span data-stu-id="18679-224">Related articles</span></span>

[<span data-ttu-id="18679-225">情報障壁の概要を理解する</span><span class="sxs-lookup"><span data-stu-id="18679-225">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="18679-226">情報バリアのポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="18679-226">Define policies for information barriers</span></span>](information-barriers-policies.md)

[<span data-ttu-id="18679-227">Microsoft Teams の情報障壁の詳細を知る</span><span class="sxs-lookup"><span data-stu-id="18679-227">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="18679-228">情報バリアポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="18679-228">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="18679-229">情報の障壁をトラブルシューティングする</span><span class="sxs-lookup"><span data-stu-id="18679-229">Troubleshooting information barriers</span></span>](information-barriers-troubleshooting.md)
