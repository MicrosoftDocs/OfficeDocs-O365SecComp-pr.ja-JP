---
title: Exchange Online でのメッセージの署名と暗号化の S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理者は、Exchange Online で S/MIME を使用する方法について説明します。
ms.openlocfilehash: 163ae5686adf934f07ee26717fa0b4998ddf3363
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296800"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a><span data-ttu-id="5e3a8-103">Exchange Online でのメッセージの署名と暗号化の S/MIME</span><span class="sxs-lookup"><span data-stu-id="5e3a8-103">S/MIME for message signing and encryption in Exchange Online</span></span>

<span data-ttu-id="5e3a8-p101">S/MIME (セキュリティ保護された/汎用インターネットメール内線番号) は、デジタル署名および暗号化されたメッセージを送信するための、広く使用されている方法 (厳密にはプロトコル) です。S/MIME では、電子メールを暗号化し、デジタル署名することができます。S/MIME を電子メールメッセージと共に使用すると、そのメッセージを受信したユーザーは、受信トレイに表示される内容が送信者から始まる正確なメッセージであることを確認するのに役立ちます。また、メッセージを受信したユーザーが特定の送信者からのメッセージではなく、送信者として偽装していることを確認できるようにすることもできます。これを行うために、S/MIME は認証、メッセージの整合性、送信元の否認不可 (デジタル署名を使用) などの暗号化セキュリティサービスを提供します。また、電子メールメッセージのプライバシーとデータセキュリティ (暗号化を使用) を強化するのにも役に立ちます。電子メールのコンテキストでの s/mime の履歴とアーキテクチャについての詳細な背景情報については、「 [s/mime につい](https://go.microsoft.com/fwlink/?LinkID=393948)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p101">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method (or more precisely, a protocol) for sending digitally signed and encrypted messages. S/MIME allows you to encrypt emails and digitally sign them. When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender. It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender. To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures). It also helps enhance privacy and data security (using encryption) for electronic messaging. For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span>

<span data-ttu-id="5e3a8-p102">Exchange Online 管理者は、組織内のメールボックスに対して S/MIME ベースのセキュリティを有効にすることができます。ここでリンクされているトピックのガイダンスを Exchange Online PowerShell と共に使用して、S/MIME を設定します。サポートされている電子メールクライアントで S/MIME を使用するには、組織内のユーザーに、署名と暗号化のために発行された証明書と、オンプレミスの Active Directory ドメインサービス (AD DS) に公開されたデータを含める必要があります。AD DS は、インターネット上のリモート施設またはクラウドベースのサービスではなく、自分が管理する物理的な場所にあるコンピューター上に配置する必要があります。AD DS の詳細については、「 [Active Directory ドメインサービス](https://go.microsoft.com/fwlink/?LinkID=394064)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p102">As an Exchange Online admin, you can enable S/MIME-based security for the mailboxes in your organization. Use the guidance in the topics linked here along with Exchange Online PowerShell to set up S/MIME. To use S/MIME in supported email clients, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS). Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet. For more information about AD DS, see [Active Directory Domain Services](https://go.microsoft.com/fwlink/?LinkID=394064).</span></span>

## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="5e3a8-116">サポートされるシナリオと技術的な考慮事項</span><span class="sxs-lookup"><span data-stu-id="5e3a8-116">Supported scenarios and technical considerations</span></span>

<span data-ttu-id="5e3a8-117">次の任意のエンドポイントで機能するように S/MIME をセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-117">You can set up S/MIME to work with any of the following end points:</span></span>

- <span data-ttu-id="5e3a8-118">Outlook 2010 以降</span><span class="sxs-lookup"><span data-stu-id="5e3a8-118">Outlook 2010 or later</span></span>

- <span data-ttu-id="5e3a8-119">Web 上の Outlook (旧称 Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="5e3a8-119">Outlook on the web (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="5e3a8-120">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="5e3a8-120">Exchange ActiveSync (EAS)</span></span>

<span data-ttu-id="5e3a8-p103">これらの各エンドポイントを使用して S/MIME をセットアップする手順は、次の手順で少し異なります。通常は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p103">The steps that you follow to set up S/MIME with each of these end points is slightly different. Generally, you will need to do the following steps:</span></span>

- <span data-ttu-id="5e3a8-p104">Windows ベースの証明機関をインストールし、S/MIME 証明書を発行するための公開キー基盤を設定します。サードパーティの証明書プロバイダーによって発行された証明書もサポートされています。詳細については、「 [Active Directory 証明書サービスの概要](https://technet.microsoft.com/library/hh831740.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p104">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates. Certificates issued by third-party certificate providers are also supported. For details, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx).</span></span>

- <span data-ttu-id="5e3a8-126">**UserSMIMECertificate**または**usercertificate**属性で、社内 AD DS アカウントでユーザー証明書を公開します。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-126">Publish the user certificate in an on-premises AD DS account in the **UserSMIMECertificate** and/or **UserCertificate** attributes.</span></span>

- <span data-ttu-id="5e3a8-p105">Exchange Online 組織の場合は、適切なバージョンの DirSync を使用して、ユーザー証明書を AD DS から Azure Active Directory に同期させます。これらの証明書は、Azure Active directory から Exchange Online ディレクトリに同期され、受信者へのメッセージの暗号化時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p105">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync. These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>

- <span data-ttu-id="5e3a8-p106">S/MIME を検証するためには、仮想の証明書のコレクションを設定します。この情報は、電子メールの署名を検証する際に Web 上の Outlook により使用され、そのメールが信頼される証明書により署名されたことが確認されます。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p106">Set up a virtual certificate collection in order to validate S/MIME. This information is used by Outlook on the web when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>

- <span data-ttu-id="5e3a8-131">S/MIME を使用する Outlook エンド ポイントまたは EAS エンド ポイントを設定します。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-131">Set up the Outlook or EAS end point to use S/MIME.</span></span>

## <a name="setup-smime-with-outlook-on-the-web"></a><span data-ttu-id="5e3a8-132">Outlook on the web で S/MIME をセットアップする</span><span class="sxs-lookup"><span data-stu-id="5e3a8-132">Setup S/MIME with Outlook on the web</span></span>

<span data-ttu-id="5e3a8-133">Outlook on the web を使用して Exchange Online の S/MIME をセットアップするには、次の主要な手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-133">Setting up S/MIME for Exchange Online with Outlook on the web involves the following key steps:</span></span>

1. [<span data-ttu-id="5e3a8-134">Outlook on the web の S/MIME 設定を構成する</span><span class="sxs-lookup"><span data-stu-id="5e3a8-134">Configure S/MIME settings for Outlook on the web</span></span>](configure-s-mime-settings-for-outlook-web-app.md)

2. [<span data-ttu-id="5e3a8-135">S/MIME を検証するための仮想証明書コレクションを設定する</span><span class="sxs-lookup"><span data-stu-id="5e3a8-135">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [<span data-ttu-id="5e3a8-136">S/MIME 用にユーザー証明書を Office 365 に同期させる</span><span class="sxs-lookup"><span data-stu-id="5e3a8-136">Sync user certificates to Office 365 for S/MIME</span></span>](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a><span data-ttu-id="5e3a8-137">関連するメッセージ暗号化テクノロジ</span><span class="sxs-lookup"><span data-stu-id="5e3a8-137">Related message encryption technologies</span></span>

<span data-ttu-id="5e3a8-p107">メッセージセキュリティがより重要になると、管理者はセキュリティで保護されたメッセージングの原則と概念を理解する必要があります。利用可能なさまざまな保護関連テクノロジ (S/MIME を含む) があるため、この点を理解することは特に重要です。s/mime の詳細と、電子メールのコンテキストでの動作の詳細については、「 [s/mime につい](https://go.microsoft.com/fwlink/?LinkID=393948)て」を参照してください。さまざまな暗号化テクノロジが連携して、保存中のメッセージと送信中のメッセージに対する保護を提供します。S/MIME は、次のテクノロジと同時に機能しますが、それらに依存するものではありません。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p107">As message security becomes more important, admins need to understand the principles and concepts of secure messaging. This understanding is especially important because of the growing variety of protection-related technologies (including S/MIME) that are available. To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). A variety of encryption technologies work together to provide protection for messages at rest and in-transit. S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>

- <span data-ttu-id="5e3a8-143">**トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-143">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span>

- <span data-ttu-id="5e3a8-144">**Secure Sockets Layer (SSL)** は、電子メール クライアントと Office 365 サーバーとの間の接続を暗号化します。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-144">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span>

- <span data-ttu-id="5e3a8-145">**BitLocker**は、データセンターのハードディスク上のデータを暗号化して、第三者が許可されていないアクセス権を取得した場合でも読み取りできないようにします。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-145">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span>

### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="5e3a8-146">S/MIME と Office 365 のメッセージ暗号化との比較</span><span class="sxs-lookup"><span data-stu-id="5e3a8-146">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="5e3a8-p108">S/MIME には、企業間および企業間の状況でよく使用される証明書と発行のインフラストラクチャが必要です。ユーザーは S/MIME の暗号化キーを制御し、送信する各メッセージにそれらを使用するかどうかを選択できます。Outlook などの電子メールプログラムは、信頼できるルート証明機関の場所を検索して、デジタル署名と署名の検証を実行します。Office 365 Message encryption は、個々のユーザーではなく、組織内外のすべてのユーザーに送信されるメールを暗号化するために、管理者が構成できるポリシーベースの暗号化サービスです。Azure Rights Management (RMS) 上に構築されているオンラインサービスであり、公開キー基盤に依存していません。Office 365 メッセージの暗号化では、組織のブランドを使用してメールをカスタマイズする機能など、追加機能も提供されます。office 365 メッセージの暗号化の詳細については、「 [office 365 message encryption](https://go.microsoft.com/fwlink/?LinkID=392525)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e3a8-p108">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations. The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send. Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature. Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization. It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure. Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand. For more information about Office 365 Message Encryption, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).</span></span>

## <a name="more-information"></a><span data-ttu-id="5e3a8-154">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5e3a8-154">More information</span></span>

[<span data-ttu-id="5e3a8-155">Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="5e3a8-155">Outlook on the web</span></span>](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[<span data-ttu-id="5e3a8-156">セキュリティで保護されたメール (2000)</span><span class="sxs-lookup"><span data-stu-id="5e3a8-156">Secure Mail (2000)</span></span>](https://technet.microsoft.com/en-us/library/cc962043.aspx)
