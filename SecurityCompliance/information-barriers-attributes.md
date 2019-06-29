---
title: 情報バリアポリシーの属性
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: この記事は、情報バリアポリシーで使用できるさまざまな属性の参照として使用します。
ms.openlocfilehash: 896b87a3ccc696d3a8193e37237fe555d326ca52
ms.sourcegitcommit: 011bfa60cafdf47900aadf96a17eb275efa877c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394312"
---
# <a name="attributes-for-information-barrier-policies-preview"></a><span data-ttu-id="f4ac8-103">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-103">Attributes for information barrier policies (Preview)</span></span>

<span data-ttu-id="f4ac8-104">Azure Active Directory の特定の属性を使用して、ユーザーをセグメントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="f4ac8-105">セグメントが定義されると、それらのセグメントは情報バリアポリシーのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="f4ac8-106">たとえば、部署を使用し\*\*\*\* て、組織内の部署別のユーザーのセグメントを定義することができます (2 つの部署に対して1人の従業員が同時に働くことは想定されていません)。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="f4ac8-107">この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="f4ac8-108">情報バリアの詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="f4ac8-109">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-109">Information barriers (Preview)</span></span>](information-barriers.md)
- [<span data-ttu-id="f4ac8-110">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-110">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="f4ac8-111">情報バリアポリシーを編集 (または削除) する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-111">Edit (or remove) information barrier policies (Preview)</span></span>](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="f4ac8-112">情報バリアポリシーで属性を使用する方法</span><span class="sxs-lookup"><span data-stu-id="f4ac8-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="f4ac8-113">この記事に記載されている属性は、ユーザーのセグメントを定義または編集するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="f4ac8-114">定義済みのセグメントは、[情報バリアポリシー](information-barriers-policies.md)でパラメーター ( *usergroupfilter*値と呼ばれる) として機能します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="f4ac8-115">セグメントを定義するために使用する属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="f4ac8-116">(この記事の[参照](#reference)セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="f4ac8-117">手順1で選択した属性に対して、ユーザーアカウントに値が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="f4ac8-118">ユーザーアカウントの詳細を表示し、必要に応じて、属性値を含めるようにユーザーアカウントを編集します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    <span data-ttu-id="f4ac8-119">PowerShell を使用してこれを行うには、「 [Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-119">To do this using PowerShell, see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

    <span data-ttu-id="f4ac8-120">Azure Active Directory でこれを行うには、「 [Azure Active directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-120">To do this in Azure Active Directory, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="f4ac8-121">次の例に示すように、 [PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="f4ac8-122">例</span><span class="sxs-lookup"><span data-stu-id="f4ac8-122">Example</span></span>  |<span data-ttu-id="f4ac8-123">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="f4ac8-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="f4ac8-124">Department 属性を使用して、Segment1 というセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="f4ac8-125">MemberOf 属性を使用して SegmentA と呼ばれるセグメントを定義します (この属性には "BlueGroup" などのグループ名が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="f4ac8-126">ExtensionAttribute1 を使用して、DayTraders という名前のセグメントを定義します (この属性には "Daytraders" のような役職が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="f4ac8-127">セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="f4ac8-128">たとえば、*部門*を使用してセグメントを定義する場合、 *department*を使用してすべてのセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="f4ac8-129">*部署*を使用したセグメントと、 *MemberOf*を使用しているセグメントを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="f4ac8-130">セグメントが重ならないようにします。各ユーザーは、1つのセグメントにのみ割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="f4ac8-131">リファレンス</span><span class="sxs-lookup"><span data-stu-id="f4ac8-131">Reference</span></span>

<span data-ttu-id="f4ac8-132">次の表に、情報バリアで使用できる属性を示します。</span><span class="sxs-lookup"><span data-stu-id="f4ac8-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="f4ac8-133">Azure Active Directory のプロパティ名 (LDAP 表示名)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-133">Azure Active Directory property name (LDAP display name)</span></span>  |<span data-ttu-id="f4ac8-134">Exchange のプロパティ名</span><span class="sxs-lookup"><span data-stu-id="f4ac8-134">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="f4ac8-135">産品</span><span class="sxs-lookup"><span data-stu-id="f4ac8-135">Co</span></span>       | <span data-ttu-id="f4ac8-136">産品</span><span class="sxs-lookup"><span data-stu-id="f4ac8-136">Co</span></span>        |
|<span data-ttu-id="f4ac8-137">Company</span><span class="sxs-lookup"><span data-stu-id="f4ac8-137">Company</span></span>     |<span data-ttu-id="f4ac8-138">Company</span><span class="sxs-lookup"><span data-stu-id="f4ac8-138">Company</span></span>         |
|<span data-ttu-id="f4ac8-139">Department</span><span class="sxs-lookup"><span data-stu-id="f4ac8-139">Department</span></span>     |<span data-ttu-id="f4ac8-140">Department</span><span class="sxs-lookup"><span data-stu-id="f4ac8-140">Department</span></span>         |
|<span data-ttu-id="f4ac8-141">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="f4ac8-141">ExtensionAttribute1</span></span> |<span data-ttu-id="f4ac8-142">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="f4ac8-142">CustomAttribute1</span></span>  |
|<span data-ttu-id="f4ac8-143">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="f4ac8-143">ExtensionAttribute2</span></span> |<span data-ttu-id="f4ac8-144">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="f4ac8-144">CustomAttribute2</span></span>  |
|<span data-ttu-id="f4ac8-145">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="f4ac8-145">ExtensionAttribute3</span></span> |<span data-ttu-id="f4ac8-146">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="f4ac8-146">CustomAttribute3</span></span>  |
|<span data-ttu-id="f4ac8-147">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="f4ac8-147">ExtensionAttribute4</span></span> |<span data-ttu-id="f4ac8-148">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="f4ac8-148">CustomAttribute4</span></span>  |
|<span data-ttu-id="f4ac8-149">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="f4ac8-149">ExtensionAttribute5</span></span> |<span data-ttu-id="f4ac8-150">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="f4ac8-150">CustomAttribute5</span></span>  |
|<span data-ttu-id="f4ac8-151">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="f4ac8-151">ExtensionAttribute6</span></span> |<span data-ttu-id="f4ac8-152">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="f4ac8-152">CustomAttribute6</span></span>  |
|<span data-ttu-id="f4ac8-153">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="f4ac8-153">ExtensionAttribute7</span></span> |<span data-ttu-id="f4ac8-154">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="f4ac8-154">CustomAttribute7</span></span>  |
|<span data-ttu-id="f4ac8-155">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="f4ac8-155">ExtensionAttribute8</span></span> |<span data-ttu-id="f4ac8-156">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="f4ac8-156">CustomAttribute8</span></span>  |
|<span data-ttu-id="f4ac8-157">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="f4ac8-157">ExtensionAttribute9</span></span> |<span data-ttu-id="f4ac8-158">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="f4ac8-158">CustomAttribute9</span></span>  |
|<span data-ttu-id="f4ac8-159">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="f4ac8-159">ExtensionAttribute10</span></span> |<span data-ttu-id="f4ac8-160">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="f4ac8-160">CustomAttribute10</span></span>  |
|<span data-ttu-id="f4ac8-161">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="f4ac8-161">ExtensionAttribute11</span></span> |<span data-ttu-id="f4ac8-162">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="f4ac8-162">CustomAttribute11</span></span>  |
|<span data-ttu-id="f4ac8-163">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="f4ac8-163">ExtensionAttribute12</span></span> |<span data-ttu-id="f4ac8-164">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="f4ac8-164">CustomAttribute12</span></span>  |
|<span data-ttu-id="f4ac8-165">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="f4ac8-165">ExtensionAttribute13</span></span> |<span data-ttu-id="f4ac8-166">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="f4ac8-166">CustomAttribute13</span></span>  |
|<span data-ttu-id="f4ac8-167">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="f4ac8-167">ExtensionAttribute14</span></span> |<span data-ttu-id="f4ac8-168">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="f4ac8-168">CustomAttribute14</span></span>  |
|<span data-ttu-id="f4ac8-169">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="f4ac8-169">ExtensionAttribute15</span></span> |<span data-ttu-id="f4ac8-170">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="f4ac8-170">CustomAttribute15</span></span>  |
|<span data-ttu-id="f4ac8-171">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="f4ac8-171">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="f4ac8-172">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="f4ac8-172">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="f4ac8-173">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="f4ac8-173">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="f4ac8-174">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="f4ac8-174">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="f4ac8-175">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="f4ac8-175">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="f4ac8-176">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="f4ac8-176">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="f4ac8-177">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="f4ac8-177">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="f4ac8-178">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="f4ac8-178">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="f4ac8-179">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="f4ac8-179">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="f4ac8-180">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="f4ac8-180">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="f4ac8-181">MailNickname</span><span class="sxs-lookup"><span data-stu-id="f4ac8-181">MailNickname</span></span> |<span data-ttu-id="f4ac8-182">エイリアス</span><span class="sxs-lookup"><span data-stu-id="f4ac8-182">Alias</span></span> |
|<span data-ttu-id="f4ac8-183">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="f4ac8-183">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="f4ac8-184">Office</span><span class="sxs-lookup"><span data-stu-id="f4ac8-184">Office</span></span> |
|<span data-ttu-id="f4ac8-185">郵便</span><span class="sxs-lookup"><span data-stu-id="f4ac8-185">PostalCode</span></span> |<span data-ttu-id="f4ac8-186">郵便</span><span class="sxs-lookup"><span data-stu-id="f4ac8-186">PostalCode</span></span> |
|<span data-ttu-id="f4ac8-187">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f4ac8-187">ProxyAddresses</span></span> |<span data-ttu-id="f4ac8-188">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="f4ac8-188">EmailAddresses</span></span> |
|<span data-ttu-id="f4ac8-189">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="f4ac8-189">StreetAddress</span></span> |<span data-ttu-id="f4ac8-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="f4ac8-190">StreetAddress</span></span> |
|<span data-ttu-id="f4ac8-191">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="f4ac8-191">TargetAddress</span></span> |<span data-ttu-id="f4ac8-192">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="f4ac8-192">ExternalEmailAddress</span></span> |
|<span data-ttu-id="f4ac8-193">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="f4ac8-193">UsageLocation</span></span> |<span data-ttu-id="f4ac8-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="f4ac8-194">UsageLocation</span></span> |
|<span data-ttu-id="f4ac8-195">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f4ac8-195">UserPrincipalName</span></span>  |<span data-ttu-id="f4ac8-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="f4ac8-196">UserPrincipalName</span></span>  |
|<span data-ttu-id="f4ac8-197">メール</span><span class="sxs-lookup"><span data-stu-id="f4ac8-197">Mail</span></span>   |<span data-ttu-id="f4ac8-198">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="f4ac8-198">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="f4ac8-199">説明</span><span class="sxs-lookup"><span data-stu-id="f4ac8-199">Description</span></span>    |<span data-ttu-id="f4ac8-200">説明</span><span class="sxs-lookup"><span data-stu-id="f4ac8-200">Description</span></span>    |
|<span data-ttu-id="f4ac8-201">所属</span><span class="sxs-lookup"><span data-stu-id="f4ac8-201">MemberOf</span></span>   |<span data-ttu-id="f4ac8-202">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="f4ac8-202">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="f4ac8-203">関連項目</span><span class="sxs-lookup"><span data-stu-id="f4ac8-203">Related topics</span></span>

[<span data-ttu-id="f4ac8-204">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-204">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="f4ac8-205">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-205">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="f4ac8-206">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="f4ac8-206">Information barriers (Preview)</span></span>](information-barriers.md)



