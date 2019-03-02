---
title: Exchange Online で電子メール接続をセキュリティで保護するために Office 365 で TLS を使用する方法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Exchange Online および Office 365 で、トランスポート層セキュリティ (TLS) とフォワード機密性 (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。また、Microsoft によって発行された Exchange Online 用の証明書に関する情報も取得します。
ms.openlocfilehash: e80f477c807f3a7ad5f751e0987b191024c816d9
ms.sourcegitcommit: 03054baf50c1dd5cd9ca6a9bd5d056f3db98f964
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/01/2019
ms.locfileid: "30354629"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a><span data-ttu-id="0f42b-104">Exchange Online で電子メール接続をセキュリティで保護するために Office 365 で TLS を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0f42b-104">How Exchange Online uses TLS to secure email connections in Office 365</span></span>

<span data-ttu-id="0f42b-p102">Exchange Online および Office 365 で、トランスポート層セキュリティ (TLS) とフォワード機密性 (FS) を使用して電子メール通信をセキュリティで保護する方法について説明します。また、Microsoft によって発行された Exchange Online 用の証明書に関する情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p102">Learn how Exchange Online and Office 365 use Transport Layer Security (TLS) and Forward Secrecy (FS) to secure email communications. Also provides information about the certificate issued by Microsoft for Exchange Online.</span></span>
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a><span data-ttu-id="0f42b-107">Office 365 および Exchange Online の TLS の基礎</span><span class="sxs-lookup"><span data-stu-id="0f42b-107">TLS basics for Office 365 and Exchange Online</span></span>

<span data-ttu-id="0f42b-p103">tls の前に送信されたトランスポート層セキュリティ (tls) と SSL は、セキュリティ証明書を使用して、コンピューター間の接続を暗号化することにより、ネットワーク上での通信をセキュリティで保護する暗号化プロトコルです。TLS は ssl (Secure Sockets layer) に優先され、ssl 3.1 と呼ばれることがよくあります。exchange Online の場合、TLS を使用して、exchange サーバーと、社内 exchange サーバーや受信者のメールサーバーなどの他のサーバーとの間の接続を暗号化します。接続が暗号化されると、その接続を介して送信されるすべてのデータが暗号化チャネル経由で送信されます。ただし、TLS で暗号化された接続を介して送信されたメッセージを転送する場合、そのメッセージは必ずしも暗号化されません。これは、単純に言うと、TLS はメッセージを暗号化せず、接続だけであるからです。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. TLS supersedes Secure Sockets Layer (SSL) and is often referred to as SSL 3.1. For Exchange Online, we use TLS to encrypt the connections between our Exchange servers and the connections between our Exchange servers and other servers such as your on-premises Exchange servers or your recipients' mail servers. Once the connection is encrypted, all data sent through that connection is sent through the encrypted channel. However, if you forward a message that was sent through a TLS-encrypted connection, that message isn't necessarily encrypted. This is because, in simple terms, TLS doesn't encrypt the message, just the connection.</span></span>
  
<span data-ttu-id="0f42b-p104">メッセージを暗号化する場合は、メッセージの内容を暗号化する、Office Message Encryption のような暗号化技術を使用する必要があります。Office 365 におけるメッセージ暗号化のオプションについては、「[Email encryption in Office 365](email-encryption.md)」と「[Office 365 Message Encryption (OME)](ome.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p104">If you want to encrypt the message you need to use an encryption technology that encrypts the message contents, for example, something like Office Message Encryption. See [Email encryption in Office 365](email-encryption.md) and [Office 365 Message Encryption (OME)](ome.md) for information on message encryption options in Office 365.</span></span> 
  
<span data-ttu-id="0f42b-p105">Office 365 とオンプレミスの組織またはパートナーなどの他の組織との間の通信のセキュリティで保護されたチャネルを設定する必要がある場合は、TLS を使用することをお勧めします。Exchange Online は常に tls を使用して電子メールをセキュリティで保護しようとしますが、相手が tls セキュリティを提供していない場合は常にこれを実行することはできません。*コネクタ*を使用して、オンプレミスのサーバーまたは重要なパートナーへのすべてのメールをセキュリティで保護する方法については、読み続けてください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p105">We recommend using TLS in situations where you want to set up a secure channel of correspondence between Office 365 and your on-premises organization or another organization, such as a partner. Exchange Online always attempts to use TLS first to secure your email but cannot always do this if the other party does not offer TLS security. Keep reading to find out how you can secure all mail to your on-premises servers or important partners by using  *connectors*.</span></span> 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a><span data-ttu-id="0f42b-119">Exchange Online で Exchange Online 顧客間において TLS を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0f42b-119">How Exchange Online uses TLS between Exchange Online customers</span></span>

<span data-ttu-id="0f42b-p106">Exchange Online サーバーでは、Microsoft のデータセンター内にある他の Exchange Online サーバーに対する接続を TLS 1.2 を使用して常に暗号化します。Office 365 組織内で電子メールを受信側に送信すると、そのメールは TLS を使用して暗号化された接続を介して自動的に送信されます。また、他の Office 365 の顧客に送信するすべての電子メールは TSL を使用して暗号化された接続を使用して送信され、FS (Forward Secrecy) を使用してセキュリティ保護されます。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p106">Exchange Online servers always encrypt connections to other Exchange Online servers in our datacenters with TLS 1.2. When you send mail to a recipient that is within your Office 365 organization, that email is automatically sent over a connection that is encrypted using TLS. Also, all email that you send to other Office 365 customers is sent over connections that are encrypted using TLS and are secured using Forward Secrecy.</span></span>
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a><span data-ttu-id="0f42b-123">office 365 が office 365 と外部の信頼されたパートナーの間で TLS を使用する方法</span><span class="sxs-lookup"><span data-stu-id="0f42b-123">How Office 365 uses TLS between Office 365 and external, trusted partners</span></span>

<span data-ttu-id="0f42b-p107">既定では、Exchange Online は常に便宜的な TLS を使用します。そのため、Exchange Online は常に最も安全なバージョンの tls を使用して接続を暗号化しようとし、両方の当事者が同意することが検出されるまで、tls 暗号のリストを下に移動します。その受信者宛てのメッセージがセキュリティで保護された接続を介してのみ送信されるように Exchange Online を構成していない限り、受信者の組織が TLS 暗号化をサポートしていない場合、既定ではメッセージは暗号化されずに送信されます。多くの企業にとって、便宜的な TLS は十分です。ただし、医療、バンキング、行政機関などのコンプライアンス要件があるビジネスでは、Exchange Online を構成して、TLS を要求するか強制することができます。手順については、「 [Office 365 でコネクタを使用してメールフローを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p107">By default, Exchange Online always uses opportunistic TLS. This means Exchange Online always tries to encrypt connections with the most secure version of TLS first, then works its way down the list of TLS ciphers until it finds one on which both parties can agree. Unless you have configured Exchange Online to ensure that messages to that recipient are only sent through secure connections, then by default the message will be sent unencrypted if the recipient organization doesn't support TLS encryption. Opportunistic TLS is sufficient for most businesses. However, for business that have compliance requirements such as medical, banking, or government organizations, you can configure Exchange Online to require, or force, TLS. For instructions, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="0f42b-p108">組織と信頼できるパートナー組織との間で tls を構成する場合、Exchange Online は強制的な tls を使用して信頼された通信チャネルを作成できます。強制 TLS では、パートナー組織がメールを送信するために、セキュリティ証明書を使用して Exchange Online に対して認証を行う必要があります。そのためには、パートナーが自分の証明書を管理する必要があります。Exchange Online では、コネクタを使用して、受信者の電子メールプロバイダーに到着する前に、承認されていないアクセスから送信されたメッセージを保護します。コネクタを使用してメールフローを構成する方法については、「 [configure mail flow using コネクタ using Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p108">If you decide to configure TLS between your organization and a trusted partner organization, Exchange Online can use forced TLS to create trusted channels of communication. Forced TLS requires your partner organization to authenticate to Exchange Online with a security certificate in order to send mail to you. Your partner will need to manage their own certificates in order to do this. In Exchange Online, we use connectors to protect messages that you send from unauthorized access before they arrive at the recipient's email provider. For information on using connectors to configure mail flow, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a><span data-ttu-id="0f42b-135">TLS と Exchange Server ハイブリッド展開</span><span class="sxs-lookup"><span data-stu-id="0f42b-135">TLS and hybrid Exchange Server deployments</span></span>

<span data-ttu-id="0f42b-p109">ハイブリッド exchange 展開を管理している場合、オンプレミスの exchange サーバーは、office 365 にのみメールボックスがある受信者にメールを送信するために、セキュリティ証明書を使用して office 365 に認証する必要があります。そのため、オンプレミスの Exchange サーバーの独自のセキュリティ証明書を管理する必要があります。また、これらのサーバー証明書を安全に保存および維持する必要があります。ハイブリッド展開での証明書の管理の詳細については、「[ハイブリッド展開の証明書要件](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p109">If you are managing a hybrid Exchange deployment, your on-premises Exchange server needs to authenticate to Office 365 using a security certificate in order to send mail to recipients whose mailboxes are only in Office 365. As a result, you need to manage your own security certificates for your on-premises Exchange servers. You must also securely store and maintain these server certificates. For more information about managing certificates in hybrid deployments, see [Certificate requirements for hybrid deployments](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).</span></span>
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a><span data-ttu-id="0f42b-140">Office 365 における Exchange Online 用強制 TLS のセットアップ方法</span><span class="sxs-lookup"><span data-stu-id="0f42b-140">How to set up forced TLS for Exchange Online in Office 365</span></span>

<span data-ttu-id="0f42b-p110">Exchange Online のお客様の場合、すべての送受信メールをセキュリティで保護するために強制的に tls を使用するには、tls を必要とする複数のコネクタを設定する必要があります。ユーザーのメールボックスに送信される電子メール用のコネクタと、ユーザーのメールボックスから送信される電子メール用のコネクタが1つ必要になります。Office 365 の Exchange 管理センターでこれらのコネクタを作成します。手順については、「 [Office 365 でコネクタを使用してメールフローを構成する](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p110">For Exchange Online customers, in order for forced TLS to work to secure all of your sent and received email, you need to set up more than one connector that requires TLS. You'll need one connector for email sent to your user mailboxes and another connector for email sent from your user mailboxes. Create these connectors in the Exchange admin center in Office 365. For instructions, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
## <a name="tls-certificate-information-for-exchange-online"></a><span data-ttu-id="0f42b-145">Exchange Online の TLS 証明書情報</span><span class="sxs-lookup"><span data-stu-id="0f42b-145">TLS certificate information for Exchange Online</span></span>

<span data-ttu-id="0f42b-p111">次の表では、Exchange Online で使用される証明書情報について説明します。ビジネスパートナーが電子メールサーバーで強制的に TLS を設定している場合は、この情報をユーザーに提供する必要があります。セキュリティ上の理由から、証明書は随時変更されることに注意してください。データセンター内での証明書への更新をロールアウトしました。新しい証明書は2018年9月3日から有効になっています。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p111">The certificate information used by Exchange Online is described in the following table. If your business partner is setting up forced TLS on their email server, you will need to provide this information to them. Be aware that for security reasons, our certificates do change from time to time. We have rolled out an update to our certificate within our datacenters. The new certificate is valid from September 3, 2018.</span></span>
  
 <span data-ttu-id="0f42b-151">**2018年9月3日から有効な現在の証明書情報**</span><span class="sxs-lookup"><span data-stu-id="0f42b-151">**Current certificate information valid from September 3, 2018**</span></span>
  
|<span data-ttu-id="0f42b-152">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="0f42b-152">**Attribute**</span></span>|<span data-ttu-id="0f42b-153">**値**</span><span class="sxs-lookup"><span data-stu-id="0f42b-153">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f42b-154">証明機関ルート発行者</span><span class="sxs-lookup"><span data-stu-id="0f42b-154">Certificate authority root issuer</span></span>  <br/> |<span data-ttu-id="0f42b-155">globalsign ルート CA – R1</span><span class="sxs-lookup"><span data-stu-id="0f42b-155">GlobalSign Root CA – R1</span></span> <br/> |
|<span data-ttu-id="0f42b-156">証明書名</span><span class="sxs-lookup"><span data-stu-id="0f42b-156">Certificate name</span></span>  <br/> |<span data-ttu-id="0f42b-157">mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0f42b-157">mail.protection.outlook.com</span></span>  <br/> |
|<span data-ttu-id="0f42b-158">組織</span><span class="sxs-lookup"><span data-stu-id="0f42b-158">Organization</span></span>  <br/> |<span data-ttu-id="0f42b-159">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0f42b-159">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="0f42b-160">組織単位</span><span class="sxs-lookup"><span data-stu-id="0f42b-160">Organization unit</span></span>  <br/> |  <br/> |
|<span data-ttu-id="0f42b-161">証明書キーの強度</span><span class="sxs-lookup"><span data-stu-id="0f42b-161">Certificate key strength</span></span>  <br/> |<span data-ttu-id="0f42b-162">2048</span><span class="sxs-lookup"><span data-stu-id="0f42b-162">2048</span></span>  <br/> |
   
 <span data-ttu-id="0f42b-163">**非推奨の証明書情報は、2018年9月3日まで有効です。**</span><span class="sxs-lookup"><span data-stu-id="0f42b-163">**Deprecated certificate information valid until September 3, 2018**</span></span>
  
<span data-ttu-id="0f42b-164">移行を円滑に行うために、しばらくの間、参照用の古い証明書情報を引き続き提供する予定です。ただし、現時点では現在の証明書情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f42b-164">To help ensure a smooth transition, we will continue to provide the old certificate information for your reference for some time, however, you should use the current certificate information from now on.</span></span>
  
****

|<span data-ttu-id="0f42b-165">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="0f42b-165">**Attribute**</span></span>|<span data-ttu-id="0f42b-166">**値**</span><span class="sxs-lookup"><span data-stu-id="0f42b-166">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f42b-167">証明機関ルート発行者</span><span class="sxs-lookup"><span data-stu-id="0f42b-167">Certificate authority root issuer</span></span>  <br/> |<span data-ttu-id="0f42b-168">Baltimore CyberTrust Root</span><span class="sxs-lookup"><span data-stu-id="0f42b-168">Baltimore CyberTrust Root</span></span>  <br/> |
|<span data-ttu-id="0f42b-169">証明書名</span><span class="sxs-lookup"><span data-stu-id="0f42b-169">Certificate name</span></span>  <br/> |<span data-ttu-id="0f42b-170">mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="0f42b-170">mail.protection.outlook.com</span></span>  <br/> |
|<span data-ttu-id="0f42b-171">組織</span><span class="sxs-lookup"><span data-stu-id="0f42b-171">Organization</span></span>  <br/> |<span data-ttu-id="0f42b-172">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0f42b-172">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="0f42b-173">組織単位</span><span class="sxs-lookup"><span data-stu-id="0f42b-173">Organization unit</span></span>  <br/> |<span data-ttu-id="0f42b-174">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0f42b-174">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="0f42b-175">証明書キーの強度</span><span class="sxs-lookup"><span data-stu-id="0f42b-175">Certificate key strength</span></span>  <br/> |<span data-ttu-id="0f42b-176">2048</span><span class="sxs-lookup"><span data-stu-id="0f42b-176">2048</span></span>  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a><span data-ttu-id="0f42b-177">新しい Exchange Online 証明書の準備</span><span class="sxs-lookup"><span data-stu-id="0f42b-177">Prepare for the new Exchange Online certificate</span></span>

<span data-ttu-id="0f42b-p112">新しい証明書は、Exchange Online で使用される以前の証明書から、別の証明機関 (CA) によって発行されます。そのため、新しい証明書を使用するためにいくつかの操作を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p112">The new certificate is issued by a different certificate authority (CA) from the previous certificate used by Exchange Online. As a result, you may need to perform some actions in order to use the new certificate.</span></span>

<span data-ttu-id="0f42b-p113">新しい証明書では、証明書の検証の一環として、新しい CA のエンドポイントに接続する必要があります。これを怠ると、メールフローが悪影響を受けてしまう可能性があります。メールサーバーに特定の宛先のみが接続できるようにするファイアウォールを使用してメールサーバーを保護する場合は、サーバーが新しい証明書を検証できるかどうかを確認する必要があります。サーバーが新しい証明書を使用できることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p113">The new certificate requires connecting to the endpoints of the new CA as part of validating the certificate. Failure to do so can result in mail flow being negatively affected. If you protect your mail servers with firewalls that only let the mail servers connect with certain destinations you need to check if your server is able to validate the new certificate. To confirm that your server can use the new certificate, complete these steps:</span></span>

1. <span data-ttu-id="0f42b-184">Windows PowerShell を使用してローカルの Exchange サーバーに接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f42b-184">Connect to your local Exchange Server using Windows PowerShell and then run the following command:</span></span>  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. <span data-ttu-id="0f42b-185">表示されるウィンドウで、[**取得**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f42b-185">On the window that appears, choose **Retrieve**.</span></span>
3. <span data-ttu-id="0f42b-p114">ユーティリティがチェックを完了すると、状態が返されます。状態が **[OK]** と表示されている場合、メールサーバーは新しい証明書を正常に検証できます。それ以外の場合は、接続が失敗する原因を特定する必要があります。多くの場合、ファイアウォールの設定を更新する必要があります。アクセスする必要があるエンドポイントの完全なリストは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p114">When the utility completes its check it returns a status. If the status displays **OK**, then your mail server can successfully validate the new certificate. If not, you need to determine what is causing the connections to fail. Most likely, you need to update the settings of a firewall. The full list of endpoints that need to be accessed include:</span></span>
    - <span data-ttu-id="0f42b-191">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="0f42b-191">ocsp.globalsign.com</span></span>
     - <span data-ttu-id="0f42b-192">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="0f42b-192">crl.globalsign.com</span></span>
     - <span data-ttu-id="0f42b-193">secure.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="0f42b-193">secure.globalsign.com</span></span>   

<span data-ttu-id="0f42b-p115">通常、Windows Update を使用してルート証明書の更新を自動的に受信します。ただし、一部の展開では、これらの更新が自動的に実行されないようにするための追加のセキュリティがあります。Windows Update でルート証明書を自動更新できない、ロックダウンされたこれらの展開では、次の手順を実行して、正しいルート CA 証明書がインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0f42b-p115">Normally, you receive updates to your root certificates automatically through Windows Update. However some deployments have additional security in place that prevents these updates from occurring automatically. In these locked-down deployments where Windows Update can't automatically update root certificates, you need to ensure that the correct root CA certificate is installed by completing these steps:</span></span>
1.  <span data-ttu-id="0f42b-197">Windows PowerShell を使用してローカルの Exchange サーバーに接続し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="0f42b-197">Connect to your local Exchange Server using Windows PowerShell and then run the following command:</span></span>  
  `certmgr.msc`
2. <span data-ttu-id="0f42b-198">[**信頼されたルート証明機関/証明書**] の下で、新しい証明書が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0f42b-198">Under **Trusted Root Certification Authority/Certificates**, confirm that the new certificate is listed.</span></span>

## <a name="get-more-information-about-tls-and-office-365"></a><span data-ttu-id="0f42b-199">TLS と Office 365 に関する追加情報</span><span class="sxs-lookup"><span data-stu-id="0f42b-199">Get more information about TLS and Office 365</span></span>

<span data-ttu-id="0f42b-200">サポートされている暗号スイートの一覧については、「 [Office 365 の暗号化に関するテクニカルリファレンスの詳細](technical-reference-details-about-encryption.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0f42b-200">For a list of supported cipher suites, see [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).</span></span>
  
[<span data-ttu-id="0f42b-201">パートナー組織とのセキュリティで保護されたメール フロー用のコネクタを設定する</span><span class="sxs-lookup"><span data-stu-id="0f42b-201">Set up connectors for secure mail flow with a partner organization</span></span>](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="0f42b-202">電子メール セキュリティを強化したコネクタ</span><span class="sxs-lookup"><span data-stu-id="0f42b-202">Connectors with enhanced email security</span></span>](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[<span data-ttu-id="0f42b-203">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="0f42b-203">Encryption in Office 365</span></span>](encryption.md)
  

