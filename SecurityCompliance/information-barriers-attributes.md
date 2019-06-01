---
title: 情報バリアポリシーの属性
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
description: この記事は、情報バリアポリシーで使用できるさまざまな属性の参照として使用します。
ms.openlocfilehash: e72e37950442974897de479c7c11f0053a578d1c
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668320"
---
# <a name="attributes-for-information-barrier-policies-preview"></a><span data-ttu-id="06827-103">情報バリアポリシーの属性 (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="06827-103">Attributes for information barrier policies (Preview)</span></span>

<span data-ttu-id="06827-104">Azure Active Directory の特定の属性を使用して、ユーザーをセグメントにすることができます。</span><span class="sxs-lookup"><span data-stu-id="06827-104">Certain attributes in Azure Active Directory can be used to segment users.</span></span> <span data-ttu-id="06827-105">次に、セグメントが情報バリアポリシーのフィルターとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="06827-105">Segments are then used as filters for information barrier policies.</span></span> <span data-ttu-id="06827-106">たとえば、部署を使用し\*\*\*\* て、組織内の部署別のユーザーのセグメントを定義することができます (2 つの部署に対して1人の従業員が同時に働くことは想定されていません)。</span><span class="sxs-lookup"><span data-stu-id="06827-106">For example, you might use **Department** to define segments of users by department within your organization (assuming no single employee works for two departments at the same time).</span></span> 

