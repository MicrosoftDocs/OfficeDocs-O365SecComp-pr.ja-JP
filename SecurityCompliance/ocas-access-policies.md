---
title: Office 365 のアクセスポリシー Cloud App Security
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: o365-administration
localization_priority: Normal
description: Office 365 cloud App Security アクセスポリシーを使用すると、ユーザー、場所、デバイス、およびアプリに基づいて、クラウドアプリへのアクセスをリアルタイムで監視し、制御することができます。クライアント証明書を管理対象デバイスに展開したり、サードパーティの MDM 証明書などの既存の証明書を使用したりすることによって、ドメインに参加していないデバイスや、Windows Intune によって管理されていないデバイスを含む、任意のデバイスのアクセスポリシーを作成できます。たとえば、クライアント証明書を管理対象デバイスに展開し、証明書を持たないデバイスからのアクセスをブロックすることができます。
ms.openlocfilehash: bb4404793647c65ab8addc148e6efe24242f3079
ms.sourcegitcommit: 8679937354c1d8870ecd41519a59d2d7468c23c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2019
ms.locfileid: "30103312"
---
# <a name="access-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="19818-105">Office 365 のアクセスポリシー Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="19818-105">Access policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="19818-106">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="19818-106">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="19818-107">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="19818-107">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="19818-108">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="19818-108">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="19818-109">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="19818-109">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="19818-110">評価の開始</span><span class="sxs-lookup"><span data-stu-id="19818-110">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="19818-111">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="19818-111">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="19818-112">ここでは、</span><span class="sxs-lookup"><span data-stu-id="19818-112">You are here!</span></span>  <br/> [<span data-ttu-id="19818-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="19818-113">Next step</span></span>](group-your-ip-addresses-in-ocas.md) <br/> |[<span data-ttu-id="19818-114">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="19818-114">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="19818-p102">Office 365 cloud App Security アクセスポリシーを使用すると、ユーザー、場所、デバイス、およびアプリに基づいて、クラウドアプリへのアクセスをリアルタイムで監視し、制御することができます。クライアント証明書を管理対象デバイスに展開したり、サードパーティの MDM 証明書などの既存の証明書を使用したりすることによって、ドメインに参加していないデバイスや、Windows Intune によって管理されていないデバイスを含む、任意のデバイスのアクセスポリシーを作成できます。たとえば、クライアント証明書を管理対象デバイスに展開し、証明書を持たないデバイスからのアクセスをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="19818-p102">Office 365 Cloud App Security access policies enable real-time monitoring and control over access to cloud apps based on user, location, device, and app. You can create access policies for any device, including devices that aren't domain joined, and not managed by Windows Intune by rolling out client certificates to managed devices or by using existing certificates, such as third-party MDM certificates. For example, you can deploy client certificates to managed devices, and then block access from devices without a certificate.</span></span>

<span data-ttu-id="19818-118">セッション [ポリシー](ocas-session-policies.md) を使用して、アクセスを完全に許可またはブロックする代わりに、セッションを監視したり、特定のセッションアクティビティを制限したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="19818-118">Instead of allowing or blocking access completely, with [session policies](ocas-session-policies.md) you can allow access while monitoring the session and/or limit specific session activities.</span></span>

## <a name="prerequisites-to-using-access-policies"></a><span data-ttu-id="19818-119">アクセスポリシーを使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="19818-119">Prerequisites to using access policies</span></span>

