---
title: Exchange Online Protection でのレポート作成とメッセージ追跡
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: 12/18/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: f40253f2-50a1-426e-9979-be74ba74cb61
description: Microsoft Exchange Online ・保護 (EOP) は、全体的なステータスと、組織の健全性を決定する際に役立つ多くのさまざまなレポートを提供します。(メッセージのない着信などを目的の受信者)、特定のイベントのトラブルシューティングに役立つツールもありますし、コンプライアンス要件を支援するためにレポートを監査します。次の表は、レポートおよび EOP の管理者に使用可能なトラブルシューティングのツールについて説明します。
ms.openlocfilehash: 01a09b2b4b72161352af3793686c6cc888e44e29
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027144"
---
# <a name="reporting-and-message-trace-in-exchange-online-protection"></a><span data-ttu-id="d4f09-105">Exchange Online Protection でのレポート作成とメッセージ追跡</span><span class="sxs-lookup"><span data-stu-id="d4f09-105">Reporting and message trace in Exchange Online Protection</span></span>

<span data-ttu-id="d4f09-p102">Microsoft Exchange Online ・保護 (EOP) は、全体的なステータスと、組織の健全性を決定する際に役立つ多くのさまざまなレポートを提供します。(メッセージのない着信などを目的の受信者)、特定のイベントのトラブルシューティングに役立つツールもありますし、コンプライアンス要件を支援するためにレポートを監査します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-p102">Microsoft Exchange Online Protection (EOP) offers many different reports that can help you determine the overall status and health of your organization. There are also tools to help you troubleshoot specific events (such as a message not arriving to its intended recipients), and auditing reports to aid with compliance requirements.</span></span> 

## <a name="usage-reports"></a><span data-ttu-id="d4f09-108">利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-108">Usage reports</span></span>

<span data-ttu-id="d4f09-109">**Office 365 グループ活動**作成され使用されている Office 365 のグループの数に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-109">**Office 365 groups activity** View information about the number of Office 365 groups that are created and used.</span></span>  

<span data-ttu-id="d4f09-110">**電子メール活動**メッセージの送信、受信でき、組織全体で、特定のユーザーの数に関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-110">**Email activity** View information about the number of messages sent, received and read in your whole organization, and by specific users.</span></span>  

<span data-ttu-id="d4f09-p103">**電子メール アプリケーションの使用状況**使用されている電子メール アプリケーションについての情報を表示します。これには、各アプリケーションの接続の合計数と接続している Outlook のバージョンが含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4f09-p103">**Email app usage** View information about the email apps that are used. This include the total number of connections for each app, and the versions of Outlook that are connecting.</span></span>  

<span data-ttu-id="d4f09-113">**メールボックスの使用状況**記憶域の使用に関する情報、クォータの使用量、アイテムの数、およびメールボックスの最後のアクティビティ (送信または読み取りアクティビティ) を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-113">**Mailbox usage** View information about storage used, quota consumption, item count, and last activity (send or read activity) for mailboxes.</span></span>

<span data-ttu-id="d4f09-114">詳細については次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f09-114">See the following resources for more information:</span></span>

