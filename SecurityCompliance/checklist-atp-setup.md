---
title: 'クイックスタート: Office 365 Advanced Threat Protection のセットアップ'
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 次のクイックスタートガイドを使用して、Office 365 Advanced Threat Protection (ATP) が組織に合わせて設定および構成されていることを確認できます。
ms.openlocfilehash: 5aecbdb63f30a620812de44907b29dcae838ba36
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693300"
---
# <a name="quick-start-guide-set-up-office-365-advanced-threat-protection"></a><span data-ttu-id="b570a-103">クイックスタートガイド: Office 365 Advanced Threat Protection のセットアップ</span><span class="sxs-lookup"><span data-stu-id="b570a-103">Quick Start Guide: Set up Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="b570a-104">ここでは、Office 365 Advanced Threat Protection (ATP) が組織に対して設定されていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。</span><span class="sxs-lookup"><span data-stu-id="b570a-104">Here's a quick-start guide you can use as a checklist to make sure Office 365 Advanced Threat Protection (ATP) is set up for your organization.</span></span> <span data-ttu-id="b570a-105">Office 365 で脅威を保護するのが初めての場合、またはどこから始めるべきかがわからない場合は、次のガイダンスを出発点としてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="b570a-105">If you're new to threat protection in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b570a-106">**ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。</span><span class="sxs-lookup"><span data-stu-id="b570a-106">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="b570a-107">使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="b570a-107">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b570a-108">前提条件</span><span class="sxs-lookup"><span data-stu-id="b570a-108">Prerequisites</span></span>

- <span data-ttu-id="b570a-109">組織には、 [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) を含むサブスクリプションが必要です。</span><span class="sxs-lookup"><span data-stu-id="b570a-109">Your organization must have a subscription that includes [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).</span></span>

