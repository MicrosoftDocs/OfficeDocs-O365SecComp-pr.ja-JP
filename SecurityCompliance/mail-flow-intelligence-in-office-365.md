---
title: Office 365 のメール フローのインテリジェンス
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c29f75e5-c16e-409e-a123-430691e38276
description: 管理者は、Office 365 (メール フロー ・ インテリジェンスとも呼ばれます) のコネクタを使用してメッセージの配信に関連付けられているエラー コードについて学習できます。
ms.openlocfilehash: 9f27dfd4c265eb62028d68c27764183202692ef4
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "28327089"
---
# <a name="mail-flow-intelligence-in-office-365"></a><span data-ttu-id="1b4da-103">Office 365 のメール フローのインテリジェンス</span><span class="sxs-lookup"><span data-stu-id="1b4da-103">Mail flow intelligence in Office 365</span></span>

<span data-ttu-id="1b4da-p101">通常、オンプレミス メール環境に Office 365 の組織から電子メール メッセージをルーティングするのにコネクタを使用します。パートナーの組織にメッセージをルーティングする Office 365 からコネクタを使用する可能性がありますもします。Office 365 は、これらのコネクタ経由でメッセージを配信できない、Office 365 で、キューに登録しています。Office 365 は、48 時間で各メッセージの配信を再試行するのには続行されます。後 48 時間は、キュー内のメッセージの有効期限、および、メッセージが配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) では、元の送信者に返されます。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p101">Typically, you use a connector to route email messages from your Office 365 organization to your on-premises email environment. You might also use a connector to route messages from Office 365 to a partner organization. When Office 365 can't deliver these messages via the connector, they're queued in Office 365. Office 365 will continue to retry delivery for each message for 48 hours. After 48 hours, the queued message will expire, and the message will be returned to the original sender in a non-delivery report (also known as an NDR or bounce message).</span></span>

<span data-ttu-id="1b4da-p102">Office 365 では、コネクタを使用してメッセージを配信できない場合、エラーが生成されます。最も一般的なエラーとその解決策については、このトピックで説明します。まとめて、コネクタ経由で送信、配信不能メッセージのキューおよび通知のエラーは、_メール フローのインテリジェンス_と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p102">Office 365 generates an error when a message can't be delivered by using a connector. The most common errors and their solutions are described in this topic. Collectively, queuing and notification errors for undeliverable messages sent via connectors is known as _mail flow intelligence_.</span></span>

## <a name="error-code-450-44312-dns-query-failed"></a><span data-ttu-id="1b4da-112">エラー コード:450 4.4.312 DNS クエリに失敗しました</span><span class="sxs-lookup"><span data-stu-id="1b4da-112">Error code: 450 4.4.312 DNS query failed</span></span>

<span data-ttu-id="1b4da-p103">通常、このエラーは、Office 365 は、コネクタが、DNS を検索するクエリに失敗しました、スマート ホストの IP アドレスで指定されているスマート ホストに接続しようとしています。このエラーの考えられる原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p103">Typically, this error means Office 365 tried to connect to the smart host that's specified in the connector, but the DNS query to find the smart host's IP addresses failed. The possible causes for this error are:</span></span>

- <span data-ttu-id="1b4da-115">ご使用のドメインの DNS ホスティング サービス (ご使用のドメインの権威ネーム サーバーを管理しているパーティ) に問題があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-115">There's an issue with your domain's DNS hosting service (the party that maintains the authoritative name servers for your domain).</span></span>

- <span data-ttu-id="1b4da-116">ご使用のドメインの有効期限が最近切れたため、MX レコードを取得できません。</span><span class="sxs-lookup"><span data-stu-id="1b4da-116">Your domain has recently expired, so the MX record can't be retrieved.</span></span>

- <span data-ttu-id="1b4da-117">ご使用のドメインの MX レコードが最近変更されましたが、Office 365 DNS サーバーは以前にキャッシュに入れられていたドメインの DNS 情報を依然として保持しています。</span><span class="sxs-lookup"><span data-stu-id="1b4da-117">Your domain's MX record has recently changed, and the Office 365 DNS servers still have previously cached DNS information for your domain.</span></span>

