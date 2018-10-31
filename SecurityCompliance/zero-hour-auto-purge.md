---
title: ゼロアワー自動消去 - 迷惑メールやマルウェアからの保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/9/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: ゼロの自動パージ (ZAP) は既にユーザーの受信トレイに配信されたメッセージをスパムやマルウェアを検出する電子メールの保護機能で、害のない、悪意のあるコンテンツをレンダリングZAP はこれは、検出された、悪意のあるコンテンツの種類によって異なります。
ms.openlocfilehash: dabe4caf8916d3f0de7a70cb3d056dd9a7fdcc3f
ms.sourcegitcommit: ceb70ea863d8b97afea077a04fc7ec612b870695
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "25857245"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="87701-104">ゼロアワー自動消去 - 迷惑メールやマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="87701-104">Zero-hour auto purge - protection against spam and malware</span></span>

<span data-ttu-id="87701-p102">ゼロの自動パージ (ZAP) は既にユーザーの受信トレイに配信されたメッセージをスパムやマルウェアを検出する電子メールの保護機能で、害のない、悪意のあるコンテンツをレンダリングZAP はこれは、検出された、悪意のあるコンテンツの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="87701-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with spam or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected.</span></span>
  
<span data-ttu-id="87701-107">ZAP は、既定の Exchange Online のメールボックスを含むすべての Office 365 サブスクリプションに含まれている Exchange のオンライン保護に使用できます。</span><span class="sxs-lookup"><span data-stu-id="87701-107">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>
  
## <a name="how-does-zap-work"></a><span data-ttu-id="87701-108">ZAP の動作方法</span><span class="sxs-lookup"><span data-stu-id="87701-108">How does ZAP work?</span></span>

<span data-ttu-id="87701-p103">Office 365 のスパム対策エンジンおよびマルウェアのシグネチャを更新する毎日のようにリアルタイムです。ただし、ユーザーは悪意のあるメッセージをさまざまな理由から、コンテンツがユーザーに最初に配信された後に後でを含む受信トレイに配信をする可能性が残っています。ZAP アドレスを継続的に監視することによってこれを Office 365 のスパムやマルウェアの署名を更新できますしたがって検索し、受信トレイに配信されるメッセージを既に削除します。スパムとして既に認識されているメールでは、ZAP は未読メ ッ セージをユーザーの迷惑メール フォルダーに移動します。新たに検出されたマルウェアが、ZAP はメールかに読み取られたかどうかに関係なく、電子メール メッセージから添付ファイルを削除します。逆では正しく分類されたない、悪意のあるメッセージの場合は true です。</span><span class="sxs-lookup"><span data-stu-id="87701-p103">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including when the content was weaponized at a time after it was first delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures, and can therefore find and remove previously delivered messages already in inboxes. For mail that was already identified as spam, ZAP moves unread messages to the user's Junk mail folder. For newly detected malware, ZAP removes the attachments from the email message, regardless of whether the mail was read or not. The reverse is true for messages that were incorrectly classified as malicious.</span></span>
  
<span data-ttu-id="87701-115">ZAP アクションは、メールボックス ユーザー、そのユーザーに通知されていないメールが移動されているために、シームレスです。</span><span class="sxs-lookup"><span data-stu-id="87701-115">The ZAP action is seamless for the mailbox user, he or she is not notified the mail has been moved.</span></span>
  
<span data-ttu-id="87701-116">リスト、[メール フローの規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)、およびエンド ・ ユーザーの規則を許可するか、追加フィルター ZAP よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="87701-116">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
 <span data-ttu-id="87701-117">**この記事の内容**</span><span class="sxs-lookup"><span data-stu-id="87701-117">**In this article:**</span></span>
  
