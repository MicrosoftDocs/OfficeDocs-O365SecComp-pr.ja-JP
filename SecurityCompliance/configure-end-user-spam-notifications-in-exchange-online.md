---
title: Exchange Online エンドユーザースパム通知の構成
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
ms.collection:
- M365-security-compliance
description: 既定の企業全体のスパムフィルターポリシーまたはドメインに適用されるカスタムスパムフィルターポリシーに対して、エンドユーザーのスパム通知を構成できます。
ms.openlocfilehash: 00ce151ab355efb419d483a17aaeeb26dfc71c0d
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36699282"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="3b00d-103">Exchange Online エンドユーザースパム通知の構成</span><span class="sxs-lookup"><span data-stu-id="3b00d-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b00d-104">このトピックはクラウドでホストされたメールボックスを保護している Exchange Online のお客様を対象としています。</span><span class="sxs-lookup"><span data-stu-id="3b00d-104">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes.</span></span> <span data-ttu-id="3b00d-105">オンプレミスのメールボックスを保護している Exchange Online Protection (EOP) スタンドアロンのお客様は、代わりに次のトピックを参照してください。 [EOP でエンドユーザーのスパム通知を構成](configure-end-user-spam-notifications-in-eop.md)します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-105">Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="3b00d-106">既定の企業全体のスパムフィルターポリシーまたはドメインに適用されるカスタムスパムフィルターポリシーに対して、エンドユーザーのスパム通知を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-106">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains.</span></span> <span data-ttu-id="3b00d-107">エンド ユーザー向けスパム通知メッセージを有効にすると、エンド ユーザーは自分のスパム検疫メッセージを自己管理することができます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-107">Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages.</span></span> <span data-ttu-id="3b00d-108">エンド ユーザー向けスパム通知は、ユーザーまたはグループに適用されるポリシーや、例外が設定されたポリシーでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="3b00d-108">End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="3b00d-p103">エンド ユーザー向けスパム通知は、構成した期間 (1 ～ 15 日の間で指定可能) に、エンド ユーザーが受信したすべてのスパム検疫済みメッセージのリストを含みます。通知メッセージを記述する言語を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="3b00d-111">通知メッセージを受信すると、エンドユーザーは次のオプションから選択できます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="3b00d-112">アクションを実行する前にコンテンツまたはヘッダーをプレビューしたい場合は、メッセージを**プレビュー**してください。</span><span class="sxs-lookup"><span data-stu-id="3b00d-112">**Preview** the message if you would like to preview the content or header prior to taking action.</span></span>

<span data-ttu-id="3b00d-113">アクションを実行する前に、デバイスのメッセージと添付ファイル (存在する場合) を確認したい場合は、メッセージを**ダウンロード**してください。</span><span class="sxs-lookup"><span data-stu-id="3b00d-113">**Download** the message if you would like to review the message and attachments (if any) on your device prior to taking action.</span></span>

<span data-ttu-id="3b00d-114">メッセージがスパムではなく、Office 365 がメールボックスにメッセージを送信する場合は、**リリースを解放**します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-114">**Release** if the message isn’t spam and you want Office 365 to send the message to your mailbox.</span></span>

<span data-ttu-id="3b00d-115">**Release &** メッセージがスパムではない場合に送信者に送信を許可し、今後の電子メールに対応するように Office 365 で [差出人セーフリスト] と [受信者] 一覧に送信者を追加します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-115">**Release & Allow Sender** if the message isn’t spam and you want Office 365 to add the sender to your safe senders and recipients list for future emails.</span></span> <span data-ttu-id="3b00d-116">管理者には、[信頼できる差出人のリスト] を上書きする、組織全体にわたる許可/ブロック構成が存在する可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="3b00d-116">Keep in mind that your admin may have other organization wide allow/block configurations that override your safe sender list.</span></span>

<span data-ttu-id="3b00d-117">メッセージがスパムではなく、メールボックスにメッセージを送信して分析のために Microsoft に報告する場合は **& レポートをリリース**します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-117">**Release & Report**, if the message isn’t spam and you want to send the message to your mailbox and report it to Microsoft for analysis.</span></span>

