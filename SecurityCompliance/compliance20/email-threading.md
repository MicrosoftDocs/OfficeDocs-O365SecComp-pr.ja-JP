---
title: 電子メールのスレッド
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2340128f508a3be389afce86596f7e6395a0bb7e
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2019
ms.locfileid: "29608037"
---
# <a name="email-threading"></a><span data-ttu-id="9c4be-102">電子メールのスレッド</span><span class="sxs-lookup"><span data-stu-id="9c4be-102">Email threading</span></span>
<span data-ttu-id="9c4be-p101">しばらくの間に起こってされている電子メールの会話を検討してください。最後の電子メールのスレッドでほとんどの場合、すべての上記メールの内容が含まれます最後の電子メールを確認すると、スレッドで行われた会話の完全なコンテキストが提供されます。校閲者が任意のコンテキストを失うことがなく収集したドキュメントの一部を確認できるように、このようなメールを識別する電子メールのスレッドします。</span><span class="sxs-lookup"><span data-stu-id="9c4be-p101">Consider an email conversation that has been going on for a while. In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread. Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="9c4be-106">電子メールのスレッドは何ですか。</span><span class="sxs-lookup"><span data-stu-id="9c4be-106">What does email threading do?</span></span>
<span data-ttu-id="9c4be-p102">各電子メールと desconstructs を解析して電子メールのスレッド、個々 のメッセージです。各電子メールは、個々 のメッセージのチェーンです。その後、メールに固有のコンテンツがあるかどうかまたは別の電子メールで完全にチェーンが含まれるかどうかを決定するワーキング セット内のすべての電子メールを分析します。最終的には、電子メールは、4 つのカテゴリに分けられます。</span><span class="sxs-lookup"><span data-stu-id="9c4be-p102">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages. Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email. In the end emails are divided into four categories:</span></span>
- <span data-ttu-id="9c4be-110">Inclusives: 電子メールの最後のメッセージは、一意のコンテンツと電子メールでは、どのコンテンツが完全に含まれるこの電子メールで他の電子メールに含まれていた添付ファイルのすべてです。</span><span class="sxs-lookup"><span data-stu-id="9c4be-110">Inclusives: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>
- <span data-ttu-id="9c4be-111">-包括的: 電子メールの最後のメッセージには、一意のコンテンツは、電子メールがどのコンテンツが完全に含まれるこの電子メールで他の電子メールに含まれていた添付ファイルのいくつか含まれていません。</span><span class="sxs-lookup"><span data-stu-id="9c4be-111">Inclusive minus: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>
- <span data-ttu-id="9c4be-112">包括的なコピー: 包括的または包含的-電子メールの正確なコピー</span><span class="sxs-lookup"><span data-stu-id="9c4be-112">Inclusive copy: an exact copy of an inclusive/inclusive minus email</span></span>
- <span data-ttu-id="9c4be-113">なし]: この電子メールの内容が完全に含まれると包括的で包括的なマイナスとしてマークされている 1 つ以上の電子メールで。</span><span class="sxs-lookup"><span data-stu-id="9c4be-113">None: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="9c4be-114">方法は、Outlook での会話とは異なるでしょうか。</span><span class="sxs-lookup"><span data-stu-id="9c4be-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="9c4be-p103">一目では、このサウンドの Outlook での会話のグループ化に非常に似ています。ただし、これにはいくつかの重要な違いがあります。2 つの会話にフォークを取得する電子メールの会話を検討してください。たとえば、他の一意のコンテンツを会話の最後の 2 つの電子メールが両方で最新の会話ではないメールに返信してください。</span><span class="sxs-lookup"><span data-stu-id="9c4be-p103">At a glance, this sounds very similar to conversation groupings in Outlook. However, there are some important distinctions. Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="9c4be-p104">Outlook は 1 つのテーマに電子メールをグループ化できます。最後のメールのみを読み取り中になります、ユニークなコンテンツが含まれる最後から 2 番目の電子メールのコンテキストがありません。電子メールのスレッド コンポーネントを個別に各電子メールを解析し、それらを比較してため、電子メールのスレッドは最後の 2 つの電子メールの両方としてマーク inclusives、描写が逃さない限り、すべてのメールを包括的にマークされているを参照することを確認します。</span><span class="sxs-lookup"><span data-stu-id="9c4be-p104">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content. Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>