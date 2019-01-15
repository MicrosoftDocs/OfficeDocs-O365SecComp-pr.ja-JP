---
title: Office 365 の ATP の安全なリンクのポリシーを設定します
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: Word、Excel、PowerPoint、および Visio のファイルおよび電子メール メッセージ内の悪意のあるリンクから組織を保護するために、安全なリンクのポリシーを設定します。
ms.openlocfilehash: 145e8998637756d204171f64021d6ad783b367f3
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015059"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="84ae6-103">Office 365 の ATP の安全なリンクのポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="84ae6-103">Set up Office 365 ATP Safe Links policies</span></span>

<span data-ttu-id="84ae6-p101">[ATP の安全なリンク](atp-safe-links.md)、 [Office 365 の高度な脅威保護](office-365-atp.md)(ATP) の機能は、フィッシングやその他の攻撃で使用される、悪意のあるリンクから組織を保護するために役立ちます。必要がある場合[Office 365 のセキュリティのアクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)ATP の安全なリンク ポリシーをセットアップするには、web アドレス (Url) をクリックすることを確認のために、組織を保護します。メール内の Url、および Office ドキュメント内の Url をスキャンするのには、ATP の安全なリンク ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p101">[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions for the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="84ae6-p102">[ATP ように継続的に新しい機能が追加されて](office-365-atp.md#new-features-are-continually-being-added-to-atp)います。新機能が追加されるは、既存の分析ツールの安全なリンク ポリシーを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p102">[New features are continually being added to ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp). As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="84ae6-109">行うこと</span><span class="sxs-lookup"><span data-stu-id="84ae6-109">What to do</span></span> 
  
