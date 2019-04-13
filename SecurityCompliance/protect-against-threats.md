---
title: Office 365 で脅威から保護する
ms.author: tracyp
author: msfttracyp
manager: laurawi
ms.audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: この記事は、すぐに脅威保護機能を構成するためのガイドとして使用してください。
ms.openlocfilehash: c651c13d5aacf1a7f95a93cacf5030e8ade4b8fd
ms.sourcegitcommit: 895f67531f2b4afe46c7487ca5b44555ca791bae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "31836831"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="e915d-103">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="e915d-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="e915d-104">Office 365 には、さまざまな脅威保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e915d-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="e915d-105">ここでは、組織に対して脅威保護機能がセットアップされていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。</span><span class="sxs-lookup"><span data-stu-id="e915d-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="e915d-106">Office 365 の脅威保護機能を初めて使用する場合や、どこから始めるべきかがわからない場合は、次のガイドを出発点としてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="e915d-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e915d-107">**ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。</span><span class="sxs-lookup"><span data-stu-id="e915d-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="e915d-108">使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="e915d-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e915d-109">前提条件</span><span class="sxs-lookup"><span data-stu-id="e915d-109">Prerequisites</span></span>

<span data-ttu-id="e915d-110">[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)でポリシーを構成するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e915d-110">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="e915d-111">次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="e915d-111">The following table includes some examples:</span></span> 

