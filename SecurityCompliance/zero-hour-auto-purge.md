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
ms.openlocfilehash: 91bb167c988e49a40895f851a518ee255abdbf08
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2019
ms.locfileid: "36698969"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="e708a-104">ゼロアワー自動消去 - スパムまたはマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="e708a-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="e708a-105">概要</span><span class="sxs-lookup"><span data-stu-id="e708a-105">Overview</span></span>

<span data-ttu-id="e708a-106">ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="e708a-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="e708a-107">これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。メールの内容、Url、または添付ファイルのため、メールを zapped することができます。</span><span class="sxs-lookup"><span data-stu-id="e708a-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="e708a-108">ZAP は、Exchange Online メールボックスを含む Office 365 サブスクリプションに含まれている既定の Exchange Online Protection で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e708a-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="e708a-109">ZAP は既定で有効になっていますが、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e708a-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="e708a-110">**迷惑メールフォルダーにメッセージを移動**するように**スパムアクション**が設定されています。</span><span class="sxs-lookup"><span data-stu-id="e708a-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <span data-ttu-id="e708a-111">すべてのメールボックスを ZAP でスクリーニングしないようにする場合は、ユーザーのセットにのみ適用される新しいスパムフィルターポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="e708a-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="e708a-112">ユーザーが既定の迷惑メール設定を保持しており、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="e708a-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="e708a-113">(Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="e708a-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span>
  
## <a name="how-zap-works"></a><span data-ttu-id="e708a-114">ZAP のしくみ</span><span class="sxs-lookup"><span data-stu-id="e708a-114">How ZAP works</span></span>

<span data-ttu-id="e708a-115">Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。</span><span class="sxs-lookup"><span data-stu-id="e708a-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="e708a-116">ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e708a-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="e708a-117">ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。</span><span class="sxs-lookup"><span data-stu-id="e708a-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="e708a-118">ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e708a-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span>

<span data-ttu-id="e708a-119">ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="e708a-119">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span> <span data-ttu-id="e708a-120">メッセージを2日より前にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e708a-120">Message must not be older than 2 days.</span></span>
  
<span data-ttu-id="e708a-121">許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)(トランスポートルールとも呼ばれます)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="e708a-121">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755) (also known as transport rules), and end user rules or additional filters take precedence over ZAP.</span></span>

### <a name="malware-zap"></a><span data-ttu-id="e708a-122">マルウェアの ZAP</span><span class="sxs-lookup"><span data-stu-id="e708a-122">Malware ZAP</span></span>

<span data-ttu-id="e708a-123">新たに検出されたマルウェアの場合、ZAP は電子メールメッセージから添付ファイルを削除し、ユーザーのメールボックスにメッセージの本文を残します。</span><span class="sxs-lookup"><span data-stu-id="e708a-123">For newly detected malware, ZAP removes attachments from email messages, leaving the body of the message in the user's mailbox.</span></span> <span data-ttu-id="e708a-124">添付ファイルは、メールの開封状況に関係なく削除されます。</span><span class="sxs-lookup"><span data-stu-id="e708a-124">Attachments are removed regardless of the read status of the mail.</span></span>

