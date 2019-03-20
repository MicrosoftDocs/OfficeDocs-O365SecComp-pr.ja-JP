---
title: Office 365 に送信されるメールのトラブルシューティング
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
ms.collection:
- M365-security-compliance
description: この資料では、Office 365 の受信トレイに電子メールを送信するときに生じる問題に関して送信者が参照できるトラブルシューティング情報と、Office 365 顧客に対するバルク メールのベスト プラクティスについて取り上げます。
ms.openlocfilehash: ac465e7ef42b9cfeb2587481202fab1b5adb5f75
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692106"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a><span data-ttu-id="93ae1-103">Office 365 に送信されるメールのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="93ae1-103">Troubleshooting mail sent to Office 365</span></span>

<span data-ttu-id="93ae1-104">この資料では、Office 365 の受信トレイに電子メールを送信するときに生じる問題に関して送信者が参照できるトラブルシューティング情報と、Office 365 顧客に対するバルク メールのベスト プラクティスについて取り上げます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-104">This article provides troubleshooting information for senders who are experiencing issues when trying to send email to inboxes in Office 365 and best practices for bulk mailing to Office 365 customers.</span></span>
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a><span data-ttu-id="93ae1-105">Office 365 へのメール配信に関する一般的な問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="93ae1-105">Troubleshooting common problems with mail delivery to Office 365</span></span>

<span data-ttu-id="93ae1-106">一般的に見られる次の問題のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="93ae1-106">Choose from one of these commonly encountered issues.</span></span>
  
