---
title: Office 365 Advanced Threat Protection のレポートを表示する
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 04/01/2019
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
ms.openlocfilehash: 3525c71f8a627d930afbf94f5f0d12e55f19a0b6
ms.sourcegitcommit: 0d5a863f48914eeaaf29f7d2a2022618de186247
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34077323"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a><span data-ttu-id="51d70-103">Office 365 Advanced Threat Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="51d70-103">View reports for Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="51d70-104">組織に[Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) があり、[必要なアクセス許可](#what-permissions-are-needed-to-view-the-atp-reports)がある場合は、セキュリティ&amp;コンプライアンスセンターでいくつかの ATP レポートを使用できます。</span><span class="sxs-lookup"><span data-stu-id="51d70-104">If your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) and you have the [necessary permissions](#what-permissions-are-needed-to-view-the-atp-reports), you can use several ATP reports in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="51d70-105">([**レポート** \> ]**ダッシュボード**に移動します。)</span><span class="sxs-lookup"><span data-stu-id="51d70-105">(Go to **Reports** \> **Dashboard**.)</span></span>
  
![セキュリティ&amp;コンプライアンスセンターのダッシュボードは、高度な脅威保護が機能している場所を確認するのに役立ちます。](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)
  
<span data-ttu-id="51d70-107">ATP レポートには、[脅威保護の状態レポート](#threat-protection-status-report)、 [Atp ファイルの種類レポート](#atp-file-types-report)、 [atp メッセージ廃棄レポート](#atp-message-disposition-report)が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51d70-107">ATP reports include the [Threat Protection Status report](#threat-protection-status-report), the [ATP File Types report](#atp-file-types-report), and the [ATP Message Disposition report](#atp-message-disposition-report).</span></span> <span data-ttu-id="51d70-108">この記事では、ATP レポートについて説明し、[表示する追加レポート](#additional-reports-to-view)へのリンクが含まれています。</span><span class="sxs-lookup"><span data-stu-id="51d70-108">This article describes the ATP reports and includes links to [additional reports to view](#additional-reports-to-view).</span></span>
  
## <a name="threat-protection-status-report"></a><span data-ttu-id="51d70-109">脅威保護の状態レポート</span><span class="sxs-lookup"><span data-stu-id="51d70-109">Threat Protection Status report</span></span>

<span data-ttu-id="51d70-110">**脅威保護の状態**レポートは、悪意のあるコンテンツや悪意のある電子メールに関する情報をまとめた1つのビューで、 [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) および[Office 365 ATP](office-365-atp.md)によって検出されブロックされます。</span><span class="sxs-lookup"><span data-stu-id="51d70-110">The **Threat Protection Status** report is a single view that brings together information about malicious content and malicious email detected and blocked by [Exchange Online Protection](eop/exchange-online-protection-overview.md) (EOP) and [Office 365 ATP](office-365-atp.md).</span></span> <span data-ttu-id="51d70-111">このレポートでは、悪意のあるコンテンツ (ファイルまたは web サイトアドレス (Url)) を使用した一意の電子メールメッセージの集計数が提供されます。これには、非マルウェア対策エンジン、[ゼロ時間の自動削除 (ZAP](zero-hour-auto-purge.md))、atp の各機能 (atp の安全な[リンク](atp-safe-links.md)など) によるブロックがあります。 [添付ファイル](atp-safe-attachments.md)、および[ATP のフィッシング対策機能](atp-anti-phishing.md)。</span><span class="sxs-lookup"><span data-stu-id="51d70-111">The report provides an aggregated count of unique email messages with malicious content (files or website addresses (URLs)) blocked by the anti-malware engine, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md), and ATP features, such as [ATP Safe Links](atp-safe-links.md), [ATP Safe Attachments](atp-safe-attachments.md), and [ATP anti-phishing capabilities](atp-anti-phishing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="51d70-112">脅威保護の状態レポートは、 [Office 365 ATP](office-365-atp.md)または[Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP) のいずれかを使用しているお客様が利用できます。ただし、ATP のお客様の脅威保護状態レポートに表示される情報には、EOP のお客様に表示されるものとは異なるデータが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="51d70-112">A Threat Protection Status report is available to customers who have either [Office 365 ATP](office-365-atp.md) or [Exchange Online Protection](eop/exchange-online-protection-eop.md) (EOP); however, the information that is displayed in the Threat Protection Status report for ATP customers will likely contain different data than what EOP customers might see.</span></span> <span data-ttu-id="51d70-113">たとえば、ATP のお客様向けの脅威保護状態レポートには、 [SharePoint Online、OneDrive、Microsoft Teams で検出された悪意のあるファイル](atp-for-spo-odb-and-teams.md)に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="51d70-113">For example, the Threat Protection Status report for ATP customers will contain information about [malicious files detected in SharePoint Online, OneDrive, or Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> <span data-ttu-id="51d70-114">このような情報は ATP に固有のものなので、EOP を持たないお客様は脅威保護の状態レポートにこれらの詳細を表示しません。</span><span class="sxs-lookup"><span data-stu-id="51d70-114">Such information is specific to ATP, so customers who have EOP but not ATP will not see those details in their Threat Protection Status report.</span></span>
  
<span data-ttu-id="51d70-115">脅威保護の状態レポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \>の**脅威保護の状態**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="51d70-115">To view the Threat Protection Status report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **Threat Protection Status**.</span></span>
  
![ATP の脅威保護状態レポート](media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)
  
<span data-ttu-id="51d70-117">1日の詳細な状態を取得するには、グラフの上にポインターを移動します。</span><span class="sxs-lookup"><span data-stu-id="51d70-117">To get detailed status for a day, hover over the graph.</span></span>
  
![1日の ATP の脅威保護状態データ](media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)
  
<span data-ttu-id="51d70-119">既定では、脅威保護の状態レポートには過去7日間のデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d70-119">By default, the Threat Protection Status report shows data for the past seven days.</span></span> <span data-ttu-id="51d70-120">ただし、**フィルター**を選択し、日付の範囲を変更して、最大90日間のデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="51d70-120">However, you can choose **Filters** and change the date range to view data for up to 90 days.</span></span> 
  
![ATP の脅威保護状態フィルター](media/4f703369-642b-402b-9758-b9c828283410.png)
  
<span data-ttu-id="51d70-122">[**データの表示**] メニューを使用して、レポートに表示される情報を変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="51d70-122">You can also use the **View data by** menu to change what information is displayed in the report.</span></span> 
  
![ATP の脅威保護状態レポートの表示オプション](media/4959bf8c-d192-4542-b00b-184e101e7513.png)
  
## <a name="atp-file-types-report"></a><span data-ttu-id="51d70-124">ATP ファイルタイプレポート</span><span class="sxs-lookup"><span data-stu-id="51d70-124">ATP File Types report</span></span>

<span data-ttu-id="51d70-125">**Atp ファイルの種類**レポートには、 [atp の安全な添付](atp-safe-attachments.md)ファイルによって検出されたファイルの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d70-125">The **ATP File Types** report shows you the type of files detected as malicious by [ATP Safe Attachments](atp-safe-attachments.md).</span></span>
  
<span data-ttu-id="51d70-126">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP**] [ファイルの種類] に移動します。</span><span class="sxs-lookup"><span data-stu-id="51d70-126">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP File Types**.</span></span>
  
![ATP ファイルタイプレポート](media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
<span data-ttu-id="51d70-128">特定の日の上にカーソルを移動すると、 [Office 365 で&amp; ](anti-spam-and-anti-malware-protection.md)、ATP の安全な[添付](atp-safe-attachments.md)ファイルとスパム対策のマルウェア対策保護によって検出された悪意のあるファイルの種類の分類を確認できます。</span><span class="sxs-lookup"><span data-stu-id="51d70-128">When you hover over a particular day, you can see the breakdown of types of malicious files that were detected by [ATP Safe Attachments](atp-safe-attachments.md) and [anti-spam &amp; anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
![1日の ATP ファイルタイプレポートデータ](media/10d18428-699a-41d2-a73e-be3a8214ada1.png)
  
## <a name="atp-message-disposition-report"></a><span data-ttu-id="51d70-130">ATP メッセージディスポジションレポート</span><span class="sxs-lookup"><span data-stu-id="51d70-130">ATP Message Disposition report</span></span>

<span data-ttu-id="51d70-131">**ATP メッセージディスポジション**レポートには、悪意のあるコンテンツが含まれていることが検出された電子メールメッセージに対して実行されたアクションが表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d70-131">The **ATP Message Disposition** report shows you the actions that were taken for email messages that were detected as having malicious content.</span></span> 
  
<span data-ttu-id="51d70-132">このレポートを表示するには[、 &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)で、[**レポート** \> **ダッシュボード** \> **ATP メッセージ廃棄**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="51d70-132">To view this report, in the [Security &amp; Compliance Center](https://protection.office.com), go to **Reports** \> **Dashboard** \> **ATP Message Disposition**.</span></span>
  
![ATP メッセージディスポジションレポート](media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)
  
<span data-ttu-id="51d70-134">グラフのバーの上にマウスカーソルを移動すると、その日に検出されたメールに対して実行されたアクションを確認できます。</span><span class="sxs-lookup"><span data-stu-id="51d70-134">When you hover over a bar in the chart, you can see what actions were taken for detected email for that day.</span></span>
  
![1日の ATP メッセージディスポジションレポートデータ](media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)
  
## <a name="additional-reports-to-view"></a><span data-ttu-id="51d70-136">表示する追加レポート</span><span class="sxs-lookup"><span data-stu-id="51d70-136">Additional reports to view</span></span>

<span data-ttu-id="51d70-137">この記事で説明されている ATP レポートに加えて、次の表に示すように、他にもいくつかのレポートを利用できます。</span><span class="sxs-lookup"><span data-stu-id="51d70-137">In addition to the ATP reports described in this article, several other reports are available, as described in the following table:</span></span>

|<span data-ttu-id="51d70-138">レポート (s)</span><span class="sxs-lookup"><span data-stu-id="51d70-138">Report(s)</span></span>  |<span data-ttu-id="51d70-139">詳細</span><span class="sxs-lookup"><span data-stu-id="51d70-139">Details</span></span>  |
|---------|---------|
|<span data-ttu-id="51d70-140">**ATP の安全なリンクの URL トレース**(これは、PowerShell を使用して生成したレポートです。)このレポートには、過去7日間 (7 日間) の ATP の安全なリンクアクションの結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="51d70-140">**ATP Safe Links URL trace** (This is a report you generate by using PowerShell.) This report shows the results of ATP Safe Links actions over the past seven (7) days.</span></span> |[<span data-ttu-id="51d70-141">取得-UrlTrace コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="51d70-141">Get-UrlTrace cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace?view=exchange-ps) |
|<span data-ttu-id="51d70-142">上位の送信者と受信者のレポート、スプーフィングメールレポート、スパム検出レポートなどの**電子メールセキュリティレポート**。</span><span class="sxs-lookup"><span data-stu-id="51d70-142">**Email security reports**, such as a Top Senders and Recipients report, a Spoof Mail report, and a Spam Detections report.</span></span> | [<span data-ttu-id="51d70-143">セキュリティ&amp; /コンプライアンスセンターで電子メールのセキュリティレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="51d70-143">View email security reports in the Security &amp; Compliance Center</span></span>](view-email-security-reports.md)        |
|<span data-ttu-id="51d70-144">**エクスプローラー**(脅威エクスプローラーとも呼ばれます)。これは[Office 365 Advanced Threat Protection プラン 2](office-365-ti.md)に含まれています。</span><span class="sxs-lookup"><span data-stu-id="51d70-144">**Explorer** (also referred to as Threat Explorer, this is included in [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md))</span></span>     | [<span data-ttu-id="51d70-145">セキュリティ&amp; /コンプライアンスセンターのエクスプローラーを使用する</span><span class="sxs-lookup"><span data-stu-id="51d70-145">Use Explorer in the Security &amp; Compliance Center</span></span>](use-explorer-in-security-and-compliance.md)        |
|<span data-ttu-id="51d70-146">**EOP および ATP の結果**(これは、PowerShell を使用して生成するカスタムレポートです)。</span><span class="sxs-lookup"><span data-stu-id="51d70-146">**EOP and ATP results** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="51d70-147">このレポートには、ドメイン、日付、イベントの種類、方向、アクション、メッセージ数などの情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="51d70-147">This report contains information, such as Domain, Date, Event Type, Direction, Action, and Message Count.</span></span>  | [<span data-ttu-id="51d70-148">Get-mailtrafficatpreport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="51d70-148">Get-MailTrafficATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport?view=exchange-ps) |
|<span data-ttu-id="51d70-149">**EOP および ATP の検出**(これは、PowerShell を使用して生成するカスタムレポートです)。</span><span class="sxs-lookup"><span data-stu-id="51d70-149">**EOP and ATP detections** (This is a custom report you generate by using PowerShell).</span></span> <span data-ttu-id="51d70-150">このレポートには、悪意のあるファイルまたは Url、フィッシングの試行、偽装、その他の電子メールやファイルの潜在的な脅威に関する詳細が記載されています。</span><span class="sxs-lookup"><span data-stu-id="51d70-150">This report contains details about malicious files or URLs, phishing attempts, impersonation, and other potential threats in email or files.</span></span>   | [<span data-ttu-id="51d70-151">Get-MailDetailATPReport コマンドレットリファレンス</span><span class="sxs-lookup"><span data-stu-id="51d70-151">Get-MailDetailATPReport cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport?view=exchange-ps)        |

  
## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a><span data-ttu-id="51d70-152">ATP レポートを表示するには、どのようなアクセス許可が必要ですか。</span><span class="sxs-lookup"><span data-stu-id="51d70-152">What permissions are needed to view the ATP reports?</span></span>

<span data-ttu-id="51d70-153">この記事に記載されているレポートを表示して使用するには、**セキュリティ&amp;コンプライアンスセンターと Exchange 管理センターの両方に対して適切な役割が割り当てられている必要があり**ます。</span><span class="sxs-lookup"><span data-stu-id="51d70-153">In order to view and use the reports described in this article, **you must have an appropriate role assigned for both the Security &amp; Compliance Center and the Exchange admin center**.</span></span>

- <span data-ttu-id="51d70-154">セキュリティ&amp; /コンプライアンスセンターでは、次の役割のいずれかが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d70-154">For the Security &amp; Compliance Center, you must have one of the following roles assigned:</span></span>
    - <span data-ttu-id="51d70-155">組織の管理</span><span class="sxs-lookup"><span data-stu-id="51d70-155">Organization Management</span></span>
    - <span data-ttu-id="51d70-156">セキュリティ管理者 (Azure Active Directory 管理センター[https://aad.portal.azure.com](https://aad.portal.azure.com)で割り当て可能)</span><span class="sxs-lookup"><span data-stu-id="51d70-156">Security Administrator (this can be assigned in the Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com)))</span></span>
    - <span data-ttu-id="51d70-157">セキュリティリーダ</span><span class="sxs-lookup"><span data-stu-id="51d70-157">Security Reader</span></span>

- <span data-ttu-id="51d70-158">Exchange Online の場合は、Exchange 管理センター ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) または PowerShell コマンドレット (「 [Exchange online Powershell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)」を参照) のいずれかで、次のいずれかの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="51d70-158">For Exchange Online, you must have one of the following roles assigned in either the Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) or with PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)):</span></span>
    - <span data-ttu-id="51d70-159">組織の管理</span><span class="sxs-lookup"><span data-stu-id="51d70-159">Organization Management</span></span>
    - <span data-ttu-id="51d70-160">表示限定の組織管理</span><span class="sxs-lookup"><span data-stu-id="51d70-160">View-only Organization Management</span></span>
    - <span data-ttu-id="51d70-161">"View-Only Recipients/表示専用受信者" 役割</span><span class="sxs-lookup"><span data-stu-id="51d70-161">View-Only Recipients role</span></span>
    - <span data-ttu-id="51d70-162">コンプライアンス管理</span><span class="sxs-lookup"><span data-stu-id="51d70-162">Compliance Management</span></span>

<span data-ttu-id="51d70-163">詳細については、以下のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="51d70-163">To learn more, see the following resources:</span></span>

- [<span data-ttu-id="51d70-164">Permissions in the Office 365 Security &amp; Compliance Center</span><span class="sxs-lookup"><span data-stu-id="51d70-164">Permissions in the Office 365 Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

- [<span data-ttu-id="51d70-165">Exchange Online の機能アクセス許可</span><span class="sxs-lookup"><span data-stu-id="51d70-165">Feature permissions in Exchange Online</span></span>](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)
   
## <a name="what-if-the-reports-arent-showing-data"></a><span data-ttu-id="51d70-166">レポートでデータが表示されない場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="51d70-166">What if the reports aren't showing data?</span></span>

<span data-ttu-id="51d70-167">ATP レポートにデータが表示されない場合は、ポリシーが正しく設定されていることを再確認してください。</span><span class="sxs-lookup"><span data-stu-id="51d70-167">If you are not seeing data in your ATP reports, double-check that your policies are set up correctly.</span></span> <span data-ttu-id="51d70-168">組織で atp の[安全なリンクポリシー](set-up-atp-safe-links-policies.md)と[atp の安全な添付ファイルのポリシー](set-up-atp-safe-attachments-policies.md)が定義されている必要があります。これは、atp 保護を適切に実行するためです。</span><span class="sxs-lookup"><span data-stu-id="51d70-168">Your organization must have [ATP Safe Links policies](set-up-atp-safe-links-policies.md) and [ATP Safe Attachments policies](set-up-atp-safe-attachments-policies.md) defined in order for ATP protection to be in place.</span></span> <span data-ttu-id="51d70-169">また、「[スパム対策およびマルウェア対策保護 (Office 365](anti-spam-and-anti-malware-protection.md))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="51d70-169">Also see [Anti-spam and anti-malware protection in Office 365](anti-spam-and-anti-malware-protection.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="51d70-170">関連項目</span><span class="sxs-lookup"><span data-stu-id="51d70-170">Related topics</span></span>

[<span data-ttu-id="51d70-171">Office 365 セキュリティ&amp; /コンプライアンスセンターのレポートと分析情報</span><span class="sxs-lookup"><span data-stu-id="51d70-171">Reports and insights in the Office 365 Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="51d70-172">セキュリティ&amp; /コンプライアンスセンターでレポートのスケジュールを作成する</span><span class="sxs-lookup"><span data-stu-id="51d70-172">Create a schedule for a report in the Security &amp; Compliance Center</span></span>](create-a-schedule-for-a-report.md)
  
[<span data-ttu-id="51d70-173">セキュリティ&amp; /コンプライアンスセンターでカスタムレポートを設定およびダウンロードする</span><span class="sxs-lookup"><span data-stu-id="51d70-173">Set up and download a custom report in the Security &amp; Compliance Center</span></span>](set-up-and-download-a-custom-report.md)
  

