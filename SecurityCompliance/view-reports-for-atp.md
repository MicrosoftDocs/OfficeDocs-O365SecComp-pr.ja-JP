---
title: Office 365 Advanced Threat Protection のレポートを表示する
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
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection: M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターで Office 365 Advanced Threat Protection のレポートを検索して使用する方法について説明します。
ms.openlocfilehash: 63fdb0a04107c686af02332ec706e7dcada788a3
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219667"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="e484d-103">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="e484d-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="e484d-p101">組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) があり、[必要なアクセス許可](#what-permissions-are-needed-to-view-these-reports)がある場合は、セキュリティ&amp;コンプライアンスセンターでいくつかの ATP レポートを使用できます。([**レポート** \> ]**ダッシュボード**に移動します。)</span><span class="sxs-lookup"><span data-stu-id="e484d-p101">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-these-reports), you can use several ATP reports in the Security &amp; Compliance Center. (Go to **Reports** \> **Dashboard**.)</span></span>
  
![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="e484d-p102">atp レポートには、[脅威保護の状態レポート](#threat-protection-status-report)、 [atp ファイルの種類レポート](#atp-file-types-report)、 [atp メッセージ廃棄レポート](#atp-message-disposition-report)が含まれます。この記事では、ATP レポートについて説明し、[表示する追加レポート](#additional-reports-to-view)へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e484d-p102">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report). This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="e484d-109">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="e484d-109">Threat Protection Status report</span></span>

<span data-ttu-id="e484d-p103">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) および[Office 365 ATP](office-365-atp.md)によって検出されブロックされます。このレポートでは、悪意のあるコンテンツ (ファイルまたは web サイトアドレス (url)) を使用した一意の電子メールメッセージの集計数が提供されます。これには、非マルウェア対策エンジン、[ゼロ時間の自動削除 (ZAP](zero-hour-auto-purge.md))、atp の各機能 (atp の安全な[リンク](atp-safe-links.md)など) によるブロックがあります。 [添付ファイル](atp-safe-attachments.md)、および[ATP のフィッシング対策機能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="e484d-p103">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md). The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e484d-p104">脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。たとえば、ATP のお客様向けの脅威保護状態レポートには、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報が含まれています。このような情報は atp に固有のものなので、EOP を持たないお客様は脅威保護の状態レポートにこれらの詳細を表示しません。</span><span class="sxs-lookup"><span data-stu-id="e484d-p104">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see. For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md). Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="e484d-115">脅威保護の状態レポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**脅威保護の状態**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e484d-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP の脅威保護状態レポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="e484d-117">1日の詳細な状態を取得するには、グラフの上にポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="e484d-117">To get detailed status for a day, hover over the graph.</span></span>
  
![1日の ATP の脅威保護状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="e484d-p105">既定では、脅威保護の状態レポートには過去7日間のデータが表示されます。ただし、**フィルター**を選択し、日付の範囲を変更して、最大90日間のデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e484d-p105">By default, the Threat Protection Status report shows data for the past seven days. However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP の脅威保護状態フィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="e484d-122">[**データの表示**] メニューを使用して、レポートに表示される情報を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="e484d-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![ATP の脅威保護状態レポートの表示オプション](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="e484d-124">ATP ファイルタイプレポート</span><span class="sxs-lookup"><span data-stu-id="e484d-124">ATP File Types report</span></span>

<span data-ttu-id="e484d-125">**atp ファイルの種類**レポートには、 [atp の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e484d-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="e484d-126">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP**] [ファイルの種類] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e484d-126">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP ファイルタイプレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="e484d-128">特定の日の上にカーソルを移動すると、 [Office 365 で&amp; ](anti-spam-and-anti-malware-protection.md)、ATP の安全な[添付](atp-safe-attachments.md)ファイルとスパム対策のマルウェア対策保護によって検出された悪意のあるファイルの種類の分類を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e484d-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![1日の ATP ファイルタイプレポートデータ](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="e484d-130">ATP メッセージディスポジションレポート</span><span class="sxs-lookup"><span data-stu-id="e484d-130">ATP Message Disposition report</span></span>

<span data-ttu-id="e484d-131">**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e484d-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="e484d-132">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP メッセージ廃棄**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="e484d-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP メッセージディスポジションレポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="e484d-134">グラフのバーの上にマウスカーソルを移動すると、その日に検出されたメールに対して実行されたアクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="e484d-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![1日の ATP メッセージディスポジションレポートデータ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="e484d-136">表示する追加レポート</span><span class="sxs-lookup"><span data-stu-id="e484d-136">Additional reports to view</span></span>

<span data-ttu-id="e484d-137">この記事で説明されている ATP レポートに加えて、次の表に示すように、他にもいくつかのレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="e484d-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="e484d-138">レポートの種類</span><span class="sxs-lookup"><span data-stu-id="e484d-138">Report type</span></span>  |<span data-ttu-id="e484d-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e484d-139">Learn more</span></span>  |
|---------|---------|
|<span data-ttu-id="e484d-140">上位の送信者と受信者のレポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。</span><span class="sxs-lookup"><span data-stu-id="e484d-140">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="e484d-141">セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="e484d-141">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="e484d-142">**エクスプローラー**(脅威エクスプローラーとも呼ばれます。これは[Office 365 の脅威インテリジェンス](office-365-ti.md)に含まれています)</span><span class="sxs-lookup"><span data-stu-id="e484d-142">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Threat Intelligence](office-365-ti.md))</span></span>     | [<span data-ttu-id="e484d-143">セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="e484d-143">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="e484d-p106">**EOP および ATP の結果**(これは、PowerShell を使用して生成するカスタムレポートです)。このレポートには、ドメイン、日付、イベントの種類、方向、アクション、メッセージ数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e484d-p106">**EOP and ATP results** (This is a custom report you generate by using PowerShell). This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="e484d-146">get-mailtrafficatpreport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="e484d-146">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="e484d-p107">**EOP および ATP の検出**(これは、PowerShell を使用して生成するカスタムレポートです)。このレポートには、悪意のあるファイルまたは url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="e484d-p107">**EOP and ATP detections** (This is a custom report you generate by using PowerShell). This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="e484d-149">Get-maildetailatpreport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="e484d-149">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="e484d-150">ATP レポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="e484d-150">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="e484d-151">この記事に記載されているレポートを表示して使用するには、**セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="e484d-151">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange Admin Center**.</span></span>

- <span data-ttu-id="e484d-152">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e484d-152">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="e484d-153">組織の管理</span><span class="sxs-lookup"><span data-stu-id="e484d-153">Organization Management</span></span>
    - <span data-ttu-id="e484d-154">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="e484d-154">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="e484d-155">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="e484d-155">Security Reader</span></span>

- <span data-ttu-id="e484d-156">exchange online の場合は、exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [exchange online powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e484d-156">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="e484d-157">組織の管理</span><span class="sxs-lookup"><span data-stu-id="e484d-157">Organization Management</span></span>
    - <span data-ttu-id="e484d-158">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="e484d-158">View-only Organization Management</span></span>
    - <span data-ttu-id="e484d-159">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="e484d-159">View-Only Recipients role</span></span>
    - <span data-ttu-id="e484d-160">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="e484d-160">Compliance Management</span></span>

<span data-ttu-id="e484d-161">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e484d-161">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="e484d-162">Office 365 セキュリティ&amp; /コンプライアンスセンターのアクセス許可</span><span class="sxs-lookup"><span data-stu-id="e484d-162">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="e484d-163">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="e484d-163">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="e484d-164">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="e484d-164">What if the reports aren't showing data?</span></span>

<span data-ttu-id="e484d-p108">ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e484d-p108">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly. Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place. Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e484d-168">関連項目</span><span class="sxs-lookup"><span data-stu-id="e484d-168">Related topics</span></span>

[<span data-ttu-id="e484d-169">Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="e484d-169">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="e484d-170">セキュリティ&amp; /コンプライアンスセンターでレポートのスケジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="e484d-170">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="e484d-171">セキュリティ&amp; /コンプライアンスセンターでカスタムレポートを設定およびダウンロードする</span><span class="sxs-lookup"><span data-stu-id="e484d-171">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

