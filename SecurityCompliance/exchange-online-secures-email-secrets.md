---
title: Exchange Online が電子メールの機密情報をセキュリティで保護する方法
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。 Distributed Key Manager (DKM) というテクノロジを使用しています。
ms.openlocfilehash: ba4c661899273f5e07c2468631298f5500d0e32f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255485"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="6efd1-104">Exchange Online が電子メールの機密情報をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="6efd1-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="6efd1-105">この記事では、Microsoft が電子メールの機密情報をデータセンターにセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="6efd1-106">自分が提供する機密情報をセキュリティで保護するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="6efd1-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="6efd1-107">office [365 のセキュリティ、プライバシー、コンプライアンス情報](https://go.microsoft.com/fwlink/?linkid=874644)を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efd1-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="6efd1-108">Distributed Key Manager (DKM) というテクノロジを使用しています。</span><span class="sxs-lookup"><span data-stu-id="6efd1-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="6efd1-109">Distributed Key Manager (DKM) は、一連の秘密キーを使用して情報を暗号化および復号化するクライアント側の機能です。</span><span class="sxs-lookup"><span data-stu-id="6efd1-109">Distributed Key Manager (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="6efd1-110">Active Directory ドメインサービス内の特定のセキュリティグループのメンバーのみが、DKM によって暗号化されたデータを復号化するためにこれらのキーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="6efd1-111">Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="6efd1-112">データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="6efd1-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="6efd1-113">デバッグ、トラブルシューティング、または監査を目的として、データセンター管理者は、セキュリティグループの一部である一時的な資格情報を取得するために、昇格されたアクセスを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6efd1-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="6efd1-114">このプロセスでは、複数レベルの法的な承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="6efd1-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="6efd1-115">アクセスが許可された場合、すべてのアクティビティがログに記録され、監査されます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="6efd1-116">さらに、アクセスが自動的に期限切れになるように設定された時間間隔に対してのみアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="6efd1-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="6efd1-117">追加の保護では、DKM テクノロジにキーのロールオーバーとアーカイブが自動化されています。</span><span class="sxs-lookup"><span data-stu-id="6efd1-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="6efd1-118">これにより、同じキーを無期限に使用しなくても、古いコンテンツに継続してアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="6efd1-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="6efd1-119">Exchange Online は、DKM を利用しますか?</span><span class="sxs-lookup"><span data-stu-id="6efd1-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="6efd1-120">Microsoft では、DKM を使用して Exchange Online データセンター内の機密情報を暗号化しています。</span><span class="sxs-lookup"><span data-stu-id="6efd1-120">Microsoft uses DKM to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="6efd1-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="6efd1-121">For example:</span></span>
  
- <span data-ttu-id="6efd1-122">接続されたアカウントの電子メールアカウントの資格情報。</span><span class="sxs-lookup"><span data-stu-id="6efd1-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="6efd1-123">接続されたアカウントは、Hotmail、Gmail、yahoo! などのサードパーティのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="6efd1-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="6efd1-124">メールアカウント。</span><span class="sxs-lookup"><span data-stu-id="6efd1-124">mail accounts.</span></span>
    
- <span data-ttu-id="6efd1-125">Rights Management service (RMS) のルートキー。</span><span class="sxs-lookup"><span data-stu-id="6efd1-125">Rights Management service (RMS) root keys.</span></span> <span data-ttu-id="6efd1-126">これは、Azure rms からインポートされるか、rms または Office 365 のメッセージ暗号化 (OME) で電子メールの暗号化と復号化に使用される、社内の Active Directory ドメインサービス RMS 展開からインポートされる顧客キーです。</span><span class="sxs-lookup"><span data-stu-id="6efd1-126">These are customer keys that are either imported from Azure RMS or from customer's on-premises Active Directory Domain Services RMS deployments that are used for encrypting and decrypting emails with RMS or Office 365 Message Encryption (OME).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="6efd1-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6efd1-127">Related topics</span></span>

[<span data-ttu-id="6efd1-128">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="6efd1-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="6efd1-129">Office 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="6efd1-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="6efd1-130">Office 365 セキュリティ&amp; /コンプライアンスセンターのサービスアシュアランス</span><span class="sxs-lookup"><span data-stu-id="6efd1-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

