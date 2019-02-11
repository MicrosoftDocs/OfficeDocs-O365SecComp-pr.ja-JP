---
title: Exchange Online Protection の概要
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 01/31/2019
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 1270a65f-ddc3-4430-b500-4d3a481efb1e
description: マイクロソフト Exchange Online Protection (EOP) は、クラウドベースの電子メール フィルタリング サービスであり、スパムやマルウェアから組織を保護するのに役立ち、メッセージング ポリシー違反から組織を保護する機能が含まれています。
ms.openlocfilehash: 16f2f423b6e517cf204e4b4f6a2949baebfd6223
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686366"
---
# <a name="exchange-online-protection-overview"></a><span data-ttu-id="f3f3d-103">Exchange Online Protection の概要</span><span class="sxs-lookup"><span data-stu-id="f3f3d-103">Exchange Online Protection overview</span></span>

<span data-ttu-id="f3f3d-p101">Microsoft Exchange Online Protection (EOP) は、スパムやマルウェアから組織を保護するクラウドベースの電子メール フィルター処理サービスであり、メッセージング ポリシー違反から組織を保護する機能を備えています。EOP はメッセージング環境の管理を簡素化し、社内のハードウェアおよびソフトウェアの維持に伴う負荷の多くを軽減します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-p101">Microsoft Exchange Online Protection (EOP) is a cloud-based email filtering service that helps protect your organization against spam and malware, and includes features to safeguard your organization from messaging-policy violations. EOP can simplify the management of your messaging environment and alleviate many of the burdens that come with maintaining on-premises hardware and software.</span></span>
  
<span data-ttu-id="f3f3d-106">メッセージング保護に EOP を使用できる基本的な方法として、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-106">The following are the primary ways you can use EOP for messaging protection:</span></span>
  
- <span data-ttu-id="f3f3d-107">**スタンドアロンのシナリオ**EOP は、クラウド ベースの電子メールの保護、オンプレミスの Microsoft Exchange Server 2013 環境、従来の Exchange Server のバージョンでは、またはその他の設置型の SMTP メール ・ ソリューションを提供します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-107">**In a standalone scenario** EOP provides cloud-based email protection for your on-premises Microsoft Exchange Server 2013 environment, legacy Exchange Server versions, or for any other on-premises SMTP email solution.</span></span> 
    
- <span data-ttu-id="f3f3d-108">**Microsoft Exchange Online の一部として** 既定で、EOP は Microsoft Exchange Online クラウドホスト型メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-108">**As a part of Microsoft Exchange Online** By default, EOP protects Microsoft Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="f3f3d-109">**ハイブリッド展開で** EOP はメッセージング環境を保護し、社内メールボックスとクラウド メールボックスが混在している場合のメール ルーティングを制御するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-109">**In a hybrid deployment** EOP can be configured to protect your messaging environment and control mail routing when you have a mix of on-premises and cloud mailboxes.</span></span> 
    
## <a name="how-eop-works"></a><span data-ttu-id="f3f3d-110">EOP の仕組み</span><span class="sxs-lookup"><span data-stu-id="f3f3d-110">How EOP works</span></span>

<span data-ttu-id="f3f3d-111">EOP の仕組みを理解すると、受信メールの処理方法がわかりやすくなります。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-111">To understand how EOP works, it helps to see how it processes incoming email:</span></span>
  
![EOP のメールの処理](../media/EOP-email-processing.png)
  
<span data-ttu-id="f3f3d-p102">受信メッセージは最初に、送信者の評価をチェックし、マルウェアがメッセージを検査する、接続フィルターを通過します。スパム メールの大多数は、この時点で停止、EOP によって削除されました。メッセージは、カスタム トランスポート ルールを作成するか、テンプレートから適用することに対してメッセージが評価される場所、ポリシーのフィルター処理を続行します。たとえば、特定の送信者からメールを受信したときに、マネージャーに通知を送信するルールを持つことができます。(データ損失の防止策のチェックも場合に発生するこの時点で、機能を使用できる機能については、 [Exchange オンライン保護サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)を参照してください。)次に、メッセージを通過コンテンツ フィルタ リングでは、用語集や迷惑メールに共通のプロパティのコンテンツをチェックする場所です。メッセージであると判断の設定に基づいて、その他のオプションの中から、検疫またはユーザーの迷惑メール フォルダーに、コンテンツ フィルターによって迷惑メールを送信することができます。メッセージのすべてのこれらの保護層に成功をした後、受信者に配信されます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-p102">An incoming message initially passes through connection filtering, which checks the sender's reputation and inspects the message for malware. The majority of spam is stopped at this point and deleted by EOP. Messages continue through policy filtering, where messages are evaluated against custom transport rules that you create or enforce from a template. For example, you can have a rule that sends a notification to a manager when mail arrives from a specific sender. (Data loss prevention checks also occur at this point, if you have that feature; for information about feature availability, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).) Next, messages pass through content filtering, where content is checked for terminology or properties common to spam. A message determined to be spam by the content filter can be sent to a user's Junk Email folder or to the quarantine, among other options, based on your settings. After a message passes all of these protection layers successfully, it's delivered to the recipient.</span></span>
  