### <a name="how-do-i-fix-error-code-450-44312"></a><span data-ttu-id="1b4da-118">450 4.4.312 のエラー コードを修正する方法は?</span><span class="sxs-lookup"><span data-stu-id="1b4da-118">How do I fix error code 450 4.4.312?</span></span>

- <span data-ttu-id="1b4da-119">特定し、ドメインの問題を解決するサービスをホストしている DNS を使用します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-119">Work with your DNS hosting service to identify and fix the problem with your domain.</span></span>

- <span data-ttu-id="1b4da-120">パートナー組織 (たとえば、サード パーティ クラウド サービス プロバイダー) からのエラーの場合は、問題を解決するパートナーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1b4da-120">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44315-connection-timed-out"></a><span data-ttu-id="1b4da-121">エラー コード:450 4.4.315 接続がタイムアウトしました</span><span class="sxs-lookup"><span data-stu-id="1b4da-121">Error code: 450 4.4.315 Connection timed out</span></span>

<span data-ttu-id="1b4da-p104">通常、つまり、Office 365 は、送信先の電子メール サーバーに接続できません。エラーの詳細では、問題について説明します。例えば：</span><span class="sxs-lookup"><span data-stu-id="1b4da-p104">Typically, this means Office 365 can't connect to the destination email server. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="1b4da-125">オンプレミス メール サーバーがダウンします。</span><span class="sxs-lookup"><span data-stu-id="1b4da-125">Your on-premises email server is down.</span></span>

- <span data-ttu-id="1b4da-126">コネクタのスマート ホストの設定にエラーがあるため、Office 365 が誤った IP アドレスに接続しようとしています。</span><span class="sxs-lookup"><span data-stu-id="1b4da-126">There's an error in the connector's smart host settings, so Office 365 is trying to connect to the wrong IP address.</span></span>

### <a name="how-do-i-fix-error-code-450-44315"></a><span data-ttu-id="1b4da-127">450 4.4.315 のエラー コードを修正する方法は?</span><span class="sxs-lookup"><span data-stu-id="1b4da-127">How do I fix error code 450 4.4.315?</span></span>

- <span data-ttu-id="1b4da-p105">どのシナリオを選択することを確認し、必要な訂正します。たとえば、メール フローが正しく動作して、コネクタの設定を変更していない場合は、する必要がありますされている場合、ネットワーク インフラストラクチャへの変更 (たとえば、またはサーバーがダウンしている場合に、オンプレミス メール環境を確認するには変更したインターネット サービス プロバイダーでは、ここで別の IP アドレスがあるため)。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p105">Find out which scenario applies to you, and make the necessary corrections. For example, if mail flow has been working correctly, and you haven't changed the connector settings, you need to check your on-premises email environment to see if the server is down, or if there have been any changes to your network infrastructure (for example, you've changed internet service providers, so you now have different IP addresses).</span></span>

- <span data-ttu-id="1b4da-130">パートナー組織 (たとえば、サード パーティ クラウド サービス プロバイダー) からのエラーの場合は、問題を解決するパートナーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1b4da-130">If the error is from your partner organization (for example, a 3rd party cloud service provider), contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44316-connection-refused"></a><span data-ttu-id="1b4da-131">エラー コード:450 4.4.316 接続が拒否されました</span><span class="sxs-lookup"><span data-stu-id="1b4da-131">Error code: 450 4.4.316 Connection refused</span></span>

<span data-ttu-id="1b4da-p106">通常、このエラーは、Office 365 では、宛先の電子メール サーバーに接続するときに接続エラーが発生しました。このエラーが発生することが原因としては、Office 365 の IP アドレスからの接続をブロックしているファイアウォールです。または、このエラー可能性がありますデザインを完全に移行する場合、設置型のメール ・ システムが Office 365 と、オンプレミスのメール環境をシャット ダウンします。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p106">Typically, this error means Office 365 encountered a connection error when it tried to connect to the destination email server. A likely cause for this error is your firewall is blocking connections from Office 365 IP addresses. Or, this error might be by design if you've completely migrated your on-premises email system to Office 365 and shut down your on-premises email environment.</span></span>