- <span data-ttu-id="19818-120">Azure AD Premium P1 ライセンス</span><span class="sxs-lookup"><span data-stu-id="19818-120">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="19818-121">関連するアプリは、 [条件付きアクセスアプリコントロールを使用して展開](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19818-121">The relevant apps should be [deployed with Conditional Access App Control](https://docs.microsoft.com/en-us/cloud-app-security/proxy-deployment-aad)</span></span>

- <span data-ttu-id="19818-122">以下の説明に従って、ユーザーを Office 365 Cloud App Security にリダイレクトする [Azure AD 条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="19818-122">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security, as described below.</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="19818-123">Azure AD 条件付きアクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="19818-123">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="19818-p103">Azure Active Directory の条件付きアクセスポリシーと Cloud App Security セッションポリシーは、相互に連携して各ユーザーセッションを調べ、各アプリのポリシーを決定します。Azure AD で条件付きアクセスポリシーを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19818-p103">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app. To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="19818-126">ユーザーまたはユーザーのグループ、および条件付きアクセスアプリコントロールを使用して制御するアプリの割り当てを使用して、 [Azure AD 条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) を構成します。</span><span class="sxs-lookup"><span data-stu-id="19818-126">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for user or group of users and the app you want to control with Conditional Access App Control.</span></span><br><span data-ttu-id="19818-127">注:  [条件付きアクセスアプリコントロールを使用](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad)して展開されたアプリのみ、このポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="19818-127">NOTE: Only apps that were [deployed with Conditional Access App Control](https://docs.microsoft.com/cloud-app-security/proxy-deployment-aad) will be affected by this policy.</span></span>

2. <span data-ttu-id="19818-128"> [ *\*条件付きアクセスアプリを使用する] コントロール*\*で [ *\*セッション*\*] を選択して、ユーザーを Office 365 Cloud App Security にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="19818-128">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** under **Session**.</span></span>

## <a name="create-a-cloud-app-security-access-policy"></a><span data-ttu-id="19818-129">クラウドアプリのセキュリティアクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="19818-129">Create a Cloud App Security access policy</span></span>

<span data-ttu-id="19818-130">新しいアクセスポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="19818-130">To create a new access policy, follow this procedure:</span></span>

1. <span data-ttu-id="19818-131">ポータルで、[ **コントロール** の後に **ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19818-131">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="19818-132">[ **ポリシー** ] ページで、[ **ポリシー** の作成] をクリックし、[ **アクセスポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="19818-132">In the **Policies** page, click **Create policy** and select **Access policy**.</span></span>

3. <span data-ttu-id="19818-133">[ **アクセスポリシー** ] ウィンドウで、[管理されていない *デバイスからのアクセスをブロック*する] など、ポリシーの名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="19818-133">In the **Access policy** window, assign a name for your policy, such as *Block access from unmanaged devices*.</span></span>

4. <span data-ttu-id="19818-p104">  \*\*次のすべての\*\*セクションに一致するアクティビティについては、[ \*\*アクティビティソース\*\*] の下で、ポリシーに適用する追加のアクティビティフィルターを選択します。フィルターには、次のオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="19818-p104">In the **Activities matching all of the following** section, Under **Activity source**, select additional activity filters to apply to the policy. Filters include the following options:</span></span>
    
    - <span data-ttu-id="19818-136">**デバイスタグ**: 管理されていないデバイスを識別するには、このフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="19818-136">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="19818-137">**場所**: このフィルターを使用して、不明 (つまり、危険) の場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="19818-137">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="19818-138">**ip アドレス**: このフィルターを使用して、ip アドレスごとにフィルター処理するか、以前に割り当てられた ip アドレスタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="19818-138">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="19818-p105">**ユーザーエージェントタグ**: このフィルターを使用して、モバイルアプリとデスクトップアプリを識別するヒューリスティックを有効にします。このフィルターは、等しいまたは等しくないように設定できます。これらの値は、各クラウドアプリのモバイルアプリとデスクトップアプリに対してテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="19818-p105">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or does not equal. The values should be tested against your mobile and desktop apps for each cloud app.</span></span>

5. <span data-ttu-id="19818-142">[ **アクション**] で、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="19818-142">Under **Actions**, select one of the following options:</span></span>
    
    - <span data-ttu-id="19818-143">**Allow**: 設定したポリシーフィルターに従って、アクセスを明示的に許可するには、このアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="19818-143">**Allow**: Set this action to explicitly allow access according to the policy filters you set.</span></span>
    
    - <span data-ttu-id="19818-144">**block**: 設定したポリシーフィルターに従ってアクセスを明示的にブロックするには、このアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="19818-144">**Block**: Set this action to explicitly block access according to the policy filters you set.</span></span>

6. <span data-ttu-id="19818-145">  \*\*ポリシーの重要度を持つ各一致イベントに対して通知を作成\*\*し、通知制限を設定して、警告を電子メールとして設定するか、またはその両方にするかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="19818-145">You can **Create an alert for each matching event with the policy's severity** and set an alert limit and select whether you want the alert as an email, a text message or both.</span></span>

## <a name="next-steps"></a><span data-ttu-id="19818-146">次の手順</span><span class="sxs-lookup"><span data-stu-id="19818-146">Next steps</span></span>

- [<span data-ttu-id="19818-147">IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="19818-147">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)