<span data-ttu-id="3b00d-118">Office 365 で、受信拒否リストに送信者を追加する場合は、[**ブロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-118">**Block** if you want Office 365 to add the sender to your blocked senders list.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3b00d-119">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="3b00d-119">What do you need to know before you begin?</span></span>

<span data-ttu-id="3b00d-120">予想所要時間:2 分</span><span class="sxs-lookup"><span data-stu-id="3b00d-120">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="3b00d-121">「この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b00d-121">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="3b00d-122">必要なアクセス許可を確認するには、「 [Exchange Online の機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)」トピックの「スパム対策」のエントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b00d-122">To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="3b00d-123">このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b00d-123">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="3b00d-124">EAC を使って、エンド ユーザー向けスパム通知を構成する</span><span class="sxs-lookup"><span data-stu-id="3b00d-124">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="3b00d-125">Exchange 管理センター (EAC) で、 **[保護]** \> **[スパム フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-125">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="3b00d-126">エンドユーザーのスパム通知を有効にするスパムフィルターポリシーを選択します (既定では無効になっています)。</span><span class="sxs-lookup"><span data-stu-id="3b00d-126">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="3b00d-127">右側のウィンドウにポリシーに関する概要情報が表示されるので、**[エンド ユーザーのスパム通知の構成]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b00d-127">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="3b00d-128">以降のダイアログ ボックスで、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-128">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="3b00d-p106">**[エンド ユーザーのスパム通知を有効にする]** このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。(反対にこのポリシーを有効にすると、このチェック ボックスをオフにすることで、ポリシー用のエンド ユーザーのスパム通知を無効にすることができます。)</span><span class="sxs-lookup"><span data-stu-id="3b00d-p106">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="3b00d-p107">**エンド ユーザーのスパム通知を～日ごとに送信** エンド ユーザーのスパム通知を送信する頻度を指定します。既定値は 3 日です。1 ～ 15 日の間で指定できます。たとえば 7 日間を指定した場合の通知には、直前の 7 日間のユーザー宛のメッセージのうち、スパム検疫に転送されたすべてのメッセージのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-p107">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="3b00d-135">**通知の言語** ドロップダウン リストを使用して、このポリシーにエンドユーザーのスパム通知の作成に使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-135">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="3b00d-136">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b00d-136">Click **save**.</span></span> <span data-ttu-id="3b00d-137">エンドユーザーのスパム通知の設定を含む、スパムフィルターポリシー設定の概要が右側のウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-137">A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="3b00d-138">エンドユーザーのスパム通知は、有効になっているスパムフィルターポリシーに対してのみ機能します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-138">End-user spam notifications will only be functional for spam filter policies that are enabled.</span></span> <span data-ttu-id="3b00d-139">>  エンド ユーザーの迷惑メールの通知は、1 日 1 回だけ送信されます。</span><span class="sxs-lookup"><span data-stu-id="3b00d-139">>  End-user spam notifications are only sent once per day.</span></span> <span data-ttu-id="3b00d-140">特定のカスタマーについて通知の配信時間を保証することは不可能であり、設定もできません。</span><span class="sxs-lookup"><span data-stu-id="3b00d-140">The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="3b00d-141">**ヒント:** エンドユーザーのスパム通知を完全に実装する前に限定された一連のユーザーに送信してテストする場合は、ユーザーが存在するドメインに対してエンドユーザーのスパム通知を有効にするカスタムスパムフィルターポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-141">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="3b00d-142">次に、EAC の [**メールフロー \>ルール**] で、メールフロールール (トランスポートルールとも呼ばれます) を作成して、必要なユーザーの例外を除き、quarantine@messaging.microsoft.com (通知を送信する電子メールアドレス) からのメッセージをブロックします。通知を受信します。</span><span class="sxs-lookup"><span data-stu-id="3b00d-142">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="3b00d-143">下の図は、Contoso.com ドメインからの 2 人のユーザー (SaraD と AlexD) に対する例外を作成する例です。</span><span class="sxs-lookup"><span data-stu-id="3b00d-143">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![エンド ユーザー向けスパム通知をテストするためのトランスポート ルール](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="3b00d-145">関連情報</span><span class="sxs-lookup"><span data-stu-id="3b00d-145">For more information</span></span>

[<span data-ttu-id="3b00d-146">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="3b00d-146">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
