---
title: EOP のメール フロー
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 3/13/2015
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。
ms.openlocfilehash: d35e6f2fdbe7bb991ebf3d766fadae34638831ef
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027344"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="bbe1e-104">EOP のメール フロー</span><span class="sxs-lookup"><span data-stu-id="bbe1e-104">Mail flow in EOP</span></span>

<span data-ttu-id="bbe1e-p102">Exchange Online Protection (EOP) のお客様の場合、組織に送信されたすべてのメッセージは EOP を通って従業員に配信されます。クラウド内のすべてのメールボックスを Exchange Online を使用してホストしているか、既存のインフラストラクチャの利用を継続するためなどの理由で、メールボックスを社内でホストしている (いわゆるスタンドアロン シナリオ) かに関係なく、処理のために EOP を通過してから従業員の受信トレイに配信されるメッセージのルーティング方法に関するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p102">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>
  
<span data-ttu-id="bbe1e-p103">メッセージングをビジネス要件に適合させるためにカスタム メール ルーティングを構成したい場合があります。たとえば、すべての送信メールをポリシー フィルタリング アプライアンスを通過させるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p103">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span> 
  
## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="bbe1e-109">メッセージとメッセージ アクセス オプションの操作</span><span class="sxs-lookup"><span data-stu-id="bbe1e-109">Working with messages and message access options</span></span>

<span data-ttu-id="bbe1e-p104">EOP はメッセージのルーティング方法の柔軟性を高めます。以下のトピックで、メール フロー プロセスの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p104">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>
  
<span data-ttu-id="bbe1e-112">[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) ディレクトリ ベースのエッジ ブロック機能を使って無効な受信者宛てのメッセージをサービス ネットワーク境界で拒否する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-112">[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span> 
  
<span data-ttu-id="bbe1e-113">「[View or Edit Managed Domains in EOP](http://technet.microsoft.com/library/69523bec-07ee-46f9-ae08-40437e39b87c.aspx)」では、EOP サービスに関連付けられたドメインの管理方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-113">[View or Edit Managed Domains in EOP](http://technet.microsoft.com/library/69523bec-07ee-46f9-ae08-40437e39b87c.aspx) describes how to manage domains that are associated with your EOP service.</span></span> 
  
<span data-ttu-id="bbe1e-p105">組織にサブドメインを追加する場合にも、それらの管理に EOP サービスを活用できます。サブドメインの詳細については、「[Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p105">If you add subdomains to your organization, your EOP service can help you manage these too. Learn more about subdomains at [Enable Mail Flow for Subdomains in Exchange Online](http://technet.microsoft.com/library/4033a30a-f506-481c-8ef0-fd9a0508ae38.aspx).</span></span>
  
<span data-ttu-id="bbe1e-p106">「[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)」では、コネクタについて概説し、それを使ってメール ルーティングをカスタマイズする方法を示します。シナリオには、パートナー組織との安全な通信の保証とスマート ホストのセットアップが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p106">[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span> 
  
<span data-ttu-id="bbe1e-p107">各ユーザーの迷惑メール フォルダーに迷惑メールが正しくルーティングされることを確認するには、いくつかの構成手順を行う必要があります。詳細については、[各ユーザーの迷惑メール フォルダーに迷惑メールがルーティングされるようにします](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。メッセージを各ユーザーの迷惑メール フォルダーに移動したくない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集することによって別のアクションができます。詳細については、[スパム フィルター ポリシーの構成](../configure-your-spam-filter-policies.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p107">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps. These are detailed in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
## <a name="verify-mail-flow"></a><span data-ttu-id="bbe1e-122">メール フローを確認する</span><span class="sxs-lookup"><span data-stu-id="bbe1e-122">Verify mail flow</span></span>

<span data-ttu-id="bbe1e-p108">コネクタ構成を含む EOP セットアップが正しく機能していることを確認するには、「[EOP サービスを設定する](set-up-your-eop-service.md)」の「このタスクの検証方法」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-p108">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span> 
  
<span data-ttu-id="bbe1e-125">「[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)」では、メール フローが正しくセットアップされているかどうかのテスト手順を示します。</span><span class="sxs-lookup"><span data-stu-id="bbe1e-125">[Test Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx) provides instructions for testing that your mail flow is set up correctly.</span></span> 
  