<span data-ttu-id="e708a-125">マルウェアの ZAP は、マルウェアポリシーで既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e708a-125">Malware ZAP is enabled by default in the Malware Policy.</span></span> <span data-ttu-id="e708a-126">Exchange Online PowerShell または Exchange Online Protection PowerShell で[new-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットの*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e708a-126">You can disable Malware ZAP by using the *ZapEnabled* parameter on the [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="phish-zap"></a><span data-ttu-id="e708a-127">フィッシング ZAP</span><span class="sxs-lookup"><span data-stu-id="e708a-127">Phish ZAP</span></span>

<span data-ttu-id="e708a-128">配信後にフィッシングとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="e708a-128">For mail that is identified as phish after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="e708a-129">[Policy フィッシング] アクションがメールに対してアクションを実行するように設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メールの開封状況に関係なく、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。</span><span class="sxs-lookup"><span data-stu-id="e708a-129">If the policy Phish action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, regardless of the read status of the mail.</span></span> <span data-ttu-id="e708a-130">[ポリシーのフィッシング] アクションが [アクションを実行する] に設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="e708a-130">If the policy Phish action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="e708a-131">ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e708a-131">Learn more about how to [configure your spam filter policies](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies) here.</span></span>

<span data-ttu-id="e708a-132">スパムポリシーでは、フィッシング ZAP が既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e708a-132">Phish ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="e708a-133">フィッシング ZAP を無効にするには、Exchange Online PowerShell または Exchange Online Protection PowerShell の[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットで*zapenabled*パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="e708a-133">You can disable Phish ZAP by using the *ZapEnabled* parameter on the [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

### <a name="spam-zap"></a><span data-ttu-id="e708a-134">スパム ZAP</span><span class="sxs-lookup"><span data-stu-id="e708a-134">Spam ZAP</span></span>

<span data-ttu-id="e708a-135">配信後にスパムとして識別されるメールの場合、ZAP はユーザーが対象とするスパムポリシーに従って処理を行います。</span><span class="sxs-lookup"><span data-stu-id="e708a-135">For mail that is identified as spam after delivery, ZAP takes action according to the Spam policy that the user is covered by.</span></span> <span data-ttu-id="e708a-136">メールに対してアクションを実行するようにポリシーのスパムアクションが設定されている場合 (リダイレクト、削除、検疫、迷惑メールへの移動)、ZAP により、メッセージが未読の場合は、ユーザーの受信トレイの迷惑メールフォルダーにメッセージが移動されます。</span><span class="sxs-lookup"><span data-stu-id="e708a-136">If the policy Spam action is set to take action on a mail (Redirect, Delete, Quarantine, Move to Junk) then ZAP will move the message to the Junk mail folder of the user's inbox, if the message is unread.</span></span> <span data-ttu-id="e708a-137">[Policy Spam] アクションがアクションを実行するように設定されていない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし]) 場合、ZAP はメールに対してアクションを実行しません。</span><span class="sxs-lookup"><span data-stu-id="e708a-137">If the policy Spam action is not set to take action (Add X-header, Modify subject, No action) then ZAP will not take action on the mail.</span></span> <span data-ttu-id="e708a-138">ここでは[、スパムフィルターポリシーを構成](configure-your-spam-filter-policies.md)する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e708a-138">Learn more about how to [Configure your spam filter policies](configure-your-spam-filter-policies.md) here.</span></span>

<span data-ttu-id="e708a-139">スパム ZAP は、スパムポリシーでは既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="e708a-139">Spam ZAP is enabled by default in the Spam Policy.</span></span> <span data-ttu-id="e708a-140">Exchange Online PowerShell または Exchange Online Protection PowerShell で[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)コマンドレットの*zapenabled*パラメーターを使用して、スパム ZAP を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e708a-140">You can disable Spam ZAP by using the *ZapEnabled* parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet in Exchange Online PowerShell or Exchange Online Protection PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="e708a-141">**Set-hostedcontentfilterpolicy**コマンドレットの*zapenabled*パラメーターは、ポリシーに対してフィッシング ZAP とスパム zap の両方を無効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="e708a-141">The *ZapEnabled* parameter on the **Set-HostedContentFilterPolicy** cmdlet disables or enables both Phish ZAP and Spam ZAP for the policy.</span></span> <span data-ttu-id="e708a-142">同じポリシー内でフィッシング ZAP とスパム ZAP を独立して有効または無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="e708a-142">You can't independently enable or disable Phish ZAP and Spam ZAP within the same policy.</span></span>

## <a name="how-to-see-if-zap-moved-your-message"></a><span data-ttu-id="e708a-143">ZAP がメッセージを移動したかどうかを確認する方法</span><span class="sxs-lookup"><span data-stu-id="e708a-143">How to see if ZAP moved your message</span></span>

<span data-ttu-id="e708a-144">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="e708a-144">To determine if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) or [Threat Explorer (and real-time detections)](threat-explorer.md).</span></span>

