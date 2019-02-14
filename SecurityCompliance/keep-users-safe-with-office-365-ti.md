---
title: Office 365 脅威インテリジェンスを使用して Office 365 ユーザーの安全を守る
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3387bfc3-028a-42f4-8133-4cbecfaab812
ms.collection: M365-security-compliance
description: Office 365 の脅威インテリジェンスが組織侵入の脅威を検出し、すばやくを軽減し、脅威から回復を支援する方法について説明します。
ms.openlocfilehash: c049e6f811eec8a30eb2b94361f8cdcbdaa8ac49
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995368"
---
# <a name="keep-your-office-365-users-safe-with-office-365-threat-intelligence"></a><span data-ttu-id="17328-103">Office 365 脅威インテリジェンスを使用して Office 365 ユーザーの安全を守る</span><span class="sxs-lookup"><span data-stu-id="17328-103">Keep your Office 365 users safe with Office 365 Threat Intelligence</span></span>

## <a name="overview"></a><span data-ttu-id="17328-104">概要</span><span class="sxs-lookup"><span data-stu-id="17328-104">Overview</span></span>

<span data-ttu-id="17328-p101">Office 365 ユーザーの攻撃を受けているか、さらに危険にさらされたについて知っていますか軽減し、ユーザーを対象とする攻撃から回復する方法をご存知ですか。Office 365 で使用されているセキュリティ機能でこれを正確に行うことができますをご存知でしたか。</span><span class="sxs-lookup"><span data-stu-id="17328-p101">Do you know which of your Office 365 users are under attack, or worse - compromised? Do know how to mitigate and recover from attacks that are targeting your users? Did you know you can do exactly this with security capabilities that are already available to you in Office 365?</span></span> 
  