- [<span data-ttu-id="93ae1-107">IP およびドメインの評価の管理者ですか</span><span class="sxs-lookup"><span data-stu-id="93ae1-107">Are you managing your IP and domain's sending reputation?</span></span>](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [<span data-ttu-id="93ae1-108">新しい IP アドレスから電子メールを送信していますか</span><span class="sxs-lookup"><span data-stu-id="93ae1-108">Are you sending email from new IP addresses?</span></span>](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [<span data-ttu-id="93ae1-109">DNS が正しく設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="93ae1-109">Confirm that your DNS is set up correctly</span></span>](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [<span data-ttu-id="93ae1-110">ルーティング不能な IP で自分をアドバタイズしていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="93ae1-110">Ensure that you do not advertise yourself as a non-routable IP</span></span>](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [<span data-ttu-id="93ae1-111">Office 365 でユーザーに電子メールを送信すると、配信不能レポート (NDR) を受信する</span><span class="sxs-lookup"><span data-stu-id="93ae1-111">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [<span data-ttu-id="93ae1-112">送信した電子メールが、受信側の EOP の迷惑メール フォルダーに分類される</span><span class="sxs-lookup"><span data-stu-id="93ae1-112">My email landed in the recipient's junk folder in EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [<span data-ttu-id="93ae1-113">自分の IP アドレスからのトラフィックが EOP によって調整される</span><span class="sxs-lookup"><span data-stu-id="93ae1-113">Traffic from my IP address is throttled by EOP</span></span>](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a><span data-ttu-id="93ae1-114">IP およびドメインの評価の管理者ですか</span><span class="sxs-lookup"><span data-stu-id="93ae1-114">Are you managing your IP and domain's sending reputation?</span></span>
<span data-ttu-id="93ae1-115"><a name="ManageRep"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-115"></span></span>

<span data-ttu-id="93ae1-p101">EOP のフィルタリング テクノロジは、Microsoft Office 365 において、また Exchange Server、Microsoft Office Outlook、Windows Live メールなどの他の Microsoft 製品においてスパム対策保護機能を提供するように設計されています。Microsoft では SPF、DKIM、DMARC といった電子メール認証テクノロジも活用します。このことにより、電子メールを送信しているドメインにその操作を行う権限があるかどうかを検証することで、なりすましやフィッシング詐欺の問題に対応できるようになります。EOP フィルタリングは、送信元の IP、ドメイン、認証、配布リストの正確さ、苦情の割合、内容などに関連した多数の要因の影響を受けます。これらの中で、送信者の評価および電子メールの配信機能を低下させる主な要因の 1 つは、迷惑メールの苦情の割合です。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p101">EOP filtering technologies are designed to provide anti-spam protections for Microsoft Office 365 as well as other Microsoft products like Exchange Server, Microsoft Office Outlook, and Windows Live Mail. We also leverage SPF, DKIM, and DMARC; email authentication technologies that help address the problem of spoofing and phishing by verifying that the domain sending the email is authorized to do so. EOP filtering is influenced by a number of factors related to the sending IP, domain, authentication, list accuracy, complaint rates, content and more. Of these, one of the principal factors in driving down a sender's reputation and their ability to deliver email is their junk email complaint rate.</span></span> 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a><span data-ttu-id="93ae1-120">新しい IP アドレスから電子メールを送信していますか</span><span class="sxs-lookup"><span data-stu-id="93ae1-120">Are you sending email from new IP addresses?</span></span>
<span data-ttu-id="93ae1-121"><a name="NewIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-121"></span></span>

<span data-ttu-id="93ae1-p102">通常、電子メールを送信するために初めて使用する IP アドレスには、当社のシステムで構築された評価はありません。その結果、新しい IP アドレスからの電子メールでは、配信の問題が発生する可能性が高くなります。迷惑メールを送信しないための評価が IP で構築されると、通常 EOP の電子メール配信エクスペリエンスは向上します。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p102">IP addresses not previously used to send email typically don't have any reputation built up in our systems. As a result, emails from new IPs are more likely to experience delivery issues. Once the IP has built a reputation for not sending spam, EOP will typically allow for a better email delivery experience.</span></span>
  
<span data-ttu-id="93ae1-p103">既存の SPF レコードで認証されているドメインに追加される新しい IP アドレスの場合、通常、そのドメインの送信評価の一部を継承できるという利点があります。ご使用のドメインの送信評価が優れていると、新しい IP の評価もすぐに向上します。新しい IP は、ボリューム、配布リストの正確さ、迷惑メールの苦情の割合に応じて、数週間またはすぐにでも、評価が向上することを期待できます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p103">New IPs that are added for domains that are authenticated under existing SPF records typically experience the added benefit of inheriting some of the domain's sending reputation. If your domain has a good sending reputation new IPs may experience a faster ramp up time. A new IP can expect to be fully ramped within a couple of weeks or sooner depending on volume, list accuracy, and junk email complaint rates.</span></span>
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a><span data-ttu-id="93ae1-128">DNS が正しく設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="93ae1-128">Confirm that your DNS is set up correctly</span></span>
<span data-ttu-id="93ae1-129"><a name="ConfirmDNSsetup"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-129"></span></span>

<span data-ttu-id="93ae1-130">メールのルーティングに必要な MX レコードなど、DNS レコードの作成と保守の手順については、DNS ホスティング プロバイダーに確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93ae1-130">For instructions about how to create and maintain DNS records, including the MX record required for mail routing, you will need to contact your DNS hosting provider.</span></span>
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a><span data-ttu-id="93ae1-131">ルーティング不能な IP で自分をアドバタイズしていないことを確認する</span><span class="sxs-lookup"><span data-stu-id="93ae1-131">Ensure that you do not advertise yourself as a non-routable IP</span></span>
<span data-ttu-id="93ae1-132"><a name="NoReverseDNS"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-132"></span></span>

<span data-ttu-id="93ae1-p104">DNS 逆引き参照を行えない送信者からの電子メールは受け付けないことがあります。場合によっては、正当な送信者が、EOP に対して接続しようとするときに、インターネット ルーティング不能な IP で自身をアドバタイズすることがあります。プライベート (ルーティング不能な) ネットワーク用に予約されている IP アドレスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p104">We may not accept email from senders who fail a reverse-DNS lookup. In some cases, legitimate senders advertise themselves incorrectly as a non-internet routable IP when attempting to open a connection to EOP. IP addresses that are reserved for private (non-routable) networking include:</span></span>
  
- <span data-ttu-id="93ae1-136">192.168.0.0/16 (または 192.168.0.0 ～ 192.168.255.255)</span><span class="sxs-lookup"><span data-stu-id="93ae1-136">192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)</span></span>
    
- <span data-ttu-id="93ae1-137">10.0.0.0/8 (または 10.0.0.0 ～ 10.255.255.255)</span><span class="sxs-lookup"><span data-stu-id="93ae1-137">10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)</span></span>
    
