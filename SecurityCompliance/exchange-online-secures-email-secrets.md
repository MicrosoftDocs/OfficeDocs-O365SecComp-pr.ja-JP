---
title: Exchange Online が電子メールの機密情報をセキュリティで保護する方法
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: だけでなく、Office 365 信頼センター Office 365 のセキュリティ、プライバシー、およびコンプライアンス情報を提供することもできます Office 365 がどのように役立つかを知っている、データ センターで提供する機密情報を保護します。分散キー マネージャー (DKM) と呼ばれるテクノロジを使用します。
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/27/2018
ms.locfileid: "22532673"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="48ad2-104">Exchange Online が電子メールの機密情報をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="48ad2-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="48ad2-105">この記事では、Microsoft がデータ センターの電子メールの機密情報をセキュリティで保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="48ad2-106">ユーザーの機密情報をセキュリティで保護する方法</span><span class="sxs-lookup"><span data-stu-id="48ad2-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="48ad2-p102">だけでなく、Office 365 信頼センター[セキュリティ、プライバシー、および Office 365 のコンプライアンス情報](https://go.microsoft.com/fwlink/?linkid=874644)を提供することもできます Office 365 がどのように役立つかを知っている、データ センターで提供する機密情報を保護します。分散キー マネージャー (DKM) と呼ばれるテクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="48ad2-p102">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters. We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="48ad2-p103">分散キー マネージャー (DKM) は、一連の秘密キーを使用して情報を暗号化および復号化するクライアント側の機能です。Active Directory ドメイン サービス内の特定のセキュリティ グループのメンバーのみが、DKM によって暗号化されたデータを解読するためにこれらのキーにアクセスできます。Exchange Online では Exchange プロセスの実行に使用する特定のサービス アカウントだけが、そのセキュリティ グループに属します。データセンター内の標準運用手順の一環として、このセキュリティ グループに属する資格情報は人間には付与されないため、人間はだれもこれらの機密情報を解読できるキーにアクセスできません。</span><span class="sxs-lookup"><span data-stu-id="48ad2-p103">Distributed Key Manager (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information. Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM. In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group. As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="48ad2-p104">デバッグ、トラブルシューティング、または監査目的のためには、セキュリティ グループに属する一時的な資格情報を取得するために、データセンターの管理者が昇格されたアクセス権限を要求する必要があります。このプロセスには複数レベルの法的な承認が必要です。アクセス権限が与えられると、すべての処理がログに記録され、監査の対象となります。さらに、アクセス権限は一定期間のみ付与され、その期間が過ぎると自動的に期限切れになります。</span><span class="sxs-lookup"><span data-stu-id="48ad2-p104">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group. This process requires multiple levels of legal approval. If access is granted, all activity is logged and audited. In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="48ad2-p105">さらに保護を強化するために、DKM テクノロジには自動化されたキー ロール オーバーとアーカイブがあります。この機能によってもまた、同じキーに無期限に依存する必要なく、古いコンテンツへ引き続きアクセスできることが保証されます。
</span><span class="sxs-lookup"><span data-stu-id="48ad2-p105">For extra protection, DKM technology includes automated key rollover and archiving. This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="48ad2-119">Exchange Online での DKM の利用</span><span class="sxs-lookup"><span data-stu-id="48ad2-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="48ad2-p106">Microsoft は、Exchange Online データセンター内の機密情報を暗号化するのに DKM を使用します。例をあげます。</span><span class="sxs-lookup"><span data-stu-id="48ad2-p106">Microsoft uses DKM to encrypt your secrets in Exchange Online datacenters. For example:</span></span>
  
- <span data-ttu-id="48ad2-p107">接続されたアカウントの電子メール アカウントの資格情報。接続されるアカウントは、Hotmail、Gmail、Yahoo! メール アカウントなど、サード パーティのアカウントです。</span><span class="sxs-lookup"><span data-stu-id="48ad2-p107">Email account credentials for connected accounts. Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo! mail accounts.</span></span>
    
- <span data-ttu-id="48ad2-p108">権限管理サービス (RMS) のルート キーをします。これらは、Azure の RMS または RMS または Office 365 メッセージの暗号化 (ホーム) で電子メールを暗号化および暗号化に使用されるお客様のオンプレミスの Active Directory ドメイン サービスの RMS 展開からをインポートするかは、お客様のキーです。</span><span class="sxs-lookup"><span data-stu-id="48ad2-p108">Rights Management service (RMS) root keys. These are customer keys that are either imported from Azure RMS or from customer's on-premises Active Directory Domain Services RMS deployments that are used for encrypting and decrypting emails with RMS or Office 365 Message Encryption (OME).</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="48ad2-127">関連項目</span><span class="sxs-lookup"><span data-stu-id="48ad2-127">Related topics</span></span>

[<span data-ttu-id="48ad2-128">Office 365 での暗号化</span><span class="sxs-lookup"><span data-stu-id="48ad2-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="48ad2-129">Office 365 の暗号化についてのテクニカル リファレンスの詳細</span><span class="sxs-lookup"><span data-stu-id="48ad2-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="48ad2-130">サービスの Office 365 のセキュリティの保証&amp;コンプライアンス センター</span><span class="sxs-lookup"><span data-stu-id="48ad2-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

