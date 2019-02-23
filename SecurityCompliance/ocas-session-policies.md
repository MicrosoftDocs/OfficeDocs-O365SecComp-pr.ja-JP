---
title: Office 365 Cloud App Security のセッション ポリシー
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.reviewer: alesibov
ms.audience: Admin
ms.topic: reference
ms.date: 02/14/2019
ms.service: O365-seccomp
localization_priority: Normal
description: office 365 Cloud App Security セッションポリシーを使用すると、リアルタイムのセッションレベルの監視が可能になり、office 365 アプリの詳細な表示を affording し、ユーザーセッションに設定したポリシーに応じて異なる操作を実行することができます。session control を使用して、アクセスを完全に許可またはブロックするのではなく、セッションの監視中にアクセスを許可したり、条件付きアクセスアプリコントロールのリバースプロキシ機能を使用して特定のセッションアクティビティを制限したりすることができます。
ms.openlocfilehash: a57b62073e93c95217a829f8aa381f4a585dacc5
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218607"
---
# <a name="session-policies-in-office-365-cloud-app-security"></a><span data-ttu-id="be37a-104">Office 365 Cloud App Security のセッション ポリシー</span><span class="sxs-lookup"><span data-stu-id="be37a-104">Session policies in Office 365 Cloud App Security</span></span>

|<span data-ttu-id="be37a-105">評価 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="be37a-105">\*\*\*\*Evaluation\*\* \>\*\*</span></span>|<span data-ttu-id="be37a-106">計画 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="be37a-106">\*\*\*\*Planning\*\* \>\*\*</span></span>|<span data-ttu-id="be37a-107">展開 \* *\>*\*</span><span class="sxs-lookup"><span data-stu-id="be37a-107">\*\*\*\*Deployment\*\* \>\*\*</span></span>|<span data-ttu-id="be37a-108">使用率 \* \* \* \*</span><span class="sxs-lookup"><span data-stu-id="be37a-108">\*\*\*\*Utilization\*\*\*\*</span></span>|
|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="be37a-109">評価の開始</span><span class="sxs-lookup"><span data-stu-id="be37a-109">Start evaluating</span></span>](office-365-cas-overview.md) <br/> |[<span data-ttu-id="be37a-110">計画を開始する</span><span class="sxs-lookup"><span data-stu-id="be37a-110">Start planning</span></span>](get-ready-for-office-365-cas.md) <br/> |<span data-ttu-id="be37a-111">ここでは、</span><span class="sxs-lookup"><span data-stu-id="be37a-111">You are here!</span></span>  <br/> [<span data-ttu-id="be37a-112">次の手順</span><span class="sxs-lookup"><span data-stu-id="be37a-112">Next step</span></span>](ocas-access-policies.md) <br/> |[<span data-ttu-id="be37a-113">利用を開始する</span><span class="sxs-lookup"><span data-stu-id="be37a-113">Start utilizing</span></span>](utilization-activities-for-ocas.md) <br/> |

<span data-ttu-id="be37a-p102">office 365 Cloud App Security セッションポリシーを使用すると、リアルタイムのセッションレベルの監視が可能になり、office 365 アプリの詳細な表示を affording し、ユーザーセッションに設定したポリシーに応じて異なる操作を実行することができます。session control を使用して、アクセスを完全に許可またはブロックするのではなく、セッションの監視中にアクセスを許可したり、条件付きアクセスアプリコントロールのリバースプロキシ機能を使用して特定のセッションアクティビティを制限したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p102">Office 365 Cloud App Security session policies enable real-time session-level monitoring, affording you granular visibility into Office 365 apps and the ability to take different actions depending on the policy you set for a user session. Instead of allowing or blocking access completely, with session control you can allow access while monitoring the session and/or limit specific session activities using the reverse proxy capabilities of Conditional Access App Control.</span></span>

