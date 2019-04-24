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
description: この記事をガイドとして使用して、今すぐ脅威保護機能を構成します。
ms.openlocfilehash: 065071999130f209d63bcafc09ad72daceceac04
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261635"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="eb759-103">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="eb759-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="eb759-104">Office 365 には、さまざまな脅威保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb759-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="eb759-105">ここでは、組織に対して脅威保護機能がセットアップされていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。</span><span class="sxs-lookup"><span data-stu-id="eb759-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="eb759-106">Office 365 の脅威保護機能を初めて使用する場合や、どこから始めるべきかがわからない場合は、次のガイドを出発点としてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="eb759-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="eb759-107">**ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。</span><span class="sxs-lookup"><span data-stu-id="eb759-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="eb759-108">使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="eb759-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="eb759-109">要件</span><span class="sxs-lookup"><span data-stu-id="eb759-109">Requirements</span></span>

### <a name="licenses"></a><span data-ttu-id="eb759-110">ライセンス</span><span class="sxs-lookup"><span data-stu-id="eb759-110">Licenses</span></span>

<span data-ttu-id="eb759-111">脅威保護機能は、すべての Office 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには、Office 365 advanced Threat Protection などの高度な機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="eb759-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features, such as those in Office 365 Advanced Threat Protection.</span></span> <span data-ttu-id="eb759-112">この記事では、各保護エリアのサブスクリプション要件を示します。</span><span class="sxs-lookup"><span data-stu-id="eb759-112">In this article we include subscription requirements for each protection area.</span></span>

