---
title: Office 365 のメール フローのインテリジェンス
ms.author: chrisda
author: chrisda
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理者は、Office 365 のコネクタを使用したメッセージ配信に関連付けられているエラーコード (メールフローインテリジェンスとも呼ばれます) について学ぶことができます。
ms.openlocfilehash: d9ddfdf7c54c8dc709c3d5ae03d9fbd76a153f7e
ms.sourcegitcommit: 0f93b37c39d807dec91f118aa671a3430c47a9ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/20/2019
ms.locfileid: "30692776"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="7f5d2-103">Office 365 のメール フローのインテリジェンス</span><span class="sxs-lookup"><span data-stu-id="7f5d2-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="7f5d2-104">通常は、コネクタを使用して、Office 365 組織からオンプレミスの電子メール環境に電子メールメッセージをルーティングします。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-104">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment.</span></span> <span data-ttu-id="7f5d2-105">また、Office 365 からパートナーの組織へメッセージをルーティングするためにコネクタを使用することもあります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-105">You might also use a connector to route messages from Office 365 to a partner organization.</span></span> <span data-ttu-id="7f5d2-106">Office 365 がコネクタ経由でこれらのメッセージを配信することができない場合、それらのメッセージは Office 365 でキューに入れられます。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-106">When Office 365 can't deliver these messages via the connector, they're queued in Office 365.</span></span> <span data-ttu-id="7f5d2-107">Office 365 は、48 時間にわたって各メッセージの配信を再試行し続けます。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-107">Office 365 will continue to retry delivery for each message for 48 hours.</span></span> <span data-ttu-id="7f5d2-108">48 時間後、キュー内のメッセージは失効し、配信不能レポート (NDR、またはバウンス メッセージとも呼ばれます) 内で元の送信者にそのメッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-108">After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="7f5d2-109">コネクタを使用してメッセージを配信できない場合、Office 365 はエラーを生成します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-109">Office 365 generates an error when a message can't be delivered by using a connector.</span></span> <span data-ttu-id="7f5d2-110">最も一般的なエラーとその解決策について、このトピックで説明します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-110">The most common errors and their solutions are described in this topic.</span></span> <span data-ttu-id="7f5d2-111">コネクタ経由で送信された配信不能メッセージのキューイングおよび通知エラーは、_メールフローインテリジェンス_と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-111">Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="7f5d2-112">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="7f5d2-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="7f5d2-113">通常、このエラーは、Office 365 がコネクタで指定されたスマートホストに接続しようとしたが、スマートホストの IP アドレスを見つけるための DNS クエリが失敗したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-113">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed.</span></span> <span data-ttu-id="7f5d2-114">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="7f5d2-114">The possible causes for this error are:</span></span>

- <span data-ttu-id="7f5d2-115">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="7f5d2-116">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="7f5d2-117">ご使用のドメインの MX レコードが最近変更されましたが、Office 365 DNS サーバーは以前にキャッシュに入れられていたドメインの DNS 情報を依然として保持しています。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="7f5d2-118">エラーコード 450 4.4.312 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="7f5d2-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="7f5d2-119">DNS ホスティングサービスと協力して、ドメインに関する問題を特定して修正します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="7f5d2-120">エラーがパートナー組織 (たとえば、サードパーティのクラウドサービスプロバイダー) によるものである場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="7f5d2-121">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="7f5d2-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="7f5d2-122">通常、これは Office 365 が宛先の電子メールサーバーに接続できないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-122">Typically, this means Office 365 can't connect to the destination email server.</span></span> <span data-ttu-id="7f5d2-123">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-123">The error details will explain the problem.</span></span> <span data-ttu-id="7f5d2-124">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-124">For example:</span></span>

