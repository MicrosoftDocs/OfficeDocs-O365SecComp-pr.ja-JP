---
title: データ損失防止と Microsoft Teams
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/26/2019
ms.audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: これで、DLP ポリシーを Microsoft Teams のチャットおよびチャネルに適用できるようになります。 機能の詳細については、この記事を参照してください。
ms.openlocfilehash: 712729972942d98afb5b3898ad357114ce1a6bae
ms.sourcegitcommit: e23b84ef4eee9cccec7205826b71ddfe9aaac2f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2019
ms.locfileid: "33367270"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a><span data-ttu-id="b9537-104">データ損失防止と Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9537-104">Data loss prevention and Microsoft Teams</span></span>

## <a name="overview-of-dlp-for-microsoft-teams"></a><span data-ttu-id="b9537-105">Microsoft Teams の DLP の概要</span><span class="sxs-lookup"><span data-stu-id="b9537-105">Overview of DLP for Microsoft Teams</span></span>

<span data-ttu-id="b9537-106">最近では、Microsoft Teams を含むように[データ損失防止](data-loss-prevention-policies.md)(DLP) 機能が拡張されています。</span><span class="sxs-lookup"><span data-stu-id="b9537-106">Recently, [data loss prevention](data-loss-prevention-policies.md) (DLP) capabilities were extended to include Microsoft Teams.</span></span> <span data-ttu-id="b9537-107">組織に DLP がある場合は、Microsoft Teams チャネルまたはチャットセッションで機密情報を共有できないようにするポリシーを定義できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b9537-107">If your organization has DLP, you can now define policies that prevent people from sharing sensitive information in a Microsoft Teams channel or chat session.</span></span> <span data-ttu-id="b9537-108">この保護がどのように機能するかについて、いくつかの例を示します。</span><span class="sxs-lookup"><span data-stu-id="b9537-108">Here are some examples of how this protection works:</span></span>

- <span data-ttu-id="b9537-109">**例 1: メッセージ内の機密情報を保護**します。</span><span class="sxs-lookup"><span data-stu-id="b9537-109">**Example 1: Protecting sensitive information in messages**.</span></span> <span data-ttu-id="b9537-110">チームのチャットまたはチャネル内の機密情報をゲスト (外部ユーザー) と共有しようとするユーザーがいるとします。</span><span class="sxs-lookup"><span data-stu-id="b9537-110">Suppose that someone attempts to share sensitive information in a Teams chat or channel with guests (external users).</span></span> <span data-ttu-id="b9537-111">これを防止するように定義された DLP ポリシーがある場合、外部ユーザーに送信される機密情報を含むメッセージは削除されます。</span><span class="sxs-lookup"><span data-stu-id="b9537-111">If you have a DLP policy defined to prevent this, messages with sensitive information that are sent to external users are deleted.</span></span> <span data-ttu-id="b9537-112">これは、DLP ポリシーがどのように構成されているかに応じて、数秒で自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="b9537-112">This happens automatically, and within seconds, according to how your DLP policy is configured.</span></span>

- <span data-ttu-id="b9537-113">**例 2: ドキュメント内の機密情報を保護**します。</span><span class="sxs-lookup"><span data-stu-id="b9537-113">**Example 2: Protecting sensitive information in documents**.</span></span> <span data-ttu-id="b9537-114">Microsoft Teams チャネルまたはチャットのゲストでドキュメントを共有しようとした場合に、ドキュメントに機密情報が含まれているとします。</span><span class="sxs-lookup"><span data-stu-id="b9537-114">Suppose that someone attempts to share a document with guests in a Microsoft Teams channel or chat, and the document contains sensitive information.</span></span> <span data-ttu-id="b9537-115">これを防止するように定義された DLP ポリシーがある場合、ドキュメントはそれらのユーザーに対して開くことができません。</span><span class="sxs-lookup"><span data-stu-id="b9537-115">If you have a DLP policy defined to prevent this, the document won't open for those users.</span></span> <span data-ttu-id="b9537-116">この場合、DLP ポリシーには、保護を設定するために SharePoint と OneDrive を含める必要があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9537-116">Note that in this case, your DLP policy must include SharePoint and OneDrive in order for protection to be in place.</span></span>

