---
title: エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 11/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
description: (脅威のエクスプ ローラーとも呼ばれます) エクスプ ローラーについては、セキュリティで&amp;コンプライアンス センターです。
ms.openlocfilehash: 1b3088028651b445d890333a25804902843d915d
ms.sourcegitcommit: 7f45890ecfa5e15575df4e3ebe472a8dd8d99112
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674922"
---
# <a name="use-explorer-in-the-security-amp-compliance-center"></a><span data-ttu-id="beaaf-103">エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="beaaf-103">Use Explorer in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="beaaf-p101">場合は、組織に[Office 365 の脅威インテリジェンス](office-365-ti.md)があり、ユーザーが必要な権限を持っている場合は、識別し、脅威を分析するのにはエクスプ ローラーを使用できます。などの識別し配信された、悪意のあるメールを削除したり、Office 365 のセキュリティ機能でキャッチされたマルウェアを参照してください。(脅威のエクスプ ローラーとも呼ばれます) をエクスプ ローラーでは、強力なセキュリティ レポートをリアルタイムに近い&amp;コンプライアンス センターです。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p101">If your organization has [Office 365 Threat Intelligence](office-365-ti.md), and you have the necessary permissions, you can use Explorer to identify and analyze threats. For example, you can identify and delete malicious email that was delivered, or see malware that was caught by Office 365 security features. Explorer (also referred to as Threat Explorer) is a powerful near real-time report in the Security &amp; Compliance Center.</span></span>
  