- <span data-ttu-id="93ae1-138">172.16.0.0/11 (または 172.16.0.0 ～ 172.31.255.255)</span><span class="sxs-lookup"><span data-stu-id="93ae1-138">172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)</span></span>
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a><span data-ttu-id="93ae1-139">Office 365 でユーザーに電子メールを送信すると、配信不能レポート (NDR) を受信する</span><span class="sxs-lookup"><span data-stu-id="93ae1-139">You received a non-delivery report (NDR) when sending email to a user in Office 365</span></span>
<span data-ttu-id="93ae1-140"><a name="NDRInbound"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-140"></span></span>

<span data-ttu-id="93ae1-p105">一部の配信の問題の原因は、Microsoft によって送信者の IP アドレスがブロックされていることや、ユーザーのアカウントが以前の迷惑メール処理によって禁止された送信者として識別されていることにあります。エラーがあって NDR を受信したと分かっている場合には、まず、NDR メッセージに記載されている指示に従って問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p105">Some delivery issues are the result of the sender's IP address being blocked by Microsoft or because the user account is identified as banned sender due to previous spam activity. If you believe that you have received the NDR in error, first follow any instructions in the NDR message to resolve the issue.</span></span> 
  
<span data-ttu-id="93ae1-143">受信したエラーの詳細については、「[DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx)」の SMTP エラー コードの完全な一覧をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-143">For more information about the error you received, see the complete list of SMTP error codes in [DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx).</span></span>
  
 <span data-ttu-id="93ae1-144">たとえば、次の NDR を受信した場合、送信 IP アドレスが Microsoft によってブロックされたことを示しています。</span><span class="sxs-lookup"><span data-stu-id="93ae1-144">For example, if you receive the following NDR, it indicates that the sending IP address was blocked by Microsoft.</span></span> 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
<span data-ttu-id="93ae1-145">この一覧から削除を要求するには、[リストから除外のポータルを使って、Office 365 の受信拒否リストから自分自身を削除する](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)という操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-145">To request removal from this list, you can [Use the delist portal to remove yourself from the Office 365 blocked senders list](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md).</span></span>
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a><span data-ttu-id="93ae1-146">送信した電子メールが、受信側の EOP の迷惑メール フォルダーに分類される</span><span class="sxs-lookup"><span data-stu-id="93ae1-146">My email landed in the recipient's junk folder in EOP</span></span>
<span data-ttu-id="93ae1-147"><a name="JunkMailBox"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-147"></span></span>

<span data-ttu-id="93ae1-p106">メッセージが誤ってスパムとして特定された場合、受信側と連絡を取り、その偽陽性メッセージを Microsoft スパム分析チームに送信することができます。Microsoft スパム分析チームでは、メッセージを評価して分析します。分析結果によっては、このメッセージが許可されるようにサービス全体のスパム コンテンツ フィルター ルールが調整されることがあります。スパムとして分類されるべきでないメッセージを Microsoft にメールで送信します。その場合は、次の手順に従ってください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p106">If a message was incorrectly identified as spam by EOP, you can work with the recipient to submit this false positive message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through. You use email to submit messages to Microsoft that should not be classified as spam. When doing so, be sure to use the steps in the following procedure.</span></span>
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a><span data-ttu-id="93ae1-152">偽陽性メッセージを Microsoft スパム分析チームに電子メールで送信するには</span><span class="sxs-lookup"><span data-stu-id="93ae1-152">To use email to submit false positive messages to the Microsoft Spam Analysis Team</span></span>

1. <span data-ttu-id="93ae1-153">スパムではないとして送信するメッセージを保存します。</span><span class="sxs-lookup"><span data-stu-id="93ae1-153">Save the message you want to submit as non-spam.</span></span>
    
