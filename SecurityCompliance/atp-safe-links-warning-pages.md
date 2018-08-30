---
title: Office 365 の ATP の安全なリンク警告ページ
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: IT Pro
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fc4e6ebb-5acc-4bc5-bad8-4f3407d1d3f4
description: 作業が Office 365 の高度な脅威保護の場合を参照する可能性があります警告ページの概要を取得します。
ms.openlocfilehash: 9cda3421a394de70dfcb759a20e13aa40f84eb2f
ms.sourcegitcommit: c35fc431a315ee8e411a95d3da20d2a44c2e6be3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "23485977"
---
# <a name="office-365-atp-safe-links-warning-pages"></a><span data-ttu-id="4fdf1-103">Office 365 の ATP の安全なリンク警告ページ</span><span class="sxs-lookup"><span data-stu-id="4fdf1-103">Office 365 ATP Safe Links warning pages</span></span>

<span data-ttu-id="4fdf1-p101">[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) は、フィッシング詐欺と[安全なリンク](atp-safe-links.md)、[安全な添付ファイル](atp-safe-attachments.md)、[フィッシング防止対策](anti-phishing-protection.md)などの機能をマルウェアから組織を保護するのに役立ちます。保護すると、電子メール メッセージ、および Office ドキュメント内のリンク (Url) がチェックされます。不審なまたは悪意のある URL が識別されると場合、は] をクリックすると、URL を開くをブロック可能性があります。サイトに直接ではなく、代わりに警告ページが表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-p101">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) helps protect your organization from phishing attempts and malware through features, such as [safe links](atp-safe-links.md), [safe attachments](atp-safe-attachments.md), and [anti-phishing protection](anti-phishing-protection.md). When protection is in place, links (URLs) in email messages and Office documents are checked. If a URL is identified as suspicious or malicious, you might be blocked from opening the URL when you click it. Instead of going directly to the site, you might see a warning page instead.</span></span> 
  
