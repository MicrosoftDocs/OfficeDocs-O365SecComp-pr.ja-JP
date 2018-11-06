---
title: ゼロアワー自動消去 - 迷惑メールやマルウェアからの保護
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
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
ms.openlocfilehash: ac181a7c57b4b16a952ff9c046edbff1380828d1
ms.sourcegitcommit: 791d23e1c2dea622b6ef77a6e2bde32e1d31a41b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2018
ms.locfileid: "25999979"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a><span data-ttu-id="5a1e4-104">ゼロアワー自動消去 - 迷惑メールやマルウェアからの保護</span><span class="sxs-lookup"><span data-stu-id="5a1e4-104">Zero-hour auto purge - protection against spam and malware</span></span>

## <a name="overview"></a><span data-ttu-id="5a1e4-105">概要</span><span class="sxs-lookup"><span data-stu-id="5a1e4-105">Overview</span></span>

<span data-ttu-id="5a1e4-p102">ゼロの自動パージ (ZAP) は既にユーザーの受信トレイに配信されたメッセージをスパムやマルウェアを検出する電子メールの保護機能で、害のない、悪意のあるコンテンツをレンダリングZAP はこれは、検出された、悪意のあるコンテンツの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-p102">Zero-hour auto purge (ZAP) is an email protection feature that detects messages with spam or malware that have already been delivered to your users' inboxes, and then renders the malicious content harmless. How ZAP does this depends on the type of malicious content detected.</span></span>
  
<span data-ttu-id="5a1e4-108">ZAP は、既定の Exchange Online のメールボックスを含むすべての Office 365 サブスクリプションに含まれている Exchange のオンライン保護に使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-108">ZAP is available with the default Exchange Online Protection that is included with any Office 365 subscription that contains Exchange Online mailboxes.</span></span>

<span data-ttu-id="5a1e4-109">ZAP が既定でオンですが、以下の条件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-109">ZAP is turned on by default, but the folowing conditions must be met:</span></span>
  