2. <span data-ttu-id="93ae1-154">空の新規メッセージを作成して、スパムではないメッセージを添付ファイルとして追加します。</span><span class="sxs-lookup"><span data-stu-id="93ae1-154">Create a new, blank message and attach the non-spam message to it.</span></span>
    
    <span data-ttu-id="93ae1-155">必要に応じて複数のスパムではないメッセージを添付ファイルとして追加できます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-155">You can attach multiple non-spam messages if needed.</span></span>
    
3. <span data-ttu-id="93ae1-156">元のメッセージの件名行をコピーし、新しいメッセージの件名行に貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-156">Copy and paste the original message subject line into the new message subject line.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="93ae1-157">新しいメッセージの本文は空のままにします。</span><span class="sxs-lookup"><span data-stu-id="93ae1-157">Leave the body of the new message empty.</span></span> 
  
4. <span data-ttu-id="93ae1-158">新しいメッセージを [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com) に送信します。</span><span class="sxs-lookup"><span data-stu-id="93ae1-158">Send your new message to [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com).</span></span>
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a><span data-ttu-id="93ae1-159">自分の IP アドレスからのトラフィックが EOP によって調整される</span><span class="sxs-lookup"><span data-stu-id="93ae1-159">Traffic from my IP address is throttled by EOP</span></span>
<span data-ttu-id="93ae1-160"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-160"></span></span>

<span data-ttu-id="93ae1-161">IP アドレスが EOP によって調整されたことを示す NDR を EOP から受信することがあります。例:</span><span class="sxs-lookup"><span data-stu-id="93ae1-161">If you receive an NDR from EOP that indicates that your IP address is being throttled by EOP, for example:</span></span>
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
<span data-ttu-id="93ae1-p107">不審な動作が対象の IP アドレスで検出され、さらに詳しく評価される間、一時的に制限されているために NDR を受信しました。評価によって疑いが晴れると、この制限はすぐ解除されます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p107">You received the NDR because suspicious activity has been detected from the IP address and it has been temporarily restricted while it is being further evaluated. If the suspicion is cleared through evaluation, this restriction will be lifted shortly.</span></span>
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a><span data-ttu-id="93ae1-164">Office 365 で送信者からの電子メールを受信できない</span><span class="sxs-lookup"><span data-stu-id="93ae1-164">I can't receive email from senders in Office 365</span></span>
<span data-ttu-id="93ae1-165"><a name="AllowEOPIPs"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-165"></span></span>

 <span data-ttu-id="93ae1-166">Microsoft ユーザーからのメッセージを受信するには、ご使用のネットワークが Microsoft データセンター内で EOP が使用している IP アドレスからの接続を許可していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-166">In order to receive messages from our users, make sure your network allows connections from the IP addresses that EOP uses in our datacenters.</span></span> <span data-ttu-id="93ae1-167">詳細については、「 [Exchange Online Protection の IP アドレス](eop/exchange-online-protection-ip-addresses.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-167">For more information, see [Exchange Online Protection IP addresses](eop/exchange-online-protection-ip-addresses.md).</span></span> 
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a><span data-ttu-id="93ae1-168">Office 365 ユーザーへのバルク メールのベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="93ae1-168">Best practices for bulk emailing to Office 365 users</span></span>
<span data-ttu-id="93ae1-169"><a name="BulkMailer"> </a></span><span class="sxs-lookup"><span data-stu-id="93ae1-169"></span></span>

<span data-ttu-id="93ae1-170">Office 365 ユーザーにバルク メール キャンペーンを頻繁に行い、電子メールが正常かつタイムリーに到着するようにしたい場合、このセクションのヒントに従ってください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-170">If you often conduct bulk email campaigns to Office 365 users and want to ensure that your emails arrive in a safe and timely manner, follow the tips in this section.</span></span>
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a><span data-ttu-id="93ae1-171">メッセージを送信している [送信元] の名前が反映されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="93ae1-171">Ensure that the From: name reflects who is sending the message</span></span>

<span data-ttu-id="93ae1-p109">[件名] はメッセージの内容に関する要約で、メッセージ本文には、オファリング、サービス、製品について明瞭かつ簡潔に記されている必要があります。 例：</span><span class="sxs-lookup"><span data-stu-id="93ae1-p109">The Subject should be a brief summary of what the message is about, and the message body should clearly and succinctly indicate what the offering, service, or product is about. For example:</span></span>
  
