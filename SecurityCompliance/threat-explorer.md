---
title: 脅威エクスプローラー (およびリアルタイム検出)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/22/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターのエクスプローラー (およびリアルタイム検出) について説明します。
ms.openlocfilehash: 62ba70cb62b0c92cf65d77dfaf3eb7306e93fa98
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34415729"
---
# <a name="threat-explorer-and-real-time-detections"></a><span data-ttu-id="537d4-103">脅威エクスプローラー (およびリアルタイム検出)</span><span class="sxs-lookup"><span data-stu-id="537d4-103">Threat Explorer (and real-time detections)</span></span>

<span data-ttu-id="537d4-104">組織で[office 365 Advanced Threat Protection](office-365-atp.md) (OFFICE 365 ATP) を使用していて、[必要なアクセス許可](#required-licenses-and-permissions)がある場合は、**エクスプローラー**または**リアルタイムの検出**(以前のリアルタイムのレポート) (以前のリアルタイムのレポート) が表示されます。 [](#new-features-in-real-time-detections)!).</span><span class="sxs-lookup"><span data-stu-id="537d4-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP), and you have the [necessary permissions](#required-licenses-and-permissions), you have either **Explorer** or **real-time detections** (formerly real-time reports — [see what's new](#new-features-in-real-time-detections)!).</span></span> <span data-ttu-id="537d4-105">セキュリティ & コンプライアンスセンターで、[脅威の**管理**] に移動してから、[**エクスプローラー** ] または [**リアルタイムの検出**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-105">In the Security & Compliance Center, go to **Threat management**, and then choose **Explorer** OR **Real-time detections**.</span></span> 

|<span data-ttu-id="537d4-106">ATP プラン2を使用すると、次のように表示されることになります。</span><span class="sxs-lookup"><span data-stu-id="537d4-106">With ATP Plan 2, you see:</span></span>  |<span data-ttu-id="537d4-107">ATP プラン1では、次のように表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="537d4-107">With ATP Plan 1, you see:</span></span>  |
|---------|---------|
|![脅威エクスプローラー](media/threatmgmt-explorer.png)      |![リアルタイムの検出](media/threatmgmt-realtimedetections.png)         |

<span data-ttu-id="537d4-110">エクスプローラー (リアルタイム検出) では、強力なレポートが用意されており、セキュリティ運用チームが脅威を調査して効果的かつ効率的に応答でき、次の図のようになります。</span><span class="sxs-lookup"><span data-stu-id="537d4-110">With Explorer (or real-time detections), you have a powerful report that enables your Security Operations team to investigate and respond to threats effectively and efficiently, and it resembles the following image:</span></span> 

![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

<span data-ttu-id="537d4-112">このレポートでは、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-112">With this report, you can:</span></span>
- [<span data-ttu-id="537d4-113">Office 365 のセキュリティ機能によって検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="537d4-113">See malware detected by Office 365 security features</span></span>](#see-malware-detected-in-email-by-technology)
- <span data-ttu-id="537d4-114">[フィッシング Url に関するデータを表示し、[verdict] をクリックします。](#view-data-about-phishing-urls-and-click-verdict)</span><span class="sxs-lookup"><span data-stu-id="537d4-114">[View data about phishing URLs and click verdict](#view-data-about-phishing-urls-and-click-verdict)</span></span>
- <span data-ttu-id="537d4-115">[エクスプローラーのビューから自動化された調査と応答プロセスを開始](#start-automated-investigation-and-response)する(ATP プラン2のみ)</span><span class="sxs-lookup"><span data-stu-id="537d4-115">[Start an automated investigation and response process from a view in Explorer](#start-automated-investigation-and-response) (ATP Plan 2 only)</span></span>
- <span data-ttu-id="537d4-116">...[悪意のある電子メールの調査など](#more-ways-to-use-explorer-or-real-time-detections)</span><span class="sxs-lookup"><span data-stu-id="537d4-116">... [Investigate malicious email, and more](#more-ways-to-use-explorer-or-real-time-detections)!</span></span>

## <a name="new-features-in-real-time-detections"></a><span data-ttu-id="537d4-117">リアルタイム検出の新機能</span><span class="sxs-lookup"><span data-stu-id="537d4-117">New features in real-time detections</span></span>

<span data-ttu-id="537d4-118">Office 365 ATP Plan 1 ユーザーの場合、*リアルタイムの検出*レポートは、以前は*リアルタイムレポート*と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="537d4-118">For Office 365 ATP Plan 1 customers, the *real-time detections* report was previously referred to as *real-time reports*.</span></span> <span data-ttu-id="537d4-119">名前の変更に加えて、いくつかの新機能と拡張機能がロールアウトされています。</span><span class="sxs-lookup"><span data-stu-id="537d4-119">In addition to the name change, several new features and enhancements are rolling out:</span></span>

- <span data-ttu-id="537d4-120">フィッシングビューには、 [ATP の安全なリンク](atp-safe-links.md)によって検出された url に関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="537d4-120">In the Phish view, you can see more details about detected URLs through [ATP Safe Links](atp-safe-links.md).</span></span> <span data-ttu-id="537d4-121">新しい詳細と機能は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="537d4-121">New details and capabilities include:</span></span>
  - <span data-ttu-id="537d4-122">電子メールメッセージ内の Url</span><span class="sxs-lookup"><span data-stu-id="537d4-122">URLs in email messages</span></span>
  - <span data-ttu-id="537d4-123">URL 情報に基づくフィルター処理</span><span class="sxs-lookup"><span data-stu-id="537d4-123">Filtering based on URL information</span></span>
  - <span data-ttu-id="537d4-124">データグラフに表示される URL 情報</span><span class="sxs-lookup"><span data-stu-id="537d4-124">URL information displayed in data graphs</span></span>
  - <span data-ttu-id="537d4-125">メッセージ内のクリックに関するクリック時間データ</span><span class="sxs-lookup"><span data-stu-id="537d4-125">Time-of-click data about clicks in messages</span></span>

- <span data-ttu-id="537d4-126">URL が変更されるたびに、[verdict] をクリックすると、警告が表示されます。</span><span class="sxs-lookup"><span data-stu-id="537d4-126">Whenever there's a change in a URL click verdict, you'll see an alert.</span></span> <span data-ttu-id="537d4-127">URL クリック verdicts は、URL の評価が分析に変更されたとき、または ATP の安全なリンクによって保護されているユーザーが[atp の安全なリンクの警告](atp-safe-links-warning-pages.md)を上書きしたときに変更できます。</span><span class="sxs-lookup"><span data-stu-id="537d4-127">URL click verdicts can change when a URL’s reputation changes post-detonation, or when a user who's protected by ATP Safe Links overrides an [ATP Safe Links warning](atp-safe-links-warning-pages.md).</span></span>  
 
<span data-ttu-id="537d4-128">これらの機能拡張によって、組織のセキュリティ管理者は以前よりも詳細な情報を表示できるようになります。</span><span class="sxs-lookup"><span data-stu-id="537d4-128">These enhancements enable your organization's security administrators to view more details than before.</span></span> <span data-ttu-id="537d4-129">セキュリティ管理者は、URL ドメイン、不在 Url、[verdicts] などの情報を参照し、Office 365 ATP ポリシーを適切に調整することができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-129">Security administrators can view information about URL domains, missed URLs, click verdicts, and more, and then adjust Office 365 ATP policies appropriately.</span></span>

> [!NOTE]
> <span data-ttu-id="537d4-130">これらの機能はプレビュー段階にありますが、URL データは限られた日数のみ利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="537d4-130">While these features are in preview, URL data will be available for a limited number of days.</span></span> 

## <a name="see-malware-detected-in-email-by-technology"></a><span data-ttu-id="537d4-131">テクノロジによる電子メールで検出されたマルウェアを参照</span><span class="sxs-lookup"><span data-stu-id="537d4-131">See malware detected in email by technology</span></span>

<span data-ttu-id="537d4-132">Office 365 テクノロジを使用して、電子メールで検出されたマルウェアを確認する必要があるとします。</span><span class="sxs-lookup"><span data-stu-id="537d4-132">Suppose you want to see malware detected in email, by Office 365 technology.</span></span> <span data-ttu-id="537d4-133">これを行うには、エクスプローラーの [ [Email _GT_ マルウェア](threat-explorer-views.md#email--malware)] ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="537d4-133">To do this, use the [Email > Malware](threat-explorer-views.md#email--malware) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="537d4-134">セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-134">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="537d4-135">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="537d4-135">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="537d4-136">[**表示**] メニューで、[**電子メール** > **マルウェア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-136">In the **View** menu, choose **Email** > **Malware**.</span></span><br/><span data-ttu-id="537d4-137">![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailMalwareMenu.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-137">![View menu for Explorer](media/ExplorerViewEmailMalwareMenu.png)</span></span><br/>

3. <span data-ttu-id="537d4-138">[**送信者**] をクリックし、[**基本** > **検出テクノロジ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-138">Click **Sender**, and then choose **Basic** > **Detection technology**.</span></span><br/><span data-ttu-id="537d4-139">これで、検出テクノロジがレポートのフィルターとして使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="537d4-139">Your detection technologies are now available as filters for the report.</span></span><br/><span data-ttu-id="537d4-140">![マルウェア検出テクノロジ](media/ExplorerEmailMalwareDetectionTech.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-140">![Malware detection technologies](media/ExplorerEmailMalwareDetectionTech.png)</span></span><br/> 

4. <span data-ttu-id="537d4-141">オプションを選択し、[**更新**] ボタンをクリックしてそのフィルターを適用します。</span><span class="sxs-lookup"><span data-stu-id="537d4-141">Select an option, and then click the **Refresh** button to apply that filter.</span></span><br/><span data-ttu-id="537d4-142">![選択されている検出テクノロジ](media/ExplorerEmailMalwareDetectionTechATP.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-142">![Selected detection technology](media/ExplorerEmailMalwareDetectionTechATP.png)</span></span><br/> 

<span data-ttu-id="537d4-143">レポートが更新され、選択した [テクノロジ] オプションを使用して、電子メールで検出された結果のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="537d4-143">The report refreshes to show the results malware detected in email, using the technology option you selected.</span></span> <span data-ttu-id="537d4-144">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-144">From here, you can conduct further analysis.</span></span>

## <a name="view-data-about-phishing-urls-and-click-verdict"></a><span data-ttu-id="537d4-145">フィッシング Url に関するデータを表示し、[verdict] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="537d4-145">View data about phishing URLs and click verdict</span></span>

<span data-ttu-id="537d4-146">許可された Url の一覧を含む、電子メール内の Url によるフィッシングの試行、禁止、および上書きを確認するとします。</span><span class="sxs-lookup"><span data-stu-id="537d4-146">Suppose that you want to see phishing attempts through URLs in email, including a list of URLs that were allowed, blocked, and overridden.</span></span> <span data-ttu-id="537d4-147">クリックされた Url を識別するには、 [ATP の安全なリンク](atp-safe-links.md)を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="537d4-147">Identifying URLs that were clicked requires [ATP Safe links](atp-safe-links.md) to be configured.</span></span> <span data-ttu-id="537d4-148">[クリック時の保護とログ記録のための、 [atp の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)を設定していることを確認してください] verdicts の [安全なリンク] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="537d4-148">Make sure that you have set up [ATP Safe Links policies](set-up-atp-safe-links-policies.md) for time-of-click protection and logging of click verdicts by ATP Safe Links.</span></span> 

<span data-ttu-id="537d4-149">メッセージ内のフィッシング Url を確認し、フィッシングメッセージで Url をクリックするには、Explorer の [[電子メール _GT_ フィッシング](threat-explorer-views.md#email--phish)ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="537d4-149">To review phish URLs in messages and clicks on URLs in phish messages, use the [Email > Phish](threat-explorer-views.md#email--phish) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="537d4-150">セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-150">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="537d4-151">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="537d4-151">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="537d4-152">[**表示**] メニューの [**電子メール** > **フィッシング**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="537d4-152">In the **View** menu, choose **Email** > **Phish**.</span></span><br/><span data-ttu-id="537d4-153">![エクスプローラーの [表示] メニュー](media/ExplorerViewEmailPhishMenu.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-153">![View menu for Explorer](media/ExplorerViewEmailPhishMenu.png)</span></span><br/>

3. <span data-ttu-id="537d4-154">[**送信者**] をクリックし、[ **url** > ] を選択して、**[verdict] をクリック**します。</span><span class="sxs-lookup"><span data-stu-id="537d4-154">Click **Sender**, and then choose **URLs** > **Click verdict**.</span></span>

4. <span data-ttu-id="537d4-155">1つまたは複数のオプション ([**ブロック**されて**ブロック**する] など) を選択し、[**更新**] ボタンをクリックして、そのフィルターを適用するオプションと同じ行にあるものをクリックします。</span><span class="sxs-lookup"><span data-stu-id="537d4-155">Select one or more options, such as **Blocked** and **Block overridden**, and then click the **Refresh** button that is on the same line as the options to apply that filter.</span></span> <span data-ttu-id="537d4-156">(ブラウザーウィンドウを更新しないでください)。</span><span class="sxs-lookup"><span data-stu-id="537d4-156">(Don't refresh your browser window.)</span></span><br/><span data-ttu-id="537d4-157">![Url および [verdicts] をクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-157">![URLs and click verdicts](media/ThreatExplorerEmailPhishClickVerdictOptions.png)</span></span><br/>

    <span data-ttu-id="537d4-158">レポートが更新され、[URL] タブにレポートの下に2つの異なる URL テーブルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="537d4-158">The report refreshes to show two different URL tables on the URL tab under the report:</span></span>

   1. <span data-ttu-id="537d4-159">**トップ url**は、フィルター処理されたメッセージに含まれる url と、各 url の電子メール配信アクション数を示します。</span><span class="sxs-lookup"><span data-stu-id="537d4-159">**Top URLs** are the URLs contained in the messages you have filtered down to, and the email delivery action counts for each URL.</span></span> <span data-ttu-id="537d4-160">[フィッシング email] ビューには、通常、正当な Url が含まれています。</span><span class="sxs-lookup"><span data-stu-id="537d4-160">In the phish email view, this list typically will contain legitimate URLs.</span></span> <span data-ttu-id="537d4-161">攻撃者は、適切な Url と正しくない Url をメッセージに混在させて配信を試みることができますが、ユーザーがクリックすると、悪意のあるリンクがより興味深いものになります。</span><span class="sxs-lookup"><span data-stu-id="537d4-161">Attackers include a mix of good and bad URLs in their messages to try to get them delivered, but they will make the malicious links more interesting for the user to click.</span></span> <span data-ttu-id="537d4-162">Url の表は、電子メールの合計数によって並べ替えられます (注: この列はビューを簡略化するために表示されていません)。</span><span class="sxs-lookup"><span data-stu-id="537d4-162">The table of URLs is sorted by total email count (NOTE: This column is not shown to simplify the view).</span></span>

   2. <span data-ttu-id="537d4-163">**トップクリック**は、クリックされた url をラップした安全なリンクです。 [合計] をクリックします (この列はビューを簡略化するためにも表示されません)。</span><span class="sxs-lookup"><span data-stu-id="537d4-163">**Top clicks** are the Safe Links wrapped URLs that were clicked, sorted by total click count (this column is also not shown to simplify the view).</span></span> <span data-ttu-id="537d4-164">列別の合計カウント [セーフリンク] は、クリックされた各 URL の [verdict count] を示します。</span><span class="sxs-lookup"><span data-stu-id="537d4-164">Total counts by column indicate the Safe Links click verdict count for each clicked URL.</span></span> <span data-ttu-id="537d4-165">フィッシングの電子メール表示では、多くの場合、疑わしいまたは悪意のある Url ですが、フィッシングメッセージ内にあるクリーンな Url を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-165">In the phish email view, these are more often suspicious or malicious URLs, but could include clean URLs that are in phish messages.</span></span> <span data-ttu-id="537d4-166">ラップされていないリンクの URL クリックは表示されません。</span><span class="sxs-lookup"><span data-stu-id="537d4-166">URL clicks on unwrapped links will not show up here.</span></span>
   
   <span data-ttu-id="537d4-167">2つの Url 表は、配信アクションと場所によって、フィッシングメールの上位の Url を示しています。また、ブロックされた (または警告によってアクセスされた) URL クリックが表示されるので、ユーザーが無効にしたり、ユーザーによって操作された潜在的なリンクを知ることができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-167">The two URLs tables show top URLs in phishing emails by delivery action and location, and they show URL clicks that were blocked (or visited despite a warning) so that you can understand what potential bad links were received by users and interacted with by users.</span></span> <span data-ttu-id="537d4-168">ここから、さらに分析を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-168">From here, you can conduct further analysis.</span></span> <span data-ttu-id="537d4-169">たとえば、グラフの下に、組織の環境でブロックされたメールの上位の Url が表示されます。</span><span class="sxs-lookup"><span data-stu-id="537d4-169">For example, below the chart, you can see the top URLs in emails that were blocked in your organization's environment.</span></span>
   
   ![ブロックされたエクスプローラーの Url](media/ExplorerPhishClickVerdictURLs.png)
   
   <span data-ttu-id="537d4-171">URL を選択して、詳細情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="537d4-171">Select a URL to view more detailed information.</span></span> <span data-ttu-id="537d4-172">[URL] ポップアップダイアログでは、メールのフィルタリングが削除されて、環境内の URL の公開が完全に表示されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="537d4-172">Note that in the URL flyout dialog, the filtering on emails is removed to show you the full view of the URL's exposure in your environment.</span></span> <span data-ttu-id="537d4-173">これにより、懸念されているものに対してエクスプローラーでメールをフィルター処理し、潜在的な脅威である特定の Url を見つけ、url フィルターを追加することなく、環境内の URL の公開について理解を深めることができます。エクスプローラービュー自体。</span><span class="sxs-lookup"><span data-stu-id="537d4-173">This lets you filter down emails in Explorer to ones you are concerned about, find specific URLs that are potential threats, then expand your understanding of the URL exposure in your environment (via the URL details dialog) without having to add URL filters to the Explorer view itself.</span></span>

## <a name="review-email-messages-reported-by-users"></a><span data-ttu-id="537d4-174">ユーザーが報告した電子メールメッセージを確認する</span><span class="sxs-lookup"><span data-stu-id="537d4-174">Review email messages reported by users</span></span>

<span data-ttu-id="537d4-175">組織内のユーザーが、 [outlook 用のレポートメッセージアドインと web 上の outlook](enable-the-report-message-add-in.md)を使用して、迷惑メールではなく迷惑メールとして報告した電子メールメッセージを表示したいとします。</span><span class="sxs-lookup"><span data-stu-id="537d4-175">Suppose that you want to see email messages that users in your organization have reported as Junk, Not Junk, or Phishing by using the [Report Message add-in for Outlook and Outlook on the web](enable-the-report-message-add-in.md).</span></span> <span data-ttu-id="537d4-176">これを行うには、[電子メール > のユーザーレポート](threat-explorer-views.md#email--user-reported)ビュー (またはリアルタイムの検出) を使用します。</span><span class="sxs-lookup"><span data-stu-id="537d4-176">To do this, use the [Email > User-reported](threat-explorer-views.md#email--user-reported) view of Explorer (or real-time detections).</span></span>

1. <span data-ttu-id="537d4-177">セキュリティ & コンプライアンス[https://protection.office.com](https://protection.office.com)センター () で、[**脅威管理** > **エクスプローラー** (または**リアルタイムの検出**)] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-177">In the Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), choose **Threat management** > **Explorer** (or **Real-time detections**).</span></span> <span data-ttu-id="537d4-178">(この例ではエクスプローラーを使用しています)。</span><span class="sxs-lookup"><span data-stu-id="537d4-178">(This example uses Explorer.)</span></span>

2. <span data-ttu-id="537d4-179">[**表示**] メニューで、[**電子メール** > **ユーザー-レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-179">In the **View** menu, choose **Email** > **User-reported**.</span></span><br/><span data-ttu-id="537d4-180">![エクスプローラーの [表示] メニュー](media/ExplorerViewMenuEmailUserReported.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-180">![View menu for Explorer](media/ExplorerViewMenuEmailUserReported.png)</span></span><br/>

3. <span data-ttu-id="537d4-181">[**送信者**] をクリックし、[**基本** > **レポートの種類**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="537d4-181">Click **Sender**, and then choose **Basic** > **Report type**.</span></span>

4. <span data-ttu-id="537d4-182">オプション (**フィッシング**など) を選択し、[**更新**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="537d4-182">Select an option, such as **Phish**, and then click the **Refresh** button.</span></span> <br/><span data-ttu-id="537d4-183">![ユーザーによって報告されるフィッシング](media/EmailUserReportedReportType.png)</span><span class="sxs-lookup"><span data-stu-id="537d4-183">![User-reported phish](media/EmailUserReportedReportType.png)</span></span><br/> 

<span data-ttu-id="537d4-184">レポートが更新され、組織内のユーザーがフィッシングとして報告した電子メールメッセージに関するデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="537d4-184">The report refreshes to show data about email messages that people in your organization have reported as a phishing attempt.</span></span> <span data-ttu-id="537d4-185">この情報を使用して、さらに分析を行い、必要に応じて、 [ATP のフィッシング対策ポリシー](set-up-anti-phishing-policies.md)を調整することができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-185">You can use this information to conduct further analysis, and if necessary, adjust your [ATP anti-phishing policies](set-up-anti-phishing-policies.md).</span></span>

## <a name="start-automated-investigation-and-response"></a><span data-ttu-id="537d4-186">自動調査と応答の開始</span><span class="sxs-lookup"><span data-stu-id="537d4-186">Start automated investigation and response</span></span>

> [!NOTE]
> <span data-ttu-id="537d4-187">自動化された調査および応答機能は、 **office 365 ATP Plan 2**および**office 365 E5**で利用できます。</span><span class="sxs-lookup"><span data-stu-id="537d4-187">Automated investigation and response capabilities are available in **Office 365 ATP Plan 2** and **Office 365 E5**.</span></span>

<span data-ttu-id="537d4-188">(新)自動化された[調査と応答](automated-investigation-response-office.md)によって、セキュリティ運用チームの時間と労力を節約し、サイバー攻撃を調査および軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="537d4-188">(NEW!) [Automated investigation and response](automated-investigation-response-office.md) can save your security operations team much time and effort in investigating and mitigating cyber attacks.</span></span> <span data-ttu-id="537d4-189">セキュリティプレイブックをトリガーできる通知を構成するだけでなく、エクスプローラーのビューから自動化された調査および応答プロセスを開始できます。</span><span class="sxs-lookup"><span data-stu-id="537d4-189">In addition to configuring alerts that can trigger a security playbook, you can start an automated investigation and response process from a view in Explorer.</span></span> 

<span data-ttu-id="537d4-190">詳細については、「[例: セキュリティ管理者がエクスプローラーから調査を開始する](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="537d4-190">For details on this, see [Example: A security administrator triggers an investigation from Explorer](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).</span></span>

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a><span data-ttu-id="537d4-191">エクスプローラーを使用するその他の方法 (またはリアルタイムの検出)</span><span class="sxs-lookup"><span data-stu-id="537d4-191">More ways to use Explorer (or real-time detections)</span></span>

<span data-ttu-id="537d4-192">この記事で説明されているシナリオに加えて、エクスプローラー (またはリアルタイムの検出) で利用できるレポートオプションが他にも多数あります。</span><span class="sxs-lookup"><span data-stu-id="537d4-192">In addition to the scenarios outlined in this article, you have many more reporting options available with Explorer (or real-time detections).</span></span> 
- [<span data-ttu-id="537d4-193">配信された悪意のあるメールの検索と調査</span><span class="sxs-lookup"><span data-stu-id="537d4-193">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="537d4-194">SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイルを表示する</span><span class="sxs-lookup"><span data-stu-id="537d4-194">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](malicious-files-detected-in-spo-odb-or-teams.md)
- [<span data-ttu-id="537d4-195">脅威エクスプローラーのビューの概要 (およびリアルタイムの検出) を取得する</span><span class="sxs-lookup"><span data-stu-id="537d4-195">Get an overview of the views in Threat Explorer (and real-time detections)</span></span>](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="537d4-196">必要なライセンスとアクセス許可</span><span class="sxs-lookup"><span data-stu-id="537d4-196">Required licenses and permissions</span></span>

<span data-ttu-id="537d4-197">エクスプローラーまたはリアルタイムの検出を取得するには、 [Office 365 ATP](office-365-atp.md)が必要です。</span><span class="sxs-lookup"><span data-stu-id="537d4-197">You must have [Office 365 ATP](office-365-atp.md) to get Explorer or real-time detections.</span></span>
- <span data-ttu-id="537d4-198">Explorer は Office 365 ATP Plan 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="537d4-198">Explorer is included in Office 365 ATP Plan 2.</span></span> 
- <span data-ttu-id="537d4-199">リアルタイム検出レポートは、Office 365 ATP Plan 1 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="537d4-199">The real-time detections report is included in Office 365 ATP Plan 1.</span></span>

<span data-ttu-id="537d4-200">エクスプローラーまたはリアルタイム検出を表示して使用するには、セキュリティ管理者やセキュリティリーダーに付与されている権限など、適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="537d4-200">To view and use Explorer or real-time detections, you must have appropriate permissions, such as those granted to a security administrator or security reader.</span></span> 

- <span data-ttu-id="537d4-201">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="537d4-201">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="537d4-202">組織の管理</span><span class="sxs-lookup"><span data-stu-id="537d4-202">Organization Management</span></span>
    - <span data-ttu-id="537d4-203">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="537d4-203">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="537d4-204">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="537d4-204">Security Reader</span></span>

- <span data-ttu-id="537d4-205">Exchange Online の場合は、Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [Exchange online Powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="537d4-205">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="537d4-206">組織の管理</span><span class="sxs-lookup"><span data-stu-id="537d4-206">Organization Management</span></span>
    - <span data-ttu-id="537d4-207">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="537d4-207">View-only Organization Management</span></span>
    - <span data-ttu-id="537d4-208">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="537d4-208">View-Only Recipients role</span></span>
    - <span data-ttu-id="537d4-209">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="537d4-209">Compliance Management</span></span>

<span data-ttu-id="537d4-210">役割とアクセス許可の詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="537d4-210">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="537d4-211">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="537d4-211">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="537d4-212">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="537d4-212">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
  
