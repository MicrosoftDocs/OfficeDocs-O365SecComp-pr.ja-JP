---
title: Office 365 の ATP の安全なリンクのポリシーを設定します
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 5/30/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
description: Word、Excel、PowerPoint、および Visio のファイルおよび電子メール メッセージ内の悪意のあるリンクから組織を保護するために、安全なリンクのポリシーを設定します。
ms.openlocfilehash: 0f43cf1eec63df4b70f88abf36e8f097da72ebbc
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532587"
---
# <a name="set-up-office-365-atp-safe-links-policies"></a><span data-ttu-id="199ee-103">Office 365 の ATP の安全なリンクのポリシーを設定します</span><span class="sxs-lookup"><span data-stu-id="199ee-103">Set up Office 365 ATP Safe Links policies</span></span>

<span data-ttu-id="199ee-p101">[ATP の安全なリンク](atp-safe-links.md)、 [Office 365 の高度な脅威保護](office-365-atp.md)(ATP) の機能は、フィッシングやその他の攻撃で使用される、悪意のあるリンクから組織を保護するために役立ちます。必要がある場合[Office 365 のセキュリティに割り当てられたアクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)ATP の安全なリンク ポリシーをセットアップするには、web アドレス (Url) をクリックすることを確認のために、組織を保護します。メール内の Url、および Office ドキュメント内の Url をスキャンするのには、ATP の安全なリンク ポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="199ee-p101">[ATP Safe Links](atp-safe-links.md) , a feature of [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), can help protect your organization from malicious links used in phishing and other attacks. If you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md), you can set up ATP Safe Links policies to help ensure that when people click web addresses (URLs), your organization is protected. Your ATP Safe Links policies can be configured to scan URLs in email and URLs in Office documents.</span></span>
  
<span data-ttu-id="199ee-107">新機能は、ATP の安全なリンクに追加されている継続的にします。</span><span class="sxs-lookup"><span data-stu-id="199ee-107">New features are continually being added to ATP Safe Links:</span></span>
  
- <span data-ttu-id="199ee-108">遅延の年 2017年 10 月で ATP の安全なリンクの保護は、Word、Excel、PowerPoint ウィンドウ、iOS および Android デバイスは、Windows 上の Visio ファイルなど、Office 365 用リソースのドキュメントの Url と、電子メール内の Url に適用する拡張されます。</span><span class="sxs-lookup"><span data-stu-id="199ee-108">In late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint on Windows, iOS, and Android devices, and Visio files on Windows.</span></span>
    
- <span data-ttu-id="199ee-109">2018年 3 月で以降では、ATP の安全なリンクの保護は、組織内のユーザー間で送信される電子メールに適用する拡張されます。</span><span class="sxs-lookup"><span data-stu-id="199ee-109">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people in an organization.</span></span>
    
- <span data-ttu-id="199ee-110">遅延 2018年 3 月で以降では、(オンラインの Word、Excel のオンライン、PowerPoint オンラインでは、および OneNote オンライン) オンライン Office および Office 365 用リソースを Mac OS での Url に適用する分析ツールの安全なリンクの保護が拡張されます。</span><span class="sxs-lookup"><span data-stu-id="199ee-110">Beginning in late March 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac OS.</span></span>
    
- <span data-ttu-id="199ee-111">月 2018年で以降では、新しい配色パターン、詳細については、特定の推奨事項があってもサイトを継続する機能と[警告のページ](atp-safe-links-warning-pages.md)が更新されます。</span><span class="sxs-lookup"><span data-stu-id="199ee-111">Beginning in May 2018, [warning pages](atp-safe-links-warning-pages.md) are updated with a new color scheme, more details, and the ability to continue to a site despite the given recommendations.</span></span> 

<span data-ttu-id="199ee-112">新機能が追加されるは、既存の分析ツールの安全なリンク ポリシーを調整する必要があります。</span><span class="sxs-lookup"><span data-stu-id="199ee-112">As new features are added, you may need to make adjustments to your existing ATP Safe Links policies.</span></span>

