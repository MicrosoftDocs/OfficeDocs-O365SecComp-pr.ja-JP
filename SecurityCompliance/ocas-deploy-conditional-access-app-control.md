---
title: Office 365 アプリ用のアプリの条件付きアクセス制御を展開する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: 次の手順に従って、office 365 Cloud App Security Conditional Access App Control によって制御されるように Azure AD Office 365 アプリを構成します。
ms.openlocfilehash: 72be95b3213b90cfe60d851d0852d465cdbe6ef9
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263113"
---
# <a name="deploy-conditional-access-app-control-for-office-365-apps"></a><span data-ttu-id="3c591-103">Office 365 アプリ用のアプリの条件付きアクセス制御を展開する</span><span class="sxs-lookup"><span data-stu-id="3c591-103">Deploy Conditional Access App Control for Office 365 apps</span></span>

|<span data-ttu-id="3c591-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3c591-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="3c591-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3c591-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="3c591-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="3c591-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="3c591-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="3c591-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="3c591-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="3c591-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="3c591-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="3c591-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="3c591-110">ここでは、</span><span class="sxs-lookup"><span data-stu-id="3c591-110">You are here!</span></span>  <br/> [<span data-ttu-id="3c591-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="3c591-111">Next step</span></span>](ocas-session-policies.md) <br/> |[<span data-ttu-id="3c591-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="3c591-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="3c591-113">次の手順に従って、office 365 Cloud App Security Conditional Access App Control によって制御されるように Azure AD Office 365 アプリを構成します。</span><span class="sxs-lookup"><span data-stu-id="3c591-113">Follow these steps to configure Azure AD Office 365 apps to be controlled by Office 365 Cloud App Security Conditional Access App Control.</span></span>

<span data-ttu-id="3c591-114">**手順 1: [Azure AD 条件付きアクセステストポリシーを作成する](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span><span class="sxs-lookup"><span data-stu-id="3c591-114">**Step 1: [Create an Azure AD conditional access test policy](#step-1-create-an-azure-ad-conditional-access-test-policy)**</span></span>

<span data-ttu-id="3c591-115">**手順 2: [アプリのポリシーをスコープとするユーザーを使用してサインイン](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)する**</span><span class="sxs-lookup"><span data-stu-id="3c591-115">**Step 2: [Sign in with a user scoped to the policy in the apps](#step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps)**</span></span>

<span data-ttu-id="3c591-116">**手順 3: Azure AD で組み込みの Cloud app Security ポリシーを選択しなかった場合、またはこのポリシーを非おすすめアプリに適用する場合は、 [cloud app security ポータルで高度なコントロールを構成](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)します。**</span><span class="sxs-lookup"><span data-stu-id="3c591-116">**Step 3: If you did not select a built-in Cloud App Security policy in Azure AD or if you want to apply the policy to a non-featured app, [Configure advanced controls in the Cloud App Security portal](#step-3-configure-advanced-controls-in-the-cloud-app-security-portal)**</span></span>

<span data-ttu-id="3c591-117">**手順 4:[展開をテストする](#step-4-test-the-deployment)**</span><span class="sxs-lookup"><span data-stu-id="3c591-117">**Step 4: [Test the deployment](#step-4-test-the-deployment)**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c591-118">office 365 アプリ用の条件付きアクセスアプリコントロールを展開するには、office 365 Cloud App Security license に加えて、 [Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) の有効なライセンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="3c591-118">To deploy Conditional Access App Control for Office 365 apps, you need a valid [license for Azure AD Premium P1](https://docs.microsoft.com/azure/active-directory/license-users-groups) as well as a Office 365 Cloud App Security license.</span></span>

## <a name="step-1-create-an-azure-ad-conditional-access-test-policy"></a><span data-ttu-id="3c591-119">手順 1: Azure AD 条件付きアクセステストポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="3c591-119">Step 1: Create an Azure AD conditional access test policy</span></span> 

1. <span data-ttu-id="3c591-120">Azure Active Directory の [ **セキュリティ**] で、[ **条件付きアクセス**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c591-120">In Azure Active Directory, under **Security**, click on **Conditional access**.</span></span>

2. <span data-ttu-id="3c591-121">[ **新しいポリシー** ] をクリックし、新しいポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c591-121">Click **New policy** and create a new policy.</span></span>

3. <span data-ttu-id="3c591-122">テストポリシーの [ **ユーザー**] で、初期サインオンと検証に使用できるテストユーザーまたはユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3c591-122">In the TEST policy, under **Users**, assign a test user or user that can be used for an initial sign-on and verification.</span></span>

4. <span data-ttu-id="3c591-123">テストポリシーの [ **クラウドアプリ**] で、制御するアプリを条件付きアクセスアプリコントロールで割り当てます。</span><span class="sxs-lookup"><span data-stu-id="3c591-123">In the TEST policy, under **Cloud app**, assign the apps you want to control with Conditional Access App Control.</span></span>

5. <span data-ttu-id="3c591-124">[ **セッション**] で、組み込みのポリシーのいずれかを使用するようにポリシーを設定するか、 **ダウンロード** **のみ** を監視します。</span><span class="sxs-lookup"><span data-stu-id="3c591-124">Under **Session**, set the policy to use either of the built-in policies, **Monitor only** or **Block downloads**.</span></span> <span data-ttu-id="3c591-125">または、[ **カスタムポリシー** を使用する] を選択して、Cloud App Security ポータルで高度なポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="3c591-125">Or select **Use custom policy** to set an advanced policy in the Cloud App Security portal.</span></span>

6. <span data-ttu-id="3c591-126">適用可能な **条件の割り当て** を追加するか、 **コントロール** を付与します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="3c591-126">Add any applicable **Condition assignments** or **Grant controls** (optional).</span></span>

> ![Azure AD 条件付きアクセス](media/image1.png)

## <a name="step-2-sign-in-with-a-user-scoped-to-the-policy-in-the-apps"></a><span data-ttu-id="3c591-128">手順 2: アプリのポリシーをスコープとするユーザーを使用してサインインする</span><span class="sxs-lookup"><span data-stu-id="3c591-128">Step 2: Sign in with a user scoped to the policy in the apps</span></span> 

<span data-ttu-id="3c591-129">ポリシーを作成したら、そのポリシーで構成されている各アプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3c591-129">After you've created the policy, sign in to each app configured in that policy.</span></span> <span data-ttu-id="3c591-130">ポリシーに構成されたユーザーを使用してサインインしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3c591-130">Make sure you sign in using a user configured in the policy.</span></span> <span data-ttu-id="3c591-131">最初に既存のセッションからサインアウトしてください。</span><span class="sxs-lookup"><span data-stu-id="3c591-131">Make sure to first sign out of existing sessions.</span></span>

<span data-ttu-id="3c591-132">Cloud App Security は、ログインする新しいアプリごとに、ポリシーの詳細をサーバーに同期します。</span><span class="sxs-lookup"><span data-stu-id="3c591-132">Cloud App Security will sync your policy details to its servers for each new app you log in to.</span></span> <span data-ttu-id="3c591-133">これには最大1分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3c591-133">This may take up to one minute.</span></span>

## <a name="step-3-configure-advanced-controls-in-the-cloud-app-security-portal"></a><span data-ttu-id="3c591-134">手順 3: Cloud App Security ポータルで高度なコントロールを構成する</span><span class="sxs-lookup"><span data-stu-id="3c591-134">Step 3: Configure advanced controls in the Cloud App Security portal</span></span> 

<span data-ttu-id="3c591-135">上記の手順により、おすすめのアプリの組み込みの Cloud App Security policy を Azure AD に直接作成することができました。</span><span class="sxs-lookup"><span data-stu-id="3c591-135">The instructions above helped you create a built-in Cloud App Security policy for featured apps directly in Azure AD.</span></span>

<span data-ttu-id="3c591-136">高度なポリシーを構成するには、Office 365 Cloud App Security ポータルで [アクセスポリシー](ocas-access-policies.md) または [セッションポリシー](ocas-session-policies.md) を作成します。</span><span class="sxs-lookup"><span data-stu-id="3c591-136">To configure an advanced policy, create an [access policy](ocas-access-policies.md) or a [session policy](ocas-session-policies.md) in the Office 365 Cloud App Security portal.</span></span>

### <a name="to-identify-devices-using-client-certificates-this-is-optional"></a><span data-ttu-id="3c591-137">クライアント証明書を使用してデバイスを識別する (オプション):</span><span class="sxs-lookup"><span data-stu-id="3c591-137">To identify devices using client certificates (this is optional):</span></span>

1. <span data-ttu-id="3c591-138">[設定] cog に移動し、[ **デバイス id**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3c591-138">Go to the settings cog and choose **Device identification**.</span></span>

2. <span data-ttu-id="3c591-139">1つ以上のルートまたは中間証明書をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3c591-139">Upload one or more root or intermediate certificates.</span></span>

3. <span data-ttu-id="3c591-140">証明書がアップロードされたら、 **デバイスタグ**と **有効なクライアント証明書**に基づいてアクセスポリシーとセッションポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="3c591-140">After the certificate is uploaded, you can create access policies and session policies based on **Device tag** and **Valid client certificate**.</span></span>

![条件付きアクセスアプリコントロールデバイス ID](media/image2.png)

> [!NOTE]
> <span data-ttu-id="3c591-142">証明書は、セッションが有効なクライアント証明書フィルターを使用するポリシーと一致する場合にのみ、ユーザーから要求されます。</span><span class="sxs-lookup"><span data-stu-id="3c591-142">A certificate is only requested from a user if the session matches a policy that uses the valid client certificate filter.</span></span>
> 
## <a name="step-4-test-the-deployment"></a><span data-ttu-id="3c591-143">手順 4: 展開をテストする</span><span class="sxs-lookup"><span data-stu-id="3c591-143">Step 4: Test the deployment</span></span> 

1. <span data-ttu-id="3c591-144">既存のセッションを最初にサインアウトします。</span><span class="sxs-lookup"><span data-stu-id="3c591-144">First sign out of any existing sessions.</span></span> <span data-ttu-id="3c591-145">次に、正常に展開された各アプリにサインインします。</span><span class="sxs-lookup"><span data-stu-id="3c591-145">Then, try to sign in to each app that was successfully deployed.</span></span> <span data-ttu-id="3c591-146">Azure AD で構成されているポリシーに一致するユーザーを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="3c591-146">Sign in using a user that matches the policy configured in Azure AD.</span></span>

2. <span data-ttu-id="3c591-147">Cloud app Security portal で、[ **調査**] の [ **アクティビティログ**] を選択し、アプリごとにログインアクティビティがキャプチャされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c591-147">In the Cloud App Security portal, under **Investigate**, select **Activity log**, and make sure the login activities are captured for each app.</span></span>

3. <span data-ttu-id="3c591-148">[ **詳細設定**] をクリックしてフィルター処理し、Source を使用してフィルター処理するには、 **アクセス制御**を使用します。</span><span class="sxs-lookup"><span data-stu-id="3c591-148">You can filter by clicking on **Advanced**, and then filtering using **Source equals Access control**.</span></span>

4. <span data-ttu-id="3c591-149">管理対象および管理されていないデバイスからモバイルアプリおよびデスクトップアプリにサインインすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c591-149">It's recommended that you sign into mobile and desktop apps from managed and unmanaged devices.</span></span> <span data-ttu-id="3c591-150">これは、アクティビティがアクティビティログに適切にキャプチャされることを確認するためのものです。</span><span class="sxs-lookup"><span data-stu-id="3c591-150">This is to make sure that the activities are properly captured in the activity log.</span></span> <span data-ttu-id="3c591-151">アクティビティが適切にキャプチャされたことを確認するには、アクティビティの引き出しを開くシングルサインオンログオンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c591-151">To verify that the activity is properly captured, click on a single sign-on log on activity so that it opens the activity drawer.</span></span> <span data-ttu-id="3c591-152">デバイスがネイティブクライアント (モバイルアプリまたはデスクトップアプリのいずれか) であるか、またはデバイスが管理されたデバイス (準拠、ドメイン参加、または有効なクライアント証明書) であるかを、 **ユーザーエージェントタグ** が正しく反映していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3c591-152">Make sure the **User agent tag** properly reflects whether the device is a native client (meaning either a mobile or desktop app) or the device is a managed device (compliant, domain joined, or valid client certificate).</span></span>

> [!NOTE]
> <span data-ttu-id="3c591-153">展開後は、条件付きアクセスアプリのコントロールページからアプリを削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c591-153">After it is deployed, you can't remove an app from the Conditional Access App Control page.</span></span> <span data-ttu-id="3c591-154">アプリにセッションまたはアクセスポリシーを設定しない限り、条件付きアクセスアプリコントロールはアプリの動作を変更しません。</span><span class="sxs-lookup"><span data-stu-id="3c591-154">As long as you don't set a session or access policy on the app, the Conditional Access App Control won't change any behavior for the app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3c591-155">次のステップ</span><span class="sxs-lookup"><span data-stu-id="3c591-155">Next steps</span></span>

- [<span data-ttu-id="3c591-156">Office 365 Cloud App Security のセッションポリシーについて</span><span class="sxs-lookup"><span data-stu-id="3c591-156">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="3c591-157">Office 365 Cloud App Security のアクセスポリシーについて</span><span class="sxs-lookup"><span data-stu-id="3c591-157">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 

- [<span data-ttu-id="3c591-158">IP アドレスをグループ化して Office 365 Cloud App Security の管理を簡素化する</span><span class="sxs-lookup"><span data-stu-id="3c591-158">Group your IP addresses to simplify management in Office 365 Cloud App Security</span></span>](group-your-ip-addresses-in-ocas.md)