> [<span data-ttu-id="87701-118">スパム フィルター ポリシーを設定します。</span><span class="sxs-lookup"><span data-stu-id="87701-118">Set spam filter policy</span></span>](zero-hour-auto-purge.md#BK_SetSpam)
    
> [<span data-ttu-id="87701-119">ZAP がメッセージを移動するかどうかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87701-119">See if ZAP moved your message</span></span>](zero-hour-auto-purge.md#BK_DidZAPMove)
    
> [<span data-ttu-id="87701-120">ZAP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="87701-120">Disable ZAP</span></span>](zero-hour-auto-purge.md#BK_Posh)
    
> [<span data-ttu-id="87701-121">FAQ</span><span class="sxs-lookup"><span data-stu-id="87701-121">FAQ</span></span>](zero-hour-auto-purge.md#BK_FAQ)
    
## <a name="working-with-zap"></a><span data-ttu-id="87701-122">ZAP での作業</span><span class="sxs-lookup"><span data-stu-id="87701-122">Working with ZAP</span></span>

<span data-ttu-id="87701-123">ZAP が既定でオンですが、いくつかの条件が満たされているかどうかを確認する必要は。</span><span class="sxs-lookup"><span data-stu-id="87701-123">ZAP is turned on by default, but you do have to make sure a couple of conditions are met:</span></span>
  
- <span data-ttu-id="87701-124">[[迷惑メール フォルダーにメッセージを移動](zero-hour-auto-purge.md#BK_SetSpam)するのには、迷惑メール フィルターのポリシーが設定されています。</span><span class="sxs-lookup"><span data-stu-id="87701-124">Spam filter policy is set to [Move message to Junk Email folder](zero-hour-auto-purge.md#BK_SetSpam).</span></span>
    
    <span data-ttu-id="87701-125">すべてのメールボックスを ZAP でスクリーニングする必要がある場合に、一連のユーザーにのみ適用する新しい迷惑メール フィルター ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="87701-125">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>
    
- <span data-ttu-id="87701-126">ユーザーの[オプション\>迷惑電子メール](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F)。</span><span class="sxs-lookup"><span data-stu-id="87701-126">The user's [Options \> Junk Email](https://support.office.com/article/068FA430-F8D7-4518-A8DA-8BC74958F05F).</span></span>
    
<span data-ttu-id="87701-127">[ZAP がメッセージを移動するかどうかを参照してください](zero-hour-auto-purge.md#BK_DidZAPMove)したい場合は、Exchange オンラインのメッセージ トレース ツールを使用できます。</span><span class="sxs-lookup"><span data-stu-id="87701-127">If you want [to see if ZAP moved your message](zero-hour-auto-purge.md#BK_DidZAPMove), you can use the Exchange Online message trace tool.</span></span>
  
<span data-ttu-id="87701-128">管理者ことも[ZAP を無効にする](zero-hour-auto-purge.md#BK_Posh)PowerShell を使用しています。</span><span class="sxs-lookup"><span data-stu-id="87701-128">Admins can also [disable ZAP](zero-hour-auto-purge.md#BK_Posh) by using PowerShell.</span></span> 
  
 <span data-ttu-id="87701-129">**迷惑メール フィルターのポリシーを設定するのには**</span><span class="sxs-lookup"><span data-stu-id="87701-129">**To set spam filter policy**</span></span>
  
1. <span data-ttu-id="87701-130">[ビジネス向けの Office 365 にサインインするための場所](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)にサインインして、**保護** \> **迷惑メール フィルター**です。</span><span class="sxs-lookup"><span data-stu-id="87701-130">Sign in to the [Where to sign in to Office 365 for business](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) and choose **protection** \> **spam filter**.</span></span> 
    
    ![EAC で保護を選択し、[スパム フィルター](media/0463c879-63fa-4a6c-9b03-e980d5ef3954.PNG)
  
2. <span data-ttu-id="87701-132">フィルター ポリシーを調整するを選択するか、[**追加**] を選択![追加アイコン](media/8ee52980-254b-440b-99a2-18d068de62d3.gif)を新規に作成します。</span><span class="sxs-lookup"><span data-stu-id="87701-132">Either choose the filter policy you want to adjust, or choose **add**![Add icon](media/8ee52980-254b-440b-99a2-18d068de62d3.gif) to create a new one.</span></span> 
    
    <span data-ttu-id="87701-p104">前のスクリーン ショットでは、ポリシーは「既定」という名前が、追加のスパム フィルター ポリシーを作成する場合を指定できます、別の名前。限定された一連のユーザーにポリシーを適用することもできます。</span><span class="sxs-lookup"><span data-stu-id="87701-p104">In the previous screen shot, the policy is named "Default", but if you create additional spam filter policies you can give them a different name. You can also apply the policy to only a limited set of users.</span></span>
    
3. <span data-ttu-id="87701-135">[ポリシー] ウィンドウで、**スパム、および一括操作**を選択し、**迷惑メール**を**迷惑メール フォルダーにメッセージを移動**するに設定されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="87701-135">In the policy window, choose **spam and bulk actions**, and make sure that **Spam** is set to **Move message to Junk Email folder**.</span></span> 
    
    <span data-ttu-id="87701-136">この時点で [**保存**」を選択する場合、Office 365 テナントにポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="87701-136">If you choose **Save** at this point, the policy applies to your Office 365 tenant.</span></span> 
    
    ![迷惑メールを設定し、[迷惑メール フォルダーにメッセージを移動するアクションを一括](media/4332cfb3-89e1-48ba-8da8-9286f2fa1089.PNG)
  
4. <span data-ttu-id="87701-p105">**受信者**、**ドメイン**、または**グループのメンバーシップ**を**適用する**ポリシーのフィルター] ウィンドウで、メニュー コントロールでスクロールを選択して、新しいポリシーを作成する、一連のユーザーにポリシーを適用する場合は、します。ポリシーを適用するとしてください。追加の条件と例外を設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="87701-p105">If you created a new policy, and you want to apply the policy to only a set of users, scroll to the **Applied To** section in the policy filter window, and in the menu controls choose the **recipients**, **domain**, or **group memberships** you want to apply the policy to. You can also set additional conditions and exceptions.</span></span> 
    
    ![適用先] セクションで、受信者を選択します](media/19ca10db-c0f4-432c-b3de-ad4101a23de6.PNG)
  
    <span data-ttu-id="87701-141">**保存**を選択したユーザーにポリシーを適用するを選択します。</span><span class="sxs-lookup"><span data-stu-id="87701-141">Choose **Save** to apply the policy to the selected users.</span></span> 
    
 <span data-ttu-id="87701-142">**ZAP がメッセージを移動するかどうかを参照してください。**</span><span class="sxs-lookup"><span data-stu-id="87701-142">**To see if ZAP moved your message**</span></span>
  
- <span data-ttu-id="87701-143">ZAP でメッセージを移動したかどうかを決定する[検索し、ビジネス管理者は、Office 365 との電子メール配信の問題を解決](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6)を使用できます。</span><span class="sxs-lookup"><span data-stu-id="87701-143">You can use the [Find and fix email delivery issues as an Office 365 for business admin](https://support.office.com/article/e7758b99-1896-41db-bf39-51e2dba21de6) to determine if the message was moved by ZAP:</span></span> 
    
    <span data-ttu-id="87701-144">ZAP によって移動されたメッセージを識別するのには、トレースの詳細のテキスト"0 時間自動パージ (ZAP)"を検索します。</span><span class="sxs-lookup"><span data-stu-id="87701-144">Look for the text "Zero-Hour Auto Purge (ZAP)" in your trace details to identify a message that was moved by ZAP.</span></span>
    
 <span data-ttu-id="87701-145">**ZAP を無効にするには**</span><span class="sxs-lookup"><span data-stu-id="87701-145">**To disable ZAP**</span></span>
  
- <span data-ttu-id="87701-146">無効にするか、Office 365 のテナントの ZAP[セット HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)EOP、コマンドレットの**ZapEnabled**パラメーターを使用するユーザーのセットです。</span><span class="sxs-lookup"><span data-stu-id="87701-146">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
    <span data-ttu-id="87701-147">次の例では、ZAP は「テスト」という名前のコンテンツ フィルター ポリシー無効になります。</span><span class="sxs-lookup"><span data-stu-id="87701-147">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
||
|:-----|
|
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

|
   
## <a name="faq"></a><span data-ttu-id="87701-148">FAQ</span><span class="sxs-lookup"><span data-stu-id="87701-148">FAQ</span></span>
<span data-ttu-id="87701-149"><a name="BK_FAQ"> </a></span><span class="sxs-lookup"><span data-stu-id="87701-149"></span></span>

 <span data-ttu-id="87701-150">**正当なメッセージが [迷惑メール] フォルダーに移動するとどうなりますか。**</span><span class="sxs-lookup"><span data-stu-id="87701-150">**What happens if a legitimate message is moved to the junk mail folder?**</span></span>
  
<span data-ttu-id="87701-p106">誤の通常のレポート作成プロセスに従う必要があります。[迷惑メール] フォルダーにメッセージを受信トレイから移動が唯一の理由の場合は、サービスが、メッセージが迷惑メールをしたことを確認するためまたは悪意のあります。</span><span class="sxs-lookup"><span data-stu-id="87701-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
 <span data-ttu-id="87701-153">**場合、[迷惑メール] フォルダーではなく Office 365 の検査を使用しますか。**</span><span class="sxs-lookup"><span data-stu-id="87701-153">**What if I use the Office 365 quarantine instead of the junk mail folder?**</span></span>
  
<span data-ttu-id="87701-154">ZAP 移動しないメッセージ検疫場所に受信トレイからこの時点で。</span><span class="sxs-lookup"><span data-stu-id="87701-154">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
 <span data-ttu-id="87701-155">**ユーザー設定のメール フロー ルールがある場合 (禁止/許可の規則)。**</span><span class="sxs-lookup"><span data-stu-id="87701-155">**What If I have a custom mail flow rule (Block/ Allow Rule)?**</span></span>
  
<span data-ttu-id="87701-p107">管理者 (メール フロー ルール) またはブロックし、許可する規則が作成した規則が優先されます。このようなメッセージは、機能の基準から除外されます。</span><span class="sxs-lookup"><span data-stu-id="87701-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="87701-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="87701-158">Related Topics</span></span>
<span data-ttu-id="87701-159"><a name="BK_FAQ"> </a></span><span class="sxs-lookup"><span data-stu-id="87701-159"></span></span>

[<span data-ttu-id="87701-160">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="87701-160">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="87701-161">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="87701-161">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