<span data-ttu-id="06827-107">この記事では、使用可能な属性の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="06827-107">This article provides a list of attributes that can be used.</span></span> <span data-ttu-id="06827-108">情報バリアの詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="06827-108">To learn more about information barriers, see the following resources:</span></span>
- [<span data-ttu-id="06827-109">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="06827-109">Information barriers (Preview)</span></span>](information-barriers.md)
- [<span data-ttu-id="06827-110">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="06827-110">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a><span data-ttu-id="06827-111">情報バリアポリシーで属性を使用する方法</span><span class="sxs-lookup"><span data-stu-id="06827-111">How to use attributes in information barrier policies</span></span>

<span data-ttu-id="06827-112">この記事に記載されている属性を使用して、ユーザーのセグメントを定義 (または編集) することができます。</span><span class="sxs-lookup"><span data-stu-id="06827-112">The attributes listed in this article can be used to define (or edit) segments of users.</span></span> <span data-ttu-id="06827-113">次の例に示すように、セグメントは情報バリアポリシーでパラメーター (UserGroupFilter) として使用されます。</span><span class="sxs-lookup"><span data-stu-id="06827-113">Segments are used as parameters (UserGroupFilter) in information barrier policies, as shown in the following examples:</span></span>

|<span data-ttu-id="06827-114">例</span><span class="sxs-lookup"><span data-stu-id="06827-114">Example</span></span>  |<span data-ttu-id="06827-115">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="06827-115">Cmdlet</span></span>  |
|---------|---------|
|<span data-ttu-id="06827-116">Department 属性を使用して、Segment1 というセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="06827-116">Define a segment called Segment1 using the Department attribute</span></span>     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
|<span data-ttu-id="06827-117">MemberOf 属性を使用して SegmentA と呼ばれるセグメントを定義します (この属性には "BlueGroup" などのグループ名が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="06827-117">Define a segment called SegmentA using the MemberOf attribute (suppose this attribute contains group names, such as "BlueGroup")</span></span>     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
|<span data-ttu-id="06827-118">ExtensionAttribute1 を使用して、DayTraders という名前のセグメントを定義します (この属性には "Daytraders" のような役職が含まれているとします)。</span><span class="sxs-lookup"><span data-stu-id="06827-118">Define a segment called DayTraders using ExtensionAttribute1 (suppose this attribute contains job titles, such as "DayTrader")</span></span>|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

<span data-ttu-id="06827-119">セグメントを定義するときは、すべてのセグメントに同じ属性を使用します。</span><span class="sxs-lookup"><span data-stu-id="06827-119">When you define segments, use the same attribute for all your segments.</span></span> <span data-ttu-id="06827-120">たとえば、*部門*を使用してセグメントを定義する場合、 *department*を使用してすべてのセグメントを定義します。</span><span class="sxs-lookup"><span data-stu-id="06827-120">For example, if you define some segments using *Department*, define all of the segments using *Department*.</span></span> <span data-ttu-id="06827-121">*部署*を使用したセグメントと、 *MemberOf*を使用しているセグメントを定義しないでください。</span><span class="sxs-lookup"><span data-stu-id="06827-121">Don't define some segments using *Department* and others using *MemberOf*.</span></span> <span data-ttu-id="06827-122">セグメントが重ならないようにします。各ユーザーは、1つのセグメントにのみ割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="06827-122">Make sure your segments do not overlap; each user should be assigned to exactly one segment.</span></span> 

<span data-ttu-id="06827-123">詳細については、「 [PowerShell を使用してセグメントを定義](information-barriers-policies.md#define-segments-using-powershell)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06827-123">To learn more, see [Define segments using PowerShell](information-barriers-policies.md#define-segments-using-powershell).</span></span>

## <a name="reference"></a><span data-ttu-id="06827-124">リファレンス</span><span class="sxs-lookup"><span data-stu-id="06827-124">Reference</span></span>

<span data-ttu-id="06827-125">次の表に、情報バリアで使用できる属性を示します。</span><span class="sxs-lookup"><span data-stu-id="06827-125">The following table lists the attributes that you can use with information barriers.</span></span>

|<span data-ttu-id="06827-126">Azure Active Directory のプロパティ名 (LDAP 表示名)</span><span class="sxs-lookup"><span data-stu-id="06827-126">Azure Active Directory property name (LDAP display name)</span></span>  |<span data-ttu-id="06827-127">Exchange のプロパティ名</span><span class="sxs-lookup"><span data-stu-id="06827-127">Exchange property name</span></span>  |
|---------|---------|
|<span data-ttu-id="06827-128">産品</span><span class="sxs-lookup"><span data-stu-id="06827-128">Co</span></span>       | <span data-ttu-id="06827-129">産品</span><span class="sxs-lookup"><span data-stu-id="06827-129">Co</span></span>        |
|<span data-ttu-id="06827-130">Company</span><span class="sxs-lookup"><span data-stu-id="06827-130">Company</span></span>     |<span data-ttu-id="06827-131">Company</span><span class="sxs-lookup"><span data-stu-id="06827-131">Company</span></span>         |
|<span data-ttu-id="06827-132">Department</span><span class="sxs-lookup"><span data-stu-id="06827-132">Department</span></span>     |<span data-ttu-id="06827-133">Department</span><span class="sxs-lookup"><span data-stu-id="06827-133">Department</span></span>         |
|<span data-ttu-id="06827-134">ExtensionAttribute1</span><span class="sxs-lookup"><span data-stu-id="06827-134">ExtensionAttribute1</span></span> |<span data-ttu-id="06827-135">CustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="06827-135">CustomAttribute1</span></span>  |
|<span data-ttu-id="06827-136">ExtensionAttribute2</span><span class="sxs-lookup"><span data-stu-id="06827-136">ExtensionAttribute2</span></span> |<span data-ttu-id="06827-137">CustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="06827-137">CustomAttribute2</span></span>  |
|<span data-ttu-id="06827-138">ExtensionAttribute3</span><span class="sxs-lookup"><span data-stu-id="06827-138">ExtensionAttribute3</span></span> |<span data-ttu-id="06827-139">CustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="06827-139">CustomAttribute3</span></span>  |
|<span data-ttu-id="06827-140">ExtensionAttribute4</span><span class="sxs-lookup"><span data-stu-id="06827-140">ExtensionAttribute4</span></span> |<span data-ttu-id="06827-141">CustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="06827-141">CustomAttribute4</span></span>  |
|<span data-ttu-id="06827-142">ExtensionAttribute5</span><span class="sxs-lookup"><span data-stu-id="06827-142">ExtensionAttribute5</span></span> |<span data-ttu-id="06827-143">CustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="06827-143">CustomAttribute5</span></span>  |
|<span data-ttu-id="06827-144">ExtensionAttribute6</span><span class="sxs-lookup"><span data-stu-id="06827-144">ExtensionAttribute6</span></span> |<span data-ttu-id="06827-145">CustomAttribute6</span><span class="sxs-lookup"><span data-stu-id="06827-145">CustomAttribute6</span></span>  |
|<span data-ttu-id="06827-146">ExtensionAttribute7</span><span class="sxs-lookup"><span data-stu-id="06827-146">ExtensionAttribute7</span></span> |<span data-ttu-id="06827-147">CustomAttribute7</span><span class="sxs-lookup"><span data-stu-id="06827-147">CustomAttribute7</span></span>  |
|<span data-ttu-id="06827-148">ExtensionAttribute8</span><span class="sxs-lookup"><span data-stu-id="06827-148">ExtensionAttribute8</span></span> |<span data-ttu-id="06827-149">CustomAttribute8</span><span class="sxs-lookup"><span data-stu-id="06827-149">CustomAttribute8</span></span>  |
|<span data-ttu-id="06827-150">ExtensionAttribute9</span><span class="sxs-lookup"><span data-stu-id="06827-150">ExtensionAttribute9</span></span> |<span data-ttu-id="06827-151">CustomAttribute9</span><span class="sxs-lookup"><span data-stu-id="06827-151">CustomAttribute9</span></span>  |
|<span data-ttu-id="06827-152">ExtensionAttribute10</span><span class="sxs-lookup"><span data-stu-id="06827-152">ExtensionAttribute10</span></span> |<span data-ttu-id="06827-153">CustomAttribute10</span><span class="sxs-lookup"><span data-stu-id="06827-153">CustomAttribute10</span></span>  |
|<span data-ttu-id="06827-154">ExtensionAttribute11</span><span class="sxs-lookup"><span data-stu-id="06827-154">ExtensionAttribute11</span></span> |<span data-ttu-id="06827-155">CustomAttribute11</span><span class="sxs-lookup"><span data-stu-id="06827-155">CustomAttribute11</span></span>  |
|<span data-ttu-id="06827-156">ExtensionAttribute12</span><span class="sxs-lookup"><span data-stu-id="06827-156">ExtensionAttribute12</span></span> |<span data-ttu-id="06827-157">CustomAttribute12</span><span class="sxs-lookup"><span data-stu-id="06827-157">CustomAttribute12</span></span>  |
|<span data-ttu-id="06827-158">ExtensionAttribute13</span><span class="sxs-lookup"><span data-stu-id="06827-158">ExtensionAttribute13</span></span> |<span data-ttu-id="06827-159">CustomAttribute13</span><span class="sxs-lookup"><span data-stu-id="06827-159">CustomAttribute13</span></span>  |
|<span data-ttu-id="06827-160">ExtensionAttribute14</span><span class="sxs-lookup"><span data-stu-id="06827-160">ExtensionAttribute14</span></span> |<span data-ttu-id="06827-161">CustomAttribute14</span><span class="sxs-lookup"><span data-stu-id="06827-161">CustomAttribute14</span></span>  |
|<span data-ttu-id="06827-162">ExtensionAttribute15</span><span class="sxs-lookup"><span data-stu-id="06827-162">ExtensionAttribute15</span></span> |<span data-ttu-id="06827-163">CustomAttribute15</span><span class="sxs-lookup"><span data-stu-id="06827-163">CustomAttribute15</span></span>  |
|<span data-ttu-id="06827-164">MSExchExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="06827-164">MSExchExtensionCustomAttribute1</span></span> |<span data-ttu-id="06827-165">ExtensionCustomAttribute1</span><span class="sxs-lookup"><span data-stu-id="06827-165">ExtensionCustomAttribute1</span></span> |
|<span data-ttu-id="06827-166">MSExchExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="06827-166">MSExchExtensionCustomAttribute2</span></span> |<span data-ttu-id="06827-167">ExtensionCustomAttribute2</span><span class="sxs-lookup"><span data-stu-id="06827-167">ExtensionCustomAttribute2</span></span> |
|<span data-ttu-id="06827-168">MSExchExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="06827-168">MSExchExtensionCustomAttribute3</span></span> |<span data-ttu-id="06827-169">ExtensionCustomAttribute3</span><span class="sxs-lookup"><span data-stu-id="06827-169">ExtensionCustomAttribute3</span></span> |
|<span data-ttu-id="06827-170">MSExchExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="06827-170">MSExchExtensionCustomAttribute4</span></span> |<span data-ttu-id="06827-171">ExtensionCustomAttribute4</span><span class="sxs-lookup"><span data-stu-id="06827-171">ExtensionCustomAttribute4</span></span> |
|<span data-ttu-id="06827-172">MSExchExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="06827-172">MSExchExtensionCustomAttribute5</span></span> |<span data-ttu-id="06827-173">ExtensionCustomAttribute5</span><span class="sxs-lookup"><span data-stu-id="06827-173">ExtensionCustomAttribute5</span></span> |
|<span data-ttu-id="06827-174">MailNickname</span><span class="sxs-lookup"><span data-stu-id="06827-174">MailNickname</span></span> |<span data-ttu-id="06827-175">エイリアス</span><span class="sxs-lookup"><span data-stu-id="06827-175">Alias</span></span> |
|<span data-ttu-id="06827-176">PhysicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="06827-176">PhysicalDeliveryOfficeName</span></span> |<span data-ttu-id="06827-177">Office</span><span class="sxs-lookup"><span data-stu-id="06827-177">Office</span></span> |
|<span data-ttu-id="06827-178">郵便</span><span class="sxs-lookup"><span data-stu-id="06827-178">PostalCode</span></span> |<span data-ttu-id="06827-179">郵便</span><span class="sxs-lookup"><span data-stu-id="06827-179">PostalCode</span></span> |
|<span data-ttu-id="06827-180">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="06827-180">ProxyAddresses</span></span> |<span data-ttu-id="06827-181">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="06827-181">EmailAddresses</span></span> |
|<span data-ttu-id="06827-182">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="06827-182">StreetAddress</span></span> |<span data-ttu-id="06827-183">StreetAddress</span><span class="sxs-lookup"><span data-stu-id="06827-183">StreetAddress</span></span> |
|<span data-ttu-id="06827-184">TargetAddress</span><span class="sxs-lookup"><span data-stu-id="06827-184">TargetAddress</span></span> |<span data-ttu-id="06827-185">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="06827-185">ExternalEmailAddress</span></span> |
|<span data-ttu-id="06827-186">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="06827-186">UsageLocation</span></span> |<span data-ttu-id="06827-187">UsageLocation</span><span class="sxs-lookup"><span data-stu-id="06827-187">UsageLocation</span></span> |
|<span data-ttu-id="06827-188">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="06827-188">UserPrincipalName</span></span>  |<span data-ttu-id="06827-189">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="06827-189">UserPrincipalName</span></span>  |
|<span data-ttu-id="06827-190">メール</span><span class="sxs-lookup"><span data-stu-id="06827-190">Mail</span></span>   |<span data-ttu-id="06827-191">WindowsEmailAddress</span><span class="sxs-lookup"><span data-stu-id="06827-191">WindowsEmailAddress</span></span>    |
|<span data-ttu-id="06827-192">説明</span><span class="sxs-lookup"><span data-stu-id="06827-192">Description</span></span>    |<span data-ttu-id="06827-193">説明</span><span class="sxs-lookup"><span data-stu-id="06827-193">Description</span></span>    |
|<span data-ttu-id="06827-194">所属</span><span class="sxs-lookup"><span data-stu-id="06827-194">MemberOf</span></span>   |<span data-ttu-id="06827-195">MemberOfGroup</span><span class="sxs-lookup"><span data-stu-id="06827-195">MemberOfGroup</span></span>  |

## <a name="related-topics"></a><span data-ttu-id="06827-196">関連項目</span><span class="sxs-lookup"><span data-stu-id="06827-196">Related topics</span></span>

[<span data-ttu-id="06827-197">Microsoft Teams の情報障壁に関するポリシーを定義する (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="06827-197">Define policies for information barriers in Microsoft Teams (Preview)</span></span>](information-barriers-policies.md)

[<span data-ttu-id="06827-198">情報障壁のトラブルシューティング (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="06827-198">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)

[<span data-ttu-id="06827-199">情報バリア (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="06827-199">Information barriers (Preview)</span></span>](information-barriers.md)



