---
title: 脅威エクスプローラーのビューとリアルタイムの検出
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 03/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: 脅威エクスプローラーとリアルタイム検出で使用できるさまざまな種類のビューについて説明します。
ms.openlocfilehash: 71ec20daae45bee8385f24091850ea6223399eae
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600820"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a><span data-ttu-id="60a78-103">脅威エクスプローラーのビューとリアルタイムの検出</span><span class="sxs-lookup"><span data-stu-id="60a78-103">Views in Threat Explorer and real-time detections</span></span>

![脅威エクスプローラー](media/ThreatExplorerFirstOpened.png)

<span data-ttu-id="60a78-105">[脅威エクスプローラー](use-explorer-in-security-and-compliance.md)(およびリアルタイムの検出レポート) は、セキュリティ運用チームがセキュリティ&amp;コンプライアンスセンターで脅威を調査して対応するのに役立つ、強力でほぼリアルタイムのツールです。</span><span class="sxs-lookup"><span data-stu-id="60a78-105">[Threat Explorer](use-explorer-in-security-and-compliance.md) (and the real-time detections report) is a powerful, near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="60a78-106">エクスプローラー (およびリアルタイム検出レポート) は、疑いのあるマルウェアおよびフィッシングに関する情報を、Office 365 の電子メールとファイル、および組織に対する他のセキュリティ上の脅威やリスクと共に表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-106">Explorer (and the real-time detections report) displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> 