|<span data-ttu-id="e915d-112">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="e915d-112">Role or role group</span></span>  |<span data-ttu-id="e915d-113">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e915d-113">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="e915d-114">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="e915d-114">Office 365 Global Administrator</span></span> |[<span data-ttu-id="e915d-115">Office 365 の管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="e915d-115">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="e915d-116">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e915d-116">Security Administrator</span></span> |[<span data-ttu-id="e915d-117">Azure Active Directory での管理者の役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e915d-117">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="e915d-118">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="e915d-118">Exchange Online Organization Management</span></span> |[<span data-ttu-id="e915d-119">Exchange Online でのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e915d-119">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="e915d-120">および</span><span class="sxs-lookup"><span data-stu-id="e915d-120">and</span></span><br> [<span data-ttu-id="e915d-121">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e915d-121">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="e915d-122">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-122">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="e915d-123">パート 1-マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="e915d-123">Part 1 - Anti-malware</span></span>

<span data-ttu-id="e915d-124">[Exchange Online protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) を含むサブスクリプションでは、マルウェア対策保護を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e915d-124">Anti-malware protection is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="e915d-125">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > の**マルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-125">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>
2. <span data-ttu-id="e915d-126">[**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-126">Double-click the **Default** policy, and then choose **settings**.</span></span>
3. <span data-ttu-id="e915d-127">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-127">Specify the following settings:</span></span>
    - <span data-ttu-id="e915d-128">[**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="e915d-128">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
    - <span data-ttu-id="e915d-129">[**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-129">In the **Common Attachment Types Filter** section, choose **On**.</span></span>
4. <span data-ttu-id="e915d-130">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-130">Click **Save**.</span></span>

<span data-ttu-id="e915d-131">マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-131">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="e915d-132">パート 2-0 日の保護</span><span class="sxs-lookup"><span data-stu-id="e915d-132">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="e915d-133">ゼロ日の保護は、 [Office 365 Advanced Threat protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) を含むサブスクリプションで利用でき、 [atp の安全なリンク](atp-safe-links.md)と atp の安全な[添付ファイル](atp-safe-attachments.md)ポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="e915d-133">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Links](atp-safe-links.md) and [ATP Safe Attachments](atp-safe-attachments.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="e915d-134">ATP の安全な添付ファイルポリシー</span><span class="sxs-lookup"><span data-stu-id="e915d-134">ATP Safe Attachments policies</span></span>

1. <span data-ttu-id="e915d-135">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP 安全添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-135">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>
2. <span data-ttu-id="e915d-136">[ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-136">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>
3. <span data-ttu-id="e915d-137">[**電子メールの添付ファイルを保護**する] セクションで**+**、プラス記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-137">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>
4. <span data-ttu-id="e915d-138">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-138">Specify the following settings:</span></span>
    - <span data-ttu-id="e915d-139">[**名前**] ボックスに「 `Block malware`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="e915d-139">In the **Name** box, type `Block malware`.</span></span>
    - <span data-ttu-id="e915d-140">[応答] セクションで、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-140">In the response section, choose **Block**.</span></span>
    - <span data-ttu-id="e915d-141">[**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-141">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>
    - <span data-ttu-id="e915d-142">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-142">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="e915d-143">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-143">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
5. <span data-ttu-id="e915d-144">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-144">Click **Save**.</span></span>
6. <span data-ttu-id="e915d-145">(推奨の追加手順)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行して、Office 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-145">(Recommended additional step) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="e915d-146">(これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。</span><span class="sxs-lookup"><span data-stu-id="e915d-146">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="e915d-147">詳細については、「 [office 365 の atp の安全な添付ファイルのポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」および「 [SharePoint、OneDrive、Microsoft Teams 用の office 365 ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-147">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="e915d-148">ATP の安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="e915d-148">ATP Safe Links policies</span></span>

<span data-ttu-id="e915d-149">ATP の安全なリンクを設定するには、既定のポリシーを確認し、ポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e915d-149">To set up ATP Safe Links, review your default policy and add a policy.</span></span>

1. <span data-ttu-id="e915d-150">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP セーフリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-150">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>
2. <span data-ttu-id="e915d-151">[**既定**のポリシー] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-151">Double-click the **Default** policy.</span></span>
3. <span data-ttu-id="e915d-152">[**安全なリンクの使用**] セクションで、[ **office 365 ProPlus、office for iOS**、および Android] オプションをオンにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-152">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>
4. <span data-ttu-id="e915d-153">[**特定の受信者に適用されるポリシー** ] セクションで、プラス**+** 記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-153">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>
5. <span data-ttu-id="e915d-154">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-154">Specify the following settings:</span></span>
    - <span data-ttu-id="e915d-155">[**名前**] ボックスに、などの名前を入力`Safe Links`します。</span><span class="sxs-lookup"><span data-stu-id="e915d-155">In the **Name** box, type a name, such as `Safe Links`.</span></span>
    - <span data-ttu-id="e915d-156">**[アクションの選択**] セクションで、[**オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-156">In the **Select the action** section, choose **On**.</span></span>
    - <span data-ttu-id="e915d-157">次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-157">Select these options:</span></span>
        - <span data-ttu-id="e915d-158">**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="e915d-158">**Use safe attachments to scan downloadable content**</span></span> 
        - <span data-ttu-id="e915d-159">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="e915d-159">**Apply safe links to email messages sent within the organization**</span></span>
        - <span data-ttu-id="e915d-160">**ユーザーが元の URL への安全なリンクをクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="e915d-160">**Do not let users click through safe links to original URL**</span></span>
    - <span data-ttu-id="e915d-161">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-161">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="e915d-162">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-162">Then, select your domain, choose **Add**, and then click **OK**.</span></span>
6. <span data-ttu-id="e915d-163">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-163">Click **Save**.</span></span>

<span data-ttu-id="e915d-164">詳細については、「 [Office 365 ATP 安全リンクポリシー](set-up-atp-safe-links-policies.md)のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-164">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="e915d-165">パート 3-フィッシング対策</span><span class="sxs-lookup"><span data-stu-id="e915d-165">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="e915d-166">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションでは、フィッシング対策保護を利用できます。</span><span class="sxs-lookup"><span data-stu-id="e915d-166">Anti-phishing protection is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="e915d-167">高度なフィッシング対策を[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e915d-167">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="e915d-168">次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e915d-168">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="e915d-169">この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。</span><span class="sxs-lookup"><span data-stu-id="e915d-169">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="e915d-170">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-170">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>
2. <span data-ttu-id="e915d-171">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-171">Click **Default policy**.</span></span>
3. <span data-ttu-id="e915d-172">[**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-172">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>
    -  <span data-ttu-id="e915d-173">[**保護するユーザーの追加**] タブで、[保護] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="e915d-173">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="e915d-174">次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="e915d-174">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="e915d-175">(個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)</span><span class="sxs-lookup"><span data-stu-id="e915d-175">(You can type an individual email address, or click to display a list.)</span></span>
    - <span data-ttu-id="e915d-176">[**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。</span><span class="sxs-lookup"><span data-stu-id="e915d-176">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="e915d-177">カスタムドメインがある場合は、それらも追加します。</span><span class="sxs-lookup"><span data-stu-id="e915d-177">If you have custom domains, add those as well.</span></span>
    - <span data-ttu-id="e915d-178">[**操作**] タブで、[**受信者の迷惑メールフォルダーにメッセージを移動する**] を選択して、偽装されたユーザーと偽装ドメインの両方を選択し、安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="e915d-178">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>
    - <span data-ttu-id="e915d-179">[**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e915d-179">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>
    - <span data-ttu-id="e915d-180">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-180">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>
4. <span data-ttu-id="e915d-181">[**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-181">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>
    - <span data-ttu-id="e915d-182">[**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e915d-182">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>
    - <span data-ttu-id="e915d-183">[**操作**] タブで、[受信者の迷惑メールフォルダーにメッセージを移動する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-183">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>
    - <span data-ttu-id="e915d-184">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-184">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="e915d-185">(変更を行っていない場合は、[**キャンセル**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="e915d-185">(If you didn't make any changes, click **Cancel**.)</span></span>
5. <span data-ttu-id="e915d-186">[既定のポリシー設定] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="e915d-186">Close the default policy settings page.</span></span>

<span data-ttu-id="e915d-187">フィッシング対策ポリシーオプションの詳細については、「 [Office 365 の ATP のフィッシング対策およびフィッシング対策ポリシー](set-up-anti-phishing-policies.md)をセットアップする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-187">To learn more about your anti-phishing policy options, see [Set up Office 365 ATP anti-phishing and anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="e915d-188">パート 4-スパム対策</span><span class="sxs-lookup"><span data-stu-id="e915d-188">Part 4 - Anti-spam</span></span>

<span data-ttu-id="e915d-189">スパム対策保護は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e915d-189">Anti-spam protection is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="e915d-190">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > のスパム**対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e915d-190">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>
2. <span data-ttu-id="e915d-191">[**カスタム**] タブで、[**カスタム設定**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="e915d-191">On the **Custom** tab, turn **Custom settings** on.</span></span>
3. <span data-ttu-id="e915d-192">[**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-192">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>
    - <span data-ttu-id="e915d-193">[**スパムと一括操作**] セクションで、しきい値を5または6に設定します。</span><span class="sxs-lookup"><span data-stu-id="e915d-193">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>
    - <span data-ttu-id="e915d-194">[**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="e915d-194">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>
4. <span data-ttu-id="e915d-195">[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e915d-195">Click **Save**.</span></span>

<span data-ttu-id="e915d-196">スパム対策ポリシーオプションの詳細については、「[スパム対策](configure-the-anti-spam-policies.md)ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-196">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="e915d-197">パート 5-サービスレベルの設定</span><span class="sxs-lookup"><span data-stu-id="e915d-197">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="e915d-198">ゼロ時間自動削除</span><span class="sxs-lookup"><span data-stu-id="e915d-198">Zero-hour auto purge</span></span>

<span data-ttu-id="e915d-199">ゼロ時間自動削除 (ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e915d-199">Zero-hour auto purge (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="e915d-200">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e915d-200">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>
- <span data-ttu-id="e915d-201">スパム対策ポリシーで、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="e915d-201">Spam actions are set to **Move message to Junk Email folder** in anti-spam policies.</span></span>
- <span data-ttu-id="e915d-202">ユーザーが既定の迷惑メール設定を保持していて、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="e915d-202">Users have kept their default junk email settings, and have not turned off junk email protection.</span></span>

<span data-ttu-id="e915d-203">詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-203">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="e915d-204">監査ログ</span><span class="sxs-lookup"><span data-stu-id="e915d-204">Audit logging</span></span>

<span data-ttu-id="e915d-205">監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="e915d-205">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="e915d-206">[セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](use-explorer-in-security-and-compliance.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e915d-206">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="e915d-207">詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-207">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="e915d-208">セットアップ後のタスク</span><span class="sxs-lookup"><span data-stu-id="e915d-208">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="e915d-209">新機能とサービス更新を見る</span><span class="sxs-lookup"><span data-stu-id="e915d-209">Watch for new features and service updates</span></span>

- [<span data-ttu-id="e915d-210">Microsoft 365 ロードマップにアクセスする</span><span class="sxs-lookup"><span data-stu-id="e915d-210">Visit the Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="e915d-211">Office 365 Advanced Threat Protection サービスの説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e915d-211">See the Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)

### <a name="see-how-atp-is-working-for-your-organization"></a><span data-ttu-id="e915d-212">組織に対して ATP がどのように機能するかを確認する</span><span class="sxs-lookup"><span data-stu-id="e915d-212">See how ATP is working for your organization</span></span>

- [<span data-ttu-id="e915d-213">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="e915d-213">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="e915d-214">セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="e915d-214">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)

### <a name="periodically-review-and-revise-your-atp-policies"></a><span data-ttu-id="e915d-215">ATP ポリシーの定期的なレビューと改訂</span><span class="sxs-lookup"><span data-stu-id="e915d-215">Periodically review and revise your ATP policies</span></span>

- [<span data-ttu-id="e915d-216">office 365 ユーザーの office 365 の脅威の調査と応答を安全に保つ</span><span class="sxs-lookup"><span data-stu-id="e915d-216">Keep your Office 365 users safe with Office 365 threat investigation and response</span></span>](keep-users-safe-with-office-365-ti.md) 

- [<span data-ttu-id="e915d-217">Office 365 セキュリティ&amp; /コンプライアンスセンターのスマートレポートと分析情報を使用する</span><span class="sxs-lookup"><span data-stu-id="e915d-217">Use the smart reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 