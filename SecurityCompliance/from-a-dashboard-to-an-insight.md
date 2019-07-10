---
title: ウォークスルー - ダッシュボードからインサイトへの移動
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/04/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 703c41df-b3e2-4e7e-9eeb-1a0b8d60fb56
ms.collection:
- M365-security-compliance
description: セキュリティ&amp; /コンプライアンスセンターの推奨されるアクションを使用して、ダッシュボードから洞察に移動する方法について説明します。
ms.openlocfilehash: e4ff0491e767fd4ffcf14a5ce8b5014447f80238
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599313"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="5c839-103">ウォークスルー - ダッシュボードからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="5c839-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="5c839-104">[Office 365 セキュリティ&amp;コンプライアンスセンターのレポートと洞察](reports-and-insights-in-security-and-compliance.md)を初めて使用する場合は、ダッシュボードから洞察や推奨されるアクションに簡単にアクセスする方法を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="5c839-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="5c839-105">これは、セキュリティ&amp;コンプライアンスセンターのいくつかのチュートリアルの1つです。</span><span class="sxs-lookup"><span data-stu-id="5c839-105">This is one of several walkthroughs for the Security &amp; Compliance Center.</span></span> <span data-ttu-id="5c839-106">その他のチュートリアルについては、「[関連項目](#related-topics)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c839-106">To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="5c839-107">チュートリアル: ダッシュボードから洞察へ</span><span class="sxs-lookup"><span data-stu-id="5c839-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="5c839-108">ダッシュボードからレポートへのフローについて詳しく説明し、分析情報とアクションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5c839-108">Let's walk through the flow from a dashboard to a report to an insight and action.</span></span> <span data-ttu-id="5c839-109">(これは、簡単な[スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)の例です。)</span><span class="sxs-lookup"><span data-stu-id="5c839-109">(This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="5c839-110">[ &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)のセキュリティダッシュボードから始めます。</span><span class="sxs-lookup"><span data-stu-id="5c839-110">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="5c839-111">([**脅威管理** \> ]**ダッシュボード**に移動します。)</span><span class="sxs-lookup"><span data-stu-id="5c839-111">(Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="5c839-112">![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>ダッシュボード] を選択します。](media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="5c839-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="5c839-113">「 **Insights** 」行には、疑わしいと考えられるいくつかのドメインを確認する必要があることを示す洞察があります。</span><span class="sxs-lookup"><span data-stu-id="5c839-113">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious.</span></span> <span data-ttu-id="5c839-114">([**インサイト**] 行で、[**ドメインペア**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="5c839-114">(In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="5c839-115">![Insights の行に、潜在的なスプーフィングの問題を紹介します。](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="5c839-115">![The Insights row mentions potential spoofing concerns](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="5c839-116">スプーフィングインテリジェンスに関連するアクティビティの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c839-116">We get a list of activities related to spoof intelligence.</span></span> <span data-ttu-id="5c839-117">これらのインスタンスは、電子メールメッセージが組織から送信されたように見えても、実際には別の組織から送信されたものです。</span><span class="sxs-lookup"><span data-stu-id="5c839-117">These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization.</span></span> <span data-ttu-id="5c839-118">目的は、スプーフィングされたメッセージが承認されているかどうかを判断することです。</span><span class="sxs-lookup"><span data-stu-id="5c839-118">The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="5c839-119">![スプーフィングインテリジェンスの分析情報](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="5c839-119">![Spoof intelligence insights](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="5c839-120">このリストでは、メッセージ数、スプーフィングが最後に検出された日付などによって情報を並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="5c839-120">In this list, we can sort the information by message count, date the spoofing was last detected, and more.</span></span> <span data-ttu-id="5c839-121">([**メッセージ数**]、[**最後の表示**] など) をクリックして、並べ替えの動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="5c839-121">(Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="5c839-122">リスト内の項目を選択すると、検出された類似の電子メールメッセージなどの追加情報が表示される詳細ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="5c839-122">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected.</span></span> <span data-ttu-id="5c839-123">(リスト内の項目をクリックし、情報と推奨事項を確認します)。</span><span class="sxs-lookup"><span data-stu-id="5c839-123">(Click an item in the list, and review the information and recommendations.)</span></span><br>![アイテムを選択すると詳細ウィンドウが開きます。](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="5c839-125">ウィンドウの上部に、組織の許可された送信者リストに送信者を追加するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="5c839-125">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list.</span></span> <span data-ttu-id="5c839-126">(この操作を実行するまで、[**送信者許可リストに追加**] を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="5c839-126">(Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this.</span></span> <span data-ttu-id="5c839-127">[スプーフィングインテリジェンスの詳細について説明](learn-about-spoof-intelligence.md)します)。</span><span class="sxs-lookup"><span data-stu-id="5c839-127">[Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="5c839-128">![送信者を承認できる](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="5c839-128">![You can authorize a sender](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="5c839-129">この方法では、ダッシュボードから洞察および推奨されるアクションに移行できます。</span><span class="sxs-lookup"><span data-stu-id="5c839-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5c839-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="5c839-130">Related topics</span></span>

[<span data-ttu-id="5c839-131">チュートリアル: 洞察から詳細レポートへ</span><span class="sxs-lookup"><span data-stu-id="5c839-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="5c839-132">チュートリアル: 詳細レポートから洞察を得る</span><span class="sxs-lookup"><span data-stu-id="5c839-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