<span data-ttu-id="4fdf1-108">[警告のページへの最近の更新](atp-safe-links-warning-pages.md#updates)と、表示される[警告のページの例](atp-safe-links-warning-pages.md#examples)を参照するには、この資料を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-108">Read this article to see [Examples of warning pages](atp-safe-links-warning-pages.md#examples) that might appear, along with [Recent updates to warning pages](atp-safe-links-warning-pages.md#updates).</span></span>
  
## <a name="examples-of-warning-pages"></a><span data-ttu-id="4fdf1-109">警告ページの例</span><span class="sxs-lookup"><span data-stu-id="4fdf1-109">Examples of warning pages</span></span>

### <a name="atp-is-scanning-the-link"></a><span data-ttu-id="4fdf1-110">分析ツールでは、リンクをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-110">ATP is scanning the link</span></span>

![分析ツールでは、リンクをスキャンします。](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

<span data-ttu-id="4fdf1-p102">ATP の安全なリンクによってスキャンされる URL です。しばらくリンクをもう一度実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-p102">A URL is being scanned by ATP Safe Links. You might have to wait a few moments to try the link again.</span></span>

### <a name="a-url-is-in-a-suspicious-email-message"></a><span data-ttu-id="4fdf1-114">不審な電子メール メッセージの URL は、します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-114">A URL is in a suspicious email message</span></span>

![不審な電子メール メッセージでこの URL は、します。](media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

<span data-ttu-id="4fdf1-p103">URL は、疑わしいと考えられるその他の電子メール メッセージに類似したように見える電子メール メッセージでは。サイトに進む前に電子メール メッセージをもう一度チェックすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-p103">The URL is in an email message that seems similar to other email messages that are considered suspicious. We recommend that you double-check the email message before proceeding to the site.</span></span>

### <a name="a-url-is-in-a-message-identified-as-a-phishing-attempt"></a><span data-ttu-id="4fdf1-118">フィッシング詐欺として識別されたメッセージの URL は、します。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-118">A URL is in a message identified as a phishing attempt</span></span>

![この URL は、フィッシング詐欺として識別されたメッセージには](media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

<span data-ttu-id="4fdf1-p104">URL は、フィッシング攻撃として識別された電子メール メッセージには。その結果、電子メール メッセージ内のすべての Url がブロックされます。サイトを続行しないでことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-p104">The URL is in an email message that has been identified as a phishing attack. As a result, all URLs in the email message are blocked. We recommend that you do not proceed to the site.</span></span>

### <a name="a-site-has-been-identified-as-malicious"></a><span data-ttu-id="4fdf1-123">悪意のあるサイトが発見されました</span><span class="sxs-lookup"><span data-stu-id="4fdf1-123">A site has been identified as malicious</span></span>

![悪意あるコードとしてこのサイトが発見されました](media/058883c8-23f0-4672-9c1c-66b084796177.png)

<span data-ttu-id="4fdf1-125">URL は、悪意あるコードとして認定されているサイトを指しています。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-125">The URL points to a site that has been identified as malicious.</span></span>  <br/> <span data-ttu-id="4fdf1-126">サイトを続行しないでことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-126">We recommend that you do not proceed to the site.</span></span>

### <a name="a-site-is-blocked"></a><span data-ttu-id="4fdf1-127">サイトがブロックされています。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-127">A site is blocked</span></span>

![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="4fdf1-p105">組織の URL がブロックされます。URL をブロックする理由は、いくつか考えられます。組織の Office 365 の管理者に問い合わせることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-p105">The URL is blocked for your organization. There are several reasons why a URL might be blocked. We recommend that you contact your organization's Office 365 administrator.</span></span>

### <a name="an-error-has-occurred"></a><span data-ttu-id="4fdf1-132">エラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="4fdf1-132">An error has occurred</span></span>

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

<span data-ttu-id="4fdf1-134">何らかのエラーが発生し、URL を開くことができません。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-134">Some kind of error has occurred, and the URL cannot be opened.</span></span>

   
## <a name="recent-updates-to-warning-pages"></a><span data-ttu-id="4fdf1-135">警告のページへの最新の更新プログラム</span><span class="sxs-lookup"><span data-stu-id="4fdf1-135">Recent updates to warning pages</span></span>

<span data-ttu-id="4fdf1-p106">いくつかの警告ページは、Office 365 の ATP の最近更新されました。、更新されたページが表示されていない場合は、すぐにします。更新プログラムには、新しい配色パターン、詳細については、特定の警告と推奨事項があっても、サイトを続行することなどがあります。</span><span class="sxs-lookup"><span data-stu-id="4fdf1-p106">Several warning pages were recently updated for Office 365 ATP. If you're not already seeing the updated pages, you will soon. The updates include a new color scheme, more details, and the ability to proceed to a site despite the given warning and recommendations.</span></span>

### <a name="url-scan-in-progress"></a><span data-ttu-id="4fdf1-139">URL スキャンの進行状況</span><span class="sxs-lookup"><span data-stu-id="4fdf1-139">URL scan in progress</span></span>

<span data-ttu-id="4fdf1-140">元の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-140">Original warning page:</span></span>

![URL スキャンの進行状況についての元の警告] ページ](media/04368763-763f-43d6-94a4-a48291d36893.png)

<span data-ttu-id="4fdf1-142">更新の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-142">Updated warning page:</span></span>

![分析ツールでは、リンクをスキャンします。](media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

### <a name="malicious-site-warning"></a><span data-ttu-id="4fdf1-144">悪意のあるサイトの警告</span><span class="sxs-lookup"><span data-stu-id="4fdf1-144">Malicious site warning</span></span>

<span data-ttu-id="4fdf1-145">元の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-145">Original warning page:</span></span>

![悪意のあるサイトについての元の警告] ページ](media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

<span data-ttu-id="4fdf1-147">更新の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-147">Updated warning page:</span></span>

![悪意あるコードとしてこのサイトが発見されました](media/058883c8-23f0-4672-9c1c-66b084796177.png)

### <a name="blocked-url-warning"></a><span data-ttu-id="4fdf1-149">警告の URL をブロック</span><span class="sxs-lookup"><span data-stu-id="4fdf1-149">Blocked URL warning</span></span>

<span data-ttu-id="4fdf1-150">元の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-150">Original warning page:</span></span>

![ブロックされた URL の元の警告] ページ](media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

<span data-ttu-id="4fdf1-152">更新の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-152">Updated warning page:</span></span>

![このサイトがブロックされています。](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

### <a name="error-occurred-warning-page"></a><span data-ttu-id="4fdf1-154">「エラーが発生しました」の警告ページ</span><span class="sxs-lookup"><span data-stu-id="4fdf1-154">"Error occurred" warning page</span></span>

<span data-ttu-id="4fdf1-155">元の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-155">Original warning page:</span></span>

![元「エラーが発生しました」の警告ページ](media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)

<span data-ttu-id="4fdf1-157">更新の警告] ページ:</span><span class="sxs-lookup"><span data-stu-id="4fdf1-157">Updated warning page:</span></span>

![エラーが発生しました](media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)
  
   
## <a name="related-topics"></a><span data-ttu-id="4fdf1-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="4fdf1-159">Related topics</span></span>

[<span data-ttu-id="4fdf1-160">Office により、フィッシング詐欺から保護する方法</span><span class="sxs-lookup"><span data-stu-id="4fdf1-160">How Office helps protect you from phishing schemes</span></span>](https://support.office.com/article/be0de46a-29cd-4c59-aaaf-136cf177d593)
  
[<span data-ttu-id="4fdf1-161">Office 365 の ATP の安全なリンク</span><span class="sxs-lookup"><span data-stu-id="4fdf1-161">Office 365 ATP safe links</span></span>](atp-safe-links.md)
  
[<span data-ttu-id="4fdf1-162">Office 365 ATP の安全な添付ファイル</span><span class="sxs-lookup"><span data-stu-id="4fdf1-162">Office 365 ATP safe attachments</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="4fdf1-163">Office 365 のスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="4fdf1-163">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

