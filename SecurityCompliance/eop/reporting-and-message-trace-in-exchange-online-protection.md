---
title: Exchange Online Protection でのレポート作成とメッセージ追跡
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online Protection (EOP) には、組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートが用意されています。 特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。 次の表には、EOP 管理者が利用できるレポートおよびトラブルシューティングのツールを示します。
ms.openlocfilehash: 0dcacec586408bf98ad4c67c11ae3bde3a8e9315
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154619"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="d238d-105">Exchange Online Protection でのレポート作成とメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="d238d-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="d238d-106">Microsoft Exchange Online Protection (EOP) には、組織の全体的な状態と正常性を判断するのに役立つさまざまなレポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d238d-106">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization.</span></span> <span data-ttu-id="d238d-107">特定イベント (目的の受信者に届かなかったメッセージなど) のトラブルシューティングを支援するツール、さらに法令遵守の要件のための監査レポートもあります。</span><span class="sxs-lookup"><span data-stu-id="d238d-107">There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span> 

## <a name="usage-reports"></a><span data-ttu-id="d238d-108">利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="d238d-108">Usage reports</span></span>

<span data-ttu-id="d238d-109">**Office 365 グループアクティビティ**作成されて使用される Office 365 グループの数に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-109">**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="d238d-110">**電子メールアクティビティ**組織全体で送受信されたメッセージの数と、特定のユーザーについての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-110">**Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="d238d-111">**メールアプリの使用状況**使用されている電子メールアプリに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-111">**Email app usage** View information about the email apps that are used.</span></span> <span data-ttu-id="d238d-112">これには、各アプリの合計接続数、および接続している Outlook のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d238d-112">This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="d238d-113">**メールボックスの使用状況**メールボックスの使用済み記憶域、クォータ消費、アイテム数、最後のアクティビティ (送信または読み取りアクティビティ) に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-113">**Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="d238d-114">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d238d-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="d238d-115">管理センターの office 365 レポート-Office 365 グループ</span><span class="sxs-lookup"><span data-stu-id="d238d-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [<span data-ttu-id="d238d-116">管理センターの Office 365 レポート-電子メールアクティビティ</span><span class="sxs-lookup"><span data-stu-id="d238d-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [<span data-ttu-id="d238d-117">管理センターの Office 365 レポート-電子メールアプリの使用状況</span><span class="sxs-lookup"><span data-stu-id="d238d-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [<span data-ttu-id="d238d-118">管理センターでの Office 365 レポート-メールボックスの使用状況</span><span class="sxs-lookup"><span data-stu-id="d238d-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-microsoft-365-admin-center"></a><span data-ttu-id="d238d-119">Microsoft &amp; 365 管理センターのセキュリティコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="d238d-119">Security &amp; compliance reports in the Microsoft 365 admin center</span></span>

<span data-ttu-id="d238d-120">これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d238d-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="d238d-121">**Advanced Threat Protection (ATP)** ATP の一部である安全なリンクと安全な添付ファイルに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-121">**Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="d238d-122">**EOP**マルウェアの検出、スプーフィングされたメール、スパム検出、組織との間のメールフローに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-122">**EOP** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="d238d-123">Advanced Threat Protection および Exchange Online Protection のレポートを表示する</span><span class="sxs-lookup"><span data-stu-id="d238d-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="d238d-124">Microsoft Graph を使用するカスタムレポート</span><span class="sxs-lookup"><span data-stu-id="d238d-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="d238d-125">Microsoft Graph を使用して Microsoft 365 管理センターで利用可能なレポートをプログラムで作成する microsoft [graph の Office 365 使用状況レポート](https://go.microsoft.com/fwlink/p/?linkid=865135)の使用に関するサブトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d238d-125">Programmatically create reports that are available in the Microsoft 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span> 

##<a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="d238d-126">レポート Web サービスを使用するカスタム レポート</span><span class="sxs-lookup"><span data-stu-id="d238d-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="d238d-127">REST/ODATA2 クエリフィルターを使用して、利用可能な Exchange Online Protection PowerShell レポートコマンドレットからプログラムでレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d238d-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="d238d-128">[Office 365 Reporting Web サービス](https://go.microsoft.com/fwlink/p/?LinkId=279926)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d238d-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span> 

##<a name="message-trace"></a><span data-ttu-id="d238d-129">メッセージの追跡</span><span class="sxs-lookup"><span data-stu-id="d238d-129">Message trace</span></span>

<span data-ttu-id="d238d-p104">EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="d238d-133">この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。</span><span class="sxs-lookup"><span data-stu-id="d238d-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="d238d-134">「 [Trace An Email Message」を](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d238d-134">See [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span></span> 

## <a name="audit-logging"></a><span data-ttu-id="d238d-135">監査ログ</span><span class="sxs-lookup"><span data-stu-id="d238d-135">Audit logging</span></span>

<span data-ttu-id="d238d-136">組織の管理者によって行われた特定の変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="d238d-136">Tracks specific changes made by admins to your organization.</span></span> <span data-ttu-id="d238d-137">これらのレポートの構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="d238d-137">These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.</span></span>  <span data-ttu-id="d238d-138">[EOP の監査レポートを](auditing-reports-in-eop.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d238d-138">see [Auditing reports in EOP](auditing-reports-in-eop.md)</span></span> 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="d238d-139">レポート機能とメッセージ トレース データの使用可能性と遅延</span><span class="sxs-lookup"><span data-stu-id="d238d-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="d238d-140">EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d238d-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d238d-141">**レポートの種類**</span><span class="sxs-lookup"><span data-stu-id="d238d-141">**Report type**</span></span> <br/> |<span data-ttu-id="d238d-142">**データ使用可能期間 (遡及期間)**</span><span class="sxs-lookup"><span data-stu-id="d238d-142">**Data available for (look back period)**</span></span> <br/> |<span data-ttu-id="d238d-143">**待機時間**</span><span class="sxs-lookup"><span data-stu-id="d238d-143">**Latency**</span></span> <br/> |
|<span data-ttu-id="d238d-144">メール保護概要レポート</span><span class="sxs-lookup"><span data-stu-id="d238d-144">Mail protection summary reports</span></span>  <br/> |<span data-ttu-id="d238d-145">90 日間</span><span class="sxs-lookup"><span data-stu-id="d238d-145">90 days</span></span>  <br/> |<span data-ttu-id="d238d-p106">メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d238d-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>  <br/> |
|<span data-ttu-id="d238d-148">メール保護詳細レポート</span><span class="sxs-lookup"><span data-stu-id="d238d-148">Mail protection detail reports</span></span>  <br/> |<span data-ttu-id="d238d-149">90 日</span><span class="sxs-lookup"><span data-stu-id="d238d-149">90 days</span></span>  <br/> |<span data-ttu-id="d238d-p107">生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d238d-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span>  <br/> <span data-ttu-id="d238d-152">7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d238d-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
|<span data-ttu-id="d238d-153">メッセージ追跡データ</span><span class="sxs-lookup"><span data-stu-id="d238d-153">Message trace data</span></span>  <br/> |<span data-ttu-id="d238d-154">90 日</span><span class="sxs-lookup"><span data-stu-id="d238d-154">90 days</span></span>  <br/> |<span data-ttu-id="d238d-155">生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d238d-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span>  <br/> <span data-ttu-id="d238d-156">7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d238d-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d238d-157">データの可用性と待機時間は、Microsoft 365 管理センターまたはリモート PowerShell を介して要求された場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="d238d-157">Data availability and latency is the same whether requested via the Microsoft 365 admin center or remote PowerShell.</span></span> 
  

