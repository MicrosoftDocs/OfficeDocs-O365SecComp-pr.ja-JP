---
title: EOP のメール フロー
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。
ms.openlocfilehash: 2081aff8da44244a1476b51eed49e5f23a5a9b9a
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676770"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="cfc13-104">EOP のメール フロー</span><span class="sxs-lookup"><span data-stu-id="cfc13-104">Mail flow in EOP</span></span>

<span data-ttu-id="cfc13-p102">Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="cfc13-p102">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>
  
<span data-ttu-id="cfc13-p103">メッセージングをビジネス要件に適合させるためにカスタム メール ルーティングを構成したい場合があります。たとえば、すべての送信メールをポリシー フィルタリング アプライアンスを通過させるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cfc13-p103">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span>
  
## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="cfc13-109">メッセージとメッセージ アクセス オプションの操作</span><span class="sxs-lookup"><span data-stu-id="cfc13-109">Working with messages and message access options</span></span>

<span data-ttu-id="cfc13-p104">EOP はメッセージのルーティング方法の柔軟性を高めます。以下のトピックで、メール フロー プロセスの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfc13-p104">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>
  
<span data-ttu-id="cfc13-112">[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)サービスネットワーク境界で無効な受信者宛てのメッセージを拒否できるようにする、ディレクトリベースのエッジブロック機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfc13-112">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span> 
  
<span data-ttu-id="cfc13-113">「[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfc13-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>
  
<span data-ttu-id="cfc13-114">組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。</span><span class="sxs-lookup"><span data-stu-id="cfc13-114">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="cfc13-115">サブドメインの詳細については[、「Exchange Online でサブドメインのメールフローを有効にする」](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfc13-115">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>
  
<span data-ttu-id="cfc13-p106">「[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」では、コネクタについて概説し、それを使ってメール ルーティングをカスタマイズする方法を示します。シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfc13-p106">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>
  
<span data-ttu-id="cfc13-118">迷惑メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cfc13-118">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps.</span></span> <span data-ttu-id="cfc13-119">これらは、[スパムが各ユーザーの迷惑メールフォルダーにルーティングされる](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)ことを確認するために詳細に記載されています。</span><span class="sxs-lookup"><span data-stu-id="cfc13-119">These are detailed in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="cfc13-120">メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションを選択できます。</span><span class="sxs-lookup"><span data-stu-id="cfc13-120">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="cfc13-121">詳細については、「 [スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfc13-121">For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
## <a name="verify-mail-flow"></a><span data-ttu-id="cfc13-122">メール フローを確認する</span><span class="sxs-lookup"><span data-stu-id="cfc13-122">Verify mail flow</span></span>

<span data-ttu-id="cfc13-p108">コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfc13-p108">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>
  
<span data-ttu-id="cfc13-125">[Office 365 コネクタを検証してメールフローをテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)するメールフローが正しく設定されていることをテストする手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="cfc13-125">[Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