<span data-ttu-id="93ae1-174">正しい</span><span class="sxs-lookup"><span data-stu-id="93ae1-174">Correct</span></span>
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
<span data-ttu-id="93ae1-175">間違い</span><span class="sxs-lookup"><span data-stu-id="93ae1-175">Incorrect</span></span>
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
<span data-ttu-id="93ae1-176">送信元について、また実行内容について分かりやすくすれば、ほとんどのスパム フィルターに引っかかることなく配信しやすくなります。</span><span class="sxs-lookup"><span data-stu-id="93ae1-176">The easier you make it for people to know who you are and what you are doing, the less difficulty you will have delivering through most spam filters.</span></span>
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a><span data-ttu-id="93ae1-177">キャンペーン電子メールには必ず登録解除オプションを含める</span><span class="sxs-lookup"><span data-stu-id="93ae1-177">Always include an unsubscribe option in campaign emails</span></span>

<span data-ttu-id="93ae1-p110">マーケティング電子メール、特にニュースレターなどでは、その後の電子メールを登録解除する方法を必ず含める必要があります。例：</span><span class="sxs-lookup"><span data-stu-id="93ae1-p110">Marketing emails, especially newsletters, should always include a way of unsubscribing from future emails. For example:</span></span>
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
<span data-ttu-id="93ae1-p111">一部の送信者は、「登録解除」という件名で特定のエイリアスに電子メールを送信することを受信者に求めています。これよりも、上記の例の 1 回のクリックで完了する操作を推奨します。受信者に電子メールを送信することを要求する場合、ユーザーがリンクをクリックする際に、すべての必須フィールドにあらかじめデータが入っているようにしてください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p111">Some senders include this option by requiring recipients to send an email to a certain alias with "Unsubscribe" in the subject. This is not preferable to the one-click example above. If you do choose to require recipients to send a mail, ensure that when they click the link, all the required fields are pre-populated.</span></span>
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a><span data-ttu-id="93ae1-183">マーケティング電子メールまたはニュースレターの登録にダブル オプトイン オプションを使用する</span><span class="sxs-lookup"><span data-stu-id="93ae1-183">Use the double opt-in option for marketing email or newsletter registration</span></span>

<span data-ttu-id="93ae1-p112">業界におけるこのベスト プラクティスは、会社の製品またはサービスを利用するためにユーザーによる連絡先情報の登録が必須である、または推奨される場合に適しています。一部の会社では、登録プロセスの際にマーケティング電子メールまたはニュースレターにユーザーを自動的にサインアップするようになっていますが、これは電子メールのフィルタリングにおいては問題のあるマーケティング手法であると見なされています。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p112">This industry best practice is recommended if your company requires or encourages users to register their contact information in order to access your product or services. Some companies make it a practice to automatically sign up their users for marketing emails or e-newsletters during the registration process, but this is considered a questionable marketing practice in the world of email filtering.</span></span>
  
<span data-ttu-id="93ae1-186">登録プロセスで、「はい、ニュースレターを送信してください」、「はい、特別なオファーを送信してください」などのチェックボックスが既定で選択されていると、不注意なユーザーが、受信の必要のないマーケティング電子メールやニュースレターに意図せずにサインアップする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="93ae1-186">During the registration process, if the "Yes, please send me your newsletter" or "Yes, please send me special offers" checkbox is selected by default, users who do not pay close attention may unintentionally sign up for marketing email or newsletters that they do not want to receive.</span></span>
  
 <span data-ttu-id="93ae1-p113">代わりに、ダブル オプトイン オプションの使用をお勧めします。このオプションでは、マーケティング電子メールまたはニュースレターのチェックボックスは既定で選択されていない状態になっています。さらに、登録フォームが送信されると、確認の電子メールがユーザーに送信されます。そのメールには、マーケティング電子メールを受信する意思を確認するための URL が記載されています。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p113">We recommend the double opt-in option instead, which means that the checkbox for marketing emails or newsletters is unchecked by default. Additionally, once the registration form has been submitted, a verification email is sent to the user with a URL that allows them to confirm their decision to receive marketing emails.</span></span> 
  
 <span data-ttu-id="93ae1-189">これにより、マーケティング電子メールを本当に受信する意志があるユーザーだけが電子メールにサインアップするようになり、以降は、問題のあるマーケティング電子メール手法を送信元の会社から排除できます。</span><span class="sxs-lookup"><span data-stu-id="93ae1-189">This helps ensure that only those users who want to receive marketing email are signed up for the emails, subsequently clearing the sending company of any questionable email marketing practices.</span></span> 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a><span data-ttu-id="93ae1-190">電子メール メッセージの内容が透過的かつトレース可能であることを確認する</span><span class="sxs-lookup"><span data-stu-id="93ae1-190">Ensure that email message content is transparent and traceable</span></span>

