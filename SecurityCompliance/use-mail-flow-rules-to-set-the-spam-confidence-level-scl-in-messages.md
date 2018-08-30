---
title: メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 4ccab17a-6d49-4786-aa28-92fb28893e99
description: トランスポート ルールを作成して、電子メール メッセージの Spam Confidence Level (SCL) を設定できます。SCL は、メッセージがスパムである可能性がどの程度かを測定します。スパムとは、迷惑な (通常は不要な) 電子メール メッセージです。メッセージに対するアクションは、メッセージの SCL 評価によって異なります。たとえば、同僚からのメッセージはスパムでないと信頼できるため、社内ユーザーからのメッセージの場合はスパム コンテンツ フィルターをバイパスできます。トランスポート ルールを使用して電子メール メッセージの SCL 値を設定すると、スパムの制御を強化できます。
ms.openlocfilehash: 7abd0d1881374b1f2a4bd32ee480445f7683d1b3
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002896"
---
# <a name="use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages"></a><span data-ttu-id="11430-108">メール フロー ルールを使用して、メッセージの Spam Confidence Level (SCL) を設定する</span><span class="sxs-lookup"><span data-stu-id="11430-108">Use mail flow rules to set the spam confidence level (SCL) in messages</span></span>

<span data-ttu-id="11430-p102">トランスポート ルールを作成して、電子メール メッセージの Spam Confidence Level (SCL) を設定できます。SCL は、メッセージがスパムである可能性がどの程度かを測定します。スパムとは、迷惑な (通常は不要な) 電子メール メッセージです。メッセージに対するアクションは、メッセージの SCL 評価によって異なります。たとえば、同僚からのメッセージはスパムでないと信頼できるため、社内ユーザーからのメッセージの場合はスパム コンテンツ フィルターをバイパスできます。トランスポート ルールを使用して電子メール メッセージの SCL 値を設定すると、スパムの制御を強化できます。</span><span class="sxs-lookup"><span data-stu-id="11430-p102">You can create a transport rule that sets the spam confidence level (SCL) of an email message. The SCL is a measure of how likely a message is to be spam. Spam is unsolicited (and typically unwanted) email messages. The service takes different action on a message depending on its SCL rating. For example, you might want to bypass spam content filtering for messages that are sent from people inside your organization because you trust that a message sent internally from a colleague isn't spam. Using transport rules to set the SCL value of a message gives you increased control in handling spam.</span></span> 
  
 <span data-ttu-id="11430-115">**始める前に把握しておくべき情報**</span><span class="sxs-lookup"><span data-stu-id="11430-115">**What do you need to know before you begin?**</span></span>
  
- <span data-ttu-id="11430-116">この手順の予想所要時間:10 分。</span><span class="sxs-lookup"><span data-stu-id="11430-116">Estimated time to complete this procedure: 10 minutes.</span></span>
    
- <span data-ttu-id="11430-p103">このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、トランスポート ルール"のエントリ[で、Exchange のオンライン機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)または[EOP でアクセス許可の機能](eop/feature-permissions-in-eop.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11430-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) or [Feature permissions in EOP](eop/feature-permissions-in-eop.md).</span></span> 
    
- <span data-ttu-id="11430-119">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11430-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
### <a name="to-create-a-transport-rule-that-sets-the-scl-of-a-message"></a><span data-ttu-id="11430-120">トランスポート ルールを作成してメッセージの SCL を設定するには</span><span class="sxs-lookup"><span data-stu-id="11430-120">To create a transport rule that sets the SCL of a message</span></span>

1. <span data-ttu-id="11430-121">Exchange 管理センター (EAC) で、 **[メール フロー]** \> **[ルール]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="11430-121">In the Exchange admin center (EAC), choose **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="11430-122">**[新規作成]**![[追加] アイコン](media/ITPro-EAC-AddIcon.gif) を選択し、 **[新しいルールの作成]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="11430-122">Choose **New**![Add Icon](media/ITPro-EAC-AddIcon.gif), and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="11430-123">ルールの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="11430-123">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="11430-124">**[その他のオプション]** を選択し、 **[このルールを適用する条件]** で、このルールに設定するアクション (つまり、SCL 値の設定) をトリガーする条件を指定します。</span><span class="sxs-lookup"><span data-stu-id="11430-124">Choose **More options**, and then under **Apply this rule if**, specify a condition that will trigger the action you'll be setting for this rule (which is to set the SCL value).</span></span>
    
    <span data-ttu-id="11430-125">たとえば、 **[送信者]** \> **[外部/内部である]** を設定し、 **[送信者の場所の選択]** ダイアログ ボックスで **[組織内]**、 **[OK]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="11430-125">For example, you can set **The sender** \> **is internal/external**, and then in the **select sender location** dialog box, select **Inside the organization**, and choose **ok**.</span></span></br>
    <span data-ttu-id="11430-126">![送信者の場所の選択](media/EOP-ETR-SetSCL-1.jpg)</span><span class="sxs-lookup"><span data-stu-id="11430-126">![Select sender location](media/EOP-ETR-SetSCL-1.jpg)</span></span>
  