<span data-ttu-id="17328-p102">[Office 365 の脅威インテリジェンス](office-365-ti.md)は、Office 365 の E5 サブスクリプションに含まれている機能のスイートです。Office 365 脅威インテリジェンスでは、平均時間ソーシャル エンジニア リングの問題の解決方法を 80%、およびスループットを向上させるケースが 37% 削減 1 か月の前の 2 四半期と比較して、Microsoft IT ができました!</span><span class="sxs-lookup"><span data-stu-id="17328-p102">[Office 365 Threat Intelligence](office-365-ti.md) is a suite of capabilities included in your Office 365 E5 subscription. Office 365 Threat Intelligence has helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput by 37% per month compared to the previous 2 quarters!</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="17328-p103">2019 の 2 月に開始し、今後数か月にロールアウト、Office 365 の脅威インテリジェンスは Office 365 高度な脅威保護計画 2、あらたな脅威保護機能となりつつあります。詳細については、 [Office 365 の高度な脅威保護の計画と価格設定](https://products.office.com/exchange/advance-threat-protection)と[Office 365 高度な脅威保護サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17328-p103">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
<span data-ttu-id="17328-p104">新規の機能を検出し、脅威から回復する方法を向上させるために最近追加しました!ここではあるから更新された脅威インテリジェンス サービス作成方法より効率的なのです。</span><span class="sxs-lookup"><span data-stu-id="17328-p104">We've recently added new capabilities to help improve how you can detect and recover from threats! Here's a quick walk through of how the updated Threat Intelligence service can make you even more efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="17328-114">侵入の脅威を検出します。</span><span class="sxs-lookup"><span data-stu-id="17328-114">Detect intrusions and threats</span></span>

<span data-ttu-id="17328-p105">[エクスプ ローラー](use-explorer-in-security-and-compliance.md)(脅威のエクスプ ローラーとも呼ばれます) により、セキュリティ管理者やアナリストを識別し、金庫のように一見無害なユーザーの構成でも最も複雑なセキュリティ設定を回避できますので、企業内でアクティブな脅威を理解します。送信者単位です。エクスプ ローラーにより、Office 365 のグローバルまたはセキュリティ管理者が迅速にユーザーが、マルウェアやフィッシングなどの脅威に感染しているかどうかを確認します。これにより、優先順位をどのユーザーと必要な応答の脅威の危険性は最も。</span><span class="sxs-lookup"><span data-stu-id="17328-p105">[Explorer](use-explorer-in-security-and-compliance.md) (also referred to as Threat Explorer) helps security admins and analysts identify and understand threats that are active in your enterprise because even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe sender whitelists. Explorer helps Office 365 global or security admins quickly determine whether users have been compromised by threats such as malware or phish. This helps prioritize which users are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="17328-p106">エクスプ ローラーでは、管理者がユーザーとメール間の関係を移動するのにも役立ちます。特定のメールに問題があったを知っているでしょうか。検索して、どのようなユーザーがメールを受信した、次の一連のイベントして、それらのユーザーに作業内容を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17328-p106">Explorer also helps admins navigate the relationships between users and mail. Know of a particular mail that was bad? Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

<span data-ttu-id="17328-p107">脅威インテリジェンス、[今すぐ](https://aka.ms/tryo365threatintel3)があるない場合![Office 365 の脅威インテリジェンスに関する詳細情報について説明](https://aka.ms/readmoreabouto365threatintel)します。</span><span class="sxs-lookup"><span data-stu-id="17328-p107">If you don't already have Threat Intelligence, [try it now](https://aka.ms/tryo365threatintel3)! And [learn more about Office 365 Threat Intelligence](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![マルウェア ファミリによって色分けされている、Office 365 で脅威のエクスプ ローラーのスクリーン ショット](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="17328-124">迅速に軽減し、脅威からの回復</span><span class="sxs-lookup"><span data-stu-id="17328-124">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="17328-p108">セキュリティ管理者が識別されると不審なまたは悪意のある、テナントで起こっているか何か、簡単が含まれているし、**インシデントのフレームワーク**を使用してその脅威への対応にできます。1 回のクリックで不要なメッセージをグループ化し、迅速に、ユーザーのメールボックスから電子メール メッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="17328-p108">Once security admins have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**. Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="17328-p109">**更新:** 最近インシデント フレームワークから直接 (ソフトまたはハード削除) の電子メールを削除する機能追加しました。以前管理者はユーザーがアイテムを復元できます、ユーザーの迷惑メール フォルダーにメールを移動する可能性がありますのみです。新しくリリースされた削除の機能により、するできるようになりました、悪意のあるまたは不要なメールが完全に削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="17328-p109">**UPDATE:** We've recently added the ability to delete (soft or hard delete) emails directly from the Incident Framework. Previously administrators could only move mails to a user's junk folder, where users could recover the item. With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
  
<span data-ttu-id="17328-p110">脅威インテリジェンス、[今すぐ](https://aka.ms/tryo365threatintel3)があるない場合![Office 365 の脅威インテリジェンスに関する詳細情報について説明](https://aka.ms/readmoreabouto365threatintel)します。</span><span class="sxs-lookup"><span data-stu-id="17328-p110">If you don't already have Threat Intelligence, [try it now](https://aka.ms/tryo365threatintel3)! And [learn more about Office 365 Threat Intelligence](https://aka.ms/readmoreabouto365threatintel).</span></span>
  
![インシデント対応の電子メール] ボックスの一覧のスクリーン ショット](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="17328-133">マイクロソフトの脅威の遠隔測定を活用します。</span><span class="sxs-lookup"><span data-stu-id="17328-133">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="17328-p111">Microsoft インテリジェントなセキュリティのグラフからデータを office 365 の脅威インテリジェンスの電源します。グラフでは、以上の 10億の Windows デバイス、450 ドル毎月 Azure ログイン、および Office 365 で、400 ドル毎月の電子メール メッセージの最新の脅威信号を取得します。この比類のない脅威の信号は、自分の組織に影響を及ぼす脅威の完全なビューを使用して、管理者およびセキュリティ アナリストにとって不可欠ですがお客様のテナントに広範な可視性を与えるものです。</span><span class="sxs-lookup"><span data-stu-id="17328-p111">Office 365 Threat Intelligence is powered with data from the Microsoft Intelligent Security Graph. The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365. This unrivaled threat signal is what gives the broad visibility into a customer tenant that is crucial for admins and security analysts to have a complete view of the threats impacting their organization.</span></span> 
  
## <a name="more-to-come"></a><span data-ttu-id="17328-137">増える</span><span class="sxs-lookup"><span data-stu-id="17328-137">More to come</span></span>

<span data-ttu-id="17328-p112">これらは、Office 365 の脅威インテリジェンスにより、企業の安全を確保できるかの例だけです!今後数週間で大幅に強化されてを製品に追加します。</span><span class="sxs-lookup"><span data-stu-id="17328-p112">These are just some examples of how Office 365 Threat Intelligence helps you secure your enterprise! In the coming weeks we are adding significant enhancements to the product including:</span></span>
  
- <span data-ttu-id="17328-140">Exchange Online の電子メールおよび SharePoint Online のドキュメントのアクションの可能性のある危険な見解を提供します。</span><span class="sxs-lookup"><span data-stu-id="17328-140">Providing insight into potentially risky actions taken on Exchange Online email and SharePoint Online documents</span></span>
    
- <span data-ttu-id="17328-141">ユーザーに送信された電子メール メッセージのフィッシング詐欺の悪意のある見解を提供するなどを持つ場合があります、受信してそれらが後で前にユーザーによって読み取ら</span><span class="sxs-lookup"><span data-stu-id="17328-141">Providing insight into malicious phishing email messages that have been sent to users, including some that have may have been received and read by users before they were weaponized</span></span>
    
- <span data-ttu-id="17328-142">インシデントへの応答にかかることが一連の操作の管理を向上</span><span class="sxs-lookup"><span data-stu-id="17328-142">Increasing the set of actions admins can take to respond to incidents</span></span>
    
## <a name="why-threat-intelligence"></a><span data-ttu-id="17328-143">なぜ脅威インテリジェンスのでしょうか。</span><span class="sxs-lookup"><span data-stu-id="17328-143">Why Threat Intelligence?</span></span>

<span data-ttu-id="17328-p113">Gartner では、ある 2017 90B ドルの上だけで費やされています cybersecurity を推定します。Sid Deshpande、gartner 社の報告でのプリンシパルのリサーチ ・ アナリストが、「業界での shift キーを検出して応答していますメッセージを送信クリア検出および応答の機能を結び付けて考えることがない限り、予防はできません」という内容として引用符で囲まれました。脅威インテリジェンスは、サービスのすべての企業のポートフォリオの重要な部分し、スタンドアロン サービスとして、または Office 365 の E5 の一部として消費されることができます。</span><span class="sxs-lookup"><span data-stu-id="17328-p113">Gartner estimates that in 2017 alone over $90B was spent on cybersecurity. Sid Deshpande, principal research analyst at Gartner, is quoted as saying that "the industry's shift to detection and response … sends a clear message that prevention is futile unless it is tied into a detection and response capability." Threat Intelligence is a critical part of every enterprise's portfolio of services, and can be consumed as standalone service or as part of Office 365 E5.</span></span>
  
## <a name="whats-next"></a><span data-ttu-id="17328-148">次は何</span><span class="sxs-lookup"><span data-stu-id="17328-148">What's Next</span></span>

- <span data-ttu-id="17328-149">この記録セッションで Office 365 の脅威インテリジェンスの詳細: [Office 365 の脅威インテリジェンスと Cyberattacks の前方を維持](https://myignite.microsoft.com/videos/53723)</span><span class="sxs-lookup"><span data-stu-id="17328-149">Learn more about Office 365 Threat Intelligence in this recorded session: [Stay Ahead of the Cyberattacks with Office 365 Threat Intelligence](https://myignite.microsoft.com/videos/53723)</span></span>
    
- <span data-ttu-id="17328-150">[今すぐに、Office 365 の脅威インテリジェンスを試す](https://aka.ms/tryo365threatintel3)か、E5 の Office の試用版を開始!</span><span class="sxs-lookup"><span data-stu-id="17328-150">[Try out Office 365 Threat Intelligence now](https://aka.ms/tryo365threatintel3) or begin your Office E5 trial today!</span></span> 
    