### <a name="eop-datacenters"></a><span data-ttu-id="f3f3d-120">EOP データセンター</span><span class="sxs-lookup"><span data-stu-id="f3f3d-120">EOP datacenters</span></span>

<span data-ttu-id="f3f3d-p103">EOP は、最良の可用性を提供するために設計された複数のデータセンターから成る世界規模のネットワーク上で稼働します。たとえば、あるデータセンターが使用できなくなった場合、電子メール メッセージはサービスの中断なく、自動的に別のデータセンターにルーティングされます。各データセンターのサーバーがユーザーの代わりにメッセージを受け付け、組織とインターネットの間を分離するレイヤーが提供されるため、組織のサーバーの負荷が軽減されます。この高可用性のネットワークによって、Microsoft は適切なタイミングで組織に電子メールが配信されることを保証できます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-p103">EOP runs on a worldwide network of datacenters that are designed to provide the best availability. For example, if a datacenter becomes unavailable, email messages are automatically routed to another datacenter without any interruption in service. Servers in each datacenter accept messages on your behalf, providing a layer of separation between your organization and the Internet, thereby reducing load on your servers. Through this highly available network, Microsoft can ensure that email reaches your organization in a timely manner.</span></span> 
  
<span data-ttu-id="f3f3d-p104">EOP はデータセンター間の負荷分散を実行しますが、1 つの地域内でのみ行います。1 つの地域でサービスが提供されている場合は、すべてのメッセージがその地域のメール ルーティングを使用して処理されます。EOP データセンターの地域メール ルーティングの動作を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-p104">EOP performs load balancing between datacenters but only within a region. If you're provisioned in one region all your messages will be processed using the mail routing for that region. The following list shows the how regional mail routing works for the EOP datacenters:</span></span>
  
    
- <span data-ttu-id="f3f3d-128">ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-128">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="f3f3d-129">アジア太平洋地域 (APAC) では、APAC のデータ センターにあるすべての Exchange Online のメールボックスが、EOP のフィルタ リングの APAC のデータ センターを通じてメッセージがルーティングされる現在。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-129">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, but messages are currently routed through APAC datacenters for EOP filtering.</span></span>
=======
- <span data-ttu-id="f3f3d-p105">南北アメリカでは、Exchange Online のすべてのメールボックスは南米のブラジルとチリでのデータ センターが使用されている場合を除き、カナダではカナダのデータ センターが使用されている米国のデータ センターに配置されます。EOP フィルタ リング用のローカル データ センター経由で、南アメリカとカナダでは、お客様のメッセージを含むすべての電子メール メッセージquaratined メールは、テナントが格納されているデータ センターに格納されます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-p105">In the Americas, all Exchange Online mailboxes are located in U.S. datacenters, with the exception of South America where datacenters in Brazil and Chile are used and in Canada where datacenters in Canada are used. All email messages, including messages for customers in South America and Canada, are routed through local datacenters for EOP filtering; quaratined email is stored in the datacenter where the tenant is located.</span></span>
    
- <span data-ttu-id="f3f3d-132">ヨーロッパ、中東、およびアフリカ (EMEA) では、すべての Exchange Online メールボックスが EMEA データセンターに配置され、すべてのメッセージが EOP フィルター処理のために EMEA データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-132">In Europe, the Middle East, and Africa (EMEA), all Exchange Online mailboxes are located in EMEA datacenters, and all messages are routed through EMEA datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="f3f3d-133">アジア太平洋地域 (APAC)、APAC のデータ センターにあるすべての Exchange Online のメールボックスおよびメッセージ現在経由 EOP のフィルタ リングの APAC のデータ センターです。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-133">In Asia-Pacific (APAC), all Exchange Online mailboxes are located in APAC datacenters, and messages are currently routed through APAC datacenters for EOP filtering.</span></span>
    
- <span data-ttu-id="f3f3d-134">Government Community Cloud (GCC) では、すべての Exchange Online メールボックスが米国データセンターに配置され、すべてのメッセージが EOP フィルター処理のために米国データセンター経由でルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-134">For the Government Community Cloud (GCC), all Exchange Online mailboxes are located in U.S. datacenters and all messages are routed through U.S. datacenters for EOP filtering.</span></span>
    
