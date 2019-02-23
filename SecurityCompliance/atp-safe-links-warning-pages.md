---
title: Office 365 ATP の安全なリンクの警告ページ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: IT Pro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
ms.collection:
- M365-security-compliance
description: Office 365 Advanced Threat Protection が機能している場合に表示される可能性がある警告ページの概要を取得します。
ms.openlocfilehash: c854b32b3750f2ccd71e1d66f9dc8f8c54564f08
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30217147"
---
# <a name="office-365-atp-safe-links-warning-pages"></a><span data-ttu-id="84a20-103">Office 365 ATP の安全なリンクの警告ページ</span><span class="sxs-lookup"><span data-stu-id="84a20-103">Office 365 ATP Safe Links warning pages</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84a20-p101">この記事は、ビジネスのお客様を対象としています。Outlook の安全なリンクに関する情報をお探しのホームユーザーの場合は、「 [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="84a20-p101">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="84a20-p102">[Office 365 Advanced Threat Protection](office-365-atp.md)(atp) は、 [atp の安全なリンク](atp-safe-links.md)、atp の安全な[添付ファイル](atp-safe-attachments.md)、[フィッシング対策保護](anti-phishing-protection.md)などの機能を介して組織をフィッシングやマルウェアから保護するのに役に立ちます。保護が設定されている場合、電子メールメッセージと Office ドキュメント内のリンク (url) はチェックされます。url が疑わしいまたは悪意のあるものとして識別された場合、その url をクリックしても url を開くことがブロックされることがあります。直接サイトに移行するのではなく、警告ページが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="84a20-p102">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) helps protect your organization from phishing attempts and malware through features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [anti-phishing protection](anti-phishing-protection.md). When protection is in place, links (URLs) in email messages and Office documents are checked. If a URL is identified as suspicious or malicious, you might be blocked from opening the URL when you click it. Instead of going directly to the site, you might see a warning page instead.</span></span> 
  
