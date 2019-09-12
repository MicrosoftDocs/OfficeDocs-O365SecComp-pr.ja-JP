---
title: Office 365 の脅威の調査および応答機能を使用して組織を安全に保つ
ms.author: tracyp
author: msfttracyp
manager: dansimp
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
ms.openlocfilehash: 22d2b7e0aa1495c0eca0cc7db8eea58b59a73654
ms.sourcegitcommit: ff370e93b792204547694139ef99bc0848304570
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/11/2019
ms.locfileid: "36852819"
---
# <a name="keep-your-organization-safe-with-office-365-threat-investigation-and-response-capabilities"></a><span data-ttu-id="4f678-103">Office 365 の脅威の調査および応答機能を使用して組織を安全に保つ</span><span class="sxs-lookup"><span data-stu-id="4f678-103">Keep your organization safe with Office 365 threat investigation and response capabilities</span></span>

<span data-ttu-id="4f678-104">どの Office 365 ユーザーが攻撃にさらされているか、または深刻な侵害になっているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f678-104">Do you know which of your Office 365 users are under attack, or worse - compromised?</span></span> <span data-ttu-id="4f678-105">ユーザーを対象とする攻撃を緩和して回復する方法を理解していますか。</span><span class="sxs-lookup"><span data-stu-id="4f678-105">Do know how to mitigate and recover from attacks that are targeting your users?</span></span> <span data-ttu-id="4f678-106">Office 365 E5 に既に提供されているセキュリティ機能を使用して、これを正確に実行できることがわかりましたか。</span><span class="sxs-lookup"><span data-stu-id="4f678-106">Did you know you can do exactly this with security capabilities that are already available to you in Office 365 E5?</span></span> 
  
<span data-ttu-id="4f678-107">Office [365 の脅威の調査と応答](office-365-ti.md)機能が Office 365 E5 サブスクリプション ( [Office 365 Advanced threat Protection](office-365-atp.md)プラン2の一部として) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="4f678-107">[Office 365 threat investigation and response](office-365-ti.md) capabilities are included in your Office 365 E5 subscription (as part of [Office 365 Advanced Threat Protection](office-365-atp.md) Plan 2).</span></span> <span data-ttu-id="4f678-108">これらの機能により、Microsoft IT はソーシャルエンジニアリングインシデントの解決にかかる平均時間を 80% 削減し、大文字と小文字のスループットを劇的に向上させました。</span><span class="sxs-lookup"><span data-stu-id="4f678-108">These capabilities have helped Microsoft IT reduce average time to resolution for social engineering incidents by 80%, and increased case throughput dramatically.</span></span> <span data-ttu-id="4f678-109">最近、脅威を検出して回復する方法を改善するために、新機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="4f678-109">Recently, new capabilities were added to help improve how you can detect and recover from threats.</span></span> <span data-ttu-id="4f678-110">この記事では、脅威の調査と応答能力が、セキュリティ運用チームの効率と効率を向上させる方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4f678-110">Read this article to see how threat investigation and response capabilities can help your security operations team be more effective and efficient.</span></span>
  
## <a name="detect-intrusions-and-threats"></a><span data-ttu-id="4f678-111">侵入と脅威を検出する</span><span class="sxs-lookup"><span data-stu-id="4f678-111">Detect intrusions and threats</span></span>

<span data-ttu-id="4f678-112">[脅威エクスプローラー](threat-explorer.md)(エクスプローラーとも呼ばれます) は、セキュリティ管理者とアナリストが組織内でアクティブな脅威を識別し、理解するのを促進します。</span><span class="sxs-lookup"><span data-stu-id="4f678-112">[Threat Explorer](threat-explorer.md) (also referred to as Explorer) helps security administrators and analysts identify and understand threats that are active in your organization.</span></span> <span data-ttu-id="4f678-113">セキュリティ設定の中でも、安全ではないとしても、安全ではないと思われるユーザー構成によって回避されることがあります。</span><span class="sxs-lookup"><span data-stu-id="4f678-113">Even the most complex security settings can be circumvented by seemingly innocuous user configurations like safe-sender allow lists.</span></span> <span data-ttu-id="4f678-114">エクスプローラーを使用すると、ユーザーがマルウェアやフィッシングなどの脅威によって侵害されたかどうかを、Office 365 のグローバル管理者またはセキュリティ管理者が迅速に判断できます。</span><span class="sxs-lookup"><span data-stu-id="4f678-114">Explorer helps Office 365 global or security administrators quickly determine whether users have been compromised by threats, such as malware or phish.</span></span> <span data-ttu-id="4f678-115">これにより、脅威や必要な応答に対して、最も危険にさらされるユーザーアカウントの優先順位付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4f678-115">This helps prioritize which user accounts are most at risk for a threat and the requisite response.</span></span> 
  
<span data-ttu-id="4f678-116">エクスプローラーを使用すると、管理者はユーザーとメール間の関係を移動することができます。</span><span class="sxs-lookup"><span data-stu-id="4f678-116">Explorer also helps administrators navigate the relationships between users and mail.</span></span> <span data-ttu-id="4f678-117">特定のメールが正しくないことがわかりますか。</span><span class="sxs-lookup"><span data-stu-id="4f678-117">Know of a particular mail that was bad?</span></span> <span data-ttu-id="4f678-118">これを検索して、どのユーザーがメールを受信したかを確認してから、一連のイベントを実行し、それらのユーザーが実行したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4f678-118">Search for it to see what users received the mail, then follow the series of events and see what those users in turn have done.</span></span>