## <a name="eop-plans-and-features"></a><span data-ttu-id="f3f3d-135">EOP のプランと機能</span><span class="sxs-lookup"><span data-stu-id="f3f3d-135">EOP plans and features</span></span>

<span data-ttu-id="f3f3d-136">EOP のサブスクリプション プランを次に示します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-136">The following are the available EOP subscription plans:</span></span>
  
- <span data-ttu-id="f3f3d-137">**EOP スタンドアロン** EOP が社内メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-137">**EOP standalone** Where EOP protects your on-premises mailboxes.</span></span> 
    
- <span data-ttu-id="f3f3d-138">**Exchange Online の EOP 機能** EOP が Exchange Online クラウドホスト型メールボックスを保護します。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-138">**EOP features in Exchange Online** Where EOP protects your Exchange Online cloud-hosted mailboxes.</span></span> 
    
- <span data-ttu-id="f3f3d-139">**Exchange Enterprise CAL とサービス** EOP スタンドアロンと同様に、EOP が社内メールボックスを保護します。また、データ損失防止 (DLP) と Web サービスを使用したレポート機能を備えています。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-139">**Exchange Enterprise CAL with Services** Where EOP protects your on-premises mailboxes, like EOP standalone, and includes data loss prevention (DLP) and reporting using web services.</span></span> 
    
<span data-ttu-id="f3f3d-140">すべての EOP サブスクリプション プランについての要件、重要な制限および機能の可用性の詳細については、「[Exchange Online Protection サービスの説明](https://go.microsoft.com/fwlink/p/?LinkId=320619)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-140">For information about requirements, important limits, and feature availability across all EOP subscription plans, see the [Exchange Online Protection Service Description](https://go.microsoft.com/fwlink/p/?LinkId=320619).</span></span>
  
## <a name="setting-up-eop"></a><span data-ttu-id="f3f3d-141">EOP の設定</span><span class="sxs-lookup"><span data-stu-id="f3f3d-141">Setting up EOP</span></span>

<span data-ttu-id="f3f3d-p106">EOP のセットアップは、特にコンプライアンス ルールが少ない小規模な組織の場合に、シンプルにすることができます。ただし、複数ドメイン、カスタム コンプライアンス ルール、またはハイブリッド メール フローが存在する大規模な組織の場合は、セットアップにより多くの計画や時間が必要となることがあります。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-p106">Setting up EOP can be simple, especially in the case of a small organization with a handful of compliance rules. However, if you have a large organization with multiple domains, custom compliance rules, or hybrid mail flow, set up can take more planning and time.</span></span>
  
<span data-ttu-id="f3f3d-144">すでに EOP を購入している場合は、「[EOP サービスを設定する](set-up-your-eop-service.md)」を参照して、メッセージング環境を保護するように EOP を構成するために必要なすべての手順が完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f3f3d-144">If you've already purchased EOP, see [Set up your EOP service](set-up-your-eop-service.md) to ensure that you complete all the steps necessary to configure EOP to protect your messaging environment.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="f3f3d-145">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f3f3d-145">For more information</span></span>

[<span data-ttu-id="f3f3d-146">EOP の機能</span><span class="sxs-lookup"><span data-stu-id="f3f3d-146">EOP features</span></span>](eop-features.md)
  
[<span data-ttu-id="f3f3d-147">EOP の使用を開始するためのビデオ</span><span class="sxs-lookup"><span data-stu-id="f3f3d-147">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="f3f3d-148">EOP の一般的な FAQ</span><span class="sxs-lookup"><span data-stu-id="f3f3d-148">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="f3f3d-149">EOP のキューイング、保留、返送されるメッセージに関する FAQ</span><span class="sxs-lookup"><span data-stu-id="f3f3d-149">EOP queued, deferred, and bounced messages FAQ</span></span>](eop-queued-deferred-and-bounced-messages-faq.md)
  
[<span data-ttu-id="f3f3d-150">代理管理の FAQ</span><span class="sxs-lookup"><span data-stu-id="f3f3d-150">Delegated administration FAQ</span></span>](delegated-administration-faq.md)
  
[<span data-ttu-id="f3f3d-151">ドメインと設定を 1 つの EOP 組織から別の EOP 組織に移動する</span><span class="sxs-lookup"><span data-stu-id="f3f3d-151">Move domains and settings from one EOP organization to another EOP organization</span></span>](move-domains-and-settings-from-one-eop-organization-to-another-eop-organization.md)
  

