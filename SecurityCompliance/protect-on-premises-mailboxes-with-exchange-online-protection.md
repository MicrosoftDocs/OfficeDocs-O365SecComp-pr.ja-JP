---
title: Exchange Online Protection を使用して社内メールボックスを保護する
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。コネクタを構成するには、アカウントが Office 365 グローバル管理者、または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「office 2013 で運用されている管理者ロールの割り当て」を参照してください。すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。
ms.openlocfilehash: 40fb5471a084cf245d9aef7f7b2b88effb5c4a83
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276037"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a><span data-ttu-id="d0011-106">Exchange Online Protection を使用して社内メールボックスを保護する</span><span class="sxs-lookup"><span data-stu-id="d0011-106">Protect on-premises mailboxes with Exchange Online Protection</span></span>

> [!NOTE]
> <span data-ttu-id="d0011-107">この記事は、中国で21vianet が運営する Office 365 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d0011-107">This article applies only to Office 365 operated by 21Vianet in China.</span></span> 
  
<span data-ttu-id="d0011-p102">一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。コネクタを構成するには、アカウントが Office 365 グローバル管理者、または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「 [office 2013 で運用されている管理者ロールの割り当て](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)」を参照してください。すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。</span><span class="sxs-lookup"><span data-stu-id="d0011-p102">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP). To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span> 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="d0011-112">手順 1: Office 365 管理センターを使用してドメインを追加して管理する</span><span class="sxs-lookup"><span data-stu-id="d0011-112">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="d0011-113">Office 365 管理センターで、 [セットアップ] に移動して、サービスにドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d0011-113">In the Office 365 admin center, navigate to Setup to add your domain to the service.</span></span>
    
2.  <span data-ttu-id="d0011-114">ポータルの手順に従って、ドメインの所有権を確認するために、該当する dns レコードを dns ホストプロバイダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="d0011-114">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span> 
    
