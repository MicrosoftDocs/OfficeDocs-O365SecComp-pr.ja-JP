---
title: Exchange のオンライン保護とオンプレミスのメールボックスを保護します。
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: メールボックスの設置型の一部またはすべてをホストする場合でも、Exchange オンライン保護 (EOP) のメールボックスを保護できます。コネクタを構成するのには自分のアカウントは、Office 365 グローバル管理者、または会社の Exchange 管理者 (組織の管理役割グループ) をする必要があります。Office 365 のアクセス許可が Exchange のアクセス許可に関連する方法については、21Vianet によって運営されて Office 365 の管理者ロールの割り当てを参照してください。すべての Exchange メールボックスは、オンプレミス、EOP サービスを設定する手順に従います。 場合、
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532800"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a><span data-ttu-id="d3c93-106">Exchange のオンライン保護とオンプレミスのメールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-106">Protect on-premises mailboxes with Exchange Online Protection</span></span>

> [!NOTE]
> <span data-ttu-id="d3c93-107">この資料は、中国での 21Vianet によって運営されて Office 365 にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="d3c93-107">This article applies only to Office 365 operated by 21Vianet in China.</span></span> 
  
<span data-ttu-id="d3c93-p102">メールボックスの設置型の一部またはすべてをホストする場合でも、Exchange オンライン保護 (EOP) のメールボックスを保護できます。コネクタを構成するのには自分のアカウントは、Office 365 グローバル管理者、または会社の Exchange 管理者 (組織の管理役割グループ) をする必要があります。Office 365 のアクセス許可が Exchange のアクセス許可に関連する方法については、 [21Vianet によって運営されて Office 365 の管理者ロールの割り当て](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)を参照してください。すべての Exchange メールボックスは、オンプレミス、EOP サービスを設定する手順に従います。 場合、</span><span class="sxs-lookup"><span data-stu-id="d3c93-p102">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP). To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span> 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="d3c93-112">手順 1: Office 365 管理センターを使用してドメインを追加して管理する</span><span class="sxs-lookup"><span data-stu-id="d3c93-112">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="d3c93-113">Office 365 管理センターで、 [セットアップ] に移動して、サービスにドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-113">In the Office 365 admin center, navigate to Setup to add your domain to the service.</span></span>
    
2.  <span data-ttu-id="d3c93-114">ポータルでドメインの所有権を確認するために DNS ホスティング プロバイダーに適用可能な DNS レコードを追加する手順に従います。</span><span class="sxs-lookup"><span data-stu-id="d3c93-114">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span> 
    
