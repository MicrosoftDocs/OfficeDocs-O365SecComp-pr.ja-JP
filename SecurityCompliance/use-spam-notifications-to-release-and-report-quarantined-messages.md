---
title: Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/14/2019
audience: Admin
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
ms.openlocfilehash: 887dab0df489e6f71266a6fdabfdd04f26a14ded
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598443"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a><span data-ttu-id="e4755-104">Office 365 でユーザーのスパム通知を使って検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="e4755-104">Use user spam notifications to release and report quarantined messages in Office 365</span></span>

<span data-ttu-id="e4755-105">管理者がユーザーのスパム通知を有効にした場合、スパムとして識別されたメールボックス宛てのメッセージを一覧表示する通知メッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="e4755-105">If your admin enables spam notifications for users, you'll receive a notification message that lists messages addressed to your mailbox that were identified as spam and quarantined instead.</span></span>
  
> [!TIP]
> <span data-ttu-id="e4755-106">管理者がこの機能を有効にする場合は、[既定のスパム対策ポリシーを変更](https://go.microsoft.com/fwlink/?LinkId=800313)するときにオプションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="e4755-106">If you're an administrator and want to enable this feature, you can choose the option when you [modify a default anti-spam policy](https://go.microsoft.com/fwlink/?LinkId=800313).</span></span> 
  
<span data-ttu-id="e4755-107">受信するメッセージには、スパム検疫済みメッセージの数と、リスト内の最後のメッセージの日付と時刻 (世界協定時刻または UTC) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="e4755-107">The message you receive includes the number of spam-quarantined messages you have, and the date and time (in Universal Coordinated Time or UTC) of the last message in the list.</span></span> <span data-ttu-id="e4755-108">一覧には、各メッセージの次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e4755-108">The list includes the following for each message:</span></span>
  
- <span data-ttu-id="e4755-109">**送信者**検疫済みメッセージの送信名と電子メールアドレス。</span><span class="sxs-lookup"><span data-stu-id="e4755-109">**Sender** The send name and email address of the quarantined message.</span></span> 
    
- <span data-ttu-id="e4755-110">**件名** 検疫されたメッセージの件名テキスト。</span><span class="sxs-lookup"><span data-stu-id="e4755-110">**Subject** The subject line text of the quarantined message.</span></span> 
    
- <span data-ttu-id="e4755-111">**日付** メッセージが検疫された日付と時刻 (UTC)。</span><span class="sxs-lookup"><span data-stu-id="e4755-111">**Date** The date and time (in UTC) that the message was quarantined.</span></span> 
    
- <span data-ttu-id="e4755-112">**サイズ**メッセージのサイズをキロバイト (kb) 単位で示します。</span><span class="sxs-lookup"><span data-stu-id="e4755-112">**Size** The size of the message, in kilobytes (KBs).</span></span> 
    
<span data-ttu-id="e4755-113">以下に、検疫済みメッセージを使用して実行できるアクションを示します。</span><span class="sxs-lookup"><span data-stu-id="e4755-113">These are the actions that you can take with a quarantined message:</span></span>

- <span data-ttu-id="e4755-114">アクションを実行する前にコンテンツまたはヘッダーをプレビューしたい場合は、メッセージを**プレビュー**してください。</span><span class="sxs-lookup"><span data-stu-id="e4755-114">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

- <span data-ttu-id="e4755-115">アクションを実行する前に、デバイスのメッセージと添付ファイル (存在する場合) を確認したい場合は、メッセージを**ダウンロード**してください。</span><span class="sxs-lookup"><span data-stu-id="e4755-115">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

- <span data-ttu-id="e4755-116">メッセージがスパムではなく、Office 365 がメールボックスにメッセージを送信する場合は、**リリースを解放**します。</span><span class="sxs-lookup"><span data-stu-id="e4755-116">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

- <span data-ttu-id="e4755-117">**Release &** メッセージがスパムではない場合に送信者に送信を許可し、今後の電子メールに対応するように Office 365 で [差出人セーフリスト] と [受信者] 一覧に送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="e4755-117">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="e4755-118">管理者には、[信頼できる差出人のリスト] を上書きする、組織全体にわたる許可/ブロック構成が存在する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="e4755-118">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

- <span data-ttu-id="e4755-119">メッセージがスパムではなく、メールボックスにメッセージを送信して分析のために Microsoft に報告する場合は **& レポートをリリース**します。</span><span class="sxs-lookup"><span data-stu-id="e4755-119">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

- <span data-ttu-id="e4755-120">Office 365 で、受信拒否リストに送信者を追加する場合は、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e4755-120">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="e4755-121">以下の点にご注意ください。</span><span class="sxs-lookup"><span data-stu-id="e4755-121">Be aware of the following:</span></span>
  
- <span data-ttu-id="e4755-122">メールフロールールに一致したために検疫されたメッセージは、ユーザーの検疫済みメッセージには含まれません。</span><span class="sxs-lookup"><span data-stu-id="e4755-122">Messages that are quarantined because they matched a mail flow rule are not included in user quarantined messages.</span></span> <span data-ttu-id="e4755-123">スパム検疫済みメッセージのみが列挙されます。</span><span class="sxs-lookup"><span data-stu-id="e4755-123">Only spam-quarantined messages are listed.</span></span>
    
- <span data-ttu-id="e4755-124">メッセージを解放して、誤検知 (迷惑メールではない) として報告することができるのは1回だけです。</span><span class="sxs-lookup"><span data-stu-id="e4755-124">You can only release a message and report it as a false positive (not junk) once.</span></span>
    

