---
title: セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 03/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターのエクスプローラー (脅威エクスプローラーとも呼ばれます) について説明します。
ms.openlocfilehash: 0c86792d8ed84b43b28bde31004dc95d2fa2b547
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30693616"
---
# <a name="use-threat-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="75995-103">セキュリティ&amp; /コンプライアンスセンターで脅威エクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="75995-103">Use Threat Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="75995-104">組織に[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)があり、必要なアクセス許可を持っている場合は、脅威エクスプローラーを使用して脅威を特定して分析することができます。</span><span class="sxs-lookup"><span data-stu-id="75995-104">If your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md), and you have the necessary permissions, you can use Threat Explorer to identify and analyze threats.</span></span> <span data-ttu-id="75995-105">たとえば、配信された悪意のある電子メールを特定して削除したり、Office 365 セキュリティ機能によって検出されたマルウェアを確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="75995-105">For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features.</span></span> <span data-ttu-id="75995-106">脅威エクスプローラー (エクスプローラーとも呼ばれます) は、セキュリティ運用チームがセキュリティ&amp;コンプライアンスセンターで脅威を調査して対応するのに役立つ、ほぼリアルタイムの強力なツールです。</span><span class="sxs-lookup"><span data-stu-id="75995-106">Threat Explorer (also referred to as Explorer) is a powerful near real-time tool to help Security Operations teams investigate and respond to threats in the Security &amp; Compliance Center.</span></span>
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="75995-108">エクスプローラーを使用するには、 &amp;セキュリティ/コンプライアンスセンターで、[**脅威管理** \> **エクスプローラー**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="75995-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75995-109">office 365 脅威インテリジェンスは office 365 Advanced threat protection プラン2に加えて、追加の脅威保護機能と共に提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="75995-109">Office 365 Threat Intelligence is now Office 365 Advanced Threat Protection Plan 2, along with additional threat protection capabilities.</span></span> <span data-ttu-id="75995-110">詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75995-110">To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="75995-111">エクスプローラーの概要</span><span class="sxs-lookup"><span data-stu-id="75995-111">Explorer overview</span></span>

<span data-ttu-id="75995-112">エクスプローラーは、疑いのあるマルウェアおよびフィッシングに関する情報を、Office 365 の電子メールやファイル、および組織に対する他のセキュリティ上の脅威やリスクと共に表示します。</span><span class="sxs-lookup"><span data-stu-id="75995-112">Explorer displays information about suspected malware and phish in email and files in Office 365, as well as other security threats and risks to your organization.</span></span> <span data-ttu-id="75995-113">エクスプローラーを最初に開くと、既定の表示で過去7日間の電子メールマルウェアの検出が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-113">When you first open Explorer, the default view shows email malware detections for the past 7 days.</span></span> <span data-ttu-id="75995-114">エクスプローラーには、Office 365 のセキュリティ保護機能 ([安全なリンク](atp-safe-links.md)と[安全な添付ファイル](atp-safe-attachments.md)を含む) を表示することもできます。これにより、過去30日間のデータを表示するように変更することができます。</span><span class="sxs-lookup"><span data-stu-id="75995-114">Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span> <span data-ttu-id="75995-115">office 365 Advanced Threat Protection プラン2または office 365 E5 の試用版のサブサブスクリプションがある場合、過去7日間の検出とメールデータのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-115">If you have a trial subcription for Office 365 Advanced Threat Protection Plan 2 or Office 365 E5, you will only see detections and email data for the past 7 days.</span></span>
  
![エクスプローラーは、上位マルウェアと対象ユーザーに関する情報を表示します。](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="75995-117">表示する情報を変更するには、[表示] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="75995-117">Use the View menu to change what information is displayed.</span></span>
  
![エクスプローラーの [表示] メニュー](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="75995-119">エクスプローラーには、上位の対象ユーザー、上位マルウェアファミリ、検出テクノロジなどの詳細を掘り下げたフィルター処理とクエリ機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="75995-119">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, detection technology and more.</span></span> <span data-ttu-id="75995-120">各種類のレポートには、データの表示と探索にさまざまな方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="75995-120">Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="75995-121">エクスプローラーでは、アスタリスク (\*) や疑問符 (?) などのワイルドカード文字を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="75995-121">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer.</span></span> <span data-ttu-id="75995-122">電子メールメッセージの [件名] フィールドを検索すると、エクスプローラーは部分一致を実行し、ワイルドカード検索と同様の結果を生成します。</span><span class="sxs-lookup"><span data-stu-id="75995-122">When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="75995-123">メール\>マルウェア</span><span class="sxs-lookup"><span data-stu-id="75995-123">Email \> Malware</span></span>

<span data-ttu-id="75995-124">このビューには、マルウェアを含むと識別された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-124">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="75995-125">マルウェアファミリ、送信者のドメイン、送信者の IP、保護の状態 (Office 365 の脅威保護機能およびポリシーによって行われた操作)、検出テクノロジ (マルウェアの検出方法) に基づいて、グラフの情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="75995-125">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![検出されたマルウェアに関するデータを表示する](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="75995-127">グラフの下に、上位マルウェアファミリ、上位の対象ユーザー、および特定のメッセージに関する詳細情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-127">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="75995-128">電子\>メールフィッシング</span><span class="sxs-lookup"><span data-stu-id="75995-128">Email \> Phish</span></span>

<span data-ttu-id="75995-129">このビューには、フィッシングとして識別された電子メールメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-129">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="75995-130">送信者のドメイン、送信者の IP、および保護の状態によって情報を表示します (Office 365 の脅威保護機能およびポリシーによって実行される操作)。</span><span class="sxs-lookup"><span data-stu-id="75995-130">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![フィッシングの試行として識別された電子メールに関するデータを表示する](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="75995-132">グラフの下に、特定のメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="75995-132">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="75995-133">電子\>メールユーザーのレポート</span><span class="sxs-lookup"><span data-stu-id="75995-133">Email \> User-reported</span></span>

<span data-ttu-id="75995-134">このビューには、ユーザーが迷惑メール、迷惑メールではないメールとして報告した電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-134">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="75995-135">レポートの種類別に情報を表示する (電子メールが迷惑メールではなく迷惑メールであったことをユーザーが決定した場合)、配信の理由 (スパムフィルターポリシー、メールフロールール、受信拒否リスト、差出人セーフリストなどの特定の場所に電子メールが送信された理由)、など)。</span><span class="sxs-lookup"><span data-stu-id="75995-135">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![迷惑メールや迷惑メールではないと報告されたメールユーザーに関するデータを表示する](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="75995-137">グラフの下に、件名行、送信者の IP アドレス、メッセージを迷惑メールとして報告したユーザー、迷惑メール、フィッシングなど、特定の電子メールメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="75995-137">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="75995-138">すべて\>のメールを電子メールで送信</span><span class="sxs-lookup"><span data-stu-id="75995-138">Email \> All mail</span></span>

<span data-ttu-id="75995-139">このビューには、フィッシングまたはマルウェアによって悪意があると識別された電子メールや、悪意のあるメール (通常の電子メール、スパム、およびバルクメール) など、すべての電子メールアクティビティが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-139">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="75995-140">**表示するデータが多すぎる**というエラーが表示された場合は、フィルターを追加し、必要に応じて、表示している日付範囲を絞り込んでください。</span><span class="sxs-lookup"><span data-stu-id="75995-140">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="75995-141">フィルターを適用するには、[**送信者**] を選択し、リスト内の項目を選択してから [最新の情報に更新] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="75995-141">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button.</span></span> <span data-ttu-id="75995-142">この例では、**検出テクノロジ**をフィルタとして使用しています (複数のオプションを使用できます)。</span><span class="sxs-lookup"><span data-stu-id="75995-142">In our example, we used **Detection technology** as a filter (there are several options available).</span></span> <span data-ttu-id="75995-143">送信者、送信者のドメイン、受信者、件名、添付ファイル名、マルウェアファミリ、保護状態 (Office 365 の脅威保護機能およびポリシーによって行われた操作)、検出テクノロジ (マルウェアの検出方法)、およびもっとその。</span><span class="sxs-lookup"><span data-stu-id="75995-143">View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![検出された電子メールに関するデータを検出テクノロジで表示する](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="75995-145">グラフの下に、件名行、受信者、送信者、状態など、特定の電子メールメッセージの詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="75995-145">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="75995-146">コンテンツ\>マルウェア</span><span class="sxs-lookup"><span data-stu-id="75995-146">Content \> Malware</span></span>

<span data-ttu-id="75995-147">このビューには、SharePoint Online、OneDrive for business、Microsoft Teams で Office 365 Advanced Threat Protection によって悪意のあるファイルとして識別されたファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-147">This view shows files that were identified as malicious by Office 365 Advanced Threat Protection in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="75995-148">マルウェアファミリ、検出テクノロジ (マルウェアの検出方法)、ワークロード (OneDrive、SharePoint、Teams) 別の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="75995-148">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![検出されたマルウェアに関するデータを表示する](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="75995-150">グラフの下に、添付ファイルのファイル名、ワークロード、ファイルのサイズ、ファイルを最後に変更したユーザーなど、特定のファイルの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-150">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="75995-151">(新)クリックフィルター機能</span><span class="sxs-lookup"><span data-stu-id="75995-151">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="75995-152">エクスプローラーを新規にクリックすると、フィルター処理することができます。</span><span class="sxs-lookup"><span data-stu-id="75995-152">New to Explorer is the ability to click to filter.</span></span> <span data-ttu-id="75995-153">凡例の項目をクリックすると、その項目がレポートのフィルターになります。</span><span class="sxs-lookup"><span data-stu-id="75995-153">When you click an item in the legend, that item becomes a filter for the report.</span></span> <span data-ttu-id="75995-154">たとえば、エクスプローラーのマルウェアビューを見ているとします。</span><span class="sxs-lookup"><span data-stu-id="75995-154">For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![[脅威管理\>エクスプローラー] に移動します。](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="75995-156">このグラフの [ **ATP 分析**] をクリックすると、次のような表示になります。</span><span class="sxs-lookup"><span data-stu-id="75995-156">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![ATO 分析の結果のみを表示するためにフィルター処理されたエクスプローラー](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="75995-158">このビューでは、 [Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)によって分析されたファイルのデータを調べています。</span><span class="sxs-lookup"><span data-stu-id="75995-158">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md).</span></span> <span data-ttu-id="75995-159">チャートの下には、ATP の安全な添付ファイルによって検出された添付ファイルがある特定の電子メールメッセージに関する詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="75995-159">Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![検出された添付ファイルを含む電子メールメッセージに関する具体的な詳細情報](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="75995-161">1つまたは複数のアイテムを選択すると、[ **Actions** ] メニューがアクティブ化され、選択したアイテムに対して選択できるいくつかの選択肢が提供されます。</span><span class="sxs-lookup"><span data-stu-id="75995-161">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![アイテムを選択すると、[アクション] メニューがアクティブになります。](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="75995-163">クリックして特定の詳細に移動する機能を使用すると、脅威の調査に長い時間をかけることができます。</span><span class="sxs-lookup"><span data-stu-id="75995-163">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="75995-164">エクスプローラーを入手するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="75995-164">How do I get Explorer?</span></span>

<span data-ttu-id="75995-165">Explorer は[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="75995-165">Explorer is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md).</span></span> 

<span data-ttu-id="75995-166">エクスプローラーを表示および使用するには、セキュリティ管理者やセキュリティリーダーに付与されている適切なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75995-166">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer.</span></span> <span data-ttu-id="75995-167">詳細については、「 [Office 365 セキュリティ&amp;コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="75995-167">To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="75995-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="75995-168">Related topics</span></span>

[<span data-ttu-id="75995-169">Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="75995-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="75995-170">配信された悪意のある電子メールを検索して調査する (Office 365 の脅威 Invesitgation および応答)</span><span class="sxs-lookup"><span data-stu-id="75995-170">Find and investigate malicious email that was delivered (Office 365 Threat Invesitgation and Response)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="75995-171">Office 365 のスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="75995-171">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