- <span data-ttu-id="5a1e4-110">**スパム アクション**は、 **[迷惑メール フォルダーにメッセージを移動**するのには設定されています。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-110">**Spam action** is set to **Move message to Junk Email folder**.</span></span> <br/><span data-ttu-id="5a1e4-111">すべてのメールボックスを ZAP でスクリーニングする必要がある場合に、一連のユーザーにのみ適用する新しい迷惑メール フィルター ポリシーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-111">You can also create a new spam filter policy that applies only to a set of users if you don't want all mailboxes to be screened by ZAP.</span></span>

- <span data-ttu-id="5a1e4-p103">ユーザーは、迷惑メールの設定をその既定値を保管してあるし、迷惑メールの保護をオフになっていません。(Outlook ユーザー オプションの詳細について[の迷惑メール フィルターの保護レベルの変更](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-p103">Users have kept their default junk mail settings, and have not turned off junk email protection. (See [Change the level of protection in the Junk Email Filter](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b) for details about user options in Outlook.)</span></span> 
  
## <a name="how-does-zap-work"></a><span data-ttu-id="5a1e4-114">ZAP の動作方法</span><span class="sxs-lookup"><span data-stu-id="5a1e4-114">How does ZAP work?</span></span>

<span data-ttu-id="5a1e4-p104">Office 365 のスパム対策エンジンおよびマルウェアのシグネチャを更新する毎日のようにリアルタイムです。ただし、ユーザーは悪意のあるメッセージをさまざまな理由から、ユーザーに配布された後の内容が後で場合を含む受信トレイに配信をする可能性が残っています。ZAP は、Office 365 のスパムやマルウェアのシグネチャの更新を継続的に監視することによってこれを説明します。ZAP では、検索でき、ユーザーの受信トレイに配信されるメッセージを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-p104">Office 365 updates anti-spam engine and malware signatures in real-time on a daily basis. However, your users might still get malicious messages delivered to their inboxes for a variety of reasons, including if content is weaponized after being delivered to users. ZAP addresses this by continually monitoring updates to the Office 365 spam and malware signatures. ZAP can find and remove previously delivered messages that are already in users' inboxes.</span></span> 
- <span data-ttu-id="5a1e4-119">スパムとして識別されるメールでは、ZAP は未読メ ッ セージをユーザーの迷惑メール フォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-119">For mail that is identified as spam, ZAP moves unread messages to users' Junk mail folder.</span></span> 
- <span data-ttu-id="5a1e4-120">新たに検出されたマルウェアが、ZAP は、電子メールが読み取られたかどうかに関係なく、電子メール メッセージから添付ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-120">For newly detected malware, ZAP removes attachments from email messages, regardless of whether the email has been read.</span></span> 
  
<span data-ttu-id="5a1e4-121">ZAP アクションが、メールボックスのユーザーのシームレスです電子メール メッセージが移動された場合に通知されません。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-121">The ZAP action is seamless for the mailbox user; they are not notified if an email message is moved.</span></span>
  
<span data-ttu-id="5a1e4-122">リスト、[メール フローの規則](https://go.microsoft.com/fwlink/p/?LinkId=722755)、およびエンド ・ ユーザーの規則を許可するか、追加フィルター ZAP よりも優先します。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-122">Allow lists, [mail flow rules](https://go.microsoft.com/fwlink/p/?LinkId=722755), and end user rules or additional filters take precedence over ZAP.</span></span>
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a><span data-ttu-id="5a1e4-123">迷惑メール フィルターのポリシー設定を確認または</span><span class="sxs-lookup"><span data-stu-id="5a1e4-123">To review or set up a spam filter policy</span></span>
  
1. <span data-ttu-id="5a1e4-124">[https://protection.office.com](https://protection.office.com)し、職場、学校のアカウントを使用して Office 365 にサインインします。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-124">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span>
2. <span data-ttu-id="5a1e4-125">**脅威の管理**の下で、**迷惑メール対策**を選択します。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-125">Under **Threat management**, choose **Anti-spam**.</span></span>
3. <span data-ttu-id="5a1e4-126">標準の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-126">Review the standard settings.</span></span> 
4. <span data-ttu-id="5a1e4-p105">設定をカスタマイズする場合は、**ユーザー設定**] タブを選択し、**カスタム設定**を有効にします。設定を編集し、 **+ ポリシーを作成する**新しいポリシーを追加するを選択する場合は、します。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-p105">If you want to customize your settings, select the **Custom** tab, and turn on **Custom settings**. Edit your settings and if you want, choose **+ Create a policy** to add a new policy.</span></span> 
    
## <a name="to-see-if-zap-moved-your-message"></a><span data-ttu-id="5a1e4-129">ZAP がメッセージを移動するかどうかを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-129">To see if ZAP moved your message</span></span>

<span data-ttu-id="5a1e4-130">ZAP がメッセージを移動するかどうかを参照してくださいしたい場合、またはいずれかの[脅威保護の状態のレポート](view-email-security-reports.md#threat-protection-status-report-new)([脅威のエクスプ ローラー](use-explorer-in-security-and-compliance.md)) を使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-130">If you want to see if ZAP moved your message, you can use either the [Threat Protection Status report](view-email-security-reports.md#threat-protection-status-report-new) (or [Threat Explorer](use-explorer-in-security-and-compliance.md)).</span></span>
    
## <a name="to-disable-zap"></a><span data-ttu-id="5a1e4-131">ZAP を無効にするには</span><span class="sxs-lookup"><span data-stu-id="5a1e4-131">To disable ZAP</span></span>
  
<span data-ttu-id="5a1e4-132">無効にするか、Office 365 のテナントの ZAP[セット HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)EOP、コマンドレットの**ZapEnabled**パラメーターを使用するユーザーのセットです。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-132">If you want to disable ZAP for your Office 365 tenant, or a set of users, use the **ZapEnabled** parameter of [Set-HostedContentFilterPolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758), an EOP cmdlet.</span></span>
    
<span data-ttu-id="5a1e4-133">次の例では、ZAP は「テスト」という名前のコンテンツ フィルター ポリシー無効になります。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-133">In the following example, ZAP is disabled for a content filter policy named "Test".</span></span>
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a><span data-ttu-id="5a1e4-134">FAQ</span><span class="sxs-lookup"><span data-stu-id="5a1e4-134">FAQ</span></span>

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a><span data-ttu-id="5a1e4-135">正当なメッセージが [迷惑メール] フォルダーに移動するとどうなりますか。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-135">What happens if a legitimate message is moved to the junk mail folder?</span></span>
  
<span data-ttu-id="5a1e4-p106">誤の通常のレポート作成プロセスに従う必要があります。[迷惑メール] フォルダーにメッセージを受信トレイから移動が唯一の理由の場合は、サービスが、メッセージが迷惑メールをしたことを確認するためまたは悪意のあります。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-p106">You should follow the normal reporting process for false-positives. The only reason the message would be moved from the inbox to the junk mail folder would be because the service has determined that the message was spam or malicious.</span></span>
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a><span data-ttu-id="5a1e4-138">場合、[迷惑メール] フォルダーではなく Office 365 の検査を使用しますか。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-138">What if I use the Office 365 quarantine instead of the junk mail folder?</span></span>
  
<span data-ttu-id="5a1e4-139">ZAP 移動しないメッセージ検疫場所に受信トレイからこの時点で。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-139">ZAP doesn't move messages into quarantine from the Inbox at this time.</span></span>
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a><span data-ttu-id="5a1e4-140">ユーザー設定のメール フロー ルールがある場合 (禁止/許可の規則)。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-140">What If I have a custom mail flow rule (Block/ Allow Rule)?</span></span>
  
<span data-ttu-id="5a1e4-p107">管理者 (メール フロー ルール) またはブロックし、許可する規則が作成した規則が優先されます。このようなメッセージは、機能の基準から除外されます。</span><span class="sxs-lookup"><span data-stu-id="5a1e4-p107">Rules created by admins (mail flow rules) or Block and Allow rules take precedence. Such messages are excluded from the feature criteria.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5a1e4-143">関連項目</span><span class="sxs-lookup"><span data-stu-id="5a1e4-143">Related Topics</span></span>

[<span data-ttu-id="5a1e4-144">Office 365 の電子メールのスパム対策保護</span><span class="sxs-lookup"><span data-stu-id="5a1e4-144">Office 365 Email Anti-Spam Protection</span></span>](anti-spam-protection.md)
  
[<span data-ttu-id="5a1e4-145">検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする</span><span class="sxs-lookup"><span data-stu-id="5a1e4-145">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](block-email-spam-to-prevent-false-negatives.md)
  

