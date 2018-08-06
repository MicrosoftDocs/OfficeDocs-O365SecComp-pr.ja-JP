---
title: Exchange Online エンドユーザースパム通知の構成
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: bfc91c73-a955-40e1-a95f-ad466624339a
description: エンドユーザーのスパム通知会社の迷惑メール フィルターの既定のポリシーやドメインに適用されるカスタムのスパム フィルター ポリシーを構成できます。
ms.openlocfilehash: 4a4c7c6b139fe0f8b0a1f6b69c1b95e321293af5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027534"
---
# <a name="configure-end-user-spam-notifications-in-exchange-online"></a><span data-ttu-id="5c66e-103">Exchange Online エンドユーザースパム通知の構成</span><span class="sxs-lookup"><span data-stu-id="5c66e-103">Configure end-user spam notifications in Exchange Online</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c66e-p101">このトピックでは、クラウドでホストされているメールボックスを保護しているお客様は、Exchange のオンラインにします。Exchange オンライン保護 (EOP) スタンドアロンのお客様は、オンプレミスのメールボックスを保護することが代わりに次トピックを参照する必要があります: [EOP でエンドユーザー スパム通知を構成](configure-end-user-spam-notifications-in-eop.md)します。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p101">This topic is for Exchange Online customers who are protecting cloud-hosted mailboxes. Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes should read the following topic instead: [Configure end-user spam notifications in EOP](configure-end-user-spam-notifications-in-eop.md).</span></span> 
  
<span data-ttu-id="5c66e-p102">エンドユーザーのスパム通知会社の迷惑メール フィルターの既定のポリシーやドメインに適用されるカスタムのスパム フィルター ポリシーを構成できます。エンド ・ ユーザーの迷惑メールの通知メッセージを有効にするには、スパム検疫されたメッセージは、独自の自己管理、エンド ・ ユーザーことができます。エンド ・ ユーザーの迷惑メールの通知は、ユーザーまたはグループ、または例外のポリシーを適用するポリシーを使用できません。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p102">You can configure end-user spam notifications for the default company-wide spam filter policy or for custom spam filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="5c66e-p103">エンド ユーザー向けスパム通知は、構成した期間 (1 ～ 15 日の間で指定可能) に、エンド ユーザーが受信したすべてのスパム検疫済みメッセージのリストを含みます。通知メッセージを記述する言語を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="5c66e-111">通知メッセージを受け取ると、エンド ・ ユーザーが自分の受信トレイにスパム メールを移動する] をクリックしてまたは、迷惑メールを電子メールで送信されない迷惑メールとしてである場合、レポートは、マイクロソフトのスパム分析チームに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5c66e-111">After receiving a notification message, end users can click to move the spam email to their inbox, or report the spam email as Not Junk, in which case it will be sent to the Microsoft Spam Analysis Team.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5c66e-112">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="5c66e-112">What do you need to know before you begin?</span></span>

<span data-ttu-id="5c66e-113">予想所要時間:2 分</span><span class="sxs-lookup"><span data-stu-id="5c66e-113">Estimated time to complete: 2 minutes</span></span>
  
<span data-ttu-id="5c66e-p104">このプロシージャまたはプロシージャを実行する前にアクセス許可を割り当てる必要があります。必要なアクセス許可については、 [Exchange のオンラインでの機能のアクセス許可](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)トピックの「スパム対策」エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="5c66e-116">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c66e-116">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="5c66e-117">EAC を使って、エンド ユーザー向けスパム通知を構成する</span><span class="sxs-lookup"><span data-stu-id="5c66e-117">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="5c66e-118">Exchange 管理センター (EAC) で、 **[保護]** \> **[スパム フィルター]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="5c66e-118">In the Exchange admin center (EAC), navigate to **Protection** \> **Spam filter**.</span></span>
    
2. <span data-ttu-id="5c66e-119">(既定で無効にされます) エンド ・ ユーザーの迷惑メール通知を有効にする迷惑メール フィルターのポリシーを選択します。</span><span class="sxs-lookup"><span data-stu-id="5c66e-119">Select the spam filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="5c66e-120">右側のウィンドウにポリシーに関する概要情報が表示されるので、 **[エンド ユーザーのスパム通知の構成]** リンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c66e-120">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="5c66e-121">以降のダイアログ ボックスで、次のオプションを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5c66e-121">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="5c66e-p105">**[エンド ユーザーのスパム通知を有効にする]** このポリシーでエンド ユーザーのスパム通知を有効にするには、このチェック ボックスをオンにします。(反対にこのポリシーを有効にすると、このチェック ボックスをオフにすることで、ポリシー用のエンド ユーザーのスパム通知を無効にすることができます。)</span><span class="sxs-lookup"><span data-stu-id="5c66e-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="5c66e-p106">**エンド ユーザーのスパム通知を～日ごとに送信** エンド ユーザーのスパム通知を送信する頻度を指定します。既定値は 3 日です。1 ～ 15 日の間で指定できます。たとえば 7 日間を指定した場合の通知には、直前の 7 日間のユーザー宛のメッセージのうち、スパム検疫に転送されたすべてのメッセージのリストが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="5c66e-128">**通知の言語** ドロップダウン リストを使用して、このポリシーにエンドユーザーのスパム通知の作成に使用する言語を選択します。</span><span class="sxs-lookup"><span data-stu-id="5c66e-128">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="5c66e-p107">[**保存**] をクリックします。右側のウィンドウで、迷惑メール フィルターを含むポリシー設定、エンド ・ ユーザーの迷惑メール通知設定の概要が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p107">Click **save**. A summary of your spam filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="5c66e-p108">エンド ・ ユーザーの迷惑メールの通知が有効になっているスパム フィルター ポリシーの機能のみをできます。> エンド ・ ユーザーの迷惑メールの通知は、1 日 1 回のみ送信されます。通知の配信時間は、どの特定の顧客に対して保証することはできませんしは構成できません。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p108">End-user spam notifications will only be functional for spam filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="5c66e-p109">**ヒント:** を完全に実装する前に、制限付きのユーザーに送信することによって、エンド ・ ユーザーの迷惑メールの通知をテストする場合は、ユーザーが存在するドメインのエンド ・ ユーザーの迷惑メール通知を有効にするカスタムのスパム フィルター ポリシーを作成します。その後、EAC で、[**メールの流れ\>ルール**、例外の通知を受信するユーザーのために quarantine@messaging.microsoft.com (通知を送信する電子メール アドレス) からのメッセージをブロックするトランスポート ルールを作成します。次の図では、Contoso.com のドメインから (SaraD と AlexD) の 2 つのユーザー用の例外を作成する例を示します。</span><span class="sxs-lookup"><span data-stu-id="5c66e-p109">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom spam filter policy that enables end-user spam notifications for the domains in which the users reside. Then, in the EAC, under **Mail flow \> rules**, create a transport rule to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications. The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![エンド ユーザー向けスパム通知をテストするためのトランスポート ルール](media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="5c66e-138">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5c66e-138">For more information</span></span>

[<span data-ttu-id="5c66e-139">スパム フィルター ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="5c66e-139">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
