---
title: Office 365 の高度な脅威保護のためのレポートを表示します。
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
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 検索し、Office 365 高度な脅威保護、セキュリティでのレポートを使用する方法を説明&amp;コンプライアンス センターです。
ms.openlocfilehash: a17f182f5c8d79e7863b26324a3c073ef18f14c9
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014949"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="d24f3-103">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="d24f3-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="d24f3-p101">セキュリティ分析ツールのいくつかのレポートを使用するには、組織が[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) には、[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合、&amp;コンプライアンス センターです。(**レポート**には、 \> **ダッシュ ボード**です)。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="d24f3-p102">ATP のレポートには、[脅威保護の状態のレポート](#threat-protection-status-report)は、[分析ツールのファイルの種類のレポート](#atp-file-types-report)、および[ATP メッセージ破棄レポート](#atp-message-disposition-report)が含まれます。この資料では、ATP のレポートについて説明し、[表示するのにはその他のレポート](#additional-reports-to-view)へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p102">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="d24f3-109">脅威保護の状態のレポート</span><span class="sxs-lookup"><span data-stu-id="d24f3-109">Threat Protection Status report</span></span>

<span data-ttu-id="d24f3-p103">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールによって、 [Exchange のオンライン保護](eop/exchange-online-protection-overview.md)(EOP) と[Office 365 の ATP](office-365-atp.md)検出されブロックに関する情報をまとめて 1 つのビューです。レポートには、悪意のあるコンテンツ (ファイルまたは web サイト アドレス (Url))、マルウェア対策エンジン、 [0 時間の自動 (ZAP) を削除する](zero-hour-auto-purge.md)、 [ATP の安全なリンク](atp-safe-links.md)、 [ATP の安全などの分析ツールの機能によってブロックされている一意の電子メール メッセージの集計の数が用意されています。添付ファイル](atp-safe-attachments.md)、および[分析ツール、フィッシング対策機能](atp-anti-phishing.md)です。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p103">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md). The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d24f3-p104">脅威保護の状態レポートは、 [Office 365 の ATP](office-365-atp.md)または[Exchange のオンライン保護](eop/exchange-online-protection-eop.md)(EOP) は使用しているお客様に利用可能ですただし、ATP のお客様の脅威保護の状態レポートに表示される情報 EOP の顧客が表示とは異なるデータが含まれる予定です。たとえば、ATP のお客様の脅威保護の状態レポート[SharePoint のオンライン、OneDrive、またはマイクロソフトのチームで悪意のあるファイルの検出](atp-for-spo-odb-and-teams.md)に関する情報が含まれます。このような情報は ATP、EOP は分析ツールではない使用しているお客様の脅威保護のステータス レポートの詳細は表示されませんので。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md). Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="d24f3-115">脅威保護の状態レポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)**のレポート**には、 \> **ダッシュ ボード** \> **脅威保護の状態**です。</span><span class="sxs-lookup"><span data-stu-id="d24f3-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP の脅威保護の状態のレポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="d24f3-117">1 日の詳細なステータスを取得するのには、グラフ上に置きます。</span><span class="sxs-lookup"><span data-stu-id="d24f3-117">To get detailed status for a day, hover over the graph.</span></span>
  