![脅威の管理に移動\>エクスプ ローラー](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="beaaf-108">セキュリティでエクスプ ローラーを使用する&amp;コンプライアンス センターでは、**脅威の管理**に移動\>**エクスプ ローラー**です。</span><span class="sxs-lookup"><span data-stu-id="beaaf-108">To use Explorer, in the Security &amp; Compliance Center, go to **Threat management** \> **Explorer**.</span></span>
      
## <a name="explorer-overview"></a><span data-ttu-id="beaaf-109">エクスプ ローラーの概要</span><span class="sxs-lookup"><span data-stu-id="beaaf-109">Explorer overview</span></span>

<span data-ttu-id="beaaf-p102">エクスプ ローラーでは、組織に電子メールでマルウェアを疑いがあると、Office 365 内のファイルだけでなく他のセキュリティ上の脅威やリスクについての情報が表示されます。最初にエクスプ ローラーを開くと、既定のビューは、過去 7 日間のウイルスからのマルウェアの検出を示します。エクスプ ローラーもセキュリティ保護機能[安全リンク](atp-safe-links.md)[安全な添付ファイル](atp-safe-attachments.md)など、Office 365 でと、過去 30 日間のデータを表示するのには変更することができます。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p102">Explorer displays information about suspected malware in email and files in Office 365, as well as other security threats and risks to your organization. When you first open Explorer, the default view shows malware detections from antivirus for the past 7 days. Explorer can also show security protection features in Office 365, including [Safe Links](atp-safe-links.md) and [Safe Attachments](atp-safe-attachments.md) and can be modified to show data for the past 30 days.</span></span>
  
![エクスプ ローラーは、上のマルウェアおよび対象となるユーザーに関する情報を示しています。](media/8e8c1582-d6f4-4521-8591-686a1cb01f7e.png)
  
<span data-ttu-id="beaaf-114">表示する情報を変更するのには、[表示] メニューを使用します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-114">Use the View menu to change what information is displayed.</span></span>
  
![エクスプ ローラーの [表示] メニュー](media/2bb34f58-555f-4967-ba55-740334ef1f8e.png)
  
<span data-ttu-id="beaaf-p103">エクスプ ローラーには、いくつかのフィルター処理とクエリ上は、ユーザー、一番上のマルウェア ファミリでは、対象となるなどの詳細にドリル ダウンすることを可能にする機能があります。レポートの各種類には、さまざまな表示およびデータを表示する方法が用意されています。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p103">Explorer has several filtering and querying capabilities that enable you to drill into details, such as top targeted users, top malware families, and more. Each kind of report offers a variety of ways to view and explore data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="beaaf-p104">ワイルドカード文字、アスタリスク (\*) または疑問符 (?)、エクスプ ローラーでは使えません。電子メール メッセージの [件名] フィールドで検索すると、エクスプ ローラーは部分に一致し、徐行を表すような結果ワイルドカード検索を実行します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p104">Do not use wildcard characters, such as an asterisk (\*) or a question mark (?), with Explorer. When you search on the Subject field for email messages, Explorer will perform partial matching and yield results similar to a wildcard search.</span></span>

## <a name="email--malware"></a><span data-ttu-id="beaaf-120">電子メール\>マルウェア</span><span class="sxs-lookup"><span data-stu-id="beaaf-120">Email \> Malware</span></span>

<span data-ttu-id="beaaf-121">このビューには、マルウェアが含まれていると識別された電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="beaaf-121">This view shows email messages identified as containing malware.</span></span>  

<span data-ttu-id="beaaf-122">マルウェア ファミリ、送信者のドメイン、送信元 IP、保護の状態 (アクション、脅威の保護機能と Office 365 のポリシーによって)、および検出技術が (どのようにマルウェアが検出されました)、グラフ内の情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-122">View information in the chart by malware family, sender domain, sender IP, protection status (actions taken by your threat protection features and policies in Office 365), and detection technology (how the malware was detected).</span></span>  

![検出されたマルウェアに関するデータを表示します。](media/d11dc568-b091-4159-b261-df13d76b520b.png)         

<span data-ttu-id="beaaf-124">上のマルウェアのファミリの詳細を表示、グラフの下上部には、ユーザー、および特定のメッセージに関する詳細が対象となります。</span><span class="sxs-lookup"><span data-stu-id="beaaf-124">Below the chart, view details about top malware families, top targeted users, and more details about specific messages.</span></span> 

## <a name="email--phish"></a><span data-ttu-id="beaaf-125">電子メール\>フィッシング詐欺</span><span class="sxs-lookup"><span data-stu-id="beaaf-125">Email \> Phish</span></span>

<span data-ttu-id="beaaf-126">このビューには、フィッシング攻撃として識別された電子メール メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="beaaf-126">This view shows email messages identified as phishing attempts.</span></span>  

<span data-ttu-id="beaaf-127">送信者ドメイン、送信元 IP、および保護の状態 (、脅威の保護機能と Office 365 のポリシーが実行するアクション) での情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-127">View information by sender domain, sender IP, and protection status (actions taken by your threat protection features and policies in Office 365).</span></span> 

![フィッシング詐欺として識別される電子メールのデータを表示します。](media/2e3f97fa-2b99-47f9-afd6-216d10633c50.png) 

<span data-ttu-id="beaaf-129">、グラフの下には、特定のメッセージに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-129">Below the chart, view more details about specific messages.</span></span> 

## <a name="email--user-reported"></a><span data-ttu-id="beaaf-130">電子メール\>ユーザーから報告されました。</span><span class="sxs-lookup"><span data-stu-id="beaaf-130">Email \> User-reported</span></span>

<span data-ttu-id="beaaf-131">このビューには、ユーザーが迷惑メール、迷惑メールまたはフィッシング詐欺メールとして報告された電子メールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="beaaf-131">This view shows email that users have reported as junk, not junk, or phishing email.</span></span>  

<span data-ttu-id="beaaf-132">レポートの種類 (ユーザーの確認メールが迷惑メール、迷惑メールまたはフィッシングのこと)、および配送の理由 (理由が電子メールを迷惑メール フィルターのポリシー、メール フロー ルール、受信拒否リスト、差出人セーフ リストなどの特定の場所になった理由は、情報を表示します。など)。</span><span class="sxs-lookup"><span data-stu-id="beaaf-132">View information by report type (the user's determination that the email was junk, not junk, or phish), and by delivery reason (reasons why email went to a specific location, such as a spam filter policy, a mail flow rule, a blocked-senders list, a safe-senders list, etc.).</span></span>  

![迷惑メール、迷惑メールまたはフィッシング詐欺として報告された電子メールのユーザーに関するデータを表示します。](media/255acd04-0d07-4b29-82af-5060a60c20ab.png)  

<span data-ttu-id="beaaf-134">、グラフの下部に、件名、送信者の IP アドレスとして、迷惑メール、しない、迷惑メールまたはフィッシング、などのメッセージを報告したユーザーなど、特定の電子メール メッセージに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-134">Below the chart, view more details about specific email messages, such as subject line, the sender's IP address, the user that reported the message as junk, not junk, or phish, and more.</span></span> 

## <a name="email--all-mail"></a><span data-ttu-id="beaaf-135">電子メール\>すべてのメール</span><span class="sxs-lookup"><span data-stu-id="beaaf-135">Email \> All mail</span></span>

<span data-ttu-id="beaaf-136">このビューは、悪意あるコードとして期日にフィッシング詐欺やマルウェア、悪意のないすべてのメールを (通常の電子メール、スパム、およびメールを一括) と同じよう特定電子メールを含む電子メール活動のすべての表示を示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-136">This views shows an all-up view of email activity, including email identified as malicious due to phishing or malware, as well all non-malicious mail (normal email, spam, and bulk mail).</span></span> 

> [!NOTE]
> <span data-ttu-id="beaaf-137">というエラーが発生する場合**が多くのデータを表示するのには**フィルターを追加し、必要に応じて、表示されている日付の範囲を絞り込む、です。</span><span class="sxs-lookup"><span data-stu-id="beaaf-137">If you get an error that reads **Too much data to display**, add a filter and, if necessary, narrow the date range you're viewing.</span></span> 

<span data-ttu-id="beaaf-p105">フィルターを適用するには、**送信者**を選択します] ボックスの一覧で項目を選択、[更新] ボタンをクリックし。この例では、フィルター (はいくつかオプションを使用) として**検出技術**を使用しました。送信者、送信者のドメイン、受信者、件名、添付ファイルの名前、マルウェア ファミリ、保護の状態 (アクション、脅威の保護機能と Office 365 のポリシーによって)、(どのようにマルウェアが検出されました)、検出技術によって情報を表示し、もっとその。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p105">To apply a filter, choose **Sender**, select an item in the list, and then click the Refresh button. In our example, we used **Detection technology** as a filter (there are several options available). View information by sender, sender's domain, recipients, subject, attachment filename, malware family, protection status (actions taken by your threat protection features and policies in Office 365), detection technology (how the malware was detected), and more.</span></span> 

![検出技術によって検出された電子メールのデータを表示します。](media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png) 

<span data-ttu-id="beaaf-142">、グラフの下には、件名、受信者、送信者、状態、などの特定の電子メール メッセージに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-142">Below the chart, view more details about specific email messages, such as subject line, recipient, sender, status, and so on.</span></span> 

## <a name="content--malware"></a><span data-ttu-id="beaaf-143">コンテンツ\>マルウェア</span><span class="sxs-lookup"><span data-stu-id="beaaf-143">Content \> Malware</span></span>

<span data-ttu-id="beaaf-144">このビューには、ビジネス、およびマイクロソフトのチームの SharePoint のオンライン、OneDrive で悪意のあるものとして識別されたファイルが表示されます。</span><span class="sxs-lookup"><span data-stu-id="beaaf-144">This view shows files that were identified as malicious in SharePoint Online, OneDrive for Business, and Microsoft Teams.</span></span>

<span data-ttu-id="beaaf-145">(どのようにマルウェアが検出されました)、マルウェア ファミリ、検出テクノロジーを使用して情報を表示し (OneDrive、SharePoint、またはチーム) の作業負荷。</span><span class="sxs-lookup"><span data-stu-id="beaaf-145">View information by malware family, detection technology (how the malware was detected), and workload (OneDrive, SharePoint, or Teams).</span></span> 

![検出されたマルウェアに関するデータを表示します。](media/d11dc568-b091-4159-b261-df13d76b520b.png)  

<span data-ttu-id="beaaf-147">、グラフの下には、添付ファイルのファイル名、作業負荷、ファイル、および詳細を最後に変更したファイルのサイズなどの特定のファイルに関する詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-147">Below the chart, view more details about specific files, such as attachment filename, workload, file size, who last modified the file, and more.</span></span> 
  
## <a name="new-click-to-filter-capabilities"></a><span data-ttu-id="beaaf-148">(New!)をクリックします-へのフィルターの機能</span><span class="sxs-lookup"><span data-stu-id="beaaf-148">(New!) Click-to-filter capabilities</span></span>

<span data-ttu-id="beaaf-p106">エクスプ ローラーにはフィルターを適用する] をクリックする機能です。凡例内の項目をクリックすると、遅延の月 2018 年そのアイテムは、レポートのフィルターになります。たとえば、エクスプ ローラーの [マルウェア] ビューを表示するいるとします。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p106">New to Explorer is the ability to click to filter. Beginning in late May 2018, when you click an item in the legend, that item becomes a filter for the report. For example, suppose we are looking at the Malware view in Explorer:</span></span>
  
