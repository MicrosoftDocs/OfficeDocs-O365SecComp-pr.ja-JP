---
title: Office 365 の脅威の調査および応答機能を使用して組織を安全に保つ
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/20/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: Office 365 の脅威調査および応答機能を使用して、組織が侵入や脅威を検出し、脅威から迅速に脅威を軽減および回復する方法について説明します。
ms.openlocfilehash: baedfb1ff74117bd2ed36cdf4551f898d377a971
ms.sourcegitcommit: 4fd64e1811ae96633035cbc9cab1dbef3cbba34d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2019
ms.locfileid: "36484400"
---
# <a name="keep-your-organization-safe-with-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="c5ed3-103">Office 365 の脅威の調査および応答機能を使用して組織を安全に保つ</span><span class="sxs-lookup"><span data-stu-id="c5ed3-103">Keep your organization safe with Office 365 threat investigation and response capabilities</span></span>

## <a name="overview"></a><span data-ttu-id="c5ed3-104">概要</span><span class="sxs-lookup"><span data-stu-id="c5ed3-104">Overview</span></span>

<span data-ttu-id="c5ed3-105">どの Office 365 ユーザーが攻撃にさらされているか、または深刻な侵害になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-105">Do you know which of your Office 365 users are under attack, or worse - compromised?</span></span> <span data-ttu-id="c5ed3-106">ユーザーを対象とする攻撃を緩和して回復する方法を理解していますか。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-106">Do know how to mitigate and recover from attacks that are targeting your users?</span></span> <span data-ttu-id="c5ed3-107">Office 365 で既に利用可能なセキュリティ機能を使用して、これを正確に実行できることがわかりましたか?</span><span class="sxs-lookup"><span data-stu-id="c5ed3-107">Did you know you can do exactly this with security capabilities that are already available to you in Office 365?</span></span> 
  
<span data-ttu-id="c5ed3-108">Office [365 の脅威の調査と応答](office-365-ti.md)機能が Office 365 E5 サブスクリプション ( [Office 365 Advanced threat Protection](office-365-atp.md)プラン2の一部として) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-108">[Office 365 threat investigation and response](office-365-ti.md) capabilities are included in your Office 365 E5 subscription (as part of [Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2).</span></span> <span data-ttu-id="c5ed3-109">これらの機能により、Microsoft IT は、社会エンジニアリングインシデントの解決に要する平均時間を 80% に減らし、過去2四半期と比較して1か月あたりのケーススループットを 37% 増加させました。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-109">These capabilities have helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput by 37% per month compared to the previous 2 quarters!</span></span> 

<span data-ttu-id="c5ed3-110">最近、新しい機能を追加して、脅威を検出して回復する方法を改善しました。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-110">We've recently added new capabilities to help improve how you can detect and recover from threats!</span></span> <span data-ttu-id="c5ed3-111">この記事では、更新された脅威の調査と応答の機能をさらに効率的にする方法について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-111">Here's a quick walk through of how the updated Threat investigation and response capabilities can make you even more efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="c5ed3-112">侵入と脅威を検出する</span><span class="sxs-lookup"><span data-stu-id="c5ed3-112">Detect intrusions and threats</span></span>

<span data-ttu-id="c5ed3-113">[脅威エクスプローラー (またはリアルタイムの検出)](threat-explorer.md)(エクスプローラーとも呼ばれます) は、セキュリティ管理者とアナリストが、安全な送信者のような一見無害なユーザー構成によって、最も複雑なセキュリティ設定を回避できるため、企業内でアクティブになっている脅威を特定し、理解するのに役立つことがあります。ホワイトリスト</span><span class="sxs-lookup"><span data-stu-id="c5ed3-113">[Threat Explorer (or real-time detections)](threat-explorer.md) (also referred to as Explorer) helps security admins and analysts identify and understand threats that are active in your enterprise because even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe sender whitelists.</span></span> <span data-ttu-id="c5ed3-114">エクスプローラーは、ユーザーがマルウェアやフィッシングなどの脅威によって侵害されたかどうかを、Office 365 グローバルまたはセキュリティ管理者が迅速に判断するのに役に立ちます。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-114">Explorer helps Office 365 global or security admins quickly determine whether users have been compromised by threats such as malware or phish.</span></span> <span data-ttu-id="c5ed3-115">これにより、脅威や必要な応答に対して最も危険度の高いユーザーに優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-115">This helps prioritize which users are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="c5ed3-116">エクスプローラーを使用すると、管理者はユーザーとメールの間の関係を移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-116">Explorer also helps admins navigate the relationships between users and mail.</span></span> <span data-ttu-id="c5ed3-117">特定のメールが正しくないことがわかりますか。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-117">Know of a particular mail that was bad?</span></span> <span data-ttu-id="c5ed3-118">これを検索して、どのユーザーがメールを受信したかを確認してから、一連のイベントを実行し、それらのユーザーが実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-118">Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