- [<span data-ttu-id="d4f09-115">グループ管理センター - Office 365 の office 365 のレポートします。</span><span class="sxs-lookup"><span data-stu-id="d4f09-115">Office 365 Reports in the admin center - Office 365 groups</span></span>](https://go.microsoft.com/fwlink/p/?linkid=861610) 
- [<span data-ttu-id="d4f09-116">Office 365 管理センター - 電子メールの利用状況レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-116">Office 365 Reports in the Admin Center - Email activity</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859706) 
- [<span data-ttu-id="d4f09-117">Office 365 管理センター - 電子メール アプリケーションの使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-117">Office 365 Reports in the Admin Center - Email apps usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859707)
- [<span data-ttu-id="d4f09-118">Office 365 管理センター - メールボックスの使用状況レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-118">Office 365 Reports in the Admin Center - Mailbox usage</span></span>](https://go.microsoft.com/fwlink/p/?linkid=859708)

## <a name="security-amp-compliance-reports-in-the-office-365-admin-center"></a><span data-ttu-id="d4f09-119">セキュリティ&amp;Office 365 の管理センターでのコンプライアンス ・ レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-119">Security &amp; compliance reports in the Office 365 admin center</span></span>

<span data-ttu-id="d4f09-120">これらの拡張されたレポートは EOP 管理者向けの対話型レポート エクスペリエンスを提供します。これには概要情報、および詳細についてドリルダウンする機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d4f09-120">These enhanced reports provide an interactive reporting experience for EOP admins, which includes summary information, and the ability to drill down for more details.</span></span>  

<span data-ttu-id="d4f09-121">**(ATP) の脅威保護の詳細**安全なリンクと分析ツールの一部である安全な添付ファイルについての情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-121">**Advanced Threat Protection (ATP)** View information about safe links and safe attachments that are part of ATP.</span></span>  

<span data-ttu-id="d4f09-122">**EOP**マルウェアの検出、スプーフィングされたメール、迷惑メールの検出、および組織との間のメール フローに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-122">**EOP** View information about malware detections, spoofed mail, spam detections, and mail flow to and from your organization.</span></span>  

[<span data-ttu-id="d4f09-123">脅威の高度な保護と Exchange のオンライン保護に関するレポートを表示</span><span class="sxs-lookup"><span data-stu-id="d4f09-123">View reports for Advanced Threat Protection and Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/p/?linkid=852409) 

##<a name="custom-reports-using-microsoft-graph"></a><span data-ttu-id="d4f09-124">Microsoft Graph を使用してカスタム レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-124">Custom reports using Microsoft Graph</span></span>

<span data-ttu-id="d4f09-125">[Microsoft Graph で使用状況レポートを Office 365](https://go.microsoft.com/fwlink/p/?linkid=865135)のサブトピックで利用できる Office 365 の管理ページのグラフを参照してください Microsoft を使用してレポートをプログラムで作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-125">Programmatically create reports that are available in the Office 365 admin center by using Microsoft Graph  See the subtopics of [Working with Office 365 usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=865135)</span></span> 

##<a name="custom-reports-using-reporting-web-services"></a><span data-ttu-id="d4f09-126">レポート Web サービスを使用するカスタム レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-126">Custom reports using reporting web services</span></span>

<span data-ttu-id="d4f09-127">プログラムを使用して、利用可能な Exchange オンライン保護 PowerShell コマンドレットを残りの部分と ODATA2 クエリのフィルター処理を使用して、レポートからレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-127">Programmatically create reports from the available Exchange Online Protection PowerShell reporting cmdlets by using REST/ODATA2 query filtering.</span></span>

<span data-ttu-id="d4f09-128">[Office 365 のレポート Web サービス](https://go.microsoft.com/fwlink/p/?LinkId=279926)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f09-128">See [Office 365 Reporting Web Services](https://go.microsoft.com/fwlink/p/?LinkId=279926)</span></span> 

##<a name="message-trace"></a><span data-ttu-id="d4f09-129">メッセージの追跡</span><span class="sxs-lookup"><span data-stu-id="d4f09-129">Message trace</span></span>

<span data-ttu-id="d4f09-p104">EOP を通過する電子メール メッセージを追跡します。電子メール メッセージがサービスで受信、拒否、延期、配信されたか確認できます。メッセージが最終的な状態になる前に、メッセージに行われた処理も表示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-p104">Follows email messages as they travel through EOP. You can determine if an email message was received, rejected, deferred, or delivered by the service. It also shows what actions were taken on the message before it reached its final status.</span></span>  

<span data-ttu-id="d4f09-133">この情報を使用して、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。</span><span class="sxs-lookup"><span data-stu-id="d4f09-133">You can use this information to efficiently answer your user's questions, troubleshoot mail flow issues, validate policy changes, and alleviates the need to contact technical support for assistance.</span></span>  

<span data-ttu-id="d4f09-134">[電子メール メッセージのトレース](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f09-134">See [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)</span></span> 

## <a name="audit-logging"></a><span data-ttu-id="d4f09-135">監査ログ</span><span class="sxs-lookup"><span data-stu-id="d4f09-135">Audit logging</span></span>

<span data-ttu-id="d4f09-p105">組織管理者が加えた変更を追跡します。これらのレポートは、構成に関する問題のトラブルシューティングを行うか、セキュリティやコンプライアンス関連の問題の原因を特定するのに役立ちます。 [EOP の監査レポート](auditing-reports-in-eop.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d4f09-p105">Tracks specific changes made by admins to your organization. These reports can help you troubleshoot configuration issues or find the cause of security or compliance-related problems.  see [Auditing reports in EOP](auditing-reports-in-eop.md)</span></span> 


## <a name="reporting-and-message-trace-data-availability-and-latency"></a><span data-ttu-id="d4f09-139">レポート機能とメッセージ トレース データの使用可能性と遅延</span><span class="sxs-lookup"><span data-stu-id="d4f09-139">Reporting and message trace data availability and latency</span></span>

<span data-ttu-id="d4f09-140">EOP のレポート機能とメッセージ トレース データが使用可能なタイミングと期間を次の表に示します。</span><span class="sxs-lookup"><span data-stu-id="d4f09-140">The following table describes when EOP reporting and message trace data is available and for how long.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="d4f09-141">**レポートの種類**</span><span class="sxs-lookup"><span data-stu-id="d4f09-141">**Report type**</span></span> <br/> |<span data-ttu-id="d4f09-142">**データ使用可能期間 (遡及期間)**</span><span class="sxs-lookup"><span data-stu-id="d4f09-142">**Data available for (look back period)**</span></span> <br/> |<span data-ttu-id="d4f09-143">**遅延時間**</span><span class="sxs-lookup"><span data-stu-id="d4f09-143">**Latency**</span></span> <br/> |
|<span data-ttu-id="d4f09-144">メール保護概要レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-144">Mail protection summary reports</span></span>  <br/> |<span data-ttu-id="d4f09-145">90 日</span><span class="sxs-lookup"><span data-stu-id="d4f09-145">90 days</span></span>  <br/> |<span data-ttu-id="d4f09-p106">メッセージ データの集計は 24 ～ 48 時間以内にほぼ完了します。最大 5 日間のマイナーな増分集計変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4f09-p106">Message data aggregation is mostly complete within 24-48 hours. Some minor incremental aggregated changes may occur for up to 5 days.</span></span>  <br/> |
|<span data-ttu-id="d4f09-148">メール保護詳細レポート</span><span class="sxs-lookup"><span data-stu-id="d4f09-148">Mail protection detail reports</span></span>  <br/> |<span data-ttu-id="d4f09-149">90 日</span><span class="sxs-lookup"><span data-stu-id="d4f09-149">90 days</span></span>  <br/> |<span data-ttu-id="d4f09-p107">生成後 7 日未満の詳細データに関しては、24 時間以内に表示されるはずですが、48 時間まで完成しない場合があります。最大 5 日分のマイナーな増分変更が実施される場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4f09-p107">For detail data that's less than 7 days old, data should appear within 24 hours but may not be complete until 48 hours. Some minor incremental changes may occur for up to 5 days.</span></span>  <br/> <span data-ttu-id="d4f09-152">7 日以上前のメッセージに関する詳細レポートを表示するには、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4f09-152">To view detail reports for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
|<span data-ttu-id="d4f09-153">メッセージ追跡データ</span><span class="sxs-lookup"><span data-stu-id="d4f09-153">Message trace data</span></span>  <br/> |<span data-ttu-id="d4f09-154">90 日</span><span class="sxs-lookup"><span data-stu-id="d4f09-154">90 days</span></span>  <br/> |<span data-ttu-id="d4f09-155">生成後 7 日未満のメッセージのメッセージ追跡を実施した場合は、メッセージが 5 ～ 30 分で表示されるはずです。</span><span class="sxs-lookup"><span data-stu-id="d4f09-155">When you run a message trace for messages that are less than 7 days old, the messages should appear within 5-30 minutes.</span></span>  <br/> <span data-ttu-id="d4f09-156">7 日以上前のメッセージのメッセージ追跡を実施した場合は、結果が出るまでに最大で数時間かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="d4f09-156">When you run a message trace for messages that are greater than 7 days old, results may take up to a few hours.</span></span>  <br/> |
   
> [!NOTE]
> <span data-ttu-id="d4f09-157">データの可用性と待機時間は、Office 365 管理者センターやリモート PowerShell を使用して要求されたかどうか同じです。</span><span class="sxs-lookup"><span data-stu-id="d4f09-157">Data availability and latency is the same whether requested via the Office 365 admin center or remote PowerShell.</span></span> 
  