5. <span data-ttu-id="11430-127">**[実行する処理]** で、 **[メッセージのプロパティを変更する]** \> **[SCL (Spam Confidence Level) の設定]** の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="11430-127">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
  
6. <span data-ttu-id="11430-128">**[SCL の指定]** ダイアログ ボックスで、次の値のいずれかを選択し、 **[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="11430-128">In the **specify SCL** dialog box, select one of the following values, and choose **ok**:</span></span>
    
  - <span data-ttu-id="11430-129">**[スパム対策フィルターのバイパス]**: SCL が -1 に設定され、コンテンツ フィルターは実行されません。</span><span class="sxs-lookup"><span data-stu-id="11430-129">**Bypass spam filtering** - This sets the SCL to -1, which means that content filtering won't be performed.</span></span> 
    
  - <span data-ttu-id="11430-130">**0 ～ 4**: SCL をこれらの値のいずれかに設定すると、追加の処理のためにメッセージはコンテンツ フィルターに渡されます。</span><span class="sxs-lookup"><span data-stu-id="11430-130">**0-4** - When you set the SCL to one of these values, the message will be passed along to the content filter for additional processing.</span></span> 
    
  - <span data-ttu-id="11430-p104">**5、6**: SCL をこれらの値のいずれかに設定すると、適用可能なコンテンツ フィルター ポリシーに指定された **[スパム]** のアクションが適用されます。既定では、メッセージは受信者の迷惑メール フォルダーに送られます。</span><span class="sxs-lookup"><span data-stu-id="11430-p104">**5, 6** - When you set the SCL to one of these values, the action specified for **Spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
  - <span data-ttu-id="11430-p105">**7 ～ 9**: SCL をこれらの値のいずれかに設定すると、適用可能なコンテンツ フィルター ポリシーに指定された **[精度の高いスパム]** のアクションが適用されます。既定では、メッセージは受信者の迷惑メール フォルダーに送られます。</span><span class="sxs-lookup"><span data-stu-id="11430-p105">**7-9** - When you set the SCL to one of these values, the action specified for **High confidence spam** in the applicable content filter policies will be applied. By default, the action is to send the message to the recipient's Junk Email folder.</span></span> 
    
    <span data-ttu-id="11430-p106">コンテンツ フィルター ポリシーの構成の詳細については、「[スパム フィルター ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。サービスの SCL 値の詳細については、「[Spam Confidence Level](spam-confidence-levels.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11430-p106">For more information about configuring your content filter policies, see [Configure your spam filter policies](configure-your-spam-filter-policies.md). For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
7. <span data-ttu-id="11430-137">ルールのその他のプロパティを指定し、 **[保存]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="11430-137">Specify additional properties for the rule, and choose **save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="11430-138">このルールで選択または指定できるその他のプロパティの詳細については、「[Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11430-138">For more information about the additional properties you can select or specify for this rule, see [Use the EAC to create a transport rule](http://technet.microsoft.com/library/e7a81372-b6d7-4d1f-bc9e-a845a7facac2.aspx#CreateEAC).</span></span> 
  
## <a name="how-do-you-know-this-worked"></a><span data-ttu-id="11430-139">正常な動作を確認する方法</span><span class="sxs-lookup"><span data-stu-id="11430-139">How do you know this worked?</span></span>

<span data-ttu-id="11430-p107">この処理が正常に動作することを確認するには、組織内のユーザーに電子メール メッセージを送信し、必要なアクションがメッセージに対して実行されたかどうかを確認します。たとえば、 **[SCL (Spam Confidence Level) の設定]** を **[スパム対策フィルターのバイパス]** に設定した場合、メッセージは指定された受信者の受信トレイに送信される必要があります。また、 **[SCL (Spam Confidence Level) の設定]** を **9** に設定し、適用可能なコンテンツ フィルター ポリシーの **[精度の高いスパム]** に対するアクションが迷惑メール フォルダーへのメッセージの送信である場合、メッセージは指定された受信者の迷惑メール フォルダーに送られる必要があります。</span><span class="sxs-lookup"><span data-stu-id="11430-p107">To verify that this procedure is working correctly, send an email message to someone inside your organization, and verify that the action performed on the message is as expected. For example, if you **set the spam confidence level (SCL)** to **Bypass spam filtering**, then the message should be sent to the specified recipient's inbox. However, if you **set the spam confidence level (SCL)** to **9**, and the **High confidence spam** action for your applicable content filter policies is to move the message to the Junk Email folder, then the message should be sent to the specified recipient's Junk Email folder.</span></span> 
  

