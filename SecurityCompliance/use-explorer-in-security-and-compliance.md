---
title: セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection: M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターのエクスプローラー (脅威エクスプローラーとも呼ばれます) について説明します。
ms.openlocfilehash: 439a7d53e185e12ddd5d2e19b9d88bd8c9b47dad
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30218987"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="0d910-103">セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="0d910-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="0d910-p101">組織に[Office 365 の脅威インテリジェンス](office-365-ti.md)があり、必要なアクセス許可が付与されている場合は、エクスプローラーを使用して脅威を識別し、分析することができます。たとえば、配信された悪意のある電子メールを特定して削除したり、Office 365 セキュリティ機能によって検出されたマルウェアを確認したりすることができます。エクスプローラー (脅威エクスプローラーとも呼ばれます) は、セキュリティ&amp; /コンプライアンスセンターの強力なほぼリアルタイムレポートです。</span><span class="sxs-lookup"><span data-stu-id="0d910-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="0d910-108">エクスプローラーを使用するには、 &amp;セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="0d910-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d910-p102">2019年2月から、次の数か月間に展開されています。 office 365 の脅威インテリジェンスは、追加の脅威保護機能を備えた office 365 Advanced threat protection プラン2になりつつあります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d910-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="0d910-111">エクスプローラーの概要</span><span class="sxs-lookup"><span data-stu-id="0d910-111">Explorer overview</span></span>