<span data-ttu-id="93ae1-p114">電子メールの送信方法と同様、その内容も重要になります。電子メール コンテンツを作成するときは、次のベスト プラクティスを使用して、電子メールがフィルタリング サービスによってフラグ設定されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p114">Just as important as the way the emails are sent is the content they contain. When creating email content, use the following best practices to ensure that your emails will not be flagged by email filtering services:</span></span>
  
- <span data-ttu-id="93ae1-193">送信者をアドレス帳に追加するよう、電子メール・メッセージが受信者に要求する場合、そうした操作がメールの配信を保証するものではないことを明記する必要があります。</span><span class="sxs-lookup"><span data-stu-id="93ae1-193">When the email message requests that recipients add the sender to the address book, it should clearly state that such action is not a guarantee of delivery.</span></span>
    
- <span data-ttu-id="93ae1-p115">メッセージ本文に含まれるリダイレクトは、類似性と一貫性があるべきで、多種多様であってはなりません。このコンテキストのリダイレクトとは、リンクやドキュメントなど、メッセージから離れた任意の対象のことです。広告や登録解除リンク、またはプロファイルの更新リンクがたくさんある場合には、すべてが同じドメインを指していなければなりません。例：</span><span class="sxs-lookup"><span data-stu-id="93ae1-p115">Redirects included in the body of the message should be similar and consistent, and not multiple and varied. A redirect in this context is anything that points away from the message, such as links and documents. If you have a lot of advertising or Unsubscribe links or Update the Profile links, they should all point to the same domain. For example:</span></span>
    
    <span data-ttu-id="93ae1-198">正しい</span><span class="sxs-lookup"><span data-stu-id="93ae1-198">Correct</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    <span data-ttu-id="93ae1-199">間違い</span><span class="sxs-lookup"><span data-stu-id="93ae1-199">Incorrect</span></span>
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- <span data-ttu-id="93ae1-200">サイズの大きな画像や添付ファイル、画像だけのメッセージは避けてください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-200">Avoid content with large images and attachments, or messages that are solely composed of an image.</span></span>
    
- <span data-ttu-id="93ae1-201">パブリック プライバシーまたは P3P 設定では、トラッキング ピクセルが存在することを明記する必要があります (Web バグまたはビーコン)。</span><span class="sxs-lookup"><span data-stu-id="93ae1-201">Your public privacy or P3P settings should clearly state the presence of tracking pixels (web bugs or beacons).</span></span>
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a><span data-ttu-id="93ae1-202">データベースから不正な電子メール エイリアスを削除する</span><span class="sxs-lookup"><span data-stu-id="93ae1-202">Remove incorrect email aliases from your databases</span></span>

<span data-ttu-id="93ae1-p116">バウンス バックを作成するデータベース内のすべての電子メール エイリアスは不要であり、電子メールのフィルタリング サービスによってさらにセキュリティを確保するうえで送信メールを危険にさらすものです。電子メール データベースを最新の情報に保ってください。</span><span class="sxs-lookup"><span data-stu-id="93ae1-p116">Any email alias in your database that creates a bounce-back is unnecessary and puts your outbound emails at risk for further scrutiny by email filtering services. Ensure that your email database is up-to-date.</span></span>
  

