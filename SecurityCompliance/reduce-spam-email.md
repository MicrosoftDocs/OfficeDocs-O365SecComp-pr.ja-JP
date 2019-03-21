---
title: Office 365 で迷惑メールを減らす方法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Office 365 でスパム メールや迷惑メールを減らすための最も一般的な方法について説明します。
ms.openlocfilehash: d32cad18cf3972a667f2eb9a11b50d1b12e809a7
ms.sourcegitcommit: b688d67935edb036658bb5aa1671328498d5ddd3
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2019
ms.locfileid: "30670562"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a><span data-ttu-id="32d64-103">Office 365 で迷惑メールを減らす方法</span><span class="sxs-lookup"><span data-stu-id="32d64-103">How to reduce spam email in Office 365</span></span>

 <span data-ttu-id="32d64-104">**Office 365 で大量のスパムを受信している方は、次のようにしてください。**</span><span class="sxs-lookup"><span data-stu-id="32d64-104">**Are you getting too much spam in Office 365? Do this.**</span></span>
  
<span data-ttu-id="32d64-p101">フィルターの改善のため、[メッセージ報告アドインを使用して](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)検出漏れメッセージを報告することを強くお勧めします。さらに、メッセージを*添付ファイルとして* junk@office365.microsoft.com または phish@office365.microsoft.com (フィッシングの場合) 宛に転送することもできます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p101">We strongly recommend that you report False Negative messages by [using the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) to help us improve our filters. Additionally, you can forward the message *as an attachment* to junk@office365.microsoft.com or phish@office365.microsoft.com (if it was phish).</span></span>

