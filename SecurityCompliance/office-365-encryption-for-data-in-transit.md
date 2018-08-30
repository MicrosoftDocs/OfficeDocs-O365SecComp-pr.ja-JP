---
title: 転送中のデータの暗号化を office 365
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '概要: マイクロソフトが送信中のデータを暗号化する方法を簡単に説明します。'
ms.openlocfilehash: 8f4781cf1127fb1b6bf742c267c76e3df39b8209
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22531603"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="caab3-103">転送中のデータの暗号化を office 365</span><span class="sxs-lookup"><span data-stu-id="caab3-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="caab3-104">顧客データの保護、他は、マイクロソフトは、転送中に Office 365 の顧客データを保護するのに暗号化テクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="caab3-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="caab3-105">データを転送中にいます。</span><span class="sxs-lookup"><span data-stu-id="caab3-105">Data is in transit:</span></span>
- <span data-ttu-id="caab3-106">クライアント コンピューターを Office 365 サーバーと通信するとき</span><span class="sxs-lookup"><span data-stu-id="caab3-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="caab3-107">Office 365 サーバーと Office 365 の別のサーバーに通信するときそして</span><span class="sxs-lookup"><span data-stu-id="caab3-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="caab3-108">場合、Office 365 のサーバーは、Office 365 以外のサーバー (外部の電子メール サーバーに提供する電子メールを Exchange Online など) と通信します。</span><span class="sxs-lookup"><span data-stu-id="caab3-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="caab3-p101">TLS または IPsec 経由で Office 365 のサーバー間でのデータ センター間の通信が実行され、顧客向けのすべてのサーバーが TLS を使用して、クライアント コンピューターとセキュリティで保護されたセッションをネゴシエート (Exchange Online の使用など、256 ビットの暗号強度で TLS 1.2 を使用 (FIPS2 検証 140-2 レベル)。(TLS 暗号スイートを Office 365 でサポートされているリストの[テクニカル リファレンスの詳細については、Office 365 での暗号化](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)を参照してください)。これは、ビジネス、および Outlook (たとえば、HTTP、POP3 など) は、web 上の Outlook、Skype クライアントによって使用されるプロトコルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="caab3-p101">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated). (See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="caab3-p102">公開証明書は、SSLAdmin、転送された情報の機密性を保護するために内部の Microsoft ツールを使用して Microsoft IT の SSL によって発行されます。Microsoft IT によって発行された証明書をすべて 2048 ビットの最小の長さがあり、 [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)のコンプライアンスには、Microsoft が所有しているパブリックの IP アドレスにのみ証明書が発行されるかどうかを確認するのには SSLAdmin が必要です。例外プロセスを通じて、この条件を満たしていない任意の IP アドレスがルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="caab3-p102">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information. All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft. Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="caab3-p103">TLS が使用されているのバージョン、前方秘密 (FS) が有効になっているかどうか、暗号などのすべての実装の詳細については、一般に使用できます。これらの詳細を表示する方法の 1 つでは、Qualys の SSL の演習 (www.ssllabs.com) などのサードパーティの web サイトを使用します。次には、以下のサービスについての情報を表示する Qualys の自動テストのページへのリンクを示します。</span><span class="sxs-lookup"><span data-stu-id="caab3-p103">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly. One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com). Below are the links to automated test pages from Qualys that display information for the following services:</span></span>
- [<span data-ttu-id="caab3-117">Office 365 ポータル</span><span class="sxs-lookup"><span data-stu-id="caab3-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="caab3-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="caab3-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="caab3-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="caab3-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="caab3-120">Skype ビジネス (SIP)</span><span class="sxs-lookup"><span data-stu-id="caab3-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="caab3-121">Skype ビジネス (Web)</span><span class="sxs-lookup"><span data-stu-id="caab3-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="caab3-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="caab3-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="caab3-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="caab3-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="caab3-124">Exchange のオンライン保護のため、Url がテナント名によって異なりますただし、すべての顧客は、 **microsoft com.mail.protection.outlook.com**を使用して Office 365 をテストできます。</span><span class="sxs-lookup"><span data-stu-id="caab3-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
