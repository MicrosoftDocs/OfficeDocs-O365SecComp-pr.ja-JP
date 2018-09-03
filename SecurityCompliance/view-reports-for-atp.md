---
title: Office 365 の高度な脅威保護のためのレポートを表示します。
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
description: 検索し、Office 365 高度な脅威保護、セキュリティでのレポートを使用する方法を説明&amp;コンプライアンス センターです。
ms.openlocfilehash: 13b2a4c142a223a8a912c9017b6033b0b5a1548b
ms.sourcegitcommit: e7b87fae103a858981bdbcdf7ec55afa4751ad05
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2018
ms.locfileid: "23782114"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="e06c6-103">Office 365 の高度な脅威保護のためのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e06c6-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="e06c6-p101">セキュリティ分析ツールのいくつかのレポートを使用するには組織に[Office 365 の高度な脅威保護](office-365-atp.md)(ATP) があり、ユーザーが必要なアクセス許可を持っている場合は場合、&amp;コンプライアンス センターです。(**レポート**には、 \> **ダッシュ ボード**です)。</span><span class="sxs-lookup"><span data-stu-id="e06c6-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the necessary permissions, you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![セキュリティ&amp;コンプライアンス センターのダッシュ ボードを使用して、脅威の高度な保護が作業しているを確認できます](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="e06c6-p102">ATP のレポートには、脅威の保護ステータス レポート、分析ツールのファイルの種類のレポート、および ATP メッセージ破棄レポートが含まれます。この資料では、ATP のレポートについて説明し、表示するのにはその他のレポートへのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e06c6-p102">ATP reports include the Threat protection status report, the ATP File Types report, and the ATP Message Disposition report. This article describes the ATP reports and includes links to additional reports to view.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="e06c6-109">脅威保護のステータス レポート</span><span class="sxs-lookup"><span data-stu-id="e06c6-109">Threat protection status report</span></span>

<span data-ttu-id="e06c6-p103">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールと Exchange のオンラインの脅威保護の高度なによって検出されブロックに関する情報をまとめて 1 つのビューです。レポートには、コンテンツを含む悪意のあるファイル (Url)、マルウェア対策エンジン、 [0 時間の自動 (ZAP) の削除](zero-hour-auto-purge.md)を[ATP の安全なリンク](atp-safe-links.md)、 [ATP などの高度な脅威保護機能によってブロックされている一意の電子メール メッセージの集計の数が用意されています。安全な添付ファイル](atp-safe-attachments.md)、および[Office 365 の ATP のフィッシング詐欺対策機能](atp-anti-phishing.md)です。</span><span class="sxs-lookup"><span data-stu-id="e06c6-p103">The **Threat protection status** report is a single view that brings together information about malicious content and malicious email detected and blocked by Exchange Online and Advanced Threat Protection. The report provides an aggregated count of unique email messages with malicious content (files or URLs) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and Advanced Threat Protection features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md).</span></span>
  
<span data-ttu-id="e06c6-112">セキュリティの脅威保護のステータス レポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **脅威保護の状態**です。</span><span class="sxs-lookup"><span data-stu-id="e06c6-112">To view the Threat protection status report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **Threat protection status**.</span></span>
  