<span data-ttu-id="be37a-p103">たとえば、管理されていないデバイスから、または特定の場所からのセッションに対して、ユーザーがアプリにアクセスできるようにすると同時に、機密ファイルのダウンロードを制限したり、ダウンロード時に特定のドキュメントの保護を要求したりできます。セッションポリシーを使用すると、これらのユーザーセッションコントロールを設定してアクセスを許可し、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p103">For example, you can decide that from unmanaged devices, or for sessions coming from specific locations, you want to allow the user to access the app but also limit the download of sensitive files or require that certain documents be protected upon download. Session policies enable you to set these user-session controls and allow access and enables you to:</span></span>

- [<span data-ttu-id="be37a-118">すべてのアクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="be37a-118">Monitor all activities</span></span>](#monitor-all-activities)

- [<span data-ttu-id="be37a-119">すべてのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="be37a-119">Block all downloads</span></span>](#block-all-downloads)

- [<span data-ttu-id="be37a-120">特定のアクティビティをブロックする</span><span class="sxs-lookup"><span data-stu-id="be37a-120">Block specific activities</span></span>](#block-specific-activities)

- [<span data-ttu-id="be37a-121">ダウンロード時にファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="be37a-121">Protect files on download</span></span>](#protect-files-on-download)

## <a name="prerequisites-to-using-session-policies"></a><span data-ttu-id="be37a-122">セッションポリシーを使用するための前提条件</span><span class="sxs-lookup"><span data-stu-id="be37a-122">Prerequisites to using session policies</span></span>

- <span data-ttu-id="be37a-123">Azure AD Premium P1 ライセンス</span><span class="sxs-lookup"><span data-stu-id="be37a-123">Azure AD Premium P1 license</span></span>

- <span data-ttu-id="be37a-124">関連する Office 365 アプリは、 [条件付きアクセスアプリコントロールを使用して展開](ocas-deploy-conditional-access-app-control.md)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be37a-124">The relevant Office 365 apps should be [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md)</span></span>

- <span data-ttu-id="be37a-125">ユーザーを Office 365 Cloud App Security にリダイレクトする [Azure AD 条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="be37a-125">An [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) should be in place that redirects users to Office 365 Cloud App Security</span></span>

## <a name="create-an-azure-ad-conditional-access-policy"></a><span data-ttu-id="be37a-126">Azure AD 条件付きアクセスポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="be37a-126">Create an Azure AD conditional access policy</span></span>

<span data-ttu-id="be37a-p104">Azure Active Directory の条件付きアクセスポリシーと Cloud App Security セッションポリシーは、相互に連携して各ユーザーセッションを調べ、各アプリのポリシーを決定します。Azure AD で条件付きアクセスポリシーを設定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be37a-p104">Azure Active Directory conditional access policies and Cloud App Security session policies work in tandem to examine each user session and make policy decisions for each app. To set up a conditional access policy in Azure AD, follow this procedure:</span></span>

1. <span data-ttu-id="be37a-p105">ユーザーまたはユーザーのグループ、および条件付きアクセスアプリコントロールを使用して制御するアプリの割り当てを使用して、 [Azure AD 条件付きアクセスポリシー](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) を構成します。注:  [条件付きアクセスアプリコントロールを使用](ocas-deploy-conditional-access-app-control.md)して展開されたアプリのみ、このポリシーの影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p105">Configure an [Azure AD conditional access policy](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) with assignments for a user or group of users and the app you want to control with the Conditional Access App Control. NOTE: Only apps that were [deployed with Conditional Access App Control](ocas-deploy-conditional-access-app-control.md) will be affected by this policy.</span></span>

2. <span data-ttu-id="be37a-131">[  **セッション**] ページ で [ **条件付きアクセスアプリコントロールの使用を強制**する] を選択して、ユーザーを Office 365 Cloud App Security にルーティングします。</span><span class="sxs-lookup"><span data-stu-id="be37a-131">Route users to Office 365 Cloud App Security by selecting the **Use Conditional Access App Control enforced restrictions** in the **Session** page.</span></span>

## <a name="create-a-cloud-app-security-session-policy"></a><span data-ttu-id="be37a-132">Cloud App Security セッションポリシーを作成する</span><span class="sxs-lookup"><span data-stu-id="be37a-132">Create a Cloud App Security session policy</span></span>

<span data-ttu-id="be37a-133">新しいセッションポリシーを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="be37a-133">To create a new session policy, follow this procedure:</span></span>

1. <span data-ttu-id="be37a-134">ポータルで、[ **コントロール** の後に **ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be37a-134">In the portal, select **Control** followed by **Policies**.</span></span>

2. <span data-ttu-id="be37a-135">[ **ポリシー** ] ページで、[ **ポリシー** の作成] をクリックし、[ **セッションポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be37a-135">In the **Policies** page, click **Create policy** and select **Session policy**.</span></span>

3. <span data-ttu-id="be37a-136">[ **セッションポリシー** ] ウィンドウで、ポリシーの名前を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="be37a-136">In the **Session policy** window, assign a name for your policy</span></span>

4. <span data-ttu-id="be37a-137">[ **セッションコントロールの種類** ] フィールドで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="be37a-137">In the **Session control type** field:</span></span>
    
    - <span data-ttu-id="be37a-p106">ユーザーのアクティビティのみを監視する場合は、[ **監視のみ** ] を選択します。この選択では、選択したアプリに対して、すべてのサインイン、ヒューリスティックダウンロード、およびアクティビティの種類がダウンロードされるように、モニターのみのポリシーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p106">Select **Monitor only** if you only want to monitor activities by users. This selection will create a Monitor only policy for the apps you selected where all sign-ins, heuristic downloads, and Activity types will be downloaded.</span></span>
    
    - <span data-ttu-id="be37a-p107">ユーザーアクティビティを監視する場合は、[ **コントロールファイルのダウンロード (DLP を使用)** ] を選択します。ブロックやユーザーのダウンロードを保護するための追加のアクションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p107">Select **Control file download (with DLP)** if you want to monitor user activities. You can take additional actions like block or protect downloads for users.</span></span>
    
    - <span data-ttu-id="be37a-p108">[ \*\*\*\* アクティビティをブロックする] を選択して特定のアクティビティをブロックします。これは、[ **アクティビティの種類** フィルター] を使用して選択できます。選択したアプリのすべてのアクティビティが監視され、アクティビティログに報告されます。[ **禁止** ] アクションを選択すると、選択した特定のアクティビティはブロックされます。選択した特定のアクティビティでは、[ **テスト** ] アクションを選択して通知を有効にした場合に警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="be37a-p108">Select **Block activities** to block specific activities, which you can select using the **Activity type** filter. All activities from selected apps will be monitored (and reported in the Activity log). The specific activities you select will be blocked if you select the **Block** action. The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

5. <span data-ttu-id="be37a-p109">[  **以下のすべてに該当**するアクティビティ] セクションの [ **アクティビティソース** ] で、ポリシーに適用する追加のアクティビティフィルターを選択します。これらのフィルターには、次のオプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p109">Under **Activity source** in the **Activities matching all of the following** section, select additional activity filters to apply to the policy. These filters can include the following options:</span></span>
    
    - <span data-ttu-id="be37a-148">**デバイスタグ**: 管理されていないデバイスを識別するには、このフィルターを使用します。</span><span class="sxs-lookup"><span data-stu-id="be37a-148">**Device tags**: Use this filter to identify unmanaged devices.</span></span>
    
    - <span data-ttu-id="be37a-149">**場所**: このフィルターを使用して、不明 (つまり、危険) の場所を特定します。</span><span class="sxs-lookup"><span data-stu-id="be37a-149">**Location**: Use this filter to identify unknown (and therefore risky) locations.</span></span>
    
    - <span data-ttu-id="be37a-150">**ip アドレス**: このフィルターを使用して、ip アドレスごとにフィルター処理するか、以前に割り当てられた ip アドレスタグを使用します。</span><span class="sxs-lookup"><span data-stu-id="be37a-150">**IP address**: Use this filter to filter per IP addresses or use previously assigned IP address tags.</span></span>
    
    - <span data-ttu-id="be37a-p110">**ユーザーエージェントタグ**: このフィルターを使用して、モバイルアプリとデスクトップアプリを識別するヒューリスティックを有効にします。このフィルターは、が **ネイティブクライアント**と等しいか等しくないように設定できます。このフィルターは、各クラウドアプリのモバイルアプリとデスクトップアプリに対してテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="be37a-p110">**User agent tag**: Use this filter to enable the heuristic to identify mobile and desktop apps. This filter can be set to equals or doesn't equal **Native client**. This filter should be tested against your mobile and desktop apps for each cloud app.</span></span><br><span data-ttu-id="be37a-p111">メモ: セッションポリシーは、モバイルアプリとデスクトップアプリをサポートしていません。アクセスポリシーを作成することによって、モバイルアプリおよびデスクトップアプリをブロックまたは許可することもできます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p111">NOTE: Session policies don’t support mobile and desktop apps. Mobile apps and desktop apps can also be blocked or allowed by creating an access policy.</span></span>

6. <span data-ttu-id="be37a-p112">[ **ファイルのダウンロードを制御する (DLP を使用)**] オプションを選択した場合は、 **次** のすべてのセクションに一致するファイルの [ **アクティビティソース** ] で、ポリシーに適用する追加のファイルフィルターを選択します。これらのフィルターには、次のオプションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p112">If you selected the option to **Control file download (with DLP)**, under **Activity source** in the **Files matching all of the following** section, select additional file filters to apply to the policy. These filters can include the following options:</span></span>
        
    - <span data-ttu-id="be37a-p113">**分類ラベル** -組織が Azure Information Protection を使用し、データが分類ラベルで保護されている場合は、このフィルターを使用します。適用した分類ラベルに基づいてファイルをフィルター処理することができます。azure information protection との統合の詳細については、「 [azure information protection 統合](https://docs.microsoft.com/cloud-app-security/azip-integration)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be37a-p113">**Classification label** - Use this filter if your organization uses Azure Information Protection and your data has been protected by its Classification labels. You can filter files based on the Classification label you applied to them. For more information about integration with Azure Information Protection, see [Azure Information Protection integration](https://docs.microsoft.com/cloud-app-security/azip-integration).</span></span>
        
    - <span data-ttu-id="be37a-161">**ファイル名** -このフィルターを使用して、特定のファイルにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="be37a-161">**File name** - Use this filter to apply the policy to specific files.</span></span>
        
    - <span data-ttu-id="be37a-162">**ファイルの種類** -このフィルターを使用して、すべての .xls ファイルのブロックダウンロードなど、特定のファイルの種類にポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="be37a-162">**File type** - Use this filter to apply the policy to specific file types, for example, block download for all .xls files.</span></span>
    
    - <span data-ttu-id="be37a-163">[ **コンテンツの検査** ] セクションで、DLP エンジンでドキュメントとファイルのコンテンツをスキャンできるようにするかどうかを設定します。</span><span class="sxs-lookup"><span data-stu-id="be37a-163">In the **Content inspection** section, set whether you want to enable the DLP engine to scan documents and file content.</span></span>
    
    - <span data-ttu-id="be37a-164">[ **アクション**] で、次のいずれかのアイテムを選択します。</span><span class="sxs-lookup"><span data-stu-id="be37a-164">Under **Actions**, select one of the following items:</span></span>
        
        - <span data-ttu-id="be37a-165">**Test (すべてのアクティビティを監視する)**: 設定したポリシーフィルターに従って、ダウンロードを明示的に許可するには、このアクションを設定します。</span><span class="sxs-lookup"><span data-stu-id="be37a-165">**Test (Monitor all activities)**: Set this action to explicitly allow download according to the policy filters you set.</span></span>
        
        - <span data-ttu-id="be37a-p114">[**ブロックする (ファイルをダウンロードしてすべてのアクティビティを監視する)**]: 設定したポリシーフィルターに従って、ダウンロードを明示的にブロックするには、このアクションを設定します。詳細については、「 [ブロックダウンロードのしくみ](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be37a-p114">**Block (Block file download and monitor all activities)**: Set this action to explicitly block download according to the policy filters you set. For more information, see [How block download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#block-download).</span></span>
        
        - <span data-ttu-id="be37a-p115">**保護 (すべてのアクティビティをダウンロードおよび監視するための分類ラベルの適用)**: このオプションは、[ **セッションポリシー**] の下で [ **コントロールファイルのダウンロード (DLP を使用)** ] を選択した場合にのみ使用できます。組織が azure information protection を使用している場合は、azure information protection での分類ラベルセットをファイルに適用する **アクション** を設定できます。詳細については、「 [保護のダウンロードのしくみ](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="be37a-p115">**Protect (Apply classification label to download and monitor all activities)**: This option is only available if you selected **Control file download (with DLP)** under **Session policy**. If your organization uses Azure Information Protection, you can set an **Action** to apply a classification label set in Azure Information Protection to the file. For more information, see [How protect download works](https://docs.microsoft.com/en-us/cloud-app-security/session-policy-aad#protect-download).</span></span>

7. <span data-ttu-id="be37a-p116">  \*\*ポリシーの重要度に一致する各イベントに対して通知を作成\*\*し、通知制限を設定することができます。警告を電子メールとして使用するか、テキストメッセージとして表示するか、またはその両方にするかを選択します。</span><span class="sxs-lookup"><span data-stu-id="be37a-p116">You can **Create an alert for each matching event with the policy's severity** and set an alert limit. Select whether you want the alert as an email, a text message, or both.</span></span>

## <a name="monitor-all-activities"></a><span data-ttu-id="be37a-173">すべてのアクティビティを監視する</span><span class="sxs-lookup"><span data-stu-id="be37a-173">Monitor all activities</span></span>

<span data-ttu-id="be37a-p117">セッションポリシーを作成すると、ポリシーに一致する各ユーザーセッションが、アプリではなく、セッションコントロールにリダイレクトされます。ユーザーには、監視に関する通知が表示され、セッションが監視されていることを知らせることができます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p117">When you create a session policy, each user session that matches the policy is redirected to session control rather than to the app directly. The user will see a monitoring notice to let them know that their sessions are being monitored.</span></span>

<span data-ttu-id="be37a-176">監視されていることをユーザーに通知しない場合は、通知メッセージを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="be37a-176">If you don't want to notify the user that they're being monitored, you can disable the notification message.</span></span>

1. <span data-ttu-id="be37a-177">[設定 cog で、[ **全般設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be37a-177">Under the settings cog, select **General settings**.</span></span>

2. <span data-ttu-id="be37a-178">次に、[ **条件付きアクセスアプリコントロール** ] の [ **ユーザーの監視** ] を選択し、[ **ユーザー** に通知する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="be37a-178">Then, under **Conditional Access App Control** select **User monitoring** and unselect the **Notify users** checkbox.</span></span>

<span data-ttu-id="be37a-p118">ユーザーをセッション内に保持するために、条件付きアクセスアプリコントロールは、アプリセッション内の関連するすべての url、Java スクリプト、cookie を Office 365 Cloud App Security url に置き換えます。たとえば、アプリで、ドメインが`myapp.com`終わるリンクを含むページが返された場合、条件付きアクセスアプリの制御によって、最後`myapp.com.us.cas.ms`のリンクが次のようなドメインに置き換えられます。このようにすると、Office 365 Cloud App Security によってセッション全体が監視されます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p118">To keep the user within the session, Conditional Access App Control replaces all the relevant URLs, Java scripts, and cookies within the app session with Office 365 Cloud App Security URLs. For example, if the app returns a page with links whose domains ends with `myapp.com`, Conditional Access App Control replaces the links with domains ending with something like `myapp.com.us.cas.ms`. This way the entire session is monitored by Office 365 Cloud App Security.</span></span>

<span data-ttu-id="be37a-p119">Conditional Access App Control は、それを経由してルーティングされるすべてのユーザーセッションのトラフィックログを記録します。トラフィックログには、時間、IP、ユーザーエージェント、アクセスした url、アップロードおよびダウンロードされたバイト数が含まれます。これらのログが分析され、継続的なレポートである **cloud App Security Conditional Access App Control**が、クラウド探索ダッシュボードのクラウド検出レポートの一覧に追加されます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p119">Conditional Access App Control records the traffic logs of every user session that is routed through it. The traffic logs include the time, IP, user agent, URLs visited, and the number of bytes uploaded and downloaded. These logs are analyzed and a continuous report, **Cloud App Security Conditional Access App Control**, is added to the list of Cloud Discovery reports in the Cloud Discovery dashboard.</span></span>

### <a name="to-export-these-logs"></a><span data-ttu-id="be37a-185">これらのログをエクスポートするには</span><span class="sxs-lookup"><span data-stu-id="be37a-185">To export these logs:</span></span>

1. <span data-ttu-id="be37a-186">[設定] cog に移動し、[ **条件付きアクセスアプリコントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be37a-186">Go to the settings cog and click **Conditional Access App Control**.</span></span>

2. <span data-ttu-id="be37a-187">表の右側で、[エクスポート] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="be37a-187">On the right side of the table, click the export button.</span></span><br>![[エクスポート] ボタン](media/image3.png)<br>

3. <span data-ttu-id="be37a-p120">レポートの範囲を選択し、[ **エクスポート**] をクリックします。この処理には時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="be37a-p120">Select the range of the report and click **Export**. This process may take some time.</span></span>

### <a name="to-download-the-exported-log"></a><span data-ttu-id="be37a-191">エクスポートされたログをダウンロードするには:</span><span class="sxs-lookup"><span data-stu-id="be37a-191">To download the exported log:</span></span>

1. <span data-ttu-id="be37a-192">レポートの準備が整ったら、[ **設定** ] に移動し、[ **レポートのエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be37a-192">After the report is ready, go to **Settings** and then **Exported reports**.</span></span>

2. <span data-ttu-id="be37a-193">表で、 **条件付きアクセスアプリコントロールのトラフィックログ** の一覧から関連するレポートを選択し、[ダウンロード] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="be37a-193">In the table, select the relevant report from the list of **Conditional Access App Control traffic logs** and click download.</span></span><br><span data-ttu-id="be37a-194">![[ダウンロード] ボタン](media/image4.png)</span><span class="sxs-lookup"><span data-stu-id="be37a-194">![download button](media/image4.png)</span></span><br>

## <a name="block-all-downloads"></a><span data-ttu-id="be37a-195">すべてのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="be37a-195">Block all downloads</span></span>

<span data-ttu-id="be37a-p121">Cloud App Security セッションポリシーで実行する **アクション** として **Block** が設定されている場合、条件付きアクセスアプリコントロールは、ポリシーのファイルフィルターごとにファイルをダウンロードすることを禁止します。ダウンロードイベントは、ユーザーがダウンロードを開始したときに、各アプリの Office 365 Cloud app Security で認識されます。intervenes が実行されないようにするために、条件付きアクセスアプリコントロールがリアルタイムで有効になります。ユーザーがダウンロードを開始したことを示すシグナルを受信すると、条件付きアクセスアプリコントロールは **ダウンロード制限** 付きメッセージをユーザーに返し、ダウンロードしたファイルをテキストファイルに置き換えます。ユーザーへのテキストファイルのメッセージは、セッションポリシーから構成およびカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="be37a-p121">When **Block** is set as the **Action** you want to take in the Cloud App Security session policy, Conditional Access App Control prevents a user from downloading a file per the policy’s file filters. A download event is recognized by Office 365 Cloud App Security for each app when a user starts a download. Conditional Access App Control intervenes in real time to prevent it from running. When the signal is received that a user has initiated a download, Conditional Access App Control returns a **Download restricted** message to the user and replaces the downloaded file with a text file. The text file's message to the user can be configured and customized from the session policy.</span></span>

## <a name="block-specific-activities"></a><span data-ttu-id="be37a-201">特定のアクティビティをブロックする</span><span class="sxs-lookup"><span data-stu-id="be37a-201">Block specific activities</span></span>

<span data-ttu-id="be37a-p122">[ **ブロック] アクティビティ** がアクティビティの **種類**として設定されている場合は、特定のアプリでブロックする特定のアクティビティを選択できます。選択したアプリのすべてのアクティビティが監視され、アクティビティログに報告されます。[ **禁止** ] アクションを選択すると、選択した特定のアクティビティはブロックされます。選択した特定のアクティビティでは、[ **テスト**] アクションを選択して通知を有効にした場合に警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="be37a-p122">When **Block activities** is set as the **Activity type**, you can select specific activities to block in specific apps. All activities from selected apps will be monitored and reported in the Activity log. The specific activities you select will be blocked if you select the **Block** action. The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="be37a-206">**特定のアクティビティ** をブロックし、特定のグループに適用して、組織のために包括的な読み取り専用モードを作成します。</span><span class="sxs-lookup"><span data-stu-id="be37a-206">**Block specific activities** and apply it to specific groups to create a comprehensive read-only mode for your organization.</span></span>

## <a name="protect-files-on-download"></a><span data-ttu-id="be37a-207">ダウンロード時にファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="be37a-207">Protect files on download</span></span>

<span data-ttu-id="be37a-p123">[ \*\*\*\* アクティビティをブロックする] を選択して特定のアクティビティをブロックします。これは、 **アクティビティの種類** のフィルターを使用して確認できます。選択したアプリのすべてのアクティビティが監視され、アクティビティログに報告されます。[ **禁止** ] アクションを選択すると、選択した特定のアクティビティはブロックされます。選択した特定のアクティビティでは、[ **テスト** ] アクションを選択して通知を有効にした場合に警告が発生します。</span><span class="sxs-lookup"><span data-stu-id="be37a-p123">Select **Block activities** to block specific activities, which you can find using the **Activity type** filter. All activities from selected apps will be monitored (and reported in the Activity log). The specific activities you select will be blocked if you select the **Block** action. The specific activities you selected will raise alerts if you select the **Test** action and have alerts turned on.</span></span>

<span data-ttu-id="be37a-p124">Cloud App Security セッションポリシーで行われる **アクション** として **保護** が設定されている場合、条件付きアクセスアプリコントロールは、ポリシーのファイルフィルターごとに、ファイルのラベル付けとその後の保護を適用します。クラウドアプリのセキュリティポリシーにオプションとして表示されるようにするには、Azure Information Protection コンソールでラベルを構成し、ラベル内で **保護** を選択する必要があります。ラベルが選択されているときに、Cloud App Security ポリシーの条件に一致するファイルがダウンロードされると、ラベルと対応する保護 (アクセス許可あり) がダウンロード時にファイルに適用されます。ダウンロードしたファイルが保護されている間、元のファイルはクラウドアプリにそのまま残ります。ファイルにアクセスしようとするユーザーは、保護が適用されているアクセス許可の要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="be37a-p124">When **Protect** is set as the **Action** to be taken in the Cloud App Security session policy, Conditional Access App Control enforces the labeling and subsequent protection of a file per the policy’s file filters. Labels are configured in the Azure Information Protection console and **Protect** must be selected within the label for it to appear as an option in the Cloud App Security policy. When a label is selected, and a file is downloaded that meets the criteria of the Cloud App Security policy, the label, and corresponding protection (with permissions) is applied to the file upon download. The original file remains as-is in the cloud app while the downloaded file is now protected. Users who try to access the file must meet the permission requirements determined by the protection applied.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be37a-217">次の手順</span><span class="sxs-lookup"><span data-stu-id="be37a-217">Next steps</span></span>

- [<span data-ttu-id="be37a-218">Office 365 Cloud App Security のアクセスポリシーについて</span><span class="sxs-lookup"><span data-stu-id="be37a-218">Learn about access policies in Office 365 Cloud App Security</span></span>](ocas-access-policies.md)

- [<span data-ttu-id="be37a-219">Azure AD の条件付きアクセスアプリコントロール機能を使用して、非管理対象デバイスのダウンロードをブロックする</span><span class="sxs-lookup"><span data-stu-id="be37a-219">Blocking downloads on unmanaged devices using Azure AD Conditional Access App Control capabilities</span></span>](https://docs.microsoft.com/en-us/cloud-app-security/use-case-proxy-block-session-aad)