- <span data-ttu-id="7f5d2-125">オンプレミスの電子メールサーバーがダウンしています。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="7f5d2-126">コネクタのスマート ホストの設定にエラーがあるため、Office 365 が誤った IP アドレスに接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="7f5d2-127">エラーコード 450 4.4.315 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="7f5d2-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="7f5d2-128">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-128">Find out which scenario applies to you, and make the necessary corrections.</span></span> <span data-ttu-id="7f5d2-129">たとえば、メールフローが正しく動作していて、コネクタの設定を変更していない場合は、オンプレミスの電子メール環境をチェックして、サーバーがダウンしているかどうか、またはネットワークインフラストラクチャに何らかの変更があったかどうかを確認する必要があります (例:インターネットサービスプロバイダーが変更され、IP アドレスが異なるようになりました。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-129">For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="7f5d2-130">エラーがパートナー組織 (たとえば、サードパーティのクラウドサービスプロバイダー) によるものである場合は、パートナーに連絡して問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="7f5d2-131">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="7f5d2-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="7f5d2-132">通常、このエラーは、Office 365 が宛先の電子メールサーバーに接続しようとしたときに接続エラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-132">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server.</span></span> <span data-ttu-id="7f5d2-133">このエラーの原因として考えられるのは、ファイアウォールが Office 365 の IP アドレスからの接続をブロックしている場合です。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-133">A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses.</span></span> <span data-ttu-id="7f5d2-134">または、オンプレミスの電子メールシステムを Office 365 に完全に移行し、オンプレミスの電子メール環境をシャットダウンした場合に、このエラーが発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-134">Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="7f5d2-135">エラーコード 450 4.4.316 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="7f5d2-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="7f5d2-136">オンプレミスの環境にメールボックスがある場合は、TCP ポート25で Office 365 の IP アドレスからオンプレミスの電子メールサーバーへの接続を許可するように、ファイアウォールの設定を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-136">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers.</span></span> <span data-ttu-id="7f5d2-137">Office 365 の IP アドレスの一覧については、「[Office 365 URL および IP アドレス範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-137">For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="7f5d2-p108">それ以上のエラー メッセージがオンプレミス環境に配信されないようにするには、通知内の **[今すぐ修正]** をクリックして、Office 365 が無効な受信者によるメッセージをすぐに拒否できるようにします。これにより、組織の無効な受信者用のクオータを超過するリスクが低減されます。このクオータの超過は、通常メッセージの配信に影響を及ぼすことがあります。または、次の手順を実行して、手動で問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="7f5d2-141">office 365 の[Exchange 管理センター (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center)で、office 365 からオンプレミスの電子メール環境に電子メールを配信するコネクタを無効にするか、削除します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="7f5d2-142">EAC で、[**メールフロー** \> **コネクタ**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="7f5d2-143">[**差出人**] の値が**Office 365**で、[**宛先**] が**組織の電子メールサーバー**の値であるコネクタを選択し、次の手順のいずれかを実行します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="7f5d2-144">[削除] [削除\*\*\*\* ![] アイコンをクリックしてコネクタを削除する](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="7f5d2-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="7f5d2-145">[ \*\*\*\* ![編集] 編集アイコンをクリックし](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)てコネクタを無効にし、 **[オンにする**] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="7f5d2-146">オンプレミスの電子メール環境に関連付けられている Office 365 の承認済みドメインを、**内部の中継**から [**権限**あり] に変更します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-146">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**.</span></span> <span data-ttu-id="7f5d2-147">手順については、「 [Exchange Online で承認済みドメインを管理](https://go.microsoft.com/fwlink/p/?linkid=785428)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-147">For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="7f5d2-148">**注**: 通常、これらの変更は30分から1時間かかり、有効になります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-148">**Note**: Typically, these changes take between 30 minutes and one hour to take effect.</span></span> <span data-ttu-id="7f5d2-149">1時間後に、エラーが表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-149">After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="7f5d2-150">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="7f5d2-151">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="7f5d2-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="7f5d2-152">通常、このエラーは、Office 365 が宛先の電子メールサーバーに接続されたが、サーバーが即時エラーで応答したか、接続要件を満たしていないことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-152">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements.</span></span> <span data-ttu-id="7f5d2-153">エラーの詳細に、この問題についての説明があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-153">The error details will explain the problem.</span></span> <span data-ttu-id="7f5d2-154">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-154">For example:</span></span>

- <span data-ttu-id="7f5d2-155">宛先の電子メールサーバーが、"サービスは利用できません" というエラーで応答しました。これは、サーバーが Office 365 との通信を維持できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="7f5d2-156">コネクタは tls を要求するように構成されていますが、送信先の電子メールサーバーが tls をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="7f5d2-157">エラーコード 450 4.4.317 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="7f5d2-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="7f5d2-158">オンプレミスの電子メールサーバー上の tls 設定と証明書、およびコネクタの tls 設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="7f5d2-159">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="7f5d2-160">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="7f5d2-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="7f5d2-161">通常、このエラーは、Office 365 がオンプレミスの電子メール環境と通信する際に問題が発生し、接続が切断されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-161">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped.</span></span> <span data-ttu-id="7f5d2-162">このエラーの考えられる原因:</span><span class="sxs-lookup"><span data-stu-id="7f5d2-162">The possible causes for this error are:</span></span>

- <span data-ttu-id="7f5d2-163">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="7f5d2-164">オンプレミスの電子メールサーバーが正しく動作していない (たとえば、サービスのハング、クラッシュ、システムリソースの不足) ため、サーバーがタイムアウトして Office 365 への接続を終了しています。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="7f5d2-165">オンプレミス環境と Office 365 の間にネットワークの問題があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="7f5d2-166">エラーコード 450 4.4.318 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="7f5d2-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="7f5d2-167">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="7f5d2-168">オンプレミス環境と Office 365 の間のネットワークの問題によって問題が発生している場合は、ネットワークチームに連絡して問題のトラブルシューティングを依頼してください。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="7f5d2-169">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="7f5d2-170">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="7f5d2-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="7f5d2-171">通常、このエラーは、Office 365 が宛先の電子メールサーバーの証明書を検証しようとしたときにエラーが発生したことを意味します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-171">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server.</span></span> <span data-ttu-id="7f5d2-172">エラーの詳細に、このエラーについての説明があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-172">The error details will explain the error.</span></span> <span data-ttu-id="7f5d2-173">例:</span><span class="sxs-lookup"><span data-stu-id="7f5d2-173">For example:</span></span>

- <span data-ttu-id="7f5d2-174">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="7f5d2-174">Certificate expired</span></span>

- <span data-ttu-id="7f5d2-175">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="7f5d2-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="7f5d2-176">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="7f5d2-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="7f5d2-177">エラーコード 450 4.7.320 を修正する方法</span><span class="sxs-lookup"><span data-stu-id="7f5d2-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="7f5d2-178">Office 365 でキューに入れられたメッセージが配信されるように、コネクタの証明書または設定を修正します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="7f5d2-179">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="7f5d2-180">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="7f5d2-180">Other error codes</span></span>

<span data-ttu-id="7f5d2-181">Office 365 は、オンプレミスまたはパートナーの電子メールサーバーにメッセージを配信する際に問題が発生しています。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-181">Office 365 is having difficulty delivering messages to your on-premises or partner email server.</span></span> <span data-ttu-id="7f5d2-182">エラーに含まれる **宛先サーバー**の情報を確認して、ご使用の環境の問題を調べるか、構成エラーがあった場合はコネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-182">Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="7f5d2-183">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f5d2-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
