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
ms.openlocfilehash: 1537dae2c99555a9257bbe5c3f9754a1f975fbbe
ms.sourcegitcommit: 8f399f260687d17a497a15bcc644187c277ea8fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/03/2019
ms.locfileid: "35462408"
---
# <a name="attributes-for-information-barrier-policies-preview"></a><span data-ttu-id="7fff2-103">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-103">Attributes for information barrier policies (Preview)</span></span>

<span data-ttu-id="7fff2-104">Azure Active Directory の特定の属性を使用して、ユーザーをセグメントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="7fff2-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="7fff2-105">セグメントが定義されると、それらのセグメントは情報バリアポリシーのフィルターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fff2-105">Once segments are defined, those segments can be used as filters for information barrier policies.</span></span> <span data-ttu-id="7fff2-106">たとえば、部署を使用し\*\*\*\* て、組織内の部署別のユーザーのセグメントを定義することができます (2 つの部署に対して1人の従業員が同時に働くことは想定されていません)。</span><span class="sxs-lookup"><span data-stu-id="7fff2-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="7fff2-107">この記事では、情報バリアで属性を使用する方法について説明し、使用できる属性の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-107">This article describes how to use attributes with information barriers, and it provides a list of attributes that can be used.</span></span> <span data-ttu-id="7fff2-108">情報バリアの詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fff2-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="7fff2-109">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-109">Information barriers (Preview)</span></span>](information-barriers.md)
- [<span data-ttu-id="7fff2-110">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-110">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)
- [<span data-ttu-id="7fff2-111">情報バリアポリシーを編集 (または削除) する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-111">Edit (or remove) information barrier policies (Preview)</span></span>](information-barriers-edit-segments-policies.md.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="7fff2-112">情報バリアポリシーで属性を使用する方法</span><span class="sxs-lookup"><span data-stu-id="7fff2-112">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="7fff2-113">この記事に記載されている属性は、ユーザーのセグメントを定義または編集するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="7fff2-113">The attributes listed in this article can be used to define or edit segments of users.</span></span> <span data-ttu-id="7fff2-114">定義済みのセグメントは、[情報バリアポリシー](information-barriers-policies.md)でパラメーター ( *usergroupfilter*値と呼ばれる) として機能します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-114">Your defined segments serve as parameters (called *UserGroupFilter* values) in [information barrier policies](information-barriers-policies.md).</span></span>

1. <span data-ttu-id="7fff2-115">セグメントを定義するために使用する属性を決定します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-115">Determine which attribute you want to use to define segments.</span></span> <span data-ttu-id="7fff2-116">(この記事の[参照](#reference)セクションを参照してください)。</span><span class="sxs-lookup"><span data-stu-id="7fff2-116">(See the [Reference](#reference) section in this article.)</span></span>

2. <span data-ttu-id="7fff2-117">手順1で選択した属性に対して、ユーザーアカウントに値が入力されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-117">Make sure the user accounts have values filled in for the attribute(s) you selected in Step 1.</span></span> <span data-ttu-id="7fff2-118">ユーザーアカウントの詳細を表示し、必要に応じて、属性値を含めるようにユーザーアカウントを編集します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-118">View user account details, and if necessary, edit user accounts to include attribute values.</span></span> 

    - <span data-ttu-id="7fff2-119">複数のアカウントを編集する (または PowerShell を使用して1つのアカウントを編集する) には、「 [Office 365 powershell でユーザーアカウントのプロパティを構成](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fff2-119">To edit multiple accounts (or use PowerShell to edit a single account), see [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).</span></span>

    - <span data-ttu-id="7fff2-120">単一のアカウントを編集するには、「 [Azure Active Directory を使用してユーザーのプロファイル情報を追加または更新](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7fff2-120">To edit a single account, see [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

3. <span data-ttu-id="7fff2-121">次の例に示すように、 [PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-121">[Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell), similar to the following examples:</span></span>

    |<span data-ttu-id="7fff2-122">例</span><span class="sxs-lookup"><span data-stu-id="7fff2-122">Example</span></span>  |<span data-ttu-id="7fff2-123">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="7fff2-123">Cmdlet</span></span>  |
    |---------|---------|
    |<span data-ttu-id="7fff2-124">Department 属性を使用して、Segment1 というセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-124">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |<span data-ttu-id="7fff2-125">MemberOf 属性を使用して SegmentA と呼ばれるセグメントを定義します (この属性には "BlueGroup" などのグループ名が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="7fff2-125">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |<span data-ttu-id="7fff2-126">ExtensionAttribute1 を使用して、DayTraders という名前のセグメントを定義します (この属性には "Daytraders" のような役職が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="7fff2-126">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > <span data-ttu-id="7fff2-127">セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-127">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="7fff2-128">たとえば、*部門*を使用してセグメントを定義する場合、 *department*を使用してすべてのセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-128">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="7fff2-129">*部署*を使用したセグメントと、 *MemberOf*を使用しているセグメントを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="7fff2-129">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="7fff2-130">セグメントが重ならないようにします。各ユーザーは、1つのセグメントにのみ割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="7fff2-130">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

## <a name="reference"></a><span data-ttu-id="7fff2-131">リファレンス</span><span class="sxs-lookup"><span data-stu-id="7fff2-131">Reference</span></span>

<span data-ttu-id="7fff2-132">次の表に、情報バリアで使用できる属性を示します。</span><span class="sxs-lookup"><span data-stu-id="7fff2-132">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="7fff2-133">Azure Active Directory のプロパティ名</span><span class="sxs-lookup"><span data-stu-id="7fff2-133">Azure Active Directory property name</span></span><br/><span data-ttu-id="7fff2-134">(LDAP 表示名)</span><span class="sxs-lookup"><span data-stu-id="7fff2-134">(LDAP display name)</span></span>  |<span data-ttu-id="7fff2-135">Exchange のプロパティ名</span><span class="sxs-lookup"><span data-stu-id="7fff2-135">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="7fff2-136">産品</span><span class="sxs-lookup"><span data-stu-id="7fff2-136">Co</span></span>       | <span data-ttu-id="7fff2-137">産品</span><span class="sxs-lookup"><span data-stu-id="7fff2-137">Co</span></span>        |
|<span data-ttu-id="7fff2-138">Company</span><span class="sxs-lookup"><span data-stu-id="7fff2-138">Company</span></span>     |<span data-ttu-id="7fff2-139">Company</span><span class="sxs-lookup"><span data-stu-id="7fff2-139">Company</span></span>         |
|<span data-ttu-id="7fff2-140">Department</span><span class="sxs-lookup"><span data-stu-id="7fff2-140">Department</span></span>     |<span data-ttu-id="7fff2-141">Department</span><span class="sxs-lookup"><span data-stu-id="7fff2-141">Department</span></span>         |
|<span data-ttu-id="7fff2-142">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="7fff2-142">ExtensionAttribute1</span></span> |<span data-ttu-id="7fff2-143">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7fff2-143">CustomAttribute1</span></span>  |
|<span data-ttu-id="7fff2-144">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="7fff2-144">ExtensionAttribute2</span></span> |<span data-ttu-id="7fff2-145">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7fff2-145">CustomAttribute2</span></span>  |
|<span data-ttu-id="7fff2-146">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="7fff2-146">ExtensionAttribute3</span></span> |<span data-ttu-id="7fff2-147">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7fff2-147">CustomAttribute3</span></span>  |
|<span data-ttu-id="7fff2-148">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="7fff2-148">ExtensionAttribute4</span></span> |<span data-ttu-id="7fff2-149">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7fff2-149">CustomAttribute4</span></span>  |
|<span data-ttu-id="7fff2-150">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="7fff2-150">ExtensionAttribute5</span></span> |<span data-ttu-id="7fff2-151">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7fff2-151">CustomAttribute5</span></span>  |
|<span data-ttu-id="7fff2-152">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="7fff2-152">ExtensionAttribute6</span></span> |<span data-ttu-id="7fff2-153">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="7fff2-153">CustomAttribute6</span></span>  |
|<span data-ttu-id="7fff2-154">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="7fff2-154">ExtensionAttribute7</span></span> |<span data-ttu-id="7fff2-155">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="7fff2-155">CustomAttribute7</span></span>  |
|<span data-ttu-id="7fff2-156">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="7fff2-156">ExtensionAttribute8</span></span> |<span data-ttu-id="7fff2-157">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="7fff2-157">CustomAttribute8</span></span>  |
|<span data-ttu-id="7fff2-158">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="7fff2-158">ExtensionAttribute9</span></span> |<span data-ttu-id="7fff2-159">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="7fff2-159">CustomAttribute9</span></span>  |
|<span data-ttu-id="7fff2-160">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="7fff2-160">ExtensionAttribute10</span></span> |<span data-ttu-id="7fff2-161">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="7fff2-161">CustomAttribute10</span></span>  |
|<span data-ttu-id="7fff2-162">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="7fff2-162">ExtensionAttribute11</span></span> |<span data-ttu-id="7fff2-163">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="7fff2-163">CustomAttribute11</span></span>  |
|<span data-ttu-id="7fff2-164">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="7fff2-164">ExtensionAttribute12</span></span> |<span data-ttu-id="7fff2-165">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="7fff2-165">CustomAttribute12</span></span>  |
|<span data-ttu-id="7fff2-166">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="7fff2-166">ExtensionAttribute13</span></span> |<span data-ttu-id="7fff2-167">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="7fff2-167">CustomAttribute13</span></span>  |
|<span data-ttu-id="7fff2-168">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="7fff2-168">ExtensionAttribute14</span></span> |<span data-ttu-id="7fff2-169">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="7fff2-169">CustomAttribute14</span></span>  |
|<span data-ttu-id="7fff2-170">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="7fff2-170">ExtensionAttribute15</span></span> |<span data-ttu-id="7fff2-171">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="7fff2-171">CustomAttribute15</span></span>  |
|<span data-ttu-id="7fff2-172">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7fff2-172">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="7fff2-173">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="7fff2-173">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="7fff2-174">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7fff2-174">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="7fff2-175">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="7fff2-175">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="7fff2-176">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7fff2-176">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="7fff2-177">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="7fff2-177">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="7fff2-178">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7fff2-178">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="7fff2-179">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="7fff2-179">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="7fff2-180">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7fff2-180">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="7fff2-181">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="7fff2-181">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="7fff2-182">MailNickname</span><span class="sxs-lookup"><span data-stu-id="7fff2-182">MailNickname</span></span> |<span data-ttu-id="7fff2-183">エイリアス</span><span class="sxs-lookup"><span data-stu-id="7fff2-183">Alias</span></span> |
|<span data-ttu-id="7fff2-184">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="7fff2-184">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="7fff2-185">Office</span><span class="sxs-lookup"><span data-stu-id="7fff2-185">Office</span></span> |
|<span data-ttu-id="7fff2-186">郵便</span><span class="sxs-lookup"><span data-stu-id="7fff2-186">PostalCode</span></span> |<span data-ttu-id="7fff2-187">郵便</span><span class="sxs-lookup"><span data-stu-id="7fff2-187">PostalCode</span></span> |
|<span data-ttu-id="7fff2-188">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="7fff2-188">ProxyAddresses</span></span> |<span data-ttu-id="7fff2-189">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="7fff2-189">EmailAddresses</span></span> |
|<span data-ttu-id="7fff2-190">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="7fff2-190">StreetAddress</span></span> |<span data-ttu-id="7fff2-191">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="7fff2-191">StreetAddress</span></span> |
|<span data-ttu-id="7fff2-192">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="7fff2-192">TargetAddress</span></span> |<span data-ttu-id="7fff2-193">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="7fff2-193">ExternalEmailAddress</span></span> |
|<span data-ttu-id="7fff2-194">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="7fff2-194">UsageLocation</span></span> |<span data-ttu-id="7fff2-195">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="7fff2-195">UsageLocation</span></span> |
|<span data-ttu-id="7fff2-196">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7fff2-196">UserPrincipalName</span></span>  |<span data-ttu-id="7fff2-197">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7fff2-197">UserPrincipalName</span></span>  |
|<span data-ttu-id="7fff2-198">メール</span><span class="sxs-lookup"><span data-stu-id="7fff2-198">Mail</span></span>   |<span data-ttu-id="7fff2-199">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="7fff2-199">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="7fff2-200">説明</span><span class="sxs-lookup"><span data-stu-id="7fff2-200">Description</span></span>    |<span data-ttu-id="7fff2-201">説明</span><span class="sxs-lookup"><span data-stu-id="7fff2-201">Description</span></span>    |
|<span data-ttu-id="7fff2-202">所属</span><span class="sxs-lookup"><span data-stu-id="7fff2-202">MemberOf</span></span>   |<span data-ttu-id="7fff2-203">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="7fff2-203">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="7fff2-204">関連項目</span><span class="sxs-lookup"><span data-stu-id="7fff2-204">Related topics</span></span>

[<span data-ttu-id="7fff2-205">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-205">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="7fff2-206">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-206">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="7fff2-207">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="7fff2-207">Information barriers (Preview)</span></span>](information-barriers.md)