- <span data-ttu-id="b570a-110">ATP 機能にアクセスするには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b570a-110">You must be assigned an appropriate role to access ATP features.</span></span> <span data-ttu-id="b570a-111">次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="b570a-111">The following table includes some examples:</span></span> 

    |<span data-ttu-id="b570a-112">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="b570a-112">Role or role group</span></span>  |<span data-ttu-id="b570a-113">詳細情報</span><span class="sxs-lookup"><span data-stu-id="b570a-113">Where to learn more</span></span>  |
    |---------|---------|
    |<span data-ttu-id="b570a-114">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="b570a-114">Office 365 Global Administrator</span></span> |[<span data-ttu-id="b570a-115">Office 365 の管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="b570a-115">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
    |<span data-ttu-id="b570a-116">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="b570a-116">Security Administrator</span></span> |[<span data-ttu-id="b570a-117">Azure Active Directory での管理者の役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b570a-117">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
    |<span data-ttu-id="b570a-118">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="b570a-118">Exchange Online Organization Management</span></span> |[<span data-ttu-id="b570a-119">Exchange Online でのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="b570a-119">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="b570a-120">および</span><span class="sxs-lookup"><span data-stu-id="b570a-120">and</span></span><br> [<span data-ttu-id="b570a-121">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="b570a-121">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

    <span data-ttu-id="b570a-122">( [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可を](permissions-in-the-security-and-compliance-center.md)参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b570a-122">(See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="b570a-123">パート 1-マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="b570a-123">Part 1 - Anti-malware</span></span>

1. <span data-ttu-id="b570a-124">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > の**マルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-124">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>
2. <span data-ttu-id="b570a-125">[**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-125">Double-click the **Default** policy, and then choose **settings**.</span></span>
3. <span data-ttu-id="b570a-126">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-126">Specify the following settings:</span></span>
    - <span data-ttu-id="b570a-127">[**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="b570a-127">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
    - <span data-ttu-id="b570a-128">[**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-128">In the **Common Attachment Types Filter** section, choose **On**.</span></span>
4. <span data-ttu-id="b570a-129">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-129">Click **Save**.</span></span>

<span data-ttu-id="b570a-130">マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-130">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="b570a-131">パート 2-0 日の保護</span><span class="sxs-lookup"><span data-stu-id="b570a-131">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="b570a-132">ゼロ日の保護は、ATP の安全なリンクや安全な添付ファイルのポリシーなどのポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="b570a-132">Zero-day protection is set up through policies, such as ATP Safe Links and Safe Attachments policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="b570a-133">ATP の安全な添付ファイルポリシー</span><span class="sxs-lookup"><span data-stu-id="b570a-133">ATP Safe Attachments policies</span></span>

1. <span data-ttu-id="b570a-134">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP 安全添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-134">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>
2. <span data-ttu-id="b570a-135">[ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-135">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
3. <span data-ttu-id="b570a-136">[**電子メールの添付ファイルを保護**する] セクションで**+**、プラス記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-136">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>
4. <span data-ttu-id="b570a-137">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-137">Specify the following settings:</span></span>
    - <span data-ttu-id="b570a-138">[**名前**] ボックスに「 `Block malware`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="b570a-138">In the **Name** box, type `Block malware`.</span></span>
    - <span data-ttu-id="b570a-139">[応答] セクションで、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-139">In the response section, choose **Block**.</span></span>
    - <span data-ttu-id="b570a-140">[**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-140">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>
    - <span data-ttu-id="b570a-141">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-141">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="b570a-142">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-142">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
5. <span data-ttu-id="b570a-143">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-143">Click **Save**.</span></span>
6. <span data-ttu-id="b570a-144">(推奨の追加手順)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行して、Office 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-144">(Recommended additional step) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="b570a-145">(これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。</span><span class="sxs-lookup"><span data-stu-id="b570a-145">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="b570a-146">詳細については、「 [office 365 の atp の安全な添付ファイルのポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」および「 [SharePoint、OneDrive、Microsoft Teams 用の office 365 ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-146">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="b570a-147">ATP の安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="b570a-147">ATP Safe Links policies</span></span>

<span data-ttu-id="b570a-148">ATP の安全なリンクを設定するには、既定のポリシーを確認し、ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b570a-148">To set up ATP Safe Links, review your default policy and add a policy.</span></span>

1. <span data-ttu-id="b570a-149">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP セーフリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-149">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>
2. <span data-ttu-id="b570a-150">[**既定**のポリシー] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-150">Double-click the **Default** policy.</span></span>
3. <span data-ttu-id="b570a-151">[**安全なリンクの使用**] セクションで、[ **office 365 ProPlus、office for iOS**、および Android] オプションをオンにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-151">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>
4. <span data-ttu-id="b570a-152">[**特定の受信者に適用されるポリシー** ] セクションで、プラス**+** 記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-152">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>
5. <span data-ttu-id="b570a-153">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-153">Specify the following settings:</span></span>
    - <span data-ttu-id="b570a-154">[**名前**] ボックスに、などの名前を入力`Safe Links`します。</span><span class="sxs-lookup"><span data-stu-id="b570a-154">In the **Name** box, type a name, such as `Safe Links`.</span></span>
    - <span data-ttu-id="b570a-155">**[アクションの選択**] セクションで、[**オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-155">In the **Select the action** section, choose **On**.</span></span>
    - <span data-ttu-id="b570a-156">次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-156">Select these options:</span></span>
        - <span data-ttu-id="b570a-157">**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="b570a-157">**Use safe attachments to scan downloadable content**</span></span> 
        - <span data-ttu-id="b570a-158">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="b570a-158">**Apply safe links to email messages sent within the organization**</span></span>
        - <span data-ttu-id="b570a-159">**ユーザーが元の URL への安全なリンクをクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="b570a-159">**Do not let users click through safe links to original URL**</span></span>
    - <span data-ttu-id="b570a-160">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-160">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="b570a-161">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-161">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
6. <span data-ttu-id="b570a-162">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-162">Click **Save**.</span></span>

<span data-ttu-id="b570a-163">詳細については、「 [Office 365 ATP 安全リンクポリシー](set-up-atp-safe-links-policies.md)のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-163">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="b570a-164">パート 3-フィッシング対策</span><span class="sxs-lookup"><span data-stu-id="b570a-164">Part 3 - Anti-phishing</span></span> 

1. <span data-ttu-id="b570a-165">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-165">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>
2. <span data-ttu-id="b570a-166">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-166">Click **Default policy**.</span></span>
3. <span data-ttu-id="b570a-167">[**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-167">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>
    -  <span data-ttu-id="b570a-168">[**保護するユーザーの追加**] タブで、[保護] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="b570a-168">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="b570a-169">次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="b570a-169">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="b570a-170">(個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)</span><span class="sxs-lookup"><span data-stu-id="b570a-170">(You can type an individual email address, or click to display a list.)</span></span>
    - <span data-ttu-id="b570a-171">[**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。</span><span class="sxs-lookup"><span data-stu-id="b570a-171">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="b570a-172">カスタムドメインがある場合は、それらも追加します。</span><span class="sxs-lookup"><span data-stu-id="b570a-172">If you have custom domains, add those as well.</span></span>
    - <span data-ttu-id="b570a-173">[**操作**] タブで、[**受信者の迷惑メールフォルダーにメッセージを移動する**] を選択して、偽装されたユーザーと偽装ドメインの両方を選択し、安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b570a-173">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>
    - <span data-ttu-id="b570a-174">[**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b570a-174">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>
    - <span data-ttu-id="b570a-175">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-175">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>
4. <span data-ttu-id="b570a-176">[**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-176">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>
    - <span data-ttu-id="b570a-177">[**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b570a-177">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>
    - <span data-ttu-id="b570a-178">[**操作**] タブで、[受信者の迷惑メールフォルダーにメッセージを移動する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-178">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>
    - <span data-ttu-id="b570a-179">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-179">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="b570a-180">(変更を行っていない場合は、[**キャンセル**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="b570a-180">(If you didn't make any changes, click **Cancel**.)</span></span>
5. <span data-ttu-id="b570a-181">[既定のポリシー設定] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b570a-181">Close the default policy settings page.</span></span>

<span data-ttu-id="b570a-182">フィッシング対策ポリシーオプションの詳細については、「 [Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシー](set-up-anti-phishing-policies.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-182">To learn more about your anti-phishing policy options, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="b570a-183">パート 4-スパム対策</span><span class="sxs-lookup"><span data-stu-id="b570a-183">Part 4 - Anti-spam</span></span>

1. <span data-ttu-id="b570a-184">[Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > のスパム**対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b570a-184">In the [Office 365 Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>
2. <span data-ttu-id="b570a-185">[**カスタム**] タブで、[**カスタム設定**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="b570a-185">On the **Custom** tab, turn **Custom settings** on.</span></span>
3. <span data-ttu-id="b570a-186">[**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-186">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>
    - <span data-ttu-id="b570a-187">[**スパムと一括操作**] セクションで、しきい値を5または6に設定します。</span><span class="sxs-lookup"><span data-stu-id="b570a-187">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>
    - <span data-ttu-id="b570a-188">[**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="b570a-188">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>
4. <span data-ttu-id="b570a-189">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b570a-189">Click **Save**.</span></span>

<span data-ttu-id="b570a-190">スパム対策ポリシーオプションの詳細については、「[スパム対策](configure-the-anti-spam-policies.md)ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-190">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="b570a-191">パート 5-サービスレベルの設定</span><span class="sxs-lookup"><span data-stu-id="b570a-191">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="b570a-192">ゼロ時間自動削除</span><span class="sxs-lookup"><span data-stu-id="b570a-192">Zero-hour auto purge</span></span>

<span data-ttu-id="b570a-193">ゼロ時間自動削除 (ZAP) は既定でオンになっています。ただし、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="b570a-193">Zero-hour auto purge (ZAP) is turned on by default; however, the following conditions must be met:</span></span>
- <span data-ttu-id="b570a-194">スパム対策ポリシーで、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="b570a-194">Spam actions are set to **Move message to Junk Email folder** in anti-spam policies.</span></span>
- <span data-ttu-id="b570a-195">ユーザーが既定の迷惑メール設定を保持していて、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="b570a-195">Users have kept their default junk email settings, and have not turned off junk email protection.</span></span>

<span data-ttu-id="b570a-196">詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-196">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="b570a-197">監査ログ</span><span class="sxs-lookup"><span data-stu-id="b570a-197">Audit logging</span></span>

<span data-ttu-id="b570a-198">[セキュリティダッシュボード](security-dashboard.md)や[エクスプローラー](use-explorer-in-security-and-compliance.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b570a-198">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md) and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span>

<span data-ttu-id="b570a-199">「 [Office 365 監査ログの検索をオンまたはオフにする」を](turn-audit-log-search-on-or-off.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-199">See [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="b570a-200">セットアップ後のタスク</span><span class="sxs-lookup"><span data-stu-id="b570a-200">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="b570a-201">新機能とサービス更新を見る</span><span class="sxs-lookup"><span data-stu-id="b570a-201">Watch for new features and service updates</span></span>

- [<span data-ttu-id="b570a-202">Microsoft 365 ロードマップにアクセスする</span><span class="sxs-lookup"><span data-stu-id="b570a-202">Visit the Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="b570a-203">Office 365 Advanced Threat Protection サービスの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b570a-203">See the Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a><span data-ttu-id="b570a-204">組織に対して ATP がどのように機能するかを確認する</span><span class="sxs-lookup"><span data-stu-id="b570a-204">See how ATP is working for your organization</span></span>

- [<span data-ttu-id="b570a-205">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="b570a-205">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="b570a-206">セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="b570a-206">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a><span data-ttu-id="b570a-207">ATP ポリシーの定期的なレビューと改訂</span><span class="sxs-lookup"><span data-stu-id="b570a-207">Periodically review and revise your ATP policies</span></span>

- [<span data-ttu-id="b570a-208">office 365 ユーザーの office 365 の脅威の調査と応答を安全に保つ</span><span class="sxs-lookup"><span data-stu-id="b570a-208">Keep your Office 365 users safe with Office 365 threat investigation and response</span></span>](keep-users-safe-with-office-365-ti.md) 

- [<span data-ttu-id="b570a-209">Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと分析情報を使用する</span><span class="sxs-lookup"><span data-stu-id="b570a-209">Use the smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 