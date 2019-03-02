---
title: チュートリアル - ダッシュボードからインサイトへの移動
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/4/2018
ms.audience: ITPro
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
ms.openlocfilehash: 732c78b35a60c1686bc382931688dec08080f8c2
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357538"
---
# <a name="walkthrough---from-a-dashboard-to-an-insight"></a><span data-ttu-id="93dcb-103">チュートリアル - ダッシュボードからインサイトへの移動</span><span class="sxs-lookup"><span data-stu-id="93dcb-103">Walkthrough - From a dashboard to an insight</span></span>

<span data-ttu-id="93dcb-104">[Office 365 セキュリティ&amp;コンプライアンスセンターのレポートと洞察](reports-and-insights-in-security-and-compliance.md)を初めて使用する場合は、ダッシュボードから洞察や推奨されるアクションに簡単にアクセスする方法を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="93dcb-104">If you're new to [reports and insights in the Office 365 Security &amp; Compliance Center](reports-and-insights-in-security-and-compliance.md), it might help to see how you can easily navigate from a dashboard to an insight and recommended actions.</span></span> 
  
<span data-ttu-id="93dcb-p101">これは、セキュリティ&amp;コンプライアンスセンターのいくつかのチュートリアルの1つです。その他のチュートリアルについては、「[関連項目](#related-topics)」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="93dcb-p101">This is one of several walkthroughs for the Security &amp; Compliance Center. To see additional walkthroughs, see the [Related topics](#related-topics) section.</span></span> 
  
## <a name="walkthrough-from-a-dashboard-to-an-insight"></a><span data-ttu-id="93dcb-107">チュートリアル: ダッシュボードから洞察へ</span><span class="sxs-lookup"><span data-stu-id="93dcb-107">Walkthrough: From a dashboard to an insight</span></span>

<span data-ttu-id="93dcb-p102">ダッシュボードからレポートへのフローについて詳しく説明し、分析情報とアクションについて説明します。(これは、簡単な[スプーフィングインテリジェンス](learn-about-spoof-intelligence.md)の例です。)</span><span class="sxs-lookup"><span data-stu-id="93dcb-p102">Let's walk through the flow from a dashboard to a report to an insight and action. (This is a brief [spoof intelligence](learn-about-spoof-intelligence.md) example.)</span></span> 
  
1. <span data-ttu-id="93dcb-p103">[ &amp;セキュリティ/コンプライアンスセンター](https://protection.office.com)のセキュリティダッシュボードから始めます。([**脅威管理** \> ]**ダッシュボード**に移動します。)</span><span class="sxs-lookup"><span data-stu-id="93dcb-p103">We begin with the Security dashboard in the [Security &amp; Compliance Center](https://protection.office.com). (Go to **Threat management** \> **Dashboard**.)</span></span><br><span data-ttu-id="93dcb-112">![セキュリティ&amp; /コンプライアンスセンターで、[脅威管理\>ダッシュボード] を選択します。](media/05a38660-eb13-4960-a266-11809c453d95.png)</span><span class="sxs-lookup"><span data-stu-id="93dcb-112">![In the Security &amp; Compliance Center, choose Threat management \> Dashboard](media/05a38660-eb13-4960-a266-11809c453d95.png)</span></span><br>
  
2. <span data-ttu-id="93dcb-p104">「 **Insights** 」行には、疑わしいと考えられるいくつかのドメインを確認する必要があることを示す洞察があります。([**インサイト**] 行で、[**ドメインペア**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="93dcb-p104">In the **Insights** row, we notice an insight indicating we need to review some domains that might be suspicious. (In the **Insights** row, click **Domain pairs**.)</span></span><br><span data-ttu-id="93dcb-115">![Insights の行に、潜在的なスプーフィングの問題を紹介します。](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span><span class="sxs-lookup"><span data-stu-id="93dcb-115">![The Insights row mentions potential spoofing concerns](media/dd1d0cb3-3201-45d7-b41d-18a0944fe85d.png)</span></span><br>
  
3. <span data-ttu-id="93dcb-p105">スプーフィングインテリジェンスに関連するアクティビティの一覧が表示されます。これらのインスタンスは、電子メールメッセージが組織から送信されたように見えても、実際には別の組織から送信されたものです。目的は、スプーフィングされたメッセージが承認されているかどうかを判断することです。</span><span class="sxs-lookup"><span data-stu-id="93dcb-p105">We get a list of activities related to spoof intelligence. These are instances where email messages were sent that look like they came from our organization but were, in fact, sent from another organization. The goal is to determine whether the spoofed messages are authorized or not.</span></span><br><span data-ttu-id="93dcb-119">![スプーフィングインテリジェンスの分析情報](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span><span class="sxs-lookup"><span data-stu-id="93dcb-119">![Spoof intelligence insights](media/a2e2b4fd-0c1e-499f-8401-cf3089da82fa.png)</span></span><br><span data-ttu-id="93dcb-p106">このリストでは、メッセージ数、スプーフィングが最後に検出された日付などによって情報を並べ替えることができます。([**メッセージ数**]、[**最後の表示**] など) をクリックして、並べ替えの動作を確認します。</span><span class="sxs-lookup"><span data-stu-id="93dcb-p106">In this list, we can sort the information by message count, date the spoofing was last detected, and more. (Click column headings, such as **Message count** or **Last seen** to see how sorting works.)</span></span> 
    
4. <span data-ttu-id="93dcb-p107">リスト内の項目を選択すると、検出された類似の電子メールメッセージなどの追加情報が表示される詳細ウィンドウが開きます。(リスト内の項目をクリックし、情報と推奨事項を確認します)。</span><span class="sxs-lookup"><span data-stu-id="93dcb-p107">Selecting an item in the list opens a details pane where we can see additional information, including similar email messages that were detected. (Click an item in the list, and review the information and recommendations.)</span></span><br>![アイテムを選択すると詳細ウィンドウが開きます。](media/7ad1faa5-6ca2-474e-a609-eb275e0a8e59.png)<br>
  
5. <span data-ttu-id="93dcb-p108">ウィンドウの上部に、組織の許可された送信者リストに送信者を追加するオプションがあります。(この操作を実行するまで、[**送信者許可リストに追加**] を選択しないでください。[スプーフィングインテリジェンスの詳細について説明](learn-about-spoof-intelligence.md)します)。</span><span class="sxs-lookup"><span data-stu-id="93dcb-p108">Notice that at the top of the pane, we have the option to add the sender to our organization's allowed senders list. (Do not select **Add to 'AllowedtoSpoof' sender allow list** until you are sure you want to do this. [Learn more about spoof intelligence](learn-about-spoof-intelligence.md).)</span></span><br><span data-ttu-id="93dcb-128">![送信者を承認できる](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span><span class="sxs-lookup"><span data-stu-id="93dcb-128">![You can authorize a sender](media/caf0c20a-6047-486d-8060-5a229a3de49f.png)</span></span>
  
<span data-ttu-id="93dcb-129">この方法では、ダッシュボードから洞察および推奨されるアクションに移行できます。</span><span class="sxs-lookup"><span data-stu-id="93dcb-129">In this way, we can move from a dashboard to insights and recommended actions.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="93dcb-130">関連項目</span><span class="sxs-lookup"><span data-stu-id="93dcb-130">Related topics</span></span>

[<span data-ttu-id="93dcb-131">チュートリアル: 洞察から詳細レポートへ</span><span class="sxs-lookup"><span data-stu-id="93dcb-131">Walkthrough: From an insight to a detailed report</span></span>](from-an-insight-to-a-detailed-report.md)
  
[<span data-ttu-id="93dcb-132">チュートリアル: 詳細レポートから洞察を得る</span><span class="sxs-lookup"><span data-stu-id="93dcb-132">Walkthrough: From a detailed report to an insight</span></span>](from-a-detailed-report-to-an-insight.md)
  

