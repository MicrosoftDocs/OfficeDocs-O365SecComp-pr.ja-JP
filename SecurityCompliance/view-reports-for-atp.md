---
title: Office 365 Advanced Threat Protection のレポートを表示する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/21/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターで Office 365 Advanced Threat Protection のレポートを検索して使用する方法について説明します。
ms.openlocfilehash: 6bf8c3222b0ce4cecd1b14f407f7e9ee42783a75
ms.sourcegitcommit: 2b46fba650df8d252b1dd2b3c3f080a383183a06
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2019
ms.locfileid: "34408402"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="f3d3c-103">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f3d3c-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="f3d3c-104">組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) があり、[必要なアクセス許可](#what-permissions-are-needed-to-view-the-atp-reports)がある場合は、セキュリティ&amp;コンプライアンスセンターでいくつかの ATP レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="f3d3c-105">([**レポート** \> ]**ダッシュボード**に移動します。)</span><span class="sxs-lookup"><span data-stu-id="f3d3c-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="f3d3c-107">ATP レポートには次のものが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-107">ATP reports include the following:</span></span>
- [<span data-ttu-id="f3d3c-108">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-108">Threat Protection Status report</span></span>](#threat-protection-status-report)
- [<span data-ttu-id="f3d3c-109">ATP ファイルタイプレポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-109">ATP File Types report</span></span>](#atp-file-types-report)
- [<span data-ttu-id="f3d3c-110">ATP メッセージディスポジションレポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-110">ATP Message Disposition report</span></span>](#atp-message-disposition-report)
- <span data-ttu-id="f3d3c-111">[リアルタイム検出またはエクスプローラー](threat-explorer.md) (OFFICE 365 ATP プラン1または2を使用しているかどうかによって異なります)</span><span class="sxs-lookup"><span data-stu-id="f3d3c-111">either [real-time detections or Explorer](threat-explorer.md) (depending on whether you have Office 365 ATP Plan 1 or 2)</span></span>
- <span data-ttu-id="f3d3c-112">...その[他](#additional-reports-to-view)。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-112">... [and more](#additional-reports-to-view).</span></span> 

<span data-ttu-id="f3d3c-113">ATP レポートの概要とその使用方法については、この記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-113">Read this article to get an overview of ATP reports and how to use them.</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="f3d3c-114">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-114">Threat Protection Status report</span></span>

<span data-ttu-id="f3d3c-115">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) および[Office 365 ATP](office-365-atp.md)によって検出されブロックされます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-115">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="f3d3c-116">このレポートは、時間の経過による検出 (最大90日間) を表示するのに役立ち、セキュリティ管理者が傾向を特定したり、ポリシーが調整を必要とするかどうかを判断したりできます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-116">This report is useful for viewing detections over time (up to 90 days), and it enables security administrators to identify trends or determine whether policies need adjustments.</span></span> 

<span data-ttu-id="f3d3c-117">脅威保護の状態レポートは、マルウェア対策エンジンによってブロックされたファイルや web サイトアドレス (Url)、[ゼロ時間の自動削除 (ZAP)](zero-hour-auto-purge.md)、ATP 機能など、悪意のあるコンテンツを含む一意の電子メールメッセージの合計数を示します。[Atp の安全なリンク](atp-safe-links.md)、 [atp の安全な添付ファイル](atp-safe-attachments.md)、および[atp のフィッシング対策機能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-117">The Threat Protection Status report provides an aggregated count of unique email messages with malicious content, such as files or website addresses (URLs) that were blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features like [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="f3d3c-118">脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-118">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="f3d3c-119">たとえば、ATP のお客様向けの脅威保護状態レポートには、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-119">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="f3d3c-120">このような情報は ATP に固有のものなので、EOP を持たないお客様は脅威保護の状態レポートにこれらの詳細を表示しません。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-120">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="f3d3c-121">脅威保護の状態レポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**脅威保護の状態**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-121">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP の脅威保護状態レポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="f3d3c-123">1日の詳細な状態を取得するには、グラフの上にポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-123">To get detailed status for a day, hover over the graph.</span></span>
  
![1日の ATP の脅威保護状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="f3d3c-125">既定では、脅威保護の状態レポートには過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-125">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="f3d3c-126">ただし、**フィルター**を選択し、日付の範囲を変更して、最大90日間のデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-126">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> <span data-ttu-id="f3d3c-127">(試用版サブスクリプションを使用している場合は、30日間のデータに制限されることがあります)。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-127">(If you are using a trial subscription, you might be limited to 30 days' of data.)</span></span>
  
![ATP の脅威保護状態フィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="f3d3c-129">[**データの表示**] メニューを使用して、レポートに表示される情報を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-129">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![ATP の脅威保護状態レポートの表示オプション](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="f3d3c-131">ATP ファイルタイプレポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-131">ATP File Types report</span></span>

<span data-ttu-id="f3d3c-132">**Atp ファイルの種類**レポートには、 [atp の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-132">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="f3d3c-133">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP**] [ファイルの種類] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-133">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP ファイルタイプレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="f3d3c-135">特定の日の上にカーソルを移動すると、 [Office 365 で&amp; ](anti-spam-and-anti-malware-protection.md)、ATP の安全な[添付](atp-safe-attachments.md)ファイルとスパム対策のマルウェア対策保護によって検出された悪意のあるファイルの種類の分類を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-135">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![1日の ATP ファイルタイプレポートデータ](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="f3d3c-137">ATP メッセージディスポジションレポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-137">ATP Message Disposition report</span></span>

<span data-ttu-id="f3d3c-138">**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-138">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="f3d3c-139">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP メッセージ廃棄**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-139">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP メッセージディスポジションレポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="f3d3c-141">グラフのバーの上にマウスカーソルを移動すると、その日に検出されたメールに対して実行されたアクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-141">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![1日の ATP メッセージディスポジションレポートデータ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="f3d3c-143">表示する追加レポート</span><span class="sxs-lookup"><span data-stu-id="f3d3c-143">Additional reports to view</span></span>

<span data-ttu-id="f3d3c-144">この記事で説明されている ATP レポートに加えて、次の表に示すように、他にもいくつかのレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-144">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="f3d3c-145">レポート (s)</span><span class="sxs-lookup"><span data-stu-id="f3d3c-145">Report(s)</span></span>  |<span data-ttu-id="f3d3c-146">詳細</span><span class="sxs-lookup"><span data-stu-id="f3d3c-146">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="f3d3c-147">**エクスプローラー**または**リアルタイム検出**(Office 365 ATP Plan 2 のお客様はエクスプローラーを所有しています。Office 365 ATP Plan 1 お客様はリアルタイムの検出を行っています。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-147">**Explorer** or **real-time detections** (Office 365 ATP Plan 2 customers have Explorer; Office 365 ATP Plan 1 customers have real-time detections.)</span></span>| [<span data-ttu-id="f3d3c-148">脅威エクスプローラー (およびリアルタイム検出)</span><span class="sxs-lookup"><span data-stu-id="f3d3c-148">Threat Explorer (and real-time detections)</span></span>](threat-explorer.md)       |
|<span data-ttu-id="f3d3c-149">上位の送信者と受信者のレポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-149">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="f3d3c-150">セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="f3d3c-150">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="f3d3c-151">**ATP の安全なリンクの URL トレース**(これは、PowerShell を使用して生成したレポートです。)このレポートには、過去7日間 (7 日間) の ATP の安全なリンクアクションの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-151">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="f3d3c-152">取得-UrlTrace コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="f3d3c-152">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|<span data-ttu-id="f3d3c-153">**EOP および ATP の結果**(これは、PowerShell を使用して生成するカスタムレポートです)。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-153">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="f3d3c-154">このレポートには、ドメイン、日付、イベントの種類、方向、アクション、メッセージ数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-154">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="f3d3c-155">Get-mailtrafficatpreport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="f3d3c-155">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="f3d3c-156">**EOP および ATP の検出**(これは、PowerShell を使用して生成するカスタムレポートです)。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-156">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="f3d3c-157">このレポートには、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-157">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="f3d3c-158">Get-MailDetailATPReport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="f3d3c-158">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="f3d3c-159">ATP レポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-159">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="f3d3c-160">この記事に記載されているレポートを表示して使用するには、**セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-160">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="f3d3c-161">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-161">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="f3d3c-162">組織の管理</span><span class="sxs-lookup"><span data-stu-id="f3d3c-162">Organization Management</span></span>
    - <span data-ttu-id="f3d3c-163">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="f3d3c-163">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="f3d3c-164">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="f3d3c-164">Security Reader</span></span>

- <span data-ttu-id="f3d3c-165">Exchange Online の場合は、Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [Exchange online Powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-165">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="f3d3c-166">組織の管理</span><span class="sxs-lookup"><span data-stu-id="f3d3c-166">Organization Management</span></span>
    - <span data-ttu-id="f3d3c-167">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="f3d3c-167">View-only Organization Management</span></span>
    - <span data-ttu-id="f3d3c-168">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="f3d3c-168">View-Only Recipients role</span></span>
    - <span data-ttu-id="f3d3c-169">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="f3d3c-169">Compliance Management</span></span>

<span data-ttu-id="f3d3c-170">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-170">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="f3d3c-171">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="f3d3c-171">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="f3d3c-172">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="f3d3c-172">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="f3d3c-173">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-173">What if the reports aren't showing data?</span></span>

<span data-ttu-id="f3d3c-174">ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-174">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="f3d3c-175">組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-175">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="f3d3c-176">また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3d3c-176">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f3d3c-177">関連項目</span><span class="sxs-lookup"><span data-stu-id="f3d3c-177">Related topics</span></span>

[<span data-ttu-id="f3d3c-178">Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="f3d3c-178">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="f3d3c-179">セキュリティ&amp; /コンプライアンスセンターでレポートのスケジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="f3d3c-179">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="f3d3c-180">セキュリティ&amp; /コンプライアンスセンターでカスタムレポートを設定およびダウンロードする</span><span class="sxs-lookup"><span data-stu-id="f3d3c-180">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