- <span data-ttu-id="60a78-107">[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) プラン2を使用している場合は、エクスプローラーがあります。</span><span class="sxs-lookup"><span data-stu-id="60a78-107">If you have [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2, then you have Explorer.</span></span>
- <span data-ttu-id="60a78-108">Office 365 ATP Plan 1 を使用している場合は、リアルタイムの検出があります。</span><span class="sxs-lookup"><span data-stu-id="60a78-108">If you have Office 365 ATP Plan 1, then you have real-time detections.</span></span>

<span data-ttu-id="60a78-109">エクスプローラー (またはリアルタイムの検出レポート) を最初に開いたとき、既定のビューには過去7日間の電子メールマルウェアの検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-109">When you first open Explorer (or the real-time detections report), the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="60a78-110">このレポートでは、[安全なリンク](atp-safe-links.md)によって検出された悪意のある Url、安全な[添付](atp-safe-attachments.md)ファイルによって検出された悪意のあるファイルなど、ATP の検出も表示できます。</span><span class="sxs-lookup"><span data-stu-id="60a78-110">This report can also show ATP detections, such as malicious URLs detected by [Safe Links](atp-safe-links.md), and malicious files detected by [Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="60a78-111">このレポートは、過去30日間のデータを表示するように変更できます (試用版サブスクリプションを使用している場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="60a78-111">This report can be modified to show data for the past 30 days (unless you are using a trial subscription).</span></span> <span data-ttu-id="60a78-112">試用版サブスクリプションには過去7日間のデータのみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="60a78-112">Trial subscriptions will include data for the past seven days only.</span></span>

<span data-ttu-id="60a78-113">表示する情報を変更するには、[**表示**] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="60a78-113">Use the **View** menu to change what information is displayed.</span></span> <span data-ttu-id="60a78-114">ツールヒントは、どのビューを使用するかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="60a78-114">Tooltips help you determine which view to use.</span></span>
  
![脅威エクスプローラーの [表示] メニュー](media/ThreatExplorerViewMenu.png)

<span data-ttu-id="60a78-116">ビューを選択したら、フィルターを適用してクエリを設定し、さらに分析を行います。</span><span class="sxs-lookup"><span data-stu-id="60a78-116">Once you have selected a view, you can apply filters and set up queries to conduct further analysis.</span></span> <span data-ttu-id="60a78-117">次のセクションでは、エクスプローラーで使用できるさまざまなビュー (またはリアルタイムの検出) について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="60a78-117">The following sections provide a brief overview of the various views available in Explorer (or real-time detections).</span></span>  

## <a name="email--malware"></a><span data-ttu-id="60a78-118">電子メール > マルウェア</span><span class="sxs-lookup"><span data-stu-id="60a78-118">Email > Malware</span></span>

<span data-ttu-id="60a78-119">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[**電子メール** > の**マルウェア**を**表示** > する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60a78-119">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Malware**.</span></span> <span data-ttu-id="60a78-120">このビューには、マルウェアが含まれていると識別された電子メールメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-120">This view shows information about email messages that were identified as containing malware.</span></span>  

![マルウェアとして識別された電子メールに関するデータを表示する](media/ExplorerEmailMalwareMenu.png) 

<span data-ttu-id="60a78-122">[**送信者**] をクリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="60a78-122">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="60a78-123">このリストを使用して、送信者、受信者、送信者ドメイン、件名、検出テクノロジ、保護状態などのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-123">Use this list to view data by sender, recipients, sender domain, subject, detection technology, protection status, and more.</span></span> 

<span data-ttu-id="60a78-124">たとえば、検出された電子メールメッセージに対して実行されたアクションを確認するには、リストで [**保護の状態**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60a78-124">For example, to see what actions were taken on detected email messages, choose **Protection status** in the list.</span></span> <span data-ttu-id="60a78-125">オプションを選択し、[最新の情報に更新] をクリックして、そのフィルターをレポートに適用します。</span><span class="sxs-lookup"><span data-stu-id="60a78-125">Select an option, and then click the Refresh button to apply that filter to your report.</span></span>

![脅威エクスプローラーの脅威保護状態オプション](media/ThreatExplorerProtectionStatusOptions.png)

<span data-ttu-id="60a78-127">グラフの下に、特定のメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-127">Below the chart, view more details about specific messages.</span></span> <span data-ttu-id="60a78-128">リスト内の項目を選択すると、フライアウトウィンドウが開き、選択した項目の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60a78-128">When you select an item in the list, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![ポップアップが開かれた脅威エクスプローラー](media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a><span data-ttu-id="60a78-130">電子メール > フィッシング</span><span class="sxs-lookup"><span data-stu-id="60a78-130">Email > Phish</span></span>

<span data-ttu-id="60a78-131">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[ **view** > **Email** > **フィッシング**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="60a78-131">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **Phish**.</span></span> <span data-ttu-id="60a78-132">このビューには、フィッシングとして識別された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-132">This view shows email messages identified as phishing attempts.</span></span>  

![フィッシングの試行として識別された電子メールに関するデータを表示する](media/ThreatExplorerEmailPhish.png) 

<span data-ttu-id="60a78-134">[**送信者**] をクリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="60a78-134">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="60a78-135">このリストを使用して、送信者、受信者、送信者ドメイン、送信者の IP、URL ドメイン、[verdict] などのデータを表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-135">Use this list to view data by sender, recipients, sender domain, sender IP, URL domain, click verdict, and more.</span></span> 

<span data-ttu-id="60a78-136">たとえば、フィッシングとして識別された Url をユーザーがクリックしたときに実行された操作を確認するには、一覧で **[Verdict]** を選択し、1つ以上のオプションを選択して、[更新] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60a78-136">For example, to see what actions were taken when people clicked on URLs that were identified as phishing attempts, choose **Click verdict** in the list, select one or more options, and then click the Refresh button.</span></span>

![フィッシングレポートの verdict オプションをクリックします。](media/ThreatExplorerEmailPhishClickVerdictOptions.png)

<span data-ttu-id="60a78-138">グラフの下に、特定のメッセージ、URL クリック、Url、および電子メールの送信元に関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-138">Below the chart, view more details about specific messages, URL clicks, URLs, and email origin.</span></span> 

![電子メールメッセージ内でフィッシングとして検出された Url](media/ThreatExplorerEmailPhishURLs.png)

<span data-ttu-id="60a78-140">検出された URL など、リスト内の項目を選択すると、フライアウトウィンドウが開き、選択した項目の詳細を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60a78-140">When you select an item in the list, such as a URL that was detected, a fly-out pane opens, where you can learn more about the item you selected.</span></span> 

![検出された URL に関する詳細](media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--user-reported"></a><span data-ttu-id="60a78-142">電子メール > ユーザーによって報告される</span><span class="sxs-lookup"><span data-stu-id="60a78-142">Email > User-reported</span></span>

<span data-ttu-id="60a78-143">このレポートを表示するには、エクスプローラー (またはリアルタイムの検出) で、[**表示** > **メール** > **ユーザー-レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60a78-143">To view this report, in Explorer (or real-time detections), choose **View** > **Email** > **User-reported**.</span></span> <span data-ttu-id="60a78-144">このビューには、ユーザーが迷惑メール、迷惑メールではないメールとして報告した電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-144">This view shows email that users have reported as junk, not junk, or phishing email.</span></span> 

![ユーザーによって報告される電子メールメッセージ](media/ThreatExplorerEmailUserReportedViewOptions.png) 

<span data-ttu-id="60a78-146">[**送信者**] をクリックして、表示オプションの一覧を開きます。</span><span class="sxs-lookup"><span data-stu-id="60a78-146">Click **Sender** to open your list of viewing options.</span></span> <span data-ttu-id="60a78-147">この一覧を使用して、送信者、受信者、レポートの種類 (電子メールが迷惑メールではないか、迷惑メールではないか、またはフィッシング) ごとに情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-147">Use this list to view information by sender, recipients, report type (the user's determination that the email was junk, not junk, or phish), and more.</span></span> 

<span data-ttu-id="60a78-148">たとえば、フィッシングとして報告された電子メールメッセージに関する情報を表示するには、[ **Sender** > **Report type**] をクリックし、[**フィッシング**] を選択してから、[更新] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="60a78-148">For example, to view information about email messages that were reported as phishing attempts, click **Sender** > **Report type**, select **Phish**, and then click the Refresh button.</span></span>

![レポートの種類のフィルター用に選択されたフィッシング](media/ThreatExplorerEmailUserReportedPhishSelected.png)

<span data-ttu-id="60a78-150">グラフの下に、件名行、送信者の IP アドレス、メッセージを迷惑メールとして報告したユーザー、迷惑メール、フィッシングなど、特定の電子メールメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-150">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

![フィッシングとして報告されたメッセージ](media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

<span data-ttu-id="60a78-152">一覧から項目を選択すると、追加の詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-152">Select an item in the list to view additional details.</span></span>

## <a name="email--all-email"></a><span data-ttu-id="60a78-153">すべてのメール > メール</span><span class="sxs-lookup"><span data-stu-id="60a78-153">Email > All email</span></span>

<span data-ttu-id="60a78-154">このレポートを表示するには、エクスプローラーで [\*\*\*\* > **すべてのメール**を**表示** > する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60a78-154">To view this report, in Explorer, choose **View** > **Email** > **All mail**.</span></span> <span data-ttu-id="60a78-155">このビューには、フィッシングまたはマルウェアによって悪意があると識別された電子メールや、悪意のあるメール (通常の電子メール、スパム、およびバルクメール) など、すべての電子メールアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-155">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="60a78-156">**表示するデータが多すぎる**というエラーが表示された場合は、フィルターを追加し、必要に応じて、表示している日付範囲を絞り込んでください。</span><span class="sxs-lookup"><span data-stu-id="60a78-156">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="60a78-157">フィルターを適用するには、[**送信者**] を選択し、リスト内の項目を選択してから [最新の情報に更新] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60a78-157">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="60a78-158">この例では、**検出テクノロジ**をフィルタとして使用しています (複数のオプションを使用できます)。</span><span class="sxs-lookup"><span data-stu-id="60a78-158">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="60a78-159">送信者、送信者のドメイン、受信者、件名、添付ファイル名、マルウェアファミリ、保護状態 (Office 365 の脅威保護機能およびポリシーによって行われた操作)、検出テクノロジ (マルウェアの検出方法)、およびもっとその。</span><span class="sxs-lookup"><span data-stu-id="60a78-159">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![検出された電子メールに関するデータを検出テクノロジで表示する](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="60a78-161">グラフの下に、件名行、受信者、送信者、状態など、特定の電子メールメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-161">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="60a78-162">コンテンツ > マルウェア</span><span class="sxs-lookup"><span data-stu-id="60a78-162">Content > Malware</span></span>

<span data-ttu-id="60a78-163">このレポートを表示するには、エクスプローラー (またはリアルタイム検出) で、[**コンテンツ** > **マルウェア**の**表示** > ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60a78-163">To view this report, in Explorer (or real-time detections), choose **View** > **Content** > **Malware**.</span></span> <span data-ttu-id="60a78-164">このビューには[、SharePoint Online、OneDrive For business、Microsoft Teams で Office 365 Advanced Threat Protection](atp-for-spo-odb-and-teams.md)によって悪意のあるファイルとして識別されたファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-164">This view shows files that were identified as malicious by [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span>

<span data-ttu-id="60a78-165">マルウェアファミリ、検出テクノロジ (マルウェアの検出方法)、ワークロード (OneDrive、SharePoint、Teams) 別の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="60a78-165">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![検出されたマルウェアに関するデータを表示する](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="60a78-167">グラフの下に、添付ファイルのファイル名、ワークロード、ファイルのサイズ、ファイルを最後に変更したユーザーなど、特定のファイルの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-167">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="click-to-filter-capabilities"></a><span data-ttu-id="60a78-168">クリックフィルター機能</span><span class="sxs-lookup"><span data-stu-id="60a78-168">Click-to-filter capabilities</span></span>

<span data-ttu-id="60a78-169">エクスプローラー (およびリアルタイム検出) を使用すると、クリックでフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="60a78-169">With Explorer (and real-time detections), you can apply a filter in a click.</span></span> <span data-ttu-id="60a78-170">凡例の項目をクリックすると、その項目がレポートのフィルターになります。</span><span class="sxs-lookup"><span data-stu-id="60a78-170">Click an item in the legend, and that item becomes a filter for the report.</span></span> <span data-ttu-id="60a78-171">たとえば、エクスプローラーのマルウェアビューを見ているとします。</span><span class="sxs-lookup"><span data-stu-id="60a78-171">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="60a78-173">このグラフの [ **ATP 分析**] をクリックすると、次のような表示になります。</span><span class="sxs-lookup"><span data-stu-id="60a78-173">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![ATP 分析の結果のみを表示するようにエクスプローラーによってフィルター処理されます。](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="60a78-175">このビューでは、 [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)によって分析されたファイルのデータを調べています。</span><span class="sxs-lookup"><span data-stu-id="60a78-175">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="60a78-176">チャートの下には、ATP の安全な添付ファイルによって検出された添付ファイルがある特定の電子メールメッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-176">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![検出された添付ファイルを含む電子メールメッセージに関する具体的な詳細情報](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="60a78-178">1つまたは複数のアイテムを選択すると、[ **Actions** ] メニューがアクティブ化され、選択したアイテムに対して選択できるいくつかの選択肢が提供されます。</span><span class="sxs-lookup"><span data-stu-id="60a78-178">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![アイテムを選択すると、[アクション] メニューがアクティブになります。](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="60a78-180">クリックして特定の詳細に移動する機能を使用すると、脅威の調査に長い時間をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="60a78-180">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>

## <a name="queries-and-filters"></a><span data-ttu-id="60a78-181">クエリとフィルター</span><span class="sxs-lookup"><span data-stu-id="60a78-181">Queries and filters</span></span>

<span data-ttu-id="60a78-182">エクスプローラー (およびリアルタイムの検出レポート) には、上位の対象ユーザー、トップのマルウェアファミリ、検出テクノロジなどの詳細を掘り下げられる、いくつかの強力なフィルターとクエリ機能があります。</span><span class="sxs-lookup"><span data-stu-id="60a78-182">Explorer (and the real-time detections report) has several powerful filters and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="60a78-183">各種類のレポートには、データの表示と探索にさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="60a78-183">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60a78-184">エクスプローラーのクエリバー (またはリアルタイムの検出) では、アスタリスク (\*) や疑問符 (?) などのワイルドカード文字を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="60a78-184">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), in the query bar for Explorer (or real-time detections).</span></span> <span data-ttu-id="60a78-185">電子メールメッセージの [件名] フィールドを検索すると、エクスプローラー (またはリアルタイムの検出) によって部分一致が実行され、ワイルドカード検索と同様の結果が得られます。</span><span class="sxs-lookup"><span data-stu-id="60a78-185">When you search on the Subject field for email messages, Explorer (or real-time detections) will perform partial matching and yield results similar to a wildcard search.</span></span>
