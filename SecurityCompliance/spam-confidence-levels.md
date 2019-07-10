---
title: Spam Confidence Level
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
ms.openlocfilehash: beb322341f4d0de25d7bac9681c0beed93c48e5f
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35600877"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="35dcb-106">Spam Confidence Levels</span><span class="sxs-lookup"><span data-stu-id="35dcb-106">Spam confidence levels</span></span>

<span data-ttu-id="35dcb-p102">電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="35dcb-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="35dcb-111">**SCL 評価**</span><span class="sxs-lookup"><span data-stu-id="35dcb-111">**SCL Rating**</span></span>|<span data-ttu-id="35dcb-112">**スパム信頼度の解釈**</span><span class="sxs-lookup"><span data-stu-id="35dcb-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="35dcb-113">**既定のアクション**</span><span class="sxs-lookup"><span data-stu-id="35dcb-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35dcb-114">-1</span><span class="sxs-lookup"><span data-stu-id="35dcb-114">-1</span></span>|<span data-ttu-id="35dcb-115">安全な送信者、安全な受信者、または安全なリストの IP アドレス (信頼できるパートナー) から送られてくる非スパム。</span><span class="sxs-lookup"><span data-stu-id="35dcb-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner).</span></span>|<span data-ttu-id="35dcb-116">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="35dcb-116">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="35dcb-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="35dcb-117">0, 1</span></span>|<span data-ttu-id="35dcb-118">非スパムメッセージがスキャンされ、クリーンであると判断された場合。</span><span class="sxs-lookup"><span data-stu-id="35dcb-118">Non-spam because the message was scanned and determined to be clean.</span></span>|<span data-ttu-id="35dcb-119">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="35dcb-119">Deliver the message to the recipients' inbox.</span></span>|
|<span data-ttu-id="35dcb-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="35dcb-120">5, 6</span></span>|<span data-ttu-id="35dcb-121">スパム</span><span class="sxs-lookup"><span data-stu-id="35dcb-121">Spam</span></span>|<span data-ttu-id="35dcb-122">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="35dcb-122">Deliver the message to the recipients' Junk Email folder.</span></span>|
|<span data-ttu-id="35dcb-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="35dcb-123">7, 8, 9</span></span>|<span data-ttu-id="35dcb-124">信頼度の高いスパム</span><span class="sxs-lookup"><span data-stu-id="35dcb-124">High confidence spam</span></span>|<span data-ttu-id="35dcb-125">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="35dcb-125">Deliver the message to the recipients' Junk Email folder.</span></span>|
   
> [!TIP]
> <span data-ttu-id="35dcb-126">SCL ランク2、3、4、7、および8は、サービスによって設定されません。</span><span class="sxs-lookup"><span data-stu-id="35dcb-126">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service.</span></span> <span data-ttu-id="35dcb-127">SCL レベルが5または6の場合は、スパムの疑いがあると見なされます。これは、特定のスパムと見なされる SCL レベル9よりも短いスパムであると見なされます。</span><span class="sxs-lookup"><span data-stu-id="35dcb-127">An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam.</span></span> <span data-ttu-id="35dcb-128">Exchange 管理センターのコンテンツフィルターポリシーを使用して、スパムや信頼度の高いスパムに対するさまざまなアクションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="35dcb-128">Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="35dcb-129">詳細については、「 [スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35dcb-129">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> <span data-ttu-id="35dcb-130">「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」で説明されているように、メールフロールール (トランスポートルールとも呼ばれます) を使用して、特定の条件に一致するメッセージの SCL レベルを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="35dcb-130">You can also set the SCL rating for messages that match specific conditions by using mail flow rules (also known as transport rules), as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).</span></span> <span data-ttu-id="35dcb-131">メールフロールールを使用して、7、8、または9の SCL を設定すると、メッセージは信頼度の高いスパムとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="35dcb-131">If you use a mail flow rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="35dcb-p104">![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="35dcb-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span>|
   

