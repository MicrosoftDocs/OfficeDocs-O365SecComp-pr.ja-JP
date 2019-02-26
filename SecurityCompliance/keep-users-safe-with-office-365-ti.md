---
title: Office 365 脅威インテリジェンスを使用して Office 365 ユーザーの安全を守る
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
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection:
- M365-security-compliance
description: Office 365 の脅威インテリジェンスが組織による侵入および脅威の検出を支援し、脅威から迅速に軽減および回復できるようにする方法について説明します。
ms.openlocfilehash: 40b39cc7f388152bd95000e2653ef94b970a6fa3
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241959"
---
# <a name="keep-your-office-365-users-safe-with-office-365-threat-intelligence"></a><span data-ttu-id="a60a8-103">Office 365 脅威インテリジェンスを使用して Office 365 ユーザーの安全を守る</span><span class="sxs-lookup"><span data-stu-id="a60a8-103">Keep your Office 365 users safe with Office 365 Threat Intelligence</span></span>

## <a name="overview"></a><span data-ttu-id="a60a8-104">概要</span><span class="sxs-lookup"><span data-stu-id="a60a8-104">Overview</span></span>

<span data-ttu-id="a60a8-p101">どの Office 365 ユーザーが攻撃にさらされているか、または深刻な侵害になっているかどうかを確認します。ユーザーを対象とする攻撃を緩和して回復する方法を理解していますか。Office 365 で既に利用可能なセキュリティ機能を使用して、これを正確に実行できることがわかりましたか?</span><span class="sxs-lookup"><span data-stu-id="a60a8-p101">Do you know which of your Office 365 users are under attack, or worse - compromised? Do know how to mitigate and recover from attacks that are targeting your users? Did you know you can do exactly this with security capabilities that are already available to you in Office 365?</span></span> 
  