## <a name="policy-tips-help-educate-users"></a><span data-ttu-id="b9537-117">ユーザーを教育するためのポリシーヒント</span><span class="sxs-lookup"><span data-stu-id="b9537-117">Policy tips help educate users</span></span>

<span data-ttu-id="b9537-118">[Exchange、outlook、および outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)、 [SharePoint および OneDrive for business サイト](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)、および[Office デスクトップクライアント](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)での dlp の動作と同様に、アクションが dlp ポリシーと競合すると、ポリシーヒントが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b9537-118">Similar to how DLP works in [Exchange, Outlook, and Outlook on the web](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint and OneDrive for Business sites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites), and [Office desktop clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs), policy tips appear when an action conflicts with a DLP policy.</span></span> <span data-ttu-id="b9537-119">ポリシーヒントの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b9537-119">Here's an example of a policy tip:</span></span>

![Teams でブロックされたメッセージ通知](media/dlp-teams-blockedmessage-notification.png)

<span data-ttu-id="b9537-121">この場合、送信者は Microsoft Teams チャネルでソーシャルセキュリティ番号を共有しようとしました。</span><span class="sxs-lookup"><span data-stu-id="b9537-121">In this case, the sender attempted to share a social security number in a Microsoft Teams channel.</span></span> <span data-ttu-id="b9537-122">[**何を行いますか?** ] リンクは、問題を解決するために送信者に対してオプションを提供するダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="b9537-122">The **What can I do?** link opens a dialog box that provides options for the sender to resolve the issue.</span></span> <span data-ttu-id="b9537-123">この場合、送信者はポリシーを上書きするか、管理者に通知してそれを確認して解決するかを選択することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b9537-123">Notice that in this case, the sender can opt to override the policy, or notify an admin to review and resolve it.</span></span>

![ブロックされたメッセージを解決するためのオプション](media/dlp-teams-blockedmessage-possibleactions.png)

<span data-ttu-id="b9537-125">組織では、ユーザーが DLP ポリシーを上書きすることを許可するかどうかを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b9537-125">In your organization, you can choose whether to allow users to override a DLP policy, or not.</span></span> <span data-ttu-id="b9537-126">また、DLP ポリシーを構成するときは、既定のポリシーヒントを使用するか、組織の[ポリシーヒントをカスタマイズ](#to-customize-policy-tips)できます。</span><span class="sxs-lookup"><span data-stu-id="b9537-126">And, when you configure your DLP policies, you can use the default policy tips, or [customize policy tips](#to-customize-policy-tips) for your organization.</span></span> 

<span data-ttu-id="b9537-127">この例では、送信者が Teams チャネルで社会保障番号を共有している場合、受信者は次のように表示されています。</span><span class="sxs-lookup"><span data-stu-id="b9537-127">Returning to our example, where a sender shared a social security number in a Teams channel, here's what the recipient saw:</span></span>

![ブロックされたメッセージ](media/dlp-teams-blockedmessage-notification-to-user.png)

<span data-ttu-id="b9537-129">[**ポップヒント]** リンクによって、メッセージがブロックされた理由を説明する DLP ポリシーに関する[記事](data-loss-prevention-policies.md)が開きます。</span><span class="sxs-lookup"><span data-stu-id="b9537-129">The **What's this?** link opens an [article](data-loss-prevention-policies.md) about DLP policies, which helps explain why the message was blocked.</span></span>

### <a name="to-customize-policy-tips"></a><span data-ttu-id="b9537-130">ポリシーヒントをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="b9537-130">To customize policy tips</span></span>