![1 日の ATP の脅威保護の状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="d24f3-p105">既定では、脅威保護の状態レポートは、過去 7 日間のデータを示します。ただし、**フィルター**を選択し、最大 90 日間のデータを表示する日付範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p105">By default, the Threat Protection Status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP の脅威保護の状態のフィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="d24f3-122">レポートに表示される情報を変更するのには **、データの表示**] メニューの [を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="d24f3-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![ATP の脅威保護の状態レポートのオプションを表示します。](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="d24f3-124">分析ツール ファイルの種類のレポート</span><span class="sxs-lookup"><span data-stu-id="d24f3-124">ATP File Types report</span></span>

<span data-ttu-id="d24f3-125">**分析ツール ファイルの種類**のレポートでは、 [ATP の安全な添付ファイル](atp-safe-attachments.md)が悪意のあるものとして検出されたファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="d24f3-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="d24f3-126">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)**のレポート**には、 \> **ダッシュ ボード** \> **分析ツール ファイルの種類**です。</span><span class="sxs-lookup"><span data-stu-id="d24f3-126">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![分析ツール ファイルの種類のレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="d24f3-128">特定の日の上に置くと、[安全な添付ファイルの分析ツール](atp-safe-attachments.md)で検出された悪意のあるファイルの種類の内訳を表示でき、[スパム対策&amp;Office 365 のマルウェア対策保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="d24f3-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![1 日のレポート データの分析ツールのファイルの種類](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="d24f3-130">ATP メッセージ破棄レポート</span><span class="sxs-lookup"><span data-stu-id="d24f3-130">ATP Message Disposition report</span></span>

<span data-ttu-id="d24f3-131">**ATP メッセージ破棄**レポートでは、悪意のあるコンテンツを持つものとして検出された電子メール メッセージのアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="d24f3-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="d24f3-132">このレポートを表示するのには、[セキュリティ&amp;コンプライアンス センター](https://protection.office.com)**のレポート**には、 \> **ダッシュ ボード** \> **ATP メッセージ廃棄**します。</span><span class="sxs-lookup"><span data-stu-id="d24f3-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP メッセージ破棄レポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="d24f3-134">グラフのバーの上にマウス ポインターを移動するとき、どのような操作を行った電子メールで検出されたその日が確認できます。</span><span class="sxs-lookup"><span data-stu-id="d24f3-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![1 日の ATP メッセージ破棄レポート データ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="d24f3-136">追加のレポートを表示するには</span><span class="sxs-lookup"><span data-stu-id="d24f3-136">Additional reports to view</span></span>

<span data-ttu-id="d24f3-137">ATP レポートは、この資料に記載されている、だけでなく他のいくつかのレポートがある、次の表に示すよう。</span><span class="sxs-lookup"><span data-stu-id="d24f3-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>


|<span data-ttu-id="d24f3-138">レポートの種類</span><span class="sxs-lookup"><span data-stu-id="d24f3-138">Report type</span></span>  |<span data-ttu-id="d24f3-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d24f3-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="d24f3-140">**電子メール セキュリティのレポート**上位の送信者と受信者のレポート、なりすましメール レポート、スパム検出レポートなどです。</span><span class="sxs-lookup"><span data-stu-id="d24f3-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="d24f3-141">セキュリティで電子メールのセキュリティ レポートを表示する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="d24f3-141">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="d24f3-142">**エクスプ ローラー**(脅威のエクスプ ローラーとも呼ばれ、これに含まれる[Office 365 の脅威インテリジェンス](office-365-ti.md))</span><span class="sxs-lookup"><span data-stu-id="d24f3-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Threat Intelligence](office-365-ti.md))</span></span>     | [<span data-ttu-id="d24f3-143">エクスプ ローラーを使用して、セキュリティで&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="d24f3-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="d24f3-p106">**EOP と分析ツールの結果**これは、PowerShell を使用して生成するカスタムのレポート)。このレポートには、ドメイン、日付、イベントの種類、方向、操作、およびメッセージの数などの情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p106">**EOP and ATP results** (This is a custom report you generate by using PowerShell). This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="d24f3-146">Get MailTrafficATPReport コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="d24f3-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="d24f3-p107">**EOP と ATP の検出**これは、PowerShell を使用して生成するカスタムのレポート)。このレポートには、悪意のあるファイルまたは Url、フィッシング詐欺、偽装、および電子メールやファイルでの他の潜在的な脅威に関する詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p107">**EOP and ATP detections** (This is a custom report you generate by using PowerShell). This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="d24f3-149">Get MailDetailATPReport コマンドレットのリファレンス</span><span class="sxs-lookup"><span data-stu-id="d24f3-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="d24f3-150">ATP のレポートを表示するのにはどのようなアクセス許可が必要か。</span><span class="sxs-lookup"><span data-stu-id="d24f3-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="d24f3-151">表示し、この資料に記載されているレポートを使用するために**セキュリティの両方に割り当てられている適切なロールを持つ必要があります&amp;コンプライアンス センターと、Exchange 管理センター**です。</span><span class="sxs-lookup"><span data-stu-id="d24f3-151">In order to view and use the reports described in this article, **you must have an appropriate role assigned in both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="d24f3-152">セキュリティの&amp;コンプライアンス センターでは、する必要があります次に割り当てられている役割の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="d24f3-152">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="d24f3-153">組織の管理</span><span class="sxs-lookup"><span data-stu-id="d24f3-153">Organization Management</span></span>
    - <span data-ttu-id="d24f3-154">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="d24f3-154">Security Administrator</span></span>
    - <span data-ttu-id="d24f3-155">セキュリティ リーダー</span><span class="sxs-lookup"><span data-stu-id="d24f3-155">Security Reader</span></span>

- <span data-ttu-id="d24f3-156">Exchange Online では、する必要があります次に割り当てられている役割の 1 つ。</span><span class="sxs-lookup"><span data-stu-id="d24f3-156">For Exchange Online, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="d24f3-157">組織の管理</span><span class="sxs-lookup"><span data-stu-id="d24f3-157">Organization Management</span></span>
    - <span data-ttu-id="d24f3-158">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="d24f3-158">View-only Organization Management</span></span>
    - <span data-ttu-id="d24f3-159">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="d24f3-159">View-Only Recipients role</span></span>
    - <span data-ttu-id="d24f3-160">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="d24f3-160">Compliance Management</span></span>

<span data-ttu-id="d24f3-161">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d24f3-161">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="d24f3-162">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="d24f3-162">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="d24f3-163">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="d24f3-163">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="d24f3-164">場合、レポート データが表示されていないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="d24f3-164">What if the reports aren't showing data?</span></span>

<span data-ttu-id="d24f3-p108">ATP レポートにデータを表示されない場合、ポリシーが正しく設定されているを再確認してください。組織には、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)および[分析ツールの安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の ATP の保護のための順序で定義されている場所が必要です。[Office 365 のスパム対策およびマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d24f3-p108">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d24f3-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="d24f3-168">Related topics</span></span>

[<span data-ttu-id="d24f3-169">レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="d24f3-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="d24f3-170">セキュリティ レポートのスケジュールを作成する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="d24f3-170">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="d24f3-171">設定し、セキュリティでのカスタム レポートをダウンロード&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="d24f3-171">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

