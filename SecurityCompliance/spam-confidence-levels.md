---
title: Spam Confidence Level
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
description: 電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
ms.openlocfilehash: cd33f440828761ab8cb496d9eff07288d974514c
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026284"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="55d4f-106">Spam Confidence Level</span><span class="sxs-lookup"><span data-stu-id="55d4f-106">Spam confidence levels</span></span>

<span data-ttu-id="55d4f-p102">電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="55d4f-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="55d4f-111">**SCL 評価**</span><span class="sxs-lookup"><span data-stu-id="55d4f-111">**SCL Rating**</span></span>|<span data-ttu-id="55d4f-112">**スパム信頼度の解釈**</span><span class="sxs-lookup"><span data-stu-id="55d4f-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="55d4f-113">**既定のアクション**</span><span class="sxs-lookup"><span data-stu-id="55d4f-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="55d4f-114">-1</span><span class="sxs-lookup"><span data-stu-id="55d4f-114">-1</span></span>  <br/> |<span data-ttu-id="55d4f-115">安全な送信者、安全な受信者、安全であると表示されている IP アドレス (信頼できるパートナー) からのメッセージであり、スパムではない</span><span class="sxs-lookup"><span data-stu-id="55d4f-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner)</span></span>  <br/> |<span data-ttu-id="55d4f-116">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="55d4f-116">Deliver the message to the recipients' inbox.</span></span>  <br/> |
|<span data-ttu-id="55d4f-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="55d4f-117">0, 1</span></span>  <br/> |<span data-ttu-id="55d4f-118">メッセージがスキャンされ、クリーンであると判断されたため、スパムではない</span><span class="sxs-lookup"><span data-stu-id="55d4f-118">Non-spam because the message was scanned and determined to be clean</span></span>  <br/> |<span data-ttu-id="55d4f-119">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="55d4f-119">Deliver the message to the recipients' inbox.</span></span>  <br/> |
|<span data-ttu-id="55d4f-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="55d4f-120">5, 6</span></span>  <br/> | <span data-ttu-id="55d4f-121">スパム</span><span class="sxs-lookup"><span data-stu-id="55d4f-121">Spam</span></span>  <br/> |<span data-ttu-id="55d4f-122">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="55d4f-122">Deliver the message to the recipients' Junk Email folder.</span></span>  <br/> |
|<span data-ttu-id="55d4f-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="55d4f-123">7, 8, 9</span></span>  <br/> |<span data-ttu-id="55d4f-124">信頼度の高いスパム</span><span class="sxs-lookup"><span data-stu-id="55d4f-124">High confidence spam</span></span>  <br/> |<span data-ttu-id="55d4f-125">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="55d4f-125">Deliver the message to the recipients' Junk Email folder.</span></span>  <br/> |
   
> [!TIP]
> <span data-ttu-id="55d4f-p103">サービスでは、2、3、4、7、および 8 の scl は設定されていません。5 または 6 の SCL レベルより特定の迷惑メールとみなされ、9 の SCL レベルのスパムである保証は、疑いのある迷惑メールと見なされます。スパムと精度の高いスパムの別のアクションは、Exchange 管理センターでコンテンツ フィルター ポリシーを使用して構成できます。詳細については、[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)を参照してください。[メッセージでスパム信頼レベル (SCL) を設定するのにはメールの流れの規則を使用する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)で説明するようトランスポート ルールを使用して特定の条件に一致するメッセージの SCL レベルを設定することもできます。7、8、または 9 の SCL が設定するのにはトランスポート ルールを使用する場合、メッセージは精度の高い迷惑メールとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="55d4f-p103">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service. An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam. Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). You can also set the SCL rating for messages that match specific conditions by using Transport rules, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). If you use a transport rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="55d4f-p104">![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="55d4f-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   

