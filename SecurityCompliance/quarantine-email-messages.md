---
title: Office 365 でメール メッセージを検疫する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 4c234874-015e-4768-8495-98fcccfc639b
ms.collection:
- M365-security-compliance
description: Office 365 で受信メールメッセージの検疫を設定することができます。これは、スパム、バルク、フィッシングメール、マルウェアとしてフィルター処理された受信メールメッセージを後で確認するために保持することができます。
ms.openlocfilehash: 90a8c9f36468fdc8c5d5825776e9678cd8f8e109
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156829"
---
# <a name="quarantine-email-messages-in-office-365"></a><span data-ttu-id="19ca2-103">Office 365 でメール メッセージを検疫する</span><span class="sxs-lookup"><span data-stu-id="19ca2-103">Quarantine email messages in Office 365</span></span>

<span data-ttu-id="19ca2-104">Office 365 で受信メールメッセージの検疫をセットアップすることができます。これは、スパム、バルクメール、フィッシングメール、マルウェアを含むメール、および指定されたメールフロールールと一致したメールを、後で確認するために保持することができます。</span><span class="sxs-lookup"><span data-stu-id="19ca2-104">You can set up quarantine for incoming email messages in Office 365 where messages that have been filtered as spam, bulk mail, phishing mail, mail that contains malware, and mail that matched a specified mail flow rule can be kept for later review.</span></span>
  
<span data-ttu-id="19ca2-105">既定では、フィルター処理されたメッセージは受信者の迷惑メールフォルダーに送信されます。ただし、既定で検疫に送信されるマルウェアを含むメールは除きます。</span><span class="sxs-lookup"><span data-stu-id="19ca2-105">By default, filtered messages are sent to the recipients' Junk Email folder, except for mail that contains malware which is sent to quarantine by default.</span></span> <span data-ttu-id="19ca2-106">管理者として、コンテンツフィルターポリシーを設定して、フィルター処理されたすべてのメッセージを検疫に送信することができます。</span><span class="sxs-lookup"><span data-stu-id="19ca2-106">As an admin, you can set up content filter policies to send all filtered messages to quarantine instead.</span></span> <span data-ttu-id="19ca2-107">コンテンツフィルター処理でメッセージに対して実行できるさまざまな操作は、[定義したスパムフィルターポリシー](https://go.microsoft.com/fwlink/?LinkId=799736)によって異なります。</span><span class="sxs-lookup"><span data-stu-id="19ca2-107">The different actions that you can take for content-filtered messages depend on the [spam filter policies you've defined](https://go.microsoft.com/fwlink/?LinkId=799736).</span></span>
  
<span data-ttu-id="19ca2-108">ユーザーと管理者の両方が、検疫済みメッセージを操作できます。</span><span class="sxs-lookup"><span data-stu-id="19ca2-108">Both users and admins can work with quarantined messages.</span></span> <span data-ttu-id="19ca2-109">ユーザーは、隔離された独自のフィルター処理されたメッセージのみを操作できます。</span><span class="sxs-lookup"><span data-stu-id="19ca2-109">Users can work with just their own filtered messages in quarantine.</span></span> <span data-ttu-id="19ca2-110">管理者は、すべてのユーザーの検疫済みメッセージを検索し、管理することができます。</span><span class="sxs-lookup"><span data-stu-id="19ca2-110">Admins can search for and manage quarantined messages for all users.</span></span>
  
<span data-ttu-id="19ca2-111">検疫済みメッセージの使用の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="19ca2-111">Learn more about working with quarantined messages:</span></span>
  
- [<span data-ttu-id="19ca2-112">管理者として検疫済みメッセージを管理する</span><span class="sxs-lookup"><span data-stu-id="19ca2-112">Manage quarantined messages as an administrator</span></span>](manage-quarantined-messages-and-files.md)
    
- [<span data-ttu-id="19ca2-113">ユーザーが検閲済みメッセージを検出して解放する</span><span class="sxs-lookup"><span data-stu-id="19ca2-113">Find and release quarantined messages as a user</span></span>](find-and-release-quarantined-messages-as-a-user.md)
    
- [<span data-ttu-id="19ca2-114">ユーザースパム通知を使用してスパム検疫済みメッセージを解放して報告する</span><span class="sxs-lookup"><span data-stu-id="19ca2-114">Use user spam notifications to release and report spam-quarantined messages</span></span>](use-spam-notifications-to-release-and-report-quarantined-messages.md)
    
- [<span data-ttu-id="19ca2-115">検疫に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="19ca2-115">Quarantine FAQ</span></span>](quarantine-faq.md)
    