![脅威の管理に移動\>エクスプ ローラー](media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)
  
<span data-ttu-id="beaaf-153">このグラフの結果で次のようなビューでは、 **ATP (デトネーション)** をクリックすると。</span><span class="sxs-lookup"><span data-stu-id="beaaf-153">Clicking **ATP Detonation** in this chart results in a view like this:</span></span> 
  
![ATO の爆発の結果のみを表示するフィルター処理されたエクスプ ローラー](media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)
  
<span data-ttu-id="beaaf-p107">このビューでは、ここで見て[Office 365 ATP の安全な添付ファイル](atp-safe-attachments.md)で detonated されたファイルのデータです。、グラフの下部に安全な添付ファイルの分析ツールによって検出された添付ファイルを含む特定の電子メール メッセージに関する詳細情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p107">In this view, we are now looking at data for files that were detonated by [Office 365 ATP Safe Attachments](atp-safe-attachments.md). Below the chart, we can see details about specific email messages that had attachments that were detected by ATP Safe Attachments.</span></span>
  
![検出された添付ファイル付き電子メール メッセージに関する特定の詳細](media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)
  
<span data-ttu-id="beaaf-158">1 つまたは複数の項目を選択するには、選択した項目を選択するいくつかの選択肢を提供する [**アクション**] メニューがアクティブにします。</span><span class="sxs-lookup"><span data-stu-id="beaaf-158">Selecting one or more items activates the **Actions** menu, which offers several choices from which to choose for the selected item(s).</span></span> 
  
