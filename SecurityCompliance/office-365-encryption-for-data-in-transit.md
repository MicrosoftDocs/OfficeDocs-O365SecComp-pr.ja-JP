---
title: 転送中のデータの Office 365 暗号化
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: '概要: 転送中に Microsoft がデータを暗号化する方法を簡単に説明します。'
ms.openlocfilehash: ba1317a0a2a685d0f3ac2216939d04e402503e49
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262799"
---
# <a name="office-365-encryption-for-data-in-transit"></a><span data-ttu-id="b9704-103">転送中のデータの Office 365 暗号化</span><span class="sxs-lookup"><span data-stu-id="b9704-103">Office 365 encryption for data in transit</span></span>

<span data-ttu-id="b9704-104">お客様のデータを保存して保護することに加えて、Microsoft は暗号化テクノロジを使用して、転送中の Office 365 顧客データを保護します。</span><span class="sxs-lookup"><span data-stu-id="b9704-104">In addition to protecting customer data at rest, Microsoft uses encryption technologies to protect Office 365 customer data in transit.</span></span> 

<span data-ttu-id="b9704-105">データの送信中:</span><span class="sxs-lookup"><span data-stu-id="b9704-105">Data is in transit:</span></span>

- <span data-ttu-id="b9704-106">クライアントコンピューターが Office 365 サーバーと通信する場合</span><span class="sxs-lookup"><span data-stu-id="b9704-106">when a client machine communicates with an Office 365 server;</span></span>
- <span data-ttu-id="b9704-107">office 365 サーバーが別の office 365 サーバーと通信する場合。そして</span><span class="sxs-lookup"><span data-stu-id="b9704-107">when an Office 365 server communicates with another Office 365 server; and</span></span>
- <span data-ttu-id="b9704-108">office 365 サーバーが office 以外の365サーバーと通信する場合 (Exchange Online が電子メールを外部電子メールサーバーに配信する場合など)。</span><span class="sxs-lookup"><span data-stu-id="b9704-108">when an Office 365 server communicates with a non-Office 365 server (e.g., Exchange Online delivering email to a foreign email server).</span></span>

<span data-ttu-id="b9704-109">Office 365 サーバー間のデータセンター間通信は tls または IPsec 経由で行われ、すべてのお客様向けのサーバーは、クライアントマシンとの tls を使用してセキュリティで保護されたセッションをネゴシエートします (例: Exchange Online では、256ビットの暗号強度で tls 1.2 が使用されます) (FIPS140-2 レベル 2-検証)。</span><span class="sxs-lookup"><span data-stu-id="b9704-109">Inter-datacenter communications between Office 365 servers takes place over TLS or IPsec, and all customer-facing servers negotiate a secure session using TLS with client machines (e.g., Exchange Online uses TLS 1.2 with 256-bit cipher strength is used (FIPS 140-2 Level 2-validated).</span></span> <span data-ttu-id="b9704-110">(office 365 でサポートされている TLS 暗号スイートの一覧については、「 [office 365 の暗号化に関する技術リファレンスの詳細](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221)」を参照してください)。これは、outlook、Skype for business、web 上の outlook などのクライアントによって使用されるプロトコル (例: HTTP、POP3 など) に適用されます。</span><span class="sxs-lookup"><span data-stu-id="b9704-110">(See [Technical reference details about encryption in Office 365](https://support.office.com/article/Technical-reference-details-about-encryption-in-Office-365-862CBE93-4268-4EF9-BA79-277545ECF221) for a list of TLS cipher suites supported by Office 365.) This applies to the protocols that are used by clients such as Outlook, Skype for Business, and Outlook on the web (e.g., HTTP, POP3, etc.).</span></span>

<span data-ttu-id="b9704-111">公開証明書は、microsoft IT SSL によって発行された microsoft IT SSL で、送信された情報の機密性を保護するための内部 microsoft ツールです。</span><span class="sxs-lookup"><span data-stu-id="b9704-111">The public certificates are issued by Microsoft IT SSL using SSLAdmin, an internal Microsoft tool to protect confidentiality of transmitted information.</span></span> <span data-ttu-id="b9704-112">microsoft によって発行されるすべての証明書の長さは2048ビットです。また、 [webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf)コンプライアンスでは、証明書が microsoft によって所有されるパブリック IP アドレスにのみ発行されるようにするために、ssladmin が必要になります。</span><span class="sxs-lookup"><span data-stu-id="b9704-112">All certificates issued by Microsoft IT have a minimum of 2048 bits in length, and [Webtrust](http://www.webtrust.org/homepage-documents/item70372.pdf) compliance requires SSLAdmin to make sure that certificates are issued only to public IP addresses owned by Microsoft.</span></span> <span data-ttu-id="b9704-113">この条件を満たすことができない IP アドレスは、例外プロセスを経由してルーティングされます。</span><span class="sxs-lookup"><span data-stu-id="b9704-113">Any IP addresses that fail to meet this criterion are routed through an exception process.</span></span>

<span data-ttu-id="b9704-114">使用されている TLS のバージョン、転送機密性 (FS) が有効になっているかどうか、暗号スイートの順番など、すべての実装の詳細を公開できます。</span><span class="sxs-lookup"><span data-stu-id="b9704-114">All implementation details such as the version of TLS being used, whether Forward Secrecy (FS) is enabled, the order of cipher suites, etc., are available publicly.</span></span> <span data-ttu-id="b9704-115">これらの詳細を確認する方法の1つは、Qualys SSL Labs (www.ssllabs.com) などのサードパーティの web サイトを使用することです。</span><span class="sxs-lookup"><span data-stu-id="b9704-115">One way to see these details is to use a third-party website, such as Qualys SSL Labs (www.ssllabs.com).</span></span> <span data-ttu-id="b9704-116">次のサービスの情報を表示する Qualys からの自動テストページへのリンクを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="b9704-116">Below are the links to automated test pages from Qualys that display information for the following services:</span></span>

- [<span data-ttu-id="b9704-117">Office 365 ポータル</span><span class="sxs-lookup"><span data-stu-id="b9704-117">Office 365 Portal</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [<span data-ttu-id="b9704-118">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b9704-118">Exchange Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [<span data-ttu-id="b9704-119">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b9704-119">SharePoint Online</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [<span data-ttu-id="b9704-120">Skype for business (SIP)</span><span class="sxs-lookup"><span data-stu-id="b9704-120">Skype for Business (SIP)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [<span data-ttu-id="b9704-121">Skype for business (Web)</span><span class="sxs-lookup"><span data-stu-id="b9704-121">Skype for Business (Web)</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [<span data-ttu-id="b9704-122">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b9704-122">Exchange Online Protection</span></span>](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [<span data-ttu-id="b9704-123">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9704-123">Microsoft Teams</span></span>](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

<span data-ttu-id="b9704-124">Exchange Online Protection の場合、url はテナント名によって異なります。ただし、すべてのお客様は、 **microsoft-com.mail.protection.outlook.com**を使用して Office 365 をテストできます。</span><span class="sxs-lookup"><span data-stu-id="b9704-124">For Exchange Online Protection, URLs vary by tenant names; however, all customers can test Office 365 using **microsoft-com.mail.protection.outlook.com**.</span></span>