<span data-ttu-id="a60a8-p102">[office 365 脅威インテリジェンス](office-365-ti.md)は、office 365 E5 サブスクリプションに含まれている機能のセットです。Office 365 の脅威インテリジェンスにより、Microsoft IT は、過去2四半期と比較して、ソーシャルエンジニアリングインシデントの解決にかかる平均時間を 80% 削減し、月あたりのスループットを 37% 増加させました。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p102">[Office 365 Threat Intelligence](office-365-ti.md) is a suite of capabilities included in your Office 365 E5 subscription. Office 365 Threat Intelligence has helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput by 37% per month compared to the previous 2 quarters!</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a60a8-p103">2019年2月から、次の数か月間に展開されています。 office 365 の脅威インテリジェンスは、追加の脅威保護機能を備えた office 365 Advanced threat protection プラン2になりつつあります。詳細については、「 [office 365 advanced threat protection プランと価格設定](https://products.office.com/exchange/advance-threat-protection)」および「 [office 365 advanced threat protection サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
<span data-ttu-id="a60a8-p104">最近、新しい機能を追加して、脅威を検出して回復する方法を改善しました。ここでは、更新された脅威インテリジェンスサービスをより効率的にする方法について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p104">We've recently added new capabilities to help improve how you can detect and recover from threats! Here's a quick walk through of how the updated Threat Intelligence service can make you even more efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="a60a8-114">侵入と脅威を検出する</span><span class="sxs-lookup"><span data-stu-id="a60a8-114">Detect intrusions and threats</span></span>

<span data-ttu-id="a60a8-p105">[エクスプローラー](use-explorer-in-security-and-compliance.md)(脅威エクスプローラーとも呼ばれます) は、セキュリティ管理者とアナリストが、安全なように見える一見したユーザー構成によって、最も複雑なセキュリティ設定を回避できるため、企業内でアクティブになっている脅威を特定して理解するのに役立つ。送信者のホワイトリスト。エクスプローラーは、ユーザーがマルウェアやフィッシングなどの脅威によって侵害されたかどうかを、Office 365 グローバルまたはセキュリティ管理者が迅速に判断するのに役に立ちます。これにより、脅威や必要な応答に対して最も危険度の高いユーザーに優先順位を付けることができます。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p105">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) helps security admins and analysts identify and understand threats that are active in your enterprise because even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe sender whitelists. Explorer helps Office 365 global or security admins quickly determine whether users have been compromised by threats such as malware or phish. This helps prioritize which users are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="a60a8-p106">エクスプローラーを使用すると、管理者はユーザーとメールの間の関係を移動することもできます。特定のメールが正しくないことがわかりますか。これを検索して、どのユーザーがメールを受信したかを確認してから、一連のイベントを実行し、それらのユーザーが実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p106">Explorer also helps admins navigate the relationships between users and mail. Know of a particular mail that was bad? Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

<span data-ttu-id="a60a8-p107">脅威インテリジェンスをまだ持っていない場合は、[今すぐお試しください](https://aka.ms/tryo365threatintel3)。[Office 365 脅威インテリジェンスの詳細について説明](https://aka.ms/readmoreabouto365threatintel)します。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p107">If you don't already have Threat Intelligence, [try it now](https://aka.ms/tryo365threatintel3)! And [learn more about Office 365 Threat Intelligence](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![Office 365 の脅威エクスプローラーのスクリーンショット、マルウェアファミリによる色分け](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="a60a8-124">脅威を迅速に軽減および復旧する</span><span class="sxs-lookup"><span data-stu-id="a60a8-124">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="a60a8-p108">セキュリティ管理者は、テナント内で疑わしいまたは悪意のあるものを特定すると、その脅威に迅速に対応し、**インシデントフレームワーク**を使用して対応することができます。不要なメッセージを1回クリックしてグループ化し、ユーザーのメールボックスからすばやく電子メールメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p108">Once security admins have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**. Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="a60a8-p109">**更新:** 最近、インシデントフレームワークから電子メールを削除 (ソフトまたはハード削除) する機能が追加されました。以前の管理者は、ユーザーの迷惑メールフォルダーにのみメールを移動でき、ユーザーはそのアイテムを回復できます。新たにリリースされた削除機能を使用すると、悪意のあるメールまたは不要なメールが完全に削除されていることを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p109">**UPDATE:** We've recently added the ability to delete (soft or hard delete) emails directly from the Incident Framework. Previously administrators could only move mails to a user's junk folder, where users could recover the item. With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
  
<span data-ttu-id="a60a8-p110">脅威インテリジェンスをまだ持っていない場合は、[今すぐお試しください](https://aka.ms/tryo365threatintel3)。[Office 365 脅威インテリジェンスの詳細について説明](https://aka.ms/readmoreabouto365threatintel)します。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p110">If you don't already have Threat Intelligence, [try it now](https://aka.ms/tryo365threatintel3)! And [learn more about Office 365 Threat Intelligence](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![インシデント修復の電子メールリストのスクリーンショット](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="a60a8-133">Microsoft の脅威テレメトリを活用する</span><span class="sxs-lookup"><span data-stu-id="a60a8-133">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="a60a8-p111">Office 365 の脅威インテリジェンスは、Microsoft のインテリジェントセキュリティグラフからのデータによって保護されています。グラフは、10億の Windows デバイス、4500億月の Azure ログイン、および Office 365 の4000億の電子メールメッセージから最新の脅威信号を取得します。この unrivaled の脅威の信号は、管理者およびセキュリティアナリストが組織に影響を与える脅威を完全に把握するために不可欠な、顧客のテナントに対する広範な可視性を提供します。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p111">Office 365 Threat Intelligence is powered with data from the Microsoft Intelligent Security Graph. The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365. This unrivaled threat signal is what gives the broad visibility into a customer tenant that is crucial for admins and security analysts to have a complete view of the threats impacting their organization.</span></span> 
  
## <a name="more-to-come"></a><span data-ttu-id="a60a8-137">詳細</span><span class="sxs-lookup"><span data-stu-id="a60a8-137">More to come</span></span>

<span data-ttu-id="a60a8-p112">これらは、Office 365 の脅威インテリジェンスが企業をセキュリティで保護するためにどのように役立つかの例にすぎません。今後数週間で、次のような製品に大幅な機能強化が加えられています。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p112">These are just some examples of how Office 365 Threat Intelligence helps you secure your enterprise! In the coming weeks we are adding significant enhancements to the product including:</span></span>
  
- <span data-ttu-id="a60a8-140">Exchange online の電子メールおよび SharePoint online ドキュメントに対して実行される危険性のあるアクションについての洞察を提供する</span><span class="sxs-lookup"><span data-stu-id="a60a8-140">Providing insight into potentially risky actions taken on Exchange Online email and SharePoint Online documents</span></span>
    
- <span data-ttu-id="a60a8-141">ユーザーに送信された悪意のあるフィッシング電子メールメッセージに洞察を提供する (たとえば、ユーザーが weaponized する前にユーザーによって受信および読み取りが行われたものも含む)</span><span class="sxs-lookup"><span data-stu-id="a60a8-141">Providing insight into malicious phishing email messages that have been sent to users, including some that have may have been received and read by users before they were weaponized</span></span>
    
- <span data-ttu-id="a60a8-142">管理者がインシデントに応答するために実行できるアクションのセットを増やす</span><span class="sxs-lookup"><span data-stu-id="a60a8-142">Increasing the set of actions admins can take to respond to incidents</span></span>
    
## <a name="why-threat-intelligence"></a><span data-ttu-id="a60a8-143">脅威インテリジェンスの理由</span><span class="sxs-lookup"><span data-stu-id="a60a8-143">Why Threat Intelligence?</span></span>

<span data-ttu-id="a60a8-p113">2017が $ 90b を超えた場合、Gartner の推定は cybersecurity に費やされました。Sid deshpande、Gartner の主な研究アナリストは、「the the the the the the the the the the the the the the the the the the the the the the the the the the the the the」と言っています。検出/応答機能に関連付けられていない限り、futile が無効であることを示すメッセージを送信します。脅威インテリジェンスは、すべての企業のサービスポートフォリオの重要な部分であり、スタンドアロンサービスとして、または Office 365 E5 の一部として使用できます。</span><span class="sxs-lookup"><span data-stu-id="a60a8-p113">Gartner estimates that in 2017 alone over $90B was spent on cybersecurity. Sid Deshpande, principal research analyst at Gartner, is quoted as saying that "the industry's shift to detection and response … sends a clear message that prevention is futile unless it is tied into a detection and response capability." Threat Intelligence is a critical part of every enterprise's portfolio of services, and can be consumed as standalone service or as part of Office 365 E5.</span></span>
  
## <a name="whats-next"></a><span data-ttu-id="a60a8-148">[次へ]</span><span class="sxs-lookup"><span data-stu-id="a60a8-148">What's Next</span></span>

- <span data-ttu-id="a60a8-149">この記録されたセッションの office 365 脅威インテリジェンスの詳細について[は、「office 365 の脅威インテリジェンスを Cyberattacks する」を参照し](https://myignite.microsoft.com/videos/53723)てください。</span><span class="sxs-lookup"><span data-stu-id="a60a8-149">Learn more about Office 365 Threat Intelligence in this recorded session: [Stay Ahead of the Cyberattacks with Office 365 Threat Intelligence](https://myignite.microsoft.com/videos/53723)</span></span>
    
- <span data-ttu-id="a60a8-150">[現在、office 365 の脅威インテリジェンスを試す](https://aka.ms/tryo365threatintel3)か、office E5 試用版を開始してください。</span><span class="sxs-lookup"><span data-stu-id="a60a8-150">[Try out Office 365 Threat Intelligence now](https://aka.ms/tryo365threatintel3) or begin your Office E5 trial today!</span></span> 
    