### <a name="how-do-i-fix-error-code-450-44316"></a><span data-ttu-id="1b4da-135">450 4.4.316 のエラー コードを修正する方法は?</span><span class="sxs-lookup"><span data-stu-id="1b4da-135">How do I fix error code 450 4.4.316?</span></span>

- <span data-ttu-id="1b4da-p107">場合は、オンプレミス環境でのメールボックスがある場合、オンプレミス メール サーバーに TCP ポート 25 上の Office 365 の IP アドレスからの接続を許可するファイアウォールの設定を変更する必要があります。Office 365 の IP アドレスのリストは、 [Office 365 の Url と IP アドレスの範囲](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p107">If you have mailboxes in your on-premises environment, you need to modify your firewall settings to allow connections from Office 365 IP addresses on TCP port 25 to your on-premises email servers. For a list of the Office 365 IP addresses, see [Office 365 URLs and IP address ranges](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2.aspx).</span></span>

- <span data-ttu-id="1b4da-p108">それ以上のエラー メッセージがオンプレミス環境に配信されないようにするには、通知内の **[今すぐ修正]** をクリックして、Office 365 が無効な受信者によるメッセージをすぐに拒否できるようにします。これにより、組織の無効な受信者用のクオータを超過するリスクが低減されます。このクオータの超過は、通常メッセージの配信に影響を及ぼすことがあります。または、次の手順を実行して、手動で問題を修正します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p108">If no more messages should be delivered to your on-premises environment, click **Fix now** in the alert so Office 365 can immediately reject the messages with invalid recipients. This will reduce the risk of exceeding your organization's quota for invalid recipients, which could impact normal message delivery. Or, you can use the following instructions to manually fix the issue:</span></span>

  - <span data-ttu-id="1b4da-141">Office 365 の[Exchange 管理センター (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) 、無効にするか、オンプレミスのメール環境を Office 365 から電子メールを配信する、コネクタの削除します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-141">In the [Exchange admin center (EAC)](https://docs.microsoft.com/Exchange/exchange-admin-center) in Office 365, disable or delete the connector that delivers email from Office 365 to your on-premises email environment:</span></span>

    1. <span data-ttu-id="1b4da-142">**メール フロー**には、EAC で\>**のコネクタ**です。</span><span class="sxs-lookup"><span data-stu-id="1b4da-142">In the EAC, go to **Mail flow** \> **Connectors**.</span></span>

    2. <span data-ttu-id="1b4da-143">**Office 365** **の**値を持つコネクタと **、組織の電子メール サーバー** **に**値を選択し、次の手順のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1b4da-143">Select the connector with the **From** value **Office 365** and the **To** value **Your organization's email server** and do one of the following steps:</span></span>

       - <span data-ttu-id="1b4da-144">**削除**] をクリックして、コネクタの削除![削除アイコン](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span><span class="sxs-lookup"><span data-stu-id="1b4da-144">Delete the connector by clicking **Delete** ![Remove icon](media/adf01106-cc79-475c-8673-065371c1897b.gif)</span></span>

       - <span data-ttu-id="1b4da-145">**編集**] をクリックして、コネクタを無効にする![[編集] アイコン](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif)チェックを**オンに**するとします。</span><span class="sxs-lookup"><span data-stu-id="1b4da-145">Disable the connector by clicking **Edit** ![Edit icon](media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) and unchecking **Turn it on**.</span></span>

  - <span data-ttu-id="1b4da-p109">**権限のある\*\*\*\*内部のリレー**からオンプレミス メール環境に関連付けられている Office 365 の承認済みドメインを変更します。手順については、[管理が受け入れドメイン Exchange オンライン](https://go.microsoft.com/fwlink/p/?linkid=785428)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p109">Change the accepted domain in Office 365 that's associated with your on-premises email environment from **Internal Relay** to **Authoritative**. For instructions, see [Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=785428).</span></span>

  <span data-ttu-id="1b4da-p110">**注**: 有効にするために 30 分と 1 時間の間でこれらの変更に一般に、します。1 時間後に、不要になったエラーが発生することを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p110">**Note**: Typically, these changes take between 30 minutes and one hour to take effect. After one hour, verify that you no longer receive the error.</span></span>

- <span data-ttu-id="1b4da-150">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-150">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44317-cannot-connect-to-remote-server"></a><span data-ttu-id="1b4da-151">エラー コード:450 4.4.317 リモート サーバーに接続できません</span><span class="sxs-lookup"><span data-stu-id="1b4da-151">Error code: 450 4.4.317 Cannot connect to remote server</span></span>

<span data-ttu-id="1b4da-p111">通常、このエラーは、Office 365 は、宛先の電子メール サーバーに接続されているが、サーバーは、すぐにエラーで応答しましたまたは、接続の要件を満たしていない場合します。エラーの詳細では、問題について説明します。例えば：</span><span class="sxs-lookup"><span data-stu-id="1b4da-p111">Typically, this error means Office 365 connected to the destination email server, but the server responded with an immediate error, or doesn't meet the connection requirements. The error details will explain the problem. For example:</span></span>

- <span data-ttu-id="1b4da-155">「サービスは利用できません」エラーで転送先の電子メール サーバーが応答したサーバーを示すことができません Office 365 と通信を維持します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-155">The destination email server responded with a "Service not available" error, which indicates the server is unable to maintain communication with Office 365.</span></span>

- <span data-ttu-id="1b4da-156">コネクタが TLS を要求するように構成されているが、送信先の電子メール サーバーが TLS をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="1b4da-156">The connector is configured to require TLS, but the destination email server doesn't support TLS.</span></span>

### <a name="how-do-i-fix-error-code-450-44317"></a><span data-ttu-id="1b4da-157">450 4.4.317 のエラー コードを修正する方法は?</span><span class="sxs-lookup"><span data-stu-id="1b4da-157">How do I fix error code 450 4.4.317?</span></span>

- <span data-ttu-id="1b4da-158">TLS の設定と、オンプレミス メール サーバー上の証明書と TLS の設定、コネクタを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-158">Verify the TLS settings and certificates on your on-premises email servers, and the TLS settings on the connector.</span></span>

- <span data-ttu-id="1b4da-159">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-159">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-44318-connection-was-closed-abruptly"></a><span data-ttu-id="1b4da-160">エラー コード:450 4.4.318 接続が突然切断されました</span><span class="sxs-lookup"><span data-stu-id="1b4da-160">Error code: 450 4.4.318 Connection was closed abruptly</span></span>

<span data-ttu-id="1b4da-p112">通常、このエラーは、Office 365 に接続が切断されましたので、オンプレミスのメール環境での通信に問題が発生します。このエラーの考えられる原因は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p112">Typically, this error means Office 365 is having difficulty communicating with your on-premises email environment, so the connection was dropped. The possible causes for this error are:</span></span>

- <span data-ttu-id="1b4da-163">ファイアウォールが SMTP パケットの検証規則を使用していますが、それらの規則が正しく動作していません。</span><span class="sxs-lookup"><span data-stu-id="1b4da-163">Your firewall uses SMTP packet examination rules, and those rules aren't working correctly.</span></span>

- <span data-ttu-id="1b4da-164">オンプレミス メール サーバーに勤務している正しく (例、サービスのハング、クラッシュ、またはシステム リソースの不足)、サーバーがタイムアウトする原因となっているはありませんし、Office 365 への接続を閉じます。</span><span class="sxs-lookup"><span data-stu-id="1b4da-164">Your on-premises email server isn't working correctly (for example, service hangs, crashes, or low system resources), which is causing the server to time out and close the connection to Office 365.</span></span>

- <span data-ttu-id="1b4da-165">オンプレミス環境と Office 365 の間にネットワークの問題があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-165">There are network issues between your on-premises environment and Office 365.</span></span>

### <a name="how-do-i-fix-error-code-450-44318"></a><span data-ttu-id="1b4da-166">450 4.4.318 のエラー コードを修正する方法は?</span><span class="sxs-lookup"><span data-stu-id="1b4da-166">How do I fix error code 450 4.4.318?</span></span>

- <span data-ttu-id="1b4da-167">どのシナリオが自分の状況に当てはまるかを調べ、必要な修正を行います。</span><span class="sxs-lookup"><span data-stu-id="1b4da-167">Find out which scenario applies to you, and make the necessary corrections.</span></span>

- <span data-ttu-id="1b4da-168">問題は、オンプレミス環境と Office 365 の間のネットワークの問題に原因がある場合は、問題のトラブルシューティングを行うネットワーク チームにお問い合わせください。</span><span class="sxs-lookup"><span data-stu-id="1b4da-168">If the problem is caused by network issues between your on-premises environment and Office 365, contact your network team to troubleshoot the issue.</span></span>

- <span data-ttu-id="1b4da-169">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-169">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="error-code-450-47320-certificate-validation-failed"></a><span data-ttu-id="1b4da-170">エラー コード:450 4.7.320 証明書の検証に失敗しました</span><span class="sxs-lookup"><span data-stu-id="1b4da-170">Error code: 450 4.7.320 Certificate validation failed</span></span>

<span data-ttu-id="1b4da-p113">通常、このエラーは、Office 365 では、宛先の電子メール サーバーの証明書を検証しているときにエラーが発生しました。エラーの詳細は、エラーを説明します。例えば：</span><span class="sxs-lookup"><span data-stu-id="1b4da-p113">Typically, this error means Office 365 encountered an error while trying to validate the certificate of the destination email server. The error details will explain the error. For example:</span></span>

- <span data-ttu-id="1b4da-174">証明書が期限切れです</span><span class="sxs-lookup"><span data-stu-id="1b4da-174">Certificate expired</span></span>

- <span data-ttu-id="1b4da-175">証明書のサブジェクトが一致しません</span><span class="sxs-lookup"><span data-stu-id="1b4da-175">Certificate subject mismatch</span></span>

- <span data-ttu-id="1b4da-176">証明書が無効です</span><span class="sxs-lookup"><span data-stu-id="1b4da-176">Certificate is no longer valid</span></span>

### <a name="how-do-i-fix-error-code-450-47320"></a><span data-ttu-id="1b4da-177">450 4.7.320 のエラー コードを修正する方法は?</span><span class="sxs-lookup"><span data-stu-id="1b4da-177">How do I fix error code 450 4.7.320?</span></span>

- <span data-ttu-id="1b4da-178">証明書を修正するか、コネクタでの設定は、Office 365 のメッセージをキューに登録されるよう配信できます。</span><span class="sxs-lookup"><span data-stu-id="1b4da-178">Fix the certificate or the settings on the connector so that queued messages in Office 365 can be delivered.</span></span>

- <span data-ttu-id="1b4da-179">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものの場合は、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-179">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>

## <a name="other-error-codes"></a><span data-ttu-id="1b4da-180">その他のエラー コード</span><span class="sxs-lookup"><span data-stu-id="1b4da-180">Other error codes</span></span>

<span data-ttu-id="1b4da-p114">Office 365 は、設置型をメッセージの配信に問題が生じてまたは電子メール サーバーのパートナーです。エラーの**転送先サーバー**情報を使用して、自分の環境で問題を確認または構成エラーがある場合は、コネクタを変更します。</span><span class="sxs-lookup"><span data-stu-id="1b4da-p114">Office 365 is having difficulty delivering messages to your on-premises or partner email server. Use the **Destination server** information in the error to examine the issue in your environment, or modify the connector if there's a configuration error.</span></span> 

<span data-ttu-id="1b4da-183">エラーがパートナー組織 (たとえば、サード パーティのクラウド サービス プロバイダー) によるものである場合、そのパートナーに連絡して問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1b4da-183">If the error is from your partner organization (for example, a 3rd party cloud service provider), you need to contact your partner to fix the issue.</span></span>
