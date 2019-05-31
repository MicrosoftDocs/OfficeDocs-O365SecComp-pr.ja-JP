---
title: Office 365 で脅威から保護する
ms.author: tracyp
author: msfttracyp
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: この記事をガイドとして使用して、今すぐ脅威保護機能を構成します。
ms.openlocfilehash: 6700e2714ea607f675b487204404d53c1d51db93
ms.sourcegitcommit: 424a614141c1f19a1c84a67ec2d71dd3d7ef6694
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/30/2019
ms.locfileid: "34590580"
---
# <a name="protect-against-threats-in-office-365"></a><span data-ttu-id="00571-103">Office 365 で脅威から保護する</span><span class="sxs-lookup"><span data-stu-id="00571-103">Protect against threats in Office 365</span></span>

<span data-ttu-id="00571-104">Office 365 には、さまざまな脅威保護機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00571-104">Office 365 includes a variety of threat protection features.</span></span> <span data-ttu-id="00571-105">ここでは、組織に対して脅威保護機能がセットアップされていることを確認するためのチェックリストとして使用できる、クイックスタートガイドを紹介します。</span><span class="sxs-lookup"><span data-stu-id="00571-105">Here's a quick-start guide you can use as a checklist to make sure your threat protection features are set up for your organization.</span></span> <span data-ttu-id="00571-106">Office 365 の脅威保護機能を初めて使用する場合や、どこから始めるべきかがわからない場合は、次のガイドを出発点としてご利用ください。</span><span class="sxs-lookup"><span data-stu-id="00571-106">If you're new to threat protection features in Office 365, or you're just not sure where to begin, use the following guidance as a starting point.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="00571-107">**ポリシーの種類ごとに最初に推奨される設定が含まれています。ただし、多くのオプションを使用できます。また、特定の組織のニーズに合わせて設定を調整することもでき**ます。</span><span class="sxs-lookup"><span data-stu-id="00571-107">**Initial recommended settings are included for each kind of policy; however, many options are available, and you can adjust your settings to meet your specific organization's needs**.</span></span> <span data-ttu-id="00571-108">使用しているポリシーまたは変更がデータセンターによって処理されるまで約30分間待機します。</span><span class="sxs-lookup"><span data-stu-id="00571-108">Allow approximately 30 minutes for your policies or changes to work their way through your datacenter.</span></span>

## <a name="requirements"></a><span data-ttu-id="00571-109">要件</span><span class="sxs-lookup"><span data-stu-id="00571-109">Requirements</span></span>

### <a name="subscriptions"></a><span data-ttu-id="00571-110">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="00571-110">Subscriptions</span></span>

<span data-ttu-id="00571-111">脅威保護機能は、すべての Office 365 サブスクリプションに含まれています。ただし、一部のサブスクリプションには、より高度な機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00571-111">Threat protection features are included in all Office 365 subscriptions; however, some subscriptions include more advanced features.</span></span> <span data-ttu-id="00571-112">次の表に、この記事に含まれる保護機能を最小限のサブスクリプション要件と共に示します。</span><span class="sxs-lookup"><span data-stu-id="00571-112">The following table lists the protection features included in this article together with the minimum subscription requirements.</span></span><br/>