![ATP の脅威保護の状態のレポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="e06c6-114">1 日の詳細なステータスを取得するのには、グラフ上に置きます。</span><span class="sxs-lookup"><span data-stu-id="e06c6-114">To get detailed status for a day, hover over the graph.</span></span>
  
![1 日の ATP の脅威保護の状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="e06c6-p104">既定では、脅威保護のステータス レポートは、過去 7 日間のデータを示します。ただし、**フィルター**を選択し、最大 90 日間のデータを表示する日付範囲を変更できます。</span><span class="sxs-lookup"><span data-stu-id="e06c6-p104">By default, the Threat protection status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP の脅威保護の状態のフィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="e06c6-119">レポートに表示される情報を変更するのには **、データの表示**] メニューの [を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="e06c6-119">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![ATP の脅威保護の状態レポートのオプションを表示します。](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="e06c6-121">分析ツール ファイルの種類のレポート</span><span class="sxs-lookup"><span data-stu-id="e06c6-121">ATP File Types report</span></span>

<span data-ttu-id="e06c6-122">**分析ツール ファイルの種類**のレポートでは、 [ATP の安全な添付ファイル](atp-safe-attachments.md)が悪意のあるものとして検出されたファイルの種類を示します。</span><span class="sxs-lookup"><span data-stu-id="e06c6-122">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="e06c6-123">セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **分析ツール ファイルの種類**です。</span><span class="sxs-lookup"><span data-stu-id="e06c6-123">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![分析ツール ファイルの種類のレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="e06c6-125">特定の日の上に置くと、[安全な添付ファイルの分析ツール](atp-safe-attachments.md)で検出された悪意のあるファイルの種類の内訳を表示でき、[スパム対策&amp;Office 365 のマルウェア対策保護](anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="e06c6-125">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![1 日のレポート データの分析ツールのファイルの種類](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="e06c6-127">ATP メッセージ破棄レポート</span><span class="sxs-lookup"><span data-stu-id="e06c6-127">ATP Message Disposition report</span></span>

<span data-ttu-id="e06c6-128">**ATP メッセージ破棄**レポートでは、悪意のあるコンテンツを持つものとして検出された電子メール メッセージのアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="e06c6-128">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="e06c6-129">セキュリティで、このレポートを表示するのには&amp;コンプライアンス センターでは、**レポート**に移動\>**ダッシュ ボード** \> **ATP メッセージ廃棄**します。</span><span class="sxs-lookup"><span data-stu-id="e06c6-129">To view this report, in the Security &amp; Compliance Center, go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP メッセージ破棄レポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="e06c6-131">グラフのバーの上にマウス ポインターを移動するとき、どのような操作を行った電子メールで検出されたその日が確認できます。</span><span class="sxs-lookup"><span data-stu-id="e06c6-131">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![1 日の ATP メッセージ破棄レポート データ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="e06c6-133">追加のレポートを表示するには</span><span class="sxs-lookup"><span data-stu-id="e06c6-133">Additional reports to view</span></span>

<span data-ttu-id="e06c6-p105">だけでなく、この資料に記載されている ATP のレポートは[電子メール セキュリティのレポート](view-email-security-reports.md)は、セキュリティで利用可能な&amp;コンプライアンス センターです。電子メール セキュリティのレポート[上位の送信者と受信者のレポート](view-email-security-reports.md#top-senders-and-recipients-report)、[なりすましメールのレポート](view-email-security-reports.md#spoof-mail-report)は、[スパム検出レポート](view-email-security-reports.md#spam-detections-report)などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e06c6-p105">In addition to the ATP reports described in this article, [email security reports](view-email-security-reports.md) are available in the Security &amp; Compliance Center. Email security reports include a [Top Senders and Recipients report](view-email-security-reports.md#top-senders-and-recipients-report), a [Spoof Mail report](view-email-security-reports.md#spoof-mail-report), a [Spam Detections report](view-email-security-reports.md#spam-detections-report), and more.</span></span>
  
<span data-ttu-id="e06c6-136">組織が[Office 365 の脅威インテリジェンス](office-365-ti.md)の場合することもでき、 [、セキュリティでエクスプ ローラーを使用して&amp;コンプライアンス センター](use-explorer-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="e06c6-136">And, if your organization has [Office 365 Threat Intelligence](office-365-ti.md), you can also [Use Explorer in the Security &amp; Compliance Center](use-explorer-in-security-and-compliance.md).</span></span>
  
## <a name="what-permissions-are-needed-to-view-these-reports"></a><span data-ttu-id="e06c6-137">これらのレポートを表示するのにはどのようなアクセス許可が必要か。</span><span class="sxs-lookup"><span data-stu-id="e06c6-137">What permissions are needed to view these reports?</span></span>

<span data-ttu-id="e06c6-138">表示し、この資料に記載されている電子メールのセキュリティ レポートを使用して、セキュリティの割り当て、適切なロールが必要&amp;コンプライアンス センターと、Exchange 管理センターで。</span><span class="sxs-lookup"><span data-stu-id="e06c6-138">In order to view and use the email security reports described in this article, you must have an appropriate role assigned in the Security &amp; Compliance Center and in the Exchange Admin Center.</span></span>
  
|<span data-ttu-id="e06c6-139">**役割グループ**</span><span class="sxs-lookup"><span data-stu-id="e06c6-139">**Role group**</span></span>|<span data-ttu-id="e06c6-140">**割り当てられている場合**</span><span class="sxs-lookup"><span data-stu-id="e06c6-140">**Where assigned**</span></span>|<span data-ttu-id="e06c6-141">**詳細情報**</span><span class="sxs-lookup"><span data-stu-id="e06c6-141">**Learn more**</span></span>|
|:-----|:-----|:-----|
| <span data-ttu-id="e06c6-142">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="e06c6-142">One of the following:</span></span>  <br/>  <span data-ttu-id="e06c6-143">組織の管理</span><span class="sxs-lookup"><span data-stu-id="e06c6-143">Organization Management</span></span>  <br/>  <span data-ttu-id="e06c6-144">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="e06c6-144">Security Administrator</span></span>  <br/>  <span data-ttu-id="e06c6-145">セキュリティ リーダー</span><span class="sxs-lookup"><span data-stu-id="e06c6-145">Security Reader</span></span>  <br/> |<span data-ttu-id="e06c6-146">セキュリティ&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e06c6-146">Security &amp; Compliance Center</span></span>  <br/> |[<span data-ttu-id="e06c6-147">Office 365 のセキュリティのアクセス権&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e06c6-147">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md) <br/> |
| <span data-ttu-id="e06c6-148">以下のいずれか:</span><span class="sxs-lookup"><span data-stu-id="e06c6-148">One of the following:</span></span>  <br/>  <span data-ttu-id="e06c6-149">組織の管理</span><span class="sxs-lookup"><span data-stu-id="e06c6-149">Organization Management</span></span>  <br/>  <span data-ttu-id="e06c6-150">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="e06c6-150">View-only Organization Management</span></span>  <br/>  <span data-ttu-id="e06c6-151">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="e06c6-151">View-Only Recipients role</span></span>  <br/>  <span data-ttu-id="e06c6-152">Compliance Management</span><span class="sxs-lookup"><span data-stu-id="e06c6-152">Compliance Management</span></span>  <br/> |<span data-ttu-id="e06c6-153">Exchange 管理センター</span><span class="sxs-lookup"><span data-stu-id="e06c6-153">Exchange Admin Center</span></span>  <br/> |[<span data-ttu-id="e06c6-154">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e06c6-154">Feature permissions in Exchange Online</span></span>](https://technet.microsoft.com/library/jj200673%28v=exchg.150%29.aspx) <br/> |
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e06c6-155">場合、レポート データが表示されていないでしょうか。</span><span class="sxs-lookup"><span data-stu-id="e06c6-155">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e06c6-p106">レポートにデータを表示されない場合、ポリシーが正しく設定されているを再確認してください。組織には、 [ATP の安全なリンクのポリシー](set-up-atp-safe-links-policies.md)および[分析ツールの安全な添付ファイル ポリシー](set-up-atp-safe-attachments-policies.md)の ATP の保護のための順序で定義されている場所が必要です。[Office 365 のスパム対策およびマルウェア対策の保護](anti-spam-and-anti-malware-protection.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e06c6-p106">If you are not seeing data in your reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e06c6-159">関連項目</span><span class="sxs-lookup"><span data-stu-id="e06c6-159">Related topics</span></span>

[<span data-ttu-id="e06c6-160">レポートと Office 365 のセキュリティ情報&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e06c6-160">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="e06c6-161">セキュリティ レポートのスケジュールを作成する&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e06c6-161">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="e06c6-162">設定し、セキュリティでのカスタム レポートをダウンロード&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="e06c6-162">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

