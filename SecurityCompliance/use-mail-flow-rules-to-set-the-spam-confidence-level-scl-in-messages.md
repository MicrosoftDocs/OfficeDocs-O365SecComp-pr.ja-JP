---
title: メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection でメッセージの SCL を設定する方法について説明します。
ms.openlocfilehash: c997f321ed14cddfa430c43e6de42f36934c642b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/17/2019
ms.locfileid: "34157969"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="58a82-103">メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する</span><span class="sxs-lookup"><span data-stu-id="58a82-103">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="58a82-104">電子メールメッセージのスパム信頼レベル (SCL) を設定するメールフロールール (トランスポートルールとも呼ばれます) を作成できます。</span><span class="sxs-lookup"><span data-stu-id="58a82-104">You can create a mail flow rule (also known as a transport rule) that sets the spam confidence level (SCL) of an email message.</span></span> <span data-ttu-id="58a82-105">SCL は、メッセージがスパムである可能性がどの程度かを測定します。</span><span class="sxs-lookup"><span data-stu-id="58a82-105">The SCL is a measure of how likely a message is to be spam.</span></span> <span data-ttu-id="58a82-106">スパムとは、迷惑な (通常は不要な) 電子メール メッセージです。</span><span class="sxs-lookup"><span data-stu-id="58a82-106">Spam is unsolicited (and typically unwanted) email messages.</span></span> <span data-ttu-id="58a82-107">メッセージに対するアクションは、メッセージの SCL 評価によって異なります。</span><span class="sxs-lookup"><span data-stu-id="58a82-107">The service takes different action on a message depending on its SCL rating.</span></span> <span data-ttu-id="58a82-108">たとえば、同僚からのメッセージはスパムでないと信頼できるため、社内ユーザーからのメッセージの場合はスパム コンテンツ フィルターをバイパスできます。</span><span class="sxs-lookup"><span data-stu-id="58a82-108">For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam.</span></span> <span data-ttu-id="58a82-109">メールフロールールを使用してメッセージの SCL 値を設定すると、スパムの処理の制御が強化されます。</span><span class="sxs-lookup"><span data-stu-id="58a82-109">Using mail flow rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="58a82-110">**始める前に把握しておくべき情報**</span><span class="sxs-lookup"><span data-stu-id="58a82-110">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="58a82-111">この手順の予想所要時間:10 分。</span><span class="sxs-lookup"><span data-stu-id="58a82-111">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="58a82-112">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a82-112">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="58a82-113">必要なアクセス許可については、「 [Exchange Online の機能のアクセス](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)許可」の「メールフロールール」、または「 [EOP の機能のアクセス許可](eop/feature-permissions-in-eop.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a82-113">To see what permissions you need, see the "Mail flow rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="58a82-114">このトピックの手順で使用可能なキーボード ショートカットについては、「**Exchange 管理センターのキーボード ショートカット**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a82-114">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="58a82-115">メッセージの SCL を設定するメールフロールールを作成するには</span><span class="sxs-lookup"><span data-stu-id="58a82-115">To create a mail flow rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="58a82-116">Exchange 管理センター (EAC) で、 **[メール フロー]** \> **[ルール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58a82-116">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="58a82-117">**[新規作成]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) を選択し、 **[新しいルールの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58a82-117">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="58a82-118">ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="58a82-118">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="58a82-119">**[その他のオプション]** を選択し、 **[このルールを適用する条件]** で、このルールに設定するアクション (つまり、SCL 値の設定) をトリガーする条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="58a82-119">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="58a82-120">たとえば、 **[送信者]** \> **[外部/内部である]** を設定し、 **[送信者の場所の選択]** ダイアログ ボックスで **[組織内]**、 **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="58a82-120">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span><br/>
    <span data-ttu-id="58a82-121">![送信者の場所の選択](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="58a82-121">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="58a82-122">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="58a82-122">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="58a82-123">**[SCL の指定]** ダイアログ ボックスで、次の値のいずれかを選択し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58a82-123">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="58a82-124">**[スパム対策フィルターのバイパス]**: SCL が -1 に設定され、コンテンツ フィルターは実行されません。</span><span class="sxs-lookup"><span data-stu-id="58a82-124">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="58a82-125">**0 ～ 4**: SCL をこれらの値のいずれかに設定すると、追加の処理のためにメッセージはコンテンツ フィルターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="58a82-125">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="58a82-p103">**5、6**: SCL をこれらの値のいずれかに設定すると、適用可能なコンテンツ フィルター ポリシーに指定された **[スパム]** のアクションが適用されます。既定では、メッセージは受信者の迷惑メール フォルダーに送られます。</span><span class="sxs-lookup"><span data-stu-id="58a82-p103">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="58a82-p104">**7 ～ 9**: SCL をこれらの値のいずれかに設定すると、適用可能なコンテンツ フィルター ポリシーに指定された **[精度の高いスパム]** のアクションが適用されます。既定では、メッセージは受信者の迷惑メール フォルダーに送られます。</span><span class="sxs-lookup"><span data-stu-id="58a82-p104">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="58a82-p105">コンテンツ フィルター ポリシーの構成の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a82-p105">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="58a82-132">ルールのその他のプロパティを指定し、 **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="58a82-132">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="58a82-133">このルールで選択または指定できるその他のプロパティの詳細については、「 [EAC を使用してメールフロールールを作成する](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="58a82-133">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures#use-the-eac-to-create-mail-flow-rules).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="58a82-134">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="58a82-134">How do you know this worked?</span></span>

<span data-ttu-id="58a82-p106">この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。また、 **[SCL (Spam Confidence Level) の設定]** を **9** に設定し、適用可能なコンテンツ フィルター ポリシーの **[精度の高いスパム]** に対するアクションが迷惑メール フォルダーへのメッセージの送信である場合、メッセージは指定された受信者の迷惑メール フォルダーに送られる必要があります。</span><span class="sxs-lookup"><span data-stu-id="58a82-p106">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

