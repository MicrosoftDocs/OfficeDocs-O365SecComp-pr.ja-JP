---
title: Exchange Online Protection の概要
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/31/2019
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。
ms.openlocfilehash: 4035a676bf815642735699a106e6430cf8245a05
ms.sourcegitcommit: f473bf7f215ba4eb2f49e0dd23a9d2e39fa512c9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2019
ms.locfileid: "36566201"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="4e166-103">Exchange Online Protection の概要</span><span class="sxs-lookup"><span data-stu-id="4e166-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="4e166-p101">マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。EOP はメッセージング環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減します。</span><span class="sxs-lookup"><span data-stu-id="4e166-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>
  
<span data-ttu-id="4e166-106">メッセージング保護に EOP を使用できる基本的な方法として、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="4e166-106">The following are the primary ways you can use EOP for messaging protection:</span></span>
  
- <span data-ttu-id="4e166-107">**スタンドアロンのシナリオで**EOP は、社内の Microsoft Exchange Server 2013 環境、レガシ Exchange Server バージョン、またはその他の社内 SMTP 電子メールソリューションに対して、クラウドベースの電子メール保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="4e166-107">**In a standalone scenario** EOP provides cloud-based email protection for your on-premises Microsoft Exchange Server 2013 environment, legacy Exchange Server versions, or for any other on-premises SMTP email solution.</span></span> 
    