<span data-ttu-id="eb759-113">脅威保護機能と subsriptions の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-113">To learn more about threat protection features and subsriptions, see the following resources:</span></span>
- [<span data-ttu-id="eb759-114">Office 365 Advanced Threat Protection サービスの説明</span><span class="sxs-lookup"><span data-stu-id="eb759-114">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)
- [<span data-ttu-id="eb759-115">Exchange Online Protection サービスの説明</span><span class="sxs-lookup"><span data-stu-id="eb759-115">Exchange Online Protection Service Description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)
- [<span data-ttu-id="eb759-116">Office 365 セキュリティ/コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="eb759-116">Office 365 Security & Compliance Center</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

### <a name="roles-and-permissions"></a><span data-ttu-id="eb759-117">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="eb759-117">Roles and permissions</span></span>

<span data-ttu-id="eb759-118">[セキュリティ & コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)でポリシーを構成するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb759-118">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="eb759-119">次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="eb759-119">The following table includes some examples:</span></span> 

|<span data-ttu-id="eb759-120">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="eb759-120">Role or role group</span></span>  |<span data-ttu-id="eb759-121">詳細情報</span><span class="sxs-lookup"><span data-stu-id="eb759-121">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="eb759-122">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="eb759-122">Office 365 Global Administrator</span></span> |[<span data-ttu-id="eb759-123">Office 365 の管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="eb759-123">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="eb759-124">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="eb759-124">Security Administrator</span></span> |[<span data-ttu-id="eb759-125">Azure Active Directory での管理者の役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb759-125">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="eb759-126">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="eb759-126">Exchange Online Organization Management</span></span> |[<span data-ttu-id="eb759-127">Exchange Online でのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="eb759-127">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="eb759-128">and</span><span class="sxs-lookup"><span data-stu-id="eb759-128">and</span></span><br> [<span data-ttu-id="eb759-129">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="eb759-129">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="eb759-130">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-130">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware"></a><span data-ttu-id="eb759-131">パート 1-マルウェア対策</span><span class="sxs-lookup"><span data-stu-id="eb759-131">Part 1 - Anti-malware</span></span>

<span data-ttu-id="eb759-132">[Exchange Online protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP) を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb759-132">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP).</span></span> 

1. <span data-ttu-id="eb759-133">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > の**マルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-133">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="eb759-134">[**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-134">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="eb759-135">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-135">Specify the following settings:</span></span>
    
    - <span data-ttu-id="eb759-136">[**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="eb759-136">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>
   
    - <span data-ttu-id="eb759-137">[**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-137">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="eb759-138">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-138">Click **Save**.</span></span>

<span data-ttu-id="eb759-139">マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-139">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---zero-day-protection"></a><span data-ttu-id="eb759-140">パート 2-0 日の保護</span><span class="sxs-lookup"><span data-stu-id="eb759-140">Part 2 - Zero-day protection</span></span>

<span data-ttu-id="eb759-141">ゼロ日の保護は、 [Office 365 Advanced Threat protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) を含むサブスクリプションで利用でき、 [atp の安全な添付ファイル](atp-safe-attachments.md)と[atp の安全なリンク](atp-safe-links.md)ポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="eb759-141">Zero-day protection is available in subscriptions that include [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="eb759-142">ATP の安全な添付ファイルポリシー</span><span class="sxs-lookup"><span data-stu-id="eb759-142">ATP Safe Attachments policies</span></span>

<span data-ttu-id="eb759-143">[atp の安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの atp の安全な添付ファイルポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb759-143">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="eb759-144">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP 安全添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-144">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="eb759-145">[ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-145">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="eb759-146">[**電子メールの添付ファイルを保護**する] セクションで**+**、プラス記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-146">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="eb759-147">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-147">Specify the following settings:</span></span>

    - <span data-ttu-id="eb759-148">[**名前**] ボックスに「 `Block malware`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="eb759-148">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="eb759-149">[応答] セクションで、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-149">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="eb759-150">[**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-150">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="eb759-151">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-151">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="eb759-152">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-152">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="eb759-153">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-153">Click **Save**.</span></span>

6. <span data-ttu-id="eb759-154">(**推奨の追加手順**)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行して、Office 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-154">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="eb759-155">(これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。</span><span class="sxs-lookup"><span data-stu-id="eb759-155">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="eb759-156">詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-156">To learn more, see:</span></span> 
- [<span data-ttu-id="eb759-157">Office 365 の ATP の安全な添付ファイルのポリシーを設定する</span><span class="sxs-lookup"><span data-stu-id="eb759-157">Set up Office 365 ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md)
- [<span data-ttu-id="eb759-158">SharePoint、OneDrive、Microsoft Teams の Office 365 ATP を有効にする</span><span class="sxs-lookup"><span data-stu-id="eb759-158">Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams</span></span>](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a><span data-ttu-id="eb759-159">ATP の安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="eb759-159">ATP Safe Links policies</span></span>

<span data-ttu-id="eb759-160">[ATP の安全なリンク](atp-safe-links.md)を設定するには、既定のポリシーを確認して編集し、特定のユーザーのポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb759-160">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="eb759-161">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP セーフリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-161">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="eb759-162">[**既定**のポリシー] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-162">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="eb759-163">[**安全なリンクの使用**] セクションで、[ **office 365 ProPlus、office for iOS**、および Android] オプションをオンにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-163">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="eb759-164">[**特定の受信者に適用されるポリシー** ] セクションで、プラス**+** 記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-164">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="eb759-165">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-165">Specify the following settings:</span></span>

    - <span data-ttu-id="eb759-166">[**名前**] ボックスに、などの名前を入力`Safe Links`します。</span><span class="sxs-lookup"><span data-stu-id="eb759-166">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="eb759-167">**[アクションの選択**] セクションで、[**オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-167">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="eb759-168">次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-168">Select these options:</span></span>

        - <span data-ttu-id="eb759-169">**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="eb759-169">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="eb759-170">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="eb759-170">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="eb759-171">**ユーザーが元の URL への安全なリンクをクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="eb759-171">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="eb759-172">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-172">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="eb759-173">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-173">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="eb759-174">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-174">Click **Save**.</span></span>

<span data-ttu-id="eb759-175">詳細については、「 [Office 365 ATP 安全リンクポリシー](set-up-atp-safe-links-policies.md)のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-175">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing"></a><span data-ttu-id="eb759-176">パート 3-フィッシング対策</span><span class="sxs-lookup"><span data-stu-id="eb759-176">Part 3 - Anti-phishing</span></span> 

<span data-ttu-id="eb759-177">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb759-177">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="eb759-178">高度なフィッシング対策を[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb759-178">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="eb759-179">次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb759-179">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="eb759-180">この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。</span><span class="sxs-lookup"><span data-stu-id="eb759-180">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="eb759-181">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-181">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="eb759-182">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-182">Click **Default policy**.</span></span>

3. <span data-ttu-id="eb759-183">[**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-183">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    -  <span data-ttu-id="eb759-184">[**保護するユーザーの追加**] タブで、[保護] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eb759-184">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="eb759-185">次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="eb759-185">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="eb759-186">(個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)</span><span class="sxs-lookup"><span data-stu-id="eb759-186">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="eb759-187">[**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。</span><span class="sxs-lookup"><span data-stu-id="eb759-187">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="eb759-188">カスタムドメインがある場合は、それらも追加します。</span><span class="sxs-lookup"><span data-stu-id="eb759-188">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="eb759-189">[**操作**] タブで、[**受信者の迷惑メールフォルダーにメッセージを移動する**] を選択して、偽装されたユーザーと偽装ドメインの両方を選択し、安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="eb759-189">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="eb759-190">[**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb759-190">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="eb759-191">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-191">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="eb759-192">[**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-192">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="eb759-193">[**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eb759-193">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="eb759-194">[**操作**] タブで、[受信者の迷惑メールフォルダーにメッセージを移動する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-194">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="eb759-195">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-195">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="eb759-196">(変更を行っていない場合は、[**キャンセル**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="eb759-196">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="eb759-197">[既定のポリシー設定] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="eb759-197">Close the default policy settings page.</span></span>

<span data-ttu-id="eb759-198">フィッシング対策ポリシーオプションの詳細については、「[フィッシング対策ポリシーの設定](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-198">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam"></a><span data-ttu-id="eb759-199">パート 4-スパム対策</span><span class="sxs-lookup"><span data-stu-id="eb759-199">Part 4 - Anti-spam</span></span>

<span data-ttu-id="eb759-200">[スパム対策保護](anti-spam-protection.md)は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb759-200">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="eb759-201">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > のスパム**対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="eb759-201">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="eb759-202">[**カスタム**] タブで、[**カスタム設定**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="eb759-202">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="eb759-203">[**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-203">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="eb759-204">[**スパムと一括操作**] セクションで、しきい値を5または6に設定します。</span><span class="sxs-lookup"><span data-stu-id="eb759-204">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="eb759-205">[**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="eb759-205">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="eb759-206">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="eb759-206">Click **Save**.</span></span>

<span data-ttu-id="eb759-207">スパム対策ポリシーオプションの詳細については、「[スパム対策](configure-the-anti-spam-policies.md)ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-207">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---service-wide-settings"></a><span data-ttu-id="eb759-208">パート 5-サービスレベルの設定</span><span class="sxs-lookup"><span data-stu-id="eb759-208">Part 5 - Service-wide settings</span></span>

### <a name="zero-hour-auto-purge"></a><span data-ttu-id="eb759-209">ゼロ時間自動削除</span><span class="sxs-lookup"><span data-stu-id="eb759-209">Zero-hour auto purge</span></span>

<span data-ttu-id="eb759-210">[ゼロ時間自動削除](zero-hour-auto-purge.md)(ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb759-210">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="eb759-211">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb759-211">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="eb759-212">スパム[対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="eb759-212">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="eb759-213">ユーザーが既定の[迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="eb759-213">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="eb759-214">詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-214">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging"></a><span data-ttu-id="eb759-215">監査ログ</span><span class="sxs-lookup"><span data-stu-id="eb759-215">Audit logging</span></span>

<span data-ttu-id="eb759-216">監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="eb759-216">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="eb759-217">[セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](use-explorer-in-security-and-compliance.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb759-217">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="eb759-218">詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-218">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="eb759-219">セットアップ後のタスク</span><span class="sxs-lookup"><span data-stu-id="eb759-219">Post-setup tasks</span></span>

### <a name="watch-for-new-features-and-service-updates"></a><span data-ttu-id="eb759-220">新機能とサービス更新を見る</span><span class="sxs-lookup"><span data-stu-id="eb759-220">Watch for new features and service updates</span></span>

- [<span data-ttu-id="eb759-221">標準または対象指定リリースオプションを設定する</span><span class="sxs-lookup"><span data-stu-id="eb759-221">Set up the Standard or Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)

- [<span data-ttu-id="eb759-222">メッセージセンターに移動して機能のアナウンスを表示する</span><span class="sxs-lookup"><span data-stu-id="eb759-222">Go to your Message center to view feature announcements</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide) 

- [<span data-ttu-id="eb759-223">新しい機能の状態を確認するには、Microsoft 365 ロードマップを参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb759-223">Visit the Microsoft 365 Roadmap to see status of new features</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)

- [<span data-ttu-id="eb759-224">Office 365 サービスの説明を確認する</span><span class="sxs-lookup"><span data-stu-id="eb759-224">Review the Office 365 Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)

### <a name="see-how-threat-protection-features-are-working-for-your-organization"></a><span data-ttu-id="eb759-225">組織に対して脅威保護機能がどのように機能しているかを確認する</span><span class="sxs-lookup"><span data-stu-id="eb759-225">See how threat protection features are working for your organization</span></span>

- [<span data-ttu-id="eb759-226">セキュリティダッシュボードにアクセスする</span><span class="sxs-lookup"><span data-stu-id="eb759-226">Visit your security dashboard</span></span>](security-dashboard.md)

- <span data-ttu-id="eb759-227">[Office 365 ATP](view-reports-for-atp.md)([エクスプローラー](use-explorer-in-security-and-compliance.md)を含む) のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="eb759-227">[View the reports for Office 365 ATP](view-reports-for-atp.md), including [Explorer](use-explorer-in-security-and-compliance.md)</span></span>

- [<span data-ttu-id="eb759-228">電子メールのセキュリティレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="eb759-228">View your email security reports</span></span>](view-email-security-reports.md)

### <a name="periodically-review-and-revise-your-threat-protection-policies"></a><span data-ttu-id="eb759-229">脅威保護ポリシーを定期的に見直し、改訂する</span><span class="sxs-lookup"><span data-stu-id="eb759-229">Periodically review and revise your threat protection policies</span></span>

- [<span data-ttu-id="eb759-230">セキュリティで保護されたスコアを確認する</span><span class="sxs-lookup"><span data-stu-id="eb759-230">Review your Secure Score</span></span>](microsoft-secure-score.md)

- [<span data-ttu-id="eb759-231">セキュリティ&amp; /コンプライアンスセンターのスマートレポートと分析情報を使用する</span><span class="sxs-lookup"><span data-stu-id="eb759-231">Use your smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md) 

- [<span data-ttu-id="eb759-232">Office 365 の脅威の調査と応答機能をユーザーに対して安全に保つ</span><span class="sxs-lookup"><span data-stu-id="eb759-232">Keep users safe with Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md) 
 