![[操作] メニューをアクティブにアイテムを選択します。](media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)
  
<span data-ttu-id="beaaf-160">クリックでフィルター処理し、特定の詳細に移動することで保存でく多くの時間の脅威を調査します。</span><span class="sxs-lookup"><span data-stu-id="beaaf-160">The ability to filter in a click and navigate to specific details can save you a lot of time in investigating threats.</span></span>
  
## <a name="how-do-i-get-explorer"></a><span data-ttu-id="beaaf-161">エクスプ ローラーを取得する方法は?</span><span class="sxs-lookup"><span data-stu-id="beaaf-161">How do I get Explorer?</span></span>

<span data-ttu-id="beaaf-162">エクスプ ローラーは、 [Office 365 の脅威インテリジェンス](office-365-ti.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="beaaf-162">Explorer is included in [Office 365 Threat Intelligence](office-365-ti.md).</span></span> 

<span data-ttu-id="beaaf-p108">表示してエクスプ ローラーを使用するためには、セキュリティ管理者やセキュリティのリーダーに与えられているなど、適切なアクセス許可が必要です。詳細についてを参照してください[では、Office 365 のセキュリティ アクセス許可&amp;コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)です。</span><span class="sxs-lookup"><span data-stu-id="beaaf-p108">You must have appropriate permissions, such as those granted to a security administrator or security reader, in order to view and use Explorer. To learn more, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="beaaf-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="beaaf-165">Related topics</span></span>

[<span data-ttu-id="beaaf-166">レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="beaaf-166">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="beaaf-167">検索し、(Office 365 の脅威インテリジェンス) に配信された悪意のある電子メールを調査</span><span class="sxs-lookup"><span data-stu-id="beaaf-167">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>](investigate-malicious-email-that-was-delivered.md)
  
[<span data-ttu-id="beaaf-168">Office 365 のスパム対策とマルウェア対策の保護</span><span class="sxs-lookup"><span data-stu-id="beaaf-168">Anti-spam and anti-malware protection in Office 365</span></span>](anti-spam-and-anti-malware-protection.md)
  