|<span data-ttu-id="00571-113">保護の種類</span><span class="sxs-lookup"><span data-stu-id="00571-113">Protection type</span></span>  |<span data-ttu-id="00571-114">サブスクリプションの要件</span><span class="sxs-lookup"><span data-stu-id="00571-114">Subscription requirement</span></span>  |
|---------|---------|
|<span data-ttu-id="00571-115">マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-115">Anti-malware protection</span></span>    | <span data-ttu-id="00571-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)EOP</span><span class="sxs-lookup"><span data-stu-id="00571-116">[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) (EOP)</span></span>        |
|<span data-ttu-id="00571-117">電子メールおよび Office ドキュメント内の悪意のある Url やファイルからの保護</span><span class="sxs-lookup"><span data-stu-id="00571-117">Protection from malicious URLs and files in email and Office documents</span></span>    | <span data-ttu-id="00571-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)ツール</span><span class="sxs-lookup"><span data-stu-id="00571-118">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)</span></span>       |
|<span data-ttu-id="00571-119">フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-119">Anti-phishing protection</span></span>    | [<span data-ttu-id="00571-120">EOP</span><span class="sxs-lookup"><span data-stu-id="00571-120">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|<span data-ttu-id="00571-121">高度なフィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-121">Advanced anti-phishing protection</span></span>    | [<span data-ttu-id="00571-122">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="00571-122">Office 365 ATP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|<span data-ttu-id="00571-123">スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-123">Anti-spam protection</span></span>     | [<span data-ttu-id="00571-124">EOP</span><span class="sxs-lookup"><span data-stu-id="00571-124">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|<span data-ttu-id="00571-125">ゼロ時間自動削除 (電子メール用)</span><span class="sxs-lookup"><span data-stu-id="00571-125">Zero-hour auto purge (for email)</span></span>    | [<span data-ttu-id="00571-126">EOP</span><span class="sxs-lookup"><span data-stu-id="00571-126">EOP</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)        |
|<span data-ttu-id="00571-127">監査ログ (これはレポートのために使用されます)</span><span class="sxs-lookup"><span data-stu-id="00571-127">Audit logging (this is used for reporting purposes)</span></span>    | [<span data-ttu-id="00571-128">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="00571-128">Exchange Online</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a><span data-ttu-id="00571-129">ロールと権限</span><span class="sxs-lookup"><span data-stu-id="00571-129">Roles and permissions</span></span>

<span data-ttu-id="00571-130">[セキュリティ _AMP_ コンプライアンスセンター](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)でポリシーを構成するには、適切な役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00571-130">You must be assigned an appropriate role to configure policies in the [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).</span></span> <span data-ttu-id="00571-131">次の表は、いくつかの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="00571-131">The following table includes some examples:</span></span> 

|<span data-ttu-id="00571-132">役割または役割グループ</span><span class="sxs-lookup"><span data-stu-id="00571-132">Role or role group</span></span>  |<span data-ttu-id="00571-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="00571-133">Where to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="00571-134">Office 365 グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="00571-134">Office 365 Global Administrator</span></span> |[<span data-ttu-id="00571-135">Office 365 の管理者の役割について</span><span class="sxs-lookup"><span data-stu-id="00571-135">About Office 365 admin roles</span></span>](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|<span data-ttu-id="00571-136">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="00571-136">Security Administrator</span></span> |[<span data-ttu-id="00571-137">Azure Active Directory での管理者の役割のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="00571-137">Administrator role permissions in Azure Active Directory</span></span>](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|<span data-ttu-id="00571-138">Exchange Online 組織の管理</span><span class="sxs-lookup"><span data-stu-id="00571-138">Exchange Online Organization Management</span></span> |[<span data-ttu-id="00571-139">Exchange Online でのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="00571-139">Permissions in Exchange Online</span></span>](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br><span data-ttu-id="00571-140">and</span><span class="sxs-lookup"><span data-stu-id="00571-140">and</span></span><br> [<span data-ttu-id="00571-141">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="00571-141">Exchange Online PowerShell</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

<span data-ttu-id="00571-142">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-142">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="part-1---anti-malware-protection"></a><span data-ttu-id="00571-143">パート 1-マルウェア対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-143">Part 1 - Anti-malware protection</span></span>

<span data-ttu-id="00571-144">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションでは[、マルウェア対策保護](anti-malware-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="00571-144">[Anti-malware protection](anti-malware-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> 

1. <span data-ttu-id="00571-145">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > の**マルウェア対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-145">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-malware**.</span></span>

2. <span data-ttu-id="00571-146">[**既定**のポリシー] をダブルクリックし、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-146">Double-click the **Default** policy, and then choose **settings**.</span></span>

3. <span data-ttu-id="00571-147">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-147">Specify the following settings:</span></span>

    - <span data-ttu-id="00571-148">[**マルウェア検出の応答**] セクションで、既定の設定の [**いいえ**] をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="00571-148">In the **Malware Detection Response** section, keep the default setting of **No**.</span></span>

    - <span data-ttu-id="00571-149">[**一般的な添付ファイルの種類のフィルター** ] セクションで、 **[オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-149">In the **Common Attachment Types Filter** section, choose **On**.</span></span>

4. <span data-ttu-id="00571-150">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-150">Click **Save**.</span></span>

<span data-ttu-id="00571-151">マルウェア対策ポリシーオプションの詳細については、「[マルウェア対策ポリシーを構成](configure-anti-malware-policies.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-151">To learn more about anti-malware policy options, see [Configure anti-malware policies](configure-anti-malware-policies.md).</span></span>

## <a name="part-2---protection-from-malicious-urls-and-files"></a><span data-ttu-id="00571-152">パート 2-悪意のある Url およびファイルからの保護</span><span class="sxs-lookup"><span data-stu-id="00571-152">Part 2 - Protection from malicious URLs and files</span></span>

<span data-ttu-id="00571-153">悪意のある Url やファイルからのクリック時の保護は、 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) を含むサブスクリプションで利用でき、Atp の[安全な添付ファイル](atp-safe-attachments.md)と[atp の安全なリンク](atp-safe-links.md)ポリシーによって設定されます。</span><span class="sxs-lookup"><span data-stu-id="00571-153">Time-of-click protection from malicious URLs and files is available in subscriptions that include [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), and is set up through [ATP Safe Attachments](atp-safe-attachments.md) and [ATP Safe Links](atp-safe-links.md) policies.</span></span>

### <a name="atp-safe-attachments-policies"></a><span data-ttu-id="00571-154">ATP の安全な添付ファイルポリシー</span><span class="sxs-lookup"><span data-stu-id="00571-154">ATP Safe Attachments policies</span></span>

<span data-ttu-id="00571-155">[Atp の安全な添付ファイル](atp-safe-attachments.md)を設定するには、少なくとも1つの Atp の安全な添付ファイルポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00571-155">To set up [ATP Safe Attachments](atp-safe-attachments.md), you must define at least one ATP Safe Attachments policy.</span></span> 

1. <span data-ttu-id="00571-156">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP 安全添付ファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-156">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP safe attachments**.</span></span>

2. <span data-ttu-id="00571-157">[ **SharePoint、OneDrive、Microsoft Teams の ATP を有効にする**] オプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-157">Select the option **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

3. <span data-ttu-id="00571-158">[**電子メールの添付ファイルを保護**する] セクションで**+**、プラス記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-158">In the **Protect email attachments** section, click the plus sign (**+**).</span></span>

4. <span data-ttu-id="00571-159">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-159">Specify the following settings:</span></span>

    - <span data-ttu-id="00571-160">[**名前**] ボックスに「 `Block malware`」と入力します。</span><span class="sxs-lookup"><span data-stu-id="00571-160">In the **Name** box, type `Block malware`.</span></span>

    - <span data-ttu-id="00571-161">[応答] セクションで、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-161">In the response section, choose **Block**.</span></span>

    - <span data-ttu-id="00571-162">[**添付ファイルのリダイレクト**] セクションで、[**リダイレクトを有効にする**] オプションを選択し、検出されたファイルを確認する組織のセキュリティ管理者またはオペレーターの電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-162">In the **Redirect attachment** section, select the option **Enable redirect**, and then specify the email address for your organization's security administrator or operator who will review detected files.</span></span>

    - <span data-ttu-id="00571-163">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-163">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="00571-164">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-164">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

5. <span data-ttu-id="00571-165">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-165">Click **Save**.</span></span>

6. <span data-ttu-id="00571-166">(**推奨の追加手順**)グローバル管理者または SharePoint Online 管理者は、 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** コマンドレットを実行して、Office 365 環境の**DisallowInfectedFileDownload**パラメーターを*true*に設定します。</span><span class="sxs-lookup"><span data-stu-id="00571-166">(**Recommended additional step**) As a global administrator or a SharePoint Online administrator run the **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet with the **DisallowInfectedFileDownload** parameter set to  *true* for your Office 365 environment.</span></span> <span data-ttu-id="00571-167">(これにより、ユーザーが悪意を持って検出されたファイルを開く、移動、コピー、または共有できなくなります)。</span><span class="sxs-lookup"><span data-stu-id="00571-167">(This prevents people from opening, moving, copying, or sharing files that are detected as malicious.)</span></span>  

<span data-ttu-id="00571-168">詳細については、「 [office 365 の atp の安全な添付ファイルのポリシーをセットアップ](set-up-atp-safe-attachments-policies.md)する」および「 [SharePoint、OneDrive、Microsoft Teams 用の office 365 ATP を有効](turn-on-atp-for-spo-odb-and-teams.md)にする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-168">To learn more, see [Set up Office 365 ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) and [Turn on Office 365 ATP for SharePoint, OneDrive, and Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).</span></span>

### <a name="atp-safe-links-policies"></a><span data-ttu-id="00571-169">ATP の安全なリンクポリシー</span><span class="sxs-lookup"><span data-stu-id="00571-169">ATP Safe Links policies</span></span>

<span data-ttu-id="00571-170">[ATP の安全なリンク](atp-safe-links.md)を設定するには、既定のポリシーを確認して編集し、特定のユーザーのポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="00571-170">To set up [ATP Safe Links](atp-safe-links.md), review and edit your default policy, and add a policy for specific users.</span></span>

1. <span data-ttu-id="00571-171">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP セーフリンク**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-171">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP Safe Links**.</span></span>

2. <span data-ttu-id="00571-172">[**既定**のポリシー] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-172">Double-click the **Default** policy.</span></span>

3. <span data-ttu-id="00571-173">[**安全なリンクの使用**] セクションで、[ **office 365 ProPlus、office for IOS**、および Android] オプションをオンにして、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-173">In the **Use safe links in** section, select the option **Office 365 ProPlus, Office for iOS and Android**, and then click **Save**.</span></span>

4. <span data-ttu-id="00571-174">[**特定の受信者に適用されるポリシー** ] セクションで、プラス**+** 記号 () をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-174">In the **Policies that apply to specific recipients** section, click the plus sign (**+**).</span></span>

5. <span data-ttu-id="00571-175">次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-175">Specify the following settings:</span></span>

    - <span data-ttu-id="00571-176">[**名前**] ボックスに、などの名前を入力`Safe Links`します。</span><span class="sxs-lookup"><span data-stu-id="00571-176">In the **Name** box, type a name, such as `Safe Links`.</span></span>

    - <span data-ttu-id="00571-177">**[アクションの選択**] セクションで、[**オン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-177">In the **Select the action** section, choose **On**.</span></span>

    - <span data-ttu-id="00571-178">次のオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-178">Select these options:</span></span>

        - <span data-ttu-id="00571-179">**安全な添付ファイルを使用してダウンロード可能なコンテンツをスキャンする**</span><span class="sxs-lookup"><span data-stu-id="00571-179">**Use safe attachments to scan downloadable content**</span></span> 

        - <span data-ttu-id="00571-180">**組織内で送信される電子メールメッセージに安全なリンクを適用する**</span><span class="sxs-lookup"><span data-stu-id="00571-180">**Apply safe links to email messages sent within the organization**</span></span>

        - <span data-ttu-id="00571-181">**ユーザーが元の URL への安全なリンクをクリックできないようにする**</span><span class="sxs-lookup"><span data-stu-id="00571-181">**Do not let users click through safe links to original URL**</span></span>

    - <span data-ttu-id="00571-182">[**適用先**] セクションで、[**受信者ドメイン**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-182">In the **Applied to** section, choose **The recipient domain is**.</span></span> <span data-ttu-id="00571-183">次に、ドメインを選択し、[**追加**] を選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-183">Then, select your domain, choose **Add**, and then click **OK**.</span></span>

6. <span data-ttu-id="00571-184">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-184">Click **Save**.</span></span>

<span data-ttu-id="00571-185">詳細については、「 [Office 365 ATP 安全リンクポリシー](set-up-atp-safe-links-policies.md)のセットアップ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-185">To learn more, see [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).</span></span> 

## <a name="part-3---anti-phishing-protection"></a><span data-ttu-id="00571-186">パート 3-フィッシング対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-186">Part 3 - Anti-phishing protection</span></span>

<span data-ttu-id="00571-187">[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションでは、[フィッシング対策保護](anti-phishing-protection.md)を利用できます。</span><span class="sxs-lookup"><span data-stu-id="00571-187">[Anti-phishing protection](anti-phishing-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="00571-188">高度なフィッシング対策を[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)で利用できます。</span><span class="sxs-lookup"><span data-stu-id="00571-188">Advanced anti-phishing protection is available in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> <span data-ttu-id="00571-189">次の手順では、ATP のフィッシング対策ポリシーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="00571-189">The following procedure describes how to configure an ATP anti-phishing policy.</span></span> <span data-ttu-id="00571-190">この手順は、(ATP を使用しない) フィッシング対策ポリシーの構成に似ています。</span><span class="sxs-lookup"><span data-stu-id="00571-190">The steps are similar for configuring an anti-phishing policy (without ATP).</span></span>

1. <span data-ttu-id="00571-191">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > **ATP のフィッシング対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-191">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **ATP anti-phishing**.</span></span>

2. <span data-ttu-id="00571-192">[**既定のポリシー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-192">Click **Default policy**.</span></span>

3. <span data-ttu-id="00571-193">[**偽装**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-193">In the **Impersonation** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="00571-194">[**保護するユーザーの追加**] タブで、[保護] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="00571-194">On the **Add users to protect** tab, turn protection on.</span></span> <span data-ttu-id="00571-195">次に、組織の取締役会のメンバー、CEO、CFO、その他のシニアリーダーなどのユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="00571-195">Then add users, such as your organization's board members, your CEO, CFO, and other senior leaders.</span></span> <span data-ttu-id="00571-196">(個々の電子メールアドレスを入力するか、クリックしてリストを表示することができます。)</span><span class="sxs-lookup"><span data-stu-id="00571-196">(You can type an individual email address, or click to display a list.)</span></span>

    - <span data-ttu-id="00571-197">[**保護するドメインの追加**] タブで、**自分が所有しているドメインを自動的**に有効にします。</span><span class="sxs-lookup"><span data-stu-id="00571-197">On the **Add domains to protect** tab, turn on **Automatically include the domains I own**.</span></span> <span data-ttu-id="00571-198">カスタムドメインがある場合は、それらも追加します。</span><span class="sxs-lookup"><span data-stu-id="00571-198">If you have custom domains, add those as well.</span></span>

    - <span data-ttu-id="00571-199">[**操作**] タブで、[**受信者の迷惑メールフォルダーにメッセージを移動する**] を選択して、偽装されたユーザーと偽装ドメインの両方を選択し、安全のヒントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="00571-199">On the **Actions** tab, select **Move message to the recipients' Junk Email folders** for both impersonated user and impersonated domain, and turn on safety tips.</span></span>

    - <span data-ttu-id="00571-200">[**メールボックスインテリジェンス**] タブで、[メールボックスインテリジェンス] がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00571-200">On the **Mailbox intelligence** tab, make sure mailbox intelligence is turned on.</span></span>

    - <span data-ttu-id="00571-201">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-201">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span>

4. <span data-ttu-id="00571-202">[**スプーフィング**] セクションで、[**編集**] をクリックし、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-202">In the **Spoof** section, click **Edit**, and then specify the following settings:</span></span>

    - <span data-ttu-id="00571-203">[**スプーフィングフィルターの設定**] タブで、[スプーフィング対策] 保護が有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="00571-203">On the **Spoofing filter settings** tab, make sure anti-spoofing protection is turned on.</span></span>

    - <span data-ttu-id="00571-204">[**操作**] タブで、[受信者の迷惑メールフォルダーにメッセージを移動する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-204">On the **Actions** tab, choose Move message to the recipients' Junk Email folders.</span></span>

    - <span data-ttu-id="00571-205">[**設定の確認**] タブで、設定を確認した後、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-205">On the **Review your settings** tab, after you have reviewed your settings, click **Save**.</span></span> <span data-ttu-id="00571-206">(変更を行っていない場合は、[**キャンセル**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="00571-206">(If you didn't make any changes, click **Cancel**.)</span></span>

5. <span data-ttu-id="00571-207">[既定のポリシー設定] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="00571-207">Close the default policy settings page.</span></span>

<span data-ttu-id="00571-208">フィッシング対策ポリシーオプションの詳細については、「[フィッシング対策ポリシーの設定](set-up-anti-phishing-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-208">To learn more about your anti-phishing policy options, see [Set up anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="part-4---anti-spam-protection"></a><span data-ttu-id="00571-209">パート 4-スパム対策保護</span><span class="sxs-lookup"><span data-stu-id="00571-209">Part 4 - Anti-spam protection</span></span>

<span data-ttu-id="00571-210">[スパム対策保護](anti-spam-protection.md)は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="00571-210">[Anti-spam protection](anti-spam-protection.md) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span>

1. <span data-ttu-id="00571-211">[セキュリティ & コンプライアンスセンター](https://protection.office.com)で、[**脅威管理** > **ポリシー** > のスパム**対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="00571-211">In the [Security & Compliance Center](https://protection.office.com), choose **Threat management** > **Policy** > **Anti-spam**.</span></span>

2. <span data-ttu-id="00571-212">[**カスタム**] タブで、[**カスタム設定**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="00571-212">On the **Custom** tab, turn **Custom settings** on.</span></span>

3. <span data-ttu-id="00571-213">[**既定のスパムフィルターポリシー**] を展開し、[**ポリシーの編集**] をクリックして、次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="00571-213">Expand **Default spam filter policy**, click **Edit policy**, and then specify the following settings:</span></span>

    - <span data-ttu-id="00571-214">[**スパムと一括操作**] セクションで、しきい値を5または6に設定します。</span><span class="sxs-lookup"><span data-stu-id="00571-214">In the **Spam and bulk actions** section, set the threshold to a value of 5 or 6.</span></span>

    - <span data-ttu-id="00571-215">[**許可するリスト**] セクションで、許可された送信者とドメインを確認し、必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="00571-215">In the **Allow lists** section, review (and if necessary, edit) your allowed senders and domains.</span></span>

4. <span data-ttu-id="00571-216">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="00571-216">Click **Save**.</span></span>

<span data-ttu-id="00571-217">スパム対策ポリシーオプションの詳細については、「[スパム対策](configure-the-anti-spam-policies.md)ポリシーを構成する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-217">To learn more about your anti-spam policy options, see [Configure the anti-spam policies](configure-the-anti-spam-policies.md).</span></span>

## <a name="part-5---additional-settings-to-configure"></a><span data-ttu-id="00571-218">パート 5-構成する追加の設定</span><span class="sxs-lookup"><span data-stu-id="00571-218">Part 5 - Additional settings to configure</span></span>

<span data-ttu-id="00571-219">マルウェア、悪意のある Url、ファイル、フィッシング、スパムからの保護を構成するだけでなく、ゼロ時間の自動削除と監査ログの設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="00571-219">In addition to configuring protection from malware, malicious URLs and files, phishing, and spam, we recommend that you configure your zero-hour auto purge and audit logging settings.</span></span>

### <a name="zero-hour-auto-purge-for-email"></a><span data-ttu-id="00571-220">電子メールのゼロ時間自動削除</span><span class="sxs-lookup"><span data-stu-id="00571-220">Zero-hour auto purge for email</span></span>

<span data-ttu-id="00571-221">[ゼロ時間自動削除](zero-hour-auto-purge.md)(ZAP) は、 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)を含むサブスクリプションで使用できます。</span><span class="sxs-lookup"><span data-stu-id="00571-221">[Zero-hour auto purge](zero-hour-auto-purge.md) (ZAP) is available in subscriptions that include [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description).</span></span> <span data-ttu-id="00571-222">この保護は既定で有効になっています。ただし、保護を有効にするには、次の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="00571-222">This protection is turned on by default; however, the following conditions must be met for protection to be in effect:</span></span>

- <span data-ttu-id="00571-223">スパム[対策ポリシー](anti-spam-protection.md)で、 **[迷惑メール] フォルダーにメッセージを移動**するように設定されています。</span><span class="sxs-lookup"><span data-stu-id="00571-223">Spam actions are set to **Move message to Junk Email folder** in [anti-spam policies](anti-spam-protection.md).</span></span>

- <span data-ttu-id="00571-224">ユーザーが既定の[迷惑メール設定](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)を保持していて、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="00571-224">Users have kept their default [junk email settings](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md), and have not turned off junk email protection.</span></span>

<span data-ttu-id="00571-225">詳細については、「[スパムおよびマルウェアに対するゼロ時間自動削除対策](zero-hour-auto-purge.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-225">To learn more, see [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).</span></span>

### <a name="audit-logging-for-reporting-and-investigation"></a><span data-ttu-id="00571-226">レポートおよび調査の監査ログ</span><span class="sxs-lookup"><span data-stu-id="00571-226">Audit logging for reporting and investigation</span></span>

<span data-ttu-id="00571-227">監査ログは、 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)を含むサブスクリプションで利用できます。</span><span class="sxs-lookup"><span data-stu-id="00571-227">Audit logging is available in subscriptions that include [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description).</span></span> <span data-ttu-id="00571-228">[セキュリティダッシュボード](security-dashboard.md)、[電子メールセキュリティレポート](view-email-security-reports.md)、[エクスプローラー](use-explorer-in-security-and-compliance.md)などの脅威保護レポートのデータを表示するには、組織に対して監査ログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="00571-228">In order to view data in threat protection reports, such as the [Security Dashboard](security-dashboard.md), [email security reports](view-email-security-reports.md), and [Explorer](use-explorer-in-security-and-compliance.md), audit logging must be turned on for your organization.</span></span> <span data-ttu-id="00571-229">詳細については、「 [Office 365 監査ログ検索をオンまたはオフに](turn-audit-log-search-on-or-off.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00571-229">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

## <a name="post-setup-tasks"></a><span data-ttu-id="00571-230">セットアップ後のタスク</span><span class="sxs-lookup"><span data-stu-id="00571-230">Post-setup tasks</span></span>

<span data-ttu-id="00571-231">脅威保護機能を構成した後は、それらの機能がどのように動作しているかを監視し、必要に応じてポリシーを確認して変更し、新しい機能とサービスの更新について確認してください。</span><span class="sxs-lookup"><span data-stu-id="00571-231">After you have configured your threat protection features, make sure to monitor how those features are working, review and revise your policies as needed, and watch for new features and service updates.</span></span>

|<span data-ttu-id="00571-232">行うこと</span><span class="sxs-lookup"><span data-stu-id="00571-232">What to do</span></span>  |<span data-ttu-id="00571-233">詳細については、リソースを参照してください</span><span class="sxs-lookup"><span data-stu-id="00571-233">Resources to learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="00571-234">レポートを表示して、組織の脅威保護機能がどのように機能するかを確認する</span><span class="sxs-lookup"><span data-stu-id="00571-234">See how threat protection features are working for your organization by viewing reports</span></span>    |[<span data-ttu-id="00571-235">セキュリティダッシュボード</span><span class="sxs-lookup"><span data-stu-id="00571-235">Security dashboard</span></span>](security-dashboard.md)<br/>[<span data-ttu-id="00571-236">電子メールセキュリティレポート</span><span class="sxs-lookup"><span data-stu-id="00571-236">Email security reports</span></span>](view-email-security-reports.md)<br/>[<span data-ttu-id="00571-237">Office 365 ATP のレポート</span><span class="sxs-lookup"><span data-stu-id="00571-237">Reports for Office 365 ATP</span></span>](view-reports-for-atp.md)<br/>[<span data-ttu-id="00571-238">脅威エクスプローラー</span><span class="sxs-lookup"><span data-stu-id="00571-238">Threat Explorer</span></span>](use-explorer-in-security-and-compliance.md)    |
|<span data-ttu-id="00571-239">必要に応じて脅威保護ポリシーを定期的にレビューし、改訂する</span><span class="sxs-lookup"><span data-stu-id="00571-239">Periodically review and revise your threat protection policies as needed</span></span>    |[<span data-ttu-id="00571-240">セキュリティ スコア</span><span class="sxs-lookup"><span data-stu-id="00571-240">Secure Score</span></span>](microsoft-secure-score.md)<br/>[<span data-ttu-id="00571-241">スマートレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="00571-241">Smart reports and insights</span></span>](reports-and-insights-in-security-and-compliance.md)<br/>[<span data-ttu-id="00571-242">Office 365 の脅威の調査と応答の機能</span><span class="sxs-lookup"><span data-stu-id="00571-242">Office 365 threat investigation and response features</span></span>](keep-users-safe-with-office-365-ti.md)          |
|<span data-ttu-id="00571-243">新機能とサービス更新を見る</span><span class="sxs-lookup"><span data-stu-id="00571-243">Watch for new features and service updates</span></span>     |[<span data-ttu-id="00571-244">標準および対象のリリースオプション</span><span class="sxs-lookup"><span data-stu-id="00571-244">Standard and Targeted release options</span></span>](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[<span data-ttu-id="00571-245">Message Center</span><span class="sxs-lookup"><span data-stu-id="00571-245">Message Center</span></span>](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[<span data-ttu-id="00571-246">Microsoft 365 ロードマップ</span><span class="sxs-lookup"><span data-stu-id="00571-246">Microsoft 365 Roadmap</span></span>](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[<span data-ttu-id="00571-247">サービスの説明</span><span class="sxs-lookup"><span data-stu-id="00571-247">Service Descriptions</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |
