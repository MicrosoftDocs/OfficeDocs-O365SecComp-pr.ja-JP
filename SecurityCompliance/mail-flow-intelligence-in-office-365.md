---
title: Office 365 のメール フローのインテリジェンス
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/27/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: '通常、コネクタを使用する、メッセージをルーティングする、Office 365 の組織から、設置するメッセージング環境です。パートナーの組織にメッセージをルーティングする Office 365 からコネクタを使用する可能性がありますもします。Office 365 は、これらのコネクタ経由でメッセージを配信できない、Office 365 で、キューに登録しています。 '
ms.openlocfilehash: 495d73524afb3ab3a34fd2f1f5f4cd747481f9d8
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027624"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="88e5e-105">Office 365 のメール フローのインテリジェンス</span><span class="sxs-lookup"><span data-stu-id="88e5e-105">Mail flow intelligence in Office 365</span></span>
  
<span data-ttu-id="88e5e-p102">通常は、コネクタを使用して、自分の Office 365 組織からオンプレミスのメッセージング環境へとメッセージをルーティングします。また、Office 365 からパートナーの組織へメッセージをルーティングするためにコネクタを使用することもあります。Office 365 がコネクタ経由でこれらのメッセージを配信することができない場合、それらのメッセージは Office 365 でキューに入れられます。Office 365 は、48 時間にわたって各メッセージの配信を再試行し続けます。48 時間後、キュー内のメッセージは失効し、配信不能レポート (NDR、またはバウンス メッセージとも呼ばれます) 内で元の送信者にそのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p102">Typically, you use a connector to route messages from your Office 365 organization to your on-premises messaging environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>
  
<span data-ttu-id="88e5e-p103">コネクタを使用してメッセージを配信できない場合、Office 365 はエラーを生成します。最も一般的なエラーとその解決策について、このトピックで説明します。コネクタ経由で送信された配信不能メッセージのキューイングおよび通知エラーは、総称としてメールフロー インテリジェンスと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p103">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as mailflow intelligence.</span></span>
  
 <span data-ttu-id="88e5e-114">**内容**</span><span class="sxs-lookup"><span data-stu-id="88e5e-114">**Contents**</span></span>
  
- [<span data-ttu-id="88e5e-115">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="88e5e-115">Error code: 450 4.4.312 DNS query failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44312)
    
- [<span data-ttu-id="88e5e-116">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="88e5e-116">Error code: 450 4.4.315 Connection timed out</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44315)
    
- [<span data-ttu-id="88e5e-117">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="88e5e-117">Error code: 450 4.4.316 Connection refused</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44316)
    
- [<span data-ttu-id="88e5e-118">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="88e5e-118">Error code: 450 4.4.317 Cannot connect to remote server</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44317)
    
- [<span data-ttu-id="88e5e-119">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="88e5e-119">Error code: 450 4.4.318 Connection was closed abruptly</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode44318)
    
- [<span data-ttu-id="88e5e-120">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="88e5e-120">Error code: 450 4.7.320 Certificate validation failed</span></span>](mail-flow-intelligence-in-office-365.md#ErrorCode47320)
    
## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="88e5e-121">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="88e5e-121">Error code: 450 4.4.312 DNS query failed</span></span>
<span data-ttu-id="88e5e-122"><a name="ErrorCode44312"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-122"></span></span>

<span data-ttu-id="88e5e-p104">通常、このエラーは、Office 365 がコネクタで指定されたスマート ホストに接続しようとしたが、スマート ホストの IP アドレスを見つけるための DNS クエリが失敗したことを意味します。このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="88e5e-p104">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host IP addresses failed. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="88e5e-125">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-125">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>
    
- <span data-ttu-id="88e5e-126">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="88e5e-126">Your domain has recently expired, so the MX record can't be retrieved.</span></span>
    
- <span data-ttu-id="88e5e-127">ご使用のドメインの MX レコードが最近変更されましたが、Office 365 DNS サーバーは以前にキャッシュに入れられていたドメインの DNS 情報を依然として保持しています。</span><span class="sxs-lookup"><span data-stu-id="88e5e-127">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>
    
<span data-ttu-id="88e5e-128">DNS ホスティング サービスと共に DNS の問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-128">You need to fix the DNS issue by working with your DNS hosting service.</span></span>
  
<span data-ttu-id="88e5e-129">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-129">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="88e5e-130">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="88e5e-130">Error code: 450 4.4.315 Connection timed out</span></span>
<span data-ttu-id="88e5e-131"><a name="ErrorCode44315"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-131"></span></span>

<span data-ttu-id="88e5e-p105">通常、これは Office 365 が宛先のメッセージング サーバーに接続できないことを意味します。エラーの詳細に、この問題についての説明があります。例:</span><span class="sxs-lookup"><span data-stu-id="88e5e-p105">Typically, this means Office 365 can't connect to the destination messaging server. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="88e5e-135">オンプレミスのメッセージング サーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="88e5e-135">Your on-premises messaging server is down.</span></span>
    
- <span data-ttu-id="88e5e-136">コネクタのスマート ホストの設定にエラーがあるため、Office 365 が誤った IP アドレスに接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="88e5e-136">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>
    
<span data-ttu-id="88e5e-p106">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。たとえば、メール フローがこれまで正しく動作していて、コネクタの設定を変更していない場合は、オンプレミスのメッセージング環境をチェックして、サーバーがダウンしていないか、またはネットワーク インフラストラクチャへの変更 (たとえば、インターネット サービス プロバイダーを変更したため、IP アドレスが以前とは異なる) があったかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p106">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises messaging environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed Internet service providers, so you now have different IP addresses).</span></span>
  
<span data-ttu-id="88e5e-139">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-139">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="88e5e-140">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="88e5e-140">Error code: 450 4.4.316 Connection refused</span></span>
<span data-ttu-id="88e5e-141"><a name="ErrorCode44316"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-141"></span></span>

<span data-ttu-id="88e5e-p107">通常、このエラーは、Office 365 が宛先のメッセージング サーバーに接続を試みたときに接続エラーが発生したことを意味します。このエラーの原因として考えられるのは、ファイアウォールが Office 365 の IP アドレスからの接続をブロックしている場合です。そうでなければ、オンプレミス メッセージング システムの Office 365 への移行が完了して、オンプレミスのメッセージング環境をシャット ダウンするときの計画的なエラーであると考えられます。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p107">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination messaging server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises messaging system to Office 365 and shut down your on-premises messaging environment..</span></span>
  
- <span data-ttu-id="88e5e-p108">オンプレミスの環境にメールボックスがある場合は、TCP ポート 25 で Office 365 の IP アドレスからオンプレミスのメッセージング サーバーへの接続を許可するようにファイアウォールの設定を変更する必要があります。Office 365 の IP アドレスの一覧については、「[Office 365 URL および IP アドレス範囲](https://go.microsoft.com/fwlink/p/?linkid=228887)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p108">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises messaging servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=228887).</span></span>
    
- <span data-ttu-id="88e5e-p109">それ以上のエラー メッセージがオンプレミス環境に配信されないようにするには、通知内の **[今すぐ修正]** をクリックして、Office 365 が無効な受信者によるメッセージをすぐに拒否できるようにします。これにより、組織の無効な受信者用のクオータを超過するリスクが低減されます。このクオータの超過は、通常メッセージの配信に影響を及ぼすことがあります。または、次の手順を実行して、手動で問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p109">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span> 
    
  - <span data-ttu-id="88e5e-p110">無効にするか、オンプレミス環境から Office 365 のコネクタを削除: Office 365 管理者センター \> **管理センター** \> **Exchange** \> **メールの流れ** \> **コネクタ**\>を選択して、**Office 365** **の**値を持つコネクタ**に**値が **、組織の電子メール サーバー**。**削除**] をクリックして、コネクタを削除![削除アイコン](media/ITPro-EAC-DeleteIcon.png)、または**編集**] をクリックして、コネクタを無効にする![[編集] アイコン](media/ITPro-EAC-EditIcon.png)チェックを**オンに**するとします。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p110">Disable or delete the connector from Office 365 to your on-premises environment: Office 365 admin center \> **Admin centers** \> **Exchange** \> **Mail flow** \> **Connectors** \> select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server**. Delete the connector by clicking **Delete**![Delete icon](media/ITPro-EAC-DeleteIcon.png), or disable the connector by clicking **Edit**![Edit icon](media/ITPro-EAC-EditIcon.png) and unchecking **Turn it on**.</span></span>
    
  - <span data-ttu-id="88e5e-p111">オンプレミスのメッセージング環境に関連付けられている Office 365 の承認済みドメインを、 **[内部の中継]** から **[権限あり]** に変更します。手順については、「 [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p111">Change the accepted domain in Office 365 that's associated with your on-premises messaging environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage Accepted Domains in Exchange Online](http://technet.microsoft.com/library/0fc0ecc0-e133-48fa-9d72-cb4793a73960.aspx).</span></span>
    
    <span data-ttu-id="88e5e-p112">**注**: 有効にするために 30 分と 1 時間の間でこれらの変更に一般に、します。1 時間後に、不要になったエラーが発生することを確認します。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p112">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>
    
<span data-ttu-id="88e5e-156">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-156">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="88e5e-157">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="88e5e-157">Error code: 450 4.4.317 Cannot connect to remote server</span></span>
<span data-ttu-id="88e5e-158"><a name="ErrorCode44317"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-158"></span></span>

<span data-ttu-id="88e5e-p113">通常、このエラーは、Office 365 が宛先のメッセージング サーバーに接続したが、サーバーが即座にエラーを返したか、接続要件を満たしていないことを意味します。エラーの詳細に、この問題についての説明があります。例:</span><span class="sxs-lookup"><span data-stu-id="88e5e-p113">Typically, this error means Office 365 connected to the destination messaging server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>
  
- <span data-ttu-id="88e5e-162">宛先のメッセージング サーバーが、"サービスは利用できません" のエラーで応答しました。これは、サーバーが Office 365 との通信を維持できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="88e5e-162">The destination messaging server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>
    
- <span data-ttu-id="88e5e-163">コネクタは TLS を要求するように設定されていますが、宛先のメッセージング サーバーが TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="88e5e-163">The connector is configured to require TLS, but the destination messaging server doesn't support TLS.</span></span>
    
<span data-ttu-id="88e5e-164">オンプレミスのメッセージング サーバーの TLS の設定と証明書と、コネクタの TLS の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="88e5e-164">Verify the TLS settings and certificates on your on-premises messaging servers, and the TLS settings on the connector.</span></span>
  
<span data-ttu-id="88e5e-165">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-165">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="88e5e-166">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="88e5e-166">Error code: 450 4.4.318 Connection was closed abruptly</span></span>
<span data-ttu-id="88e5e-167"><a name="ErrorCode44318"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-167"></span></span>

<span data-ttu-id="88e5e-p114">通常、このエラーは、Office 365 とオンプレミスのメッセージング環境との通信に問題が生じ、接続が切断されたことを意味します。このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="88e5e-p114">Typically, this error means Office 365 is having difficulty communicating with your on-premises messaging environment, so the connection was dropped. The possible causes for this error are:</span></span>
  
- <span data-ttu-id="88e5e-170">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="88e5e-170">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>
    
- <span data-ttu-id="88e5e-171">オンプレミスのメッセージング サーバーが正しく動作していない (たとえば、サービスのハング、クラッシュ、システム リソースの不足) ため、Office 365 への接続がタイムアウトし、終了しました。</span><span class="sxs-lookup"><span data-stu-id="88e5e-171">Your on-premises messaging server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>
    
- <span data-ttu-id="88e5e-p115">オンプレミス環境と Office 365 の間にネットワークの問題があります。問題が解決しない場合は、ネットワーク チームに連絡して、問題のトラブルシューティングを依頼してください。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p115">There are network issues between your on-premises environment and Office 365. If the problem persists, contact your network team to troubleshoot the issue.</span></span>
    
<span data-ttu-id="88e5e-174">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="88e5e-174">Find out which scenario applies to you, and make the necessary corrections.</span></span>
  
<span data-ttu-id="88e5e-175">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-175">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="88e5e-176">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="88e5e-176">Error code: 450 4.7.320 Certificate validation failed</span></span>
<span data-ttu-id="88e5e-177"><a name="ErrorCode47320"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-177"></span></span>

<span data-ttu-id="88e5e-p116">通常、このエラーは、Office 365が宛先のメッセージング サーバーの証明書を検証しているときにエラーが発生したことを意味します。エラーの詳細に、このエラーについての説明があります。例:</span><span class="sxs-lookup"><span data-stu-id="88e5e-p116">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination messaging server. The error details will explain the error. For example:</span></span>
  
- <span data-ttu-id="88e5e-181">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="88e5e-181">Certificate expired</span></span>
    
- <span data-ttu-id="88e5e-182">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="88e5e-182">Certificate subject mismatch</span></span>
    
- <span data-ttu-id="88e5e-183">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="88e5e-183">Certificate is no longer valid</span></span>
    
<span data-ttu-id="88e5e-184">証明書かコネクタを修正し、Office 365 でキューに入れられているメッセージが配信されるようにしてください。</span><span class="sxs-lookup"><span data-stu-id="88e5e-184">Please fix the certificate or the connector so that queued messages in Office 365can be delivered.</span></span>
  
<span data-ttu-id="88e5e-185">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-185">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  
## <a name="other-error-codes"></a><span data-ttu-id="88e5e-186">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="88e5e-186">Other error codes</span></span>
<span data-ttu-id="88e5e-187"><a name="sectionSection6"> </a></span><span class="sxs-lookup"><span data-stu-id="88e5e-187"></span></span>

<span data-ttu-id="88e5e-p117">Office 365 がオンプレミスまたはパートナーのメッセージング サーバーにメッセージを配信する際に問題が発生しています。エラーに含まれる **宛先サーバー**の情報を確認して、ご使用の環境の問題を調べるか、構成エラーがあった場合はコネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="88e5e-p117">Office 365 is having difficulty delivering messages to your on-premises or partner messaging server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 
  
<span data-ttu-id="88e5e-190">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88e5e-190">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
  