> [!TIP]
> <span data-ttu-id="d0011-115">「 [21vianet が運用する office 365 にドメインとユーザーを追加](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)する」と「 [office の dns レコードを作成](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)する」を参照してください。 dns レコードを管理するときは、ドメインをサービスに追加して dns を構成する際に参照するのに役立つリソースです。</span><span class="sxs-lookup"><span data-stu-id="d0011-115">[Add your domain and users to Office 365 operated by 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) and [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="d0011-116">手順 2: 受信者を追加してドメインの種類を構成する</span><span class="sxs-lookup"><span data-stu-id="d0011-116">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="d0011-p103">EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](https://go.microsoft.com/fwlink/?LinkId=506782)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p103">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).</span></span>
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="d0011-121">手順 3:EAC を使用してメール フローをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d0011-121">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="d0011-p104">Exchange 管理センター (EAC) で、EOP とオンプレミスのメールサーバー間のメールフローを有効にするコネクタを作成します。詳細な手順については、「 [EOP による基本的なメールフローの設定に必要なコネクタを作成する](https://go.microsoft.com/fwlink/?LinkId=506780)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p104">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Create required connectors to set up basic email flow through EOP](https://go.microsoft.com/fwlink/?LinkId=506780).</span></span>
  
 <span data-ttu-id="d0011-124">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="d0011-124">How do you know this task worked?</span></span> 
  
 <span data-ttu-id="d0011-p105">サービスと環境の間のメールフローを確認するテストを実行するには、リモート接続アナライザーを使用します。詳細については、「 [test mail flow with the remote Connectivity analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)」の「リモート接続アナライザーを使用して電子メール配信をテストする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p105">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span>
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="d0011-127">手順 4: 受信ポート 25 SMTP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="d0011-127">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="d0011-p106">コネクタを構成した後、DNS レコードの更新が伝達されるように、72時間待機します。次に、ファイアウォールまたはメールサーバー上の受信ポート-25 SMTP トラフィックを制限して、EOP データセンターからのメールのみを受け入れるようにします。具体的には、21vianet が運用している[Office 365 の url および ip アドレス範囲](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)に記載されている ip アドレスからのものです。これにより、受信可能な受信メッセージの範囲を制限することで、オンプレミス環境を保護します。また、メールリレーの接続を許可する IP アドレスを制御する設定がメールサーバーにある場合は、それらの設定も更新します。</span><span class="sxs-lookup"><span data-stu-id="d0011-p106">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365 operated by 21Vianet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="d0011-p107">SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p107">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="d0011-134">手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する</span><span class="sxs-lookup"><span data-stu-id="d0011-134">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="d0011-p108">スパム (迷惑) メールがそれぞれのユーザーの迷惑メールフォルダーに正しくルーティングされるようにするには、いくつかの構成手順を実行する必要があります。この手順は、[スパムが各ユーザーの迷惑メールフォルダーにルーティングされるよう](https://go.microsoft.com/fwlink/?LinkId=506804)にするためのものです。メッセージを各ユーザーの [迷惑メール] フォルダーに移動しない場合は、Exchange 管理センターでコンテンツフィルターポリシーを編集して、別のアクションを選択することができます。詳細については、「 [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p108">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](https://go.microsoft.com/fwlink/?LinkId=506804). If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805).</span></span> 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="d0011-139">手順 6: Office 365 管理センターを使用して、MX レコードが EOP をポイントするようにする</span><span class="sxs-lookup"><span data-stu-id="d0011-139">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="d0011-p109">Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP を通過するようにします。詳細については、「dns レコードを[管理するときに、Office 365 の dns レコードを作成](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p109">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).</span></span>
  
<span data-ttu-id="d0011-142">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="d0011-142">How do you know this task worked?</span></span>
  
 <span data-ttu-id="d0011-p110">MX レコードを検証するテストを実行するには、リモート接続アナライザーを使用します。詳細については、「 [test mail flow with the remote Connectivity analyzer](https://go.microsoft.com/fwlink/?LinkId=506784)」の「リモート接続アナライザーを使用して MX レコードおよび送信コネクタをテストする」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p110">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span> 
  
<span data-ttu-id="d0011-p111">ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="d0011-p111">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="d0011-147">リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。</span><span class="sxs-lookup"><span data-stu-id="d0011-147">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>
    
- <span data-ttu-id="d0011-p112">Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。</span><span class="sxs-lookup"><span data-stu-id="d0011-p112">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="d0011-150">送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d0011-150">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="d0011-151">あまり一般的ではない: オンプレミスのメールボックスとクラウド内のハイブリッドセットアップ</span><span class="sxs-lookup"><span data-stu-id="d0011-151">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="d0011-p113">exchange Online で exchange メールボックスがオンプレミスにあり、クラウド内に1つ以上のメールボックスがある場合は、*ハイブリッド*セットアップがあります。ハイブリッドセットアップでは、オンプレミス環境とクラウド環境で、空き時間情報予定表共有やメールルーティングなどの機能が一緒に機能します。メールボックスを Exchange Online に移行する際に、ハイブリッドセットアップが行われている場合があります。ハイブリッド環境は、EOP スタンドアロンの保護とは異なる方法で設定されます。</span><span class="sxs-lookup"><span data-stu-id="d0011-p113">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a  *hybrid*  setup. In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments. You might have a hybrid setup in place while you transition mailboxes to Exchange Online. A hybrid environment is set up differently than EOP standalone protection.</span></span> 
  
<span data-ttu-id="d0011-p114">多くの従業員に対してクラウドベースの電子メールを活用するために、ハイブリッドシナリオを選択することができます。この操作は、オンプレミスのメールボックスの一部をホストするときに実行することもできます。たとえば、法務部門の場合です。</span><span class="sxs-lookup"><span data-stu-id="d0011-p114">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees. You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span> 
  
<span data-ttu-id="d0011-p115">ハイブリッドセットアップは複雑になることがありますが、多くの利点があります。exchange を使用したハイブリッドシナリオのセットアップの詳細については、「 [21vianet が運用している Office 365 を使用して exchange ハイブリッド展開機能を構成](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d0011-p115">A hybrid setup can be complex, but it has many benefits. To learn more about setting up hybrid scenarios with Exchange, see [Configuring Exchange hybrid deployment features with Office 365 operated by 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).</span></span>
  