> [!TIP]
> <span data-ttu-id="32d64-p102">迷惑メールと思われるメッセージが迷惑メール フォルダーにある場合、問題にはなりません。メールボックス内に一切表示しないようにするには、スパム対策ポリシーを変更して、メッセージを検疫する必要があります。メッセージ検疫の詳細については「[Office 365 でメール メッセージを検疫する](quarantine-email-messages.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d64-p102">If you think the message is junk and it is in the Junk Email folder, that should not be a problem. If you don't want to see it at all in the mailbox, you should change the antispam policy to quarantine the message. More information on quarantining a message can be found in [Quarantine email messages in Office 365](quarantine-email-messages.md).</span></span>

## <a name="fixing-allowed-spam"></a><span data-ttu-id="32d64-110">許可されている迷惑メールを解決する</span><span class="sxs-lookup"><span data-stu-id="32d64-110">Fixing allowed spam</span></span>

<span data-ttu-id="32d64-p103">多くの場合、構成が正しくないために迷惑メールがお客様の受信トレイに入ってしまっているようです。最も一般的なのは、フィルターをバイパスするようにメール フロー ルール (別名: トランスポート ルール) でドメインを構成すること、または許可/安全送信者リストにドメインを一覧表示することです。この方法では、本来検出されるはずのこれらのメッセージが迷惑メール フィルターをスキップしてしまうため、正しくありません。</span><span class="sxs-lookup"><span data-stu-id="32d64-p103">We often see that customers get junk mail into their inbox because of incorrect configurations. The most common of which is configuring your domains in a mail flow rule (also known as a transport rule) to bypass filters or listing your domain(s) in the allowed/safe-senders list. This is not good because these messages skip spam filtering and could have otherwise been caught.</span></span>  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a><span data-ttu-id="32d64-114">大量の迷惑メールを受け取る他の一般的な原因の解決方法</span><span class="sxs-lookup"><span data-stu-id="32d64-114">Solutions to other common causes of getting too much spam</span></span>

<span data-ttu-id="32d64-p104">大量のスパムを受信しないようにするには、Exchange Online Protection (EOP) で管理者がいくつかのタスクを実行する必要があります。Office 365 テナントの管理者でなく、大量の迷惑メールを受け取っているユーザーは、これらのタスクを管理者と一緒に行うこともできます。そうしない場合は、ユーザーのセクションにスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="32d64-p104">In order to protect you from getting too much spam, Exchange Online Protection (EOP) requires that administrators complete a few tasks. If you are not the administrator for your Office 365 tenant and you are getting too much spam, then you may want to work with your administrator on these tasks. Otherwise, you can skip to the user section.</span></span>
  
### <a name="for-admins"></a><span data-ttu-id="32d64-118">管理者向け</span><span class="sxs-lookup"><span data-stu-id="32d64-118">For admins</span></span>

- <span data-ttu-id="32d64-p105">**DNS レコードを Office 365 用にする**: EOP で最大の保護を提供するには、すべてのドメインのメール エクスチェンジャー (MX) の DNS レコードを Office 365 専用にする必要があります。「[任意の DNS ホスティング プロバイダーで Office 365 用の DNS レコードを作成する](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d64-p105">**Point your DNS records to Office 365** In order for EOP to provide the best protection, your mail exchanger (MX) DNS record(s) for all domains must be pointed to Office 365 -- and only to Office 365. See [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).</span></span>
    
- <span data-ttu-id="32d64-p106">**すべてのメールボックスで迷惑メール ルールを有効にする**: 既定では、迷惑メールのフィルタリング アクションは**メッセージを迷惑メール フォルダーに移動する**ように設定されています。この設定が優先される現在のスパム ポリシー アクションである場合、各メールボックスで[迷惑メール ルールが有効になっている必要があります](https://support.office.com/ja-JP/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。設定を確認するには、1 つ以上のメールボックスに対して Get-MailboxJunkEmailConfiguration コマンドレットを実行します。たとえば、コマンド「Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}」を実行すると、すべてのメールボックスに対して設定をチェックすることができます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p106">**Enable the junk mail rule on all mailboxes** By default, the spam filtering action is set to **Move message to Junk Email folder**. If this is the preferred and current spam policy action, then each mailbox [must also have the junk mail rule enabled](https://support.office.com/ja-JP/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). To check this, you can run the Get-MailboxJunkEmailConfiguration cmdlet against one or more mailboxes. For example, you might check all mailboxes for this by running the following: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}</span></span>
    
    <span data-ttu-id="32d64-p107">出力を表示するときは、Enable プロパティを True に設定する必要があります。False に設定されている場合は、Set-MailboxJunkEmailConfiguration を実行して True に変更できます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p107">When viewing the output, the Enable property should be set to True. If it is set to False, you can run Set-MailboxJunkEmailConfiguration to change it to True.</span></span>
    
- <span data-ttu-id="32d64-p108">**オンプレミス Exchange Server でメール フロー ルールを作成する**: Exchange Online Protection を使用していても、メールボックスがオンプレミス Exchange Server にある場合は、Exchange Server でいくつかのメール フロー ルールを作成する必要があります。「[EOP 専用の命令](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="32d64-p108">**Create mail flow rules in on-premises Exchange Server** If you are using Exchange Online Protection, but your mailboxes are located in on-premises Exchange Server, then you will need to create a couple of mail flow rules in on-premises Exchange Server. See the [instructions for EOP-only](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).</span></span>
    
- <span data-ttu-id="32d64-p109">**バルク メールをスパムとしてマークする**: バルク メールとは、ユーザーはサインアップした可能性があるとしても望ましくないと思われるメールのことです。メッセージ ヘッダーで、X-Microsoft-Antispam ヘッダーの中の BCL (Bulk Confidence Level) プロパティを見つけます。迷惑メール フィルターに設定されたしきい値よりも BCL 値の方が小さければ、これらのタイプのバルク メッセージを迷惑メールとしてマークするようにしきい値を調整することが必要になる場合があります。[バルク メールの処理](https://docs.microsoft.com/ja-JP/office365/SecurityCompliance/bulk-complaint-level-values)に関する許容度とユーザー設定はユーザーによって異なります。ユーザー設定ごとに異なるポリシーやルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p109">**Mark bulk email as spam** Bulk email is email which users may have signed up for, but may still be undesirable. In the message header, find the BCL (Bulk Confidence Level) property in the X-Microsoft-Antispam header. If the BCL value is less than the threshold set in the spam filter, you may want to adjust the threshold to instead mark these types of bulk messages as spam. Different users have different tolerances and preferences for [how bulk email](https://docs.microsoft.com/ja-JP/office365/SecurityCompliance/bulk-complaint-level-values) is handled. You can create different policies or rules for different user preferences.</span></span> 
    
- <span data-ttu-id="32d64-p110">**すぐに送信者をブロックする** 送信者をすぐにブロックする必要がある場合は、メール アドレス、ドメイン、または IP アドレスでブロックすることができます。「[EAC を使用して、ドメインまたはユーザーから送信されたメッセージをブロックするメール フロー ルールを作成する](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user)」をご覧ください。エンド ユーザーの許可リストのエントリは、管理者が設定したブロックを無効にできることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="32d64-p110">**Immediately block a sender** In the case where you need to immediately block a sender, you can block by email address, domain, or IP address. See [Use the EAC to create a mail flow rule that blocks messages sent from a domain or user](create-organization-wide-safe-sender-or-blocked-sender-lists-in-office-365.md#use-the-eac-to-create-a-mail-flow-rule-that-blocks-messages-sent-from-a-domain-or-user). An entry in an end-user allow list can override a block set by the administrator.</span></span>
    
- <span data-ttu-id="32d64-p111">**ユーザーのメッセージ報告アドインをオンにする**: [ユーザーのメッセージ報告アドインを有効にする](enable-the-report-message-add-in.md)ことを強くお勧めします。管理者は、ユーザーが送信しているフィードバックを調べ、何らかのパターンを使用して、問題の原因となっている可能性がある設定を調整することもできます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p111">**Turn on the report message add-in for users** We strongly recommend that you [enable the report message add-in for you users](enable-the-report-message-add-in.md). As an administrator, you may also be able to view the feedback your users are sending and use any patterns to adjust any settings that may be causing problems.</span></span>
- <span data-ttu-id="32d64-139">**[DKIM](use-dkim-to-validate-outbound-email.md)を有効にする**: これにより、すべての送信メッセージに署名して、ドメインとテナントのセキュリティを強化します。</span><span class="sxs-lookup"><span data-stu-id="32d64-139">**Enable [DKIM](use-dkim-to-validate-outbound-email.md)** to sign all your outbound messages to increase the security in your domain and tenant.</span></span>
 > [!TIP]
> <span data-ttu-id="32d64-140">DKIM を有効化したら、[DMARC](use-dkim-to-validate-outbound-email.md) も有効にする必要があります。このレコードにより、DKIM と SPF が正しく動作していることを確認するためです。また、秘密キーと公開対称キーは O365 によって管理されるため、ほとんどのスプーフィング電子メールには署名がありません。</span><span class="sxs-lookup"><span data-stu-id="32d64-140">After you enable DKIM you must enable [DMARC](use-dkim-to-validate-outbound-email.md) since this record will validate if DKIM and SPF are working correctly and, generally, spoofing emails don't have the signature, since O365 manages your private and public symmetric key.</span></span>
    
### <a name="for-users"></a><span data-ttu-id="32d64-141">ユーザー向け</span><span class="sxs-lookup"><span data-stu-id="32d64-141">For users</span></span>

- <span data-ttu-id="32d64-p112">**迷惑メール ルールを有効にして許可リストを確認する**: 迷惑メール対策ルールが有効で、送信者または送信者のドメインが個人の許可リストでバイパスするように設定されていないことを確認します。これらの設定にアクセスする最適な方法は、[禁止または許可 (迷惑メール設定)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46) の使用です。その際に、送信者のメール アドレスまたはドメインをブロックするように選択することもできます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p112">**Enable the junk mail rule and check your allow list** Check that the junk mail action rule is enabled and that the sender or sender's domain is not set to bypass in your personal allow list. The best way to access these settings is from [Block or allow (junk email settings)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). While you are there, you may also choose to block the sender's email address or domain.</span></span>
    
- <span data-ttu-id="32d64-p113">**Microsoft に迷惑メールを報告する** [メッセージ報告アドインを使用する](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) を使用して、Microsoft に迷惑メール メッセージを報告します。また、junk@office365.microsoft.com にメッセージを送信し、1 つ以上のメッセージをレポートに添付することができます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p113">**Report spam to Microsoft** Report spam messages to Microsoft by using the [Use the Report Message add-in](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Additionally, you can send a message to junk@office365.microsoft.com and attach one or more messages to report.</span></span>
    
    <span data-ttu-id="32d64-147">**重要**: メッセージを添付ファイルとして転送しなければ、ヘッダーがないために Office 365 の迷惑メール フィルターの改善ができなくなります。</span><span class="sxs-lookup"><span data-stu-id="32d64-147">**Important** If you do not forward the messages as attachments, then the headers will be missing and we will be unable to improve the junk mail filtering in Office 365.</span></span> 
    
- <span data-ttu-id="32d64-p114">**バルク メールの受信を停止する**: サインアップしたメッセージ (ニュースレター、製品アナウンスなど) に、信頼できる送信元からの登録解除リンクが含まれている場合は、簡単に登録を解除することができます。Office 365 では通常、こうしたメッセージをスパムとして扱いません。また、送信者をブロックしたり、すべてのバルク メールをスパムとして扱うように管理者に設定変更を依頼したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="32d64-p114">**Unsubscribe from bulk email** If the message was something that you signed up for (newsletters, product announcements, etc.) and contains an unsubscribe link from a reputable source, you may want to simply unsubscribe. Office 365 does not typically treat these messages as spam. You can also choose to block the sender, or ask your administrator to make a change that will cause all bulk mail to be treated as spam.</span></span>