## <a name="what-to-do"></a><span data-ttu-id="199ee-113">行うこと</span><span class="sxs-lookup"><span data-stu-id="199ee-113">What to do</span></span> 
  
1. [<span data-ttu-id="199ee-114">前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="199ee-114">Review the prerequisites</span></span>](#review-the-prerequisites)
    
2. <span data-ttu-id="199ee-115">[を定義するすべてのユーザーに適用される、ATP の安全なリンク ポリシー](set-up-atp-safe-links-policies.md#reveddefaultscc)、 [ATP の安全なリンクをユーザー設定のブロックされた Url リストの設定](set-up-a-custom-blocked-urls-list-wtih-atp.md)を含む</span><span class="sxs-lookup"><span data-stu-id="199ee-115">[Define an ATP Safe Links policy that applies to everyone](set-up-atp-safe-links-policies.md#reveddefaultscc), including [setting up your custom blocked URLs list for ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md)</span></span>
    
3. <span data-ttu-id="199ee-116">[特定の電子メールの受信者ポリシーを追加](set-up-atp-safe-links-policies.md#addemailpolscc) [ATP の安全なリンクのカスタム」を書き換えない"Url リストの設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を含む</span><span class="sxs-lookup"><span data-stu-id="199ee-116">[Add a policy for specific email recipients](set-up-atp-safe-links-policies.md#addemailpolscc), including [setting up your custom "Do not rewrite" URLs list for ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
4. <span data-ttu-id="199ee-117">[ATP の安全なリンク ポリシーのオプションについて](set-up-atp-safe-links-policies.md#policyoptions)、最近の変更の設定を含む</span><span class="sxs-lookup"><span data-stu-id="199ee-117">[Learn about ATP Safe Links policy options](set-up-atp-safe-links-policies.md#policyoptions), including settings for recent changes</span></span>
    
## <a name="review-the-prerequisites"></a><span data-ttu-id="199ee-118">前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="199ee-118">Review the prerequisites</span></span>

- <span data-ttu-id="199ee-119">組織が[Office 365 の高度な脅威保護](office-365-atp.md)を持っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="199ee-119">Make sure that your organization has [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>
    
- <span data-ttu-id="199ee-120">必要があるかどうかを確認[Office 365 のセキュリティに割り当てられたアクセス権&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="199ee-120">Make sure that you have the necessary [permissions assigned in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="199ee-121">[ATP の安全なリンク ポリシーのオプションについて理解します。](#learn-about-atp-safe-links-policy-options)(この記事で)。</span><span class="sxs-lookup"><span data-stu-id="199ee-121">[Learn about ATP Safe Links policy options](#learn-about-atp-safe-links-policy-options) (in this article).</span></span> 
    
- <span data-ttu-id="199ee-122">最大 30 分間のすべての Office 365 のデータ センターに展開するのには、新規または更新されたポリシーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="199ee-122">Allow up to 30 minutes for your new or updated policy to spread to all Office 365 datacenters.</span></span>
    
## <a name="define-an-atp-safe-links-policy-that-applies-to-everyone"></a><span data-ttu-id="199ee-123">ATP の安全なリンクすべてのユーザーに適用されるポリシーを定義します。</span><span class="sxs-lookup"><span data-stu-id="199ee-123">Define an ATP Safe Links policy that applies to everyone</span></span>

<span data-ttu-id="199ee-p102">脅威保護の高度な Office 365 の企業である場合は、組織内の全員に適用される、ATP の安全なリンク ポリシーを定義するがあります。セキュリティのいずれかのポリシーを編集することができます&amp;コンプライアンス センターまたは、Exchange 管理センターです。セキュリティを使用することをお勧めします。&amp;コンプライアンス センターを表示または編集するポリシーとデータ分析ツールのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="199ee-p102">When you have Advanced Threat Protection in Office 365 Enterprise, you will have an ATP Safe Links policy to define that applies to everyone in your organization. You can edit your policy in either the Security &amp; Compliance Center or the Exchange admin center. We recommend using the Security &amp; Compliance Center to review or edit any of your ATP policies.</span></span>
  
1. <span data-ttu-id="199ee-127">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="199ee-127">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="199ee-128">**脅威の管理**の下で、左側のナビゲーションでは、選択**ポリシー \> ** **安全なリンク**です。</span><span class="sxs-lookup"><span data-stu-id="199ee-128">In the left navigation, under **Threat management**, choose **Policy \>** **Safe Links**.</span></span>
    
3. <span data-ttu-id="199ee-129">**組織全体に適用されるポリシー** ] セクションで **[既定**] を選択しの**編集**([編集] ボタンのような鉛筆) します。</span><span class="sxs-lookup"><span data-stu-id="199ee-129">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![安全なリンクの保護のため、既定のポリシーを編集するのにはの編集] をクリックします。](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
4. <span data-ttu-id="199ee-p103">**次の Url をブロックする**] セクションでは、訪問から、組織内のユーザーを禁止する 1 つまたは複数の Url を指定します。( [ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="199ee-p103">In the **Block the following URLs** section, specify one or more URLs that you want to prevent people in your organization from visiting. (See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).)</span></span>
    
5. <span data-ttu-id="199ee-p104">**電子メール以外のコンテンツに適用される設定**をオンまたはオフ) に使用するオプションです。(お勧めのすべてのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-p104">In the **Settings that apply to content except email** section, select (or clear) the options you want to use. (We recommend that you select all the options.)</span></span> 
    
6. <span data-ttu-id="199ee-135">[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-135">Choose **Save**.</span></span>
    
## <a name="add-a-policy-for-specific-email-recipients"></a><span data-ttu-id="199ee-136">特定の電子メールの受信者にポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="199ee-136">Add a policy for specific email recipients</span></span>

<span data-ttu-id="199ee-p105">すべてのユーザーに対してポリシーを定義した後は、電子メールの受信者の特定のグループに対してポリシーを追加することを検討してください。これにより、既定のポリシーに対する例外を指定することができます。いずれかのセキュリティを使用してポリシーを追加することができます&amp;コンプライアンス センター (推奨) または、Exchange 管理センターです。セキュリティを使用することをお勧めします。&amp;コンプライアンス センターを表示または編集するポリシーとデータ分析ツールのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="199ee-p105">After you have defined a policy for all users, consider adding policies for specific groups of email recipients. This enables you to specify exceptions to your default policy. You can add policies using either the Security &amp; Compliance Center (recommended) or the Exchange admin center. We recommend using the Security &amp; Compliance Center to review or edit any of your ATP policies.</span></span>
  
1. <span data-ttu-id="199ee-141">[https://protection.office.com](https://protection.office.com)と、職場、学校のアカウントでサインインします。</span><span class="sxs-lookup"><span data-stu-id="199ee-141">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="199ee-142">**脅威の管理**の下で、左側のナビゲーションでは、**ポリシー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-142">In the left navigation, under **Threat management**, choose **Policy**.</span></span>
    
3. <span data-ttu-id="199ee-143">**安全なリンク**を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-143">Choose **Safe Links**.</span></span>
    
4. <span data-ttu-id="199ee-144">**特定の受信者に適用されるポリシー** ] セクションで [**新規**] をクリックして ([新規] ボタンのようなプラス記号 ( **+**))。</span><span class="sxs-lookup"><span data-stu-id="199ee-144">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)).</span></span>
    
    ![特定の電子メールの受信者の安全なリンク ポリシーを追加するのには新規を選択します。](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)
  
5. <span data-ttu-id="199ee-146">ポリシーの名前、説明、設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="199ee-146">Specify the name, description, and settings for your policy.</span></span>
    
    <span data-ttu-id="199ee-147">**の使用例:** ない直接クリックでと呼ばれる順番にクリックして特定の web サイト分析ツールの安全なリンクの保護なしに、組織内の特定のグループにユーザーを許可しないポリシーを設定するに可能性がありますを指定する次の設定を推奨します。</span><span class="sxs-lookup"><span data-stu-id="199ee-147">**Example:** To set up a policy called "no direct click through" that does not allow people in a certain group in your organization to click through to a specific website without ATP Safe Links protection, you might specify the following recommended settings:</span></span> 
    
  - <span data-ttu-id="199ee-148">[**名**] ボックスで、型を直接クリックします。</span><span class="sxs-lookup"><span data-stu-id="199ee-148">In the **Name** box, type no direct click through.</span></span>
    
  - <span data-ttu-id="199ee-149">[**説明**] ボックスで、人々 のように、しませんから、ATP の安全なリンクの確認を行わず、web サイトにアクセス] をクリックして特定のグループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="199ee-149">In the **Description** box, type a description like, Prevents people in certain groups from clicking through to a website without ATP Safe Links verification.</span></span>
    
  - <span data-ttu-id="199ee-150">[**アクションを選択**] セクション**を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="199ee-150">In the **Select the action** section, choose **On**.</span></span>
    
  - <span data-ttu-id="199ee-151">**使用の安全な添付ファイル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-151">Select **Use Safe Attachments to scan downloadable content**.</span></span>
    
  - <span data-ttu-id="199ee-152">このオプションが利用可能な場合は、**組織内で送信されるメッセージに適用の安全なリンク**を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-152">If this option is available, select **Apply Safe Links to messages sent within the organization**.</span></span>
    
  - <span data-ttu-id="199ee-153">**元の URL を使用] をクリックするユーザーを許可しない**を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-153">Select **Do not allow user to click through to original URL**.</span></span>
    
  - <span data-ttu-id="199ee-p106">(省略可能です)**次の Url の書き換えは**、組織の安全であると見なされる 1 つまたは複数の Url を指定します。( [ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください)</span><span class="sxs-lookup"><span data-stu-id="199ee-p106">(This is optional) In the **Do not rewrite the following URLs** section, specify one or more URLs that are considered to be safe for your organization. (See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md))</span></span>
    
  - <span data-ttu-id="199ee-p107">[**適用先**] セクションでは、**受信者のメンバーである**を選択し、ポリシーに追加するグループを選択し、します。**追加**を選択し、[ **ok]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="199ee-p107">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
6. <span data-ttu-id="199ee-158">[ **保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="199ee-158">Choose **Save**.</span></span>
    
## <a name="learn-about-atp-safe-links-policy-options"></a><span data-ttu-id="199ee-159">ATP の安全なリンク ポリシーのオプションについてください。</span><span class="sxs-lookup"><span data-stu-id="199ee-159">Learn about ATP Safe Links policy options</span></span>

<span data-ttu-id="199ee-p108">設定または ATP の安全なリンクのポリシーを編集すると、利用可能ないくつかのオプションが表示されます。参考までにこれらのオプションとは、次の表は各 1 つとその影響について説明します。定義または編集するポリシーの 2 つの主な種類があることに注意してください: すべてのユーザーに適用される既定のポリシーおよび特定の受信者に対して定義されているポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="199ee-p108">As you set up or edit an ATP Safe Links policy, will see several options available. In case you are wondering what these options are, the following table describes each one and its effect. Note that there are two main kinds of policies to define or edit: a default policy that applies to everyone, and additional policies that are defined for specific recipients.</span></span>
  
|<span data-ttu-id="199ee-163">**このポリシーの**</span><span class="sxs-lookup"><span data-stu-id="199ee-163">**For this policy**</span></span>|<span data-ttu-id="199ee-164">**このオプション**</span><span class="sxs-lookup"><span data-stu-id="199ee-164">**This option**</span></span>|<span data-ttu-id="199ee-165">**機能**</span><span class="sxs-lookup"><span data-stu-id="199ee-165">**Does this**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="199ee-166">既定値 (定義されると、既定のポリシーが適用されます、組織内の全員に)</span><span class="sxs-lookup"><span data-stu-id="199ee-166">Default (once defined, the default policy applies to everyone in the organization)</span></span>  <br/> |<span data-ttu-id="199ee-167">**次の Url をブロックします。**</span><span class="sxs-lookup"><span data-stu-id="199ee-167">**Block the following URLs**</span></span> <br/> |<span data-ttu-id="199ee-p109">自動的にブロックされている Url のカスタム リストを所有する組織を有効にします。ユーザーは、この一覧に URL をクリックするときは、URL がブロックされている理由を説明する[警告] ページ](atp-safe-links-warning-pages.md)に移動します。</span><span class="sxs-lookup"><span data-stu-id="199ee-p109">Enables your organization to have a custom list of URLs that are automatically blocked. When users click a URL in this list, they'll be taken to a [warning page](atp-safe-links-warning-pages.md) that explains why the URL is blocked.  </span></span><br/> <span data-ttu-id="199ee-170">最大 3 つのワイルドカードのアスタリスクを新たに追加されたサポートの詳細については[ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定する](set-up-a-custom-blocked-urls-list-wtih-atp.md)を参照してください (\*)。</span><span class="sxs-lookup"><span data-stu-id="199ee-170">See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md) for more details, such as newly added support for up to three wildcard asterisks (\*).</span></span>  <br/> |
|<span data-ttu-id="199ee-171">既定値</span><span class="sxs-lookup"><span data-stu-id="199ee-171">Default</span></span>  <br/> |<span data-ttu-id="199ee-172">**Office 365 ProPlus、オフィスの iOS および Android**</span><span class="sxs-lookup"><span data-stu-id="199ee-172">**Office 365 ProPlus, Office for iOS and Android**</span></span> <br/> |<span data-ttu-id="199ee-173">このオプションを選択すると、ATP の安全なリンクはドキュメントの Url に保護が適用される文書を開く Office 365 用リソース (Word、Excel、および PowerPoint では、Windows または Mac OS) の Office、iOS または Android デバイス、ウィンドウ、および Office オンライン (Word で Visio 2016オンライン、PowerPoint のオンライン、オンラインの Excel で、OneNote オンライン) は、Office 365 にサインインしたユーザーを提供します。</span><span class="sxs-lookup"><span data-stu-id="199ee-173">When this option is selected, ATP Safe Links protection is applied to URLs in documents that are open in Office 365 ProPlus (Word, Excel, and PowerPoint on Windows or Mac OS), Office documents on iOS, or Android devices, Visio 2016 on Windows, and Office Online (Word Online, PowerPoint Online, Excel Online, and OneNote Online), provided the user has signed into Office 365.</span></span>  <br/> <span data-ttu-id="199ee-p110">> [!TIP]> **Windows で Office 2016**のみが表示された場合、機能の更新に達していない、Office 365 環境まだ (および準備中)。それまでは、Word 2016、2016 の Excel、PowerPoint 2016 または Windows で実行されている Visio 2016 ATP の安全なリンクの保護が適用されます。</span><span class="sxs-lookup"><span data-stu-id="199ee-p110">> [!TIP]> If you see only **Office 2016 on Windows**, then the feature updates have not reached your Office 365 environment yet (and they are coming soon). Until then, ATP Safe Links protection applies to Word 2016, Excel 2016, PowerPoint 2016 or Visio 2016 running on Windows.</span></span>           |
|<span data-ttu-id="199ee-176">既定値</span><span class="sxs-lookup"><span data-stu-id="199ee-176">Default</span></span>  <br/> |<span data-ttu-id="199ee-177">**ユーザーは、ATP の安全なリンクをクリックしたときに記録しません。**</span><span class="sxs-lookup"><span data-stu-id="199ee-177">**Don't track when users click ATP Safe Links**</span></span> <br/> |<span data-ttu-id="199ee-178">このオプションを選択すると、Word、Excel、PowerPoint、および Visio のドキュメント内の Url が格納されていないために、データをクリックします。</span><span class="sxs-lookup"><span data-stu-id="199ee-178">When this option is selected, click data for URLs in Word, Excel, PowerPoint, and Visio documents is not stored.</span></span>  <br/> |
|<span data-ttu-id="199ee-179">既定値</span><span class="sxs-lookup"><span data-stu-id="199ee-179">Default</span></span>  <br/> |<span data-ttu-id="199ee-180">**ユーザーが元の URL への ATP の安全なリンクをクリックしてできないように**</span><span class="sxs-lookup"><span data-stu-id="199ee-180">**Don't let users click through ATP Safe Links to original URL**</span></span> <br/> |<span data-ttu-id="199ee-181">このオプションを選択すると、ユーザーは、悪意があると決定される URL に過去の[警告] ページ](atp-safe-links-warning-pages.md)の続行できません。</span><span class="sxs-lookup"><span data-stu-id="199ee-181">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="199ee-182">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-182">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-183">**Off**</span><span class="sxs-lookup"><span data-stu-id="199ee-183">**Off**</span></span> <br/> |<span data-ttu-id="199ee-184">電子メール メッセージ内の Url をスキャンしません。</span><span class="sxs-lookup"><span data-stu-id="199ee-184">Does not scan URLs in email messages.</span></span>  <br/> <span data-ttu-id="199ee-185">使用すると、特定の受信者グループに電子メール メッセージで Url をスキャンしないルールなど、例外の規則を定義できます。</span><span class="sxs-lookup"><span data-stu-id="199ee-185">Enables you to define an exception rule, such as a rule that does not scan URLs in email messages for a specific group of recipients.</span></span>  <br/> |
|<span data-ttu-id="199ee-186">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-186">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-187">**上**</span><span class="sxs-lookup"><span data-stu-id="199ee-187">**On**</span></span> <br/> |<span data-ttu-id="199ee-188">ユーザーが電子メール メッセージで Url をクリックすると、ATP の安全なリンクの保護を使用してルート ユーザーに Url をリライトします。</span><span class="sxs-lookup"><span data-stu-id="199ee-188">Rewrites URLs to route users through ATP Safe Links protection when the users click URLs in email messages.</span></span>  <br/> <span data-ttu-id="199ee-189">ブロックまたは悪意のある Url の一覧をクリックすると URL をチェックします。</span><span class="sxs-lookup"><span data-stu-id="199ee-189">Checks a URL when clicked against a list of blocked or malicious URLs.</span></span>  <br/> |
|<span data-ttu-id="199ee-190">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-190">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-191">**安全な添付ファイルを使用して、ダウンロード可能なコンテンツをスキャンするには**</span><span class="sxs-lookup"><span data-stu-id="199ee-191">**Use Safe Attachments to scan downloadable content**</span></span> <br/> |<span data-ttu-id="199ee-192">このオプションを選択すると、ダウンロード可能なコンテンツをポイントする Url がスキャンされます。</span><span class="sxs-lookup"><span data-stu-id="199ee-192">When this option is selected, URLs that point to downloadable content are scanned.</span></span>  <br/> |
|<span data-ttu-id="199ee-193">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-193">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-194">**安全なリンクを組織内で送信されたメッセージに適用します。**</span><span class="sxs-lookup"><span data-stu-id="199ee-194">**Apply Safe Links to messages sent within the organization**</span></span> <br/> | <span data-ttu-id="199ee-195">*この機能は 2018年 3 月にロールアウトします。*</span><span class="sxs-lookup"><span data-stu-id="199ee-195">*This feature is rolling out beginning in March 2018.*</span></span>  <br/> <span data-ttu-id="199ee-196">このオプションが使用可能であり、選択した場合、ATP の安全なリンクの保護は、電子メール アカウントを提供する、組織内のユーザー間で送信されるメッセージは、Office 365 でホストされる電子メールに適用されます。</span><span class="sxs-lookup"><span data-stu-id="199ee-196">When this option is available and selected, ATP Safe Links protection is applied to email messages sent between people in your organization, provided the email accounts are hosted in Office 365.</span></span>  <br/> |
|<span data-ttu-id="199ee-197">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-197">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-198">**ユーザーのクリックを追跡しません。**</span><span class="sxs-lookup"><span data-stu-id="199ee-198">**Do not track user clicks**</span></span> <br/> |<span data-ttu-id="199ee-199">このオプションを選択すると、外部の送信者からの電子メール内の Url が格納されていないために、データをクリックします。</span><span class="sxs-lookup"><span data-stu-id="199ee-199">When this option is selected, click data for URLs in email from external senders is not stored.</span></span>  <br/> <span data-ttu-id="199ee-200">URL は、組織内で送信された電子メール メッセージ内のリンクの追跡] をクリックします。 は現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="199ee-200">URL click tracking for links within email messages sent within the organization is currently not supported.</span></span>  <br/> |
|<span data-ttu-id="199ee-201">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-201">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-202">**ユーザーが元の URL を使用] をクリックしてできないようにします。**</span><span class="sxs-lookup"><span data-stu-id="199ee-202">**Do not allow users to click through to original URL**</span></span> <br/> |<span data-ttu-id="199ee-203">このオプションを選択すると、ユーザーは、悪意があると決定される URL に過去の[警告] ページ](atp-safe-links-warning-pages.md)の続行できません。</span><span class="sxs-lookup"><span data-stu-id="199ee-203">When this option is selected, users cannot proceed past a [warning page](atp-safe-links-warning-pages.md) to a URL that is determined to be malicious.</span></span>  <br/> |
|<span data-ttu-id="199ee-204">特定の電子メールの受信者用に作成されたポリシー</span><span class="sxs-lookup"><span data-stu-id="199ee-204">A policy created for specific email recipients</span></span>  <br/> |<span data-ttu-id="199ee-205">**次の Url の書き換えを行う**</span><span class="sxs-lookup"><span data-stu-id="199ee-205">**Do not rewrite the following URLs**</span></span> <br/> |<span data-ttu-id="199ee-p111">Url のままです。電子メールの受信者、組織内の特定のグループのスキャンの必要がない安全な Url のカスタム一覧を保持します。</span><span class="sxs-lookup"><span data-stu-id="199ee-p111">Leaves URLs as they are. Keeps a custom list of safe URLs that don't need scanning for a specific group of email recipients in your organization.  </span></span><br/> <span data-ttu-id="199ee-208">詳細については、アスタリスクのワイルドカードをサポートするために最新の変更を含む[ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)を参照してください (\*)。</span><span class="sxs-lookup"><span data-stu-id="199ee-208">See [Set up a custom "Do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for more details, including recent changes to support for wildcard asterisks (\*).</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="199ee-209">関連項目</span><span class="sxs-lookup"><span data-stu-id="199ee-209">Related topics</span></span>

[<span data-ttu-id="199ee-210">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="199ee-210">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="199ee-211">Office 365 で ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="199ee-211">ATP Safe Links in Office 365</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="199ee-212">ATP の安全な添付ファイルを Office 365 で</span><span class="sxs-lookup"><span data-stu-id="199ee-212">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="199ee-213">ATP の安全なリンクを使用してカスタムのブロックされた Url リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="199ee-213">Set up a custom blocked URLs list using ATP Safe Links</span></span>](set-up-a-custom-blocked-urls-list-wtih-atp.md)
  
[<span data-ttu-id="199ee-214">ATP の安全なリンクを使用してカスタム」を書き換えない"Url リストを設定します。</span><span class="sxs-lookup"><span data-stu-id="199ee-214">Set up a custom "Do not rewrite" URLs list using ATP Safe Links</span></span>](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
  
[<span data-ttu-id="199ee-215">脅威の高度な保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="199ee-215">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)

[<span data-ttu-id="199ee-216">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="199ee-216">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  

