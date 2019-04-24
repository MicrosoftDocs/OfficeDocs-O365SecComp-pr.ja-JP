---
title: Office 365 Cloud App Security のアプリの条件付きアクセス制御を使用してアプリを保護する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/27/2019
ms.service: O365-seccomp
localization_priority: Normal
description: Office 365 Cloud App Security Conditional Access App Control を使用してリアルタイムで違反とリークを阻止します。
ms.openlocfilehash: d8370b1e02866db8f92ab7f6a46b06ddc3ed1055
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262989"
---
# <a name="protect-apps-with-office-365-cloud-app-security-conditional-access-app-control"></a><span data-ttu-id="147db-103">Office 365 Cloud App Security のアプリの条件付きアクセス制御を使用してアプリを保護する</span><span class="sxs-lookup"><span data-stu-id="147db-103">Protect apps with Office 365 Cloud App Security Conditional Access App Control</span></span>

|<span data-ttu-id="147db-104">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="147db-104">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="147db-105">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="147db-105">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="147db-106">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="147db-106">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="147db-107">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="147db-107">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="147db-108">評価の開始</span><span class="sxs-lookup"><span data-stu-id="147db-108">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="147db-109">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="147db-109">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="147db-110">ここでは、</span><span class="sxs-lookup"><span data-stu-id="147db-110">You are here!</span></span>  <br/> [<span data-ttu-id="147db-111">次の手順</span><span class="sxs-lookup"><span data-stu-id="147db-111">Next step</span></span>](ocas-deploy-conditional-access-app-control.md) <br/> |[<span data-ttu-id="147db-112">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="147db-112">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="147db-113">今日の workplace では、多くの場合、実際のクラウド環境で何が起こっているかを知るのに十分ではありません。</span><span class="sxs-lookup"><span data-stu-id="147db-113">In today’s workplace, it’s often not enough to know what’s happening in your cloud environment after the fact.</span></span> <span data-ttu-id="147db-114">従業員が意図的に、または誤ってデータや組織をリスクにさらされる前に、リアルタイムで違反とリークを阻止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="147db-114">You want to stop breaches and leaks in real time, before employees intentionally or inadvertently put your data and your organization at risk.</span></span> <span data-ttu-id="147db-115">組織内のユーザーがクラウドアプリでこれらのサービスとツールを利用できるようにして、自分のデバイスが動作するようにすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="147db-115">It's important to enable users in your organization to make the most of the services and tools available to them in cloud apps, and let them bring their own devices to work.</span></span> <span data-ttu-id="147db-116">同時に、データ漏洩から、リアルタイムでデータの盗難から組織を保護するためのツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="147db-116">At the same time, you need tools to help protect your organization from data leaks, and data theft, in real time.</span></span> <span data-ttu-id="147db-117">Azure Active Directory と共に、Office 365 Cloud app Security は、これらの機能を条件付きアクセスアプリコントロールを使用した総合的かつ統合された環境で提供します。</span><span class="sxs-lookup"><span data-stu-id="147db-117">Together with Azure Active Directory, Office 365 Cloud App Security delivers these capabilities in a holistic and integrated experience with Conditional Access App Control.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="147db-118">Cloud app security Conditional Access App Control を使用するには、 [Azure active Directory P1 ライセンス](https://azure.microsoft.com/pricing/details/active-directory/) と、アクティブな[Office 365 Cloud App Security](office-365-cas-overview.md)サブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="147db-118">To use Cloud App Security Conditional Access App Control, you need an [Azure Active Directory P1 license](https://azure.microsoft.com/pricing/details/active-directory/) and an active [Office 365 Cloud App Security](office-365-cas-overview.md) subscription.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="147db-119">メカニズム</span><span class="sxs-lookup"><span data-stu-id="147db-119">How it works</span></span>

<span data-ttu-id="147db-120">条件付きアクセスアプリコントロールはリバースプロキシアーキテクチャを使用し、Azure AD 条件付きアクセスと一意に統合されています。</span><span class="sxs-lookup"><span data-stu-id="147db-120">Conditional Access App Control uses a reverse proxy architecture and is uniquely integrated with Azure AD conditional access.</span></span> <span data-ttu-id="147db-121">Azure AD 条件付きアクセスを使用すると、特定の条件に基づいて組織のアプリにアクセス制御を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="147db-121">Azure AD conditional access allows you to enforce access controls on your organization’s apps based on certain conditions.</span></span> <span data-ttu-id="147db-122">条件は、 ** (ユーザーまたはユーザー ** のグループ) と、条件付きアクセスポリシーが適用される *場所* (場所とネットワーク) を定義します。</span><span class="sxs-lookup"><span data-stu-id="147db-122">The conditions define *who* (user or group of users) and *what* (which cloud apps) and *where* (which locations and networks) a conditional access policy is applied to.</span></span> <span data-ttu-id="147db-123">条件を決定した後、ユーザーを Office 365 Cloud app Security にルーティングすることができます。これには、access および session control を適用することによって、条件付きアクセスアプリを使用してデータを保護できます。</span><span class="sxs-lookup"><span data-stu-id="147db-123">After you’ve determined the conditions, you can route users to Office 365 Cloud App Security where you can protect data with Conditional Access App Control by applying access and session controls.</span></span>

<span data-ttu-id="147db-124">Conditional access App Control アクセスおよびセッションポリシーに基づいて、ユーザーのアプリのアクセスとセッションをリアルタイムで監視および制御することができます。</span><span class="sxs-lookup"><span data-stu-id="147db-124">Conditional Access App Control enables user app access and sessions to be monitored and controlled in real time based on access and session policies.</span></span> <span data-ttu-id="147db-125">アクセスポリシーとセッションポリシーは、Cloud App Security ポータル内で使用され、フィルターをさらに絞り込み、ユーザーに対してアクションを実行するように設定します。</span><span class="sxs-lookup"><span data-stu-id="147db-125">Access and session policies are used within the Cloud App Security portal to further refine filters and set actions to be taken on a user.</span></span> <span data-ttu-id="147db-126">アクセスポリシーとセッションポリシーを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="147db-126">With the access and session policies, you can:</span></span>

- <span data-ttu-id="147db-127">**ダウンロード時にブロック**する: 機密ドキュメントのダウンロードをブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="147db-127">**Block on download**: You can block the download of sensitive documents.</span></span> <span data-ttu-id="147db-128">たとえば、管理されていないデバイスの場合です。</span><span class="sxs-lookup"><span data-stu-id="147db-128">For example, on unmanaged devices.</span></span>

- <span data-ttu-id="147db-129">**ダウンロード時の保護**: 機密ドキュメントのダウンロードをブロックする代わりに、ダウンロード時に暗号化によってドキュメントを保護するよう要求することができます。</span><span class="sxs-lookup"><span data-stu-id="147db-129">**Protect on download**: Instead of blocking the download of sensitive documents, you can require documents to be protected via encryption on download.</span></span> <span data-ttu-id="147db-130">この暗号化によって、信頼されていないデバイスにデータがダウンロードされた場合に、ドキュメントが保護され、ユーザーアクセスが認証されます。</span><span class="sxs-lookup"><span data-stu-id="147db-130">This encryption makes sure the document is protected and user access is authenticated if the data is downloaded to an untrusted device.</span></span>

- <span data-ttu-id="147db-131">**低信頼ユーザーセッションを監視**する: アプリケーションがアプリにサインインするときに、危険性のあるユーザーが監視され、その操作がセッション内からログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="147db-131">**Monitor low-trust user sessions**: Risky users are monitored when they sign into apps and their actions are logged from within the session.</span></span> <span data-ttu-id="147db-132">ユーザーの行動を調査および分析して、状況を把握することができます。また、どのような状況でも、今後はセッションポリシーを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="147db-132">You can investigate and analyze user behavior to understand where, and under what conditions, session policies should be applied in the future.</span></span>

- <span data-ttu-id="147db-133">**アクセスをブロック**する: 非管理対象デバイスまたは企業以外のネットワークから、特定のアプリへのアクセスを完全にブロックすることができます。</span><span class="sxs-lookup"><span data-stu-id="147db-133">**Block access**: You can completely block access to specific apps for users coming from unmanaged devices or from non-corporate networks.</span></span>

- <span data-ttu-id="147db-134">**読み取り専用モードの作成**: アプリ内のカスタムアクティビティを監視およびブロックすることで、特定のユーザー用の特定のアプリに対して読み取り専用モードを作成できます。</span><span class="sxs-lookup"><span data-stu-id="147db-134">**Create read-only mode**: By monitoring and blocking custom in-app activities, you can create a read-only mode to specific apps for specific users.</span></span>

- <span data-ttu-id="147db-135">**ユーザーセッションを企業以外のネットワークから制限**する: 企業ネットワークの一部でない場所から保護されたアプリにアクセスするユーザーには、制限付きアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="147db-135">**Restrict user sessions from non-corporate networks**: Users accessing a protected app from a location that isn't part of your corporate network are allowed restricted access.</span></span> <span data-ttu-id="147db-136">機密マテリアルのダウンロードは、ブロックまたは保護されます。</span><span class="sxs-lookup"><span data-stu-id="147db-136">The download of sensitive materials is blocked or protected.</span></span>

### <a name="how-session-control-works"></a><span data-ttu-id="147db-137">セッションコントロールのしくみ</span><span class="sxs-lookup"><span data-stu-id="147db-137">How session control works</span></span>

<span data-ttu-id="147db-138">条件付きアクセスアプリコントロールを使用してセッションポリシーを作成すると、ユーザーをアプリに直接ではなくリバースプロキシ経由でリダイレクトすることによって、ユーザーセッションを制御できます。</span><span class="sxs-lookup"><span data-stu-id="147db-138">Creating a session policy with Conditional Access App Control enables you to control user sessions by redirecting the user through a reverse proxy instead of directly to the app.</span></span> <span data-ttu-id="147db-139">その後、ユーザーの要求と応答は、アプリに直接ではなく、Office 365 Cloud App Security を経由して行われます。</span><span class="sxs-lookup"><span data-stu-id="147db-139">From then on, user requests and responses go through Office 365 Cloud App Security rather than directly to the app.</span></span>

<span data-ttu-id="147db-140">ユーザーをセッション内に保持するには、アプリセッション内の関連するすべての url、Java スクリプト、および cookie が Office 365 Cloud app Security url に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="147db-140">To keep the user within the session, all the relevant URLs, Java scripts, and cookies within the app session are replaced with Office 365 Cloud App Security URLs.</span></span> <span data-ttu-id="147db-141">たとえば、アプリが myapp.com で終わるドメインのリンクを持つページを返した場合、リンクは次のようなドメインに置き換えられます。 myapp.com.us.cas.ms</span><span class="sxs-lookup"><span data-stu-id="147db-141">For example, if the app returns a page with links whose domains end with myapp.com, the link is replaced with domains ending with something like: myapp.com.us.cas.ms</span></span>

<span data-ttu-id="147db-142">この方法では、デバイスに何もインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="147db-142">This method doesn't require you to install anything on the device.</span></span> <span data-ttu-id="147db-143">この方法は、管理されていないデバイスからセッションを監視する場合に最適です。</span><span class="sxs-lookup"><span data-stu-id="147db-143">This method is ideal when monitoring sessions from unmanaged devices.</span></span>

<span data-ttu-id="147db-144">Office 365 Cloud App Security を介してセッションが指示されたら、次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="147db-144">After a session is directed through Office 365 Cloud App Security, the following actions can be done:</span></span>

1. <span data-ttu-id="147db-145">ユーザーアクティビティのトラフィックを検査する</span><span class="sxs-lookup"><span data-stu-id="147db-145">Inspect the traffic for user activities</span></span>

2. <span data-ttu-id="147db-146">Office 365 Cloud App Security Activity log で、識別されたアクティビティを表示する</span><span class="sxs-lookup"><span data-stu-id="147db-146">Display the identified activities in the Office 365 Cloud App Security Activity log</span></span>

3. <span data-ttu-id="147db-147">トラフィックログを保存して分析する</span><span class="sxs-lookup"><span data-stu-id="147db-147">Save the traffic logs and analyze them</span></span>

4. <span data-ttu-id="147db-148">管理者がトラフィックログをエクスポートできるようにする</span><span class="sxs-lookup"><span data-stu-id="147db-148">Enable the admin to export the traffic logs</span></span>

5. <span data-ttu-id="147db-149">セッションにポリシーを適用する</span><span class="sxs-lookup"><span data-stu-id="147db-149">Enforce policies on the session</span></span>

## <a name="managed-device-identification"></a><span data-ttu-id="147db-150">管理対象デバイスの識別</span><span class="sxs-lookup"><span data-stu-id="147db-150">Managed device identification</span></span>

<span data-ttu-id="147db-151">Conditional Access App Control デバイスが管理されているかどうかを考慮したポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="147db-151">Conditional Access App Control enables you to create policies that take into account whether a device is managed or not.</span></span> <span data-ttu-id="147db-152">デバイスが管理されているかどうかを確認するには、次の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="147db-152">To identify whether a device is managed or not, the feature uses:</span></span>

- <span data-ttu-id="147db-153">準拠しているデバイス</span><span class="sxs-lookup"><span data-stu-id="147db-153">Compliant devices</span></span>

- <span data-ttu-id="147db-154">ドメインに参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="147db-154">Domain-joined devices</span></span>

- <span data-ttu-id="147db-155">クライアント証明書の展開</span><span class="sxs-lookup"><span data-stu-id="147db-155">Client certificates deployment</span></span>

### <a name="compliant-and-domain-joined-devices"></a><span data-ttu-id="147db-156">準拠しているデバイスとドメインに参加しているデバイス</span><span class="sxs-lookup"><span data-stu-id="147db-156">Compliant and domain-joined devices</span></span>

<span data-ttu-id="147db-157">Azure AD 条件付きアクセスを使用すると、準拠し、ドメインに参加しているデバイス情報を Office 365 Cloud App Security に直接渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="147db-157">Azure AD conditional access enables compliant and domain-joined device information to be passed directly to Office 365 Cloud App Security.</span></span> <span data-ttu-id="147db-158">そこから、デバイス状態をフィルターとして使用するアクセスポリシーまたはセッションポリシーを開発できます。</span><span class="sxs-lookup"><span data-stu-id="147db-158">From there, an access policy or a session policy can be developed that uses device state as a filter.</span></span> <span data-ttu-id="147db-159">詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/azure/active-directory/device-management-introduction)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="147db-159">For more information, see the [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>

### <a name="client-certificate-authenticated-devices"></a><span data-ttu-id="147db-160">クライアント証明書の認証済みデバイス</span><span class="sxs-lookup"><span data-stu-id="147db-160">Client-certificate authenticated devices</span></span>

<span data-ttu-id="147db-161">デバイス識別メカニズムは、クライアント証明書を使用して、関連するデバイスからの認証を要求できます。</span><span class="sxs-lookup"><span data-stu-id="147db-161">The device identification mechanism can request authentication from relevant devices using client certificates.</span></span> <span data-ttu-id="147db-162">組織に既に展開されている既存のクライアント証明書を使用するか、新しいクライアント証明書を管理対象デバイスにロールアウトすることができます。</span><span class="sxs-lookup"><span data-stu-id="147db-162">You can either use existing client certificates already deployed in your organization or roll out new client certificates to managed devices.</span></span> <span data-ttu-id="147db-163">その証明書の存在を使用して、アクセスおよびセッションポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="147db-163">You then use the presence of those certificates to set access and session policies.</span></span> <span data-ttu-id="147db-164">クライアント証明書を展開する方法については、「 [deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="147db-164">For information on how to deploy client certificates see [Deploy Conditional Access App Control for Office 365 apps](ocas-deploy-conditional-access-app-control.md).</span></span>

## <a name="supported-apps-and-clients"></a><span data-ttu-id="147db-165">サポートされるアプリとクライアント</span><span class="sxs-lookup"><span data-stu-id="147db-165">Supported apps and clients</span></span>

<span data-ttu-id="147db-166">Office 365 の条件付きアクセスアプリコントロールは、次のおすすめアプリをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="147db-166">Conditional Access App Control for Office 365 supports the following featured apps:</span></span>

- <span data-ttu-id="147db-167">Exchange Online (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="147db-167">Exchange Online (preview)</span></span>

- <span data-ttu-id="147db-168">OneDrive for business (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="147db-168">OneDrive for Business (preview)</span></span>

- <span data-ttu-id="147db-169">Power BI (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="147db-169">Power BI (preview)</span></span>

- <span data-ttu-id="147db-170">SharePoint Online (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="147db-170">SharePoint Online (preview)</span></span>

- <span data-ttu-id="147db-171">Microsoft Teams (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="147db-171">Microsoft Teams (preview)</span></span>

- <span data-ttu-id="147db-172">Yammer (プレビュー)</span><span class="sxs-lookup"><span data-stu-id="147db-172">Yammer (preview)</span></span>

<span data-ttu-id="147db-173">その他のアプリは、継続的に boarded control に送られます。</span><span class="sxs-lookup"><span data-stu-id="147db-173">Additional apps are being continuously on-boarded to session control.</span></span>

## <a name="next-steps"></a><span data-ttu-id="147db-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="147db-174">Next steps</span></span>

- [<span data-ttu-id="147db-175">Office 365 アプリ用のアプリの条件付きアクセス制御を展開する</span><span class="sxs-lookup"><span data-stu-id="147db-175">Deploy Conditional Access App Control for Office 365 apps</span></span>](ocas-deploy-conditional-access-app-control.md)

- [<span data-ttu-id="147db-176">Office 365 Cloud App Security のセッションポリシーについて</span><span class="sxs-lookup"><span data-stu-id="147db-176">Learn about session policies in Office 365 Cloud App Security</span></span>](ocas-session-policies.md)

- [<span data-ttu-id="147db-177">Office 365 Cloud App Security のアクセスポリシーについて</span><span class="sxs-lookup"><span data-stu-id="147db-177">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md) 