<span data-ttu-id="0d910-p103">エクスプローラーには、Office 365 の電子メールやファイルにある疑いのあるマルウェアに関する情報と、組織に対する他のセキュリティ上の脅威やリスクが表示されます。エクスプローラーを最初に開くと、既定の表示では過去7日間のウイルス対策によるマルウェアの検出が表示されます。エクスプローラーには、Office 365 のセキュリティ保護機能 ([安全なリンク](atp-safe-links.md)と[安全な添付ファイル](atp-safe-attachments.md)を含む) を表示することもできます。これにより、過去30日間のデータを表示するように変更することができます。</span><span class="sxs-lookup"><span data-stu-id="0d910-p103">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![エクスプローラーは、上位マルウェアと対象ユーザーに関する情報を表示します。](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="0d910-116">表示する情報を変更するには、[表示] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="0d910-116">Use the View menu to change what information is displayed.</span></span>
  
![エクスプローラーの [表示] メニュー](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="0d910-p104">エクスプローラーには、上位の対象ユーザー、上位のマルウェアファミリなどの詳細を掘り下げられるフィルター処理とクエリ機能がいくつか用意されています。各種類のレポートには、データの表示と探索にさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="0d910-p104">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d910-p105">エクスプローラーでは、アスタリスク (\*) や疑問符 (?) などのワイルドカード文字を使用しないでください。電子メールメッセージの [件名] フィールドを検索すると、エクスプローラーは部分一致を実行し、ワイルドカード検索と同様の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="0d910-p105">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="0d910-122">メール\>マルウェア</span><span class="sxs-lookup"><span data-stu-id="0d910-122">Email \> Malware</span></span>

<span data-ttu-id="0d910-123">このビューには、マルウェアを含むと識別された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-123">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="0d910-124">マルウェアファミリ、送信者のドメイン、送信者の IP、保護の状態 (Office 365 の脅威保護機能およびポリシーによって行われた操作)、検出テクノロジ (マルウェアの検出方法) に基づいて、グラフの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d910-124">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![検出されたマルウェアに関するデータを表示する](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="0d910-126">グラフの下に、上位マルウェアファミリ、上位の対象ユーザー、および特定のメッセージに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-126">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="0d910-127">電子\>メールフィッシング</span><span class="sxs-lookup"><span data-stu-id="0d910-127">Email \> Phish</span></span>

<span data-ttu-id="0d910-128">このビューには、フィッシングとして識別された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-128">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="0d910-129">送信者のドメイン、送信者の IP、および保護の状態によって情報を表示します (Office 365 の脅威保護機能およびポリシーによって実行される操作)。</span><span class="sxs-lookup"><span data-stu-id="0d910-129">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![フィッシングの試行として識別された電子メールに関するデータを表示する](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="0d910-131">グラフの下に、特定のメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d910-131">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="0d910-132">電子\>メールユーザーのレポート</span><span class="sxs-lookup"><span data-stu-id="0d910-132">Email \> User-reported</span></span>

<span data-ttu-id="0d910-133">このビューには、ユーザーが迷惑メール、迷惑メールではないメールとして報告した電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-133">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="0d910-134">レポートの種類別に情報を表示する (電子メールが迷惑メールではなく迷惑メールであったことをユーザーが決定した場合)、配信の理由 (スパムフィルターポリシー、メールフロールール、受信拒否リスト、差出人セーフリストなどの特定の場所に電子メールが送信された理由)、など)。</span><span class="sxs-lookup"><span data-stu-id="0d910-134">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![迷惑メールや迷惑メールではないと報告されたメールユーザーに関するデータを表示する](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="0d910-136">グラフの下に、件名行、送信者の IP アドレス、メッセージを迷惑メールとして報告したユーザー、迷惑メール、フィッシングなど、特定の電子メールメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d910-136">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="0d910-137">すべて\>のメールを電子メールで送信</span><span class="sxs-lookup"><span data-stu-id="0d910-137">Email \> All mail</span></span>

<span data-ttu-id="0d910-138">このビューには、フィッシングまたはマルウェアによって悪意があると識別された電子メールや、悪意のあるメール (通常の電子メール、スパム、およびバルクメール) など、すべての電子メールアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-138">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="0d910-139">**表示するデータが多すぎる**というエラーが表示された場合は、フィルターを追加し、必要に応じて、表示している日付範囲を絞り込んでください。</span><span class="sxs-lookup"><span data-stu-id="0d910-139">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="0d910-p106">フィルターを適用するには、[**送信者**] を選択し、リスト内の項目を選択してから [最新の情報に更新] をクリックします。この例では、**検出テクノロジ**をフィルタとして使用しています (複数のオプションを使用できます)。送信者、送信者のドメイン、受信者、件名、添付ファイル名、マルウェアファミリ、保護状態 (Office 365 の脅威保護機能およびポリシーによって行われた操作)、検出テクノロジ (マルウェアの検出方法)、およびもっとその。</span><span class="sxs-lookup"><span data-stu-id="0d910-p106">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![検出された電子メールに関するデータを検出テクノロジで表示する](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="0d910-144">グラフの下に、件名行、受信者、送信者、状態など、特定の電子メールメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d910-144">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="0d910-145">コンテンツ\>マルウェア</span><span class="sxs-lookup"><span data-stu-id="0d910-145">Content \> Malware</span></span>

<span data-ttu-id="0d910-146">このビューには、SharePoint Online、OneDrive for business、Microsoft Teams で悪意のあるファイルとして識別されたファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-146">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="0d910-147">マルウェアファミリ、検出テクノロジ (マルウェアの検出方法)、ワークロード (OneDrive、SharePoint、Teams) 別の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="0d910-147">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![検出されたマルウェアに関するデータを表示する](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="0d910-149">グラフの下に、添付ファイルのファイル名、ワークロード、ファイルのサイズ、ファイルを最後に変更したユーザーなど、特定のファイルの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-149">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="0d910-150">(新)クリックフィルター機能</span><span class="sxs-lookup"><span data-stu-id="0d910-150">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="0d910-p107">エクスプローラーを新規にクリックすると、フィルター処理することができます。2018年5月後期に凡例の項目をクリックすると、その項目がレポートのフィルターになります。たとえば、エクスプローラーのマルウェアビューを見ているとします。</span><span class="sxs-lookup"><span data-stu-id="0d910-p107">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="0d910-155">このグラフの [ **ATP 分析**] をクリックすると、次のような表示になります。</span><span class="sxs-lookup"><span data-stu-id="0d910-155">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![ATO 分析の結果のみを表示するためにフィルター処理されたエクスプローラー](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="0d910-p108">このビューでは、 [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)によって分析されたファイルのデータを調べています。チャートの下には、ATP の安全な添付ファイルによって検出された添付ファイルがある特定の電子メールメッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-p108">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![検出された添付ファイルを含む電子メールメッセージに関する具体的な詳細情報](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="0d910-160">1つまたは複数のアイテムを選択すると、[ **Actions** ] メニューがアクティブ化され、選択したアイテムに対して選択できるいくつかの選択肢が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0d910-160">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![アイテムを選択すると、[アクション] メニューがアクティブになります。](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="0d910-162">クリックして特定の詳細に移動する機能を使用すると、脅威の調査に長い時間をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="0d910-162">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="0d910-163">エクスプローラーを入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="0d910-163">How do I get Explorer?</span></span>

<span data-ttu-id="0d910-164">エクスプローラーは、 [Office 365 の脅威インテリジェンス](office-365-ti.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0d910-164">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="0d910-p109">エクスプローラーを表示および使用するには、セキュリティ管理者やセキュリティリーダーに付与されている適切なアクセス許可を持っている必要があります。詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0d910-p109">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0d910-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="0d910-167">Related topics</span></span>

[<span data-ttu-id="0d910-168">Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="0d910-168">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="0d910-169">配信された悪意のある電子メールを検索して調査する (Office 365 の脅威インテリジェンス)</span><span class="sxs-lookup"><span data-stu-id="0d910-169">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="0d910-170">Office 365 のスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="0d910-170">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

