---
title: EOP サービスを設定する
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: このトピックでは、Microsoft Exchange Online Protection (EOP) のセットアップ方法について説明します。Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。コネクタの構成方法の詳細については、「Configure mail flow using connectors in Office 365」をご覧ください。
ms.openlocfilehash: f1c65164adcaa17c58ae9c4b4b957c477b9e02f3
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027114"
---
# <a name="set-up-your-eop-service"></a><span data-ttu-id="ee966-105">EOP サービスを設定する</span><span class="sxs-lookup"><span data-stu-id="ee966-105">Set up your EOP service</span></span>

<span data-ttu-id="ee966-p102">このトピックでは、Microsoft Exchange Online Protection (EOP) のセットアップ方法について説明します。Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。コネクタの構成方法の詳細については、「[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p102">This topic explains how to set up Microsoft Exchange Online Protection (EOP). If you landed here from the Office 365 domains wizard, go back to the Office 365 domains wizard if you don't want to use Exchange Online Protection. If you're looking for more information on how to configure connectors, see [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ee966-p103">このトピックは、対象とする社内メールボックスがあり、それらをスタンドアロン シナリオとして知られている EOP で保護する場合を前提としています。Exchange Online によりクラウド上のすべてのメールボックスをホストする場合、このトピックに記載されているすべての作業を行う必要はありません。 [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312)に移動してサインアップして、クラウド メールボックスを購入してください。社内メールボックスの一部をホストし、一部をクラウド上に置く場合は、ハイブリッド シナリオと呼びます。この場合、より高度なメール フローの設定が必要です。ハイブリッド メール フローとその設定方法の詳細については、「 [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p103">This topic assumes you have on-premises mailboxes and you want to protect them with EOP, which is known as a standalone scenario. If you want to host all of your mailboxes in the cloud with Exchange Online, you don't have to complete all of the steps in this topic. Go to [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) to sign up and purchase cloud mailboxes. If you want to host some of your mailboxes on premises and some in the cloud, this is known as a hybrid scenario. It requires more advanced mail-flow settings. [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx) explains hybrid mail flow and has links to resources that show how to set it up.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ee966-115">始める前に把握しておくべき情報</span><span class="sxs-lookup"><span data-stu-id="ee966-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ee966-116">このタスクの予想所要時間:1 時間</span><span class="sxs-lookup"><span data-stu-id="ee966-116">Estimated time to complete this task: 1 hour</span></span>
    
- <span data-ttu-id="ee966-p104">コネクタを構成するには、アカウントが Office 365 グローバル管理者または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。Office 365 のアクセス許可と Exchange のアクセス許可の関連についての詳細は、「[Office 365 の権限](https://go.microsoft.com/fwlink/p/?LinkID=335814)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p104">To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Permissions in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=335814).</span></span>
    
- <span data-ttu-id="ee966-119">EOP に登録にしていない場合は、「[Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660)」にアクセスして、サービスを購入するか、試用してみてください。</span><span class="sxs-lookup"><span data-stu-id="ee966-119">If you haven't signed up for EOP, visit [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) and choose to buy or try the service.</span></span> 
    
- <span data-ttu-id="ee966-120">このトピックの手順で使用可能なキーボード ショートカットについては、「 **Keyboard shortcuts in Exchange 2013**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-120">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="ee966-p105">問題がある場合は、Exchange のフォーラムで質問してください。 次のフォーラムにアクセスしてください。[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)、 または [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="ee966-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="ee966-124">実行方法</span><span class="sxs-lookup"><span data-stu-id="ee966-124">How do you do this?</span></span>

### <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="ee966-125">手順 1: Office 365 管理センターを使用してドメインを追加して管理する</span><span class="sxs-lookup"><span data-stu-id="ee966-125">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="ee966-126">Office 365 管理センターで、 **[セットアップ]** に移動して、サービスにドメインを追加します。</span><span class="sxs-lookup"><span data-stu-id="ee966-126">In the Office 365 admin center, navigate to **Setup** to add your domain to the service.</span></span> 
    
    <span data-ttu-id="ee966-p106">Office 365 管理センターの見つけ方がわからない場合、詳細については、「[Office 365 管理センターについて](https://go.microsoft.com/fwlink/p/?LinkId=521888)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p106">Not sure where to find the Office 365 admin center? Learn more at [About the Office 365 admin center](https://go.microsoft.com/fwlink/p/?LinkId=521888).</span></span>
    
2. <span data-ttu-id="ee966-129">ドメインの所有権を確認するため、以下の手順に従って、適用可能な DNS レコードを DNS ホスティング プロバイダーに追加します。</span><span class="sxs-lookup"><span data-stu-id="ee966-129">Follow the steps to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>
    
> [!TIP]
> <span data-ttu-id="ee966-130">サービスへのドメインの追加と DNS の構成に役立つ情報については、「[Office 365 にドメインを追加する](https://go.microsoft.com/fwlink/p/?LinkId=282303)」と「[Office 365 の DNS レコードを作成する](https://go.microsoft.com/fwlink/p/?LinkId=304219)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-130">[Add your domain to Office 365](https://go.microsoft.com/fwlink/p/?LinkId=282303) and [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a><span data-ttu-id="ee966-131">手順 2:受信者を追加し、オプションとして DBEB を有効化する</span><span class="sxs-lookup"><span data-stu-id="ee966-131">Step 2: Add recipients and optionally enable DBEB</span></span>

<span data-ttu-id="ee966-p107">EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p107">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="ee966-136">手順 3:EAC を使用してメール フローをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ee966-136">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="ee966-p108">Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。詳細な手順については、「[Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p108">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx).</span></span>
  
#### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="ee966-139">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="ee966-139">How do you know this task worked?</span></span>

<span data-ttu-id="ee966-p109">サービスとユーザーの環境間のメール フローを確認するテストを実行するには、リモート接続アナライザーを使用します。詳しくは、「[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」のトピック「リモート接続アナライザーを使用して電子メール配信をテストする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p109">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).</span></span>
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="ee966-142">手順 4: 受信ポート 25 SMTP アクセスを許可する</span><span class="sxs-lookup"><span data-stu-id="ee966-142">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="ee966-p110">コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。この後、ファイアウォールまたはメール サーバーで、EOP データセンターからの (具体的には [Exchange Online Protection の IP アドレス](exchange-online-protection-ip-addresses.md) に一覧表示されている IP アドレスからの) メールだけを受信するように、受信用ポート 25 の SMTP トラフィックを制限します。これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。</span><span class="sxs-lookup"><span data-stu-id="ee966-p110">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [Exchange Online Protection IP addresses](exchange-online-protection-ip-addresses.md). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="ee966-p111">SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p111">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="ee966-149">手順 5: シェルを使用してスパムがそれぞれのユーザーの迷惑メール フォルダーにルーティングされることを確認する</span><span class="sxs-lookup"><span data-stu-id="ee966-149">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="ee966-p112">スパム (迷惑) メールを各ユーザーの迷惑メール フォルダーに正しくルーティングされることを確認するには、いくつかの構成手順を行う必要があります。[スパムを各ユーザーの迷惑メール フォルダーにルーティングされるようにするの](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)には、手順が用意されています。</span><span class="sxs-lookup"><span data-stu-id="ee966-p112">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
  
<span data-ttu-id="ee966-p113">各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションを選択する可能性があります。詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p113">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
### <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="ee966-154">手順 6: Office 365 管理センターを使用して、MX レコードが EOP をポイントするようにする</span><span class="sxs-lookup"><span data-stu-id="ee966-154">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="ee966-p114">Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。サード パーティのフィルタリング サービスを通して電子メールを EOP に送るのではなく、MX レコードが直接 EOP をポイントするようにします。詳細については、「[Office 365 の DNS レコードを作成する ](https://go.microsoft.com/fwlink/p/?LinkId=304219)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p114">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. Be sure to point your MX record directly to EOP as opposed to having a third-party filtering service relay email to EOP. For more information, you can again reference [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).</span></span>
  
#### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="ee966-158">このタスクの検証方法</span><span class="sxs-lookup"><span data-stu-id="ee966-158">How do you know this task worked?</span></span>

<span data-ttu-id="ee966-p115">MX レコードを検証するテストを実行するには、リモート接続アナライザーを使用します。詳しくは、「[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」のトピック「リモート接続アナライザーを使用して MX レコードおよび送信コネクタをテストする」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee966-p115">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).</span></span> 
  
<span data-ttu-id="ee966-p116">ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。</span><span class="sxs-lookup"><span data-stu-id="ee966-p116">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="ee966-163">リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。</span><span class="sxs-lookup"><span data-stu-id="ee966-163">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span> 
    
- <span data-ttu-id="ee966-p117">Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。</span><span class="sxs-lookup"><span data-stu-id="ee966-p117">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="ee966-166">送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ee966-166">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
> [!TIP]
> <span data-ttu-id="ee966-p118">セットアップ完了後、スパムやマルウェアを削除するために EOP で行う追加作業はありません。EOP はスパムやマルウェアを自動的に削除します。ただしビジネス要件に基づいて、EAC の設定を微調整することも可能です。詳細については、「[Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)」を参照してください。 > サービスの開始後に、「[EOP を構成するためのベスト プラクティス](best-practices-for-configuring-eop.md)」を参考にされることをお勧めします。ここでは、EOP セットアップ後の推奨設定や注意点について紹介しています。</span><span class="sxs-lookup"><span data-stu-id="ee966-p118">When you've completed your setup, you don't have to perform extra steps to make EOP remove spam and malware. EOP removes spam and malware automatically. However, you can fine tune your settings in the EAC, based on your business requirements. For more information, see [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx). > Now that your service is running, we recommend reading [Best practices for configuring EOP](best-practices-for-configuring-eop.md), which describes recommended settings and considerations for after you set up EOP.</span></span> 
  

