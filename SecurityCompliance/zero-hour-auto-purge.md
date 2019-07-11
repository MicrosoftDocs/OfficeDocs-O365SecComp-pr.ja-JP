---
title: ゼロアワー自動消去 - スパムまたはマルウェアからの保護
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているスパムまたはマルウェアを含むメッセージを検出し、その悪意のあるコンテンツを無害にする電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。
ms.openlocfilehash: ceb5a973a65406527de3361a354247908b4cab63
ms.sourcegitcommit: 986f40a00ab454093b21e724d58594b8b8b4a9ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2019
ms.locfileid: "35613665"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="9d838-104">ゼロアワー自動消去 - スパムまたはマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="9d838-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="9d838-105">概要</span><span class="sxs-lookup"><span data-stu-id="9d838-105">Overview</span></span>

<span data-ttu-id="9d838-106">ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="9d838-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="9d838-107">これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。メールの内容、Url、または添付ファイルのため、メールを zapped することができます。</span><span class="sxs-lookup"><span data-stu-id="9d838-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="9d838-108">ZAP は、Exchange Online メールボックスを含む Office 365 サブスクリプションに含まれている既定の Exchange Online Protection で利用できます。</span><span class="sxs-lookup"><span data-stu-id="9d838-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="9d838-109">ZAP は既定で有効になっていますが、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d838-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="9d838-110">**迷惑メールフォルダーにメッセージを移動**するように**スパムアクション**が設定されています。</span><span class="sxs-lookup"><span data-stu-id="9d838-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="9d838-111">すべてのメールボックスを ZAP でスクリーニングしないようにする場合は、ユーザーのセットにのみ適用される新しいスパムフィルターポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="9d838-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="9d838-112">ユーザーが既定の迷惑メール設定を保持しており、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="9d838-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="9d838-113">(Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="9d838-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-zap-works"></a><span data-ttu-id="9d838-114">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="9d838-114">How ZAP works</span></span>

<span data-ttu-id="9d838-115">Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。</span><span class="sxs-lookup"><span data-stu-id="9d838-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="9d838-116">ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9d838-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="9d838-117">ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。</span><span class="sxs-lookup"><span data-stu-id="9d838-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="9d838-118">ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="9d838-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="9d838-119">ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="9d838-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="9d838-120">メッセージを2日より前にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="9d838-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="9d838-121">許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="9d838-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>

<span data-ttu-id="9d838-122">**マルウェアの ZAP**新たに検出されたマルウェアの場合、ZAP は電子メールメッセージから添付ファイルを削除し、ユーザーのメールボックスにメッセージの本文を残します。</span><span class="sxs-lookup"><span data-stu-id="9d838-122">**Malware ZAP** For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="9d838-123">添付ファイルは、メールの開封状況に関係なく削除されます。</span><span class="sxs-lookup"><span data-stu-id="9d838-123">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="9d838-124">マルウェアの ZAP は、マルウェアポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9d838-124">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="9d838-125">[New-malwarefilterpolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy?view=exchange-ps)の**zapenabled**パラメーターを使用して、EOP コマンドレットを使用して、マルウェアの ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d838-125">Malware ZAP can be disabled using the **ZapEnabled** parameter of [Set-MalwareFilterPolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy?view=exchange-ps), an EOP cmdlet.</span></span>

<span data-ttu-id="9d838-126">**フィッシング ZAP**配信後にフィッシングとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="9d838-126">**Phish ZAP** For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="9d838-127">[Policy フィッシング] アクションがメールに対してアクションを実行するように設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メールの開封状況に関係なく、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。</span><span class="sxs-lookup"><span data-stu-id="9d838-127">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="9d838-128">[ポリシーのフィッシング] アクションが [アクションを実行する] に設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="9d838-128">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="9d838-129">ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d838-129">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="9d838-130">スパムポリシーでは、フィッシング ZAP が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9d838-130">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="9d838-131">フィッシング ZAP は、EOP コマンドレットである[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)の**zapenabled**パラメーターを使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d838-131">Phish ZAP can be disabled using the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
<span data-ttu-id="9d838-132">注:-ZapEnabled を無効にすると、フィッシング ZAP とスパム ZAP の両方が無効になります。</span><span class="sxs-lookup"><span data-stu-id="9d838-132">Note: Disabling -ZapEnabled will disable both Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="9d838-133">**スパム ZAP**配信後にスパムとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="9d838-133">**Spam ZAP** For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="9d838-134">メールに対してアクションを実行するようにポリシーのスパムアクションが設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メッセージが未読の場合は、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。</span><span class="sxs-lookup"><span data-stu-id="9d838-134">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="9d838-135">[Policy Spam] アクションがアクションを実行するように設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="9d838-135">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="9d838-136">ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9d838-136">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com/en-us/office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="9d838-137">スパム ZAP は、スパムポリシーでは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="9d838-137">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="9d838-138">スパム ZAP は、EOP コマンドレットの**Zapenabled**パラメーター [](https://go.microsoft.com/fwlink/p/?LinkId=722758)を使用して無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="9d838-138">Spam ZAP can be disabled using the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
<span data-ttu-id="9d838-139">注:-ZapEnabled を無効にすると、フィッシング ZAP とスパム ZAP の両方が無効になります。</span><span class="sxs-lookup"><span data-stu-id="9d838-139">Note: Disabling -ZapEnabled will disable both Phish ZAP and Spam ZAP</span></span>

## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="9d838-140">ZAP がメッセージを移動したかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="9d838-140">To see if ZAP moved your message</span></span>

<span data-ttu-id="9d838-141">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="9d838-141">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="to-disable-zap"></a><span data-ttu-id="9d838-142">ZAP を無効にするには</span><span class="sxs-lookup"><span data-stu-id="9d838-142">To disable ZAP</span></span>
<span data-ttu-id="9d838-143">**マルウェアの無効化**O365 テナントまたはユーザーのセットのためのマルウェア ZAP を無効にするには、EOP コマンドレットの[new-malwarefilterpolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy?view=exchange-ps)の**zapenabled**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d838-143">**Disabling Malware ZAP** To disable Malware ZAP for your O365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-MalwareFilterPolicy](https://docs.microsoft.com/en-us/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy?view=exchange-ps), an EOP cmdlet.</span></span>

<span data-ttu-id="9d838-144">次の例では、"Test" という名前のコンテンツフィルターポリシーで ZAP が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9d838-144">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>

```Powershell
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```
<span data-ttu-id="9d838-145">**フィッシングおよびスパム ZAP の無効化**O365 テナントまたはユーザーのセットに対してフィッシングとスパムの両方の ZAP を無効にするには、EOP [](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットの**zapenabled**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="9d838-145">**Disabling Phish and Spam ZAP** To disable both Phish and Spam ZAP for your O365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>

<span data-ttu-id="9d838-146">次の例では、"Test" という名前のコンテンツフィルターポリシーで ZAP が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="9d838-146">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>

```Powershell
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="9d838-147">FAQ</span><span class="sxs-lookup"><span data-stu-id="9d838-147">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="9d838-148">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="9d838-148">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="9d838-149">誤[検知](prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d838-149">You should follow the normal reporting process for [false-positives](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="9d838-150">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="9d838-150">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="9d838-151">迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="9d838-151">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="9d838-152">この時点で、ZAP は受信トレイからメッセージを検疫に移動しません。</span><span class="sxs-lookup"><span data-stu-id="9d838-152">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="9d838-153">カスタムメールフロールール (ブロック/許可ルール) を持っている場合</span><span class="sxs-lookup"><span data-stu-id="9d838-153">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="9d838-154">管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。</span><span class="sxs-lookup"><span data-stu-id="9d838-154">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="9d838-155">このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。</span><span class="sxs-lookup"><span data-stu-id="9d838-155">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="9d838-156">メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="9d838-156">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>
<span data-ttu-id="9d838-157">この場合、ZAP は、メッセージが削除されているか、迷惑メールにある場合を除き、この場合でも動作します。</span><span class="sxs-lookup"><span data-stu-id="9d838-157">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9d838-158">関連項目</span><span class="sxs-lookup"><span data-stu-id="9d838-158">Related Topics</span></span>

[<span data-ttu-id="9d838-159">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="9d838-159">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="9d838-160">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="9d838-160">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