![Office 365 の脅威エクスプローラーのスクリーンショット、マルウェアファミリによる色分け](media/591338dd-252a-437d-b5f2-87aa42e74b0c.png)
  
## <a name="quickly-mitigate-and-recover-from-threats"></a><span data-ttu-id="4f678-120">脅威を迅速に軽減および復旧する</span><span class="sxs-lookup"><span data-stu-id="4f678-120">Quickly mitigate and recover from threats</span></span>

<span data-ttu-id="4f678-121">セキュリティ管理者は、テナント内で疑わしいまたは悪意のあるものを特定すると、その脅威にすばやく対応し、**インシデントフレームワーク**を使用して対応することができます。</span><span class="sxs-lookup"><span data-stu-id="4f678-121">Once security administrators have identified something suspicious or malicious happening in their tenant, they can quickly contain and respond to that threat with the **Incident Framework**.</span></span> <span data-ttu-id="4f678-122">不要なメッセージを1回クリックしてグループ化し、ユーザーのメールボックスからすばやく電子メールメッセージを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f678-122">Group unwanted messages with one-click and quickly remove the email messages from your user's mailboxes.</span></span> 
  
 <span data-ttu-id="4f678-123">**更新:** インシデントフレームワークから直接電子メールメッセージを削除 (ソフトまたは削除) する機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="4f678-123">**UPDATE:** The ability to delete (soft or hard delete) email messages directly from the Incident framework has been added.</span></span> <span data-ttu-id="4f678-124">以前の管理者は、ユーザーの迷惑メールフォルダーにのみメールを移動でき、ユーザーはそのアイテムを回復できます。</span><span class="sxs-lookup"><span data-stu-id="4f678-124">Previously administrators could only move mails to a user's junk folder, where users could recover the item.</span></span> <span data-ttu-id="4f678-125">新たにリリースされた削除機能を使用すると、悪意のあるメールまたは不要なメールが完全に削除されていることを確認できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="4f678-125">With the newly released Delete capabilities, you can now be sure that a malicious or unwanted mail is removed permanently.</span></span> 
    
![インシデント修復の電子メールリストのスクリーンショット](media/9d8452d3-d8d2-4b26-81f9-76396e08dd17.png)
  
## <a name="leverage-the-threat-telemetry-of-microsoft"></a><span data-ttu-id="4f678-127">Microsoft の脅威テレメトリを活用する</span><span class="sxs-lookup"><span data-stu-id="4f678-127">Leverage the threat telemetry of Microsoft</span></span>

<span data-ttu-id="4f678-128">Office 365 の脅威の調査と応答機能には、 [Microsoft インテリジェントセキュリティグラフ](https://go.microsoft.com/fwlink/?linkid=2036223)からのデータが使用されています。</span><span class="sxs-lookup"><span data-stu-id="4f678-128">Office 365 threat investigation and response capabilities are powered with data from the [Microsoft Intelligent Security Graph](https://go.microsoft.com/fwlink/?linkid=2036223).</span></span> <span data-ttu-id="4f678-129">グラフは、10億の Windows デバイス、4500億月の Azure ログイン、および Office 365 の4000億の電子メールメッセージから最新の脅威信号を取得します。</span><span class="sxs-lookup"><span data-stu-id="4f678-129">The graph acquires the latest threat signal from over 1 billion Windows devices, 450 billion monthly Azure logins, and 400 billion monthly email messages in Office 365.</span></span> <span data-ttu-id="4f678-130">この unrivaled threat signal は、組織に影響を与える脅威をより完全に表示するために、セキュリティ運用チームが持つ広範な可視性を提供します。</span><span class="sxs-lookup"><span data-stu-id="4f678-130">This unrivaled threat signal is what gives the broad visibility your security operations team have for a more complete view of the threats impacting your organization.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="4f678-131">次の手順</span><span class="sxs-lookup"><span data-stu-id="4f678-131">Next steps</span></span>

- <span data-ttu-id="4f678-132">詳細については、 [「Office 365 Advanced Threat Protection](office-365-atp.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f678-132">Learn more about [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span>

- <span data-ttu-id="4f678-133">この記録されたセッションの Office 365 脅威の調査および応答機能の詳細について[は、「office 365 で Cyberattacks](https://myignite.microsoft.com/videos/53723)をご確認ください。</span><span class="sxs-lookup"><span data-stu-id="4f678-133">Learn more about Office 365 threat investigation and response capabilities in this recorded session: [Stay Ahead of the Cyberattacks with Office 365](https://myignite.microsoft.com/videos/53723).</span></span>

- <span data-ttu-id="4f678-134">Office 365 Advanced Threat Protection プラン2をまだお持ちでない場合は、今すぐご利用ください。</span><span class="sxs-lookup"><span data-stu-id="4f678-134">If you don't already have Office 365 Advanced Threat Protection Plan 2, try or buy it now.</span></span> <span data-ttu-id="4f678-135">「 [Office 365 Advanced Threat Protection: プランと料金」を](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content)参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f678-135">See [Office 365 Advanced Threat Protection: Plans and pricing](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content).</span></span>
    
- <span data-ttu-id="4f678-136">[Microsoft Defender Advanced Threat protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)を使用して保護を拡張します。</span><span class="sxs-lookup"><span data-stu-id="4f678-136">Extend protection with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span>