---
title: ゼロアワー自動消去 - スパムやマルウェアからの保護
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
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
ms.openlocfilehash: b28de1b05843e3f5b0f6e7fc905c96f094c277f9
ms.sourcegitcommit: 74ad22a5c6c3c9d9324f0f97070909e323a4e9cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30524021"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="be724-104">ゼロアワー自動消去 - スパムやマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="be724-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="be724-105">概要</span><span class="sxs-lookup"><span data-stu-id="be724-105">Overview</span></span>

<span data-ttu-id="be724-106">ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。</span><span class="sxs-lookup"><span data-stu-id="be724-106">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with phish, spam, or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless.</span></span> <span data-ttu-id="be724-107">これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。メールの内容、url、または添付ファイルのため、メールを zapped することができます。</span><span class="sxs-lookup"><span data-stu-id="be724-107">How ZAP does this depends on the type of malicious content detected; mail can be zapped due to mail content, URLs, or attachments.</span></span>
  
<span data-ttu-id="be724-108">ZAP は、exchange online メールボックスを含む Office 365 サブスクリプションに含まれている既定の exchange online Protection で利用できます。</span><span class="sxs-lookup"><span data-stu-id="be724-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="be724-109">ZAP は既定で有効になっていますが、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="be724-109">ZAP is turned on by default, but the following conditions must be met:</span></span>
  
- <span data-ttu-id="be724-110">**迷惑メールフォルダーにメッセージを移動**するように**スパムアクション**が設定されています。</span><span class="sxs-lookup"><span data-stu-id="be724-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="be724-111">すべてのメールボックスを ZAP でスクリーニングしないようにする場合は、ユーザーのセットにのみ適用される新しいスパムフィルターポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="be724-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="be724-112">ユーザーが既定の迷惑メール設定を保持しており、迷惑メールの保護がオフになっていない。</span><span class="sxs-lookup"><span data-stu-id="be724-112">Users have kept their default junk mail settings, and have not turned off junk email protection.</span></span> <span data-ttu-id="be724-113">(Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="be724-113">(See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="be724-114">ZAP はどのように動作しますか?</span><span class="sxs-lookup"><span data-stu-id="be724-114">How does ZAP work?</span></span>

<span data-ttu-id="be724-115">Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。</span><span class="sxs-lookup"><span data-stu-id="be724-115">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis.</span></span> <span data-ttu-id="be724-116">ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="be724-116">However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users.</span></span> <span data-ttu-id="be724-117">ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。</span><span class="sxs-lookup"><span data-stu-id="be724-117">ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures.</span></span> <span data-ttu-id="be724-118">ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。</span><span class="sxs-lookup"><span data-stu-id="be724-118">ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 

- <span data-ttu-id="be724-119">スパムとして識別されたメールの場合、ZAP は未読のメッセージをユーザーの迷惑メールフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="be724-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 

- <span data-ttu-id="be724-120">フィッシングとして識別されるメールの場合、ZAP は、電子メールが開封されたかどうかに関係なく、ユーザーの迷惑メールフォルダーにメッセージを移動します。</span><span class="sxs-lookup"><span data-stu-id="be724-120">For mail that is identified as phish, ZAP moves messages to users' Junk mail folder, regardless of whether the email has been read.</span></span>

- <span data-ttu-id="be724-121">新たに検出されたマルウェアの場合、ZAP は電子メールメッセージの添付ファイルを削除します (電子メールが開封されたかどうかは関係ありません)。</span><span class="sxs-lookup"><span data-stu-id="be724-121">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="be724-122">ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。</span><span class="sxs-lookup"><span data-stu-id="be724-122">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="be724-123">許可リスト、[メールフロールール](https://go.microsoft.com/fwlink/p/?LinkId=722755)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。</span><span class="sxs-lookup"><span data-stu-id="be724-123">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="be724-124">スパムフィルターポリシーを確認または設定するには</span><span class="sxs-lookup"><span data-stu-id="be724-124">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="be724-125">に[https://protection.office.com](https://protection.office.com)移動して、Office 365 の職場または学校のアカウントを使用してサインインします。</span><span class="sxs-lookup"><span data-stu-id="be724-125">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>

2. <span data-ttu-id="be724-126">[**脅威の管理**] で、[**スパム対策**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be724-126">Under **Threat management**, choose **Anti-spam**.</span></span>

3. <span data-ttu-id="be724-127">標準設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="be724-127">Review the standard settings.</span></span> 

4. <span data-ttu-id="be724-128">設定をカスタマイズする場合は、[**ユーザー**設定] タブを選択し、[**ユーザー設定**] をオンにします。</span><span class="sxs-lookup"><span data-stu-id="be724-128">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**.</span></span> <span data-ttu-id="be724-129">設定を編集し、必要に応じて、[ **+ ポリシーを作成**して新しいポリシーを追加する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="be724-129">Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="be724-130">ZAP がメッセージを移動したかどうかを確認するには</span><span class="sxs-lookup"><span data-stu-id="be724-130">To see if ZAP moved your message</span></span>

<span data-ttu-id="be724-131">ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)(または[脅威エクスプローラー](use-explorer-in-security-and-compliance.md)) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="be724-131">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="be724-132">ZAP を無効にするには</span><span class="sxs-lookup"><span data-stu-id="be724-132">To disable ZAP</span></span>
  
<span data-ttu-id="be724-133">Office 365 テナントまたはユーザーのセットに対する ZAP を無効にする場合は、 [set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)の EOP コマンドレットの**zapenabled**パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="be724-133">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="be724-134">次の例では、"Test" という名前のコンテンツフィルターポリシーで ZAP が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="be724-134">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="be724-135">FAQ</span><span class="sxs-lookup"><span data-stu-id="be724-135">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="be724-136">正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="be724-136">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="be724-137">誤検知の通常のレポートプロセスに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="be724-137">You should follow the normal reporting process for false-positives.</span></span> <span data-ttu-id="be724-138">メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。</span><span class="sxs-lookup"><span data-stu-id="be724-138">The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="be724-139">迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="be724-139">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="be724-140">この時点で、ZAP は受信トレイからメッセージを検疫に移動しません。</span><span class="sxs-lookup"><span data-stu-id="be724-140">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="be724-141">カスタムメールフロールール (ブロック/許可ルール) を持っている場合</span><span class="sxs-lookup"><span data-stu-id="be724-141">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="be724-142">管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。</span><span class="sxs-lookup"><span data-stu-id="be724-142">Rules created by admins (mail flow rules) or Block and Allow rules take precedence.</span></span> <span data-ttu-id="be724-143">このようなメッセージは、機能の条件から除外されます。</span><span class="sxs-lookup"><span data-stu-id="be724-143">Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="be724-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="be724-144">Related Topics</span></span>

[<span data-ttu-id="be724-145">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="be724-145">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="be724-146">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="be724-146">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](reduce-spam-email.md)
  

