---
title: Spam Confidence Level
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 10/2/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: 電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。
ms.openlocfilehash: 1822fa50f9815397513fddf7a2024a99277cbb28
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275647"
---
# <a name="spam-confidence-levels"></a><span data-ttu-id="e08f6-106">Spam Confidence Level</span><span class="sxs-lookup"><span data-stu-id="e08f6-106">Spam confidence levels</span></span>

<span data-ttu-id="e08f6-p102">電子メール メッセージがスパム フィルターを通過すると、その電子メール メッセージにはスパム スコアが割り当てられます。そのスコアは個別の Spam Confidence Level (SCL) 評価にマップされ、X-ヘッダーにスタンプされます。サービスは SCL 評価のスパム信頼度の解釈を基に、メッセージに対してアクションを実施します。次の表は、さまざまな SCL 評価がフィルターによって解釈される方法、および評価ごとに受信メッセージに対して実行される既定のアクションを示しています。</span><span class="sxs-lookup"><span data-stu-id="e08f6-p102">When an email message goes through spam filtering it is assigned a spam score. That score is mapped to an individual Spam Confidence Level (SCL) rating and stamped in an X-header. The service takes actions upon the messages depending upon the spam confidence interpretation of the SCL rating. The following table shows how the different SCL ratings are interpreted by the filters and the default action that is taken on inbound messages for each rating.</span></span>
  
|<span data-ttu-id="e08f6-111">**SCL 評価**</span><span class="sxs-lookup"><span data-stu-id="e08f6-111">**SCL Rating**</span></span>|<span data-ttu-id="e08f6-112">**スパム信頼度の解釈**</span><span class="sxs-lookup"><span data-stu-id="e08f6-112">**Spam Confidence Interpretation**</span></span>|<span data-ttu-id="e08f6-113">**既定のアクション**</span><span class="sxs-lookup"><span data-stu-id="e08f6-113">**Default Action**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e08f6-114">-1</span><span class="sxs-lookup"><span data-stu-id="e08f6-114">-1</span></span>  <br/> |<span data-ttu-id="e08f6-115">安全な送信者、安全な受信者、安全であると表示されている IP アドレス (信頼できるパートナー) からのメッセージであり、スパムではない</span><span class="sxs-lookup"><span data-stu-id="e08f6-115">Non-spam coming from a safe sender, safe recipient, or safe listed IP address (trusted partner)</span></span>  <br/> |<span data-ttu-id="e08f6-116">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="e08f6-116">Deliver the message to the recipients' inbox.</span></span>  <br/> |
|<span data-ttu-id="e08f6-117">0, 1</span><span class="sxs-lookup"><span data-stu-id="e08f6-117">0, 1</span></span>  <br/> |<span data-ttu-id="e08f6-118">メッセージがスキャンされ、クリーンであると判断されたため、スパムではない</span><span class="sxs-lookup"><span data-stu-id="e08f6-118">Non-spam because the message was scanned and determined to be clean</span></span>  <br/> |<span data-ttu-id="e08f6-119">受信者の受信トレイにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="e08f6-119">Deliver the message to the recipients' inbox.</span></span>  <br/> |
|<span data-ttu-id="e08f6-120">5, 6</span><span class="sxs-lookup"><span data-stu-id="e08f6-120">5, 6</span></span>  <br/> | <span data-ttu-id="e08f6-121">スパム</span><span class="sxs-lookup"><span data-stu-id="e08f6-121">Spam</span></span>  <br/> |<span data-ttu-id="e08f6-122">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="e08f6-122">Deliver the message to the recipients' Junk Email folder.</span></span>  <br/> |
|<span data-ttu-id="e08f6-123">7, 8, 9</span><span class="sxs-lookup"><span data-stu-id="e08f6-123">7, 8, 9</span></span>  <br/> |<span data-ttu-id="e08f6-124">信頼度の高いスパム</span><span class="sxs-lookup"><span data-stu-id="e08f6-124">High confidence spam</span></span>  <br/> |<span data-ttu-id="e08f6-125">受信者の迷惑メール フォルダーにメッセージを配信します。</span><span class="sxs-lookup"><span data-stu-id="e08f6-125">Deliver the message to the recipients' Junk Email folder.</span></span>  <br/> |
   
> [!TIP]
> <span data-ttu-id="e08f6-p103">SCL ランク2、3、4、7、および8は、サービスによって設定されません。scl レベルが5または6の場合は、スパムの疑いがあると見なされます。これは、特定のスパムと見なされる scl レベル9よりも短いスパムであると見なされます。Exchange 管理センターのコンテンツフィルターポリシーを使用して、スパムや信頼度の高いスパムに対するさまざまなアクションを構成できます。詳細については、「[スパムフィルターポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。「[メールフロールールを使用してメッセージにスパム信頼レベル (SCL) を設定する](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md)」の説明に従って、トランスポートルールを使用して、特定の条件に一致するメッセージの SCL レベルを設定することもできます。トランスポートルールを使用して、7、8、または9の SCL を設定すると、メッセージは信頼度の高いスパムとして処理されます。</span><span class="sxs-lookup"><span data-stu-id="e08f6-p103">SCL ratings of 2, 3, 4, 7, and 8 are not set by the service. An SCL rating of 5 or 6 is considered suspected spam, which is less certain to be spam than an SCL rating of 9, which is considered certain spam. Different actions for spam and high confidence spam can be configured via your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). You can also set the SCL rating for messages that match specific conditions by using Transport rules, as described in [Use mail flow rules to set the spam confidence level (SCL) in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md). If you use a transport rule to set SCL of 7, 8, or 9 the message will be treated as high confidence spam.</span></span> 
  
||
|:-----|
|<span data-ttu-id="e08f6-p104">![LinkedIn Learning の小さいアイコン](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Office 365 を初めて使用する場合は、**         LinkedIn Learning が提供する **Office 365 admins and IT pros** のための無料のビデオ コースをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e08f6-p104">![The short icon for LinkedIn Learning](media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **New to Office 365?**         Discover free video courses for **Office 365 admins and IT pros**, brought to you by LinkedIn Learning.</span></span> |
   

