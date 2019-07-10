---
title: Exchange Online が電子メールの機密情報をセキュリティで保護する方法
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Office 365 のセキュリティ、プライバシー、コンプライアンス情報を提供する Office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。 Distributed Key Manager (DKM) というテクノロジを使用しています。
ms.openlocfilehash: 8350785968c68b22c58be17ec68d94ff908c95d9
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599433"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="83d51-104">Exchange Online が電子メールの機密情報をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="83d51-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="83d51-105">この記事では、Microsoft が電子メールの機密情報をデータセンターにセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="83d51-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="83d51-106">自分が提供する機密情報をセキュリティで保護するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="83d51-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="83d51-107">Office [365 のセキュリティ、プライバシー、コンプライアンス情報](https://go.microsoft.com/fwlink/?linkid=874644)を提供する office 365 セキュリティセンターに加えて、office 365 がデータセンターで提供する機密情報を保護する方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d51-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="83d51-108">Distributed Key Manager (DKM) というテクノロジを使用しています。</span><span class="sxs-lookup"><span data-stu-id="83d51-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="83d51-109">[分散キーマネージャー](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)(DKM) は、一連の秘密キーを使用して情報を暗号化および復号化するクライアント側の機能です。</span><span class="sxs-lookup"><span data-stu-id="83d51-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="83d51-110">Active Directory ドメインサービス内の特定のセキュリティグループのメンバーのみが、DKM によって暗号化されたデータを復号化するためにこれらのキーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="83d51-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="83d51-111">Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。</span><span class="sxs-lookup"><span data-stu-id="83d51-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="83d51-112">データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="83d51-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="83d51-113">デバッグ、トラブルシューティング、または監査を目的として、データセンター管理者は、セキュリティグループの一部である一時的な資格情報を取得するために、昇格されたアクセスを要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83d51-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="83d51-114">このプロセスでは、複数レベルの法的な承認が必要です。</span><span class="sxs-lookup"><span data-stu-id="83d51-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="83d51-115">アクセスが許可された場合、すべてのアクティビティがログに記録され、監査されます。</span><span class="sxs-lookup"><span data-stu-id="83d51-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="83d51-116">さらに、アクセスが自動的に期限切れになるように設定された時間間隔に対してのみアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="83d51-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="83d51-117">追加の保護では、DKM テクノロジにキーのロールオーバーとアーカイブが自動化されています。</span><span class="sxs-lookup"><span data-stu-id="83d51-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="83d51-118">これにより、同じキーを無期限に使用しなくても、古いコンテンツに継続してアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="83d51-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="83d51-119">Exchange Online は、DKM を利用しますか?</span><span class="sxs-lookup"><span data-stu-id="83d51-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="83d51-120">Microsoft では、[分散キーマネージャー](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)を使用して Exchange Online データセンター内の機密情報を暗号化しています。</span><span class="sxs-lookup"><span data-stu-id="83d51-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="83d51-121">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="83d51-121">For example:</span></span>
  
- <span data-ttu-id="83d51-122">接続されたアカウントの電子メールアカウントの資格情報。</span><span class="sxs-lookup"><span data-stu-id="83d51-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="83d51-123">接続されたアカウントは、Hotmail、Gmail、Yahoo! などのサードパーティのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="83d51-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="83d51-124">メールアカウント。</span><span class="sxs-lookup"><span data-stu-id="83d51-124">mail accounts.</span></span>
    
- <span data-ttu-id="83d51-125">顧客キー。</span><span class="sxs-lookup"><span data-stu-id="83d51-125">Customer key.</span></span> <span data-ttu-id="83d51-126">[Office 365 で顧客キー](controlling-your-data-using-customer-key.md)を使用している場合は、 [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)を使用して機密情報を保護します。</span><span class="sxs-lookup"><span data-stu-id="83d51-126">If you are using [Customer Key in Office 365](controlling-your-data-using-customer-key.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="83d51-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="83d51-127">Related topics</span></span>

[<span data-ttu-id="83d51-128">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="83d51-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="83d51-129">Office 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="83d51-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="83d51-130">Office 365 セキュリティ&amp; /コンプライアンスセンターのサービスアシュアランス</span><span class="sxs-lookup"><span data-stu-id="83d51-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