<span data-ttu-id="c5ed3-119">これらの機能がまだ用意されていない場合は、[今すぐお試しください](https://aka.ms/tryo365threatintel3)。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-119">If you don't already have these capabilities, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="c5ed3-120">[Office 365 の脅威の調査と応答の詳細に](https://aka.ms/readmoreabouto365threatintel)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-120">And [learn more about Office 365 threat investigation and response](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![Office 365 の脅威エクスプローラーのスクリーンショット、マルウェアファミリによる色分け](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="c5ed3-122">脅威を迅速に軽減および復旧する</span><span class="sxs-lookup"><span data-stu-id="c5ed3-122">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="c5ed3-123">セキュリティ管理者は、テナント内で疑わしいまたは悪意のあるものを特定すると、その脅威に迅速に対応し、**インシデントフレームワーク**を使用して対応することができます。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-123">Once security admins have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**.</span></span> <span data-ttu-id="c5ed3-124">不要なメッセージを1回クリックしてグループ化し、ユーザーのメールボックスからすばやく電子メールメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-124">Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="c5ed3-125">**更新:** インシデントフレームワークから直接電子メールを削除 (ソフト削除またはハード削除) する機能を追加しました。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-125">**UPDATE:** We've added the ability to delete (soft or hard delete) emails directly from the Incident Framework.</span></span> <span data-ttu-id="c5ed3-126">以前の管理者は、ユーザーの迷惑メールフォルダーにのみメールを移動でき、ユーザーはそのアイテムを回復できます。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-126">Previously administrators could only move mails to a user's junk folder, where users could recover the item.</span></span> <span data-ttu-id="c5ed3-127">新たにリリースされた削除機能を使用すると、悪意のあるメールまたは不要なメールが完全に削除されていることを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-127">With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
  
<span data-ttu-id="c5ed3-128">これらの機能がまだ用意されていない場合は、[今すぐお試しください](https://aka.ms/tryo365threatintel3)。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-128">If you don't already have these capabilities, [try it now](https://aka.ms/tryo365threatintel3)!</span></span> <span data-ttu-id="c5ed3-129">[Office 365 の脅威の調査と応答の詳細に](https://aka.ms/readmoreabouto365threatintel)ついて説明します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-129">And [learn more about Office 365 threat investigation and response](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![インシデント修復の電子メールリストのスクリーンショット](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="c5ed3-131">Microsoft の脅威テレメトリを活用する</span><span class="sxs-lookup"><span data-stu-id="c5ed3-131">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="c5ed3-132">Office 365 の脅威の調査と応答機能には、Microsoft インテリジェントセキュリティグラフからのデータが使用されています。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-132">Office 365 threat investigation and response capabilities are powered with data from the Microsoft Intelligent Security Graph.</span></span> <span data-ttu-id="c5ed3-133">グラフは、10億の Windows デバイス、4500億月の Azure ログイン、および Office 365 の4000億の電子メールメッセージから最新の脅威信号を取得します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-133">The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365.</span></span> <span data-ttu-id="c5ed3-134">この unrivaled の脅威の信号は、管理者およびセキュリティアナリストが組織に影響を与える脅威を完全に把握するために不可欠な、顧客のテナントに対する広範な可視性を提供します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-134">This unrivaled threat signal is what gives the broad visibility into a customer tenant that is crucial for admins and security analysts to have a complete view of the threats impacting their organization.</span></span> 
  
## <a name="why-use-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="c5ed3-135">Office 365 の脅威の調査および応答機能を使用する理由</span><span class="sxs-lookup"><span data-stu-id="c5ed3-135">Why use Office 365 threat investigation and response capabilities?</span></span>

<span data-ttu-id="c5ed3-136">2017が $ 90B を超えた場合、Gartner の推定は cybersecurity に費やされました。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-136">Gartner estimates that in 2017 alone over $90B was spent on cybersecurity.</span></span> <span data-ttu-id="c5ed3-137">Sid Deshpande、Gartner の主な研究アナリストは、「the the the the the the the the the the the the the the the the the the the the the the the the the the the the the」と言っています。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-137">Sid Deshpande, principal research analyst at Gartner, is quoted as saying that "the industry's shift to detection and response …</span></span> <span data-ttu-id="c5ed3-138">検出/応答機能に関連付けられていない限り、futile が無効であることを示すメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-138">sends a clear message that prevention is futile unless it is tied into a detection and response capability."</span></span> <span data-ttu-id="c5ed3-139">脅威の調査と応答は、すべての企業のサービスポートフォリオの重要な部分であり、スタンドアロンサービスとして、または Office 365 E5 の一部として使用できます。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-139">Threat investigation and response is a critical part of every enterprise's portfolio of services, and can be consumed as standalone service or as part of Office 365 E5.</span></span>
  
## <a name="whats-next"></a><span data-ttu-id="c5ed3-140">[次へ]</span><span class="sxs-lookup"><span data-stu-id="c5ed3-140">What's Next</span></span>

- <span data-ttu-id="c5ed3-141">この記録されたセッションの Office 365 脅威の調査および応答機能の詳細については[、「office 365 で Cyberattacks を使用する](https://myignite.microsoft.com/videos/53723)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-141">Learn more about Office 365 threat investigation and response capabilities  in this recorded session: [Stay Ahead of the Cyberattacks with Office 365](https://myignite.microsoft.com/videos/53723)</span></span>
    
- <span data-ttu-id="c5ed3-142">[今すぐ office 365 の脅威の調査と応答機能を試す](https://aka.ms/tryo365threatintel3)か、または office E5 の試用版を開始しましょう。</span><span class="sxs-lookup"><span data-stu-id="c5ed3-142">[Try out Office 365 threat investigation and response capabilities now](https://aka.ms/tryo365threatintel3) or begin your Office E5 trial today!</span></span> 
    

