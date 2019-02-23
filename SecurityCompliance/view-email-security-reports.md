---
title: セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/07/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection: M365-security-compliance
description: Office 365 Enterprise を使用して組織の電子メールセキュリティレポートを検索して使用する方法について説明します。電子メールセキュリティレポートは、セキュリティ&amp;コンプライアンスセンターで利用できます。
ms.openlocfilehash: 809bfbdfdda8bd1ed9b88c9bca7e9ce14d774868
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216417"
---
# <a name="view-email-security-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="614a5-104">セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="614a5-104">View email security reports in the Security &amp; Compliance Center</span></span>

<span data-ttu-id="614a5-p102">[ &amp;セキュリティコンプライアンスセンター](https://security.microsoft.com)では、さまざまな電子メールセキュリティレポートを使用して、Office 365 のスパム対策とマルウェア対策機能が組織を保護する方法を確認するのに役立てることができます。[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、**レポート** \> **ダッシュボード**にアクセスすること&amp;によって、セキュリティコンプライアンスセンターでこれらのレポートを表示できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p102">A variety of email security reports are available in the [Security &amp; Compliance Center](https://security.microsoft.com) to help you see how anti-spam and anti-malware features in Office 365 are protecting your organization. If you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can view these reports in the Security &amp; Compliance Center by going to **Reports** \> **Dashboard**.</span></span>
  
![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="614a5-108">電子メールのセキュリティレポートには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="614a5-108">Your email security reports include the following:</span></span>
  
- [<span data-ttu-id="614a5-109">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-109">Threat Protection Status report</span></span>](view-email-security-reports.md#tps) 
    
- [<span data-ttu-id="614a5-110">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-110">Malware Detections report</span></span>](view-email-security-reports.md#maldet)
    
- [<span data-ttu-id="614a5-111">上位マルウェアレポート</span><span class="sxs-lookup"><span data-stu-id="614a5-111">Top Malware report</span></span>](#top-malware-report)
    
- <span data-ttu-id="614a5-112">[[上位送信者および受信者] レポート](view-email-security-reports.md#topsenders)</span><span class="sxs-lookup"><span data-stu-id="614a5-112">[Top Senders and Recipients report](view-email-security-reports.md#topsenders)</span></span>
    
- [<span data-ttu-id="614a5-113">スプーフィングメールレポート</span><span class="sxs-lookup"><span data-stu-id="614a5-113">Spoof Mail report</span></span>](#spoof-mail-report)
    
- [<span data-ttu-id="614a5-114">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-114">Spam Detections report</span></span>](#spam-detections-report)
    
- [<span data-ttu-id="614a5-115">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="614a5-115">Sent and received email report</span></span>](view-email-security-reports.md#sentreceivedemail)
    
- <span data-ttu-id="614a5-116">[ユーザーによって報告](view-email-security-reports.md#userreported)されたメッセージレポート(新)</span><span class="sxs-lookup"><span data-stu-id="614a5-116">[User-reported messages report](view-email-security-reports.md#userreported) (new!)</span></span> 
    
## <a name="threat-protection-status-report"></a><span data-ttu-id="614a5-117">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-117">Threat Protection Status report</span></span>

<span data-ttu-id="614a5-p103">新しい**脅威保護状態**レポートは、Exchange Online Protection によって検出およびブロックされた悪意のある電子メールを示すスマートレポートです。このレポートには、マルウェアまたはフィッシングの試行として識別された電子メールに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p103">The new **Threat Protection Status** report is a smart report that shows malicious email that was detected and blocked by Exchange Online Protection. This report shows information about email identified as malware or a phishing attempt.</span></span> 

> [!NOTE]
> <span data-ttu-id="614a5-p104">脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。たとえば、EOP のお客様は、電子メールで検出されたマルウェアに関する情報を表示できますが、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報は、ATP 固有の機能です。([ATP レポートの詳細について](view-reports-for-atp.md)は、を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="614a5-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, EOP customers can view information about malware detected in email, but not information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md), an ATP-specific capability. ([Learn more about ATP reports](view-reports-for-atp.md).)</span></span>
  
<span data-ttu-id="614a5-123">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **脅威保護の状態**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-123">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![脅威保護の状態レポート](media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)
  
<span data-ttu-id="614a5-p105">脅威保護の状態レポートを初めて開いたとき、既定では過去7日間のデータがレポートに表示されます。ただし、[**フィルター** ] をクリックして、最大90日間の日付範囲を変更することができます。このレポートは、組織の Exchange Online Protection 機能の有効性と影響、および長期的な傾向を確認するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p105">When you first open the Threat Protection Status report, the report shows data for the past seven days by default; however, you can click **Filters** and change the date range for up to 90 days of detail. This report is useful for viewing the effectiveness and impact of your organization's Exchange Online Protection features, and for longer-term trending.</span></span> 
  
![脅威保護の状態レポートのフィルター](media/ab6b6b8d-e97a-4c3a-8fb1-c4940dcb7a07.png)
  
<span data-ttu-id="614a5-128">悪意があると識別された電子メール、フィッシングとして識別された電子メール、マルウェアを含んでいると識別された電子メールのデータを表示するかどうかを選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="614a5-128">You can also choose whether to view data for email identified as malicious, email identified as a phishing attempts, or email identified as containing malware.</span></span>
  
![脅威保護の状態レポートの表示オプション](media/d429ecd7-cb7a-4c99-8d27-79a2832cf467.png)
  
## <a name="malware-detections-report"></a><span data-ttu-id="614a5-130">マルウェア検出レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-130">Malware Detections report</span></span>

<span data-ttu-id="614a5-131">**マルウェア検出**レポートは、組織のマルウェアが含まれているとして検出された受信メッセージと送信メッセージの数を示します。</span><span class="sxs-lookup"><span data-stu-id="614a5-131">The **Malware Detections** report shows how many incoming and outgoing messages were detected as containing malware for your organization.</span></span> 
  
<span data-ttu-id="614a5-132">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **マルウェア検出**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Malware Detections**.</span></span>
  
![マルウェア検出レポートの例](media/a1ba61a3-565a-46d6-b0d5-6a6cff6b31d7.png)
  
<span data-ttu-id="614a5-p106">脅威保護の状態レポートなどの他のレポートと同様に、レポートには既定で過去7日間のデータが表示されます。ただし、[**フィルター** ] を選択して、日付の範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p106">Similar to other reports, like the Threat Protection Status report, the report displays data for the past seven days by default. However, you can choose **Filters** to change the date range.</span></span> 
  
## <a name="top-malware-report"></a><span data-ttu-id="614a5-136">上位マルウェアレポート</span><span class="sxs-lookup"><span data-stu-id="614a5-136">Top Malware report</span></span>

<span data-ttu-id="614a5-137">**上位マルウェア**レポートには、Exchange Online によって検出されたさまざまな種類のマルウェアが表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-137">The **Top Malware** report shows the various kinds of malware that was detected by Exchange Online.</span></span> 
  
<span data-ttu-id="614a5-138">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[ **Reports** \> **Dashboard** \> **Top マルウェア**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-138">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Malware**.</span></span>
  
![SCC-EOP Top マルウェア](media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)
  
<span data-ttu-id="614a5-140">円グラフのくさび形の上にポインターを移動すると、マルウェアの種類の名前と、マルウェアを持っていることが検出されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-140">When you hover over a wedge in the pie chart, you can see the name of a kind of malware and how many messages were detected as having that malware.</span></span>
  
<span data-ttu-id="614a5-141">レポートをクリック (またはタップ) して、新しいブラウザーウィンドウでレポートを開きます。これにより、レポートの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-141">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![このレポートには、組織で検出された上位のマルウェアが表示されます。](media/3fded224-fb31-4713-86f2-8afce5ce2991.png)
  
<span data-ttu-id="614a5-143">グラフの下に、検出されたマルウェアの一覧と、マルウェアを持っていることが検出されたメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-143">Below the chart, you'll see a list of detected malware and how many messages were detected as having that malware.</span></span>
  
## <a name="top-senders-and-recipients-report"></a><span data-ttu-id="614a5-144">[上位送信者および受信者] レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-144">Top Senders and Recipients report</span></span>

<span data-ttu-id="614a5-145">[**上位の送信者と受信者**] レポートは、上位の電子メール送信者を示す円グラフです。</span><span class="sxs-lookup"><span data-stu-id="614a5-145">The **Top Senders and Recipients** report is a pie chart showing your top email senders.</span></span> 
  
<span data-ttu-id="614a5-146">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**上位送信者および受信者**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-146">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Top Senders and Recipients**.</span></span>
  
![このレポートを表示するには、 &amp;セキュリティ/コンプライアンスセンターで、 \> [ \>レポートダッシュボードのトップ送信者と受信者] に移動します。](media/b5506b5c-2420-4a5a-9ea3-d654294ac838.png)
  
<span data-ttu-id="614a5-148">円グラフのくさび形の上にポインターを移動すると、送信または受信したメッセージの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-148">When you hover over a wedge in the pie chart, you can see a count of messages sent or received.</span></span>
  
<span data-ttu-id="614a5-149">レポートをクリック (またはタップ) して、新しいブラウザーウィンドウでレポートを開きます。これにより、レポートの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-149">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="614a5-p107">[**データの表示**] リストを使用して、上位の送信者、受信者、スパム受信者、およびマルウェア受信者のデータを表示するかどうかを選択します。Advanced Threat Protection によって検出されたマルウェアの受信者を確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p107">Use the **Show data for** list to choose whether to view data for top senders, receivers, spam recipients, and malware recipients. You can also see who received malware that was detected by Advanced Threat Protection.</span></span> 
  
![特定の情報を表示するには、[データの表示] リストを使用します。](media/bd91449f-7d42-4749-8666-7b44044049b8.png)
  
<span data-ttu-id="614a5-153">グラフの下に、上位の電子メール送信者または受信者の数と、指定された期間に送受信されたメッセージ数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-153">Below the chart, you'll see who the top email senders or recipients were, along with a count of messages sent or received for the given time period.</span></span>
  
## <a name="spoof-mail-report"></a><span data-ttu-id="614a5-154">スプーフィングメールレポート</span><span class="sxs-lookup"><span data-stu-id="614a5-154">Spoof Mail report</span></span>

<span data-ttu-id="614a5-155">[**スプーフィングメール**] レポートには、検出されたスプーフィングメールメッセージの数と、それらのメッセージのうちどれが "good" (正当なビジネス上の理由で、メールのスプーフィングが行われたもの) であることが示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-155">The **Spoof Mail** report shows how many spoof mail messages were detected, and of those, which ones were considered "good" (spoof mail done for legitimate business reasons).</span></span> 
  
<span data-ttu-id="614a5-156">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**スプーフィングメール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-156">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spoof Mail**.</span></span>
  
![このレポートを表示するには、 &amp;セキュリティ/コンプライアンスセンターで、 \> [ \>レポートダッシュボードのスプーフィングメール] に移動します。](media/0427e85c-9e40-4225-a0f0-e21a4e8b0e44.png)
  
<span data-ttu-id="614a5-158">グラフの1日をポイントすると、受信したスプーフィングメールメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-158">When you hover over a day in the chart, you can see how many spoof mail messages came through.</span></span>
  
<span data-ttu-id="614a5-159">レポートをクリック (またはタップ) して、新しいブラウザーウィンドウでレポートを開きます。これにより、レポートの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-159">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
## <a name="spam-detections-report"></a><span data-ttu-id="614a5-160">スパム検出レポート</span><span class="sxs-lookup"><span data-stu-id="614a5-160">Spam Detections report</span></span>

<span data-ttu-id="614a5-161">**スパム検出**レポートには、Exchange Online によってブロックされているすべてのスパムコンテンツが表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-161">The **Spam Detections** report shows all the spam content blocked by Exchange Online.</span></span> 
  
<span data-ttu-id="614a5-162">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **スパム検出**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-162">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Spam Detections**.</span></span>
  
![このレポートを表示するには、 &amp;セキュリティ/コンプライアンスセンターで、 \> [ \> Reports Dashboard EOP Spam の検出] に移動します。](media/028cff3c-79ce-4ec0-8f0f-ec32ac28243a.png)
  
<span data-ttu-id="614a5-p108">グラフの1日の上にカーソルを置くと、その日にブロックされたアイテムの数と、それらのアイテムがどのように分類されているかを確認できます。たとえば、フィルター処理されたスパムメッセージの数と、ブロックされたインターネットプロトコル (IP) アドレスからのアイテムの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p108">When you hover over a day in the chart, you can see how many items were blocked that day, as well as how those items are categorized. For example, you can see how many spam messages were filtered, and how many items came from a blocked Internet Protocol (IP) address.</span></span>
  
<span data-ttu-id="614a5-166">レポートをクリック (またはタップ) して、新しいブラウザーウィンドウでレポートを開きます。これにより、レポートの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-166">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
![スパム検出レポートでは、ブロックまたはフィルターで除外されたスパムメッセージの数がわかります。](media/370ec67d-eb30-4863-bfcf-68a41be02295.png)
  
<span data-ttu-id="614a5-p109">グラフの下に、検出されたスパムアイテムの一覧が表示されます。その他の情報を表示するアイテムを選択します。これには、受信または送信、メッセージ ID、受信者などの追加情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p109">Below the chart, you'll see a list of spam items that were detected. Select an item to view additional information, such as whether the spam item was inbound or outbound, its message ID, and its recipient.</span></span>
  
## <a name="sent-and-received-email-report"></a><span data-ttu-id="614a5-170">送信および受信した電子メールレポート</span><span class="sxs-lookup"><span data-stu-id="614a5-170">Sent and received email report</span></span>

<span data-ttu-id="614a5-171">**送信および受信**した電子メールレポートは、スパム検出、マルウェア、および "good" と識別された電子メールを含む、受信および送信電子メールに関する情報を示すスマートレポートです。</span><span class="sxs-lookup"><span data-stu-id="614a5-171">The **Sent and received email** report is a smart report that shows information about incoming and outgoing email, including spam detections, malware, and email identified as "good."</span></span> 
  
<span data-ttu-id="614a5-172">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **送受信メール**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-172">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Sent and received email**.</span></span>
  
![このレポートを表示するには、 &amp;セキュリティ/コンプライアンスセンターで、 \> [ \>レポートダッシュボード送受信メール] に移動します。](media/0e710ed0-1b0e-4dac-8796-94a01a710f3a.png)
  
<span data-ttu-id="614a5-p110">グラフの1日の上にカーソルを置くと、受信したメッセージの数と、それらのメッセージがどのように分類されるかを確認できます。たとえば、マルウェアが含まれているとして検出されたメッセージの数と、スパムとして識別されたメッセージの数を確認できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-p110">When you hover over a day in the chart, you can see how many messages came in, and how those messages are categorized. For example, you can see how many messages were detected as containing malware, and how many were identified as spam.</span></span>
  
<span data-ttu-id="614a5-176">レポートをクリック (またはタップ) して、新しいブラウザーウィンドウでレポートを開きます。これにより、レポートの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-176">Click (or tap) the report to open it in a new browser window, where you can get a more detailed view of the report.</span></span>
  
<span data-ttu-id="614a5-177">[**分類**] ボックスの一覧を使用すると、情報を種類別または方向 (受信および送信) 別に表示できます。</span><span class="sxs-lookup"><span data-stu-id="614a5-177">You can use the **Break down by** list to view information by type or by direction (incoming and outgoing).</span></span> 
  
![[分類] ボックスの一覧を使用して、種類または方向で情報を表示する](media/a5b30c94-d75f-4bfc-851a-cb155685b177.png)
  
<span data-ttu-id="614a5-p111">グラフの下に、 **GoodMail**、 **SpamContentFiltered**などの電子メールカテゴリの一覧が表示されます。カテゴリを選択して、マルウェアに対して行われたアクションや電子メールが受信または送信されたかどうかなどの追加情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="614a5-p111">Below the chart, you'll see a list of email categories, such as **GoodMail**, **SpamContentFiltered**, and so on. Select a category to view additional information, such as actions that were taken for malware, and whether email was incoming or outgoing.</span></span>
  
![このレポートは、マルウェア対策、スパム対策、およびその他のメッセージの検出に関する情報を示します。](media/9ea4b606-f27a-46ee-97a7-be018e2b839c.png)
  
## <a name="user-reported-messages-report-new"></a><span data-ttu-id="614a5-182">ユーザーによって報告されたメッセージレポート (新)</span><span class="sxs-lookup"><span data-stu-id="614a5-182">User-reported messages report (new!)</span></span>

<span data-ttu-id="614a5-183">ユーザーによって報告された**メッセージ**レポートには、ユーザーが[レポートメッセージアドイン](enable-the-report-message-add-in.md)を使用して、迷惑メール、フィッシングの試行、または正常なメールとして報告した電子メールメッセージに関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="614a5-183">The **User-reported messages** report shows information about email messages that users have reported as junk, phishing attempts, or good mail by using the [Report Message add-in](enable-the-report-message-add-in.md).</span></span>
  
<span data-ttu-id="614a5-p112">組織に対して構成されたスパムポリシーの例外やメールフロールールなどの配信理由を含む、各メッセージの詳細を表示できます。詳細を表示するには、[ユーザーレポート] リスト内のアイテムを選択し、[**概要**] タブと [**詳細**] タブで情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="614a5-p112">Details are available for each message, including the delivery reason, such a spam policy exception or mail flow rule configured for your organization. To view details, select an item in the user-reports list, and then view the information on the **Summary** and **Details** tabs.</span></span> 
  
![ユーザーによって報告されたメッセージのレポートには、ユーザーが迷惑メールではないというラベルが付けられます。](media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)
  
<span data-ttu-id="614a5-187">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、次のいずれかの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="614a5-187">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), do one of the following:</span></span>
  
- <span data-ttu-id="614a5-188">[**脅威管理** \> ]**ダッシュボード** \>の**ユーザーによって報告**されたメッセージに移動します。</span><span class="sxs-lookup"><span data-stu-id="614a5-188">Go to **Threat management** \> **Dashboard** \> **User-reported messages**.</span></span>
    
- <span data-ttu-id="614a5-189">[**脅威の管理** \> ] に移動して **、ユーザーから報告**されたメッセージを**確認** \>します。</span><span class="sxs-lookup"><span data-stu-id="614a5-189">Go to **Threat management** \> **Review** \> **User-reported messages**.</span></span>
    
![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\> ] \> [ユーザーから報告されたメッセージを確認する] を選択します。](media/e372c57c-1414-4616-957b-bc933b8c8711.png)
  
> [!IMPORTANT]
> <span data-ttu-id="614a5-p113">ユーザーによって報告されたメッセージレポートが正常に機能するためには、Office 365 環境の**監査ログを有効にする必要があり**ます。これは、通常、Exchange Online で監査ログの役割が割り当てられているユーザーによって行われます。詳細については、「 [Office 365 監査ログ検索をオンまたはオフにする](turn-audit-log-search-on-or-off.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614a5-p113">In order for the User-reported messages report to work correctly, **audit logging must be turned on** for your Office 365 environment. This is typically done by someone who has the Audit Logs role assigned in Exchange Online. For more information, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> 
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="614a5-194">これらのレポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="614a5-194">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="614a5-195">この記事に記載されているレポートを表示して使用するには、**セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="614a5-195">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="614a5-196">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="614a5-196">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="614a5-197">組織の管理</span><span class="sxs-lookup"><span data-stu-id="614a5-197">Organization Management</span></span>
    - <span data-ttu-id="614a5-198">セキュリティ管理者 (Azure Active Directory 管理センターで割り当てることができます[https://aad.portal.azure.com](https://aad.portal.azure.com)()</span><span class="sxs-lookup"><span data-stu-id="614a5-198">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>
    - <span data-ttu-id="614a5-199">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="614a5-199">Security Reader</span></span>

- <span data-ttu-id="614a5-200">exchange online の場合は、exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [exchange online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="614a5-200">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="614a5-201">組織の管理</span><span class="sxs-lookup"><span data-stu-id="614a5-201">Organization Management</span></span>
    - <span data-ttu-id="614a5-202">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="614a5-202">View-only Organization Management</span></span>
    - <span data-ttu-id="614a5-203">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="614a5-203">View-Only Recipients role</span></span>
    - <span data-ttu-id="614a5-204">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="614a5-204">Compliance Management</span></span>

<span data-ttu-id="614a5-205">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="614a5-205">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="614a5-206">Office 365 セキュリティ&amp; /コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="614a5-206">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="614a5-207">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="614a5-207">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="614a5-208">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="614a5-208">What if the reports aren't showing data?</span></span>

<span data-ttu-id="614a5-p114">レポートにデータが表示されない場合は、ポリシーが正しく設定されているかどうかを再確認してください。詳細については、「 [Office 365 のスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="614a5-p114">If you are not seeing data in your reports, double-check that your policies are set up correctly. To learn more, see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="614a5-211">関連項目</span><span class="sxs-lookup"><span data-stu-id="614a5-211">Related topics</span></span>

[<span data-ttu-id="614a5-212">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="614a5-212">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="614a5-213">Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="614a5-213">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="614a5-214">セキュリティ&amp; /コンプライアンスセンターでレポートのスケジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="614a5-214">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="614a5-215">セキュリティ&amp; /コンプライアンスセンターでカスタムレポートを設定およびダウンロードする</span><span class="sxs-lookup"><span data-stu-id="614a5-215">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