<span data-ttu-id="84a20-110">この記事では、表示される可能性がある[警告ページの例](atp-safe-links-warning-pages.md#examples)と、[警告ページに対する最新の更新プログラム](atp-safe-links-warning-pages.md#updates)を確認しています。</span><span class="sxs-lookup"><span data-stu-id="84a20-110">Read this article to see [Examples of warning pages](atp-safe-links-warning-pages.md#examples) that might appear, along with [Recent updates to warning pages](atp-safe-links-warning-pages.md#updates).</span></span>
  
## <a name="examples-of-warning-pages"></a><span data-ttu-id="84a20-111">警告ページの例</span><span class="sxs-lookup"><span data-stu-id="84a20-111">Examples of warning pages</span></span>

### <a name="atp-is-scanning-the-link"></a><span data-ttu-id="84a20-112">ATP がリンクをスキャンしています</span><span class="sxs-lookup"><span data-stu-id="84a20-112">ATP is scanning the link</span></span>

<span data-ttu-id="84a20-p103">ATP の安全なリンクによって、URL がスキャンされています。リンクを再度試すには、しばらく待つ必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="84a20-p103">A URL is being scanned by ATP Safe Links. You might have to wait a few moments to try the link again.</span></span>

![ATP がリンクをスキャンしています](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="a-url-is-in-a-suspicious-email-message"></a><span data-ttu-id="84a20-116">疑わしい電子メールメッセージ内の URL</span><span class="sxs-lookup"><span data-stu-id="84a20-116">A URL is in a suspicious email message</span></span>

<span data-ttu-id="84a20-p104">この URL は、疑わしいと思われる他の電子メールメッセージに類似した電子メールメッセージに含まれています。サイトに進む前に、電子メールメッセージをもう一度確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84a20-p104">The URL is in an email message that seems similar to other email messages that are considered suspicious. We recommend that you double-check the email message before proceeding to the site.</span></span>

![この URL は疑わしい電子メールメッセージに含まれています](media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a><span data-ttu-id="84a20-120">フィッシングの試行として識別されたメッセージ内の URL</span><span class="sxs-lookup"><span data-stu-id="84a20-120">A URL is in a message identified as a phishing attempt</span></span>

<span data-ttu-id="84a20-p105">この URL は、フィッシング攻撃として識別された電子メールメッセージに含まれています。その結果、電子メールメッセージ内のすべての url がブロックされます。サイトに進まないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84a20-p105">The URL is in an email message that has been identified as a phishing attack. As a result, all URLs in the email message are blocked. We recommend that you do not proceed to the site.</span></span>

![この URL は、フィッシングとして識別されたメッセージ内にあります。](media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="a-site-has-been-identified-as-malicious"></a><span data-ttu-id="84a20-125">サイトが悪意のあるものとして識別された</span><span class="sxs-lookup"><span data-stu-id="84a20-125">A site has been identified as malicious</span></span>

<span data-ttu-id="84a20-126">URL は、悪意があると識別されたサイトを指しています。</span><span class="sxs-lookup"><span data-stu-id="84a20-126">The URL points to a site that has been identified as malicious.</span></span>  <br/> <span data-ttu-id="84a20-127">サイトに進まないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84a20-127">We recommend that you do not proceed to the site.</span></span>

![このサイトは悪意のあるものとして識別されています。](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="a-site-is-blocked"></a><span data-ttu-id="84a20-129">サイトがブロックされている</span><span class="sxs-lookup"><span data-stu-id="84a20-129">A site is blocked</span></span>

<span data-ttu-id="84a20-p106">組織の URL がブロックされています。URL がブロックされる理由はいくつかあります。組織の Office 365 管理者に連絡することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="84a20-p106">The URL is blocked for your organization. There are several reasons why a URL might be blocked. We recommend that you contact your organization's Office 365 administrator.</span></span>

![このサイトはブロックされています](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="an-error-has-occurred"></a><span data-ttu-id="84a20-134">エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="84a20-134">An error has occurred</span></span>

<span data-ttu-id="84a20-135">何らかのエラーが発生し、URL を開くことができません。</span><span class="sxs-lookup"><span data-stu-id="84a20-135">Some kind of error has occurred, and the URL cannot be opened.</span></span>

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

## <a name="recent-updates-to-warning-pages"></a><span data-ttu-id="84a20-137">警告ページに対する最新の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="84a20-137">Recent updates to warning pages</span></span>

<span data-ttu-id="84a20-p107">Office 365 ATP のために最近更新された警告ページがいくつかあります。更新されたページがまだ表示されていない場合は、間もなく表示されます。更新には、新しい配色、詳細、および指定された警告と推奨事項にかかわらずサイトに進む機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="84a20-p107">Several warning pages were recently updated for Office 365 ATP. If you're not already seeing the updated pages, you will soon. The updates include a new color scheme, more details, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="url-scan-in-progress"></a><span data-ttu-id="84a20-141">進行中の URL スキャン</span><span class="sxs-lookup"><span data-stu-id="84a20-141">URL scan in progress</span></span>

<span data-ttu-id="84a20-142">元の警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-142">Original warning page:</span></span>

![進行中の URL スキャンに関する元の警告ページ](media/04368763-763f-43d6-94a4-a48291d36893.png)

<span data-ttu-id="84a20-144">更新された警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-144">Updated warning page:</span></span>

![ATP がリンクをスキャンしています](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a><span data-ttu-id="84a20-146">悪意のあるサイトの警告</span><span class="sxs-lookup"><span data-stu-id="84a20-146">Malicious site warning</span></span>

<span data-ttu-id="84a20-147">元の警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-147">Original warning page:</span></span>

![悪意のあるサイトに関する元の警告ページ](media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

<span data-ttu-id="84a20-149">更新された警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-149">Updated warning page:</span></span>

![このサイトは悪意のあるものとして識別されています。](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="84a20-151">ブロックされた URL の警告</span><span class="sxs-lookup"><span data-stu-id="84a20-151">Blocked URL warning</span></span>

<span data-ttu-id="84a20-152">元の警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-152">Original warning page:</span></span>

![ブロックされた URL に関する元の警告ページ](media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

<span data-ttu-id="84a20-154">更新された警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-154">Updated warning page:</span></span>

![このサイトはブロックされています](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a><span data-ttu-id="84a20-156">"エラーが発生しました" の警告ページ</span><span class="sxs-lookup"><span data-stu-id="84a20-156">"Error occurred" warning page</span></span>

<span data-ttu-id="84a20-157">元の警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-157">Original warning page:</span></span>

![元の "エラーが発生しました" という警告ページ](media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

<span data-ttu-id="84a20-159">更新された警告ページ:</span><span class="sxs-lookup"><span data-stu-id="84a20-159">Updated warning page:</span></span>

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
   
