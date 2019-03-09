---
title: Office 365 でエンド ユーザーのスパム通知を使って検疫済みメッセージを解放して報告する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 管理者がユーザーの通知を有効にした場合、スパム、大量、またはフィッシングメッセージとして識別されたメールボックスに送信されたメッセージを一覧表示する通知メッセージを受け取ります。 通知された後にメッセージを解放または報告することができます。
ms.openlocfilehash: 7f68b70298fca7d8ed5f5e5b8dc9c727c3a6a6c1
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492726"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="389a6-104">Office 365 でエンド ユーザーのスパム通知を使って検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="389a6-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="389a6-105">管理者がユーザーのスパム通知を有効にした場合、スパムとして識別されたメールボックス宛てのメッセージを一覧表示する通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="389a6-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="389a6-106">管理者がこの機能を有効にする場合は、[既定のスパム対策ポリシーを変更](https://go.microsoft.com/fwlink/?LinkId=800313)するときにオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="389a6-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="389a6-107">受信するメッセージには、スパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻または UTC) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="389a6-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="389a6-108">一覧には、各メッセージの次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="389a6-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="389a6-109">**送信者**検疫済みメッセージの送信名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="389a6-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="389a6-110">**件名** 検疫されたメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="389a6-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="389a6-111">**日付** メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="389a6-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="389a6-112">**サイズ**メッセージのサイズをキロバイト (kb) 単位で示します。</span><span class="sxs-lookup"><span data-stu-id="389a6-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="389a6-113">現時点では、検疫済みメッセージを使用して実行できるアクションは2つあります。</span><span class="sxs-lookup"><span data-stu-id="389a6-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="389a6-114">**受信トレイへの解放**メッセージを受信トレイに送信して、そのメッセージを表示できるようにするには、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="389a6-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="389a6-115">**迷惑メールではないと報告**このオプションを選択すると、メッセージのコピーが分析のために Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="389a6-115">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis.</span></span> <span data-ttu-id="389a6-116">スパム チームはメッセージの評価と分析を行い、分析結果に応じてスパム対策フィルター ルールを調整し、そのメッセージの通過を許可します。</span><span class="sxs-lookup"><span data-stu-id="389a6-116">The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="389a6-117">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="389a6-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="389a6-118">メールフロールールに一致したために検疫されたメッセージは、ユーザーの検疫済みメッセージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="389a6-118">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="389a6-119">スパム検疫済みメッセージのみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="389a6-119">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="389a6-120">メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="389a6-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