<span data-ttu-id="b9537-131">このタスクを実行するには、DLP ポリシーを編集する権限を持つ役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9537-131">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="b9537-132">詳細については、「 [Permissions](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9537-132">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="b9537-133">Office 365 Security & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="b9537-133">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="b9537-134">[**データ損失防止** > **ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-134">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="b9537-135">ポリシーを選択し、[**ポリシー設定**] の横にある [**編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-135">Select a policy, and next to **Policy settings**, choose **Edit**.</span></span>

4. <span data-ttu-id="b9537-136">新しいルールを作成するか、ポリシーの既存のルールを編集します。</span><span class="sxs-lookup"><span data-stu-id="b9537-136">Either create a new rule, or edit an existing rule for the policy.</span></span><br/>![ポリシーのルールを編集する](media/dlp-teams-editrule.png)<br/>

5. <span data-ttu-id="b9537-138">[**ユーザー通知**] タブで、[**電子メールテキストのカスタマイズ**] または [**ポリシーヒントテキストオプションのカスタマイズ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-138">On the **User notifications** tab, select **Customize the email text** and/or **Customize the policy tip text** options.</span></span><br/><span data-ttu-id="b9537-139">![ユーザー通知とポリシーヒントをカスタマイズする](media/dlp-teams-editrule-usernotifications.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-139">![Customize user notifications and policy tips](media/dlp-teams-editrule-usernotifications.png)</span></span><br/>  

6. <span data-ttu-id="b9537-140">電子メール通知やポリシーヒントに使用するテキストを指定し、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-140">Specify the text you want to use for email notifications and/or policy tips, and then choose **Save**.</span></span> 

7. <span data-ttu-id="b9537-141">[**ポリシー設定**] タブで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-141">On the **Policy settings** tab, choose **Save**.</span></span>

<span data-ttu-id="b9537-142">変更がデータセンターを経由して、ユーザーアカウントに同期されるまで約1時間の時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="b9537-142">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>
 
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a><span data-ttu-id="b9537-143">既存の DLP ポリシーに Microsoft Teams を場所として追加する</span><span class="sxs-lookup"><span data-stu-id="b9537-143">Add Microsoft Teams as a location to existing DLP policies</span></span>

<span data-ttu-id="b9537-144">このタスクを実行するには、DLP ポリシーを編集する権限を持つ役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9537-144">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="b9537-145">詳細については、「 [Permissions](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9537-145">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="b9537-146">Office 365 Security & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="b9537-146">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="b9537-147">[**データ損失防止** > **ポリシー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-147">Choose **Data loss prevention** > **Policy**.</span></span> 

3. <span data-ttu-id="b9537-148">ポリシーを選択し、[**場所**] で値を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9537-148">Select a policy, and look at the values under **Locations**.</span></span> <span data-ttu-id="b9537-149">**Teams のチャットおよびチャネルメッセージ**が表示される場合は、すべて設定されています。</span><span class="sxs-lookup"><span data-stu-id="b9537-149">If you see **Teams chat and channel messages**, you're all set.</span></span> <span data-ttu-id="b9537-150">表示しない場合は、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9537-150">If you don't, click **Edit**.</span></span><br/><span data-ttu-id="b9537-151">![既存のポリシーの場所](media/dlp-teams-editexistingpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-151">![Locations for existing policy](media/dlp-teams-editexistingpolicy.png)</span></span><br/>

4. <span data-ttu-id="b9537-152">[**状態**] 列で、 **Teams のチャットおよびチャネルメッセージ**のポリシーをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b9537-152">In the **Status** column, turn the policy on for **Teams chat and channel messages**.</span></span><br/><span data-ttu-id="b9537-153">![Teams のチャットおよびチャネルの DLP](media/dlp-teams-addteamschatschannels.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-153">![DLP for Teams chats and channels](media/dlp-teams-addteamschatschannels.png)</span></span><br/>

5. <span data-ttu-id="b9537-154">すべてのアカウントの既定の設定をそのまま使用するか、または含めるアカウントまたは除外するアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="b9537-154">Keep the default settings of all accounts, or specify which accounts to include or exclude.</span></span>

6. <span data-ttu-id="b9537-155">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9537-155">Click **Save**.</span></span>

<span data-ttu-id="b9537-156">変更がデータセンターを経由して、ユーザーアカウントに同期されるまで約1時間の時間を確保します。</span><span class="sxs-lookup"><span data-stu-id="b9537-156">Allow approximately one hour for your changes to work their way through your data center and sync to user accounts.</span></span>

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a><span data-ttu-id="b9537-157">Microsoft Teams の新しい DLP ポリシーを定義する</span><span class="sxs-lookup"><span data-stu-id="b9537-157">Define a new DLP policy for Microsoft Teams</span></span>

<span data-ttu-id="b9537-158">このタスクを実行するには、DLP ポリシーを編集する権限を持つ役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9537-158">To perform this task, you must be assigned a role that has permissions to edit DLP policies.</span></span> <span data-ttu-id="b9537-159">詳細については、「 [Permissions](data-loss-prevention-policies.md#permissions)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9537-159">To learn more, see [Permissions](data-loss-prevention-policies.md#permissions).</span></span>

1. <span data-ttu-id="b9537-160">Office 365 Security & コンプライアンスセンター ([https://protection.office.com](https://protection.office.com)) に移動し、サインインします。</span><span class="sxs-lookup"><span data-stu-id="b9537-160">Go to the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)) and sign in.</span></span>

2. <span data-ttu-id="b9537-161">[**データ損失防止** > **ポリシー** > ] を選択して **、ポリシーを作成**します。</span><span class="sxs-lookup"><span data-stu-id="b9537-161">Choose **Data loss prevention** > **Policy** > **+ Create a policy**.</span></span> 

3. <span data-ttu-id="b9537-162">[テンプレート](data-loss-prevention-policies.md#dlp-policy-templates)を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-162">Choose a [template](data-loss-prevention-policies.md#dlp-policy-templates), and then choose **Next**.</span></span><br/><span data-ttu-id="b9537-163">この例では、米国の個人を特定できる情報データテンプレートを選択しました。</span><span class="sxs-lookup"><span data-stu-id="b9537-163">In our example, we chose the U.S. Personally Identifiable Information Data template.</span></span><br/><span data-ttu-id="b9537-164">![DLP ポリシーのプライバシーテンプレート](media/dlp-teams-createnewpolicy-template.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-164">![Privacy template for DLP policy](media/dlp-teams-createnewpolicy-template.png)</span></span><br/>

4. <span data-ttu-id="b9537-165">[**ポリシーに名前**をつける] タブで、ポリシーの名前と説明を指定し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-165">On the **Name your policy** tab, specify a name and description for the policy, and then choose **Next**.</span></span> 

5. <span data-ttu-id="b9537-166">[**場所の選択**] タブで、すべての場所の既定の設定をそのまま使用するか、[特定の**場所を選択**する] を選択して、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-166">On the **Choose locations** tab, keep the default setting of all locations, or select **Let me choose specific locations**, and then choose **Next**.</span></span><br/><span data-ttu-id="b9537-167">特定の場所を選択する場合は、DLP ポリシーの場所を選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-167">If you opted to choose specific locations, select the locations for your DLP policy, and then choose **Next**.</span></span><br/><span data-ttu-id="b9537-168">![DLP ポリシーの場所](media/dlp-teams-selectlocationsnewpolicy.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-168">![DLP policy locations](media/dlp-teams-selectlocationsnewpolicy.png)</span></span><br/>
    > [!NOTE]
    > <span data-ttu-id="b9537-169">機密情報が含まれるドキュメントが不適切に共有されないようにするには、 **SharePoint サイト**と**OneDrive アカウント**が、 **Teams のチャットおよびチャネルメッセージ**と共にオンになっていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b9537-169">If you want to make sure documents that contain sensitive information are not shared inappropriately, make sure **SharePoint sites** and **OneDrive accounts** are turned on, along with **Teams chat and channel messages**.</span></span>
<br/>

6. <span data-ttu-id="b9537-170">[**ポリシー設定**] タブの [**保護するコンテンツの種類をカスタマイズ**する] で、既定の簡易設定をそのまま使用するか、[**詳細設定**] を選択して [**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-170">On the **Policy settings** tab, under **Customize the type of content you want to protect**, keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**.</span></span> <span data-ttu-id="b9537-171">[詳細設定] を選択した場合は、ポリシーのルールを作成または編集することができます。</span><span class="sxs-lookup"><span data-stu-id="b9537-171">If you choose advanced settings, you can create or edit rules for your policy.</span></span> <span data-ttu-id="b9537-172">(詳細については、「 [Simple settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)」と「advanced settings」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="b9537-172">(To get help with this, see [Simple settings vs. advanced settings](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)</span></span>

7.  <span data-ttu-id="b9537-173">[**ポリシー設定**] タブの [**機密情報が検出された場合に実行**する操作] で、設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9537-173">On the **Policy settings** tab, under **What do you want to do if we detect sensitive info?**, review the settings.</span></span> <span data-ttu-id="b9537-174">(既定の[ポリシーヒントと電子メール通知](use-notifications-and-policy-tips.md)を保持するか、カスタマイズするかを選択できます)。</span><span class="sxs-lookup"><span data-stu-id="b9537-174">(Here's where you can choose to keep default [policy tips and email notifications](use-notifications-and-policy-tips.md), or customize them.)</span></span><br/><span data-ttu-id="b9537-175">![ヒントと通知を含む DLP ポリシー設定](media/dlp-teams-policysettings-tipsemails.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-175">![DLP policy settings with tips and notifications](media/dlp-teams-policysettings-tipsemails.png)</span></span><br/><span data-ttu-id="b9537-176">設定の確認または編集が完了したら、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-176">When you're finished reviewing or editing settings, choose **Next**.</span></span>

8. <span data-ttu-id="b9537-177">[**ポリシー設定**] タブの [**ポリシーをオンにするか、または最初にテストしますか?**] で、ポリシーをオンにするか、[最初にテスト](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)するか、または今すぐ有効にしないかを選択し、[**次へ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-177">On the **Policy settings** tab, under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.</span></span><br/><span data-ttu-id="b9537-178">![ポリシーを有効にするかどうかを指定する](media/dlp-teams-policysettings-turnonnow.png)</span><span class="sxs-lookup"><span data-stu-id="b9537-178">![Specify whether to turn the policy on](media/dlp-teams-policysettings-turnonnow.png)</span></span><br/>

9. <span data-ttu-id="b9537-179">[**設定の確認**] タブで、新しいポリシーの設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9537-179">On the **Review your settings** tab, review the settings for your new policy.</span></span> <span data-ttu-id="b9537-180">[**編集**] を選択して変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="b9537-180">Choose **Edit** to make changes.</span></span> <span data-ttu-id="b9537-181">完了したら、[**作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b9537-181">When you're finished, choose **Create**.</span></span> 

<span data-ttu-id="b9537-182">新しいポリシーがデータセンターを使用して動作し、ユーザーアカウントに同期できるようになるまで約1時間かかります。</span><span class="sxs-lookup"><span data-stu-id="b9537-182">Allow approximately one hour for your new policy to work its way through your data center and sync to user accounts.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b9537-183">関連記事</span><span class="sxs-lookup"><span data-stu-id="b9537-183">Related articles</span></span>

[<span data-ttu-id="b9537-184">DLP ポリシーの作成、テスト、調整</span><span class="sxs-lookup"><span data-stu-id="b9537-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)

[<span data-ttu-id="b9537-185">メール通知を送信して、DLP ポリシーのヒントを表示する</span><span class="sxs-lookup"><span data-stu-id="b9537-185">Send email notifications and show policy tips for DLP policies</span></span>](use-notifications-and-policy-tips.md)
