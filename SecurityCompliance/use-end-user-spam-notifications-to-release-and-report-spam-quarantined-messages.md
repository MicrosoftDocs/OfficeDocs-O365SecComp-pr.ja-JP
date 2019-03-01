---
title: エンド ユーザーのスパム通知を使ってスパム検疫済みメッセージを解放して報告する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 4b250bc9-0056-4426-8397-7b4398f1b026
ms.collection:
- M365-security-compliance
description: '検疫済みメールに関するエンドユーザーのスパム通知メッセージを管理者から取得したユーザーは、これらのメッセージに対してこれらの操作を行うことができます。 '
ms.openlocfilehash: adddd5032e6254b6084a7f6e714859b713815ed2
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341238"
---
# <a name="use-end-user-spam-notifications-to-release-and-report-spam-quarantined-messages"></a><span data-ttu-id="61e22-103">エンド ユーザーのスパム通知を使ってスパム検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="61e22-103">Use end-user spam notifications to release and report spam-quarantined messages</span></span>

<span data-ttu-id="61e22-104">[![TechNet から support.office.com に移動するコンテンツについてのイメージ内のテキスト](media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)</span><span class="sxs-lookup"><span data-stu-id="61e22-104">[![Text in image about content moving from TechNet to support.office.com](media/ab7c897a-4798-4f31-8c84-f17a8409b133.png)](https://go.microsoft.com/fwlink/p/?LinkID=624152)</span></span>
  
<span data-ttu-id="61e22-p101">管理者がエンドユーザーのスパム通知を有効にした場合、ユーザーは、自分のメールボックス宛てに送信されたメッセージのうち、スパムと特定されて検疫されたメッセージがリストされている通知メッセージを受信します。このメッセージには、列挙されたスパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻 (UTC)) が含まれています。このリストで、各メッセージに関する以下の情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="61e22-p101">If your administrator enables end-user spam notifications, you'll receive a notification message that lists messages intended for your mailbox that were identified as spam and quarantined instead. This message includes the number of spam-quarantined messages listed, and the date and time (in Universal Coordinated Time (UTC)) of the last message in the list. From this list, you can view the following information about each message:</span></span> 
  
- <span data-ttu-id="61e22-108">**送信者** 検疫されたメッセージの送信者名と電子メール アドレス。</span><span class="sxs-lookup"><span data-stu-id="61e22-108">**Sender** The sender name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="61e22-109">**件名** 検疫されたメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="61e22-109">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="61e22-110">**日付** メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="61e22-110">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="61e22-111">**サイズ** 検疫されたメッセージのキロバイト (KB) 単位のサイズ。</span><span class="sxs-lookup"><span data-stu-id="61e22-111">**Size** The size of the quarantined message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="61e22-112">各メッセージに対して次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="61e22-112">You can perform the following actions on each message:</span></span>
  
- <span data-ttu-id="61e22-113">**受信トレイに移動** このリンクをクリックすると、メッセージがそれを表示可能な受信トレイに送信されます。</span><span class="sxs-lookup"><span data-stu-id="61e22-113">**Release to Inbox** Clicking this link sends the message to your inbox where you can view it.</span></span> 
    
- <span data-ttu-id="61e22-p102">**迷惑メールではないと報告** このリンクをクリックすると、メッセージのコピーが分析のために Microsoft に送信されます。スパム チームはメッセージの評価と分析を行い、分析結果に応じてスパム対策フィルター ルールを調整し、そのメッセージの通過を許可します。</span><span class="sxs-lookup"><span data-stu-id="61e22-p102">**Report as Not Junk** Clicking this link sends a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
> [!NOTE]
>  <span data-ttu-id="61e22-p103">メールフロールール (とも呼ばれます) が一致したために検疫されたメッセージは、エンドユーザースパム検疫済みメッセージには含まれません。スパム検疫済みメッセージのみが一覧表示されます。> メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="61e22-p103">Messages that are quarantined due to a mail flow rule (also known as a ) match are not included in end user spam quarantined messages. Only spam-quarantined messages are listed. >  You can only release a message and report it as a false positive (not junk) once.</span></span> 
  