> [!TIP]
> <span data-ttu-id="d3c93-115">[自分のドメインを追加しユーザーが Office 365 の 21Vianet によって運営されて](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)、 [Office 365 の DNS レコードを管理するときに作成する DNS レコード](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)は、サービスにドメインを追加すると DNS の構成を行うを参照するための有用なリソースです。</span><span class="sxs-lookup"><span data-stu-id="d3c93-115">[Add your domain and users to Office 365 operated by 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) and [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="d3c93-116">手順 2: 受信者を追加し、ドメインの種類を構成します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-116">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="d3c93-p103">EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](https://go.microsoft.com/fwlink/?LinkId=506782)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p103">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).</span></span>
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="d3c93-121">手順 3:EAC を使用してメール フローをセットアップする</span><span class="sxs-lookup"><span data-stu-id="d3c93-121">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="d3c93-p104">EOP とオンプレミス メール サーバー間のメール フローを有効にする Exchange 管理センター (EAC) では、コネクタを作成します。詳細については、[作成に必要なコネクタ EOP で基本的なメール フローの設定を](https://go.microsoft.com/fwlink/?LinkId=506780)参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p104">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Create required connectors to set up basic email flow through EOP](https://go.microsoft.com/fwlink/?LinkId=506780).</span></span>
  
 <span data-ttu-id="d3c93-124">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="d3c93-124">How do you know this task worked?</span></span> 
  
 <span data-ttu-id="d3c93-p105">サービスとお客様の環境との間のメール フローを確認するテストを実行するのにには、リモート接続アナライザーを使用します。詳細については、[電子メールの配信をテストするのには、リモート接続アナライザーを使用する] セクションで[、リモート接続アナライザーを使用してメール フローをテスト](https://go.microsoft.com/fwlink/?LinkId=506784)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p105">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span>
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="d3c93-127">手順 4: 受信ポート 25 SMTP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="d3c93-127">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="d3c93-p106">コネクタを構成した後、DNS レコードの更新の伝達を許可するのには 72 時間を待機します。その後、EOP データ センターの[Url と IP アドレスを Office 365 を運用している 21Vianet の範囲](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)に記載されている IP アドレスから特にからのみメールを受信するようにファイアウォールまたはメール サーバーのポート 25 で SMTP トラフィックを受信を制限します。これは、受信メッセージを受信できることの範囲を制限することで、オンプレミス環境を保護します。さらに、メールの第三者中継用の接続を許可する IP アドレスを制御する、メール サーバー上の設定をした場合にもこれらの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p106">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365 operated by 21Vianet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="d3c93-p107">SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p107">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="d3c93-134">手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する</span><span class="sxs-lookup"><span data-stu-id="d3c93-134">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="d3c93-p108">スパム (迷惑) メールを各ユーザーの迷惑メール フォルダーに正しくルーティングされることを確認するには、いくつかの構成手順を行う必要があります。[スパムを各ユーザーの迷惑メール フォルダーにルーティングされるようにするの](https://go.microsoft.com/fwlink/?LinkId=506804)には、手順が用意されています。各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションを選択する可能性があります。詳細については、[コンテンツ フィルター ポリシーの構成](https://go.microsoft.com/fwlink/?LinkId=506805)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p108">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](https://go.microsoft.com/fwlink/?LinkId=506804). If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805).</span></span> 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="d3c93-139">手順 6: Office 365 管理センターを使用して、MX レコードが EOP をポイントするようにする</span><span class="sxs-lookup"><span data-stu-id="d3c93-139">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="d3c93-p109">構成手順を Office 365 ドメイン、ドメインの MX レコードを更新する EOP で受信メールが流れるようにします。詳細については、 [Office 365 の DNS レコードを管理するときに作成する DNS レコード](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)をもう一度参照できます。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p109">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).</span></span>
  
<span data-ttu-id="d3c93-142">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="d3c93-142">How do you know this task worked?</span></span>
  
 <span data-ttu-id="d3c93-p110">MX レコードを確認するテストを実行するのにには、リモート接続アナライザーを使用します。詳細についてを参照してください"、MX レコードと送信コネクタをテストするのには、リモート接続アナライザーを使用する] [、リモート接続アナライザーを使用してメール フローをテスト](https://go.microsoft.com/fwlink/?LinkId=506784)します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p110">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span> 
  
<span data-ttu-id="d3c93-p111">ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p111">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="d3c93-147">リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-147">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>
    
- <span data-ttu-id="d3c93-p112">Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p112">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="d3c93-150">送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="d3c93-150">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="d3c93-151">あまり一般的: メールボックスをオンプレミスとクラウドでは、ハイブリッド設定</span><span class="sxs-lookup"><span data-stu-id="d3c93-151">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="d3c93-p113">Exchange メールボックスの設置型がある場合と 1 つまたは複数のメールボックス Exchange Online でクラウドの*ハイブリッド*に設定してあります。ハイブリッド設定では、機能など、空き時間予定表の共有と設置型で、共同作業およびクラウド環境のメール ルーティングします。Exchange Online にメールボックスを移行するときに、場所にハイブリッドの設定があります。ハイブリッド環境は EOP スタンドアロンの保護とは異なる設定ができます。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p113">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a  *hybrid*  setup. In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments. You might have a hybrid setup in place while you transition mailboxes to Exchange Online. A hybrid environment is set up differently than EOP standalone protection.</span></span> 
  
<span data-ttu-id="d3c93-p114">ハイブリッド シナリオでは、従業員のほとんどのクラウド ベースの電子メールの利用を選択する場合があります。こうことにもホストしているいくつかのメールボックスの設置型です。たとえば、法務部門です。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p114">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees. You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span> 
  
<span data-ttu-id="d3c93-p115">ハイブリッドの設定が複雑になることができますが、多くの利点があります。Exchange を使用するハイブリッド シナリオの設定に関する詳細については、 [21Vianet によって運営されて Office 365 のハイブリッド展開機能を Exchange の構成](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d3c93-p115">A hybrid setup can be complex, but it has many benefits. To learn more about setting up hybrid scenarios with Exchange, see [Configuring Exchange hybrid deployment features with Office 365 operated by 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).</span></span>
  