## <a name="disable-zap"></a><span data-ttu-id="e708a-145">ZAP を無効にする</span><span class="sxs-lookup"><span data-stu-id="e708a-145">Disable ZAP</span></span>

<span data-ttu-id="e708a-146">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://go.microsoft.com/fwlink/p/?linkid=396554)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e708a-146">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span> <span data-ttu-id="e708a-147">Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://go.microsoft.com/fwlink/p/?linkid=627290)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e708a-147">To connect to Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290).</span></span>

### <a name="disable-malware-zap"></a><span data-ttu-id="e708a-148">マルウェアの無効化 \* \*</span><span class="sxs-lookup"><span data-stu-id="e708a-148">Disable Malware ZAP\*\*</span></span>

<span data-ttu-id="e708a-149">この例では、"Test" という名前のマルウェアフィルターポリシーの ZAP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e708a-149">This example disables ZAP in the malware filter policy named "Test".</span></span>

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="e708a-150">構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e708a-150">For detailed syntax and parameter information, see [Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy).</span></span>

### <a name="disable-phish-zap-and-spam-zap"></a><span data-ttu-id="e708a-151">フィッシング ZAP とスパム ZAP を無効にする</span><span class="sxs-lookup"><span data-stu-id="e708a-151">Disable Phish ZAP and Spam ZAP</span></span>

<span data-ttu-id="e708a-152">この例では、"Test" という名前のコンテンツフィルターポリシーでフィッシング ZAP とスパム ZAP を無効にします。</span><span class="sxs-lookup"><span data-stu-id="e708a-152">This example disables Phish ZAP and Spam ZAP in the content filter policy named "Test".</span></span>

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

<span data-ttu-id="e708a-153">構文およびパラメーターの詳細については、「 [set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e708a-153">For detailed syntax and parameter information, see [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758).</span></span>

## <a name="faq"></a><span data-ttu-id="e708a-154">FAQ</span><span class="sxs-lookup"><span data-stu-id="e708a-154">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="e708a-155">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="e708a-155">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="e708a-156">誤[検知](prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e708a-156">You should follow the normal reporting process for [false-positives](prevent-email-from-being-marked-as-spam.md).</span></span> <span data-ttu-id="e708a-157">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="e708a-157">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="e708a-158">迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="e708a-158">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="e708a-159">この時点で、ZAP は受信トレイからメッセージを検疫に移動しません。</span><span class="sxs-lookup"><span data-stu-id="e708a-159">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="e708a-160">カスタムメールフロールール (ブロック/許可ルール) を持っている場合</span><span class="sxs-lookup"><span data-stu-id="e708a-160">What if I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="e708a-161">管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。</span><span class="sxs-lookup"><span data-stu-id="e708a-161">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="e708a-162">このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。</span><span class="sxs-lookup"><span data-stu-id="e708a-162">Such messages are excluded from the feature criteria so the mail flow will follow the rule action (Block/Allow Rule).</span></span>

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a><span data-ttu-id="e708a-163">メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="e708a-163">What if a message is moved to another folder (e.g. Inbox rule)?</span></span>

<span data-ttu-id="e708a-164">この場合、ZAP は、メッセージが削除されているか、迷惑メールにある場合を除き、この場合でも動作します。</span><span class="sxs-lookup"><span data-stu-id="e708a-164">ZAP still works in this case, unless the message has been deleted or is in Junk.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e708a-165">関連項目</span><span class="sxs-lookup"><span data-stu-id="e708a-165">Related Topics</span></span>

[<span data-ttu-id="e708a-166">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="e708a-166">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="e708a-167">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="e708a-167">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