- <span data-ttu-id="4e166-108">**Microsoft Exchange Online の一部として** 既定で、EOP は Microsoft Exchange Online クラウドホスト型メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="4e166-108">**As a part of Microsoft Exchange Online** By default, EOP protects Microsoft Exchange Online cloud-hosted mailboxes.</span></span> <span data-ttu-id="4e166-109">Exchange Online の機能の構成については、「[脅威から保護](../protect-against-threats.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e166-109">See [Protect against threats](../protect-against-threats.md) for help configuring these Exchange Online capabilities.</span></span> 
    
- <span data-ttu-id="4e166-110">**ハイブリッド展開で** EOP はメッセージング環境を保護し、社内メールボックスとクラウド メールボックスが混在している場合のメール ルーティングを制御するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="4e166-110">**In a hybrid deployment** EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span> 

<span data-ttu-id="4e166-111">これらの Exchange Online Protection の記事は、ハイブリッド環境およびオンプレミス環境に適用されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-111">These Exchange Online Protection articles apply to hybrid and on-premises environments.</span></span> 
    
## <a name="how-eop-works"></a><span data-ttu-id="4e166-112">EOP の仕組み</span><span class="sxs-lookup"><span data-stu-id="4e166-112">How EOP works</span></span>

<span data-ttu-id="4e166-113">EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="4e166-113">To understand how EOP works, it helps to see how it processes incoming email:</span></span>

![EOP の電子メールプロセス。](../media/GitHubBugs/emailprocessingineop.png)
  
<span data-ttu-id="4e166-115">受信メッセージは、最初は、送信者の評価をチェックし、マルウェアのメッセージを検査することによって、接続フィルターによって渡されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-115">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware.</span></span> <span data-ttu-id="4e166-116">スパムの大部分は、この時点で停止し、EOP によって削除されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-116">The majority of spam is stopped at this point and deleted by EOP.</span></span> <span data-ttu-id="4e166-117">メッセージはポリシーのフィルター処理によって続行されます。これにより、テンプレートから作成または適用するカスタムメールフロールール (トランスポートルールとも呼ばれる) に対してメッセージが評価されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-117">Messages continue through policy filtering, where messages are evaluated against custom mail flow rules (also known as transport rules) that you create or enforce from a template.</span></span> <span data-ttu-id="4e166-118">たとえば、特定の送信者からのメールが到着すると、管理者に通知を送信するルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4e166-118">For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender.</span></span> <span data-ttu-id="4e166-119">(この機能を使用している場合は、この時点でデータ損失防止チェックも行われます。機能の可用性の詳細については、「 [Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください)。次に、メッセージはコンテンツフィルターを通過し、スパムに共通の用語やプロパティがないかどうかが確認されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-119">(Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam.</span></span> <span data-ttu-id="4e166-120">コンテンツフィルターによってスパムと判断されたメッセージは、設定に基づいて、ユーザーの迷惑メールフォルダーまたは検疫に送信できます。</span><span class="sxs-lookup"><span data-stu-id="4e166-120">A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options, based on your settings.</span></span> <span data-ttu-id="4e166-121">このような保護層をすべて正常に通過すると、メッセージは受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-121">After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>
  
### <a name="eop-datacenters"></a><span data-ttu-id="4e166-122">EOP データセンター</span><span class="sxs-lookup"><span data-stu-id="4e166-122">EOP datacenters</span></span>

<span data-ttu-id="4e166-p104">EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。各データセンターのサーバーがユーザーの代わりにメッセージを受け付け、組織とインターネットの間を分離するレイヤーが提供されるため、組織のサーバーの負荷が軽減されます。この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="4e166-p104">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span> 
  
<span data-ttu-id="4e166-p105">EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="4e166-p105">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>
  
    
- <span data-ttu-id="4e166-130">ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="4e166-130">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="4e166-131">アジア太平洋 (APAC) では、すべての Exchange Online メールボックスが APAC データセンターに配置されており、現在、メッセージは EOP フィルター処理のために APAC データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="4e166-131">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>

- <span data-ttu-id="4e166-132">南北アメリカでは、すべての Exchange Online メールボックスは米国のデータセンターに配置されており、ブラジルとチリのデータセンターが使用されている南米と、カナダのデータセンターが使用されているカナダには例外があります。</span><span class="sxs-lookup"><span data-stu-id="4e166-132">In the Americas, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used.</span></span> <span data-ttu-id="4e166-133">南米およびカナダの顧客宛てのメッセージを含むすべての電子メールメッセージは、EOP フィルター処理のためにローカルデータセンターを経由してルーティングされます。quaratined 電子メールは、テナントが配置されているデータセンターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="4e166-133">All email messages, including messages for customers in South America and Canada, are routed through local datacenters for EOP filtering; quaratined email is stored in the datacenter where the tenant is located.</span></span>
    
- <span data-ttu-id="4e166-134">Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="4e166-134">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>
    
## <a name="eop-plans-and-features"></a><span data-ttu-id="4e166-135">EOP のプランと機能</span><span class="sxs-lookup"><span data-stu-id="4e166-135">EOP plans and features</span></span>

<span data-ttu-id="4e166-136">EOP のサブスクリプション プランを次に示します。</span><span class="sxs-lookup"><span data-stu-id="4e166-136">The following are the available EOP subscription plans:</span></span>
  
- <span data-ttu-id="4e166-137">**EOP スタンドアロン** EOP が社内メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="4e166-137">**EOP standalone** Where EOP protects your on-premises mailboxes.</span></span> 
    
- <span data-ttu-id="4e166-138">**Exchange Online の EOP 機能** EOP が Exchange Online クラウドホスト型メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="4e166-138">**EOP features in Exchange Online** Where EOP protects your Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="4e166-139">**Exchange Enterprise CAL とサービス** EOP スタンドアロンと同様に、EOP が社内メールボックスを保護します。また、データ損失防止 (DLP) と Web サービスを使用したレポート機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="4e166-139">**Exchange Enterprise CAL with Services** Where EOP protects your on-premises mailboxes, like EOP standalone, and includes data loss prevention (DLP) and reporting using web services.</span></span> 
    
<span data-ttu-id="4e166-140">すべての EOP サブスクリプション プランについての要件、重要な制限および機能の可用性の詳細については、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e166-140">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span></span>
  
## <a name="setting-up-eop"></a><span data-ttu-id="4e166-141">EOP の設定</span><span class="sxs-lookup"><span data-stu-id="4e166-141">Setting up EOP</span></span>

<span data-ttu-id="4e166-p107">EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="4e166-p107">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>
  
<span data-ttu-id="4e166-144">すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="4e166-144">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="4e166-145">関連情報</span><span class="sxs-lookup"><span data-stu-id="4e166-145">For more information</span></span>

[<span data-ttu-id="4e166-146">EOP の機能</span><span class="sxs-lookup"><span data-stu-id="4e166-146">EOP features</span></span>](eop-features.md)
  
[<span data-ttu-id="4e166-147">EOP の一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="4e166-147">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="4e166-148">EOP のキューイング、保留、返送されるメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="4e166-148">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)
  
[<span data-ttu-id="4e166-149">代理管理に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="4e166-149">Delegated administration FAQ</span></span>](delegated-administration-faq.md)
  
[<span data-ttu-id="4e166-150">ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する</span><span class="sxs-lookup"><span data-stu-id="4e166-150">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

