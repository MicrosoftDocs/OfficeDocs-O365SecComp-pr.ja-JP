---
title: EOP でのエンドユーザー スパム通知の構成
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
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
description: エンド ユーザー向けスパム通知は、既定の会社全体のコンテンツ フィルター ポリシーに対して、またはドメインに適用されるカスタム コンテンツ フィルター ポリシーに対して構成できます。
ms.openlocfilehash: 990fa31cc22b33d235d6e8f106511996a52212a2
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002926"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="e2d9f-103">EOP でのエンドユーザー スパム通知の構成</span><span class="sxs-lookup"><span data-stu-id="e2d9f-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e2d9f-p101">このトピックは、Exchange オンライン保護 (EOP) スタンドアロンのお客様は、オンプレミスのメールボックスを保護することにします。クラウドでホストされているメールボックスを保護しているお客様は、Exchange のオンラインが代わりに次のトピックを読み取る必要があります:[構成のエンド ・ ユーザー スパム通知 Exchange オンライン](configure-end-user-spam-notifications-in-exchange-online.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p101">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes. Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="e2d9f-p102">エンド ユーザー向けスパム通知は、既定の会社全体のコンテンツ フィルター ポリシーに対して、またはドメインに適用されるカスタム コンテンツ フィルター ポリシーに対して構成できます。エンド ユーザー向けスパム通知メッセージを有効にすると、エンド ユーザーは自分のスパム検疫メッセージを自己管理することができます。エンド ユーザー向けスパム通知は、ユーザーまたはグループに適用されるポリシーや、例外が設定されたポリシーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="e2d9f-p103">エンド ユーザー向けスパム通知は、構成した期間 (1 ～ 15 日の間で指定可能) に、エンド ユーザーが受信したすべてのスパム検疫済みメッセージのリストを含みます。通知メッセージを記述する言語を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="e2d9f-111">通知メッセージを受け取ると、エンド ・ ユーザーが自分の受信トレイにスパム メールを移動する] をクリックしてまたは、迷惑メールを電子メールで送信されない迷惑メールとしてである場合、レポートは、マイクロソフトのスパム分析チームに送信されます。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e2d9f-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="e2d9f-112">What do you need to know before you begin?</span></span>
<span data-ttu-id="e2d9f-113"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="e2d9f-113"></span></span>

<span data-ttu-id="e2d9f-114">予想所要時間 : 5 分</span><span class="sxs-lookup"><span data-stu-id="e2d9f-114">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="e2d9f-p104">この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。必要なアクセス許可の一覧については、以下を参照してください。「[EOP の機能アクセス許可](eop/feature-permissions-in-eop.md)」トピックの「スパム対策」。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](eop/feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="e2d9f-117">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-117">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="e2d9f-118">EAC を使って、エンド ユーザー向けスパム通知を構成する</span><span class="sxs-lookup"><span data-stu-id="e2d9f-118">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="e2d9f-119">Exchange 管理センター (EAC) で、 **[保護]** \> **[コンテンツ フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-119">In the Exchange admin center (EAC), navigate to **Protection** \> **Content filter**.</span></span>
    
2. <span data-ttu-id="e2d9f-120">エンド ユーザー向けスパム通知で有効にするコンテンツ フィルター ポリシーを選択します (コンテンツ フィルター ポリシーは既定では無効です)。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-120">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="e2d9f-121">右側のウィンドウにポリシーに関する概要情報が表示されるので、 **[エンド ユーザーのスパム通知の構成]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-121">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="e2d9f-122">以降のダイアログ ボックスで、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-122">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="e2d9f-p105">**[エンド ユーザーのスパム通知を有効にする]** このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。(反対にこのポリシーを有効にすると、このチェック ボックスをオフにすることで、ポリシー用のエンド ユーザーのスパム通知を無効にすることができます。)</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="e2d9f-p106">**エンド ユーザーのスパム通知を～日ごとに送信** エンド ユーザーのスパム通知を送信する頻度を指定します。既定値は 3 日です。1 ～ 15 日の間で指定できます。たとえば 7 日間を指定した場合の通知には、直前の 7 日間のユーザー宛のメッセージのうち、スパム検疫に転送されたすべてのメッセージのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="e2d9f-129">**通知の言語** ドロップダウン リストを使用して、このポリシーにエンドユーザーのスパム通知の作成に使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-129">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="e2d9f-p107">**[保存]** をクリックします。エンドユーザーのスパム通知の設定を含む、コンテンツ フィルター ポリシー設定の概要が右ペインに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="e2d9f-p108">エンド ユーザー向けスパム通知は、有効なコンテンツ フィルター ポリシーに対してのみ機能します。 >  エンド ユーザーの迷惑メールの通知は、1 日 1 回だけ送信されます。特定のカスタマーについて通知の配信時間を保証することは不可能であり、設定もできません。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="e2d9f-p109">**ヒント:** エンド ユーザーのスパム通知を完全に実装する前に一部のユーザーに送信してテストする場合は、それらのユーザーが存在しているドメインでエンド ユーザーのスパム通知を有効にするカスタム コンテンツ フィルター ポリシーを作成します。その後、EAC の **[メール フロー] \> [ルール]** で quarantine@messaging.microsoft.com (通知を送信する電子メール アドレス) からのメッセージをブロックするトランスポート ルールを作成し、通知を送るユーザーを対象から除きます。下の図は、Contoso.com ドメインからの 2 人のユーザー (SaraD と AlexD) に対する例外を作成する例です。</span><span class="sxs-lookup"><span data-stu-id="e2d9f-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![エンド ユーザー向けスパム通知をテストするためのトランスポート ルール](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="e2d9f-139">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e2d9f-139">For more information</span></span>

[<span data-ttu-id="e2d9f-140">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="e2d9f-140">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