1. <span data-ttu-id="84ae6-110">[前提条件を確認](#review-the-prerequisites)します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-110">[Review the prerequisites](#review-the-prerequisites).</span></span>
    
2. <span data-ttu-id="84ae6-p103">[レビューしすべてのユーザーに適用される分析ツールの安全なリンクの既定のポリシーを編集](#define-an-atp-safe-links-policy-that-applies-to-everyone)します。たとえば、 [ATP の安全なリンクのカスタム ブロックされた Url リストを設定](set-up-a-custom-blocked-urls-list-wtih-atp.md)できます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p103">[Review and edit the default ATP Safe Links policy that applies to everyone](#define-an-atp-safe-links-policy-that-applies-to-everyone). For example, you can [set up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span>
    
3. <span data-ttu-id="84ae6-113">[特定の電子メールの受信者ポリシーを追加または編集](#add-a-policy-for-specific-email-recipients)を含む[ATP の安全なリンクのカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-113">[Add or edit policies for specific email recipients](#add-a-policy-for-specific-email-recipients), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
4. <span data-ttu-id="84ae6-114">[ATP の安全なリンク ポリシーのオプションについて理解します。](#learn-about-atp-safe-links-policy-options)(ここでは)、最近の変更の設定を含む</span><span class="sxs-lookup"><span data-stu-id="84ae6-114">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article), including settings for recent changes</span></span>
    
## <a name="step-1-review-the-prerequisites"></a><span data-ttu-id="84ae6-115">手順 1: 前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-115">Step 1: Review the prerequisites</span></span>

- <span data-ttu-id="84ae6-116">組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-116">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="84ae6-p104">ATP のポリシーを編集または定義するために必要な権限があることを確認します。参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p104">Make sure that you have the necessary permissions to define or edit ATP policies. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="84ae6-119">(これは、Office ドキュメント内の ATP の安全なリンクの保護のため)[現代の認証](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)を使用する Office のクライアントが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-119">Make sure that Office clients are configured to use [Modern Authentication](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016) (this is for ATP Safe Links protection in Office documents).</span></span>
    
- <span data-ttu-id="84ae6-120">[ATP の安全なリンク ポリシーのオプションについて理解します。](#learn-about-atp-safe-links-policy-options)(この記事で)。</span><span class="sxs-lookup"><span data-stu-id="84ae6-120">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 

- <span data-ttu-id="84ae6-121">最大 30 分間のすべての Office 365 のデータ センターに展開するのには、新規または更新されたポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-121">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="step-2-define-or-review-the-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="84ae6-122">手順 2: 定義 (または確認) すべてのユーザーに適用される分析ツールの安全なリンク ポリシー</span><span class="sxs-lookup"><span data-stu-id="84ae6-122">Step 2: Define (or review) the ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="84ae6-p105">[Office 365 の高度な脅威保護](office-365-atp.md)がある場合は、組織内の全員に適用される既定の ATP の安全なリンク ポリシーするがあります。確認して、ことを確認し、必要な場合は、既定のポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p105">When you have [Office 365 Advanced Threat Protection](office-365-atp.md), you will have a default ATP Safe Links policy that applies to everyone in your organization. Make sure to review, and if needed, edit your default policy.</span></span>
  
1. <span data-ttu-id="84ae6-125">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-125">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="84ae6-126">**脅威の管理**の下で、左側のナビゲーションでは、選択\*\*ポリシー \> \*\* **安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="84ae6-126">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="84ae6-127">**組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-127">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="84ae6-128">![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="84ae6-128">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span>
  
4. <span data-ttu-id="84ae6-p106">**次の Url をブロックする**] セクションでは、訪問から、組織内のユーザーを禁止する 1 つまたは複数の Url を指定します。( [ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p106">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="84ae6-p107">**電子メール以外のコンテンツに適用される設定**をオンまたはオフ) に使用するオプションです。(お勧めのすべてのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p107">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="84ae6-133">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-133">Choose **Save**.</span></span>
    
## <a name="step-3-add-or-edit-atp-safe-links-policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="84ae6-134">手順 3: 追加 (または編集) 特定の電子メールの受信者に適用される ATP の安全なリンク ポリシー</span><span class="sxs-lookup"><span data-stu-id="84ae6-134">Step 3: Add (or edit) ATP Safe Links policies that apply to specific email recipients</span></span>

<span data-ttu-id="84ae6-p108">レビュー (または編集した) すべてのユーザーに適用される既定の ATP の安全なリンク ポリシー、次の手順、特定の受信者に適用する追加のポリシーを定義します。たとえば、追加のポリシーを定義することにより、既定のポリシーに例外を指定できます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p108">After you have reviewed (or edited) the default ATP Safe Links policy that applies to everyone, your next step is to define additional policies that would apply to specific recipients. For example, you can specify exceptions to your default policy by defining an additional policy.</span></span> 
  
1. <span data-ttu-id="84ae6-137">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-137">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="84ae6-138">**脅威の管理**の下で、左側のナビゲーションでは、**ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-138">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="84ae6-139">**安全なリンク**を選択します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-139">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="84ae6-140">**特定の受信者に適用されるポリシー** ] セクションで [**新規**] をクリックして ([新規] ボタンのようなプラス記号 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="84ae6-140">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span><br/><span data-ttu-id="84ae6-141">![特定の電子メールの受信者の安全なリンク ポリシーを追加するのには新規を選択します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="84ae6-141">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
5. <span data-ttu-id="84ae6-142">ポリシーの名前、説明、設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-142">Specify the name, description, and settings for your policy.</span></span><br/><span data-ttu-id="84ae6-143">**の使用例:** ない直接クリックでと呼ばれる順番にクリックして特定の web サイト分析ツールの安全なリンクの保護なしに、組織内の特定のグループにユーザーを許可しないポリシーを設定するに可能性がありますを指定する次の設定を推奨します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-143">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="84ae6-144">[**名**] ボックスで、型を直接クリックします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-144">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="84ae6-145">[**説明**] ボックスで、人々 のように、しませんから、ATP の安全なリンクの確認を行わず、web サイトにアクセス] をクリックして特定のグループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-145">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="84ae6-146">[**アクションを選択**] セクション**を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-146">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="84ae6-147">**使用の安全な添付ファイル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-147">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="84ae6-148">このオプションが利用可能な場合は、**組織内で送信されるメッセージに適用の安全なリンク**を選択します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-148">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="84ae6-149">**元の URL を使用] をクリックするユーザーを許可しない**を選択します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-149">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="84ae6-p109">(省略可能です)**次の Url の書き換えは**、組織の安全であると見なされる 1 つまたは複数の Url を指定します。( [ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください)</span><span class="sxs-lookup"><span data-stu-id="84ae6-p109">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="84ae6-p110">[**適用先**] セクションでは、**受信者のメンバーである**を選択し、ポリシーに追加するグループを選択し、します。**追加**を選択し、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p110">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="84ae6-154">[ **保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-154">Choose **Save**.</span></span>
    
## <a name="step-4-learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="84ae6-155">ATP の安全なリンク ポリシーのオプションについて、手順 4。</span><span class="sxs-lookup"><span data-stu-id="84ae6-155">Step 4: Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="84ae6-p111">設定する、ATP の安全なリンク ポリシーを編集するか、利用可能ないくつかのオプションが表示されます。参考までにこれらのオプションとは、次の表は各 1 つとその影響について説明します。ATP の安全なリンクのポリシーを定義または編集するの 2 つの主な種類があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p111">As you set up or edit your ATP Safe Links policies, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. Remember that there are two main kinds of ATP Safe Links policies to define or edit:</span></span>
- <span data-ttu-id="84ae6-159">すべてのユーザーに適用される[既定のポリシー](#default-policy-options)</span><span class="sxs-lookup"><span data-stu-id="84ae6-159">a [default policy](#default-policy-options) that applies to everyone</span></span> 
- <span data-ttu-id="84ae6-160">[特定の受信者用に定義されているポリシー](#policies-that-apply-to-specific-email-recipients)を追加</span><span class="sxs-lookup"><span data-stu-id="84ae6-160">additional [policies that are defined for specific recipients](#policies-that-apply-to-specific-email-recipients)</span></span> 

### <a name="default-policy-options"></a><span data-ttu-id="84ae6-161">ポリシーの既定のオプション</span><span class="sxs-lookup"><span data-stu-id="84ae6-161">Default policy options</span></span>

<span data-ttu-id="84ae6-162">ポリシーの既定のオプションは、組織内のすべてのユーザーに適用されます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-162">Default policy options apply to everyone in your organization.</span></span>

|<span data-ttu-id="84ae6-163">このオプション</span><span class="sxs-lookup"><span data-stu-id="84ae6-163">This option</span></span>  |<span data-ttu-id="84ae6-164">機能</span><span class="sxs-lookup"><span data-stu-id="84ae6-164">Does this</span></span>  |
|---------|---------|
| <span data-ttu-id="84ae6-165">**次の Url をブロックします。**</span><span class="sxs-lookup"><span data-stu-id="84ae6-165">**Block the following URLs**</span></span> <br/>    | <span data-ttu-id="84ae6-p112">自動的にブロックされている Url のカスタム リストを所有する組織を有効にします。ユーザーは、この一覧に URL をクリックするときは、URL がブロックされている理由を説明する[警告] ページ](atp-safe-links-warning-pages.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p112">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="84ae6-168">詳細についてを参照してください [ATP の安全なリンクを使用してカスタム ブロックされた Url リストを設定</span><span class="sxs-lookup"><span data-stu-id="84ae6-168">To learn more, see [Set up a custom blocked URLs list using ATP Safe Links</span></span>      |
| <span data-ttu-id="84ae6-169">**Office 365 ProPlus、オフィスの iOS および Android**</span><span class="sxs-lookup"><span data-stu-id="84ae6-169">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/>    | <span data-ttu-id="84ae6-170">このオプションを選択すると、ATP の安全なリンクはドキュメントの Url に保護が適用される文書を開く Office 365 用リソース (Word、Excel、および PowerPoint では、Windows または Mac OS) の Office、iOS または Android デバイス、ウィンドウ、および Office オンライン (Word で Visio 2016オンライン、PowerPoint のオンライン、オンラインの Excel で、OneNote オンライン) は、Office 365 にサインインしたユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-170">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span> <br/><br/><span data-ttu-id="84ae6-p113">**Windows で Office 2016**のみが表示された場合、機能の更新に達していない、Office 365 環境まだ (および準備中)。それまでは、Word 2016、2016 の Excel、PowerPoint 2016 または Windows で実行されている Visio 2016 ATP の安全なリンクの保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p113">If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>            |
| <span data-ttu-id="84ae6-173">**ユーザーは、ATP の安全なリンクをクリックしたときに記録しません。**</span><span class="sxs-lookup"><span data-stu-id="84ae6-173">**Don't track when users click ATP Safe Links**</span></span> <br/>  | <span data-ttu-id="84ae6-174">このオプションを選択すると、Word、Excel、PowerPoint、および Visio のドキュメント内の Url が格納されていないために、データをクリックします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-174">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="84ae6-175">**ユーザーが元の URL への ATP の安全なリンクをクリックしてできないように**</span><span class="sxs-lookup"><span data-stu-id="84ae6-175">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="84ae6-176">このオプションを選択すると、ユーザーは、悪意があると決定される URL に過去の[警告] ページ](atp-safe-links-warning-pages.md)の続行できません。</span><span class="sxs-lookup"><span data-stu-id="84ae6-176">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |

### <a name="policies-that-apply-to-specific-email-recipients"></a><span data-ttu-id="84ae6-177">特定の電子メールの受信者に適用されるポリシー</span><span class="sxs-lookup"><span data-stu-id="84ae6-177">Policies that apply to specific email recipients</span></span>

|<span data-ttu-id="84ae6-178">このオプション</span><span class="sxs-lookup"><span data-stu-id="84ae6-178">This option</span></span>  |<span data-ttu-id="84ae6-179">機能</span><span class="sxs-lookup"><span data-stu-id="84ae6-179">Does this</span></span>  |
|---------|---------|
|<span data-ttu-id="84ae6-180">**Off**</span><span class="sxs-lookup"><span data-stu-id="84ae6-180">**Off**</span></span> <br/> |<span data-ttu-id="84ae6-181">電子メール メッセージ内の Url をスキャンしません。</span><span class="sxs-lookup"><span data-stu-id="84ae6-181">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="84ae6-182">使用すると、特定の受信者グループに電子メール メッセージで Url をスキャンしないルールなど、例外の規則を定義できます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-182">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="84ae6-183">**上**</span><span class="sxs-lookup"><span data-stu-id="84ae6-183">**On**</span></span> <br/> |<span data-ttu-id="84ae6-184">ユーザーが電子メール メッセージで Url をクリックすると、ATP の安全なリンクの保護を使用してルート ユーザーに Url をリライトします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-184">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="84ae6-185">ブロックまたは悪意のある Url の一覧をクリックすると URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="84ae6-185">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="84ae6-186">**安全な添付ファイルを使用して、ダウンロード可能なコンテンツをスキャンするには**</span><span class="sxs-lookup"><span data-stu-id="84ae6-186">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="84ae6-187">このオプションを選択すると、ダウンロード可能なコンテンツをポイントする Url がスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-187">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="84ae6-188">**安全なリンクを組織内で送信されたメッセージに適用します。**</span><span class="sxs-lookup"><span data-stu-id="84ae6-188">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="84ae6-189">このオプションが使用可能であり、選択した場合、ATP の安全なリンクの保護は、電子メール アカウントを提供する、組織内のユーザー間で送信されるメッセージは、Office 365 でホストされる電子メールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="84ae6-189">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="84ae6-190">**ユーザーのクリックを追跡しません。**</span><span class="sxs-lookup"><span data-stu-id="84ae6-190">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="84ae6-p114">このオプションを選択すると、外部の送信者からの電子メール内の Url が格納されていないために、データをクリックします。URL は、組織内で送信された電子メール メッセージ内のリンクの追跡] をクリックします。 は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p114">When this option is selected, click data for URLs in email from external senders is not stored. URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="84ae6-193">**ユーザーが元の URL を使用] をクリックしてできないようにします。**</span><span class="sxs-lookup"><span data-stu-id="84ae6-193">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="84ae6-194">このオプションを選択すると、ユーザーは、悪意があると決定される URL に過去の[警告] ページ](atp-safe-links-warning-pages.md)の続行できません。</span><span class="sxs-lookup"><span data-stu-id="84ae6-194">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="84ae6-195">**次の Url の書き換えを行う**</span><span class="sxs-lookup"><span data-stu-id="84ae6-195">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="84ae6-p115">Url のままです。電子メールの受信者、組織内の特定のグループのスキャンの必要がない安全な Url のカスタム一覧を保持します。 詳細については、アスタリスクのワイルドカードをサポートするために最新の変更を含む[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください (\*)。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p115">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).  </span></span><br/> |
   
## <a name="next-steps"></a><span data-ttu-id="84ae6-199">次の手順</span><span class="sxs-lookup"><span data-stu-id="84ae6-199">Next steps</span></span>

<span data-ttu-id="84ae6-p116">ATP の安全なリンク ポリシーがあると、どの分析ツールが動作して、orgnization のレポートを表示することによって確認できます。詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="84ae6-p116">Once your ATP Safe Links policies are in place, you can see how ATP is working for your orgnization by viewing reports. See the following resources to learn more:</span></span>

- [<span data-ttu-id="84ae6-202">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="84ae6-202">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)

- [<span data-ttu-id="84ae6-203">エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="84ae6-203">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md) 