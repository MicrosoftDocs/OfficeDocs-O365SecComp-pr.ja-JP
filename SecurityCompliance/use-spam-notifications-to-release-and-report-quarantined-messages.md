---
title: Office 365 でエンド ユーザーのスパム通知を使って検疫済みメッセージを解放して報告する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/12/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
description: 管理者は、ユーザーへの通知を有効と、自分のメールボックスに送信される迷惑メール、一括、またはフィッシング詐欺メールとして識別されたメッセージの一覧が表示される通知メッセージが表示されます。解放するか、通知された後にメッセージを報告します。
ms.openlocfilehash: e355a94af5ac295503a8e205b1a896afc1c54fb6
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531895"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="44273-104">Office 365 でエンド ユーザーのスパム通知を使って検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="44273-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="44273-105">管理者は、ユーザーの迷惑メールの通知を有効と、迷惑メールとして識別され、代わりに検疫メールボックス宛てのメッセージの一覧が表示される通知メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44273-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="44273-106">オプションを選択するには、管理者とこの機能を有効にする場合は、ときに[既定の迷惑メール対策ポリシーを変更](https://go.microsoft.com/fwlink/?LinkId=800313)します。</span><span class="sxs-lookup"><span data-stu-id="44273-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="44273-p102">受信したメッセージは、リスト内のスパム検疫されたメッセージがある場合は、日付と時間 (世界協定時刻または UTC) の最後のメッセージの数を含みます。一覧には、メッセージごとに次が含まれています。</span><span class="sxs-lookup"><span data-stu-id="44273-p102">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list. The list includes the following for each message:</span></span>
  
- <span data-ttu-id="44273-109">**送信者**検疫済みのメッセージの送信の名前と電子メール アドレスです。</span><span class="sxs-lookup"><span data-stu-id="44273-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="44273-110">**件名** 検疫されたメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="44273-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="44273-111">**日付** メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="44273-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="44273-112">**サイズ**キロバイト (kb 単位) で、メッセージのサイズです。</span><span class="sxs-lookup"><span data-stu-id="44273-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="44273-113">現在、検疫済みのメッセージで実行できる 2 つのアクションがあります。</span><span class="sxs-lookup"><span data-stu-id="44273-113">Currently, there are two actions you can take with a quarantined message:</span></span>
  
- <span data-ttu-id="44273-114">**受信トレイへのリリース**表示できます、受信トレイにメッセージを送信する場合に選択します。</span><span class="sxs-lookup"><span data-stu-id="44273-114">**Release to Inbox** Choose this to send the message to your inbox, where you can view it.</span></span> 
    
- <span data-ttu-id="44273-p103">**[迷惑メールのレポート**分析のため、メッセージのコピーを Microsoft に送信する場合に選択します。スパム チーム評価し、メッセージを分析し、分析の結果によって、スパム対策フィルターを許可する規則を介してメッセージを調整します。</span><span class="sxs-lookup"><span data-stu-id="44273-p103">**Report as Not Junk** Choose this to send a copy of the message to Microsoft for analysis. The spam team evaluates and analyzes the message, and, depending on the results of the analysis, adjusts the anti-spam filter rules to allow the message through.</span></span> 
    
<span data-ttu-id="44273-117">次の対応になります。</span><span class="sxs-lookup"><span data-stu-id="44273-117">Be aware of the following:</span></span>
  
- <span data-ttu-id="44273-p104">メール フロー ルールに一致するために隔離されているメッセージは、ユーザーが検疫されたメッセージには含まれません。スパム検疫済みメッセージのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="44273-p104">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages. Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="44273-120">メッセージを移動して、それを誤検知 (迷惑メールではない) として報告できるのは一度だけです。</span><span class="sxs-lookup"><span data-stu-id="44273-120">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

