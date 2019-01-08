---
title: セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
description: 検索し、Office 365 の企業で、組織の電子メール セキュリティのレポートを使用する方法について説明します。電子メール セキュリティのレポートは、セキュリティで利用可能な&amp;コンプライアンス センターです。
ms.openlocfilehash: 670317707c5695161f23615fb87fe93258e8d95b
ms.sourcegitcommit: 30faa3ba91cab4c36e3d8d8ed5858d5269ea8a56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/08/2019
ms.locfileid: "27749331"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="640ab-104">セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="640ab-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="640ab-p102">さまざまな電子メール セキュリティのレポートでは使用、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com) Office 365 のスパム対策およびマルウェア対策の機能が、組織を保護する方法を見るのに役立ちます。セキュリティのこれらのレポートを表示するには[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、 &amp; **のレポート**に移動してコンプライアンス センター \> **ダッシュ ボード**。</span><span class="sxs-lookup"><span data-stu-id="640ab-p102">A variety of email security reports are available in the [Security &amp; Compliance Center](https://security.microsoft.com) to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="640ab-108">電子メール セキュリティ レポートを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="640ab-108">Your email security reports include the following:</span></span>
  
- [<span data-ttu-id="640ab-109">脅威保護の状態のレポート</span><span class="sxs-lookup"><span data-stu-id="640ab-109">Threat Protection Status report</span></span>](view-email-security-reports.md#tps) 
    
- [<span data-ttu-id="640ab-110">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="640ab-111">上のマルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-111">Top Malware report</span></span>](#top-malware-report)
    
- [<span data-ttu-id="640ab-112">最上位の送信者と受信者のレポート</span><span class="sxs-lookup"><span data-stu-id="640ab-112">Top Senders and Recipients report</span></span>](view-email-security-reports.md#topsenders)
    
- [<span data-ttu-id="640ab-113">なりすましメール レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="640ab-114">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="640ab-115">レポートの送信および受信したメール</span><span class="sxs-lookup"><span data-stu-id="640ab-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="640ab-116">[メッセージのユーザーから報告されたレポート](view-email-security-reports.md#userreported)(new!)</span><span class="sxs-lookup"><span data-stu-id="640ab-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report"></a><span data-ttu-id="640ab-117">脅威保護の状態のレポート</span><span class="sxs-lookup"><span data-stu-id="640ab-117">Threat Protection Status report</span></span>

<span data-ttu-id="640ab-p103">新しい**脅威保護の状態**レポートは、悪意のある電子メールが検出され、Exchange のオンライン保護によってブロックされていることを示すスマート レポートです。このレポートには、マルウェアやフィッシング詐欺として識別された電子メールに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="640ab-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="640ab-p104">脅威保護の状態レポートは、 [Office 365 の ATP](office-365-atp.md)または[Exchange のオンライン保護](eop/exchange-online-protection-eop.md)(EOP) は使用しているお客様に利用可能ですただし、ATP のお客様の脅威保護の状態レポートに表示される情報 EOP の顧客が表示とは異なるデータが含まれる予定です。たとえば、EOP の顧客はで電子メールがない[悪意のあるファイルは、SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで検出](atp-for-spo-odb-and-teams.md)に関する情報、分析ツールに固有の機能で検出されたマルウェアに関する情報を表示できます。([ATP のレポートについての詳細](view-reports-for-atp.md))</span><span class="sxs-lookup"><span data-stu-id="640ab-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="640ab-123">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **脅威保護の状態**です。</span><span class="sxs-lookup"><span data-stu-id="640ab-123">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![脅威保護の状態のレポート](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="640ab-p105">最初に脅威保護の状態レポートを開くと、レポート データが表示過去 7 日間の既定ではただし、[**フィルター** ] をクリックし、詳細の最大 90 日間の日付の範囲を変更できます。このレポートは、有効性と、組織の Exchange のオンライン保護機能の影響を表示し、長期的な傾向を見るために便利です。</span><span class="sxs-lookup"><span data-stu-id="640ab-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![脅威保護の状態レポートのフィルター](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="640ab-128">かどうか悪意のあるものとして識別される電子メールのデータを表示するように、フィッシング詐欺を試みると、識別された電子メールまたは電子メールとして識別されるマルウェアを含むこともできます。</span><span class="sxs-lookup"><span data-stu-id="640ab-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![脅威保護のステータス レポートの表示オプション](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="640ab-130">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-130">Malware Detections report</span></span>

<span data-ttu-id="640ab-131">受信および送信メッセージの数が組織のマルウェアが含まれていると検出された**マルウェア検出**レポートを示しています。</span><span class="sxs-lookup"><span data-stu-id="640ab-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="640ab-132">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **のマルウェア検出**します。</span><span class="sxs-lookup"><span data-stu-id="640ab-132">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![マルウェア検出レポートの例](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="640ab-p106">脅威保護のステータス レポートと同様に、他のレポートのようなレポート データを表示過去 7 日間の既定では。ただし、日付の範囲を変更するのには**フィルター**を選択できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="640ab-136">上のマルウェア レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-136">Top Malware report</span></span>

<span data-ttu-id="640ab-137">**上のマルウェア**レポートは、Exchange Online によって検出されたマルウェアのさまざまな種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="640ab-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="640ab-138">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **上のマルウェア**です。</span><span class="sxs-lookup"><span data-stu-id="640ab-138">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC の EOP の一番上のマルウェア](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="640ab-140">ウェッジ、円グラフの上に置くと、メッセージの数は、そのマルウェアを持つものとして検出されたマルウェアの種類の名前を表示できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="640ab-141">レポートをレポートの詳細なビューを入手するため、新しいブラウザー ウィンドウで開くことを] をクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="640ab-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![このレポートは、組織で検出された上位のマルウェアを示しています](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="640ab-143">、グラフの下部には、検出されたマルウェアとメッセージの数は、そのマルウェアを持つものとして検出された一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="640ab-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="640ab-144">最上位の送信者と受信者のレポート</span><span class="sxs-lookup"><span data-stu-id="640ab-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="640ab-145">**上位送信者と受信者**のレポートでは、一番上の電子メールの送信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="640ab-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="640ab-146">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **上の送信者および受信者**です。</span><span class="sxs-lookup"><span data-stu-id="640ab-146">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、レポートに移動\>ダッシュ ボード\>上の送信者と受信者](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="640ab-148">ウェッジ、円グラフの上に置くと、送信または受信されたメッセージの数を表示できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="640ab-149">レポートをレポートの詳細なビューを入手するため、新しいブラウザー ウィンドウで開くことを] をクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="640ab-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="640ab-p107">**データを表示する**] ボックスの一覧を使用すると、最上位の送信者、受信機、迷惑メールの受信者、およびマルウェアの受信者のデータを表示するのにかどうかを選択できます。脅威の高度な保護によって検出されたマルウェアを受信したユーザーも確認できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![名前を付けてデータを表示する] ボックスの一覧を使用して、特定の情報を表示するのには](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="640ab-153">、グラフの下部に表示した上の電子メールの送信者または受信者が、指定された時間内に送受信されたメッセージの数とします。</span><span class="sxs-lookup"><span data-stu-id="640ab-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="640ab-154">なりすましメール レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-154">Spoof Mail report</span></span>

<span data-ttu-id="640ab-155">なりすましメール メッセージの数が検出されると、**なりすましメール**レポートに表示し、それらのどれが「な」(なりすましメールが正当なビジネス上の理由から行われます) を検討しました。</span><span class="sxs-lookup"><span data-stu-id="640ab-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="640ab-156">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **なりすましメール**です。</span><span class="sxs-lookup"><span data-stu-id="640ab-156">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、レポートに移動\>ダッシュ ボード\>なりすましメール](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="640ab-158">上に置くと 1 日のグラフで、なりすましメール メッセージの数がによって生成されたものを確認できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="640ab-159">レポートをレポートの詳細なビューを入手するため、新しいブラウザー ウィンドウで開くことを] をクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="640ab-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="640ab-160">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-160">Spam Detections report</span></span>

<span data-ttu-id="640ab-161">**スパム検出**レポートは、Exchange Online によってブロックされているすべての迷惑メールの内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="640ab-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="640ab-162">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **スパム検出**します。</span><span class="sxs-lookup"><span data-stu-id="640ab-162">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、レポートに移動\>ダッシュ ボード\>EOP スパム検出](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="640ab-p108">上に置くと 1 日のグラフで、項目の数がその日がブロックされたは、それらのアイテムを分類する方法を確認できます。たとえば、スパム メッセージの数がフィルター処理され、ブロックされているインターネット プロトコル (IP) アドレスからアイテムの数が付属して表示できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="640ab-166">レポートをレポートの詳細なビューを入手するため、新しいブラウザー ウィンドウで開くことを] をクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="640ab-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![スパム検出レポートが表示されたスパム メッセージの数のブロックまたはフィルターで除外](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="640ab-p109">、グラフの下部には、検出されたスパムの項目の一覧が表示されます。迷惑メール アイテムが受信または送信したかどうか、メッセージ ID、受信者のなどの追加情報を表示する項目を選択します。</span><span class="sxs-lookup"><span data-stu-id="640ab-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="640ab-170">レポートの送信および受信したメール</span><span class="sxs-lookup"><span data-stu-id="640ab-170">Sent and received email report</span></span>

<span data-ttu-id="640ab-171">**送信および受信した電子メール**のレポートは、着信および発信メール、迷惑メールの検出、マルウェアでは、「正常」と識別された電子メールなどに関する情報を表示するスマート レポート</span><span class="sxs-lookup"><span data-stu-id="640ab-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="640ab-172">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)**のレポート**には、 \> **ダッシュ ボード** \> **送信および受信した電子メール**です。</span><span class="sxs-lookup"><span data-stu-id="640ab-172">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、レポートに移動\>ダッシュ ボード\>送信および受信したメール](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="640ab-p110">上に置くと 1 日のグラフで、メッセージの数が入って来るし、それらのメッセージを分類する方法を確認できます。たとえば、メッセージの数は、マルウェアが含まれていると検出され、何スパムとして識別されたを表示できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="640ab-176">レポートをレポートの詳細なビューを入手するため、新しいブラウザー ウィンドウで開くことを] をクリックして (またはタップ) します。</span><span class="sxs-lookup"><span data-stu-id="640ab-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="640ab-177">種類または方向 (受信および送信) の情報を表示するのに**ごとに分割**] ボックスの一覧を使用できます。</span><span class="sxs-lookup"><span data-stu-id="640ab-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![ブレーク ダウンでリストを使用して、種類または方向で情報を表示するのには](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="640ab-p111">、グラフの下部には、 **GoodMail**、 **SpamContentFiltered**、など、電子メールのカテゴリの一覧が表示されます。選択、カテゴリ、マルウェアの実行されたアクションなどの追加情報を表示し、電子メールで送信するかどうかは、着信または発信しました。</span><span class="sxs-lookup"><span data-stu-id="640ab-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![このレポートについては、マルウェア対策、スパム対策、およびその他のメッセージの検出を通知します。](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="640ab-182">ユーザーから報告されたメッセージのレポート (new!)</span><span class="sxs-lookup"><span data-stu-id="640ab-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="640ab-183">**メッセージのユーザーから報告された**レポートでは、ユーザー[レポート メッセージのアドインを](enable-the-report-message-add-in.md)使用して、迷惑メール、フィッシング詐欺、または正常なメールとして報告している電子メール メッセージに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="640ab-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="640ab-p112">配送理由、このような迷惑メール ポリシーの例外または組織用に構成されたメール フローの規則を含む、各メッセージの詳細情報があります。詳細を表示するには、ユーザー レポートの一覧で項目を選択し、**概要**と**詳細**のタブに情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="640ab-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![User-Reported メッセージ レポートでは、試行として、迷惑メール、迷惑メールまたはフィッシングというラベルの付いたメッセージのユーザーを示します。](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="640ab-187">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://security.microsoft.com)、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="640ab-187">To view this report, in the [Security &amp; Compliance Center](https://security.microsoft.com), do one of the following:</span></span>
  
- <span data-ttu-id="640ab-188">**脅威の管理**に移動\>**ダッシュ ボード** \> **メッセージのユーザーから報告されました**。</span><span class="sxs-lookup"><span data-stu-id="640ab-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="640ab-189">**脅威の管理**に移動\>**レビュー** \> **メッセージのユーザーから報告されました**。</span><span class="sxs-lookup"><span data-stu-id="640ab-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![セキュリティ&amp;コンプライアンス センターでは、脅威の管理を選択して\>レビュー\>ユーザーにメッセージが報告されます。](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="640ab-p113">**監査ログを有効にする必要があります**が、Office 365 環境に正常に動作するメッセージをユーザーから報告されたレポートの順序します。これは通常、Exchange のオンラインを割り当てられている監査ログのロールを持つユーザーによって行います。詳細については、[オンまたはオフ、Office 365 を有効にする監査ログの検索](turn-audit-log-search-on-or-off.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="640ab-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="640ab-194">これらのレポートを表示するのにはどのようなアクセス許可が必要か。</span><span class="sxs-lookup"><span data-stu-id="640ab-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="640ab-195">表示し、この資料に記載されているレポートを使用するために**セキュリティの両方に割り当てられている適切なロールを持つ必要があります&amp;コンプライアンス センターと、Exchange 管理センター**です。</span><span class="sxs-lookup"><span data-stu-id="640ab-195">In order to view and use the reports described in this article, **you must have an appropriate role assigned in both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="640ab-196">セキュリティの&amp;コンプライアンス センターでは、する必要があります次に割り当てられている役割の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="640ab-196">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="640ab-197">組織の管理</span><span class="sxs-lookup"><span data-stu-id="640ab-197">Organization Management</span></span>
    - <span data-ttu-id="640ab-198">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="640ab-198">Security Administrator</span></span>
    - <span data-ttu-id="640ab-199">セキュリティ リーダー</span><span class="sxs-lookup"><span data-stu-id="640ab-199">Security Reader</span></span>

- <span data-ttu-id="640ab-200">Exchange Online では、する必要があります次に割り当てられている役割の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="640ab-200">For Exchange Online, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="640ab-201">組織の管理</span><span class="sxs-lookup"><span data-stu-id="640ab-201">Organization Management</span></span>
    - <span data-ttu-id="640ab-202">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="640ab-202">View-only Organization Management</span></span>
    - <span data-ttu-id="640ab-203">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="640ab-203">View-Only Recipients role</span></span>
    - <span data-ttu-id="640ab-204">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="640ab-204">Compliance Management</span></span>

<span data-ttu-id="640ab-205">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="640ab-205">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="640ab-206">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="640ab-206">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="640ab-207">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="640ab-207">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="640ab-208">場合、レポート データが表示されていないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="640ab-208">What if the reports aren't showing data?</span></span>

<span data-ttu-id="640ab-p114">レポートにデータを表示されない場合、ポリシーが正しく設定されているを再確認してください。詳細については、 [Office 365 でのスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="640ab-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="640ab-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="640ab-211">Related topics</span></span>

[<span data-ttu-id="640ab-212">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="640ab-212">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="640ab-213">レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="640ab-213">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="640ab-214">セキュリティ レポートのスケジュールを作成する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="640ab-214">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="640ab-215">設定し、セキュリティでのカスタム レポートをダウンロード&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="640ab-215">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

