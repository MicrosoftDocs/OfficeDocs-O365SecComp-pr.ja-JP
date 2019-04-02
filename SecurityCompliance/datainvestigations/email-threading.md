---
title: 電子メールのスレッド化
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: ca4823ecfc06ddc0ef6f6840ad55fec492ac472c
ms.sourcegitcommit: 2c5834235c32b2616e1813ce24eeb3419a09629f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2019
ms.locfileid: "31030267"
---
# <a name="email-threading"></a><span data-ttu-id="e098a-102">電子メールのスレッド化</span><span class="sxs-lookup"><span data-stu-id="e098a-102">Email threading</span></span>

<span data-ttu-id="e098a-103">しばらくの間、電子メールでの会話を検討してください。</span><span class="sxs-lookup"><span data-stu-id="e098a-103">Consider an email conversation that has been going on for a while.</span></span> <span data-ttu-id="e098a-104">ほとんどの場合、スレッドの最後のメールには、先行するすべてのメールの内容が含まれます。最後のメールを確認すると、スレッドで発生した会話のコンテキストが完全にわかります。</span><span class="sxs-lookup"><span data-stu-id="e098a-104">In most cases, the last email on the thread will include the contents of all the preceding emails; reviewing the last email will give a complete context of the conversation that happened in the thread.</span></span> <span data-ttu-id="e098a-105">電子メールスレッドでは、このような電子メールを識別して、校閲者が収集されたドキュメントの一部をコンテキストを失わずに確認できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e098a-105">Email threading identifies such emails so that reviewers can review a fraction of collected documents without losing any context.</span></span>

## <a name="what-does-email-threading-do"></a><span data-ttu-id="e098a-106">電子メールスレッド処理の機能</span><span class="sxs-lookup"><span data-stu-id="e098a-106">What does email threading do?</span></span>

<span data-ttu-id="e098a-107">電子メールスレッドは各電子メールを解析し、個々のメッセージにコンストラクトを作成します。各電子メールは、個々のメッセージのチェインです。</span><span class="sxs-lookup"><span data-stu-id="e098a-107">Email threading parses each email and desconstructs it to individual messages; each email is a chain of individual messages.</span></span> <span data-ttu-id="e098a-108">次に、作業セット内のすべての電子メールを分析して、電子メールに固有のコンテンツがあるかどうか、またはチェーンが完全に別の電子メールに含まれているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="e098a-108">Then, it analyzes all emails in the working set to determine whether an email has unique content or if the chain is wholly contained in a different email.</span></span> <span data-ttu-id="e098a-109">エンドメールは、次の4つのカテゴリに分かれています。</span><span class="sxs-lookup"><span data-stu-id="e098a-109">In the end emails are divided into four categories:</span></span>

- <span data-ttu-id="e098a-110">**包括**: 電子メールの最後のメッセージに固有のコンテンツがあり、電子メールには、その電子メールに含まれているその他の電子メールに含まれていたすべての添付ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e098a-110">**Inclusive**: the last message in the email has unique content, and the email has all of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>


- <span data-ttu-id="e098a-111">**包括減算**: 電子メールの最後のメッセージには一意のコンテンツがありますが、この電子メールに含まれているその他の電子メールに含まれていた添付ファイルの一部が電子メールに含まれていません。</span><span class="sxs-lookup"><span data-stu-id="e098a-111">**Inclusive minus**: the last message in the email has unique content, but the email does not contain some of the attachments that were included in other emails of which the content is wholly contained in this email.</span></span>

- <span data-ttu-id="e098a-112">包括的**コピー**: 包括/包括型電子メールの正確なコピー</span><span class="sxs-lookup"><span data-stu-id="e098a-112">**Inclusive copy**: an exact copy of an inclusive/inclusive minus email</span></span>

- <span data-ttu-id="e098a-113">**None**: この電子メールの内容は、包括的/包括的なマイナスとしてマークされた少なくとも1つの電子メールに完全に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e098a-113">**None**: The content of this email is wholly contained in at least one email that is marked as inclusive/inclusive minus.</span></span>

## <a name="how-is-it-different-from-conversations-in-outlook"></a><span data-ttu-id="e098a-114">Outlook の会話とどのように異なるのですか?</span><span class="sxs-lookup"><span data-stu-id="e098a-114">How is it different from conversations in Outlook?</span></span>
<span data-ttu-id="e098a-115">このことは、Outlook での会話のグループ化とよく似ています。</span><span class="sxs-lookup"><span data-stu-id="e098a-115">At a glance, this sounds very similar to conversation groupings in Outlook.</span></span> <span data-ttu-id="e098a-116">ただし、いくつかの重要な違いがあります。</span><span class="sxs-lookup"><span data-stu-id="e098a-116">However, there are some important distinctions.</span></span> <span data-ttu-id="e098a-117">2つの会話にフォークされた電子メールの会話を検討します。たとえば、会話の最後の2通の電子メールにはそれぞれ固有のコンテンツがあるため、会話の最新の電子メールには応答していないユーザーがいます。</span><span class="sxs-lookup"><span data-stu-id="e098a-117">Consider an email conversation that got forked into two conversation; for instance, someone responded to an email that is not the latest in the conversation so the last two emails in the conversation both have unique content.</span></span>

<span data-ttu-id="e098a-118">Outlook は、電子メールを1つの会話にグループ化します。最後の電子メールのみを読み取ると、2番目から最後の電子メールのコンテキストが失われることになります。これには、一意のコンテンツが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e098a-118">Outlook would still group the emails into a single conversation; reading only the last email would mean missing the context of the second-to-last email, which also contains unique content.</span></span> <span data-ttu-id="e098a-119">電子メールスレッドは各電子メールを個別のコンポーネントに分解してそれらを比較するので、電子メールスレッドは最後の2つの電子メールの両方を inclusives としてマークします。これにより、すべての電子メールを包括的なものとしてマークされている限り、そのままの状態になります。</span><span class="sxs-lookup"><span data-stu-id="e098a-119">Because email threading parses out each email into individual components and compares them, email threading would mark both of the last two emails as inclusives, ensuring that you won't miss any context as long as you read all emails marked as inclusive.</span></span>